# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180014780`
- end: `0x18001488d`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180014780`
- `0x180014d38`

## callees

- `0x180001710`
- `0x18000aeb8`
- `0x18000f0fc`
- `0x1800128a4`
- `0x180014780`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18001482c`
- `ADVAPI32!RegEnumKeyExW` at `0x18001482c`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
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
0x180014780  mov     [rsp-8+arg_10], rbx
0x180014785  push    rbp
0x180014786  push    rsi
0x180014787  push    rdi
0x180014788  lea     rbp, [rsp-180h]
0x180014790  sub     rsp, 280h
0x180014797  mov     rax, cs:__security_cookie
0x18001479e  xor     rax, rsp
0x1800147a1  mov     [rbp+190h+var_20], rax
0x1800147a8  mov     rsi, rdx
0x1800147ab  mov     [rsp+290h+hKey], 0
0x1800147b4  mov     r8, rdx; lpSubKey
0x1800147b7  mov     [rsp+290h+var_248], 0
0x1800147c0  mov     rdx, [rcx]; hKey
0x1800147c3  mov     rdi, rcx
0x1800147c6  lea     rcx, [rsp+290h+hKey]; this
0x1800147cb  mov     [rsp+290h+var_240], 0
0x1800147d4  mov     r9d, 2001Fh; unsigned int
0x1800147da  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800147df  mov     ebx, eax
0x1800147e1  test    eax, eax
0x1800147e3  jnz     short loc_18001485F
0x1800147e5  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800147ee  mov     rcx, [rsp+290h+hKey]; hKey
0x1800147f3  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800147f8  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800147fd  lea     r9, [rsp+290h+cchName]; lpcchName
0x180014802  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18001480b  lea     r8, [rsp+290h+Name]; lpName
0x180014810  mov     [rsp+290h+lpClass], 0; lpClass
0x180014819  xor     edx, edx; dwIndex
0x18001481b  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180014824  mov     [rsp+290h+cchName], 100h
0x18001482c  call    cs:__imp_RegEnumKeyExW
0x180014832  lea     rcx, [rsp+290h+hKey]; this
0x180014837  test    eax, eax
0x180014839  jnz     short loc_18001484D
0x18001483b  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180014840  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180014845  mov     ebx, eax
0x180014847  test    eax, eax
0x180014849  jnz     short loc_18001485F
0x18001484b  jmp     short loc_1800147EE
0x18001484d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014852  mov     rdx, rsi; unsigned __int16 *
0x180014855  mov     rcx, rdi; this
0x180014858  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001485d  mov     ebx, eax
0x18001485f  lea     rcx, [rsp+290h+hKey]; this
0x180014864  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014869  mov     eax, ebx
0x18001486b  mov     rcx, [rbp+190h+var_20]
0x180014872  xor     rcx, rsp; StackCookie
0x180014875  call    __security_check_cookie
0x18001487a  mov     rbx, [rsp+290h+arg_10]
0x180014882  add     rsp, 280h
0x180014889  pop     rdi
0x18001488a  pop     rsi
0x18001488b  pop     rbp
0x18001488c  retn
```
