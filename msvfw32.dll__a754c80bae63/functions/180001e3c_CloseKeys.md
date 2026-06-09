# CloseKeys

- ea: `0x180001e3c`
- end: `0x180001e95`
- name: `CloseKeys`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001010`

## callees

- `0x180001e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e63`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180001e77`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180001e77`

## pseudocode

```c
__int64 CloseKeys()
{
  int i; // eax
  __int64 result; // rax

  for ( i = keyscached; keyscached; i = keyscached )
  {
    keyscached = i - 1;
    RegCloseKey((HKEY)ahkey[i - 1]);
    DeleteAtom(akeyatoms[keyscached]);
  }
  result = (unsigned int)(i - 1);
  keyscached = result;
  return result;
}

```

## disassembly

```asm
0x180001e3c  push    rdi
0x180001e3e  sub     rsp, 20h
0x180001e42  mov     eax, cs:keyscached
0x180001e48  test    eax, eax
0x180001e4a  jz      short loc_180001E87
0x180001e4c  lea     rdi, cs:180000000h
0x180001e53  dec     eax
0x180001e55  mov     cs:keyscached, eax
0x180001e5b  mov     rcx, rva ahkey[rdi+rax*8]; hKey
0x180001e63  call    cs:__imp_RegCloseKey
0x180001e69  mov     ecx, cs:keyscached
0x180001e6f  movzx   ecx, rva akeyatoms[rdi+rcx*2]; nAtom
0x180001e77  call    cs:__imp_DeleteAtom
0x180001e7d  mov     eax, cs:keyscached
0x180001e83  test    eax, eax
0x180001e85  jnz     short loc_180001E53
0x180001e87  dec     eax
0x180001e89  mov     cs:keyscached, eax
0x180001e8f  add     rsp, 20h
0x180001e93  pop     rdi
0x180001e94  retn
```
