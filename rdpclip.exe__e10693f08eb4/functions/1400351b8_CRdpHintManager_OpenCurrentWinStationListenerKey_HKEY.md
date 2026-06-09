# CRdpHintManager::OpenCurrentWinStationListenerKey(HKEY__ * *)

- ea: `0x1400351b8`
- end: `0x140035548`
- name: `?OpenCurrentWinStationListenerKey@CRdpHintManager@@AEAAJPEAPEAUHKEY__@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140035550`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x140008c10`
- `0x140008c9c`
- `0x14000a640`
- `0x140011054`
- `0x1400351b8`
- `0x14006a120`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140035369`
- `msvcrt!wcsrchr` at `0x140035369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400352a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400352db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400352a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400352db`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140035274`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140035274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140035267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140035267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400354e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400354e6`
- `WINSTA!WinStationNameFromLogonIdW` at `0x140035300`
- `WINSTA!WinStationNameFromLogonIdW` at `0x140035300`

## string_xrefs

- `0x1400353f5`: `StringCchCopy() failed.`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::OpenCurrentWinStationListenerKey(CRdpHintManager *this, HKEY *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v4; // ebx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  unsigned int v16; // eax
  DWORD pSessionId; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Str[40]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  pSessionId = 0;
  phkResult = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"phKeyListener");
    }
    return (unsigned int)-2147467261;
  }
  *a2 = 0;
  memset_0(SubKey, 0, 0x104u);
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    if ( !(unsigned __int8)WinStationNameFromLogonIdW(0, pSessionId, Str) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467259;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 91;
LABEL_21:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v10,
        -2147467259);
      return (unsigned int)-2147467259;
    }
    v12 = wcsrchr(Str, 0x23u);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467259;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 92;
      goto LABEL_21;
    }
    *v12 = 0;
    v4 = StringCchCopyW(SubKey, 0x104u, L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\");
    if ( (v4 & 0x80000000) == 0 )
    {
      v4 = StringCchCatW(SubKey, 0x104u, Str);
      if ( (v4 & 0x80000000) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
            v16,
            (__int64)SubKey);
        }
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult) )
        {
          *a2 = phkResult;
          return v4;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)-2147467259;
        }
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 96;
        goto LABEL_21;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v4;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 94;
      v15 = "StringCchCat() failed.";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v4;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 93;
      v15 = "StringCchCopy() failed.";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
      v13,
      (__int64)v15,
      v4);
    return v4;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids, v8, v7);
  }
  v9 = GetLastError();
  v4 = v9;
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x1400351b8  push    rbp
0x1400351ba  push    rbx
0x1400351bb  push    rsi
0x1400351bc  push    rdi
0x1400351bd  lea     rbp, [rsp-1B8h]
0x1400351c5  sub     rsp, 2B8h
0x1400351cc  mov     rax, cs:__security_cookie
0x1400351d3  xor     rax, rsp
0x1400351d6  mov     [rbp+1D0h+var_30], rax
0x1400351dd  mov     [rsp+2D0h+pSessionId], 0
0x1400351e5  mov     rsi, rdx
0x1400351e8  mov     [rsp+2D0h+var_298], 0
0x1400351f1  test    rdx, rdx
0x1400351f4  jnz     short loc_14003524D
0x1400351f6  mov     rax, cs:WPP_GLOBAL_Control
0x1400351fd  lea     rdi, WPP_GLOBAL_Control
0x140035204  cmp     rax, rdi
0x140035207  jz      short loc_140035243
0x140035209  test    byte ptr [rax+1Ch], 8
0x14003520d  jz      short loc_140035243
0x14003520f  cmp     byte ptr [rax+19h], 2
0x140035213  jb      short loc_140035243
0x140035215  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003521a  lea     rcx, aPhkeylistener; "phKeyListener"
0x140035221  mov     r9d, eax
0x140035224  mov     [rsp+2D0h+phkResult], rcx
0x140035229  lea     edx, [rsi+59h]
0x14003522c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035233  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003523a  mov     rcx, [rcx+10h]
0x14003523e  call    WPP_SF_Ds
0x140035243  mov     ebx, 80004003h
0x140035248  jmp     loc_14003552B
0x14003524d  mov     qword ptr [rdx], 0
0x140035254  lea     rcx, [rbp+1D0h+SubKey]; void *
0x140035258  mov     edi, 104h
0x14003525d  xor     edx, edx; Val
0x14003525f  mov     r8d, edi; Size
0x140035262  call    memset_0
0x140035267  call    cs:__imp_GetCurrentProcessId
0x14003526d  mov     ecx, eax; dwProcessId
0x14003526f  lea     rdx, [rsp+2D0h+pSessionId]; pSessionId
0x140035274  call    cs:__imp_ProcessIdToSessionId
0x14003527a  test    eax, eax
0x14003527c  jnz     short loc_1400352F5
0x14003527e  mov     rax, cs:WPP_GLOBAL_Control
0x140035285  lea     rdi, WPP_GLOBAL_Control
0x14003528c  mov     esi, 80070000h
0x140035291  cmp     rax, rdi
0x140035294  jz      short loc_1400352DB
0x140035296  test    byte ptr [rax+1Ch], 8
0x14003529a  jz      short loc_1400352DB
0x14003529c  cmp     byte ptr [rax+19h], 2
0x1400352a0  jb      short loc_1400352DB
0x1400352a2  call    cs:__imp_GetLastError
0x1400352a8  mov     ebx, eax
0x1400352aa  test    eax, eax
0x1400352ac  jle     short loc_1400352B3
0x1400352ae  movzx   ebx, ax
0x1400352b1  or      ebx, esi
0x1400352b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400352b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352bf  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400352c6  mov     edx, 5Ah ; 'Z'
0x1400352cb  mov     dword ptr [rsp+2D0h+phkResult], ebx
0x1400352cf  mov     r9d, eax
0x1400352d2  mov     rcx, [rcx+10h]
0x1400352d6  call    WPP_SF_Dd
0x1400352db  call    cs:__imp_GetLastError
0x1400352e1  mov     ebx, eax
0x1400352e3  test    eax, eax
0x1400352e5  jle     loc_14003552B
0x1400352eb  movzx   ebx, ax
0x1400352ee  or      ebx, esi
0x1400352f0  jmp     loc_14003552B
0x1400352f5  mov     edx, [rsp+2D0h+pSessionId]
0x1400352f9  lea     r8, [rsp+2D0h+Str]
0x1400352fe  xor     ecx, ecx
0x140035300  call    cs:__imp_WinStationNameFromLogonIdW
0x140035306  test    al, al
0x140035308  jnz     short loc_14003535F
0x14003530a  mov     rax, cs:WPP_GLOBAL_Control
0x140035311  lea     rdi, WPP_GLOBAL_Control
0x140035318  cmp     rax, rdi
0x14003531b  jz      short loc_140035355
0x14003531d  test    byte ptr [rax+1Ch], 8
0x140035321  jz      short loc_140035355
0x140035323  cmp     byte ptr [rax+19h], 2
0x140035327  jb      short loc_140035355
0x140035329  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003532e  mov     edx, 5Bh ; '['
0x140035333  mov     rcx, cs:WPP_GLOBAL_Control
0x14003533a  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035341  mov     r9d, eax
0x140035344  mov     dword ptr [rsp+2D0h+phkResult], 80004005h
0x14003534c  mov     rcx, [rcx+10h]
0x140035350  call    WPP_SF_Dd
0x140035355  mov     ebx, 80004005h
0x14003535a  jmp     loc_14003552B
0x14003535f  mov     edx, 23h ; '#'; Ch
0x140035364  lea     rcx, [rsp+2D0h+Str]; Str
0x140035369  call    cs:__imp_wcsrchr
0x14003536f  mov     rcx, rax
0x140035372  test    rax, rax
0x140035375  jnz     short loc_1400353A2
0x140035377  mov     rax, cs:WPP_GLOBAL_Control
0x14003537e  lea     rdi, WPP_GLOBAL_Control
0x140035385  cmp     rax, rdi
0x140035388  jz      short loc_140035355
0x14003538a  test    byte ptr [rax+1Ch], 8
0x14003538e  jz      short loc_140035355
0x140035390  cmp     byte ptr [rax+19h], 2
0x140035394  jb      short loc_140035355
0x140035396  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003539b  mov     edx, 5Ch ; '\'
0x1400353a0  jmp     short loc_140035333
0x1400353a2  xor     eax, eax
0x1400353a4  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Ter"...
0x1400353ab  mov     [rcx], ax
0x1400353ae  mov     rdx, rdi; unsigned __int64
0x1400353b1  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x1400353b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400353ba  mov     ebx, eax
0x1400353bc  test    eax, eax
0x1400353be  jns     short loc_140035424
0x1400353c0  mov     rax, cs:WPP_GLOBAL_Control
0x1400353c7  lea     rdi, WPP_GLOBAL_Control
0x1400353ce  cmp     rax, rdi
0x1400353d1  jz      loc_14003552B
0x1400353d7  test    byte ptr [rax+1Ch], 8
0x1400353db  jz      loc_14003552B
0x1400353e1  cmp     byte ptr [rax+19h], 2
0x1400353e5  jb      loc_14003552B
0x1400353eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400353f0  mov     edx, 5Dh ; ']'
0x1400353f5  lea     rcx, aStringcchcopyF_1; "StringCchCopy() failed."
0x1400353fc  mov     [rsp+2D0h+var_2A8], ebx
0x140035400  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035407  mov     [rsp+2D0h+phkResult], rcx
0x14003540c  mov     r9d, eax
0x14003540f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035416  mov     rcx, [rcx+10h]
0x14003541a  call    WPP_SF_DsD
0x14003541f  jmp     loc_14003552B
0x140035424  lea     r8, [rsp+2D0h+Str]; unsigned __int16 *
0x140035429  mov     rdx, rdi; unsigned __int64
0x14003542c  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x140035430  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035435  mov     ebx, eax
0x140035437  test    eax, eax
0x140035439  jns     short loc_140035479
0x14003543b  mov     rax, cs:WPP_GLOBAL_Control
0x140035442  lea     rdi, WPP_GLOBAL_Control
0x140035449  cmp     rax, rdi
0x14003544c  jz      loc_14003552B
0x140035452  test    byte ptr [rax+1Ch], 8
0x140035456  jz      loc_14003552B
0x14003545c  cmp     byte ptr [rax+19h], 2
0x140035460  jb      loc_14003552B
0x140035466  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003546b  mov     edx, 5Eh ; '^'
0x140035470  lea     rcx, aStringcchcatFa_0; "StringCchCat() failed."
0x140035477  jmp     short loc_1400353FC
0x140035479  mov     rax, cs:WPP_GLOBAL_Control
0x140035480  lea     rdi, WPP_GLOBAL_Control
0x140035487  cmp     rax, rdi
0x14003548a  jz      short loc_1400354C8
0x14003548c  test    dword ptr [rax+1Ch], 200h
0x140035493  jz      short loc_1400354C8
0x140035495  cmp     byte ptr [rax+19h], 5
0x140035499  jb      short loc_1400354C8
0x14003549b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400354a0  lea     rcx, [rbp+1D0h+SubKey]
0x1400354a4  mov     edx, 5Fh ; '_'
0x1400354a9  mov     [rsp+2D0h+phkResult], rcx
0x1400354ae  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400354b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400354bc  mov     r9d, eax
0x1400354bf  mov     rcx, [rcx+10h]
0x1400354c3  call    WPP_SF_DS
0x1400354c8  lea     rax, [rsp+2D0h+var_298]
0x1400354cd  mov     r9d, 20019h; samDesired
0x1400354d3  xor     r8d, r8d; ulOptions
0x1400354d6  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1400354db  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1400354df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400354e6  call    cs:__imp_RegOpenKeyExW
0x1400354ec  test    eax, eax
0x1400354ee  jz      short loc_140035523
0x1400354f0  mov     rax, cs:WPP_GLOBAL_Control
0x1400354f7  cmp     rax, rdi
0x1400354fa  jz      loc_140035355
0x140035500  test    byte ptr [rax+1Ch], 8
0x140035504  jz      loc_140035355
0x14003550a  cmp     byte ptr [rax+19h], 2
0x14003550e  jb      loc_140035355
0x140035514  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035519  mov     edx, 60h ; '`'
0x14003551e  jmp     loc_140035333
0x140035523  mov     rax, [rsp+2D0h+var_298]
0x140035528  mov     [rsi], rax
0x14003552b  mov     eax, ebx
0x14003552d  mov     rcx, [rbp+1D0h+var_30]
0x140035534  xor     rcx, rsp; StackCookie
0x140035537  call    __security_check_cookie
0x14003553c  add     rsp, 2B8h
0x140035543  pop     rdi
0x140035544  pop     rsi
0x140035545  pop     rbx
0x140035546  pop     rbp
0x140035547  retn
```
