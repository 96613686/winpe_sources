# ATL::CDynamicAccessor::GetRowsetProperties(IUnknown *,ulong *,int *,ulong)

- ea: `0x1800090c8`
- end: `0x1800091f5`
- name: `?GetRowsetProperties@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@PEAKPEAHK@Z`
- size: `301`
- prototype: `__int64 __fastcall(ATL::CDynamicAccessor *this, struct IUnknown *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007dac`

## callees

- `0x1800090c8`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091b3`

## pseudocode

```c
__int64 __fastcall ATL::CDynamicAccessor::GetRowsetProperties(
        ATL::CDynamicAccessor *this,
        struct IUnknown *a2,
        unsigned int *a3,
        int *a4)
{
  int v6; // edi
  _DWORD *v7; // rcx
  __int64 i; // r9
  unsigned int v9; // eax
  bool v10; // cf
  __int16 *v11; // rax
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  unsigned int *v16; // [rsp+48h] [rbp-28h] BYREF
  int v17; // [rsp+50h] [rbp-20h]
  GUID v18; // [rsp+54h] [rbp-1Ch]

  if ( !a2 || !a4 )
    return 2147500037LL;
  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_0c733a55_2a1c_11ce_ade5_00aa0044773d,
         &v15);
  *(_QWORD *)a4 = 0;
  if ( v6 >= 0 )
  {
    v14 = 0;
    pv = 0;
    v16 = a3;
    v17 = 2;
    v18 = DBPROPSET_ROWSET;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int **, int *, LPVOID *))(*(_QWORD *)v15 + 24LL))(
           v15,
           1,
           &v16,
           &v14,
           &pv);
    v7 = pv;
    if ( v6 >= 0 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v9 = 2;
        if ( v7[2] < 2u )
          v9 = v7[2];
        v10 = (unsigned int)i < v9;
        v11 = *(__int16 **)v7;
        if ( !v10 )
          break;
        a4[i] = v11[36 * i + 28];
      }
      if ( v11 )
      {
        CoTaskMemFree(*(LPVOID *)v7);
        v7 = pv;
      }
    }
    CoTaskMemFree(v7);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800090c8  mov     [rsp-18h+arg_0], rbx
0x1800090cd  push    rbp
0x1800090ce  push    rsi
0x1800090cf  push    rdi
0x1800090d0  mov     rbp, rsp
0x1800090d3  sub     rsp, 70h
0x1800090d7  mov     rax, cs:__security_cookie
0x1800090de  xor     rax, rsp
0x1800090e1  mov     [rbp+var_8], rax
0x1800090e5  mov     rbx, r9
0x1800090e8  mov     rsi, r8
0x1800090eb  mov     r9, rdx
0x1800090ee  test    rdx, rdx
0x1800090f1  jz      loc_1800091D4
0x1800090f7  test    rbx, rbx
0x1800090fa  jz      loc_1800091D4
0x180009100  mov     [rbp+var_30], 0
0x180009108  mov     rax, [rdx]
0x18000910b  lea     r8, [rbp+var_30]
0x18000910f  lea     rdx, _GUID_0c733a55_2a1c_11ce_ade5_00aa0044773d
0x180009116  mov     rcx, r9
0x180009119  mov     rax, [rax]
0x18000911c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009121  mov     edi, eax
0x180009123  xor     ecx, ecx
0x180009125  mov     [rbx], rcx
0x180009128  test    eax, eax
0x18000912a  js      loc_1800091BA
0x180009130  mov     [rbp+var_38], ecx
0x180009133  mov     [rbp+pv], rcx
0x180009137  mov     [rbp+var_28], rsi
0x18000913b  lea     esi, [rcx+2]
0x18000913e  mov     [rbp+var_20], esi
0x180009141  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180009148  movdqu  [rbp+var_1C], xmm0
0x18000914d  mov     rcx, [rbp+var_30]
0x180009151  mov     rax, [rcx]
0x180009154  lea     rdx, [rbp+pv]
0x180009158  mov     [rsp+70h+var_50], rdx
0x18000915d  lea     r9, [rbp+var_38]
0x180009161  lea     r8, [rbp+var_28]
0x180009165  lea     edx, [rsi-1]
0x180009168  mov     rax, [rax+18h]
0x18000916c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009171  mov     edi, eax
0x180009173  mov     rcx, [rbp+pv]
0x180009177  test    eax, eax
0x180009179  js      short loc_1800091B3
0x18000917b  xor     r9d, r9d
0x18000917e  mov     eax, esi
0x180009180  cmp     [rcx+8], esi
0x180009183  cmovb   eax, [rcx+8]
0x180009187  cmp     r9d, eax
0x18000918a  mov     rax, [rcx]
0x18000918d  jnb     short loc_1800091A1
0x18000918f  lea     rdx, [r9+r9*8]
0x180009193  movsx   edx, word ptr [rax+rdx*8+38h]
0x180009198  mov     [rbx+r9*4], edx
0x18000919c  inc     r9d
0x18000919f  jmp     short loc_18000917E
0x1800091a1  test    rax, rax
0x1800091a4  jz      short loc_1800091B3
0x1800091a6  mov     rcx, rax; pv
0x1800091a9  call    cs:__imp_CoTaskMemFree
0x1800091af  mov     rcx, [rbp+pv]; pv
0x1800091b3  call    cs:__imp_CoTaskMemFree
0x1800091b9  nop
0x1800091ba  mov     rcx, [rbp+var_30]
0x1800091be  test    rcx, rcx
0x1800091c1  jz      short loc_1800091D0
0x1800091c3  mov     rax, [rcx]
0x1800091c6  mov     rax, [rax+10h]
0x1800091ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091cf  nop
0x1800091d0  mov     eax, edi
0x1800091d2  jmp     short loc_1800091D9
0x1800091d4  mov     eax, 80004005h
0x1800091d9  mov     rcx, [rbp+var_8]
0x1800091dd  xor     rcx, rsp; StackCookie
0x1800091e0  call    __security_check_cookie
0x1800091e5  mov     rbx, [rsp+70h+arg_0]
0x1800091ed  add     rsp, 70h
0x1800091f1  pop     rdi
0x1800091f2  pop     rsi
0x1800091f3  pop     rbp
0x1800091f4  retn
```
