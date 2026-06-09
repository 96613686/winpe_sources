# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180005c00`
- end: `0x180005c7a`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `122`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c80`
- `0x180005d4c`
- `0x180005e94`
- `0x180006ec4`
- `0x18001fb4c`
- `0x18001fc48`
- `0x18001fd80`
- `0x18001fedc`

## callees

- `0x1800026d4`
- `0x180005c00`
- `0x1800163ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005c51`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005c51`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  size_t v3; // rcx
  void *v4; // rax
  __int64 v5; // rdx
  void *v6; // rcx
  _QWORD *result; // rax

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    goto LABEL_10;
  v3 = 2LL * *a2;
  if ( v3 < 0x1000 )
    goto LABEL_7;
  if ( v3 + 39 < v3 )
LABEL_10:
    __scrt_throw_std_bad_array_new_length();
  v4 = operator new(v3 + 39);
  v6 = v4;
  if ( v4 )
  {
    result = (_QWORD *)(((unsigned __int64)v4 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(result - 1) = v6;
    goto LABEL_9;
  }
  _o__invalid_parameter_noinfo_noreturn(0, v5);
  __debugbreak();
LABEL_7:
  result = 0;
  if ( v3 )
    result = operator new(v3);
LABEL_9:
  --*a2;
  return result;
}

```

## disassembly

```asm
0x180005c00  push    rbx
0x180005c02  sub     rsp, 20h
0x180005c06  inc     qword ptr [rdx]
0x180005c09  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005c13  mov     rcx, [rdx]
0x180005c16  mov     rbx, rdx
0x180005c19  cmp     rcx, rax
0x180005c1c  ja      short loc_180005C74
0x180005c1e  add     rcx, rcx
0x180005c21  cmp     rcx, 1000h
0x180005c28  jb      short loc_180005C5E
0x180005c2a  lea     rax, [rcx+27h]
0x180005c2e  cmp     rax, rcx
0x180005c31  jbe     short loc_180005C74
0x180005c33  mov     rcx, rax; Size
0x180005c36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c3b  mov     rcx, rax
0x180005c3e  test    rax, rax
0x180005c41  jz      short loc_180005C51
0x180005c43  lea     rax, [rax+27h]
0x180005c47  and     rax, 0FFFFFFFFFFFFFFE0h
0x180005c4b  mov     [rax-8], rcx
0x180005c4f  jmp     short loc_180005C6A
0x180005c51  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005c58  nop     dword ptr [rax+rax+00h]
0x180005c5d  int     3; Trap to Debugger
0x180005c5e  xor     eax, eax
0x180005c60  test    rcx, rcx
0x180005c63  jz      short loc_180005C6A
0x180005c65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c6a  dec     qword ptr [rbx]
0x180005c6d  add     rsp, 20h
0x180005c71  pop     rbx
0x180005c72  retn
0x180005c74  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
