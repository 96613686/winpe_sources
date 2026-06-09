# NotifySessionResultRecovery

- ea: `0x140010f44`
- end: `0x1400112ec`
- name: `NotifySessionResultRecovery`
- size: `936`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000eee0`
- `0x14000f13c`
- `0x14000fff0`
- `0x1400128d4`
- `0x140013ae0`

## callees

- `0x14000271f`
- `0x140010f44`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011216`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010fb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010fb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011005`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011005`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011047`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400111ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400111ed`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010fde`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140011088`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400110cc`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010fde`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140011088`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400110cc`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140011034`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140011124`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140011034`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140011124`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400111d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011256`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011285`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400111d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011256`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011285`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011194`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400112b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400112b9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140011201`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140011201`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x140011061`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x140011061`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400112a4`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400112a4`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140011135`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140011169`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140011135`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140011169`

## string_xrefs

- `0x14001107b`: `SessionAutoDeleteKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NotifySessionResultRecovery(LPCWSTR lpSubKey, int a2)
{
  signed int DWORD; // eax
  signed int InitiationInfo; // ebx
  unsigned int v5; // r9d
  int v6; // eax
  int v7; // edx
  int v8; // eax
  LSTATUS v9; // eax
  bool v10; // cc
  signed int LastError; // eax
  bool v12; // cc
  unsigned int v14; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-55h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+40h] [rbp-49h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-41h] BYREF
  BYTE v19[8]; // [rsp+50h] [rbp-39h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp-31h] BYREF
  _DWORD v21[5]; // [rsp+60h] [rbp-29h] BYREF
  int v22; // [rsp+74h] [rbp-15h]
  _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp+17h] BYREF

  *(_DWORD *)Data = a2;
  memset_0(v21, 0, 0x40u);
  SystemTime = 0;
  FileTime = 0;
  *(_DWORD *)v19 = 5;
  hKey = 0;
  v15 = 0;
  v14 = 0;
  EnterCriticalSection(&stru_140024310);
  v17 = &stru_140024310;
  DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"ChildCount", &v14);
  InitiationInfo = DWORD;
  if ( (int)(DWORD + 0x80000000) >= 0 && DWORD != -2147024894 )
    goto LABEL_3;
  v5 = v14;
  if ( v14 > 1 )
  {
    --v14;
    InitiationInfo = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"ChildCount", v5 - 1);
LABEL_3:
    LeaveCriticalSection(&stru_140024310);
    goto LABEL_36;
  }
  LeaveCriticalSection(&stru_140024310);
  v21[0] = 64;
  InitiationInfo = OmaDmGetInitiationInfo(lpSubKey, v21);
  if ( InitiationInfo >= 0 )
  {
    InitiationInfo = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"SessionAutoDeleteKey", &v15);
    if ( InitiationInfo >= 0 )
    {
      v6 = v22;
      if ( v22 != 5
        || v15
        && ((LODWORD(v17) = 0,
             InitiationInfo = OmaDmRegistryGetDWORD(
                                HKEY_LOCAL_MACHINE,
                                lpSubKey,
                                L"SessionHRESULT",
                                (unsigned int *)&v17),
             ((InitiationInfo + 0x80000000) & 0x80000000) != 0)
         || InitiationInfo == -2147024894)
        && ((int)v17 >= 0
         || ((unsigned int)((_DWORD)v17 + 2147012894) > 0x1E
          || (v7 = 1476427821, !_bittest(&v7, (_DWORD)v17 + 2147012894)))
         && (_DWORD)v17 != -2147012816
          ? (v8 = OmaDmCloseSession(lpSubKey))
          : (v8 = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"SessionState", 6u)),
            (InitiationInfo = v8, v8 >= 0) && (v6 = v22, v22 != 5)) )
      {
        if ( v6 != 6 )
        {
          if ( v15 )
          {
            v9 = OmaDmCloseSession(lpSubKey);
LABEL_23:
            InitiationInfo = v9;
            goto LABEL_36;
          }
          v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
          v10 = v9 <= 0;
          if ( v9 || (v9 = RegSetValueExW(hKey, L"SessionHRESULT", 0, 4u, Data, 4u), v10 = v9 <= 0, v9) )
          {
            if ( v10 )
              goto LABEL_23;
            InitiationInfo = (unsigned __int16)v9 | 0x80070000;
          }
          else
          {
            GetSystemTime(&SystemTime);
            if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
              goto LABEL_41;
            LastError = GetLastError();
            InitiationInfo = LastError;
            if ( LastError > 0 )
              InitiationInfo = (unsigned __int16)LastError | 0x80070000;
            if ( InitiationInfo >= 0 )
            {
LABEL_41:
              v9 = RegSetValueExW(hKey, L"SessionStateTimeStamp", 0, 3u, (const BYTE *)&FileTime, 8u);
              v12 = v9 <= 0;
              if ( v9 || (v9 = RegSetValueExW(hKey, L"SessionState", 0, 4u, v19, 4u), v12 = v9 <= 0, v9) )
              {
                if ( v12 )
                  goto LABEL_23;
                InitiationInfo = (unsigned __int16)v9 | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
LABEL_36:
  OmaDmFreeInitiationInfo(v21);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)InitiationInfo;
}

```

## disassembly

```asm
0x140010f44  mov     [rsp-8+arg_10], rbx
0x140010f49  push    rbp
0x140010f4a  push    rdi
0x140010f4b  push    r13
0x140010f4d  push    r14
0x140010f4f  push    r15
0x140010f51  lea     rbp, [rsp-37h]
0x140010f56  sub     rsp, 0C0h
0x140010f5d  mov     rax, cs:__security_cookie
0x140010f64  xor     rax, rsp
0x140010f67  mov     [rbp+57h+var_30], rax
0x140010f6b  mov     rdi, rcx
0x140010f6e  mov     dword ptr [rbp+57h+Data], edx
0x140010f71  xor     edx, edx; Val
0x140010f73  lea     r8d, [rdx+40h]; Size
0x140010f77  lea     rcx, [rbp+57h+var_80]; void *
0x140010f7b  call    memset_0
0x140010f80  xorps   xmm0, xmm0
0x140010f83  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x140010f87  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x140010f8f  mov     dword ptr [rbp+57h+var_90], 5
0x140010f96  mov     [rbp+57h+hKey], 0
0x140010f9e  mov     [rbp+57h+var_AC], 0
0x140010fa5  mov     [rbp+57h+var_B0], 0
0x140010fac  lea     r15, stru_140024310
0x140010fb3  mov     rcx, r15; lpCriticalSection
0x140010fb6  call    cs:__imp_EnterCriticalSection
0x140010fbd  nop     dword ptr [rax+rax+00h]
0x140010fc2  mov     [rbp+57h+var_A0], r15
0x140010fc6  lea     r9, [rbp+57h+var_B0]
0x140010fca  lea     r8, aChildcount; "ChildCount"
0x140010fd1  mov     rdx, rdi
0x140010fd4  mov     r14, 0FFFFFFFF80000002h
0x140010fdb  mov     rcx, r14
0x140010fde  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140010fe5  nop     dword ptr [rax+rax+00h]
0x140010fea  mov     ebx, eax
0x140010fec  mov     r13d, 80000000h
0x140010ff2  lea     edx, [rax+r13]
0x140010ff6  test    r13d, edx
0x140010ff9  jnz     short loc_140011016
0x140010ffb  cmp     eax, 80070002h
0x140011000  jz      short loc_140011016
0x140011002  mov     rcx, r15; lpCriticalSection
0x140011005  call    cs:__imp_LeaveCriticalSection
0x14001100c  nop     dword ptr [rax+rax+00h]
0x140011011  jmp     loc_1400112A0
0x140011016  mov     r9d, [rbp+57h+var_B0]
0x14001101a  cmp     r9d, 1
0x14001101e  jbe     short loc_140011044
0x140011020  dec     r9d
0x140011023  mov     [rbp+57h+var_B0], r9d
0x140011027  lea     r8, aChildcount; "ChildCount"
0x14001102e  mov     rdx, rdi
0x140011031  mov     rcx, r14
0x140011034  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14001103b  nop     dword ptr [rax+rax+00h]
0x140011040  mov     ebx, eax
0x140011042  jmp     short loc_140011002
0x140011044  mov     rcx, r15; lpCriticalSection
0x140011047  call    cs:__imp_LeaveCriticalSection
0x14001104e  nop     dword ptr [rax+rax+00h]
0x140011053  mov     [rbp+57h+var_80], 40h ; '@'
0x14001105a  lea     rdx, [rbp+57h+var_80]
0x14001105e  mov     rcx, rdi
0x140011061  call    cs:__imp_OmaDmGetInitiationInfo
0x140011068  nop     dword ptr [rax+rax+00h]
0x14001106d  mov     ebx, eax
0x14001106f  test    eax, eax
0x140011071  js      loc_1400112A0
0x140011077  lea     r9, [rbp+57h+var_AC]
0x14001107b  lea     r8, aSessionautodel; "SessionAutoDeleteKey"
0x140011082  mov     rdx, rdi
0x140011085  mov     rcx, r14
0x140011088  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001108f  nop     dword ptr [rax+rax+00h]
0x140011094  mov     ebx, eax
0x140011096  test    eax, eax
0x140011098  js      loc_1400112A0
0x14001109e  mov     eax, [rbp+57h+var_6C]
0x1400110a1  cmp     eax, 5
0x1400110a4  jnz     loc_140011157
0x1400110aa  cmp     [rbp+57h+var_AC], 0
0x1400110ae  jz      loc_1400112A0
0x1400110b4  mov     dword ptr [rbp+57h+var_A0], 0
0x1400110bb  lea     r9, [rbp+57h+var_A0]
0x1400110bf  lea     r8, aSessionhresult; "SessionHRESULT"
0x1400110c6  mov     rdx, rdi
0x1400110c9  mov     rcx, r14
0x1400110cc  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400110d3  nop     dword ptr [rax+rax+00h]
0x1400110d8  mov     ebx, eax
0x1400110da  add     eax, r13d
0x1400110dd  test    r13d, eax
0x1400110e0  jnz     short loc_1400110EE
0x1400110e2  cmp     ebx, 80070002h
0x1400110e8  jnz     loc_1400112A0
0x1400110ee  mov     eax, dword ptr [rbp+57h+var_A0]
0x1400110f1  test    eax, eax
0x1400110f3  jns     short loc_140011132
0x1400110f5  lea     ecx, [rax+7FF8D11Eh]
0x1400110fb  cmp     ecx, 1Eh
0x1400110fe  ja      short loc_14001110A
0x140011100  mov     edx, 5800802Dh
0x140011105  bt      edx, ecx
0x140011108  jb      short loc_140011111
0x14001110a  cmp     eax, 80072F30h
0x14001110f  jnz     short loc_140011132
0x140011111  mov     r9d, 6
0x140011117  lea     r8, aSessionstate; "SessionState"
0x14001111e  mov     rdx, rdi
0x140011121  mov     rcx, r14
0x140011124  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14001112b  nop     dword ptr [rax+rax+00h]
0x140011130  jmp     short loc_140011141
0x140011132  mov     rcx, rdi
0x140011135  call    cs:__imp_OmaDmCloseSession
0x14001113c  nop     dword ptr [rax+rax+00h]
0x140011141  test    eax, eax
0x140011143  mov     ebx, eax
0x140011145  js      loc_1400112A0
0x14001114b  mov     eax, [rbp+57h+var_6C]
0x14001114e  cmp     eax, 5
0x140011151  jz      loc_1400112A0
0x140011157  cmp     eax, 6
0x14001115a  jz      loc_1400112A0
0x140011160  cmp     [rbp+57h+var_AC], 0
0x140011164  jz      short loc_14001117C
0x140011166  mov     rcx, rdi
0x140011169  call    cs:__imp_OmaDmCloseSession
0x140011170  nop     dword ptr [rax+rax+00h]
0x140011175  mov     ebx, eax
0x140011177  jmp     loc_1400112A0
0x14001117c  lea     rax, [rbp+57h+hKey]
0x140011180  mov     [rsp+0E0h+phkResult], rax; phkResult
0x140011185  mov     r9d, 20006h; samDesired
0x14001118b  xor     r8d, r8d; ulOptions
0x14001118e  mov     rdx, rdi; lpSubKey
0x140011191  mov     rcx, r14; hKey
0x140011194  call    cs:__imp_RegOpenKeyExW
0x14001119b  nop     dword ptr [rax+rax+00h]
0x1400111a0  test    eax, eax
0x1400111a2  jz      short loc_1400111B4
0x1400111a4  jle     short loc_140011175
0x1400111a6  movzx   ebx, ax
0x1400111a9  or      ebx, 80070000h
0x1400111af  jmp     loc_1400112A0
0x1400111b4  mov     r14d, 4
0x1400111ba  mov     [rsp+0E0h+cbData], r14d; cbData
0x1400111bf  lea     rax, [rbp+57h+Data]
0x1400111c3  mov     [rsp+0E0h+phkResult], rax; lpData
0x1400111c8  mov     r9d, r14d; dwType
0x1400111cb  xor     r8d, r8d; Reserved
0x1400111ce  lea     rdx, aSessionhresult; "SessionHRESULT"
0x1400111d5  mov     rcx, [rbp+57h+hKey]; hKey
0x1400111d9  call    cs:__imp_RegSetValueExW
0x1400111e0  nop     dword ptr [rax+rax+00h]
0x1400111e5  test    eax, eax
0x1400111e7  jnz     short loc_1400111A4
0x1400111e9  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1400111ed  call    cs:__imp_GetSystemTime
0x1400111f4  nop     dword ptr [rax+rax+00h]
0x1400111f9  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1400111fd  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x140011201  call    cs:__imp_SystemTimeToFileTime
0x140011208  nop     dword ptr [rax+rax+00h]
0x14001120d  mov     edi, 80070000h
0x140011212  test    eax, eax
0x140011214  jnz     short loc_140011231
0x140011216  call    cs:__imp_GetLastError
0x14001121d  nop     dword ptr [rax+rax+00h]
0x140011222  mov     ebx, eax
0x140011224  test    eax, eax
0x140011226  jle     short loc_14001122D
0x140011228  movzx   ebx, ax
0x14001122b  or      ebx, edi
0x14001122d  test    ebx, ebx
0x14001122f  js      short loc_1400112A0
0x140011231  mov     [rsp+0E0h+cbData], 8; cbData
0x140011239  lea     rax, [rbp+57h+FileTime]
0x14001123d  mov     [rsp+0E0h+phkResult], rax; lpData
0x140011242  mov     r9d, 3; dwType
0x140011248  xor     r8d, r8d; Reserved
0x14001124b  lea     rdx, aSessionstateti; "SessionStateTimeStamp"
0x140011252  mov     rcx, [rbp+57h+hKey]; hKey
0x140011256  call    cs:__imp_RegSetValueExW
0x14001125d  nop     dword ptr [rax+rax+00h]
0x140011262  test    eax, eax
0x140011264  jnz     short loc_140011295
0x140011266  mov     [rsp+0E0h+cbData], r14d; cbData
0x14001126b  lea     rax, [rbp+57h+var_90]
0x14001126f  mov     [rsp+0E0h+phkResult], rax; lpData
0x140011274  mov     r9d, r14d; dwType
0x140011277  xor     r8d, r8d; Reserved
0x14001127a  lea     rdx, aSessionstate; "SessionState"
0x140011281  mov     rcx, [rbp+57h+hKey]; hKey
0x140011285  call    cs:__imp_RegSetValueExW
0x14001128c  nop     dword ptr [rax+rax+00h]
0x140011291  test    eax, eax
0x140011293  jz      short loc_1400112A0
0x140011295  jle     loc_140011175
0x14001129b  movzx   ebx, ax
0x14001129e  or      ebx, edi
0x1400112a0  lea     rcx, [rbp+57h+var_80]
0x1400112a4  call    cs:__imp_OmaDmFreeInitiationInfo
0x1400112ab  nop     dword ptr [rax+rax+00h]
0x1400112b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1400112b4  test    rcx, rcx
0x1400112b7  jz      short loc_1400112C5
0x1400112b9  call    cs:__imp_RegCloseKey
0x1400112c0  nop     dword ptr [rax+rax+00h]
0x1400112c5  mov     eax, ebx
0x1400112c7  mov     rcx, [rbp+57h+var_30]
0x1400112cb  xor     rcx, rsp; StackCookie
0x1400112ce  call    __security_check_cookie
0x1400112d3  mov     rbx, [rsp+0E0h+arg_10]
0x1400112db  add     rsp, 0C0h
0x1400112e2  pop     r15
0x1400112e4  pop     r14
0x1400112e6  pop     r13
0x1400112e8  pop     rdi
0x1400112e9  pop     rbp
0x1400112ea  retn
```
