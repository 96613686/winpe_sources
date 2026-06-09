# GetURLMoniker(IUnknown *,ushort * *)

- ea: `0x1800c9e88`
- end: `0x1800ca096`
- name: `?GetURLMoniker@@YAJPEAUIUnknown@@PEAPEAG@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cae80`

## callees

- `0x1800c8f34`
- `0x1800c9e88`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c9f73`
- `ole32!CoTaskMemFree` at `0x1800c9f73`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9f60`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9f60`

## pseudocode

```c
__int64 __fastcall GetURLMoniker(struct IUnknown *a1, unsigned __int16 **a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned __int16 *v9; // rax
  OLECHAR *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-10h]
  int v15; // [rsp+20h] [rbp-10h]
  int v16; // [rsp+20h] [rbp-10h]
  OLECHAR *psz; // [rsp+50h] [rbp+20h] BYREF
  __int64 v18; // [rsp+58h] [rbp+28h] BYREF
  __int64 v19; // [rsp+60h] [rbp+30h] BYREF
  __int64 v20; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v20 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &IID_IServiceProvider,
         &v20);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v19 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v20 + 24LL))(
           v20,
           &IID_IBindHost,
           &IID_IBindHost,
           &v19);
    v5 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v15 = 3364;
        bidTraceW(
          off_18012A218[0],
          3444745,
          L"<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v6,
          v15);
      }
      goto LABEL_18;
    }
    v18 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64 *, _DWORD))(*(_QWORD *)v19 + 24LL))(
           v19,
           L".",
           0,
           &v18,
           0);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        LODWORD(v14) = 3358;
        bidTraceW(
          off_18012A218[0],
          3438601,
          L"<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v7,
          v14);
      }
      goto LABEL_15;
    }
    psz = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, OLECHAR **))(*(_QWORD *)v18 + 160LL))(v18, 0, 0, &psz);
    v5 = v8;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_12:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_15:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_18:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        return v5;
      }
      LODWORD(v14) = 3352;
      v11 = (unsigned int)v8;
      v12 = 3432457;
    }
    else
    {
      if ( !psz )
        goto LABEL_12;
      v9 = SysAllocString(psz);
      v10 = psz;
      *a2 = v9;
      CoTaskMemFree(v10);
      if ( *a2 )
        goto LABEL_12;
      v5 = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_12;
      LODWORD(v14) = 3346;
      v11 = 2147942414LL;
      v12 = 3426313;
    }
    bidTraceW(off_18012A218[0], v12, L"<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT} line %d\n", v11, v14);
    goto LABEL_12;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v16 = 3370;
    bidTraceW(off_18012A218[0], 3450889, L"<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT} line %d\n", (unsigned int)v4, v16);
  }
  return v5;
}

```

## disassembly

```asm
0x1800c9e88  push    rbp
0x1800c9e8a  push    rbx
0x1800c9e8b  push    rdi
0x1800c9e8c  mov     rbp, rsp
0x1800c9e8f  sub     rsp, 30h
0x1800c9e93  mov     qword ptr [rdx], 0
0x1800c9e9a  lea     r8, [rbp+arg_18]
0x1800c9e9e  mov     rax, [rcx]
0x1800c9ea1  mov     rdi, rdx
0x1800c9ea4  lea     rdx, IID_IServiceProvider
0x1800c9eab  mov     [rbp+arg_18], 0
0x1800c9eb3  mov     rax, [rax]
0x1800c9eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9ebb  mov     ebx, eax
0x1800c9ebd  test    eax, eax
0x1800c9ebf  js      loc_1800CA05F
0x1800c9ec5  mov     rcx, [rbp+arg_18]
0x1800c9ec9  lea     rdx, IID_IBindHost
0x1800c9ed0  mov     [rbp+arg_10], 0
0x1800c9ed8  lea     r9, [rbp+arg_10]
0x1800c9edc  mov     r8, rdx
0x1800c9edf  mov     rax, [rcx]
0x1800c9ee2  mov     rax, [rax+18h]
0x1800c9ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9eeb  mov     ebx, eax
0x1800c9eed  test    eax, eax
0x1800c9eef  js      loc_1800CA021
0x1800c9ef5  mov     rcx, [rbp+arg_10]
0x1800c9ef9  lea     r9, [rbp+arg_8]
0x1800c9efd  mov     [rbp+arg_8], 0
0x1800c9f05  lea     rdx, asc_1801112EC; "."
0x1800c9f0c  xor     r8d, r8d
0x1800c9f0f  mov     [rsp+30h+var_10], 0
0x1800c9f17  mov     rax, [rcx]
0x1800c9f1a  mov     rax, [rax+18h]
0x1800c9f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9f23  mov     ebx, eax
0x1800c9f25  test    eax, eax
0x1800c9f27  js      loc_1800C9FE3
0x1800c9f2d  mov     rcx, [rbp+arg_8]
0x1800c9f31  lea     r9, [rbp+psz]
0x1800c9f35  mov     [rbp+psz], 0
0x1800c9f3d  xor     r8d, r8d
0x1800c9f40  xor     edx, edx
0x1800c9f42  mov     rax, [rcx]
0x1800c9f45  mov     rax, [rax+0A0h]
0x1800c9f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9f51  mov     ebx, eax
0x1800c9f53  test    eax, eax
0x1800c9f55  js      short loc_1800C9FA5
0x1800c9f57  mov     rcx, [rbp+psz]; psz
0x1800c9f5b  test    rcx, rcx
0x1800c9f5e  jz      short loc_1800C9FD1
0x1800c9f60  call    cs:__imp_SysAllocString
0x1800c9f67  nop     dword ptr [rax+rax+00h]
0x1800c9f6c  mov     rcx, [rbp+psz]; pv
0x1800c9f70  mov     [rdi], rax
0x1800c9f73  call    cs:__imp_CoTaskMemFree
0x1800c9f7a  nop     dword ptr [rax+rax+00h]
0x1800c9f7f  cmp     qword ptr [rdi], 0
0x1800c9f83  jnz     short loc_1800C9FD1
0x1800c9f85  test    byte ptr cs:_bidGblFlags, 2
0x1800c9f8c  mov     ebx, 8007000Eh
0x1800c9f91  jz      short loc_1800C9FD1
0x1800c9f93  mov     [rsp+30h+var_10], 0D12h
0x1800c9f9b  mov     r9d, ebx
0x1800c9f9e  mov     edx, 344809h
0x1800c9fa3  jmp     short loc_1800C9FBE
0x1800c9fa5  test    byte ptr cs:_bidGblFlags, 2
0x1800c9fac  jz      short loc_1800C9FD1
0x1800c9fae  mov     [rsp+30h+var_10], 0D18h
0x1800c9fb6  mov     r9d, eax
0x1800c9fb9  mov     edx, 346009h
0x1800c9fbe  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c9fc5  lea     r8, aGeturlmonikerA; "<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT}"...
0x1800c9fcc  call    _bidTraceW
0x1800c9fd1  mov     rcx, [rbp+arg_8]
0x1800c9fd5  mov     rax, [rcx]
0x1800c9fd8  mov     rax, [rax+10h]
0x1800c9fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9fe1  jmp     short loc_1800CA00F
0x1800c9fe3  test    byte ptr cs:_bidGblFlags, 2
0x1800c9fea  jz      short loc_1800CA00F
0x1800c9fec  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c9ff3  lea     r8, aGeturlmonikerA; "<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT}"...
0x1800c9ffa  mov     r9d, eax
0x1800c9ffd  mov     [rsp+30h+var_10], 0D1Eh
0x1800ca005  mov     edx, 347809h
0x1800ca00a  call    _bidTraceW
0x1800ca00f  mov     rcx, [rbp+arg_10]
0x1800ca013  mov     rax, [rcx]
0x1800ca016  mov     rax, [rax+10h]
0x1800ca01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca01f  jmp     short loc_1800CA04D
0x1800ca021  test    byte ptr cs:_bidGblFlags, 2
0x1800ca028  jz      short loc_1800CA04D
0x1800ca02a  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800ca031  lea     r8, aGeturlmonikerA; "<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT}"...
0x1800ca038  mov     r9d, eax
0x1800ca03b  mov     [rsp+30h+var_10], 0D24h
0x1800ca043  mov     edx, 349009h
0x1800ca048  call    _bidTraceW
0x1800ca04d  mov     rcx, [rbp+arg_18]
0x1800ca051  mov     rax, [rcx]
0x1800ca054  mov     rax, [rax+10h]
0x1800ca058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca05d  jmp     short loc_1800CA08B
0x1800ca05f  test    byte ptr cs:_bidGblFlags, 2
0x1800ca066  jz      short loc_1800CA08B
0x1800ca068  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800ca06f  lea     r8, aGeturlmonikerA; "<GetURLMoniker|ADO|ERR> 0x%08x{HRESULT}"...
0x1800ca076  mov     r9d, eax
0x1800ca079  mov     [rsp+30h+var_10], 0D2Ah
0x1800ca081  mov     edx, 34A809h
0x1800ca086  call    _bidTraceW
0x1800ca08b  mov     eax, ebx
0x1800ca08d  add     rsp, 30h
0x1800ca091  pop     rdi
0x1800ca092  pop     rbx
0x1800ca093  pop     rbp
0x1800ca094  retn
```
