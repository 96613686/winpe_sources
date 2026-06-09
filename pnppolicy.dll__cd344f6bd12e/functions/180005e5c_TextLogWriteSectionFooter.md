# TextLogWriteSectionFooter

- ea: `0x180005e5c`
- end: `0x180005fbb`
- name: `TextLogWriteSectionFooter`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800063bc`
- `0x180006590`

## callees

- `0x1800044e0`
- `0x180004d34`
- `0x18000512c`
- `0x180005b88`
- `0x180005bcc`
- `0x180005e5c`
- `0x18000a1a0`

## pseudocode

```c
__int64 __fastcall TextLogWriteSectionFooter(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 result; // rax
  HRESULT v9; // eax
  __int64 v10; // r9
  const char *v11; // r9
  char pszDest[128]; // [rsp+30h] [rbp-98h] BYREF

  result = TextLogVerifyInsertionPoint(a1, *(unsigned int *)(a2 + 12));
  if ( !(_DWORD)result )
    return result;
  TextLogDeleteString(a1, *(_DWORD *)(a2 + 12));
  TextLogInsertString(a1, *(unsigned int *)(a2 + 12), "\r\n");
  if ( !a4 )
  {
    v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit]");
    goto LABEL_16;
  }
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1641:
        v11 = "REBOOT_INITIATED";
        break;
      case 3010:
        v11 = "REBOOT_REQUIRED";
        break;
      case 3011:
        v11 = "RESTART_REQUIRED";
        break;
      case -536870386:
        v11 = "DI_DO_DEFAULT";
        break;
      default:
        v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: FAILURE(0x%08x)]", a5);
        goto LABEL_16;
    }
    v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: SUCCESS (%s)]", v11);
    goto LABEL_16;
  }
  v9 = StringCchPrintfA(pszDest, 0x80u, "[Exit status: SUCCESS]");
LABEL_16:
  if ( v9 >= 0 )
    TextLogWriteEntry(a1, *(_DWORD *)(a2 + 12), (__int64)pszDest, v10, 32);
  return TextLogWriteEntry(a1, *(_DWORD *)(a2 + 12), (__int64)"Section end", v10, 65568);
}

```

## disassembly

```asm
0x180005e5c  mov     [rsp+arg_10], rbx
0x180005e61  mov     [rsp+arg_18], rsi
0x180005e66  push    rdi
0x180005e67  sub     rsp, 0C0h
0x180005e6e  mov     rax, cs:__security_cookie
0x180005e75  xor     rax, rsp
0x180005e78  mov     [rsp+0C8h+var_18], rax
0x180005e80  mov     rdi, rdx
0x180005e83  mov     esi, r9d
0x180005e86  mov     edx, [rdx+0Ch]
0x180005e89  mov     rbx, rcx
0x180005e8c  call    TextLogVerifyInsertionPoint
0x180005e91  test    eax, eax
0x180005e93  jz      loc_180005F96
0x180005e99  mov     edx, [rdi+0Ch]
0x180005e9c  mov     rcx, rbx
0x180005e9f  call    TextLogDeleteString
0x180005ea4  mov     edx, [rdi+0Ch]
0x180005ea7  lea     r8, asc_18000D654; "\r\n"
0x180005eae  mov     rcx, rbx
0x180005eb1  call    TextLogInsertString
0x180005eb6  test    esi, esi
0x180005eb8  jz      loc_180005F4A
0x180005ebe  mov     r9d, [rsp+0C8h+arg_20]
0x180005ec6  test    r9d, r9d
0x180005ec9  jnz     short loc_180005ED4
0x180005ecb  lea     r8, aExitStatusSucc; "[Exit status: SUCCESS]"
0x180005ed2  jmp     short loc_180005F51
0x180005ed4  cmp     r9d, 669h
0x180005edb  jz      short loc_180005F2B
0x180005edd  cmp     r9d, 0BC2h
0x180005ee4  jz      short loc_180005F22
0x180005ee6  cmp     r9d, 0BC3h
0x180005eed  jz      short loc_180005F19
0x180005eef  cmp     r9d, 0E000020Eh
0x180005ef6  jnz     short loc_180005F01
0x180005ef8  lea     r9, aDiDoDefault; "DI_DO_DEFAULT"
0x180005eff  jmp     short loc_180005F32
0x180005f01  lea     r8, aExitStatusFail; "[Exit status: FAILURE(0x%08x)]"
0x180005f08  mov     edx, 80h; cchDest
0x180005f0d  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x180005f12  call    StringCchPrintfA
0x180005f17  jmp     short loc_180005F60
0x180005f19  lea     r9, aRestartRequire; "RESTART_REQUIRED"
0x180005f20  jmp     short loc_180005F32
0x180005f22  lea     r9, aRebootRequired; "REBOOT_REQUIRED"
0x180005f29  jmp     short loc_180005F32
0x180005f2b  lea     r9, aRebootInitiate; "REBOOT_INITIATED"
0x180005f32  lea     r8, aExitStatusSucc_0; "[Exit status: SUCCESS (%s)]"
0x180005f39  mov     edx, 80h; cchDest
0x180005f3e  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x180005f43  call    StringCchPrintfA
0x180005f48  jmp     short loc_180005F60
0x180005f4a  lea     r8, aExit; "[Exit]"
0x180005f51  mov     edx, 80h; cchDest
0x180005f56  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x180005f5b  call    StringCchPrintfA
0x180005f60  test    eax, eax
0x180005f62  js      short loc_180005F7C
0x180005f64  mov     edx, [rdi+0Ch]
0x180005f67  lea     r8, [rsp+0C8h+pszDest]
0x180005f6c  mov     rcx, rbx
0x180005f6f  mov     [rsp+0C8h+var_A8], 20h ; ' '
0x180005f77  call    TextLogWriteEntry
0x180005f7c  mov     edx, [rdi+0Ch]
0x180005f7f  lea     r8, aSectionEnd; "Section end"
0x180005f86  mov     rcx, rbx
0x180005f89  mov     [rsp+0C8h+var_A8], 10020h
0x180005f91  call    TextLogWriteEntry
0x180005f96  mov     rcx, [rsp+0C8h+var_18]
0x180005f9e  xor     rcx, rsp; StackCookie
0x180005fa1  call    __security_check_cookie
0x180005fa6  lea     r11, [rsp+0C8h+var_8]
0x180005fae  mov     rbx, [r11+20h]
0x180005fb2  mov     rsi, [r11+28h]
0x180005fb6  mov     rsp, r11
0x180005fb9  pop     rdi
0x180005fba  retn
```
