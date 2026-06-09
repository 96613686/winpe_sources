# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x180009984`
- end: `0x1800099cb`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae30`

## callees

- `0x180009984`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800099a9`
- `KERNEL32!lstrcmpiW` at `0x1800099a9`

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
0x180009984  mov     [rsp+arg_0], rbx
0x180009989  push    rdi
0x18000998a  sub     rsp, 20h
0x18000998e  mov     rdi, rdx
0x180009991  xor     ebx, ebx
0x180009993  cmp     ebx, 0Ch
0x180009996  jge     short loc_1800099BB
0x180009998  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000999f  movsxd  rdx, ebx
0x1800099a2  mov     rcx, rdi; lpString1
0x1800099a5  mov     rdx, [rax+rdx*8]; lpString2
0x1800099a9  call    cs:__imp_lstrcmpiW
0x1800099af  test    eax, eax
0x1800099b1  jz      short loc_1800099B7
0x1800099b3  inc     ebx
0x1800099b5  jmp     short loc_180009993
0x1800099b7  xor     eax, eax
0x1800099b9  jmp     short loc_1800099C0
0x1800099bb  mov     eax, 1
0x1800099c0  mov     rbx, [rsp+28h+arg_0]
0x1800099c5  add     rsp, 20h
0x1800099c9  pop     rdi
0x1800099ca  retn
```
