# co_array_t<IMVKey *>::allocate(unsigned __int64)

- ea: `0x180014a6c`
- end: `0x180014b17`
- name: `?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z`
- size: `171`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013e50`
- `0x180017d04`
- `0x18002eb90`
- `0x180036710`

## callees

- `0x180012d80`
- `0x180012da0`
- `0x180014a6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180014a98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180014a98`

## string_xrefs

- `0x180014ac8`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180014ae5`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180014afc`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
__int64 __fastcall co_array_t<IMVKey *>::allocate(__int64 a1, unsigned __int64 a2)
{
  LPVOID v4; // rax
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !is_mul_ok(a2, 8u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
      (const char *)0x80070216LL,
      v7);
  v4 = CoTaskMemRealloc(*(LPVOID *)a1, 8 * a2);
  *(_QWORD *)a1 = v4;
  if ( a2 && !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3F,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
      v5);
  result = 0xFFFFFFFFLL;
  if ( a2 > 0xFFFFFFFF )
  {
    *(_DWORD *)(a1 + 8) = -1;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
      (const char *)0x80070216LL,
      v7);
  }
  *(_DWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x180014a6c  mov     [rsp+arg_0], rbx
0x180014a71  push    rdi; int
0x180014a72  sub     rsp, 20h
0x180014a76  mov     eax, 8
0x180014a7b  mov     [rsp+28h+arg_10], 0
0x180014a84  mov     rbx, rdx
0x180014a87  mov     rdi, rcx
0x180014a8a  mul     rdx
0x180014a8d  test    rdx, rdx
0x180014a90  jnz     short loc_180014AC3
0x180014a92  mov     rcx, [rcx]; pv
0x180014a95  mov     rdx, rax; cb
0x180014a98  call    cs:__imp_CoTaskMemRealloc
0x180014a9e  mov     [rdi], rax
0x180014aa1  test    rbx, rbx
0x180014aa4  jz      short loc_180014AAB
0x180014aa6  test    rax, rax
0x180014aa9  jz      short loc_180014AE0
0x180014aab  mov     eax, 0FFFFFFFFh
0x180014ab0  cmp     rbx, rax
0x180014ab3  ja      short loc_180014AF7
0x180014ab5  mov     [rdi+8], ebx
0x180014ab8  mov     rbx, [rsp+28h+arg_0]
0x180014abd  add     rsp, 20h
0x180014ac1  pop     rdi
0x180014ac2  retn
0x180014ac3  mov     rcx, [rsp+28h]; this
0x180014ac8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014acf  mov     r9d, 80070216h; char *
0x180014ad5  mov     edx, 3Bh ; ';'; void *
0x180014ada  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014ae0  mov     rcx, [rsp+28h]; this
0x180014ae5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014aec  mov     edx, 3Fh ; '?'; void *
0x180014af1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180014af7  mov     rcx, [rsp+28h]; this
0x180014afc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014b03  mov     r9d, 80070216h; char *
0x180014b09  mov     [rdi+8], eax
0x180014b0c  mov     edx, 41h ; 'A'; void *
0x180014b11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
