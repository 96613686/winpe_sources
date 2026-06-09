# IsTeredoQualified(ulong)

- ea: `0x14004aa20`
- end: `0x14004abfe`
- name: `?IsTeredoQualified@@YAHK@Z`
- size: `478`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003af44`

## callees

- `0x140034ce4`
- `0x14004a994`
- `0x14004aa20`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14004aaac`
- `KERNEL32!CreateEventW` at `0x14004aaac`
- `KERNEL32!HeapFree` at `0x14004abdf`
- `KERNEL32!HeapFree` at `0x14004abdf`
- `KERNEL32!GetProcessHeap` at `0x14004aa42`
- `KERNEL32!GetProcessHeap` at `0x14004abcb`
- `KERNEL32!GetProcessHeap` at `0x14004aa42`
- `KERNEL32!GetProcessHeap` at `0x14004abcb`
- `KERNEL32!HeapAlloc` at `0x14004aa58`
- `KERNEL32!HeapAlloc` at `0x14004aa58`
- `KERNEL32!CloseHandle` at `0x14004abb3`
- `KERNEL32!CloseHandle` at `0x14004abb3`
- `KERNEL32!WaitForSingleObject` at `0x14004ab1c`
- `KERNEL32!WaitForSingleObject` at `0x14004ab1c`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x14004ab77`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x14004ab77`
- `IPHLPAPI!FreeMibTable` at `0x14004ab96`
- `IPHLPAPI!FreeMibTable` at `0x14004ab96`
- `IPHLPAPI!NotifyStableUnicastIpAddressTable` at `0x14004aaea`
- `IPHLPAPI!NotifyStableUnicastIpAddressTable` at `0x14004aaea`

## string_xrefs

- `0x14004aa85`: `base\diagnosis\ra\racommon\src\teredoutils.cpp`
- `0x14004ab45`: `base\diagnosis\ra\racommon\src\teredoutils.cpp`

## pseudocode

```c
__int64 __fastcall IsTeredoQualified()
{
  unsigned int v0; // esi
  HANDLE ProcessHeap; // rax
  CEventLogger *v2; // rcx
  _DWORD *v3; // rdi
  HANDLE *v4; // rbx
  HANDLE EventW; // rax
  CEventLogger *v6; // rcx
  NTSTATUS v7; // eax
  CEventLogger *v8; // rcx
  CEventLogger *v9; // rcx
  HANDLE v10; // rax
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+48h] [rbp+10h] BYREF
  HANDLE NotificationHandle; // [rsp+50h] [rbp+18h] BYREF

  NotificationHandle = 0;
  v0 = 0;
  Table = 0;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  v4 = (HANDLE *)(v3 + 2);
  if ( v3 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *v4 = EventW;
    if ( !EventW )
    {
      CEventLogger::LogError(
        v6,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
        0x97u,
        L"IsTeredoQualified",
        0);
      goto LABEL_14;
    }
    v7 = NotifyStableUnicastIpAddressTable(0x17u, &Table, TeredoQualVerifCallback, v3, &NotificationHandle);
    if ( v7 )
    {
      if ( v7 != 997 )
      {
        CEventLogger::LogError(
          v8,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
          0xC4u,
          L"IsTeredoQualified",
          0x80004005);
        goto LABEL_14;
      }
      if ( WaitForSingleObject(*v4, 0x2710u) == 258 )
        CEventLogger::LogError(
          v9,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\teredoutils.cpp",
          0xBCu,
          L"IsTeredoQualified",
          0);
    }
    else if ( (unsigned int)IsTeredoAddrPresent(Table) == 1 )
    {
      *v3 = 1;
    }
    v0 = *v3;
  }
  else
  {
    CEventLogger::LogError(
      v2,
      &Recoverable_Error,
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
  if ( *v4 )
  {
    CloseHandle(*v4);
    *v4 = 0;
  }
  if ( v3 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v3);
  }
  return v0;
}

```

## disassembly

```asm
0x14004aa20  mov     rax, rsp
0x14004aa23  mov     [rax+8], rbx
0x14004aa27  mov     [rax+20h], rsi
0x14004aa2b  push    rdi
0x14004aa2c  sub     rsp, 30h
0x14004aa30  mov     qword ptr [rax+18h], 0
0x14004aa38  xor     esi, esi
0x14004aa3a  mov     qword ptr [rax+10h], 0
0x14004aa42  call    cs:__imp_GetProcessHeap
0x14004aa49  nop     dword ptr [rax+rax+00h]
0x14004aa4e  mov     rcx, rax; hHeap
0x14004aa51  lea     edx, [rsi+8]; dwFlags
0x14004aa54  lea     r8d, [rsi+10h]; dwBytes
0x14004aa58  call    cs:__imp_HeapAlloc
0x14004aa5f  nop     dword ptr [rax+rax+00h]
0x14004aa64  mov     rdi, rax
0x14004aa67  lea     rbx, [rax+8]
0x14004aa6b  test    rax, rax
0x14004aa6e  jnz     short loc_14004AAA2
0x14004aa70  mov     [rsp+38h+var_10], 8007000Eh; unsigned int
0x14004aa78  mov     r9d, 90h; unsigned int
0x14004aa7e  lea     rax, aIsteredoqualif; "IsTeredoQualified"
0x14004aa85  lea     r8, aBaseDiagnosisR_10; "base\\diagnosis\\ra\\racommon\\src\\ter"...
0x14004aa8c  mov     [rsp+38h+NotificationHandle], rax; unsigned __int16 *
0x14004aa91  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14004aa98  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14004aa9d  jmp     loc_14004AB6D
0x14004aaa2  xor     r9d, r9d; lpName
0x14004aaa5  xor     r8d, r8d; bInitialState
0x14004aaa8  xor     edx, edx; bManualReset
0x14004aaaa  xor     ecx, ecx; lpEventAttributes
0x14004aaac  call    cs:__imp_CreateEventW
0x14004aab3  nop     dword ptr [rax+rax+00h]
0x14004aab8  mov     [rbx], rax
0x14004aabb  test    rax, rax
0x14004aabe  jnz     short loc_14004AACC
0x14004aac0  mov     [rsp+38h+var_10], esi
0x14004aac4  mov     r9d, 97h
0x14004aaca  jmp     short loc_14004AA7E
0x14004aacc  lea     rax, [rsp+38h+arg_10]
0x14004aad1  mov     ecx, 17h; Family
0x14004aad6  mov     r9, rdi; CallerContext
0x14004aad9  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x14004aade  lea     r8, ?TeredoQualVerifCallback@@YAXPEAXPEAU_MIB_UNICASTIPADDRESS_TABLE@@@Z; CallerCallback
0x14004aae5  lea     rdx, [rsp+38h+Table]; Table
0x14004aaea  call    cs:__imp_NotifyStableUnicastIpAddressTable
0x14004aaf1  nop     dword ptr [rax+rax+00h]
0x14004aaf6  test    eax, eax
0x14004aaf8  jz      short loc_14004AB5A
0x14004aafa  cmp     eax, 3E5h
0x14004aaff  jz      short loc_14004AB14
0x14004ab01  mov     [rsp+38h+var_10], 80004005h
0x14004ab09  mov     r9d, 0C4h
0x14004ab0f  jmp     loc_14004AA7E
0x14004ab14  mov     rcx, [rbx]; hHandle
0x14004ab17  mov     edx, 2710h; dwMilliseconds
0x14004ab1c  call    cs:__imp_WaitForSingleObject
0x14004ab23  nop     dword ptr [rax+rax+00h]
0x14004ab28  cmp     eax, 102h
0x14004ab2d  jnz     short loc_14004AB6B
0x14004ab2f  lea     rax, aIsteredoqualif; "IsTeredoQualified"
0x14004ab36  mov     [rsp+38h+var_10], esi; unsigned int
0x14004ab3a  mov     r9d, 0BCh; unsigned int
0x14004ab40  mov     [rsp+38h+NotificationHandle], rax; unsigned __int16 *
0x14004ab45  lea     r8, aBaseDiagnosisR_10; "base\\diagnosis\\ra\\racommon\\src\\ter"...
0x14004ab4c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14004ab53  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14004ab58  jmp     short loc_14004AB6B
0x14004ab5a  mov     rcx, [rsp+38h+Table]; struct _MIB_UNICASTIPADDRESS_TABLE *
0x14004ab5f  call    ?IsTeredoAddrPresent@@YAHPEAU_MIB_UNICASTIPADDRESS_TABLE@@@Z; IsTeredoAddrPresent(_MIB_UNICASTIPADDRESS_TABLE *)
0x14004ab64  cmp     eax, 1
0x14004ab67  jnz     short loc_14004AB6B
0x14004ab69  mov     [rdi], eax
0x14004ab6b  mov     esi, [rdi]
0x14004ab6d  mov     rcx, [rsp+38h+arg_10]; NotificationHandle
0x14004ab72  test    rcx, rcx
0x14004ab75  jz      short loc_14004AB8C
0x14004ab77  call    cs:__imp_CancelMibChangeNotify2
0x14004ab7e  nop     dword ptr [rax+rax+00h]
0x14004ab83  mov     [rsp+38h+arg_10], 0
0x14004ab8c  mov     rcx, [rsp+38h+Table]; Memory
0x14004ab91  test    rcx, rcx
0x14004ab94  jz      short loc_14004ABAB
0x14004ab96  call    cs:__imp_FreeMibTable
0x14004ab9d  nop     dword ptr [rax+rax+00h]
0x14004aba2  mov     [rsp+38h+Table], 0
0x14004abab  mov     rcx, [rbx]; hObject
0x14004abae  test    rcx, rcx
0x14004abb1  jz      short loc_14004ABC6
0x14004abb3  call    cs:__imp_CloseHandle
0x14004abba  nop     dword ptr [rax+rax+00h]
0x14004abbf  mov     qword ptr [rbx], 0
0x14004abc6  test    rdi, rdi
0x14004abc9  jz      short loc_14004ABEB
0x14004abcb  call    cs:__imp_GetProcessHeap
0x14004abd2  nop     dword ptr [rax+rax+00h]
0x14004abd7  mov     r8, rdi; lpMem
0x14004abda  xor     edx, edx; dwFlags
0x14004abdc  mov     rcx, rax; hHeap
0x14004abdf  call    cs:__imp_HeapFree
0x14004abe6  nop     dword ptr [rax+rax+00h]
0x14004abeb  mov     rbx, [rsp+38h+arg_0]
0x14004abf0  mov     eax, esi
0x14004abf2  mov     rsi, [rsp+38h+arg_18]
0x14004abf7  add     rsp, 30h
0x14004abfb  pop     rdi
0x14004abfc  retn
```
