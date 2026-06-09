# _RecoverUserShellFolderKeys(ushort const *,ushort const *,HKEY__ *)

- ea: `0x1800123ac`
- end: `0x18001250e`
- name: `?_RecoverUserShellFolderKeys@@YAJPEBG0PEAUHKEY__@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(const WCHAR *, const unsigned __int16 *, HKEY hKeySrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009488`

## callees

- `0x180003480`
- `0x180003fdc`
- `0x180005b60`
- `0x180009cb0`
- `0x18000a1f4`
- `0x18000df14`
- `0x18000df6c`
- `0x180012330`
- `0x1800123ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001241f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001241f`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180012476`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180012476`

## string_xrefs

- `0x18001244b`: `minio\profapi\path.cpp`
- `0x180012488`: `minio\profapi\path.cpp`
- `0x1800124b5`: `minio\profapi\path.cpp`
- `0x18001243c`: `Failed Path %ws`

## pseudocode

```c
__int64 __fastcall _RecoverUserShellFolderKeys(const WCHAR *a1, const unsigned __int16 *a2, HKEY hKeySrc)
{
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int (*v11)(HKEY, void *, void *, int, int); // r9
  __int64 v12; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  HKEY hKeyDest[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD dwDisposition; // [rsp+88h] [rbp+20h] BYREF

  hKeyDest[0] = 0;
  dwDisposition = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKeyDest,
    0);
  v6 = RegCreateKeyExW(HKEY_USERS, a1, 0, 0, 0, 0xF003Fu, 0, hKeyDest, &dwDisposition);
  if ( v6 == 5 )
    goto LABEL_14;
  if ( !v6 )
  {
    if ( dwDisposition != 2 )
    {
      v8 = RegCopyTreeW(hKeySrc, 0, hKeyDest[0]);
      if ( v8 )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x44,
               (unsigned int)"minio\\profapi\\path.cpp",
               (const char *)v8,
               dwOptions);
        goto LABEL_7;
      }
      v10 = SetDefaultUserHiveSecurity(a2, hKeyDest[0]);
      v9 = v10;
      if ( v10 < 0 )
      {
        v12 = 70;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"minio\\profapi\\path.cpp",
          (const char *)(unsigned int)v10,
          dwOptions);
        goto LABEL_15;
      }
      v10 = SetHiveLpacSecurity_(a2, hKeyDest[0], 1, v11);
      v9 = v10;
      if ( v10 < 0 )
      {
        v12 = 72;
        goto LABEL_10;
      }
      ProfAPITelemetry::UserShellFolderBackupKeyApplied();
    }
LABEL_14:
    v9 = 0;
    goto LABEL_15;
  }
  v7 = wil::details::in1diag3::Return_Win32Msg(
         retaddr,
         (void *)0x39,
         (unsigned int)"minio\\profapi\\path.cpp",
         (const char *)v6,
         (unsigned int)"Failed Path %ws",
         (const char *)a1);
LABEL_7:
  v9 = v7;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKeyDest);
  return v9;
}

```

## disassembly

```asm
0x1800123ac  mov     rax, rsp
0x1800123af  mov     [rax+8], rbx
0x1800123b3  mov     [rax+10h], rsi
0x1800123b7  push    rdi
0x1800123b8  sub     rsp, 60h
0x1800123bc  mov     rsi, r8
0x1800123bf  mov     rdi, rdx
0x1800123c2  mov     rbx, rcx
0x1800123c5  mov     qword ptr [rax-18h], 0
0x1800123cd  mov     dword ptr [rax+20h], 0
0x1800123d4  xor     edx, edx
0x1800123d6  lea     rcx, [rax-18h]
0x1800123da  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800123df  lea     rax, [rsp+68h+dwDisposition]
0x1800123e7  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1800123ec  lea     rax, [rsp+68h+hKeyDest]
0x1800123f1  mov     [rsp+68h+phkResult], rax; phkResult
0x1800123f6  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800123ff  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x180012407  mov     [rsp+68h+dwOptions], 0; int
0x18001240f  xor     r9d, r9d; lpClass
0x180012412  xor     r8d, r8d; Reserved
0x180012415  mov     rdx, rbx; lpSubKey
0x180012418  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001241f  call    cs:__imp_RegCreateKeyExW
0x180012425  cmp     eax, 5
0x180012428  jz      loc_1800124F0
0x18001242e  test    eax, eax
0x180012430  jz      short loc_18001245E
0x180012432  mov     rcx, [rsp+68h]; this
0x180012437  mov     qword ptr [rsp+68h+samDesired], rbx; char *
0x18001243c  lea     rdx, aFailedPathWs; "Failed Path %ws"
0x180012443  mov     qword ptr [rsp+68h+dwOptions], rdx; unsigned int
0x180012448  mov     r9d, eax; char *
0x18001244b  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180012452  mov     edx, 39h ; '9'; void *
0x180012457  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001245c  jmp     short loc_180012499
0x18001245e  cmp     [rsp+68h+dwDisposition], 2
0x180012466  jz      loc_1800124F0
0x18001246c  mov     r8, [rsp+68h+hKeyDest]; hKeyDest
0x180012471  xor     edx, edx; lpSubKey
0x180012473  mov     rcx, rsi; hKeySrc
0x180012476  call    cs:__imp_RegCopyTreeW
0x18001247c  test    eax, eax
0x18001247e  jz      short loc_18001249D
0x180012480  mov     rcx, [rsp+68h]; this
0x180012485  mov     r9d, eax; char *
0x180012488  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18001248f  mov     edx, 44h ; 'D'; void *
0x180012494  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012499  mov     ebx, eax
0x18001249b  jmp     short loc_1800124F2
0x18001249d  mov     rdx, [rsp+68h+hKeyDest]; HKEY
0x1800124a2  mov     rcx, rdi; unsigned __int16 *
0x1800124a5  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x1800124aa  mov     ebx, eax
0x1800124ac  test    eax, eax
0x1800124ae  jns     short loc_1800124CB
0x1800124b0  mov     edx, 46h ; 'F'; void *
0x1800124b5  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x1800124bc  mov     r9d, eax; char *
0x1800124bf  mov     rcx, [rsp+68h]; this
0x1800124c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800124c9  jmp     short loc_1800124F2
0x1800124cb  mov     r8d, 1; int
0x1800124d1  mov     rdx, [rsp+68h+hKeyDest]; HKEY
0x1800124d6  mov     rcx, rdi; unsigned __int16 *
0x1800124d9  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x1800124de  mov     ebx, eax
0x1800124e0  test    eax, eax
0x1800124e2  jns     short loc_1800124EB
0x1800124e4  mov     edx, 48h ; 'H'
0x1800124e9  jmp     short loc_1800124B5
0x1800124eb  call    ?UserShellFolderBackupKeyApplied@ProfAPITelemetry@@SAXXZ; ProfAPITelemetry::UserShellFolderBackupKeyApplied(void)
0x1800124f0  xor     ebx, ebx
0x1800124f2  lea     rcx, [rsp+68h+hKeyDest]
0x1800124f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800124fc  mov     eax, ebx
0x1800124fe  mov     rbx, [rsp+68h+arg_0]
0x180012503  mov     rsi, [rsp+68h+arg_8]
0x180012508  add     rsp, 60h
0x18001250c  pop     rdi
0x18001250d  retn
```
