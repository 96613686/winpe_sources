# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x180009f54`
- end: `0x180009f9b`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b44c`

## callees

- `0x180009f54`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180009f79`
- `KERNEL32!lstrcmpiW` at `0x180009f79`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CanForceRemoveKey(ATL::CRegParser *this, const unsigned __int16 *a2)
{
  int i; // ebx

  for ( i = 0; i < 12; ++i )
  {
    if ( !lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[i]) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180009f54  mov     [rsp+arg_0], rbx
0x180009f59  push    rdi
0x180009f5a  sub     rsp, 20h
0x180009f5e  mov     rdi, rdx
0x180009f61  xor     ebx, ebx
0x180009f63  cmp     ebx, 0Ch
0x180009f66  jge     short loc_180009F8B
0x180009f68  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180009f6f  movsxd  rdx, ebx
0x180009f72  mov     rcx, rdi; lpString1
0x180009f75  mov     rdx, [rax+rdx*8]; lpString2
0x180009f79  call    cs:__imp_lstrcmpiW
0x180009f7f  test    eax, eax
0x180009f81  jz      short loc_180009F87
0x180009f83  inc     ebx
0x180009f85  jmp     short loc_180009F63
0x180009f87  xor     eax, eax
0x180009f89  jmp     short loc_180009F90
0x180009f8b  mov     eax, 1
0x180009f90  mov     rbx, [rsp+28h+arg_0]
0x180009f95  add     rsp, 20h
0x180009f99  pop     rdi
0x180009f9a  retn
```
