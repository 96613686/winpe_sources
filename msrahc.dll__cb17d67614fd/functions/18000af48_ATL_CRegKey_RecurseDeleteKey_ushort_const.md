# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000af48`
- end: `0x18000b055`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000af48`
- `0x18000b44c`

## callees

- `0x18000a064`
- `0x18000a394`
- `0x18000ac00`
- `0x18000af48`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000aff4`
- `ADVAPI32!RegEnumKeyExW` at `0x18000aff4`

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
0x18000af48  mov     [rsp-8+arg_10], rbx
0x18000af4d  push    rbp
0x18000af4e  push    rsi
0x18000af4f  push    rdi
0x18000af50  lea     rbp, [rsp-180h]
0x18000af58  sub     rsp, 280h
0x18000af5f  mov     rax, cs:__security_cookie
0x18000af66  xor     rax, rsp
0x18000af69  mov     [rbp+190h+var_20], rax
0x18000af70  mov     rsi, rdx
0x18000af73  mov     [rsp+290h+hKey], 0
0x18000af7c  mov     r8, rdx; lpSubKey
0x18000af7f  mov     [rsp+290h+var_240], 0
0x18000af88  mov     rdx, [rcx]; hKey
0x18000af8b  mov     rdi, rcx
0x18000af8e  lea     rcx, [rsp+290h+hKey]; this
0x18000af93  mov     [rsp+290h+var_238], 0
0x18000af9c  mov     r9d, 2001Fh; unsigned int
0x18000afa2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000afa7  mov     ebx, eax
0x18000afa9  test    eax, eax
0x18000afab  jnz     short loc_18000B027
0x18000afad  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000afb6  mov     rcx, [rsp+290h+hKey]; hKey
0x18000afbb  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000afc0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000afc5  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000afca  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000afd3  lea     r8, [rsp+290h+Name]; lpName
0x18000afd8  mov     [rsp+290h+lpClass], 0; lpClass
0x18000afe1  xor     edx, edx; dwIndex
0x18000afe3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000afec  mov     [rsp+290h+cchName], 100h
0x18000aff4  call    cs:__imp_RegEnumKeyExW
0x18000affa  lea     rcx, [rsp+290h+hKey]; this
0x18000afff  test    eax, eax
0x18000b001  jnz     short loc_18000B015
0x18000b003  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000b008  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b00d  mov     ebx, eax
0x18000b00f  test    eax, eax
0x18000b011  jnz     short loc_18000B027
0x18000b013  jmp     short loc_18000AFB6
0x18000b015  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b01a  mov     rdx, rsi; unsigned __int16 *
0x18000b01d  mov     rcx, rdi; this
0x18000b020  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000b025  mov     ebx, eax
0x18000b027  lea     rcx, [rsp+290h+hKey]; this
0x18000b02c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b031  mov     eax, ebx
0x18000b033  mov     rcx, [rbp+190h+var_20]
0x18000b03a  xor     rcx, rsp; StackCookie
0x18000b03d  call    __security_check_cookie
0x18000b042  mov     rbx, [rsp+290h+arg_10]
0x18000b04a  add     rsp, 280h
0x18000b051  pop     rdi
0x18000b052  pop     rsi
0x18000b053  pop     rbp
0x18000b054  retn
```
