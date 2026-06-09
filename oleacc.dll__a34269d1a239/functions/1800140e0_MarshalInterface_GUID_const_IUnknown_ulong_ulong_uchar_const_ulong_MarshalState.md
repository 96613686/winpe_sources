# MarshalInterface(_GUID const &,IUnknown *,ulong,ulong,uchar const * *,ulong *,MarshalState *)

- ea: `0x1800140e0`
- end: `0x18001430c`
- name: `?MarshalInterface@@YAJAEBU_GUID@@PEAUIUnknown@@KKPEAPEBEPEAKPEAVMarshalState@@@Z`
- size: `556`
- prototype: `__int64 __usercall@<rax>(IID *riid@<rcx>, LPUNKNOWN pUnk@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const unsigned __int8 **, unsigned int *, struct MarshalState *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013f50`

## callees

- `0x1800140e0`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180014203`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180014203`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180014255`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180014288`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800142a6`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800142e7`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180014255`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180014288`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800142a6`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800142e7`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001417a`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18001417a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001415e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001415e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014131`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014131`

## pseudocode

```c
HRESULT __fastcall MarshalInterface(
        IID *riid,
        LPUNKNOWN pUnk,
        __int64 a3,
        DWORD a4,
        const unsigned __int8 **a5,
        unsigned int *a6,
        struct MarshalState *a7)
{
  HRESULT result; // eax
  HRESULT v11; // ebx
  HRESULT HGlobalFromStream; // ebx
  LPSTREAM v13; // rdi
  int v14; // ebx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(LPSTREAM, __int128 *, __int64); // rax
  unsigned int v17; // ebx
  const unsigned __int8 *v18; // rax
  LPSTREAM v19; // rax
  LPSTREAM ppstm; // [rsp+30h] [rbp-71h] BYREF
  __int64 v21; // [rsp+38h] [rbp-69h]
  HGLOBAL phglobal; // [rsp+40h] [rbp-61h] BYREF
  __int128 v23; // [rsp+50h] [rbp-51h] BYREF
  __int128 v24; // [rsp+60h] [rbp-41h]
  __int128 v25; // [rsp+70h] [rbp-31h]
  __int128 v26; // [rsp+80h] [rbp-21h]
  __int128 v27; // [rsp+90h] [rbp-11h]

  ppstm = 0;
  result = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( result >= 0 )
  {
    if ( !ppstm )
      return -2147467259;
    v11 = CoMarshalInterface(ppstm, riid, pUnk, 0, 0, a4);
    if ( v11 < 0 )
    {
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return v11;
    }
    phglobal = 0;
    HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
    if ( HGlobalFromStream >= 0 && phglobal )
    {
      v13 = ppstm;
      v21 = 0;
      v14 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
      if ( v14 < 0 )
        goto LABEL_14;
      v15 = *(_QWORD *)v13;
      v23 = 0;
      v16 = *(__int64 (__fastcall **)(LPSTREAM, __int128 *, __int64))(v15 + 96);
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v14 = v16(v13, &v23, 1);
      if ( v14 < 0 )
      {
LABEL_14:
        CoReleaseMarshalData(ppstm);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return v14;
      }
      v17 = v24;
      if ( !(_DWORD)v24 )
      {
        CoReleaseMarshalData(ppstm);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return -2147467259;
      }
      v18 = (const unsigned __int8 *)GlobalLock(phglobal);
      if ( v18 )
      {
        *a5 = v18;
        v19 = ppstm;
        *a6 = v17;
        *(_QWORD *)a7 = v19;
        *((_QWORD *)a7 + 1) = phglobal;
        return 0;
      }
      CoReleaseMarshalData(ppstm);
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return -2147467259;
    }
    v21 = 0;
    (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
    CoReleaseMarshalData(ppstm);
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    result = -2147467259;
    if ( HGlobalFromStream < 0 )
      return HGlobalFromStream;
  }
  return result;
}

```

## disassembly

```asm
0x1800140e0  mov     [rsp-8+arg_10], rbx
0x1800140e5  push    rbp
0x1800140e6  push    rsi
0x1800140e7  push    rdi
0x1800140e8  push    r12
0x1800140ea  push    r13
0x1800140ec  push    r14
0x1800140ee  push    r15
0x1800140f0  lea     rbp, [rsp-0Fh]
0x1800140f5  sub     rsp, 0B0h
0x1800140fc  mov     rax, cs:__security_cookie
0x180014103  xor     rax, rsp
0x180014106  mov     [rbp+3Fh+var_40], rax
0x18001410a  mov     r14, [rbp+3Fh+arg_30]
0x18001410e  lea     r8, [rbp+3Fh+ppstm]; ppstm
0x180014112  mov     r15, [rbp+3Fh+arg_20]
0x180014116  mov     rdi, rdx
0x180014119  mov     r12, [rbp+3Fh+arg_28]
0x18001411d  mov     rbx, rcx
0x180014120  xor     r13d, r13d
0x180014123  mov     edx, 1; fDeleteOnRelease
0x180014128  xor     ecx, ecx; hGlobal
0x18001412a  mov     [rbp+3Fh+ppstm], r13
0x18001412e  mov     esi, r9d
0x180014131  call    cs:__imp_CreateStreamOnHGlobal
0x180014137  test    eax, eax
0x180014139  js      loc_18001422A
0x18001413f  mov     rcx, [rbp+3Fh+ppstm]; pStm
0x180014143  test    rcx, rcx
0x180014146  jz      loc_1800142BC
0x18001414c  mov     [rsp+0E0h+mshlflags], esi; mshlflags
0x180014150  xor     r9d, r9d; dwDestContext
0x180014153  mov     r8, rdi; pUnk
0x180014156  mov     [rsp+0E0h+pvDestContext], r13; pvDestContext
0x18001415b  mov     rdx, rbx; riid
0x18001415e  call    cs:__imp_CoMarshalInterface
0x180014164  mov     rcx, [rbp+3Fh+ppstm]; pstm
0x180014168  mov     ebx, eax
0x18001416a  test    eax, eax
0x18001416c  js      loc_180014274
0x180014172  lea     rdx, [rbp+3Fh+phglobal]; phglobal
0x180014176  mov     [rbp+3Fh+phglobal], r13
0x18001417a  call    cs:__imp_GetHGlobalFromStream
0x180014180  mov     ebx, eax
0x180014182  test    eax, eax
0x180014184  js      loc_1800142C6
0x18001418a  cmp     [rbp+3Fh+phglobal], r13
0x18001418e  jz      loc_1800142C6
0x180014194  mov     rdi, [rbp+3Fh+ppstm]
0x180014198  xor     r9d, r9d
0x18001419b  xor     r8d, r8d
0x18001419e  mov     [rbp+3Fh+var_A8], r13
0x1800141a2  mov     edx, r13d
0x1800141a5  mov     rcx, rdi
0x1800141a8  mov     rax, [rdi]
0x1800141ab  mov     rax, [rax+28h]
0x1800141af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141b4  mov     ebx, eax
0x1800141b6  test    eax, eax
0x1800141b8  js      loc_180014284
0x1800141be  mov     rax, [rdi]
0x1800141c1  lea     rdx, [rbp+3Fh+var_90]
0x1800141c5  xorps   xmm0, xmm0
0x1800141c8  mov     r8d, 1
0x1800141ce  mov     rcx, rdi
0x1800141d1  movups  [rbp+3Fh+var_90], xmm0
0x1800141d5  mov     rax, [rax+60h]
0x1800141d9  movups  [rbp+3Fh+var_80], xmm0
0x1800141dd  movups  [rbp+3Fh+var_70], xmm0
0x1800141e1  movups  [rbp+3Fh+var_60], xmm0
0x1800141e5  movups  [rbp+3Fh+var_50], xmm0
0x1800141e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141ee  mov     ebx, eax
0x1800141f0  test    eax, eax
0x1800141f2  js      loc_180014284
0x1800141f8  mov     ebx, dword ptr [rbp+3Fh+var_80]
0x1800141fb  test    ebx, ebx
0x1800141fd  jz      short loc_180014251
0x1800141ff  mov     rcx, [rbp+3Fh+phglobal]; hMem
0x180014203  call    cs:__imp_GlobalLock
0x180014209  test    rax, rax
0x18001420c  jz      loc_1800142A2
0x180014212  mov     [r15], rax
0x180014215  mov     rax, [rbp+3Fh+ppstm]
0x180014219  mov     [r12], ebx
0x18001421d  mov     [r14], rax
0x180014220  mov     rax, [rbp+3Fh+phglobal]
0x180014224  mov     [r14+8], rax
0x180014228  xor     eax, eax
0x18001422a  mov     rcx, [rbp+3Fh+var_40]
0x18001422e  xor     rcx, rsp; StackCookie
0x180014231  call    __security_check_cookie
0x180014236  mov     rbx, [rsp+0E0h+arg_10]
0x18001423e  add     rsp, 0B0h
0x180014245  pop     r15
0x180014247  pop     r14
0x180014249  pop     r13
0x18001424b  pop     r12
0x18001424d  pop     rdi
0x18001424e  pop     rsi
0x18001424f  pop     rbp
0x180014250  retn
0x180014251  mov     rcx, [rbp+3Fh+ppstm]; pStm
0x180014255  call    cs:__imp_CoReleaseMarshalData
0x18001425b  mov     rcx, [rbp+3Fh+ppstm]
0x18001425f  mov     rax, [rcx]
0x180014262  mov     rax, [rax+10h]
0x180014266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001426b  mov     ebx, 80004005h
0x180014270  mov     eax, ebx
0x180014272  jmp     short loc_18001422A
0x180014274  mov     rdx, [rcx]
0x180014277  mov     rax, [rdx+10h]
0x18001427b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014280  mov     eax, ebx
0x180014282  jmp     short loc_18001422A
0x180014284  mov     rcx, [rbp+3Fh+ppstm]; pStm
0x180014288  call    cs:__imp_CoReleaseMarshalData
0x18001428e  mov     rcx, [rbp+3Fh+ppstm]
0x180014292  mov     rax, [rcx]
0x180014295  mov     rax, [rax+10h]
0x180014299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001429e  mov     eax, ebx
0x1800142a0  jmp     short loc_18001422A
0x1800142a2  mov     rcx, [rbp+3Fh+ppstm]; pStm
0x1800142a6  call    cs:__imp_CoReleaseMarshalData
0x1800142ac  mov     rcx, [rbp+3Fh+ppstm]
0x1800142b0  mov     rax, [rcx]
0x1800142b3  mov     rax, [rax+10h]
0x1800142b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142bc  mov     eax, 80004005h
0x1800142c1  jmp     loc_18001422A
0x1800142c6  mov     rcx, [rbp+3Fh+ppstm]
0x1800142ca  xor     r9d, r9d
0x1800142cd  xor     r8d, r8d
0x1800142d0  mov     [rbp+3Fh+var_A8], r13
0x1800142d4  mov     rdx, r13
0x1800142d7  mov     rax, [rcx]
0x1800142da  mov     rax, [rax+28h]
0x1800142de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e3  mov     rcx, [rbp+3Fh+ppstm]; pStm
0x1800142e7  call    cs:__imp_CoReleaseMarshalData
0x1800142ed  mov     rcx, [rbp+3Fh+ppstm]
0x1800142f1  mov     rax, [rcx]
0x1800142f4  mov     rax, [rax+10h]
0x1800142f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142fd  test    ebx, ebx
0x1800142ff  mov     eax, 80004005h
0x180014304  cmovs   eax, ebx
0x180014307  jmp     loc_18001422A
```
