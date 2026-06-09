# SQLWriteDSNToIni

- ea: `0x18000fc40`
- end: `0x18000fcc7`
- name: `SQLWriteDSNToIni`
- size: `135`
- prototype: `BOOL __stdcall(LPCSTR lpszDSN, LPCSTR lpszDriver)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x18000a100`
- `0x18000fc40`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLWriteDSNToIni(LPCSTR lpszDSN, LPCSTR lpszDriver)
{
  WCHAR *v2; // rbx
  BOOL v4; // edi
  int v5; // eax
  LPCWSTR lpszDSNa; // [rsp+40h] [rbp+18h] BYREF
  LPCWSTR lpszDrivera; // [rsp+48h] [rbp+20h] BYREF

  lpszDrivera = 0;
  v2 = 0;
  lpszDSNa = 0;
  v4 = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszDriver, (WCHAR **)&lpszDrivera, 0xFFFFFFFD) )
  {
    v5 = GWConvertToUnicode(lpszDSN, (WCHAR **)&lpszDSNa, 0xFFFFFFFD);
    v2 = (WCHAR *)lpszDSNa;
    if ( v5 )
      v4 = SQLWriteDSNToIniW(lpszDSNa, lpszDrivera);
  }
  OFree((void *)lpszDrivera);
  OFree(v2);
  return v4;
}

```

## disassembly

```asm
0x18000fc40  mov     r11, rsp
0x18000fc43  mov     [r11+8], rbx
0x18000fc47  mov     [r11+10h], rsi
0x18000fc4b  push    rdi
0x18000fc4c  sub     rsp, 20h
0x18000fc50  mov     rax, rdx
0x18000fc53  mov     qword ptr [r11+20h], 0
0x18000fc5b  xor     ebx, ebx
0x18000fc5d  lea     rdx, [r11+20h]
0x18000fc61  mov     rsi, rcx
0x18000fc64  mov     [r11+18h], rbx
0x18000fc68  mov     rcx, rax; lpMultiByteStr
0x18000fc6b  xor     edi, edi
0x18000fc6d  lea     r8d, [rbx-3]
0x18000fc71  call    GWConvertToUnicode
0x18000fc76  test    eax, eax
0x18000fc78  jz      short loc_18000FCA3
0x18000fc7a  lea     r8d, [rbx-3]
0x18000fc7e  mov     rcx, rsi; lpMultiByteStr
0x18000fc81  lea     rdx, [rsp+28h+lpszDSN]
0x18000fc86  call    GWConvertToUnicode
0x18000fc8b  mov     rbx, [rsp+28h+lpszDSN]
0x18000fc90  test    eax, eax
0x18000fc92  jz      short loc_18000FCA3
0x18000fc94  mov     rdx, [rsp+28h+lpszDriver]; lpszDriver
0x18000fc99  mov     rcx, rbx; lpszDSN
0x18000fc9c  call    SQLWriteDSNToIniW
0x18000fca1  mov     edi, eax
0x18000fca3  mov     rcx, [rsp+28h+lpszDriver]
0x18000fca8  call    OFree
0x18000fcad  mov     rcx, rbx
0x18000fcb0  call    OFree
0x18000fcb5  mov     rbx, [rsp+28h+arg_0]
0x18000fcba  mov     eax, edi
0x18000fcbc  mov     rsi, [rsp+28h+arg_8]
0x18000fcc1  add     rsp, 20h
0x18000fcc5  pop     rdi
0x18000fcc6  retn
```
