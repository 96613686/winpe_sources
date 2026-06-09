# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000d348`
- end: `0x18000d455`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d348`
- `0x18000d764`

## callees

- `0x18000c954`
- `0x18000c980`
- `0x18000d074`
- `0x18000d348`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d3f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d3f4`

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
0x18000d348  mov     [rsp-8+arg_10], rbx
0x18000d34d  push    rbp
0x18000d34e  push    rsi
0x18000d34f  push    rdi
0x18000d350  lea     rbp, [rsp-180h]
0x18000d358  sub     rsp, 280h
0x18000d35f  mov     rax, cs:__security_cookie
0x18000d366  xor     rax, rsp
0x18000d369  mov     [rbp+190h+var_20], rax
0x18000d370  mov     rsi, rdx
0x18000d373  mov     [rsp+290h+hKey], 0
0x18000d37c  mov     r8, rdx; lpSubKey
0x18000d37f  mov     [rsp+290h+var_240], 0
0x18000d388  mov     rdx, [rcx]; hKey
0x18000d38b  mov     rdi, rcx
0x18000d38e  lea     rcx, [rsp+290h+hKey]; this
0x18000d393  mov     [rsp+290h+var_238], 0
0x18000d39c  mov     r9d, 2001Fh; unsigned int
0x18000d3a2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d3a7  mov     ebx, eax
0x18000d3a9  test    eax, eax
0x18000d3ab  jnz     short loc_18000D427
0x18000d3ad  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000d3b6  mov     rcx, [rsp+290h+hKey]; hKey
0x18000d3bb  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000d3c0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000d3c5  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000d3ca  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000d3d3  lea     r8, [rsp+290h+Name]; lpName
0x18000d3d8  mov     [rsp+290h+lpClass], 0; lpClass
0x18000d3e1  xor     edx, edx; dwIndex
0x18000d3e3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000d3ec  mov     [rsp+290h+cchName], 100h
0x18000d3f4  call    cs:__imp_RegEnumKeyExW
0x18000d3fa  lea     rcx, [rsp+290h+hKey]; this
0x18000d3ff  test    eax, eax
0x18000d401  jnz     short loc_18000D415
0x18000d403  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000d408  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000d40d  mov     ebx, eax
0x18000d40f  test    eax, eax
0x18000d411  jnz     short loc_18000D427
0x18000d413  jmp     short loc_18000D3B6
0x18000d415  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d41a  mov     rdx, rsi; unsigned __int16 *
0x18000d41d  mov     rcx, rdi; this
0x18000d420  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000d425  mov     ebx, eax
0x18000d427  lea     rcx, [rsp+290h+hKey]; this
0x18000d42c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d431  mov     eax, ebx
0x18000d433  mov     rcx, [rbp+190h+var_20]
0x18000d43a  xor     rcx, rsp; StackCookie
0x18000d43d  call    __security_check_cookie
0x18000d442  mov     rbx, [rsp+290h+arg_10]
0x18000d44a  add     rsp, 280h
0x18000d451  pop     rdi
0x18000d452  pop     rsi
0x18000d453  pop     rbp
0x18000d454  retn
```
