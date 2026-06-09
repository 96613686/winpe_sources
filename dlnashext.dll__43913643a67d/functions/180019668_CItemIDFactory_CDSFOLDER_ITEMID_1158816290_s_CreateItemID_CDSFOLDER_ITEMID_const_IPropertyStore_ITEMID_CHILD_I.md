# CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::s_CreateItemID(CDSFOLDER_ITEMID const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180019668`
- end: `0x1800197b9`
- name: `?s_CreateItemID@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBUCDSFOLDER_ITEMID@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016ce4`
- `0x180017fcc`

## callees

- `0x1800125c4`
- `0x180019668`
- `0x1800333e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001976f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001976f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197a0`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::s_CreateItemID(
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
      *(_DWORD *)(v10 + 6) = 1158816290;
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
0x180019668  mov     [rsp-28h+arg_0], rbx
0x18001966d  push    rbp
0x18001966e  push    rsi
0x18001966f  push    rdi
0x180019670  push    r14
0x180019672  push    r15
0x180019674  mov     rbp, rsp
0x180019677  sub     rsp, 30h
0x18001967b  xor     eax, eax
0x18001967d  mov     qword ptr [r8], 0
0x180019684  mov     [rbp+Src], 0
0x18001968c  mov     rdi, r9
0x18001968f  mov     dword ptr [rbp+Size], eax
0x180019692  mov     r15, r8
0x180019695  mov     r10, rdx
0x180019698  mov     r14, rcx
0x18001969b  test    rdx, rdx
0x18001969e  jz      short loc_1800196FC
0x1800196a0  mov     [rbp+arg_10], rax
0x1800196a4  lea     r8, [rbp+arg_10]
0x1800196a8  mov     rax, [rdx]
0x1800196ab  mov     rcx, r10
0x1800196ae  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x1800196b5  mov     rax, [rax]
0x1800196b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196bd  mov     ebx, eax
0x1800196bf  test    eax, eax
0x1800196c1  js      loc_1800197A6
0x1800196c7  mov     rcx, [rbp+arg_10]
0x1800196cb  lea     r8, [rbp+Size]
0x1800196cf  lea     rdx, [rbp+Src]
0x1800196d3  mov     rax, [rcx]
0x1800196d6  mov     rax, [rax+28h]
0x1800196da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196df  mov     rcx, [rbp+arg_10]
0x1800196e3  mov     ebx, eax
0x1800196e5  mov     rax, [rcx]
0x1800196e8  mov     rax, [rax+10h]
0x1800196ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f1  test    ebx, ebx
0x1800196f3  js      loc_1800197A6
0x1800196f9  mov     eax, dword ptr [rbp+Size]
0x1800196fc  lea     esi, [rax+0Ch]
0x1800196ff  add     rsi, 2
0x180019703  test    rdi, rdi
0x180019706  jz      short loc_18001975F
0x180019708  mov     rax, [rdi]
0x18001970b  mov     rdx, rsi
0x18001970e  mov     rcx, rdi
0x180019711  mov     rax, [rax+18h]
0x180019715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001971a  mov     rbx, rax
0x18001971d  test    rbx, rbx
0x180019720  jz      short loc_180019797
0x180019722  mov     dword ptr [rbx+6], 45122222h
0x180019729  movzx   eax, word ptr [rbp+Size]
0x18001972d  mov     [rbx+0Ah], ax
0x180019731  mov     word ptr [rbx+0Ch], 4
0x180019737  test    r14, r14
0x18001973a  jz      short loc_180019742
0x18001973c  mov     eax, [r14]
0x18001973f  mov     [rbx+0Eh], eax
0x180019742  mov     rdx, [rbp+Src]; Src
0x180019746  test    rdx, rdx
0x180019749  jz      short loc_180019758
0x18001974b  mov     r8d, dword ptr [rbp+Size]; Size
0x18001974f  lea     rcx, [rbx+12h]; void *
0x180019753  call    memcpy_0
0x180019758  mov     [r15], rbx
0x18001975b  xor     ebx, ebx
0x18001975d  jmp     short loc_18001979C
0x18001975f  lea     rdi, [rsi+8]
0x180019763  cmp     rdi, 10001h
0x18001976a  ja      short loc_180019797
0x18001976c  mov     rcx, rdi; cb
0x18001976f  call    cs:__imp_CoTaskMemAlloc
0x180019775  mov     rbx, rax
0x180019778  test    rax, rax
0x18001977b  jz      short loc_18001971D
0x18001977d  mov     r8, rdi; Size
0x180019780  xor     edx, edx; Val
0x180019782  mov     rcx, rax; void *
0x180019785  call    memset_0
0x18001978a  sub     di, 2
0x18001978e  mov     [rbx+4], si
0x180019792  mov     [rbx], di
0x180019795  jmp     short loc_180019722
0x180019797  mov     ebx, 8007000Eh
0x18001979c  mov     rcx, [rbp+Src]; pv
0x1800197a0  call    cs:__imp_CoTaskMemFree
0x1800197a6  mov     eax, ebx
0x1800197a8  mov     rbx, [rsp+30h+arg_0]
0x1800197ad  add     rsp, 30h
0x1800197b1  pop     r15
0x1800197b3  pop     r14
0x1800197b5  pop     rdi
0x1800197b6  pop     rsi
0x1800197b7  pop     rbp
0x1800197b8  retn
```
