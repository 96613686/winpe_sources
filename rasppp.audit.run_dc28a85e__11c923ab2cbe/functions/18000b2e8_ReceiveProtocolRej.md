# ReceiveProtocolRej

- ea: `0x18000b2e8`
- end: `0x18000b576`
- name: `ReceiveProtocolRej`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c3e8`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000b2e8`
- `0x18000e358`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000f984`
- `0x180011230`
- `0x1800115d0`
- `0x180013b54`
- `0x18002b0dc`

## string_xrefs

- `0x18000b333`: `PPP Protocol Reject, Protocol = %x`
- `0x18000b3e0`: `Protocol Rej silently discarded on port %d. Lcp not open`

## pseudocode

```c
__int64 __fastcall ReceiveProtocolRej(__int64 a1, unsigned __int8 *a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  __int64 v6; // r8
  int *PointerToCPCB; // rbx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // [rsp+30h] [rbp-828h] BYREF
  char v16[2044]; // [rsp+34h] [rbp-824h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"PPP Protocol Reject, Protocol = %x", 0);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
  }
  result = a2[5];
  if ( (unsigned __int16)(result + (a2[4] << 8)) >= 6u )
  {
    result = GetCpIndexFromProtocol(a2[7] + (a2[6] << 8));
    v5 = result;
    if ( (_DWORD)result != -1 )
    {
      if ( !(_DWORD)result )
      {
        *(_DWORD *)(a1 + 1496) = 732;
        return NotifyCallerOfFailure(a1, 732);
      }
      if ( !*(_DWORD *)(a1 + 48) )
      {
        if ( byte_18004DF33 >= 0 )
          return result;
        v6 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        result = FormatRRASErrorString(&v15, L"Protocol Rej silently discarded on port %d. Lcp not open", v6);
LABEL_11:
        if ( byte_18004DF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        return result;
      }
      if ( (unsigned int)result < (unsigned int)PppConfigInfo )
      {
        PointerToCPCB = (int *)GetPointerToCPCB(a1, (unsigned int)result);
        PointerToCPCB[10] = 733;
      }
      else
      {
        PointerToCPCB = (int *)(a1 + 1456);
        v5 = 0;
        *(_DWORD *)(a1 + 1496) = 917;
      }
      result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), PointerToCPCB[2], *((_DWORD *)CpTable + 44 * v5), 0, 0);
      v8 = *PointerToCPCB;
      if ( *PointerToCPCB <= 5 )
      {
        if ( v8 != 5 )
        {
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( !v10 )
                return result;
              v11 = v10 - 1;
              if ( !v11 )
                return result;
              if ( v11 == 1 )
              {
                result = FsmThisLayerFinished(a1, v5, 1);
                if ( (_DWORD)result )
                  *PointerToCPCB = 2;
                return result;
              }
            }
          }
LABEL_29:
          if ( byte_18004DF33 >= 0 )
            return result;
          LOWORD(v15) = 0;
          result = FormatRRASErrorString(
                     &v15,
                     L"Illegal transition->UnknownCode rcvd while in %hs state",
                     FsmStates[*PointerToCPCB]);
          goto LABEL_11;
        }
        goto LABEL_33;
      }
      v12 = v8 - 6;
      if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
      {
LABEL_33:
        result = FsmThisLayerFinished(a1, v5, 1);
        if ( (_DWORD)result )
          *PointerToCPCB = 3;
        return result;
      }
      if ( v14 != 1 )
        goto LABEL_29;
      result = FsmThisLayerDown(a1, v5);
      if ( (_DWORD)result )
      {
        PointerToCPCB[6] = dword_18004D9F8;
        PointerToCPCB[7] = dword_18004D9F4;
        result = FsmSendTermReq(a1, v5);
        *PointerToCPCB = 5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b2e8  mov     [rsp+arg_10], rbx
0x18000b2ed  push    rsi
0x18000b2ee  push    rdi
0x18000b2ef  push    r15
0x18000b2f1  sub     rsp, 840h
0x18000b2f8  mov     rax, cs:__security_cookie
0x18000b2ff  xor     rax, rsp
0x18000b302  mov     [rsp+858h+var_28], rax
0x18000b30a  mov     rbx, rdx
0x18000b30d  mov     rdi, rcx
0x18000b310  xor     eax, eax
0x18000b312  lea     rcx, [rsp+858h+var_824]; void *
0x18000b317  xor     edx, edx; Val
0x18000b319  mov     [rsp+858h+var_828], eax
0x18000b31d  mov     r8d, 7FCh; Size
0x18000b323  call    memset_0
0x18000b328  test    cs:byte_18004DF34, 1
0x18000b32f  jz      short loc_18000B36D
0x18000b331  xor     eax, eax
0x18000b333  lea     rdx, aPppProtocolRej; "PPP Protocol Reject, Protocol = %x"
0x18000b33a  xor     r8d, r8d
0x18000b33d  mov     word ptr [rsp+858h+var_828], ax
0x18000b342  lea     rcx, [rsp+858h+var_828]
0x18000b347  call    FormatRRASErrorString
0x18000b34c  test    cs:byte_18004DF34, 1
0x18000b353  jz      short loc_18000B36D
0x18000b355  lea     r8, [rsp+858h+var_828]
0x18000b35a  lea     rdx, RasPppTraceInfo
0x18000b361  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b368  call    McTemplateU0z_EventWriteTransfer
0x18000b36d  movzx   edx, byte ptr [rbx+4]
0x18000b371  mov     ecx, 100h
0x18000b376  movzx   eax, byte ptr [rbx+5]
0x18000b37a  mov     r15d, 6
0x18000b380  imul    edx, ecx
0x18000b383  add     dx, ax
0x18000b386  cmp     dx, r15w
0x18000b38a  jb      loc_18000B551
0x18000b390  movzx   eax, byte ptr [rbx+7]
0x18000b394  movzx   ecx, byte ptr [rbx+6]
0x18000b398  shl     ecx, 8
0x18000b39b  add     ecx, eax
0x18000b39d  call    GetCpIndexFromProtocol
0x18000b3a2  mov     esi, eax
0x18000b3a4  cmp     eax, 0FFFFFFFFh
0x18000b3a7  jz      loc_18000B551
0x18000b3ad  test    eax, eax
0x18000b3af  jnz     short loc_18000B3C9
0x18000b3b1  mov     edx, 2DCh
0x18000b3b6  mov     rcx, rdi
0x18000b3b9  mov     [rdi+5D8h], edx
0x18000b3bf  call    NotifyCallerOfFailure
0x18000b3c4  jmp     loc_18000B551
0x18000b3c9  cmp     dword ptr [rdi+30h], 0
0x18000b3cd  jnz     short loc_18000B422
0x18000b3cf  cmp     cs:byte_18004DF33, 0
0x18000b3d6  jge     loc_18000B551
0x18000b3dc  mov     r8, [rdi+10h]
0x18000b3e0  lea     rdx, aProtocolRejSil; "Protocol Rej silently discarded on port"...
0x18000b3e7  xor     eax, eax
0x18000b3e9  mov     word ptr [rsp+858h+var_828], ax
0x18000b3ee  lea     rcx, [rsp+858h+var_828]
0x18000b3f3  call    FormatRRASErrorString
0x18000b3f8  cmp     cs:byte_18004DF33, 0
0x18000b3ff  jge     loc_18000B551
0x18000b405  lea     r8, [rsp+858h+var_828]
0x18000b40a  lea     rdx, RasPppTraceError
0x18000b411  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b418  call    McTemplateU0z_EventWriteTransfer
0x18000b41d  jmp     loc_18000B551
0x18000b422  cmp     eax, dword ptr cs:PppConfigInfo
0x18000b428  jb      short loc_18000B43C
0x18000b42a  lea     rbx, [rdi+5B0h]
0x18000b431  xor     esi, esi
0x18000b433  mov     dword ptr [rbx+28h], 395h
0x18000b43a  jmp     short loc_18000B450
0x18000b43c  mov     edx, eax
0x18000b43e  mov     rcx, rdi
0x18000b441  call    GetPointerToCPCB
0x18000b446  mov     rbx, rax
0x18000b449  mov     dword ptr [rax+28h], 2DDh
0x18000b450  mov     r8, cs:CpTable
0x18000b457  xor     r9d, r9d
0x18000b45a  mov     ecx, esi
0x18000b45c  imul    rdx, rcx, 0B0h
0x18000b463  mov     ecx, [rdi+40h]
0x18000b466  mov     [rsp+858h+var_838], 0
0x18000b46e  mov     r8d, [rdx+r8]
0x18000b472  mov     edx, [rbx+8]
0x18000b475  call    RemoveFromTimerQ
0x18000b47a  mov     ecx, [rbx]
0x18000b47c  cmp     ecx, 5
0x18000b47f  jg      short loc_18000B4C7
0x18000b481  jz      loc_18000B537
0x18000b487  test    ecx, ecx
0x18000b489  jz      short loc_18000B4DB
0x18000b48b  sub     ecx, 1
0x18000b48e  jz      short loc_18000B4DB
0x18000b490  sub     ecx, 1
0x18000b493  jz      loc_18000B551
0x18000b499  sub     ecx, 1
0x18000b49c  jz      loc_18000B551
0x18000b4a2  cmp     ecx, 1
0x18000b4a5  jnz     short loc_18000B4DB
0x18000b4a7  mov     r8d, ecx
0x18000b4aa  mov     edx, esi
0x18000b4ac  mov     rcx, rdi
0x18000b4af  call    FsmThisLayerFinished
0x18000b4b4  test    eax, eax
0x18000b4b6  jz      loc_18000B551
0x18000b4bc  mov     dword ptr [rbx], 2
0x18000b4c2  jmp     loc_18000B551
0x18000b4c7  sub     ecx, r15d
0x18000b4ca  jz      short loc_18000B537
0x18000b4cc  sub     ecx, 1
0x18000b4cf  jz      short loc_18000B537
0x18000b4d1  sub     ecx, 1
0x18000b4d4  jz      short loc_18000B537
0x18000b4d6  cmp     ecx, 1
0x18000b4d9  jz      short loc_18000B505
0x18000b4db  cmp     cs:byte_18004DF33, 0
0x18000b4e2  jge     short loc_18000B551
0x18000b4e4  xor     eax, eax
0x18000b4e6  lea     rdx, aIllegalTransit_0; "Illegal transition->UnknownCode rcvd wh"...
0x18000b4ed  mov     word ptr [rsp+858h+var_828], ax
0x18000b4f2  lea     rax, FsmStates
0x18000b4f9  movsxd  r8, dword ptr [rbx]
0x18000b4fc  mov     r8, [rax+r8*8]
0x18000b500  jmp     loc_18000B3EE
0x18000b505  mov     edx, esi
0x18000b507  mov     rcx, rdi
0x18000b50a  call    FsmThisLayerDown
0x18000b50f  test    eax, eax
0x18000b511  jz      short loc_18000B551
0x18000b513  mov     eax, cs:dword_18004D9F8
0x18000b519  mov     edx, esi
0x18000b51b  mov     [rbx+18h], eax
0x18000b51e  mov     rcx, rdi
0x18000b521  mov     eax, cs:dword_18004D9F4
0x18000b527  mov     [rbx+1Ch], eax
0x18000b52a  call    FsmSendTermReq
0x18000b52f  mov     dword ptr [rbx], 5
0x18000b535  jmp     short loc_18000B551
0x18000b537  mov     r8d, 1
0x18000b53d  mov     edx, esi
0x18000b53f  mov     rcx, rdi
0x18000b542  call    FsmThisLayerFinished
0x18000b547  test    eax, eax
0x18000b549  jz      short loc_18000B551
0x18000b54b  mov     dword ptr [rbx], 3
0x18000b551  mov     rcx, [rsp+858h+var_28]
0x18000b559  xor     rcx, rsp; StackCookie
0x18000b55c  call    __security_check_cookie
0x18000b561  mov     rbx, [rsp+858h+arg_10]
0x18000b569  add     rsp, 840h
0x18000b570  pop     r15
0x18000b572  pop     rdi
0x18000b573  pop     rsi
0x18000b574  retn
```
