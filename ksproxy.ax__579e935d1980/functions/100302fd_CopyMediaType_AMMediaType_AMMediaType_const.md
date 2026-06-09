# CopyMediaType(_AMMediaType *,_AMMediaType const *)

- ea: `0x100302fd`
- end: `0x10030356`
- name: `?CopyMediaType@@YGJPAU_AMMediaType@@PBU1@@Z`
- size: `89`
- prototype: `int __cdecl(struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10011c10`
- `0x10015b10`
- `0x10016700`
- `0x10017af0`
- `0x1001bb90`
- `0x10030148`
- `0x100302c4`
- `0x10033920`

## callees

- `0x100302fd`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1003031f`
- `ole32!CoTaskMemAlloc` at `0x1003031f`

## pseudocode

```c
int __fastcall CopyMediaType(_DWORD *a1, int a2)
{
  void *v3; // eax

  qmemcpy(a1, (const void *)a2, 0x48u);
  if ( *(_DWORD *)(a2 + 64) )
  {
    v3 = CoTaskMemAlloc(*(_DWORD *)(a2 + 64));
    a1[17] = v3;
    if ( !v3 )
    {
      a1[16] = 0;
      return -2147024882;
    }
    memcpy(v3, *(const void **)(a2 + 68), a1[16]);
  }
  a1[15] = 0;
  return 0;
}

```

## disassembly

```asm
0x100302fd  mov     edi, edi
0x100302ff  push    ebp
0x10030300  mov     ebp, esp
0x10030302  push    ecx
0x10030303  push    ebx
0x10030304  push    esi
0x10030305  push    edi
0x10030306  mov     eax, edx
0x10030308  mov     ebx, ecx
0x1003030a  push    12h
0x1003030c  pop     ecx
0x1003030d  mov     esi, eax
0x1003030f  mov     [ebp+var_4], eax
0x10030312  mov     edi, ebx
0x10030314  rep movsd
0x10030316  cmp     dword ptr [eax+40h], 0
0x1003031a  jz      short loc_10030348
0x1003031c  push    dword ptr [eax+40h]; cb
0x1003031f  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10030325  mov     [ebx+44h], eax
0x10030328  test    eax, eax
0x1003032a  jnz     short loc_10030336
0x1003032c  mov     [ebx+40h], eax
0x1003032f  mov     eax, 8007000Eh
0x10030334  jmp     short loc_10030351
0x10030336  mov     ecx, [ebp+var_4]
0x10030339  push    dword ptr [ebx+40h]; Size
0x1003033c  push    dword ptr [ecx+44h]; Src
0x1003033f  push    eax; void *
0x10030340  call    _memcpy
0x10030345  add     esp, 0Ch
0x10030348  mov     dword ptr [ebx+3Ch], 0
0x1003034f  xor     eax, eax
0x10030351  pop     edi
0x10030352  pop     esi
0x10030353  pop     ebx
0x10030354  leave
0x10030355  retn
```
