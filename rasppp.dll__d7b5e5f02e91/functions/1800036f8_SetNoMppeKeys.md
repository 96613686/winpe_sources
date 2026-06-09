# SetNoMppeKeys

- ea: `0x1800036f8`
- end: `0x180003803`
- name: `SetNoMppeKeys`
- size: `267`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000380c`
- `0x18000ecac`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800036f8`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x1800037a0`: `RasCompressionSetInfo(NULL) failed, Error=%d`

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
  v2 = (*((__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))&xmmword_18004D490 + 1))(a1, v7, v5);
  v3 = v2;
  if ( v2 )
  {
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString((wchar_t *)&v9, L"RasCompressionSetInfo(NULL) failed, Error=%d", v2);
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceError,
          (const wchar_t *)&v9);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800036f8  mov     [rsp-8+arg_8], rbx
0x1800036fd  push    rbp
0x1800036fe  lea     rbp, [rsp-0A10h]
0x180003706  sub     rsp, 0B10h
0x18000370d  mov     rax, cs:__security_cookie
0x180003714  xor     rax, rsp
0x180003717  mov     [rbp+0A10h+var_10], rax
0x18000371e  mov     rbx, rcx
0x180003721  xor     eax, eax
0x180003723  lea     rcx, [rbp+0A10h+var_80C]; void *
0x18000372a  mov     [rbp+0A10h+var_810], eax
0x180003730  xor     edx, edx; Val
0x180003732  mov     r8d, 7FCh; Size
0x180003738  call    memset_0
0x18000373d  xor     edx, edx; Val
0x18000373f  lea     rcx, [rbp+0A10h+var_980]; void *
0x180003746  mov     r8d, 170h; Size
0x18000374c  call    memset_0
0x180003751  xor     edx, edx; Val
0x180003753  mov     [rbp+0A10h+var_918], 4
0x18000375d  mov     r8d, 170h; Size
0x180003763  lea     rcx, [rsp+0B10h+var_AF0]; void *
0x180003768  call    memset_0
0x18000376d  mov     rax, qword ptr cs:xmmword_18004D490+8
0x180003774  lea     r8, [rsp+0B10h+var_AF0]
0x180003779  lea     rdx, [rbp+0A10h+var_980]
0x180003780  mov     [rbp+0A10h+var_A88], 4
0x180003787  mov     rcx, rbx
0x18000378a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378f  mov     ebx, eax
0x180003791  test    eax, eax
0x180003793  jz      short loc_1800037E0
0x180003795  cmp     cs:byte_18004DF33, 0
0x18000379c  jge     short loc_1800037E0
0x18000379e  xor     ecx, ecx
0x1800037a0  lea     rdx, aRascompression_0; "RasCompressionSetInfo(NULL) failed, Err"...
0x1800037a7  mov     word ptr [rbp+0A10h+var_810], cx
0x1800037ae  mov     r8d, eax
0x1800037b1  lea     rcx, [rbp+0A10h+var_810]
0x1800037b8  call    FormatRRASErrorString
0x1800037bd  cmp     cs:byte_18004DF33, 0
0x1800037c4  jge     short loc_1800037E0
0x1800037c6  lea     r8, [rbp+0A10h+var_810]
0x1800037cd  lea     rdx, RasPppTraceError
0x1800037d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800037db  call    McTemplateU0z_EventWriteTransfer
0x1800037e0  mov     eax, ebx
0x1800037e2  mov     rcx, [rbp+0A10h+var_10]
0x1800037e9  xor     rcx, rsp; StackCookie
0x1800037ec  call    __security_check_cookie
0x1800037f1  mov     rbx, [rsp+0B10h+arg_8]
0x1800037f9  add     rsp, 0B10h
0x180003800  pop     rbp
0x180003801  retn
```
