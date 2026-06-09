# CImpIColumnsInfo::GetColumnInfo(unsigned __int64 *,tagDBCOLUMNINFO * *,ushort * *)

- ea: `0x1800119d0`
- end: `0x180011d02`
- name: `?GetColumnInfo@CImpIColumnsInfo@@UEAAJPEA_KPEAPEAUtagDBCOLUMNINFO@@PEAPEAG@Z`
- size: `818`
- prototype: `__int64 __fastcall(CImpIColumnsInfo *__hidden this, unsigned __int64 *, struct tagDBCOLUMNINFO **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180003c38`
- `0x1800041b4`
- `0x1800041ec`
- `0x180004224`
- `0x1800042f4`
- `0x180004338`
- `0x180004384`
- `0x1800119d0`
- `0x180016584`
- `0x18002f092`
- `0x18002f0aa`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011a20`
- `KERNEL32!GetCurrentThreadId` at `0x180011a20`
- `KERNEL32!LeaveCriticalSection` at `0x180011cac`
- `KERNEL32!LeaveCriticalSection` at `0x180011ce2`
- `KERNEL32!LeaveCriticalSection` at `0x180011cac`
- `KERNEL32!LeaveCriticalSection` at `0x180011ce2`
- `ole32!CoTaskMemFree` at `0x180011adf`
- `ole32!CoTaskMemFree` at `0x180011adf`
- `ole32!CoTaskMemAlloc` at `0x180011a98`
- `ole32!CoTaskMemAlloc` at `0x180011ac3`
- `ole32!CoTaskMemAlloc` at `0x180011a98`
- `ole32!CoTaskMemAlloc` at `0x180011ac3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011a46`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180011a46`
- `MSDART!UMSEnterCSWraper` at `0x180011a0b`
- `MSDART!UMSEnterCSWraper` at `0x180011a0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsInfo::GetColumnInfo(
        CImpIColumnsInfo *this,
        unsigned __int64 *a2,
        struct tagDBCOLUMNINFO **a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // r12
  struct tagDBCOLUMNINFO **v5; // rbx
  __int64 v8; // rdi
  unsigned __int16 v9; // r14
  struct tagDBCOLUMNINFO *v10; // rbp
  int v11; // ecx
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  CMetaData *v14; // r13
  char *v15; // rdi
  CMetaData *v16; // rcx
  unsigned __int16 *Name; // rcx
  __int16 v18; // r9
  __int64 v19; // rax
  size_t v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned int Ordinal; // eax
  __int64 v23; // r10
  unsigned int Flags; // eax
  __int64 v25; // r10
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // dx
  __int64 v28; // r10
  __int64 Size; // rax
  unsigned __int16 Type; // ax
  __int64 v31; // r10
  unsigned __int16 v32; // dx
  unsigned __int8 Scale; // al
  __int64 v34; // r10
  unsigned __int16 v35; // dx
  unsigned __int8 Precision; // al
  __int64 v37; // r10
  __int64 v38; // r11
  bool v39; // zf
  __int64 v40; // rcx
  unsigned int v42; // ebx
  __int64 v43; // rcx
  __int64 v44; // [rsp+20h] [rbp-58h]

  v4 = a4;
  v5 = a3;
  v8 = *((_QWORD *)this + 3) + 128LL;
  v44 = v8;
  UMSEnterCSWraper(v8);
  v9 = 0;
  if ( !*(_DWORD *)(v8 + 12) )
    *(_DWORD *)(v8 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a2 )
    *a2 = 0;
  if ( v5 )
    *v5 = 0;
  if ( v4 )
    *v4 = 0;
  if ( !a2 || !v5 || !v4 )
  {
    v11 = -2147024809;
    goto LABEL_33;
  }
  v10 = (struct tagDBCOLUMNINFO *)CoTaskMemAlloc(80LL * *(unsigned int *)(*((_QWORD *)this + 3) + 152LL));
  if ( !v10 )
  {
LABEL_13:
    v11 = -2147024882;
LABEL_33:
    v42 = Exit(v11, 0);
    --*(_DWORD *)(v8 + 16);
    v39 = (*(_DWORD *)(v8 + 12))-- == 1;
    if ( v39 )
      *(_DWORD *)(v8 + 8) = -1;
    v43 = *(_QWORD *)v8;
    --*(_DWORD *)(v43 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v43 + 8));
    return v42;
  }
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *(unsigned int *)(*((_QWORD *)this + 3) + 268LL));
  if ( !v12 )
  {
    CoTaskMemFree(v10);
    goto LABEL_13;
  }
  v13 = *((_QWORD *)this + 3);
  v14 = (CMetaData *)(v13 + 304);
  memset_0(v10, 0, 80LL * *(unsigned int *)(v13 + 152));
  if ( *(_DWORD *)(*((_QWORD *)this + 3) + 152LL) )
  {
    v15 = (char *)v12;
    do
    {
      if ( CMetaData::mdGetName(v14, v9) )
      {
        Name = CMetaData::mdGetName(v16, v9);
        v19 = -1;
        do
          ++v19;
        while ( Name[v19] != v18 );
        v20 = 2LL * (unsigned int)(v19 + 1);
        v21 = CMetaData::mdGetName(v14, v9);
        memcpy_0(v15, v21, v20);
        v10[v9].pwszName = (LPOLESTR)v15;
        v15 += v20;
      }
      Ordinal = CMetaData::mdGetOrdinal(v14, v9);
      *(&v10->iOrdinal + v23) = Ordinal;
      Flags = CMetaData::mdGetFlags(v14, v9);
      *(&v10->dwFlags + 2 * v25) = Flags;
      if ( CMetaData::mdGetSize(v14, v26) == -1 )
        Size = -1;
      else
        Size = CMetaData::mdGetSize(v14, v27);
      *(&v10->ulColumnSize + v28) = Size;
      Type = CMetaData::mdGetType(v14, v9);
      *(&v10->wType + 4 * v31) = Type;
      Scale = CMetaData::mdGetScale(v14, v32);
      *(&v10->bScale + 8 * v34) = Scale;
      Precision = CMetaData::mdGetPrecision(v14, v35);
      *(&v10->bPrecision + 8 * v37) = Precision;
      if ( !*(_DWORD *)(9648 * v38 + *((_QWORD *)v14 + 4) + 2160) )
      {
        *(&v10->columnid.eKind + 2 * v37) = 6;
        *(union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D *)((char *)&v10->columnid.uGuid + 8 * v37) = *(union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D *)(9648 * v38 + *((_QWORD *)v14 + 4) + 2144);
      }
      ++v9;
    }
    while ( (unsigned int)v9 < *(_DWORD *)(*((_QWORD *)this + 3) + 152LL) );
    v8 = v44;
    v4 = a4;
    v5 = a3;
  }
  *v5 = v10;
  *v4 = v12;
  *a2 = *(unsigned __int16 *)(*((_QWORD *)this + 3) + 306LL);
  --*(_DWORD *)(v8 + 16);
  v39 = (*(_DWORD *)(v8 + 12))-- == 1;
  if ( v39 )
    *(_DWORD *)(v8 + 8) = -1;
  v40 = *(_QWORD *)v8;
  --*(_DWORD *)(v40 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v40 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800119d0  mov     [rsp+arg_18], r9
0x1800119d5  mov     [rsp+arg_10], r8
0x1800119da  mov     [rsp+arg_8], rdx
0x1800119df  push    rbx
0x1800119e0  push    rbp
0x1800119e1  push    rsi
0x1800119e2  push    rdi
0x1800119e3  push    r12
0x1800119e5  push    r13
0x1800119e7  push    r14
0x1800119e9  push    r15
0x1800119eb  sub     rsp, 38h
0x1800119ef  mov     r12, r9
0x1800119f2  mov     rbx, r8
0x1800119f5  mov     rsi, rdx
0x1800119f8  mov     r15, rcx
0x1800119fb  mov     rdi, [rcx+18h]
0x1800119ff  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011a03  mov     [rsp+78h+var_58], rdi
0x180011a08  mov     rcx, rdi
0x180011a0b  call    cs:__imp_UMSEnterCSWraper
0x180011a12  nop     dword ptr [rax+rax+00h]
0x180011a17  xor     r14d, r14d
0x180011a1a  cmp     [rdi+0Ch], r14d
0x180011a1e  jnz     short loc_180011A2F
0x180011a20  call    cs:__imp_GetCurrentThreadId
0x180011a27  nop     dword ptr [rax+rax+00h]
0x180011a2c  mov     [rdi+8], eax
0x180011a2f  mov     eax, 1
0x180011a34  add     [rdi+0Ch], eax
0x180011a37  add     [rdi+10h], eax
0x180011a3a  mov     [rsp+78h+arg_0], rdi
0x180011a42  xor     edx, edx; perrinfo
0x180011a44  xor     ecx, ecx; dwReserved
0x180011a46  call    cs:__imp_SetErrorInfo
0x180011a4d  nop     dword ptr [rax+rax+00h]
0x180011a52  test    rsi, rsi
0x180011a55  jz      short loc_180011A5A
0x180011a57  mov     [rsi], r14
0x180011a5a  test    rbx, rbx
0x180011a5d  jz      short loc_180011A62
0x180011a5f  mov     [rbx], r14
0x180011a62  test    r12, r12
0x180011a65  jz      short loc_180011A6B
0x180011a67  mov     [r12], r14
0x180011a6b  test    rsi, rsi
0x180011a6e  jz      loc_180011CBC
0x180011a74  test    rbx, rbx
0x180011a77  jz      loc_180011CBC
0x180011a7d  test    r12, r12
0x180011a80  jz      loc_180011CBC
0x180011a86  mov     rax, [r15+18h]
0x180011a8a  mov     ecx, [rax+98h]
0x180011a90  lea     rcx, [rcx+rcx*4]
0x180011a94  shl     rcx, 4; cb
0x180011a98  call    cs:__imp_CoTaskMemAlloc
0x180011a9f  nop     dword ptr [rax+rax+00h]
0x180011aa4  mov     rbp, rax
0x180011aa7  test    rax, rax
0x180011aaa  jnz     short loc_180011AB6
0x180011aac  mov     ecx, 8007000Eh
0x180011ab1  jmp     loc_180011CC1
0x180011ab6  mov     rax, [r15+18h]
0x180011aba  mov     ecx, [rax+10Ch]
0x180011ac0  add     rcx, rcx; cb
0x180011ac3  call    cs:__imp_CoTaskMemAlloc
0x180011aca  nop     dword ptr [rax+rax+00h]
0x180011acf  mov     rsi, rax
0x180011ad2  mov     [rsp+78h+var_50], rax
0x180011ad7  mov     rcx, rbp; void *
0x180011ada  test    rax, rax
0x180011add  jnz     short loc_180011AED
0x180011adf  call    cs:__imp_CoTaskMemFree
0x180011ae6  nop     dword ptr [rax+rax+00h]
0x180011aeb  jmp     short loc_180011AAC
0x180011aed  mov     rax, [r15+18h]
0x180011af1  lea     r13, [rax+130h]
0x180011af8  mov     eax, [rax+98h]
0x180011afe  lea     r8, [rax+rax*4]
0x180011b02  shl     r8, 4; Size
0x180011b06  xor     edx, edx; Val
0x180011b08  call    memset_0
0x180011b0d  mov     [rsp+78h+arg_0], rsi
0x180011b15  mov     rax, [r15+18h]
0x180011b19  or      esi, 0FFFFFFFFh
0x180011b1c  xor     r9d, r9d
0x180011b1f  cmp     [rax+98h], r9d
0x180011b26  jbe     loc_180011C75
0x180011b2c  mov     rdi, [rsp+78h+arg_0]
0x180011b34  lea     r12d, [r9+1]
0x180011b38  movzx   edx, r14w; unsigned __int16
0x180011b3c  mov     rcx, r13; this
0x180011b3f  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180011b44  test    rax, rax
0x180011b47  jz      short loc_180011B98
0x180011b49  movzx   edx, r14w; unsigned __int16
0x180011b4d  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180011b52  mov     rcx, rax
0x180011b55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011b59  inc     rax
0x180011b5c  cmp     [rcx+rax*2], r9w
0x180011b61  jnz     short loc_180011B59
0x180011b63  lea     ebx, [rax+1]
0x180011b66  add     rbx, rbx
0x180011b69  movzx   edx, r14w; unsigned __int16
0x180011b6d  mov     rcx, r13; this
0x180011b70  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180011b75  mov     rdx, rax; Src
0x180011b78  mov     r8, rbx; Size
0x180011b7b  mov     rcx, rdi; void *
0x180011b7e  call    memcpy_0
0x180011b83  movzx   r11d, r14w
0x180011b87  lea     rax, [r11+r11*4]
0x180011b8b  add     rax, rax
0x180011b8e  mov     [rbp+rax*8+0], rdi
0x180011b93  add     rdi, rbx
0x180011b96  jmp     short loc_180011B9C
0x180011b98  movzx   r11d, r14w
0x180011b9c  lea     r10, [r11+r11*4]
0x180011ba0  add     r10, r10
0x180011ba3  movzx   edx, r14w; unsigned __int16
0x180011ba7  mov     rcx, r13; this
0x180011baa  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x180011baf  mov     edx, eax
0x180011bb1  mov     [rbp+r10*8+10h], rdx
0x180011bb6  movzx   edx, r14w; unsigned __int16
0x180011bba  mov     rcx, r13; this
0x180011bbd  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180011bc2  mov     [rbp+r10*8+18h], eax
0x180011bc7  mov     rcx, r13; this
0x180011bca  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x180011bcf  cmp     eax, esi
0x180011bd1  jnz     short loc_180011BD9
0x180011bd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011bd7  jmp     short loc_180011BE3
0x180011bd9  mov     rcx, r13; this
0x180011bdc  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x180011be1  mov     eax, eax
0x180011be3  mov     [rbp+r10*8+20h], rax
0x180011be8  movzx   edx, r14w; unsigned __int16
0x180011bec  mov     rcx, r13; this
0x180011bef  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180011bf4  mov     [rbp+r10*8+28h], ax
0x180011bfa  mov     rcx, r13; this
0x180011bfd  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x180011c02  mov     [rbp+r10*8+2Bh], al
0x180011c07  mov     rcx, r13; this
0x180011c0a  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x180011c0f  mov     [rbp+r10*8+2Ah], al
0x180011c14  imul    rcx, r11, 25B0h
0x180011c1b  mov     rax, [r13+20h]
0x180011c1f  xor     r9d, r9d
0x180011c22  cmp     [rcx+rax+870h], r9d
0x180011c2a  jnz     short loc_180011C48
0x180011c2c  mov     dword ptr [rbp+r10*8+40h], 6
0x180011c35  mov     rax, [r13+20h]
0x180011c39  movups  xmm0, xmmword ptr [rcx+rax+860h]
0x180011c41  movdqu  xmmword ptr [rbp+r10*8+30h], xmm0
0x180011c48  add     r14w, r12w
0x180011c4c  mov     rcx, [r15+18h]
0x180011c50  movzx   eax, r14w
0x180011c54  cmp     eax, [rcx+98h]
0x180011c5a  jb      loc_180011B38
0x180011c60  mov     rdi, [rsp+78h+var_58]
0x180011c65  mov     r12, [rsp+78h+arg_18]
0x180011c6d  mov     rbx, [rsp+78h+arg_10]
0x180011c75  mov     [rbx], rbp
0x180011c78  mov     rax, [rsp+78h+var_50]
0x180011c7d  mov     [r12], rax
0x180011c81  mov     rax, [r15+18h]
0x180011c85  movzx   ecx, word ptr [rax+132h]
0x180011c8c  mov     rax, [rsp+78h+arg_8]
0x180011c94  mov     [rax], rcx
0x180011c97  add     [rdi+10h], esi
0x180011c9a  add     [rdi+0Ch], esi
0x180011c9d  jnz     short loc_180011CA2
0x180011c9f  mov     [rdi+8], esi
0x180011ca2  mov     rcx, [rdi]
0x180011ca5  dec     dword ptr [rcx+30h]
0x180011ca8  add     rcx, 8; lpCriticalSection
0x180011cac  call    cs:__imp_LeaveCriticalSection
0x180011cb3  nop     dword ptr [rax+rax+00h]
0x180011cb8  xor     eax, eax
0x180011cba  jmp     short loc_180011CF0
0x180011cbc  mov     ecx, 80070057h; int
0x180011cc1  xor     edx, edx; unsigned int
0x180011cc3  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180011cc8  mov     ebx, eax
0x180011cca  or      esi, 0FFFFFFFFh
0x180011ccd  add     [rdi+10h], esi
0x180011cd0  add     [rdi+0Ch], esi
0x180011cd3  jnz     short loc_180011CD8
0x180011cd5  mov     [rdi+8], esi
0x180011cd8  mov     rcx, [rdi]
0x180011cdb  dec     dword ptr [rcx+30h]
0x180011cde  add     rcx, 8; lpCriticalSection
0x180011ce2  call    cs:__imp_LeaveCriticalSection
0x180011ce9  nop     dword ptr [rax+rax+00h]
0x180011cee  mov     eax, ebx
0x180011cf0  add     rsp, 38h
0x180011cf4  pop     r15
0x180011cf6  pop     r14
0x180011cf8  pop     r13
0x180011cfa  pop     r12
0x180011cfc  pop     rdi
0x180011cfd  pop     rsi
0x180011cfe  pop     rbp
0x180011cff  pop     rbx
0x180011d00  retn
```
