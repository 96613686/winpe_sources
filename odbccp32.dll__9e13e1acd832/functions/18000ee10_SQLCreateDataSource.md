# SQLCreateDataSource

- ea: `0x18000ee10`
- end: `0x18000ee61`
- name: `SQLCreateDataSource`
- size: `81`
- prototype: `BOOL __stdcall(HWND hwndParent, LPCSTR lpszDSN)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x180002d20`
- `0x18000ee10`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLCreateDataSource(HWND hwndParent, LPCSTR lpszDSN)
{
  BOOL v3; // ebx
  LPCWSTR lpszDSNa; // [rsp+40h] [rbp+18h] BYREF

  lpszDSNa = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszDSN, (WCHAR **)&lpszDSNa, 0xFFFFFFFD) )
    v3 = SQLCreateDataSourceW(hwndParent, lpszDSNa);
  else
    v3 = 0;
  OFree((void *)lpszDSNa);
  return v3;
}

```

## disassembly

```asm
0x18000ee10  push    rbx
0x18000ee12  sub     rsp, 20h
0x18000ee16  mov     rax, rdx
0x18000ee19  mov     [rsp+28h+lpszDSN], 0
0x18000ee22  mov     rbx, rcx
0x18000ee25  lea     rdx, [rsp+28h+lpszDSN]
0x18000ee2a  mov     rcx, rax; lpMultiByteStr
0x18000ee2d  mov     r8d, 0FFFFFFFDh
0x18000ee33  call    GWConvertToUnicode
0x18000ee38  test    eax, eax
0x18000ee3a  jnz     short loc_18000EE40
0x18000ee3c  xor     ebx, ebx
0x18000ee3e  jmp     short loc_18000EE4F
0x18000ee40  mov     rdx, [rsp+28h+lpszDSN]; lpszDSN
0x18000ee45  mov     rcx, rbx; hwndParent
0x18000ee48  call    SQLCreateDataSourceW
0x18000ee4d  mov     ebx, eax
0x18000ee4f  mov     rcx, [rsp+28h+lpszDSN]
0x18000ee54  call    OFree
0x18000ee59  mov     eax, ebx
0x18000ee5b  add     rsp, 20h
0x18000ee5f  pop     rbx
0x18000ee60  retn
```
