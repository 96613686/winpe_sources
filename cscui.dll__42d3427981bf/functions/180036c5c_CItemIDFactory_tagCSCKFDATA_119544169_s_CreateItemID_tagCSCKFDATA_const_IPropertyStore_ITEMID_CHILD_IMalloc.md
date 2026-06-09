# CItemIDFactory<tagCSCKFDATA,119544169>::s_CreateItemID(tagCSCKFDATA const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180036c5c`
- end: `0x180036db0`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagCSCKFDATA@@$0HCABJGJ@@@SAJPEFBUtagCSCKFDATA@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(_OWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003565c`

## callees

- `0x180036c5c`
- `0x18004c61e`
- `0x18004c636`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d97`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagCSCKFDATA,119544169>::s_CreateItemID(
        _OWORD *a1,
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
    v9 = (unsigned int)(v4 + 24) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 24) + 2LL);
    }
    else
    {
      v11 = v4 + 34;
      if ( (unsigned __int64)(unsigned int)(v4 + 24) + 10 > 0x10001 )
        goto LABEL_16;
      v12 = CoTaskMemAlloc((unsigned int)(v4 + 24) + 10LL);
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
      *(_DWORD *)(v10 + 6) = 119544169;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 16;
      if ( a1 )
        *(_OWORD *)(v10 + 14) = *a1;
      if ( Src )
        memcpy_0((void *)(v10 + 30), Src, (unsigned int)Size);
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
0x180036c5c  mov     [rsp-28h+arg_0], rbx
0x180036c61  push    rbp
0x180036c62  push    rsi
0x180036c63  push    rdi
0x180036c64  push    r14
0x180036c66  push    r15
0x180036c68  mov     rbp, rsp
0x180036c6b  sub     rsp, 30h
0x180036c6f  xor     eax, eax
0x180036c71  mov     qword ptr [r8], 0
0x180036c78  mov     [rbp+Src], 0
0x180036c80  mov     rdi, r9
0x180036c83  mov     dword ptr [rbp+Size], eax
0x180036c86  mov     r15, r8
0x180036c89  mov     r10, rdx
0x180036c8c  mov     r14, rcx
0x180036c8f  test    rdx, rdx
0x180036c92  jz      short loc_180036CF0
0x180036c94  mov     [rbp+arg_10], rax
0x180036c98  lea     r8, [rbp+arg_10]
0x180036c9c  mov     rax, [rdx]
0x180036c9f  mov     rcx, r10
0x180036ca2  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180036ca9  mov     rax, [rax]
0x180036cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cb1  mov     ebx, eax
0x180036cb3  test    eax, eax
0x180036cb5  js      loc_180036D9D
0x180036cbb  mov     rcx, [rbp+arg_10]
0x180036cbf  lea     r8, [rbp+Size]
0x180036cc3  lea     rdx, [rbp+Src]
0x180036cc7  mov     rax, [rcx]
0x180036cca  mov     rax, [rax+28h]
0x180036cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cd3  mov     rcx, [rbp+arg_10]
0x180036cd7  mov     ebx, eax
0x180036cd9  mov     rax, [rcx]
0x180036cdc  mov     rax, [rax+10h]
0x180036ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ce5  test    ebx, ebx
0x180036ce7  js      loc_180036D9D
0x180036ced  mov     eax, dword ptr [rbp+Size]
0x180036cf0  lea     esi, [rax+18h]
0x180036cf3  add     rsi, 2
0x180036cf7  test    rdi, rdi
0x180036cfa  jz      short loc_180036D56
0x180036cfc  mov     rax, [rdi]
0x180036cff  mov     rdx, rsi
0x180036d02  mov     rcx, rdi
0x180036d05  mov     rax, [rax+18h]
0x180036d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d0e  mov     rbx, rax
0x180036d11  test    rbx, rbx
0x180036d14  jz      short loc_180036D8E
0x180036d16  mov     dword ptr [rbx+6], 7201969h
0x180036d1d  movzx   eax, word ptr [rbp+Size]
0x180036d21  mov     [rbx+0Ah], ax
0x180036d25  mov     word ptr [rbx+0Ch], 10h
0x180036d2b  test    r14, r14
0x180036d2e  jz      short loc_180036D39
0x180036d30  movups  xmm0, xmmword ptr [r14]
0x180036d34  movdqu  xmmword ptr [rbx+0Eh], xmm0
0x180036d39  mov     rdx, [rbp+Src]; Src
0x180036d3d  test    rdx, rdx
0x180036d40  jz      short loc_180036D4F
0x180036d42  mov     r8d, dword ptr [rbp+Size]; Size
0x180036d46  lea     rcx, [rbx+1Eh]; void *
0x180036d4a  call    memcpy_0
0x180036d4f  mov     [r15], rbx
0x180036d52  xor     ebx, ebx
0x180036d54  jmp     short loc_180036D93
0x180036d56  lea     rdi, [rsi+8]
0x180036d5a  cmp     rdi, 10001h
0x180036d61  ja      short loc_180036D8E
0x180036d63  mov     rcx, rdi; cb
0x180036d66  call    cs:__imp_CoTaskMemAlloc
0x180036d6c  mov     rbx, rax
0x180036d6f  test    rax, rax
0x180036d72  jz      short loc_180036D11
0x180036d74  mov     r8, rdi; Size
0x180036d77  xor     edx, edx; Val
0x180036d79  mov     rcx, rax; void *
0x180036d7c  call    memset_0
0x180036d81  sub     di, 2
0x180036d85  mov     [rbx+4], si
0x180036d89  mov     [rbx], di
0x180036d8c  jmp     short loc_180036D16
0x180036d8e  mov     ebx, 8007000Eh
0x180036d93  mov     rcx, [rbp+Src]; pv
0x180036d97  call    cs:__imp_CoTaskMemFree
0x180036d9d  mov     eax, ebx
0x180036d9f  mov     rbx, [rsp+30h+arg_0]
0x180036da4  add     rsp, 30h
0x180036da8  pop     r15
0x180036daa  pop     r14
0x180036dac  pop     rdi
0x180036dad  pop     rsi
0x180036dae  pop     rbp
0x180036daf  retn
```
