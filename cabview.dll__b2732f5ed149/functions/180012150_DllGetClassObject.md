# DllGetClassObject

- ea: `0x180012150`
- end: `0x180012201`
- name: `DllGetClassObject`
- size: `177`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011dd4`
- `0x180011e00`
- `0x180012150`
- `0x180013010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  __int64 v7; // rax
  HRESULT v8; // ebx
  CThisDllClassFactory *v9; // rax
  CThisDllClassFactory *v10; // rax
  CThisDllClassFactory *v11; // rdi

  *ppv = 0;
  v5 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_CabFolder.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_CabFolder.Data1 )
    v5 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_CabFolder.Data4;
  if ( !v5 )
    goto LABEL_8;
  v7 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_CabViewDataObject.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_CabViewDataObject.Data1 )
    v7 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_CabViewDataObject.Data4;
  if ( v7 )
    return -2147467259;
LABEL_8:
  v9 = (CThisDllClassFactory *)operator new(0x20u);
  if ( !v9 )
    return -2147024882;
  v10 = CThisDllClassFactory::CThisDllClassFactory(v9, rclsid);
  v11 = v10;
  if ( !v10 )
    return -2147024882;
  v8 = (**(__int64 (__fastcall ***)(CThisDllClassFactory *, const IID *const, LPVOID *))v10)(v10, riid, ppv);
  (*(void (__fastcall **)(CThisDllClassFactory *))(*(_QWORD *)v11 + 16LL))(v11);
  return v8;
}

```

## disassembly

```asm
0x180012150  push    rbx
0x180012152  push    rbp
0x180012153  push    rsi
0x180012154  push    rdi
0x180012155  sub     rsp, 28h
0x180012159  mov     qword ptr [r8], 0
0x180012160  mov     rsi, r8
0x180012163  mov     rax, [rcx]
0x180012166  mov     rbp, rdx
0x180012169  sub     rax, qword ptr cs:CLSID_CabFolder.Data1
0x180012170  mov     rbx, rcx
0x180012173  jnz     short loc_180012180
0x180012175  mov     rax, [rcx+8]
0x180012179  sub     rax, qword ptr cs:CLSID_CabFolder.Data4
0x180012180  test    rax, rax
0x180012183  jz      short loc_1800121A8
0x180012185  mov     rax, [rcx]
0x180012188  sub     rax, qword ptr cs:CLSID_CabViewDataObject.Data1
0x18001218f  jnz     short loc_18001219C
0x180012191  mov     rax, [rcx+8]
0x180012195  sub     rax, qword ptr cs:CLSID_CabViewDataObject.Data4
0x18001219c  test    rax, rax
0x18001219f  jz      short loc_1800121A8
0x1800121a1  mov     ebx, 80004005h
0x1800121a6  jmp     short loc_1800121F6
0x1800121a8  mov     ecx, 20h ; ' '; unsigned __int64
0x1800121ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800121b2  test    rax, rax
0x1800121b5  jz      short loc_1800121F1
0x1800121b7  mov     rdx, rbx; struct _GUID *
0x1800121ba  mov     rcx, rax; this
0x1800121bd  call    ??0CThisDllClassFactory@@QEAA@AEBU_GUID@@@Z; CThisDllClassFactory::CThisDllClassFactory(_GUID const &)
0x1800121c2  mov     rdi, rax
0x1800121c5  test    rax, rax
0x1800121c8  jz      short loc_1800121F1
0x1800121ca  mov     rax, [rax]
0x1800121cd  mov     r8, rsi
0x1800121d0  mov     rdx, rbp
0x1800121d3  mov     rcx, rdi
0x1800121d6  mov     rax, [rax]
0x1800121d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121de  mov     rcx, [rdi]
0x1800121e1  mov     ebx, eax
0x1800121e3  mov     rax, [rcx+10h]
0x1800121e7  mov     rcx, rdi
0x1800121ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ef  jmp     short loc_1800121F6
0x1800121f1  mov     ebx, 8007000Eh
0x1800121f6  mov     eax, ebx
0x1800121f8  add     rsp, 28h
0x1800121fc  pop     rdi
0x1800121fd  pop     rsi
0x1800121fe  pop     rbp
0x1800121ff  pop     rbx
0x180012200  retn
```
