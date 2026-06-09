# AddComboBoxAccesibilityInfo

- ea: `0x180085568`
- end: `0x180085639`
- name: `AddComboBoxAccesibilityInfo`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180086a8c`

## callees

- `0x180085568`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!__imp_SetAccessibilityName` at `0x1800855c8`
- `MSOERT2!__imp_SetAccessibilityName` at `0x180085612`
- `MSOERT2!__imp_SetAccessibilityName` at `0x1800855c8`
- `MSOERT2!__imp_SetAccessibilityName` at `0x180085612`
- `USER32!LoadStringW` at `0x1800855b6`
- `USER32!LoadStringW` at `0x1800855fd`
- `USER32!LoadStringW` at `0x1800855b6`
- `USER32!LoadStringW` at `0x1800855fd`

## pseudocode

```c
int __fastcall AddComboBoxAccesibilityInfo(__int64 a1, __int64 a2)
{
  int result; // eax
  WCHAR Buffer[512]; // [rsp+20h] [rbp-818h] BYREF
  WCHAR v6[512]; // [rsp+420h] [rbp-418h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  if ( LoadStringW(g_hLocRes, 0x497u, Buffer, 512) )
    SetAccessibilityName(a1, Buffer);
  memset_0(v6, 0, sizeof(v6));
  result = LoadStringW(g_hLocRes, 0x498u, v6, 512);
  if ( result )
    return SetAccessibilityName(a2, v6);
  return result;
}

```

## disassembly

```asm
0x180085568  mov     [rsp+arg_10], rbx
0x18008556d  push    rdi
0x18008556e  sub     rsp, 830h
0x180085575  mov     rax, cs:__security_cookie
0x18008557c  xor     rax, rsp
0x18008557f  mov     [rsp+838h+var_18], rax
0x180085587  mov     rbx, rdx
0x18008558a  mov     rdi, rcx
0x18008558d  xor     edx, edx; Val
0x18008558f  lea     rcx, [rsp+838h+Buffer]; void *
0x180085594  mov     r8d, 400h; Size
0x18008559a  call    memset_0
0x18008559f  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800855a6  lea     r8, [rsp+838h+Buffer]; lpBuffer
0x1800855ab  mov     r9d, 200h; cchBufferMax
0x1800855b1  mov     edx, 497h; uID
0x1800855b6  call    cs:__imp_LoadStringW
0x1800855bc  test    eax, eax
0x1800855be  jz      short loc_1800855CE
0x1800855c0  lea     rdx, [rsp+838h+Buffer]
0x1800855c5  mov     rcx, rdi
0x1800855c8  call    cs:__imp_SetAccessibilityName
0x1800855ce  xor     edx, edx; Val
0x1800855d0  lea     rcx, [rsp+838h+var_418]; void *
0x1800855d8  mov     r8d, 400h; Size
0x1800855de  call    memset_0
0x1800855e3  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800855ea  lea     r8, [rsp+838h+var_418]; lpBuffer
0x1800855f2  mov     r9d, 200h; cchBufferMax
0x1800855f8  mov     edx, 498h; uID
0x1800855fd  call    cs:__imp_LoadStringW
0x180085603  test    eax, eax
0x180085605  jz      short loc_180085618
0x180085607  lea     rdx, [rsp+838h+var_418]
0x18008560f  mov     rcx, rbx
0x180085612  call    cs:__imp_SetAccessibilityName
0x180085618  mov     rcx, [rsp+838h+var_18]
0x180085620  xor     rcx, rsp; StackCookie
0x180085623  call    __security_check_cookie
0x180085628  mov     rbx, [rsp+838h+arg_10]
0x180085630  add     rsp, 830h
0x180085637  pop     rdi
0x180085638  retn
```
