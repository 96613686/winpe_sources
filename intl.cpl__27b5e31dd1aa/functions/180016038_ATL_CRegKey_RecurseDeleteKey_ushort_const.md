# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180016038`
- end: `0x180016145`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016038`
- `0x18001646c`

## callees

- `0x1800143d4`
- `0x180014aac`
- `0x180015d5c`
- `0x180016038`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800160f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800160f6`

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
        goto LABEL_6;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_6:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180016038  mov     [rsp-8+arg_10], rbx
0x18001603d  push    rbp
0x18001603e  push    rsi
0x18001603f  push    rdi
0x180016040  lea     rbp, [rsp-180h]
0x180016048  sub     rsp, 280h
0x18001604f  mov     rax, cs:__security_cookie
0x180016056  xor     rax, rsp
0x180016059  mov     [rbp+190h+var_20], rax
0x180016060  mov     rsi, rdx
0x180016063  mov     [rsp+290h+hKey], 0
0x18001606c  mov     r8, rdx; lpSubKey
0x18001606f  mov     [rsp+290h+var_240], 0
0x180016078  mov     rdx, [rcx]; hKey
0x18001607b  mov     rdi, rcx
0x18001607e  lea     rcx, [rsp+290h+hKey]; this
0x180016083  mov     [rsp+290h+var_238], 0
0x18001608c  mov     r9d, 2001Fh; unsigned int
0x180016092  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016097  mov     ebx, eax
0x180016099  test    eax, eax
0x18001609b  jnz     short loc_180016117
0x18001609d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800160a6  jmp     short loc_1800160B8
0x1800160a8  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800160ad  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800160b2  mov     ebx, eax
0x1800160b4  test    eax, eax
0x1800160b6  jnz     short loc_180016117
0x1800160b8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800160bd  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800160c2  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800160c7  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800160cc  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800160d5  lea     r8, [rsp+290h+Name]; lpName
0x1800160da  mov     [rsp+290h+lpClass], 0; lpClass
0x1800160e3  xor     edx, edx; dwIndex
0x1800160e5  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800160ee  mov     [rsp+290h+cchName], 100h
0x1800160f6  call    cs:__imp_RegEnumKeyExW
0x1800160fc  lea     rcx, [rsp+290h+hKey]; this
0x180016101  test    eax, eax
0x180016103  jz      short loc_1800160A8
0x180016105  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001610a  mov     rdx, rsi; unsigned __int16 *
0x18001610d  mov     rcx, rdi; this
0x180016110  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180016115  mov     ebx, eax
0x180016117  lea     rcx, [rsp+290h+hKey]; this
0x18001611c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016121  mov     eax, ebx
0x180016123  mov     rcx, [rbp+190h+var_20]
0x18001612a  xor     rcx, rsp; StackCookie
0x18001612d  call    __security_check_cookie
0x180016132  mov     rbx, [rsp+290h+arg_10]
0x18001613a  add     rsp, 280h
0x180016141  pop     rdi
0x180016142  pop     rsi
0x180016143  pop     rbp
0x180016144  retn
```
