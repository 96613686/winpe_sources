# CMemoryMappedCache::_DeleteCacheFileIfNeeded(void)

- ea: `0x18004f204`
- end: `0x18004f31f`
- name: `?_DeleteCacheFileIfNeeded@CMemoryMappedCache@@AEAAXXZ`
- size: `283`
- prototype: `void __fastcall(CMemoryMappedCache *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x18004f13c`

## callees

- `0x180024a18`
- `0x180025298`
- `0x18002568c`
- `0x180025c6c`
- `0x18004f204`
- `0x18006ed20`
- `0x1800a73bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f294`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f294`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f237`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f237`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f314`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004f314`

## pseudocode

```c
void __fastcall CMemoryMappedCache::_DeleteCacheFileIfNeeded(CMemoryMappedCache *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // r14
  unsigned int v4; // edi
  __int64 v5; // rdx
  unsigned int v6; // r8d
  unsigned __int64 v7; // [rsp+30h] [rbp-468h] BYREF
  unsigned __int16 v8[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR FileName[264]; // [rsp+250h] [rbp-248h] BYREF

  if ( *((_QWORD *)this + 6) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
    v3 = *((_QWORD *)this + 6);
    v4 = *((_DWORD *)this + 5);
    v7 = 0;
    if ( ((int)CVersionManager::_EnsureVersionMapping(v3, v4, 1u) < 0
       || (int)GetEntryVersion(
                 *(volatile struct VERSION_HEADER **)(v3 + (-(__int64)((v4 & 1) != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 80),
                 (const struct _GUID *)this + 2,
                 &v7) < 0
       || v7 != *((_QWORD *)this + 3) && v7)
      && GetCachePath((unsigned __int16 *)this + 44, v5, *((_DWORD *)this + 5), 0)
      && CMemoryMappedCache::_GetObjectName(this, v8, v6) >= 0
      && (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s", (char *)this + 88, v8) >= 0 )
    {
      DeleteFileW(FileName);
    }
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18004f204  push    rbx
0x18004f206  push    rsi
0x18004f207  push    rdi
0x18004f208  push    r14
0x18004f20a  sub     rsp, 478h
0x18004f211  mov     rax, cs:__security_cookie
0x18004f218  xor     rax, rsp
0x18004f21b  mov     [rsp+498h+var_38], rax
0x18004f223  cmp     qword ptr [rcx+30h], 0
0x18004f228  mov     rbx, rcx
0x18004f22b  jz      short loc_18004F29A
0x18004f22d  lea     rsi, [rcx+260h]
0x18004f234  mov     rcx, rsi; lpCriticalSection
0x18004f237  call    cs:__imp_EnterCriticalSection
0x18004f23d  mov     r14, [rbx+30h]
0x18004f241  mov     r8d, 1
0x18004f247  mov     edi, [rbx+14h]
0x18004f24a  mov     rcx, r14
0x18004f24d  mov     edx, edi
0x18004f24f  mov     [rsp+498h+var_468], 0
0x18004f258  call    ?_EnsureVersionMapping@CVersionManager@@AEAAJW4CM_SCOPEFLAGS@@W4VERACCESS@1@K@Z; CVersionManager::_EnsureVersionMapping(CM_SCOPEFLAGS,CVersionManager::VERACCESS,ulong)
0x18004f25d  test    eax, eax
0x18004f25f  js      short loc_18004F2BC
0x18004f261  and     dil, 1
0x18004f265  lea     rdx, [rbx+20h]; struct _GUID *
0x18004f269  neg     dil
0x18004f26c  lea     r8, [rsp+498h+var_468]; unsigned __int64 *
0x18004f271  sbb     rcx, rcx
0x18004f274  and     rcx, 0FFFFFFFFFFFFFFD0h
0x18004f278  mov     rcx, [r14+rcx+50h]; volatile struct VERSION_HEADER *
0x18004f27d  call    ?GetEntryVersion@@YAJPEAXAEBU_GUID@@PEA_K@Z; GetEntryVersion(void *,_GUID const &,unsigned __int64 *)
0x18004f282  test    eax, eax
0x18004f284  js      short loc_18004F2BC
0x18004f286  mov     rax, [rsp+498h+var_468]
0x18004f28b  cmp     rax, [rbx+18h]
0x18004f28f  jnz     short loc_18004F2B7
0x18004f291  mov     rcx, rsi; lpCriticalSection
0x18004f294  call    cs:__imp_LeaveCriticalSection
0x18004f29a  mov     rcx, [rsp+498h+var_38]
0x18004f2a2  xor     rcx, rsp; StackCookie
0x18004f2a5  call    __security_check_cookie
0x18004f2aa  add     rsp, 478h
0x18004f2b1  pop     r14
0x18004f2b3  pop     rdi
0x18004f2b4  pop     rsi
0x18004f2b5  pop     rbx
0x18004f2b6  retn
0x18004f2b7  test    rax, rax
0x18004f2ba  jz      short loc_18004F291
0x18004f2bc  mov     r8d, [rbx+14h]
0x18004f2c0  lea     rcx, [rbx+58h]
0x18004f2c4  xor     r9d, r9d
0x18004f2c7  call    ?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z; GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)
0x18004f2cc  test    eax, eax
0x18004f2ce  jz      short loc_18004F291
0x18004f2d0  lea     rdx, [rsp+498h+var_458]; unsigned __int16 *
0x18004f2d5  mov     rcx, rbx; this
0x18004f2d8  call    ?_GetObjectName@CMemoryMappedCache@@AEAAJPEAGK@Z; CMemoryMappedCache::_GetObjectName(ushort *,ulong)
0x18004f2dd  test    eax, eax
0x18004f2df  js      short loc_18004F291
0x18004f2e1  lea     rax, [rsp+498h+var_458]
0x18004f2e6  mov     edx, 104h; unsigned __int64
0x18004f2eb  lea     r9, [rbx+58h]
0x18004f2ef  mov     [rsp+498h+var_478], rax
0x18004f2f4  lea     r8, aSS; "%s\\%s"
0x18004f2fb  lea     rcx, [rsp+498h+FileName]; unsigned __int16 *
0x18004f303  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f308  test    eax, eax
0x18004f30a  js      short loc_18004F291
0x18004f30c  lea     rcx, [rsp+498h+FileName]; lpFileName
0x18004f314  call    cs:__imp_DeleteFileW
0x18004f31a  jmp     loc_18004F291
```
