# DoLaunchWizard(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006ac0`
- end: `0x180006b82`
- name: `?DoLaunchWizard@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180006ac0`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x180006b42`
- `SHELL32!ShellExecuteW` at `0x180006b42`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180006b10`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180006b10`

## string_xrefs

- `0x180006b07`: `%windir%\system32\BitLockerWizard.exe`

## pseudocode

```c
__int64 __fastcall DoLaunchWizard(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  LONG v4; // ebx
  __int64 result; // rax
  WCHAR File[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(File, 0, 0x208u);
  v4 = ExpandEnvStringForUser(0, L"%windir%\\system32\\BitLockerWizard.exe", File, 260);
  if ( v4 >= 0 && (unsigned int)ShellExecuteW(0, L"open", File, a1->rgvarg->bstrVal, 0, 1) <= 0x20 )
    v4 = -2147467259;
  a2->vt = 19;
  result = 0;
  a2->lVal = v4;
  return result;
}

```

## disassembly

```asm
0x180006ac0  mov     [rsp+arg_10], rbx
0x180006ac5  mov     [rsp+arg_18], rsi
0x180006aca  push    rdi
0x180006acb  sub     rsp, 250h
0x180006ad2  mov     rax, cs:__security_cookie
0x180006ad9  xor     rax, rsp
0x180006adc  mov     [rsp+258h+var_18], rax
0x180006ae4  mov     rdi, rdx
0x180006ae7  mov     rsi, rcx
0x180006aea  xor     edx, edx; Val
0x180006aec  lea     rcx, [rsp+258h+File]; void *
0x180006af1  mov     r8d, 208h; Size
0x180006af7  call    memset_0
0x180006afc  mov     r9d, 104h
0x180006b02  lea     r8, [rsp+258h+File]
0x180006b07  lea     rdx, aWindirSystem32; "%windir%\\system32\\BitLockerWizard.exe"
0x180006b0e  xor     ecx, ecx
0x180006b10  call    cs:__imp_ExpandEnvStringForUser
0x180006b16  mov     ebx, eax
0x180006b18  test    eax, eax
0x180006b1a  js      short loc_180006B53
0x180006b1c  mov     r9, [rsi]
0x180006b1f  lea     r8, [rsp+258h+File]; lpFile
0x180006b24  mov     [rsp+258h+nShowCmd], 1; nShowCmd
0x180006b2c  lea     rdx, Operation; "open"
0x180006b33  xor     ecx, ecx; hwnd
0x180006b35  mov     [rsp+258h+lpDirectory], 0; lpDirectory
0x180006b3e  mov     r9, [r9+8]; lpParameters
0x180006b42  call    cs:__imp_ShellExecuteW
0x180006b48  cmp     eax, 20h ; ' '
0x180006b4b  mov     ecx, 80004005h
0x180006b50  cmovbe  ebx, ecx
0x180006b53  mov     word ptr [rdi], 13h
0x180006b58  xor     eax, eax
0x180006b5a  mov     [rdi+8], ebx
0x180006b5d  mov     rcx, [rsp+258h+var_18]
0x180006b65  xor     rcx, rsp; StackCookie
0x180006b68  call    __security_check_cookie
0x180006b6d  lea     r11, [rsp+258h+var_8]
0x180006b75  mov     rbx, [r11+20h]
0x180006b79  mov     rsi, [r11+28h]
0x180006b7d  mov     rsp, r11
0x180006b80  pop     rdi
0x180006b81  retn
```
