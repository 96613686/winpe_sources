# PlaiForEachRegKey<_PLA_REGISTRY_CONTEXT *,long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *)>(HKEY__ *,ushort const *,long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *),long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *),_PLA_REGISTRY_CONTEXT *)

- ea: `0x18001e000`
- end: `0x18001e8dc`
- name: `??$PlaiForEachRegKey@PEAU_PLA_REGISTRY_CONTEXT@@P6AJPEAUHKEY__@@PEBGPEAU1@@Z@@YAJPEAUHKEY__@@PEBGP6AJ01PEAU_PLA_REGISTRY_CONTEXT@@@Z32@Z`
- size: `2268`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64 (__fastcall *)(HKEY, LPWSTR, struct _PLA_REGISTRY_CONTEXT *), __int64, struct _PLA_REGISTRY_CONTEXT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004bbb0`
- `0x1800f4804`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x18001e000`
- `0x18001e8e4`
- `0x18002b3a0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e59a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e59a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e06d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e06d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001e423`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001e423`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e8aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e8aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001e160`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001e160`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e270`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e262`

## pseudocode

```c
__int64 __fastcall PlaiForEachRegKey<_PLA_REGISTRY_CONTEXT *,long (*)(HKEY__ *,unsigned short const *,_PLA_REGISTRY_CONTEXT *)>(
        HKEY a1,
        const WCHAR *a2,
        __int64 (__fastcall *a3)(HKEY, LPWSTR, struct _PLA_REGISTRY_CONTEXT *),
        __int64 a4,
        struct _PLA_REGISTRY_CONTEXT *a5)
{
  DWORD v5; // r14d
  LSTATUS v6; // eax
  int v7; // eax
  signed int v8; // ebx
  __int64 v9; // rax
  struct _PLA_REGISTRY_CONTEXT **v10; // r9
  struct _PLA_REGISTRY_CONTEXT **v11; // rax
  LSTATUS v12; // eax
  int v13; // eax
  __int64 v14; // rax
  DWORD v15; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // r13
  HANDLE ProcessHeap; // rax
  WCHAR *v19; // rax
  int v20; // edx
  unsigned __int64 v21; // rcx
  WCHAR *v22; // r8
  __int64 v23; // rax
  unsigned int v24; // r12d
  DWORD v25; // esi
  LSTATUS v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 (__fastcall *v30)(HKEY, LPWSTR, struct _PLA_REGISTRY_CONTEXT *); // r13
  DWORD v31; // r14d
  LSTATUS v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  LPDWORD lpcValues; // [rsp+38h] [rbp-C8h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  struct _PLA_REGISTRY_CONTEXT *v42; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+84h] [rbp-7Ch] BYREF
  LPWSTR lpValueName; // [rsp+88h] [rbp-78h]
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+98h] [rbp-68h] BYREF
  DWORD cValues; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR *v51; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall *v52)(HKEY, LPWSTR, struct _PLA_REGISTRY_CONTEXT *); // [rsp+B8h] [rbp-48h]
  unsigned __int16 v53[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v54[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v55[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v56[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v57[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v58[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v59[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v60[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v61[64]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v5 = 0;
  v42 = a5;
  v52 = a3;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v7 = PlaiHResultFromWin32(v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v42) = 0;
    v41 = v7;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v53[v9] );
      v10 = (struct _PLA_REGISTRY_CONTEXT **)&v41;
      v11 = &v42;
LABEL_83:
      lpcValues = (LPDWORD)v11;
      goto LABEL_84;
    }
    goto LABEL_85;
  }
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v13 = PlaiHResultFromWin32(v12);
  v8 = v13;
  if ( v13 < 0 )
  {
    v41 = 0;
    LODWORD(v42) = v13;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_85;
    }
    PlaiWhoAmI(v54, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v54[v14] );
    goto LABEL_14;
  }
  v15 = cbMaxValueNameLen;
  if ( cbMaxSubKeyLen > cbMaxValueNameLen )
    v15 = cbMaxSubKeyLen;
  if ( v15 + 1 >= v15 )
  {
    cchValueName = v15 + 1;
    v16 = 2LL * (v15 + 1);
    if ( v16 <= 0xFFFFFFFF )
    {
      v17 = (unsigned int)v16;
      ProcessHeap = GetProcessHeap();
      v19 = (WCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)v17);
      v20 = xmmword_180169738;
      v21 = qword_180169748;
      lpValueName = v19;
      v22 = v19;
      v50 = v17;
      v51 = v19;
      v41 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
      {
        EventingWriteEvent(&g_Eventing, PLA_EVENT_ALLOC, 4, qword_180147320, 1, &v41, 4, &v51, 8, &v50, 8);
        v21 = qword_180169748;
        v20 = xmmword_180169738;
        v22 = lpValueName;
      }
      if ( v22 )
      {
        v24 = (unsigned int)v17 >> 1;
        v25 = (unsigned int)v17 >> 1;
        v8 = 0;
        while ( 1 )
        {
          if ( v5 >= cValues )
          {
LABEL_52:
            v30 = v52;
            v31 = 0;
            if ( v52 )
            {
              while ( v31 < cSubKeys )
              {
                cchValueName = v25;
                v32 = RegEnumKeyExW(hKey, v31, v22, &cchValueName, 0, 0, 0, 0);
                v33 = PlaiHResultFromWin32(v32);
                v8 = v33;
                if ( v33 < 0 )
                {
                  LODWORD(v42) = v33;
                  v41 = 0;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v59, 0x4000000000000800uLL);
                    v36 = -1;
                    do
                      ++v36;
                    while ( v59[v36] );
                    goto LABEL_69;
                  }
                  goto LABEL_70;
                }
                v34 = v30(hKey, lpValueName, v42);
                v8 = v34;
                if ( v34 < 0 )
                {
                  LODWORD(v42) = v34;
                  v41 = 0;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v58, 0x4000000000000800uLL);
                    v35 = -1;
                    do
                      ++v35;
                    while ( v58[v35] );
                    goto LABEL_69;
                  }
                  goto LABEL_70;
                }
                if ( v34 == 1 )
                  goto LABEL_70;
                v22 = lpValueName;
                ++v31;
                v25 = v24;
              }
            }
            goto LABEL_70;
          }
          v25 = (unsigned int)v17 >> 1;
          cchValueName = (unsigned int)v17 >> 1;
          v26 = RegEnumValueW(hKey, v5, v22, &cchValueName, 0, 0, 0, 0);
          v8 = v26;
          if ( v26 )
          {
            if ( v26 > 0 )
              v8 = (unsigned __int16)v26 | 0x80070000;
            if ( v8 < 0 )
              break;
          }
          v27 = PlaiRegSaveValue(hKey, lpValueName, v42);
          v8 = v27;
          if ( v27 < 0 )
          {
            LODWORD(v42) = v27;
            v41 = 0;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v57, 0x4000000000000800uLL);
              v29 = -1;
              do
                ++v29;
              while ( v57[v29] );
LABEL_69:
              EventingWriteEvent(
                &g_Eventing,
                PLA_EVENT_ERROR,
                5,
                &v42,
                4,
                qword_180147320,
                1,
                &v41,
                4,
                "PlaiForEachRegKey",
                18);
              goto LABEL_70;
            }
            goto LABEL_70;
          }
          v22 = lpValueName;
          if ( v27 == 1 )
            goto LABEL_52;
          ++v5;
        }
        LODWORD(v42) = v8;
        v41 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v56, 0x4000000000000800uLL);
          v28 = -1;
          do
            ++v28;
          while ( v56[v28] );
          goto LABEL_69;
        }
LABEL_70:
        PlaiFree(lpValueName, 1);
        goto LABEL_85;
      }
      v41 = 0;
      v8 = -2147024882;
      LODWORD(v42) = -2147024882;
      if ( !v20 || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0 || v21 != (v21 & 0x4000000000000800LL) )
        goto LABEL_85;
      PlaiWhoAmI(v55, 0x4000000000000800uLL);
      v23 = -1;
      do
        ++v23;
      while ( v55[v23] );
      lpcValues = (LPDWORD)&v41;
LABEL_15:
      v10 = &v42;
LABEL_84:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        v10,
        4,
        qword_180147320,
        1,
        lpcValues,
        4,
        "PlaiForEachRegKey",
        18);
      goto LABEL_85;
    }
    v8 = -2147024362;
    LODWORD(v42) = -2147024362;
    v41 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_85;
    }
    PlaiWhoAmI(v60, 0x4000000000000800uLL);
    v37 = -1;
    do
      ++v37;
    while ( v60[v37] );
LABEL_14:
    lpcValues = (LPDWORD)&v41;
    goto LABEL_15;
  }
  v8 = -2147024362;
  cchValueName = -1;
  LODWORD(v42) = -2147024362;
  v41 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v38 = -1;
    do
      ++v38;
    while ( v61[v38] );
    v10 = &v42;
    v11 = (struct _PLA_REGISTRY_CONTEXT **)&v41;
    goto LABEL_83;
  }
LABEL_85:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e000  mov     [rsp-8+arg_18], rbx
0x18001e005  push    rbp
0x18001e006  push    rsi
0x18001e007  push    rdi
0x18001e008  push    r12
0x18001e00a  push    r13
0x18001e00c  push    r14
0x18001e00e  push    r15
0x18001e010  lea     rbp, [rsp-450h]
0x18001e018  sub     rsp, 550h
0x18001e01f  mov     rax, cs:__security_cookie
0x18001e026  xor     rax, rsp
0x18001e029  mov     [rbp+480h+var_40], rax
0x18001e030  mov     rax, [rbp+480h+arg_20]
0x18001e037  xor     r14d, r14d
0x18001e03a  mov     [rsp+580h+var_508], rax
0x18001e03f  mov     r9d, 20019h; samDesired
0x18001e045  lea     rax, [rbp+480h+hKey]
0x18001e049  mov     [rbp+480h+var_4C8], r8
0x18001e04d  xor     r8d, r8d; ulOptions
0x18001e050  mov     [rsp+580h+phkResult], rax; phkResult
0x18001e055  mov     [rbp+480h+cSubKeys], r14d
0x18001e059  mov     [rbp+480h+cbMaxSubKeyLen], r14d
0x18001e05d  mov     [rbp+480h+cValues], r14d
0x18001e061  mov     [rbp+480h+cbMaxValueNameLen], r14d
0x18001e065  mov     [rbp+480h+cchValueName], r14d
0x18001e069  mov     [rbp+480h+hKey], r14
0x18001e06d  call    cs:__imp_RegOpenKeyExW
0x18001e073  mov     ecx, eax; unsigned int
0x18001e075  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18001e07a  mov     ebx, eax
0x18001e07c  test    eax, eax
0x18001e07e  jns     loc_18001E11C
0x18001e084  cmp     dword ptr cs:xmmword_180169738, r14d
0x18001e08b  mov     dword ptr [rsp+580h+var_508], r14d
0x18001e090  mov     [rsp+580h+var_510], eax
0x18001e094  jz      loc_18001E8A1
0x18001e09a  mov     rdx, 4000000000000800h; unsigned __int64
0x18001e0a4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001e0ab  jz      loc_18001E8A1
0x18001e0b1  mov     rax, cs:qword_180169748
0x18001e0b8  and     rax, rdx
0x18001e0bb  cmp     cs:qword_180169748, rax
0x18001e0c2  jnz     loc_18001E8A1
0x18001e0c8  lea     rcx, [rbp+480h+var_4C0]; unsigned __int16 *
0x18001e0cc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001e0d1  lea     rcx, [rbp+480h+var_4C0]
0x18001e0d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e0d9  inc     rax
0x18001e0dc  cmp     [rcx+rax*2], r14w
0x18001e0e1  jnz     short loc_18001E0D9
0x18001e0e3  lea     ecx, [rax+rax]
0x18001e0e6  lea     rax, [rbp+480h+var_4C0]
0x18001e0ea  add     rcx, 2
0x18001e0ee  mov     [rsp+580h+var_520], rcx
0x18001e0f3  lea     r9, [rsp+580h+var_510]
0x18001e0f8  mov     [rsp+580h+lpftLastWriteTime], rax
0x18001e0fd  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18001e104  mov     [rsp+580h+lpcbSecurityDescriptor], 12h
0x18001e10d  mov     [rsp+580h+lpcbMaxValueLen], rax
0x18001e112  lea     rax, [rsp+580h+var_508]
0x18001e117  jmp     loc_18001E85E
0x18001e11c  mov     rcx, [rbp+480h+hKey]; hKey
0x18001e120  lea     rax, [rbp+480h+cbMaxValueNameLen]
0x18001e124  mov     [rsp+580h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001e129  xor     r9d, r9d; lpReserved
0x18001e12c  mov     [rsp+580h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18001e131  xor     r8d, r8d; lpcchClass
0x18001e134  mov     [rsp+580h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18001e139  xor     edx, edx; lpClass
0x18001e13b  mov     [rsp+580h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001e140  lea     rax, [rbp+480h+cValues]
0x18001e144  mov     [rsp+580h+lpcValues], rax; lpcValues
0x18001e149  lea     rax, [rbp+480h+cbMaxSubKeyLen]
0x18001e14d  mov     [rsp+580h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001e152  mov     [rsp+580h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001e157  lea     rax, [rbp+480h+cSubKeys]
0x18001e15b  mov     [rsp+580h+phkResult], rax; lpcSubKeys
0x18001e160  call    cs:__imp_RegQueryInfoKeyW
0x18001e166  mov     ecx, eax; unsigned int
0x18001e168  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18001e16d  mov     ebx, eax
0x18001e16f  test    eax, eax
0x18001e171  jns     loc_18001E234
0x18001e177  cmp     dword ptr cs:xmmword_180169738, r14d
0x18001e17e  mov     [rsp+580h+var_510], r14d
0x18001e183  mov     dword ptr [rsp+580h+var_508], eax
0x18001e187  jz      loc_18001E8A1
0x18001e18d  mov     rdx, 4000000000000800h; unsigned __int64
0x18001e197  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001e19e  jz      loc_18001E8A1
0x18001e1a4  mov     rax, cs:qword_180169748
0x18001e1ab  and     rax, rdx
0x18001e1ae  cmp     cs:qword_180169748, rax
0x18001e1b5  jnz     loc_18001E8A1
0x18001e1bb  lea     rcx, [rbp+480h+var_440]; unsigned __int16 *
0x18001e1bf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001e1c4  lea     rcx, [rbp+480h+var_440]
0x18001e1c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e1cc  inc     rax
0x18001e1cf  cmp     [rcx+rax*2], r14w
0x18001e1d4  jnz     short loc_18001E1CC
0x18001e1d6  lea     ecx, [rax+rax]
0x18001e1d9  lea     rax, [rbp+480h+var_440]
0x18001e1dd  mov     r15d, 4
0x18001e1e3  add     rcx, 2
0x18001e1e7  mov     [rsp+580h+var_520], rcx
0x18001e1ec  mov     [rsp+580h+lpftLastWriteTime], rax
0x18001e1f1  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18001e1f8  mov     [rsp+580h+lpcbSecurityDescriptor], 12h
0x18001e201  mov     [rsp+580h+lpcbMaxValueLen], rax
0x18001e206  lea     edi, [r15-3]
0x18001e20a  mov     [rsp+580h+lpcbMaxValueNameLen], r15
0x18001e20f  lea     rax, [rsp+580h+var_510]
0x18001e214  mov     [rsp+580h+lpcValues], rax
0x18001e219  lea     rax, qword_180147320
0x18001e220  mov     [rsp+580h+lpcbMaxClassLen], rdi
0x18001e225  mov     [rsp+580h+lpcbMaxSubKeyLen], rax
0x18001e22a  lea     r9, [rsp+580h+var_508]
0x18001e22f  jmp     loc_18001E883
0x18001e234  mov     eax, [rbp+480h+cbMaxValueNameLen]
0x18001e237  cmp     [rbp+480h+cbMaxSubKeyLen], eax
0x18001e23a  cmova   eax, [rbp+480h+cbMaxSubKeyLen]
0x18001e23e  lea     ecx, [rax+1]
0x18001e241  cmp     ecx, eax
0x18001e243  jb      loc_18001E7B5
0x18001e249  mov     eax, ecx
0x18001e24b  mov     [rbp+480h+cchValueName], ecx
0x18001e24e  add     rax, rax
0x18001e251  mov     ecx, 0FFFFFFFFh
0x18001e256  cmp     rax, rcx
0x18001e259  ja      loc_18001E73C
0x18001e25f  mov     r13d, eax
0x18001e262  call    cs:__imp_GetProcessHeap
0x18001e268  mov     r8d, r13d; dwBytes
0x18001e26b  xor     edx, edx; dwFlags
0x18001e26d  mov     rcx, rax; hHeap
0x18001e270  call    cs:__imp_HeapAlloc
0x18001e276  mov     edx, dword ptr cs:xmmword_180169738
0x18001e27c  lea     rsi, qword_180147320
0x18001e283  mov     rcx, cs:qword_180169748
0x18001e28a  mov     edi, 1
0x18001e28f  mov     [rbp+480h+lpValueName], rax
0x18001e293  mov     r8, rax
0x18001e296  mov     [rbp+480h+var_4D8], r13
0x18001e29a  mov     [rbp+480h+var_4D0], rax
0x18001e29e  mov     [rsp+580h+var_510], r14d
0x18001e2a3  lea     r15d, [rdi+3]
0x18001e2a7  test    edx, edx
0x18001e2a9  jz      short loc_18001E326
0x18001e2ab  mov     r9, 4000000000000200h
0x18001e2b5  test    qword ptr cs:xmmword_180169738+8, r9
0x18001e2bc  jz      short loc_18001E326
0x18001e2be  mov     rax, rcx
0x18001e2c1  and     rax, r9
0x18001e2c4  cmp     rcx, rax
0x18001e2c7  jnz     short loc_18001E326
0x18001e2c9  lea     ecx, [rdi+7]
0x18001e2cc  mov     r9, rsi
0x18001e2cf  mov     [rsp+580h+lpcbSecurityDescriptor], rcx
0x18001e2d4  lea     rax, [rbp+480h+var_4D8]
0x18001e2d8  mov     [rsp+580h+lpcbMaxValueLen], rax
0x18001e2dd  lea     rdx, PLA_EVENT_ALLOC
0x18001e2e4  mov     [rsp+580h+lpcbMaxValueNameLen], rcx
0x18001e2e9  lea     rax, [rbp+480h+var_4D0]
0x18001e2ed  mov     [rsp+580h+lpcValues], rax
0x18001e2f2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001e2f9  lea     rax, [rsp+580h+var_510]
0x18001e2fe  mov     [rsp+580h+lpcbMaxClassLen], r15
0x18001e303  mov     [rsp+580h+lpcbMaxSubKeyLen], rax
0x18001e308  mov     r8d, r15d
0x18001e30b  mov     [rsp+580h+phkResult], rdi
0x18001e310  call    EventingWriteEvent
0x18001e315  mov     rcx, cs:qword_180169748
0x18001e31c  mov     edx, dword ptr cs:xmmword_180169738
0x18001e322  mov     r8, [rbp+480h+lpValueName]; lpName
0x18001e326  test    r8, r8
0x18001e329  jnz     loc_18001E3D7
0x18001e32f  mov     [rsp+580h+var_510], r14d
0x18001e334  mov     ebx, 8007000Eh
0x18001e339  mov     dword ptr [rsp+580h+var_508], ebx
0x18001e33d  test    edx, edx
0x18001e33f  jz      loc_18001E8A1
0x18001e345  mov     rdx, 4000000000000800h; unsigned __int64
0x18001e34f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001e356  jz      loc_18001E8A1
0x18001e35c  mov     rax, rcx
0x18001e35f  and     rax, rdx
0x18001e362  cmp     rcx, rax
0x18001e365  jnz     loc_18001E8A1
0x18001e36b  lea     rcx, [rbp+480h+var_3C0]; unsigned __int16 *
0x18001e372  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001e377  lea     rcx, [rbp+480h+var_3C0]
0x18001e37e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e382  inc     rax
0x18001e385  cmp     [rcx+rax*2], r14w
0x18001e38a  jnz     short loc_18001E382
0x18001e38c  lea     ecx, [rax+rax]
0x18001e38f  lea     rax, [rbp+480h+var_3C0]
0x18001e396  add     rcx, 2
0x18001e39a  mov     [rsp+580h+var_520], rcx
0x18001e39f  mov     [rsp+580h+lpftLastWriteTime], rax
0x18001e3a4  lea     rax, aPlaiforeachreg; "PlaiForEachRegKey"
0x18001e3ab  mov     [rsp+580h+lpcbSecurityDescriptor], 12h
0x18001e3b4  mov     [rsp+580h+lpcbMaxValueLen], rax
0x18001e3b9  lea     rax, [rsp+580h+var_510]
0x18001e3be  mov     [rsp+580h+lpcbMaxValueNameLen], r15
0x18001e3c3  mov     [rsp+580h+lpcValues], rax
0x18001e3c8  mov     [rsp+580h+lpcbMaxClassLen], rdi
0x18001e3cd  mov     [rsp+580h+lpcbMaxSubKeyLen], rsi
0x18001e3d2  jmp     loc_18001E22A
0x18001e3d7  mov     r12d, r13d
0x18001e3da  shr     r12d, 1
0x18001e3dd  mov     esi, r12d
0x18001e3e0  xor     ebx, ebx
0x18001e3e2  cmp     r14d, [rbp+480h+cValues]
0x18001e3e6  jnb     loc_18001E55C
0x18001e3ec  mov     rcx, [rbp+480h+hKey]; hKey
0x18001e3f0  lea     r9, [rbp+480h+cchValueName]; lpcchValueName
0x18001e3f4  mov     [rsp+580h+lpcValues], 0; lpcbData
0x18001e3fd  mov     esi, r13d
0x18001e400  mov     [rsp+580h+lpcbMaxClassLen], 0; lpData
0x18001e409  mov     edx, r14d; dwIndex
0x18001e40c  shr     esi, 1
0x18001e40e  mov     [rsp+580h+lpcbMaxSubKeyLen], 0; lpType
0x18001e417  mov     [rbp+480h+cchValueName], esi
0x18001e41a  mov     [rsp+580h+phkResult], 0; lpReserved
0x18001e423  call    cs:__imp_RegEnumValueW
0x18001e429  mov     ebx, eax
0x18001e42b  test    eax, eax
0x18001e42d  jz      short loc_18001E43E
0x18001e42f  jle     short loc_18001E43A
0x18001e431  movzx   ebx, ax
0x18001e434  or      ebx, 80070000h
0x18001e43a  test    ebx, ebx
0x18001e43c  js      short loc_18001E46E
0x18001e43e  mov     r8, [rsp+580h+var_508]; struct _PLA_REGISTRY_CONTEXT *
0x18001e443  mov     rdx, [rbp+480h+lpValueName]; lpValueName
0x18001e447  mov     rcx, [rbp+480h+hKey]; hKey
0x18001e44b  call    ?PlaiRegSaveValue@@YAJPEAUHKEY__@@PEBGPEAU_PLA_REGISTRY_CONTEXT@@@Z; PlaiRegSaveValue(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *)
0x18001e450  mov     ebx, eax
0x18001e452  test    eax, eax
0x18001e454  js      loc_18001E4E5
0x18001e45a  mov     r8, [rbp+480h+lpValueName]
0x18001e45e  cmp     eax, edi
0x18001e460  jz      loc_18001E55C
0x18001e466  add     r14d, edi
0x18001e469  jmp     loc_18001E3E2
0x18001e46e  xor     r14d, r14d
0x18001e471  mov     dword ptr [rsp+580h+var_508], ebx
0x18001e475  cmp     dword ptr cs:xmmword_180169738, r14d
0x18001e47c  mov     [rsp+580h+var_510], r14d
0x18001e481  jz      loc_18001E72C
0x18001e487  mov     rdx, 4000000000000800h; unsigned __int64
0x18001e491  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001e498  jz      loc_18001E72C
0x18001e49e  mov     rax, cs:qword_180169748
0x18001e4a5  and     rax, rdx
0x18001e4a8  cmp     cs:qword_180169748, rax
0x18001e4af  jnz     loc_18001E72C
0x18001e4b5  lea     rcx, [rbp+480h+var_340]; unsigned __int16 *
0x18001e4bc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001e4c1  lea     rcx, [rbp+480h+var_340]
0x18001e4c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e4cc  inc     rax
0x18001e4cf  cmp     [rcx+rax*2], r14w
0x18001e4d4  jnz     short loc_18001E4CC
0x18001e4d6  lea     ecx, [rax+rax]
0x18001e4d9  lea     rax, [rbp+480h+var_340]
0x18001e4e0  jmp     loc_18001E6C6
0x18001e4e5  xor     r14d, r14d
0x18001e4e8  mov     dword ptr [rsp+580h+var_508], eax
0x18001e4ec  cmp     dword ptr cs:xmmword_180169738, r14d
0x18001e4f3  mov     [rsp+580h+var_510], r14d
0x18001e4f8  jz      loc_18001E72C
0x18001e4fe  mov     rdx, 4000000000000800h; unsigned __int64
0x18001e508  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001e50f  jz      loc_18001E72C
0x18001e515  mov     rax, cs:qword_180169748
0x18001e51c  and     rax, rdx
0x18001e51f  cmp     cs:qword_180169748, rax
0x18001e526  jnz     loc_18001E72C
0x18001e52c  lea     rcx, [rbp+480h+var_2C0]; unsigned __int16 *
0x18001e533  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001e538  lea     rcx, [rbp+480h+var_2C0]
0x18001e53f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e543  inc     rax
0x18001e546  cmp     [rcx+rax*2], r14w
0x18001e54b  jnz     short loc_18001E543
0x18001e54d  lea     ecx, [rax+rax]
0x18001e550  lea     rax, [rbp+480h+var_2C0]
0x18001e557  jmp     loc_18001E6C6
0x18001e55c  mov     r13, [rbp+480h+var_4C8]
0x18001e560  xor     r14d, r14d
0x18001e563  test    r13, r13
0x18001e566  jz      loc_18001E72C
0x18001e56c  cmp     r14d, [rbp+480h+cSubKeys]
0x18001e570  jnb     loc_18001E72C
0x18001e576  mov     rcx, [rbp+480h+hKey]; hKey
0x18001e57a  lea     r9, [rbp+480h+cchValueName]; lpcchName
  ... truncated ...
```
