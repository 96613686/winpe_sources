# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180001de0`
- end: `0x180001ea3`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001490`
- `0x180001c20`
- `0x180001de0`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e5e`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@HH@Z` at `0x180001e46`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@HH@Z` at `0x180001e46`

## pseudocode

```c
signed int __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v4; // rax
  signed int result; // eax
  TREE_HASH_TABLE *v6; // rax
  TREE_HASH_TABLE *v7; // rbx
  HANDLE ProcessHeap; // rax
  W3_URL_INFO_CACHE *v9; // rcx

  g_pGlobalInfo = a3;
  v4 = operator new(8u);
  if ( v4 )
  {
    *v4 = &CIISGlobalModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
               a2,
               v4,
               84);
    if ( result < 0 )
      return result;
    v6 = (TREE_HASH_TABLE *)operator new(0x38u);
    v7 = v6;
    if ( v6 )
    {
      TREE_HASH_TABLE::TREE_HASH_TABLE(v6, 1, 1);
      *((_QWORD *)v7 + 5) = 0;
      *(_QWORD *)v7 = &W3_URL_INFO_CACHE::`vftable';
      ProcessHeap = GetProcessHeap();
      *((_QWORD *)v7 + 6) = HeapAlloc(ProcessHeap, 8u, 0x2000u);
      g_pUriCache = v7;
      return W3_URL_INFO_CACHE::Initialize(v9);
    }
    g_pUriCache = 0;
  }
  return -2147024888;
}

```

## disassembly

```asm
0x180001de0  push    rbx
0x180001de2  sub     rsp, 20h
0x180001de6  mov     ecx, 8; Size
0x180001deb  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, r8; IHttpServer * g_pGlobalInfo
0x180001df2  mov     rbx, rdx
0x180001df5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001dfa  mov     rdx, rax
0x180001dfd  test    rax, rax
0x180001e00  jz      loc_180001E98
0x180001e06  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180001e0d  mov     r8d, 54h ; 'T'
0x180001e13  mov     [rdx], rax
0x180001e16  mov     rcx, [rbx]
0x180001e19  mov     rax, [rcx+18h]
0x180001e1d  mov     rcx, rbx
0x180001e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e25  test    eax, eax
0x180001e27  js      short loc_180001E9D
0x180001e29  mov     ecx, 38h ; '8'; Size
0x180001e2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e33  mov     rbx, rax
0x180001e36  test    rax, rax
0x180001e39  jz      short loc_180001E8D
0x180001e3b  mov     edx, 1
0x180001e40  mov     rcx, rax
0x180001e43  mov     r8d, edx
0x180001e46  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@HH@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int,int)
0x180001e4c  lea     rax, ??_7W3_URL_INFO_CACHE@@6B@; const W3_URL_INFO_CACHE::`vftable'
0x180001e53  mov     qword ptr [rbx+28h], 0
0x180001e5b  mov     [rbx], rax
0x180001e5e  call    cs:__imp_GetProcessHeap
0x180001e64  mov     edx, 8; dwFlags
0x180001e69  mov     r8d, 2000h; dwBytes
0x180001e6f  mov     rcx, rax; hHeap
0x180001e72  call    cs:__imp_HeapAlloc
0x180001e78  mov     [rbx+30h], rax
0x180001e7c  mov     cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA, rbx; W3_URL_INFO_CACHE * g_pUriCache
0x180001e83  add     rsp, 20h
0x180001e87  pop     rbx
0x180001e88  jmp     ?Initialize@W3_URL_INFO_CACHE@@QEAAJXZ; W3_URL_INFO_CACHE::Initialize(void)
0x180001e8d  mov     cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA, 0; W3_URL_INFO_CACHE * g_pUriCache
0x180001e98  mov     eax, 80070008h
0x180001e9d  add     rsp, 20h
0x180001ea1  pop     rbx
0x180001ea2  retn
```
