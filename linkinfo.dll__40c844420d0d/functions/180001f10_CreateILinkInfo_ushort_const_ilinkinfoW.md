# CreateILinkInfo(ushort const *,_ilinkinfoW * *)

- ea: `0x180001f10`
- end: `0x1800023c0`
- name: `?CreateILinkInfo@@YAHPEBGPEAPEAU_ilinkinfoW@@@Z`
- size: `1200`
- prototype: `int(const unsigned __int16 *, struct _ilinkinfoW **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180001ca0`
- `0x18000535c`

## callees

- `0x180001de0`
- `0x180001f10`
- `0x1800023d0`
- `0x180002500`
- `0x180002b00`
- `0x1800030d0`
- `0x180004b50`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180002017`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180002017`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001f56`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180001f56`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000223d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000223d`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001f94`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800020c6`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001f94`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800020c6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002273`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002291`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800022b4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002273`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002291`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800022b4`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180002339`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180002339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000239a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000239a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021ae`
- `MPR!WNetGetConnectionW` at `0x180002217`
- `MPR!WNetGetConnectionW` at `0x180002217`

## pseudocode

```c
__int64 __fastcall CreateILinkInfo(const unsigned __int16 *a1, struct _ilinkinfoW **a2)
{
  __int64 v3; // r15
  __int64 v4; // rbx
  WCHAR *v5; // rdx
  __int64 v6; // rcx
  WCHAR *v7; // r8
  int v8; // r14d
  __int64 v9; // r9
  WCHAR *v10; // rcx
  BOOL IsUNCW; // edi
  WCHAR *p_szStart; // rsi
  unsigned int NetType; // edi
  unsigned int v15; // r10d
  WCHAR *v16; // rcx
  __int64 v17; // r8
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  DWORD v20; // ebx
  HLOCAL v21; // rsi
  WCHAR *v22; // rdx
  __int64 v23; // rcx
  WCHAR *p_LocalName; // r8
  __int64 v25; // r9
  WCHAR *v26; // rcx
  DWORD ConnectionW; // eax
  const WCHAR *v28; // rdx
  unsigned __int16 *v29; // rax
  LPWSTR v30; // rdx
  unsigned __int16 i; // cx
  unsigned __int64 v32; // rdx
  WCHAR *p_Buffer; // rcx
  WCHAR *v34; // r8
  WCHAR *v35; // rcx
  size_t v36; // [rsp+20h] [rbp-E0h]
  const WCHAR *lpWideCharStr; // [rsp+28h] [rbp-D8h]
  DWORD nLength; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR LocalName; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR RootPathName[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer; // [rsp+70h] [rbp-90h] BYREF
  __int16 v44; // [rsp+72h] [rbp-8Eh]
  unsigned __int16 v45; // [rsp+74h] [rbp-8Ch]
  WCHAR szStart; // [rsp+76h] [rbp-8Ah] BYREF
  WCHAR RemoteName[264]; // [rsp+280h] [rbp+180h] BYREF

  v3 = 260;
  FilePart = 0;
  if ( GetFullPathNameW(a1, 0x104u, &Buffer, &FilePart) - 1 > 0x101 )
    return 0;
  if ( !IsCharAlphaW(Buffer) || v44 != 58 || !(unsigned int)CharIsSlash(v45) )
  {
    IsUNCW = PathIsUNCW(&Buffer);
    if ( IsUNCW )
    {
      if ( !(unsigned int)CharIsSlash(v45) )
      {
        do
          v29 = CharNextW(v28);
        while ( !(unsigned int)CharIsSlash(*v29) );
      }
      v30 = CharNextW(v28);
      for ( i = *v30; *v30; i = *v30 )
      {
        if ( (unsigned int)CharIsSlash(i) )
          break;
        v30 = CharNextW(v30);
      }
      p_szStart = v30 + 1;
      if ( !*v30 )
      {
        *v30 = 92;
        *p_szStart = 0;
      }
      v4 = 2147483646;
      v32 = v30 - &Buffer;
      if ( v32 > 0x7FFFFFFE )
      {
        RemoteName[0] = 0;
      }
      else
      {
        p_Buffer = &Buffer;
        v34 = RemoteName;
        do
        {
          if ( !v32 )
            break;
          if ( !*p_Buffer )
            break;
          *v34++ = *p_Buffer++;
          --v32;
          --v3;
        }
        while ( v3 );
        v35 = v34 - 1;
        if ( v3 )
          v35 = v34;
        *v35 = 0;
      }
      CharUpperW(RemoteName);
      IsUNCW = 1;
      v8 = 1;
    }
    else
    {
      v8 = 0;
      p_szStart = 0;
      SetLastError(0xA1u);
      v4 = 2147483646;
    }
    goto LABEL_14;
  }
  v4 = 2147483646;
  v5 = &Buffer;
  v6 = 2147483646;
  v7 = RootPathName;
  v8 = 0;
  v9 = 4;
  do
  {
    if ( !v6 )
      break;
    if ( !*v5 )
      break;
    *v7++ = *v5++;
    --v6;
    --v9;
  }
  while ( v9 );
  v10 = v7 - 1;
  if ( v9 )
    v10 = v7;
  *v10 = 0;
  if ( GetDriveTypeW(RootPathName) == 4 )
  {
    nLength = 260;
    v22 = RootPathName;
    v23 = 2147483646;
    p_LocalName = &LocalName;
    v25 = 3;
    do
    {
      if ( !v23 )
        break;
      if ( !*v22 )
        break;
      *p_LocalName++ = *v22++;
      --v23;
      --v25;
    }
    while ( v25 );
    v26 = p_LocalName - 1;
    if ( v25 )
      v26 = p_LocalName;
    *v26 = 0;
    ConnectionW = WNetGetConnectionW(&LocalName, RemoteName, &nLength);
    if ( !ConnectionW )
    {
      IsUNCW = 1;
      v8 = 1;
      goto LABEL_13;
    }
    if ( ConnectionW != 2250 )
    {
      IsUNCW = 0;
      goto LABEL_13;
    }
  }
  IsUNCW = 1;
LABEL_13:
  p_szStart = &szStart;
LABEL_14:
  if ( !IsUNCW )
    return 0;
  CanonicalizeTrailingSlash(p_szStart);
  if ( !v8 )
    return CreateLocalILinkInfo(&Buffer, a2);
  hMem = 0;
  nLength = 0;
  *(_DWORD *)RootPathName = 0;
  NetType = GetNetType(RemoteName, (unsigned int *)RootPathName);
  if ( NetType )
  {
    if ( IsCharAlphaW(Buffer) && v44 == 58 && (unsigned int)CharIsSlash(v45) )
    {
      v15 = 3;
      v16 = &Buffer;
      v17 = 3;
      v18 = &LocalName;
      do
      {
        if ( !v4 )
          break;
        if ( !*v16 )
          break;
        *v18++ = *v16++;
        --v4;
        --v17;
      }
      while ( v17 );
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
    }
    else
    {
      v15 = 2;
      LocalName = 0;
    }
    NetType = UnifyICNRLinkInfo(
                RemoteName,
                v15,
                &LocalName,
                *(unsigned int *)RootPathName,
                (struct tagICNRLINKW **)&hMem,
                &nLength);
    if ( NetType )
    {
      v20 = nLength;
      lpWideCharStr = p_szStart;
      v21 = hMem;
      LODWORD(v36) = nLength;
      NetType = UnifyILinkInfo(0, 0, &String1, (const struct _cnrlink *)hMem, v36, lpWideCharStr, a2);
      if ( v20 )
        LocalFree(v21);
    }
  }
  return NetType;
}

```

## disassembly

```asm
0x180001f10  push    rbp
0x180001f12  push    r12
0x180001f14  push    r13
0x180001f16  push    r15
0x180001f18  lea     rbp, [rsp-3B8h]
0x180001f20  sub     rsp, 4B8h
0x180001f27  mov     rax, cs:__security_cookie
0x180001f2e  xor     rax, rsp
0x180001f31  mov     [rbp+3D0h+var_40], rax
0x180001f38  mov     r13, rdx
0x180001f3b  lea     r9, [rsp+4D0h+FilePart]; lpFilePart
0x180001f40  mov     r15d, 104h
0x180001f46  lea     r8, [rsp+4D0h+Buffer]; lpBuffer
0x180001f4b  xor     r12d, r12d
0x180001f4e  mov     edx, r15d; nBufferLength
0x180001f51  mov     [rsp+4D0h+FilePart], r12
0x180001f56  call    cs:__imp_GetFullPathNameW
0x180001f5d  nop     dword ptr [rax+rax+00h]
0x180001f62  dec     eax
0x180001f64  cmp     eax, 101h
0x180001f69  ja      loc_1800023B8
0x180001f6f  movzx   ecx, [rsp+4D0h+Buffer]; ch
0x180001f74  mov     [rsp+4D0h+var_28], rdi
0x180001f7c  mov     [rsp+4D0h+arg_10], rbx
0x180001f84  mov     [rsp+4D0h+var_20], rsi
0x180001f8c  mov     [rsp+4D0h+var_30], r14
0x180001f94  call    cs:__imp_IsCharAlphaW
0x180001f9b  nop     dword ptr [rax+rax+00h]
0x180001fa0  test    eax, eax
0x180001fa2  jz      loc_180002238
0x180001fa8  cmp     [rsp+4D0h+var_45E], 3Ah ; ':'
0x180001fae  jnz     loc_180002238
0x180001fb4  movzx   ecx, [rsp+4D0h+var_45C]; unsigned __int16
0x180001fb9  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001fbe  test    eax, eax
0x180001fc0  jz      loc_180002238
0x180001fc6  mov     ebx, 7FFFFFFEh
0x180001fcb  lea     rdx, [rsp+4D0h+Buffer]
0x180001fd0  mov     ecx, ebx
0x180001fd2  lea     r8, [rsp+4D0h+RootPathName]
0x180001fd7  xor     r14d, r14d
0x180001fda  mov     r9d, 4
0x180001fe0  test    rcx, rcx
0x180001fe3  jz      short loc_180002002
0x180001fe5  movzx   eax, word ptr [rdx]
0x180001fe8  test    ax, ax
0x180001feb  jz      short loc_180002002
0x180001fed  mov     [r8], ax
0x180001ff1  add     rdx, 2
0x180001ff5  add     r8, 2
0x180001ff9  dec     rcx
0x180001ffc  sub     r9, 1
0x180002000  jnz     short loc_180001FE0
0x180002002  test    r9, r9
0x180002005  lea     rcx, [r8-2]
0x180002009  cmovnz  rcx, r8
0x18000200d  xor     eax, eax
0x18000200f  mov     [rcx], ax
0x180002012  lea     rcx, [rsp+4D0h+RootPathName]; lpRootPathName
0x180002017  call    cs:__imp_GetDriveTypeW
0x18000201e  nop     dword ptr [rax+rax+00h]
0x180002023  cmp     eax, 4
0x180002026  jz      loc_1800021BC
0x18000202c  mov     edi, 1
0x180002031  lea     rsi, [rsp+4D0h+szStart]
0x180002036  test    edi, edi
0x180002038  jz      loc_1800023B0
0x18000203e  mov     rcx, rsi; lpszStart
0x180002041  call    ?CanonicalizeTrailingSlash@@YAXPEAG@Z; CanonicalizeTrailingSlash(ushort *)
0x180002046  test    r14d, r14d
0x180002049  jnz     short loc_180002097
0x18000204b  mov     rdx, r13; struct _ilinkinfoW **
0x18000204e  lea     rcx, [rsp+4D0h+Buffer]; lpString
0x180002053  call    ?CreateLocalILinkInfo@@YAHPEBGPEAPEAU_ilinkinfoW@@@Z; CreateLocalILinkInfo(ushort const *,_ilinkinfoW * *)
0x180002058  mov     rbx, [rsp+4D0h+arg_10]
0x180002060  mov     rsi, [rsp+4D0h+var_20]
0x180002068  mov     r14, [rsp+4D0h+var_30]
0x180002070  mov     rdi, [rsp+4D0h+var_28]
0x180002078  mov     rcx, [rbp+3D0h+var_40]
0x18000207f  xor     rcx, rsp; StackCookie
0x180002082  call    __security_check_cookie
0x180002087  add     rsp, 4B8h
0x18000208e  pop     r15
0x180002090  pop     r13
0x180002092  pop     r12
0x180002094  pop     rbp
0x180002095  retn
0x180002097  lea     rdx, [rsp+4D0h+RootPathName]; unsigned int *
0x18000209c  mov     [rsp+4D0h+hMem], r12
0x1800020a1  lea     rcx, [rbp+3D0h+RemoteName]; unsigned __int16 *
0x1800020a8  mov     [rsp+4D0h+nLength], r12d
0x1800020ad  mov     dword ptr [rsp+4D0h+RootPathName], r12d
0x1800020b2  call    ?GetNetType@@YAHPEBGPEAK@Z; GetNetType(ushort const *,ulong *)
0x1800020b7  mov     edi, eax
0x1800020b9  test    eax, eax
0x1800020bb  jz      loc_180002174
0x1800020c1  movzx   ecx, [rsp+4D0h+Buffer]; ch
0x1800020c6  call    cs:__imp_IsCharAlphaW
0x1800020cd  nop     dword ptr [rax+rax+00h]
0x1800020d2  test    eax, eax
0x1800020d4  jz      loc_180002352
0x1800020da  cmp     [rsp+4D0h+var_45E], 3Ah ; ':'
0x1800020e0  jnz     loc_180002352
0x1800020e6  movzx   ecx, [rsp+4D0h+var_45C]; unsigned __int16
0x1800020eb  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x1800020f0  test    eax, eax
0x1800020f2  jz      loc_180002352
0x1800020f8  mov     r10d, 3
0x1800020fe  lea     rcx, [rsp+4D0h+Buffer]
0x180002103  mov     r8d, r10d
0x180002106  lea     rdx, [rsp+4D0h+LocalName]
0x18000210b  nop     dword ptr [rax+rax+00h]
0x180002110  test    rbx, rbx
0x180002113  jz      short loc_180002131
0x180002115  movzx   eax, word ptr [rcx]
0x180002118  test    ax, ax
0x18000211b  jz      short loc_180002131
0x18000211d  mov     [rdx], ax
0x180002120  add     rcx, 2
0x180002124  add     rdx, 2
0x180002128  dec     rbx
0x18000212b  sub     r8, 1
0x18000212f  jnz     short loc_180002110
0x180002131  test    r8, r8
0x180002134  lea     rcx, [rdx-2]
0x180002138  cmovnz  rcx, rdx
0x18000213c  xor     eax, eax
0x18000213e  mov     [rcx], ax
0x180002141  mov     r9d, dword ptr [rsp+4D0h+RootPathName]; unsigned int
0x180002146  lea     rax, [rsp+4D0h+nLength]
0x18000214b  mov     [rsp+4D0h+lpWideCharStr], rax; unsigned int *
0x180002150  lea     r8, [rsp+4D0h+LocalName]; unsigned __int16 *
0x180002155  lea     rax, [rsp+4D0h+hMem]
0x18000215a  mov     edx, r10d; unsigned int
0x18000215d  lea     rcx, [rbp+3D0h+RemoteName]; lpString
0x180002164  mov     [rsp+4D0h+var_4B0], rax; struct tagICNRLINKW **
0x180002169  call    ?UnifyICNRLinkInfo@@YAHPEBGK0KPEAPEAUtagICNRLINKW@@PEAI@Z; UnifyICNRLinkInfo(ushort const *,ulong,ushort const *,ulong,tagICNRLINKW * *,uint *)
0x18000216e  mov     edi, eax
0x180002170  test    eax, eax
0x180002172  jnz     short loc_18000217B
0x180002174  mov     eax, edi
0x180002176  jmp     loc_180002058
0x18000217b  mov     ebx, [rsp+4D0h+nLength]
0x18000217f  lea     r8, String1; lpString1
0x180002186  mov     [rsp+4D0h+var_4A0], r13; struct _ilinkinfoW **
0x18000218b  xor     edx, edx; Size
0x18000218d  mov     [rsp+4D0h+lpWideCharStr], rsi; lpWideCharStr
0x180002192  xor     ecx, ecx; Src
0x180002194  mov     rsi, [rsp+4D0h+hMem]
0x180002199  mov     r9, rsi; struct _cnrlink *
0x18000219c  mov     dword ptr [rsp+4D0h+var_4B0], ebx; size_t
0x1800021a0  call    ?UnifyILinkInfo@@YAHPEBU_volumeid@@IPEBGPEBU_cnrlink@@I1PEAPEAU_ilinkinfoW@@@Z; UnifyILinkInfo(_volumeid const *,uint,ushort const *,_cnrlink const *,uint,ushort const *,_ilinkinfoW * *)
0x1800021a5  mov     edi, eax
0x1800021a7  test    ebx, ebx
0x1800021a9  jz      short loc_180002174
0x1800021ab  mov     rcx, rsi; hMem
0x1800021ae  call    cs:__imp_LocalFree
0x1800021b5  nop     dword ptr [rax+rax+00h]
0x1800021ba  jmp     short loc_180002174
0x1800021bc  mov     [rsp+4D0h+nLength], r15d
0x1800021c1  lea     rdx, [rsp+4D0h+RootPathName]
0x1800021c6  mov     rcx, rbx
0x1800021c9  lea     r8, [rsp+4D0h+LocalName]
0x1800021ce  mov     r9d, 3
0x1800021d4  test    rcx, rcx
0x1800021d7  jz      short loc_1800021F6
0x1800021d9  movzx   eax, word ptr [rdx]
0x1800021dc  test    ax, ax
0x1800021df  jz      short loc_1800021F6
0x1800021e1  mov     [r8], ax
0x1800021e5  add     rdx, 2
0x1800021e9  add     r8, 2
0x1800021ed  dec     rcx
0x1800021f0  sub     r9, 1
0x1800021f4  jnz     short loc_1800021D4
0x1800021f6  lea     rcx, [r8-2]
0x1800021fa  test    r9, r9
0x1800021fd  lea     rdx, [rbp+3D0h+RemoteName]; lpRemoteName
0x180002204  cmovnz  rcx, r8
0x180002208  xor     eax, eax
0x18000220a  lea     r8, [rsp+4D0h+nLength]; lpnLength
0x18000220f  mov     [rcx], ax
0x180002212  lea     rcx, [rsp+4D0h+LocalName]; lpLocalName
0x180002217  call    cs:__imp_WNetGetConnectionW
0x18000221e  nop     dword ptr [rax+rax+00h]
0x180002223  test    eax, eax
0x180002225  jnz     loc_18000236F
0x18000222b  mov     edi, 1
0x180002230  mov     r14d, edi
0x180002233  jmp     loc_180002031
0x180002238  lea     rcx, [rsp+4D0h+Buffer]; pszPath
0x18000223d  call    cs:__imp_PathIsUNCW
0x180002244  nop     dword ptr [rax+rax+00h]
0x180002249  mov     edi, eax
0x18000224b  test    eax, eax
0x18000224d  jz      loc_180002390
0x180002253  movzx   ecx, [rsp+4D0h+var_45C]; unsigned __int16
0x180002258  lea     rdx, [rsp+4D0h+var_45C]
0x18000225d  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180002262  test    eax, eax
0x180002264  jnz     short loc_18000228E
0x180002266  nop     word ptr [rax+rax+00000000h]
0x180002270  mov     rcx, rdx; lpsz
0x180002273  call    cs:__imp_CharNextW
0x18000227a  nop     dword ptr [rax+rax+00h]
0x18000227f  mov     rdx, rax
0x180002282  movzx   ecx, word ptr [rax]; unsigned __int16
0x180002285  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x18000228a  test    eax, eax
0x18000228c  jz      short loc_180002270
0x18000228e  mov     rcx, rdx; lpsz
0x180002291  call    cs:__imp_CharNextW
0x180002298  nop     dword ptr [rax+rax+00h]
0x18000229d  mov     rdx, rax
0x1800022a0  movzx   ecx, word ptr [rax]; unsigned __int16
0x1800022a3  test    cx, cx
0x1800022a6  jz      short loc_1800022CB
0x1800022a8  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x1800022ad  test    eax, eax
0x1800022af  jnz     short loc_1800022CB
0x1800022b1  mov     rcx, rdx; lpsz
0x1800022b4  call    cs:__imp_CharNextW
0x1800022bb  nop     dword ptr [rax+rax+00h]
0x1800022c0  mov     rdx, rax
0x1800022c3  movzx   ecx, word ptr [rax]
0x1800022c6  test    cx, cx
0x1800022c9  jnz     short loc_1800022A8
0x1800022cb  lea     rsi, [rdx+2]
0x1800022cf  cmp     [rdx], r12w
0x1800022d3  jz      loc_180002381
0x1800022d9  lea     rax, [rsp+4D0h+Buffer]
0x1800022de  mov     ebx, 7FFFFFFEh
0x1800022e3  sub     rdx, rax
0x1800022e6  sar     rdx, 1
0x1800022e9  cmp     rdx, rbx
0x1800022ec  ja      short loc_180002364
0x1800022ee  lea     rcx, [rsp+4D0h+Buffer]
0x1800022f3  lea     r8, [rbp+3D0h+RemoteName]
0x1800022fa  nop     word ptr [rax+rax+00h]
0x180002300  test    rdx, rdx
0x180002303  jz      short loc_180002322
0x180002305  movzx   eax, word ptr [rcx]
0x180002308  test    ax, ax
0x18000230b  jz      short loc_180002322
0x18000230d  mov     [r8], ax
0x180002311  add     rcx, 2
0x180002315  add     r8, 2
0x180002319  dec     rdx
0x18000231c  sub     r15, 1
0x180002320  jnz     short loc_180002300
0x180002322  test    r15, r15
0x180002325  lea     rcx, [r8-2]
0x180002329  cmovnz  rcx, r8
0x18000232d  xor     eax, eax
0x18000232f  mov     [rcx], ax
0x180002332  lea     rcx, [rbp+3D0h+RemoteName]; lpsz
0x180002339  call    cs:__imp_CharUpperW
0x180002340  nop     dword ptr [rax+rax+00h]
0x180002345  mov     edi, 1
0x18000234a  mov     r14d, edi
0x18000234d  jmp     loc_180002036
0x180002352  xor     eax, eax
0x180002354  mov     r10d, 2
0x18000235a  mov     [rsp+4D0h+LocalName], ax
0x18000235f  jmp     loc_180002141
0x180002364  xor     eax, eax
0x180002366  mov     [rbp+3D0h+RemoteName], ax
0x18000236d  jmp     short loc_180002332
0x18000236f  cmp     eax, 8CAh
0x180002374  jz      loc_18000202C
0x18000237a  xor     edi, edi
0x18000237c  jmp     loc_180002031
0x180002381  xor     eax, eax
0x180002383  mov     word ptr [rdx], 5Ch ; '\'
0x180002388  mov     [rsi], ax
0x18000238b  jmp     loc_1800022D9
0x180002390  xor     r14d, r14d
0x180002393  xor     esi, esi
0x180002395  mov     ecx, 0A1h; dwErrCode
0x18000239a  call    cs:__imp_SetLastError
0x1800023a1  nop     dword ptr [rax+rax+00h]
0x1800023a6  mov     ebx, 7FFFFFFEh
0x1800023ab  jmp     loc_180002036
0x1800023b0  mov     eax, r12d
0x1800023b3  jmp     loc_180002058
0x1800023b8  mov     eax, r12d
0x1800023bb  jmp     loc_180002078
```
