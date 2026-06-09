# FormatSystemRegPath(_SYSTEM_NAME_INFO *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18005d530`
- end: `0x18005db35`
- name: `?FormatSystemRegPath@@YAPEAGPEAU_SYSTEM_NAME_INFO@@PEBGKPEAPEAUHKEY__@@@Z`
- size: `1541`
- prototype: `unsigned __int16 *__fastcall(struct _SYSTEM_NAME_INFO *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b450`
- `0x18005be80`
- `0x18005db3c`
- `0x1800adb18`

## callees

- `0x180028d60`
- `0x18005d530`
- `0x1800bec20`
- `0x1800c8058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d6c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d708`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dad1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d6c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d708`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d6ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d6ad`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18005d639`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18005d639`

## string_xrefs

- `0x18005da87`: `Software\Microsoft\Cryptography\Services`

## pseudocode

```c
unsigned __int16 *__fastcall FormatSystemRegPath(
        struct _SYSTEM_NAME_INFO *a1,
        const unsigned __int16 *a2,
        int a3,
        HKEY *a4)
{
  unsigned __int16 *v4; // r14
  int v6; // r12d
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  LSTATUS v12; // eax
  int v13; // edi
  int v14; // r8d
  unsigned int i; // ebx
  unsigned int v16; // r10d
  __int64 v17; // rdx
  _WORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  _WORD *v21; // rsi
  DWORD LastError; // ebx
  unsigned int j; // r13d
  __int64 v25; // r11
  unsigned int *v26; // r15
  unsigned int v27; // r14d
  _WORD *v28; // r10
  __int64 v29; // rcx
  __int64 v30; // rdx
  _WORD *v31; // r8
  _WORD *v32; // rcx
  signed int v33; // r8d
  __int64 v34; // rcx
  _WORD *v35; // rax
  __int64 v36; // rax
  const WCHAR *v37; // rdx
  _WORD *v38; // r8
  __int64 v39; // rcx
  __int64 v40; // r9
  _WORD *v41; // rcx
  __int64 v42; // rcx
  _WORD *v43; // rax
  __int64 v44; // rax
  _WORD *v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rdx
  _WORD *v48; // rcx
  unsigned __int16 *CurrentServiceOrUserName; // rax
  HKEY phkResult; // [rsp+28h] [rbp-79h] BYREF
  unsigned int v51; // [rsp+30h] [rbp-71h]
  __int128 v52; // [rsp+38h] [rbp-69h] BYREF
  unsigned __int16 *v53; // [rsp+48h] [rbp-59h]
  _DWORD v54[2]; // [rsp+50h] [rbp-51h] BYREF
  __int128 *v55; // [rsp+58h] [rbp-49h]
  int v56; // [rsp+60h] [rbp-41h]
  __int128 *v57; // [rsp+68h] [rbp-39h]
  int v58; // [rsp+70h] [rbp-31h]
  const unsigned __int16 **v59; // [rsp+78h] [rbp-29h]
  HKEY *v60; // [rsp+80h] [rbp-21h]
  __int128 v61; // [rsp+88h] [rbp-19h] BYREF
  const wchar_t *v62; // [rsp+98h] [rbp-9h]
  __int128 v63; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v64; // [rsp+B0h] [rbp+Fh]
  const unsigned __int16 *v65; // [rsp+110h] [rbp+6Fh] BYREF

  v65 = a2;
  v4 = 0;
  v60 = a4;
  phkResult = 0;
  v53 = 0;
  v62 = 0;
  v6 = 1;
  v64 = 0;
  v61 = 0;
  v52 = 0;
  v63 = 0;
  if ( a2 )
  {
    v58 = 1;
    v59 = &v65;
    v7 = 3;
  }
  else
  {
    v7 = 2;
  }
  v8 = a3 & 0xFF0000;
  v51 = v7;
  if ( (a3 & 0xFF0000) == 0x20000 )
    goto LABEL_4;
  if ( v8 > 0x70000 )
  {
    switch ( v8 )
    {
      case 0x90000u:
        v9 = L"Software\\Microsoft\\EnterpriseCertificates";
        goto LABEL_5;
      case 0x80000u:
LABEL_39:
        v9 = L"Software\\Policies\\Microsoft\\SystemCertificates";
        goto LABEL_5;
      case 0xA0000u:
        v9 = L"OSDATA\\Software\\Microsoft\\WCOSCertificates";
        goto LABEL_5;
    }
LABEL_97:
    SetLastError(0x80070057);
    goto LABEL_25;
  }
  switch ( v8 )
  {
    case 0x70000u:
      goto LABEL_39;
    case 0x10000u:
LABEL_4:
      v9 = L"Software\\Microsoft\\SystemCertificates";
LABEL_5:
      v54[0] = 1;
      *(_QWORD *)&v52 = v9;
LABEL_6:
      v55 = &v52;
      goto LABEL_7;
    case 0x40000u:
    case 0x50000u:
      v54[0] = 3;
      v55 = &v61;
      *(_QWORD *)&v61 = L"Software\\Microsoft\\Cryptography\\Services";
      v62 = L"SystemCertificates";
      if ( v8 == 0x40000 )
      {
        CurrentServiceOrUserName = GetCurrentServiceOrUserName();
        v53 = CurrentServiceOrUserName;
        v4 = CurrentServiceOrUserName;
        if ( !CurrentServiceOrUserName )
          goto LABEL_25;
      }
      else
      {
        CurrentServiceOrUserName = (unsigned __int16 *)*((_QWORD *)a1 + 2);
        if ( !CurrentServiceOrUserName )
        {
          v54[0] = 1;
          goto LABEL_7;
        }
      }
      *((_QWORD *)&v61 + 1) = CurrentServiceOrUserName;
      goto LABEL_7;
  }
  if ( v8 != 393216 )
    goto LABEL_97;
  if ( *((_QWORD *)a1 + 2) )
  {
    *(_QWORD *)&v52 = *((_QWORD *)a1 + 2);
    *((_QWORD *)&v52 + 1) = L"Software\\Microsoft\\SystemCertificates";
    v54[0] = 2;
    goto LABEL_6;
  }
  v54[0] = 0;
LABEL_7:
  v57 = &v63;
  *(_QWORD *)&v63 = *((_QWORD *)a1 + 1);
  v10 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    v56 = 3;
    *((_QWORD *)&v63 + 1) = L"PhysicalStores";
    v64 = v10;
  }
  else
  {
    v56 = 1;
  }
  v11 = (const WCHAR *)*((_QWORD *)a1 + 3);
  if ( v11 )
  {
    v12 = RegConnectRegistryExW(v11, (HKEY)((v8 == 393216) - 2147483646LL), 0, &phkResult);
    if ( v12 )
    {
      SetLastError(v12);
      goto LABEL_25;
    }
  }
  else if ( *((_QWORD *)a1 + 4) )
  {
    phkResult = (HKEY)*((_QWORD *)a1 + 4);
  }
  else
  {
    if ( v8 == 327680 )
      goto LABEL_32;
    if ( v8 == 458752 )
      goto LABEL_37;
    if ( v8 > 0x60000 )
      goto LABEL_32;
    if ( v8 == 393216 )
    {
      phkResult = HKEY_USERS;
      goto LABEL_11;
    }
    if ( v8 == 0x10000 )
LABEL_37:
      phkResult = HKEY_CURRENT_USER;
    else
LABEL_32:
      phkResult = HKEY_LOCAL_MACHINE;
  }
LABEL_11:
  v13 = 0;
  v14 = 1;
  for ( i = 0; i < v7; ++i )
  {
    v16 = v54[4 * i];
    if ( v16 )
    {
      v17 = 0;
      do
      {
        v18 = (_WORD *)*((_QWORD *)(&v55)[2 * i] + v17);
        if ( v18 && *v18 )
        {
          if ( !v14 )
            ++v13;
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v13 += v19;
          v14 = 0;
        }
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (unsigned int)v17 < v16 );
    }
  }
  v20 = (unsigned int)(v13 + 1);
  v21 = LocalAlloc(0, 2 * v20);
  if ( !v21 )
  {
    SetLastError(0x8007000E);
LABEL_25:
    v21 = 0;
    goto LABEL_26;
  }
  for ( j = 0; j < v7; ++j )
  {
    v25 = 0;
    v26 = &v54[4 * j];
    v27 = *v26;
    while ( (unsigned int)v25 < v27 )
    {
      v28 = *(_WORD **)(*((_QWORD *)v26 + 1) + 8 * v25);
      if ( v28 && *v28 )
      {
        if ( v6 )
        {
          if ( (_DWORD)v20 )
          {
            if ( (unsigned int)v20 > 0x7FFFFFFFuLL )
            {
              *v21 = 0;
LABEL_117:
              v33 = -2147024809;
LABEL_90:
              SetLastError(v33);
              PkiDefaultCryptFree(v21);
              v4 = v53;
              goto LABEL_25;
            }
            v29 = 2147483646;
            v30 = (unsigned int)v20;
            v31 = v21;
            do
            {
              if ( !v29 )
                break;
              if ( !*v28 )
                break;
              *v31++ = *v28++;
              --v29;
              --v30;
            }
            while ( v30 );
            v32 = v31 - 1;
            if ( v30 )
              v32 = v31;
            v33 = -2147024774;
            if ( v30 )
              v33 = 0;
            *v32 = 0;
          }
          else
          {
            v33 = -2147024809;
          }
          if ( v33 < 0 )
            goto LABEL_90;
          v6 = 0;
        }
        else
        {
          if ( !(_DWORD)v20 || (unsigned int)v20 > 0x7FFFFFFFuLL )
            goto LABEL_117;
          v34 = (unsigned int)v20;
          v35 = v21;
          do
          {
            if ( !*v35 )
              break;
            ++v35;
            --v34;
          }
          while ( v34 );
          v33 = -2147024809;
          if ( !v34 )
            goto LABEL_90;
          v36 = (unsigned int)v20 - v34;
          v37 = L"\\";
          v38 = &v21[v36];
          v39 = 2147483646;
          v40 = (unsigned int)v20 - v36;
          if ( (unsigned int)v20 != v36 )
          {
            do
            {
              if ( !v39 )
                break;
              if ( !*v37 )
                break;
              *v38++ = *v37++;
              --v39;
              --v40;
            }
            while ( v40 );
          }
          v41 = v38 - 1;
          if ( v40 )
            v41 = v38;
          v33 = -2147024774;
          if ( v40 )
            v33 = 0;
          *v41 = 0;
          if ( !v40 )
            goto LABEL_90;
          v42 = (unsigned int)v20;
          v43 = v21;
          do
          {
            if ( !*v43 )
              break;
            ++v43;
            --v42;
          }
          while ( v42 );
          v33 = -2147024809;
          if ( !v42 )
            goto LABEL_90;
          v44 = (unsigned int)v20 - v42;
          v45 = &v21[v44];
          v46 = 2147483646;
          v47 = (unsigned int)v20 - v44;
          if ( (unsigned int)v20 != v44 )
          {
            do
            {
              if ( !v46 )
                break;
              if ( !*v28 )
                break;
              *v45++ = *v28++;
              --v46;
              --v47;
            }
            while ( v47 );
          }
          v48 = v45 - 1;
          if ( v47 )
            v48 = v45;
          v33 = -2147024774;
          if ( v47 )
            v33 = 0;
          *v48 = 0;
          if ( !v47 )
            goto LABEL_90;
        }
      }
      v25 = (unsigned int)(v25 + 1);
    }
    v7 = v51;
  }
  if ( v6 )
    *v21 = 0;
  v4 = v53;
LABEL_26:
  if ( v4 )
  {
    LastError = GetLastError();
    LocalFree(v4);
    SetLastError(LastError);
  }
  *v60 = phkResult;
  return v21;
}

```

## disassembly

```asm
0x18005d530  mov     r11, rsp
0x18005d533  mov     [r11+10h], rdx
0x18005d537  push    rbp
0x18005d538  push    rbx
0x18005d539  push    r14
0x18005d53b  lea     rbp, [r11-5Fh]
0x18005d53f  sub     rsp, 0E0h
0x18005d546  mov     rax, cs:__security_cookie
0x18005d54d  xor     rax, rsp
0x18005d550  mov     [rbp+57h+var_40], rax
0x18005d554  xor     eax, eax
0x18005d556  mov     [r11-20h], rdi
0x18005d55a  xor     r14d, r14d
0x18005d55d  mov     [r11-28h], r12
0x18005d561  mov     [r11-38h], r15
0x18005d565  xorps   xmm0, xmm0
0x18005d568  mov     [rbp+57h+var_78], r9
0x18005d56c  xorps   xmm1, xmm1
0x18005d56f  mov     [rbp+57h+phkResult], 0
0x18005d577  mov     ebx, r8d
0x18005d57a  mov     [rbp+57h+var_B0], r14
0x18005d57e  mov     rdi, rcx
0x18005d581  mov     [rbp+57h+var_60], rax
0x18005d585  mov     r12d, 1
0x18005d58b  mov     [rbp+57h+var_48], rax
0x18005d58f  movups  [rbp+57h+var_70], xmm0
0x18005d593  movups  [rbp+57h+var_C0], xmm0
0x18005d597  movups  [rbp+57h+var_58], xmm1
0x18005d59b  test    rdx, rdx
0x18005d59e  jz      loc_18005D73C
0x18005d5a4  lea     rax, [rbp+57h+arg_8]
0x18005d5a8  mov     [rbp+57h+var_88], r12d
0x18005d5ac  mov     [rbp+57h+var_80], rax
0x18005d5b0  mov     r15d, 3
0x18005d5b6  and     ebx, 0FF0000h
0x18005d5bc  mov     [rsp+0F0h+arg_10], rsi
0x18005d5c4  mov     [rbp+57h+var_C8], r15d
0x18005d5c8  mov     [rsp+0F0h+var_28], r13
0x18005d5d0  cmp     ebx, 20000h
0x18005d5d6  jnz     loc_18005D765
0x18005d5dc  lea     rax, aSoftwareMicros_15; "Software\\Microsoft\\SystemCertificates"
0x18005d5e3  mov     [rbp+57h+var_A8], r12d
0x18005d5e7  mov     qword ptr [rbp+57h+var_C0], rax
0x18005d5eb  lea     rax, [rbp+57h+var_C0]
0x18005d5ef  mov     [rbp+57h+var_A0], rax
0x18005d5f3  lea     rax, [rbp+57h+var_58]
0x18005d5f7  mov     [rbp+57h+var_90], rax
0x18005d5fb  mov     rax, [rdi+8]
0x18005d5ff  mov     qword ptr [rbp+57h+var_58], rax
0x18005d603  mov     rax, [rdi]
0x18005d606  test    rax, rax
0x18005d609  jnz     loc_18005DA5D
0x18005d60f  mov     [rbp+57h+var_98], r12d
0x18005d613  mov     rcx, [rdi+18h]; lpMachineName
0x18005d617  test    rcx, rcx
0x18005d61a  jz      loc_18005D747
0x18005d620  xor     edx, edx
0x18005d622  lea     r9, [rbp+57h+phkResult]; phkResult
0x18005d626  cmp     ebx, 60000h
0x18005d62c  setz    dl
0x18005d62f  xor     r8d, r8d; Flags
0x18005d632  add     rdx, 0FFFFFFFF80000002h; hKey
0x18005d639  call    cs:__imp_RegConnectRegistryExW
0x18005d63f  test    eax, eax
0x18005d641  jnz     loc_18005DACF
0x18005d647  xor     edi, edi
0x18005d649  mov     r8d, r12d
0x18005d64c  xor     ebx, ebx
0x18005d64e  mov     eax, ebx
0x18005d650  add     rax, rax
0x18005d653  mov     r10d, [rbp+rax*8+57h+var_A8]
0x18005d658  test    r10d, r10d
0x18005d65b  jz      short loc_18005D69C
0x18005d65d  mov     r11, [rbp+rax*8+57h+var_A0]
0x18005d662  xor     edx, edx
0x18005d664  mov     rcx, [r11+rdx*8]
0x18005d668  test    rcx, rcx
0x18005d66b  jz      short loc_18005D695
0x18005d66d  cmp     word ptr [rcx], 0
0x18005d671  jz      short loc_18005D695
0x18005d673  lea     eax, [rdi+1]
0x18005d676  xor     r9d, r9d
0x18005d679  test    r8d, r8d
0x18005d67c  cmovz   edi, eax
0x18005d67f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005d686  inc     rax
0x18005d689  cmp     [rcx+rax*2], r9w
0x18005d68e  jnz     short loc_18005D686
0x18005d690  add     edi, eax
0x18005d692  mov     r8d, r9d
0x18005d695  inc     edx
0x18005d697  cmp     edx, r10d
0x18005d69a  jb      short loc_18005D664
0x18005d69c  inc     ebx
0x18005d69e  cmp     ebx, r15d
0x18005d6a1  jb      short loc_18005D64E
0x18005d6a3  inc     edi
0x18005d6a5  xor     ecx, ecx; uFlags
0x18005d6a7  mov     ebx, edi
0x18005d6a9  lea     rdx, [rdi+rdi]; uBytes
0x18005d6ad  call    cs:__imp_LocalAlloc
0x18005d6b3  mov     rsi, rax
0x18005d6b6  test    rax, rax
0x18005d6b9  jnz     loc_18005D7BF
0x18005d6bf  mov     ecx, 8007000Eh; dwErrCode
0x18005d6c4  call    cs:__imp_SetLastError
0x18005d6ca  xor     esi, esi
0x18005d6cc  mov     r15, [rsp+0F0h+var_30]
0x18005d6d4  mov     r13, [rsp+0F0h+var_28]
0x18005d6dc  mov     r12, [rsp+0F0h+var_20]
0x18005d6e4  mov     rdi, [rsp+0D8h]
0x18005d6ec  test    r14, r14
0x18005d6ef  jz      loc_18005D9F1
0x18005d6f5  call    cs:__imp_GetLastError
0x18005d6fb  mov     rcx, r14; hMem
0x18005d6fe  mov     ebx, eax
0x18005d700  call    cs:__imp_LocalFree
0x18005d706  mov     ecx, ebx; dwErrCode
0x18005d708  call    cs:__imp_SetLastError
0x18005d70e  mov     rdx, [rbp+57h+var_78]
0x18005d712  mov     rcx, [rbp+57h+phkResult]
0x18005d716  mov     [rdx], rcx
0x18005d719  mov     rax, rsi
0x18005d71c  mov     rsi, [rsp+0F0h+arg_10]
0x18005d724  mov     rcx, [rbp+57h+var_40]
0x18005d728  xor     rcx, rsp; StackCookie
0x18005d72b  call    __security_check_cookie
0x18005d730  add     rsp, 0E0h
0x18005d737  pop     r14
0x18005d739  pop     rbx
0x18005d73a  pop     rbp
0x18005d73b  retn
0x18005d73c  mov     r15d, 2
0x18005d742  jmp     loc_18005D5B6
0x18005d747  mov     rax, [rdi+20h]
0x18005d74b  test    rax, rax
0x18005d74e  jnz     short loc_18005D7B6
0x18005d750  cmp     ebx, 50000h
0x18005d756  jnz     short loc_18005D785
0x18005d758  mov     [rbp+57h+phkResult], 0FFFFFFFF80000002h
0x18005d760  jmp     loc_18005D647
0x18005d765  cmp     ebx, 70000h
0x18005d76b  jbe     loc_18005DA1D
0x18005d771  cmp     ebx, 90000h
0x18005d777  jnz     short loc_18005D79E
0x18005d779  lea     rax, aSoftwareMicros_5; "Software\\Microsoft\\EnterpriseCertific"...
0x18005d780  jmp     loc_18005D5E3
0x18005d785  cmp     ebx, 70000h
0x18005d78b  jnz     loc_18005DADC
0x18005d791  mov     [rbp+57h+phkResult], 0FFFFFFFF80000001h
0x18005d799  jmp     loc_18005D647
0x18005d79e  cmp     ebx, 80000h
0x18005d7a4  jnz     loc_18005DA01
0x18005d7aa  lea     rax, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\SystemCe"...
0x18005d7b1  jmp     loc_18005D5E3
0x18005d7b6  mov     [rbp+57h+phkResult], rax
0x18005d7ba  jmp     loc_18005D647
0x18005d7bf  xor     r13d, r13d
0x18005d7c2  cmp     r13d, r15d
0x18005d7c5  jnb     loc_18005D9DC
0x18005d7cb  mov     eax, r13d
0x18005d7ce  lea     r15, [rbp+57h+var_A8]
0x18005d7d2  shl     rax, 4
0x18005d7d6  xor     r11d, r11d
0x18005d7d9  add     r15, rax
0x18005d7dc  mov     r14d, [r15]
0x18005d7df  nop
0x18005d7e0  cmp     r11d, r14d
0x18005d7e3  jnb     loc_18005D9D0
0x18005d7e9  mov     rax, [r15+8]
0x18005d7ed  mov     r10, [rax+r11*8]
0x18005d7f1  test    r10, r10
0x18005d7f4  jz      short loc_18005D86E
0x18005d7f6  cmp     word ptr [r10], 0
0x18005d7fb  jz      short loc_18005D86E
0x18005d7fd  test    r12d, r12d
0x18005d800  jz      short loc_18005D876
0x18005d802  test    edi, edi
0x18005d804  jz      loc_18005DB17
0x18005d80a  cmp     rbx, 7FFFFFFFh
0x18005d811  ja      loc_18005DB25
0x18005d817  mov     ecx, 7FFFFFFEh
0x18005d81c  mov     rdx, rbx
0x18005d81f  mov     r8, rsi
0x18005d822  test    rcx, rcx
0x18005d825  jz      short loc_18005D845
0x18005d827  movzx   eax, word ptr [r10]
0x18005d82b  test    ax, ax
0x18005d82e  jz      short loc_18005D845
0x18005d830  mov     [r8], ax
0x18005d834  add     r10, 2
0x18005d838  add     r8, 2
0x18005d83c  dec     rcx
0x18005d83f  sub     rdx, 1
0x18005d843  jnz     short loc_18005D822
0x18005d845  lea     rcx, [r8-2]
0x18005d849  test    rdx, rdx
0x18005d84c  cmovnz  rcx, r8
0x18005d850  xor     eax, eax
0x18005d852  test    rdx, rdx
0x18005d855  mov     r8d, 8007007Ah
0x18005d85b  cmovnz  r8d, eax
0x18005d85f  mov     [rcx], ax
0x18005d862  test    r8d, r8d
0x18005d865  js      loc_18005D9B6
0x18005d86b  xor     r12d, r12d
0x18005d86e  inc     r11d
0x18005d871  jmp     loc_18005D7E0
0x18005d876  test    edi, edi
0x18005d878  jz      loc_18005DB2A
0x18005d87e  cmp     rbx, 7FFFFFFFh
0x18005d885  ja      loc_18005DB2A
0x18005d88b  mov     rcx, rbx
0x18005d88e  mov     rax, rsi
0x18005d891  cmp     word ptr [rax], 0
0x18005d895  jz      short loc_18005D8A1
0x18005d897  add     rax, 2
0x18005d89b  sub     rcx, 1
0x18005d89f  jnz     short loc_18005D891
0x18005d8a1  xor     eax, eax
0x18005d8a3  mov     r8d, 80070057h
0x18005d8a9  test    rcx, rcx
0x18005d8ac  cmovnz  r8d, eax
0x18005d8b0  jz      loc_18005D9B6
0x18005d8b6  mov     rax, rbx
0x18005d8b9  sub     rax, rcx
0x18005d8bc  test    rcx, rcx
0x18005d8bf  jz      loc_18005D9B6
0x18005d8c5  mov     r9, rbx
0x18005d8c8  lea     rdx, SubBlock; "\\"
0x18005d8cf  lea     r8, [rsi+rax*2]
0x18005d8d3  mov     ecx, 7FFFFFFEh
0x18005d8d8  sub     r9, rax
0x18005d8db  jz      short loc_18005D902
0x18005d8dd  nop     dword ptr [rax]
0x18005d8e0  test    rcx, rcx
0x18005d8e3  jz      short loc_18005D902
0x18005d8e5  movzx   eax, word ptr [rdx]
0x18005d8e8  test    ax, ax
0x18005d8eb  jz      short loc_18005D902
0x18005d8ed  mov     [r8], ax
0x18005d8f1  add     rdx, 2
0x18005d8f5  add     r8, 2
0x18005d8f9  dec     rcx
0x18005d8fc  sub     r9, 1
0x18005d900  jnz     short loc_18005D8E0
0x18005d902  lea     rcx, [r8-2]
0x18005d906  test    r9, r9
0x18005d909  cmovnz  rcx, r8
0x18005d90d  xor     eax, eax
0x18005d90f  test    r9, r9
0x18005d912  mov     r8d, 8007007Ah
0x18005d918  cmovnz  r8d, eax
0x18005d91c  mov     [rcx], ax
0x18005d91f  jz      loc_18005D9B6
0x18005d925  test    edi, edi
0x18005d927  jz      loc_18005DB2A
0x18005d92d  mov     rcx, rbx
0x18005d930  mov     rax, rsi
0x18005d933  cmp     word ptr [rax], 0
0x18005d937  jz      short loc_18005D943
0x18005d939  add     rax, 2
0x18005d93d  sub     rcx, 1
0x18005d941  jnz     short loc_18005D933
0x18005d943  xor     eax, eax
0x18005d945  mov     r8d, 80070057h
0x18005d94b  test    rcx, rcx
0x18005d94e  cmovnz  r8d, eax
0x18005d952  jz      short loc_18005D9B6
0x18005d954  mov     rax, rbx
0x18005d957  sub     rax, rcx
0x18005d95a  test    rcx, rcx
0x18005d95d  jz      short loc_18005D9B6
0x18005d95f  mov     rdx, rbx
0x18005d962  lea     r8, [rsi+rax*2]
0x18005d966  mov     ecx, 7FFFFFFEh
0x18005d96b  sub     rdx, rax
0x18005d96e  jz      short loc_18005D993
0x18005d970  test    rcx, rcx
0x18005d973  jz      short loc_18005D993
0x18005d975  movzx   eax, word ptr [r10]
0x18005d979  test    ax, ax
0x18005d97c  jz      short loc_18005D993
0x18005d97e  mov     [r8], ax
0x18005d982  add     r10, 2
0x18005d986  add     r8, 2
0x18005d98a  dec     rcx
0x18005d98d  sub     rdx, 1
0x18005d991  jnz     short loc_18005D970
0x18005d993  lea     rcx, [r8-2]
0x18005d997  test    rdx, rdx
0x18005d99a  cmovnz  rcx, r8
0x18005d99e  xor     eax, eax
0x18005d9a0  test    rdx, rdx
0x18005d9a3  mov     r8d, 8007007Ah
0x18005d9a9  cmovnz  r8d, eax
0x18005d9ad  mov     [rcx], ax
0x18005d9b0  jnz     loc_18005D86E
0x18005d9b6  mov     ecx, r8d; dwErrCode
0x18005d9b9  call    cs:__imp_SetLastError
  ... truncated ...
```
