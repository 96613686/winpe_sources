# CPackage::IconWriteToStream(IStream *,ulong *)

- ea: `0x180008dcc`
- end: `0x180008eb9`
- name: `?IconWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z`
- size: `237`
- prototype: `__int64 __fastcall(CPackage *this, struct IStream *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a074`

## callees

- `0x180008dcc`
- `0x18000af50`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180008e08`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180008e3d`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180008e08`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180008e3d`

## pseudocode

```c
__int64 __fastcall CPackage::IconWriteToStream(CPackage *this, struct IStream *a2, unsigned int *a3)
{
  int v6; // ecx
  __int64 v7; // rax
  __int16 v8; // dx
  struct IStreamVtbl *lpVtbl; // rax
  _WORD v11[2]; // [rsp+30h] [rbp-148h] BYREF
  _DWORD v12[3]; // [rsp+34h] [rbp-144h] BYREF
  CHAR pszDst[272]; // [rsp+40h] [rbp-138h] BYREF

  SHUnicodeToAnsi((PCWSTR)(*((_QWORD *)this + 12) + 528LL), pszDst, 260);
  *a3 = 0;
  v6 = StringWriteToStream(a2, pszDst, a3);
  if ( v6 >= 0 )
  {
    SHUnicodeToAnsi((PCWSTR)(*((_QWORD *)this + 12) + 8LL), pszDst, 260);
    v6 = StringWriteToStream(a2, pszDst, a3);
    if ( v6 >= 0 )
    {
      v7 = *((_QWORD *)this + 12);
      v12[0] = 0;
      v8 = *(_WORD *)(v7 + 1048);
      lpVtbl = a2->lpVtbl;
      v11[0] = v8;
      v6 = ((__int64 (__fastcall *)(struct IStream *, _WORD *, __int64, _DWORD *))lpVtbl->Write)(a2, v11, 2, v12);
      if ( v6 >= 0 )
        *a3 += v12[0];
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008dcc  push    rbx
0x180008dce  push    rsi
0x180008dcf  push    rdi
0x180008dd0  sub     rsp, 160h
0x180008dd7  mov     rax, cs:__security_cookie
0x180008dde  xor     rax, rsp
0x180008de1  mov     [rsp+178h+var_28], rax
0x180008de9  mov     rsi, rcx
0x180008dec  mov     rbx, r8
0x180008def  mov     rcx, [rcx+60h]
0x180008df3  mov     rdi, rdx
0x180008df6  add     rcx, 210h; pwszSrc
0x180008dfd  lea     rdx, [rsp+178h+pszDst]; pszDst
0x180008e02  mov     r8d, 104h; cchBuf
0x180008e08  call    cs:__imp_SHUnicodeToAnsi
0x180008e0e  mov     r8, rbx; unsigned int *
0x180008e11  mov     dword ptr [rbx], 0
0x180008e17  lea     rdx, [rsp+178h+pszDst]; char *
0x180008e1c  mov     rcx, rdi; struct IStream *
0x180008e1f  call    ?StringWriteToStream@@YAJPEAUIStream@@PEBDPEAK@Z; StringWriteToStream(IStream *,char const *,ulong *)
0x180008e24  mov     ecx, eax
0x180008e26  test    eax, eax
0x180008e28  js      short loc_180008E9C
0x180008e2a  mov     rcx, [rsi+60h]
0x180008e2e  lea     rdx, [rsp+178h+pszDst]; pszDst
0x180008e33  add     rcx, 8; pwszSrc
0x180008e37  mov     r8d, 104h; cchBuf
0x180008e3d  call    cs:__imp_SHUnicodeToAnsi
0x180008e43  mov     r8, rbx; unsigned int *
0x180008e46  lea     rdx, [rsp+178h+pszDst]; char *
0x180008e4b  mov     rcx, rdi; struct IStream *
0x180008e4e  call    ?StringWriteToStream@@YAJPEAUIStream@@PEBDPEAK@Z; StringWriteToStream(IStream *,char const *,ulong *)
0x180008e53  mov     ecx, eax
0x180008e55  test    eax, eax
0x180008e57  js      short loc_180008E9C
0x180008e59  mov     rax, [rsi+60h]
0x180008e5d  lea     r9, [rsp+178h+var_144]
0x180008e62  mov     [rsp+178h+var_144], 0
0x180008e6a  mov     r8d, 2
0x180008e70  mov     rcx, rdi
0x180008e73  movzx   edx, word ptr [rax+418h]
0x180008e7a  mov     rax, [rdi]
0x180008e7d  mov     [rsp+178h+var_148], dx
0x180008e82  lea     rdx, [rsp+178h+var_148]
0x180008e87  mov     rax, [rax+20h]
0x180008e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e90  mov     ecx, eax
0x180008e92  test    eax, eax
0x180008e94  js      short loc_180008E9C
0x180008e96  mov     eax, [rsp+178h+var_144]
0x180008e9a  add     [rbx], eax
0x180008e9c  mov     eax, ecx
0x180008e9e  mov     rcx, [rsp+178h+var_28]
0x180008ea6  xor     rcx, rsp; StackCookie
0x180008ea9  call    __security_check_cookie
0x180008eae  add     rsp, 160h
0x180008eb5  pop     rdi
0x180008eb6  pop     rsi
0x180008eb7  pop     rbx
0x180008eb8  retn
```
