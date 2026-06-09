# CKey::CKey(HKEY__ *,ushort const *,long *,int,ulong)

- ea: `0x1800020b0`
- end: `0x1800021e3`
- name: `??0CKey@@QEAA@PEAUHKEY__@@PEBGPEAJHK@Z`
- size: `307`
- prototype: `CKey *(CKey *__hidden this, HKEY, const unsigned __int16 *, int *, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000277c`

## callees

- `0x180001460`
- `0x1800020b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000219f`
- `ADVAPI32!RegCloseKey` at `0x18000219f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002190`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002190`
- `ADVAPI32!RegOpenKeyExW` at `0x18000212a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000212a`

## pseudocode

```c
CKey *__fastcall CKey::CKey(CKey *this, HKEY a2, const unsigned __int16 *a3, int *a4)
{
  HKEY *v4; // rsi
  DWORD *v5; // r15
  DWORD *lpcValues; // rbp
  int v9; // ebx
  DWORD cbSecurityDescriptor; // [rsp+60h] [rbp-48h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-40h] BYREF

  v4 = (HKEY *)((char *)this + 8);
  *((_DWORD *)this + 4) = 0;
  v5 = (DWORD *)((char *)this + 88);
  *((_QWORD *)this + 1) = 0;
  lpcValues = (DWORD *)((char *)this + 96);
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 24) = 0;
  *(_QWORD *)this = &CKey::`vftable';
  *((_QWORD *)this + 10) = (char *)this + 20;
  v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a3, 0, 0x20019u, (PHKEY)this + 1);
  if ( !v9 )
  {
    cbSecurityDescriptor = 0;
    ftLastWriteTime = 0;
    v9 = RegQueryInfoKeyW(
           *v4,
           0,
           0,
           0,
           v5,
           (LPDWORD)this + 23,
           0,
           lpcValues,
           (LPDWORD)this + 25,
           (LPDWORD)this + 26,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    if ( v9 )
    {
      RegCloseKey(*v4);
      *v4 = 0;
    }
  }
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  *a4 = v9;
  return this;
}

```

## disassembly

```asm
0x1800020b0  mov     [rsp+arg_8], rbx
0x1800020b5  push    rbp
0x1800020b6  push    rsi
0x1800020b7  push    rdi
0x1800020b8  push    r14
0x1800020ba  push    r15
0x1800020bc  sub     rsp, 80h
0x1800020c3  mov     rax, cs:__security_cookie
0x1800020ca  xor     rax, rsp
0x1800020cd  mov     [rsp+0A8h+var_38], rax
0x1800020d2  lea     rsi, [rcx+8]
0x1800020d6  mov     dword ptr [rcx+10h], 0
0x1800020dd  lea     r15, [rcx+58h]
0x1800020e1  mov     qword ptr [rsi], 0
0x1800020e8  lea     rbp, [rcx+60h]
0x1800020ec  mov     dword ptr [r15], 0
0x1800020f3  lea     rax, ??_7CKey@@6B@; const CKey::`vftable'
0x1800020fa  mov     dword ptr [rbp+0], 0
0x180002101  mov     [rcx], rax
0x180002104  mov     r14, r9
0x180002107  lea     rax, [rcx+14h]
0x18000210b  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x180002110  mov     [rcx+50h], rax
0x180002114  mov     rdx, r8; lpSubKey
0x180002117  mov     rdi, rcx
0x18000211a  mov     r9d, 20019h; samDesired
0x180002120  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002127  xor     r8d, r8d; ulOptions
0x18000212a  call    cs:__imp_RegOpenKeyExW
0x180002130  mov     ebx, eax
0x180002132  test    eax, eax
0x180002134  jnz     short loc_1800021AC
0x180002136  lea     r8, [rsp+0A8h+ftLastWriteTime]
0x18000213b  mov     [rsp+0A8h+cbSecurityDescriptor], eax
0x18000213f  mov     [rsp+0A8h+lpftLastWriteTime], r8; lpftLastWriteTime
0x180002144  lea     rax, [rdi+68h]
0x180002148  lea     r8, [rsp+0A8h+cbSecurityDescriptor]
0x18000214d  mov     qword ptr [rsp+0A8h+ftLastWriteTime.dwLowDateTime], 0
0x180002156  mov     [rsp+0A8h+lpcbSecurityDescriptor], r8; lpcbSecurityDescriptor
0x18000215b  lea     rcx, [rdi+64h]
0x18000215f  mov     [rsp+0A8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180002164  lea     rdx, [rdi+5Ch]
0x180002168  mov     [rsp+0A8h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x18000216d  xor     r9d, r9d; lpReserved
0x180002170  mov     rcx, [rsi]; hKey
0x180002173  xor     r8d, r8d; lpcchClass
0x180002176  mov     [rsp+0A8h+lpcValues], rbp; lpcValues
0x18000217b  mov     [rsp+0A8h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180002184  mov     [rsp+0A8h+lpcbMaxSubKeyLen], rdx; lpcbMaxSubKeyLen
0x180002189  xor     edx, edx; lpClass
0x18000218b  mov     [rsp+0A8h+phkResult], r15; lpcSubKeys
0x180002190  call    cs:__imp_RegQueryInfoKeyW
0x180002196  mov     ebx, eax
0x180002198  test    eax, eax
0x18000219a  jz      short loc_1800021AC
0x18000219c  mov     rcx, [rsi]; hKey
0x18000219f  call    cs:__imp_RegCloseKey
0x1800021a5  mov     qword ptr [rsi], 0
0x1800021ac  test    ebx, ebx
0x1800021ae  jle     short loc_1800021B9
0x1800021b0  movzx   ebx, bx
0x1800021b3  or      ebx, 80070000h
0x1800021b9  mov     [r14], ebx
0x1800021bc  mov     rax, rdi
0x1800021bf  mov     rcx, [rsp+0A8h+var_38]
0x1800021c4  xor     rcx, rsp; StackCookie
0x1800021c7  call    __security_check_cookie
0x1800021cc  mov     rbx, [rsp+0A8h+arg_8]
0x1800021d4  add     rsp, 80h
0x1800021db  pop     r15
0x1800021dd  pop     r14
0x1800021df  pop     rdi
0x1800021e0  pop     rsi
0x1800021e1  pop     rbp
0x1800021e2  retn
```
