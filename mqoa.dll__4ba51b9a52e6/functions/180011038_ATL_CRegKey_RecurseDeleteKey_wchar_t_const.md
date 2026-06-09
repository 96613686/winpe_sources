# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x180011038`
- end: `0x180011161`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `297`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011038`
- `0x180011504`

## callees

- `0x18000cb08`
- `0x18000e35c`
- `0x180010074`
- `0x180011038`
- `0x1800273b0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800110f4`
- `ADVAPI32!RegEnumKeyExW` at `0x1800110f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( v4 )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  else
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        return v4;
      }
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180011038  mov     [rsp-8+arg_10], rbx
0x18001103d  push    rbp
0x18001103e  push    rsi
0x18001103f  push    rdi
0x180011040  lea     rbp, [rsp-180h]
0x180011048  sub     rsp, 280h
0x18001104f  mov     rax, cs:__security_cookie
0x180011056  xor     rax, rsp
0x180011059  mov     [rbp+190h+var_20], rax
0x180011060  mov     rsi, rdx
0x180011063  mov     rdi, rcx
0x180011066  mov     [rsp+290h+hKey], 0
0x18001106f  mov     [rsp+290h+var_240], 0
0x180011078  mov     [rsp+290h+var_238], 0
0x180011081  mov     r9d, 2001Fh; unsigned int
0x180011087  mov     r8, rdx; lpSubKey
0x18001108a  mov     rdx, [rcx]; hKey
0x18001108d  lea     rcx, [rsp+290h+hKey]; this
0x180011092  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WKK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong,ulong)
0x180011097  mov     ebx, eax
0x180011099  test    eax, eax
0x18001109b  jz      short loc_1800110AD
0x18001109d  lea     rcx, [rsp+290h+hKey]; this
0x1800110a2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800110a7  nop
0x1800110a8  jmp     loc_18001113D
0x1800110ad  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800110b6  mov     [rsp+290h+cchName], 100h
0x1800110be  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800110c3  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800110c8  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800110d1  mov     [rsp+290h+lpClass], 0; lpClass
0x1800110da  mov     [rsp+290h+lpReserved], 0; unsigned int
0x1800110e3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800110e8  lea     r8, [rsp+290h+Name]; lpName
0x1800110ed  xor     edx, edx; dwIndex
0x1800110ef  mov     rcx, [rsp+290h+hKey]; hKey
0x1800110f4  call    cs:__imp_RegEnumKeyExW
0x1800110fa  lea     rcx, [rsp+290h+hKey]; this
0x1800110ff  test    eax, eax
0x180011101  jnz     short loc_180011120
0x180011103  lea     rdx, [rsp+290h+Name]; wchar_t *
0x180011108  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001110d  mov     ebx, eax
0x18001110f  test    eax, eax
0x180011111  jz      short loc_1800110B6
0x180011113  lea     rcx, [rsp+290h+hKey]; this
0x180011118  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001111d  nop
0x18001111e  jmp     short loc_18001113D
0x180011120  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011125  mov     rdx, rsi; wchar_t *
0x180011128  mov     rcx, rdi; this
0x18001112b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180011130  mov     ebx, eax
0x180011132  lea     rcx, [rsp+290h+hKey]; this
0x180011137  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001113c  nop
0x18001113d  mov     eax, ebx
0x18001113f  mov     rcx, [rbp+190h+var_20]
0x180011146  xor     rcx, rsp; StackCookie
0x180011149  call    __security_check_cookie
0x18001114e  mov     rbx, [rsp+290h+arg_10]
0x180011156  add     rsp, 280h
0x18001115d  pop     rdi
0x18001115e  pop     rsi
0x18001115f  pop     rbp
0x180011160  retn
```
