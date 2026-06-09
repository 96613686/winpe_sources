# SQLWritePrivateProfileStringCover

- ea: `0x18000a1b4`
- end: `0x18000a313`
- name: `SQLWritePrivateProfileStringCover`
- size: `351`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, BYTE *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a320`

## callees

- `0x180001010`
- `0x180004bac`
- `0x18000a1b4`
- `0x180013fa8`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a21c`
- `msvcrt!_wcsicmp` at `0x18000a21c`

## pseudocode

```c
__int64 __fastcall SQLWritePrivateProfileStringCover(const WCHAR *a1, const WCHAR *a2, BYTE *a3, const wchar_t *a4)
{
  __int64 v8; // rbx
  WCHAR v10[8]; // [rsp+50h] [rbp-58h] BYREF

  if ( a1 && *a1 && a4 && *a4 )
  {
    if ( (g_wSystemDSN & 1) != 0
      || !_wcsicmp(a4, L"ODBCINST.INI")
      || (v8 = -2147483647, (g_wSystemDSN & 4) != 0)
      && (unsigned int)cpGetPrivateProfileString(
                         (HKEY)g_hkeyMachine,
                         a1,
                         a2,
                         (void *)&SubKey,
                         0xFFFFu,
                         0,
                         v10,
                         10,
                         (__int64)a4,
                         0)
      && !(unsigned int)cpGetPrivateProfileString(
                          HKEY_CURRENT_USER,
                          a1,
                          a2,
                          (void *)&SubKey,
                          0xFFFFu,
                          0,
                          v10,
                          10,
                          (__int64)a4,
                          0) )
    {
      v8 = g_hkeyMachine;
    }
    return cpWritePrivateProfileString((HKEY)v8, (__int64)a1, a2, 1u, a3, (__int64)a4);
  }
  else
  {
    PostInstError(4);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a1b4  push    rbx
0x18000a1b6  push    rbp
0x18000a1b7  push    rsi
0x18000a1b8  push    rdi
0x18000a1b9  push    r14
0x18000a1bb  push    r15
0x18000a1bd  sub     rsp, 78h
0x18000a1c1  mov     rax, cs:__security_cookie
0x18000a1c8  xor     rax, rsp
0x18000a1cb  mov     [rsp+0A8h+var_48], rax
0x18000a1d0  xor     r15d, r15d
0x18000a1d3  mov     rdi, r9
0x18000a1d6  mov     r14, r8
0x18000a1d9  mov     rbp, rdx
0x18000a1dc  mov     rsi, rcx
0x18000a1df  test    rcx, rcx
0x18000a1e2  jz      loc_18000A2ED
0x18000a1e8  cmp     [rcx], r15w
0x18000a1ec  jz      loc_18000A2ED
0x18000a1f2  test    r9, r9
0x18000a1f5  jz      loc_18000A2ED
0x18000a1fb  cmp     [r9], r15w
0x18000a1ff  jz      loc_18000A2ED
0x18000a205  test    byte ptr cs:g_wSystemDSN, 1
0x18000a20c  jnz     loc_18000A2C6
0x18000a212  lea     rdx, aOdbcinstIni; "ODBCINST.INI"
0x18000a219  mov     rcx, r9; String1
0x18000a21c  call    cs:__imp__wcsicmp
0x18000a222  test    eax, eax
0x18000a224  jz      loc_18000A2C6
0x18000a22a  test    byte ptr cs:g_wSystemDSN, 4
0x18000a231  mov     rbx, 0FFFFFFFF80000001h
0x18000a238  jz      loc_18000A2CD
0x18000a23e  mov     rcx, cs:g_hkeyMachine
0x18000a245  lea     rax, [rsp+0A8h+var_58]
0x18000a24a  mov     [rsp+0A8h+var_60], r15
0x18000a24f  lea     r9, SubKey
0x18000a256  mov     [rsp+0A8h+var_68], rdi
0x18000a25b  mov     r8, rbp
0x18000a25e  mov     [rsp+0A8h+var_70], 0Ah
0x18000a266  mov     rdx, rsi
0x18000a269  mov     [rsp+0A8h+var_78], rax
0x18000a26e  mov     [rsp+0A8h+var_80], r15
0x18000a273  mov     dword ptr [rsp+0A8h+lpData], 0FFFFh
0x18000a27b  call    cpGetPrivateProfileString
0x18000a280  test    eax, eax
0x18000a282  jz      short loc_18000A2CD
0x18000a284  mov     [rsp+0A8h+var_60], r15
0x18000a289  lea     rax, [rsp+0A8h+var_58]
0x18000a28e  mov     [rsp+0A8h+var_68], rdi
0x18000a293  lea     r9, SubKey
0x18000a29a  mov     [rsp+0A8h+var_70], 0Ah
0x18000a2a2  mov     r8, rbp
0x18000a2a5  mov     [rsp+0A8h+var_78], rax
0x18000a2aa  mov     rdx, rsi
0x18000a2ad  mov     [rsp+0A8h+var_80], r15
0x18000a2b2  mov     rcx, rbx
0x18000a2b5  mov     dword ptr [rsp+0A8h+lpData], 0FFFFh
0x18000a2bd  call    cpGetPrivateProfileString
0x18000a2c2  test    eax, eax
0x18000a2c4  jnz     short loc_18000A2CD
0x18000a2c6  mov     rbx, cs:g_hkeyMachine
0x18000a2cd  mov     [rsp+0A8h+var_80], rdi; __int64
0x18000a2d2  mov     r9d, 1
0x18000a2d8  mov     r8, rbp
0x18000a2db  mov     [rsp+0A8h+lpData], r14; lpData
0x18000a2e0  mov     rdx, rsi
0x18000a2e3  mov     rcx, rbx; hKey
0x18000a2e6  call    cpWritePrivateProfileString
0x18000a2eb  jmp     short loc_18000A2F9
0x18000a2ed  mov     ecx, 4
0x18000a2f2  call    PostInstError
0x18000a2f7  xor     eax, eax
0x18000a2f9  mov     rcx, [rsp+0A8h+var_48]
0x18000a2fe  xor     rcx, rsp; StackCookie
0x18000a301  call    __security_check_cookie
0x18000a306  add     rsp, 78h
0x18000a30a  pop     r15
0x18000a30c  pop     r14
0x18000a30e  pop     rdi
0x18000a30f  pop     rsi
0x18000a310  pop     rbp
0x18000a311  pop     rbx
0x18000a312  retn
```
