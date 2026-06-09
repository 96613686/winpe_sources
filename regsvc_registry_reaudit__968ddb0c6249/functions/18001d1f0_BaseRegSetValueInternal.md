# BaseRegSetValueInternal

- ea: `0x18001d1f0`
- end: `0x18001d283`
- name: `BaseRegSetValueInternal`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a0c0`

## callees

- `0x18001d1f0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001d26b`
- `ntdll!NtSetValueKey` at `0x18001d25f`
- `ntdll!NtSetValueKey` at `0x18001d25f`

## pseudocode

```c
ULONG __fastcall BaseRegSetValueInternal(void *a1, struct _UNICODE_STRING *a2, ULONG a3, void *Data, ULONG DataSize)
{
  __int16 Length; // ax
  NTSTATUS v6; // eax

  if ( !a2 )
    goto LABEL_5;
  Length = a2->Length;
  if ( (a2->Length & 1) != 0 )
    goto LABEL_5;
  if ( Length )
  {
    if ( a2->Buffer )
    {
LABEL_9:
      a2->Length = Length - 2;
      goto LABEL_10;
    }
LABEL_5:
    if ( a2->Buffer || a2->Length != 2 || a2->MaximumLength )
      return 87;
    Length = 2;
    goto LABEL_9;
  }
LABEL_10:
  if ( a1 == (void *)-2147483644LL || a1 == (void *)-2147483568LL || a1 == (void *)-2147483552LL )
    return 5;
  v6 = NtSetValueKey(a1, a2, 0, a3, Data, DataSize);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x18001d1f0  sub     rsp, 38h
0x18001d1f4  xor     r10d, r10d
0x18001d1f7  mov     r11d, 2
0x18001d1fd  test    rdx, rdx
0x18001d200  jz      short loc_18001D214
0x18001d202  movzx   eax, word ptr [rdx]
0x18001d205  test    al, 1
0x18001d207  jnz     short loc_18001D214
0x18001d209  test    ax, ax
0x18001d20c  jz      short loc_18001D231
0x18001d20e  cmp     [rdx+8], r10
0x18001d212  jnz     short loc_18001D22A
0x18001d214  cmp     [rdx+8], r10
0x18001d218  jnz     short loc_18001D279
0x18001d21a  cmp     [rdx], r11w
0x18001d21e  jnz     short loc_18001D279
0x18001d220  cmp     [rdx+2], r10w
0x18001d225  jnz     short loc_18001D279
0x18001d227  mov     eax, r11d
0x18001d22a  sub     ax, r11w
0x18001d22e  mov     [rdx], ax
0x18001d231  cmp     rcx, 0FFFFFFFF80000004h
0x18001d238  jz      short loc_18001D272
0x18001d23a  cmp     rcx, 0FFFFFFFF80000050h
0x18001d241  jz      short loc_18001D272
0x18001d243  cmp     rcx, 0FFFFFFFF80000060h
0x18001d24a  jz      short loc_18001D272
0x18001d24c  mov     eax, [rsp+38h+arg_20]
0x18001d250  mov     [rsp+38h+DataSize], eax; DataSize
0x18001d254  mov     [rsp+38h+Data], r9; Data
0x18001d259  mov     r9d, r8d; Type
0x18001d25c  xor     r8d, r8d; TitleIndex
0x18001d25f  call    cs:__imp_NtSetValueKey
0x18001d265  mov     ecx, eax
0x18001d267  add     rsp, 38h
0x18001d26b  jmp     cs:__imp_RtlNtStatusToDosError
0x18001d272  mov     eax, 5
0x18001d277  jmp     short loc_18001D27E
0x18001d279  mov     eax, 57h ; 'W'
0x18001d27e  add     rsp, 38h
0x18001d282  retn
```
