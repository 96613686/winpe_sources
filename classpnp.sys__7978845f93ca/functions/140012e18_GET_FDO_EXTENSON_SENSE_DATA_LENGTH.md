# GET_FDO_EXTENSON_SENSE_DATA_LENGTH

- ea: `0x140012e18`
- end: `0x140012e36`
- name: `GET_FDO_EXTENSON_SENSE_DATA_LENGTH`
- size: `30`
- prototype: `UCHAR __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140010400`
- `0x140011ba0`
- `0x140012a00`
- `0x14001f450`
- `0x140026640`
- `0x140038294`

## callees

- `0x140012e18`

## pseudocode

```c
UCHAR __stdcall GET_FDO_EXTENSON_SENSE_DATA_LENGTH(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  UCHAR result; // al
  UCHAR SenseDataLength; // cl

  result = 0;
  if ( FdoExtension->SenseData )
  {
    SenseDataLength = FdoExtension->SenseDataLength;
    result = 18;
    if ( SenseDataLength )
      return SenseDataLength;
  }
  return result;
}

```

## disassembly

```asm
0x140012e18  xor     al, al
0x140012e1a  cmp     qword ptr [rcx+240h], 0
0x140012e22  jz      short locret_140012E35
0x140012e24  movzx   ecx, byte ptr [rcx+225h]
0x140012e2b  mov     eax, 12h
0x140012e30  test    cl, cl
0x140012e32  cmovnz  eax, ecx
0x140012e35  retn
```
