# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x180010328`
- end: `0x180010435`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010328`
- `0x18001075c`

## callees

- `0x1800017a0`
- `0x18000fc14`
- `0x18000fc40`
- `0x180010044`
- `0x180010328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800103d4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800103d4`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180010328  mov     [rsp-8+arg_10], rbx
0x18001032d  push    rbp
0x18001032e  push    rsi
0x18001032f  push    rdi
0x180010330  lea     rbp, [rsp-180h]
0x180010338  sub     rsp, 280h
0x18001033f  mov     rax, cs:__security_cookie
0x180010346  xor     rax, rsp
0x180010349  mov     [rbp+190h+var_20], rax
0x180010350  mov     rsi, rdx
0x180010353  mov     [rsp+290h+hKey], 0
0x18001035c  mov     r8, rdx; lpSubKey
0x18001035f  mov     [rsp+290h+var_240], 0
0x180010368  mov     rdx, [rcx]; hKey
0x18001036b  mov     rdi, rcx
0x18001036e  lea     rcx, [rsp+290h+hKey]; this
0x180010373  mov     [rsp+290h+var_238], 0
0x18001037c  mov     r9d, 2001Fh; unsigned int
0x180010382  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010387  mov     ebx, eax
0x180010389  test    eax, eax
0x18001038b  jnz     short loc_180010407
0x18001038d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180010396  mov     rcx, [rsp+290h+hKey]; hKey
0x18001039b  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800103a0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800103a5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800103aa  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800103b3  lea     r8, [rsp+290h+Name]; lpName
0x1800103b8  mov     [rsp+290h+lpClass], 0; lpClass
0x1800103c1  xor     edx, edx; dwIndex
0x1800103c3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800103cc  mov     [rsp+290h+cchName], 100h
0x1800103d4  call    cs:__imp_RegEnumKeyExW
0x1800103da  lea     rcx, [rsp+290h+hKey]; this
0x1800103df  test    eax, eax
0x1800103e1  jnz     short loc_1800103F5
0x1800103e3  lea     rdx, [rsp+290h+Name]; wchar_t *
0x1800103e8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x1800103ed  mov     ebx, eax
0x1800103ef  test    eax, eax
0x1800103f1  jnz     short loc_180010407
0x1800103f3  jmp     short loc_180010396
0x1800103f5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800103fa  mov     rdx, rsi; wchar_t *
0x1800103fd  mov     rcx, rdi; this
0x180010400  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180010405  mov     ebx, eax
0x180010407  lea     rcx, [rsp+290h+hKey]; this
0x18001040c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010411  mov     eax, ebx
0x180010413  mov     rcx, [rbp+190h+var_20]
0x18001041a  xor     rcx, rsp; StackCookie
0x18001041d  call    __security_check_cookie
0x180010422  mov     rbx, [rsp+290h+arg_10]
0x18001042a  add     rsp, 280h
0x180010431  pop     rdi
0x180010432  pop     rsi
0x180010433  pop     rbp
0x180010434  retn
```
