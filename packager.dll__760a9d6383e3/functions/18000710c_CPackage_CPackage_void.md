# CPackage::~CPackage(void)

- ea: `0x18000710c`
- end: `0x1800072e0`
- name: `??1CPackage@@QEAA@XZ`
- size: `468`
- prototype: `void __fastcall(CPackage *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a300`
- `0x18000a760`

## callees

- `0x18000710c`
- `0x18000a43c`
- `0x18000a718`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800071be`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800071be`

## pseudocode

```c
void __fastcall CPackage::~CPackage(CPackage *this)
{
  __int64 v2; // rax
  const WCHAR *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 i; // rdi

  --g_cRefThisDll;
  *(_QWORD *)this = &CPackage::`vftable'{for `IEnumOLEVERB'};
  *((_QWORD *)this + 1) = &CPackage::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 2) = &CPackage::`vftable'{for `IOleObject'};
  *((_QWORD *)this + 3) = &CPackage::`vftable'{for `IViewObject2'};
  *((_QWORD *)this + 4) = &CPackage::`vftable'{for `IDataObject'};
  *((_QWORD *)this + 5) = &CPackage::`vftable'{for `IPersistStorage'};
  *((_QWORD *)this + 6) = &CPackage::`vftable'{for `IAdviseSink'};
  *((_QWORD *)this + 7) = &CPackage::`vftable'{for `IRunnableObject'};
  *((_QWORD *)this + 8) = &CPackage::`vftable'{for `IPersistFile'};
  *((_QWORD *)this + 9) = &CPackage::`vftable'{for `IExternalConnection'};
  *((_QWORD *)this + 10) = &CPackage::`vftable'{for `IOlePackagerLinkNotify'};
  CPackage::_DestroyIC(this);
  if ( *((_DWORD *)this + 26) == 1 )
  {
    v4 = (void *)*((_QWORD *)this + 15);
  }
  else
  {
    if ( *((_DWORD *)this + 26) != 3 )
      goto LABEL_9;
    v2 = *((_QWORD *)this + 14);
    if ( v2 )
    {
      v3 = *(const WCHAR **)(v2 + 592);
      if ( v3 )
      {
        DeleteFileW(v3);
        operator delete(*(void **)(*((_QWORD *)this + 14) + 592LL));
      }
    }
    v4 = (void *)*((_QWORD *)this + 14);
  }
  operator delete(v4);
LABEL_9:
  v5 = *((_QWORD *)this + 20);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 21);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 22);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 23);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 33);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  operator delete(*((void **)this + 17));
  operator delete(*((void **)this + 18));
  v10 = *((_QWORD *)this + 29);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 29) = 0;
  }
  if ( *((_QWORD *)this + 28) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 54); i = (unsigned int)(i + 1) )
      operator delete(*(void **)(*((_QWORD *)this + 28) + 24 * i + 8));
    operator delete(*((void **)this + 28));
  }
}

```

## disassembly

```asm
0x18000710c  mov     [rsp+arg_0], rbx
0x180007111  push    rdi
0x180007112  sub     rsp, 20h
0x180007116  dec     cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000711c  lea     rax, ??_7CPackage@@6BIEnumOLEVERB@@@; const CPackage::`vftable'{for `IEnumOLEVERB'}
0x180007123  mov     [rcx], rax
0x180007126  mov     rbx, rcx
0x180007129  lea     rax, ??_7CPackage@@6BIOleCommandTarget@@@; const CPackage::`vftable'{for `IOleCommandTarget'}
0x180007130  mov     [rcx+8], rax
0x180007134  lea     rax, ??_7CPackage@@6BIOleObject@@@; const CPackage::`vftable'{for `IOleObject'}
0x18000713b  mov     [rcx+10h], rax
0x18000713f  lea     rax, ??_7CPackage@@6BIViewObject2@@@; const CPackage::`vftable'{for `IViewObject2'}
0x180007146  mov     [rcx+18h], rax
0x18000714a  lea     rax, ??_7CPackage@@6BIDataObject@@@; const CPackage::`vftable'{for `IDataObject'}
0x180007151  mov     [rcx+20h], rax
0x180007155  lea     rax, ??_7CPackage@@6BIPersistStorage@@@; const CPackage::`vftable'{for `IPersistStorage'}
0x18000715c  mov     [rcx+28h], rax
0x180007160  lea     rax, ??_7CPackage@@6BIAdviseSink@@@; const CPackage::`vftable'{for `IAdviseSink'}
0x180007167  mov     [rcx+30h], rax
0x18000716b  lea     rax, ??_7CPackage@@6BIRunnableObject@@@; const CPackage::`vftable'{for `IRunnableObject'}
0x180007172  mov     [rcx+38h], rax
0x180007176  lea     rax, ??_7CPackage@@6BIPersistFile@@@; const CPackage::`vftable'{for `IPersistFile'}
0x18000717d  mov     [rcx+40h], rax
0x180007181  lea     rax, ??_7CPackage@@6BIExternalConnection@@@; const CPackage::`vftable'{for `IExternalConnection'}
0x180007188  mov     [rcx+48h], rax
0x18000718c  lea     rax, ??_7CPackage@@6BIOlePackagerLinkNotify@@@; const CPackage::`vftable'{for `IOlePackagerLinkNotify'}
0x180007193  mov     [rcx+50h], rax
0x180007197  call    ?_DestroyIC@CPackage@@IEAAXXZ; CPackage::_DestroyIC(void)
0x18000719c  mov     ecx, [rbx+68h]
0x18000719f  sub     ecx, 1
0x1800071a2  jz      short loc_1800071DA
0x1800071a4  cmp     ecx, 2
0x1800071a7  jnz     short loc_1800071E3
0x1800071a9  mov     rax, [rbx+70h]
0x1800071ad  test    rax, rax
0x1800071b0  jz      short loc_1800071D4
0x1800071b2  mov     rcx, [rax+250h]; lpFileName
0x1800071b9  test    rcx, rcx
0x1800071bc  jz      short loc_1800071D4
0x1800071be  call    cs:__imp_DeleteFileW
0x1800071c4  mov     rcx, [rbx+70h]
0x1800071c8  mov     rcx, [rcx+250h]; lpMem
0x1800071cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800071d4  mov     rcx, [rbx+70h]
0x1800071d8  jmp     short loc_1800071DE
0x1800071da  mov     rcx, [rbx+78h]; lpMem
0x1800071de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800071e3  mov     rcx, [rbx+0A0h]
0x1800071ea  test    rcx, rcx
0x1800071ed  jz      short loc_1800071FB
0x1800071ef  mov     rax, [rcx]
0x1800071f2  mov     rax, [rax+10h]
0x1800071f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071fb  mov     rcx, [rbx+0A8h]
0x180007202  test    rcx, rcx
0x180007205  jz      short loc_180007213
0x180007207  mov     rax, [rcx]
0x18000720a  mov     rax, [rax+10h]
0x18000720e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007213  mov     rcx, [rbx+0B0h]
0x18000721a  test    rcx, rcx
0x18000721d  jz      short loc_18000722B
0x18000721f  mov     rax, [rcx]
0x180007222  mov     rax, [rax+10h]
0x180007226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000722b  mov     rcx, [rbx+0B8h]
0x180007232  test    rcx, rcx
0x180007235  jz      short loc_180007243
0x180007237  mov     rax, [rcx]
0x18000723a  mov     rax, [rax+10h]
0x18000723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007243  mov     rcx, [rbx+108h]
0x18000724a  test    rcx, rcx
0x18000724d  jz      short loc_18000725B
0x18000724f  mov     rax, [rcx]
0x180007252  mov     rax, [rax+10h]
0x180007256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000725b  mov     rcx, [rbx+88h]; lpMem
0x180007262  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007267  mov     rcx, [rbx+90h]; lpMem
0x18000726e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007273  mov     rcx, [rbx+0E8h]
0x18000727a  test    rcx, rcx
0x18000727d  jz      short loc_180007296
0x18000727f  mov     rax, [rcx]
0x180007282  mov     rax, [rax+10h]
0x180007286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728b  mov     qword ptr [rbx+0E8h], 0
0x180007296  cmp     qword ptr [rbx+0E0h], 0
0x18000729e  jz      short loc_1800072D5
0x1800072a0  xor     edi, edi
0x1800072a2  cmp     [rbx+0D8h], edi
0x1800072a8  jbe     short loc_1800072C9
0x1800072aa  mov     rcx, [rbx+0E0h]
0x1800072b1  lea     rdx, [rdi+rdi*2]
0x1800072b5  mov     rcx, [rcx+rdx*8+8]; lpMem
0x1800072ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072bf  inc     edi
0x1800072c1  cmp     edi, [rbx+0D8h]
0x1800072c7  jb      short loc_1800072AA
0x1800072c9  mov     rcx, [rbx+0E0h]; lpMem
0x1800072d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072d5  mov     rbx, [rsp+28h+arg_0]
0x1800072da  add     rsp, 20h
0x1800072de  pop     rdi
0x1800072df  retn
```
