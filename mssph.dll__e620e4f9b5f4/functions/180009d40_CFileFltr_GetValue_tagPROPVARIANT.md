# CFileFltr::GetValue(tagPROPVARIANT * *)

- ea: `0x180009d40`
- end: `0x180009e4b`
- name: `?GetValue@CFileFltr@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `267`
- prototype: `HRESULT __fastcall(CFileFltr *this, PROPVARIANT **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d6a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009e3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009e3a`

## pseudocode

```c
HRESULT __fastcall CFileFltr::GetValue(CFileFltr *this, PROPVARIANT **a2)
{
  struct tagPROPVARIANT *v5; // rax
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  bool v9; // zf
  __int16 v10; // ax
  PROPVARIANT pvarSrc[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+30h] [rbp-18h]

  if ( !a2 )
    return -2147467261;
  v5 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  *a2 = (PROPVARIANT *)v5;
  if ( !v5 )
    return -2147024882;
  *(_OWORD *)&v5->vt = 0;
  v5->bstrblobVal.pData = 0;
  v6 = *((_DWORD *)this + 19);
  v12 = 0;
  *(_OWORD *)pvarSrc = 0;
  if ( v6 == 4 )
  {
    v9 = (*((_DWORD *)this + 16) & 0x4000) == 0;
    LOWORD(pvarSrc[0]) = 11;
    if ( v9 )
      v10 = 0;
    else
      v10 = -1;
    LOWORD(pvarSrc[1]) = v10;
  }
  else if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
          return -2147418113;
        LOWORD(pvarSrc[0]) = 64;
        pvarSrc[1] = *((PROPVARIANT *)this + 12);
      }
      else
      {
        LOWORD(pvarSrc[0]) = 64;
        pvarSrc[1] = *((PROPVARIANT *)this + 11);
      }
    }
    else
    {
      LOWORD(pvarSrc[0]) = 64;
      pvarSrc[1] = *((PROPVARIANT *)this + 10);
    }
  }
  else
  {
    LOWORD(pvarSrc[0]) = 19;
    LODWORD(pvarSrc[1]) = *((_DWORD *)this + 16);
  }
  return PropVariantCopy(*a2, pvarSrc);
}

```

## disassembly

```asm
0x180009d40  mov     [rsp+arg_0], rbx
0x180009d45  push    rdi
0x180009d46  sub     rsp, 40h
0x180009d4a  mov     rbx, rdx
0x180009d4d  mov     rdi, rcx
0x180009d50  test    rdx, rdx
0x180009d53  jnz     short loc_180009D65
0x180009d55  mov     eax, 80004003h
0x180009d5a  mov     rbx, [rsp+48h+arg_0]
0x180009d5f  add     rsp, 40h
0x180009d63  pop     rdi
0x180009d64  retn
0x180009d65  mov     ecx, 18h; cb
0x180009d6a  call    cs:__imp_CoTaskMemAlloc
0x180009d70  mov     [rbx], rax
0x180009d73  test    rax, rax
0x180009d76  jnz     short loc_180009D82
0x180009d78  mov     eax, 8007000Eh
0x180009d7d  jmp     loc_180009E40
0x180009d82  xor     ecx, ecx
0x180009d84  xorps   xmm0, xmm0
0x180009d87  movups  xmmword ptr [rax], xmm0
0x180009d8a  mov     [rax+10h], rcx
0x180009d8e  xor     eax, eax
0x180009d90  mov     ecx, [rdi+4Ch]
0x180009d93  mov     [rsp+48h+var_18], rax
0x180009d98  movups  xmmword ptr [rsp+48h+pvarSrc], xmm0
0x180009d9d  cmp     ecx, 4
0x180009da0  jz      short loc_180009E11
0x180009da2  test    ecx, ecx
0x180009da4  jz      short loc_180009DFE
0x180009da6  sub     ecx, 1
0x180009da9  jz      short loc_180009DE9
0x180009dab  sub     ecx, 1
0x180009dae  jz      short loc_180009DD4
0x180009db0  cmp     ecx, 1
0x180009db3  jz      short loc_180009DBF
0x180009db5  mov     eax, 8000FFFFh
0x180009dba  jmp     loc_180009E40
0x180009dbf  mov     eax, 40h ; '@'
0x180009dc4  mov     word ptr [rsp+48h+pvarSrc], ax
0x180009dc9  mov     rax, [rdi+60h]
0x180009dcd  mov     [rsp+48h+pvarSrc+8], rax
0x180009dd2  jmp     short loc_180009E32
0x180009dd4  mov     eax, 40h ; '@'
0x180009dd9  mov     word ptr [rsp+48h+pvarSrc], ax
0x180009dde  mov     rax, [rdi+58h]
0x180009de2  mov     [rsp+48h+pvarSrc+8], rax
0x180009de7  jmp     short loc_180009E32
0x180009de9  mov     eax, 40h ; '@'
0x180009dee  mov     word ptr [rsp+48h+pvarSrc], ax
0x180009df3  mov     rax, [rdi+50h]
0x180009df7  mov     [rsp+48h+pvarSrc+8], rax
0x180009dfc  jmp     short loc_180009E32
0x180009dfe  mov     eax, 13h
0x180009e03  mov     word ptr [rsp+48h+pvarSrc], ax
0x180009e08  mov     eax, [rdi+40h]
0x180009e0b  mov     dword ptr [rsp+48h+pvarSrc+8], eax
0x180009e0f  jmp     short loc_180009E32
0x180009e11  test    dword ptr [rdi+40h], 4000h
0x180009e18  mov     eax, 0Bh
0x180009e1d  mov     word ptr [rsp+48h+pvarSrc], ax
0x180009e22  jz      short loc_180009E2B
0x180009e24  mov     eax, 0FFFFFFFFh
0x180009e29  jmp     short loc_180009E2D
0x180009e2b  xor     eax, eax
0x180009e2d  mov     word ptr [rsp+48h+pvarSrc+8], ax
0x180009e32  mov     rcx, [rbx]; pvarDest
0x180009e35  lea     rdx, [rsp+48h+pvarSrc]; pvarSrc
0x180009e3a  call    cs:__imp_PropVariantCopy
0x180009e40  mov     rbx, [rsp+48h+arg_0]
0x180009e45  add     rsp, 40h
0x180009e49  pop     rdi
0x180009e4a  retn
```
