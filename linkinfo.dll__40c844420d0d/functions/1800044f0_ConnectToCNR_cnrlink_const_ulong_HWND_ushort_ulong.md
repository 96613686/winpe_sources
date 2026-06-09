# ConnectToCNR(_cnrlink const *,ulong,HWND__ *,ushort *,ulong *)

- ea: `0x1800044f0`
- end: `0x180004757`
- name: `?ConnectToCNR@@YAHPEBU_cnrlink@@KPEAUHWND__@@PEAGPEAK@Z`
- size: `615`
- prototype: `__int64 __usercall@<rax>(const struct _cnrlink *@<rcx>, DWORD dwFlags@<edx>, HWND@<r8>, unsigned __int16 *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005240`

## callees

- `0x180001ae0`
- `0x180001bd0`
- `0x1800044cc`
- `0x1800044f0`
- `0x1800047fc`
- `0x1800049dc`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180004644`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180004644`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000457a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800045d3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000457a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800045d3`
- `MPR!WNetGetConnectionW` at `0x18000460d`
- `MPR!WNetGetConnectionW` at `0x18000460d`
- `MPR!WNetUseConnectionW` at `0x18000470b`
- `MPR!WNetUseConnectionW` at `0x18000470b`

## pseudocode

```c
__int64 __fastcall ConnectToCNR(
        const struct _cnrlink *a1,
        DWORD dwFlags,
        HWND a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  const struct _cnrlink *v5; // rbx
  const CHAR *v9; // r8
  WCHAR *v10; // r15
  int v11; // r13d
  WCHAR *v12; // rsi
  int v13; // r8d
  unsigned int v14; // ebx
  int NetProviderName; // eax
  unsigned __int16 *lpProvider; // rcx
  DWORD nLength; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v19; // [rsp+44h] [rbp-BCh]
  LPDWORD lpResult; // [rsp+48h] [rbp-B8h]
  HWND hwndOwner; // [rsp+50h] [rbp-B0h]
  struct _NETRESOURCEW NetResource; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR LocalName; // [rsp+88h] [rbp-78h] BYREF
  WCHAR WideCharStr[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR RootPathName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v26[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v5 = (const struct _cnrlink *)((char *)a1 + 20);
  hwndOwner = a3;
  lpResult = a5;
  v19 = 0;
  *a5 = 0;
  v9 = (char *)a1 + *((unsigned int *)a1 + 2);
  nLength = 0;
  if ( v9 == (char *)a1 + 20 )
  {
    v10 = WideCharStr;
    MultiByteToWideChar(0, 0, v9, -1, WideCharStr, 260);
  }
  else
  {
    v10 = (WCHAR *)((char *)a1 + *(unsigned int *)v5);
  }
  if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
  {
    v11 = 1;
    if ( (const struct _cnrlink *)((char *)a1 + *((unsigned int *)a1 + 2)) == v5 )
    {
      v12 = RootPathName;
      MultiByteToWideChar(0, 0, (LPCCH)a1 + *((unsigned int *)a1 + 3), -1, RootPathName, 260);
    }
    else
    {
      v12 = (WCHAR *)((char *)a1 + *((unsigned int *)a1 + 6));
    }
    nLength = 260;
    StringCchCopyW(&LocalName, 3u, v12);
    if ( WNetGetConnectionW(&LocalName, a4, &nLength) )
    {
      v19 = GetDriveTypeW(v12) == 1;
    }
    else if ( !(unsigned int)CompareNetNames(v10, a4) )
    {
      StringCchCopyW(a4, 0x104u, v12);
      v14 = 1;
      goto LABEL_22;
    }
    goto LABEL_13;
  }
  v12 = 0;
  v11 = 0;
  if ( (dwFlags & 0x80u) != 0 )
  {
LABEL_13:
    v14 = SearchForRedirectedConnection(a1, a4);
    if ( v14 )
      goto LABEL_22;
  }
  memset(&NetResource, 0, 24);
  NetResource.dwType = 1;
  NetResource.lpRemoteName = v10;
  *(_OWORD *)&NetResource.lpComment = 0;
  NetProviderName = GetNetProviderName(a1, v26);
  lpProvider = v26;
  if ( !NetProviderName )
    lpProvider = NetResource.lpProvider;
  NetResource.lpProvider = lpProvider;
  if ( v19 )
  {
    NetResource.lpLocalName = v12;
  }
  else if ( v11 )
  {
    dwFlags |= 0x80u;
  }
  nLength = 260;
  if ( WNetUseConnectionW(hwndOwner, &NetResource, 0, 0, dwFlags, a4, &nLength, lpResult) )
    return 0;
  v14 = 1;
LABEL_22:
  CatPath(a4, L"\\", v13);
  return v14;
}

```

## disassembly

```asm
0x1800044f0  push    rbp
0x1800044f2  push    rbx
0x1800044f3  push    rsi
0x1800044f4  push    rdi
0x1800044f5  push    r12
0x1800044f7  push    r13
0x1800044f9  push    r14
0x1800044fb  push    r15
0x1800044fd  lea     rbp, [rsp-5D8h]
0x180004505  sub     rsp, 6D8h
0x18000450c  mov     rax, cs:__security_cookie
0x180004513  xor     rax, rsp
0x180004516  mov     [rbp+610h+var_50], rax
0x18000451d  mov     rax, [rbp+610h+arg_20]
0x180004524  lea     rbx, [rcx+14h]
0x180004528  mov     [rsp+710h+hwndOwner], r8
0x18000452d  mov     r14, r9
0x180004530  mov     r12d, edx
0x180004533  mov     [rsp+710h+var_6C8], rax
0x180004538  mov     rdi, rcx
0x18000453b  mov     [rsp+710h+var_6CC], 0
0x180004543  mov     dword ptr [rax], 0
0x180004549  mov     r8d, [rcx+8]
0x18000454d  add     r8, rcx; int
0x180004550  mov     [rsp+710h+nLength], 0
0x180004558  cmp     r8, rbx
0x18000455b  jnz     short loc_180004588
0x18000455d  lea     rax, [rbp+610h+WideCharStr]
0x180004561  mov     [rsp+710h+cchWideChar], 104h; cchWideChar
0x180004569  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000456d  mov     [rsp+710h+lpWideCharStr], rax; lpWideCharStr
0x180004572  xor     edx, edx; dwFlags
0x180004574  lea     r15, [rbp+610h+WideCharStr]
0x180004578  xor     ecx, ecx; CodePage
0x18000457a  call    cs:__imp_MultiByteToWideChar
0x180004581  nop     dword ptr [rax+rax+00h]
0x180004586  jmp     short loc_18000458E
0x180004588  mov     r15d, [rbx]
0x18000458b  add     r15, rdi
0x18000458e  test    byte ptr [rdi+4], 1
0x180004592  jz      loc_18000465E
0x180004598  mov     eax, [rdi+8]
0x18000459b  mov     r13d, 1
0x1800045a1  add     rax, rdi
0x1800045a4  cmp     rax, rbx
0x1800045a7  jnz     short loc_1800045E1
0x1800045a9  mov     r8d, [rdi+0Ch]
0x1800045ad  lea     rax, [rbp+610h+RootPathName]
0x1800045b4  add     r8, rdi; lpMultiByteStr
0x1800045b7  mov     [rsp+710h+cchWideChar], 104h; cchWideChar
0x1800045bf  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800045c3  mov     [rsp+710h+lpWideCharStr], rax; lpWideCharStr
0x1800045c8  xor     edx, edx; dwFlags
0x1800045ca  lea     rsi, [rbp+610h+RootPathName]
0x1800045d1  xor     ecx, ecx; CodePage
0x1800045d3  call    cs:__imp_MultiByteToWideChar
0x1800045da  nop     dword ptr [rax+rax+00h]
0x1800045df  jmp     short loc_1800045E7
0x1800045e1  mov     esi, [rdi+18h]
0x1800045e4  add     rsi, rdi
0x1800045e7  mov     ebx, 104h
0x1800045ec  lea     rcx, [rbp+610h+LocalName]; unsigned __int16 *
0x1800045f0  mov     r8, rsi; unsigned __int16 *
0x1800045f3  mov     [rsp+710h+nLength], ebx
0x1800045f7  mov     edx, 3; unsigned __int64
0x1800045fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004601  lea     r8, [rsp+710h+nLength]; lpnLength
0x180004606  mov     rdx, r14; lpRemoteName
0x180004609  lea     rcx, [rbp+610h+LocalName]; lpLocalName
0x18000460d  call    cs:__imp_WNetGetConnectionW
0x180004614  nop     dword ptr [rax+rax+00h]
0x180004619  test    eax, eax
0x18000461b  jnz     short loc_180004641
0x18000461d  mov     rdx, r14
0x180004620  mov     rcx, r15
0x180004623  call    ?CompareNetNames@@YA?AW4_comparisonresult@@PEBG0@Z; CompareNetNames(ushort const *,ushort const *)
0x180004628  test    eax, eax
0x18000462a  jnz     short loc_180004668
0x18000462c  mov     r8, rsi; unsigned __int16 *
0x18000462f  mov     edx, ebx; unsigned __int64
0x180004631  mov     rcx, r14; unsigned __int16 *
0x180004634  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004639  mov     ebx, r13d
0x18000463c  jmp     loc_18000471E
0x180004641  mov     rcx, rsi; lpRootPathName
0x180004644  call    cs:__imp_GetDriveTypeW
0x18000464b  nop     dword ptr [rax+rax+00h]
0x180004650  xor     ecx, ecx
0x180004652  cmp     eax, r13d
0x180004655  setz    cl
0x180004658  mov     [rsp+710h+var_6CC], ecx
0x18000465c  jmp     short loc_180004668
0x18000465e  xor     esi, esi
0x180004660  xor     r13d, r13d
0x180004663  test    r12b, r12b
0x180004666  jns     short loc_18000467D
0x180004668  mov     rdx, r14; unsigned __int16 *
0x18000466b  mov     rcx, rdi; struct tagICNRLINKW *
0x18000466e  call    ?SearchForRedirectedConnection@@YAHQEBUtagICNRLINKW@@PEAGH@Z; SearchForRedirectedConnection(tagICNRLINKW const * const,ushort *,int)
0x180004673  mov     ebx, eax
0x180004675  test    eax, eax
0x180004677  jnz     loc_18000471E
0x18000467d  xorps   xmm0, xmm0
0x180004680  lea     rdx, [rbp+610h+var_260]; unsigned __int16 *
0x180004687  movups  xmmword ptr [rsp+710h+NetResource.dwScope], xmm0
0x18000468c  mov     rcx, rdi; struct tagICNRLINKW *
0x18000468f  mov     [rsp+710h+NetResource.dwType], 1
0x180004697  movups  xmmword ptr [rsp+710h+NetResource.lpLocalName], xmm0
0x18000469c  mov     [rsp+710h+NetResource.lpRemoteName], r15
0x1800046a1  movups  xmmword ptr [rsp+710h+NetResource.lpComment], xmm0
0x1800046a6  call    ?GetNetProviderName@@YAHQEBUtagICNRLINKW@@PEAG@Z; GetNetProviderName(tagICNRLINKW const * const,ushort *)
0x1800046ab  test    eax, eax
0x1800046ad  lea     rcx, [rbp+610h+var_260]
0x1800046b4  cmovz   rcx, [rbp+610h+NetResource.lpProvider]
0x1800046b9  cmp     [rsp+710h+var_6CC], 0
0x1800046be  mov     [rbp+610h+NetResource.lpProvider], rcx
0x1800046c2  jz      short loc_1800046CB
0x1800046c4  mov     [rsp+710h+NetResource.lpLocalName], rsi
0x1800046c9  jmp     short loc_1800046D5
0x1800046cb  test    r13d, r13d
0x1800046ce  jz      short loc_1800046D5
0x1800046d0  bts     r12d, 7
0x1800046d5  mov     rax, [rsp+710h+var_6C8]
0x1800046da  lea     rdx, [rsp+710h+NetResource]; lpNetResource
0x1800046df  mov     rcx, [rsp+710h+hwndOwner]; hwndOwner
0x1800046e4  xor     r9d, r9d; lpUserId
0x1800046e7  mov     [rsp+710h+lpResult], rax; lpResult
0x1800046ec  xor     r8d, r8d; lpPassword
0x1800046ef  lea     rax, [rsp+710h+nLength]
0x1800046f4  mov     [rsp+710h+nLength], 104h
0x1800046fc  mov     [rsp+710h+lpBufferSize], rax; lpBufferSize
0x180004701  mov     qword ptr [rsp+710h+cchWideChar], r14; lpAccessName
0x180004706  mov     dword ptr [rsp+710h+lpWideCharStr], r12d; dwFlags
0x18000470b  call    cs:__imp_WNetUseConnectionW
0x180004712  nop     dword ptr [rax+rax+00h]
0x180004717  test    eax, eax
0x180004719  jnz     short loc_18000472F
0x18000471b  lea     ebx, [rax+1]
0x18000471e  lea     rdx, asc_180006504; "\\"
0x180004725  mov     rcx, r14; unsigned __int16 *
0x180004728  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x18000472d  jmp     short loc_180004731
0x18000472f  xor     ebx, ebx
0x180004731  mov     eax, ebx
0x180004733  mov     rcx, [rbp+610h+var_50]
0x18000473a  xor     rcx, rsp; StackCookie
0x18000473d  call    __security_check_cookie
0x180004742  add     rsp, 6D8h
0x180004749  pop     r15
0x18000474b  pop     r14
0x18000474d  pop     r13
0x18000474f  pop     r12
0x180004751  pop     rdi
0x180004752  pop     rsi
0x180004753  pop     rbx
0x180004754  pop     rbp
0x180004755  retn
```
