# CabViewDataObject_CreateInstance(_GUID const &,void * *)

- ea: `0x18000b074`
- end: `0x18000b126`
- name: `?CabViewDataObject_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011e70`

## callees

- `0x18000ae38`
- `0x18000b074`
- `0x180011e00`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CabViewDataObject_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  CObjectWithSite *v5; // rax
  CObjectWithSite *v6; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (CObjectWithSite *)operator new(0x268u);
  v6 = v5;
  if ( v5 )
  {
    CObjectWithSite::CObjectWithSite(v5);
    *((_DWORD *)v6 + 8) = 1;
    *((_QWORD *)v6 + 2) = &CCabObj::`vftable'{for `IDataObject'};
    *(_QWORD *)v6 = &CCabObj::`vftable'{for `CObjectWithSite'};
    *((_QWORD *)v6 + 3) = &CCabObj::`vftable'{for `IPersistStream'};
    *((_DWORD *)v6 + 10) = 8;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    _InterlockedIncrement(&g_cRefThisDll);
    v4 = (**(__int64 (__fastcall ***)(CObjectWithSite *, const struct _GUID *, void **))v6)(v6, a1, a2);
    (*(void (__fastcall **)(CObjectWithSite *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b074  push    rbx
0x18000b076  push    rbp
0x18000b077  push    rsi
0x18000b078  push    rdi
0x18000b079  sub     rsp, 28h
0x18000b07d  mov     rbp, rcx
0x18000b080  mov     qword ptr [rdx], 0
0x18000b087  mov     ecx, 268h; unsigned __int64
0x18000b08c  mov     rsi, rdx
0x18000b08f  mov     edi, 8007000Eh
0x18000b094  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b099  mov     rbx, rax
0x18000b09c  test    rax, rax
0x18000b09f  jz      short loc_18000B11B
0x18000b0a1  mov     rcx, rax; this
0x18000b0a4  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x18000b0a9  lea     rax, ??_7CCabObj@@6BIDataObject@@@; const CCabObj::`vftable'{for `IDataObject'}
0x18000b0b0  mov     dword ptr [rbx+20h], 1
0x18000b0b7  mov     [rbx+10h], rax
0x18000b0bb  lea     rcx, ??_7CCabObj@@6BCObjectWithSite@@@; const CCabObj::`vftable'{for `CObjectWithSite'}
0x18000b0c2  lea     rax, ??_7CCabObj@@6BIPersistStream@@@; const CCabObj::`vftable'{for `IPersistStream'}
0x18000b0c9  mov     [rbx], rcx
0x18000b0cc  mov     [rbx+18h], rax
0x18000b0d0  mov     dword ptr [rbx+28h], 8
0x18000b0d7  mov     qword ptr [rbx+40h], 0
0x18000b0df  mov     qword ptr [rbx+48h], 0
0x18000b0e7  mov     qword ptr [rbx+50h], 0
0x18000b0ef  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000b0f6  mov     rax, [rbx]
0x18000b0f9  mov     r8, rsi
0x18000b0fc  mov     rdx, rbp
0x18000b0ff  mov     rcx, rbx
0x18000b102  mov     rax, [rax]
0x18000b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10a  mov     rcx, [rbx]
0x18000b10d  mov     edi, eax
0x18000b10f  mov     rax, [rcx+10h]
0x18000b113  mov     rcx, rbx
0x18000b116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11b  mov     eax, edi
0x18000b11d  add     rsp, 28h
0x18000b121  pop     rdi
0x18000b122  pop     rsi
0x18000b123  pop     rbp
0x18000b124  pop     rbx
0x18000b125  retn
```
