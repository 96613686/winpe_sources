# CItemIDFactory<tagCSCROOTDATA,53483873>::s_CreateItemID(tagCSCROOTDATA const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180013c44`
- end: `0x180013d95`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagCSCROOTDATA@@$0DDABJGB@@@SAJPEFBUtagCSCROOTDATA@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(_DWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012678`

## callees

- `0x180013c44`
- `0x18004c61e`
- `0x18004c636`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d7c`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagCSCROOTDATA,53483873>::s_CreateItemID(
        _DWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v4; // eax
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rbx
  __int16 v11; // di
  void *v12; // rax
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v4 = 0;
  *a3 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
  {
LABEL_5:
    v9 = (unsigned int)(v4 + 12) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 12) + 2LL);
    }
    else
    {
      v11 = v4 + 22;
      if ( (unsigned __int64)(unsigned int)(v4 + 12) + 10 > 0x10001 )
        goto LABEL_16;
      v12 = CoTaskMemAlloc((unsigned int)(v4 + 12) + 10LL);
      v10 = (__int64)v12;
      if ( v12 )
      {
        memset_0(v12, 0, v9 + 8);
        *(_WORD *)(v10 + 4) = v9;
        *(_WORD *)v10 = v11 - 2;
        goto LABEL_8;
      }
    }
    if ( v10 )
    {
LABEL_8:
      *(_DWORD *)(v10 + 6) = 53483873;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 4;
      if ( a1 )
        *(_DWORD *)(v10 + 14) = *a1;
      if ( Src )
        memcpy_0((void *)(v10 + 18), Src, (unsigned int)Size);
      *a3 = v10;
      v8 = 0;
      goto LABEL_17;
    }
LABEL_16:
    v8 = -2147024882;
LABEL_17:
    CoTaskMemFree(Src);
    return (unsigned int)v8;
  }
  v16 = 0;
  v8 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v16);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v16 + 40LL))(v16, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v8 >= 0 )
    {
      v4 = Size;
      goto LABEL_5;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013c44  mov     [rsp-28h+arg_0], rbx
0x180013c49  push    rbp
0x180013c4a  push    rsi
0x180013c4b  push    rdi
0x180013c4c  push    r14
0x180013c4e  push    r15
0x180013c50  mov     rbp, rsp
0x180013c53  sub     rsp, 30h
0x180013c57  xor     eax, eax
0x180013c59  mov     qword ptr [r8], 0
0x180013c60  mov     [rbp+Src], 0
0x180013c68  mov     rdi, r9
0x180013c6b  mov     dword ptr [rbp+Size], eax
0x180013c6e  mov     r15, r8
0x180013c71  mov     r10, rdx
0x180013c74  mov     r14, rcx
0x180013c77  test    rdx, rdx
0x180013c7a  jz      short loc_180013CD8
0x180013c7c  mov     [rbp+arg_10], rax
0x180013c80  lea     r8, [rbp+arg_10]
0x180013c84  mov     rax, [rdx]
0x180013c87  mov     rcx, r10
0x180013c8a  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180013c91  mov     rax, [rax]
0x180013c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c99  mov     ebx, eax
0x180013c9b  test    eax, eax
0x180013c9d  js      loc_180013D82
0x180013ca3  mov     rcx, [rbp+arg_10]
0x180013ca7  lea     r8, [rbp+Size]
0x180013cab  lea     rdx, [rbp+Src]
0x180013caf  mov     rax, [rcx]
0x180013cb2  mov     rax, [rax+28h]
0x180013cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cbb  mov     rcx, [rbp+arg_10]
0x180013cbf  mov     ebx, eax
0x180013cc1  mov     rax, [rcx]
0x180013cc4  mov     rax, [rax+10h]
0x180013cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ccd  test    ebx, ebx
0x180013ccf  js      loc_180013D82
0x180013cd5  mov     eax, dword ptr [rbp+Size]
0x180013cd8  lea     esi, [rax+0Ch]
0x180013cdb  add     rsi, 2
0x180013cdf  test    rdi, rdi
0x180013ce2  jz      short loc_180013D3B
0x180013ce4  mov     rax, [rdi]
0x180013ce7  mov     rdx, rsi
0x180013cea  mov     rcx, rdi
0x180013ced  mov     rax, [rax+18h]
0x180013cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cf6  mov     rbx, rax
0x180013cf9  test    rbx, rbx
0x180013cfc  jz      short loc_180013D73
0x180013cfe  mov     dword ptr [rbx+6], 3301961h
0x180013d05  movzx   eax, word ptr [rbp+Size]
0x180013d09  mov     [rbx+0Ah], ax
0x180013d0d  mov     word ptr [rbx+0Ch], 4
0x180013d13  test    r14, r14
0x180013d16  jz      short loc_180013D1E
0x180013d18  mov     eax, [r14]
0x180013d1b  mov     [rbx+0Eh], eax
0x180013d1e  mov     rdx, [rbp+Src]; Src
0x180013d22  test    rdx, rdx
0x180013d25  jz      short loc_180013D34
0x180013d27  mov     r8d, dword ptr [rbp+Size]; Size
0x180013d2b  lea     rcx, [rbx+12h]; void *
0x180013d2f  call    memcpy_0
0x180013d34  mov     [r15], rbx
0x180013d37  xor     ebx, ebx
0x180013d39  jmp     short loc_180013D78
0x180013d3b  lea     rdi, [rsi+8]
0x180013d3f  cmp     rdi, 10001h
0x180013d46  ja      short loc_180013D73
0x180013d48  mov     rcx, rdi; cb
0x180013d4b  call    cs:__imp_CoTaskMemAlloc
0x180013d51  mov     rbx, rax
0x180013d54  test    rax, rax
0x180013d57  jz      short loc_180013CF9
0x180013d59  mov     r8, rdi; Size
0x180013d5c  xor     edx, edx; Val
0x180013d5e  mov     rcx, rax; void *
0x180013d61  call    memset_0
0x180013d66  sub     di, 2
0x180013d6a  mov     [rbx+4], si
0x180013d6e  mov     [rbx], di
0x180013d71  jmp     short loc_180013CFE
0x180013d73  mov     ebx, 8007000Eh
0x180013d78  mov     rcx, [rbp+Src]; pv
0x180013d7c  call    cs:__imp_CoTaskMemFree
0x180013d82  mov     eax, ebx
0x180013d84  mov     rbx, [rsp+30h+arg_0]
0x180013d89  add     rsp, 30h
0x180013d8d  pop     r15
0x180013d8f  pop     r14
0x180013d91  pop     rdi
0x180013d92  pop     rsi
0x180013d93  pop     rbp
0x180013d94  retn
```
