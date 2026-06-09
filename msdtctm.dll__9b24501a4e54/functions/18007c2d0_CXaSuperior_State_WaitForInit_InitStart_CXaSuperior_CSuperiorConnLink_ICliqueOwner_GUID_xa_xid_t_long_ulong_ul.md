# CXaSuperior_State_WaitForInit::InitStart(CXaSuperior *,CSuperiorConnLink *,ICliqueOwner *,_GUID *,xa_xid_t *,long,ulong,ulong,char *,int,_GUID *)

- ea: `0x18007c2d0`
- end: `0x18007c592`
- name: `?InitStart@CXaSuperior_State_WaitForInit@@UEAA?AW4_XaSuperiorStart_Result@@PEAVCXaSuperior@@PEAVCSuperiorConnLink@@PEAUICliqueOwner@@PEAU_GUID@@PEAUxa_xid_t@@JKKPEADH3@Z`
- size: `706`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18006e904`
- `0x18006e928`
- `0x18006ed68`
- `0x180073a6c`
- `0x180075b1c`
- `0x18007812c`
- `0x18007c2d0`
- `0x180085624`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c3ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c3ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007c382`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007c382`

## string_xrefs

- `0x18007c392`: `com\complus\dtc\dtc\tm\src\tmxasup.cpp`
- `0x18007c47e`: `com\complus\dtc\dtc\tm\src\tmxasup.cpp`
- `0x18007c4e9`: `com\complus\dtc\dtc\tm\src\tmxasup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXaSuperior_State_WaitForInit::InitStart(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        _OWORD *a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        int a11,
        struct _GUID *a12)
{
  struct _GUID *v15; // rbp
  CTmTrace *v16; // rcx
  CTx *v17; // rax
  CTx *v18; // rsi
  _QWORD *v19; // r15
  int inited; // eax
  CTmTrace *v21; // rcx
  void *v22; // r9
  int v23; // edi

  *(_QWORD *)(a2 + 112) = a4;
  *(_OWORD *)(a2 + 316) = *a5;
  *(_OWORD *)(a2 + 332) = *a6;
  *(_OWORD *)(a2 + 348) = a6[1];
  *(_OWORD *)(a2 + 364) = a6[2];
  *(_OWORD *)(a2 + 380) = a6[3];
  *(_OWORD *)(a2 + 396) = a6[4];
  *(_OWORD *)(a2 + 412) = a6[5];
  *(_OWORD *)(a2 + 428) = a6[6];
  *(_OWORD *)(a2 + 444) = a6[7];
  *(_OWORD *)(a2 + 456) = *(_OWORD *)((char *)a6 + 124);
  *(_DWORD *)(a2 + 488) = a11;
  v15 = (struct _GUID *)(a2 + 472);
  if ( CoCreateGuid((GUID *)(a2 + 472)) < 0 )
    CTmTrace::InternalError(v16, "com\\complus\\dtc\\dtc\\tm\\src\\tmxasup.cpp", 3603);
  v17 = (CTx *)HeapAlloc(g_CTx_MemAlloc, 0, 0x5D8u);
  if ( v17 )
    v18 = CTx::CTx(v17, v15);
  else
    v18 = 0;
  if ( !v18 )
    return 2;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 112) + 8LL))(*(_QWORD *)(a2 + 112));
  v19 = (_QWORD *)(a2 + 496);
  inited = CTx::InitXaSuperior(v18, *(_QWORD *)(a2 + 112), a7);
  if ( inited == 1 )
  {
    DtcWriteToEventLoggerExUnFilteredA(
      1u,
      2u,
      0xC0001046,
      v22,
      0,
      a10,
      0,
      (void *)((a2 + 80) & ((unsigned __int128)-(__int128)a2 >> 64)),
      a2 + 120);
    return 4;
  }
  if ( inited == 2 )
    return 2;
  if ( inited != 3 )
    CTmTrace::InvalidValue(v21, "com\\complus\\dtc\\dtc\\tm\\src\\tmxasup.cpp", 3641, inited);
  v23 = CXaFindTrans::Insert(v21, a5, a2, a2 + 504);
  if ( v23 == 1 )
  {
    *(_QWORD *)(a3 + 56) = (a2 + 8) & -(__int64)(a2 != 0);
    (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)(a2 + 128) + 8LL))(a2 + 128, a3 + 8);
    (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)a1 + 264LL))(a1, a2);
    *a12 = *v15;
    return 1;
  }
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)((a2 + 16) & -(__int64)(a2 != 0)) + 56LL))((a2 + 16) & -(__int64)(a2 != 0));
  (**(void (__fastcall ***)(_QWORD))*v19)(*v19);
  *v19 = 0;
  CTx::Zap(v18);
  if ( v23 == 2 )
    return 2;
  if ( v23 != 3 )
    CTmTrace::InvalidValue(
      (CTmTrace *)(unsigned int)(v23 - 2),
      "com\\complus\\dtc\\dtc\\tm\\src\\tmxasup.cpp",
      3670,
      v23);
  return 3;
}

```

## disassembly

```asm
0x18007c2d0  push    rbx
0x18007c2d2  push    rbp
0x18007c2d3  push    rsi
0x18007c2d4  push    rdi
0x18007c2d5  push    r12
0x18007c2d7  push    r13
0x18007c2d9  push    r14
0x18007c2db  push    r15
0x18007c2dd  sub     rsp, 68h
0x18007c2e1  mov     r13, r8
0x18007c2e4  mov     rbx, rdx
0x18007c2e7  mov     r12, rcx
0x18007c2ea  mov     [rdx+70h], r9
0x18007c2ee  mov     rdi, [rsp+0A8h+arg_20]
0x18007c2f6  movups  xmm0, xmmword ptr [rdi]
0x18007c2f9  movdqu  xmmword ptr [rdx+13Ch], xmm0
0x18007c301  mov     rax, [rsp+0A8h+arg_28]
0x18007c309  movups  xmm0, xmmword ptr [rax]
0x18007c30c  movups  xmmword ptr [rdx+14Ch], xmm0
0x18007c313  movups  xmm1, xmmword ptr [rax+10h]
0x18007c317  movups  xmmword ptr [rdx+15Ch], xmm1
0x18007c31e  movups  xmm0, xmmword ptr [rax+20h]
0x18007c322  movups  xmmword ptr [rdx+16Ch], xmm0
0x18007c329  movups  xmm1, xmmword ptr [rax+30h]
0x18007c32d  movups  xmmword ptr [rdx+17Ch], xmm1
0x18007c334  movups  xmm0, xmmword ptr [rax+40h]
0x18007c338  movups  xmmword ptr [rdx+18Ch], xmm0
0x18007c33f  movups  xmm1, xmmword ptr [rax+50h]
0x18007c343  movups  xmmword ptr [rdx+19Ch], xmm1
0x18007c34a  movups  xmm0, xmmword ptr [rax+60h]
0x18007c34e  movups  xmmword ptr [rdx+1ACh], xmm0
0x18007c355  movups  xmm1, xmmword ptr [rax+70h]
0x18007c359  movups  xmmword ptr [rdx+1BCh], xmm1
0x18007c360  movups  xmm0, xmmword ptr [rax+7Ch]
0x18007c364  movups  xmmword ptr [rdx+1C8h], xmm0
0x18007c36b  mov     eax, [rsp+0A8h+arg_50]
0x18007c372  mov     [rdx+1E8h], eax
0x18007c378  lea     rbp, [rdx+1D8h]
0x18007c37f  mov     rcx, rbp; pguid
0x18007c382  call    cs:__imp_CoCreateGuid
0x18007c388  test    eax, eax
0x18007c38a  jns     short loc_18007C39F
0x18007c38c  mov     r8d, 0E13h; int
0x18007c392  lea     rdx, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\tm\\src\\tmxasu"...
0x18007c399  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x18007c39f  xor     edx, edx; dwFlags
0x18007c3a1  mov     r8d, 5D8h; dwBytes
0x18007c3a7  mov     rcx, cs:?g_CTx_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x18007c3ae  call    cs:__imp_HeapAlloc
0x18007c3b4  mov     [rsp+0A8h+arg_20], rax
0x18007c3bc  test    rax, rax
0x18007c3bf  jz      short loc_18007C3D1
0x18007c3c1  mov     rdx, rbp; struct _GUID *
0x18007c3c4  mov     rcx, rax; this
0x18007c3c7  call    ??0CTx@@QEAA@PEAU_GUID@@@Z; CTx::CTx(_GUID *)
0x18007c3cc  mov     rsi, rax
0x18007c3cf  jmp     short loc_18007C3D3
0x18007c3d1  xor     esi, esi
0x18007c3d3  test    rsi, rsi
0x18007c3d6  jz      loc_18007C57C
0x18007c3dc  mov     rcx, [rbx+70h]
0x18007c3e0  mov     rax, [rcx]
0x18007c3e3  mov     rax, [rax+8]
0x18007c3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c3ec  mov     rax, rbx
0x18007c3ef  lea     rcx, [rbx+10h]
0x18007c3f3  neg     rax
0x18007c3f6  sbb     r14, r14
0x18007c3f9  and     r14, rcx
0x18007c3fc  lea     r15, [rbx+1F0h]
0x18007c403  lea     r8, [rbx+78h]
0x18007c407  mov     rax, rbx
0x18007c40a  lea     rcx, [rbx+50h]
0x18007c40e  neg     rax
0x18007c411  sbb     rdx, rdx
0x18007c414  and     rdx, rcx
0x18007c417  mov     [rsp+0A8h+var_58], r14
0x18007c41c  mov     [rsp+0A8h+var_60], r15
0x18007c421  mov     qword ptr [rsp+0A8h+var_68], r8; int
0x18007c426  mov     [rsp+0A8h+var_70], rdx; void *
0x18007c42b  mov     [rsp+0A8h+var_78], rbx
0x18007c430  mov     rax, qword ptr [rsp+0A8h+arg_48]
0x18007c438  mov     qword ptr [rsp+0A8h+var_80], rax; unsigned int
0x18007c43d  mov     eax, [rsp+0A8h+arg_40]
0x18007c444  mov     dword ptr [rsp+0A8h+var_88], eax
0x18007c448  mov     r8d, [rsp+0A8h+arg_30]
0x18007c450  mov     rdx, [rbx+70h]
0x18007c454  mov     rcx, rsi
0x18007c457  call    ?InitXaSuperior@CTx@@QEAA?AW4_Init_Tx_XaTrans@@PEAUICliqueOwner@@JKKPEADPEAVITxToSuperior@@PEAVITxToXaSuperior@@PEAPEAVISuperiorToTx@@PEAPEAVIXaSuperiorToTx@@PEAVCTxStatusNotify@@@Z; CTx::InitXaSuperior(ICliqueOwner *,long,ulong,ulong,char *,ITxToSuperior *,ITxToXaSuperior *,ISuperiorToTx * *,IXaSuperiorToTx * *,CTxStatusNotify *)
0x18007c45c  mov     edx, eax
0x18007c45e  sub     edx, 1
0x18007c461  jz      loc_18007C558
0x18007c467  sub     edx, 1
0x18007c46a  jz      loc_18007C57C
0x18007c470  cmp     edx, 1
0x18007c473  jz      short loc_18007C48B
0x18007c475  mov     r9d, eax; int
0x18007c478  mov     r8d, 0E39h; int
0x18007c47e  lea     rdx, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\tm\\src\\tmxasu"...
0x18007c485  call    ?InvalidValue@CTmTrace@@QEAAXPEBDHJ@Z; CTmTrace::InvalidValue(char const *,int,long)
0x18007c48b  lea     r9, [rbx+1F8h]
0x18007c492  mov     r8, rbx
0x18007c495  mov     rdx, rdi
0x18007c498  call    ?Insert@CXaFindTrans@@QEAA?AW4_XaSuperiorInsert_Result@@PEAU_GUID@@PEAVCXaSuperior@@PEAJ@Z; CXaFindTrans::Insert(_GUID *,CXaSuperior *,long *)
0x18007c49d  mov     edi, eax
0x18007c49f  cmp     eax, 1
0x18007c4a2  jz      short loc_18007C500
0x18007c4a4  mov     rdx, [r14]
0x18007c4a7  mov     rcx, r14
0x18007c4aa  mov     rax, [rdx+38h]
0x18007c4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4b3  mov     rcx, [r15]
0x18007c4b6  mov     rdx, [rcx]
0x18007c4b9  mov     rax, [rdx]
0x18007c4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4c1  mov     qword ptr [r15], 0
0x18007c4c8  mov     rcx, rsi; this
0x18007c4cb  call    ?Zap@CTx@@QEAAXXZ; CTx::Zap(void)
0x18007c4d0  mov     ecx, edi
0x18007c4d2  sub     ecx, 2; this
0x18007c4d5  jz      loc_18007C57C
0x18007c4db  cmp     ecx, 1
0x18007c4de  jz      short loc_18007C4F6
0x18007c4e0  mov     r9d, edi; int
0x18007c4e3  mov     r8d, 0E56h; int
0x18007c4e9  lea     rdx, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\tm\\src\\tmxasu"...
0x18007c4f0  call    ?InvalidValue@CTmTrace@@QEAAXPEBDHJ@Z; CTmTrace::InvalidValue(char const *,int,long)
0x18007c4f6  mov     eax, 3
0x18007c4fb  jmp     loc_18007C581
0x18007c500  mov     rax, rbx
0x18007c503  lea     rdx, [rbx+8]
0x18007c507  neg     rax
0x18007c50a  sbb     rcx, rcx
0x18007c50d  and     rcx, rdx
0x18007c510  mov     [r13+38h], rcx
0x18007c514  lea     rcx, [rbx+80h]
0x18007c51b  mov     rax, [rcx]
0x18007c51e  lea     rdx, [r13+8]
0x18007c522  mov     rax, [rax+8]
0x18007c526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c52b  mov     rcx, [r12]
0x18007c52f  mov     rax, [rcx+108h]
0x18007c536  mov     rdx, rbx
0x18007c539  mov     rcx, r12
0x18007c53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c541  movups  xmm0, xmmword ptr [rbp+0]
0x18007c545  mov     rcx, [rsp+0A8h+arg_58]
0x18007c54d  movdqu  xmmword ptr [rcx], xmm0
0x18007c551  mov     eax, 1
0x18007c556  jmp     short loc_18007C581
0x18007c558  xor     eax, eax
0x18007c55a  lea     edx, [rax+2]; unsigned __int16
0x18007c55d  lea     ecx, [rax+1]; unsigned __int16
0x18007c560  mov     [rsp+0A8h+var_78], rax; char **
0x18007c565  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x18007c56a  mov     r8d, 0C0001046h; unsigned int
0x18007c570  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExUnFilteredA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x18007c575  mov     eax, 4
0x18007c57a  jmp     short loc_18007C581
0x18007c57c  mov     eax, 2
0x18007c581  add     rsp, 68h
0x18007c585  pop     r15
0x18007c587  pop     r14
0x18007c589  pop     r13
0x18007c58b  pop     r12
0x18007c58d  pop     rdi
0x18007c58e  pop     rsi
0x18007c58f  pop     rbp
0x18007c590  pop     rbx
0x18007c591  retn
```
