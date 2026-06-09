# CASFReader::GetState(ulong,_FilterState *)

- ea: `0x18000a460`
- end: `0x18000a4d0`
- name: `?GetState@CASFReader@@UEAAJKPEAW4_FilterState@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned int, enum _FilterState *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a460`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetState(CASFReader *this, __int64 a2, enum _FilterState *a3)
{
  __int64 v4; // rcx
  __int64 v6; // rdx
  int v7; // ecx

  v4 = *((_QWORD *)this + 55);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, __int64, enum _FilterState *, CASFReader *))(*(_QWORD *)v4 + 56LL))(
             v4,
             a2,
             a3,
             this);
  if ( !a3 )
    return 2147500035LL;
  v6 = *((_QWORD *)this + 32);
  v7 = 0;
  if ( v6 )
  {
    while ( !*(_DWORD *)(*(_QWORD *)(v6 + 16) + 324LL) )
    {
      v6 = *(_QWORD *)(v6 + 8);
      if ( !v6 )
        goto LABEL_10;
    }
    v7 = 1;
  }
LABEL_10:
  *a3 = *((enum _FilterState *)this + 4);
  if ( *((_DWORD *)this + 4) == 1 )
    return v7 != 0 ? 0x40268 : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x18000a460  mov     r9, rcx
0x18000a463  mov     rcx, [rcx+1B8h]
0x18000a46a  test    rcx, rcx
0x18000a46d  jz      short loc_18000A47B
0x18000a46f  mov     rax, [rcx]
0x18000a472  mov     rax, [rax+38h]
0x18000a476  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a47b  test    r8, r8
0x18000a47e  jnz     short loc_18000A487
0x18000a480  mov     eax, 80004003h
0x18000a485  jmp     short locret_18000A4CF
0x18000a487  mov     rdx, [r9+100h]
0x18000a48e  xor     ecx, ecx
0x18000a490  test    rdx, rdx
0x18000a493  jz      short loc_18000A4B4
0x18000a495  mov     rax, [rdx+10h]
0x18000a499  cmp     [rax+144h], ecx
0x18000a49f  jnz     short loc_18000A4AF
0x18000a4a1  mov     rax, [rdx+8]
0x18000a4a5  mov     rdx, rax
0x18000a4a8  test    rax, rax
0x18000a4ab  jnz     short loc_18000A495
0x18000a4ad  jmp     short loc_18000A4B4
0x18000a4af  mov     ecx, 1
0x18000a4b4  mov     eax, [r9+10h]
0x18000a4b8  mov     [r8], eax
0x18000a4bb  cmp     dword ptr [r9+10h], 1
0x18000a4c0  jnz     short loc_18000A4CD
0x18000a4c2  neg     ecx
0x18000a4c4  sbb     eax, eax
0x18000a4c6  and     eax, 40268h
0x18000a4cb  jmp     short locret_18000A4CF
0x18000a4cd  xor     eax, eax
0x18000a4cf  retn
```
