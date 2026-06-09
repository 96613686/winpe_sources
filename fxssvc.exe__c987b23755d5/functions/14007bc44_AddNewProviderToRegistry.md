# AddNewProviderToRegistry

- ea: `0x14007bc44`
- end: `0x14007c075`
- name: `AddNewProviderToRegistry`
- size: `1073`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001c720`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x14006fa88`
- `0x1400709fc`
- `0x14007bc44`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007bfe7`
- `ADVAPI32!RegCloseKey` at `0x14007c02a`
- `ADVAPI32!RegCloseKey` at `0x14007bfe7`
- `ADVAPI32!RegCloseKey` at `0x14007c02a`
- `ADVAPI32!RegOpenKeyExW` at `0x14007bccc`
- `ADVAPI32!RegOpenKeyExW` at `0x14007bccc`
- `ADVAPI32!RegCreateKeyExW` at `0x14007bd48`
- `ADVAPI32!RegCreateKeyExW` at `0x14007bd48`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007bf6b`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007bf6b`
- `KERNEL32!GetLastError` at `0x14007bdbc`
- `KERNEL32!GetLastError` at `0x14007be13`
- `KERNEL32!GetLastError` at `0x14007be6e`
- `KERNEL32!GetLastError` at `0x14007bec4`
- `KERNEL32!GetLastError` at `0x14007bf0e`
- `KERNEL32!GetLastError` at `0x14007bdbc`
- `KERNEL32!GetLastError` at `0x14007be13`
- `KERNEL32!GetLastError` at `0x14007be6e`
- `KERNEL32!GetLastError` at `0x14007bec4`
- `KERNEL32!GetLastError` at `0x14007bf0e`

## pseudocode

```c
__int64 __fastcall AddNewProviderToRegistry(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v9; // ebx
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  LSTATUS v13; // eax
  DWORD LastError; // eax
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  int phkResultc; // [rsp+20h] [rbp-40h]
  HKEY v25; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF

  hKey = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Device Providers", 0, 0x20006u, &hKey);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 106;
      v12 = v9;
LABEL_64:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v12);
      return v9;
    }
    return v9;
  }
  v13 = RegCreateKeyExW(hKey, a1, 0, 0, 0, 0x2000000u, 0, &v25, 0);
  v9 = v13;
  if ( !v13 )
  {
    if ( SetRegistryStringValue(v25, 1u, L"FriendlyName", a2, phkResult) )
    {
      if ( SetRegistryStringValue(v25, 2u, L"ImageName", a3, phkResulta) )
      {
        if ( SetRegistryStringValue(v25, 1u, L"ProviderName", a4, phkResultb) )
        {
          if ( SetRegistryStringValue(v25, 1u, L"GUID", a1, phkResultc) )
          {
            if ( (unsigned int)SetRegistryDword(v25, L"APIVersion", a5) )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, a2);
              }
              goto LABEL_52;
            }
            LastError = GetLastError();
            v9 = LastError;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 112;
              goto LABEL_40;
            }
          }
          else
          {
            LastError = GetLastError();
            v9 = LastError;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 111;
              goto LABEL_40;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 110;
            goto LABEL_40;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 109;
          goto LABEL_40;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 108;
LABEL_40:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
    }
    if ( !v9 )
      goto LABEL_52;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
      (_DWORD)a2,
      v13);
  }
LABEL_42:
  if ( !hKey )
    goto LABEL_58;
  v17 = RegDeleteKeyExW(hKey, a1, 0, 0);
  if ( v17
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v17);
  }
LABEL_52:
  if ( hKey )
  {
    v18 = RegCloseKey(hKey);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v18);
      }
    }
  }
LABEL_58:
  if ( v25 )
  {
    v19 = RegCloseKey(v25);
    if ( v19 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 116;
        v12 = v19;
        goto LABEL_64;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14007bc44  push    rbp
0x14007bc46  push    rbx
0x14007bc47  push    rsi
0x14007bc48  push    rdi
0x14007bc49  push    r12
0x14007bc4b  push    r14
0x14007bc4d  push    r15
0x14007bc4f  mov     rbp, rsp
0x14007bc52  sub     rsp, 60h
0x14007bc56  mov     r14, r9
0x14007bc59  mov     [rbp+hKey], 0
0x14007bc61  mov     rsi, r8
0x14007bc64  mov     [rbp+var_10], 0
0x14007bc6c  mov     rdi, rdx
0x14007bc6f  mov     r15, rcx
0x14007bc72  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bc79  lea     rax, WPP_GLOBAL_Control
0x14007bc80  mov     r12d, 2
0x14007bc86  cmp     rcx, rax
0x14007bc89  jz      short loc_14007BCAC
0x14007bc8b  test    [rcx+1Ch], r12b
0x14007bc8f  jz      short loc_14007BCAC
0x14007bc91  cmp     byte ptr [rcx+19h], 5
0x14007bc95  jb      short loc_14007BCAC
0x14007bc97  mov     rcx, [rcx+10h]
0x14007bc9b  lea     edx, [r12+67h]
0x14007bca0  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007bca7  call    WPP_SF_
0x14007bcac  lea     rax, [rbp+hKey]
0x14007bcb0  mov     r9d, 20006h; samDesired
0x14007bcb6  xor     r8d, r8d; ulOptions
0x14007bcb9  mov     [rsp+60h+phkResult], rax; phkResult
0x14007bcbe  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Fax\\Device Provid"...
0x14007bcc5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007bccc  call    cs:__imp_RegOpenKeyExW
0x14007bcd2  mov     ebx, eax
0x14007bcd4  test    eax, eax
0x14007bcd6  jz      short loc_14007BD10
0x14007bcd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bcdf  lea     rax, WPP_GLOBAL_Control
0x14007bce6  cmp     rcx, rax
0x14007bce9  jz      loc_14007C064
0x14007bcef  test    [rcx+1Ch], r12b
0x14007bcf3  jz      loc_14007C064
0x14007bcf9  cmp     [rcx+19h], r12b
0x14007bcfd  jb      loc_14007C064
0x14007bd03  mov     edx, 6Ah ; 'j'
0x14007bd08  mov     r9d, ebx
0x14007bd0b  jmp     loc_14007C054
0x14007bd10  mov     rcx, [rbp+hKey]; hKey
0x14007bd14  lea     rax, [rbp+var_10]
0x14007bd18  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x14007bd21  xor     r9d, r9d; lpClass
0x14007bd24  mov     [rsp+60h+var_28], rax; phkResult
0x14007bd29  xor     r8d, r8d; Reserved
0x14007bd2c  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14007bd35  mov     rdx, r15; lpSubKey
0x14007bd38  mov     [rsp+60h+samDesired], 2000000h; samDesired
0x14007bd40  mov     dword ptr [rsp+60h+phkResult], 0; int
0x14007bd48  call    cs:__imp_RegCreateKeyExW
0x14007bd4e  mov     ebx, eax
0x14007bd50  test    eax, eax
0x14007bd52  jz      short loc_14007BDA0
0x14007bd54  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bd5b  lea     rsi, WPP_GLOBAL_Control
0x14007bd62  cmp     rcx, rsi
0x14007bd65  jz      loc_14007BF55
0x14007bd6b  test    [rcx+1Ch], r12b
0x14007bd6f  jz      loc_14007BF55
0x14007bd75  cmp     [rcx+19h], r12b
0x14007bd79  jb      loc_14007BF55
0x14007bd7f  mov     rcx, [rcx+10h]
0x14007bd83  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007bd8a  mov     edx, 6Bh ; 'k'
0x14007bd8f  mov     dword ptr [rsp+60h+phkResult], eax
0x14007bd93  mov     r9, rdi
0x14007bd96  call    WPP_SF_Sd
0x14007bd9b  jmp     loc_14007BF55
0x14007bda0  mov     rcx, [rbp+var_10]; HKEY
0x14007bda4  lea     r8, aFriendlyname; "FriendlyName"
0x14007bdab  mov     r9, rdi; unsigned __int16 *
0x14007bdae  mov     edx, 1; unsigned int
0x14007bdb3  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007bdb8  test    eax, eax
0x14007bdba  jnz     short loc_14007BDF9
0x14007bdbc  call    cs:__imp_GetLastError
0x14007bdc2  mov     ebx, eax
0x14007bdc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bdcb  lea     rsi, WPP_GLOBAL_Control
0x14007bdd2  cmp     rcx, rsi
0x14007bdd5  jz      loc_14007BF4D
0x14007bddb  test    [rcx+1Ch], r12b
0x14007bddf  jz      loc_14007BF4D
0x14007bde5  cmp     [rcx+19h], r12b
0x14007bde9  jb      loc_14007BF4D
0x14007bdef  mov     edx, 6Ch ; 'l'
0x14007bdf4  jmp     loc_14007BF3A
0x14007bdf9  mov     rcx, [rbp+var_10]; HKEY
0x14007bdfd  lea     r8, aImagename; "ImageName"
0x14007be04  mov     r9, rsi; unsigned __int16 *
0x14007be07  mov     edx, r12d; unsigned int
0x14007be0a  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007be0f  test    eax, eax
0x14007be11  jnz     short loc_14007BE50
0x14007be13  call    cs:__imp_GetLastError
0x14007be19  mov     ebx, eax
0x14007be1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007be22  lea     rsi, WPP_GLOBAL_Control
0x14007be29  cmp     rcx, rsi
0x14007be2c  jz      loc_14007BF4D
0x14007be32  test    [rcx+1Ch], r12b
0x14007be36  jz      loc_14007BF4D
0x14007be3c  cmp     [rcx+19h], r12b
0x14007be40  jb      loc_14007BF4D
0x14007be46  mov     edx, 6Dh ; 'm'
0x14007be4b  jmp     loc_14007BF3A
0x14007be50  mov     rcx, [rbp+var_10]; HKEY
0x14007be54  lea     r8, aProvidername; "ProviderName"
0x14007be5b  mov     esi, 1
0x14007be60  mov     r9, r14; unsigned __int16 *
0x14007be63  mov     edx, esi; unsigned int
0x14007be65  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007be6a  test    eax, eax
0x14007be6c  jnz     short loc_14007BEAB
0x14007be6e  call    cs:__imp_GetLastError
0x14007be74  mov     ebx, eax
0x14007be76  mov     rcx, cs:WPP_GLOBAL_Control
0x14007be7d  lea     rsi, WPP_GLOBAL_Control
0x14007be84  cmp     rcx, rsi
0x14007be87  jz      loc_14007BF4D
0x14007be8d  test    [rcx+1Ch], r12b
0x14007be91  jz      loc_14007BF4D
0x14007be97  cmp     [rcx+19h], r12b
0x14007be9b  jb      loc_14007BF4D
0x14007bea1  mov     edx, 6Eh ; 'n'
0x14007bea6  jmp     loc_14007BF3A
0x14007beab  mov     rcx, [rbp+var_10]; HKEY
0x14007beaf  lea     r8, aGuid_0; "GUID"
0x14007beb6  mov     r9, r15; unsigned __int16 *
0x14007beb9  mov     edx, esi; unsigned int
0x14007bebb  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14007bec0  test    eax, eax
0x14007bec2  jnz     short loc_14007BEF2
0x14007bec4  call    cs:__imp_GetLastError
0x14007beca  mov     ebx, eax
0x14007becc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bed3  lea     rsi, WPP_GLOBAL_Control
0x14007beda  cmp     rcx, rsi
0x14007bedd  jz      short loc_14007BF4D
0x14007bedf  test    [rcx+1Ch], r12b
0x14007bee3  jz      short loc_14007BF4D
0x14007bee5  cmp     [rcx+19h], r12b
0x14007bee9  jb      short loc_14007BF4D
0x14007beeb  mov     edx, 6Fh ; 'o'
0x14007bef0  jmp     short loc_14007BF3A
0x14007bef2  mov     r8d, [rbp+arg_20]
0x14007bef6  lea     rdx, aApiversion; "APIVersion"
0x14007befd  mov     rcx, [rbp+var_10]
0x14007bf01  call    SetRegistryDword
0x14007bf06  test    eax, eax
0x14007bf08  jnz     loc_14007BFA7
0x14007bf0e  call    cs:__imp_GetLastError
0x14007bf14  mov     ebx, eax
0x14007bf16  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bf1d  lea     rsi, WPP_GLOBAL_Control
0x14007bf24  cmp     rcx, rsi
0x14007bf27  jz      short loc_14007BF4D
0x14007bf29  test    [rcx+1Ch], r12b
0x14007bf2d  jz      short loc_14007BF4D
0x14007bf2f  cmp     [rcx+19h], r12b
0x14007bf33  jb      short loc_14007BF4D
0x14007bf35  mov     edx, 70h ; 'p'
0x14007bf3a  mov     rcx, [rcx+10h]
0x14007bf3e  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007bf45  mov     r9d, eax
0x14007bf48  call    WPP_SF_d
0x14007bf4d  test    ebx, ebx
0x14007bf4f  jz      loc_14007BFDE
0x14007bf55  mov     rcx, [rbp+hKey]; hKey
0x14007bf59  test    rcx, rcx
0x14007bf5c  jz      loc_14007C021
0x14007bf62  xor     r9d, r9d; Reserved
0x14007bf65  xor     r8d, r8d; samDesired
0x14007bf68  mov     rdx, r15; lpSubKey
0x14007bf6b  call    cs:__imp_RegDeleteKeyExW
0x14007bf71  test    eax, eax
0x14007bf73  jz      short loc_14007BFDE
0x14007bf75  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bf7c  cmp     rcx, rsi
0x14007bf7f  jz      short loc_14007BFDE
0x14007bf81  test    [rcx+1Ch], r12b
0x14007bf85  jz      short loc_14007BFDE
0x14007bf87  cmp     [rcx+19h], r12b
0x14007bf8b  jb      short loc_14007BFDE
0x14007bf8d  mov     rcx, [rcx+10h]
0x14007bf91  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007bf98  mov     edx, 72h ; 'r'
0x14007bf9d  mov     r9d, eax
0x14007bfa0  call    WPP_SF_d
0x14007bfa5  jmp     short loc_14007BFDE
0x14007bfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bfae  lea     rsi, WPP_GLOBAL_Control
0x14007bfb5  cmp     rcx, rsi
0x14007bfb8  jz      short loc_14007BFDE
0x14007bfba  test    [rcx+1Ch], r12b
0x14007bfbe  jz      short loc_14007BFDE
0x14007bfc0  cmp     byte ptr [rcx+19h], 5
0x14007bfc4  jb      short loc_14007BFDE
0x14007bfc6  mov     rcx, [rcx+10h]
0x14007bfca  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007bfd1  mov     edx, 71h ; 'q'
0x14007bfd6  mov     r9, rdi
0x14007bfd9  call    WPP_SF_S
0x14007bfde  mov     rcx, [rbp+hKey]; hKey
0x14007bfe2  test    rcx, rcx
0x14007bfe5  jz      short loc_14007C021
0x14007bfe7  call    cs:__imp_RegCloseKey
0x14007bfed  test    eax, eax
0x14007bfef  jz      short loc_14007C021
0x14007bff1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bff8  cmp     rcx, rsi
0x14007bffb  jz      short loc_14007C021
0x14007bffd  test    [rcx+1Ch], r12b
0x14007c001  jz      short loc_14007C021
0x14007c003  cmp     [rcx+19h], r12b
0x14007c007  jb      short loc_14007C021
0x14007c009  mov     rcx, [rcx+10h]
0x14007c00d  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c014  mov     edx, 73h ; 's'
0x14007c019  mov     r9d, eax
0x14007c01c  call    WPP_SF_d
0x14007c021  mov     rcx, [rbp+var_10]; hKey
0x14007c025  test    rcx, rcx
0x14007c028  jz      short loc_14007C064
0x14007c02a  call    cs:__imp_RegCloseKey
0x14007c030  test    eax, eax
0x14007c032  jz      short loc_14007C064
0x14007c034  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c03b  cmp     rcx, rsi
0x14007c03e  jz      short loc_14007C064
0x14007c040  test    [rcx+1Ch], r12b
0x14007c044  jz      short loc_14007C064
0x14007c046  cmp     [rcx+19h], r12b
0x14007c04a  jb      short loc_14007C064
0x14007c04c  mov     edx, 74h ; 't'
0x14007c051  mov     r9d, eax
0x14007c054  mov     rcx, [rcx+10h]
0x14007c058  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c05f  call    WPP_SF_d
0x14007c064  mov     eax, ebx
0x14007c066  add     rsp, 60h
0x14007c06a  pop     r15
0x14007c06c  pop     r14
0x14007c06e  pop     r12
0x14007c070  pop     rdi
0x14007c071  pop     rsi
0x14007c072  pop     rbx
0x14007c073  pop     rbp
0x14007c074  retn
```
