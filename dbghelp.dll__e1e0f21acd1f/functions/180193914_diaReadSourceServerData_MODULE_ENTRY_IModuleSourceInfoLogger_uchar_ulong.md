# diaReadSourceServerData(_MODULE_ENTRY *,IModuleSourceInfoLogger *,uchar * *,ulong *)

- ea: `0x180193914`
- end: `0x180193b1f`
- name: `?diaReadSourceServerData@@YAHPEAU_MODULE_ENTRY@@PEAVIModuleSourceInfoLogger@@PEAPEAEPEAK@Z`
- size: `523`
- prototype: `__int64 __fastcall(struct _MODULE_ENTRY *, struct IModuleSourceInfoLogger *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18019b240`
- `0x18019f648`

## callees

- `0x1800089f0`
- `0x180008ad0`
- `0x180016da4`
- `0x18018b498`
- `0x180193914`
- `0x1801940f4`
- `0x180205010`

## string_xrefs

- `0x180193975`: `Succeeded reading srcsrv source stream (legacy).`
- `0x18019399a`: `Failed reading srcsrv source stream (legacy).`
- `0x180193a36`: `Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex - not enough memory.`
- `0x180193acd`: `Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex.`
- `0x180193a94`: `Succeeded reading srcsrv source stream (legacy) via ISvcLegacySourceIndex.`
- `0x180193af7`: `Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex - error reading source index data size.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall diaReadSourceServerData(
        struct _MODULE_ENTRY *a1,
        struct IModuleSourceInfoLogger *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  _QWORD *v8; // rax
  unsigned int Stream; // esi
  __int64 v10; // rax
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  unsigned __int8 *v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF
  __int64 v16; // [rsp+80h] [rbp+40h] BYREF
  __int64 v17; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  *a4 = 0;
  v8 = (_QWORD *)*((_QWORD *)a1 + 2434);
  if ( !v8 )
    return 0;
  if ( !*v8 )
  {
    if ( !v8[1] )
      return 0;
    v15 = 0;
    v16 = 0;
    v12 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v8[2];
    if ( v12 && (**v12)(v12, &GUID_e39aa759_5041_4b55_9650_550e4ea8172c, &v15) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, &v16) >= 0 && v16 )
      {
        v13 = (unsigned __int8 *)pMemAlloc((unsigned int)(v16 + 1));
        *a3 = v13;
        if ( !v13 )
        {
          (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)a2 + 16LL))(
            a2,
            a1,
            L"Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex - not enough memory.");
          ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(&v15);
          return 0;
        }
        v17 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64 *))(*(_QWORD *)v15 + 32LL))(
               v15,
               v16,
               v13,
               &v17) >= 0
          && v17 == v16 )
        {
          (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)a2 + 8LL))(
            a2,
            a1,
            L"Succeeded reading srcsrv source stream (legacy) via ISvcLegacySourceIndex.");
          FeatureUsed(L"SourceStream_legacy", *((const unsigned __int16 **)a1 + 38));
          *a4 = v17;
          v14 = 1;
LABEL_21:
          ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(&v15);
          return v14;
        }
        (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)a2 + 16LL))(
          a2,
          a1,
          L"Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex.");
        FreeIt(*a3);
        *a3 = 0;
      }
      else
      {
        (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)a2 + 16LL))(
          a2,
          a1,
          L"Failed reading srcsrv source stream (legacy) via ISvcLegacySourceIndex - error reading source index data size.");
      }
    }
    v14 = 0;
    goto LABEL_21;
  }
  Stream = diaReadStream(a1, L"srcsrv", a3, a4);
  v10 = *(_QWORD *)a2;
  if ( Stream )
  {
    (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(v10 + 8))(
      a2,
      a1,
      L"Succeeded reading srcsrv source stream (legacy).");
    FeatureUsed(L"SourceStream_legacy", *((const unsigned __int16 **)a1 + 38));
  }
  else
  {
    (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(v10 + 16))(
      a2,
      a1,
      L"Failed reading srcsrv source stream (legacy).");
  }
  return Stream;
}

```

## disassembly

```asm
0x180193914  push    rbp
0x180193916  push    rbx
0x180193917  push    rsi
0x180193918  push    rdi
0x180193919  push    r14
0x18019391b  mov     rbp, rsp
0x18019391e  sub     rsp, 40h
0x180193922  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18019392a  mov     r14, r9
0x18019392d  mov     rsi, r8
0x180193930  mov     rbx, rdx
0x180193933  mov     rdi, rcx
0x180193936  mov     qword ptr [r8], 0
0x18019393d  mov     dword ptr [r9], 0
0x180193944  mov     rax, [rcx+4C10h]
0x18019394b  test    rax, rax
0x18019394e  jz      loc_180193A56
0x180193954  cmp     qword ptr [rax], 0
0x180193958  jz      short loc_1801939B1
0x18019395a  lea     rdx, aSrcsrv_0; "srcsrv"
0x180193961  call    ?diaReadStream@@YAHPEAU_MODULE_ENTRY@@PEBGPEAPEAEPEAK@Z; diaReadStream(_MODULE_ENTRY *,ushort const *,uchar * *,ulong *)
0x180193966  mov     esi, eax
0x180193968  mov     rax, [rbx]
0x18019396b  mov     rdx, rdi
0x18019396e  mov     rcx, rbx
0x180193971  test    esi, esi
0x180193973  jz      short loc_18019399A
0x180193975  lea     r8, aSucceededReadi_1; "Succeeded reading srcsrv source stream "...
0x18019397c  mov     rax, [rax+8]
0x180193980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193985  mov     rdx, [rdi+130h]; unsigned __int16 *
0x18019398c  lea     rcx, aSourcestreamLe; "SourceStream_legacy"
0x180193993  call    ?FeatureUsed@@YAXPEBG0@Z; FeatureUsed(ushort const *,ushort const *)
0x180193998  jmp     short loc_1801939AA
0x18019399a  lea     r8, aFailedReadingS_3; "Failed reading srcsrv source stream (le"...
0x1801939a1  mov     rax, [rax+10h]
0x1801939a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801939aa  mov     eax, esi
0x1801939ac  jmp     loc_180193A58
0x1801939b1  cmp     qword ptr [rax+8], 0
0x1801939b6  jz      loc_180193A56
0x1801939bc  mov     [rbp+arg_0], 0
0x1801939c4  mov     [rbp+arg_10], 0
0x1801939cc  mov     rcx, [rax+10h]
0x1801939d0  test    rcx, rcx
0x1801939d3  jz      loc_180193B0D
0x1801939d9  mov     rax, [rcx]
0x1801939dc  lea     r8, [rbp+arg_0]
0x1801939e0  lea     rdx, _GUID_e39aa759_5041_4b55_9650_550e4ea8172c
0x1801939e7  mov     rax, [rax]
0x1801939ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801939ef  test    eax, eax
0x1801939f1  js      loc_180193B0D
0x1801939f7  mov     rcx, [rbp+arg_0]
0x1801939fb  mov     rax, [rcx]
0x1801939fe  lea     rdx, [rbp+arg_10]
0x180193a02  mov     rax, [rax+18h]
0x180193a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193a0b  test    eax, eax
0x180193a0d  js      loc_180193AF4
0x180193a13  mov     rax, [rbp+arg_10]
0x180193a17  test    rax, rax
0x180193a1a  jz      loc_180193AF4
0x180193a20  lea     ecx, [rax+1]; dwBytes
0x180193a23  call    pMemAlloc
0x180193a28  mov     r8, rax
0x180193a2b  mov     [rsi], rax
0x180193a2e  test    rax, rax
0x180193a31  jnz     short loc_180193A63
0x180193a33  mov     rax, [rbx]
0x180193a36  lea     r8, aFailedReadingS_0; "Failed reading srcsrv source stream (le"...
0x180193a3d  mov     rdx, rdi
0x180193a40  mov     rcx, rbx
0x180193a43  mov     rax, [rax+10h]
0x180193a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193a4c  nop
0x180193a4d  lea     rcx, [rbp+arg_0]
0x180193a51  call    ??1?$CComPtr@UIDiaSymbol@@@ATL@@QEAA@XZ; ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(void)
0x180193a56  xor     eax, eax
0x180193a58  add     rsp, 40h
0x180193a5c  pop     r14
0x180193a5e  pop     rdi
0x180193a5f  pop     rsi
0x180193a60  pop     rbx
0x180193a61  pop     rbp
0x180193a62  retn
0x180193a63  mov     [rbp+arg_18], 0
0x180193a6b  mov     rcx, [rbp+arg_0]
0x180193a6f  mov     rax, [rcx]
0x180193a72  lea     r9, [rbp+arg_18]
0x180193a76  mov     rdx, [rbp+arg_10]
0x180193a7a  mov     rax, [rax+20h]
0x180193a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193a83  test    eax, eax
0x180193a85  js      short loc_180193ACA
0x180193a87  mov     rax, [rbp+arg_10]
0x180193a8b  cmp     [rbp+arg_18], rax
0x180193a8f  jnz     short loc_180193ACA
0x180193a91  mov     rax, [rbx]
0x180193a94  lea     r8, aSucceededReadi_0; "Succeeded reading srcsrv source stream "...
0x180193a9b  mov     rdx, rdi
0x180193a9e  mov     rcx, rbx
0x180193aa1  mov     rax, [rax+8]
0x180193aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193aaa  mov     rdx, [rdi+130h]; unsigned __int16 *
0x180193ab1  lea     rcx, aSourcestreamLe; "SourceStream_legacy"
0x180193ab8  call    ?FeatureUsed@@YAXPEBG0@Z; FeatureUsed(ushort const *,ushort const *)
0x180193abd  mov     eax, dword ptr [rbp+arg_18]
0x180193ac0  mov     [r14], eax
0x180193ac3  mov     ebx, 1
0x180193ac8  jmp     short loc_180193B0F
0x180193aca  mov     rax, [rbx]
0x180193acd  lea     r8, aFailedReadingS_6; "Failed reading srcsrv source stream (le"...
0x180193ad4  mov     rdx, rdi
0x180193ad7  mov     rcx, rbx
0x180193ada  mov     rax, [rax+10h]
0x180193ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193ae3  mov     rcx, [rsi]; lpMem
0x180193ae6  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x180193aeb  mov     qword ptr [rsi], 0
0x180193af2  jmp     short loc_180193B0D
0x180193af4  mov     rax, [rbx]
0x180193af7  lea     r8, aFailedReadingS_1; "Failed reading srcsrv source stream (le"...
0x180193afe  mov     rdx, rdi
0x180193b01  mov     rcx, rbx
0x180193b04  mov     rax, [rax+10h]
0x180193b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193b0d  xor     ebx, ebx
0x180193b0f  lea     rcx, [rbp+arg_0]
0x180193b13  call    ??1?$CComPtr@UIDiaSymbol@@@ATL@@QEAA@XZ; ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(void)
0x180193b18  mov     eax, ebx
0x180193b1a  jmp     loc_180193A58
```
