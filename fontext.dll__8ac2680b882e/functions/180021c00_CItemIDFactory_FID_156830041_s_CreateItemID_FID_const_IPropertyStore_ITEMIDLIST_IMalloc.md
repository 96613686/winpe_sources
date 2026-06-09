# CItemIDFactory<FID,156830041>::s_CreateItemID(FID const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)

- ea: `0x180021c00`
- end: `0x180021d43`
- name: `?s_CreateItemID@?$CItemIDFactory@UFID@@$0JFJAJFJ@@@SAJPEFBUFID@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(void *Src, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021954`
- `0x1800220b4`

## callees

- `0x180021c00`
- `0x180031032`
- `0x18003104a`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d2a`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<FID,156830041>::s_CreateItemID(
        void *Src,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _QWORD *a3,
        __int64 a4)
{
  unsigned int v4; // eax
  int v7; // ebx
  __int16 v8; // si
  size_t v9; // rdi
  char *v10; // rax
  char *v11; // rbx
  __int64 v13; // [rsp+58h] [rbp+38h] BYREF
  void *Srca; // [rsp+60h] [rbp+40h] BYREF
  unsigned int Size; // [rsp+68h] [rbp+48h] BYREF
  int Size_4; // [rsp+6Ch] [rbp+4Ch]

  Size_4 = HIDWORD(a4);
  v4 = 0;
  *a3 = 0;
  Srca = 0;
  Size = 0;
  if ( a2 )
  {
    v13 = 0;
    v7 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v13);
    if ( v7 < 0 )
      return (unsigned int)v7;
    v7 = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v13 + 40LL))(v13, &Srca, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v7 < 0 )
      return (unsigned int)v7;
    v4 = Size;
  }
  v8 = v4 + 2806;
  v9 = v4 + 2804 + 10LL;
  if ( v9 <= 0x10001 && (v10 = (char *)CoTaskMemAlloc(v4 + 2804 + 10LL), (v11 = v10) != 0) )
  {
    memset_0(v10, 0, v9);
    *((_WORD *)v11 + 2) = v8;
    *(_WORD *)v11 = v9 - 2;
    *(_DWORD *)(v11 + 6) = 156830041;
    *((_WORD *)v11 + 5) = Size;
    *((_WORD *)v11 + 6) = 2796;
    if ( Src )
      memcpy_0(v11 + 14, Src, 0xAECu);
    if ( Srca )
      memcpy_0(v11 + 2810, Srca, Size);
    *a3 = v11;
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
  }
  CoTaskMemFree(Srca);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021c00  mov     [rsp-28h+arg_0], rbx
0x180021c05  mov     [rsp-28h+Size], r9
0x180021c0a  push    rbp
0x180021c0b  push    rsi
0x180021c0c  push    rdi
0x180021c0d  push    r14
0x180021c0f  push    r15
0x180021c11  mov     rbp, rsp
0x180021c14  sub     rsp, 20h
0x180021c18  xor     eax, eax
0x180021c1a  mov     qword ptr [r8], 0
0x180021c21  mov     [rbp+Src], 0
0x180021c29  mov     r14, r8
0x180021c2c  mov     dword ptr [rbp+Size], eax
0x180021c2f  mov     r9, rdx
0x180021c32  mov     r15, rcx
0x180021c35  test    rdx, rdx
0x180021c38  jz      short loc_180021C96
0x180021c3a  mov     [rbp+arg_8], rax
0x180021c3e  lea     r8, [rbp+arg_8]
0x180021c42  mov     rax, [rdx]
0x180021c45  mov     rcx, r9
0x180021c48  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180021c4f  mov     rax, [rax]
0x180021c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c57  mov     ebx, eax
0x180021c59  test    eax, eax
0x180021c5b  js      loc_180021D30
0x180021c61  mov     rcx, [rbp+arg_8]
0x180021c65  lea     r8, [rbp+Size]
0x180021c69  lea     rdx, [rbp+Src]
0x180021c6d  mov     rax, [rcx]
0x180021c70  mov     rax, [rax+28h]
0x180021c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c79  mov     rcx, [rbp+arg_8]
0x180021c7d  mov     ebx, eax
0x180021c7f  mov     rax, [rcx]
0x180021c82  mov     rax, [rax+10h]
0x180021c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c8b  test    ebx, ebx
0x180021c8d  js      loc_180021D30
0x180021c93  mov     eax, dword ptr [rbp+Size]
0x180021c96  lea     esi, [rax+0AF4h]
0x180021c9c  add     rsi, 2
0x180021ca0  lea     rdi, [rsi+8]
0x180021ca4  cmp     rdi, 10001h
0x180021cab  ja      short loc_180021D21
0x180021cad  mov     rcx, rdi; cb
0x180021cb0  call    cs:__imp_CoTaskMemAlloc
0x180021cb6  mov     rbx, rax
0x180021cb9  test    rax, rax
0x180021cbc  jz      short loc_180021D21
0x180021cbe  mov     r8, rdi; Size
0x180021cc1  xor     edx, edx; Val
0x180021cc3  mov     rcx, rax; void *
0x180021cc6  call    memset_0
0x180021ccb  mov     [rbx+4], si
0x180021ccf  sub     di, 2
0x180021cd3  mov     [rbx], di
0x180021cd6  mov     r8d, 0AECh; Size
0x180021cdc  mov     dword ptr [rbx+6], 9590959h
0x180021ce3  movzx   ecx, word ptr [rbp+Size]
0x180021ce7  mov     [rbx+0Ah], cx
0x180021ceb  mov     [rbx+0Ch], r8w
0x180021cf0  test    r15, r15
0x180021cf3  jz      short loc_180021D01
0x180021cf5  lea     rcx, [rbx+0Eh]; void *
0x180021cf9  mov     rdx, r15; Src
0x180021cfc  call    memcpy_0
0x180021d01  mov     rdx, [rbp+Src]; Src
0x180021d05  test    rdx, rdx
0x180021d08  jz      short loc_180021D1A
0x180021d0a  mov     r8d, dword ptr [rbp+Size]; Size
0x180021d0e  lea     rcx, [rbx+0AFAh]; void *
0x180021d15  call    memcpy_0
0x180021d1a  mov     [r14], rbx
0x180021d1d  xor     ebx, ebx
0x180021d1f  jmp     short loc_180021D26
0x180021d21  mov     ebx, 8007000Eh
0x180021d26  mov     rcx, [rbp+Src]; pv
0x180021d2a  call    cs:__imp_CoTaskMemFree
0x180021d30  mov     eax, ebx
0x180021d32  mov     rbx, [rsp+20h+arg_0]
0x180021d37  add     rsp, 20h
0x180021d3b  pop     r15
0x180021d3d  pop     r14
0x180021d3f  pop     rdi
0x180021d40  pop     rsi
0x180021d41  pop     rbp
0x180021d42  retn
```
