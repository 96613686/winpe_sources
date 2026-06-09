# UserSecurityContext::~UserSecurityContext(void)

- ea: `0x180016278`
- end: `0x180016309`
- name: `??1UserSecurityContext@@UEAA@XZ`
- size: `145`
- prototype: `void __fastcall(UserSecurityContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016310`

## callees

- `0x180007e10`
- `0x18000a524`
- `0x180016278`
- `0x1800175c0`

## import_xrefs

- `msvcrt!free` at `0x1800162ef`
- `msvcrt!free` at `0x1800162ef`
- `ADVAPI32!CryptAcquireContextW` at `0x1800162c3`
- `ADVAPI32!CryptAcquireContextW` at `0x1800162c3`
- `ADVAPI32!CryptReleaseContext` at `0x1800162d6`
- `ADVAPI32!CryptReleaseContext` at `0x1800162d6`
- `KERNEL32!DeleteCriticalSection` at `0x1800162e4`
- `KERNEL32!DeleteCriticalSection` at `0x1800162e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserSecurityContext::~UserSecurityContext(UserSecurityContext *this)
{
  HCRYPTPROV phProv; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &UserSecurityContext::`vftable';
  UserSecurityContext::ReleaseNonCacheableCryptoProvider(this);
  if ( mqwcslen((const wchar_t *)this + 50) )
  {
    phProv = 0;
    CryptAcquireContextW(&phProv, (LPCWSTR)this + 50, *((LPCWSTR *)this + 3), *((_DWORD *)this + 14), 0x10u);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  free(*((void **)this + 11));
  CACSecurityContext::~CACSecurityContext((UserSecurityContext *)((char *)this + 8));
}

```

## disassembly

```asm
0x180016278  mov     [rsp+arg_8], rbx
0x18001627d  push    rdi
0x18001627e  sub     rsp, 30h
0x180016282  mov     rdi, rcx
0x180016285  lea     rax, ??_7UserSecurityContext@@6B@; const UserSecurityContext::`vftable'
0x18001628c  mov     [rcx], rax
0x18001628f  call    ?ReleaseNonCacheableCryptoProvider@UserSecurityContext@@AEAAXXZ; UserSecurityContext::ReleaseNonCacheableCryptoProvider(void)
0x180016294  lea     rcx, [rdi+64h]; wchar_t *
0x180016298  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001629d  test    eax, eax
0x18001629f  jz      short loc_1800162DD
0x1800162a1  mov     [rsp+38h+phProv], 0
0x1800162aa  mov     [rsp+38h+dwFlags], 10h; dwFlags
0x1800162b2  mov     r9d, [rdi+38h]; dwProvType
0x1800162b6  mov     r8, [rdi+18h]; szProvider
0x1800162ba  lea     rdx, [rdi+64h]; szContainer
0x1800162be  lea     rcx, [rsp+38h+phProv]; phProv
0x1800162c3  call    cs:__imp_CryptAcquireContextW
0x1800162c9  nop
0x1800162ca  mov     rcx, [rsp+38h+phProv]; hProv
0x1800162cf  test    rcx, rcx
0x1800162d2  jz      short loc_1800162DD
0x1800162d4  xor     edx, edx; dwFlags
0x1800162d6  call    cs:__imp_CryptReleaseContext
0x1800162dc  nop
0x1800162dd  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x1800162e4  call    cs:__imp_DeleteCriticalSection
0x1800162ea  nop
0x1800162eb  mov     rcx, [rdi+58h]; Block
0x1800162ef  call    cs:__imp_free
0x1800162f5  nop
0x1800162f6  lea     rcx, [rdi+8]; this
0x1800162fa  mov     rbx, [rsp+38h+arg_8]
0x1800162ff  add     rsp, 30h
0x180016303  pop     rdi
0x180016304  jmp     ??1CACSecurityContext@@QEAA@XZ; CACSecurityContext::~CACSecurityContext(void)
```
