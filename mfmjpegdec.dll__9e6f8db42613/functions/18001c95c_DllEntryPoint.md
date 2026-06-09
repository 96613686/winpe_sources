# _DllEntryPoint

- ea: `0x18001c95c`
- end: `0x18001c987`
- name: `_DllEntryPoint`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c8e4`

## callees

- `0x18001c95c`
- `0x18003e2f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001c969`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001c969`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  int v2; // ecx

  if ( !a2 )
  {
    v2 = 0;
    goto LABEL_5;
  }
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    v2 = 1;
LABEL_5:
    DllInitClasses(v2);
  }
  return 1;
}

```

## disassembly

```asm
0x18001c95c  sub     rsp, 28h
0x18001c960  test    edx, edx
0x18001c962  jz      short loc_18001C976
0x18001c964  cmp     edx, 1
0x18001c967  jnz     short loc_18001C97D
0x18001c969  call    cs:__imp_DisableThreadLibraryCalls
0x18001c96f  mov     ecx, 1
0x18001c974  jmp     short loc_18001C978
0x18001c976  xor     ecx, ecx; int
0x18001c978  call    ?DllInitClasses@@YAXH@Z; DllInitClasses(int)
0x18001c97d  mov     eax, 1
0x18001c982  add     rsp, 28h
0x18001c986  retn
```
