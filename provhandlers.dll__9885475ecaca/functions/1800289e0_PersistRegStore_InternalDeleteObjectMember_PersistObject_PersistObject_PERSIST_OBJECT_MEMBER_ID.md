# PersistRegStore::InternalDeleteObjectMember(PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)

- ea: `0x1800289e0`
- end: `0x180028aea`
- name: `?InternalDeleteObjectMember@PersistRegStore@@MEAAJPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z`
- size: `266`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180007f48`
- `0x1800289e0`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ac5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028aa7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028aa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028a93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028a93`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PersistRegStore::InternalDeleteObjectMember(__int64 *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rax
  unsigned int (__fastcall *v7)(__int64 *); // rax
  signed int v8; // ebx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  const WCHAR *v10; // rdi
  LSTATUS v11; // eax
  bool v12; // cc
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  WCHAR ValueName[8]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v16; // [rsp+48h] [rbp-30h]

  v3 = *a1;
  hKey = 0;
  *(_OWORD *)ValueName = 0;
  v7 = *(unsigned int (__fastcall **)(__int64 *))(v3 + 72);
  v16 = 0;
  if ( v7(a1) )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)(a2 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    v10 = *(const WCHAR **)(a2 + 24);
    LeaveCriticalSection(v9);
    if ( v10 )
    {
      v8 = StringCchPrintfW(ValueName, 0x10u, L"%d", a3);
      if ( v8 >= 0 )
      {
        v11 = RegOpenKeyExW((HKEY)a1[2], v10, 0, 0xF003Fu, &hKey);
        v12 = v11 <= 0;
        if ( v11 || (v11 = RegDeleteValueW(hKey, ValueName), v12 = v11 <= 0, v11) )
        {
          if ( v12 )
            v8 = v11;
          else
            v8 = (unsigned __int16)v11 | 0x80070000;
        }
      }
    }
    else
    {
      v8 = -2147024809;
    }
  }
  else
  {
    v8 = -2102788096;
  }
  RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800289e0  mov     [rsp+arg_18], rbx
0x1800289e5  push    rbp
0x1800289e6  push    rsi
0x1800289e7  push    rdi
0x1800289e8  sub     rsp, 60h
0x1800289ec  mov     rax, cs:__security_cookie
0x1800289f3  xor     rax, rsp
0x1800289f6  mov     [rsp+78h+var_20], rax
0x1800289fb  mov     rax, [rcx]
0x1800289fe  xorps   xmm0, xmm0
0x180028a01  mov     ebp, r8d
0x180028a04  mov     [rsp+78h+hKey], 0
0x180028a0d  mov     rdi, rdx
0x180028a10  mov     rsi, rcx
0x180028a13  movups  xmmword ptr [rsp+78h+ValueName], xmm0
0x180028a18  mov     rax, [rax+48h]
0x180028a1c  movups  [rsp+78h+var_30], xmm0
0x180028a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a26  test    eax, eax
0x180028a28  jnz     short loc_180028A34
0x180028a2a  mov     ebx, 82AA0000h
0x180028a2f  jmp     loc_180028AC0
0x180028a34  lea     rbx, [rdi+20h]
0x180028a38  mov     rcx, rbx; lpCriticalSection
0x180028a3b  call    cs:__imp_EnterCriticalSection
0x180028a41  mov     rdi, [rdi+18h]
0x180028a45  mov     rcx, rbx; lpCriticalSection
0x180028a48  call    cs:__imp_LeaveCriticalSection
0x180028a4e  test    rdi, rdi
0x180028a51  jnz     short loc_180028A5A
0x180028a53  mov     ebx, 80070057h
0x180028a58  jmp     short loc_180028AC0
0x180028a5a  mov     r9d, ebp
0x180028a5d  lea     r8, aD; "%d"
0x180028a64  mov     edx, 10h; unsigned __int64
0x180028a69  lea     rcx, [rsp+78h+ValueName]; unsigned __int16 *
0x180028a6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028a73  mov     ebx, eax
0x180028a75  test    eax, eax
0x180028a77  js      short loc_180028AC0
0x180028a79  mov     rcx, [rsi+10h]; hKey
0x180028a7d  lea     rax, [rsp+78h+hKey]
0x180028a82  mov     r9d, 0F003Fh; samDesired
0x180028a88  mov     [rsp+78h+phkResult], rax; phkResult
0x180028a8d  xor     r8d, r8d; ulOptions
0x180028a90  mov     rdx, rdi; lpSubKey
0x180028a93  call    cs:__imp_RegOpenKeyExW
0x180028a99  test    eax, eax
0x180028a9b  jnz     short loc_180028AB1
0x180028a9d  mov     rcx, [rsp+78h+hKey]; hKey
0x180028aa2  lea     rdx, [rsp+78h+ValueName]; lpValueName
0x180028aa7  call    cs:__imp_RegDeleteValueW
0x180028aad  test    eax, eax
0x180028aaf  jz      short loc_180028AC0
0x180028ab1  jg      short loc_180028AB7
0x180028ab3  mov     ebx, eax
0x180028ab5  jmp     short loc_180028AC0
0x180028ab7  movzx   ebx, ax
0x180028aba  or      ebx, 80070000h
0x180028ac0  mov     rcx, [rsp+78h+hKey]; hKey
0x180028ac5  call    cs:__imp_RegCloseKey
0x180028acb  mov     eax, ebx
0x180028acd  mov     rcx, [rsp+78h+var_20]
0x180028ad2  xor     rcx, rsp; StackCookie
0x180028ad5  call    __security_check_cookie
0x180028ada  mov     rbx, [rsp+78h+arg_18]
0x180028ae2  add     rsp, 60h
0x180028ae6  pop     rdi
0x180028ae7  pop     rsi
0x180028ae8  pop     rbp
0x180028ae9  retn
```
