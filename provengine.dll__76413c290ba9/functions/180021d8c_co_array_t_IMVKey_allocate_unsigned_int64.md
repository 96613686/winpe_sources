# co_array_t<IMVKey *>::allocate(unsigned __int64)

- ea: `0x180021d8c`
- end: `0x180021e37`
- name: `?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z`
- size: `171`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001def0`
- `0x180030f6c`

## callees

- `0x180021cf4`
- `0x180021d14`
- `0x180021d8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180021db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180021db8`

## string_xrefs

- `0x180021de8`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180021e05`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180021e1c`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x180021d8c  mov     [rsp+arg_0], rbx
0x180021d91  push    rdi; int
0x180021d92  sub     rsp, 20h
0x180021d96  mov     eax, 8
0x180021d9b  mov     [rsp+28h+arg_10], 0
0x180021da4  mov     rbx, rdx
0x180021da7  mov     rdi, rcx
0x180021daa  mul     rdx
0x180021dad  test    rdx, rdx
0x180021db0  jnz     short loc_180021DE3
0x180021db2  mov     rcx, [rcx]; pv
0x180021db5  mov     rdx, rax; cb
0x180021db8  call    cs:__imp_CoTaskMemRealloc
0x180021dbe  mov     [rdi], rax
0x180021dc1  test    rbx, rbx
0x180021dc4  jz      short loc_180021DCB
0x180021dc6  test    rax, rax
0x180021dc9  jz      short loc_180021E00
0x180021dcb  mov     eax, 0FFFFFFFFh
0x180021dd0  cmp     rbx, rax
0x180021dd3  ja      short loc_180021E17
0x180021dd5  mov     [rdi+8], ebx
0x180021dd8  mov     rbx, [rsp+28h+arg_0]
0x180021ddd  add     rsp, 20h
0x180021de1  pop     rdi
0x180021de2  retn
0x180021de3  mov     rcx, [rsp+28h]; this
0x180021de8  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180021def  mov     r9d, 80070216h; char *
0x180021df5  mov     edx, 3Bh ; ';'; void *
0x180021dfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021e00  mov     rcx, [rsp+28h]; this
0x180021e05  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180021e0c  mov     edx, 3Fh ; '?'; void *
0x180021e11  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021e17  mov     rcx, [rsp+28h]; this
0x180021e1c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180021e23  mov     r9d, 80070216h; char *
0x180021e29  mov     [rdi+8], eax
0x180021e2c  mov     edx, 41h ; 'A'; void *
0x180021e31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
