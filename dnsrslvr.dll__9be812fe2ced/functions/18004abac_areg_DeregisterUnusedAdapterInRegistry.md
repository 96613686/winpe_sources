# areg_DeregisterUnusedAdapterInRegistry

- ea: `0x18004abac`
- end: `0x18004adf9`
- name: `areg_DeregisterUnusedAdapterInRegistry`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180036b50`

## callees

- `0x180026134`
- `0x1800264e4`
- `0x180046ec0`
- `0x18004ab34`
- `0x18004abac`
- `0x1800623a4`
- `0x180085fb8`
- `0x180086700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004ac4a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004ac4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004add2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004add2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac77`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004adbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004adbb`

## pseudocode

```c
LSTATUS areg_DeregisterUnusedAdapterInRegistry()
{
  DWORD i; // edi
  LSTATUS result; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  int ValueEx2; // ebx
  _DWORD *EntryFromRegistry; // rax
  void *v6; // rbx
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v10[66]; // [rsp+4Ch] [rbp-B4h] BYREF

  phkResult = 0;
  LODWORD(v10[0]) = 0;
  cchName = 259;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 129, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  for ( i = 0; ; ++i )
  {
    cchName = 259;
    result = RegEnumKeyExW(g_hAregRegKey, i, (LPWSTR)v10 + 2, &cchName, 0, 0, 0, 0);
    if ( result )
      break;
    result = RegOpenKeyExW(g_hAregRegKey, (LPCWSTR)v10 + 2, 0, 0x20019u, &phkResult);
    if ( result )
      break;
    ValueEx2 = Reg_GetValueEx2(v2, phkResult, v3, 0x82u, 4, (__int64)lpClass, v10);
    result = RegCloseKey(phkResult);
    phkResult = 0;
    if ( ValueEx2 )
      return result;
    if ( !LODWORD(v10[0]) )
    {
      EntryFromRegistry = areg_ReadEntryFromRegistry((WCHAR *)v10 + 2, 0, 1);
      v6 = EntryFromRegistry;
      if ( EntryFromRegistry )
      {
        if ( EntryFromRegistry[67] || EntryFromRegistry[66] || EntryFromRegistry[69] || EntryFromRegistry[70] )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          {
            WPP_SF_S(1035, 130, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (char *)v10 + 4);
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            {
              WPP_SF_(1035, 131, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_(1035, 132, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
            }
          }
          areg_DeleteEntry(v6);
          --i;
          SetEvent(g_hAregWakeEvent);
        }
        else
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          {
            WPP_SF_S(1035, 133, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (char *)v10 + 4);
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_(1035, 134, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
          }
          areg_FreeEntry(v6);
        }
      }
    }
  }
  if ( phkResult )
    return RegCloseKey(phkResult);
  return result;
}

```

## disassembly

```asm
0x18004abac  push    rbp
0x18004abae  push    rbx
0x18004abaf  push    rsi
0x18004abb0  push    rdi
0x18004abb1  push    r12
0x18004abb3  push    r13
0x18004abb5  push    r14
0x18004abb7  lea     rbp, [rsp-170h]
0x18004abbf  sub     rsp, 270h
0x18004abc6  mov     rax, cs:__security_cookie
0x18004abcd  xor     rax, rsp
0x18004abd0  mov     [rbp+1A0h+var_40], rax
0x18004abd7  mov     esi, cs:g_fAregPurge
0x18004abdd  xor     r14d, r14d
0x18004abe0  mov     [rsp+2A0h+phkResult], r14
0x18004abe5  mov     [rsp+2A0h+var_254], r14d
0x18004abea  mov     [rsp+2A0h+cchName], 103h
0x18004abf2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004abf9  lea     r13, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18004ac00  mov     r12d, 40Bh
0x18004ac06  jz      short loc_18004AC18
0x18004ac08  mov     edx, 81h
0x18004ac0d  mov     ecx, r12d
0x18004ac10  mov     r8, r13
0x18004ac13  call    WPP_SF_
0x18004ac18  mov     edi, r14d
0x18004ac1b  mov     rcx, cs:g_hAregRegKey; hKey
0x18004ac22  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18004ac27  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18004ac2c  lea     r8, [rsp+2A0h+Name]; lpName
0x18004ac31  mov     [rsp+2A0h+lpcchClass], r14; lpcchClass
0x18004ac36  mov     edx, edi; dwIndex
0x18004ac38  mov     [rsp+2A0h+lpClass], r14; lpClass
0x18004ac3d  mov     [rsp+2A0h+lpReserved], r14; lpReserved
0x18004ac42  mov     [rsp+2A0h+cchName], 103h
0x18004ac4a  call    cs:__imp_RegEnumKeyExW
0x18004ac50  test    eax, eax
0x18004ac52  jnz     loc_18004ADC8
0x18004ac58  mov     rcx, cs:g_hAregRegKey; hKey
0x18004ac5f  lea     rax, [rsp+2A0h+phkResult]
0x18004ac64  mov     r9d, 20019h; samDesired
0x18004ac6a  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x18004ac6f  xor     r8d, r8d; ulOptions
0x18004ac72  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x18004ac77  call    cs:__imp_RegOpenKeyExW
0x18004ac7d  test    eax, eax
0x18004ac7f  jnz     loc_18004ADC8
0x18004ac85  mov     rdx, [rsp+2A0h+phkResult]
0x18004ac8a  lea     rax, [rsp+2A0h+var_254]
0x18004ac8f  mov     [rsp+2A0h+lpcchClass], rax
0x18004ac94  mov     r9d, 82h
0x18004ac9a  mov     dword ptr [rsp+2A0h+lpReserved], 4
0x18004aca2  call    Reg_GetValueEx2
0x18004aca7  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18004acac  mov     ebx, eax
0x18004acae  call    cs:__imp_RegCloseKey
0x18004acb4  mov     [rsp+2A0h+phkResult], r14
0x18004acb9  test    ebx, ebx
0x18004acbb  jnz     loc_18004ADD8
0x18004acc1  cmp     [rsp+2A0h+var_254], r14d
0x18004acc6  jnz     loc_18004ADC1
0x18004accc  xor     edx, edx
0x18004acce  lea     r8d, [rbx+1]
0x18004acd2  lea     rcx, [rsp+2A0h+Name]; Src
0x18004acd7  call    areg_ReadEntryFromRegistry
0x18004acdc  mov     rbx, rax
0x18004acdf  test    rax, rax
0x18004ace2  jz      loc_18004ADC1
0x18004ace8  cmp     [rax+10Ch], r14d
0x18004acef  jnz     short loc_18004AD4F
0x18004acf1  cmp     [rax+108h], r14d
0x18004acf8  jnz     short loc_18004AD4F
0x18004acfa  cmp     [rax+114h], r14d
0x18004ad01  jnz     short loc_18004AD4F
0x18004ad03  cmp     [rax+118h], r14d
0x18004ad0a  jnz     short loc_18004AD4F
0x18004ad0c  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004ad12  test    al, 8
0x18004ad14  jz      short loc_18004AD45
0x18004ad16  mov     edx, 85h
0x18004ad1b  lea     r9, [rsp+2A0h+Name]
0x18004ad20  mov     ecx, r12d
0x18004ad23  mov     r8, r13
0x18004ad26  call    WPP_SF_S
0x18004ad2b  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004ad31  test    al, 8
0x18004ad33  jz      short loc_18004AD45
0x18004ad35  mov     edx, 86h
0x18004ad3a  mov     ecx, r12d
0x18004ad3d  mov     r8, r13
0x18004ad40  call    WPP_SF_
0x18004ad45  mov     rcx, rbx; void *
0x18004ad48  call    areg_FreeEntry
0x18004ad4d  jmp     short loc_18004ADC1
0x18004ad4f  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004ad55  test    al, 8
0x18004ad57  jz      short loc_18004ADA2
0x18004ad59  mov     edx, 82h
0x18004ad5e  lea     r9, [rsp+2A0h+Name]
0x18004ad63  mov     ecx, r12d
0x18004ad66  mov     r8, r13
0x18004ad69  call    WPP_SF_S
0x18004ad6e  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004ad74  test    al, 8
0x18004ad76  jz      short loc_18004ADA2
0x18004ad78  mov     edx, 83h
0x18004ad7d  mov     ecx, r12d
0x18004ad80  mov     r8, r13
0x18004ad83  call    WPP_SF_
0x18004ad88  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18004ad8e  test    al, 8
0x18004ad90  jz      short loc_18004ADA2
0x18004ad92  mov     edx, 84h
0x18004ad97  mov     ecx, r12d
0x18004ad9a  mov     r8, r13
0x18004ad9d  call    WPP_SF_
0x18004ada2  mov     r8d, 1
0x18004ada8  mov     edx, esi
0x18004adaa  mov     rcx, rbx; void *
0x18004adad  call    areg_DeleteEntry
0x18004adb2  mov     rcx, cs:g_hAregWakeEvent; hEvent
0x18004adb9  dec     edi
0x18004adbb  call    cs:__imp_SetEvent
0x18004adc1  inc     edi
0x18004adc3  jmp     loc_18004AC1B
0x18004adc8  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18004adcd  test    rcx, rcx
0x18004add0  jz      short loc_18004ADD8
0x18004add2  call    cs:__imp_RegCloseKey
0x18004add8  mov     rcx, [rbp+1A0h+var_40]
0x18004addf  xor     rcx, rsp; StackCookie
0x18004ade2  call    __security_check_cookie
0x18004ade7  add     rsp, 270h
0x18004adee  pop     r14
0x18004adf0  pop     r13
0x18004adf2  pop     r12
0x18004adf4  pop     rdi
0x18004adf5  pop     rsi
0x18004adf6  pop     rbx
0x18004adf7  pop     rbp
0x18004adf8  retn
```
