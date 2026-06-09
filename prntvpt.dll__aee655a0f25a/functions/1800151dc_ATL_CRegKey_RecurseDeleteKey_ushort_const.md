# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800151dc`
- end: `0x1800152e9`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800151dc`
- `0x1800155fc`

## callees

- `0x18000f970`
- `0x180012144`
- `0x180012560`
- `0x1800146d4`
- `0x1800151dc`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180015288`
- `ADVAPI32!RegEnumKeyExW` at `0x180015288`

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
0x1800151dc  mov     [rsp-8+arg_10], rbx
0x1800151e1  push    rbp
0x1800151e2  push    rsi
0x1800151e3  push    rdi
0x1800151e4  lea     rbp, [rsp-180h]
0x1800151ec  sub     rsp, 280h
0x1800151f3  mov     rax, cs:__security_cookie
0x1800151fa  xor     rax, rsp
0x1800151fd  mov     [rbp+190h+var_20], rax
0x180015204  mov     rsi, rdx
0x180015207  mov     [rsp+290h+hKey], 0
0x180015210  mov     r8, rdx; lpSubKey
0x180015213  mov     [rsp+290h+var_240], 0
0x18001521c  mov     rdx, [rcx]; hKey
0x18001521f  mov     rdi, rcx
0x180015222  lea     rcx, [rsp+290h+hKey]; this
0x180015227  mov     [rsp+290h+var_238], 0
0x180015230  mov     r9d, 2001Fh; unsigned int
0x180015236  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001523b  mov     ebx, eax
0x18001523d  test    eax, eax
0x18001523f  jnz     short loc_1800152BB
0x180015241  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18001524a  mov     rcx, [rsp+290h+hKey]; hKey
0x18001524f  lea     rax, [rsp+290h+ftLastWriteTime]
0x180015254  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180015259  lea     r9, [rsp+290h+cchName]; lpcchName
0x18001525e  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180015267  lea     r8, [rsp+290h+Name]; lpName
0x18001526c  mov     [rsp+290h+lpClass], 0; lpClass
0x180015275  xor     edx, edx; dwIndex
0x180015277  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180015280  mov     [rsp+290h+cchName], 100h
0x180015288  call    cs:__imp_RegEnumKeyExW
0x18001528e  lea     rcx, [rsp+290h+hKey]; this
0x180015293  test    eax, eax
0x180015295  jnz     short loc_1800152A9
0x180015297  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18001529c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800152a1  mov     ebx, eax
0x1800152a3  test    eax, eax
0x1800152a5  jnz     short loc_1800152BB
0x1800152a7  jmp     short loc_18001524A
0x1800152a9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800152ae  mov     rdx, rsi; unsigned __int16 *
0x1800152b1  mov     rcx, rdi; this
0x1800152b4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800152b9  mov     ebx, eax
0x1800152bb  lea     rcx, [rsp+290h+hKey]; this
0x1800152c0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800152c5  mov     eax, ebx
0x1800152c7  mov     rcx, [rbp+190h+var_20]
0x1800152ce  xor     rcx, rsp; StackCookie
0x1800152d1  call    __security_check_cookie
0x1800152d6  mov     rbx, [rsp+290h+arg_10]
0x1800152de  add     rsp, 280h
0x1800152e5  pop     rdi
0x1800152e6  pop     rsi
0x1800152e7  pop     rbp
0x1800152e8  retn
```
