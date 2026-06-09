# CFontFolderEnum::ParseName(ushort const *,_ITEMIDLIST * *)

- ea: `0x180012f00`
- end: `0x18001301a`
- name: `?ParseName@CFontFolderEnum@@QEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `282`
- prototype: `int(CFontFolderEnum *__hidden this, const unsigned __int16 *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017a70`

## callees

- `0x180012f00`
- `0x180013108`
- `0x180022cb8`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012fd5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012fd5`

## pseudocode

```c
__int64 __fastcall CFontFolderEnum::ParseName(
        CFontFolderEnum *this,
        const unsigned __int16 *a2,
        const struct _ITEMIDLIST **a3)
{
  int v6; // ebx
  int v7; // esi
  int v8; // r15d
  const struct _ITEMIDLIST *v9; // r14
  WCHAR String1[264]; // [rsp+50h] [rbp-258h] BYREF

  v6 = -2147024809;
  if ( a3 )
  {
    *a3 = 0;
    v6 = CFontFolderEnum::_CheckAndInitEnumerator(this);
    if ( v6 >= 0 )
    {
      v7 = 0;
      v8 = ***((_DWORD ***)this + 12);
      while ( v7 < v8 )
      {
        v9 = *(const struct _ITEMIDLIST **)(*(_QWORD *)(**((_QWORD **)this + 12) + 8LL) + 8LL * v7);
        memset_0(String1, 0, 0x208u);
        if ( (int)FID_ParsingName(v9, String1, 0x104u) >= 0
          && CompareStringEx(0, 0x10u, String1, -1, a2, -1, 0, 0, 0) == 2 )
        {
          *a3 = v9;
          break;
        }
        ++v7;
      }
    }
  }
  if ( !*a3 )
    return (unsigned int)-2147467259;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012f00  push    rbx
0x180012f02  push    rbp
0x180012f03  push    rsi
0x180012f04  push    rdi
0x180012f05  push    r12
0x180012f07  push    r14
0x180012f09  push    r15
0x180012f0b  sub     rsp, 270h
0x180012f12  mov     rax, cs:__security_cookie
0x180012f19  xor     rax, rsp
0x180012f1c  mov     [rsp+2A8h+var_48], rax
0x180012f24  mov     rdi, r8
0x180012f27  mov     r12, rdx
0x180012f2a  mov     rbp, rcx
0x180012f2d  mov     ebx, 80070057h
0x180012f32  test    r8, r8
0x180012f35  jz      loc_180012FEA
0x180012f3b  mov     qword ptr [r8], 0
0x180012f42  call    ?_CheckAndInitEnumerator@CFontFolderEnum@@AEAAJXZ; CFontFolderEnum::_CheckAndInitEnumerator(void)
0x180012f47  mov     ebx, eax
0x180012f49  test    eax, eax
0x180012f4b  js      loc_180012FEA
0x180012f51  mov     rax, [rbp+60h]
0x180012f55  xor     esi, esi
0x180012f57  mov     rcx, [rax]
0x180012f5a  mov     r15d, [rcx]
0x180012f5d  cmp     esi, r15d
0x180012f60  jge     loc_180012FEA
0x180012f66  mov     rax, [rbp+60h]
0x180012f6a  xor     edx, edx; Val
0x180012f6c  movsxd  rcx, esi
0x180012f6f  mov     r8d, 208h; Size
0x180012f75  mov     rax, [rax]
0x180012f78  mov     rax, [rax+8]
0x180012f7c  mov     r14, [rax+rcx*8]
0x180012f80  lea     rcx, [rsp+2A8h+String1]; void *
0x180012f85  call    memset_0
0x180012f8a  mov     r8d, 104h; unsigned int
0x180012f90  lea     rdx, [rsp+2A8h+String1]; unsigned __int16 *
0x180012f95  mov     rcx, r14; struct _ITEMIDLIST *
0x180012f98  call    ?FID_ParsingName@@YAJPEFBU_ITEMIDLIST@@PEAGI@Z; FID_ParsingName(_ITEMIDLIST const *,ushort *,uint)
0x180012f9d  test    eax, eax
0x180012f9f  js      short loc_180012FE0
0x180012fa1  or      eax, 0FFFFFFFFh
0x180012fa4  mov     [rsp+2A8h+lParam], 0; lParam
0x180012fad  mov     [rsp+2A8h+lpReserved], 0; lpReserved
0x180012fb6  lea     r8, [rsp+2A8h+String1]; lpString1
0x180012fbb  mov     [rsp+2A8h+lpVersionInformation], 0; lpVersionInformation
0x180012fc4  mov     r9d, eax; cchCount1
0x180012fc7  mov     [rsp+2A8h+cchCount2], eax; cchCount2
0x180012fcb  xor     ecx, ecx; lpLocaleName
0x180012fcd  lea     edx, [rax+11h]; dwCmpFlags
0x180012fd0  mov     [rsp+2A8h+lpString2], r12; lpString2
0x180012fd5  call    cs:__imp_CompareStringEx
0x180012fdb  cmp     eax, 2
0x180012fde  jz      short loc_180012FE7
0x180012fe0  inc     esi
0x180012fe2  jmp     loc_180012F5D
0x180012fe7  mov     [rdi], r14
0x180012fea  cmp     qword ptr [rdi], 0
0x180012fee  mov     eax, 80004005h
0x180012ff3  cmovz   ebx, eax
0x180012ff6  mov     eax, ebx
0x180012ff8  mov     rcx, [rsp+2A8h+var_48]
0x180013000  xor     rcx, rsp; StackCookie
0x180013003  call    __security_check_cookie
0x180013008  add     rsp, 270h
0x18001300f  pop     r15
0x180013011  pop     r14
0x180013013  pop     r12
0x180013015  pop     rdi
0x180013016  pop     rsi
0x180013017  pop     rbp
0x180013018  pop     rbx
0x180013019  retn
```
