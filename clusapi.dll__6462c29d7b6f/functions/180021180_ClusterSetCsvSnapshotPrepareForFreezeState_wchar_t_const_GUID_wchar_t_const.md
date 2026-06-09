# ClusterSetCsvSnapshotPrepareForFreezeState(wchar_t const *,_GUID,wchar_t const *)

- ea: `0x180021180`
- end: `0x180021395`
- name: `?ClusterSetCsvSnapshotPrepareForFreezeState@@YAKPEB_WU_GUID@@0@Z`
- size: `533`
- prototype: `unsigned int __fastcall(const wchar_t *, struct _GUID *__struct_ptr, const wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002cce0`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001236c`
- `0x18001fd7c`
- `0x18001fe48`
- `0x18001fe7c`
- `0x180021180`
- `0x18002ea30`
- `0x180052d30`
- `0x1800589e0`
- `0x1800590f0`
- `0x18006d3e0`
- `0x1800acfe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180021304`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180021304`
- `RPCRT4!UuidFromStringW` at `0x1800212de`
- `RPCRT4!UuidFromStringW` at `0x1800212de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002120e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002129b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002120e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002129b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180021204`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180021204`

## pseudocode

```c
DWORD __fastcall ClusterSetCsvSnapshotPrepareForFreezeState(const wchar_t *a1, struct _GUID *a2, const wchar_t *a3)
{
  struct _HCLUSTER *v7; // rax
  struct _HCLUSTER *v8; // rbx
  DWORD v9; // ebx
  struct _HRESOURCE *v10; // rdi
  struct _HNODE *v11; // rbx
  DWORD LastError; // eax
  __int128 v13; // xmm0
  DWORD GrantedAccess; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  HRESOURCE v17; // [rsp+60h] [rbp-A0h] BYREF
  HNODE v18; // [rsp+68h] [rbp-98h] BYREF
  struct _HCLUSTER *v19; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+88h] [rbp-78h]
  UUID Uuid; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+A8h] [rbp-58h]
  _BYTE v24[3008]; // [rsp+8C0h] [rbp+7C0h] BYREF
  unsigned __int16 StringUuid[40]; // [rsp+1480h] [rbp+1380h] BYREF
  WCHAR Buffer[256]; // [rsp+14D0h] [rbp+13D0h] BYREF
  WCHAR szNodeId[264]; // [rsp+16D0h] [rbp+15D0h] BYREF

  GrantedAccess = 0;
  memset_0(&v20, 0, 0x840u);
  memset_0(v24, 0, sizeof(v24));
  cchName = 260;
  nSize = 256;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, &nSize) )
    return GetLastError();
  v7 = OpenClusterEx(0, 0x2000000u, &GrantedAccess);
  v19 = v7;
  v8 = v7;
  if ( v7 )
  {
    v17 = OpenClusterResourceEx(v7, a1, 0x2000000u, &GrantedAccess);
    v10 = v17;
    if ( v17 )
    {
      v18 = OpenClusterNodeEx(v8, Buffer, 0x2000000u, &GrantedAccess);
      v11 = v18;
      if ( v18 )
      {
        v13 = (__int128)*a2;
        v20 = 29;
        v21 = v13;
        StringCchCopyW(StringUuid, 0x28u, a3 + 11);
        StringUuid[36] = 0;
        UuidFromStringW(StringUuid, &Uuid);
        GetClusterNodeId(0, szNodeId, &cchName);
        v23 = wcstol(szNodeId, 0, 10);
        LastError = ClusterpResourceControl(v10, v11, 0x1401F6Au, &v20, 0x840u, v24, 0xBC0u, &GrantedAccess, 0, 0);
      }
      else
      {
        LastError = GetLastError();
      }
      v9 = LastError;
      cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
    }
    else
    {
      v9 = GetLastError();
    }
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v17);
  }
  else
  {
    v9 = GetLastError();
  }
  cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v19);
  return v9;
}

```

## disassembly

```asm
0x180021180  push    rbp
0x180021182  push    rbx
0x180021183  push    rsi
0x180021184  push    rdi
0x180021185  push    r14
0x180021187  lea     rbp, [rsp-17F0h]
0x18002118f  mov     eax, 18F0h
0x180021194  call    _alloca_probe
0x180021199  sub     rsp, rax
0x18002119c  mov     rax, cs:__security_cookie
0x1800211a3  xor     rax, rsp
0x1800211a6  mov     [rbp+1810h+var_30], rax
0x1800211ad  mov     r14, r8
0x1800211b0  mov     [rsp+1910h+GrantedAccess], 0
0x1800211b8  mov     rsi, rdx
0x1800211bb  mov     rdi, rcx
0x1800211be  xor     edx, edx; Val
0x1800211c0  lea     rcx, [rbp+1810h+var_1890]; void *
0x1800211c4  mov     r8d, 840h; Size
0x1800211ca  call    memset_0
0x1800211cf  xor     edx, edx; Val
0x1800211d1  lea     rcx, [rbp+1810h+var_1050]; void *
0x1800211d8  mov     r8d, 0BC0h; Size
0x1800211de  call    memset_0
0x1800211e3  lea     r8, [rsp+1910h+nSize]; nSize
0x1800211e8  mov     [rsp+1910h+cchName], 104h
0x1800211f0  lea     rdx, [rbp+1810h+Buffer]; lpBuffer
0x1800211f7  mov     [rsp+1910h+nSize], 100h
0x1800211ff  mov     ecx, 5; NameType
0x180021204  call    cs:__imp_GetComputerNameExW
0x18002120a  test    eax, eax
0x18002120c  jnz     short loc_180021219
0x18002120e  call    cs:__imp_GetLastError
0x180021214  jmp     loc_180021378
0x180021219  lea     r8, [rsp+1910h+GrantedAccess]; GrantedAccess
0x18002121e  mov     edx, 2000000h; DesiredAccess
0x180021223  xor     ecx, ecx; lpszClusterName
0x180021225  call    OpenClusterEx
0x18002122a  mov     [rsp+1910h+var_18A0], rax
0x18002122f  mov     rbx, rax
0x180021232  test    rax, rax
0x180021235  jnz     short loc_180021244
0x180021237  call    cs:__imp_GetLastError
0x18002123d  mov     ebx, eax
0x18002123f  jmp     loc_18002136C
0x180021244  lea     r9, [rsp+1910h+GrantedAccess]; lpdwGrantedAccess
0x180021249  mov     r8d, 2000000h; dwDesiredAccess
0x18002124f  mov     rdx, rdi; lpszResourceName
0x180021252  mov     rcx, rbx; hCluster
0x180021255  call    OpenClusterResourceEx
0x18002125a  mov     [rsp+1910h+var_18B0], rax
0x18002125f  mov     rdi, rax
0x180021262  test    rax, rax
0x180021265  jnz     short loc_180021274
0x180021267  call    cs:__imp_GetLastError
0x18002126d  mov     ebx, eax
0x18002126f  jmp     loc_180021362
0x180021274  lea     r9, [rsp+1910h+GrantedAccess]; lpdwGrantedAccess
0x180021279  mov     r8d, 2000000h; dwDesiredAccess
0x18002127f  lea     rdx, [rbp+1810h+Buffer]; lpszNodeName
0x180021286  mov     rcx, rbx; hCluster
0x180021289  call    OpenClusterNodeEx
0x18002128e  mov     [rsp+1910h+var_18A8], rax
0x180021293  mov     rbx, rax
0x180021296  test    rax, rax
0x180021299  jnz     short loc_1800212A6
0x18002129b  call    cs:__imp_GetLastError
0x1800212a1  jmp     loc_180021356
0x1800212a6  movaps  xmm0, xmmword ptr [rsi]
0x1800212a9  lea     r8, [r14+16h]; wchar_t *
0x1800212ad  mov     edx, 28h ; '('; unsigned __int64
0x1800212b2  mov     [rbp+1810h+var_1890], 1Dh
0x1800212b9  lea     rcx, [rbp+1810h+StringUuid]; wchar_t *
0x1800212c0  movdqu  [rbp+1810h+var_1888], xmm0
0x1800212c5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800212ca  xor     eax, eax
0x1800212cc  lea     rdx, [rbp+1810h+Uuid]; Uuid
0x1800212d0  lea     rcx, [rbp+1810h+StringUuid]; StringUuid
0x1800212d7  mov     [rbp+1810h+var_448], ax
0x1800212de  call    cs:__imp_UuidFromStringW
0x1800212e4  lea     r8, [rsp+1910h+cchName]; lpcchName
0x1800212e9  xor     ecx, ecx; hNode
0x1800212eb  lea     rdx, [rbp+1810h+szNodeId]; lpszNodeId
0x1800212f2  call    GetClusterNodeId
0x1800212f7  xor     edx, edx; EndPtr
0x1800212f9  lea     rcx, [rbp+1810h+szNodeId]; String
0x180021300  lea     r8d, [rdx+0Ah]; Radix
0x180021304  call    cs:__imp_wcstol
0x18002130a  mov     [rsp+1910h+var_18C8], 0; wchar_t *
0x180021313  lea     r9, [rbp+1810h+var_1890]; void *
0x180021317  mov     [rsp+1910h+var_18D0], 0; bool
0x18002131c  mov     r8d, 1401F6Ah; unsigned int
0x180021322  mov     [rbp+1810h+var_1868], eax
0x180021325  mov     rdx, rbx; struct _HNODE *
0x180021328  lea     rax, [rsp+1910h+GrantedAccess]
0x18002132d  mov     rcx, rdi; struct _HRESOURCE *
0x180021330  mov     [rsp+1910h+var_18D8], rax; unsigned int *
0x180021335  lea     rax, [rbp+1810h+var_1050]
0x18002133c  mov     [rsp+1910h+var_18E0], 0BC0h; unsigned int
0x180021344  mov     [rsp+1910h+var_18E8], rax; void *
0x180021349  mov     [rsp+1910h+var_18F0], 840h; unsigned int
0x180021351  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x180021356  lea     rcx, [rsp+1910h+var_18A8]
0x18002135b  mov     ebx, eax
0x18002135d  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180021362  lea     rcx, [rsp+1910h+var_18B0]
0x180021367  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18002136c  lea     rcx, [rsp+1910h+var_18A0]
0x180021371  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x180021376  mov     eax, ebx
0x180021378  mov     rcx, [rbp+1810h+var_30]
0x18002137f  xor     rcx, rsp; StackCookie
0x180021382  call    __security_check_cookie
0x180021387  add     rsp, 18F0h
0x18002138e  pop     r14
0x180021390  pop     rdi
0x180021391  pop     rsi
0x180021392  pop     rbx
0x180021393  pop     rbp
0x180021394  retn
```
