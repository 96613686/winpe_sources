# SchemeCacheCryptBlobArray

- ea: `0x180001808`
- end: `0x180001871`
- name: `SchemeCacheCryptBlobArray`
- size: `105`
- prototype: `__int64 __fastcall(int, __int64, int, int, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003ef0`
- `0x1800196e0`
- `0x18001a250`

## callees

- `0x1800013fc`
- `0x180001808`
- `0x180001878`
- `0x1800063b0`
- `0x18000a990`

## string_xrefs

- `0x180001861`: `WriteToCache`

## pseudocode

```c
__int64 __fastcall SchemeCacheCryptBlobArray(int a1, __int64 a2, int a3, int a4, __int64 a5)
{
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  unsigned __int16 *v9; // rdi
  unsigned int v10; // ebx

  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v9 = CryptnetUrlCacheDir;
  if ( CryptnetUrlCacheDir && (unsigned int)I_UrlCacheWriteCryptBlobArray((_DWORD)CryptnetUrlCacheDir, a1, a3, a4, a5) )
  {
    v10 = 1;
  }
  else
  {
    CryptDiagAddActionWithLastError(L"WriteToCache");
    v10 = 0;
  }
  operator delete(v9);
  return v10;
}

```

## disassembly

```asm
0x180001808  push    rbx
0x18000180a  push    rbp
0x18000180b  push    rsi
0x18000180c  push    rdi
0x18000180d  sub     rsp, 38h
0x180001811  mov     rbx, r9
0x180001814  mov     rsi, r8
0x180001817  mov     rbp, rcx
0x18000181a  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x18000181f  mov     rdi, rax
0x180001822  test    rax, rax
0x180001825  jz      short loc_180001861
0x180001827  mov     rdx, [rsp+58h+arg_20]
0x18000182f  mov     r9, rbx
0x180001832  mov     [rsp+58h+var_38], rdx
0x180001837  mov     r8, rsi
0x18000183a  mov     rdx, rbp
0x18000183d  mov     rcx, rax
0x180001840  call    I_UrlCacheWriteCryptBlobArray
0x180001845  test    eax, eax
0x180001847  jz      short loc_180001861
0x180001849  mov     ebx, 1
0x18000184e  mov     rcx, rdi; hMem
0x180001851  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001856  mov     eax, ebx
0x180001858  add     rsp, 38h
0x18000185c  pop     rdi
0x18000185d  pop     rsi
0x18000185e  pop     rbp
0x18000185f  pop     rbx
0x180001860  retn
0x180001861  lea     rcx, aWritetocache; "WriteToCache"
0x180001868  call    CryptDiagAddActionWithLastError
0x18000186d  xor     ebx, ebx
0x18000186f  jmp     short loc_18000184E
```
