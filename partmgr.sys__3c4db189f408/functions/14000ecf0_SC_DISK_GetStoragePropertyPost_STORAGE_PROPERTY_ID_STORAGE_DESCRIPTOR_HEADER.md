# SC_DISK::GetStoragePropertyPost(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER *)

- ea: `0x14000ecf0`
- end: `0x14000ed8e`
- name: `?GetStoragePropertyPost@SC_DISK@@MEAAJW4_STORAGE_PROPERTY_ID@@PEAU_STORAGE_DESCRIPTOR_HEADER@@@Z`
- size: `158`
- prototype: `int(SC_DISK *__hidden this, enum _STORAGE_PROPERTY_ID, struct _STORAGE_DESCRIPTOR_HEADER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000ec70`
- `0x14000ecf0`
- `0x14000f130`

## pseudocode

```c
__int64 __fastcall SC_DISK::GetStoragePropertyPost(
        struct _UNICODE_STRING *this,
        int a2,
        struct _STORAGE_DESCRIPTOR_HEADER *a3)
{
  unsigned int v3; // ecx
  ULONG Buffer_high; // r9d
  ULONG Size; // eax
  int v6; // edx
  int v7; // edx
  int v8; // edx
  ULONG Version; // edx

  if ( a2 > 21 )
  {
    v6 = a2 - 49;
    if ( v6 )
    {
      v7 = v6 - 8;
      if ( !v7 )
        return 0;
      v8 = v7 - 1;
      if ( !v8 )
      {
        Version = a3[4].Version;
        v3 = 0;
        if ( Version < a3->Version || Version > a3->Size - 1 )
          a3[4].Version = 0;
        return v3;
      }
      if ( v8 != 7 )
        return 0;
      return (unsigned int)SC_DISK::GetFruIdDescPost(this, (struct _STORAGE_FRU_ID_DESCRIPTOR *)a3, (__int64)a3);
    }
    else
    {
      return (unsigned int)SC_DISK::ValidateNvmeDesc((SC_DISK *)this, (struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR *)a3);
    }
  }
  if ( a2 != 6 )
    return 0;
  Buffer_high = HIDWORD(this[14].Buffer);
  if ( a3[2].Version != Buffer_high )
    return (unsigned int)-1073739509;
  Size = a3[2].Size;
  if ( Size < Buffer_high )
    return (unsigned int)-1073739509;
  v3 = 0;
  if ( Size % Buffer_high )
    return (unsigned int)-1073739509;
  return v3;
}

```

## disassembly

```asm
0x14000ecf0  sub     rsp, 28h
0x14000ecf4  cmp     edx, 15h
0x14000ecf7  jg      short loc_14000ED3E
0x14000ecf9  jz      short loc_14000ED12
0x14000ecfb  sub     edx, 4
0x14000ecfe  jz      short loc_14000ED12
0x14000ed00  sub     edx, 2
0x14000ed03  jz      short loc_14000ED16
0x14000ed05  sub     edx, 1
0x14000ed08  jz      short loc_14000ED12
0x14000ed0a  sub     edx, 1
0x14000ed0d  jz      short loc_14000ED12
0x14000ed0f  sub     edx, 3
0x14000ed12  xor     ecx, ecx
0x14000ed14  jmp     short loc_14000ED86
0x14000ed16  mov     r9d, [rcx+0ECh]
0x14000ed1d  cmp     [r8+10h], r9d
0x14000ed21  jnz     short loc_14000ED37
0x14000ed23  mov     eax, [r8+14h]
0x14000ed27  cmp     eax, r9d
0x14000ed2a  jb      short loc_14000ED37
0x14000ed2c  xor     edx, edx
0x14000ed2e  xor     ecx, ecx
0x14000ed30  div     r9d
0x14000ed33  test    edx, edx
0x14000ed35  jz      short loc_14000ED86
0x14000ed37  mov     ecx, 0C000090Bh; this
0x14000ed3c  jmp     short loc_14000ED86
0x14000ed3e  sub     edx, 31h ; '1'
0x14000ed41  jz      short loc_14000ED7C
0x14000ed43  sub     edx, 8
0x14000ed46  jz      short loc_14000ED12
0x14000ed48  sub     edx, 1
0x14000ed4b  jz      short loc_14000ED61
0x14000ed4d  sub     edx, 2
0x14000ed50  jz      short loc_14000ED12
0x14000ed52  cmp     edx, 5
0x14000ed55  jnz     short loc_14000ED12
0x14000ed57  mov     rdx, r8; struct _STORAGE_FRU_ID_DESCRIPTOR *
0x14000ed5a  call    ?GetFruIdDescPost@SC_DISK@@AEAAJPEAU_STORAGE_FRU_ID_DESCRIPTOR@@@Z; SC_DISK::GetFruIdDescPost(_STORAGE_FRU_ID_DESCRIPTOR *)
0x14000ed5f  jmp     short loc_14000ED84
0x14000ed61  mov     edx, [r8+20h]
0x14000ed65  xor     ecx, ecx; this
0x14000ed67  cmp     edx, [r8]
0x14000ed6a  jb      short loc_14000ED76
0x14000ed6c  mov     eax, [r8+4]
0x14000ed70  dec     eax
0x14000ed72  cmp     edx, eax
0x14000ed74  jbe     short loc_14000ED86
0x14000ed76  mov     [r8+20h], ecx
0x14000ed7a  jmp     short loc_14000ED86
0x14000ed7c  mov     rdx, r8; struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR *
0x14000ed7f  call    ?ValidateNvmeDesc@SC_DISK@@AEAAJPEAU_STORAGE_PROTOCOL_DATA_DESCRIPTOR@@@Z; SC_DISK::ValidateNvmeDesc(_STORAGE_PROTOCOL_DATA_DESCRIPTOR *)
0x14000ed84  mov     ecx, eax
0x14000ed86  mov     eax, ecx
0x14000ed88  add     rsp, 28h
0x14000ed8c  retn
```
