# PerflibciIsLocalQueryFromHandle

- ea: `0x180016574`
- end: `0x1800165c8`
- name: `PerflibciIsLocalQueryFromHandle`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180018960`
- `0x180018c80`
- `0x180018dd0`
- `0x180019060`
- `0x1800191b0`

## callees

- `0x180007300`
- `0x18000dca0`
- `0x180016574`

## pseudocode

```c
__int64 __fastcall PerflibciIsLocalQueryFromHandle(__int64 a1)
{
  DWORD v2; // edi
  int v3; // ebx

  v2 = 87;
  if ( a1 )
  {
    v3 = *(_DWORD *)(a1 + 36);
    if ( v3 == PerflibciValidateCode() )
    {
      v2 = PerflibciLocalWaitForMutex(*(void **)a1);
      if ( !v2 )
        return (*(_BYTE *)(a1 + 32) & 1) != 0 ? 0xD : 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180016574  mov     [rsp+arg_0], rbx
0x180016579  mov     [rsp+arg_8], rsi
0x18001657e  push    rdi
0x18001657f  sub     rsp, 20h
0x180016583  mov     rsi, rcx
0x180016586  mov     edi, 57h ; 'W'
0x18001658b  test    rcx, rcx
0x18001658e  jz      short loc_1800165B6
0x180016590  mov     ebx, [rcx+24h]
0x180016593  call    ?PerflibciValidateCode@@YAKXZ; PerflibciValidateCode(void)
0x180016598  cmp     ebx, eax
0x18001659a  jnz     short loc_1800165B6
0x18001659c  mov     rcx, [rsi]; void *
0x18001659f  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x1800165a4  mov     edi, eax
0x1800165a6  test    eax, eax
0x1800165a8  jnz     short loc_1800165B6
0x1800165aa  mov     al, [rsi+20h]
0x1800165ad  and     al, 1
0x1800165af  neg     al
0x1800165b1  sbb     edi, edi
0x1800165b3  and     edi, 0Dh
0x1800165b6  mov     rbx, [rsp+28h+arg_0]
0x1800165bb  mov     eax, edi
0x1800165bd  mov     rsi, [rsp+28h+arg_8]
0x1800165c2  add     rsp, 20h
0x1800165c6  pop     rdi
0x1800165c7  retn
```
