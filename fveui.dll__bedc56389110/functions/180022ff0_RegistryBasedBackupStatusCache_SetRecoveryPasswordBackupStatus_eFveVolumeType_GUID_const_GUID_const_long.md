# RegistryBasedBackupStatusCache::SetRecoveryPasswordBackupStatus(eFveVolumeType,_GUID const *,_GUID const *,long)

- ea: `0x180022ff0`
- end: `0x180023298`
- name: `?SetRecoveryPasswordBackupStatus@RegistryBasedBackupStatusCache@@UEBAJW4eFveVolumeType@@PEBU_GUID@@1J@Z`
- size: `680`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x180016ac8`
- `0x180022ff0`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002304d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002304d`
- `ADVAPI32!RegSetValueExW` at `0x1800231be`
- `ADVAPI32!RegSetValueExW` at `0x180023228`
- `ADVAPI32!RegSetValueExW` at `0x1800231be`
- `ADVAPI32!RegSetValueExW` at `0x180023228`
- `ADVAPI32!RegCreateKeyExW` at `0x18002314c`
- `ADVAPI32!RegCreateKeyExW` at `0x18002314c`
- `ADVAPI32!RegCloseKey` at `0x180023271`
- `ADVAPI32!RegCloseKey` at `0x180023271`

## pseudocode

```c
__int64 RegistryBasedBackupStatusCache::SetRecoveryPasswordBackupStatus(
        __int64 a1,
        int a2,
        const GUID *a3,
        const GUID *a4,
        ...)
{
  signed int v8; // ebx
  unsigned int RegistrySubKeyForProtector; // eax
  HKEY v10; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  va_list Data; // [rsp+2E0h] [rbp+1E0h] BYREF

  va_start(Data, a4);
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  if ( !v8 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      (unsigned int)v8);
  if ( v8 >= 0 )
  {
LABEL_6:
    RegistrySubKeyForProtector = RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(a1, a2, a3, a4, SubKey);
    v8 = RegistrySubKeyForProtector;
    if ( !RegistrySubKeyForProtector )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        RegistrySubKeyForProtector);
    if ( v8 >= 0 )
    {
LABEL_11:
      v10 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v11 = RegCreateKeyExW(v10, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      if ( !v8 )
        goto LABEL_18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)v8);
      if ( v8 >= 0 )
      {
LABEL_18:
        v12 = RegSetValueExW(hKey, L"LastBackupStatus", 0, 4u, (const BYTE *)Data, 4u);
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( !v8 )
          goto LABEL_25;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            121,
            &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
            (unsigned int)v8);
        if ( v8 >= 0 )
        {
LABEL_25:
          v13 = RegSetValueExW(hKey, L"LastBackupTime", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u);
          v8 = v13;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              122,
              &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
              (unsigned int)v8);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022ff0  push    rbp
0x180022ff2  push    rbx
0x180022ff3  push    rsi
0x180022ff4  push    rdi
0x180022ff5  push    r14
0x180022ff7  push    r15
0x180022ff9  lea     rbp, [rsp-188h]
0x180023001  sub     rsp, 288h
0x180023008  mov     rax, cs:__security_cookie
0x18002300f  xor     rax, rsp
0x180023012  mov     [rbp+1B0h+var_40], rax
0x180023019  mov     r14, r8
0x18002301c  mov     [rsp+2B0h+hKey], 0
0x180023025  mov     esi, edx
0x180023027  mov     rdi, rcx
0x18002302a  xor     edx, edx; Val
0x18002302c  lea     rcx, [rsp+2B0h+SubKey]; void *
0x180023031  mov     r8d, 208h; Size
0x180023037  mov     r15, r9
0x18002303a  call    memset_0
0x18002303f  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180023044  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002304d  call    cs:__imp_GetSystemTimeAsFileTime
0x180023053  mov     rax, [rdi]
0x180023056  mov     rcx, rdi
0x180023059  mov     rax, [rax+28h]
0x18002305d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023062  mov     ebx, eax
0x180023064  lea     rax, WPP_GLOBAL_Control
0x18002306b  test    ebx, ebx
0x18002306d  jz      short loc_1800230A1
0x18002306f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023076  cmp     rcx, rax
0x180023079  jz      short loc_180023099
0x18002307b  test    byte ptr [rcx+1Ch], 40h
0x18002307f  jz      short loc_180023099
0x180023081  mov     rcx, [rcx+10h]
0x180023085  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18002308c  mov     edx, 76h ; 'v'
0x180023091  mov     r9d, ebx
0x180023094  call    WPP_SF_d
0x180023099  test    ebx, ebx
0x18002309b  js      loc_180023267
0x1800230a1  lea     rax, [rsp+2B0h+SubKey]
0x1800230a6  mov     r9, r15
0x1800230a9  mov     r8, r14
0x1800230ac  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x1800230b1  mov     edx, esi
0x1800230b3  mov     rcx, rdi
0x1800230b6  call    ?GetRegistrySubKeyForProtector@RegistryBasedBackupStatusCache@@AEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAG_K@Z; RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(eFveVolumeType,_GUID const *,_GUID const *,ushort *,unsigned __int64)
0x1800230bb  mov     ebx, eax
0x1800230bd  test    eax, eax
0x1800230bf  jz      short loc_1800230FC
0x1800230c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230c8  lea     rsi, WPP_GLOBAL_Control
0x1800230cf  cmp     rcx, rsi
0x1800230d2  jz      short loc_1800230F2
0x1800230d4  test    byte ptr [rcx+1Ch], 40h
0x1800230d8  jz      short loc_1800230F2
0x1800230da  mov     rcx, [rcx+10h]
0x1800230de  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800230e5  mov     edx, 77h ; 'w'
0x1800230ea  mov     r9d, eax
0x1800230ed  call    WPP_SF_d
0x1800230f2  test    ebx, ebx
0x1800230f4  js      loc_180023267
0x1800230fa  jmp     short loc_180023103
0x1800230fc  lea     rsi, WPP_GLOBAL_Control
0x180023103  mov     rax, [rdi]
0x180023106  mov     rcx, rdi
0x180023109  mov     rax, [rax+18h]
0x18002310d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023112  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18002311b  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180023120  mov     rcx, rax; hKey
0x180023123  xor     r9d, r9d; lpClass
0x180023126  lea     rax, [rsp+2B0h+hKey]
0x18002312b  xor     r8d, r8d; Reserved
0x18002312e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180023133  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002313c  mov     [rsp+2B0h+samDesired], 2000000h; samDesired
0x180023144  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x18002314c  call    cs:__imp_RegCreateKeyExW
0x180023152  mov     ebx, eax
0x180023154  mov     edi, 80070000h
0x180023159  test    eax, eax
0x18002315b  jle     short loc_180023162
0x18002315d  movzx   ebx, ax
0x180023160  or      ebx, edi
0x180023162  test    ebx, ebx
0x180023164  jz      short loc_180023198
0x180023166  mov     rcx, cs:WPP_GLOBAL_Control
0x18002316d  cmp     rcx, rsi
0x180023170  jz      short loc_180023190
0x180023172  test    byte ptr [rcx+1Ch], 40h
0x180023176  jz      short loc_180023190
0x180023178  mov     rcx, [rcx+10h]
0x18002317c  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180023183  mov     edx, 78h ; 'x'
0x180023188  mov     r9d, ebx
0x18002318b  call    WPP_SF_d
0x180023190  test    ebx, ebx
0x180023192  js      loc_180023267
0x180023198  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002319d  lea     rax, [rbp+1B0h+Data]
0x1800231a4  mov     r9d, 4; dwType
0x1800231aa  lea     rdx, aLastbackupstat; "LastBackupStatus"
0x1800231b1  mov     [rsp+2B0h+samDesired], r9d; cbData
0x1800231b6  xor     r8d, r8d; Reserved
0x1800231b9  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800231be  call    cs:__imp_RegSetValueExW
0x1800231c4  mov     ebx, eax
0x1800231c6  test    eax, eax
0x1800231c8  jle     short loc_1800231CF
0x1800231ca  movzx   ebx, ax
0x1800231cd  or      ebx, edi
0x1800231cf  test    ebx, ebx
0x1800231d1  jz      short loc_180023201
0x1800231d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231da  cmp     rcx, rsi
0x1800231dd  jz      short loc_1800231FD
0x1800231df  test    byte ptr [rcx+1Ch], 40h
0x1800231e3  jz      short loc_1800231FD
0x1800231e5  mov     rcx, [rcx+10h]
0x1800231e9  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800231f0  mov     edx, 79h ; 'y'
0x1800231f5  mov     r9d, ebx
0x1800231f8  call    WPP_SF_d
0x1800231fd  test    ebx, ebx
0x1800231ff  js      short loc_180023267
0x180023201  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180023206  lea     rax, [rsp+2B0h+SystemTimeAsFileTime]
0x18002320b  mov     [rsp+2B0h+samDesired], 8; cbData
0x180023213  lea     rdx, aLastbackuptime; "LastBackupTime"
0x18002321a  mov     r9d, 0Bh; dwType
0x180023220  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x180023225  xor     r8d, r8d; Reserved
0x180023228  call    cs:__imp_RegSetValueExW
0x18002322e  mov     ebx, eax
0x180023230  test    eax, eax
0x180023232  jle     short loc_180023239
0x180023234  movzx   ebx, ax
0x180023237  or      ebx, edi
0x180023239  test    ebx, ebx
0x18002323b  jz      short loc_180023267
0x18002323d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023244  cmp     rcx, rsi
0x180023247  jz      short loc_180023267
0x180023249  test    byte ptr [rcx+1Ch], 40h
0x18002324d  jz      short loc_180023267
0x18002324f  mov     rcx, [rcx+10h]
0x180023253  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18002325a  mov     edx, 7Ah ; 'z'
0x18002325f  mov     r9d, ebx
0x180023262  call    WPP_SF_d
0x180023267  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002326c  test    rcx, rcx
0x18002326f  jz      short loc_180023277
0x180023271  call    cs:__imp_RegCloseKey
0x180023277  mov     eax, ebx
0x180023279  mov     rcx, [rbp+1B0h+var_40]
0x180023280  xor     rcx, rsp; StackCookie
0x180023283  call    __security_check_cookie
0x180023288  add     rsp, 288h
0x18002328f  pop     r15
0x180023291  pop     r14
0x180023293  pop     rdi
0x180023294  pop     rsi
0x180023295  pop     rbx
0x180023296  pop     rbp
0x180023297  retn
```
