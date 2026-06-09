# IsOkayToExec

- ea: `0x180001a68`
- end: `0x180001a91`
- name: `IsOkayToExec`
- size: `41`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180004074`
- `0x18000ba40`
- `0x18001f0c4`
- `0x18001f1f0`
- `0x18001f9e4`
- `0x18001fd20`
- `0x18002071c`
- `0x180020820`
- `0x18002092c`
- `0x180020b14`
- `0x180020ccc`
- `0x180027a68`
- `0x180027f0c`

## callees

- `0x180001a68`
- `0x180001a98`
- `0x180006bf4`

## pseudocode

```c
__int64 __fastcall IsOkayToExec(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int Client; // eax
  unsigned int v5; // ecx

  if ( (int)LocateClient(a1, a2, a3, a4) >= 0 )
    return 0;
  Client = CreateClient(1, 0);
  v5 = 0;
  if ( Client < 0 )
    return (unsigned int)Client;
  return v5;
}

```

## disassembly

```asm
0x180001a68  sub     rsp, 28h
0x180001a6c  call    LocateClient
0x180001a71  test    eax, eax
0x180001a73  jns     short loc_180001A8D
0x180001a75  xor     edx, edx
0x180001a77  mov     cl, 1
0x180001a79  call    CreateClient
0x180001a7e  xor     ecx, ecx
0x180001a80  test    eax, eax
0x180001a82  cmovs   ecx, eax
0x180001a85  mov     eax, ecx
0x180001a87  add     rsp, 28h
0x180001a8b  retn
0x180001a8d  xor     eax, eax
0x180001a8f  jmp     short loc_180001A87
```
