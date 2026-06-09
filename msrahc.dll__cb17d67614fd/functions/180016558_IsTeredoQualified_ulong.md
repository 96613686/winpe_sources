# IsTeredoQualified(ulong)

- ea: `0x180016558`
- end: `0x1800166e8`
- name: `?IsTeredoQualified@@YAHK@Z`
- size: `400`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010adc`

## callees

- `0x180014660`
- `0x180016510`
- `0x180016558`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800165d1`
- `KERNEL32!CreateEventW` at `0x1800165d1`
- `KERNEL32!GetProcessHeap` at `0x18001657a`
- `KERNEL32!GetProcessHeap` at `0x1800166c2`
- `KERNEL32!GetProcessHeap` at `0x18001657a`
- `KERNEL32!GetProcessHeap` at `0x1800166c2`
- `KERNEL32!HeapAlloc` at `0x18001658a`
- `KERNEL32!HeapAlloc` at `0x18001658a`
- `KERNEL32!CloseHandle` at `0x1800166b0`
- `KERNEL32!CloseHandle` at `0x1800166b0`
- `KERNEL32!HeapFree` at `0x1800166d0`
- `KERNEL32!HeapFree` at `0x1800166d0`
- `KERNEL32!WaitForSingleObject` at `0x180016632`
- `KERNEL32!WaitForSingleObject` at `0x180016632`
- `IPHLPAPI!NotifyStableUnicastIpAddressTable` at `0x180016609`
- `IPHLPAPI!NotifyStableUnicastIpAddressTable` at `0x180016609`
- `IPHLPAPI!FreeMibTable` at `0x180016699`
- `IPHLPAPI!FreeMibTable` at `0x180016699`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016680`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180016680`

## string_xrefs

- `0x1800165b1`: `base\diagnosis\ra\racommon\src\teredoutils.cpp`
- `0x180016655`: `base\diagnosis\ra\racommon\src\teredoutils.cpp`

## pseudocode

```c
__int64 __fastcall IsTeredoQualified()
{
  unsigned int v0; // esi
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  _DWORD *v4; // rdi
  HANDLE *v5; // rbx
  HANDLE EventW; // rax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  NTSTATUS v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  HANDLE v14; // rax
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+48h] [rbp+10h] BYREF
  HANDLE NotificationHandle; // [rsp+50h] [rbp+18h] BYREF

  NotificationHandle = 0;
  v0 = 0;
  Table = 0;
  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  v5 = (HANDLE *)(v4 + 2);
  if ( v4 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *v5 = EventW;
    if ( !EventW )
    {
      CEventLogger::LogError(
        v8,
        v7,
        L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
        0x97u,
        L"IsTeredoQualified",
        0);
      goto LABEL_14;
    }
    v9 = NotifyStableUnicastIpAddressTable(0x17u, &Table, TeredoQualVerifCallback, v4, &NotificationHandle);
    if ( v9 )
    {
      if ( v9 != 997 )
      {
        CEventLogger::LogError(
          v11,
          v10,
          L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
          0xC4u,
          L"IsTeredoQualified",
          0x80004005);
        goto LABEL_14;
      }
      if ( WaitForSingleObject(*v5, 0x32u) == 258 )
        CEventLogger::LogError(
          v13,
          v12,
          L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
          0xBCu,
          L"IsTeredoQualified",
          0);
    }
    else if ( (unsigned int)IsTeredoAddrPresent(Table) == 1 )
    {
      *v4 = 1;
    }
    v0 = *v4;
  }
  else
  {
    CEventLogger::LogError(
      v3,
      v2,
      L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
      0x90u,
      L"IsTeredoQualified",
      0x8007000E);
  }
LABEL_14:
  if ( NotificationHandle )
  {
    CancelMibChangeNotify2(NotificationHandle);
    NotificationHandle = 0;
  }
  if ( Table )
  {
    FreeMibTable(Table);
    Table = 0;
  }
  if ( *v5 )
  {
    CloseHandle(*v5);
    *v5 = 0;
  }
  if ( v4 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v4);
  }
  return v0;
}

```

## disassembly

```asm
0x180016558  mov     rax, rsp
0x18001655b  mov     [rax+8], rbx
0x18001655f  mov     [rax+20h], rsi
0x180016563  push    rdi
0x180016564  sub     rsp, 30h
0x180016568  mov     qword ptr [rax+18h], 0
0x180016570  xor     esi, esi
0x180016572  mov     qword ptr [rax+10h], 0
0x18001657a  call    cs:__imp_GetProcessHeap
0x180016580  mov     rcx, rax; hHeap
0x180016583  lea     edx, [rsi+8]; dwFlags
0x180016586  lea     r8d, [rsi+10h]; dwBytes
0x18001658a  call    cs:__imp_HeapAlloc
0x180016590  mov     rdi, rax
0x180016593  lea     rbx, [rax+8]
0x180016597  test    rax, rax
0x18001659a  jnz     short loc_1800165C7
0x18001659c  mov     [rsp+38h+var_10], 8007000Eh; unsigned int
0x1800165a4  mov     r9d, 90h; unsigned int
0x1800165aa  lea     rax, aIsteredoqualif; "IsTeredoQualified"
0x1800165b1  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\racommon\\src\\ter"...
0x1800165b8  mov     [rsp+38h+NotificationHandle], rax; unsigned __int16 *
0x1800165bd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800165c2  jmp     loc_180016676
0x1800165c7  xor     r9d, r9d; lpName
0x1800165ca  xor     r8d, r8d; bInitialState
0x1800165cd  xor     edx, edx; bManualReset
0x1800165cf  xor     ecx, ecx; lpEventAttributes
0x1800165d1  call    cs:__imp_CreateEventW
0x1800165d7  mov     [rbx], rax
0x1800165da  test    rax, rax
0x1800165dd  jnz     short loc_1800165EB
0x1800165df  mov     [rsp+38h+var_10], esi
0x1800165e3  mov     r9d, 97h
0x1800165e9  jmp     short loc_1800165AA
0x1800165eb  lea     rax, [rsp+38h+arg_10]
0x1800165f0  mov     ecx, 17h; Family
0x1800165f5  mov     r9, rdi; CallerContext
0x1800165f8  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x1800165fd  lea     r8, ?TeredoQualVerifCallback@@YAXPEAXPEAU_MIB_UNICASTIPADDRESS_TABLE@@@Z; CallerCallback
0x180016604  lea     rdx, [rsp+38h+Table]; Table
0x180016609  call    cs:__imp_NotifyStableUnicastIpAddressTable
0x18001660f  test    eax, eax
0x180016611  jz      short loc_180016663
0x180016613  cmp     eax, 3E5h
0x180016618  jz      short loc_18001662A
0x18001661a  mov     [rsp+38h+var_10], 80004005h
0x180016622  mov     r9d, 0C4h
0x180016628  jmp     short loc_1800165AA
0x18001662a  mov     rcx, [rbx]; hHandle
0x18001662d  mov     edx, 32h ; '2'; dwMilliseconds
0x180016632  call    cs:__imp_WaitForSingleObject
0x180016638  cmp     eax, 102h
0x18001663d  jnz     short loc_180016674
0x18001663f  lea     rax, aIsteredoqualif; "IsTeredoQualified"
0x180016646  mov     [rsp+38h+var_10], esi; unsigned int
0x18001664a  mov     r9d, 0BCh; unsigned int
0x180016650  mov     [rsp+38h+NotificationHandle], rax; unsigned __int16 *
0x180016655  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\racommon\\src\\ter"...
0x18001665c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016661  jmp     short loc_180016674
0x180016663  mov     rcx, [rsp+38h+Table]; struct _MIB_UNICASTIPADDRESS_TABLE *
0x180016668  call    ?IsTeredoAddrPresent@@YAHPEAU_MIB_UNICASTIPADDRESS_TABLE@@@Z; IsTeredoAddrPresent(_MIB_UNICASTIPADDRESS_TABLE *)
0x18001666d  cmp     eax, 1
0x180016670  jnz     short loc_180016674
0x180016672  mov     [rdi], eax
0x180016674  mov     esi, [rdi]
0x180016676  mov     rcx, [rsp+38h+arg_10]; NotificationHandle
0x18001667b  test    rcx, rcx
0x18001667e  jz      short loc_18001668F
0x180016680  call    cs:__imp_CancelMibChangeNotify2
0x180016686  mov     [rsp+38h+arg_10], 0
0x18001668f  mov     rcx, [rsp+38h+Table]; Memory
0x180016694  test    rcx, rcx
0x180016697  jz      short loc_1800166A8
0x180016699  call    cs:__imp_FreeMibTable
0x18001669f  mov     [rsp+38h+Table], 0
0x1800166a8  mov     rcx, [rbx]; hObject
0x1800166ab  test    rcx, rcx
0x1800166ae  jz      short loc_1800166BD
0x1800166b0  call    cs:__imp_CloseHandle
0x1800166b6  mov     qword ptr [rbx], 0
0x1800166bd  test    rdi, rdi
0x1800166c0  jz      short loc_1800166D6
0x1800166c2  call    cs:__imp_GetProcessHeap
0x1800166c8  mov     r8, rdi; lpMem
0x1800166cb  xor     edx, edx; dwFlags
0x1800166cd  mov     rcx, rax; hHeap
0x1800166d0  call    cs:__imp_HeapFree
0x1800166d6  mov     rbx, [rsp+38h+arg_0]
0x1800166db  mov     eax, esi
0x1800166dd  mov     rsi, [rsp+38h+arg_18]
0x1800166e2  add     rsp, 30h
0x1800166e6  pop     rdi
0x1800166e7  retn
```
