# ReportStatus(ulong,ulong)

- ea: `0x140002f7c`
- end: `0x140003012`
- name: `?ReportStatus@@YAXKK@Z`
- size: `150`
- prototype: `void __fastcall(DWORD dwEventID, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ec0`
- `0x140003110`
- `0x1400032a0`

## callees

- `0x140002f7c`
- `0x140003384`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002ff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002ff8`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x140003001`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x140003001`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x140002f9e`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x140002f9e`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140002fed`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140002fed`

## pseudocode

```c
void __fastcall ReportStatus(DWORD dwEventID, int a2)
{
  HANDLE v3; // rbx
  int RawData; // [rsp+68h] [rbp+10h] BYREF
  LPCWSTR Strings; // [rsp+70h] [rbp+18h] BYREF

  RawData = a2;
  Strings = 0;
  v3 = RegisterEventSourceW(0, L"IISCTLS");
  if ( v3 )
  {
    if ( (int)WhoAmI((unsigned __int16 **)&Strings) >= 0 )
    {
      ReportEventW(v3, 4u, 0, dwEventID, 0, 1u, 4u, &Strings, &RawData);
      LocalFree((HLOCAL)Strings);
    }
    DeregisterEventSource(v3);
  }
}

```

## disassembly

```asm
0x140002f7c  mov     [rsp+arg_0], rbx
0x140002f81  mov     [rsp+RawData], edx
0x140002f85  push    rdi
0x140002f86  sub     rsp, 50h
0x140002f8a  mov     edi, ecx
0x140002f8c  mov     [rsp+58h+Strings], 0
0x140002f95  xor     ecx, ecx; lpUNCServerName
0x140002f97  lea     rdx, SourceName; "IISCTLS"
0x140002f9e  call    cs:__imp_RegisterEventSourceW
0x140002fa4  mov     rbx, rax
0x140002fa7  test    rax, rax
0x140002faa  jz      short loc_140003007
0x140002fac  lea     rcx, [rsp+58h+Strings]; unsigned __int16 **
0x140002fb1  call    ?WhoAmI@@YAJPEAPEAG@Z; WhoAmI(ushort * *)
0x140002fb6  test    eax, eax
0x140002fb8  js      short loc_140002FFE
0x140002fba  xor     r8d, r8d; wCategory
0x140002fbd  lea     rax, [rsp+58h+RawData]
0x140002fc2  mov     [rsp+58h+lpRawData], rax; lpRawData
0x140002fc7  mov     r9d, edi; dwEventID
0x140002fca  lea     rax, [rsp+58h+Strings]
0x140002fcf  mov     [rsp+58h+lpStrings], rax; lpStrings
0x140002fd4  lea     ecx, [r8+4]
0x140002fd8  mov     [rsp+58h+dwDataSize], ecx; dwDataSize
0x140002fdc  mov     edx, ecx; wType
0x140002fde  mov     [rsp+58h+wNumStrings], 1; wNumStrings
0x140002fe5  mov     rcx, rbx; hEventLog
0x140002fe8  mov     [rsp+58h+lpUserSid], r8; lpUserSid
0x140002fed  call    cs:__imp_ReportEventW
0x140002ff3  mov     rcx, [rsp+58h+Strings]; hMem
0x140002ff8  call    cs:__imp_LocalFree
0x140002ffe  mov     rcx, rbx; hEventLog
0x140003001  call    cs:__imp_DeregisterEventSource
0x140003007  mov     rbx, [rsp+58h+arg_0]
0x14000300c  add     rsp, 50h
0x140003010  pop     rdi
0x140003011  retn
```
