# CreateShare(ushort *,ushort *,ushort *,uchar *,uchar *,long *,long *,uchar *,ulong *,ulong *,ulong *,_LIST_ENTRY *,CNfsTaskContext *,uchar)

- ea: `0x18001d798`
- end: `0x18001dce3`
- name: `?CreateShare@@YAKPEAG00PEAE1PEAJ21PEAK33PEAU_LIST_ENTRY@@PEAVCNfsTaskContext@@E@Z`
- size: `1355`
- prototype: `unsigned int __usercall@<eax>(unsigned __int16 *@<rcx>, LPCWCH lpSrcStr@<rdx>, unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *, int *, int *, unsigned __int8 *, unsigned int *, unsigned int *, unsigned int *, struct _LIST_ENTRY *, struct CNfsTaskContext *, unsigned __int8)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009c88`
- `0x18000a144`

## callees

- `0x180006a54`
- `0x18001d320`
- `0x18001d798`
- `0x18001dcec`
- `0x18001e358`
- `0x18001e418`
- `0x18001e8b8`
- `0x18001ea14`
- `0x18001eb14`
- `0x18001eb70`
- `0x18001ef68`
- `0x180020d94`
- `0x18002115c`
- `0x180021318`
- `0x1800219fc`
- `0x180029d60`
- `0x18002d45c`
- `0x180034714`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d9a2`
- `msvcrt!_wcsicmp` at `0x18001db5a`
- `msvcrt!_wcsicmp` at `0x18001d9a2`
- `msvcrt!_wcsicmp` at `0x18001db5a`
- `ntdll!RtlInitUnicodeString` at `0x18001d965`
- `ntdll!RtlInitUnicodeString` at `0x18001d974`
- `ntdll!RtlInitUnicodeString` at `0x18001da3a`
- `ntdll!RtlInitUnicodeString` at `0x18001da6e`
- `ntdll!RtlInitUnicodeString` at `0x18001d965`
- `ntdll!RtlInitUnicodeString` at `0x18001d974`
- `ntdll!RtlInitUnicodeString` at `0x18001da3a`
- `ntdll!RtlInitUnicodeString` at `0x18001da6e`
- `KERNEL32!HeapFree` at `0x18001dcb1`
- `KERNEL32!HeapFree` at `0x18001dcb1`
- `KERNEL32!GetLastError` at `0x18001db40`
- `KERNEL32!GetLastError` at `0x18001db40`
- `KERNEL32!GetProcessHeap` at `0x18001dca3`
- `KERNEL32!GetProcessHeap` at `0x18001dca3`
- `KERNEL32!GetComputerNameExW` at `0x18001db36`
- `KERNEL32!GetComputerNameExW` at `0x18001db36`

## pseudocode

```c
__int64 __fastcall CreateShare(
        unsigned __int16 *a1,
        LPCWCH lpSrcStr,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        int *a6,
        int *a7,
        unsigned __int8 *a8,
        unsigned int *a9,
        unsigned int *a10,
        unsigned int *a11,
        struct _LIST_ENTRY *a12,
        struct CNfsTaskContext *a13,
        unsigned __int8 a14)
{
  void *v17; // r15
  DWORD NfsShareList; // ebx
  struct _LIST_ENTRY *Flink; // r13
  char v20; // si
  struct _LIST_ENTRY *v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  unsigned __int8 v26; // si
  struct _LIST_ENTRY *v27; // rbx
  unsigned int v28; // eax
  DWORD Share; // eax
  unsigned int v30; // esi
  HANDLE ProcessHeap; // rax
  unsigned __int8 v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v34; // [rsp+51h] [rbp-AFh] BYREF
  unsigned __int8 v35; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int8 v36; // [rsp+53h] [rbp-ADh] BYREF
  DWORD nSize; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int8 v38; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v39[7]; // [rsp+59h] [rbp-A7h] BYREF
  unsigned __int16 *v40; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v41; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-88h]
  struct _LIST_ENTRY v44; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v45; // [rsp+90h] [rbp-70h]
  struct _LIST_ENTRY *v46; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v47; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING v48; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v49; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v50; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v51[80]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v52[3]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v53; // [rsp+13Ch] [rbp+3Ch]
  unsigned __int16 v54[262]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v55[268]; // [rsp+35Ch] [rbp+25Ch] BYREF
  _BYTE v56[588]; // [rsp+574h] [rbp+474h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+7C0h] [rbp+6C0h] BYREF

  SourceString = lpSrcStr;
  v46 = a12;
  *(_DWORD *)&v39[3] = 0;
  v33 = 0;
  lpMem = 0;
  v17 = 0;
  v41 = 0;
  v47 = a4;
  memset_0(v52, 0, 0x688u);
  v35 = 0;
  v36 = 0;
  v34 = 0;
  v50 = 0;
  LOWORD(nSize) = 0;
  v49 = 0;
  v40 = 0;
  v44 = 0;
  if ( !(unsigned int)IsAliasFormatValid(lpSrcStr) )
  {
    NfsShareList = 87;
    (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64))(*(_QWORD *)a13 + 40LL))(a13, 87, 3221229638LL);
    return NfsShareList;
  }
  NfsShareList = CheckPathExportableEx(
                   a1,
                   a13,
                   &v36,
                   &v33,
                   (DWORD)v39,
                   &v38,
                   &v34,
                   &v35,
                   (unsigned __int16 *)&nSize,
                   &v40);
  if ( !NfsShareList )
  {
    if ( !v36 )
    {
      (*(void (__fastcall **)(struct CNfsTaskContext *, __int64))(*(_QWORD *)a13 + 88LL))(a13, 2147483654LL);
      return 1005;
    }
    if ( v34 )
      a1 = v40;
    v45 = a1;
    NfsShareList = GetNfsShareList(&v44);
    if ( !NfsShareList )
    {
      Flink = v44.Flink;
      v20 = 0;
      while ( Flink != &v44 )
      {
        v21 = Flink - 1;
        Flink = Flink->Flink;
        v40 = (unsigned __int16 *)v21;
        DestinationString = 0;
        v48 = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)&v21[34].Blink + 2);
        RtlInitUnicodeString(&v48, SourceString);
        if ( (unsigned __int8)CompareUnicodeShareNames(&DestinationString, &v48) && (!a3 || !_wcsicmp(a3, v40 + 549)) )
        {
          NfsShareList = 183;
          v22 = 3221229589LL;
          v23 = 183;
LABEL_22:
          (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64))(*(_QWORD *)a13 + 40LL))(a13, v23, v22);
          goto LABEL_23;
        }
        if ( v20 || (*(_DWORD *)v40 & 0x2000000) != 0 )
          v20 = 1;
      }
      if ( v35
        && !v20
        && !(*(unsigned __int8 (__fastcall **)(struct CNfsTaskContext *, __int64))(*(_QWORD *)a13 + 48LL))(
              a13,
              2147487849LL) )
      {
        NfsShareList = 87;
        v22 = 1073745929;
        v23 = 87;
        goto LABEL_22;
      }
LABEL_23:
      FreeNfsExportList(&v44);
      if ( !NfsShareList )
      {
        InitializeNfsExportEntry((struct _NFS_EXPORT *)v52);
        RtlInitUnicodeString(&v49, v45);
        v24 = StringCchCopyW(v54, 0x106u, v49.Buffer);
        NfsShareList = NfsGetErrorFromHr(v24);
        if ( !NfsShareList )
        {
          RtlInitUnicodeString(&v50, SourceString);
          v25 = StringCchCopyW(v55, 0x106u, v50.Buffer);
          NfsShareList = NfsGetErrorFromHr(v25);
          if ( !NfsShareList )
          {
            v26 = v33;
            if ( v34 && v33 )
            {
              v52[0] |= 0x1800000u;
              v53 = nSize;
            }
            else if ( v35 && v33 )
            {
              v52[0] |= 0x2800000u;
            }
            else
            {
              NfsShareList = IsPathClusteredEx(v54, &v33);
              if ( NfsShareList )
                return NfsShareList;
              v26 = v33;
            }
            if ( !v26 )
              goto LABEL_38;
            if ( a14 )
            {
              v26 = 0;
              (*(void (__fastcall **)(struct CNfsTaskContext *, const wchar_t *))(*(_QWORD *)a13 + 16LL))(
                a13,
                L"Cluster override switch is enabled - treating clustered disk as if it's non-clustered");
            }
            if ( !v26 )
            {
LABEL_38:
              if ( a3 )
              {
                nSize = 16;
                if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, &DestinationString.Length, &nSize) )
                {
                  NfsShareList = GetLastError();
                  if ( NfsShareList )
                    return NfsShareList;
                }
                if ( _wcsicmp(&DestinationString.Length, a3) )
                {
                  NfsShareList = 87;
                  (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, unsigned __int16 *))(*(_QWORD *)a13 + 40LL))(
                    a13,
                    87,
                    3221229643LL,
                    a3);
                  return NfsShareList;
                }
              }
            }
            v27 = v46;
            if ( v46 )
            {
              SortPermissionsList(v46, 0, v56);
              v28 = CreateSharePermissionString(v27, (unsigned __int16 **)&lpMem, &v41);
              v17 = lpMem;
              NfsShareList = v28;
              if ( v28 )
                goto LABEL_52;
            }
            UpdateShareProperties(
              (unsigned int)v52,
              (_DWORD)v47,
              (_DWORD)a5,
              (_DWORD)a6,
              (__int64)a7,
              (__int64)a8,
              (__int64)a9,
              (__int64)a10,
              (__int64)a11);
            ValidateShareConfig((struct _NFS_EXPORT *)v52, a13);
            if ( v26 )
            {
              memset_0(v51, 0, 0x48u);
              NfsShareList = InitializeClusterParams(v52, v17, v51);
              if ( NfsShareList )
              {
LABEL_52:
                if ( v17 )
                {
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v17);
                }
                return NfsShareList;
              }
              Share = NfsClusCreateShareEx((struct _NFS_SHARE_PARAMS *)v51, a3, a13, (unsigned int *)&v39[3]);
            }
            else
            {
              Share = NfsCreateShareCore(v52, v17, &v39[3]);
            }
            NfsShareList = Share;
            if ( !Share )
            {
              v30 = *(_DWORD *)&v39[3];
              if ( *(_DWORD *)&v39[3] )
              {
                (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD))(*(_QWORD *)a13 + 88LL))(
                  a13,
                  *(unsigned int *)&v39[3]);
                NfsShareList = GetWin32ErrorForNfsError(v30);
              }
            }
            goto LABEL_52;
          }
        }
      }
    }
  }
  return NfsShareList;
}

```

## disassembly

```asm
0x18001d798  mov     [rsp-8+arg_18], rbx
0x18001d79d  push    rbp
0x18001d79e  push    rsi
0x18001d79f  push    rdi
0x18001d7a0  push    r12
0x18001d7a2  push    r13
0x18001d7a4  push    r14
0x18001d7a6  push    r15
0x18001d7a8  lea     rbp, [rsp-6F0h]
0x18001d7b0  sub     rsp, 7F0h
0x18001d7b7  mov     rax, cs:__security_cookie
0x18001d7be  xor     rax, rsp
0x18001d7c1  mov     [rbp+720h+var_40], rax
0x18001d7c8  mov     rax, [rbp+720h+arg_58]
0x18001d7cf  xor     r14d, r14d
0x18001d7d2  mov     rdi, [rbp+720h+arg_60]
0x18001d7d9  mov     r12, r8
0x18001d7dc  mov     rbx, rdx
0x18001d7df  mov     [rsp+820h+SourceString], rdx
0x18001d7e4  mov     rsi, rcx
0x18001d7e7  mov     [rbp+720h+var_788], rax
0x18001d7eb  xor     edx, edx; Val
0x18001d7ed  mov     dword ptr [rsp+820h+var_7C7+3], r14d
0x18001d7f2  mov     r8d, 688h; Size
0x18001d7f8  mov     [rsp+820h+var_7D0], r14b
0x18001d7fd  lea     rcx, [rbp+720h+var_6F0]; void *
0x18001d801  mov     [rsp+820h+lpMem], r14
0x18001d806  mov     r15d, r14d
0x18001d809  mov     [rsp+820h+var_7B8], r14d
0x18001d80e  mov     [rbp+720h+var_780], r9
0x18001d812  call    memset_0
0x18001d817  mov     r8, [rbp+720h+arg_40]
0x18001d81e  xorps   xmm0, xmm0
0x18001d821  xorps   xmm1, xmm1
0x18001d824  mov     [rsp+820h+var_7CE], r14b
0x18001d829  mov     rdx, rdi
0x18001d82c  mov     [rsp+820h+var_7CD], r14b
0x18001d831  mov     rcx, rbx; lpSrcStr
0x18001d834  mov     [rsp+820h+var_7CF], r14b
0x18001d839  movups  xmmword ptr [rbp+720h+var_758.Length], xmm0
0x18001d83d  mov     word ptr [rsp+820h+nSize], r14w
0x18001d843  movups  xmmword ptr [rbp+720h+var_768.Length], xmm1
0x18001d847  mov     [rsp+820h+var_7C0], r14
0x18001d84c  movups  xmmword ptr [rbp+720h+var_7A0.Flink], xmm0
0x18001d850  call    IsAliasFormatValid
0x18001d855  test    eax, eax
0x18001d857  jnz     short loc_18001D87D
0x18001d859  mov     rax, [rdi]
0x18001d85c  lea     r14d, [r15+57h]
0x18001d860  mov     r8d, 0C0001046h
0x18001d866  mov     edx, r14d
0x18001d869  mov     rcx, rdi
0x18001d86c  mov     ebx, r14d
0x18001d86f  mov     rax, [rax+28h]
0x18001d873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d878  jmp     loc_18001DCB7
0x18001d87d  lea     rax, [rsp+820h+var_7C0]
0x18001d882  mov     rdx, rdi; struct CNfsTaskContext *
0x18001d885  mov     [rsp+820h+var_7D8], rax; unsigned __int16 **
0x18001d88a  lea     r9, [rsp+820h+var_7D0]; unsigned __int8 *
0x18001d88f  lea     rax, [rsp+820h+nSize]
0x18001d894  mov     rcx, rsi; unsigned __int16 *
0x18001d897  mov     [rsp+820h+var_7E0], rax; unsigned __int16 *
0x18001d89c  lea     r8, [rsp+820h+var_7CD]; unsigned __int8 *
0x18001d8a1  lea     rax, [rsp+820h+var_7CE]
0x18001d8a6  mov     [rsp+820h+var_7E8], rax; unsigned __int8 *
0x18001d8ab  lea     rax, [rsp+820h+var_7CF]
0x18001d8b0  mov     [rsp+820h+var_7F0], rax; unsigned __int8 *
0x18001d8b5  lea     rax, [rsp+820h+var_7C8]
0x18001d8ba  mov     [rsp+820h+var_7F8], rax; unsigned __int8 *
0x18001d8bf  lea     rax, [rsp+820h+var_7C7]
0x18001d8c4  mov     qword ptr [rsp+820h+pdwValue], rax; pdwValue
0x18001d8c9  call    ?CheckPathExportableEx@@YAKPEAGPEAVCNfsTaskContext@@PEAE222220PEAPEAG@Z; CheckPathExportableEx(ushort *,CNfsTaskContext *,uchar *,uchar *,uchar *,uchar *,uchar *,uchar *,ushort *,ushort * *)
0x18001d8ce  mov     ebx, eax
0x18001d8d0  test    eax, eax
0x18001d8d2  jnz     loc_18001DCB7
0x18001d8d8  cmp     [rsp+820h+var_7CD], r14b
0x18001d8dd  jnz     short loc_18001D8FD
0x18001d8df  mov     rax, [rdi]
0x18001d8e2  mov     edx, 80000006h
0x18001d8e7  mov     rcx, rdi
0x18001d8ea  mov     rax, [rax+58h]
0x18001d8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f3  mov     ebx, 3EDh
0x18001d8f8  jmp     loc_18001DCB7
0x18001d8fd  cmp     [rsp+820h+var_7CF], r14b
0x18001d902  lea     rcx, [rbp+720h+var_7A0]; struct _LIST_ENTRY *
0x18001d906  cmovnz  rsi, [rsp+820h+var_7C0]
0x18001d90c  mov     [rbp+720h+var_790], rsi
0x18001d910  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x18001d915  mov     ebx, eax
0x18001d917  test    eax, eax
0x18001d919  jnz     loc_18001DCB7
0x18001d91f  mov     r13, [rbp+720h+var_7A0.Flink]
0x18001d923  mov     sil, r14b
0x18001d926  lea     rax, [rbp+720h+var_7A0]
0x18001d92a  mov     r14d, 57h ; 'W'
0x18001d930  cmp     r13, rax
0x18001d933  jz      loc_18001D9D9
0x18001d939  lea     rax, [r13-10h]
0x18001d93d  xorps   xmm0, xmm0
0x18001d940  mov     r13, [r13+0]
0x18001d944  lea     rdx, [rax+22Ch]; SourceString
0x18001d94b  xorps   xmm1, xmm1
0x18001d94e  mov     [rsp+820h+var_7C0], rax
0x18001d953  lea     rcx, [rbp+720h+DestinationString]; DestinationString
0x18001d95a  movups  xmmword ptr [rbp+720h+DestinationString.Length], xmm0
0x18001d961  movups  xmmword ptr [rbp+720h+var_778.Length], xmm1
0x18001d965  call    cs:__imp_RtlInitUnicodeString
0x18001d96b  mov     rdx, [rsp+820h+SourceString]; SourceString
0x18001d970  lea     rcx, [rbp+720h+var_778]; DestinationString
0x18001d974  call    cs:__imp_RtlInitUnicodeString
0x18001d97a  lea     rdx, [rbp+720h+var_778]
0x18001d97e  lea     rcx, [rbp+720h+DestinationString]
0x18001d985  call    CompareUnicodeShareNames
0x18001d98a  test    al, al
0x18001d98c  jz      short loc_18001D9AC
0x18001d98e  test    r12, r12
0x18001d991  jz      short loc_18001D9CA
0x18001d993  mov     rdx, [rsp+820h+var_7C0]
0x18001d998  mov     rcx, r12; String1
0x18001d99b  add     rdx, 44Ah; String2
0x18001d9a2  call    cs:__imp__wcsicmp
0x18001d9a8  test    eax, eax
0x18001d9aa  jz      short loc_18001D9CA
0x18001d9ac  test    sil, sil
0x18001d9af  jnz     short loc_18001D9C2
0x18001d9b1  mov     rax, [rsp+820h+var_7C0]
0x18001d9b6  test    dword ptr [rax], 2000000h
0x18001d9bc  jz      loc_18001D926
0x18001d9c2  mov     sil, 1
0x18001d9c5  jmp     loc_18001D926
0x18001d9ca  mov     ebx, 0B7h
0x18001d9cf  mov     r8d, 0C0001015h
0x18001d9d5  mov     edx, ebx
0x18001d9d7  jmp     short loc_18001DA09
0x18001d9d9  cmp     [rsp+820h+var_7CE], r15b
0x18001d9de  jz      short loc_18001DA18
0x18001d9e0  test    sil, sil
0x18001d9e3  jnz     short loc_18001DA18
0x18001d9e5  mov     rax, [rdi]
0x18001d9e8  mov     edx, 80001069h
0x18001d9ed  mov     rcx, rdi
0x18001d9f0  mov     rax, [rax+30h]
0x18001d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f9  test    al, al
0x18001d9fb  jnz     short loc_18001DA18
0x18001d9fd  mov     ebx, r14d
0x18001da00  mov     r8d, 40001009h
0x18001da06  mov     edx, r14d
0x18001da09  mov     rax, [rdi]
0x18001da0c  mov     rcx, rdi
0x18001da0f  mov     rax, [rax+28h]
0x18001da13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da18  lea     rcx, [rbp+720h+var_7A0]; struct _LIST_ENTRY *
0x18001da1c  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18001da21  test    ebx, ebx
0x18001da23  jnz     loc_18001DCB7
0x18001da29  lea     rcx, [rbp+720h+var_6F0]; struct _NFS_EXPORT *
0x18001da2d  call    ?InitializeNfsExportEntry@@YAXPEAU_NFS_EXPORT@@@Z; InitializeNfsExportEntry(_NFS_EXPORT *)
0x18001da32  mov     rdx, [rbp+720h+var_790]; SourceString
0x18001da36  lea     rcx, [rbp+720h+var_768]; DestinationString
0x18001da3a  call    cs:__imp_RtlInitUnicodeString
0x18001da40  mov     r8, [rbp+720h+var_768.Buffer]; unsigned __int16 *
0x18001da44  lea     rcx, [rbp+720h+var_6D0]; unsigned __int16 *
0x18001da48  mov     esi, 106h
0x18001da4d  mov     edx, esi; unsigned __int64
0x18001da4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001da54  mov     ecx, eax; int
0x18001da56  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001da5b  mov     ebx, eax
0x18001da5d  test    eax, eax
0x18001da5f  jnz     loc_18001DCB7
0x18001da65  mov     rdx, [rsp+820h+SourceString]; SourceString
0x18001da6a  lea     rcx, [rbp+720h+var_758]; DestinationString
0x18001da6e  call    cs:__imp_RtlInitUnicodeString
0x18001da74  mov     r8, [rbp+720h+var_758.Buffer]; unsigned __int16 *
0x18001da78  lea     rcx, [rbp+720h+var_4C4]; unsigned __int16 *
0x18001da7f  mov     edx, esi; unsigned __int64
0x18001da81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001da86  mov     ecx, eax; int
0x18001da88  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18001da8d  mov     ebx, eax
0x18001da8f  test    eax, eax
0x18001da91  jnz     loc_18001DCB7
0x18001da97  mov     sil, [rsp+820h+var_7D0]
0x18001da9c  cmp     [rsp+820h+var_7CF], r15b
0x18001daa1  jz      short loc_18001DABA
0x18001daa3  test    sil, sil
0x18001daa6  jz      short loc_18001DABA
0x18001daa8  movzx   eax, word ptr [rsp+820h+nSize]
0x18001daad  or      [rbp+720h+var_6F0], 1800000h
0x18001dab4  mov     [rbp+720h+var_6E4], ax
0x18001dab8  jmp     short loc_18001DAEC
0x18001daba  cmp     [rsp+820h+var_7CE], r15b
0x18001dabf  jz      short loc_18001DACF
0x18001dac1  test    sil, sil
0x18001dac4  jz      short loc_18001DACF
0x18001dac6  or      [rbp+720h+var_6F0], 2800000h
0x18001dacd  jmp     short loc_18001DAEC
0x18001dacf  lea     rdx, [rsp+820h+var_7D0]
0x18001dad4  lea     rcx, [rbp+720h+var_6D0]
0x18001dad8  call    IsPathClusteredEx
0x18001dadd  mov     ebx, eax
0x18001dadf  test    eax, eax
0x18001dae1  jnz     loc_18001DCB7
0x18001dae7  mov     sil, [rsp+820h+var_7D0]
0x18001daec  test    sil, sil
0x18001daef  jz      short loc_18001DB18
0x18001daf1  cmp     [rbp+720h+arg_68], r15b
0x18001daf8  jz      short loc_18001DB13
0x18001dafa  mov     rax, [rdi]
0x18001dafd  lea     rdx, aClusterOverrid; "Cluster override switch is enabled - tr"...
0x18001db04  xor     sil, sil
0x18001db07  mov     rcx, rdi
0x18001db0a  mov     rax, [rax+10h]
0x18001db0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db13  test    sil, sil
0x18001db16  jnz     short loc_18001DB87
0x18001db18  test    r12, r12
0x18001db1b  jz      short loc_18001DB87
0x18001db1d  lea     r8, [rsp+820h+nSize]; nSize
0x18001db22  mov     [rsp+820h+nSize], 10h
0x18001db2a  lea     rdx, [rbp+720h+DestinationString]; lpBuffer
0x18001db31  mov     ecx, 4; NameType
0x18001db36  call    cs:__imp_GetComputerNameExW
0x18001db3c  test    eax, eax
0x18001db3e  jnz     short loc_18001DB50
0x18001db40  call    cs:__imp_GetLastError
0x18001db46  mov     ebx, eax
0x18001db48  test    eax, eax
0x18001db4a  jnz     loc_18001DCB7
0x18001db50  mov     rdx, r12; String2
0x18001db53  lea     rcx, [rbp+720h+DestinationString]; String1
0x18001db5a  call    cs:__imp__wcsicmp
0x18001db60  test    eax, eax
0x18001db62  jz      short loc_18001DB87
0x18001db64  mov     rax, [rdi]
0x18001db67  mov     r9, r12
0x18001db6a  mov     r8d, 0C000104Bh
0x18001db70  mov     edx, r14d
0x18001db73  mov     rcx, rdi
0x18001db76  mov     ebx, r14d
0x18001db79  mov     rax, [rax+28h]
0x18001db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db82  jmp     loc_18001DCB7
0x18001db87  mov     rbx, [rbp+720h+var_788]
0x18001db8b  test    rbx, rbx
0x18001db8e  jz      short loc_18001DBC2
0x18001db90  lea     r8, [rbp+720h+var_2AC]
0x18001db97  xor     edx, edx
0x18001db99  mov     rcx, rbx
0x18001db9c  call    SortPermissionsList
0x18001dba1  lea     r8, [rsp+820h+var_7B8]; unsigned int *
0x18001dba6  mov     rcx, rbx; struct _LIST_ENTRY *
0x18001dba9  lea     rdx, [rsp+820h+lpMem]; unsigned __int16 **
0x18001dbae  call    ?CreateSharePermissionString@@YAKPEAU_LIST_ENTRY@@PEAPEAGPEAK@Z; CreateSharePermissionString(_LIST_ENTRY *,ushort * *,ulong *)
0x18001dbb3  mov     r15, [rsp+820h+lpMem]
0x18001dbb8  mov     ebx, eax
0x18001dbba  test    eax, eax
0x18001dbbc  jnz     loc_18001DC9E
0x18001dbc2  mov     rax, [rbp+720h+arg_50]
0x18001dbc9  lea     rcx, [rbp+720h+var_6F0]
0x18001dbcd  mov     r9, [rbp+720h+arg_28]
0x18001dbd4  mov     r8, [rbp+720h+arg_20]
0x18001dbdb  mov     rdx, [rbp+720h+var_780]
0x18001dbdf  mov     [rsp+820h+var_7E0], rax
0x18001dbe4  mov     rax, [rbp+720h+arg_48]
0x18001dbeb  mov     [rsp+820h+var_7E8], rax
0x18001dbf0  mov     rax, [rbp+720h+arg_40]
0x18001dbf7  mov     [rsp+820h+var_7F0], rax
0x18001dbfc  mov     rax, [rbp+720h+arg_38]
0x18001dc03  mov     [rsp+820h+var_7F8], rax
0x18001dc08  mov     rax, [rbp+720h+arg_30]
0x18001dc0f  mov     qword ptr [rsp+820h+pdwValue], rax
0x18001dc14  call    UpdateShareProperties
0x18001dc19  mov     rdx, rdi; struct CNfsTaskContext *
0x18001dc1c  lea     rcx, [rbp+720h+var_6F0]; struct _NFS_EXPORT *
0x18001dc20  call    ?ValidateShareConfig@@YAXPEAU_NFS_EXPORT@@PEAVCNfsTaskContext@@@Z; ValidateShareConfig(_NFS_EXPORT *,CNfsTaskContext *)
0x18001dc25  test    sil, sil
0x18001dc28  jz      short loc_18001DC65
0x18001dc2a  xor     edx, edx; Val
0x18001dc2c  lea     rcx, [rbp+720h+var_740]; void *
0x18001dc30  lea     r8d, [rdx+48h]; Size
0x18001dc34  call    memset_0
0x18001dc39  lea     r8, [rbp+720h+var_740]
0x18001dc3d  mov     rdx, r15
0x18001dc40  lea     rcx, [rbp+720h+var_6F0]
0x18001dc44  call    InitializeClusterParams
0x18001dc49  mov     ebx, eax
0x18001dc4b  test    eax, eax
0x18001dc4d  jnz     short loc_18001DC9E
0x18001dc4f  lea     r9, [rsp+820h+var_7C7+3]; unsigned int *
0x18001dc54  mov     r8, rdi; struct CNfsTaskContext *
0x18001dc57  mov     rdx, r12; unsigned __int16 *
0x18001dc5a  lea     rcx, [rbp+720h+var_740]; struct _NFS_SHARE_PARAMS *
0x18001dc5e  call    ?NfsClusCreateShareEx@@YAKPEAU_NFS_SHARE_PARAMS@@PEAGPEAVCNfsTaskContext@@PEAK@Z; NfsClusCreateShareEx(_NFS_SHARE_PARAMS *,ushort *,CNfsTaskContext *,ulong *)
0x18001dc63  jmp     short loc_18001DC76
0x18001dc65  lea     r8, [rsp+820h+var_7C7+3]
0x18001dc6a  mov     rdx, r15
  ... truncated ...
```
