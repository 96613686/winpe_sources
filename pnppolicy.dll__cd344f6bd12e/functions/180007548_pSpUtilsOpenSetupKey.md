# pSpUtilsOpenSetupKey

- ea: `0x180007548`
- end: `0x180007625`
- name: `pSpUtilsOpenSetupKey`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800061d8`
- `0x1800077d0`

## callees

- `0x180003820`
- `0x180003988`
- `0x180007548`
- `0x18000a1a0`

## pseudocode

```c
__int64 __fastcall pSpUtilsOpenSetupKey(HANDLE *a1, _QWORD *a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 v7; // [rsp+34h] [rbp-234h] BYREF

  LODWORD(v7) = 520;
  v5 = pSetupOpenKey((void *)0xFFFFFFFF80000002LL, L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup", a3, 1u, a1);
  if ( !v5 && a2 )
  {
    pSetupQueryValue(*a1, L"SetupOverride", (__int64)&v7);
    *a2 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180007548  mov     [rsp+arg_10], rbx
0x18000754d  mov     [rsp+arg_18], rsi
0x180007552  push    rdi
0x180007553  sub     rsp, 260h
0x18000755a  mov     rax, cs:__security_cookie
0x180007561  xor     rax, rsp
0x180007564  mov     [rsp+268h+var_18], rax
0x18000756c  mov     rbx, rdx
0x18000756f  mov     [rsp+268h+var_248], rcx
0x180007574  mov     rsi, rcx
0x180007577  mov     [rsp+268h+var_238], 0
0x18000757f  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007586  mov     dword ptr [rsp+268h+var_234], 208h
0x18000758e  mov     rcx, 0FFFFFFFF80000002h
0x180007595  mov     r9d, 1
0x18000759b  call    pSetupOpenKey
0x1800075a0  mov     edi, eax
0x1800075a2  test    eax, eax
0x1800075a4  jnz     short loc_1800075FE
0x1800075a6  test    rbx, rbx
0x1800075a9  jz      short loc_1800075FE
0x1800075ab  mov     rcx, [rsi]; KeyHandle
0x1800075ae  lea     rax, [rsp+268h+var_234]
0x1800075b3  lea     r9, [rsp+268h+var_228]
0x1800075b8  mov     [rsp+268h+var_248], rax; __int64
0x1800075bd  lea     r8, [rsp+268h+var_238]
0x1800075c2  lea     rdx, aSetupoverride; "SetupOverride"
0x1800075c9  call    pSetupQueryValue
0x1800075ce  test    eax, eax
0x1800075d0  jnz     short loc_1800075F7
0x1800075d2  cmp     [rsp+268h+var_238], 1
0x1800075d7  jnz     short loc_1800075F7
0x1800075d9  lea     r9d, [rdi+1]
0x1800075dd  mov     [rsp+268h+var_248], rbx
0x1800075e2  lea     rdx, [rsp+268h+var_228]
0x1800075e7  mov     rcx, 0FFFFFFFF80000002h
0x1800075ee  call    pSetupOpenKey
0x1800075f3  test    eax, eax
0x1800075f5  jz      short loc_1800075FE
0x1800075f7  mov     qword ptr [rbx], 0
0x1800075fe  mov     eax, edi
0x180007600  mov     rcx, [rsp+268h+var_18]
0x180007608  xor     rcx, rsp; StackCookie
0x18000760b  call    __security_check_cookie
0x180007610  lea     r11, [rsp+268h+var_8]
0x180007618  mov     rbx, [r11+20h]
0x18000761c  mov     rsi, [r11+28h]
0x180007620  mov     rsp, r11
0x180007623  pop     rdi
0x180007624  retn
```
