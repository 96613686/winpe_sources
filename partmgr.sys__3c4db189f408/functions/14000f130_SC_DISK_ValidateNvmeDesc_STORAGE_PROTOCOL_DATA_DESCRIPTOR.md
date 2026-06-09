# SC_DISK::ValidateNvmeDesc(_STORAGE_PROTOCOL_DATA_DESCRIPTOR *)

- ea: `0x14000f130`
- end: `0x14000f179`
- name: `?ValidateNvmeDesc@SC_DISK@@AEAAJPEAU_STORAGE_PROTOCOL_DATA_DESCRIPTOR@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ecf0`

## callees

- `0x14000f130`

## pseudocode

```c
__int64 __fastcall SC_DISK::ValidateNvmeDesc(SC_DISK *this, struct _STORAGE_PROTOCOL_DATA_DESCRIPTOR *a2)
{
  unsigned int v2; // r8d
  ULONG Size; // r9d
  __int64 ProtocolDataOffset; // rcx
  ULONG ProtocolDataLength; // eax

  v2 = -1073741811;
  if ( a2->Version == 48 )
  {
    Size = a2->Size;
    if ( Size >= 0x30 )
    {
      ProtocolDataOffset = a2->ProtocolSpecificData.ProtocolDataOffset;
      if ( (unsigned int)ProtocolDataOffset >= 0x28 )
      {
        ProtocolDataLength = a2->ProtocolSpecificData.ProtocolDataLength;
        if ( ProtocolDataLength >= 0x1000
          && Size >= (unsigned int)ProtocolDataOffset + ProtocolDataLength
          && *(_WORD *)((char *)&a2->ProtocolSpecificData.ProtocolType + ProtocolDataOffset)
          && *(ULONG *)((char *)&a2[10].ProtocolSpecificData.Reserved[1] + ProtocolDataOffset) )
        {
          return 0;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000f130  cmp     dword ptr [rdx], 30h ; '0'
0x14000f133  mov     r8d, 0C000000Dh
0x14000f139  jnz     short loc_14000F175
0x14000f13b  mov     r9d, [rdx+4]
0x14000f13f  cmp     r9d, 30h ; '0'
0x14000f143  jb      short loc_14000F175
0x14000f145  mov     ecx, [rdx+18h]
0x14000f148  cmp     ecx, 28h ; '('
0x14000f14b  jb      short loc_14000F175
0x14000f14d  mov     eax, [rdx+1Ch]
0x14000f150  cmp     eax, 1000h
0x14000f155  jb      short loc_14000F175
0x14000f157  add     eax, ecx
0x14000f159  cmp     r9d, eax
0x14000f15c  jb      short loc_14000F175
0x14000f15e  xor     r9d, r9d
0x14000f161  cmp     [rcx+rdx+8], r9w
0x14000f167  jz      short loc_14000F175
0x14000f169  cmp     [rcx+rdx+20Ch], r9d
0x14000f171  cmovnz  r8d, r9d
0x14000f175  mov     eax, r8d
0x14000f178  retn
```
