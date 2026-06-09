# SQLRemoveTranslatorCover

- ea: `0x180009c30`
- end: `0x180009cea`
- name: `SQLRemoveTranslatorCover`
- size: `186`
- prototype: `__int64 __fastcall(const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009cf0`

## callees

- `0x180001010`
- `0x180004bac`
- `0x180007200`
- `0x180009c30`
- `0x180014ae0`

## pseudocode

```c
__int64 __fastcall SQLRemoveTranslatorCover(const WCHAR *a1, _DWORD *a2)
{
  int v4; // ecx
  WCHAR v6[8]; // [rsp+50h] [rbp-28h] BYREF

  if ( a1 && *a1 )
  {
    if ( (unsigned int)cpGetPrivateProfileString(
                         HKEY_LOCAL_MACHINE,
                         L"ODBC Translators",
                         a1,
                         (void *)&SubKey,
                         0xFFFFu,
                         0,
                         v6,
                         5,
                         (__int64)L"ODBCINST.INI",
                         0) )
      return RemoveTranslator(a1, a2);
    v4 = 6;
  }
  else
  {
    v4 = 7;
  }
  PostInstError(v4);
  return 0;
}

```

## disassembly

```asm
0x180009c30  mov     r11, rsp
0x180009c33  mov     [r11+18h], rbx
0x180009c37  mov     [r11+20h], rsi
0x180009c3b  push    rdi
0x180009c3c  sub     rsp, 70h
0x180009c40  mov     rax, cs:__security_cookie
0x180009c47  xor     rax, rsp
0x180009c4a  mov     [rsp+78h+var_18], rax
0x180009c4f  xor     esi, esi
0x180009c51  mov     rdi, rdx
0x180009c54  mov     rbx, rcx
0x180009c57  test    rcx, rcx
0x180009c5a  jz      short loc_180009CBF
0x180009c5c  cmp     [rcx], si
0x180009c5f  jz      short loc_180009CBF
0x180009c61  mov     [r11-30h], rsi
0x180009c65  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180009c6c  mov     [r11-38h], rax
0x180009c70  lea     r9, SubKey
0x180009c77  mov     [rsp+78h+var_40], 5
0x180009c7f  lea     rax, [r11-28h]
0x180009c83  mov     [r11-48h], rax
0x180009c87  lea     rdx, szSection; "ODBC Translators"
0x180009c8e  mov     r8, rcx
0x180009c91  mov     [r11-50h], rsi
0x180009c95  mov     rcx, 0FFFFFFFF80000002h
0x180009c9c  mov     [rsp+78h+var_58], 0FFFFh
0x180009ca4  call    cpGetPrivateProfileString
0x180009ca9  test    eax, eax
0x180009cab  jnz     short loc_180009CB2
0x180009cad  lea     ecx, [rsi+6]
0x180009cb0  jmp     short loc_180009CC4
0x180009cb2  mov     rdx, rdi
0x180009cb5  mov     rcx, rbx
0x180009cb8  call    RemoveTranslator
0x180009cbd  jmp     short loc_180009CCB
0x180009cbf  mov     ecx, 7
0x180009cc4  call    PostInstError
0x180009cc9  xor     eax, eax
0x180009ccb  mov     rcx, [rsp+78h+var_18]
0x180009cd0  xor     rcx, rsp; StackCookie
0x180009cd3  call    __security_check_cookie
0x180009cd8  lea     r11, [rsp+78h+var_8]
0x180009cdd  mov     rbx, [r11+20h]
0x180009ce1  mov     rsi, [r11+28h]
0x180009ce5  mov     rsp, r11
0x180009ce8  pop     rdi
0x180009ce9  retn
```
