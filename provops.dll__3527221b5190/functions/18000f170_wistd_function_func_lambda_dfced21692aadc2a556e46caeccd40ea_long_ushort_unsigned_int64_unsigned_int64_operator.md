# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000f170`
- end: `0x18000f1d2`
- name: `??R?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007654`
- `0x18000f170`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000f192`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000f192`

## string_xrefs

- `0x18000f1a7`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  DWORD FullPathNameW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  FullPathNameW = GetFullPathNameW(**(LPCWSTR **)(a1 + 8), *a3, *a2, 0);
  *v5 = FullPathNameW;
  if ( !FullPathNameW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAA,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             v7);
  if ( FullPathNameW < v4 )
    *v5 = FullPathNameW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18000f170  mov     [rsp+arg_0], rbx
0x18000f175  push    rdi
0x18000f176  sub     rsp, 20h
0x18000f17a  mov     rbx, [r8]
0x18000f17d  mov     rax, rdx
0x18000f180  mov     rcx, [rcx+8]
0x18000f184  mov     edx, ebx; nBufferLength
0x18000f186  mov     rdi, [r9]
0x18000f189  xor     r9d, r9d; lpFilePart
0x18000f18c  mov     r8, [rax]; lpBuffer
0x18000f18f  mov     rcx, [rcx]; lpFileName
0x18000f192  call    cs:__imp_GetFullPathNameW
0x18000f198  mov     eax, eax
0x18000f19a  mov     [rdi], rax
0x18000f19d  test    rax, rax
0x18000f1a0  jnz     short loc_18000F1BA
0x18000f1a2  mov     rcx, [rsp+28h]; this
0x18000f1a7  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f1ae  mov     edx, 0AAh; void *
0x18000f1b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f1b8  jmp     short loc_18000F1C7
0x18000f1ba  cmp     rax, rbx
0x18000f1bd  jnb     short loc_18000F1C5
0x18000f1bf  inc     rax
0x18000f1c2  mov     [rdi], rax
0x18000f1c5  xor     eax, eax
0x18000f1c7  mov     rbx, [rsp+28h+arg_0]
0x18000f1cc  add     rsp, 20h
0x18000f1d0  pop     rdi
0x18000f1d1  retn
```
