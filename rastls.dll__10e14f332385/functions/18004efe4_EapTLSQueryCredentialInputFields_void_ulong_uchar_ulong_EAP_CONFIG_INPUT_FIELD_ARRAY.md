# EapTLSQueryCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x18004efe4`
- end: `0x18004f500`
- name: `?EapTLSQueryCredentialInputFields@@YAKPEAXKPEAEKPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `1308`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005a330`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x1800316cc`
- `0x180035680`
- `0x18003623c`
- `0x180036254`
- `0x18004efe4`
- `0x180050150`
- `0x1800515ac`
- `0x180071b98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f28b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f3bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f28b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004f3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f42f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f217`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f2e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f332`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f411`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f217`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f2e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f332`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4ce`

## pseudocode

```c
__int64 __fastcall EapTLSQueryCredentialInputFields(
        void *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5)
{
  HLOCAL v8; // r13
  DWORD IsUsingRegistryCert; // ebx
  DWORD UserData; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  DWORD v13; // esi
  DWORD v14; // eax
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  int v16; // r14d
  EAP_CONFIG_INPUT_FIELD_DATA *v17; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // r15
  __int64 v23; // rsi
  __int64 v24; // rax
  SIZE_T v25; // r14
  LPWSTR pwszLabel; // rcx
  __int64 v27; // rdx
  LPWSTR pwszData; // rcx
  __int64 v29; // r8
  SIZE_T v30; // rdx
  size_t v31; // rsi
  EAP_CONFIG_INPUT_FIELD_DATA *pFields; // rax
  int v34; // [rsp+20h] [rbp-F0h]
  void *v35; // [rsp+80h] [rbp-90h]
  HKEY v36; // [rsp+88h] [rbp-88h]
  int v37; // [rsp+90h] [rbp-80h] BYREF
  void *Src; // [rsp+98h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-70h] BYREF
  HLOCAL v40; // [rsp+A8h] [rbp-68h] BYREF
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-60h] BYREF
  WCHAR v42[256]; // [rsp+2B0h] [rbp+1A0h] BYREF

  v37 = 0;
  memset_0(v42, 0, sizeof(v42));
  memset_0(Buffer, 0, sizeof(Buffer));
  v8 = 0;
  hMem = 0;
  v40 = 0;
  Src = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 791, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  if ( !a5 )
  {
    IsUsingRegistryCert = 87;
    goto LABEL_46;
  }
  *a5 = 0;
  IsUsingRegistryCert = EapTlsIsUsingRegistryCert(a2, a4, a3, &v37);
  if ( IsUsingRegistryCert )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        792,
        &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
        IsUsingRegistryCert);
    goto LABEL_46;
  }
  if ( v37 )
  {
    IsUsingRegistryCert = -2143158246;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 793, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    goto LABEL_46;
  }
  UserData = EapTlsReadUserData(0, 0, (struct _EAPTLS_USER_PROPERTIES **)&hMem);
  v8 = hMem;
  IsUsingRegistryCert = UserData;
  if ( UserData )
  {
LABEL_46:
    FreeEAPConfigInputFieldArray(a5, RasEapFreeMemory);
    goto LABEL_47;
  }
  v13 = 2;
  *((_DWORD *)hMem + 3) = 4;
  v14 = EapTlsInvokeIdentityUI(
          v12,
          v11,
          1,
          a2 | 2,
          v34,
          0,
          0,
          0,
          0,
          a3,
          a4,
          (unsigned __int8 *)v8,
          *((_DWORD *)v8 + 2),
          &v40,
          &v37,
          (unsigned __int16 **)&Src,
          v35,
          v36);
  IsUsingRegistryCert = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 794, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v14);
      v15 = WPP_GLOBAL_Control;
    }
    v16 = 0;
    v13 = 1;
    IsUsingRegistryCert = 0;
    if ( v15 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v15 + 2), 795, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  }
  else
  {
    v16 = 1;
  }
  v17 = (EAP_CONFIG_INPUT_FIELD_DATA *)LocalAlloc(0x40u, 40LL * v13);
  a5->pFields = v17;
  if ( !v17 )
  {
    LastError = GetLastError();
    IsUsingRegistryCert = LastError;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_45;
    v20 = 796;
    v21 = LastError;
    goto LABEL_21;
  }
  a5->dwNumberOfFields = v13;
  v22 = 0;
  v23 = -1;
  a5->dwVersion = 1;
  if ( v16 == 1 )
  {
    if ( !LoadStringW(g_hInstance, 0x6A5u, Buffer, 256) )
    {
      IsUsingRegistryCert = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v20 = 797;
LABEL_26:
        v21 = IsUsingRegistryCert;
LABEL_21:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v21);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    v24 = -1;
    do
      ++v24;
    while ( Buffer[v24] );
    v25 = (unsigned int)(2 * v24 + 2);
    a5->pFields->pwszLabel = (LPWSTR)LocalAlloc(0x40u, v25);
    pwszLabel = a5->pFields->pwszLabel;
    if ( !pwszLabel )
      goto LABEL_30;
    memcpy_0(pwszLabel, Buffer, v25);
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)Src + v27) );
    a5->pFields->pwszData = (LPWSTR)LocalAlloc(0x40u, 2 * v27 + 2);
    pwszData = a5->pFields->pwszData;
    if ( !pwszData )
    {
LABEL_30:
      IsUsingRegistryCert = GetLastError();
      goto LABEL_45;
    }
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)Src + v29) );
    memcpy_0(pwszData, Src, 2 * v29 + 2);
    v22 = 1;
    a5->pFields->dwSize = 40;
    a5->pFields->dwMinDataLength = 0;
    a5->pFields->dwMaxDataLength = 1024;
    a5->pFields->Type = EapConfigSmartCardUsername;
    a5->pFields->dwFlagProps = 4;
  }
  if ( LoadStringW(g_hInstance, 0x6A4u, v42, 256) )
  {
    do
      ++v23;
    while ( v42[v23] );
    v30 = (unsigned int)(2 * v23 + 2);
    v31 = v30;
    a5->pFields[v22].pwszLabel = (LPWSTR)LocalAlloc(0x40u, v30);
    pFields = a5->pFields;
    if ( pFields[v22].pwszLabel )
    {
      pFields[v22].dwSize = 40;
      a5->pFields[v22].dwMinDataLength = 0;
      a5->pFields[v22].dwMaxDataLength = 1024;
      a5->pFields[v22].Type = EapConfigInputPin;
      a5->pFields[v22].dwFlagProps = 3;
      memcpy_0(a5->pFields[v22].pwszLabel, v42, v31);
    }
    else
    {
      IsUsingRegistryCert = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v20 = 799;
        goto LABEL_26;
      }
    }
  }
  else
  {
    IsUsingRegistryCert = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v20 = 798;
      goto LABEL_26;
    }
  }
LABEL_45:
  if ( IsUsingRegistryCert )
    goto LABEL_46;
LABEL_47:
  LocalFree(Src);
  LocalFree(v8);
  LocalFree(v40);
  return IsUsingRegistryCert;
}

```

## disassembly

```asm
0x18004efe4  mov     [rsp-8+arg_0], rbx
0x18004efe9  push    rbp
0x18004efea  push    rsi
0x18004efeb  push    rdi
0x18004efec  push    r12
0x18004efee  push    r13
0x18004eff0  push    r14
0x18004eff2  push    r15
0x18004eff4  lea     rbp, [rsp-3B0h]
0x18004effc  sub     rsp, 4C0h
0x18004f003  mov     rax, cs:__security_cookie
0x18004f00a  xor     rax, rsp
0x18004f00d  mov     [rbp+3E0h+var_40], rax
0x18004f014  mov     rdi, [rbp+3E0h+arg_20]
0x18004f01b  lea     rcx, [rbp+3E0h+var_240]; void *
0x18004f022  mov     r15, r8
0x18004f025  mov     r14d, edx
0x18004f028  mov     ebx, 200h
0x18004f02d  xor     esi, esi
0x18004f02f  mov     r8d, ebx; Size
0x18004f032  mov     [rbp+3E0h+var_460], esi
0x18004f035  xor     edx, edx; Val
0x18004f037  mov     r12d, r9d
0x18004f03a  call    memset_0
0x18004f03f  mov     r8d, ebx; Size
0x18004f042  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18004f046  xor     edx, edx; Val
0x18004f048  call    memset_0
0x18004f04d  mov     r13d, esi
0x18004f050  mov     [rbp+3E0h+hMem], rsi
0x18004f054  mov     [rbp+3E0h+var_448], rsi
0x18004f058  mov     [rbp+3E0h+Src], rsi
0x18004f05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f063  lea     rax, WPP_GLOBAL_Control
0x18004f06a  cmp     rcx, rax
0x18004f06d  jz      short loc_18004F084
0x18004f06f  mov     rcx, [rcx+10h]
0x18004f073  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f07a  mov     edx, 317h
0x18004f07f  call    WPP_SF_
0x18004f084  test    rdi, rdi
0x18004f087  jnz     short loc_18004F091
0x18004f089  lea     ebx, [rdi+57h]
0x18004f08c  jmp     loc_18004F4A8
0x18004f091  xorps   xmm0, xmm0
0x18004f094  lea     r9, [rbp+3E0h+var_460]; int *
0x18004f098  mov     r8, r15; unsigned __int8 *
0x18004f09b  mov     edx, r12d; unsigned int
0x18004f09e  mov     ecx, r14d; unsigned int
0x18004f0a1  movups  xmmword ptr [rdi], xmm0
0x18004f0a4  call    ?EapTlsIsUsingRegistryCert@@YAKKKPEAEPEAH@Z; EapTlsIsUsingRegistryCert(ulong,ulong,uchar *,int *)
0x18004f0a9  mov     ebx, eax
0x18004f0ab  test    eax, eax
0x18004f0ad  jz      short loc_18004F0E3
0x18004f0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0b6  lea     rax, WPP_GLOBAL_Control
0x18004f0bd  cmp     rcx, rax
0x18004f0c0  jz      loc_18004F4A8
0x18004f0c6  mov     rcx, [rcx+10h]
0x18004f0ca  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f0d1  mov     edx, 318h
0x18004f0d6  mov     r9d, ebx
0x18004f0d9  call    WPP_SF_d
0x18004f0de  jmp     loc_18004F4A8
0x18004f0e3  cmp     [rbp+3E0h+var_460], esi
0x18004f0e6  jz      short loc_18004F11E
0x18004f0e8  mov     ebx, 8042001Ah
0x18004f0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0f4  lea     rax, WPP_GLOBAL_Control
0x18004f0fb  cmp     rcx, rax
0x18004f0fe  jz      loc_18004F4A8
0x18004f104  mov     rcx, [rcx+10h]
0x18004f108  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f10f  mov     edx, 319h
0x18004f114  call    WPP_SF_
0x18004f119  jmp     loc_18004F4A8
0x18004f11e  lea     r8, [rbp+3E0h+hMem]; struct _EAPTLS_USER_PROPERTIES **
0x18004f122  xor     edx, edx; unsigned int
0x18004f124  xor     ecx, ecx; Src
0x18004f126  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x18004f12b  mov     r13, [rbp+3E0h+hMem]
0x18004f12f  mov     ebx, eax
0x18004f131  test    eax, eax
0x18004f133  jnz     loc_18004F4A8
0x18004f139  lea     esi, [rax+2]
0x18004f13c  mov     dword ptr [r13+0Ch], 4
0x18004f144  lea     rax, [rbp+3E0h+Src]
0x18004f148  or      r14d, esi
0x18004f14b  mov     [rsp+4F0h+var_478], rax
0x18004f150  lea     r8d, [rbx+1]
0x18004f154  lea     rax, [rbp+3E0h+var_460]
0x18004f158  mov     r9d, r14d
0x18004f15b  mov     [rsp+4F0h+var_480], rax
0x18004f160  lea     rax, [rbp+3E0h+var_448]
0x18004f164  mov     [rsp+4F0h+var_488], rax
0x18004f169  mov     eax, [r13+8]
0x18004f16d  mov     [rsp+4F0h+var_490], eax
0x18004f171  mov     [rsp+4F0h+var_498], r13
0x18004f176  mov     [rsp+4F0h+var_4A0], r12d
0x18004f17b  xor     r12d, r12d
0x18004f17e  mov     [rsp+4F0h+var_4A8], r15
0x18004f183  mov     [rsp+4F0h+var_4B0], r12d
0x18004f188  mov     [rsp+4F0h+var_4B8], r12
0x18004f18d  mov     [rsp+4F0h+var_4C0], r12
0x18004f192  mov     [rsp+4F0h+var_4C8], r12
0x18004f197  call    EapTlsInvokeIdentityUI
0x18004f19c  mov     ebx, eax
0x18004f19e  test    eax, eax
0x18004f1a0  jz      short loc_18004F1FB
0x18004f1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1a9  lea     r15, WPP_GLOBAL_Control
0x18004f1b0  cmp     rcx, r15
0x18004f1b3  jz      short loc_18004F1D4
0x18004f1b5  mov     rcx, [rcx+10h]
0x18004f1b9  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f1c0  mov     edx, 31Ah
0x18004f1c5  mov     r9d, eax
0x18004f1c8  call    WPP_SF_d
0x18004f1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1d4  mov     r14d, r12d
0x18004f1d7  mov     esi, 1
0x18004f1dc  mov     ebx, r12d
0x18004f1df  cmp     rcx, r15
0x18004f1e2  jz      short loc_18004F208
0x18004f1e4  mov     rcx, [rcx+10h]
0x18004f1e8  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f1ef  mov     edx, 31Bh
0x18004f1f4  call    WPP_SF_
0x18004f1f9  jmp     short loc_18004F208
0x18004f1fb  mov     r14d, 1
0x18004f201  lea     r15, WPP_GLOBAL_Control
0x18004f208  mov     eax, esi
0x18004f20a  mov     ecx, 40h ; '@'; uFlags
0x18004f20f  lea     rdx, [rax+rax*4]
0x18004f213  shl     rdx, 3; uBytes
0x18004f217  call    cs:__imp_LocalAlloc
0x18004f21d  mov     [rdi+8], rax
0x18004f221  test    rax, rax
0x18004f224  jnz     short loc_18004F25B
0x18004f226  call    cs:__imp_GetLastError
0x18004f22c  mov     ebx, eax
0x18004f22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f235  cmp     rcx, r15
0x18004f238  jz      loc_18004F4A4
0x18004f23e  mov     edx, 31Ch
0x18004f243  mov     r9d, eax
0x18004f246  mov     rcx, [rcx+10h]
0x18004f24a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004f251  call    WPP_SF_d
0x18004f256  jmp     loc_18004F4A4
0x18004f25b  mov     [rdi+4], esi
0x18004f25e  mov     r15, r12
0x18004f261  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004f265  mov     dword ptr [rdi], 1
0x18004f26b  cmp     r14d, 1
0x18004f26f  jnz     loc_18004F3A4
0x18004f275  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18004f27c  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x18004f280  mov     r9d, 100h; cchBufferMax
0x18004f286  mov     edx, 6A5h; uID
0x18004f28b  call    cs:__imp_LoadStringW
0x18004f291  test    eax, eax
0x18004f293  jnz     short loc_18004F2BE
0x18004f295  call    cs:__imp_GetLastError
0x18004f29b  mov     ebx, eax
0x18004f29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f2a4  lea     rax, WPP_GLOBAL_Control
0x18004f2ab  cmp     rcx, rax
0x18004f2ae  jz      loc_18004F4A4
0x18004f2b4  mov     edx, 31Dh
0x18004f2b9  mov     r9d, ebx
0x18004f2bc  jmp     short loc_18004F246
0x18004f2be  lea     rcx, [rbp+3E0h+Buffer]
0x18004f2c2  mov     rax, rsi
0x18004f2c5  inc     rax
0x18004f2c8  cmp     [rcx+rax*2], r12w
0x18004f2cd  jnz     short loc_18004F2C5
0x18004f2cf  lea     eax, ds:2[rax*2]
0x18004f2d6  mov     ecx, 40h ; '@'; uFlags
0x18004f2db  mov     edx, eax; uBytes
0x18004f2dd  mov     r14d, eax
0x18004f2e0  call    cs:__imp_LocalAlloc
0x18004f2e6  mov     rcx, [rdi+8]
0x18004f2ea  mov     [rcx+10h], rax
0x18004f2ee  mov     rax, [rdi+8]
0x18004f2f2  mov     rcx, [rax+10h]; void *
0x18004f2f6  test    rcx, rcx
0x18004f2f9  jnz     short loc_18004F308
0x18004f2fb  call    cs:__imp_GetLastError
0x18004f301  mov     ebx, eax
0x18004f303  jmp     loc_18004F4A4
0x18004f308  mov     r8, r14; Size
0x18004f30b  lea     rdx, [rbp+3E0h+Buffer]; Src
0x18004f30f  call    memcpy_0
0x18004f314  mov     rax, [rbp+3E0h+Src]
0x18004f318  mov     rdx, rsi
0x18004f31b  inc     rdx
0x18004f31e  cmp     [rax+rdx*2], r12w
0x18004f323  jnz     short loc_18004F31B
0x18004f325  lea     rdx, ds:2[rdx*2]; uBytes
0x18004f32d  mov     ecx, 40h ; '@'; uFlags
0x18004f332  call    cs:__imp_LocalAlloc
0x18004f338  mov     rcx, [rdi+8]
0x18004f33c  mov     [rcx+18h], rax
0x18004f340  mov     rax, [rdi+8]
0x18004f344  mov     rcx, [rax+18h]; void *
0x18004f348  test    rcx, rcx
0x18004f34b  jz      short loc_18004F2FB
0x18004f34d  mov     rdx, [rbp+3E0h+Src]; Src
0x18004f351  mov     r8, rsi
0x18004f354  inc     r8
0x18004f357  cmp     [rdx+r8*2], r12w
0x18004f35c  jnz     short loc_18004F354
0x18004f35e  lea     r8, ds:2[r8*2]; Size
0x18004f366  call    memcpy_0
0x18004f36b  mov     rax, [rdi+8]
0x18004f36f  mov     r15d, 1
0x18004f375  mov     dword ptr [rax], 28h ; '('
0x18004f37b  mov     rax, [rdi+8]
0x18004f37f  mov     [rax+20h], r12d
0x18004f383  mov     rax, [rdi+8]
0x18004f387  mov     dword ptr [rax+24h], 400h
0x18004f38e  mov     rax, [rdi+8]
0x18004f392  mov     dword ptr [rax+4], 7
0x18004f399  mov     rax, [rdi+8]
0x18004f39d  mov     dword ptr [rax+8], 4
0x18004f3a4  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18004f3ab  lea     r8, [rbp+3E0h+var_240]; lpBuffer
0x18004f3b2  mov     r9d, 100h; cchBufferMax
0x18004f3b8  mov     edx, 6A4h; uID
0x18004f3bd  call    cs:__imp_LoadStringW
0x18004f3c3  test    eax, eax
0x18004f3c5  jnz     short loc_18004F3F0
0x18004f3c7  call    cs:__imp_GetLastError
0x18004f3cd  mov     ebx, eax
0x18004f3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f3d6  lea     rax, WPP_GLOBAL_Control
0x18004f3dd  cmp     rcx, rax
0x18004f3e0  jz      loc_18004F4A4
0x18004f3e6  mov     edx, 31Eh
0x18004f3eb  jmp     loc_18004F2B9
0x18004f3f0  lea     rax, [rbp+3E0h+var_240]
0x18004f3f7  inc     rsi
0x18004f3fa  cmp     [rax+rsi*2], r12w
0x18004f3ff  jnz     short loc_18004F3F7
0x18004f401  lea     eax, ds:2[rsi*2]
0x18004f408  mov     ecx, 40h ; '@'; uFlags
0x18004f40d  mov     edx, eax; uBytes
0x18004f40f  mov     esi, eax
0x18004f411  call    cs:__imp_LocalAlloc
0x18004f417  mov     rcx, [rdi+8]
0x18004f41b  lea     r9, [r15+r15*4]
0x18004f41f  mov     [rcx+r9*8+10h], rax
0x18004f424  mov     rax, [rdi+8]
0x18004f428  cmp     [rax+r9*8+10h], r12
0x18004f42d  jnz     short loc_18004F454
0x18004f42f  call    cs:__imp_GetLastError
0x18004f435  mov     ebx, eax
0x18004f437  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f43e  lea     rax, WPP_GLOBAL_Control
0x18004f445  cmp     rcx, rax
0x18004f448  jz      short loc_18004F4A4
0x18004f44a  mov     edx, 31Fh
0x18004f44f  jmp     loc_18004F2B9
0x18004f454  mov     dword ptr [rax+r9*8], 28h ; '('
0x18004f45c  lea     rdx, [rbp+3E0h+var_240]; Src
0x18004f463  mov     rax, [rdi+8]
0x18004f467  mov     r8, rsi; Size
0x18004f46a  mov     [rax+r9*8+20h], r12d
0x18004f46f  mov     rax, [rdi+8]
0x18004f473  mov     dword ptr [rax+r9*8+24h], 400h
0x18004f47c  mov     rax, [rdi+8]
0x18004f480  mov     dword ptr [rax+r9*8+4], 4
0x18004f489  mov     rax, [rdi+8]
0x18004f48d  mov     dword ptr [rax+r9*8+8], 3
0x18004f496  mov     rcx, [rdi+8]
0x18004f49a  mov     rcx, [rcx+r9*8+10h]; void *
0x18004f49f  call    memcpy_0
0x18004f4a4  test    ebx, ebx
0x18004f4a6  jz      short loc_18004F4B7
0x18004f4a8  lea     rdx, RasEapFreeMemory; unsigned int (*)(unsigned __int8 *)
0x18004f4af  mov     rcx, rdi; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18004f4b2  call    ?FreeEAPConfigInputFieldArray@@YAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x18004f4b7  mov     rcx, [rbp+3E0h+Src]; hMem
0x18004f4bb  call    cs:__imp_LocalFree
0x18004f4c1  mov     rcx, r13; hMem
0x18004f4c4  call    cs:__imp_LocalFree
0x18004f4ca  mov     rcx, [rbp+3E0h+var_448]; hMem
0x18004f4ce  call    cs:__imp_LocalFree
0x18004f4d4  mov     eax, ebx
0x18004f4d6  mov     rcx, [rbp+3E0h+var_40]
0x18004f4dd  xor     rcx, rsp; StackCookie
0x18004f4e0  call    __security_check_cookie
0x18004f4e5  mov     rbx, [rsp+4F0h+arg_0]
0x18004f4ed  add     rsp, 4C0h
0x18004f4f4  pop     r15
0x18004f4f6  pop     r14
0x18004f4f8  pop     r13
0x18004f4fa  pop     r12
0x18004f4fc  pop     rdi
  ... truncated ...
```
