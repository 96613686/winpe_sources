# CImpIAccessor::DeleteRedAccessor(tagREDACCESSOR *)

- ea: `0x1000d450`
- end: `0x1000d496`
- name: `?DeleteRedAccessor@CImpIAccessor@@AAGXPAUtagREDACCESSOR@@@Z`
- size: `70`
- prototype: `void(CImpIAccessor *__hidden this, struct tagREDACCESSOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000cff0`

## callees

- `0x1000d450`
- `0x1004cea1`

## pseudocode

```c
void __fastcall CImpIAccessor::DeleteRedAccessor(int a1, int a2)
{
  unsigned int i; // esi

  if ( *(_DWORD *)(a2 + 32) )
    operator delete(*(void **)(a2 + 32));
  for ( i = 0; i < *(_DWORD *)(a2 + 36); ++i )
  {
    if ( *(_DWORD *)(52 * i + a2 + 60) )
      operator delete(*(void **)(52 * i + a2 + 60));
  }
  operator delete((void *)a2);
}

```

## disassembly

```asm
0x1000d450  mov     edi, edi
0x1000d452  push    esi
0x1000d453  push    edi
0x1000d454  mov     edi, edx
0x1000d456  mov     eax, [edi+20h]
0x1000d459  test    eax, eax
0x1000d45b  jz      short loc_1000D466
0x1000d45d  push    eax; Block
0x1000d45e  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000d463  add     esp, 4
0x1000d466  xor     esi, esi
0x1000d468  cmp     [edi+24h], esi
0x1000d46b  jbe     short loc_1000D48A
0x1000d46d  nop     dword ptr [eax]
0x1000d470  imul    eax, esi, 34h ; '4'
0x1000d473  mov     eax, [eax+edi+3Ch]
0x1000d477  test    eax, eax
0x1000d479  jz      short loc_1000D484
0x1000d47b  push    eax; Block
0x1000d47c  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000d481  add     esp, 4
0x1000d484  inc     esi
0x1000d485  cmp     esi, [edi+24h]
0x1000d488  jb      short loc_1000D470
0x1000d48a  push    edi; Block
0x1000d48b  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000d490  add     esp, 4
0x1000d493  pop     edi
0x1000d494  pop     esi
0x1000d495  retn
```
