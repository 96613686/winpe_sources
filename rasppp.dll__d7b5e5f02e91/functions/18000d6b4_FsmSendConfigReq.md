# FsmSendConfigReq

- ea: `0x18000d6b4`
- end: `0x18000d8ab`
- name: `FsmSendConfigReq`
- size: `503`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `8`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009fd0`
- `0x18000a280`
- `0x18000a4c0`
- `0x18000b580`
- `0x18000c234`
- `0x18000c8d4`
- `0x18000cdc8`
- `0x180017e60`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000be68`
- `0x18000d6b4`
- `0x18000f780`
- `0x1800115d0`
- `0x180011748`
- `0x180012a20`
- `0x180013e50`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000d753`: `The control protocol for %x, returned error %d`
- `0x18000d7a0`: `while making a configure request on port %d`

## pseudocode

```c
__int64 __fastcall FsmSendConfigReq(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 PointerToCPCB; // rsi
  _BYTE *v5; // r15
  __int64 v6; // r14
  unsigned int v7; // eax
  __int64 v8; // r8
  _BYTE *v10; // rdx
  __int16 v11; // cx
  int v12; // ebx
  unsigned int v13; // r8d
  char *v14; // r9
  int v15; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v16[2044]; // [rsp+44h] [rbp-824h] BYREF

  v2 = (unsigned int)a2;
  v15 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v16, 0, sizeof(v16));
  if ( !PointerToCPCB )
    return 0;
  v5 = *(_BYTE **)(a1 + 40);
  v6 = 176 * v2;
  v7 = (*((__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))CpTable + 22 * v2 + 12))(
         *(_QWORD *)(PointerToCPCB + 16),
         v5 + 2,
         1498);
  if ( v7 )
  {
    *(_DWORD *)(PointerToCPCB + 40) = v7;
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v15,
        L"The control protocol for %x, returned error %d",
        *(unsigned int *)((char *)CpTable + v6),
        v7);
      if ( byte_18004DF33 < 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        if ( byte_18004DF33 < 0 )
        {
          v8 = *(_QWORD *)(a1 + 16);
          LOWORD(v15) = 0;
          FormatRRASErrorString((wchar_t *)&v15, L"while making a configure request on port %d", v8);
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        }
      }
    }
    FsmClose(a1, (unsigned int)v2);
    return 0;
  }
  v10 = *(_BYTE **)(a1 + 40);
  v11 = *(_WORD *)((char *)CpTable + v6);
  v10[1] = v11;
  *v10 = HIBYTE(v11);
  v5[2] = 1;
  v5[3] = GetUId(a1, (unsigned int)v2);
  v12 = ((unsigned __int8)v5[4] << 8) + (unsigned __int8)v5[5];
  LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), v12 + 2);
  if ( (unsigned int)PortSendOrDisconnect(a1, v12 + 2) )
    return 0;
  v13 = (unsigned __int8)v5[3];
  v14 = (char *)CpTable;
  *(_DWORD *)(PointerToCPCB + 8) = v13;
  InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), v13, *(_DWORD *)&v14[v6], 0, 0, *(_DWORD *)(a1 + 36));
  return 1;
}

```

## disassembly

```asm
0x18000d6b4  mov     [rsp+arg_10], rbx
0x18000d6b9  mov     [rsp+arg_18], rsi
0x18000d6be  push    rdi
0x18000d6bf  push    r14
0x18000d6c1  push    r15
0x18000d6c3  sub     rsp, 850h
0x18000d6ca  mov     rax, cs:__security_cookie
0x18000d6d1  xor     rax, rsp
0x18000d6d4  mov     [rsp+868h+var_28], rax
0x18000d6dc  mov     ebx, edx
0x18000d6de  mov     rdi, rcx
0x18000d6e1  call    GetPointerToCPCB
0x18000d6e6  xor     ecx, ecx
0x18000d6e8  xor     edx, edx; Val
0x18000d6ea  mov     [rsp+868h+var_828], ecx
0x18000d6ee  mov     r8d, 7FCh; Size
0x18000d6f4  lea     rcx, [rsp+868h+var_824]; void *
0x18000d6f9  mov     rsi, rax
0x18000d6fc  call    memset_0
0x18000d701  test    rsi, rsi
0x18000d704  jz      loc_18000D7E3
0x18000d70a  mov     r15, [rdi+28h]
0x18000d70e  mov     r8d, 5DAh
0x18000d714  mov     rax, cs:CpTable
0x18000d71b  mov     rcx, [rsi+10h]
0x18000d71f  imul    r14, rbx, 0B0h
0x18000d726  lea     rdx, [r15+2]
0x18000d72a  mov     rax, [r14+rax+60h]
0x18000d72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d734  test    eax, eax
0x18000d736  jz      loc_18000D80F
0x18000d73c  mov     [rsi+28h], eax
0x18000d73f  cmp     cs:byte_18004DF33, 0
0x18000d746  jge     loc_18000D7D9
0x18000d74c  mov     r8, cs:CpTable
0x18000d753  lea     rdx, aTheControlProt_0; "The control protocol for %x, returned e"...
0x18000d75a  xor     ecx, ecx
0x18000d75c  mov     r9d, eax
0x18000d75f  mov     word ptr [rsp+868h+var_828], cx
0x18000d764  lea     rcx, [rsp+868h+var_828]
0x18000d769  mov     r8d, [r14+r8]
0x18000d76d  call    FormatRRASErrorString
0x18000d772  cmp     cs:byte_18004DF33, 0
0x18000d779  jge     short loc_18000D7D9
0x18000d77b  lea     r8, [rsp+868h+var_828]
0x18000d780  lea     rdx, RasPppTraceError
0x18000d787  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d78e  call    McTemplateU0z_EventWriteTransfer
0x18000d793  cmp     cs:byte_18004DF33, 0
0x18000d79a  jge     short loc_18000D7D9
0x18000d79c  mov     r8, [rdi+10h]
0x18000d7a0  lea     rdx, aWhileMakingACo; "while making a configure request on por"...
0x18000d7a7  xor     eax, eax
0x18000d7a9  lea     rcx, [rsp+868h+var_828]
0x18000d7ae  mov     word ptr [rsp+868h+var_828], ax
0x18000d7b3  call    FormatRRASErrorString
0x18000d7b8  cmp     cs:byte_18004DF33, 0
0x18000d7bf  jge     short loc_18000D7D9
0x18000d7c1  lea     r8, [rsp+868h+var_828]
0x18000d7c6  lea     rdx, RasPppTraceError
0x18000d7cd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7d4  call    McTemplateU0z_EventWriteTransfer
0x18000d7d9  mov     edx, ebx
0x18000d7db  mov     rcx, rdi
0x18000d7de  call    FsmClose
0x18000d7e3  xor     eax, eax
0x18000d7e5  mov     rcx, [rsp+868h+var_28]
0x18000d7ed  xor     rcx, rsp; StackCookie
0x18000d7f0  call    __security_check_cookie
0x18000d7f5  lea     r11, [rsp+868h+var_18]
0x18000d7fd  mov     rbx, [r11+30h]
0x18000d801  mov     rsi, [r11+38h]
0x18000d805  mov     rsp, r11
0x18000d808  pop     r15
0x18000d80a  pop     r14
0x18000d80c  pop     rdi
0x18000d80d  retn
0x18000d80f  mov     rdx, [rdi+28h]
0x18000d813  mov     rax, cs:CpTable
0x18000d81a  movzx   ecx, word ptr [r14+rax]
0x18000d81f  mov     [rdx+1], cl
0x18000d822  movzx   eax, cx
0x18000d825  shr     ax, 8
0x18000d829  mov     rcx, rdi
0x18000d82c  mov     [rdx], al
0x18000d82e  mov     edx, ebx
0x18000d830  mov     byte ptr [r15+2], 1
0x18000d835  call    GetUId
0x18000d83a  mov     [r15+3], al
0x18000d83e  mov     rdx, rdi
0x18000d841  movzx   ebx, byte ptr [r15+5]
0x18000d846  xor     ecx, ecx
0x18000d848  movzx   eax, byte ptr [r15+4]
0x18000d84d  mov     r8, [rdi+28h]
0x18000d851  shl     eax, 8
0x18000d854  add     ebx, eax
0x18000d856  lea     r9d, [rbx+2]
0x18000d85a  call    LogPPPPacket
0x18000d85f  lea     edx, [rbx+2]
0x18000d862  mov     rcx, rdi
0x18000d865  call    PortSendOrDisconnect
0x18000d86a  test    eax, eax
0x18000d86c  jnz     loc_18000D7E3
0x18000d872  movzx   r8d, byte ptr [r15+3]
0x18000d877  mov     r9, cs:CpTable
0x18000d87e  mov     [rsi+8], r8d
0x18000d882  mov     ecx, [rdi+24h]
0x18000d885  mov     rdx, [rdi+10h]
0x18000d889  mov     r9d, [r14+r9]
0x18000d88d  mov     [rsp+868h+var_838], ecx
0x18000d891  mov     ecx, [rdi+40h]
0x18000d894  mov     [rsp+868h+var_840], eax
0x18000d898  mov     [rsp+868h+var_848], eax
0x18000d89c  call    InsertInTimerQ
0x18000d8a1  mov     eax, 1
0x18000d8a6  jmp     loc_18000D7E5
```
