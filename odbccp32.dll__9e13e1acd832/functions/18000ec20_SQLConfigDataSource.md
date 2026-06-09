# SQLConfigDataSource

- ea: `0x18000ec20`
- end: `0x18000ecb4`
- name: `SQLConfigDataSource`
- size: `148`
- prototype: `BOOL __stdcall(HWND hwndParent, WORD fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002940`
- `0x180008570`
- `0x18000ec20`
- `0x18000fea8`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLConfigDataSource(HWND hwndParent, WORD fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes)
{
  WCHAR *v4; // rbx
  BOOL v8; // edi
  __int16 v9; // ax
  int v10; // eax
  LPCWSTR lpszAttributesa; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpszDrivera; // [rsp+28h] [rbp-30h] BYREF

  lpszDrivera = 0;
  v4 = 0;
  lpszAttributesa = 0;
  v8 = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszDriver, (WCHAR **)&lpszDrivera, 0xFFFFFFFD) )
  {
    v9 = dnlen(lpszAttributes);
    v10 = GWConvertToUnicode(lpszAttributes, (WCHAR **)&lpszAttributesa, v9);
    v4 = (WCHAR *)lpszAttributesa;
    if ( v10 )
      v8 = SQLConfigDataSourceW(hwndParent, fRequest, lpszDrivera, lpszAttributesa);
  }
  OFree((void *)lpszDrivera);
  OFree(v4);
  return v8;
}

```

## disassembly

```asm
0x18000ec20  push    rbx
0x18000ec22  push    rbp
0x18000ec23  push    rsi
0x18000ec24  push    rdi
0x18000ec25  push    r14
0x18000ec27  sub     rsp, 30h
0x18000ec2b  mov     rax, r8
0x18000ec2e  mov     [rsp+58h+lpszDriver], 0
0x18000ec37  xor     ebx, ebx
0x18000ec39  movzx   ebp, dx
0x18000ec3c  mov     r14, rcx
0x18000ec3f  mov     [rsp+58h+lpszAttributes], rbx
0x18000ec44  lea     rdx, [rsp+58h+lpszDriver]
0x18000ec49  mov     rcx, rax; lpMultiByteStr
0x18000ec4c  mov     rsi, r9
0x18000ec4f  xor     edi, edi
0x18000ec51  lea     r8d, [rbx-3]
0x18000ec55  call    GWConvertToUnicode
0x18000ec5a  test    eax, eax
0x18000ec5c  jz      short loc_18000EC95
0x18000ec5e  mov     rcx, rsi
0x18000ec61  call    dnlen
0x18000ec66  movsx   r8d, ax
0x18000ec6a  lea     rdx, [rsp+58h+lpszAttributes]
0x18000ec6f  mov     rcx, rsi; lpMultiByteStr
0x18000ec72  call    GWConvertToUnicode
0x18000ec77  mov     rbx, [rsp+58h+lpszAttributes]
0x18000ec7c  test    eax, eax
0x18000ec7e  jz      short loc_18000EC95
0x18000ec80  mov     r8, [rsp+58h+lpszDriver]; lpszDriver
0x18000ec85  mov     r9, rbx; lpszAttributes
0x18000ec88  movzx   edx, bp; fRequest
0x18000ec8b  mov     rcx, r14; hwndParent
0x18000ec8e  call    SQLConfigDataSourceW
0x18000ec93  mov     edi, eax
0x18000ec95  mov     rcx, [rsp+58h+lpszDriver]
0x18000ec9a  call    OFree
0x18000ec9f  mov     rcx, rbx
0x18000eca2  call    OFree
0x18000eca7  mov     eax, edi
0x18000eca9  add     rsp, 30h
0x18000ecad  pop     r14
0x18000ecaf  pop     rdi
0x18000ecb0  pop     rsi
0x18000ecb1  pop     rbp
0x18000ecb2  pop     rbx
0x18000ecb3  retn
```
