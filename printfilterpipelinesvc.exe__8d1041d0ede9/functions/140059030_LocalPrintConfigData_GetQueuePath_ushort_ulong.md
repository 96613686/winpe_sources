# LocalPrintConfigData::GetQueuePath(ushort *,ulong)

- ea: `0x140059030`
- end: `0x140059080`
- name: `?GetQueuePath@LocalPrintConfigData@@UEAAJPEAGK@Z`
- size: `80`
- prototype: `int __fastcall(LocalPrintConfigData *this, BYTE *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140059030`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x140059069`
- `WINSPOOL!GetPrinterDataW` at `0x140059069`

## string_xrefs

- `0x14005905e`: `PrintQueueV4DriverDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall LocalPrintConfigData::GetQueuePath(LocalPrintConfigData *this, BYTE *a2, int a3)
{
  void *v3; // rcx
  int result; // eax
  DWORD pType; // [rsp+40h] [rbp+8h] BYREF
  DWORD pcbNeeded; // [rsp+50h] [rbp+18h] BYREF

  v3 = (void *)*((_QWORD *)this + 14);
  pcbNeeded = 0;
  pType = 0;
  result = GetPrinterDataW(v3, (LPWSTR)L"PrintQueueV4DriverDirectory", &pType, a2, 2 * a3, &pcbNeeded);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140059030  sub     rsp, 38h
0x140059034  mov     rcx, [rcx+70h]; hPrinter
0x140059038  lea     eax, [r8+r8]
0x14005903c  lea     r8, [rsp+38h+arg_10]
0x140059041  mov     [rsp+38h+arg_10], 0
0x140059049  mov     [rsp+38h+pcbNeeded], r8; pcbNeeded
0x14005904e  mov     r9, rdx; pData
0x140059051  lea     r8, [rsp+38h+pType]; pType
0x140059056  mov     [rsp+38h+pType], 0
0x14005905e  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x140059065  mov     [rsp+38h+nSize], eax; nSize
0x140059069  call    cs:__imp_GetPrinterDataW
0x14005906f  test    eax, eax
0x140059071  jle     short loc_14005907B
0x140059073  movzx   eax, ax
0x140059076  or      eax, 80070000h
0x14005907b  add     rsp, 38h
0x14005907f  retn
```
