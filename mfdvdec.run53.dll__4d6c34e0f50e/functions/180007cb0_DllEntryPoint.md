# _DllEntryPoint

- ea: `0x180007cb0`
- end: `0x180007cfa`
- name: `_DllEntryPoint`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800065c8`

## callees

- `0x180007cb0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007cbd`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007cbd`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  void (__fastcall *v2)(__int64, _QWORD); // rax
  __int64 v3; // rcx

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      DisableThreadLibraryCalls(a1);
      v2 = (void (__fastcall *)(__int64, _QWORD))qword_180022018;
      if ( qword_180022018 )
      {
        v3 = 1;
LABEL_7:
        v2(v3, off_180022008);
      }
    }
  }
  else
  {
    v2 = (void (__fastcall *)(__int64, _QWORD))qword_180022018;
    if ( qword_180022018 )
    {
      v3 = 0;
      goto LABEL_7;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180007cb0  sub     rsp, 28h
0x180007cb4  test    edx, edx
0x180007cb6  jz      short loc_180007CD6
0x180007cb8  cmp     edx, 1
0x180007cbb  jnz     short loc_180007CF0
0x180007cbd  call    cs:__imp_DisableThreadLibraryCalls
0x180007cc3  mov     rax, cs:qword_180022018
0x180007cca  test    rax, rax
0x180007ccd  jz      short loc_180007CF0
0x180007ccf  mov     ecx, 1
0x180007cd4  jmp     short loc_180007CE4
0x180007cd6  mov     rax, cs:qword_180022018
0x180007cdd  test    rax, rax
0x180007ce0  jz      short loc_180007CF0
0x180007ce2  xor     ecx, ecx
0x180007ce4  mov     rdx, cs:off_180022008
0x180007ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf0  mov     eax, 1
0x180007cf5  add     rsp, 28h
0x180007cf9  retn
```
