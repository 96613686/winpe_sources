# bCheckBitmapInfo

- ea: `0x180091c60`
- end: `0x180091d80`
- name: `bCheckBitmapInfo`
- size: `288`
- prototype: `__int64 __fastcall(struct tagHANDLETABLE *, MR *this, unsigned int, unsigned int, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001eb5c`
- `0x180020730`
- `0x180091280`

## callees

- `0x18001e098`
- `0x18001e0d8`
- `0x18001f070`
- `0x18007ac50`
- `0x180091c60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091d33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091d5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091d33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091d5b`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180091d23`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180091d23`

## pseudocode

```c
__int64 __fastcall bCheckBitmapInfo(
        struct tagHANDLETABLE *a1,
        MR *this,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  HLOCAL v11; // rcx
  HLOCAL v12; // rbx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  char v14; // [rsp+38h] [rbp-30h]
  int v15; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+44h] [rbp-24h]

  hMem = 0;
  v14 = 0;
  if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, this) )
    return 0;
  if ( !(unsigned int)bCheckBitmapInfoHeader(this, a3, a4, a5, &hMem) )
  {
    v11 = hMem;
    if ( !hMem || !v14 )
      return 0;
    goto LABEL_15;
  }
  v12 = hMem;
  if ( *(_DWORD *)hMem == 124 && *((_DWORD *)hMem + 14) == 1296188740 )
  {
    if ( a3 + *((_DWORD *)hMem + 28) < a3 )
    {
LABEL_13:
      if ( !v14 )
        return 0;
      v11 = v12;
LABEL_15:
      LocalFree(v11);
      return 0;
    }
    if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, this) )
    {
      if ( !*((_DWORD *)v12 + 28) )
      {
        v15 = 60430534;
        v16 = 2;
        RtlLogUnexpectedCodepath(&v15);
      }
      goto LABEL_13;
    }
  }
  BitmapInfoPtr::operator=(a6, &hMem);
  if ( hMem && v14 )
    LocalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x180091c60  push    rbp
0x180091c62  push    rbx
0x180091c63  push    rsi
0x180091c64  push    rdi
0x180091c65  push    r14
0x180091c67  push    r15
0x180091c69  mov     rbp, rsp
0x180091c6c  sub     rsp, 68h
0x180091c70  mov     rax, cs:__security_cookie
0x180091c77  xor     rax, rsp
0x180091c7a  mov     [rbp+var_18], rax
0x180091c7e  mov     ebx, r9d
0x180091c81  mov     edi, r8d
0x180091c84  mov     rsi, rdx
0x180091c87  mov     r15, rcx
0x180091c8a  mov     r14, [rbp+arg_28]
0x180091c8e  mov     [rbp+hMem], 0
0x180091c96  mov     [rbp+var_30], 0
0x180091c9a  call    IsValidEnhMetaRecordOffExt
0x180091c9f  test    eax, eax
0x180091ca1  jnz     short loc_180091CAA
0x180091ca3  xor     eax, eax
0x180091ca5  jmp     loc_180091D67
0x180091caa  lea     rax, [rbp+hMem]
0x180091cae  mov     [rsp+68h+var_48], rax
0x180091cb3  mov     r9d, [rbp+arg_20]
0x180091cb7  mov     r8d, ebx
0x180091cba  mov     edx, edi
0x180091cbc  mov     rcx, rsi
0x180091cbf  call    bCheckBitmapInfoHeader
0x180091cc4  test    eax, eax
0x180091cc6  jnz     short loc_180091CD8
0x180091cc8  mov     rcx, [rbp+hMem]
0x180091ccc  test    rcx, rcx
0x180091ccf  jz      short loc_180091D3A
0x180091cd1  cmp     [rbp+var_30], al
0x180091cd4  jz      short loc_180091D3A
0x180091cd6  jmp     short loc_180091D33
0x180091cd8  mov     rbx, [rbp+hMem]
0x180091cdc  cmp     dword ptr [rbx], 7Ch ; '|'
0x180091cdf  jnz     short loc_180091D3F
0x180091ce1  cmp     dword ptr [rbx+38h], 4D424544h
0x180091ce8  jnz     short loc_180091D3F
0x180091cea  mov     r8d, [rbx+70h]
0x180091cee  add     r8d, edi
0x180091cf1  cmp     r8d, edi
0x180091cf4  jnb     short loc_180091CF8
0x180091cf6  jmp     short loc_180091D2A
0x180091cf8  mov     r9d, [rbx+74h]
0x180091cfc  mov     rdx, rsi; this
0x180091cff  mov     rcx, r15; struct tagHANDLETABLE *
0x180091d02  call    IsValidEnhMetaRecordOffExt
0x180091d07  test    eax, eax
0x180091d09  jnz     short loc_180091D3F
0x180091d0b  cmp     [rbx+70h], eax
0x180091d0e  jnz     short loc_180091D2A
0x180091d10  mov     [rbp+var_28], 39A18C6h
0x180091d17  mov     [rbp+var_24], 2
0x180091d1f  lea     rcx, [rbp+var_28]
0x180091d23  call    cs:__imp_RtlLogUnexpectedCodepath
0x180091d29  nop
0x180091d2a  cmp     [rbp+var_30], 0
0x180091d2e  jz      short loc_180091D3A
0x180091d30  mov     rcx, rbx; hMem
0x180091d33  call    cs:__imp_LocalFree
0x180091d39  nop
0x180091d3a  jmp     loc_180091CA3
0x180091d3f  lea     rdx, [rbp+hMem]
0x180091d43  mov     rcx, r14
0x180091d46  call    ??4BitmapInfoPtr@@QEAAAEAV0@AEAV0@@Z; BitmapInfoPtr::operator=(BitmapInfoPtr &)
0x180091d4b  nop
0x180091d4c  mov     rcx, [rbp+hMem]; hMem
0x180091d50  test    rcx, rcx
0x180091d53  jz      short loc_180091D62
0x180091d55  cmp     [rbp+var_30], 0
0x180091d59  jz      short loc_180091D62
0x180091d5b  call    cs:__imp_LocalFree
0x180091d61  nop
0x180091d62  mov     eax, 1
0x180091d67  mov     rcx, [rbp+var_18]
0x180091d6b  xor     rcx, rsp; StackCookie
0x180091d6e  call    __security_check_cookie
0x180091d73  add     rsp, 68h
0x180091d77  pop     r15
0x180091d79  pop     r14
0x180091d7b  pop     rdi
0x180091d7c  pop     rsi
0x180091d7d  pop     rbx
0x180091d7e  pop     rbp
0x180091d7f  retn
```
