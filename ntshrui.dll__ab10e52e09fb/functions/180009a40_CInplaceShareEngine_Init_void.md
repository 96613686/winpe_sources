# CInplaceShareEngine::Init(void)

- ea: `0x180009a40`
- end: `0x180009bf8`
- name: `?Init@CInplaceShareEngine@@QEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(CInplaceShareEngine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009910`

## callees

- `0x1800098dc`
- `0x180009a40`
- `0x180009c50`
- `0x1800259bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009b87`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009b87`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009b21`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009b21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009afc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009afc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b4e`
- `SHELL32!SHGetFolderPathEx` at `0x180009a68`
- `SHELL32!SHGetFolderPathEx` at `0x180009ab0`
- `SHELL32!SHGetFolderPathEx` at `0x180009ad5`
- `SHELL32!SHGetFolderPathEx` at `0x180009bb1`
- `SHELL32!SHGetFolderPathEx` at `0x180009a68`
- `SHELL32!SHGetFolderPathEx` at `0x180009ab0`
- `SHELL32!SHGetFolderPathEx` at `0x180009ad5`
- `SHELL32!SHGetFolderPathEx` at `0x180009bb1`

## pseudocode

```c
HRESULT __fastcall CInplaceShareEngine::Init(CInplaceShareEngine *this)
{
  HRESULT result; // eax
  __int64 v3; // rdx
  HLOCAL v4; // rax
  _QWORD *v5; // rbx
  _QWORD *cbSid; // [rsp+40h] [rbp+8h] BYREF

  result = SHGetFolderPathEx(&FOLDERID_UserProfiles, 0, 0, (char *)this + 1112, 260);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3 + 556) );
  *((_DWORD *)this + 412) = v3;
  if ( result < 0 )
    return result;
  result = SHGetFolderPathEx(&FOLDERID_Profile, 0, 0, (char *)this + 72, 260);
  if ( result < 0 )
    return result;
  result = SHGetFolderPathEx(&FOLDERID_Public, 0, 0, (char *)this + 592, 260);
  if ( result < 0 )
    return result;
  LODWORD(cbSid) = 68;
  v4 = LocalAlloc(0x40u, 0x44u);
  *((_QWORD *)this + 207) = v4;
  if ( !v4 )
    return -2147024882;
  if ( CreateWellKnownSid(WinCreatorOwnerSid, 0, v4, (DWORD *)&cbSid)
    || (result = ResultFromKnownLastError(), result >= 0) )
  {
    result = CoCreateInstance(
               &CLSID_ShareManager,
               0,
               1u,
               &GUID_5bb62628_92e7_4f54_81a5_29c579341e13,
               (LPVOID *)this + 8);
    if ( result >= 0 )
    {
      cbSid = operator new(0x248u, (const struct std::nothrow_t *)std::nothrow);
      v5 = cbSid;
      if ( cbSid )
      {
        cbSid[5] = 0;
        v5[6] = 0;
        v5[7] = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)v5);
        *((_QWORD *)this + 209) = v5;
        result = SHGetFolderPathEx(&FOLDERID_Profile, 0, 0, v5 + 8, 260);
        if ( result >= 0 )
          return CDefaultAclCache::_CreatePrivateProtectedAcl((CDefaultAclCache *)v5, (struct CAceList **)v5 + 7);
        return result;
      }
      *((_QWORD *)this + 209) = 0;
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009a40  mov     [rsp+arg_8], rbx
0x180009a45  push    rdi
0x180009a46  sub     rsp, 30h
0x180009a4a  mov     rdi, rcx
0x180009a4d  mov     dword ptr [rsp+38h+ppv], 104h
0x180009a55  lea     r9, [rcx+458h]
0x180009a5c  xor     r8d, r8d
0x180009a5f  lea     rcx, FOLDERID_UserProfiles
0x180009a66  xor     edx, edx
0x180009a68  call    cs:__imp_SHGetFolderPathEx
0x180009a6e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009a75  nop     word ptr [rax+rax+00000000h]
0x180009a80  inc     rdx
0x180009a83  cmp     word ptr [rdi+rdx*2+458h], 0
0x180009a8c  jnz     short loc_180009A80
0x180009a8e  mov     [rdi+670h], edx
0x180009a94  test    eax, eax
0x180009a96  js      short loc_180009ADF
0x180009a98  lea     r9, [rdi+48h]
0x180009a9c  mov     dword ptr [rsp+38h+ppv], 104h
0x180009aa4  xor     r8d, r8d
0x180009aa7  lea     rcx, FOLDERID_Profile
0x180009aae  xor     edx, edx
0x180009ab0  call    cs:__imp_SHGetFolderPathEx
0x180009ab6  test    eax, eax
0x180009ab8  js      short loc_180009ADF
0x180009aba  lea     r9, [rdi+250h]
0x180009ac1  mov     dword ptr [rsp+38h+ppv], 104h
0x180009ac9  xor     r8d, r8d
0x180009acc  lea     rcx, FOLDERID_Public
0x180009ad3  xor     edx, edx
0x180009ad5  call    cs:__imp_SHGetFolderPathEx
0x180009adb  test    eax, eax
0x180009add  jns     short loc_180009AEA
0x180009adf  mov     rbx, [rsp+38h+arg_8]
0x180009ae4  add     rsp, 30h
0x180009ae8  pop     rdi
0x180009ae9  retn
0x180009aea  mov     edx, 44h ; 'D'; uBytes
0x180009aef  mov     dword ptr [rsp+38h+cbSid], 44h ; 'D'
0x180009af7  mov     ecx, 40h ; '@'; uFlags
0x180009afc  call    cs:__imp_LocalAlloc
0x180009b02  mov     [rdi+678h], rax
0x180009b09  test    rax, rax
0x180009b0c  jz      loc_180009BDC
0x180009b12  lea     r9, [rsp+38h+cbSid]; cbSid
0x180009b17  mov     r8, rax; pSid
0x180009b1a  xor     edx, edx; DomainSid
0x180009b1c  mov     ecx, 3; WellKnownSidType
0x180009b21  call    cs:__imp_CreateWellKnownSid
0x180009b27  test    eax, eax
0x180009b29  jz      loc_180009BE6
0x180009b2f  lea     rax, [rdi+40h]
0x180009b33  xor     edx, edx; pUnkOuter
0x180009b35  lea     r9, _GUID_5bb62628_92e7_4f54_81a5_29c579341e13; riid
0x180009b3c  mov     [rsp+38h+ppv], rax; ppv
0x180009b41  mov     r8d, 1; dwClsContext
0x180009b47  lea     rcx, CLSID_ShareManager; rclsid
0x180009b4e  call    cs:__imp_CoCreateInstance
0x180009b54  test    eax, eax
0x180009b56  js      short loc_180009ADF
0x180009b58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b5f  mov     ecx, 248h; unsigned __int64
0x180009b64  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b69  mov     [rsp+38h+cbSid], rax
0x180009b6e  mov     rbx, rax
0x180009b71  test    rax, rax
0x180009b74  jz      short loc_180009BD5
0x180009b76  xor     eax, eax
0x180009b78  mov     rcx, rbx; lpCriticalSection
0x180009b7b  mov     [rbx+28h], rax
0x180009b7f  mov     [rbx+30h], rax
0x180009b83  mov     [rbx+38h], rax
0x180009b87  call    cs:__imp_InitializeCriticalSection
0x180009b8d  mov     [rdi+688h], rbx
0x180009b94  test    rbx, rbx
0x180009b97  jz      short loc_180009BDC
0x180009b99  lea     r9, [rbx+40h]
0x180009b9d  mov     dword ptr [rsp+38h+ppv], 104h
0x180009ba5  xor     r8d, r8d
0x180009ba8  lea     rcx, FOLDERID_Profile
0x180009baf  xor     edx, edx
0x180009bb1  call    cs:__imp_SHGetFolderPathEx
0x180009bb7  test    eax, eax
0x180009bb9  js      loc_180009ADF
0x180009bbf  lea     rdx, [rbx+38h]; struct CAceList **
0x180009bc3  mov     rcx, rbx; this
0x180009bc6  mov     rbx, [rsp+38h+arg_8]
0x180009bcb  add     rsp, 30h
0x180009bcf  pop     rdi
0x180009bd0  jmp     ?_CreatePrivateProtectedAcl@CDefaultAclCache@@AEAAJPEAPEAVCAceList@@@Z; CDefaultAclCache::_CreatePrivateProtectedAcl(CAceList * *)
0x180009bd5  mov     [rdi+688h], rax
0x180009bdc  mov     eax, 8007000Eh
0x180009be1  jmp     loc_180009ADF
0x180009be6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009beb  test    eax, eax
0x180009bed  jns     loc_180009B2F
0x180009bf3  jmp     loc_180009ADF
```
