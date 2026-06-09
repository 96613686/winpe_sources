# bCheckBitmapInfo

- ea: `0x1800f6d38`
- end: `0x1800f6e70`
- name: `bCheckBitmapInfo`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800f6c30`

## callees

- `0x1800f6d38`
- `0x1800f6e78`
- `0x180105d40`
- `0x1801475e0`

## import_xrefs

- `ntdll!RtlLogUnexpectedCodepath` at `0x1800f6e31`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800f6e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6e5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6e5a`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800f6d72`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800f6e09`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800f6d72`
- `GDI32!IsValidEnhMetaRecordOffExt` at `0x1800f6e09`

## pseudocode

```c
__int64 __fastcall bCheckBitmapInfo(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  HLOCAL v10; // rcx
  HLOCAL v12; // rbx
  __int64 v13; // r8
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  char v15; // [rsp+38h] [rbp-30h]
  int v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17; // [rsp+44h] [rbp-24h]

  hMem = 0;
  v15 = 0;
  if ( !(unsigned int)((__int64 (*)(void))IsValidEnhMetaRecordOffExt)() )
    return 0;
  if ( !(unsigned int)bCheckBitmapInfoHeader(a2, a3, a4, a5, &hMem) )
  {
    v10 = hMem;
    if ( !hMem || !v15 )
      return 0;
    goto LABEL_11;
  }
  v12 = hMem;
  if ( *(_DWORD *)hMem == 124 && *((_DWORD *)hMem + 14) == 1296188740 )
  {
    v13 = a3 + *((_DWORD *)hMem + 28);
    if ( (unsigned int)v13 < a3 )
    {
LABEL_9:
      if ( !v15 )
        return 0;
      v10 = v12;
LABEL_11:
      LocalFree(v10);
      return 0;
    }
    if ( !(unsigned int)IsValidEnhMetaRecordOffExt(a1, a2, v13, *((unsigned int *)hMem + 29)) )
    {
      if ( !*((_DWORD *)v12 + 28) )
      {
        v16 = 60430534;
        v17 = 2;
        RtlLogUnexpectedCodepath(&v16);
      }
      goto LABEL_9;
    }
  }
  BitmapInfoPtr::operator=(a6, &hMem);
  if ( hMem && v15 )
    LocalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x1800f6d38  push    rbp
0x1800f6d3a  push    rbx
0x1800f6d3b  push    rsi
0x1800f6d3c  push    rdi
0x1800f6d3d  push    r14
0x1800f6d3f  push    r15
0x1800f6d41  mov     rbp, rsp
0x1800f6d44  sub     rsp, 68h
0x1800f6d48  mov     rax, cs:__security_cookie
0x1800f6d4f  xor     rax, rsp
0x1800f6d52  mov     [rbp+var_18], rax
0x1800f6d56  mov     r14, [rbp+arg_28]
0x1800f6d5a  mov     ebx, r9d
0x1800f6d5d  mov     edi, r8d
0x1800f6d60  mov     [rbp+hMem], 0
0x1800f6d68  mov     rsi, rdx
0x1800f6d6b  mov     [rbp+var_30], 0
0x1800f6d6f  mov     r15, rcx
0x1800f6d72  call    cs:__imp_IsValidEnhMetaRecordOffExt
0x1800f6d79  nop     dword ptr [rax+rax+00h]
0x1800f6d7e  test    eax, eax
0x1800f6d80  jz      short loc_1800F6DAE
0x1800f6d82  mov     r9d, [rbp+arg_20]
0x1800f6d86  lea     rax, [rbp+hMem]
0x1800f6d8a  mov     r8d, ebx
0x1800f6d8d  mov     [rsp+68h+var_48], rax
0x1800f6d92  mov     edx, edi
0x1800f6d94  mov     rcx, rsi
0x1800f6d97  call    bCheckBitmapInfoHeader
0x1800f6d9c  test    eax, eax
0x1800f6d9e  jnz     short loc_1800F6DCA
0x1800f6da0  mov     rcx, [rbp+hMem]
0x1800f6da4  test    rcx, rcx
0x1800f6da7  jz      short loc_1800F6DAE
0x1800f6da9  cmp     [rbp+var_30], al
0x1800f6dac  jnz     short loc_1800F6DF1
0x1800f6dae  xor     eax, eax
0x1800f6db0  mov     rcx, [rbp+var_18]
0x1800f6db4  xor     rcx, rsp; StackCookie
0x1800f6db7  call    __security_check_cookie
0x1800f6dbc  add     rsp, 68h
0x1800f6dc0  pop     r15
0x1800f6dc2  pop     r14
0x1800f6dc4  pop     rdi
0x1800f6dc5  pop     rsi
0x1800f6dc6  pop     rbx
0x1800f6dc7  pop     rbp
0x1800f6dc8  retn
0x1800f6dca  mov     rbx, [rbp+hMem]
0x1800f6dce  cmp     dword ptr [rbx], 7Ch ; '|'
0x1800f6dd1  jnz     short loc_1800F6E3F
0x1800f6dd3  cmp     dword ptr [rbx+38h], 4D424544h
0x1800f6dda  jnz     short loc_1800F6E3F
0x1800f6ddc  mov     r8d, [rbx+70h]
0x1800f6de0  add     r8d, edi
0x1800f6de3  cmp     r8d, edi
0x1800f6de6  jnb     short loc_1800F6DFF
0x1800f6de8  cmp     [rbp+var_30], 0
0x1800f6dec  jz      short loc_1800F6DAE
0x1800f6dee  mov     rcx, rbx; hMem
0x1800f6df1  call    cs:__imp_LocalFree
0x1800f6df8  nop     dword ptr [rax+rax+00h]
0x1800f6dfd  jmp     short loc_1800F6DAE
0x1800f6dff  mov     r9d, [rbx+74h]
0x1800f6e03  mov     rdx, rsi
0x1800f6e06  mov     rcx, r15
0x1800f6e09  call    cs:__imp_IsValidEnhMetaRecordOffExt
0x1800f6e10  nop     dword ptr [rax+rax+00h]
0x1800f6e15  test    eax, eax
0x1800f6e17  jnz     short loc_1800F6E3F
0x1800f6e19  cmp     [rbx+70h], eax
0x1800f6e1c  jnz     short loc_1800F6DE8
0x1800f6e1e  lea     rcx, [rbp+var_28]
0x1800f6e22  mov     [rbp+var_28], 39A18C6h
0x1800f6e29  mov     [rbp+var_24], 2
0x1800f6e31  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800f6e38  nop     dword ptr [rax+rax+00h]
0x1800f6e3d  jmp     short loc_1800F6DE8
0x1800f6e3f  lea     rdx, [rbp+hMem]
0x1800f6e43  mov     rcx, r14
0x1800f6e46  call    ??4BitmapInfoPtr@@QEAAAEAV0@AEAV0@@Z; BitmapInfoPtr::operator=(BitmapInfoPtr &)
0x1800f6e4b  mov     rcx, [rbp+hMem]; hMem
0x1800f6e4f  test    rcx, rcx
0x1800f6e52  jz      short loc_1800F6E66
0x1800f6e54  cmp     [rbp+var_30], 0
0x1800f6e58  jz      short loc_1800F6E66
0x1800f6e5a  call    cs:__imp_LocalFree
0x1800f6e61  nop     dword ptr [rax+rax+00h]
0x1800f6e66  mov     eax, 1
0x1800f6e6b  jmp     loc_1800F6DB0
```
