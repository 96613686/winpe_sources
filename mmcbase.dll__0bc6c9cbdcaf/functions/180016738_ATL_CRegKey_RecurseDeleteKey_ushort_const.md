# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180016738`
- end: `0x180016845`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008670`
- `0x180016738`

## callees

- `0x180008cdc`
- `0x180015a44`
- `0x1800164b4`
- `0x180016738`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800167e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800167e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180016738  mov     [rsp-8+arg_10], rbx
0x18001673d  push    rbp
0x18001673e  push    rsi
0x18001673f  push    rdi
0x180016740  lea     rbp, [rsp-180h]
0x180016748  sub     rsp, 280h
0x18001674f  mov     rax, cs:__security_cookie
0x180016756  xor     rax, rsp
0x180016759  mov     [rbp+190h+var_20], rax
0x180016760  mov     rsi, rdx
0x180016763  mov     rdi, rcx
0x180016766  mov     [rsp+290h+hKey], 0
0x18001676f  mov     [rsp+290h+var_240], 0
0x180016778  mov     [rsp+290h+var_238], 0
0x180016781  mov     r9d, 2001Fh; unsigned int
0x180016787  mov     r8, rdx; lpSubKey
0x18001678a  mov     rdx, [rcx]; hKey
0x18001678d  lea     rcx, [rsp+290h+hKey]; this
0x180016792  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180016797  mov     ebx, eax
0x180016799  test    eax, eax
0x18001679b  jnz     short loc_180016817
0x18001679d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800167a6  mov     [rsp+290h+cchName], 100h
0x1800167ae  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800167b3  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800167b8  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800167c1  mov     [rsp+290h+lpClass], 0; lpClass
0x1800167ca  mov     [rsp+290h+lpReserved], 0; unsigned int
0x1800167d3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800167d8  lea     r8, [rsp+290h+Name]; lpName
0x1800167dd  xor     edx, edx; dwIndex
0x1800167df  mov     rcx, [rsp+290h+hKey]; hKey
0x1800167e4  call    cs:__imp_RegEnumKeyExW
0x1800167ea  lea     rcx, [rsp+290h+hKey]; this
0x1800167ef  test    eax, eax
0x1800167f1  jnz     short loc_180016805
0x1800167f3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800167f8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800167fd  mov     ebx, eax
0x1800167ff  test    eax, eax
0x180016801  jnz     short loc_180016817
0x180016803  jmp     short loc_1800167A6
0x180016805  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001680a  mov     rdx, rsi; unsigned __int16 *
0x18001680d  mov     rcx, rdi; this
0x180016810  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180016815  mov     ebx, eax
0x180016817  lea     rcx, [rsp+290h+hKey]; this
0x18001681c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016821  mov     eax, ebx
0x180016823  mov     rcx, [rbp+190h+var_20]
0x18001682a  xor     rcx, rsp; StackCookie
0x18001682d  call    __security_check_cookie
0x180016832  mov     rbx, [rsp+290h+arg_10]
0x18001683a  add     rsp, 280h
0x180016841  pop     rdi
0x180016842  pop     rsi
0x180016843  pop     rbp
0x180016844  retn
```
