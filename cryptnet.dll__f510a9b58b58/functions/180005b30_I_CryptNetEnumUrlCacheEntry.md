# I_CryptNetEnumUrlCacheEntry

- ea: `0x180005b30`
- end: `0x180005bbd`
- name: `I_CryptNetEnumUrlCacheEntry`
- size: `141`
- prototype: `__int64 __fastcall(char, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001798`
- `0x1800052d0`
- `0x180005b30`
- `0x1800063b0`
- `0x18000a990`

## pseudocode

```c
__int64 __fastcall I_CryptNetEnumUrlCacheEntry(char a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 *CryptnetFlushCacheDir; // rax
  unsigned __int16 *v8; // rbx
  unsigned int v9; // edi
  void *v11; // rdx
  unsigned __int16 *v12; // rcx

  if ( a2 )
  {
    if ( *(_DWORD *)a2 > 8u )
    {
      v12 = *(unsigned __int16 **)(a2 + 8);
      if ( v12 )
      {
        v8 = 0;
        v11 = 0;
        goto LABEL_12;
      }
    }
  }
  if ( (a1 & 4) != 0 )
    CryptnetFlushCacheDir = I_SchemeGetCryptnetFlushCacheDir();
  else
    CryptnetFlushCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  v8 = CryptnetFlushCacheDir;
  if ( CryptnetFlushCacheDir )
  {
    v11 = 0;
    v12 = CryptnetFlushCacheDir;
    if ( !a2 )
    {
LABEL_8:
      v9 = I_UrlCacheEnum(v12, v11, a4);
      goto LABEL_6;
    }
LABEL_12:
    if ( *(_DWORD *)a2 > 0x10u && *(_QWORD *)(a2 + 16) )
      v11 = *(void **)(a2 + 16);
    goto LABEL_8;
  }
  v9 = 0;
LABEL_6:
  operator delete(v8);
  return v9;
}

```

## disassembly

```asm
0x180005b30  push    rbx
0x180005b32  push    rbp
0x180005b33  push    rsi
0x180005b34  push    rdi
0x180005b35  push    r14
0x180005b37  sub     rsp, 30h
0x180005b3b  mov     rbp, r9
0x180005b3e  mov     r14, r8
0x180005b41  mov     rdi, rdx
0x180005b44  mov     esi, ecx
0x180005b46  test    rdx, rdx
0x180005b49  jnz     short loc_180005B93
0x180005b4b  test    sil, 4
0x180005b4f  jnz     short loc_180005BB6
0x180005b51  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x180005b56  mov     rbx, rax
0x180005b59  test    rax, rax
0x180005b5c  jnz     short loc_180005B75
0x180005b5e  xor     edi, edi
0x180005b60  mov     rcx, rbx; hMem
0x180005b63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005b68  mov     eax, edi
0x180005b6a  add     rsp, 30h
0x180005b6e  pop     r14
0x180005b70  pop     rdi
0x180005b71  pop     rsi
0x180005b72  pop     rbp
0x180005b73  pop     rbx
0x180005b74  retn
0x180005b75  xor     edx, edx; void *
0x180005b77  mov     rcx, rbx; Src
0x180005b7a  test    rdi, rdi
0x180005b7d  jnz     short loc_180005BA5
0x180005b7f  mov     r9, r14
0x180005b82  mov     [rsp+58h+var_38], rbp; __int64
0x180005b87  mov     r8d, esi
0x180005b8a  call    I_UrlCacheEnum
0x180005b8f  mov     edi, eax
0x180005b91  jmp     short loc_180005B60
0x180005b93  cmp     dword ptr [rdx], 8
0x180005b96  jbe     short loc_180005B4B
0x180005b98  mov     rcx, [rdx+8]
0x180005b9c  test    rcx, rcx
0x180005b9f  jz      short loc_180005B4B
0x180005ba1  xor     ebx, ebx
0x180005ba3  xor     edx, edx
0x180005ba5  cmp     dword ptr [rdi], 10h
0x180005ba8  jbe     short loc_180005B7F
0x180005baa  cmp     qword ptr [rdi+10h], 0
0x180005baf  cmovnz  rdx, [rdi+10h]
0x180005bb4  jmp     short loc_180005B7F
0x180005bb6  call    ?I_SchemeGetCryptnetFlushCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetFlushCacheDir(void)
0x180005bbb  jmp     short loc_180005B56
```
