# HrUpdateProfileInfo(wchar_t const *,ulong,...)

- ea: `0x180019274`
- end: `0x180019a3f`
- name: `?HrUpdateProfileInfo@@YAJPEB_WKZZ`
- size: `1995`
- prototype: `__int64(const wchar_t *, unsigned int, ...)`
- caller_count: `11`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180018c2c`
- `0x180072b30`
- `0x18009ddd4`
- `0x1800a6020`
- `0x1800c1258`
- `0x1800c6864`
- `0x1800d67ec`
- `0x1800e4bc0`
- `0x1800e4ee0`
- `0x1800e5350`
- `0x1800e55a0`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180014cc0`
- `0x180014fb0`
- `0x180015650`
- `0x180019274`
- `0x180055c20`
- `0x1800a88a0`
- `0x1800cce74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800199a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800199a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019352`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019409`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800194b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019562`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019622`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800196bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001975e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001989c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019937`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019352`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019409`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800194b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019562`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019622`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800196bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001975e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001989c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019937`

## string_xrefs

- `0x18001960a`: `DateCreated`

## pseudocode

```c
__int64 HrUpdateProfileInfo(const wchar_t *a1, __int16 a2, ...)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r14
  const BYTE **v6; // rdi
  const BYTE *v7; // rsi
  __int64 v8; // rax
  LSTATUS v9; // eax
  PVOID *v10; // rcx
  const BYTE *v11; // rsi
  LSTATUS v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  const BYTE *v19; // rax
  LSTATUS v20; // eax
  __int64 v21; // r9
  const BYTE *v22; // rax
  LSTATUS v23; // eax
  __int64 v24; // r9
  int v25; // eax
  int v26; // eax
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  __int64 v30; // r8
  int v31; // eax
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  PVOID *v36; // rcx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-10h] BYREF
  const BYTE *lpData; // [rsp+A0h] [rbp+50h] BYREF
  va_list va; // [rsp+A0h] [rbp+50h]
  va_list va1; // [rsp+A8h] [rbp+58h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  lpData = va_arg(va1, const BYTE *);
  hKey = 0;
  lpCriticalSection = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  lpCriticalSection = 0;
  NetworkPropertyMaps::LockProfileStore(&lpCriticalSection);
  v3 = HrOpenProfileKey(a1, 0x2001Fu, &hKey);
  v4 = v3;
  if ( !v3 )
  {
    v5 = -1;
    va_copy((va_list)v6, va);
    v4 = 0;
    if ( (a2 & 1) != 0 )
    {
      v7 = lpData;
      va_copy((va_list)v6, va1);
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&lpData[2 * v8] );
      v9 = RegSetValueExW(hKey, L"ProfileName", 0, 1u, lpData, 2 * v8 + 2);
      v4 = v9;
      if ( v9 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            (_DWORD)v7,
            v9);
          goto LABEL_15;
        }
      }
      else
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v7);
          goto LABEL_15;
        }
      }
LABEL_16:
      if ( (a2 & 2) == 0 )
        goto LABEL_27;
      v11 = *v6++;
      do
        ++v5;
      while ( *(_WORD *)&v11[2 * v5] );
      v12 = RegSetValueExW(hKey, L"Description", 0, 1u, v11, 2 * v5 + 2);
      v4 = v12;
      if ( v12 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            (_DWORD)v11,
            v12);
          goto LABEL_26;
        }
      }
      else
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v11);
LABEL_26:
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
LABEL_27:
      if ( (a2 & 4) != 0 )
      {
        v13 = *(_DWORD *)v6++;
        *(_DWORD *)Data = v13;
        v14 = RegSetValueExW(hKey, L"Managed", 0, 4u, Data, 4u);
        v4 = v14;
        if ( v14 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_38;
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v15, *(unsigned int *)Data, v14);
        }
        else
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_38;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            *(unsigned int *)Data);
        }
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_38:
      if ( (a2 & 8) != 0 )
      {
        v16 = *(_DWORD *)v6++;
        *(_DWORD *)Data = v16;
        if ( v16 == 2 )
        {
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
            WPP_SF_(v10[2], 43, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
        }
        else
        {
          v17 = RegSetValueExW(hKey, L"Category", 0, 4u, Data, 4u);
          v4 = v17;
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              if ( v17 > 0 )
                v17 = (unsigned __int16)v17 | 0x80070000;
              WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v18, *(unsigned int *)Data, v17);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              41,
              &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
              *(unsigned int *)Data);
          }
        }
      }
      if ( (a2 & 0x20) != 0 )
      {
        v19 = *v6++;
        v20 = RegSetValueExW(hKey, L"DateCreated", 0, 3u, v19, 0x10u);
        v4 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v20 > 0 )
              v21 = (unsigned __int16)v20 | 0x80070000;
            else
              v21 = (unsigned int)v20;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v21);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
        }
      }
      if ( (a2 & 0x40) != 0 )
      {
        v22 = *v6++;
        v23 = RegSetValueExW(hKey, L"DateLastConnected", 0, 3u, v22, 0x10u);
        v4 = v23;
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v23 > 0 )
              v24 = (unsigned __int16)v23 | 0x80070000;
            else
              v24 = (unsigned int)v23;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v24);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
        }
      }
      if ( (a2 & 0x80u) != 0 )
      {
        v25 = *(_DWORD *)v6++;
        *(_DWORD *)Data = v25;
        v26 = RegSetValueExW(hKey, L"NameType", 0, 4u, Data, 4u);
        v4 = v26;
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v27, *(unsigned int *)Data, v26);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            *(unsigned int *)Data);
        }
      }
      if ( (a2 & 0x100) != 0 )
      {
        v28 = *(_DWORD *)v6++;
        *(_DWORD *)Data = v28;
        v29 = RegSetValueExW(hKey, L"DescType", 0, 4u, Data, 4u);
        v4 = v29;
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v29 > 0 )
              v29 = (unsigned __int16)v29 | 0x80070000;
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v30, *(unsigned int *)Data, v29);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            *(unsigned int *)Data);
        }
      }
      if ( (a2 & 0x200) != 0 )
      {
        v31 = *(_DWORD *)v6++;
        *(_DWORD *)Data = v31;
        v32 = RegSetValueExW(hKey, L"CategoryType", 0, 4u, Data, 4u);
        v4 = v32;
        if ( v32 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v32 > 0 )
              v32 = (unsigned __int16)v32 | 0x80070000;
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v33, *(unsigned int *)Data, v32);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            *(unsigned int *)Data);
        }
      }
      if ( (a2 & 0x400) != 0 )
      {
        *(_DWORD *)Data = *(_DWORD *)v6;
        v34 = RegSetValueExW(hKey, L"IconType", 0, 4u, Data, 4u);
        v4 = v34;
        if ( v34 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v34 > 0 )
              v34 = (unsigned __int16)v34 | 0x80070000;
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v35, *(unsigned int *)Data, v34);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            *(unsigned int *)Data);
        }
      }
      RegCloseKey(hKey);
      if ( (int)v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_119;
    }
LABEL_15:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v36 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_123;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
      (_DWORD)a1,
      v3);
LABEL_119:
    v36 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 8) != 0 )
    WPP_SF_d(v36[2], 57, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v4);
LABEL_123:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180019274  mov     [rsp-38h+arg_8], edx
0x180019278  mov     [rsp-38h+arg_10], r8
0x18001927d  mov     [rsp-38h+arg_18], r9
0x180019282  push    rbp
0x180019283  push    rbx
0x180019284  push    rsi
0x180019285  push    rdi
0x180019286  push    r12
0x180019288  push    r13
0x18001928a  push    r14
0x18001928c  mov     rbp, rsp
0x18001928f  sub     rsp, 50h
0x180019293  mov     rax, cs:__security_cookie
0x18001929a  xor     rax, rsp
0x18001929d  mov     [rbp+var_8], rax
0x1800192a1  xor     r12d, r12d
0x1800192a4  mov     rdi, rcx
0x1800192a7  mov     [rbp+hKey], r12
0x1800192ab  mov     [rbp+lpCriticalSection], r12
0x1800192af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192b6  lea     r13, WPP_GLOBAL_Control
0x1800192bd  cmp     rcx, r13
0x1800192c0  jz      short loc_1800192DD
0x1800192c2  test    byte ptr [rcx+1Ch], 8
0x1800192c6  jz      short loc_1800192DD
0x1800192c8  mov     rcx, [rcx+10h]
0x1800192cc  lea     edx, [r12+22h]
0x1800192d1  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800192d8  call    WPP_SF_
0x1800192dd  lea     rcx, [rbp+lpCriticalSection]
0x1800192e1  mov     [rbp+lpCriticalSection], r12
0x1800192e5  call    ?LockProfileStore@NetworkPropertyMaps@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; NetworkPropertyMaps::LockProfileStore(void)
0x1800192ea  lea     r8, [rbp+hKey]; HKEY *
0x1800192ee  mov     edx, 2001Fh; unsigned int
0x1800192f3  mov     rcx, rdi; wchar_t *
0x1800192f6  call    ?HrOpenProfileKey@@YAJPEB_WKPEAPEAUHKEY__@@@Z; HrOpenProfileKey(wchar_t const *,ulong,HKEY__ * *)
0x1800192fb  mov     ebx, eax
0x1800192fd  test    eax, eax
0x1800192ff  jnz     loc_1800199BB
0x180019305  or      r14, 0FFFFFFFFFFFFFFFFh
0x180019309  lea     rdi, [rbp+arg_10]
0x18001930d  test    byte ptr [rbp+arg_8], 1
0x180019311  mov     ebx, r12d
0x180019314  jz      loc_1800193C2
0x18001931a  mov     rsi, [rdi]
0x18001931d  add     rdi, 8
0x180019321  mov     rax, r14
0x180019324  inc     rax
0x180019327  cmp     [rsi+rax*2], r12w
0x18001932c  jnz     short loc_180019324
0x18001932e  mov     rcx, [rbp+hKey]; hKey
0x180019332  lea     eax, ds:2[rax*2]
0x180019339  mov     [rsp+50h+cbData], eax; cbData
0x18001933d  lea     rdx, Value; "ProfileName"
0x180019344  mov     r9d, 1; dwType
0x18001934a  mov     [rsp+50h+lpData], rsi; lpData
0x18001934f  xor     r8d, r8d; Reserved
0x180019352  call    cs:__imp_RegSetValueExW
0x180019358  mov     ebx, eax
0x18001935a  test    eax, eax
0x18001935c  jnz     short loc_180019388
0x18001935e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019365  cmp     rcx, r13
0x180019368  jz      short loc_1800193C9
0x18001936a  test    byte ptr [rcx+1Ch], 4
0x18001936e  jz      short loc_1800193C9
0x180019370  mov     rcx, [rcx+10h]
0x180019374  lea     edx, [rax+23h]
0x180019377  mov     r9, rsi
0x18001937a  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x180019381  call    WPP_SF_S
0x180019386  jmp     short loc_1800193C2
0x180019388  mov     rcx, cs:WPP_GLOBAL_Control
0x18001938f  cmp     rcx, r13
0x180019392  jz      short loc_1800193C9
0x180019394  test    byte ptr [rcx+1Ch], 1
0x180019398  jz      short loc_1800193C9
0x18001939a  test    eax, eax
0x18001939c  jle     short loc_1800193A6
0x18001939e  movzx   eax, ax
0x1800193a1  or      eax, 80070000h
0x1800193a6  mov     rcx, [rcx+10h]
0x1800193aa  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800193b1  mov     edx, 24h ; '$'
0x1800193b6  mov     dword ptr [rsp+50h+lpData], eax
0x1800193ba  mov     r9, rsi
0x1800193bd  call    WPP_SF_Sd
0x1800193c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193c9  test    byte ptr [rbp+arg_8], 2
0x1800193cd  jz      loc_180019480
0x1800193d3  mov     rsi, [rdi]
0x1800193d6  add     rdi, 8
0x1800193da  inc     r14
0x1800193dd  cmp     [rsi+r14*2], r12w
0x1800193e2  jnz     short loc_1800193DA
0x1800193e4  mov     rcx, [rbp+hKey]; hKey
0x1800193e8  lea     eax, ds:2[r14*2]
0x1800193f0  mov     [rsp+50h+cbData], eax; cbData
0x1800193f4  lea     rdx, aDescription; "Description"
0x1800193fb  mov     r9d, 1; dwType
0x180019401  mov     [rsp+50h+lpData], rsi; lpData
0x180019406  xor     r8d, r8d; Reserved
0x180019409  call    cs:__imp_RegSetValueExW
0x18001940f  mov     ebx, eax
0x180019411  test    eax, eax
0x180019413  jnz     short loc_18001943F
0x180019415  mov     rcx, cs:WPP_GLOBAL_Control
0x18001941c  cmp     rcx, r13
0x18001941f  jz      short loc_180019480
0x180019421  test    byte ptr [rcx+1Ch], 4
0x180019425  jz      short loc_180019480
0x180019427  mov     rcx, [rcx+10h]
0x18001942b  lea     edx, [rax+25h]
0x18001942e  mov     r9, rsi
0x180019431  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x180019438  call    WPP_SF_S
0x18001943d  jmp     short loc_180019479
0x18001943f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019446  cmp     rcx, r13
0x180019449  jz      short loc_180019480
0x18001944b  test    byte ptr [rcx+1Ch], 1
0x18001944f  jz      short loc_180019480
0x180019451  test    eax, eax
0x180019453  jle     short loc_18001945D
0x180019455  movzx   eax, ax
0x180019458  or      eax, 80070000h
0x18001945d  mov     rcx, [rcx+10h]
0x180019461  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x180019468  mov     edx, 26h ; '&'
0x18001946d  mov     dword ptr [rsp+50h+lpData], eax
0x180019471  mov     r9, rsi
0x180019474  call    WPP_SF_Sd
0x180019479  mov     rcx, cs:WPP_GLOBAL_Control
0x180019480  mov     esi, 4
0x180019485  test    byte ptr [rbp+arg_8], sil
0x180019489  jz      loc_180019528
0x18001948f  mov     eax, [rdi]
0x180019491  lea     rdx, aManaged; "Managed"
0x180019498  mov     rcx, [rbp+hKey]; hKey
0x18001949c  add     rdi, 8
0x1800194a0  mov     dword ptr [rbp+Data], eax
0x1800194a3  mov     r9d, esi; dwType
0x1800194a6  lea     rax, [rbp+Data]
0x1800194aa  mov     [rsp+50h+cbData], esi; cbData
0x1800194ae  xor     r8d, r8d; Reserved
0x1800194b1  mov     [rsp+50h+lpData], rax; lpData
0x1800194b6  call    cs:__imp_RegSetValueExW
0x1800194bc  mov     ebx, eax
0x1800194be  test    eax, eax
0x1800194c0  jnz     short loc_1800194ED
0x1800194c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194c9  cmp     rcx, r13
0x1800194cc  jz      short loc_180019528
0x1800194ce  test    [rcx+1Ch], sil
0x1800194d2  jz      short loc_180019528
0x1800194d4  mov     r9d, dword ptr [rbp+Data]
0x1800194d8  lea     edx, [rsi+23h]
0x1800194db  mov     rcx, [rcx+10h]
0x1800194df  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800194e6  call    WPP_SF_d
0x1800194eb  jmp     short loc_180019521
0x1800194ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194f4  cmp     rcx, r13
0x1800194f7  jz      short loc_180019528
0x1800194f9  test    byte ptr [rcx+1Ch], 1
0x1800194fd  jz      short loc_180019528
0x1800194ff  test    eax, eax
0x180019501  jle     short loc_18001950B
0x180019503  movzx   eax, ax
0x180019506  or      eax, 80070000h
0x18001950b  mov     r9d, dword ptr [rbp+Data]
0x18001950f  mov     edx, 28h ; '('
0x180019514  mov     rcx, [rcx+10h]
0x180019518  mov     dword ptr [rsp+50h+lpData], eax
0x18001951c  call    WPP_SF_dD
0x180019521  mov     rcx, cs:WPP_GLOBAL_Control
0x180019528  test    byte ptr [rbp+arg_8], 8
0x18001952c  jz      loc_1800195EF
0x180019532  mov     eax, [rdi]
0x180019534  add     rdi, 8
0x180019538  mov     dword ptr [rbp+Data], eax
0x18001953b  cmp     eax, 2
0x18001953e  jz      loc_1800195CF
0x180019544  mov     rcx, [rbp+hKey]; hKey
0x180019548  lea     rax, [rbp+Data]
0x18001954c  mov     [rsp+50h+cbData], esi; cbData
0x180019550  lea     rdx, aCategory; "Category"
0x180019557  mov     r9d, esi; dwType
0x18001955a  mov     [rsp+50h+lpData], rax; lpData
0x18001955f  xor     r8d, r8d; Reserved
0x180019562  call    cs:__imp_RegSetValueExW
0x180019568  mov     ebx, eax
0x18001956a  test    eax, eax
0x18001956c  jnz     short loc_180019599
0x18001956e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019575  cmp     rcx, r13
0x180019578  jz      short loc_1800195EF
0x18001957a  test    [rcx+1Ch], sil
0x18001957e  jz      short loc_1800195EF
0x180019580  mov     r9d, dword ptr [rbp+Data]
0x180019584  lea     edx, [rax+29h]
0x180019587  mov     rcx, [rcx+10h]
0x18001958b  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x180019592  call    WPP_SF_d
0x180019597  jmp     short loc_1800195EF
0x180019599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195a0  cmp     rcx, r13
0x1800195a3  jz      short loc_1800195EF
0x1800195a5  test    byte ptr [rcx+1Ch], 1
0x1800195a9  jz      short loc_1800195EF
0x1800195ab  test    eax, eax
0x1800195ad  jle     short loc_1800195B7
0x1800195af  movzx   eax, ax
0x1800195b2  or      eax, 80070000h
0x1800195b7  mov     r9d, dword ptr [rbp+Data]
0x1800195bb  mov     edx, 2Ah ; '*'
0x1800195c0  mov     rcx, [rcx+10h]
0x1800195c4  mov     dword ptr [rsp+50h+lpData], eax
0x1800195c8  call    WPP_SF_dD
0x1800195cd  jmp     short loc_1800195EF
0x1800195cf  cmp     rcx, r13
0x1800195d2  jz      short loc_1800195EF
0x1800195d4  test    byte ptr [rcx+1Ch], 2
0x1800195d8  jz      short loc_1800195EF
0x1800195da  mov     rcx, [rcx+10h]
0x1800195de  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800195e5  mov     edx, 2Bh ; '+'
0x1800195ea  call    WPP_SF_
0x1800195ef  test    byte ptr [rbp+arg_8], 20h
0x1800195f3  mov     r14d, 10h
0x1800195f9  jz      loc_180019690
0x1800195ff  mov     rax, [rdi]
0x180019602  lea     r9d, [r14-0Dh]; dwType
0x180019606  mov     rcx, [rbp+hKey]; hKey
0x18001960a  lea     rdx, ValueName; "DateCreated"
0x180019611  add     rdi, 8
0x180019615  mov     [rsp+50h+cbData], r14d; cbData
0x18001961a  xor     r8d, r8d; Reserved
0x18001961d  mov     [rsp+50h+lpData], rax; lpData
0x180019622  call    cs:__imp_RegSetValueExW
0x180019628  mov     ebx, eax
0x18001962a  test    eax, eax
0x18001962c  jnz     short loc_180019655
0x18001962e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019635  cmp     rcx, r13
0x180019638  jz      short loc_180019690
0x18001963a  test    [rcx+1Ch], sil
0x18001963e  jz      short loc_180019690
0x180019640  mov     rcx, [rcx+10h]
0x180019644  lea     edx, [rax+2Ch]
0x180019647  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18001964e  call    WPP_SF_
0x180019653  jmp     short loc_180019690
0x180019655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001965c  cmp     rcx, r13
0x18001965f  jz      short loc_180019690
0x180019661  test    byte ptr [rcx+1Ch], 1
0x180019665  jz      short loc_180019690
0x180019667  test    eax, eax
0x180019669  jg      short loc_180019670
0x18001966b  mov     r9d, eax
0x18001966e  jmp     short loc_18001967B
0x180019670  movzx   r9d, ax
0x180019674  or      r9d, 80070000h
0x18001967b  mov     rcx, [rcx+10h]
0x18001967f  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x180019686  mov     edx, 2Dh ; '-'
0x18001968b  call    WPP_SF_d
0x180019690  test    byte ptr [rbp+arg_8], 40h
0x180019694  jz      loc_18001972D
0x18001969a  mov     rax, [rdi]
0x18001969d  lea     rdx, aDatelastconnec; "DateLastConnected"
0x1800196a4  mov     rcx, [rbp+hKey]; hKey
0x1800196a8  add     rdi, 8
0x1800196ac  mov     [rsp+50h+cbData], r14d; cbData
0x1800196b1  mov     r9d, 3; dwType
0x1800196b7  xor     r8d, r8d; Reserved
0x1800196ba  mov     [rsp+50h+lpData], rax; lpData
0x1800196bf  call    cs:__imp_RegSetValueExW
0x1800196c5  mov     ebx, eax
0x1800196c7  test    eax, eax
0x1800196c9  jnz     short loc_1800196F2
0x1800196cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196d2  cmp     rcx, r13
0x1800196d5  jz      short loc_18001972D
0x1800196d7  test    [rcx+1Ch], sil
0x1800196db  jz      short loc_18001972D
0x1800196dd  mov     rcx, [rcx+10h]
0x1800196e1  lea     edx, [rax+2Eh]
0x1800196e4  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800196eb  call    WPP_SF_
0x1800196f0  jmp     short loc_18001972D
0x1800196f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196f9  cmp     rcx, r13
0x1800196fc  jz      short loc_18001972D
0x1800196fe  test    byte ptr [rcx+1Ch], 1
0x180019702  jz      short loc_18001972D
0x180019704  test    eax, eax
0x180019706  jg      short loc_18001970D
0x180019708  mov     r9d, eax
  ... truncated ...
```
