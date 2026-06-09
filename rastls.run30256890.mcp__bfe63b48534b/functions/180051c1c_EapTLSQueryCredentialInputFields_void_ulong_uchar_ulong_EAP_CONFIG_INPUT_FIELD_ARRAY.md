# EapTLSQueryCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x180051c1c`
- end: `0x180052190`
- name: `?EapTLSQueryCredentialInputFields@@YAKPEAXKPEAEKPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `1396`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005d6e0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180033f40`
- `0x180038270`
- `0x180038e4c`
- `0x180038e64`
- `0x180051c1c`
- `0x180052e60`
- `0x180054344`
- `0x180076a1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051ecf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052022`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051ecf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180052022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051e4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051f33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051f91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052082`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051e4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051f33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051f91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052157`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052157`

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
  unsigned int UserData; // eax
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 791, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
        IsUsingRegistryCert);
    goto LABEL_46;
  }
  if ( v37 )
  {
    IsUsingRegistryCert = -2143158246;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 793, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 794, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v14);
      v15 = WPP_GLOBAL_Control;
    }
    v16 = 0;
    v13 = 1;
    IsUsingRegistryCert = 0;
    if ( v15 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v15 + 2), 795, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v21);
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
0x180051c1c  mov     [rsp-8+arg_0], rbx
0x180051c21  push    rbp
0x180051c22  push    rsi
0x180051c23  push    rdi
0x180051c24  push    r12
0x180051c26  push    r13
0x180051c28  push    r14
0x180051c2a  push    r15
0x180051c2c  lea     rbp, [rsp-3B0h]
0x180051c34  sub     rsp, 4C0h
0x180051c3b  mov     rax, cs:__security_cookie
0x180051c42  xor     rax, rsp
0x180051c45  mov     [rbp+3E0h+var_40], rax
0x180051c4c  mov     rdi, [rbp+3E0h+arg_20]
0x180051c53  lea     rcx, [rbp+3E0h+var_240]; void *
0x180051c5a  mov     r15, r8
0x180051c5d  mov     r14d, edx
0x180051c60  mov     ebx, 200h
0x180051c65  xor     esi, esi
0x180051c67  mov     r8d, ebx; Size
0x180051c6a  mov     [rbp+3E0h+var_460], esi
0x180051c6d  xor     edx, edx; Val
0x180051c6f  mov     r12d, r9d
0x180051c72  call    memset_0
0x180051c77  mov     r8d, ebx; Size
0x180051c7a  lea     rcx, [rbp+3E0h+Buffer]; void *
0x180051c7e  xor     edx, edx; Val
0x180051c80  call    memset_0
0x180051c85  mov     r13d, esi
0x180051c88  mov     [rbp+3E0h+hMem], rsi
0x180051c8c  mov     [rbp+3E0h+var_448], rsi
0x180051c90  mov     [rbp+3E0h+Src], rsi
0x180051c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180051c9b  lea     rax, WPP_GLOBAL_Control
0x180051ca2  cmp     rcx, rax
0x180051ca5  jz      short loc_180051CBC
0x180051ca7  mov     rcx, [rcx+10h]
0x180051cab  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051cb2  mov     edx, 317h
0x180051cb7  call    WPP_SF_
0x180051cbc  test    rdi, rdi
0x180051cbf  jnz     short loc_180051CC9
0x180051cc1  lea     ebx, [rdi+57h]
0x180051cc4  jmp     loc_180052125
0x180051cc9  xorps   xmm0, xmm0
0x180051ccc  lea     r9, [rbp+3E0h+var_460]; int *
0x180051cd0  mov     r8, r15; unsigned __int8 *
0x180051cd3  mov     edx, r12d; unsigned int
0x180051cd6  mov     ecx, r14d; unsigned int
0x180051cd9  movups  xmmword ptr [rdi], xmm0
0x180051cdc  call    ?EapTlsIsUsingRegistryCert@@YAKKKPEAEPEAH@Z; EapTlsIsUsingRegistryCert(ulong,ulong,uchar *,int *)
0x180051ce1  mov     ebx, eax
0x180051ce3  test    eax, eax
0x180051ce5  jz      short loc_180051D1B
0x180051ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180051cee  lea     rax, WPP_GLOBAL_Control
0x180051cf5  cmp     rcx, rax
0x180051cf8  jz      loc_180052125
0x180051cfe  mov     rcx, [rcx+10h]
0x180051d02  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051d09  mov     edx, 318h
0x180051d0e  mov     r9d, ebx
0x180051d11  call    WPP_SF_d
0x180051d16  jmp     loc_180052125
0x180051d1b  cmp     [rbp+3E0h+var_460], esi
0x180051d1e  jz      short loc_180051D56
0x180051d20  mov     ebx, 8042001Ah
0x180051d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d2c  lea     rax, WPP_GLOBAL_Control
0x180051d33  cmp     rcx, rax
0x180051d36  jz      loc_180052125
0x180051d3c  mov     rcx, [rcx+10h]
0x180051d40  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051d47  mov     edx, 319h
0x180051d4c  call    WPP_SF_
0x180051d51  jmp     loc_180052125
0x180051d56  lea     r8, [rbp+3E0h+hMem]; struct _EAPTLS_USER_PROPERTIES **
0x180051d5a  xor     edx, edx; unsigned int
0x180051d5c  xor     ecx, ecx; Src
0x180051d5e  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180051d63  mov     r13, [rbp+3E0h+hMem]
0x180051d67  mov     ebx, eax
0x180051d69  test    eax, eax
0x180051d6b  jnz     loc_180052125
0x180051d71  lea     esi, [rax+2]
0x180051d74  mov     dword ptr [r13+0Ch], 4
0x180051d7c  lea     rax, [rbp+3E0h+Src]
0x180051d80  or      r14d, esi
0x180051d83  mov     [rsp+4F0h+var_478], rax
0x180051d88  lea     r8d, [rbx+1]
0x180051d8c  lea     rax, [rbp+3E0h+var_460]
0x180051d90  mov     r9d, r14d
0x180051d93  mov     [rsp+4F0h+var_480], rax
0x180051d98  lea     rax, [rbp+3E0h+var_448]
0x180051d9c  mov     [rsp+4F0h+var_488], rax
0x180051da1  mov     eax, [r13+8]
0x180051da5  mov     [rsp+4F0h+var_490], eax
0x180051da9  mov     [rsp+4F0h+var_498], r13
0x180051dae  mov     [rsp+4F0h+var_4A0], r12d
0x180051db3  xor     r12d, r12d
0x180051db6  mov     [rsp+4F0h+var_4A8], r15
0x180051dbb  mov     [rsp+4F0h+var_4B0], r12d
0x180051dc0  mov     [rsp+4F0h+var_4B8], r12
0x180051dc5  mov     [rsp+4F0h+var_4C0], r12
0x180051dca  mov     [rsp+4F0h+var_4C8], r12
0x180051dcf  call    EapTlsInvokeIdentityUI
0x180051dd4  mov     ebx, eax
0x180051dd6  test    eax, eax
0x180051dd8  jz      short loc_180051E33
0x180051dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180051de1  lea     r15, WPP_GLOBAL_Control
0x180051de8  cmp     rcx, r15
0x180051deb  jz      short loc_180051E0C
0x180051ded  mov     rcx, [rcx+10h]
0x180051df1  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051df8  mov     edx, 31Ah
0x180051dfd  mov     r9d, eax
0x180051e00  call    WPP_SF_d
0x180051e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e0c  mov     r14d, r12d
0x180051e0f  mov     esi, 1
0x180051e14  mov     ebx, r12d
0x180051e17  cmp     rcx, r15
0x180051e1a  jz      short loc_180051E40
0x180051e1c  mov     rcx, [rcx+10h]
0x180051e20  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051e27  mov     edx, 31Bh
0x180051e2c  call    WPP_SF_
0x180051e31  jmp     short loc_180051E40
0x180051e33  mov     r14d, 1
0x180051e39  lea     r15, WPP_GLOBAL_Control
0x180051e40  mov     eax, esi
0x180051e42  mov     ecx, 40h ; '@'; uFlags
0x180051e47  lea     rdx, [rax+rax*4]
0x180051e4b  shl     rdx, 3; uBytes
0x180051e4f  call    cs:__imp_LocalAlloc
0x180051e56  nop     dword ptr [rax+rax+00h]
0x180051e5b  mov     [rdi+8], rax
0x180051e5f  test    rax, rax
0x180051e62  jnz     short loc_180051E9F
0x180051e64  call    cs:__imp_GetLastError
0x180051e6b  nop     dword ptr [rax+rax+00h]
0x180051e70  mov     ebx, eax
0x180051e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e79  cmp     rcx, r15
0x180051e7c  jz      loc_180052121
0x180051e82  mov     edx, 31Ch
0x180051e87  mov     r9d, eax
0x180051e8a  mov     rcx, [rcx+10h]
0x180051e8e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180051e95  call    WPP_SF_d
0x180051e9a  jmp     loc_180052121
0x180051e9f  mov     [rdi+4], esi
0x180051ea2  mov     r15, r12
0x180051ea5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180051ea9  mov     dword ptr [rdi], 1
0x180051eaf  cmp     r14d, 1
0x180051eb3  jnz     loc_180052009
0x180051eb9  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180051ec0  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x180051ec4  mov     r9d, 100h; cchBufferMax
0x180051eca  mov     edx, 6A5h; uID
0x180051ecf  call    cs:__imp_LoadStringW
0x180051ed6  nop     dword ptr [rax+rax+00h]
0x180051edb  test    eax, eax
0x180051edd  jnz     short loc_180051F11
0x180051edf  call    cs:__imp_GetLastError
0x180051ee6  nop     dword ptr [rax+rax+00h]
0x180051eeb  mov     ebx, eax
0x180051eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180051ef4  lea     rax, WPP_GLOBAL_Control
0x180051efb  cmp     rcx, rax
0x180051efe  jz      loc_180052121
0x180051f04  mov     edx, 31Dh
0x180051f09  mov     r9d, ebx
0x180051f0c  jmp     loc_180051E8A
0x180051f11  lea     rcx, [rbp+3E0h+Buffer]
0x180051f15  mov     rax, rsi
0x180051f18  inc     rax
0x180051f1b  cmp     [rcx+rax*2], r12w
0x180051f20  jnz     short loc_180051F18
0x180051f22  lea     eax, ds:2[rax*2]
0x180051f29  mov     ecx, 40h ; '@'; uFlags
0x180051f2e  mov     edx, eax; uBytes
0x180051f30  mov     r14d, eax
0x180051f33  call    cs:__imp_LocalAlloc
0x180051f3a  nop     dword ptr [rax+rax+00h]
0x180051f3f  mov     rcx, [rdi+8]
0x180051f43  mov     [rcx+10h], rax
0x180051f47  mov     rax, [rdi+8]
0x180051f4b  mov     rcx, [rax+10h]; void *
0x180051f4f  test    rcx, rcx
0x180051f52  jnz     short loc_180051F67
0x180051f54  call    cs:__imp_GetLastError
0x180051f5b  nop     dword ptr [rax+rax+00h]
0x180051f60  mov     ebx, eax
0x180051f62  jmp     loc_180052121
0x180051f67  mov     r8, r14; Size
0x180051f6a  lea     rdx, [rbp+3E0h+Buffer]; Src
0x180051f6e  call    memcpy_0
0x180051f73  mov     rax, [rbp+3E0h+Src]
0x180051f77  mov     rdx, rsi
0x180051f7a  inc     rdx
0x180051f7d  cmp     [rax+rdx*2], r12w
0x180051f82  jnz     short loc_180051F7A
0x180051f84  lea     rdx, ds:2[rdx*2]; uBytes
0x180051f8c  mov     ecx, 40h ; '@'; uFlags
0x180051f91  call    cs:__imp_LocalAlloc
0x180051f98  nop     dword ptr [rax+rax+00h]
0x180051f9d  mov     rcx, [rdi+8]
0x180051fa1  mov     [rcx+18h], rax
0x180051fa5  mov     rax, [rdi+8]
0x180051fa9  mov     rcx, [rax+18h]; void *
0x180051fad  test    rcx, rcx
0x180051fb0  jz      short loc_180051F54
0x180051fb2  mov     rdx, [rbp+3E0h+Src]; Src
0x180051fb6  mov     r8, rsi
0x180051fb9  inc     r8
0x180051fbc  cmp     [rdx+r8*2], r12w
0x180051fc1  jnz     short loc_180051FB9
0x180051fc3  lea     r8, ds:2[r8*2]; Size
0x180051fcb  call    memcpy_0
0x180051fd0  mov     rax, [rdi+8]
0x180051fd4  mov     r15d, 1
0x180051fda  mov     dword ptr [rax], 28h ; '('
0x180051fe0  mov     rax, [rdi+8]
0x180051fe4  mov     [rax+20h], r12d
0x180051fe8  mov     rax, [rdi+8]
0x180051fec  mov     dword ptr [rax+24h], 400h
0x180051ff3  mov     rax, [rdi+8]
0x180051ff7  mov     dword ptr [rax+4], 7
0x180051ffe  mov     rax, [rdi+8]
0x180052002  mov     dword ptr [rax+8], 4
0x180052009  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180052010  lea     r8, [rbp+3E0h+var_240]; lpBuffer
0x180052017  mov     r9d, 100h; cchBufferMax
0x18005201d  mov     edx, 6A4h; uID
0x180052022  call    cs:__imp_LoadStringW
0x180052029  nop     dword ptr [rax+rax+00h]
0x18005202e  test    eax, eax
0x180052030  jnz     short loc_180052061
0x180052032  call    cs:__imp_GetLastError
0x180052039  nop     dword ptr [rax+rax+00h]
0x18005203e  mov     ebx, eax
0x180052040  mov     rcx, cs:WPP_GLOBAL_Control
0x180052047  lea     rax, WPP_GLOBAL_Control
0x18005204e  cmp     rcx, rax
0x180052051  jz      loc_180052121
0x180052057  mov     edx, 31Eh
0x18005205c  jmp     loc_180051F09
0x180052061  lea     rax, [rbp+3E0h+var_240]
0x180052068  inc     rsi
0x18005206b  cmp     [rax+rsi*2], r12w
0x180052070  jnz     short loc_180052068
0x180052072  lea     eax, ds:2[rsi*2]
0x180052079  mov     ecx, 40h ; '@'; uFlags
0x18005207e  mov     edx, eax; uBytes
0x180052080  mov     esi, eax
0x180052082  call    cs:__imp_LocalAlloc
0x180052089  nop     dword ptr [rax+rax+00h]
0x18005208e  mov     rcx, [rdi+8]
0x180052092  lea     r9, [r15+r15*4]
0x180052096  mov     [rcx+r9*8+10h], rax
0x18005209b  mov     rax, [rdi+8]
0x18005209f  cmp     [rax+r9*8+10h], r12
0x1800520a4  jnz     short loc_1800520D1
0x1800520a6  call    cs:__imp_GetLastError
0x1800520ad  nop     dword ptr [rax+rax+00h]
0x1800520b2  mov     ebx, eax
0x1800520b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520bb  lea     rax, WPP_GLOBAL_Control
0x1800520c2  cmp     rcx, rax
0x1800520c5  jz      short loc_180052121
0x1800520c7  mov     edx, 31Fh
0x1800520cc  jmp     loc_180051F09
0x1800520d1  mov     dword ptr [rax+r9*8], 28h ; '('
0x1800520d9  lea     rdx, [rbp+3E0h+var_240]; Src
0x1800520e0  mov     rax, [rdi+8]
0x1800520e4  mov     r8, rsi; Size
0x1800520e7  mov     [rax+r9*8+20h], r12d
0x1800520ec  mov     rax, [rdi+8]
0x1800520f0  mov     dword ptr [rax+r9*8+24h], 400h
0x1800520f9  mov     rax, [rdi+8]
0x1800520fd  mov     dword ptr [rax+r9*8+4], 4
0x180052106  mov     rax, [rdi+8]
0x18005210a  mov     dword ptr [rax+r9*8+8], 3
0x180052113  mov     rcx, [rdi+8]
0x180052117  mov     rcx, [rcx+r9*8+10h]; void *
0x18005211c  call    memcpy_0
0x180052121  test    ebx, ebx
0x180052123  jz      short loc_180052134
0x180052125  lea     rdx, RasEapFreeMemory; unsigned int (*)(unsigned __int8 *)
0x18005212c  mov     rcx, rdi; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18005212f  call    ?FreeEAPConfigInputFieldArray@@YAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x180052134  mov     rcx, [rbp+3E0h+Src]; hMem
0x180052138  call    cs:__imp_LocalFree
0x18005213f  nop     dword ptr [rax+rax+00h]
0x180052144  mov     rcx, r13; hMem
0x180052147  call    cs:__imp_LocalFree
0x18005214e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
