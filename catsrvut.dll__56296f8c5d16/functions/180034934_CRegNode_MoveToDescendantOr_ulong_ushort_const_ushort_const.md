# CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)

- ea: `0x180034934`
- end: `0x180034d85`
- name: `?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z`
- size: `1105`
- prototype: `int(CRegNode *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003466c`
- `0x1800347c0`
- `0x180034d90`
- `0x180034db0`
- `0x180034dd0`
- `0x180034df0`
- `0x180034f70`

## callees

- `0x18000717c`
- `0x180014ec8`
- `0x180033b08`
- `0x180034108`
- `0x180034730`
- `0x180034934`
- `0x180034f88`
- `0x180034fa8`
- `0x180034ff4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180034a82`
- `msvcrt!wcsrchr` at `0x180034a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034a24`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180034a90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180034a90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034bdb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034bdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800349ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800349ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegNode::MoveToDescendantOr(
        CRegNode *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v6; // r15d
  const WCHAR *v7; // rax
  bool v8; // zf
  unsigned __int16 *v9; // rsi
  LPWSTR v10; // r12
  const WCHAR *v11; // r14
  LSTATUS v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // r14
  unsigned __int16 *v17; // rax
  int v19; // ebx
  wchar_t *v20; // rax
  unsigned int v21; // r8d
  _QWORD *v22; // rbx
  int v23; // eax
  unsigned __int16 *v24; // r9
  int v25; // eax
  int v26; // eax
  CHkeyCache *v27; // rcx
  void *v28; // rcx
  HKEY *v29; // r14
  unsigned __int16 **v30; // rbx
  void *v31; // rcx
  _QWORD *v32; // rbx
  void *v33; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *v35; // [rsp+30h] [rbp-40h]
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-1Ch] BYREF
  BOOL v38; // [rsp+58h] [rbp-18h]
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  LPCWSTR lpValueName; // [rsp+68h] [rbp-8h]
  DWORD cbData; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 *v43; // [rsp+C8h] [rbp+58h]

  v43 = a4;
  v37 = 2;
  v6 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v7 = 0;
  v8 = *a4 == 92;
  if ( *a4 != 92 )
    v7 = a4;
  lpValueName = v7;
  v38 = !v8;
  if ( *a3 == 92 )
  {
    v9 = 0;
    hKey = (HKEY)*((_QWORD *)this + 3);
    v10 = (LPWSTR)*((_QWORD *)this + 5);
    goto LABEL_5;
  }
  v13 = *((_QWORD *)this + 4);
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v13 + 2 * v14) );
  }
  else
  {
    v14 = 0;
  }
  v15 = -1;
  do
    ++v15;
  while ( a3[v15] );
  v16 = v15 + v14 + 2;
  v17 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v16, 2u));
  v9 = v17;
  if ( !v17 )
    return 2147942414LL;
  *v17 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    v19 = StringCchPrintfW(v17, v16, L"%s\\");
    if ( v19 < 0 )
      goto LABEL_83;
  }
  v19 = StringCchCatW(v9, v16, a3);
  if ( v19 < 0 )
    goto LABEL_83;
  v20 = wcsrchr(v9, 0x5Cu);
  if ( v20 )
    v10 = CharNextW(v20);
  else
    v10 = v9;
  v22 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v22 && (v23 = CHkeyCache::Find(*((CHkeyCache **)this + 9), v9), v23 > -1) )
  {
    hKey = *(HKEY *)(*v22 + 16LL * v23 + 8);
    v6 = 1;
    v25 = 0;
  }
  else
  {
    v25 = RegSafeOpenKeyEx(*((HKEY *)this + 3), a3, v21, *((_DWORD *)this + 16), &hKey);
  }
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      if ( v25 == 2 )
      {
        v19 = 1;
        goto LABEL_83;
      }
    }
    else
    {
      if ( a2 != 2 )
      {
        v19 = -2147418113;
LABEL_83:
        CoTaskMemFree(v9);
        return (unsigned int)v19;
      }
      if ( v25 == 2 )
      {
        v26 = RegSafeCreateKeyEx(*((HKEY *)this + 3), a3, v21, v24, lpData, *((_DWORD *)this + 16), v35, &hKey, &v37);
        if ( v26 )
        {
          if ( v26 != 1314 && v26 != 5 )
          {
            v19 = -2146369503;
            goto LABEL_83;
          }
LABEL_41:
          v19 = -2146367453;
          goto LABEL_83;
        }
        goto LABEL_5;
      }
    }
  }
  if ( v25 )
  {
    if ( v25 != 1314 && v25 != 5 )
    {
      v19 = -2146369487;
      goto LABEL_83;
    }
    goto LABEL_41;
  }
LABEL_5:
  cbData = 256;
  v11 = lpValueName;
  v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)this + 88, &cbData);
  if ( !v12 )
  {
    *((_DWORD *)this + 21) = 1;
    goto LABEL_47;
  }
  *((_DWORD *)this + 21) = 0;
  if ( v12 == 234 )
    goto LABEL_46;
  if ( v12 == 2 && !v11 )
  {
    Type = 0;
    cbData = 0;
LABEL_46:
    v12 = 0;
  }
LABEL_47:
  v19 = -2146369497;
  if ( a2 == 1 )
  {
    if ( v12 == 2 )
    {
      v19 = 1;
      goto LABEL_54;
    }
  }
  else if ( a2 == 2 && v12 == 2 )
  {
    if ( RegSetValueExW(hKey, v11, 0, 0, 0, 0) )
    {
      v19 = -2146369496;
LABEL_54:
      if ( *((HKEY *)this + 3) != hKey && !v6 )
      {
        RegSafeCloseKey(hKey);
        if ( !v9 )
          return (unsigned int)v19;
        CoTaskMemFree(v9);
        v9 = 0;
      }
      goto LABEL_82;
    }
    v12 = RegQueryValueExW(hKey, v11, 0, &Type, 0, &cbData);
  }
  if ( v12 )
    goto LABEL_54;
  *((_DWORD *)this + 2) &= 0xFFFFFFFC;
  *((_DWORD *)this + 2) |= v38;
  if ( *a3 != 92 )
  {
    v27 = (CHkeyCache *)*((_QWORD *)this + 9);
    if ( v27 )
    {
      if ( !v6 )
      {
        if ( v9 )
        {
          v19 = CHkeyCache::Append(v27, v9, hKey);
          if ( v19 < 0 )
            goto LABEL_83;
        }
      }
      if ( *((_DWORD *)this + 20) )
      {
        v28 = (void *)*((_QWORD *)this + 4);
        if ( v28 )
        {
          CoTaskMemFree(v28);
          *((_QWORD *)this + 4) = 0;
        }
      }
      *((_DWORD *)this + 20) = v6;
      v29 = (HKEY *)((char *)this + 24);
      v30 = (unsigned __int16 **)((char *)this + 32);
    }
    else
    {
      v29 = (HKEY *)((char *)this + 24);
      RegSafeCloseKey(*((HKEY *)this + 3));
      v30 = (unsigned __int16 **)((char *)this + 32);
      v31 = (void *)*((_QWORD *)this + 4);
      if ( v31 )
      {
        CoTaskMemFree(v31);
        *v30 = 0;
      }
    }
    *v29 = hKey;
    *v30 = v9;
    v9 = 0;
    *((_QWORD *)this + 5) = v10;
  }
  v32 = (_QWORD *)((char *)this + 48);
  v33 = (void *)*((_QWORD *)this + 6);
  if ( v33 )
  {
    CoTaskMemFree(v33);
    *v32 = 0;
  }
  if ( *v43 == 92 )
  {
    *v32 = 0;
  }
  else
  {
    v19 = LocalCopyString(v43, (unsigned __int16 **)this + 6);
    if ( v19 < 0 )
      goto LABEL_82;
  }
  *((_DWORD *)this + 14) = Type;
  *((_DWORD *)this + 15) = cbData;
  if ( a2 == 2 && v37 == 1 )
    v19 = 1114114;
  else
    v19 = 0;
LABEL_82:
  if ( v9 )
    goto LABEL_83;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180034934  mov     [rsp-38h+arg_0], rbx
0x180034939  mov     [rsp-38h+arg_18], r9
0x18003493e  mov     [rsp-38h+arg_8], edx
0x180034942  push    rbp
0x180034943  push    rsi
0x180034944  push    rdi
0x180034945  push    r12
0x180034947  push    r13
0x180034949  push    r14
0x18003494b  push    r15
0x18003494d  mov     rbp, rsp
0x180034950  sub     rsp, 70h
0x180034954  mov     r13, r8
0x180034957  mov     rdi, rcx
0x18003495a  mov     edx, 2
0x18003495f  mov     [rbp+var_1C], edx
0x180034962  xor     ebx, ebx
0x180034964  mov     r15d, ebx
0x180034967  mov     [rbp+hKey], rbx
0x18003496b  mov     [rbp+Type], ebx
0x18003496e  mov     [rbp+cbData], ebx
0x180034971  lea     r12d, [rdx+5Ah]
0x180034975  mov     eax, ebx
0x180034977  cmp     r12w, [r9]
0x18003497b  cmovnz  rax, r9
0x18003497f  mov     [rbp+lpValueName], rax
0x180034983  mov     eax, ebx
0x180034985  setnz   al
0x180034988  mov     [rbp+var_18], eax
0x18003498b  cmp     r12w, [r8]
0x18003498f  jnz     short loc_1800349E4
0x180034991  mov     esi, ebx
0x180034993  mov     rax, [rcx+18h]
0x180034997  mov     [rbp+hKey], rax
0x18003499b  mov     r12, [rcx+28h]
0x18003499f  mov     [rbp+cbData], 100h
0x1800349a6  lea     rax, [rdi+58h]
0x1800349aa  lea     rcx, [rbp+cbData]
0x1800349ae  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800349b3  mov     [rsp+70h+lpData], rax; lpData
0x1800349b8  lea     r9, [rbp+Type]; lpType
0x1800349bc  xor     r8d, r8d; lpReserved
0x1800349bf  mov     r14, [rbp+lpValueName]
0x1800349c3  mov     rdx, r14; lpValueName
0x1800349c6  mov     rcx, [rbp+hKey]; hKey
0x1800349ca  call    cs:__imp_RegQueryValueExW
0x1800349d0  test    eax, eax
0x1800349d2  jnz     loc_180034B86
0x1800349d8  mov     dword ptr [rdi+54h], 1
0x1800349df  jmp     loc_180034BA2
0x1800349e4  mov     rcx, [rcx+20h]
0x1800349e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800349ec  test    rcx, rcx
0x1800349ef  jz      short loc_1800349FF
0x1800349f1  mov     rax, r8
0x1800349f4  inc     rax
0x1800349f7  cmp     [rcx+rax*2], bx
0x1800349fb  jnz     short loc_1800349F4
0x1800349fd  jmp     short loc_180034A02
0x1800349ff  mov     rax, rbx
0x180034a02  mov     rcx, r8
0x180034a05  inc     rcx
0x180034a08  cmp     [r13+rcx*2+0], bx
0x180034a0e  jnz     short loc_180034A05
0x180034a10  lea     r14, [rax+2]
0x180034a14  add     r14, rcx
0x180034a17  mov     rax, rdx
0x180034a1a  mul     r14
0x180034a1d  cmovb   rax, r8
0x180034a21  mov     rcx, rax; cb
0x180034a24  call    cs:__imp_CoTaskMemAlloc
0x180034a2a  mov     rsi, rax
0x180034a2d  test    rax, rax
0x180034a30  jnz     short loc_180034A3C
0x180034a32  mov     eax, 8007000Eh
0x180034a37  jmp     loc_180034D6D
0x180034a3c  mov     [rax], bx
0x180034a3f  mov     r9, [rdi+20h]
0x180034a43  test    r9, r9
0x180034a46  jz      short loc_180034A64
0x180034a48  lea     r8, aS_1; "%s\\"
0x180034a4f  mov     rdx, r14; unsigned __int64
0x180034a52  mov     rcx, rsi; unsigned __int16 *
0x180034a55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034a5a  mov     ebx, eax
0x180034a5c  test    eax, eax
0x180034a5e  js      loc_180034D61
0x180034a64  mov     r8, r13; unsigned __int16 *
0x180034a67  mov     rdx, r14; unsigned __int64
0x180034a6a  mov     rcx, rsi; unsigned __int16 *
0x180034a6d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034a72  mov     ebx, eax
0x180034a74  test    eax, eax
0x180034a76  js      loc_180034D61
0x180034a7c  mov     edx, r12d; Ch
0x180034a7f  mov     rcx, rsi; Str
0x180034a82  call    cs:__imp_wcsrchr
0x180034a88  test    rax, rax
0x180034a8b  jz      short loc_180034A9B
0x180034a8d  mov     rcx, rax; lpsz
0x180034a90  call    cs:__imp_CharNextW
0x180034a96  mov     r12, rax
0x180034a99  jmp     short loc_180034A9E
0x180034a9b  mov     r12, rsi
0x180034a9e  mov     rbx, [rdi+48h]
0x180034aa2  test    rbx, rbx
0x180034aa5  jz      short loc_180034AD3
0x180034aa7  mov     rdx, rsi; unsigned __int16 *
0x180034aaa  mov     rcx, rbx; this
0x180034aad  call    ?Find@CHkeyCache@@AEAAJPEBG@Z; CHkeyCache::Find(ushort const *)
0x180034ab2  cmp     eax, 0FFFFFFFFh
0x180034ab5  jle     short loc_180034AD3
0x180034ab7  movsxd  rcx, eax
0x180034aba  add     rcx, rcx
0x180034abd  mov     rax, [rbx]
0x180034ac0  mov     rcx, [rax+rcx*8+8]
0x180034ac5  mov     [rbp+hKey], rcx
0x180034ac9  xor     ebx, ebx
0x180034acb  lea     r15d, [rbx+1]
0x180034acf  mov     eax, ebx
0x180034ad1  jmp     short loc_180034AEE
0x180034ad3  xor     ebx, ebx
0x180034ad5  lea     rax, [rbp+hKey]
0x180034ad9  mov     [rsp+70h+lpData], rax; unsigned int
0x180034ade  mov     r9d, [rdi+40h]; unsigned int
0x180034ae2  mov     rdx, r13; unsigned __int16 *
0x180034ae5  mov     rcx, [rdi+18h]; HKEY
0x180034ae9  call    ?RegSafeOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; RegSafeOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180034aee  mov     ecx, [rbp+arg_8]
0x180034af1  test    ecx, ecx
0x180034af3  jz      short loc_180034B5E
0x180034af5  sub     ecx, 1
0x180034af8  jz      short loc_180034B51
0x180034afa  cmp     ecx, 1
0x180034afd  jz      short loc_180034B09
0x180034aff  mov     ebx, 8000FFFFh
0x180034b04  jmp     loc_180034D61
0x180034b09  cmp     eax, 2
0x180034b0c  jnz     short loc_180034B5E
0x180034b0e  lea     rax, [rbp+var_1C]
0x180034b12  mov     [rsp+70h+var_30], rax; unsigned int *
0x180034b17  lea     rax, [rbp+hKey]
0x180034b1b  mov     [rsp+70h+var_38], rax; HKEY *
0x180034b20  mov     eax, [rdi+40h]
0x180034b23  mov     dword ptr [rsp+70h+lpcbData], eax; unsigned int
0x180034b27  mov     rdx, r13; unsigned __int16 *
0x180034b2a  mov     rcx, [rdi+18h]; HKEY
0x180034b2e  call    ?RegSafeCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; RegSafeCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180034b33  test    eax, eax
0x180034b35  jz      loc_18003499F
0x180034b3b  cmp     eax, 522h
0x180034b40  jz      short loc_180034B7C
0x180034b42  cmp     eax, 5
0x180034b45  jz      short loc_180034B7C
0x180034b47  mov     ebx, 80110021h
0x180034b4c  jmp     loc_180034D61
0x180034b51  cmp     eax, 2
0x180034b54  jnz     short loc_180034B5E
0x180034b56  lea     ebx, [rax-1]
0x180034b59  jmp     loc_180034D61
0x180034b5e  test    eax, eax
0x180034b60  jz      loc_18003499F
0x180034b66  cmp     eax, 522h
0x180034b6b  jz      short loc_180034B7C
0x180034b6d  cmp     eax, 5
0x180034b70  jz      short loc_180034B7C
0x180034b72  mov     ebx, 80110031h
0x180034b77  jmp     loc_180034D61
0x180034b7c  mov     ebx, 80110823h
0x180034b81  jmp     loc_180034D61
0x180034b86  mov     [rdi+54h], ebx
0x180034b89  cmp     eax, 0EAh
0x180034b8e  jz      short loc_180034BA0
0x180034b90  cmp     eax, 2
0x180034b93  jnz     short loc_180034BA2
0x180034b95  test    r14, r14
0x180034b98  jnz     short loc_180034BA2
0x180034b9a  mov     [rbp+Type], ebx
0x180034b9d  mov     [rbp+cbData], ebx
0x180034ba0  mov     eax, ebx
0x180034ba2  mov     ebx, 80110027h
0x180034ba7  mov     ecx, [rbp+arg_8]
0x180034baa  sub     ecx, 1
0x180034bad  jz      loc_180034C4C
0x180034bb3  cmp     ecx, 1
0x180034bb6  jnz     short loc_180034C12
0x180034bb8  cmp     eax, 2
0x180034bbb  jnz     short loc_180034C12
0x180034bbd  mov     dword ptr [rsp+70h+lpcbData], 0; cbData
0x180034bc5  mov     [rsp+70h+lpData], 0; lpData
0x180034bce  xor     r9d, r9d; dwType
0x180034bd1  xor     r8d, r8d; Reserved
0x180034bd4  mov     rdx, r14; lpValueName
0x180034bd7  mov     rcx, [rbp+hKey]; hKey
0x180034bdb  call    cs:__imp_RegSetValueExW
0x180034be1  test    eax, eax
0x180034be3  jz      short loc_180034BEC
0x180034be5  mov     ebx, 80110028h
0x180034bea  jmp     short loc_180034C16
0x180034bec  lea     rax, [rbp+cbData]
0x180034bf0  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180034bf5  mov     [rsp+70h+lpData], 0; lpData
0x180034bfe  lea     r9, [rbp+Type]; lpType
0x180034c02  xor     r8d, r8d; lpReserved
0x180034c05  mov     rdx, r14; lpValueName
0x180034c08  mov     rcx, [rbp+hKey]; hKey
0x180034c0c  call    cs:__imp_RegQueryValueExW
0x180034c12  test    eax, eax
0x180034c14  jz      short loc_180034C56
0x180034c16  mov     rcx, [rbp+hKey]; HKEY
0x180034c1a  cmp     [rdi+18h], rcx
0x180034c1e  jz      loc_180034D5C
0x180034c24  test    r15d, r15d
0x180034c27  jnz     loc_180034D5C
0x180034c2d  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180034c32  test    rsi, rsi
0x180034c35  jz      loc_180034D6B
0x180034c3b  mov     rcx, rsi; pv
0x180034c3e  call    cs:__imp_CoTaskMemFree
0x180034c44  nop
0x180034c45  xor     esi, esi
0x180034c47  jmp     loc_180034D5C
0x180034c4c  cmp     eax, 2
0x180034c4f  jnz     short loc_180034C12
0x180034c51  lea     ebx, [rax-1]
0x180034c54  jmp     short loc_180034C16
0x180034c56  and     dword ptr [rdi+8], 0FFFFFFFCh
0x180034c5a  mov     eax, [rbp+var_18]
0x180034c5d  or      [rdi+8], eax
0x180034c60  mov     r14d, 5Ch ; '\'
0x180034c66  cmp     r14w, [r13+0]
0x180034c6b  jz      loc_180034D00
0x180034c71  mov     rcx, [rdi+48h]; this
0x180034c75  test    rcx, rcx
0x180034c78  jz      short loc_180034CC6
0x180034c7a  test    r15d, r15d
0x180034c7d  jnz     short loc_180034C9A
0x180034c7f  test    rsi, rsi
0x180034c82  jz      short loc_180034C9A
0x180034c84  mov     r8, [rbp+hKey]; HKEY
0x180034c88  mov     rdx, rsi; unsigned __int16 *
0x180034c8b  call    ?Append@CHkeyCache@@QEAAJPEBGPEAUHKEY__@@@Z; CHkeyCache::Append(ushort const *,HKEY__ *)
0x180034c90  mov     ebx, eax
0x180034c92  test    eax, eax
0x180034c94  js      loc_180034D61
0x180034c9a  cmp     dword ptr [rdi+50h], 0
0x180034c9e  jz      short loc_180034CB8
0x180034ca0  mov     rcx, [rdi+20h]; pv
0x180034ca4  test    rcx, rcx
0x180034ca7  jz      short loc_180034CB8
0x180034ca9  call    cs:__imp_CoTaskMemFree
0x180034caf  nop
0x180034cb0  mov     qword ptr [rdi+20h], 0
0x180034cb8  mov     [rdi+50h], r15d
0x180034cbc  lea     r14, [rdi+18h]
0x180034cc0  lea     rbx, [rdi+20h]
0x180034cc4  jmp     short loc_180034CEC
0x180034cc6  lea     r14, [rdi+18h]
0x180034cca  mov     rcx, [r14]; HKEY
0x180034ccd  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180034cd2  lea     rbx, [rdi+20h]
0x180034cd6  mov     rcx, [rbx]; pv
0x180034cd9  test    rcx, rcx
0x180034cdc  jz      short loc_180034CEC
0x180034cde  call    cs:__imp_CoTaskMemFree
0x180034ce4  nop
0x180034ce5  mov     qword ptr [rbx], 0
0x180034cec  mov     rax, [rbp+hKey]
0x180034cf0  mov     [r14], rax
0x180034cf3  mov     [rbx], rsi
0x180034cf6  xor     esi, esi
0x180034cf8  mov     [rdi+28h], r12
0x180034cfc  lea     r14d, [rsi+5Ch]
0x180034d00  lea     rbx, [rdi+30h]
0x180034d04  mov     rcx, [rbx]; pv
0x180034d07  test    rcx, rcx
0x180034d0a  jz      short loc_180034D1A
0x180034d0c  call    cs:__imp_CoTaskMemFree
0x180034d12  nop
0x180034d13  mov     qword ptr [rbx], 0
0x180034d1a  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180034d1e  cmp     r14w, [rcx]
0x180034d22  jz      short loc_180034D34
0x180034d24  mov     rdx, rbx; unsigned __int16 **
0x180034d27  call    ?LocalCopyString@@YAJPEBGPEAPEAG@Z; LocalCopyString(ushort const *,ushort * *)
0x180034d2c  mov     ebx, eax
0x180034d2e  test    eax, eax
0x180034d30  js      short loc_180034D5C
0x180034d32  jmp     short loc_180034D3B
0x180034d34  mov     qword ptr [rbx], 0
0x180034d3b  mov     eax, [rbp+Type]
0x180034d3e  mov     [rdi+38h], eax
0x180034d41  mov     eax, [rbp+cbData]
0x180034d44  mov     [rdi+3Ch], eax
0x180034d47  cmp     [rbp+arg_8], 2
0x180034d4b  jnz     short loc_180034D5A
0x180034d4d  cmp     [rbp+var_1C], 1
0x180034d51  jnz     short loc_180034D5A
0x180034d53  mov     ebx, 110002h
0x180034d58  jmp     short loc_180034D5C
  ... truncated ...
```
