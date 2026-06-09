# HrUpdateSignatureInfo(tagNLA_SIGNATURE *,ulong,...)

- ea: `0x18009e278`
- end: `0x18009e6ae`
- name: `?HrUpdateSignatureInfo@@YAJPEAUtagNLA_SIGNATURE@@KZZ`
- size: `1078`
- prototype: `__int64(struct tagNLA_SIGNATURE *, unsigned int, ...)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18009e050`
- `0x1800cafd0`
- `0x1800d5e24`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180014fb0`
- `0x180047ff4`
- `0x180055c20`
- `0x18009e278`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e627`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e338`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e3ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e488`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e4d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e61b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e338`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e3ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e488`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e4d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009e61b`

## pseudocode

```c
__int64 HrUpdateSignatureInfo(struct tagNLA_SIGNATURE *a1, char a2, ...)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  va_list v5; // rdi
  LSTATUS v6; // eax
  __int64 v7; // r9
  __int64 v8; // r15
  const BYTE *v9; // rcx
  __int64 v10; // rax
  LSTATUS v11; // eax
  __int64 v12; // r9
  int v13; // eax
  const BYTE *v14; // r14
  __int64 v15; // rax
  LSTATUS v16; // eax
  const BYTE *v17; // r14
  LSTATUS v18; // eax
  PVOID *v19; // rcx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-18h] BYREF
  const BYTE *lpData; // [rsp+A0h] [rbp+50h] BYREF
  va_list va; // [rsp+A0h] [rbp+50h]
  va_list va1; // [rsp+A8h] [rbp+58h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  lpData = va_arg(va1, const BYTE *);
  hKey = 0;
  *(_QWORD *)Data = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  v3 = HrOpenSignatureKey(a1, 0x2001Fu, &hKey);
  v4 = v3;
  if ( !v3 )
  {
    va_copy(v5, va);
    v4 = 0;
    if ( (a2 & 1) != 0 )
    {
      va_copy(v5, va1);
      v6 = RegSetValueExW(hKey, L"ProfileGuid", 0, 1u, lpData, 0x4Eu);
      v4 = v6;
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v6 > 0 )
            v7 = (unsigned __int16)v6 | 0x80070000;
          else
            v7 = (unsigned int)v6;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v7);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
      }
    }
    v8 = -1;
    if ( (a2 & 2) != 0 )
    {
      v9 = *(const BYTE **)v5;
      v5 += 8;
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&v9[2 * v10] );
      v11 = RegSetValueExW(hKey, L"Description", 0, 1u, v9, 2 * v10 + 2);
      v4 = v11;
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          else
            v12 = (unsigned int)v11;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v12);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
      }
    }
    if ( (a2 & 4) != 0 )
    {
      v13 = *(_DWORD *)v5;
      v5 += 8;
      *(_DWORD *)Data = v13;
      v4 = RegSetValueExW(hKey, L"Source", 0, 4u, Data, 4u);
    }
    if ( (a2 & 8) != 0 )
    {
      v14 = *(const BYTE **)v5;
      v5 += 8;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
      v16 = RegSetValueExW(hKey, L"DnsSuffix", 0, 1u, v14, 2 * v15 + 2);
      v4 = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            (_DWORD)v14,
            v16);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v14);
      }
    }
    if ( (a2 & 0x10) != 0 )
    {
      v17 = *(const BYTE **)v5;
      v5 += 8;
      do
        ++v8;
      while ( *(_WORD *)&v17[2 * v8] );
      v18 = RegSetValueExW(hKey, L"FirstNetwork", 0, 1u, v17, 2 * v8 + 2);
      v4 = v18;
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            (_DWORD)v17,
            v18);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v17);
      }
    }
    if ( (a2 & 0x20) != 0 )
      v4 = RegSetValueExW(hKey, L"DefaultGatewayMac", 0, 3u, *(const BYTE **)v5, *((_DWORD *)v5 + 2));
    RegCloseKey(hKey);
    if ( (int)v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_58;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v3);
LABEL_58:
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_d(v19[2], 28, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18009e278  mov     [rsp-38h+arg_8], edx
0x18009e27c  mov     [rsp-38h+arg_10], r8
0x18009e281  mov     [rsp-38h+arg_18], r9
0x18009e286  push    rbp
0x18009e287  push    rbx
0x18009e288  push    rdi
0x18009e289  push    r12
0x18009e28b  push    r13
0x18009e28d  push    r14
0x18009e28f  push    r15
0x18009e291  mov     rbp, rsp
0x18009e294  sub     rsp, 50h
0x18009e298  mov     rax, cs:__security_cookie
0x18009e29f  xor     rax, rsp
0x18009e2a2  mov     [rbp+var_10], rax
0x18009e2a6  xor     r12d, r12d
0x18009e2a9  mov     rbx, rcx
0x18009e2ac  mov     [rbp+hKey], r12
0x18009e2b0  mov     qword ptr [rbp+Data], r12
0x18009e2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e2bb  lea     r13, WPP_GLOBAL_Control
0x18009e2c2  cmp     rcx, r13
0x18009e2c5  jz      short loc_18009E2E2
0x18009e2c7  test    byte ptr [rcx+1Ch], 8
0x18009e2cb  jz      short loc_18009E2E2
0x18009e2cd  mov     rcx, [rcx+10h]
0x18009e2d1  lea     edx, [r12+12h]
0x18009e2d6  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e2dd  call    WPP_SF_
0x18009e2e2  lea     r8, [rbp+hKey]; HKEY *
0x18009e2e6  mov     edx, 2001Fh; unsigned int
0x18009e2eb  mov     rcx, rbx; struct tagNLA_SIGNATURE *
0x18009e2ee  call    ?HrOpenSignatureKey@@YAJPEAUtagNLA_SIGNATURE@@KPEAPEAUHKEY__@@@Z; HrOpenSignatureKey(tagNLA_SIGNATURE *,ulong,HKEY__ * *)
0x18009e2f3  mov     ebx, eax
0x18009e2f5  test    eax, eax
0x18009e2f7  jnz     loc_18009E63C
0x18009e2fd  test    byte ptr [rbp+arg_8], 1
0x18009e301  lea     rdi, [rbp+arg_10]
0x18009e305  mov     ebx, r12d
0x18009e308  lea     r14d, [rax+4]
0x18009e30c  jz      loc_18009E3A6
0x18009e312  mov     rax, [rdi]
0x18009e315  lea     r9d, [r14-3]; dwType
0x18009e319  mov     rcx, [rbp+hKey]; hKey
0x18009e31d  lea     rdx, aProfileguid; "ProfileGuid"
0x18009e324  add     rdi, 8
0x18009e328  mov     [rsp+50h+cbData], 4Eh ; 'N'; cbData
0x18009e330  xor     r8d, r8d; Reserved
0x18009e333  mov     [rsp+50h+lpData], rax; lpData
0x18009e338  call    cs:__imp_RegSetValueExW
0x18009e33e  mov     ebx, eax
0x18009e340  test    eax, eax
0x18009e342  jnz     short loc_18009E36B
0x18009e344  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e34b  cmp     rcx, r13
0x18009e34e  jz      short loc_18009E3A6
0x18009e350  test    [rcx+1Ch], r14b
0x18009e354  jz      short loc_18009E3A6
0x18009e356  mov     rcx, [rcx+10h]
0x18009e35a  lea     edx, [rax+13h]
0x18009e35d  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e364  call    WPP_SF_
0x18009e369  jmp     short loc_18009E3A6
0x18009e36b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e372  cmp     rcx, r13
0x18009e375  jz      short loc_18009E3A6
0x18009e377  test    byte ptr [rcx+1Ch], 1
0x18009e37b  jz      short loc_18009E3A6
0x18009e37d  test    eax, eax
0x18009e37f  jg      short loc_18009E386
0x18009e381  mov     r9d, eax
0x18009e384  jmp     short loc_18009E391
0x18009e386  movzx   r9d, ax
0x18009e38a  or      r9d, 80070000h
0x18009e391  mov     rcx, [rcx+10h]
0x18009e395  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e39c  mov     edx, 14h
0x18009e3a1  call    WPP_SF_d
0x18009e3a6  or      r15, 0FFFFFFFFFFFFFFFFh
0x18009e3aa  test    byte ptr [rbp+arg_8], 2
0x18009e3ae  jz      loc_18009E45A
0x18009e3b4  mov     rcx, [rdi]
0x18009e3b7  add     rdi, 8
0x18009e3bb  mov     rax, r15
0x18009e3be  inc     rax
0x18009e3c1  cmp     [rcx+rax*2], r12w
0x18009e3c6  jnz     short loc_18009E3BE
0x18009e3c8  lea     eax, ds:2[rax*2]
0x18009e3cf  mov     r9d, 1; dwType
0x18009e3d5  mov     [rsp+50h+cbData], eax; cbData
0x18009e3d9  lea     rdx, aDescription; "Description"
0x18009e3e0  mov     [rsp+50h+lpData], rcx; lpData
0x18009e3e5  xor     r8d, r8d; Reserved
0x18009e3e8  mov     rcx, [rbp+hKey]; hKey
0x18009e3ec  call    cs:__imp_RegSetValueExW
0x18009e3f2  mov     ebx, eax
0x18009e3f4  test    eax, eax
0x18009e3f6  jnz     short loc_18009E41F
0x18009e3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e3ff  cmp     rcx, r13
0x18009e402  jz      short loc_18009E45A
0x18009e404  test    [rcx+1Ch], r14b
0x18009e408  jz      short loc_18009E45A
0x18009e40a  mov     rcx, [rcx+10h]
0x18009e40e  lea     edx, [rax+15h]
0x18009e411  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e418  call    WPP_SF_
0x18009e41d  jmp     short loc_18009E45A
0x18009e41f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e426  cmp     rcx, r13
0x18009e429  jz      short loc_18009E45A
0x18009e42b  test    byte ptr [rcx+1Ch], 1
0x18009e42f  jz      short loc_18009E45A
0x18009e431  test    eax, eax
0x18009e433  jg      short loc_18009E43A
0x18009e435  mov     r9d, eax
0x18009e438  jmp     short loc_18009E445
0x18009e43a  movzx   r9d, ax
0x18009e43e  or      r9d, 80070000h
0x18009e445  mov     rcx, [rcx+10h]
0x18009e449  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e450  mov     edx, 16h
0x18009e455  call    WPP_SF_d
0x18009e45a  test    byte ptr [rbp+arg_8], r14b
0x18009e45e  jz      short loc_18009E490
0x18009e460  mov     eax, [rdi]
0x18009e462  lea     rdx, aSource; "Source"
0x18009e469  mov     rcx, [rbp+hKey]; hKey
0x18009e46d  add     rdi, 8
0x18009e471  mov     dword ptr [rbp+Data], eax
0x18009e474  mov     r9d, r14d; dwType
0x18009e477  lea     rax, [rbp+Data]
0x18009e47b  mov     [rsp+50h+cbData], r14d; cbData
0x18009e480  xor     r8d, r8d; Reserved
0x18009e483  mov     [rsp+50h+lpData], rax; lpData
0x18009e488  call    cs:__imp_RegSetValueExW
0x18009e48e  mov     ebx, eax
0x18009e490  test    byte ptr [rbp+arg_8], 8
0x18009e494  jz      loc_18009E542
0x18009e49a  mov     r14, [rdi]
0x18009e49d  add     rdi, 8
0x18009e4a1  mov     rax, r15
0x18009e4a4  inc     rax
0x18009e4a7  cmp     [r14+rax*2], r12w
0x18009e4ac  jnz     short loc_18009E4A4
0x18009e4ae  mov     rcx, [rbp+hKey]; hKey
0x18009e4b2  lea     eax, ds:2[rax*2]
0x18009e4b9  mov     [rsp+50h+cbData], eax; cbData
0x18009e4bd  lea     rdx, aDnssuffix; "DnsSuffix"
0x18009e4c4  mov     r9d, 1; dwType
0x18009e4ca  mov     [rsp+50h+lpData], r14; lpData
0x18009e4cf  xor     r8d, r8d; Reserved
0x18009e4d2  call    cs:__imp_RegSetValueExW
0x18009e4d8  mov     ebx, eax
0x18009e4da  test    eax, eax
0x18009e4dc  jnz     short loc_18009E508
0x18009e4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e4e5  cmp     rcx, r13
0x18009e4e8  jz      short loc_18009E542
0x18009e4ea  test    byte ptr [rcx+1Ch], 4
0x18009e4ee  jz      short loc_18009E542
0x18009e4f0  mov     rcx, [rcx+10h]
0x18009e4f4  lea     edx, [rax+17h]
0x18009e4f7  mov     r9, r14
0x18009e4fa  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e501  call    WPP_SF_S
0x18009e506  jmp     short loc_18009E542
0x18009e508  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e50f  cmp     rcx, r13
0x18009e512  jz      short loc_18009E542
0x18009e514  test    byte ptr [rcx+1Ch], 1
0x18009e518  jz      short loc_18009E542
0x18009e51a  test    eax, eax
0x18009e51c  jle     short loc_18009E526
0x18009e51e  movzx   eax, ax
0x18009e521  or      eax, 80070000h
0x18009e526  mov     rcx, [rcx+10h]
0x18009e52a  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e531  mov     edx, 18h
0x18009e536  mov     dword ptr [rsp+50h+lpData], eax
0x18009e53a  mov     r9, r14
0x18009e53d  call    WPP_SF_Sd
0x18009e542  test    byte ptr [rbp+arg_8], 10h
0x18009e546  jz      loc_18009E5F2
0x18009e54c  mov     r14, [rdi]
0x18009e54f  add     rdi, 8
0x18009e553  inc     r15
0x18009e556  cmp     [r14+r15*2], r12w
0x18009e55b  jnz     short loc_18009E553
0x18009e55d  mov     rcx, [rbp+hKey]; hKey
0x18009e561  lea     eax, ds:2[r15*2]
0x18009e569  mov     [rsp+50h+cbData], eax; cbData
0x18009e56d  lea     rdx, aFirstnetwork; "FirstNetwork"
0x18009e574  mov     r9d, 1; dwType
0x18009e57a  mov     [rsp+50h+lpData], r14; lpData
0x18009e57f  xor     r8d, r8d; Reserved
0x18009e582  call    cs:__imp_RegSetValueExW
0x18009e588  mov     ebx, eax
0x18009e58a  test    eax, eax
0x18009e58c  jnz     short loc_18009E5B8
0x18009e58e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e595  cmp     rcx, r13
0x18009e598  jz      short loc_18009E5F2
0x18009e59a  test    byte ptr [rcx+1Ch], 4
0x18009e59e  jz      short loc_18009E5F2
0x18009e5a0  mov     rcx, [rcx+10h]
0x18009e5a4  lea     edx, [rax+19h]
0x18009e5a7  mov     r9, r14
0x18009e5aa  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e5b1  call    WPP_SF_S
0x18009e5b6  jmp     short loc_18009E5F2
0x18009e5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e5bf  cmp     rcx, r13
0x18009e5c2  jz      short loc_18009E5F2
0x18009e5c4  test    byte ptr [rcx+1Ch], 1
0x18009e5c8  jz      short loc_18009E5F2
0x18009e5ca  test    eax, eax
0x18009e5cc  jle     short loc_18009E5D6
0x18009e5ce  movzx   eax, ax
0x18009e5d1  or      eax, 80070000h
0x18009e5d6  mov     rcx, [rcx+10h]
0x18009e5da  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e5e1  mov     edx, 1Ah
0x18009e5e6  mov     dword ptr [rsp+50h+lpData], eax
0x18009e5ea  mov     r9, r14
0x18009e5ed  call    WPP_SF_Sd
0x18009e5f2  test    byte ptr [rbp+arg_8], 20h
0x18009e5f6  jz      short loc_18009E623
0x18009e5f8  mov     eax, [rdi+8]
0x18009e5fb  lea     rdx, aDefaultgateway_0; "DefaultGatewayMac"
0x18009e602  mov     rcx, [rbp+hKey]; hKey
0x18009e606  mov     r9d, 3; dwType
0x18009e60c  mov     [rsp+50h+cbData], eax; cbData
0x18009e610  xor     r8d, r8d; Reserved
0x18009e613  mov     rax, [rdi]
0x18009e616  mov     [rsp+50h+lpData], rax; lpData
0x18009e61b  call    cs:__imp_RegSetValueExW
0x18009e621  mov     ebx, eax
0x18009e623  mov     rcx, [rbp+hKey]; hKey
0x18009e627  call    cs:__imp_RegCloseKey
0x18009e62d  test    ebx, ebx
0x18009e62f  jle     short loc_18009E666
0x18009e631  movzx   ebx, bx
0x18009e634  or      ebx, 80070000h
0x18009e63a  jmp     short loc_18009E666
0x18009e63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e643  cmp     rcx, r13
0x18009e646  jz      short loc_18009E690
0x18009e648  test    byte ptr [rcx+1Ch], 1
0x18009e64c  jz      short loc_18009E66D
0x18009e64e  mov     rcx, [rcx+10h]
0x18009e652  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e659  mov     edx, 1Bh
0x18009e65e  mov     r9d, eax
0x18009e661  call    WPP_SF_d
0x18009e666  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e66d  cmp     rcx, r13
0x18009e670  jz      short loc_18009E690
0x18009e672  test    byte ptr [rcx+1Ch], 8
0x18009e676  jz      short loc_18009E690
0x18009e678  mov     rcx, [rcx+10h]
0x18009e67c  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e683  mov     edx, 1Ch
0x18009e688  mov     r9d, ebx
0x18009e68b  call    WPP_SF_d
0x18009e690  mov     eax, ebx
0x18009e692  mov     rcx, [rbp+var_10]
0x18009e696  xor     rcx, rsp; StackCookie
0x18009e699  call    __security_check_cookie
0x18009e69e  add     rsp, 50h
0x18009e6a2  pop     r15
0x18009e6a4  pop     r14
0x18009e6a6  pop     r13
0x18009e6a8  pop     r12
0x18009e6aa  pop     rdi
0x18009e6ab  pop     rbx
0x18009e6ac  pop     rbp
0x18009e6ad  retn
```
