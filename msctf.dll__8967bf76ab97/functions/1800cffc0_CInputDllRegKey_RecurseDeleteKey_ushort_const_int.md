# CInputDllRegKey::RecurseDeleteKey(ushort const *,int)

- ea: `0x1800cffc0`
- end: `0x1800d0143`
- name: `?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z`
- size: `387`
- prototype: `__int64 __fastcall(CInputDllRegKey *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800cffc0`
- `0x1800d086c`
- `0x1800d0b9c`

## callees

- `0x1800539d8`
- `0x1800cf4a4`
- `0x1800cffc0`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d00c4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d00c4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d00fd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d00fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d00b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d00b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d0067`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d0067`

## pseudocode

```c
__int64 __fastcall CInputDllRegKey::RecurseDeleteKey(CInputDllRegKey *this, const unsigned __int16 *a2, int a3)
{
  HKEY v7; // rdx
  unsigned int v8; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  void **v11; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h]
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  v11 = &CPreloadRegKey::`vftable';
  v7 = (HKEY)*((_QWORD *)this + 1);
  hKey = 0;
  v8 = CInputDllRegKey::Open((CInputDllRegKey *)&v11, v7, a2, 0x2001Fu);
  if ( !v8 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      Name[255] = 0;
      v8 = CInputDllRegKey::RecurseDeleteKey((CInputDllRegKey *)&v11, Name, 1);
      if ( v8 )
        goto LABEL_10;
    }
    if ( a3 )
    {
      CInputDllRegKey::Close((CInputDllRegKey *)&v11);
      v8 = RegDeleteKeyExW(*((HKEY *)this + 1), a2, 0, 0);
    }
    else
    {
      do
      {
        cchName = 256;
        if ( RegEnumValueW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
          break;
        v8 = RegDeleteValueW(hKey, Name);
      }
      while ( !v8 );
    }
  }
LABEL_10:
  v11 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v11);
  return v8;
}

```

## disassembly

```asm
0x1800cffc0  mov     [rsp-8+arg_10], rbx
0x1800cffc5  mov     [rsp-8+arg_18], rsi
0x1800cffca  push    rbp
0x1800cffcb  push    rdi
0x1800cffcc  push    r13
0x1800cffce  push    r14
0x1800cffd0  push    r15
0x1800cffd2  lea     rbp, [rsp-170h]
0x1800cffda  sub     rsp, 270h
0x1800cffe1  mov     rax, cs:__security_cookie
0x1800cffe8  xor     rax, rsp
0x1800cffeb  mov     [rbp+190h+var_30], rax
0x1800cfff2  mov     r14d, r8d
0x1800cfff5  lea     r13, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800cfffc  mov     r8, rdx; lpSubKey
0x1800cffff  mov     [rsp+290h+var_248], r13
0x1800d0004  mov     rsi, rdx
0x1800d0007  mov     rdi, rcx
0x1800d000a  mov     rdx, [rcx+8]; hKey
0x1800d000e  xor     r15d, r15d
0x1800d0011  lea     rcx, [rsp+290h+var_248]; this
0x1800d0016  mov     [rsp+290h+hKey], r15
0x1800d001b  mov     r9d, 2001Fh; samDesired
0x1800d0021  call    ?Open@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CInputDllRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800d0026  mov     ebx, eax
0x1800d0028  test    eax, eax
0x1800d002a  jnz     loc_1800D0107
0x1800d0030  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r15
0x1800d0035  mov     rcx, [rsp+290h+hKey]; hKey
0x1800d003a  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800d003f  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800d0044  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800d0049  mov     [rsp+290h+lpcchClass], r15; lpcchClass
0x1800d004e  lea     r8, [rsp+290h+Name]; lpName
0x1800d0053  mov     [rsp+290h+lpClass], r15; lpClass
0x1800d0058  xor     edx, edx; dwIndex
0x1800d005a  mov     [rsp+290h+lpReserved], r15; lpReserved
0x1800d005f  mov     [rsp+290h+cchName], 100h
0x1800d0067  call    cs:__imp_RegEnumKeyExW
0x1800d006d  test    eax, eax
0x1800d006f  jnz     short loc_1800D0094
0x1800d0071  lea     r8d, [rax+1]; int
0x1800d0075  mov     [rbp+190h+var_32], r15w
0x1800d007d  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800d0082  lea     rcx, [rsp+290h+var_248]; this
0x1800d0087  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x1800d008c  mov     ebx, eax
0x1800d008e  test    eax, eax
0x1800d0090  jz      short loc_1800D0035
0x1800d0092  jmp     short loc_1800D0107
0x1800d0094  test    r14d, r14d
0x1800d0097  jz      short loc_1800D00D0
0x1800d0099  lea     rcx, [rsp+290h+var_248]; this
0x1800d009e  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800d00a3  mov     rcx, [rdi+8]; hKey
0x1800d00a7  xor     r9d, r9d; Reserved
0x1800d00aa  xor     r8d, r8d; samDesired
0x1800d00ad  mov     rdx, rsi; lpSubKey
0x1800d00b0  call    cs:__imp_RegDeleteKeyExW
0x1800d00b6  mov     ebx, eax
0x1800d00b8  jmp     short loc_1800D0107
0x1800d00ba  mov     rcx, [rsp+290h+hKey]; hKey
0x1800d00bf  lea     rdx, [rsp+290h+Name]; lpValueName
0x1800d00c4  call    cs:__imp_RegDeleteValueW
0x1800d00ca  mov     ebx, eax
0x1800d00cc  test    eax, eax
0x1800d00ce  jnz     short loc_1800D0107
0x1800d00d0  mov     rcx, [rsp+290h+hKey]; hKey
0x1800d00d5  lea     r9, [rsp+290h+cchName]; lpcchValueName
0x1800d00da  mov     [rsp+290h+lpftLastWriteTime], r15; lpcbData
0x1800d00df  lea     r8, [rsp+290h+Name]; lpValueName
0x1800d00e4  mov     [rsp+290h+lpcchClass], r15; lpData
0x1800d00e9  xor     edx, edx; dwIndex
0x1800d00eb  mov     [rsp+290h+lpClass], r15; lpType
0x1800d00f0  mov     [rsp+290h+lpReserved], r15; lpReserved
0x1800d00f5  mov     [rsp+290h+cchName], 100h
0x1800d00fd  call    cs:__imp_RegEnumValueW
0x1800d0103  test    eax, eax
0x1800d0105  jz      short loc_1800D00BA
0x1800d0107  lea     rcx, [rsp+290h+var_248]; this
0x1800d010c  mov     [rsp+290h+var_248], r13
0x1800d0111  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800d0116  mov     eax, ebx
0x1800d0118  mov     rcx, [rbp+190h+var_30]
0x1800d011f  xor     rcx, rsp; StackCookie
0x1800d0122  call    __security_check_cookie
0x1800d0127  lea     r11, [rsp+290h+var_20]
0x1800d012f  mov     rbx, [r11+40h]
0x1800d0133  mov     rsi, [r11+48h]
0x1800d0137  mov     rsp, r11
0x1800d013a  pop     r15
0x1800d013c  pop     r14
0x1800d013e  pop     r13
0x1800d0140  pop     rdi
0x1800d0141  pop     rbp
0x1800d0142  retn
```
