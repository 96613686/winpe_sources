# AllocAndReturnOpenStoreStruct

- ea: `0x18002e55c`
- end: `0x18002e5db`
- name: `AllocAndReturnOpenStoreStruct`
- size: `127`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *Src, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e5f0`
- `0x18002e830`
- `0x18002ea20`

## callees

- `0x18000590c`
- `0x18002e55c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e57a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e5ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e5ae`

## pseudocode

```c
_QWORD *__fastcall AllocAndReturnOpenStoreStruct(int a1, __int64 a2, int a3, __int64 a4, unsigned __int16 *Src, int a6)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  unsigned __int16 *v13; // rax

  v10 = LocalAlloc(0x40u, 0x38u);
  v11 = v10;
  if ( !v10 )
    return 0;
  *(_DWORD *)v10 = a1;
  if ( a1 )
  {
    v10[1] = a2;
  }
  else
  {
    v13 = AllocAndCopyWStr(Src);
    v11[4] = v13;
    if ( !v13 )
    {
      LocalFree(v11);
      return 0;
    }
    *((_DWORD *)v11 + 4) = a3;
    v11[3] = a4;
    v11[5] = 0;
  }
  *((_DWORD *)v11 + 12) = a6;
  return v11;
}

```

## disassembly

```asm
0x18002e55c  push    rbx
0x18002e55e  push    rbp
0x18002e55f  push    rsi
0x18002e560  push    rdi
0x18002e561  push    r14
0x18002e563  sub     rsp, 20h
0x18002e567  mov     rsi, rdx
0x18002e56a  mov     edi, ecx
0x18002e56c  mov     edx, 38h ; '8'; uBytes
0x18002e571  mov     rbp, r9
0x18002e574  mov     r14d, r8d
0x18002e577  lea     ecx, [rdx+8]; uFlags
0x18002e57a  call    cs:__imp_LocalAlloc
0x18002e580  mov     rbx, rax
0x18002e583  test    rax, rax
0x18002e586  jnz     short loc_18002E58C
0x18002e588  xor     eax, eax
0x18002e58a  jmp     short loc_18002E5D0
0x18002e58c  mov     [rax], edi
0x18002e58e  test    edi, edi
0x18002e590  jz      short loc_18002E598
0x18002e592  mov     [rax+8], rsi
0x18002e596  jmp     short loc_18002E5C6
0x18002e598  mov     rcx, [rsp+48h+Src]; Src
0x18002e59d  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x18002e5a2  mov     [rbx+20h], rax
0x18002e5a6  test    rax, rax
0x18002e5a9  jnz     short loc_18002E5B6
0x18002e5ab  mov     rcx, rbx; hMem
0x18002e5ae  call    cs:__imp_LocalFree
0x18002e5b4  jmp     short loc_18002E588
0x18002e5b6  mov     [rbx+10h], r14d
0x18002e5ba  mov     [rbx+18h], rbp
0x18002e5be  mov     qword ptr [rbx+28h], 0
0x18002e5c6  mov     eax, [rsp+48h+arg_28]
0x18002e5ca  mov     [rbx+30h], eax
0x18002e5cd  mov     rax, rbx
0x18002e5d0  add     rsp, 20h
0x18002e5d4  pop     r14
0x18002e5d6  pop     rdi
0x18002e5d7  pop     rsi
0x18002e5d8  pop     rbp
0x18002e5d9  pop     rbx
0x18002e5da  retn
```
