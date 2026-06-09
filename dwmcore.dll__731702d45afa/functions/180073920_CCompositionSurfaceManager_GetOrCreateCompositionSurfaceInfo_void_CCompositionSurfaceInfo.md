# CCompositionSurfaceManager::GetOrCreateCompositionSurfaceInfo(void *,CCompositionSurfaceInfo * *)

- ea: `0x180073920`
- end: `0x180073a96`
- name: `?GetOrCreateCompositionSurfaceInfo@CCompositionSurfaceManager@@QEAAJPEAXPEAPEAVCCompositionSurfaceInfo@@@Z`
- size: `374`
- prototype: `int(CCompositionSurfaceManager *__hidden this, void *, struct CCompositionSurfaceInfo **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073ee0`
- `0x1801d5af8`

## callees

- `0x180050270`
- `0x1800735f0`
- `0x180073920`
- `0x1800c3f0c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800739d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800739d2`
- `ntdll!RtlLookupElementGenericTable` at `0x18007399c`
- `ntdll!RtlLookupElementGenericTable` at `0x18007399c`
- `win32u!NtValidateCompositionSurfaceHandle` at `0x180073952`
- `win32u!NtValidateCompositionSurfaceHandle` at `0x180073952`

## pseudocode

```c
__int64 __fastcall CCompositionSurfaceManager::GetOrCreateCompositionSurfaceInfo(
        CCompositionSurfaceManager *this,
        void *a2,
        struct CCompositionSurfaceInfo **a3)
{
  int v6; // eax
  int v7; // ebx
  struct IVtrSurfaceManager *VtrSurfaceManager; // rax
  struct CCompositionSurfaceInfo *v9; // rdi
  PVOID v10; // rax
  char v11; // si
  int v13; // eax
  _QWORD Buffer[5]; // [rsp+30h] [rbp-28h] BYREF
  struct _LUID v15; // [rsp+70h] [rbp+18h] BYREF
  struct CCompositionSurfaceInfo *v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  *a3 = 0;
  v6 = NtValidateCompositionSurfaceHandle(a2, &v15);
  if ( v6 < 0 )
  {
    v7 = v6 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6 | 0x10000000, 0x36u, 0);
  }
  else
  {
    v7 = 0;
    VtrSurfaceManager = TryGetVtrSurfaceManager();
    if ( VtrSurfaceManager )
    {
      (*(void (__fastcall **)(struct IVtrSurfaceManager *, void *, struct _LUID *))(*(_QWORD *)VtrSurfaceManager + 40LL))(
        VtrSurfaceManager,
        a2,
        &v15);
      goto LABEL_4;
    }
  }
  if ( v7 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x36u, 0);
    return (unsigned int)v7;
  }
LABEL_4:
  v9 = 0;
  Buffer[0] = v15;
  Buffer[1] = 0;
  v10 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), Buffer);
  if ( v10 )
    v9 = (struct CCompositionSurfaceInfo *)*((_QWORD *)v10 + 1);
  v16 = v9;
  if ( v9 )
  {
    v11 = 1;
    (*(void (__fastcall **)(struct CCompositionSurfaceInfo *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  else
  {
    v13 = CCompositionSurfaceInfo::Create(a2, v15, this, &v16);
    v7 = v13;
    if ( v13 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, 0x46u, 0);
      goto LABEL_9;
    }
    v9 = v16;
    v11 = 0;
  }
  *a3 = v9;
  if ( v11 )
LABEL_9:
    CloseHandle(a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180073920  mov     rax, rsp
0x180073923  mov     [rax+8], rbx
0x180073927  mov     [rax+10h], rbp
0x18007392b  push    rsi
0x18007392c  push    rdi
0x18007392d  push    r14
0x18007392f  sub     rsp, 40h
0x180073933  mov     rbp, rdx
0x180073936  mov     qword ptr [rax+18h], 0
0x18007393e  mov     rsi, rcx
0x180073941  mov     qword ptr [r8], 0
0x180073948  mov     rcx, rbp
0x18007394b  lea     rdx, [rax+18h]
0x18007394f  mov     r14, r8
0x180073952  call    cs:__imp_NtValidateCompositionSurfaceHandle
0x180073958  mov     ebx, eax
0x18007395a  mov     edi, 36h ; '6'
0x18007395f  test    eax, eax
0x180073961  js      loc_180073A54
0x180073967  xor     ebx, ebx
0x180073969  call    ?TryGetVtrSurfaceManager@@YAPEAVIVtrSurfaceManager@@XZ; TryGetVtrSurfaceManager(void)
0x18007396e  mov     r9, rax
0x180073971  test    rax, rax
0x180073974  jnz     loc_180073A7A
0x18007397a  test    ebx, ebx
0x18007397c  js      loc_180073A35
0x180073982  mov     rax, qword ptr [rsp+58h+arg_10.LowPart]
0x180073987  lea     rcx, [rsi+8]; Table
0x18007398b  xor     edi, edi
0x18007398d  mov     [rsp+58h+Buffer], rax
0x180073992  lea     rdx, [rsp+58h+Buffer]; Buffer
0x180073997  mov     [rsp+58h+var_20], rdi
0x18007399c  call    cs:__imp_RtlLookupElementGenericTable
0x1800739a2  test    rax, rax
0x1800739a5  jz      short loc_1800739AB
0x1800739a7  mov     rdi, [rax+8]
0x1800739ab  mov     [rsp+58h+arg_18], rdi
0x1800739b0  test    rdi, rdi
0x1800739b3  jz      short loc_1800739ED
0x1800739b5  mov     rax, [rdi]
0x1800739b8  mov     rcx, rdi
0x1800739bb  mov     sil, 1
0x1800739be  mov     rax, [rax+8]
0x1800739c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739c7  mov     [r14], rdi
0x1800739ca  test    sil, sil
0x1800739cd  jz      short loc_1800739D8
0x1800739cf  mov     rcx, rbp; hObject
0x1800739d2  call    cs:__imp_CloseHandle
0x1800739d8  mov     rbp, [rsp+58h+arg_8]
0x1800739dd  mov     eax, ebx
0x1800739df  mov     rbx, [rsp+58h+arg_0]
0x1800739e4  add     rsp, 40h
0x1800739e8  pop     r14
0x1800739ea  pop     rdi
0x1800739eb  pop     rsi
0x1800739ec  retn
0x1800739ed  mov     rdx, qword ptr [rsp+58h+arg_10.LowPart]; struct _LUID
0x1800739f2  lea     r9, [rsp+58h+arg_18]; struct CCompositionSurfaceInfo **
0x1800739f7  mov     r8, rsi; struct CCompositionSurfaceManager *
0x1800739fa  mov     rcx, rbp; void *
0x1800739fd  call    ?Create@CCompositionSurfaceInfo@@SAJPEAXU_LUID@@PEAVCCompositionSurfaceManager@@PEAPEAV1@@Z; CCompositionSurfaceInfo::Create(void *,_LUID,CCompositionSurfaceManager *,CCompositionSurfaceInfo * *)
0x180073a02  mov     ebx, eax
0x180073a04  test    eax, eax
0x180073a06  js      short loc_180073A12
0x180073a08  mov     rdi, [rsp+58h+arg_18]
0x180073a0d  xor     sil, sil
0x180073a10  jmp     short loc_1800739C7
0x180073a12  xor     edx, edx; int *
0x180073a14  mov     [rsp+58h+var_30], 0; void *
0x180073a1d  mov     r9d, eax; int
0x180073a20  mov     [rsp+58h+var_38], 46h ; 'F'; unsigned int
0x180073a28  xor     r8d, r8d; unsigned int
0x180073a2b  lea     ecx, [rdx+14h]; unsigned int
0x180073a2e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180073a33  jmp     short loc_1800739CF
0x180073a35  xor     edx, edx; int *
0x180073a37  mov     [rsp+58h+var_30], 0; void *
0x180073a40  mov     r9d, ebx; int
0x180073a43  mov     [rsp+58h+var_38], edi; unsigned int
0x180073a47  xor     r8d, r8d; unsigned int
0x180073a4a  lea     ecx, [rdx+14h]; unsigned int
0x180073a4d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180073a52  jmp     short loc_1800739D8
0x180073a54  xor     edx, edx; int *
0x180073a56  mov     [rsp+58h+var_30], 0; void *
0x180073a5f  bts     ebx, 1Ch
0x180073a63  mov     [rsp+58h+var_38], edi; unsigned int
0x180073a67  mov     r9d, ebx; int
0x180073a6a  xor     r8d, r8d; unsigned int
0x180073a6d  lea     ecx, [rdx+14h]; unsigned int
0x180073a70  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180073a75  jmp     loc_18007397A
0x180073a7a  mov     rcx, [rax]
0x180073a7d  lea     r8, [rsp+58h+arg_10]
0x180073a82  mov     rdx, rbp
0x180073a85  mov     rax, [rcx+28h]
0x180073a89  mov     rcx, r9
0x180073a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a91  jmp     loc_180073982
```
