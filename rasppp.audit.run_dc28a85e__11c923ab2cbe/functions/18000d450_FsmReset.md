# FsmReset

- ea: `0x18000d450`
- end: `0x18000d5dd`
- name: `FsmReset`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c050`
- `0x18000cf3c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000be68`
- `0x18000d450`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000d4b8`: `FsmReset called for protocol = %x, port = %d`
- `0x18000d55d`: `Reset for protocol = %x failed with error %d`

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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v10) = 0;
    FormatRRASErrorString(
      &v10,
      L"FsmReset called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v10);
  }
  v7 = *(_QWORD *)(PointerToCPCB + 16);
  *(_DWORD *)(PointerToCPCB + 8) = 0;
  *(_DWORD *)(PointerToCPCB + 24) = dword_18004D9F8;
  *(_DWORD *)(PointerToCPCB + 28) = dword_18004D9F4;
  *(_DWORD *)(PointerToCPCB + 32) = dword_18004D9FC;
  *(_DWORD *)(PointerToCPCB + 36) = dword_18004DA00;
  v8 = (*((__int64 (__fastcall **)(__int64))CpTable + 22 * v2 + 6))(v7);
  v9 = v8;
  if ( v8 )
  {
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(
        &v10,
        L"Reset for protocol = %x failed with error %d",
        *((unsigned int *)CpTable + 44 * v2),
        v8);
      if ( byte_18004DF33 < 0 )
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
0x18000d450  mov     [rsp+arg_10], rbx
0x18000d455  mov     [rsp+arg_18], rbp
0x18000d45a  push    rsi
0x18000d45b  push    rdi
0x18000d45c  push    r14
0x18000d45e  sub     rsp, 830h
0x18000d465  mov     rax, cs:__security_cookie
0x18000d46c  xor     rax, rsp
0x18000d46f  mov     [rsp+848h+var_28], rax
0x18000d477  mov     edi, edx
0x18000d479  mov     rbp, rcx
0x18000d47c  call    GetPointerToCPCB
0x18000d481  xor     ecx, ecx
0x18000d483  xor     edx, edx; Val
0x18000d485  mov     [rsp+848h+var_828], ecx
0x18000d489  mov     r8d, 7FCh; Size
0x18000d48f  lea     rcx, [rsp+848h+var_824]; void *
0x18000d494  mov     rbx, rax
0x18000d497  call    memset_0
0x18000d49c  test    rbx, rbx
0x18000d49f  jnz     short loc_18000D4A8
0x18000d4a1  xor     eax, eax
0x18000d4a3  jmp     loc_18000D5B4
0x18000d4a8  test    cs:byte_18004DF34, 1
0x18000d4af  jz      short loc_18000D500
0x18000d4b1  mov     r8, cs:CpTable
0x18000d4b8  lea     rdx, aFsmresetCalled; "FsmReset called for protocol = %x, port"...
0x18000d4bf  mov     r9, [rbp+10h]
0x18000d4c3  xor     eax, eax
0x18000d4c5  imul    rcx, rdi, 0B0h
0x18000d4cc  mov     word ptr [rsp+848h+var_828], ax
0x18000d4d1  mov     r8d, [rcx+r8]
0x18000d4d5  lea     rcx, [rsp+848h+var_828]
0x18000d4da  call    FormatRRASErrorString
0x18000d4df  test    cs:byte_18004DF34, 1
0x18000d4e6  jz      short loc_18000D500
0x18000d4e8  lea     r8, [rsp+848h+var_828]
0x18000d4ed  lea     rdx, RasPppTraceInfo
0x18000d4f4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d4fb  call    McTemplateU0z_EventWriteTransfer
0x18000d500  mov     rcx, [rbx+10h]
0x18000d504  mov     dword ptr [rbx+8], 0
0x18000d50b  mov     eax, cs:dword_18004D9F8
0x18000d511  mov     [rbx+18h], eax
0x18000d514  mov     eax, cs:dword_18004D9F4
0x18000d51a  mov     [rbx+1Ch], eax
0x18000d51d  mov     eax, cs:dword_18004D9FC
0x18000d523  mov     [rbx+20h], eax
0x18000d526  mov     eax, cs:dword_18004DA00
0x18000d52c  mov     [rbx+24h], eax
0x18000d52f  mov     rax, cs:CpTable
0x18000d536  imul    r14, rdi, 0B0h
0x18000d53d  mov     rax, [r14+rax+30h]
0x18000d542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d547  mov     esi, eax
0x18000d549  test    eax, eax
0x18000d54b  jz      short loc_18000D5AF
0x18000d54d  cmp     cs:byte_18004DF33, 0
0x18000d554  jge     short loc_18000D59D
0x18000d556  mov     r8, cs:CpTable
0x18000d55d  lea     rdx, aResetForProtoc; "Reset for protocol = %x failed with err"...
0x18000d564  xor     ecx, ecx
0x18000d566  mov     r9d, eax
0x18000d569  mov     word ptr [rsp+848h+var_828], cx
0x18000d56e  lea     rcx, [rsp+848h+var_828]
0x18000d573  mov     r8d, [r14+r8]
0x18000d577  call    FormatRRASErrorString
0x18000d57c  cmp     cs:byte_18004DF33, 0
0x18000d583  jge     short loc_18000D59D
0x18000d585  lea     r8, [rsp+848h+var_828]
0x18000d58a  lea     rdx, RasPppTraceError
0x18000d591  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d598  call    McTemplateU0z_EventWriteTransfer
0x18000d59d  mov     edx, edi
0x18000d59f  mov     [rbx+28h], esi
0x18000d5a2  mov     rcx, rbp
0x18000d5a5  call    FsmClose
0x18000d5aa  jmp     loc_18000D4A1
0x18000d5af  mov     eax, 1
0x18000d5b4  mov     rcx, [rsp+848h+var_28]
0x18000d5bc  xor     rcx, rsp; StackCookie
0x18000d5bf  call    __security_check_cookie
0x18000d5c4  lea     r11, [rsp+848h+var_18]
0x18000d5cc  mov     rbx, [r11+30h]
0x18000d5d0  mov     rbp, [r11+38h]
0x18000d5d4  mov     rsp, r11
0x18000d5d7  pop     r14
0x18000d5d9  pop     rdi
0x18000d5da  pop     rsi
0x18000d5db  retn
```
