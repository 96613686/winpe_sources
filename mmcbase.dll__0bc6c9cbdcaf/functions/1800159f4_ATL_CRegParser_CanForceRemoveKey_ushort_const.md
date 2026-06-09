# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x1800159f4`
- end: `0x180015a3b`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008670`

## callees

- `0x1800159f4`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180015a19`
- `KERNEL32!lstrcmpiW` at `0x180015a19`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CanForceRemoveKey(ATL::CRegParser *this, const unsigned __int16 *a2)
{
  int i; // ebx

  for ( i = 0; i < 2; ++i )
  {
    if ( !lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[i]) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800159f4  mov     [rsp+arg_0], rbx
0x1800159f9  push    rdi
0x1800159fa  sub     rsp, 20h
0x1800159fe  mov     rdi, rdx
0x180015a01  xor     ebx, ebx
0x180015a03  cmp     ebx, 2
0x180015a06  jge     short loc_180015A2B
0x180015a08  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x180015a0f  movsxd  rdx, ebx
0x180015a12  mov     rcx, rdi; lpString1
0x180015a15  mov     rdx, [rax+rdx*8]; lpString2
0x180015a19  call    cs:__imp_lstrcmpiW
0x180015a1f  test    eax, eax
0x180015a21  jz      short loc_180015A27
0x180015a23  inc     ebx
0x180015a25  jmp     short loc_180015A03
0x180015a27  xor     eax, eax
0x180015a29  jmp     short loc_180015A30
0x180015a2b  mov     eax, 1
0x180015a30  mov     rbx, [rsp+28h+arg_0]
0x180015a35  add     rsp, 20h
0x180015a39  pop     rdi
0x180015a3a  retn
```
