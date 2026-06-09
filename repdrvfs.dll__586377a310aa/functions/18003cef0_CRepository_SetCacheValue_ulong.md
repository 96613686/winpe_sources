# CRepository::SetCacheValue(ulong)

- ea: `0x18003cef0`
- end: `0x18003d049`
- name: `?SetCacheValue@CRepository@@UEAAJK@Z`
- size: `345`
- prototype: `__int64 __fastcall(CRepository *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180018c3c`
- `0x180024ca0`
- `0x180038e6c`
- `0x18003cef0`
- `0x180044170`
- `0x180044208`

## import_xrefs

- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003cf0c`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18003cf0c`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x18003cf16`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x18003cf16`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18003cf1f`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18003cf1f`
- `wbemcomn!GetMemLogObject` at `0x18003cf5e`
- `wbemcomn!GetMemLogObject` at `0x18003cf5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cf69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003cf69`

## string_xrefs

- `0x18003cfd9`: `Max Class Cache Item Age (ms)`
- `0x18003d000`: `Max Class Cache Item Age (ms)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepository::SetCacheValue(CRepository *this, int a2)
{
  int v3; // r8d
  int RegistryPathCIMOM; // ebx
  int RegistryPathRoot; // eax
  int v6; // r8d
  unsigned int v7; // eax
  int v8; // r8d
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  if ( (unsigned __int8)CWbemInstallObject::IsOffline(this) )
  {
    RegistryPathCIMOM = CWbemInstallObject::GetRegistryPathCIMOM();
    RegistryPathRoot = CWbemInstallObject::GetRegistryPathRoot();
    v7 = DLRegOpenKeyExW(RegistryPathRoot, RegistryPathCIMOM, v6, 131103, (__int64)&v13);
  }
  else
  {
    v7 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", v3, 131103, (__int64)&v13);
  }
  v9 = v7;
  if ( v7 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, v9);
    }
    return v9;
  }
  else
  {
    v14 = v13;
    v16 = 4;
    v15 = 0;
    if ( (unsigned int)DLRegQueryValueExW(
                         v13,
                         (unsigned int)L"Max Class Cache Item Age (ms)",
                         v8,
                         0,
                         (__int64)&v15,
                         (__int64)&v16) )
    {
      v15 = 10000;
      DLRegSetValueExW(v13, (unsigned int)L"Max Class Cache Item Age (ms)", v12, 4, (__int64)&v15, 4);
    }
    dword_180058AC0 = a2;
    LODWORD(qword_180058AC4) = v15;
    CForestCache::MakeRoom((CForestCache *)qword_180058A80, 0);
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18003cef0  mov     [rsp-8+arg_0], rbx
0x18003cef5  mov     [rsp-8+arg_8], rdi
0x18003cefa  push    rbp
0x18003cefb  mov     rbp, rsp
0x18003cefe  sub     rsp, 40h
0x18003cf02  mov     edi, edx
0x18003cf04  mov     [rbp+var_10], 0
0x18003cf0c  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18003cf12  test    al, al
0x18003cf14  jz      short loc_18003CF36
0x18003cf16  call    cs:__imp_?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ; CWbemInstallObject::GetRegistryPathCIMOM(void)
0x18003cf1c  mov     rbx, rax
0x18003cf1f  call    cs:__imp_?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ; CWbemInstallObject::GetRegistryPathRoot(void)
0x18003cf25  lea     rcx, [rbp+var_10]
0x18003cf29  mov     [rsp+40h+var_20], rcx
0x18003cf2e  mov     rdx, rbx
0x18003cf31  mov     rcx, rax
0x18003cf34  jmp     short loc_18003CF4D
0x18003cf36  lea     rax, [rbp+var_10]
0x18003cf3a  mov     [rsp+40h+var_20], rax
0x18003cf3f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x18003cf46  mov     rcx, 0FFFFFFFF80000002h
0x18003cf4d  mov     r9d, 2001Fh
0x18003cf53  call    DLRegOpenKeyExW
0x18003cf58  mov     ebx, eax
0x18003cf5a  test    eax, eax
0x18003cf5c  jz      short loc_18003CFAD
0x18003cf5e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003cf64  mov     edx, ebx
0x18003cf66  mov     rcx, rax
0x18003cf69  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cf6f  lea     rax, WPP_GLOBAL_Control
0x18003cf76  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf7d  cmp     rcx, rax
0x18003cf80  jz      short loc_18003CFA6
0x18003cf82  test    byte ptr [rcx+1Ch], 1
0x18003cf86  jz      short loc_18003CFA6
0x18003cf88  cmp     byte ptr [rcx+19h], 2
0x18003cf8c  jb      short loc_18003CFA6
0x18003cf8e  mov     edx, 45h ; 'E'
0x18003cf93  mov     r9d, ebx
0x18003cf96  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003cf9d  mov     rcx, [rcx+10h]
0x18003cfa1  call    WPP_SF_d
0x18003cfa6  mov     eax, ebx
0x18003cfa8  jmp     loc_18003D039
0x18003cfad  mov     rcx, [rbp+var_10]
0x18003cfb1  mov     [rbp+var_8], rcx
0x18003cfb5  mov     ebx, 4
0x18003cfba  mov     [rbp+arg_18], ebx
0x18003cfbd  mov     [rbp+arg_10], 0
0x18003cfc4  lea     rax, [rbp+arg_18]
0x18003cfc8  mov     [rsp+40h+var_18], rax
0x18003cfcd  lea     rax, [rbp+arg_10]
0x18003cfd1  mov     [rsp+40h+var_20], rax
0x18003cfd6  xor     r9d, r9d
0x18003cfd9  lea     rdx, aMaxClassCacheI; "Max Class Cache Item Age (ms)"
0x18003cfe0  call    DLRegQueryValueExW
0x18003cfe5  test    eax, eax
0x18003cfe7  jz      short loc_18003D010
0x18003cfe9  mov     [rbp+arg_10], 2710h
0x18003cff0  mov     dword ptr [rsp+40h+var_18], ebx
0x18003cff4  lea     rax, [rbp+arg_10]
0x18003cff8  mov     [rsp+40h+var_20], rax
0x18003cffd  mov     r9d, ebx
0x18003d000  lea     rdx, aMaxClassCacheI; "Max Class Cache Item Age (ms)"
0x18003d007  mov     rcx, [rbp+var_10]
0x18003d00b  call    DLRegSetValueExW
0x18003d010  mov     cs:dword_180058AC0, edi
0x18003d016  mov     eax, [rbp+arg_10]
0x18003d019  mov     dword ptr cs:qword_180058AC4, eax
0x18003d01f  xor     edx, edx; unsigned int
0x18003d021  lea     rcx, qword_180058A80; this
0x18003d028  call    ?MakeRoom@CForestCache@@QEAA_NK@Z; CForestCache::MakeRoom(ulong)
0x18003d02d  nop
0x18003d02e  lea     rcx, [rbp+var_8]; this
0x18003d032  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x18003d037  xor     eax, eax
0x18003d039  mov     rbx, [rsp+40h+arg_0]
0x18003d03e  mov     rdi, [rsp+40h+arg_8]
0x18003d043  add     rsp, 40h
0x18003d047  pop     rbp
0x18003d048  retn
```
