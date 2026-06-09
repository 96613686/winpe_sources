# pSpUtilsOpenSetupKey

- ea: `0x180020148`
- end: `0x180020221`
- name: `pSpUtilsOpenSetupKey`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020384`

## callees

- `0x18000be40`
- `0x180020148`
- `0x180020f3c`
- `0x180020fd8`

## pseudocode

```c
__int64 __fastcall pSpUtilsOpenSetupKey(HANDLE *a1, _QWORD *a2)
{
  unsigned int v4; // edi
  __int64 v6; // [rsp+34h] [rbp-234h] BYREF

  LODWORD(v6) = 520;
  v4 = pSetupOpenKeyEx(-2147483646, L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup", 1, a1);
  if ( !v4 && a2 )
  {
    pSetupQueryValue(*a1, L"SetupOverride", (__int64)&v6);
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180020148  mov     [rsp+arg_10], rbx
0x18002014d  mov     [rsp+arg_18], rsi
0x180020152  push    rdi
0x180020153  sub     rsp, 260h
0x18002015a  mov     rax, cs:__security_cookie
0x180020161  xor     rax, rsp
0x180020164  mov     [rsp+268h+var_18], rax
0x18002016c  mov     rbx, rdx
0x18002016f  mov     [rsp+268h+var_238], 0
0x180020177  mov     rsi, rcx
0x18002017a  mov     dword ptr [rsp+268h+var_234], 208h
0x180020182  mov     r9, rcx
0x180020185  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002018c  mov     rcx, 0FFFFFFFF80000002h
0x180020193  mov     r8d, 1
0x180020199  call    pSetupOpenKeyEx
0x18002019e  mov     edi, eax
0x1800201a0  test    eax, eax
0x1800201a2  jnz     short loc_1800201FA
0x1800201a4  test    rbx, rbx
0x1800201a7  jz      short loc_1800201FA
0x1800201a9  mov     rcx, [rsi]; KeyHandle
0x1800201ac  lea     rax, [rsp+268h+var_234]
0x1800201b1  lea     r9, [rsp+268h+var_228]
0x1800201b6  mov     [rsp+268h+var_248], rax; __int64
0x1800201bb  lea     r8, [rsp+268h+var_238]
0x1800201c0  lea     rdx, SourceString; "SetupOverride"
0x1800201c7  call    pSetupQueryValue
0x1800201cc  test    eax, eax
0x1800201ce  jnz     short loc_1800201F3
0x1800201d0  cmp     [rsp+268h+var_238], 1
0x1800201d5  jnz     short loc_1800201F3
0x1800201d7  mov     r9, rbx
0x1800201da  lea     r8d, [rdi+1]
0x1800201de  lea     rdx, [rsp+268h+var_228]
0x1800201e3  mov     rcx, 0FFFFFFFF80000002h
0x1800201ea  call    pSetupOpenKeyEx
0x1800201ef  test    eax, eax
0x1800201f1  jz      short loc_1800201FA
0x1800201f3  mov     qword ptr [rbx], 0
0x1800201fa  mov     eax, edi
0x1800201fc  mov     rcx, [rsp+268h+var_18]
0x180020204  xor     rcx, rsp; StackCookie
0x180020207  call    __security_check_cookie
0x18002020c  lea     r11, [rsp+268h+var_8]
0x180020214  mov     rbx, [r11+20h]
0x180020218  mov     rsi, [r11+28h]
0x18002021c  mov     rsp, r11
0x18002021f  pop     rdi
0x180020220  retn
```
