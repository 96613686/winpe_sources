# SQLRemoveTranslator

- ea: `0x18000fb70`
- end: `0x18000fbc0`
- name: `SQLRemoveTranslator`
- size: `80`
- prototype: `BOOL __stdcall(LPCSTR lpszTranslator, LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x180009cf0`
- `0x18000fb70`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLRemoveTranslator(LPCSTR lpszTranslator, LPDWORD lpdwUsageCount)
{
  BOOL v3; // ebx
  LPCWSTR lpszTranslatora; // [rsp+40h] [rbp+18h] BYREF

  lpszTranslatora = 0;
  v3 = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszTranslator, (WCHAR **)&lpszTranslatora, 0xFFFFFFFD) )
    v3 = SQLRemoveTranslatorW(lpszTranslatora, lpdwUsageCount);
  OFree((void *)lpszTranslatora);
  return v3;
}

```

## disassembly

```asm
0x18000fb70  mov     [rsp+arg_0], rbx
0x18000fb75  push    rdi
0x18000fb76  sub     rsp, 20h
0x18000fb7a  mov     rdi, rdx
0x18000fb7d  mov     [rsp+28h+lpszTranslator], 0
0x18000fb86  xor     ebx, ebx
0x18000fb88  lea     rdx, [rsp+28h+lpszTranslator]
0x18000fb8d  lea     r8d, [rbx-3]
0x18000fb91  call    GWConvertToUnicode
0x18000fb96  test    eax, eax
0x18000fb98  jz      short loc_18000FBA9
0x18000fb9a  mov     rcx, [rsp+28h+lpszTranslator]; lpszTranslator
0x18000fb9f  mov     rdx, rdi; lpdwUsageCount
0x18000fba2  call    SQLRemoveTranslatorW
0x18000fba7  mov     ebx, eax
0x18000fba9  mov     rcx, [rsp+28h+lpszTranslator]
0x18000fbae  call    OFree
0x18000fbb3  mov     eax, ebx
0x18000fbb5  mov     rbx, [rsp+28h+arg_0]
0x18000fbba  add     rsp, 20h
0x18000fbbe  pop     rdi
0x18000fbbf  retn
```
