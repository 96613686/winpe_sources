# CabFolder_CreateInstance(_GUID const &,void * *)

- ea: `0x18000d478`
- end: `0x18000d534`
- name: `?CabFolder_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011e70`

## callees

- `0x18000d478`
- `0x180011e00`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CabFolder_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax
  _DWORD *v6; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x50u);
  v6 = v5;
  if ( v5 )
  {
    v5[10] = 1;
    *(_QWORD *)v5 = &CCabFolder::`vftable'{for `IPersistFolder2'};
    *((_QWORD *)v5 + 1) = &CCabFolder::`vftable'{for `IShellFolder2'};
    *((_QWORD *)v5 + 2) = &CCabFolder::`vftable'{for `IShellFolderViewCB'};
    *((_QWORD *)v5 + 3) = &CCabFolder::`vftable'{for `IFolderType'};
    *((_QWORD *)v5 + 4) = &CCabFolder::`vftable'{for `IExplorerPaneVisibility'};
    *((_QWORD *)v5 + 6) = 0;
    v5[14] = 128;
    *((_QWORD *)v5 + 9) = 0;
    _InterlockedIncrement(&g_cRefThisDll);
    v4 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v5)(v5, a1, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x18000d478  push    rbx
0x18000d47a  push    rbp
0x18000d47b  push    rsi
0x18000d47c  push    rdi
0x18000d47d  sub     rsp, 28h
0x18000d481  mov     rbp, rcx
0x18000d484  mov     qword ptr [rdx], 0
0x18000d48b  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000d490  mov     rsi, rdx
0x18000d493  mov     edi, 8007000Eh
0x18000d498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d49d  mov     rbx, rax
0x18000d4a0  test    rax, rax
0x18000d4a3  jz      loc_18000D529
0x18000d4a9  lea     rax, ??_7CCabFolder@@6BIPersistFolder2@@@; const CCabFolder::`vftable'{for `IPersistFolder2'}
0x18000d4b0  mov     dword ptr [rbx+28h], 1
0x18000d4b7  mov     [rbx], rax
0x18000d4ba  lea     rax, ??_7CCabFolder@@6BIShellFolder2@@@; const CCabFolder::`vftable'{for `IShellFolder2'}
0x18000d4c1  mov     [rbx+8], rax
0x18000d4c5  lea     rax, ??_7CCabFolder@@6BIShellFolderViewCB@@@; const CCabFolder::`vftable'{for `IShellFolderViewCB'}
0x18000d4cc  mov     [rbx+10h], rax
0x18000d4d0  lea     rax, ??_7CCabFolder@@6BIFolderType@@@; const CCabFolder::`vftable'{for `IFolderType'}
0x18000d4d7  mov     [rbx+18h], rax
0x18000d4db  lea     rax, ??_7CCabFolder@@6BIExplorerPaneVisibility@@@; const CCabFolder::`vftable'{for `IExplorerPaneVisibility'}
0x18000d4e2  mov     [rbx+20h], rax
0x18000d4e6  mov     qword ptr [rbx+30h], 0
0x18000d4ee  mov     dword ptr [rbx+38h], 80h
0x18000d4f5  mov     qword ptr [rbx+48h], 0
0x18000d4fd  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000d504  mov     rax, [rbx]
0x18000d507  mov     r8, rsi
0x18000d50a  mov     rdx, rbp
0x18000d50d  mov     rcx, rbx
0x18000d510  mov     rax, [rax]
0x18000d513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d518  mov     rcx, [rbx]
0x18000d51b  mov     edi, eax
0x18000d51d  mov     rax, [rcx+10h]
0x18000d521  mov     rcx, rbx
0x18000d524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d529  mov     eax, edi
0x18000d52b  add     rsp, 28h
0x18000d52f  pop     rdi
0x18000d530  pop     rsi
0x18000d531  pop     rbp
0x18000d532  pop     rbx
0x18000d533  retn
```
