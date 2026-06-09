# FsmTimeout

- ea: `0x18000c8d4`
- end: `0x18000cc74`
- name: `FsmTimeout`
- size: `928`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800023c0`
- `0x180003170`
- `0x18000442c`
- `0x18000c8d4`
- `0x18000d6b4`
- `0x18000e358`
- `0x18000e7a4`
- `0x180011230`
- `0x1800115d0`
- `0x18001348c`
- `0x180013b54`
- `0x18002b0dc`

## string_xrefs

- `0x18000c93e`: `Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d`

## pseudocode

```c
unsigned int __fastcall FsmTimeout(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v5; // rbp
  int *PointerToCPCB; // rdi
  unsigned int result; // eax
  __int64 v10; // r15
  __int64 v11; // r8
  unsigned __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // eax
  int v22; // [rsp+40h] [rbp-848h] BYREF
  _BYTE v23[2044]; // [rsp+44h] [rbp-844h] BYREF

  v5 = (unsigned int)a2;
  v22 = 0;
  PointerToCPCB = (int *)GetPointerToCPCB(a1, a2);
  result = (unsigned int)memset_0(v23, 0, sizeof(v23));
  if ( !PointerToCPCB )
    return result;
  v10 = *(_QWORD *)(a1 + 1472);
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v11 = *(unsigned int *)(a1 + 64);
    LOWORD(v22) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v22,
      L"Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d",
      v11,
      a3,
      *((_DWORD *)CpTable + 44 * v5),
      a4);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v22);
  }
  result = GetCpIndexFromProtocol(*(_DWORD *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFF38uLL) + v10 + 1420));
  if ( (_DWORD)v5 == result )
  {
    if ( *(_DWORD *)(a1 + 48) == 1 )
    {
      result = -a4;
      if ( a3 >= *(_DWORD *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFC0uLL) + a1 + 1400) )
      {
        v12 = -(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFC0uLL;
        v13 = *(_DWORD *)(v12 + a1 + 1416);
        if ( v13 )
        {
          *(_DWORD *)(v12 + a1 + 1416) = v13 - 1;
          return ApWork(a1, v5, 0, 0, a4);
        }
        else
        {
          v14 = *(_DWORD *)(a1 + 1496);
          if ( !v14 )
          {
            v14 = 718;
            *(_DWORD *)(a1 + 1496) = 718;
          }
          return NotifyCallerOfFailure(a1, v14);
        }
      }
    }
    return result;
  }
  result = GetCpIndexFromProtocol(49193);
  if ( (_DWORD)v5 == result && *(_DWORD *)(a1 + 48) == 2 )
  {
    if ( a3 < PointerToCPCB[2] )
      return result;
    v15 = PointerToCPCB[6];
    if ( v15 )
    {
      PointerToCPCB[6] = v15 - 1;
      result = CbWork(a1, (unsigned int)v5, 0, 0);
    }
    else
    {
      v16 = *(unsigned int *)(a1 + 1496);
      if ( !(_DWORD)v16 )
      {
        *(_DWORD *)(a1 + 1496) = 718;
        v16 = 718;
      }
      result = NotifyCallerOfFailure(a1, v16);
    }
  }
  if ( a3 >= PointerToCPCB[2] )
  {
    v17 = *PointerToCPCB;
    if ( *PointerToCPCB <= 5 )
    {
      if ( v17 == 5 || v17 == 4 )
      {
        v18 = PointerToCPCB[7];
        if ( v18 )
        {
          PointerToCPCB[7] = v18 - 1;
          return FsmSendTermReq(a1, (unsigned int)v5);
        }
        else
        {
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"Terminate retry exceeded");
          if ( !PointerToCPCB[10] )
            PointerToCPCB[10] = 718;
          result = FsmThisLayerFinished(a1, v5, 1);
          if ( result )
          {
            result = (*PointerToCPCB != 4) + 2;
            *PointerToCPCB = result;
          }
        }
        return result;
      }
      goto LABEL_35;
    }
    v19 = v17 - 6;
    if ( v19 && (unsigned int)(v19 - 1) >= 2 )
    {
LABEL_35:
      if ( byte_18004DF33 < 0 )
      {
        LOWORD(v22) = 0;
        result = FormatRRASErrorString(
                   (wchar_t *)&v22,
                   L"Illegal transition->FsmTimeout rcvd while in %hs state",
                   FsmStates[*PointerToCPCB]);
        if ( byte_18004DF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v22);
      }
      return result;
    }
    v20 = PointerToCPCB[6];
    if ( v20 )
    {
      PointerToCPCB[6] = v20 - 1;
      if ( !(_DWORD)v5 && *(_DWORD *)(a1 + 1496) == 721 && (*(_BYTE *)(a1 + 56) & 4) == 0 )
        NotifyCaller(a1, 9u, 0);
      v21 = *(_DWORD *)(a1 + 36);
      if ( v21 < dword_18004D9E8 )
        *(_DWORD *)(a1 + 36) = v21 + 1;
      result = FsmSendConfigReq(a1, (unsigned int)v5);
      if ( result && *PointerToCPCB != 8 )
        *PointerToCPCB = 6;
    }
    else
    {
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceError,
          L"Request retry exceeded");
      if ( !PointerToCPCB[10] )
        PointerToCPCB[10] = 718;
      result = FsmThisLayerFinished(a1, v5, 1);
      if ( result )
        *PointerToCPCB = 3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c8d4  push    rbx
0x18000c8d6  push    rbp
0x18000c8d7  push    rsi
0x18000c8d8  push    rdi
0x18000c8d9  push    r14
0x18000c8db  push    r15
0x18000c8dd  sub     rsp, 858h
0x18000c8e4  mov     rax, cs:__security_cookie
0x18000c8eb  xor     rax, rsp
0x18000c8ee  mov     [rsp+888h+var_48], rax
0x18000c8f6  mov     esi, r9d
0x18000c8f9  mov     ebp, edx
0x18000c8fb  mov     r14d, r8d
0x18000c8fe  mov     rbx, rcx
0x18000c901  call    GetPointerToCPCB
0x18000c906  xor     ecx, ecx
0x18000c908  xor     edx, edx; Val
0x18000c90a  mov     [rsp+888h+var_848], ecx
0x18000c90e  mov     r8d, 7FCh; Size
0x18000c914  lea     rcx, [rsp+888h+var_844]; void *
0x18000c919  mov     rdi, rax
0x18000c91c  call    memset_0
0x18000c921  test    rdi, rdi
0x18000c924  jz      loc_18000CC53
0x18000c92a  test    cs:byte_18004DF34, 1
0x18000c931  mov     r15, [rbx+5C0h]
0x18000c938  jz      short loc_18000C993
0x18000c93a  mov     r8d, [rbx+40h]
0x18000c93e  lea     rdx, aRecvTimeoutEve; "Recv timeout event received for portid="...
0x18000c945  xor     eax, eax
0x18000c947  mov     [rsp+888h+var_860], esi
0x18000c94b  mov     word ptr [rsp+888h+var_848], ax
0x18000c950  mov     r9d, r14d
0x18000c953  mov     rax, cs:CpTable
0x18000c95a  imul    rcx, rbp, 0B0h
0x18000c961  mov     ecx, [rcx+rax]
0x18000c964  mov     [rsp+888h+var_868], ecx
0x18000c968  lea     rcx, [rsp+888h+var_848]
0x18000c96d  call    FormatRRASErrorString
0x18000c972  test    cs:byte_18004DF34, 1
0x18000c979  jz      short loc_18000C993
0x18000c97b  lea     r8, [rsp+888h+var_848]
0x18000c980  lea     rdx, RasPppTraceInfo
0x18000c987  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c98e  call    McTemplateU0z_EventWriteTransfer
0x18000c993  mov     eax, esi
0x18000c995  neg     eax
0x18000c997  sbb     rcx, rcx
0x18000c99a  and     rcx, 0FFFFFFFFFFFFFF38h
0x18000c9a1  mov     ecx, [rcx+r15+58Ch]
0x18000c9a9  call    GetCpIndexFromProtocol
0x18000c9ae  cmp     ebp, eax
0x18000c9b0  jnz     loc_18000CA37
0x18000c9b6  cmp     dword ptr [rbx+30h], 1
0x18000c9ba  jnz     loc_18000CC53
0x18000c9c0  mov     eax, esi
0x18000c9c2  neg     eax
0x18000c9c4  sbb     rcx, rcx
0x18000c9c7  and     rcx, 0FFFFFFFFFFFFFFC0h
0x18000c9cb  cmp     r14d, [rcx+rbx+578h]
0x18000c9d3  jb      loc_18000CC53
0x18000c9d9  mov     eax, esi
0x18000c9db  neg     eax
0x18000c9dd  sbb     r8, r8
0x18000c9e0  and     r8, 0FFFFFFFFFFFFFFC0h
0x18000c9e4  mov     eax, [r8+rbx+588h]
0x18000c9ec  test    eax, eax
0x18000c9ee  jz      short loc_18000CA13
0x18000c9f0  dec     eax
0x18000c9f2  mov     [rsp+888h+var_868], esi
0x18000c9f6  mov     [r8+rbx+588h], eax
0x18000c9fe  xor     r9d, r9d
0x18000ca01  xor     r8d, r8d
0x18000ca04  mov     edx, ebp
0x18000ca06  mov     rcx, rbx
0x18000ca09  call    ApWork
0x18000ca0e  jmp     loc_18000CC53
0x18000ca13  mov     esi, [rbx+5D8h]
0x18000ca19  test    esi, esi
0x18000ca1b  jnz     short loc_18000CA28
0x18000ca1d  mov     esi, 2CEh
0x18000ca22  mov     [rbx+5D8h], esi
0x18000ca28  mov     edx, esi
0x18000ca2a  mov     rcx, rbx
0x18000ca2d  call    NotifyCallerOfFailure
0x18000ca32  jmp     loc_18000CC53
0x18000ca37  mov     ecx, 0C029h
0x18000ca3c  call    GetCpIndexFromProtocol
0x18000ca41  mov     esi, 2CEh
0x18000ca46  cmp     ebp, eax
0x18000ca48  jnz     short loc_18000CA92
0x18000ca4a  cmp     dword ptr [rbx+30h], 2
0x18000ca4e  jnz     short loc_18000CA92
0x18000ca50  cmp     r14d, [rdi+8]
0x18000ca54  jb      loc_18000CC53
0x18000ca5a  mov     eax, [rdi+18h]
0x18000ca5d  test    eax, eax
0x18000ca5f  jz      short loc_18000CA78
0x18000ca61  dec     eax
0x18000ca63  xor     r9d, r9d
0x18000ca66  xor     r8d, r8d
0x18000ca69  mov     [rdi+18h], eax
0x18000ca6c  mov     edx, ebp
0x18000ca6e  mov     rcx, rbx
0x18000ca71  call    CbWork
0x18000ca76  jmp     short loc_18000CA92
0x18000ca78  mov     edx, [rbx+5D8h]
0x18000ca7e  test    edx, edx
0x18000ca80  jnz     short loc_18000CA8A
0x18000ca82  mov     [rbx+5D8h], esi
0x18000ca88  mov     edx, esi
0x18000ca8a  mov     rcx, rbx
0x18000ca8d  call    NotifyCallerOfFailure
0x18000ca92  cmp     r14d, [rdi+8]
0x18000ca96  jb      loc_18000CC53
0x18000ca9c  mov     ecx, [rdi]
0x18000ca9e  cmp     ecx, 5
0x18000caa1  jg      loc_18000CB46
0x18000caa7  jz      short loc_18000CAD5
0x18000caa9  test    ecx, ecx
0x18000caab  jz      loc_18000CB55
0x18000cab1  sub     ecx, 1
0x18000cab4  jz      loc_18000CB55
0x18000caba  sub     ecx, 1
0x18000cabd  jz      loc_18000CB55
0x18000cac3  sub     ecx, 1
0x18000cac6  jz      loc_18000CB55
0x18000cacc  cmp     ecx, 1
0x18000cacf  jnz     loc_18000CB55
0x18000cad5  mov     eax, [rdi+1Ch]
0x18000cad8  test    eax, eax
0x18000cada  jz      short loc_18000CAF0
0x18000cadc  dec     eax
0x18000cade  mov     edx, ebp
0x18000cae0  mov     rcx, rbx
0x18000cae3  mov     [rdi+1Ch], eax
0x18000cae6  call    FsmSendTermReq
0x18000caeb  jmp     loc_18000CC53
0x18000caf0  test    cs:byte_18004DF33, 80h
0x18000caf7  jz      short loc_18000CB13
0x18000caf9  lea     r8, aTerminateRetry; "Terminate retry exceeded"
0x18000cb00  lea     rdx, RasPppTraceError
0x18000cb07  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cb0e  call    McTemplateU0z_EventWriteTransfer
0x18000cb13  cmp     dword ptr [rdi+28h], 0
0x18000cb17  jnz     short loc_18000CB1C
0x18000cb19  mov     [rdi+28h], esi
0x18000cb1c  mov     r8d, 1
0x18000cb22  mov     edx, ebp
0x18000cb24  mov     rcx, rbx
0x18000cb27  call    FsmThisLayerFinished
0x18000cb2c  test    eax, eax
0x18000cb2e  jz      loc_18000CC53
0x18000cb34  xor     eax, eax
0x18000cb36  cmp     dword ptr [rdi], 4
0x18000cb39  setnz   al
0x18000cb3c  add     eax, 2
0x18000cb3f  mov     [rdi], eax
0x18000cb41  jmp     loc_18000CC53
0x18000cb46  sub     ecx, 6
0x18000cb49  jz      short loc_18000CBB2
0x18000cb4b  sub     ecx, 1
0x18000cb4e  jz      short loc_18000CBB2
0x18000cb50  cmp     ecx, 1
0x18000cb53  jz      short loc_18000CBB2
0x18000cb55  cmp     cs:byte_18004DF33, 0
0x18000cb5c  jge     loc_18000CC53
0x18000cb62  xor     eax, eax
0x18000cb64  lea     rdx, aIllegalTransit; "Illegal transition->FsmTimeout rcvd whi"...
0x18000cb6b  mov     word ptr [rsp+888h+var_848], ax
0x18000cb70  lea     rcx, [rsp+888h+var_848]
0x18000cb75  movsxd  r8, dword ptr [rdi]
0x18000cb78  lea     rax, FsmStates
0x18000cb7f  mov     r8, [rax+r8*8]
0x18000cb83  call    FormatRRASErrorString
0x18000cb88  cmp     cs:byte_18004DF33, 0
0x18000cb8f  jge     loc_18000CC53
0x18000cb95  lea     r8, [rsp+888h+var_848]
0x18000cb9a  lea     rdx, RasPppTraceError
0x18000cba1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cba8  call    McTemplateU0z_EventWriteTransfer
0x18000cbad  jmp     loc_18000CC53
0x18000cbb2  mov     eax, [rdi+18h]
0x18000cbb5  test    eax, eax
0x18000cbb7  jz      short loc_18000CC0D
0x18000cbb9  dec     eax
0x18000cbbb  mov     [rdi+18h], eax
0x18000cbbe  test    ebp, ebp
0x18000cbc0  jnz     short loc_18000CBE2
0x18000cbc2  cmp     dword ptr [rbx+5D8h], 2D1h
0x18000cbcc  jnz     short loc_18000CBE2
0x18000cbce  test    byte ptr [rbx+38h], 4
0x18000cbd2  jnz     short loc_18000CBE2
0x18000cbd4  xor     r8d, r8d
0x18000cbd7  lea     edx, [rbp+9]
0x18000cbda  mov     rcx, rbx
0x18000cbdd  call    NotifyCaller
0x18000cbe2  mov     eax, [rbx+24h]
0x18000cbe5  cmp     eax, cs:dword_18004D9E8
0x18000cbeb  jnb     short loc_18000CBF2
0x18000cbed  inc     eax
0x18000cbef  mov     [rbx+24h], eax
0x18000cbf2  mov     edx, ebp
0x18000cbf4  mov     rcx, rbx
0x18000cbf7  call    FsmSendConfigReq
0x18000cbfc  test    eax, eax
0x18000cbfe  jz      short loc_18000CC53
0x18000cc00  cmp     dword ptr [rdi], 8
0x18000cc03  jz      short loc_18000CC53
0x18000cc05  mov     dword ptr [rdi], 6
0x18000cc0b  jmp     short loc_18000CC53
0x18000cc0d  test    cs:byte_18004DF33, 80h
0x18000cc14  jz      short loc_18000CC30
0x18000cc16  lea     r8, aRequestRetryEx; "Request retry exceeded"
0x18000cc1d  lea     rdx, RasPppTraceError
0x18000cc24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cc2b  call    McTemplateU0z_EventWriteTransfer
0x18000cc30  cmp     dword ptr [rdi+28h], 0
0x18000cc34  jnz     short loc_18000CC39
0x18000cc36  mov     [rdi+28h], esi
0x18000cc39  mov     r8d, 1
0x18000cc3f  mov     edx, ebp
0x18000cc41  mov     rcx, rbx
0x18000cc44  call    FsmThisLayerFinished
0x18000cc49  test    eax, eax
0x18000cc4b  jz      short loc_18000CC53
0x18000cc4d  mov     dword ptr [rdi], 3
0x18000cc53  mov     rcx, [rsp+888h+var_48]
0x18000cc5b  xor     rcx, rsp; StackCookie
0x18000cc5e  call    __security_check_cookie
0x18000cc63  add     rsp, 858h
0x18000cc6a  pop     r15
0x18000cc6c  pop     r14
0x18000cc6e  pop     rdi
0x18000cc6f  pop     rsi
0x18000cc70  pop     rbp
0x18000cc71  pop     rbx
0x18000cc72  retn
```
