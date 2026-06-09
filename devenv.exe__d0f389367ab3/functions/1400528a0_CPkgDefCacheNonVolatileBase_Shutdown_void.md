# CPkgDefCacheNonVolatileBase::Shutdown(void)

- ea: `0x1400528a0`
- end: `0x14005297e`
- name: `?Shutdown@CPkgDefCacheNonVolatileBase@@MEAAXXZ`
- size: `222`
- prototype: `void __fastcall(CPkgDefCacheNonVolatileBase *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1400095f4`
- `0x14000f478`
- `0x1400314d0`
- `0x140035330`
- `0x1400528a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005293c`
- `ADVAPI32!RegCloseKey` at `0x14005293c`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400528c1`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400528c1`
- `ADVAPI32!RevertToSelf` at `0x140052947`
- `ADVAPI32!RevertToSelf` at `0x140052947`

## string_xrefs

- `0x140052926`: `Deleted volatile pkgdef Configuration cache`
- `0x140052960`: `Released pkgdef cache usage tracker`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPkgDefCacheNonVolatileBase::Shutdown(CPkgDefCacheNonVolatileBase *this)
{
  bool v2; // bl
  HKEY v3; // rcx
  int v4; // eax
  unsigned int v5; // edx
  int v6; // eax
  HKEY hKey[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  if ( *((_BYTE *)this + 288) )
  {
    v2 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
    *(_OWORD *)hKey = 0;
    v8 = 0;
    v3 = ::hKey;
    if ( *((_QWORD *)this + 29) )
      v3 = (HKEY)*((_QWORD *)this + 29);
    hKey[0] = v3;
    LODWORD(hKey[1]) = 0;
    v8 = 0;
    v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, *((const unsigned __int16 **)this + 20));
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    CLogger::LogInfo(L"Deleted volatile pkgdef Configuration cache", v5, 0);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( v2 )
      RevertToSelf();
  }
  v6 = CCacheUsageTracker::SetInUseFlag((CPkgDefCacheNonVolatileBase *)((char *)this + 264), 0);
  CLogger::LogInfo(L"Released pkgdef cache usage tracker", v6, 0);
  CPkgDefCache::Shutdown(this);
}

```

## disassembly

```asm
0x1400528a0  mov     [rsp+arg_8], rbx
0x1400528a5  push    rdi
0x1400528a6  sub     rsp, 40h
0x1400528aa  mov     rdi, rcx
0x1400528ad  cmp     byte ptr [rcx+120h], 0
0x1400528b4  jz      loc_14005294D
0x1400528ba  mov     rcx, [rcx+0E0h]; hToken
0x1400528c1  call    cs:__imp_ImpersonateLoggedOnUser
0x1400528c7  test    eax, eax
0x1400528c9  setnz   bl
0x1400528cc  mov     [rsp+48h+arg_0], bl
0x1400528d0  xorps   xmm0, xmm0
0x1400528d3  xor     eax, eax
0x1400528d5  movups  xmmword ptr [rsp+48h+hKey], xmm0
0x1400528da  mov     [rsp+48h+var_18], rax
0x1400528df  mov     rax, [rdi+0E8h]
0x1400528e6  mov     rcx, cs:hKey
0x1400528ed  test    rax, rax
0x1400528f0  cmovnz  rcx, rax
0x1400528f4  mov     [rsp+48h+hKey], rcx
0x1400528f9  and     dword ptr [rsp+48h+hKey+8], 0
0x1400528fe  and     [rsp+48h+var_18], 0
0x140052904  mov     rdx, [rdi+0A0h]; unsigned __int16 *
0x14005290b  lea     rcx, [rsp+48h+hKey]; this
0x140052910  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140052915  movzx   edx, ax
0x140052918  or      edx, 80070000h
0x14005291e  test    eax, eax
0x140052920  cmovle  edx, eax; int
0x140052923  xor     r8d, r8d; unsigned __int16 *
0x140052926  lea     rcx, aDeletedVolatil; "Deleted volatile pkgdef Configuration c"...
0x14005292d  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140052932  mov     rcx, [rsp+48h+hKey]; hKey
0x140052937  test    rcx, rcx
0x14005293a  jz      short loc_140052943
0x14005293c  call    cs:__imp_RegCloseKey
0x140052942  nop
0x140052943  test    bl, bl
0x140052945  jz      short loc_14005294D
0x140052947  call    cs:__imp_RevertToSelf
0x14005294d  lea     rcx, [rdi+108h]; this
0x140052954  xor     edx, edx; bool
0x140052956  call    ?SetInUseFlag@CCacheUsageTracker@@QEAAJ_N@Z; CCacheUsageTracker::SetInUseFlag(bool)
0x14005295b  xor     r8d, r8d; unsigned __int16 *
0x14005295e  mov     edx, eax; int
0x140052960  lea     rcx, aReleasedPkgdef; "Released pkgdef cache usage tracker"
0x140052967  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14005296c  mov     rcx, rdi; this
0x14005296f  mov     rbx, [rsp+48h+arg_8]
0x140052974  add     rsp, 40h
0x140052978  pop     rdi
0x140052979  jmp     ?Shutdown@CPkgDefCache@@MEAAXXZ; CPkgDefCache::Shutdown(void)
```
