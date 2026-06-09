# SQLRemoveDSNFromIni

- ea: `0x18000fab0`
- end: `0x18000faf1`
- name: `SQLRemoveDSNFromIni`
- size: `65`
- prototype: `BOOL __stdcall(LPCSTR lpszDSN)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x180009960`
- `0x18000fab0`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLRemoveDSNFromIni(LPCSTR lpszDSN)
{
  BOOL v1; // ebx
  LPCWSTR lpszDSNa; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  lpszDSNa = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszDSN, (WCHAR **)&lpszDSNa, 0xFFFFFFFD) )
    v1 = SQLRemoveDSNFromIniW(lpszDSNa);
  OFree((void *)lpszDSNa);
  return v1;
}

```

## disassembly

```asm
0x18000fab0  push    rbx
0x18000fab2  sub     rsp, 20h
0x18000fab6  xor     ebx, ebx
0x18000fab8  mov     [rsp+28h+lpszDSN], 0
0x18000fac1  lea     rdx, [rsp+28h+lpszDSN]
0x18000fac6  lea     r8d, [rbx-3]
0x18000faca  call    GWConvertToUnicode
0x18000facf  test    eax, eax
0x18000fad1  jz      short loc_18000FADF
0x18000fad3  mov     rcx, [rsp+28h+lpszDSN]; lpszDSN
0x18000fad8  call    SQLRemoveDSNFromIniW
0x18000fadd  mov     ebx, eax
0x18000fadf  mov     rcx, [rsp+28h+lpszDSN]
0x18000fae4  call    OFree
0x18000fae9  mov     eax, ebx
0x18000faeb  add     rsp, 20h
0x18000faef  pop     rbx
0x18000faf0  retn
```
