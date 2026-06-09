# SetNoMppeKeys

- ea: `0x180003660`
- end: `0x18000376a`
- name: `SetNoMppeKeys`
- size: `266`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003770`
- `0x18000e86c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180003660`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180003708`: `RasCompressionSetInfo(NULL) failed, Error=%d`

## pseudocode

```c
__int64 __fastcall SetNoMppeKeys(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  _BYTE v5[104]; // [rsp+20h] [rbp-E0h] BYREF
  int v6; // [rsp+88h] [rbp-78h]
  _BYTE v7[104]; // [rsp+190h] [rbp+90h] BYREF
  int v8; // [rsp+1F8h] [rbp+F8h]
  int v9; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v10[2044]; // [rsp+304h] [rbp+204h] BYREF

  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  memset_0(v7, 0, 0x170u);
  v8 = 4;
  memset_0(v5, 0, 0x170u);
  v6 = 4;
  v2 = (*((__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))&xmmword_18004C490 + 1))(a1, v7, v5);
  v3 = v2;
  if ( v2 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"RasCompressionSetInfo(NULL) failed, Error=%d", v2);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v9);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003660  mov     [rsp-8+arg_8], rbx
0x180003665  push    rbp
0x180003666  lea     rbp, [rsp-0A10h]
0x18000366e  sub     rsp, 0B10h
0x180003675  mov     rax, cs:__security_cookie
0x18000367c  xor     rax, rsp
0x18000367f  mov     [rbp+0A10h+var_10], rax
0x180003686  mov     rbx, rcx
0x180003689  xor     eax, eax
0x18000368b  lea     rcx, [rbp+0A10h+var_80C]; void *
0x180003692  mov     [rbp+0A10h+var_810], eax
0x180003698  xor     edx, edx; Val
0x18000369a  mov     r8d, 7FCh; Size
0x1800036a0  call    memset_0
0x1800036a5  xor     edx, edx; Val
0x1800036a7  lea     rcx, [rbp+0A10h+var_980]; void *
0x1800036ae  mov     r8d, 170h; Size
0x1800036b4  call    memset_0
0x1800036b9  xor     edx, edx; Val
0x1800036bb  mov     [rbp+0A10h+var_918], 4
0x1800036c5  mov     r8d, 170h; Size
0x1800036cb  lea     rcx, [rsp+0B10h+var_AF0]; void *
0x1800036d0  call    memset_0
0x1800036d5  mov     rax, qword ptr cs:xmmword_18004C490+8
0x1800036dc  lea     r8, [rsp+0B10h+var_AF0]
0x1800036e1  lea     rdx, [rbp+0A10h+var_980]
0x1800036e8  mov     [rbp+0A10h+var_A88], 4
0x1800036ef  mov     rcx, rbx
0x1800036f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f7  mov     ebx, eax
0x1800036f9  test    eax, eax
0x1800036fb  jz      short loc_180003748
0x1800036fd  cmp     cs:byte_18004CF33, 0
0x180003704  jge     short loc_180003748
0x180003706  xor     ecx, ecx
0x180003708  lea     rdx, aRascompression_0; "RasCompressionSetInfo(NULL) failed, Err"...
0x18000370f  mov     word ptr [rbp+0A10h+var_810], cx
0x180003716  mov     r8d, eax
0x180003719  lea     rcx, [rbp+0A10h+var_810]
0x180003720  call    FormatRRASErrorString
0x180003725  cmp     cs:byte_18004CF33, 0
0x18000372c  jge     short loc_180003748
0x18000372e  lea     r8, [rbp+0A10h+var_810]
0x180003735  lea     rdx, RasPppTraceError
0x18000373c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003743  call    McTemplateU0z_EventWriteTransfer
0x180003748  mov     eax, ebx
0x18000374a  mov     rcx, [rbp+0A10h+var_10]
0x180003751  xor     rcx, rsp; StackCookie
0x180003754  call    __security_check_cookie
0x180003759  mov     rbx, [rsp+0B10h+arg_8]
0x180003761  add     rsp, 0B10h
0x180003768  pop     rbp
0x180003769  retn
```
