# CCMLuaUtil::DeleteRegTree(int,ushort const *)

- ea: `0x180003240`
- end: `0x18000337b`
- name: `?DeleteRegTree@CCMLuaUtil@@UEAAJHPEBG@Z`
- size: `315`
- prototype: `int __fastcall(CCMLuaUtil *this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003240`
- `0x180005486`
- `0x1800054b0`
- `0x180006010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000333c`
- `ADVAPI32!RegCloseKey` at `0x18000333c`
- `ADVAPI32!RegDeleteKeyW` at `0x18000334c`
- `ADVAPI32!RegDeleteKeyW` at `0x18000334c`
- `ADVAPI32!RegEnumKeyExW` at `0x18000332a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000332a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000329f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000329f`

## pseudocode

```c
int __fastcall CCMLuaUtil::DeleteRegTree(CCMLuaUtil *this, unsigned int a2, const unsigned __int16 *a3)
{
  _BOOL8 v6; // rbx
  int result; // eax
  bool v8; // sf
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v6 = a2 != 0;
  result = RegOpenKeyExW((HKEY)(v6 - 0x7FFFFFFF), a3, 0, 0xF003Fu, &hKey);
  v8 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v8 = result < 0;
  }
  if ( !v8 )
  {
    memset_0(Name, 0, 0x20Au);
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        break;
      (*(void (__fastcall **)(CCMLuaUtil *, _QWORD, WCHAR *))(*(_QWORD *)this + 104LL))(this, a2, Name);
    }
    RegCloseKey(hKey);
    result = RegDeleteKeyW((HKEY)(v6 - 0x7FFFFFFF), a3);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180003240  push    rbp
0x180003242  push    rbx
0x180003243  push    rsi
0x180003244  push    rdi
0x180003245  push    r14
0x180003247  lea     rbp, [rsp-180h]
0x18000324f  sub     rsp, 280h
0x180003256  mov     rax, cs:__security_cookie
0x18000325d  xor     rax, rsp
0x180003260  mov     [rbp+1A0h+var_30], rax
0x180003267  mov     eax, edx
0x180003269  mov     [rsp+2A0h+hKey], 0
0x180003272  neg     eax
0x180003274  mov     rdi, r8
0x180003277  mov     esi, edx
0x180003279  lea     rax, [rsp+2A0h+hKey]
0x18000327e  sbb     rbx, rbx
0x180003281  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180003286  mov     r14, rcx
0x180003289  neg     rbx
0x18000328c  mov     r9d, 0F003Fh; samDesired
0x180003292  xor     r8d, r8d; ulOptions
0x180003295  mov     rdx, rdi; lpSubKey
0x180003298  lea     rcx, [rbx-7FFFFFFFh]; hKey
0x18000329f  call    cs:__imp_RegOpenKeyExW
0x1800032a5  test    eax, eax
0x1800032a7  jle     short loc_1800032B3
0x1800032a9  movzx   eax, ax
0x1800032ac  or      eax, 80070000h
0x1800032b1  test    eax, eax
0x1800032b3  js      loc_18000335E
0x1800032b9  xor     edx, edx; Val
0x1800032bb  lea     rcx, [rsp+2A0h+Name]; void *
0x1800032c0  mov     r8d, 20Ah; Size
0x1800032c6  call    memset_0
0x1800032cb  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], 0
0x1800032d4  jmp     short loc_1800032EC
0x1800032d6  mov     rax, [r14]
0x1800032d9  lea     r8, [rsp+2A0h+Name]
0x1800032de  mov     edx, esi
0x1800032e0  mov     rcx, r14
0x1800032e3  mov     rax, [rax+68h]
0x1800032e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ec  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800032f1  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x1800032f6  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800032fb  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180003300  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180003309  lea     r8, [rsp+2A0h+Name]; lpName
0x18000330e  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180003317  xor     edx, edx; dwIndex
0x180003319  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x180003322  mov     [rsp+2A0h+cchName], 104h
0x18000332a  call    cs:__imp_RegEnumKeyExW
0x180003330  cmp     eax, 103h
0x180003335  jnz     short loc_1800032D6
0x180003337  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000333c  call    cs:__imp_RegCloseKey
0x180003342  mov     rdx, rdi; lpSubKey
0x180003345  lea     rcx, [rbx-7FFFFFFFh]; hKey
0x18000334c  call    cs:__imp_RegDeleteKeyW
0x180003352  test    eax, eax
0x180003354  jle     short loc_18000335E
0x180003356  movzx   eax, ax
0x180003359  or      eax, 80070000h
0x18000335e  mov     rcx, [rbp+1A0h+var_30]
0x180003365  xor     rcx, rsp; StackCookie
0x180003368  call    __security_check_cookie
0x18000336d  add     rsp, 280h
0x180003374  pop     r14
0x180003376  pop     rdi
0x180003377  pop     rsi
0x180003378  pop     rbx
0x180003379  pop     rbp
0x18000337a  retn
```
