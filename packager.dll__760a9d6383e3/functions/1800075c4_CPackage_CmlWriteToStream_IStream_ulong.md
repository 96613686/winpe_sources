# CPackage::CmlWriteToStream(IStream *,ulong *)

- ea: `0x1800075c4`
- end: `0x180007678`
- name: `?CmlWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z`
- size: `180`
- prototype: `__int64 __fastcall(CPackage *this, struct IStream *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a074`

## callees

- `0x1800075c4`
- `0x18000af50`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180007632`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180007632`

## pseudocode

```c
__int64 __fastcall CPackage::CmlWriteToStream(CPackage *this, struct IStream *a2, unsigned int *a3)
{
  __int16 *v3; // rax
  __int16 v8; // dx
  struct IStreamVtbl *lpVtbl; // rax
  int v10; // edx
  const WCHAR *v11; // rcx
  _WORD v13[2]; // [rsp+30h] [rbp-148h] BYREF
  unsigned int v14[3]; // [rsp+34h] [rbp-144h] BYREF
  CHAR pszDst[272]; // [rsp+40h] [rbp-138h] BYREF

  v3 = (__int16 *)*((_QWORD *)this + 15);
  v8 = *v3;
  lpVtbl = a2->lpVtbl;
  v13[0] = v8;
  v10 = ((__int64 (__fastcall *)(struct IStream *, _WORD *, __int64))lpVtbl->Write)(a2, v13, 2);
  if ( v10 >= 0 )
  {
    v11 = (const WCHAR *)(*((_QWORD *)this + 15) + 4LL);
    v14[0] = 2;
    SHUnicodeToAnsi(v11, pszDst, 260);
    v10 = StringWriteToStream(a2, pszDst, v14);
    if ( v10 >= 0 )
    {
      if ( a3 )
        *a3 = v14[0];
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800075c4  push    rbx
0x1800075c6  push    rsi
0x1800075c7  push    rdi
0x1800075c8  sub     rsp, 160h
0x1800075cf  mov     rax, cs:__security_cookie
0x1800075d6  xor     rax, rsp
0x1800075d9  mov     [rsp+178h+var_28], rax
0x1800075e1  mov     rax, [rcx+78h]
0x1800075e5  mov     rdi, rdx
0x1800075e8  xor     r9d, r9d
0x1800075eb  mov     rbx, r8
0x1800075ee  mov     rsi, rcx
0x1800075f1  mov     rcx, rdi
0x1800075f4  movzx   edx, word ptr [rax]
0x1800075f7  mov     rax, [rdi]
0x1800075fa  lea     r8d, [r9+2]
0x1800075fe  mov     [rsp+178h+var_148], dx
0x180007603  lea     rdx, [rsp+178h+var_148]
0x180007608  mov     rax, [rax+20h]
0x18000760c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007611  mov     edx, eax
0x180007613  test    eax, eax
0x180007615  js      short loc_18000765B
0x180007617  mov     rcx, [rsi+78h]
0x18000761b  lea     rdx, [rsp+178h+pszDst]; pszDst
0x180007620  add     rcx, 4; pwszSrc
0x180007624  mov     [rsp+178h+var_144], 2
0x18000762c  mov     r8d, 104h; cchBuf
0x180007632  call    cs:__imp_SHUnicodeToAnsi
0x180007638  lea     r8, [rsp+178h+var_144]; unsigned int *
0x18000763d  mov     rcx, rdi; struct IStream *
0x180007640  lea     rdx, [rsp+178h+pszDst]; char *
0x180007645  call    ?StringWriteToStream@@YAJPEAUIStream@@PEBDPEAK@Z; StringWriteToStream(IStream *,char const *,ulong *)
0x18000764a  mov     edx, eax
0x18000764c  test    eax, eax
0x18000764e  js      short loc_18000765B
0x180007650  test    rbx, rbx
0x180007653  jz      short loc_18000765B
0x180007655  mov     eax, [rsp+178h+var_144]
0x180007659  mov     [rbx], eax
0x18000765b  mov     eax, edx
0x18000765d  mov     rcx, [rsp+178h+var_28]
0x180007665  xor     rcx, rsp; StackCookie
0x180007668  call    __security_check_cookie
0x18000766d  add     rsp, 160h
0x180007674  pop     rdi
0x180007675  pop     rsi
0x180007676  pop     rbx
0x180007677  retn
```
