# _pSpUtilsSetTextLogPath

- ea: `0x180021124`
- end: `0x1800211f8`
- name: `_pSpUtilsSetTextLogPath`
- size: `212`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800202d0`
- `0x180020384`

## callees

- `0x180020878`
- `0x180020a14`
- `0x180021124`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002118e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002118e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211c9`

## pseudocode

```c
__int64 __fastcall pSpUtilsSetTextLogPath(STRSAFE_LPCWSTR pszSrc, int a2)
{
  const wchar_t *v4; // rdi
  void *v5; // rbx
  bool v6; // zf
  const wchar_t *v7; // rdx
  void *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  v4 = L"setupapi.dev.log";
  v5 = 0;
  v6 = a2 == 0;
  v7 = L"setupapi.app.log";
  if ( v6 )
    v4 = L"setupapi.offline.log";
  if ( !a2 )
    v7 = L"setupapi.offline.log";
  if ( (unsigned int)pSetupAppendPath(pszSrc, v7, (__int64 *)&v9) )
  {
    v5 = v9;
    if ( qword_180032AF0 )
      HeapFree(hHeap, 0, qword_180032AF0);
    qword_180032AF0 = v5;
  }
  if ( (unsigned int)pSetupAppendPath(pszSrc, v4, (__int64 *)&v9) )
  {
    v5 = v9;
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
    lpMem = v5;
  }
  if ( v5 )
    pSetupMakeSurePathExists((const WCHAR *)v5);
  return 1;
}

```

## disassembly

```asm
0x180021124  mov     r11, rsp
0x180021127  mov     [r11+8], rbx
0x18002112b  mov     [r11+10h], rsi
0x18002112f  push    rdi
0x180021130  sub     rsp, 20h
0x180021134  mov     eax, edx
0x180021136  mov     qword ptr [r11+18h], 0
0x18002113e  mov     rsi, rcx
0x180021141  lea     rdi, aSetupapiDevLog; "setupapi.dev.log"
0x180021148  lea     rcx, aSetupapiOfflin; "setupapi.offline.log"
0x18002114f  xor     ebx, ebx
0x180021151  test    edx, edx
0x180021153  lea     r8, [r11+18h]
0x180021157  lea     rdx, aSetupapiAppLog; "setupapi.app.log"
0x18002115e  cmovz   rdi, rcx
0x180021162  test    eax, eax
0x180021164  cmovz   rdx, rcx
0x180021168  mov     rcx, rsi; pszSrc
0x18002116b  call    pSetupAppendPath
0x180021170  test    eax, eax
0x180021172  jz      short loc_18002119B
0x180021174  mov     r8, cs:qword_180032AF0; lpMem
0x18002117b  mov     rbx, [rsp+28h+arg_10]
0x180021180  test    r8, r8
0x180021183  jz      short loc_180021194
0x180021185  mov     rcx, cs:hHeap; hHeap
0x18002118c  xor     edx, edx; dwFlags
0x18002118e  call    cs:__imp_HeapFree
0x180021194  mov     cs:qword_180032AF0, rbx
0x18002119b  lea     r8, [rsp+28h+arg_10]
0x1800211a0  mov     rdx, rdi
0x1800211a3  mov     rcx, rsi; pszSrc
0x1800211a6  call    pSetupAppendPath
0x1800211ab  test    eax, eax
0x1800211ad  jz      short loc_1800211D6
0x1800211af  mov     r8, cs:lpMem; lpMem
0x1800211b6  mov     rbx, [rsp+28h+arg_10]
0x1800211bb  test    r8, r8
0x1800211be  jz      short loc_1800211CF
0x1800211c0  mov     rcx, cs:hHeap; hHeap
0x1800211c7  xor     edx, edx; dwFlags
0x1800211c9  call    cs:__imp_HeapFree
0x1800211cf  mov     cs:lpMem, rbx
0x1800211d6  test    rbx, rbx
0x1800211d9  jz      short loc_1800211E3
0x1800211db  mov     rcx, rbx
0x1800211de  call    pSetupMakeSurePathExists
0x1800211e3  mov     rbx, [rsp+28h+arg_0]
0x1800211e8  mov     eax, 1
0x1800211ed  mov     rsi, [rsp+28h+arg_8]
0x1800211f2  add     rsp, 20h
0x1800211f6  pop     rdi
0x1800211f7  retn
```
