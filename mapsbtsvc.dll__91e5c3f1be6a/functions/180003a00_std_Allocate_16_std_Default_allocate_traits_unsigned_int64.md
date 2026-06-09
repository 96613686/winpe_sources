# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180003a00`
- end: `0x180003a57`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a60`
- `0x180003eac`
- `0x180005a1c`
- `0x18000990c`
- `0x1800099b8`
- `0x180009a70`
- `0x180009b98`
- `0x180009c38`
- `0x18000a10c`
- `0x18000a31c`
- `0x18000a460`
- `0x18000a564`
- `0x18000a6d8`
- `0x18000a9b8`
- `0x18000aab8`
- `0x18000bb70`
- `0x18000fb54`
- `0x180010448`
- `0x180010594`
- `0x1800114f8`
- `0x18001167c`
- `0x180012d90`
- `0x180013168`

## callees

- `0x18000224c`
- `0x180003a00`
- `0x1800060f0`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return operator new(a1);
  if ( a1 + 39 < a1 )
    std::_Throw_bad_array_new_length();
  v2 = operator new(a1 + 39);
  v3 = v2;
  if ( !v2 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v3;
  return result;
}

```

## disassembly

```asm
0x180003a00  sub     rsp, 28h
0x180003a04  test    rcx, rcx
0x180003a07  jnz     short loc_180003A10
0x180003a09  xor     eax, eax
0x180003a0b  add     rsp, 28h
0x180003a0f  retn
0x180003a10  cmp     rcx, 1000h
0x180003a17  jb      short loc_180003A48
0x180003a19  lea     rax, [rcx+27h]
0x180003a1d  cmp     rax, rcx
0x180003a20  jbe     short loc_180003A51
0x180003a22  mov     rcx, rax; Size
0x180003a25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a2a  mov     rcx, rax
0x180003a2d  test    rax, rax
0x180003a30  jnz     short loc_180003A37
0x180003a32  lea     ecx, [rax+5]; Size
0x180003a35  int     29h; Win8: RtlFailFast(ecx)
0x180003a37  add     rax, 27h ; '''
0x180003a3b  and     rax, 0FFFFFFFFFFFFFFE0h
0x180003a3f  mov     [rax-8], rcx
0x180003a43  add     rsp, 28h
0x180003a47  retn
0x180003a48  add     rsp, 28h
0x180003a4c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a51  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
