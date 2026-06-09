# CItemIDFactory<tagCSCDRIVESDATA,153491801>::s_CreateItemID(tagCSCDRIVESDATA const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180035010`
- end: `0x180035161`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagCSCDRIVESDATA@@$0JCGBJFJ@@@SAJPEFBUtagCSCDRIVESDATA@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(_DWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033698`

## callees

- `0x180035010`
- `0x18004c61e`
- `0x18004c636`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035148`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagCSCDRIVESDATA,153491801>::s_CreateItemID(
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
      *(_DWORD *)(v10 + 6) = 153491801;
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
0x180035010  mov     [rsp-28h+arg_0], rbx
0x180035015  push    rbp
0x180035016  push    rsi
0x180035017  push    rdi
0x180035018  push    r14
0x18003501a  push    r15
0x18003501c  mov     rbp, rsp
0x18003501f  sub     rsp, 30h
0x180035023  xor     eax, eax
0x180035025  mov     qword ptr [r8], 0
0x18003502c  mov     [rbp+Src], 0
0x180035034  mov     rdi, r9
0x180035037  mov     dword ptr [rbp+Size], eax
0x18003503a  mov     r15, r8
0x18003503d  mov     r10, rdx
0x180035040  mov     r14, rcx
0x180035043  test    rdx, rdx
0x180035046  jz      short loc_1800350A4
0x180035048  mov     [rbp+arg_10], rax
0x18003504c  lea     r8, [rbp+arg_10]
0x180035050  mov     rax, [rdx]
0x180035053  mov     rcx, r10
0x180035056  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18003505d  mov     rax, [rax]
0x180035060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035065  mov     ebx, eax
0x180035067  test    eax, eax
0x180035069  js      loc_18003514E
0x18003506f  mov     rcx, [rbp+arg_10]
0x180035073  lea     r8, [rbp+Size]
0x180035077  lea     rdx, [rbp+Src]
0x18003507b  mov     rax, [rcx]
0x18003507e  mov     rax, [rax+28h]
0x180035082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035087  mov     rcx, [rbp+arg_10]
0x18003508b  mov     ebx, eax
0x18003508d  mov     rax, [rcx]
0x180035090  mov     rax, [rax+10h]
0x180035094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035099  test    ebx, ebx
0x18003509b  js      loc_18003514E
0x1800350a1  mov     eax, dword ptr [rbp+Size]
0x1800350a4  lea     esi, [rax+0Ch]
0x1800350a7  add     rsi, 2
0x1800350ab  test    rdi, rdi
0x1800350ae  jz      short loc_180035107
0x1800350b0  mov     rax, [rdi]
0x1800350b3  mov     rdx, rsi
0x1800350b6  mov     rcx, rdi
0x1800350b9  mov     rax, [rax+18h]
0x1800350bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350c2  mov     rbx, rax
0x1800350c5  test    rbx, rbx
0x1800350c8  jz      short loc_18003513F
0x1800350ca  mov     dword ptr [rbx+6], 9261959h
0x1800350d1  movzx   eax, word ptr [rbp+Size]
0x1800350d5  mov     [rbx+0Ah], ax
0x1800350d9  mov     word ptr [rbx+0Ch], 4
0x1800350df  test    r14, r14
0x1800350e2  jz      short loc_1800350EA
0x1800350e4  mov     eax, [r14]
0x1800350e7  mov     [rbx+0Eh], eax
0x1800350ea  mov     rdx, [rbp+Src]; Src
0x1800350ee  test    rdx, rdx
0x1800350f1  jz      short loc_180035100
0x1800350f3  mov     r8d, dword ptr [rbp+Size]; Size
0x1800350f7  lea     rcx, [rbx+12h]; void *
0x1800350fb  call    memcpy_0
0x180035100  mov     [r15], rbx
0x180035103  xor     ebx, ebx
0x180035105  jmp     short loc_180035144
0x180035107  lea     rdi, [rsi+8]
0x18003510b  cmp     rdi, 10001h
0x180035112  ja      short loc_18003513F
0x180035114  mov     rcx, rdi; cb
0x180035117  call    cs:__imp_CoTaskMemAlloc
0x18003511d  mov     rbx, rax
0x180035120  test    rax, rax
0x180035123  jz      short loc_1800350C5
0x180035125  mov     r8, rdi; Size
0x180035128  xor     edx, edx; Val
0x18003512a  mov     rcx, rax; void *
0x18003512d  call    memset_0
0x180035132  sub     di, 2
0x180035136  mov     [rbx+4], si
0x18003513a  mov     [rbx], di
0x18003513d  jmp     short loc_1800350CA
0x18003513f  mov     ebx, 8007000Eh
0x180035144  mov     rcx, [rbp+Src]; pv
0x180035148  call    cs:__imp_CoTaskMemFree
0x18003514e  mov     eax, ebx
0x180035150  mov     rbx, [rsp+30h+arg_0]
0x180035155  add     rsp, 30h
0x180035159  pop     r15
0x18003515b  pop     r14
0x18003515d  pop     rdi
0x18003515e  pop     rsi
0x18003515f  pop     rbp
0x180035160  retn
```
