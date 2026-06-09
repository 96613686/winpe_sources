# FsmReset

- ea: `0x18000d020`
- end: `0x18000d1ac`
- name: `FsmReset`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bc28`
- `0x18000cb10`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000ba40`
- `0x18000d020`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000d088`: `FsmReset called for protocol = %x, port = %d`
- `0x18000d12d`: `Reset for protocol = %x failed with error %d`

## pseudocode

```c
__int64 __fastcall FsmReset(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 PointerToCPCB; // rbx
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // esi
  int v10; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-824h] BYREF

  v2 = (unsigned int)a2;
  v10 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v11, 0, sizeof(v11));
  if ( !PointerToCPCB )
    return 0;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v10) = 0;
    FormatRRASErrorString(
      &v10,
      L"FsmReset called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v10);
  }
  v7 = *(_QWORD *)(PointerToCPCB + 16);
  *(_DWORD *)(PointerToCPCB + 8) = 0;
  *(_DWORD *)(PointerToCPCB + 24) = dword_18004C9F8;
  *(_DWORD *)(PointerToCPCB + 28) = dword_18004C9F4;
  *(_DWORD *)(PointerToCPCB + 32) = dword_18004C9FC;
  *(_DWORD *)(PointerToCPCB + 36) = dword_18004CA00;
  v8 = (*((__int64 (__fastcall **)(__int64))CpTable + 22 * v2 + 6))(v7);
  v9 = v8;
  if ( v8 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(
        &v10,
        L"Reset for protocol = %x failed with error %d",
        *((unsigned int *)CpTable + 44 * v2),
        v8);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v10);
    }
    *(_DWORD *)(PointerToCPCB + 40) = v9;
    FsmClose(a1, (unsigned int)v2);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d020  mov     [rsp+arg_10], rbx
0x18000d025  mov     [rsp+arg_18], rbp
0x18000d02a  push    rsi
0x18000d02b  push    rdi
0x18000d02c  push    r14
0x18000d02e  sub     rsp, 830h
0x18000d035  mov     rax, cs:__security_cookie
0x18000d03c  xor     rax, rsp
0x18000d03f  mov     [rsp+848h+var_28], rax
0x18000d047  mov     edi, edx
0x18000d049  mov     rbp, rcx
0x18000d04c  call    GetPointerToCPCB
0x18000d051  xor     ecx, ecx
0x18000d053  xor     edx, edx; Val
0x18000d055  mov     [rsp+848h+var_828], ecx
0x18000d059  mov     r8d, 7FCh; Size
0x18000d05f  lea     rcx, [rsp+848h+var_824]; void *
0x18000d064  mov     rbx, rax
0x18000d067  call    memset_0
0x18000d06c  test    rbx, rbx
0x18000d06f  jnz     short loc_18000D078
0x18000d071  xor     eax, eax
0x18000d073  jmp     loc_18000D184
0x18000d078  test    cs:byte_18004CF34, 1
0x18000d07f  jz      short loc_18000D0D0
0x18000d081  mov     r8, cs:CpTable
0x18000d088  lea     rdx, aFsmresetCalled; "FsmReset called for protocol = %x, port"...
0x18000d08f  mov     r9, [rbp+10h]
0x18000d093  xor     eax, eax
0x18000d095  imul    rcx, rdi, 0B0h
0x18000d09c  mov     word ptr [rsp+848h+var_828], ax
0x18000d0a1  mov     r8d, [rcx+r8]
0x18000d0a5  lea     rcx, [rsp+848h+var_828]
0x18000d0aa  call    FormatRRASErrorString
0x18000d0af  test    cs:byte_18004CF34, 1
0x18000d0b6  jz      short loc_18000D0D0
0x18000d0b8  lea     r8, [rsp+848h+var_828]
0x18000d0bd  lea     rdx, RasPppTraceInfo
0x18000d0c4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d0cb  call    McTemplateU0z_EventWriteTransfer
0x18000d0d0  mov     rcx, [rbx+10h]
0x18000d0d4  mov     dword ptr [rbx+8], 0
0x18000d0db  mov     eax, cs:dword_18004C9F8
0x18000d0e1  mov     [rbx+18h], eax
0x18000d0e4  mov     eax, cs:dword_18004C9F4
0x18000d0ea  mov     [rbx+1Ch], eax
0x18000d0ed  mov     eax, cs:dword_18004C9FC
0x18000d0f3  mov     [rbx+20h], eax
0x18000d0f6  mov     eax, cs:dword_18004CA00
0x18000d0fc  mov     [rbx+24h], eax
0x18000d0ff  mov     rax, cs:CpTable
0x18000d106  imul    r14, rdi, 0B0h
0x18000d10d  mov     rax, [r14+rax+30h]
0x18000d112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d117  mov     esi, eax
0x18000d119  test    eax, eax
0x18000d11b  jz      short loc_18000D17F
0x18000d11d  cmp     cs:byte_18004CF33, 0
0x18000d124  jge     short loc_18000D16D
0x18000d126  mov     r8, cs:CpTable
0x18000d12d  lea     rdx, aResetForProtoc; "Reset for protocol = %x failed with err"...
0x18000d134  xor     ecx, ecx
0x18000d136  mov     r9d, eax
0x18000d139  mov     word ptr [rsp+848h+var_828], cx
0x18000d13e  lea     rcx, [rsp+848h+var_828]
0x18000d143  mov     r8d, [r14+r8]
0x18000d147  call    FormatRRASErrorString
0x18000d14c  cmp     cs:byte_18004CF33, 0
0x18000d153  jge     short loc_18000D16D
0x18000d155  lea     r8, [rsp+848h+var_828]
0x18000d15a  lea     rdx, RasPppTraceError
0x18000d161  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d168  call    McTemplateU0z_EventWriteTransfer
0x18000d16d  mov     edx, edi
0x18000d16f  mov     [rbx+28h], esi
0x18000d172  mov     rcx, rbp
0x18000d175  call    FsmClose
0x18000d17a  jmp     loc_18000D071
0x18000d17f  mov     eax, 1
0x18000d184  mov     rcx, [rsp+848h+var_28]
0x18000d18c  xor     rcx, rsp; StackCookie
0x18000d18f  call    __security_check_cookie
0x18000d194  lea     r11, [rsp+848h+var_18]
0x18000d19c  mov     rbx, [r11+30h]
0x18000d1a0  mov     rbp, [r11+38h]
0x18000d1a4  mov     rsp, r11
0x18000d1a7  pop     r14
0x18000d1a9  pop     rdi
0x18000d1aa  pop     rsi
0x18000d1ab  retn
```
