# CItemIDFactory<tagCSCITEMDATA,86514056>::s_CreateItemID(tagCSCITEMDATA const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x18003a47c`
- end: `0x18003a5dc`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagCSCITEMDATA@@$0FCIBJII@@@SAJPEFBUtagCSCITEMDATA@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(_OWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800372ec`
- `0x1800373e8`

## callees

- `0x18003a47c`
- `0x18004c61e`
- `0x18004c636`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5c3`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagCSCITEMDATA,86514056>::s_CreateItemID(
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
    v9 = (unsigned int)(v4 + 36) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 36) + 2LL);
    }
    else
    {
      v11 = v4 + 46;
      if ( (unsigned __int64)(unsigned int)(v4 + 36) + 10 > 0x10001 )
        goto LABEL_16;
      v12 = CoTaskMemAlloc((unsigned int)(v4 + 36) + 10LL);
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
      *(_DWORD *)(v10 + 6) = 86514056;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 28;
      if ( a1 )
      {
        *(_OWORD *)(v10 + 14) = *a1;
        *(_OWORD *)(v10 + 26) = *(_OWORD *)((char *)a1 + 12);
      }
      if ( Src )
        memcpy_0((void *)(v10 + 42), Src, (unsigned int)Size);
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
0x18003a47c  mov     [rsp-28h+arg_0], rbx
0x18003a481  push    rbp
0x18003a482  push    rsi
0x18003a483  push    rdi
0x18003a484  push    r14
0x18003a486  push    r15
0x18003a488  mov     rbp, rsp
0x18003a48b  sub     rsp, 30h
0x18003a48f  xor     eax, eax
0x18003a491  mov     qword ptr [r8], 0
0x18003a498  mov     [rbp+Src], 0
0x18003a4a0  mov     rdi, r9
0x18003a4a3  mov     dword ptr [rbp+Size], eax
0x18003a4a6  mov     r15, r8
0x18003a4a9  mov     r10, rdx
0x18003a4ac  mov     r14, rcx
0x18003a4af  test    rdx, rdx
0x18003a4b2  jz      short loc_18003A510
0x18003a4b4  mov     [rbp+arg_10], rax
0x18003a4b8  lea     r8, [rbp+arg_10]
0x18003a4bc  mov     rax, [rdx]
0x18003a4bf  mov     rcx, r10
0x18003a4c2  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18003a4c9  mov     rax, [rax]
0x18003a4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4d1  mov     ebx, eax
0x18003a4d3  test    eax, eax
0x18003a4d5  js      loc_18003A5C9
0x18003a4db  mov     rcx, [rbp+arg_10]
0x18003a4df  lea     r8, [rbp+Size]
0x18003a4e3  lea     rdx, [rbp+Src]
0x18003a4e7  mov     rax, [rcx]
0x18003a4ea  mov     rax, [rax+28h]
0x18003a4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4f3  mov     rcx, [rbp+arg_10]
0x18003a4f7  mov     ebx, eax
0x18003a4f9  mov     rax, [rcx]
0x18003a4fc  mov     rax, [rax+10h]
0x18003a500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a505  test    ebx, ebx
0x18003a507  js      loc_18003A5C9
0x18003a50d  mov     eax, dword ptr [rbp+Size]
0x18003a510  lea     esi, [rax+24h]
0x18003a513  add     rsi, 2
0x18003a517  test    rdi, rdi
0x18003a51a  jz      short loc_18003A582
0x18003a51c  mov     rax, [rdi]
0x18003a51f  mov     rdx, rsi
0x18003a522  mov     rcx, rdi
0x18003a525  mov     rax, [rax+18h]
0x18003a529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a52e  mov     rbx, rax
0x18003a531  test    rbx, rbx
0x18003a534  jz      loc_18003A5BA
0x18003a53a  mov     dword ptr [rbx+6], 5281988h
0x18003a541  movzx   eax, word ptr [rbp+Size]
0x18003a545  mov     [rbx+0Ah], ax
0x18003a549  mov     word ptr [rbx+0Ch], 1Ch
0x18003a54f  test    r14, r14
0x18003a552  jz      short loc_18003A565
0x18003a554  movups  xmm0, xmmword ptr [r14]
0x18003a558  movups  xmmword ptr [rbx+0Eh], xmm0
0x18003a55c  movups  xmm1, xmmword ptr [r14+0Ch]
0x18003a561  movups  xmmword ptr [rbx+1Ah], xmm1
0x18003a565  mov     rdx, [rbp+Src]; Src
0x18003a569  test    rdx, rdx
0x18003a56c  jz      short loc_18003A57B
0x18003a56e  mov     r8d, dword ptr [rbp+Size]; Size
0x18003a572  lea     rcx, [rbx+2Ah]; void *
0x18003a576  call    memcpy_0
0x18003a57b  mov     [r15], rbx
0x18003a57e  xor     ebx, ebx
0x18003a580  jmp     short loc_18003A5BF
0x18003a582  lea     rdi, [rsi+8]
0x18003a586  cmp     rdi, 10001h
0x18003a58d  ja      short loc_18003A5BA
0x18003a58f  mov     rcx, rdi; cb
0x18003a592  call    cs:__imp_CoTaskMemAlloc
0x18003a598  mov     rbx, rax
0x18003a59b  test    rax, rax
0x18003a59e  jz      short loc_18003A531
0x18003a5a0  mov     r8, rdi; Size
0x18003a5a3  xor     edx, edx; Val
0x18003a5a5  mov     rcx, rax; void *
0x18003a5a8  call    memset_0
0x18003a5ad  sub     di, 2
0x18003a5b1  mov     [rbx+4], si
0x18003a5b5  mov     [rbx], di
0x18003a5b8  jmp     short loc_18003A53A
0x18003a5ba  mov     ebx, 8007000Eh
0x18003a5bf  mov     rcx, [rbp+Src]; pv
0x18003a5c3  call    cs:__imp_CoTaskMemFree
0x18003a5c9  mov     eax, ebx
0x18003a5cb  mov     rbx, [rsp+30h+arg_0]
0x18003a5d0  add     rsp, 30h
0x18003a5d4  pop     r15
0x18003a5d6  pop     r14
0x18003a5d8  pop     rdi
0x18003a5d9  pop     rsi
0x18003a5da  pop     rbp
0x18003a5db  retn
```
