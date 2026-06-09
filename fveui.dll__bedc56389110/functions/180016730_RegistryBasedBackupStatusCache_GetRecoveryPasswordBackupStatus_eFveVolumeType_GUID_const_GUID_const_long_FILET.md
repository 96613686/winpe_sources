# RegistryBasedBackupStatusCache::GetRecoveryPasswordBackupStatus(eFveVolumeType,_GUID const *,_GUID const *,long *,_FILETIME *)

- ea: `0x180016730`
- end: `0x180016ac0`
- name: `?GetRecoveryPasswordBackupStatus@RegistryBasedBackupStatusCache@@UEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAJPEAU_FILETIME@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x18000e354`
- `0x18000e408`
- `0x180016730`
- `0x180016ac8`
- `0x180023414`
- `0x18002d010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016a6c`
- `ADVAPI32!RegCloseKey` at `0x180016a6c`
- `ADVAPI32!RegOpenKeyExW` at `0x180016899`
- `ADVAPI32!RegOpenKeyExW` at `0x180016899`
- `ADVAPI32!RegGetValueW` at `0x180016927`
- `ADVAPI32!RegGetValueW` at `0x1800169ac`
- `ADVAPI32!RegGetValueW` at `0x180016927`
- `ADVAPI32!RegGetValueW` at `0x1800169ac`

## pseudocode

```c
__int64 __fastcall RegistryBasedBackupStatusCache::GetRecoveryPasswordBackupStatus(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6)
{
  unsigned int RegistrySubKeyForProtector; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  signed int v13; // ebx
  PVOID *v14; // r10
  HKEY v15; // rax
  LSTATUS v16; // eax
  LSTATUS ValueW; // eax
  LSTATUS v18; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcbData = 0;
  pvData = 0;
  v23 = 0;
  hkey = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
  RegistrySubKeyForProtector = RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(a1, a2, a3, a4, SubKey);
  v13 = RegistrySubKeyForProtector;
  if ( !RegistrySubKeyForProtector )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_S(v14[2], 125, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, SubKey);
    v15 = (HKEY)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    v16 = RegOpenKeyExW(v15, SubKey, 0, 1u, &hkey);
    v13 = v16;
    if ( v16 > 0 )
      v13 = (unsigned __int16)v16 | 0x80070000;
    if ( !v13 )
      goto LABEL_21;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        (unsigned int)v13);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 >= 0 )
    {
LABEL_21:
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"LastBackupStatus", 0x10u, 0, &pvData, &pcbData);
      v13 = ValueW;
      if ( ValueW > 0 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
      if ( !v13 )
        goto LABEL_28;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)v13);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 >= 0 )
      {
LABEL_28:
        pcbData = 8;
        v18 = RegGetValueW(hkey, 0, L"LastBackupTime", 0x40u, 0, &v23, &pcbData);
        v13 = v18;
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
        if ( !v13 )
          goto LABEL_35;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
            (unsigned int)v13);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 >= 0 )
        {
LABEL_35:
          *a5 = pvData;
          *a6 = v23;
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    goto LABEL_36;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      RegistrySubKeyForProtector);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 >= 0 )
    goto LABEL_11;
LABEL_36:
  if ( v13 == -2147024894 )
  {
    *a5 = -2147024894;
    *a6 = 0;
    v13 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  else if ( v13 < 0 )
  {
    goto LABEL_42;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
  {
    WPP_SF_di(v14[2], v11, v12, (unsigned int)*a5, *a6);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( hkey )
  {
    RegCloseKey(hkey);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x20) != 0 )
    WPP_SF_d(v14[2], 130, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016730  push    rbp
0x180016732  push    rbx
0x180016733  push    rsi
0x180016734  push    rdi
0x180016735  push    r12
0x180016737  push    r14
0x180016739  push    r15
0x18001673b  lea     rbp, [rsp-180h]
0x180016743  sub     rsp, 280h
0x18001674a  mov     rax, cs:__security_cookie
0x180016751  xor     rax, rsp
0x180016754  mov     [rbp+1B0h+var_40], rax
0x18001675b  mov     r15, [rbp+1B0h+arg_28]
0x180016762  mov     rdi, r8
0x180016765  mov     r12, [rbp+1B0h+arg_20]
0x18001676c  mov     ebx, edx
0x18001676e  mov     r14, rcx
0x180016771  mov     [rsp+2B0h+var_270], 0
0x180016779  xor     edx, edx; Val
0x18001677b  mov     [rsp+2B0h+var_26C], 0
0x180016783  mov     r8d, 208h; Size
0x180016789  mov     [rsp+2B0h+var_260], 0
0x180016792  lea     rcx, [rsp+2B0h+SubKey]; void *
0x180016797  mov     [rsp+2B0h+hkey], 0
0x1800167a0  mov     rsi, r9
0x1800167a3  call    memset_0
0x1800167a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167af  lea     rax, WPP_GLOBAL_Control
0x1800167b6  cmp     rcx, rax
0x1800167b9  jz      short loc_1800167D6
0x1800167bb  test    byte ptr [rcx+1Ch], 20h
0x1800167bf  jz      short loc_1800167D6
0x1800167c1  mov     rcx, [rcx+10h]
0x1800167c5  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800167cc  mov     edx, 7Bh ; '{'
0x1800167d1  call    WPP_SF_
0x1800167d6  lea     rax, [rsp+2B0h+SubKey]
0x1800167db  mov     r9, rsi
0x1800167de  mov     r8, rdi
0x1800167e1  mov     [rsp+2B0h+phkResult], rax
0x1800167e6  mov     edx, ebx
0x1800167e8  mov     rcx, r14
0x1800167eb  call    ?GetRegistrySubKeyForProtector@RegistryBasedBackupStatusCache@@AEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAG_K@Z; RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(eFveVolumeType,_GUID const *,_GUID const *,ushort *,unsigned __int64)
0x1800167f0  mov     ebx, eax
0x1800167f2  mov     esi, 40h ; '@'
0x1800167f7  test    eax, eax
0x1800167f9  jz      short loc_18001683B
0x1800167fb  mov     r10, cs:WPP_GLOBAL_Control
0x180016802  lea     rdi, WPP_GLOBAL_Control
0x180016809  cmp     r10, rdi
0x18001680c  jz      short loc_180016831
0x18001680e  test    [r10+1Ch], sil
0x180016812  jz      short loc_180016831
0x180016814  mov     rcx, [r10+10h]
0x180016818  lea     edx, [rsi+3Ch]
0x18001681b  mov     r9d, eax
0x18001681e  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016825  call    WPP_SF_d
0x18001682a  mov     r10, cs:WPP_GLOBAL_Control
0x180016831  test    ebx, ebx
0x180016833  js      loc_180016A0E
0x180016839  jmp     short loc_180016849
0x18001683b  mov     r10, cs:WPP_GLOBAL_Control
0x180016842  lea     rdi, WPP_GLOBAL_Control
0x180016849  cmp     r10, rdi
0x18001684c  jz      short loc_18001686F
0x18001684e  test    byte ptr [r10+1Ch], 8
0x180016853  jz      short loc_18001686F
0x180016855  mov     rcx, [r10+10h]
0x180016859  lea     r9, [rsp+2B0h+SubKey]
0x18001685e  mov     edx, 7Dh ; '}'
0x180016863  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001686a  call    WPP_SF_S
0x18001686f  mov     rax, [r14]
0x180016872  mov     rcx, r14
0x180016875  mov     rax, [rax+18h]
0x180016879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687e  mov     rcx, rax; hKey
0x180016881  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180016886  lea     rax, [rsp+2B0h+hkey]
0x18001688b  mov     r9d, 1; samDesired
0x180016891  xor     r8d, r8d; ulOptions
0x180016894  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180016899  call    cs:__imp_RegOpenKeyExW
0x18001689f  mov     ebx, eax
0x1800168a1  mov     r14d, 80070000h
0x1800168a7  test    eax, eax
0x1800168a9  jle     short loc_1800168B1
0x1800168ab  movzx   ebx, ax
0x1800168ae  or      ebx, r14d
0x1800168b1  test    ebx, ebx
0x1800168b3  jz      short loc_1800168EE
0x1800168b5  mov     r10, cs:WPP_GLOBAL_Control
0x1800168bc  cmp     r10, rdi
0x1800168bf  jz      short loc_1800168E6
0x1800168c1  test    [r10+1Ch], sil
0x1800168c5  jz      short loc_1800168E6
0x1800168c7  mov     rcx, [r10+10h]
0x1800168cb  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800168d2  mov     edx, 7Eh ; '~'
0x1800168d7  mov     r9d, ebx
0x1800168da  call    WPP_SF_d
0x1800168df  mov     r10, cs:WPP_GLOBAL_Control
0x1800168e6  test    ebx, ebx
0x1800168e8  js      loc_180016A0E
0x1800168ee  mov     rcx, [rsp+2B0h+hkey]; hkey
0x1800168f3  lea     rax, [rsp+2B0h+var_270]
0x1800168f8  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800168fd  lea     r8, aLastbackupstat; "LastBackupStatus"
0x180016904  lea     rax, [rsp+2B0h+var_26C]
0x180016909  mov     [rsp+2B0h+var_270], 4
0x180016911  mov     [rsp+2B0h+pvData], rax; pvData
0x180016916  mov     r9d, 10h; dwFlags
0x18001691c  xor     edx, edx; lpSubKey
0x18001691e  mov     [rsp+2B0h+phkResult], 0; pdwType
0x180016927  call    cs:__imp_RegGetValueW
0x18001692d  mov     ebx, eax
0x18001692f  test    eax, eax
0x180016931  jle     short loc_180016939
0x180016933  movzx   ebx, ax
0x180016936  or      ebx, r14d
0x180016939  test    ebx, ebx
0x18001693b  jz      short loc_180016976
0x18001693d  mov     r10, cs:WPP_GLOBAL_Control
0x180016944  cmp     r10, rdi
0x180016947  jz      short loc_18001696E
0x180016949  test    [r10+1Ch], sil
0x18001694d  jz      short loc_18001696E
0x18001694f  mov     rcx, [r10+10h]
0x180016953  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001695a  mov     edx, 7Fh
0x18001695f  mov     r9d, ebx
0x180016962  call    WPP_SF_d
0x180016967  mov     r10, cs:WPP_GLOBAL_Control
0x18001696e  test    ebx, ebx
0x180016970  js      loc_180016A0E
0x180016976  mov     rcx, [rsp+2B0h+hkey]; hkey
0x18001697b  lea     rax, [rsp+2B0h+var_270]
0x180016980  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180016985  lea     r8, aLastbackuptime; "LastBackupTime"
0x18001698c  lea     rax, [rsp+2B0h+var_260]
0x180016991  mov     [rsp+2B0h+var_270], 8
0x180016999  mov     [rsp+2B0h+pvData], rax; pvData
0x18001699e  mov     r9d, esi; dwFlags
0x1800169a1  xor     edx, edx; lpSubKey
0x1800169a3  mov     [rsp+2B0h+phkResult], 0; pdwType
0x1800169ac  call    cs:__imp_RegGetValueW
0x1800169b2  mov     ebx, eax
0x1800169b4  test    eax, eax
0x1800169b6  jle     short loc_1800169BE
0x1800169b8  movzx   ebx, ax
0x1800169bb  or      ebx, r14d
0x1800169be  test    ebx, ebx
0x1800169c0  jz      short loc_1800169F7
0x1800169c2  mov     r10, cs:WPP_GLOBAL_Control
0x1800169c9  cmp     r10, rdi
0x1800169cc  jz      short loc_1800169F3
0x1800169ce  test    [r10+1Ch], sil
0x1800169d2  jz      short loc_1800169F3
0x1800169d4  mov     rcx, [r10+10h]
0x1800169d8  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800169df  mov     edx, 80h
0x1800169e4  mov     r9d, ebx
0x1800169e7  call    WPP_SF_d
0x1800169ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800169f3  test    ebx, ebx
0x1800169f5  js      short loc_180016A0E
0x1800169f7  mov     eax, [rsp+2B0h+var_26C]
0x1800169fb  mov     [r12], eax
0x1800169ff  mov     rax, [rsp+2B0h+var_260]
0x180016a04  mov     [r15], rax
0x180016a07  mov     r10, cs:WPP_GLOBAL_Control
0x180016a0e  mov     eax, 80070002h
0x180016a13  cmp     ebx, eax
0x180016a15  jnz     short loc_180016A2B
0x180016a17  mov     [r12], eax
0x180016a1b  xor     eax, eax
0x180016a1d  mov     [r15], rax
0x180016a20  xor     ebx, ebx
0x180016a22  mov     r10, cs:WPP_GLOBAL_Control
0x180016a29  jmp     short loc_180016A2F
0x180016a2b  test    ebx, ebx
0x180016a2d  js      short loc_180016A62
0x180016a2f  cmp     r10, rdi
0x180016a32  jz      short loc_180016A62
0x180016a34  test    byte ptr [r10+1Ch], 8
0x180016a39  jz      short loc_180016A62
0x180016a3b  mov     ecx, [r15+4]
0x180016a3f  mov     eax, [r15]
0x180016a42  mov     r9d, [r12]
0x180016a46  shl     rcx, 20h
0x180016a4a  or      rcx, rax
0x180016a4d  mov     [rsp+2B0h+phkResult], rcx
0x180016a52  mov     rcx, [r10+10h]
0x180016a56  call    WPP_SF_di
0x180016a5b  mov     r10, cs:WPP_GLOBAL_Control
0x180016a62  mov     rcx, [rsp+2B0h+hkey]; hKey
0x180016a67  test    rcx, rcx
0x180016a6a  jz      short loc_180016A79
0x180016a6c  call    cs:__imp_RegCloseKey
0x180016a72  mov     r10, cs:WPP_GLOBAL_Control
0x180016a79  cmp     r10, rdi
0x180016a7c  jz      short loc_180016A9D
0x180016a7e  test    byte ptr [r10+1Ch], 20h
0x180016a83  jz      short loc_180016A9D
0x180016a85  mov     rcx, [r10+10h]
0x180016a89  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016a90  mov     edx, 82h
0x180016a95  mov     r9d, ebx
0x180016a98  call    WPP_SF_d
0x180016a9d  mov     eax, ebx
0x180016a9f  mov     rcx, [rbp+1B0h+var_40]
0x180016aa6  xor     rcx, rsp; StackCookie
0x180016aa9  call    __security_check_cookie
0x180016aae  add     rsp, 280h
0x180016ab5  pop     r15
0x180016ab7  pop     r14
0x180016ab9  pop     r12
0x180016abb  pop     rdi
0x180016abc  pop     rsi
0x180016abd  pop     rbx
0x180016abe  pop     rbp
0x180016abf  retn
```
