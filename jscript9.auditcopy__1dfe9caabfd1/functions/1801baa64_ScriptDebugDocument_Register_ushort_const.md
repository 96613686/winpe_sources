# ScriptDebugDocument::Register(ushort const *)

- ea: `0x1801baa64`
- end: `0x1801bae5b`
- name: `?Register@ScriptDebugDocument@@QEAAJPEBG@Z`
- size: `1015`
- prototype: `__int64 __fastcall(ScriptDebugDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801bc50c`

## callees

- `0x180135cd0`
- `0x1801751c8`
- `0x1801a2420`
- `0x1801ac2f8`
- `0x1801baa64`
- `0x180218ff4`
- `0x1802283e4`
- `0x180228450`
- `0x180228590`
- `0x180228718`
- `0x18022897c`
- `0x180228a88`
- `0x180256a64`
- `0x180256d08`
- `0x180364010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1801babae`
- `msvcrt!wcscpy_s` at `0x1801babae`
- `msvcrt!wcsrchr` at `0x1801bab77`
- `msvcrt!wcsrchr` at `0x1801bab8e`
- `msvcrt!wcsrchr` at `0x1801bab77`
- `msvcrt!wcsrchr` at `0x1801bab8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801bab09`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1801bab09`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ScriptDebugDocument::Register(ScriptDebugDocument *this, wchar_t *a2)
{
  __int64 v3; // rax
  ScriptEngine *v4; // r13
  __int64 *v5; // r12
  bool v6; // zf
  void **ppv; // rsi
  HRESULT LatestPDM; // eax
  __int64 v9; // rcx
  int DebugApplicationCoreNoRef; // ebx
  wchar_t *v11; // rbx
  wchar_t *v12; // r14
  unsigned __int16 *v13; // r15
  wchar_t *v14; // rax
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 *v24; // r8
  char v26; // [rsp+40h] [rbp-40h]
  struct IDebugApplicationNode *v27; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  struct IDebugDocumentContext *v29; // [rsp+58h] [rbp-28h] BYREF
  struct IDebugApplicationNode *v30; // [rsp+60h] [rbp-20h] BYREF
  struct IDebugApplication64 *v31; // [rsp+68h] [rbp-18h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h]
  __int64 v33; // [rsp+78h] [rbp-8h]

  v33 = -2;
  v3 = *((_QWORD *)this + 4);
  v4 = *(ScriptEngine **)(v3 + 32);
  v5 = *(__int64 **)(*(_QWORD *)(v3 + 16) + 72LL);
  v32 = *(_QWORD *)(*v5 + 8);
  v6 = (*((_BYTE *)v5 + 36) & 1) == 0;
  v26 = *((_BYTE *)v5 + 36) & 1;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  ppv = (void **)((char *)this + 24);
  if ( !v6 )
  {
    DebugApplicationCoreNoRef = 0;
    v13 = 0;
    v12 = 0;
LABEL_24:
    if ( (int)ScriptDebugDocument::GetDocumentContext(this, *((_DWORD *)v5 + 5), 1u, &v29) >= 0 )
    {
      v31 = 0;
      if ( ((int (__fastcall *)(struct IDebugDocumentContext *, struct IDebugApplication64 **))v29->lpVtbl->GetDocument)(
             v29,
             &v31) >= 0 )
      {
        v28 = 0;
        if ( ((__int64 (__fastcall *)(struct IDebugApplication64 *, GUID *, __int64 *))v31->lpVtbl->QueryInterface)(
               v31,
               &GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a,
               &v28) >= 0 )
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL) + 56LL) = v28;
        ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v28);
      }
      ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((__int64 *)&v31);
    }
    if ( !v26 )
    {
      DebugApplicationCoreNoRef = ScriptDebugDocument::AddText(this);
      if ( DebugApplicationCoreNoRef >= 0 )
      {
        if ( !(*(unsigned int (__fastcall **)(void *, struct IDebugApplicationNode **))(*(_QWORD *)*ppv + 128LL))(
                *ppv,
                &v27) )
        {
          ScriptDebugDocument::DbgGetRootApplicationNode(this, &v30);
          v28 = 0;
          if ( !(**(unsigned int (__fastcall ***)(void *, GUID *, __int64 *))*ppv)(
                  *ppv,
                  &GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a,
                  &v28) )
          {
            v20 = operator new[]<HeapAllocator>(
                    32,
                    v18,
                    v19,
                    (__int64 (__fastcall *)(char *, __int64))HeapAllocator::NoThrowAlloc);
            if ( v20 )
            {
              v21 = *v5;
              v22 = v28;
              *(_QWORD *)v20 = &ScriptDocumentProviderBridge::`vftable';
              *(_DWORD *)(v20 + 8) = 0;
              *(_QWORD *)(v20 + 16) = v22;
              *(_QWORD *)(v20 + 24) = v21;
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
              v31 = (struct IDebugApplication64 *)v20;
              _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
            }
            else
            {
              v20 = 0;
              v31 = 0;
            }
            v23 = v20;
            if ( !v20 )
              v23 = v28;
            ((void (__fastcall *)(struct IDebugApplicationNode *, __int64))v27->lpVtbl->SetDocumentProvider)(v27, v23);
            ATL::CComPtr<ScriptDocumentProviderBridge>::~CComPtr<ScriptDocumentProviderBridge>((ScriptDocumentProviderBridge **)&v31);
          }
          ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(&v28);
        }
        DebugApplicationCoreNoRef = ScriptDebugDocument::AttachNode(this, v27, v30);
        if ( DebugApplicationCoreNoRef >= 0 )
          *((_BYTE *)this + 52) = 1;
      }
    }
    goto LABEL_45;
  }
  if ( ShouldUseLocalPDM() )
    LatestPDM = LoadLatestPDM(&CLSID_CDebugDocumentHelper, &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871, ppv);
  else
    LatestPDM = CoCreateInstance(&CLSID_CDebugDocumentHelper, 0, 1u, &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871, ppv);
  DebugApplicationCoreNoRef = LatestPDM;
  if ( LatestPDM )
    goto LABEL_51;
  v11 = L"script block";
  if ( a2 )
    v11 = a2;
  if ( *(_QWORD *)(*v5 + 8) == -1 )
  {
    v12 = v11;
    v13 = (unsigned __int16 *)AllocateArray<HeapAllocator,unsigned short,1>(
                                v9,
                                (__int64 (__fastcall *)(char *, __int64))HeapAllocator::NoThrowAlloc,
                                0xFFu);
    ScriptDebugDocument::GetFormattedTitle(this, (char *)v11, v13);
  }
  else
  {
    v13 = v11;
    v12 = (wchar_t *)AllocateArray<HeapAllocator,unsigned short,1>(
                       v9,
                       (__int64 (__fastcall *)(char *, __int64))HeapAllocator::NoThrowAlloc,
                       0xFFu);
    v14 = wcsrchr(v11, 0x2Fu);
    if ( v14 || (v14 = wcsrchr(v11, 0x5Cu)) != 0 )
      v11 = v14 + 1;
    wcscpy_s(v12, 0xFFu, v11);
  }
  v31 = 0;
  DebugApplicationCoreNoRef = ScriptEngine::GetDebugApplicationCoreNoRef(v4, &v31);
  if ( DebugApplicationCoreNoRef >= 0 )
  {
    v16 = 1;
    if ( v32 != -1 )
      v16 = 8;
    DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(void *, struct IDebugApplication64 *, wchar_t *, unsigned __int16 *, int))(*(_QWORD *)*ppv + 24LL))(
                                  *ppv,
                                  v31,
                                  v12,
                                  v13,
                                  v16);
    if ( DebugApplicationCoreNoRef >= 0 )
    {
      v17 = v4 ? (__int64)v4 + 48 : 0LL;
      DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64, _DWORD, char *))(*(_QWORD *)*ppv + 80LL))(
                                    *ppv,
                                    0,
                                    *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL) + 24LL),
                                    v17,
                                    0,
                                    (char *)this + 40);
      if ( DebugApplicationCoreNoRef >= 0 )
        goto LABEL_24;
    }
  }
LABEL_45:
  if ( v32 == -1 )
  {
    if ( v13 )
    {
      v24 = v13;
LABEL_50:
      DeleteArray<HeapAllocator,unsigned short const *>(v15, 255, v24);
    }
  }
  else if ( v12 )
  {
    v24 = v12;
    goto LABEL_50;
  }
LABEL_51:
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((__int64 *)&v29);
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((__int64 *)&v27);
  ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>((__int64 *)&v30);
  return (unsigned int)DebugApplicationCoreNoRef;
}

```

## disassembly

```asm
0x1801baa64  mov     rax, rsp
0x1801baa67  mov     [rax+10h], rdx
0x1801baa6b  mov     [rax+8], rcx
0x1801baa6f  push    rbp
0x1801baa70  push    rsi
0x1801baa71  push    rdi
0x1801baa72  push    r12
0x1801baa74  push    r13
0x1801baa76  push    r14
0x1801baa78  push    r15
0x1801baa7a  mov     rbp, rsp
0x1801baa7d  sub     rsp, 80h
0x1801baa84  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1801baa8c  mov     [rax+18h], rbx
0x1801baa90  mov     rdi, [rbp+arg_0]
0x1801baa94  mov     rax, [rdi+20h]
0x1801baa98  mov     r13, [rax+20h]
0x1801baa9c  mov     rax, [rax+10h]
0x1801baaa0  mov     r12, [rax+48h]
0x1801baaa4  mov     rax, [r12]
0x1801baaa8  mov     rax, [rax+8]
0x1801baaac  mov     [rbp+var_10], rax
0x1801baab0  mov     al, [r12+24h]
0x1801baab5  and     al, 1
0x1801baab7  mov     [rbp+var_40], al
0x1801baaba  mov     r14d, 0
0x1801baac0  mov     [rbp+var_20], r14
0x1801baac4  mov     [rbp+var_38], r14
0x1801baac8  mov     [rbp+var_28], r14
0x1801baacc  lea     rsi, [rdi+18h]
0x1801baad0  jnz     loc_1801BAC5E
0x1801baad6  call    ?ShouldUseLocalPDM@@YAHXZ; ShouldUseLocalPDM(void)
0x1801baadb  lea     rcx, CLSID_CDebugDocumentHelper; struct _GUID *
0x1801baae2  test    eax, eax
0x1801baae4  jz      short loc_1801BAAF7
0x1801baae6  mov     r8, rsi; void **
0x1801baae9  lea     rdx, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; struct _GUID *
0x1801baaf0  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x1801baaf5  jmp     short loc_1801BAB15
0x1801baaf7  mov     [rsp+80h+ppv], rsi; ppv
0x1801baafc  lea     r9, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; riid
0x1801bab03  xor     edx, edx; pUnkOuter
0x1801bab05  lea     r8d, [rdx+1]; dwClsContext
0x1801bab09  call    cs:__imp_CoCreateInstance
0x1801bab10  nop     dword ptr [rax+rax+00h]
0x1801bab15  mov     ebx, eax
0x1801bab17  test    eax, eax
0x1801bab19  jnz     loc_1801BAE20
0x1801bab1f  mov     rax, [rbp+Str]
0x1801bab23  lea     rbx, aScriptBlock; "script block"
0x1801bab2a  test    rax, rax
0x1801bab2d  cmovnz  rbx, rax
0x1801bab31  mov     rax, [r12]
0x1801bab35  mov     r8d, 0FFh
0x1801bab3b  lea     rdx, ?NoThrowAlloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAlloc(unsigned __int64)
0x1801bab42  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1801bab47  jnz     short loc_1801BAB64
0x1801bab49  mov     r14, rbx
0x1801bab4c  call    ??$AllocateArray@UHeapAllocator@@G$00@@YAPEAGPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,ushort,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1801bab51  mov     r15, rax
0x1801bab54  mov     r8, rax; unsigned __int16 *
0x1801bab57  mov     rdx, rbx; unsigned __int16 *
0x1801bab5a  mov     rcx, rdi; this
0x1801bab5d  call    ?GetFormattedTitle@ScriptDebugDocument@@QEAAXPEBGPEAGH@Z; ScriptDebugDocument::GetFormattedTitle(ushort const *,ushort *,int)
0x1801bab62  jmp     short loc_1801BABBA
0x1801bab64  mov     r15, rbx
0x1801bab67  call    ??$AllocateArray@UHeapAllocator@@G$00@@YAPEAGPEAUHeapAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<HeapAllocator,ushort,1>(HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x1801bab6c  mov     r14, rax
0x1801bab6f  mov     edx, 2Fh ; '/'; Ch
0x1801bab74  mov     rcx, rbx; Str
0x1801bab77  call    cs:__imp_wcsrchr
0x1801bab7e  nop     dword ptr [rax+rax+00h]
0x1801bab83  test    rax, rax
0x1801bab86  jnz     short loc_1801BAB9F
0x1801bab88  lea     edx, [rax+5Ch]; Ch
0x1801bab8b  mov     rcx, rbx; Str
0x1801bab8e  call    cs:__imp_wcsrchr
0x1801bab95  nop     dword ptr [rax+rax+00h]
0x1801bab9a  test    rax, rax
0x1801bab9d  jz      short loc_1801BABA3
0x1801bab9f  lea     rbx, [rax+2]
0x1801baba3  mov     r8, rbx; Source
0x1801baba6  mov     edx, 0FFh; SizeInWords
0x1801babab  mov     rcx, r14; Destination
0x1801babae  call    cs:__imp_wcscpy_s
0x1801babb5  nop     dword ptr [rax+rax+00h]
0x1801babba  mov     [rbp+var_18], 0
0x1801babc2  lea     rdx, [rbp+var_18]; struct IDebugApplication64 **
0x1801babc6  mov     rcx, r13; this
0x1801babc9  call    ?GetDebugApplicationCoreNoRef@ScriptEngine@@QEAAJPEAPEAUIDebugApplication64@@@Z; ScriptEngine::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)
0x1801babce  mov     ebx, eax
0x1801babd0  test    eax, eax
0x1801babd2  js      loc_1801BADFC
0x1801babd8  mov     rcx, [rsi]
0x1801babdb  mov     rax, [rcx]
0x1801babde  mov     edx, 1
0x1801babe3  lea     r8d, [rdx+7]
0x1801babe7  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1801babec  cmovnz  edx, r8d
0x1801babf0  mov     dword ptr [rsp+80h+ppv], edx
0x1801babf4  mov     r9, r15
0x1801babf7  mov     r8, r14
0x1801babfa  mov     rdx, [rbp+var_18]
0x1801babfe  mov     rax, [rax+18h]
0x1801bac02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bac07  mov     ebx, eax
0x1801bac09  test    eax, eax
0x1801bac0b  js      loc_1801BADFC
0x1801bac11  mov     rcx, [rsi]
0x1801bac14  mov     rax, [rcx]
0x1801bac17  mov     r10, [rax+50h]
0x1801bac1b  test    r13, r13
0x1801bac1e  jz      short loc_1801BAC26
0x1801bac20  lea     rax, [r13+30h]
0x1801bac24  jmp     short loc_1801BAC28
0x1801bac26  xor     eax, eax
0x1801bac28  lea     r9, [rdi+28h]
0x1801bac2c  mov     rdx, [rdi+20h]
0x1801bac30  mov     r8, [rdx+10h]
0x1801bac34  mov     [rsp+80h+var_58], r9
0x1801bac39  mov     dword ptr [rsp+80h+ppv], 0
0x1801bac41  mov     r9, rax
0x1801bac44  mov     r8d, [r8+18h]
0x1801bac48  xor     edx, edx
0x1801bac4a  mov     rax, r10
0x1801bac4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bac52  mov     ebx, eax
0x1801bac54  test    eax, eax
0x1801bac56  js      loc_1801BADFC
0x1801bac5c  jmp     short loc_1801BAC66
0x1801bac5e  xor     ebx, ebx
0x1801bac60  xor     r15d, r15d
0x1801bac63  xor     r14d, r14d
0x1801bac66  lea     r9, [rbp+var_28]; struct IDebugDocumentContext **
0x1801bac6a  mov     r8d, 1; unsigned int
0x1801bac70  mov     edx, [r12+14h]; unsigned int
0x1801bac75  mov     rcx, rdi; this
0x1801bac78  call    ?GetDocumentContext@ScriptDebugDocument@@QEAAJKKPEAPEAUIDebugDocumentContext@@@Z; ScriptDebugDocument::GetDocumentContext(ulong,ulong,IDebugDocumentContext * *)
0x1801bac7d  test    eax, eax
0x1801bac7f  js      short loc_1801BACEA
0x1801bac81  mov     [rbp+var_18], 0
0x1801bac89  mov     rcx, [rbp+var_28]
0x1801bac8d  mov     rax, [rcx]
0x1801bac90  lea     rdx, [rbp+var_18]
0x1801bac94  mov     rax, [rax+18h]
0x1801bac98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bac9d  test    eax, eax
0x1801bac9f  js      short loc_1801BACE1
0x1801baca1  mov     [rbp+var_30], 0
0x1801baca9  mov     rcx, [rbp+var_18]
0x1801bacad  mov     rax, [rcx]
0x1801bacb0  lea     r8, [rbp+var_30]
0x1801bacb4  lea     rdx, _GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a
0x1801bacbb  mov     rax, [rax]
0x1801bacbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bacc3  test    eax, eax
0x1801bacc5  js      short loc_1801BACD7
0x1801bacc7  mov     rax, [rdi+20h]
0x1801baccb  mov     rcx, [rax+10h]
0x1801baccf  mov     rax, [rbp+var_30]
0x1801bacd3  mov     [rcx+38h], rax
0x1801bacd7  lea     rcx, [rbp+var_30]
0x1801bacdb  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bace0  nop
0x1801bace1  lea     rcx, [rbp+var_18]
0x1801bace5  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bacea  cmp     [rbp+var_40], 0
0x1801bacee  jnz     loc_1801BADFC
0x1801bacf4  mov     rcx, rdi; this
0x1801bacf7  call    ?AddText@ScriptDebugDocument@@AEAAJXZ; ScriptDebugDocument::AddText(void)
0x1801bacfc  mov     ebx, eax
0x1801bacfe  test    eax, eax
0x1801bad00  js      loc_1801BADFC
0x1801bad06  mov     rcx, [rsi]
0x1801bad09  mov     rax, [rcx]
0x1801bad0c  lea     rdx, [rbp+var_38]
0x1801bad10  mov     rax, [rax+80h]
0x1801bad17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bad1c  test    eax, eax
0x1801bad1e  jnz     loc_1801BADE2
0x1801bad24  lea     rdx, [rbp+var_20]; struct IDebugApplicationNode **
0x1801bad28  mov     rcx, rdi; this
0x1801bad2b  call    ?DbgGetRootApplicationNode@ScriptDebugDocument@@QEAAJPEAPEAUIDebugApplicationNode@@@Z; ScriptDebugDocument::DbgGetRootApplicationNode(IDebugApplicationNode * *)
0x1801bad30  mov     [rbp+var_30], 0
0x1801bad38  mov     rcx, [rsi]
0x1801bad3b  mov     rax, [rcx]
0x1801bad3e  lea     r8, [rbp+var_30]
0x1801bad42  lea     rdx, _GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a
0x1801bad49  mov     rax, [rax]
0x1801bad4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bad51  test    eax, eax
0x1801bad53  jnz     loc_1801BADD9
0x1801bad59  lea     r9, ?NoThrowAlloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::NoThrowAlloc(unsigned __int64)
0x1801bad60  lea     ecx, [rax+20h]
0x1801bad63  call    ??$?_UUHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@_NP80@EAAPEAD0@Z@Z; operator new[]<HeapAllocator>(unsigned __int64,HeapAllocator *,bool,char * (HeapAllocator::*)(unsigned __int64))
0x1801bad68  mov     rbx, rax
0x1801bad6b  test    rax, rax
0x1801bad6e  jz      short loc_1801BADAC
0x1801bad70  mov     rax, [r12]
0x1801bad74  mov     rcx, [rbp+var_30]
0x1801bad78  lea     rdx, ??_7ScriptDocumentProviderBridge@@6B@; const ScriptDocumentProviderBridge::`vftable'
0x1801bad7f  mov     [rbx], rdx
0x1801bad82  mov     dword ptr [rbx+8], 0
0x1801bad89  mov     [rbx+10h], rcx
0x1801bad8d  mov     [rbx+18h], rax
0x1801bad91  test    rcx, rcx
0x1801bad94  jz      short loc_1801BADA2
0x1801bad96  mov     rax, [rcx]
0x1801bad99  mov     rax, [rax+8]
0x1801bad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bada2  mov     [rbp+var_18], rbx
0x1801bada6  lock inc dword ptr [rbx+8]
0x1801badaa  jmp     short loc_1801BADB2
0x1801badac  xor     ebx, ebx
0x1801badae  mov     [rbp+var_18], rbx
0x1801badb2  mov     rcx, [rbp+var_38]
0x1801badb6  mov     rax, [rcx]
0x1801badb9  mov     rax, [rax+40h]
0x1801badbd  test    rbx, rbx
0x1801badc0  mov     rdx, rbx
0x1801badc3  jnz     short loc_1801BADC9
0x1801badc5  mov     rdx, [rbp+var_30]
0x1801badc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801badce  nop
0x1801badcf  lea     rcx, [rbp+var_18]
0x1801badd3  call    ??1?$CComPtr@VScriptDocumentProviderBridge@@@ATL@@QEAA@XZ; ATL::CComPtr<ScriptDocumentProviderBridge>::~CComPtr<ScriptDocumentProviderBridge>(void)
0x1801badd8  nop
0x1801badd9  lea     rcx, [rbp+var_30]
0x1801baddd  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bade2  mov     r8, [rbp+var_20]; struct IDebugApplicationNode *
0x1801bade6  mov     rdx, [rbp+var_38]; struct IDebugApplicationNode *
0x1801badea  mov     rcx, rdi; this
0x1801baded  call    ?AttachNode@ScriptDebugDocument@@AEAAJPEAUIDebugApplicationNode@@0@Z; ScriptDebugDocument::AttachNode(IDebugApplicationNode *,IDebugApplicationNode *)
0x1801badf2  mov     ebx, eax
0x1801badf4  test    eax, eax
0x1801badf6  js      short loc_1801BADFC
0x1801badf8  mov     byte ptr [rdi+34h], 1
0x1801badfc  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1801bae01  jnz     short loc_1801BAE0D
0x1801bae03  test    r15, r15
0x1801bae06  jz      short loc_1801BAE20
0x1801bae08  mov     r8, r15
0x1801bae0b  jmp     short loc_1801BAE15
0x1801bae0d  test    r14, r14
0x1801bae10  jz      short loc_1801BAE20
0x1801bae12  mov     r8, r14
0x1801bae15  mov     edx, 0FFh
0x1801bae1a  call    ??$DeleteArray@UHeapAllocator@@PEBG@@YAXPEAUHeapAllocator@@_KPEAPEBG@Z; DeleteArray<HeapAllocator,ushort const *>(HeapAllocator *,unsigned __int64,ushort const * *)
0x1801bae1f  nop
0x1801bae20  lea     rcx, [rbp+var_28]
0x1801bae24  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bae29  nop
0x1801bae2a  lea     rcx, [rbp+var_38]
0x1801bae2e  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bae33  nop
0x1801bae34  lea     rcx, [rbp+var_20]
0x1801bae38  call    ??1?$CComPtr@UIDebugApplicationThread64@@@ATL@@QEAA@XZ; ATL::CComPtr<IDebugApplicationThread64>::~CComPtr<IDebugApplicationThread64>(void)
0x1801bae3d  mov     eax, ebx
0x1801bae3f  mov     rbx, [rsp+80h+arg_10]
0x1801bae47  add     rsp, 80h
0x1801bae4e  pop     r15
0x1801bae50  pop     r14
0x1801bae52  pop     r13
0x1801bae54  pop     r12
0x1801bae56  pop     rdi
0x1801bae57  pop     rsi
0x1801bae58  pop     rbp
0x1801bae59  retn
```
