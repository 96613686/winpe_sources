# CAggregateeDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)

- ea: `0x180004c2c`
- end: `0x180004d4e`
- name: `?LoadTypeInfoEntry@CAggregateeDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z`
- size: `290`
- prototype: `__int64 __fastcall(CAggregateeDispMgr *__hidden this, const struct _GUID *, const struct _GUID *, void *, int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180005310`
- `0x1800065a0`
- `0x1800072a0`
- `0x1800080d0`
- `0x180008834`
- `0x180009c20`
- `0x18000a94c`

## callees

- `0x180004c2c`
- `0x180012010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180004cdd`
- `KERNEL32!LocalAlloc` at `0x180004cdd`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180004c82`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180004c82`

## pseudocode

```c
__int64 __fastcall CAggregateeDispMgr::LoadTypeInfoEntry(
        CAggregateeDispMgr *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void *a4)
{
  __int128 v4; // xmm0
  GUID v6; // xmm1
  HRESULT v8; // edi
  __int64 v9; // rbx
  __int64 i; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  __int64 result; // rax
  int v14; // ecx
  GUID rguid; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+78h] [rbp+28h] BYREF
  ITypeLib *pptlib; // [rsp+80h] [rbp+30h] BYREF

  v4 = (__int128)*a3;
  v6 = *a2;
  pptlib = 0;
  v17 = 0;
  v16 = v4;
  rguid = v6;
  v8 = LoadRegTypeLib(&rguid, 1u, 0, 0x800u, &pptlib);
  if ( v8 < 0
    || (v8 = ((__int64 (__fastcall *)(ITypeLib *, __int128 *, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
               pptlib,
               &v16,
               &v17),
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib),
        v8 < 0) )
  {
LABEL_9:
    v9 = v17;
LABEL_10:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)v8;
  }
  else
  {
    v9 = v17;
    for ( i = *((_QWORD *)this + 2); i; i = *(_QWORD *)(i + 24) )
    {
      if ( *(_QWORD *)(i + 8) == v17 )
      {
        v8 = -2147467259;
        goto LABEL_10;
      }
    }
    v11 = LocalAlloc(0x40u, 0x20u);
    v12 = v11;
    if ( !v11 )
    {
      v8 = -2147024882;
      goto LABEL_9;
    }
    v11[1] = v9;
    v14 = *((_DWORD *)this + 2);
    *((_DWORD *)this + 2) = v14 + 1;
    *(_DWORD *)v11 = v14;
    v11[2] = a4;
    v11[3] = *((_QWORD *)this + 2);
    result = 0;
    *((_QWORD *)this + 2) = v12;
  }
  return result;
}

```

## disassembly

```asm
0x180004c2c  mov     [rsp-18h+arg_0], rbx
0x180004c31  mov     [rsp-18h+arg_18], rsi
0x180004c36  push    rbp
0x180004c37  push    rdi
0x180004c38  push    r14
0x180004c3a  mov     rbp, rsp
0x180004c3d  sub     rsp, 50h
0x180004c41  movups  xmm0, xmmword ptr [r8]
0x180004c45  xor     r8d, r8d; wVerMinor
0x180004c48  mov     r14, r9
0x180004c4b  movups  xmm1, xmmword ptr [rdx]
0x180004c4e  mov     rsi, rcx
0x180004c51  mov     [rbp+arg_10], 0
0x180004c59  lea     rax, [rbp+arg_10]
0x180004c5d  mov     [rbp+arg_8], 0
0x180004c65  lea     edx, [r8+1]; wVerMajor
0x180004c69  mov     [rsp+50h+pptlib], rax; pptlib
0x180004c6e  mov     r9d, 800h; lcid
0x180004c74  lea     rcx, [rbp+rguid]; rguid
0x180004c78  movdqu  [rbp+var_10], xmm0
0x180004c7d  movdqu  xmmword ptr [rbp+rguid.Data1], xmm1
0x180004c82  call    cs:__imp_LoadRegTypeLib
0x180004c88  mov     edi, eax
0x180004c8a  test    eax, eax
0x180004c8c  js      short loc_180004CF0
0x180004c8e  mov     rcx, [rbp+arg_10]
0x180004c92  lea     r8, [rbp+arg_8]
0x180004c96  lea     rdx, [rbp+var_10]
0x180004c9a  mov     rax, [rcx]
0x180004c9d  mov     rax, [rax+30h]
0x180004ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca6  mov     rcx, [rbp+arg_10]
0x180004caa  mov     edi, eax
0x180004cac  mov     rax, [rcx]
0x180004caf  mov     rax, [rax+10h]
0x180004cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb8  test    edi, edi
0x180004cba  js      short loc_180004CF0
0x180004cbc  mov     rbx, [rbp+arg_8]
0x180004cc0  mov     rax, [rsi+10h]
0x180004cc4  jmp     short loc_180004CD0
0x180004cc6  cmp     [rax+8], rbx
0x180004cca  jz      short loc_180004D1F
0x180004ccc  mov     rax, [rax+18h]
0x180004cd0  test    rax, rax
0x180004cd3  jnz     short loc_180004CC6
0x180004cd5  mov     edx, 20h ; ' '; uBytes
0x180004cda  lea     ecx, [rdx+20h]; uFlags
0x180004cdd  call    cs:__imp_LocalAlloc
0x180004ce3  mov     rdx, rax
0x180004ce6  test    rax, rax
0x180004ce9  jnz     short loc_180004D2B
0x180004ceb  mov     edi, 8007000Eh
0x180004cf0  mov     rbx, [rbp+arg_8]
0x180004cf4  test    rbx, rbx
0x180004cf7  jz      short loc_180004D08
0x180004cf9  mov     rdx, [rbx]
0x180004cfc  mov     rcx, rbx
0x180004cff  mov     rax, [rdx+10h]
0x180004d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d08  mov     eax, edi
0x180004d0a  lea     r11, [rsp+50h+var_s0]
0x180004d0f  mov     rbx, [r11+20h]
0x180004d13  mov     rsi, [r11+38h]
0x180004d17  mov     rsp, r11
0x180004d1a  pop     r14
0x180004d1c  pop     rdi
0x180004d1d  pop     rbp
0x180004d1e  retn
0x180004d1f  test    rax, rax
0x180004d22  jz      short loc_180004CD5
0x180004d24  mov     edi, 80004005h
0x180004d29  jmp     short loc_180004CF4
0x180004d2b  mov     [rax+8], rbx
0x180004d2f  mov     ecx, [rsi+8]
0x180004d32  lea     eax, [rcx+1]
0x180004d35  mov     [rsi+8], eax
0x180004d38  mov     [rdx], ecx
0x180004d3a  mov     [rdx+10h], r14
0x180004d3e  mov     rax, [rsi+10h]
0x180004d42  mov     [rdx+18h], rax
0x180004d46  xor     eax, eax
0x180004d48  mov     [rsi+10h], rdx
0x180004d4c  jmp     short loc_180004D0A
```
