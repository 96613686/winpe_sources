# DiskQuotaPropSheetExt::CreateInstance(_GUID const &,void * *)

- ea: `0x180016340`
- end: `0x18001640a`
- name: `?CreateInstance@DiskQuotaPropSheetExt@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011790`

## callees

- `0x180006ec0`
- `0x180016340`
- `0x180019dd0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiskQuotaPropSheetExt::CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // esi
  _QWORD *v5; // rax
  _QWORD *v6; // rdi

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x50u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = &DiskQuotaPropSheetExt::`vftable'{for `IShellExtInit'};
    v5[1] = &DiskQuotaPropSheetExt::`vftable'{for `IShellPropSheetExt'};
    CString::CString((CString *)(v5 + 2));
    CString::CString((CString *)(v6 + 4));
    CString::CString((CString *)(v6 + 6));
    *((_BYTE *)v6 + 64) = 0;
    *((_DWORD *)v6 + 18) = 1;
    _InterlockedIncrement(&g_cRefThisDll);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v6)(v6, a1, a2);
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180016340  mov     [rsp+arg_0], rbx
0x180016345  mov     [rsp+arg_18], rbp
0x18001634a  push    rsi
0x18001634b  push    rdi
0x18001634c  push    r14
0x18001634e  sub     rsp, 20h
0x180016352  mov     r14, rdx
0x180016355  mov     rbp, rcx
0x180016358  mov     qword ptr [rdx], 0
0x18001635f  mov     esi, 8007000Eh
0x180016364  mov     ecx, 50h ; 'P'; uBytes
0x180016369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001636e  mov     rdi, rax
0x180016371  mov     [rsp+38h+arg_8], rax
0x180016376  test    rax, rax
0x180016379  jz      short loc_1800163C9
0x18001637b  lea     rax, ??_7DiskQuotaPropSheetExt@@6BIShellExtInit@@@; const DiskQuotaPropSheetExt::`vftable'{for `IShellExtInit'}
0x180016382  mov     [rdi], rax
0x180016385  lea     rax, ??_7DiskQuotaPropSheetExt@@6BIShellPropSheetExt@@@; const DiskQuotaPropSheetExt::`vftable'{for `IShellPropSheetExt'}
0x18001638c  mov     [rdi+8], rax
0x180016390  lea     rbx, [rdi+10h]
0x180016394  mov     [rsp+38h+arg_10], rbx
0x180016399  mov     rcx, rbx; this
0x18001639c  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800163a1  nop
0x1800163a2  lea     rcx, [rbx+10h]; this
0x1800163a6  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800163ab  nop
0x1800163ac  lea     rcx, [rbx+20h]; this
0x1800163b0  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800163b5  mov     byte ptr [rbx+30h], 0
0x1800163b9  mov     dword ptr [rdi+48h], 1
0x1800163c0  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800163c7  jmp     short loc_1800163CB
0x1800163c9  xor     edi, edi
0x1800163cb  test    rdi, rdi
0x1800163ce  jz      short loc_1800163F5
0x1800163d0  mov     rax, [rdi]
0x1800163d3  mov     r8, r14
0x1800163d6  mov     rdx, rbp
0x1800163d9  mov     rcx, rdi
0x1800163dc  mov     rax, [rax]
0x1800163df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e4  mov     esi, eax
0x1800163e6  mov     rdx, [rdi]
0x1800163e9  mov     rcx, rdi
0x1800163ec  mov     rax, [rdx+10h]
0x1800163f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163f5  mov     eax, esi
0x1800163f7  mov     rbx, [rsp+38h+arg_0]
0x1800163fc  mov     rbp, [rsp+38h+arg_18]
0x180016401  add     rsp, 20h
0x180016405  pop     r14
0x180016407  pop     rdi
0x180016408  pop     rsi
0x180016409  retn
```
