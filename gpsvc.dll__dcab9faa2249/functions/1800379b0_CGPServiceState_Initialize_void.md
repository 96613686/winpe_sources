# CGPServiceState::Initialize(void)

- ea: `0x1800379b0`
- end: `0x1800382c4`
- name: `?Initialize@CGPServiceState@@SAKXZ`
- size: `2324`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036340`

## callees

- `0x180009a90`
- `0x18001dcf0`
- `0x18002c478`
- `0x1800379b0`
- `0x1800382cc`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d6f0`
- `0x18007d770`
- `0x18007d794`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800379f7`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180037cfe`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800379f7`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180037cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037ea1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037ea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037f13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037f13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800381e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800381f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800381e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800381f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003814e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003814e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037c02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037feb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038104`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800381d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037c02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037feb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038104`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800381d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180037f6d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180037f6d`
- `ntdll!EtwEventWrite` at `0x180037b42`
- `ntdll!EtwEventWrite` at `0x180038056`
- `ntdll!EtwEventWrite` at `0x180037b42`
- `ntdll!EtwEventWrite` at `0x180038056`

## string_xrefs

- `0x180037bcf`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\ServiceInstances`
- `0x180037fb8`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\ServiceInstances`
- `0x1800380cc`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\ServiceInstances`

## pseudocode

```c
__int64 CGPServiceState::Initialize(void)
{
  __int64 v0; // rax
  const wchar_t *v1; // rdx
  __int64 v2; // r8
  _WORD *v3; // r9
  _WORD *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // r10d
  _WORD *v8; // r9
  wchar_t *v9; // r8
  __int64 v10; // rax
  bool v11; // zf
  _QWORD *v12; // rax
  unsigned __int16 **v13; // r14
  LSTATUS StringGuid; // edi
  CGuid *v15; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // rdx
  __int64 v19; // r8
  _WORD *v20; // r9
  _WORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // r11d
  _WORD *v25; // r9
  wchar_t *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rcx
  _WORD *v29; // rax
  _WORD *v30; // r8
  __int64 v31; // rcx
  WCHAR *v32; // rdx
  unsigned __int64 v33; // rbx
  LSTATUS v34; // eax
  __int64 v35; // rax
  unsigned int v36; // r13d
  __int64 v37; // rsi
  unsigned __int64 v38; // rax
  DWORD v39; // ecx
  DWORD i; // r12d
  _QWORD *v41; // rsi
  unsigned __int64 v42; // rax
  const WCHAR *v43; // rdx
  DWORD v44; // ebx
  HKEY v45; // rax
  __int64 v46; // rcx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwDisposition[2]; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v52; // [rsp+80h] [rbp-80h]
  _WORD *v53; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h]
  int v55; // [rsp+94h] [rbp-6Ch]
  WCHAR *v56; // [rsp+98h] [rbp-68h]
  DWORD v57; // [rsp+A0h] [rbp-60h]
  int v58; // [rsp+A4h] [rbp-5Ch]
  _WORD v59[13]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v60[6]; // [rsp+D2h] [rbp-2Eh] BYREF
  wchar_t Buffer[20]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR Name[40]; // [rsp+100h] [rbp+0h] BYREF

  if ( CGPServiceState::m_CurrentState )
    return 0;
  _itow(4166, Buffer, 10);
  v0 = 2147483646;
  v1 = L"%%";
  v2 = 13;
  v3 = v59;
  while ( v0 && *v1 )
  {
    *v3++ = *v1++;
    --v0;
    if ( !--v2 )
    {
      *(v3 - 1) = 0;
      goto LABEL_21;
    }
  }
  v4 = v59;
  *v3 = 0;
  v5 = 13;
  while ( *v4 )
  {
    ++v4;
    if ( !--v5 )
      goto LABEL_21;
  }
  v6 = 2147483646;
  v7 = 0;
  v8 = &v60[-2 * v5];
  v9 = Buffer;
  while ( v6 && *v9 )
  {
    *v8++ = *v9++;
    --v6;
    if ( !--v5 )
    {
      --v8;
      v7 = -2147024774;
      break;
    }
  }
  *v8 = 0;
  if ( v7 >= 0 )
  {
    v53 = v59;
    v10 = -1;
    do
      v11 = v59[++v10] == 0;
    while ( !v11 );
    v54 = 2 * v10 + 2;
    v55 = 0;
    if ( (unsigned int)EtwEventWrite(
                         CGPServiceEventReporting::s_pEventProviderHandle,
                         OPERATIONAL_INFORMATION_MESSAGE,
                         1,
                         &v53) )
      GetLastError();
  }
LABEL_21:
  CGPServiceState::m_CurrentState = 0;
  CGPServiceState::m_PreviousStates = 0;
  CGPServiceState::m_PreviousStateCount = 0;
  v12 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v52 = v12;
  v13 = (unsigned __int16 **)v12;
  if ( v12 )
  {
    v12[1] = 0;
    *v12 = &CGPServiceState::`vftable';
    cchName = 0;
    phkResult = 0;
    dwDisposition[0] = 0;
    StringGuid = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\ServiceInstances",
                   0,
                   0,
                   1u,
                   0x2001Fu,
                   0,
                   &phkResult,
                   dwDisposition);
    if ( !StringGuid )
    {
      v15 = CGuid::Create();
      if ( v15 )
      {
        StringGuid = CGuid::GetStringGuid(v15, v13 + 1);
        if ( !StringGuid )
        {
          v43 = v13[1];
          *(_QWORD *)dwDisposition = 0;
          StringGuid = RegCreateKeyExW(phkResult, v43, 0, 0, 1u, 0x20019u, 0, (PHKEY)dwDisposition, &cchName);
          if ( !StringGuid )
            RegCloseKey(*(HKEY *)dwDisposition);
        }
      }
      else
      {
        StringGuid = 14;
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    cSubKeys = 0;
    hKey = 0;
    if ( !StringGuid )
    {
      cchName = 0;
      StringGuid = RegCreateKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\ServiceInstances",
                     0,
                     0,
                     1u,
                     0x2001Fu,
                     0,
                     &hKey,
                     &cchName);
      if ( StringGuid || (StringGuid = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0)) != 0 )
      {
LABEL_27:
        if ( hKey )
          RegCloseKey(hKey);
        if ( !StringGuid )
          return (unsigned int)StringGuid;
        goto LABEL_32;
      }
      v42 = 8LL * cSubKeys;
      if ( !is_mul_ok(cSubKeys, 8u) )
        v42 = -1;
      v52 = operator new[](v42, (const struct std::nothrow_t *)&std::nothrow);
      v41 = v52;
      if ( !v52 )
      {
LABEL_98:
        StringGuid = 14;
        goto LABEL_27;
      }
      v44 = 0;
      while ( 1 )
      {
        v39 = cSubKeys;
        if ( v44 >= cSubKeys )
          break;
        v45 = (HKEY)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        phkResult = v45;
        if ( !v45 )
        {
          v41[v44] = 0;
          operator delete(v41);
          goto LABEL_98;
        }
        v46 = v44++;
        *(_QWORD *)v45 = &CGPServiceState::`vftable';
        *((_QWORD *)v45 + 1) = 0;
        v41[v46] = v45;
      }
      v36 = 0;
      for ( i = 0; ; ++i )
      {
        while ( 1 )
        {
          if ( i >= v39 )
          {
LABEL_26:
            CGPServiceState::m_PreviousStates = v41;
            CGPServiceState::m_PreviousStateCount = v36;
            CGPServiceState::m_CurrentState = (struct CGPServiceState *)v13;
            goto LABEL_27;
          }
          cchName = 37;
          v34 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
          StringGuid = v34;
          if ( v34 != 234 )
            break;
          v39 = cSubKeys;
          StringGuid = 0;
          ++i;
        }
        if ( v34 == 259 )
        {
          StringGuid = 0;
          goto LABEL_26;
        }
        if ( v34 )
          goto LABEL_27;
        v35 = v36++;
        phkResult = 0;
        v37 = v41[v35];
        if ( !*(_QWORD *)(v37 + 8) )
        {
          dwDisposition[0] = 0;
          RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\ServiceInstances",
            0,
            0,
            1u,
            0x2001Fu,
            0,
            &phkResult,
            dwDisposition);
        }
        v38 = -1;
        do
          ++v38;
        while ( Name[v38] );
        v33 = v38 + 1;
        if ( v38 + 1 >= v38 && (*(_QWORD *)dwDisposition = 0, is_mul_ok(v33, 2u)) )
        {
          v29 = LocalAlloc(0x40u, 2 * v33);
          *(_QWORD *)(v37 + 8) = v29;
          v30 = v29;
          if ( !v29 )
          {
            StringGuid = 14;
            goto LABEL_35;
          }
          if ( v33 )
          {
            if ( v33 > 0x7FFFFFFF )
            {
              LOWORD(StringGuid) = 87;
              *v29 = 0;
            }
            else
            {
              v31 = 2147483646;
              v32 = Name;
              StringGuid = 0;
              while ( v31 && *v32 )
              {
                *v30++ = *v32++;
                --v31;
                if ( !--v33 )
                {
                  --v30;
                  StringGuid = -2147024774;
                  break;
                }
              }
              *v30 = 0;
              if ( StringGuid >= 0 )
              {
                StringGuid = 0;
                goto LABEL_35;
              }
            }
          }
          else
          {
            LOWORD(StringGuid) = 87;
          }
          LocalFree(*(HLOCAL *)(v37 + 8));
          *(_QWORD *)(v37 + 8) = 0;
          StringGuid = (unsigned __int16)StringGuid;
        }
        else
        {
          StringGuid = 534;
        }
LABEL_35:
        if ( phkResult )
          RegCloseKey(phkResult);
        _itow(4167, Buffer, 10);
        v17 = 2147483646;
        v18 = L"%%";
        v19 = 13;
        v20 = v59;
        while ( v17 && *v18 )
        {
          *v20++ = *v18++;
          --v17;
          if ( !--v19 )
          {
            *(v20 - 1) = 0;
            goto LABEL_86;
          }
        }
        *v20 = 0;
        v21 = v59;
        v22 = 13;
        while ( *v21 )
        {
          ++v21;
          if ( !--v22 )
            goto LABEL_86;
        }
        v23 = 2147483646;
        v24 = 0;
        v25 = &v60[-2 * v22];
        v26 = Buffer;
        while ( v23 && *v26 )
        {
          *v25++ = *v26++;
          --v23;
          if ( !--v22 )
          {
            --v25;
            v24 = -2147024774;
            break;
          }
        }
        *v25 = 0;
        if ( v24 >= 0 )
        {
          v53 = v59;
          v27 = -1;
          do
            v11 = v59[++v27] == 0;
          while ( !v11 );
          v55 = 0;
          v54 = 2 * v27 + 2;
          v28 = -1;
          dwDisposition[0] = 0;
          do
            v11 = Name[++v28] == 0;
          while ( !v11 );
          if ( (int)ULongLongToULong(2 * v28 + 2, dwDisposition) >= 0 )
          {
            v56 = Name;
            v57 = dwDisposition[0];
            v58 = 0;
            if ( (unsigned int)EtwEventWrite(
                                 CGPServiceEventReporting::s_pEventProviderHandle,
                                 OPERATIONAL_INFORMATION_MESSAGE_WITH_STRING,
                                 2,
                                 &v53) )
              GetLastError();
          }
          else
          {
            GetLastError();
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"SizeTToULong() Failed to convert size_t to ULONG");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"SizeTToULong() Failed to convert size_t to ULONG");
              }
            }
          }
        }
LABEL_86:
        if ( StringGuid )
          goto LABEL_27;
        v41 = v52;
        v39 = cSubKeys;
      }
    }
  }
  else
  {
    v13 = 0;
    StringGuid = 14;
    cSubKeys = 0;
    hKey = 0;
  }
LABEL_32:
  CGPServiceState::Uninitialize();
  if ( v13 )
    (*((void (__fastcall **)(unsigned __int16 **, __int64))*v13 + 1))(v13, 1);
  return (unsigned int)StringGuid;
}

```

## disassembly

```asm
0x1800379b0  mov     r11, rsp
0x1800379b3  push    rbp
0x1800379b4  lea     rbp, [rsp-80h]
0x1800379b9  sub     rsp, 180h
0x1800379c0  mov     rax, cs:__security_cookie
0x1800379c7  xor     rax, rsp
0x1800379ca  mov     [rbp+80h+var_30], rax
0x1800379ce  cmp     cs:?m_CurrentState@CGPServiceState@@0PEAV1@EA, 0; CGPServiceState * CGPServiceState::m_CurrentState
0x1800379d6  jnz     loc_180037C2A
0x1800379dc  mov     [r11+18h], rdi
0x1800379e0  lea     rdx, [rbp+80h+Buffer]; Buffer
0x1800379e4  mov     [r11-20h], r14
0x1800379e8  mov     r8d, 0Ah; Radix
0x1800379ee  mov     ecx, 1046h; Value
0x1800379f3  mov     [r11-28h], r15
0x1800379f7  call    cs:__imp__itow
0x1800379fd  mov     eax, 7FFFFFFEh
0x180037a02  mov     [rsp+180h+arg_8], rsi
0x180037a0a  lea     rdx, asc_1800C64E0; "%%"
0x180037a11  mov     r8d, 0Dh
0x180037a17  lea     r9, [rbp+80h+var_C8]
0x180037a1b  nop     dword ptr [rax+rax+00h]
0x180037a20  test    rax, rax
0x180037a23  jz      short loc_180037A5B
0x180037a25  movzx   ecx, word ptr [rdx]
0x180037a28  test    cx, cx
0x180037a2b  jz      short loc_180037A56
0x180037a2d  mov     [r9], cx
0x180037a31  add     rdx, 2
0x180037a35  add     r9, 2
0x180037a39  dec     rax
0x180037a3c  sub     r8, 1
0x180037a40  jnz     short loc_180037A20
0x180037a42  xor     r15d, r15d
0x180037a45  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180037a4c  mov     [r9-2], r15w
0x180037a51  jmp     loc_180037B50
0x180037a56  test    r8, r8
0x180037a59  jz      short loc_180037A42
0x180037a5b  xor     r15d, r15d
0x180037a5e  lea     rcx, [rbp+80h+var_C8]
0x180037a62  mov     [r9], r15w
0x180037a66  mov     eax, 0Dh
0x180037a6b  nop     dword ptr [rax+rax+00h]
0x180037a70  cmp     [rcx], r15w
0x180037a74  jz      short loc_180037A98
0x180037a76  add     rcx, 2
0x180037a7a  sub     rax, 1
0x180037a7e  jnz     short loc_180037A70
0x180037a80  mov     r10d, 80070057h
0x180037a86  test    r10w, r10w
0x180037a8a  jz      short loc_180037AF1
0x180037a8c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180037a93  jmp     loc_180037B50
0x180037a98  lea     rcx, [rax+rax]
0x180037a9c  mov     edx, 7FFFFFFEh
0x180037aa1  lea     r9, [rbp+80h+var_AE]
0x180037aa5  mov     r10d, r15d
0x180037aa8  sub     r9, rcx
0x180037aab  lea     r8, [rbp+80h+Buffer]
0x180037aaf  test    rax, rax
0x180037ab2  jz      short loc_180037AD7
0x180037ab4  test    rdx, rdx
0x180037ab7  jz      short loc_180037AE8
0x180037ab9  movzx   ecx, word ptr [r8]
0x180037abd  test    cx, cx
0x180037ac0  jz      short loc_180037AE3
0x180037ac2  mov     [r9], cx
0x180037ac6  add     r8, 2
0x180037aca  add     r9, 2
0x180037ace  dec     rdx
0x180037ad1  sub     rax, 1
0x180037ad5  jnz     short loc_180037AB4
0x180037ad7  sub     r9, 2
0x180037adb  mov     r10d, 8007007Ah
0x180037ae1  jmp     short loc_180037AE8
0x180037ae3  test    rax, rax
0x180037ae6  jz      short loc_180037AD7
0x180037ae8  mov     [r9], r15w
0x180037aec  test    r10d, r10d
0x180037aef  js      short loc_180037A86
0x180037af1  lea     rax, [rbp+80h+var_C8]
0x180037af5  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180037afc  mov     [rbp+80h+var_F8], rax
0x180037b00  lea     rcx, [rbp+80h+var_C8]
0x180037b04  mov     rax, rsi
0x180037b07  nop     word ptr [rax+rax+00000000h]
0x180037b10  cmp     [rcx+rax*2+2], r15w
0x180037b16  lea     rax, [rax+1]
0x180037b1a  jnz     short loc_180037B10
0x180037b1c  mov     rcx, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x180037b23  lea     eax, ds:2[rax*2]
0x180037b2a  lea     r9, [rbp+80h+var_F8]
0x180037b2e  mov     [rbp+80h+var_F0], eax
0x180037b31  mov     r8d, 1
0x180037b37  mov     [rbp+80h+var_EC], r15d
0x180037b3b  lea     rdx, OPERATIONAL_INFORMATION_MESSAGE
0x180037b42  call    cs:__imp_EtwEventWrite
0x180037b48  test    eax, eax
0x180037b4a  jnz     loc_1800381FF
0x180037b50  mov     [rsp+180h+arg_0], rbx
0x180037b58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037b5f  mov     ecx, 10h; unsigned __int64
0x180037b64  mov     [rsp+180h+var_8], r12
0x180037b6c  mov     cs:?m_CurrentState@CGPServiceState@@0PEAV1@EA, r15; CGPServiceState * CGPServiceState::m_CurrentState
0x180037b73  mov     cs:?m_PreviousStates@CGPServiceState@@0PEAPEAV1@EA, r15; CGPServiceState * * CGPServiceState::m_PreviousStates
0x180037b7a  mov     cs:?m_PreviousStateCount@CGPServiceState@@0KA, r15d; ulong CGPServiceState::m_PreviousStateCount
0x180037b81  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037b86  mov     [rbp+80h+var_100], rax
0x180037b8a  mov     r14, rax
0x180037b8d  test    rax, rax
0x180037b90  jz      loc_180037CAA
0x180037b96  mov     [rax+8], r15
0x180037b9a  lea     r12, ??_7CGPServiceState@@6B@; const CGPServiceState::`vftable'
0x180037ba1  mov     [rax], r12
0x180037ba4  test    rax, rax
0x180037ba7  jz      loc_180037CAD
0x180037bad  mov     [rsp+180h+cchName], r15d
0x180037bb2  mov     [rsp+180h+var_110], r15
0x180037bb7  test    r15, r15
0x180037bba  jnz     loc_18003820A
0x180037bc0  lea     rax, [rsp+180h+dwDisposition]
0x180037bc5  mov     [rsp+180h+dwDisposition], r15d
0x180037bca  mov     [rsp+180h+lpdwDisposition], rax; lpdwDisposition
0x180037bcf  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180037bd6  lea     rax, [rsp+180h+var_110]
0x180037bdb  xor     r9d, r9d; lpClass
0x180037bde  mov     [rsp+180h+phkResult], rax; phkResult
0x180037be3  xor     r8d, r8d; Reserved
0x180037be6  mov     [rsp+180h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180037beb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037bf2  mov     [rsp+180h+samDesired], 2001Fh; samDesired
0x180037bfa  mov     [rsp+180h+dwOptions], 1; dwOptions
0x180037c02  call    cs:__imp_RegCreateKeyExW
0x180037c08  mov     edi, eax
0x180037c0a  test    eax, eax
0x180037c0c  jnz     loc_18003809A
0x180037c12  call    ?Create@CGuid@@SAPEAV1@XZ; CGuid::Create(void)
0x180037c17  test    rax, rax
0x180037c1a  jnz     loc_180038084
0x180037c20  mov     edi, 0Eh
0x180037c25  jmp     loc_18003809A
0x180037c2a  xor     eax, eax
0x180037c2c  jmp     short loc_180037C95
0x180037c2e  test    edi, edi
0x180037c30  jnz     short loc_180037C47
0x180037c32  mov     cs:?m_PreviousStates@CGPServiceState@@0PEAPEAV1@EA, rsi; CGPServiceState * * CGPServiceState::m_PreviousStates
0x180037c39  mov     cs:?m_PreviousStateCount@CGPServiceState@@0KA, r13d; ulong CGPServiceState::m_PreviousStateCount
0x180037c40  mov     cs:?m_CurrentState@CGPServiceState@@0PEAV1@EA, r14; CGPServiceState * CGPServiceState::m_CurrentState
0x180037c47  mov     rcx, [rsp+180h+hKey]; hKey
0x180037c4c  mov     r13, [rsp+180h+var_10]
0x180037c54  test    rcx, rcx
0x180037c57  jz      short loc_180037C5F
0x180037c59  call    cs:__imp_RegCloseKey
0x180037c5f  test    edi, edi
0x180037c61  jnz     short loc_180037CBC
0x180037c63  mov     r15, [rsp+180h+var_20]
0x180037c6b  mov     eax, edi
0x180037c6d  mov     rdi, [rsp+180h+arg_10]
0x180037c75  mov     r14, [rsp+180h+var_18]
0x180037c7d  mov     r12, [rsp+180h+var_8]
0x180037c85  mov     rsi, [rsp+180h+arg_8]
0x180037c8d  mov     rbx, [rsp+180h+arg_0]
0x180037c95  mov     rcx, [rbp+80h+var_30]
0x180037c99  xor     rcx, rsp; StackCookie
0x180037c9c  call    __security_check_cookie
0x180037ca1  add     rsp, 180h
0x180037ca8  pop     rbp
0x180037ca9  retn
0x180037caa  mov     r14, r15
0x180037cad  mov     edi, 0Eh
0x180037cb2  mov     [rsp+180h+cSubKeys], r15d
0x180037cb7  mov     [rsp+180h+hKey], r15
0x180037cbc  call    ?Uninitialize@CGPServiceState@@SAXXZ; CGPServiceState::Uninitialize(void)
0x180037cc1  test    r14, r14
0x180037cc4  jz      short loc_180037C63
0x180037cc6  mov     rax, [r14]
0x180037cc9  mov     edx, 1
0x180037cce  mov     rcx, r14
0x180037cd1  mov     rax, [rax+8]
0x180037cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cda  jmp     short loc_180037C63
0x180037cdc  mov     edi, 216h
0x180037ce1  mov     rcx, [rsp+180h+var_110]; hKey
0x180037ce6  test    rcx, rcx
0x180037ce9  jnz     loc_180037E78
0x180037cef  mov     r8d, 0Ah; Radix
0x180037cf5  lea     rdx, [rbp+80h+Buffer]; Buffer
0x180037cf9  mov     ecx, 1047h; Value
0x180037cfe  call    cs:__imp__itow
0x180037d04  mov     ecx, 7FFFFFFEh
0x180037d09  lea     rdx, asc_1800C64E0; "%%"
0x180037d10  mov     r8d, 0Dh
0x180037d16  lea     r9, [rbp+80h+var_C8]
0x180037d1a  nop     word ptr [rax+rax+00h]
0x180037d20  test    rcx, rcx
0x180037d23  jz      short loc_180037D51
0x180037d25  movzx   eax, word ptr [rdx]
0x180037d28  test    ax, ax
0x180037d2b  jz      short loc_180037D4C
0x180037d2d  mov     [r9], ax
0x180037d31  add     rdx, 2
0x180037d35  add     r9, 2
0x180037d39  dec     rcx
0x180037d3c  sub     r8, 1
0x180037d40  jnz     short loc_180037D20
0x180037d42  mov     [r9-2], r15w
0x180037d47  jmp     loc_180038064
0x180037d4c  test    r8, r8
0x180037d4f  jz      short loc_180037D42
0x180037d51  mov     [r9], r15w
0x180037d55  lea     rax, [rbp+80h+var_C8]
0x180037d59  mov     ecx, 0Dh
0x180037d5e  xchg    ax, ax
0x180037d60  cmp     word ptr [rax], 0
0x180037d64  jz      short loc_180037D82
0x180037d66  add     rax, 2
0x180037d6a  sub     rcx, 1
0x180037d6e  jnz     short loc_180037D60
0x180037d70  mov     r11d, 80070057h
0x180037d76  test    r11w, r11w
0x180037d7a  jnz     loc_180038064
0x180037d80  jmp     short loc_180037DDD
0x180037d82  lea     rax, [rcx+rcx]
0x180037d86  mov     edx, 7FFFFFFEh
0x180037d8b  lea     r9, [rbp+80h+var_AE]
0x180037d8f  mov     r11d, r15d
0x180037d92  sub     r9, rax
0x180037d95  lea     r8, [rbp+80h+Buffer]
0x180037d99  test    rcx, rcx
0x180037d9c  jz      short loc_180037DC3
0x180037d9e  xchg    ax, ax
0x180037da0  test    rdx, rdx
0x180037da3  jz      short loc_180037DD4
0x180037da5  movzx   eax, word ptr [r8]
0x180037da9  test    ax, ax
0x180037dac  jz      short loc_180037DCF
0x180037dae  mov     [r9], ax
0x180037db2  add     r8, 2
0x180037db6  add     r9, 2
0x180037dba  dec     rdx
0x180037dbd  sub     rcx, 1
0x180037dc1  jnz     short loc_180037DA0
0x180037dc3  sub     r9, 2
0x180037dc7  mov     r11d, 8007007Ah
0x180037dcd  jmp     short loc_180037DD4
0x180037dcf  test    rcx, rcx
0x180037dd2  jz      short loc_180037DC3
0x180037dd4  mov     [r9], r15w
0x180037dd8  test    r11d, r11d
0x180037ddb  js      short loc_180037D76
0x180037ddd  lea     rax, [rbp+80h+var_C8]
0x180037de1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180037de8  mov     [rbp+80h+var_F8], rax
0x180037dec  lea     rcx, [rbp+80h+var_C8]
0x180037df0  mov     rax, rsi
0x180037df3  cmp     word ptr [rcx+rax*2+2], 0
0x180037df9  lea     rax, [rax+1]
0x180037dfd  jnz     short loc_180037DF3
0x180037dff  lea     eax, ds:2[rax*2]
0x180037e06  mov     [rbp+80h+var_EC], r15d
0x180037e0a  mov     [rbp+80h+var_F0], eax
0x180037e0d  mov     rcx, rsi
0x180037e10  lea     rax, [rbp+80h+Name]
0x180037e14  mov     [rsp+180h+dwDisposition], r15d
0x180037e19  cmp     word ptr [rax+rcx*2+2], 0
0x180037e1f  lea     rcx, [rcx+1]
0x180037e23  jnz     short loc_180037E19
0x180037e25  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x180037e2d  lea     rdx, [rsp+180h+dwDisposition]; unsigned int *
0x180037e32  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180037e37  test    eax, eax
0x180037e39  jns     loc_18003802B
0x180037e3f  call    cs:__imp_GetLastError
0x180037e45  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180037e4c  jz      loc_180038064
0x180037e52  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180037e59  test    rax, rax
0x180037e5c  jz      loc_180038287
0x180037e62  lea     rdx, aSizettoulongFa; "SizeTToULong() Failed to convert size_t"...
0x180037e69  mov     ecx, 2
0x180037e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e73  jmp     loc_180038064
0x180037e78  call    cs:__imp_RegCloseKey
0x180037e7e  jmp     loc_180037CEF
0x180037e83  mov     eax, 2
0x180037e88  mov     qword ptr [rsp+180h+dwDisposition], r15
0x180037e8d  mul     rbx
0x180037e90  test    rdx, rdx
0x180037e93  jnz     loc_180037CDC
0x180037e99  mov     rdx, rax; uBytes
0x180037e9c  mov     ecx, 40h ; '@'; uFlags
0x180037ea1  call    cs:__imp_LocalAlloc
0x180037ea7  mov     [rsi+8], rax
0x180037eab  mov     r8, rax
0x180037eae  test    rax, rax
0x180037eb1  jz      short loc_180037F2D
0x180037eb3  test    rbx, rbx
0x180037eb6  jz      loc_180038270
0x180037ebc  cmp     rbx, 7FFFFFFFh
  ... truncated ...
```
