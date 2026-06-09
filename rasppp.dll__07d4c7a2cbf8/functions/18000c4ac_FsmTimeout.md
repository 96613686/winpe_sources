# FsmTimeout

- ea: `0x18000c4ac`
- end: `0x18000c84b`
- name: `FsmTimeout`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800023a8`
- `0x180003110`
- `0x180004388`
- `0x18000c4ac`
- `0x18000d284`
- `0x18000df18`
- `0x18000e364`
- `0x180010cfc`
- `0x180011064`
- `0x180012dcc`
- `0x180013490`
- `0x18002a138`

## string_xrefs

- `0x18000c516`: `Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d`

## pseudocode

```c
__int64 __fastcall FsmTimeout(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v5; // rbp
  int *PointerToCPCB; // rdi
  __int64 result; // rax
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
  result = (__int64)memset_0(v23, 0, sizeof(v23));
  if ( !PointerToCPCB )
    return result;
  v10 = *(_QWORD *)(a1 + 1472);
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v11 = *(unsigned int *)(a1 + 64);
    LOWORD(v22) = 0;
    FormatRRASErrorString(
      &v22,
      L"Recv timeout event received for portid=%d,Id=%d,Protocol=%x,fAuth=%d",
      v11,
      a3,
      *((_DWORD *)CpTable + 44 * v5),
      a4);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v22);
  }
  result = GetCpIndexFromProtocol(*(unsigned int *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFF38uLL) + v10 + 1420));
  if ( (_DWORD)v5 == (_DWORD)result )
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
  if ( (_DWORD)v5 == (_DWORD)result && *(_DWORD *)(a1 + 48) == 2 )
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
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasPppTraceError,
              L"Terminate retry exceeded");
          if ( !PointerToCPCB[10] )
            PointerToCPCB[10] = 718;
          result = FsmThisLayerFinished(a1, v5, 1);
          if ( (_DWORD)result )
          {
            result = (unsigned int)(*PointerToCPCB != 4) + 2;
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
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v22) = 0;
        result = FormatRRASErrorString(
                   &v22,
                   L"Illegal transition->FsmTimeout rcvd while in %hs state",
                   FsmStates[*PointerToCPCB]);
        if ( byte_18004CF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v22);
      }
      return result;
    }
    v20 = PointerToCPCB[6];
    if ( v20 )
    {
      PointerToCPCB[6] = v20 - 1;
      if ( !(_DWORD)v5 && *(_DWORD *)(a1 + 1496) == 721 && (*(_BYTE *)(a1 + 56) & 4) == 0 )
        NotifyCaller(a1, 9);
      v21 = *(_DWORD *)(a1 + 36);
      if ( v21 < dword_18004C9E8 )
        *(_DWORD *)(a1 + 36) = v21 + 1;
      result = FsmSendConfigReq(a1, (unsigned int)v5);
      if ( (_DWORD)result && *PointerToCPCB != 8 )
        *PointerToCPCB = 6;
    }
    else
    {
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceError,
          L"Request retry exceeded");
      if ( !PointerToCPCB[10] )
        PointerToCPCB[10] = 718;
      result = FsmThisLayerFinished(a1, v5, 1);
      if ( (_DWORD)result )
        *PointerToCPCB = 3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c4ac  push    rbx
0x18000c4ae  push    rbp
0x18000c4af  push    rsi
0x18000c4b0  push    rdi
0x18000c4b1  push    r14
0x18000c4b3  push    r15
0x18000c4b5  sub     rsp, 858h
0x18000c4bc  mov     rax, cs:__security_cookie
0x18000c4c3  xor     rax, rsp
0x18000c4c6  mov     [rsp+888h+var_48], rax
0x18000c4ce  mov     esi, r9d
0x18000c4d1  mov     ebp, edx
0x18000c4d3  mov     r14d, r8d
0x18000c4d6  mov     rbx, rcx
0x18000c4d9  call    GetPointerToCPCB
0x18000c4de  xor     ecx, ecx
0x18000c4e0  xor     edx, edx; Val
0x18000c4e2  mov     [rsp+888h+var_848], ecx
0x18000c4e6  mov     r8d, 7FCh; Size
0x18000c4ec  lea     rcx, [rsp+888h+var_844]; void *
0x18000c4f1  mov     rdi, rax
0x18000c4f4  call    memset_0
0x18000c4f9  test    rdi, rdi
0x18000c4fc  jz      loc_18000C82B
0x18000c502  test    cs:byte_18004CF34, 1
0x18000c509  mov     r15, [rbx+5C0h]
0x18000c510  jz      short loc_18000C56B
0x18000c512  mov     r8d, [rbx+40h]
0x18000c516  lea     rdx, aRecvTimeoutEve; "Recv timeout event received for portid="...
0x18000c51d  xor     eax, eax
0x18000c51f  mov     [rsp+888h+var_860], esi
0x18000c523  mov     word ptr [rsp+888h+var_848], ax
0x18000c528  mov     r9d, r14d
0x18000c52b  mov     rax, cs:CpTable
0x18000c532  imul    rcx, rbp, 0B0h
0x18000c539  mov     ecx, [rcx+rax]
0x18000c53c  mov     [rsp+888h+var_868], ecx
0x18000c540  lea     rcx, [rsp+888h+var_848]
0x18000c545  call    FormatRRASErrorString
0x18000c54a  test    cs:byte_18004CF34, 1
0x18000c551  jz      short loc_18000C56B
0x18000c553  lea     r8, [rsp+888h+var_848]
0x18000c558  lea     rdx, RasPppTraceInfo
0x18000c55f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c566  call    McTemplateU0z_EventWriteTransfer
0x18000c56b  mov     eax, esi
0x18000c56d  neg     eax
0x18000c56f  sbb     rcx, rcx
0x18000c572  and     rcx, 0FFFFFFFFFFFFFF38h
0x18000c579  mov     ecx, [rcx+r15+58Ch]
0x18000c581  call    GetCpIndexFromProtocol
0x18000c586  cmp     ebp, eax
0x18000c588  jnz     loc_18000C60F
0x18000c58e  cmp     dword ptr [rbx+30h], 1
0x18000c592  jnz     loc_18000C82B
0x18000c598  mov     eax, esi
0x18000c59a  neg     eax
0x18000c59c  sbb     rcx, rcx
0x18000c59f  and     rcx, 0FFFFFFFFFFFFFFC0h
0x18000c5a3  cmp     r14d, [rcx+rbx+578h]
0x18000c5ab  jb      loc_18000C82B
0x18000c5b1  mov     eax, esi
0x18000c5b3  neg     eax
0x18000c5b5  sbb     r8, r8
0x18000c5b8  and     r8, 0FFFFFFFFFFFFFFC0h
0x18000c5bc  mov     eax, [r8+rbx+588h]
0x18000c5c4  test    eax, eax
0x18000c5c6  jz      short loc_18000C5EB
0x18000c5c8  dec     eax
0x18000c5ca  mov     [rsp+888h+var_868], esi
0x18000c5ce  mov     [r8+rbx+588h], eax
0x18000c5d6  xor     r9d, r9d
0x18000c5d9  xor     r8d, r8d
0x18000c5dc  mov     edx, ebp
0x18000c5de  mov     rcx, rbx
0x18000c5e1  call    ApWork
0x18000c5e6  jmp     loc_18000C82B
0x18000c5eb  mov     esi, [rbx+5D8h]
0x18000c5f1  test    esi, esi
0x18000c5f3  jnz     short loc_18000C600
0x18000c5f5  mov     esi, 2CEh
0x18000c5fa  mov     [rbx+5D8h], esi
0x18000c600  mov     edx, esi
0x18000c602  mov     rcx, rbx
0x18000c605  call    NotifyCallerOfFailure
0x18000c60a  jmp     loc_18000C82B
0x18000c60f  mov     ecx, 0C029h
0x18000c614  call    GetCpIndexFromProtocol
0x18000c619  mov     esi, 2CEh
0x18000c61e  cmp     ebp, eax
0x18000c620  jnz     short loc_18000C66A
0x18000c622  cmp     dword ptr [rbx+30h], 2
0x18000c626  jnz     short loc_18000C66A
0x18000c628  cmp     r14d, [rdi+8]
0x18000c62c  jb      loc_18000C82B
0x18000c632  mov     eax, [rdi+18h]
0x18000c635  test    eax, eax
0x18000c637  jz      short loc_18000C650
0x18000c639  dec     eax
0x18000c63b  xor     r9d, r9d
0x18000c63e  xor     r8d, r8d
0x18000c641  mov     [rdi+18h], eax
0x18000c644  mov     edx, ebp
0x18000c646  mov     rcx, rbx
0x18000c649  call    CbWork
0x18000c64e  jmp     short loc_18000C66A
0x18000c650  mov     edx, [rbx+5D8h]
0x18000c656  test    edx, edx
0x18000c658  jnz     short loc_18000C662
0x18000c65a  mov     [rbx+5D8h], esi
0x18000c660  mov     edx, esi
0x18000c662  mov     rcx, rbx
0x18000c665  call    NotifyCallerOfFailure
0x18000c66a  cmp     r14d, [rdi+8]
0x18000c66e  jb      loc_18000C82B
0x18000c674  mov     ecx, [rdi]
0x18000c676  cmp     ecx, 5
0x18000c679  jg      loc_18000C71E
0x18000c67f  jz      short loc_18000C6AD
0x18000c681  test    ecx, ecx
0x18000c683  jz      loc_18000C72D
0x18000c689  sub     ecx, 1
0x18000c68c  jz      loc_18000C72D
0x18000c692  sub     ecx, 1
0x18000c695  jz      loc_18000C72D
0x18000c69b  sub     ecx, 1
0x18000c69e  jz      loc_18000C72D
0x18000c6a4  cmp     ecx, 1
0x18000c6a7  jnz     loc_18000C72D
0x18000c6ad  mov     eax, [rdi+1Ch]
0x18000c6b0  test    eax, eax
0x18000c6b2  jz      short loc_18000C6C8
0x18000c6b4  dec     eax
0x18000c6b6  mov     edx, ebp
0x18000c6b8  mov     rcx, rbx
0x18000c6bb  mov     [rdi+1Ch], eax
0x18000c6be  call    FsmSendTermReq
0x18000c6c3  jmp     loc_18000C82B
0x18000c6c8  test    cs:byte_18004CF33, 80h
0x18000c6cf  jz      short loc_18000C6EB
0x18000c6d1  lea     r8, aTerminateRetry; "Terminate retry exceeded"
0x18000c6d8  lea     rdx, RasPppTraceError
0x18000c6df  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c6e6  call    McTemplateU0z_EventWriteTransfer
0x18000c6eb  cmp     dword ptr [rdi+28h], 0
0x18000c6ef  jnz     short loc_18000C6F4
0x18000c6f1  mov     [rdi+28h], esi
0x18000c6f4  mov     r8d, 1
0x18000c6fa  mov     edx, ebp
0x18000c6fc  mov     rcx, rbx
0x18000c6ff  call    FsmThisLayerFinished
0x18000c704  test    eax, eax
0x18000c706  jz      loc_18000C82B
0x18000c70c  xor     eax, eax
0x18000c70e  cmp     dword ptr [rdi], 4
0x18000c711  setnz   al
0x18000c714  add     eax, 2
0x18000c717  mov     [rdi], eax
0x18000c719  jmp     loc_18000C82B
0x18000c71e  sub     ecx, 6
0x18000c721  jz      short loc_18000C78A
0x18000c723  sub     ecx, 1
0x18000c726  jz      short loc_18000C78A
0x18000c728  cmp     ecx, 1
0x18000c72b  jz      short loc_18000C78A
0x18000c72d  cmp     cs:byte_18004CF33, 0
0x18000c734  jge     loc_18000C82B
0x18000c73a  xor     eax, eax
0x18000c73c  lea     rdx, aIllegalTransit; "Illegal transition->FsmTimeout rcvd whi"...
0x18000c743  mov     word ptr [rsp+888h+var_848], ax
0x18000c748  lea     rcx, [rsp+888h+var_848]
0x18000c74d  movsxd  r8, dword ptr [rdi]
0x18000c750  lea     rax, FsmStates
0x18000c757  mov     r8, [rax+r8*8]
0x18000c75b  call    FormatRRASErrorString
0x18000c760  cmp     cs:byte_18004CF33, 0
0x18000c767  jge     loc_18000C82B
0x18000c76d  lea     r8, [rsp+888h+var_848]
0x18000c772  lea     rdx, RasPppTraceError
0x18000c779  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c780  call    McTemplateU0z_EventWriteTransfer
0x18000c785  jmp     loc_18000C82B
0x18000c78a  mov     eax, [rdi+18h]
0x18000c78d  test    eax, eax
0x18000c78f  jz      short loc_18000C7E5
0x18000c791  dec     eax
0x18000c793  mov     [rdi+18h], eax
0x18000c796  test    ebp, ebp
0x18000c798  jnz     short loc_18000C7BA
0x18000c79a  cmp     dword ptr [rbx+5D8h], 2D1h
0x18000c7a4  jnz     short loc_18000C7BA
0x18000c7a6  test    byte ptr [rbx+38h], 4
0x18000c7aa  jnz     short loc_18000C7BA
0x18000c7ac  xor     r8d, r8d
0x18000c7af  lea     edx, [rbp+9]
0x18000c7b2  mov     rcx, rbx
0x18000c7b5  call    NotifyCaller
0x18000c7ba  mov     eax, [rbx+24h]
0x18000c7bd  cmp     eax, cs:dword_18004C9E8
0x18000c7c3  jnb     short loc_18000C7CA
0x18000c7c5  inc     eax
0x18000c7c7  mov     [rbx+24h], eax
0x18000c7ca  mov     edx, ebp
0x18000c7cc  mov     rcx, rbx
0x18000c7cf  call    FsmSendConfigReq
0x18000c7d4  test    eax, eax
0x18000c7d6  jz      short loc_18000C82B
0x18000c7d8  cmp     dword ptr [rdi], 8
0x18000c7db  jz      short loc_18000C82B
0x18000c7dd  mov     dword ptr [rdi], 6
0x18000c7e3  jmp     short loc_18000C82B
0x18000c7e5  test    cs:byte_18004CF33, 80h
0x18000c7ec  jz      short loc_18000C808
0x18000c7ee  lea     r8, aRequestRetryEx; "Request retry exceeded"
0x18000c7f5  lea     rdx, RasPppTraceError
0x18000c7fc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c803  call    McTemplateU0z_EventWriteTransfer
0x18000c808  cmp     dword ptr [rdi+28h], 0
0x18000c80c  jnz     short loc_18000C811
0x18000c80e  mov     [rdi+28h], esi
0x18000c811  mov     r8d, 1
0x18000c817  mov     edx, ebp
0x18000c819  mov     rcx, rbx
0x18000c81c  call    FsmThisLayerFinished
0x18000c821  test    eax, eax
0x18000c823  jz      short loc_18000C82B
0x18000c825  mov     dword ptr [rdi], 3
0x18000c82b  mov     rcx, [rsp+888h+var_48]
0x18000c833  xor     rcx, rsp; StackCookie
0x18000c836  call    __security_check_cookie
0x18000c83b  add     rsp, 858h
0x18000c842  pop     r15
0x18000c844  pop     r14
0x18000c846  pop     rdi
0x18000c847  pop     rsi
0x18000c848  pop     rbp
0x18000c849  pop     rbx
0x18000c84a  retn
```
