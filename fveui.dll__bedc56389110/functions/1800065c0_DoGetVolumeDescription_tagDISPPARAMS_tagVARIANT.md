# DoGetVolumeDescription(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x1800065c0`
- end: `0x1800066c5`
- name: `?DoGetVolumeDescription@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001bd4`
- `0x180002028`
- `0x1800065c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000667b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000667b`
- `FVEAPI!FveGetDescriptionW` at `0x18000660b`
- `FVEAPI!FveGetDescriptionW` at `0x180006667`
- `FVEAPI!FveGetDescriptionW` at `0x18000660b`
- `FVEAPI!FveGetDescriptionW` at `0x180006667`
- `FVEAPI!FveCloseVolume` at `0x18000669e`
- `FVEAPI!FveCloseVolume` at `0x18000669e`
- `FVEAPI!FveOpenVolumeW` at `0x1800065ec`
- `FVEAPI!FveOpenVolumeW` at `0x1800065ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DoGetVolumeDescription(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  OLECHAR *v4; // rdi
  int DescriptionW; // ebx
  unsigned __int64 v6; // rax
  OLECHAR *v7; // rax
  BSTR v8; // rax
  int v9; // ecx
  unsigned __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  rgvarg = a1->rgvarg;
  v4 = 0;
  v11 = 0;
  v12 = -1;
  DescriptionW = FveOpenVolumeW(rgvarg->llVal, 0, &v12);
  if ( DescriptionW >= 0 )
  {
    FveGetDescriptionW(v12, 0, 0, &v11);
    if ( v11 < 0x7FFFFFFFFFFFFFFFLL )
    {
      v6 = 2 * v11;
      if ( !is_mul_ok(v11, 2u) )
        v6 = -1;
      v7 = (OLECHAR *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
      v4 = v7;
      if ( v7 )
      {
        DescriptionW = FveGetDescriptionW(v12, v7, v11, &v11);
        if ( DescriptionW >= 0 )
        {
          a2->vt = 8;
          v8 = SysAllocString(v4);
          v9 = DescriptionW;
          a2->llVal = (LONGLONG)v8;
          if ( !v8 )
            v9 = -2147024882;
          DescriptionW = v9;
        }
      }
      else
      {
        DescriptionW = -2147024882;
      }
    }
    else
    {
      DescriptionW = -2147024362;
    }
  }
  if ( v12 != -1 )
  {
    FveCloseVolume(v12);
    v12 = -1;
  }
  if ( v4 )
    operator delete(v4);
  return (unsigned int)DescriptionW;
}

```

## disassembly

```asm
0x1800065c0  mov     rax, rsp
0x1800065c3  mov     [rax+10h], rbx
0x1800065c7  push    rbp
0x1800065c8  push    rsi
0x1800065c9  push    rdi
0x1800065ca  sub     rsp, 20h
0x1800065ce  mov     rcx, [rcx]
0x1800065d1  lea     r8, [rax+18h]
0x1800065d5  mov     rsi, rdx
0x1800065d8  xor     edi, edi
0x1800065da  mov     [rax+8], rdi
0x1800065de  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800065e2  mov     [rax+18h], rbp
0x1800065e6  xor     edx, edx
0x1800065e8  mov     rcx, [rcx+8]
0x1800065ec  call    cs:__imp_FveOpenVolumeW
0x1800065f2  mov     ebx, eax
0x1800065f4  test    eax, eax
0x1800065f6  js      loc_180006694
0x1800065fc  mov     rcx, [rsp+38h+arg_10]
0x180006601  lea     r9, [rsp+38h+arg_0]
0x180006606  xor     r8d, r8d
0x180006609  xor     edx, edx
0x18000660b  call    cs:__imp_FveGetDescriptionW
0x180006611  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000661b  cmp     [rsp+38h+arg_0], rax
0x180006620  jb      short loc_180006629
0x180006622  mov     ebx, 80070216h
0x180006627  jmp     short loc_180006694
0x180006629  mov     eax, 2
0x18000662e  mul     [rsp+38h+arg_0]
0x180006633  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000663a  cmovb   rax, rbp
0x18000663e  mov     rcx, rax; unsigned __int64
0x180006641  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006646  mov     rdi, rax
0x180006649  test    rax, rax
0x18000664c  jnz     short loc_180006655
0x18000664e  mov     ebx, 8007000Eh
0x180006653  jmp     short loc_180006694
0x180006655  mov     r8, [rsp+38h+arg_0]
0x18000665a  lea     r9, [rsp+38h+arg_0]
0x18000665f  mov     rcx, [rsp+38h+arg_10]
0x180006664  mov     rdx, rdi
0x180006667  call    cs:__imp_FveGetDescriptionW
0x18000666d  mov     ebx, eax
0x18000666f  test    eax, eax
0x180006671  js      short loc_180006694
0x180006673  mov     rcx, rdi; psz
0x180006676  mov     word ptr [rsi], 8
0x18000667b  call    cs:__imp_SysAllocString
0x180006681  mov     ecx, ebx
0x180006683  mov     ebx, 8007000Eh
0x180006688  test    rax, rax
0x18000668b  mov     [rsi+8], rax
0x18000668f  cmovz   ecx, ebx
0x180006692  mov     ebx, ecx
0x180006694  mov     rcx, [rsp+38h+arg_10]
0x180006699  cmp     rcx, rbp
0x18000669c  jz      short loc_1800066A9
0x18000669e  call    cs:__imp_FveCloseVolume
0x1800066a4  mov     [rsp+38h+arg_10], rbp
0x1800066a9  test    rdi, rdi
0x1800066ac  jz      short loc_1800066B6
0x1800066ae  mov     rcx, rdi; void *
0x1800066b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800066b6  mov     eax, ebx
0x1800066b8  mov     rbx, [rsp+38h+arg_8]
0x1800066bd  add     rsp, 20h
0x1800066c1  pop     rdi
0x1800066c2  pop     rsi
0x1800066c3  pop     rbp
0x1800066c4  retn
```
