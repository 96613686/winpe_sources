# FAX_SetReceiptsConfiguration

- ea: `0x140020890`
- end: `0x140020d87`
- name: `FAX_SetReceiptsConfiguration`
- size: `1271`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14000c5ac`
- `0x140014c24`
- `0x140020890`
- `0x14002ce80`
- `0x1400452ac`
- `0x14005549c`
- `0x140065dbc`
- `0x1400708c4`
- `0x140070a64`
- `0x1400755e0`
- `0x14007d2d0`
- `0x14007f654`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140020ce1`
- `ADVAPI32!RegCloseKey` at `0x140020ce1`
- `KERNEL32!GetLastError` at `0x140020ad2`
- `KERNEL32!GetLastError` at `0x140020b8d`
- `KERNEL32!GetLastError` at `0x140020c64`
- `KERNEL32!GetLastError` at `0x140020ad2`
- `KERNEL32!GetLastError` at `0x140020b8d`
- `KERNEL32!GetLastError` at `0x140020c64`
- `KERNEL32!CloseHandle` at `0x140020c3b`
- `KERNEL32!CloseHandle` at `0x140020c3b`
- `KERNEL32!EnterCriticalSection` at `0x140020a93`
- `KERNEL32!EnterCriticalSection` at `0x140020a93`
- `KERNEL32!LeaveCriticalSection` at `0x140020d5f`
- `KERNEL32!LeaveCriticalSection` at `0x140020d5f`

## pseudocode

```c
__int64 __fastcall FAX_SetReceiptsConfiguration(void *a1, __int64 a2)
{
  CMapDeviceId *v4; // rcx
  int v5; // ebx
  int Win32StructSize; // eax
  unsigned int v7; // ebx
  int v8; // ebp
  unsigned int ClientAPIVersion; // eax
  int v10; // ecx
  int *v11; // rsi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  int v15; // ebp
  int v16; // r14d
  HKEY v17; // rax
  HKEY v18; // r15
  DWORD v19; // eax
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  PCWSTR v22; // rax
  __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  __int64 v25; // r10
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // r10
  int v30; // edx
  int v31; // eax
  DWORD LastError; // eax
  int ConfigEvent; // eax
  _BYTE *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // [rsp+88h] [rbp+10h] BYREF

  v37 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 != 72 )
  {
    Win32StructSize = GetWin32StructSize(&fax_receipts_config_fields);
    v4 = WPP_GLOBAL_Control;
    if ( Win32StructSize != v5 )
      goto LABEL_23;
  }
  if ( (*(_DWORD *)(a2 + 4) & 0xFFFFFFFA) != 0 )
    goto LABEL_23;
  if ( (*(_BYTE *)(a2 + 4) & 4) != 0 )
  {
    v7 = 1630;
LABEL_24:
    if ( v4 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v4 + 2), 276, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v7);
    return v7;
  }
  v8 = 0;
  ClientAPIVersion = FindClientAPIVersion(a1);
  v10 = *(_DWORD *)(a2 + 4);
  v11 = (int *)(a2 + 64);
  v12 = ClientAPIVersion;
  if ( (v10 & 1) == 0 && !*v11 )
  {
LABEL_16:
    if ( (v10 & 1) != 0 )
      goto LABEL_19;
    goto LABEL_17;
  }
  if ( !(unsigned int)AreReceiptsEnabled() )
  {
    v4 = WPP_GLOBAL_Control;
    v7 = v12 < 0x10000 ? 87 : 7011;
    goto LABEL_24;
  }
  v10 = *(_DWORD *)(a2 + 4);
  if ( (v10 & 1) != 0 )
  {
    v8 = 1;
    goto LABEL_16;
  }
LABEL_17:
  if ( !*v11 && *(_QWORD *)(a2 + 56) )
  {
LABEL_22:
    v4 = WPP_GLOBAL_Control;
LABEL_23:
    v7 = 87;
    goto LABEL_24;
  }
LABEL_19:
  if ( (v8 || *v11) && *(_DWORD *)(a2 + 8) > 2u )
    goto LABEL_22;
  v13 = FaxSvcAccessCheck(0x40u, &v37, 0, 1);
  v7 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v13);
    }
LABEL_97:
    if ( v7 == 8 || v7 == 14 )
      return 7001;
    return v7;
  }
  if ( v37 )
  {
    v15 = *(_DWORD *)(a2 + 4) & 1;
    EnterCriticalSection(&g_CsConfig);
    if ( *(_DWORD *)(a2 + 8) != 2 || (v16 = 0, !v15) && !*v11 )
      v16 = 1;
    v17 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Receipts", 0, 0x2001Fu);
    v18 = v17;
    if ( v17 )
    {
      lpMem = (LPVOID)GetRegistrySecureString(v17, 0);
      v7 = StoreReceiptsSettings(a2);
      if ( v7 )
      {
        v7 = 1015;
      }
      else
      {
        dword_1400A1644 = *(_DWORD *)(a2 + 4);
        dword_1400A1680 = *v11;
        if ( !v15 && !*v11 )
          goto LABEL_71;
        *(_DWORD *)&dword_1400A1660 = *(_DWORD *)(a2 + 32);
        dword_1400A1648 = *(_DWORD *)(a2 + 8);
        if ( !ReplaceStringWithCopy(&qword_1400A1658, *(const unsigned __int16 **)(a2 + 24))
          || !ReplaceStringWithCopy(&qword_1400A1668, *(const unsigned __int16 **)(a2 + 40)) )
        {
          goto LABEL_54;
        }
        v22 = UserName;
        if ( !UserName )
          goto LABEL_68;
        v23 = *(_QWORD *)(a2 + 48);
        if ( !v23 )
          goto LABEL_68;
        v24 = (unsigned __int16 *)lpMem;
        if ( !lpMem )
          goto LABEL_68;
        v25 = *(_QWORD *)(a2 + 56);
        if ( !v25 )
          goto LABEL_68;
        v26 = v23 - (_QWORD)UserName;
        do
        {
          v27 = *(PCWSTR)((char *)v22 + v26);
          v28 = *v22 - v27;
          if ( v28 )
            break;
          ++v22;
        }
        while ( v27 );
        if ( v28 )
          goto LABEL_68;
        v29 = v25 - (_QWORD)lpMem;
        do
        {
          v30 = *(unsigned __int16 *)((char *)v24 + v29);
          v31 = *v24 - v30;
          if ( v31 )
            break;
          ++v24;
        }
        while ( v30 );
        if ( v31 )
LABEL_68:
          v16 = 1;
        if ( ReplaceStringWithCopy((unsigned __int16 **)&UserName, *(const unsigned __int16 **)(a2 + 48)) )
        {
LABEL_71:
          if ( hObject && v16 == 1 )
          {
            if ( !CloseHandle(hObject)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                280,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                LastError);
            }
            hObject = 0;
          }
          ConfigEvent = CreateConfigEvent(0);
          if ( ConfigEvent
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_h(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              281,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned __int16)ConfigEvent);
          }
        }
        else
        {
LABEL_54:
          v7 = GetLastError();
        }
      }
      v19 = RegCloseKey(v18);
      if ( !v19 )
        goto LABEL_89;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v21 = 282;
    }
    else
    {
      v19 = GetLastError();
      v7 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v21 = 279;
    }
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v19);
LABEL_89:
    v34 = lpMem;
    if ( lpMem )
    {
      v35 = -1;
      do
        ++v35;
      while ( *((_WORD *)lpMem + v35) );
      v36 = 2 * v35;
      if ( v36 )
      {
        do
        {
          *v34++ = 0;
          --v36;
        }
        while ( v36 );
        v34 = lpMem;
      }
      pMemFree(v34);
      lpMem = 0;
    }
    LeaveCriticalSection(&g_CsConfig);
    goto LABEL_97;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x140020890  mov     rax, rsp
0x140020893  push    rbx
0x140020894  push    rbp
0x140020895  push    rsi
0x140020896  push    rdi
0x140020897  push    r12
0x140020899  push    r13
0x14002089b  push    r14
0x14002089d  push    r15
0x14002089f  sub     rsp, 38h
0x1400208a3  xor     r12d, r12d
0x1400208a6  mov     rdi, rdx
0x1400208a9  mov     [rax+10h], r12d
0x1400208ad  mov     rsi, rcx
0x1400208b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400208b7  lea     r15, WPP_GLOBAL_Control
0x1400208be  mov     r14b, 4
0x1400208c1  cmp     rcx, r15
0x1400208c4  jz      short loc_1400208EE
0x1400208c6  test    [rcx+1Ch], r14b
0x1400208ca  jz      short loc_1400208EE
0x1400208cc  cmp     byte ptr [rcx+19h], 5
0x1400208d0  jb      short loc_1400208EE
0x1400208d2  mov     rcx, [rcx+10h]
0x1400208d6  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400208dd  mov     edx, 113h
0x1400208e2  call    WPP_SF_
0x1400208e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400208ee  mov     ebx, [rdi]
0x1400208f0  cmp     ebx, 48h ; 'H'
0x1400208f3  jz      short loc_140020910
0x1400208f5  lea     rcx, ?fax_receipts_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_receipts_config_fields
0x1400208fc  call    GetWin32StructSize
0x140020901  mov     rcx, cs:WPP_GLOBAL_Control
0x140020908  cmp     eax, ebx
0x14002090a  jnz     loc_1400209A8
0x140020910  test    dword ptr [rdi+4], 0FFFFFFFAh
0x140020917  jnz     loc_1400209A8
0x14002091d  test    [rdi+4], r14b
0x140020921  jz      short loc_14002092D
0x140020923  mov     ebx, 65Eh
0x140020928  jmp     loc_1400209AD
0x14002092d  mov     rcx, rsi; void *
0x140020930  mov     ebp, r12d
0x140020933  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x140020938  mov     ecx, [rdi+4]
0x14002093b  lea     rsi, [rdi+40h]
0x14002093f  mov     r13d, 1
0x140020945  mov     ebx, eax
0x140020947  test    r13b, cl
0x14002094a  jnz     short loc_140020951
0x14002094c  cmp     [rsi], r12d
0x14002094f  jz      short loc_140020982
0x140020951  call    AreReceiptsEnabled
0x140020956  test    eax, eax
0x140020958  jnz     short loc_140020977
0x14002095a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020961  cmp     ebx, 10000h
0x140020967  sbb     ebx, ebx
0x140020969  and     ebx, 0FFFFE4F4h
0x14002096f  add     ebx, 1B63h
0x140020975  jmp     short loc_1400209AD
0x140020977  mov     ecx, [rdi+4]
0x14002097a  test    r13b, cl
0x14002097d  jz      short loc_140020987
0x14002097f  mov     ebp, r13d
0x140020982  test    r13b, cl
0x140020985  jnz     short loc_140020992
0x140020987  cmp     [rsi], r12d
0x14002098a  jnz     short loc_140020992
0x14002098c  cmp     [rdi+38h], r12
0x140020990  jnz     short loc_1400209A1
0x140020992  test    ebp, ebp
0x140020994  jnz     short loc_14002099B
0x140020996  cmp     [rsi], r12d
0x140020999  jz      short loc_1400209E7
0x14002099b  cmp     dword ptr [rdi+8], 2
0x14002099f  jbe     short loc_1400209E7
0x1400209a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400209a8  mov     ebx, 57h ; 'W'
0x1400209ad  cmp     rcx, r15
0x1400209b0  jz      loc_140020D74
0x1400209b6  test    [rcx+1Ch], r14b
0x1400209ba  jz      loc_140020D74
0x1400209c0  cmp     byte ptr [rcx+19h], 2
0x1400209c4  jb      loc_140020D74
0x1400209ca  mov     rcx, [rcx+10h]
0x1400209ce  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400209d5  mov     edx, 114h
0x1400209da  mov     r9d, ebx
0x1400209dd  call    WPP_SF_d
0x1400209e2  jmp     loc_140020D74
0x1400209e7  xor     r8d, r8d; unsigned int *
0x1400209ea  lea     rdx, [rsp+78h+arg_8]; int *
0x1400209f2  mov     r9d, r13d; int
0x1400209f5  lea     ecx, [r8+40h]; unsigned int
0x1400209f9  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x1400209fe  mov     ebx, eax
0x140020a00  test    eax, eax
0x140020a02  jz      short loc_140020A45
0x140020a04  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a0b  cmp     rcx, r15
0x140020a0e  jz      loc_140020D65
0x140020a14  test    [rcx+1Ch], r14b
0x140020a18  jz      loc_140020D65
0x140020a1e  cmp     byte ptr [rcx+19h], 2
0x140020a22  jb      loc_140020D65
0x140020a28  mov     rcx, [rcx+10h]
0x140020a2c  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020a33  mov     edx, 115h
0x140020a38  mov     r9d, eax
0x140020a3b  call    WPP_SF_d
0x140020a40  jmp     loc_140020D65
0x140020a45  cmp     [rsp+78h+arg_8], r12d
0x140020a4d  jnz     short loc_140020A86
0x140020a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a56  cmp     rcx, r15
0x140020a59  jz      short loc_140020A7C
0x140020a5b  test    [rcx+1Ch], r14b
0x140020a5f  jz      short loc_140020A7C
0x140020a61  cmp     byte ptr [rcx+19h], 2
0x140020a65  jb      short loc_140020A7C
0x140020a67  mov     rcx, [rcx+10h]
0x140020a6b  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020a72  mov     edx, 116h
0x140020a77  call    WPP_SF_
0x140020a7c  mov     eax, 5
0x140020a81  jmp     loc_140020D76
0x140020a86  mov     ebp, [rdi+4]
0x140020a89  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020a90  and     ebp, r13d
0x140020a93  call    cs:__imp_EnterCriticalSection
0x140020a99  cmp     dword ptr [rdi+8], 2
0x140020a9d  jnz     short loc_140020AAB
0x140020a9f  mov     r14d, r12d
0x140020aa2  test    ebp, ebp
0x140020aa4  jnz     short loc_140020AAE
0x140020aa6  cmp     [rsi], r12d
0x140020aa9  jnz     short loc_140020AAE
0x140020aab  mov     r14d, r13d
0x140020aae  mov     r9d, 2001Fh
0x140020ab4  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x140020abb  xor     r8d, r8d
0x140020abe  mov     rcx, 0FFFFFFFF80000002h
0x140020ac5  call    OpenRegistryKey
0x140020aca  mov     r15, rax
0x140020acd  test    rax, rax
0x140020ad0  jnz     short loc_140020B0F
0x140020ad2  call    cs:__imp_GetLastError
0x140020ad8  mov     ebx, eax
0x140020ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ae1  lea     rdi, WPP_GLOBAL_Control
0x140020ae8  cmp     rcx, rdi
0x140020aeb  jz      loc_140020D1B
0x140020af1  test    byte ptr [rcx+1Ch], 4
0x140020af5  jz      loc_140020D1B
0x140020afb  cmp     byte ptr [rcx+19h], 2
0x140020aff  jb      loc_140020D1B
0x140020b05  mov     edx, 117h
0x140020b0a  jmp     loc_140020D08
0x140020b0f  lea     r8, Class
0x140020b16  mov     [rsp+78h+var_58], r12; __int64
0x140020b1b  mov     rcx, r15; hKey
0x140020b1e  call    GetRegistrySecureString
0x140020b23  mov     rcx, rdi
0x140020b26  mov     cs:lpMem, rax
0x140020b2d  call    StoreReceiptsSettings
0x140020b32  mov     ebx, eax
0x140020b34  test    eax, eax
0x140020b36  jz      short loc_140020B49
0x140020b38  mov     ebx, 3F7h
0x140020b3d  lea     rdi, WPP_GLOBAL_Control
0x140020b44  jmp     loc_140020CDE
0x140020b49  mov     eax, [rdi+4]
0x140020b4c  mov     cs:dword_1400A1644, eax
0x140020b52  mov     eax, [rsi]
0x140020b54  mov     cs:dword_1400A1680, eax
0x140020b5a  test    ebp, ebp
0x140020b5c  jnz     short loc_140020B67
0x140020b5e  cmp     [rsi], r12d
0x140020b61  jz      loc_140020C2A
0x140020b67  mov     eax, [rdi+20h]
0x140020b6a  lea     rcx, qword_1400A1658; unsigned __int16 **
0x140020b71  mov     cs:dword_1400A1660, eax
0x140020b77  mov     eax, [rdi+8]
0x140020b7a  mov     cs:dword_1400A1648, eax
0x140020b80  mov     rdx, [rdi+18h]; unsigned __int16 *
0x140020b84  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140020b89  test    eax, eax
0x140020b8b  jnz     short loc_140020B97
0x140020b8d  call    cs:__imp_GetLastError
0x140020b93  mov     ebx, eax
0x140020b95  jmp     short loc_140020B3D
0x140020b97  mov     rdx, [rdi+28h]; unsigned __int16 *
0x140020b9b  lea     rcx, qword_1400A1668; unsigned __int16 **
0x140020ba2  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140020ba7  test    eax, eax
0x140020ba9  jz      short loc_140020B8D
0x140020bab  mov     rax, cs:UserName
0x140020bb2  test    rax, rax
0x140020bb5  jz      short loc_140020C0F
0x140020bb7  mov     rdx, [rdi+30h]
0x140020bbb  test    rdx, rdx
0x140020bbe  jz      short loc_140020C0F
0x140020bc0  mov     rcx, cs:lpMem
0x140020bc7  test    rcx, rcx
0x140020bca  jz      short loc_140020C0F
0x140020bcc  mov     r10, [rdi+38h]
0x140020bd0  test    r10, r10
0x140020bd3  jz      short loc_140020C0F
0x140020bd5  sub     rdx, rax
0x140020bd8  movzx   r9d, word ptr [rax]
0x140020bdc  movzx   r8d, word ptr [rax+rdx]
0x140020be1  sub     r9d, r8d
0x140020be4  jnz     short loc_140020BEF
0x140020be6  add     rax, 2
0x140020bea  test    r8d, r8d
0x140020bed  jnz     short loc_140020BD8
0x140020bef  test    r9d, r9d
0x140020bf2  jnz     short loc_140020C0F
0x140020bf4  sub     r10, rcx
0x140020bf7  movzx   eax, word ptr [rcx]
0x140020bfa  movzx   edx, word ptr [rcx+r10]
0x140020bff  sub     eax, edx
0x140020c01  jnz     short loc_140020C0B
0x140020c03  add     rcx, 2
0x140020c07  test    edx, edx
0x140020c09  jnz     short loc_140020BF7
0x140020c0b  test    eax, eax
0x140020c0d  jz      short loc_140020C12
0x140020c0f  mov     r14d, r13d
0x140020c12  mov     rdx, [rdi+30h]; unsigned __int16 *
0x140020c16  lea     rcx, UserName; unsigned __int16 **
0x140020c1d  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140020c22  test    eax, eax
0x140020c24  jz      loc_140020B8D
0x140020c2a  mov     rcx, cs:hObject; hObject
0x140020c31  test    rcx, rcx
0x140020c34  jz      short loc_140020C9B
0x140020c36  cmp     r14d, r13d
0x140020c39  jnz     short loc_140020C9B
0x140020c3b  call    cs:__imp_CloseHandle
0x140020c41  test    eax, eax
0x140020c43  jnz     short loc_140020C8B
0x140020c45  mov     rax, cs:WPP_GLOBAL_Control
0x140020c4c  lea     rdi, WPP_GLOBAL_Control
0x140020c53  cmp     rax, rdi
0x140020c56  jz      short loc_140020C92
0x140020c58  test    byte ptr [rax+1Ch], 4
0x140020c5c  jz      short loc_140020C92
0x140020c5e  cmp     byte ptr [rax+19h], 2
0x140020c62  jb      short loc_140020C92
0x140020c64  call    cs:__imp_GetLastError
0x140020c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c71  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020c78  mov     edx, 118h
0x140020c7d  mov     r9d, eax
0x140020c80  mov     rcx, [rcx+10h]
0x140020c84  call    WPP_SF_d
0x140020c89  jmp     short loc_140020C92
0x140020c8b  lea     rdi, WPP_GLOBAL_Control
0x140020c92  mov     cs:hObject, r12
0x140020c99  jmp     short loc_140020CA2
0x140020c9b  lea     rdi, WPP_GLOBAL_Control
0x140020ca2  xor     ecx, ecx
0x140020ca4  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x140020ca9  test    eax, eax
0x140020cab  jz      short loc_140020CDE
0x140020cad  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cb4  cmp     rcx, rdi
0x140020cb7  jz      short loc_140020CDE
0x140020cb9  test    byte ptr [rcx+1Ch], 4
0x140020cbd  jz      short loc_140020CDE
0x140020cbf  cmp     byte ptr [rcx+19h], 2
0x140020cc3  jb      short loc_140020CDE
0x140020cc5  mov     rcx, [rcx+10h]
0x140020cc9  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020cd0  movzx   r9d, ax
0x140020cd4  mov     edx, 119h
0x140020cd9  call    WPP_SF_h
0x140020cde  mov     rcx, r15; hKey
0x140020ce1  call    cs:__imp_RegCloseKey
0x140020ce7  test    eax, eax
0x140020ce9  jz      short loc_140020D1B
0x140020ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cf2  cmp     rcx, rdi
0x140020cf5  jz      short loc_140020D1B
0x140020cf7  test    byte ptr [rcx+1Ch], 4
0x140020cfb  jz      short loc_140020D1B
0x140020cfd  cmp     byte ptr [rcx+19h], 2
0x140020d01  jb      short loc_140020D1B
0x140020d03  mov     edx, 11Ah
0x140020d08  mov     rcx, [rcx+10h]
0x140020d0c  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140020d13  mov     r9d, eax
0x140020d16  call    WPP_SF_d
0x140020d1b  mov     rcx, cs:lpMem
0x140020d22  test    rcx, rcx
0x140020d25  jz      short loc_140020D58
0x140020d27  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
