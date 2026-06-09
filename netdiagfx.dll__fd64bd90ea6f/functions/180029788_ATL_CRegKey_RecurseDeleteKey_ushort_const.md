# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180029788`
- end: `0x180029895`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180028cdc`
- `0x180029788`

## callees

- `0x18001f0a4`
- `0x180021094`
- `0x180029250`
- `0x180029788`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180029834`
- `ADVAPI32!RegEnumKeyExW` at `0x180029834`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open(hKey, *this, a2, 0x2001Fu);
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
    ATL::CRegKey::Close(hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x180029788  mov     [rsp-8+arg_10], rbx
0x18002978d  push    rbp
0x18002978e  push    rsi
0x18002978f  push    rdi
0x180029790  lea     rbp, [rsp-180h]
0x180029798  sub     rsp, 280h
0x18002979f  mov     rax, cs:__security_cookie
0x1800297a6  xor     rax, rsp
0x1800297a9  mov     [rbp+190h+var_20], rax
0x1800297b0  mov     rsi, rdx
0x1800297b3  mov     [rsp+290h+hKey], 0
0x1800297bc  mov     r8, rdx; lpSubKey
0x1800297bf  mov     [rsp+290h+var_240], 0
0x1800297c8  mov     rdx, [rcx]; hKey
0x1800297cb  mov     rdi, rcx
0x1800297ce  lea     rcx, [rsp+290h+hKey]; this
0x1800297d3  mov     [rsp+290h+var_238], 0
0x1800297dc  mov     r9d, 2001Fh; unsigned int
0x1800297e2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800297e7  mov     ebx, eax
0x1800297e9  test    eax, eax
0x1800297eb  jnz     short loc_180029867
0x1800297ed  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800297f6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800297fb  lea     rax, [rsp+290h+ftLastWriteTime]
0x180029800  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180029805  lea     r9, [rsp+290h+cchName]; lpcchName
0x18002980a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180029813  lea     r8, [rsp+290h+Name]; lpName
0x180029818  mov     [rsp+290h+lpClass], 0; lpClass
0x180029821  xor     edx, edx; dwIndex
0x180029823  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18002982c  mov     [rsp+290h+cchName], 100h
0x180029834  call    cs:__imp_RegEnumKeyExW
0x18002983a  lea     rcx, [rsp+290h+hKey]; this
0x18002983f  test    eax, eax
0x180029841  jnz     short loc_180029855
0x180029843  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180029848  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002984d  mov     ebx, eax
0x18002984f  test    eax, eax
0x180029851  jnz     short loc_180029867
0x180029853  jmp     short loc_1800297F6
0x180029855  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002985a  mov     rdx, rsi; unsigned __int16 *
0x18002985d  mov     rcx, rdi; this
0x180029860  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180029865  mov     ebx, eax
0x180029867  lea     rcx, [rsp+290h+hKey]; this
0x18002986c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029871  mov     eax, ebx
0x180029873  mov     rcx, [rbp+190h+var_20]
0x18002987a  xor     rcx, rsp; StackCookie
0x18002987d  call    __security_check_cookie
0x180029882  mov     rbx, [rsp+290h+arg_10]
0x18002988a  add     rsp, 280h
0x180029891  pop     rdi
0x180029892  pop     rsi
0x180029893  pop     rbp
0x180029894  retn
```
