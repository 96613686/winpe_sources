# SQLPostInstallerError

- ea: `0x18000f8c0`
- end: `0x18000f924`
- name: `SQLPostInstallerError`
- size: `100`
- prototype: `SQLRETURN __stdcall(DWORD dwErrorCode, LPCSTR lpszErrMsg)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180004db0`
- `0x18000f8c0`
- `0x1800138e4`

## pseudocode

```c
SQLRETURN __stdcall SQLPostInstallerError(DWORD dwErrorCode, LPCSTR lpszErrMsg)
{
  WCHAR *v2; // rbx
  SQLRETURN v4; // di
  int v5; // eax
  WCHAR *v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v7 = 0;
  if ( !lpszErrMsg || (v4 = -1, v5 = GWConvertToUnicode(lpszErrMsg, &v7, 0xFFFFFFFD), v2 = v7, v5) )
    v4 = SQLPostInstallerErrorW(dwErrorCode, v2);
  OFree(v2);
  return v4;
}

```

## disassembly

```asm
0x18000f8c0  mov     r11, rsp
0x18000f8c3  mov     [r11+8], rbx
0x18000f8c7  mov     [r11+18h], rsi
0x18000f8cb  push    rdi
0x18000f8cc  sub     rsp, 20h
0x18000f8d0  xor     ebx, ebx
0x18000f8d2  mov     rax, rdx
0x18000f8d5  mov     [r11+10h], rbx
0x18000f8d9  mov     esi, ecx
0x18000f8db  test    rdx, rdx
0x18000f8de  jz      short loc_18000F8FC
0x18000f8e0  lea     r8d, [rbx-3]
0x18000f8e4  mov     rcx, rax; lpMultiByteStr
0x18000f8e7  lea     rdx, [r11+10h]
0x18000f8eb  or      edi, 0FFFFFFFFh
0x18000f8ee  call    GWConvertToUnicode
0x18000f8f3  mov     rbx, [rsp+28h+arg_8]
0x18000f8f8  test    eax, eax
0x18000f8fa  jz      short loc_18000F909
0x18000f8fc  mov     rdx, rbx; lpszErrorMsg
0x18000f8ff  mov     ecx, esi; dwErrorCode
0x18000f901  call    SQLPostInstallerErrorW
0x18000f906  movzx   edi, ax
0x18000f909  mov     rcx, rbx
0x18000f90c  call    OFree
0x18000f911  mov     rbx, [rsp+28h+arg_0]
0x18000f916  movzx   eax, di
0x18000f919  mov     rsi, [rsp+28h+arg_10]
0x18000f91e  add     rsp, 20h
0x18000f922  pop     rdi
0x18000f923  retn
```
