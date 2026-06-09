# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180005658`
- end: `0x180005765`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005658`
- `0x180005a90`

## callees

- `0x180004464`
- `0x180004d4c`
- `0x18000517c`
- `0x180005658`
- `0x180031680`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180005704`
- `ADVAPI32!RegEnumKeyExW` at `0x180005704`

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
0x180005658  mov     [rsp-8+arg_10], rbx
0x18000565d  push    rbp
0x18000565e  push    rsi
0x18000565f  push    rdi
0x180005660  lea     rbp, [rsp-180h]
0x180005668  sub     rsp, 280h
0x18000566f  mov     rax, cs:__security_cookie
0x180005676  xor     rax, rsp
0x180005679  mov     [rbp+190h+var_20], rax
0x180005680  mov     rsi, rdx
0x180005683  mov     [rsp+290h+hKey], 0
0x18000568c  mov     r8, rdx; lpSubKey
0x18000568f  mov     [rsp+290h+var_240], 0
0x180005698  mov     rdx, [rcx]; hKey
0x18000569b  mov     rdi, rcx
0x18000569e  lea     rcx, [rsp+290h+hKey]; this
0x1800056a3  mov     [rsp+290h+var_238], 0
0x1800056ac  mov     r9d, 2001Fh; unsigned int
0x1800056b2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800056b7  mov     ebx, eax
0x1800056b9  test    eax, eax
0x1800056bb  jnz     short loc_180005737
0x1800056bd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800056c6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800056cb  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800056d0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800056d5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800056da  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800056e3  lea     r8, [rsp+290h+Name]; lpName
0x1800056e8  mov     [rsp+290h+lpClass], 0; lpClass
0x1800056f1  xor     edx, edx; dwIndex
0x1800056f3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800056fc  mov     [rsp+290h+cchName], 100h
0x180005704  call    cs:__imp_RegEnumKeyExW
0x18000570a  lea     rcx, [rsp+290h+hKey]; this
0x18000570f  test    eax, eax
0x180005711  jnz     short loc_180005725
0x180005713  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005718  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000571d  mov     ebx, eax
0x18000571f  test    eax, eax
0x180005721  jnz     short loc_180005737
0x180005723  jmp     short loc_1800056C6
0x180005725  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000572a  mov     rdx, rsi; unsigned __int16 *
0x18000572d  mov     rcx, rdi; this
0x180005730  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180005735  mov     ebx, eax
0x180005737  lea     rcx, [rsp+290h+hKey]; this
0x18000573c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005741  mov     eax, ebx
0x180005743  mov     rcx, [rbp+190h+var_20]
0x18000574a  xor     rcx, rsp; StackCookie
0x18000574d  call    __security_check_cookie
0x180005752  mov     rbx, [rsp+290h+arg_10]
0x18000575a  add     rsp, 280h
0x180005761  pop     rdi
0x180005762  pop     rsi
0x180005763  pop     rbp
0x180005764  retn
```
