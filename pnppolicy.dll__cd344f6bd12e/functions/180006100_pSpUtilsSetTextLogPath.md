# _pSpUtilsSetTextLogPath

- ea: `0x180006100`
- end: `0x1800061d2`
- name: `_pSpUtilsSetTextLogPath`
- size: `210`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800076d4`
- `0x1800077d0`

## callees

- `0x180006100`
- `0x1800079f0`
- `0x180007cd0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006162`
- `KERNEL32!HeapFree` at `0x18000619d`
- `KERNEL32!HeapFree` at `0x180006162`
- `KERNEL32!HeapFree` at `0x18000619d`

## pseudocode

```c
__int64 __fastcall pSpUtilsSetTextLogPath(STRSAFE_LPCWSTR pszSrc, int a2)
{
  bool v3; // zf
  const wchar_t *v4; // rsi
  const wchar_t *v5; // rdx

  v3 = a2 == 0;
  v4 = L"setupapi.dev.log";
  v5 = L"setupapi.app.log";
  if ( v3 )
    v4 = L"setupapi.offline.log";
  if ( !a2 )
    v5 = L"setupapi.offline.log";
  if ( (unsigned int)pSetupAppendPath(pszSrc, v5) )
  {
    if ( qword_1800116E0 )
      HeapFree(hHeap, 0, qword_1800116E0);
    qword_1800116E0 = 0;
  }
  if ( (unsigned int)pSetupAppendPath(pszSrc, v4) )
  {
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
    lpMem = 0;
  }
  TextLogOffline = a2 == 0;
  return 1;
}

```

## disassembly

```asm
0x180006100  push    rbx
0x180006102  push    rbp
0x180006103  push    rsi
0x180006104  push    rdi
0x180006105  sub     rsp, 28h
0x180006109  mov     edi, edx
0x18000610b  mov     [rsp+48h+arg_10], 0
0x180006114  lea     rax, aSetupapiOfflin; "setupapi.offline.log"
0x18000611b  xor     ebx, ebx
0x18000611d  test    edx, edx
0x18000611f  lea     rsi, aSetupapiDevLog; "setupapi.dev.log"
0x180006126  lea     rdx, aSetupapiAppLog; "setupapi.app.log"
0x18000612d  mov     rbp, rcx
0x180006130  cmovz   rsi, rax
0x180006134  lea     r8, [rsp+48h+arg_10]
0x180006139  test    edi, edi
0x18000613b  cmovz   rdx, rax; STRSAFE_LPCWSTR
0x18000613f  call    pSetupAppendPath
0x180006144  test    eax, eax
0x180006146  jz      short loc_18000616F
0x180006148  mov     r8, cs:qword_1800116E0; lpMem
0x18000614f  mov     rbx, [rsp+48h+arg_10]
0x180006154  test    r8, r8
0x180006157  jz      short loc_180006168
0x180006159  mov     rcx, cs:hHeap; hHeap
0x180006160  xor     edx, edx; dwFlags
0x180006162  call    cs:__imp_HeapFree
0x180006168  mov     cs:qword_1800116E0, rbx
0x18000616f  lea     r8, [rsp+48h+arg_10]
0x180006174  mov     rdx, rsi; STRSAFE_LPCWSTR
0x180006177  mov     rcx, rbp; pszSrc
0x18000617a  call    pSetupAppendPath
0x18000617f  test    eax, eax
0x180006181  jz      short loc_1800061AA
0x180006183  mov     r8, cs:lpMem; lpMem
0x18000618a  mov     rbx, [rsp+48h+arg_10]
0x18000618f  test    r8, r8
0x180006192  jz      short loc_1800061A3
0x180006194  mov     rcx, cs:hHeap; hHeap
0x18000619b  xor     edx, edx; dwFlags
0x18000619d  call    cs:__imp_HeapFree
0x1800061a3  mov     cs:lpMem, rbx
0x1800061aa  test    rbx, rbx
0x1800061ad  jz      short loc_1800061B7
0x1800061af  mov     rcx, rbx
0x1800061b2  call    pSetupMakeSurePathExists
0x1800061b7  xor     eax, eax
0x1800061b9  test    edi, edi
0x1800061bb  setz    al
0x1800061be  mov     cs:TextLogOffline, eax
0x1800061c4  mov     eax, 1
0x1800061c9  add     rsp, 28h
0x1800061cd  pop     rdi
0x1800061ce  pop     rsi
0x1800061cf  pop     rbp
0x1800061d0  pop     rbx
0x1800061d1  retn
```
