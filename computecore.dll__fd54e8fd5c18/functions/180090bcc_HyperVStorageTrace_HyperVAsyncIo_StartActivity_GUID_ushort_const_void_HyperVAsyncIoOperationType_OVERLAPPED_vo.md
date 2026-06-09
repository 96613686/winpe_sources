# HyperVStorageTrace::HyperVAsyncIo::StartActivity(_GUID,ushort const *,void *,HyperVAsyncIoOperationType,_OVERLAPPED *,void const *,ulong)

- ea: `0x180090bcc`
- end: `0x1800910a7`
- name: `?StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800910b0`

## callees

- `0x1800016ec`
- `0x1800067c0`
- `0x180007dbc`
- `0x180007e24`
- `0x1800136d0`
- `0x180014a2c`
- `0x1800150dc`
- `0x180066284`
- `0x180081f2c`
- `0x180082140`
- `0x180090bcc`
- `0x180092168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090da5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090e49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090e49`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180090d86`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180090d86`
- `RPCRT4!UuidCreate` at `0x180090c9f`
- `RPCRT4!UuidCreate` at `0x180090c9f`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVAsyncIo::StartActivity(
        __int64 a1,
        __int128 *a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *a7,
        unsigned int a8)
{
  __int128 v8; // xmm0
  __int64 *v10; // rax
  __int64 v12; // r13
  __int64 v13; // r8
  __int64 *v14; // rdi
  wchar_t *v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // r14
  int IsDebugTraceEnabled; // r15d
  _DWORD *v19; // rcx
  char v20; // si
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rsi
  __int64 v24; // rcx
  RTL_SRWLOCK *v25; // rcx
  __int64 v26; // rsi
  bool v27; // cc
  __int64 *v28; // rcx
  void *v29; // r12
  DWORD CurrentThreadId; // eax
  __int64 v31; // r8
  int v32; // r9d
  int v33; // ecx
  __int64 v34; // rax
  int v35; // eax
  _DWORD *v36; // rax
  void *v37; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh] BYREF
  void *v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  void **v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 *v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  int v59; // [rsp+ECh] [rbp-14h]
  __int64 *v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  __int64 *v62; // [rsp+100h] [rbp+0h]
  int v63; // [rsp+108h] [rbp+8h]
  int v64; // [rsp+10Ch] [rbp+Ch]
  __int64 **v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  __int64 *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h]
  __int64 *v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+140h] [rbp+40h]
  __int64 v72; // [rsp+148h] [rbp+48h]
  int *v73; // [rsp+150h] [rbp+50h]
  __int64 v74; // [rsp+158h] [rbp+58h]
  __int64 *v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  void **v77; // [rsp+170h] [rbp+70h]
  __int64 v78; // [rsp+178h] [rbp+78h]
  unsigned int *v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+188h] [rbp+88h]

  v8 = *a2;
  v37 = a7;
  v10 = a3;
  if ( !a3 )
    v10 = &qword_1800AD7F8;
  v12 = -1;
  v13 = -1;
  *(_OWORD *)(a1 + 336) = v8;
  do
    ++v13;
  while ( *((_WORD *)v10 + v13) );
  v14 = (__int64 *)(a1 + 368);
  std::wstring::_Assign<unsigned short>(a1 + 368, v10);
  *(_QWORD *)(a1 + 400) = a4;
  v15 = `HvsGetOperationName'::`2'::g_OperationNames[a5];
  v16 = -1;
  *(_DWORD *)(a1 + 408) = a5;
  do
    ++v16;
  while ( v15[v16] );
  v17 = (__int64 *)(a1 + 416);
  std::wstring::_Assign<unsigned short>(a1 + 416, v15);
  *(_QWORD *)(a1 + 448) = a6;
  UuidCreate((UUID *)(a1 + 352));
  IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC020u);
  v19 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( !v19 || (v20 = 1, !*v19) )
    v20 = 0;
  if ( IsDebugTraceEnabled || v20 )
  {
    if ( __TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) )
    {
      Init_thread_header(&__TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA);
      if ( __TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA == -1 )
      {
        byte_1800E31D4 = IsDebugTraceEnabled != 0;
        byte_1800E31D5 = v20;
        Init_thread_footer(&__TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA);
      }
    }
    if ( *(_QWORD *)(a1 + 392) <= 7u )
      v21 = a1 + 368;
    else
      v21 = *v14;
    if ( *(_QWORD *)(a1 + 440) <= 7u )
      v22 = a1 + 416;
    else
      v22 = *v17;
    HvsDebugTraceInternal(
      0xC020u,
      (const struct HvsDebugTraceParameters *)&`HyperVStorageTrace::HyperVAsyncIo::StartActivity'::`9'::traceParameters,
      v22,
      v21);
  }
  SRWLock = 0;
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v23 = *(_QWORD *)(a1 + 272);
  v24 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( *(_DWORD *)v24 > 5u
    && (*(_QWORD *)(v24 + 16) & 0xA0) != 0
    && (*(_QWORD *)(v24 + 24) & 0xA0LL) == *(_QWORD *)(v24 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v23 + 8));
  }
  else
  {
    *(_OWORD *)(v23 + 8) = 0;
  }
  v25 = SRWLock;
  *(_DWORD *)v23 = 1;
  if ( v25 )
    ReleaseSRWLockExclusive(v25);
  v26 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( *(_DWORD *)v26 > 5u
    && (*(_QWORD *)(v26 + 16) & 0xA0) != 0
    && (*(_QWORD *)(v26 + 24) & 0xA0LL) == *(_QWORD *)(v26 + 24) )
  {
    v27 = *(_QWORD *)(a1 + 440) <= 7u;
    v28 = *(__int64 **)(a1 + 448);
    v29 = v37;
    v39 = a8;
    v41 = v37;
    v42 = v28[3];
    v40 = *((_DWORD *)v28 + 5);
    LODWORD(SRWLock) = *((_DWORD *)v28 + 4);
    v43 = v28[1];
    v44 = *v28;
    v45 = v28;
    if ( !v27 )
      v17 = (__int64 *)*v17;
    v27 = *(_QWORD *)(a1 + 392) <= 7u;
    v46 = *(_QWORD *)(a1 + 400);
    if ( !v27 )
      v14 = (__int64 *)*v14;
    CurrentThreadId = GetCurrentThreadId();
    v31 = *(_QWORD *)(a1 + 272);
    LODWORD(v37) = CurrentThreadId;
    v47 = 0;
    if ( !*(_BYTE *)(v31 + 4)
      || (v32 = v31 + 24, !*(_DWORD *)(v31 + 24))
      && !*(_DWORD *)(v31 + 28)
      && !*(_DWORD *)(v31 + 32)
      && !*(_DWORD *)(v31 + 36) )
    {
      v32 = 0;
    }
    v80 = 4;
    v79 = &v39;
    v77 = &v41;
    v75 = &v42;
    v73 = &v40;
    p_SRWLock = &SRWLock;
    v69 = &v43;
    v67 = &v44;
    v65 = &v45;
    v33 = 2;
    v78 = 8;
    v76 = 8;
    v74 = 4;
    v72 = 4;
    v70 = 8;
    v68 = 8;
    v66 = 8;
    if ( v17 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v17 + v34) );
      v35 = 2 * v34 + 2;
    }
    else
    {
      v17 = &qword_1800AD7F8;
      v35 = 2;
    }
    v63 = v35;
    v60 = &v46;
    v62 = v17;
    v64 = 0;
    v61 = 8;
    if ( v14 )
    {
      do
        ++v12;
      while ( *((_WORD *)v14 + v12) );
      v33 = 2 * v12 + 2;
    }
    else
    {
      v14 = &qword_1800AD7F8;
    }
    v58 = v33;
    v55 = a1 + 352;
    v59 = 0;
    v53 = a1 + 336;
    v57 = v14;
    v51 = &v37;
    v56 = 16;
    v49 = &v47;
    v54 = 16;
    v52 = 4;
    v50 = 8;
    tlgWriteTransfer_EventWriteTransfer(v26, (int)&qword_1800CDE90, v31 + 8, v32, 0x11u, &v48);
  }
  else
  {
    v29 = v37;
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  if ( *(_DWORD *)(a1 + 408) == 5 )
  {
    v36 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( v36 )
    {
      if ( *v36 )
      {
        if ( **(_DWORD **)(a1 + 272) == 1 )
          HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(
            (HyperVStorageTrace::HyperVAsyncIo *)a1,
            L"ActivityStart",
            v29,
            a8);
      }
    }
  }
}

```

## disassembly

```asm
0x180090bcc  mov     [rsp-8+arg_8], rbx
0x180090bd1  push    rbp
0x180090bd2  push    rsi
0x180090bd3  push    rdi
0x180090bd4  push    r12
0x180090bd6  push    r13
0x180090bd8  push    r14
0x180090bda  push    r15
0x180090bdc  lea     rbp, [rsp-0A0h]
0x180090be4  sub     rsp, 1A0h
0x180090beb  mov     rax, cs:__security_cookie
0x180090bf2  xor     rax, rsp
0x180090bf5  mov     [rbp+0D0h+var_40], rax
0x180090bfc  movups  xmm0, xmmword ptr [rdx]
0x180090bff  mov     esi, [rbp+0D0h+arg_20]
0x180090c05  mov     rbx, rcx
0x180090c08  mov     rcx, [rbp+0D0h+arg_30]
0x180090c0f  xor     r12d, r12d
0x180090c12  test    r8, r8
0x180090c15  mov     [rsp+1D0h+var_1A0], rcx
0x180090c1a  mov     rax, r8
0x180090c1d  lea     rcx, qword_1800AD7F8
0x180090c24  cmovz   rax, rcx
0x180090c28  mov     r14, r9
0x180090c2b  or      r13, 0FFFFFFFFFFFFFFFFh
0x180090c2f  mov     r8, r13
0x180090c32  movdqu  xmmword ptr [rbx+150h], xmm0
0x180090c3a  inc     r8
0x180090c3d  cmp     [rax+r8*2], r12w
0x180090c42  jnz     short loc_180090C3A
0x180090c44  lea     rdi, [rbx+170h]
0x180090c4b  mov     rdx, rax
0x180090c4e  mov     rcx, rdi
0x180090c51  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180090c56  lea     rdx, ?g_OperationNames@?1??HvsGetOperationName@@YAPEBGW4HyperVAsyncIoOperationType@@@Z@4QBQEBGB; ushort const * const near * const `HvsGetOperationName(HyperVAsyncIoOperationType)'::`2'::g_OperationNames
0x180090c5d  mov     [rbx+190h], r14
0x180090c64  mov     rdx, [rdx+rsi*8]
0x180090c68  mov     r8, r13
0x180090c6b  mov     [rbx+198h], esi
0x180090c71  inc     r8
0x180090c74  cmp     [rdx+r8*2], r12w
0x180090c79  jnz     short loc_180090C71
0x180090c7b  lea     r14, [rbx+1A0h]
0x180090c82  mov     rcx, r14
0x180090c85  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180090c8a  mov     rax, [rbp+0D0h+arg_28]
0x180090c91  lea     rcx, [rbx+160h]; Uuid
0x180090c98  mov     [rbx+1C0h], rax
0x180090c9f  call    cs:__imp_UuidCreate
0x180090ca5  mov     ecx, 0C020h; unsigned __int16
0x180090caa  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180090caf  test    eax, eax
0x180090cb1  mov     r15d, eax
0x180090cb4  setnz   r12b
0x180090cb8  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180090cbd  mov     rcx, [rax+8]
0x180090cc1  xor     eax, eax
0x180090cc3  test    rcx, rcx
0x180090cc6  jz      short loc_180090CD1
0x180090cc8  mov     ecx, [rcx]
0x180090cca  mov     sil, 1
0x180090ccd  test    ecx, ecx
0x180090ccf  jnz     short loc_180090CD4
0x180090cd1  mov     sil, al
0x180090cd4  test    r15d, r15d
0x180090cd7  jnz     short loc_180090CDE
0x180090cd9  test    sil, sil
0x180090cdc  jz      short loc_180090D36
0x180090cde  mov     ecx, cs:_tls_index
0x180090ce4  mov     rax, gs:58h
0x180090ced  mov     edx, 10h
0x180090cf2  mov     rax, [rax+rcx*8]
0x180090cf6  mov     ecx, [rdx+rax]
0x180090cf9  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, ecx
0x180090cff  jg      loc_18009106F
0x180090d05  cmp     qword ptr [rdi+18h], 7
0x180090d0a  jbe     short loc_180090D11
0x180090d0c  mov     r9, [rdi]
0x180090d0f  jmp     short loc_180090D14
0x180090d11  mov     r9, rdi
0x180090d14  cmp     qword ptr [r14+18h], 7
0x180090d19  jbe     short loc_180090D20
0x180090d1b  mov     r8, [r14]
0x180090d1e  jmp     short loc_180090D23
0x180090d20  mov     r8, r14
0x180090d23  lea     rdx, ?traceParameters@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4UHvsDebugTraceParameters@@B; struct HvsDebugTraceParameters *
0x180090d2a  mov     ecx, 0C020h; unsigned int
0x180090d2f  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180090d34  xor     eax, eax
0x180090d36  lea     rdx, [rsp+1D0h+SRWLock]
0x180090d3b  mov     [rsp+1D0h+SRWLock], rax
0x180090d40  mov     rcx, rbx
0x180090d43  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180090d48  mov     rsi, [rbx+110h]
0x180090d4f  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180090d54  mov     r12d, 0A0h
0x180090d5a  mov     rcx, [rax+8]
0x180090d5e  mov     eax, [rcx]
0x180090d60  cmp     eax, 5
0x180090d63  jbe     short loc_180090D8E
0x180090d65  mov     rdx, [rcx+18h]
0x180090d69  mov     rax, [rcx+10h]
0x180090d6d  test    r12b, al
0x180090d70  jz      short loc_180090D8E
0x180090d72  mov     rax, rdx
0x180090d75  and     rax, r12
0x180090d78  cmp     rax, rdx
0x180090d7b  jnz     short loc_180090D8E
0x180090d7d  lea     rdx, [rsi+8]; ActivityId
0x180090d81  mov     ecx, 3; ControlCode
0x180090d86  call    cs:__imp_EventActivityIdControl
0x180090d8c  jmp     short loc_180090D95
0x180090d8e  xorps   xmm0, xmm0
0x180090d91  movups  xmmword ptr [rsi+8], xmm0
0x180090d95  mov     rcx, [rsp+1D0h+SRWLock]; SRWLock
0x180090d9a  mov     dword ptr [rsi], 1
0x180090da0  test    rcx, rcx
0x180090da3  jz      short loc_180090DAB
0x180090da5  call    cs:__imp_ReleaseSRWLockExclusive
0x180090dab  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180090db0  mov     r15d, [rbp+0D0h+arg_38]
0x180090db7  mov     rsi, [rax+8]
0x180090dbb  mov     eax, [rsi]
0x180090dbd  cmp     eax, 5
0x180090dc0  jbe     loc_180090FEF
0x180090dc6  mov     rcx, [rsi+18h]
0x180090dca  mov     rax, [rsi+10h]
0x180090dce  test    r12b, al
0x180090dd1  jz      loc_180090FEF
0x180090dd7  mov     rax, rcx
0x180090dda  and     rax, r12
0x180090ddd  cmp     rax, rcx
0x180090de0  jnz     loc_180090FEF
0x180090de6  cmp     qword ptr [r14+18h], 7
0x180090deb  mov     rcx, [rbx+1C0h]
0x180090df2  mov     r12, [rsp+1D0h+var_1A0]
0x180090df7  mov     [rsp+1D0h+var_190], r15d
0x180090dfc  mov     [rsp+1D0h+var_188], r12
0x180090e01  mov     rax, [rcx+18h]
0x180090e05  mov     [rsp+1D0h+var_180], rax
0x180090e0a  mov     eax, [rcx+14h]
0x180090e0d  mov     [rsp+1D0h+var_18C], eax
0x180090e11  mov     eax, [rcx+10h]
0x180090e14  mov     dword ptr [rsp+1D0h+SRWLock], eax
0x180090e18  mov     rax, [rcx+8]
0x180090e1c  mov     [rsp+1D0h+var_178], rax
0x180090e21  mov     rax, [rcx]
0x180090e24  mov     [rsp+1D0h+var_170], rax
0x180090e29  mov     [rsp+1D0h+var_168], rcx
0x180090e2e  jbe     short loc_180090E33
0x180090e30  mov     r14, [r14]
0x180090e33  cmp     qword ptr [rdi+18h], 7
0x180090e38  mov     rax, [rbx+190h]
0x180090e3f  mov     [rsp+1D0h+var_160], rax
0x180090e44  jbe     short loc_180090E49
0x180090e46  mov     rdi, [rdi]
0x180090e49  call    cs:__imp_GetCurrentThreadId
0x180090e4f  mov     r8, [rbx+110h]
0x180090e56  xor     edx, edx
0x180090e58  mov     dword ptr [rsp+1D0h+var_1A0], eax
0x180090e5c  mov     [rsp+1D0h+var_158], rdx
0x180090e61  cmp     [r8+4], dl
0x180090e65  jz      short loc_180090E82
0x180090e67  lea     r9, [r8+18h]
0x180090e6b  cmp     [r9], edx
0x180090e6e  jnz     short loc_180090E85
0x180090e70  cmp     [r9+4], edx
0x180090e74  jnz     short loc_180090E85
0x180090e76  cmp     [r9+8], edx
0x180090e7a  jnz     short loc_180090E85
0x180090e7c  cmp     [r9+0Ch], edx
0x180090e80  jnz     short loc_180090E85
0x180090e82  mov     r9, rdx; int
0x180090e85  mov     [rbp+0D0h+var_48], 4
0x180090e90  lea     rax, [rsp+1D0h+var_190]
0x180090e95  mov     [rbp+0D0h+var_50], rax
0x180090e9c  lea     rax, [rsp+1D0h+var_188]
0x180090ea1  mov     [rbp+0D0h+var_60], rax
0x180090ea5  lea     rax, [rsp+1D0h+var_180]
0x180090eaa  mov     [rbp+0D0h+var_70], rax
0x180090eae  lea     rax, [rsp+1D0h+var_18C]
0x180090eb3  mov     [rbp+0D0h+var_80], rax
0x180090eb7  lea     rax, [rsp+1D0h+SRWLock]
0x180090ebc  mov     [rbp+0D0h+var_90], rax
0x180090ec0  lea     rax, [rsp+1D0h+var_178]
0x180090ec5  mov     [rbp+0D0h+var_A0], rax
0x180090ec9  lea     rax, [rsp+1D0h+var_170]
0x180090ece  mov     [rbp+0D0h+var_B0], rax
0x180090ed2  lea     rax, [rsp+1D0h+var_168]
0x180090ed7  mov     [rbp+0D0h+var_C0], rax
0x180090edb  mov     ecx, 2
0x180090ee0  mov     [rbp+0D0h+var_58], 8
0x180090ee8  mov     [rbp+0D0h+var_68], 8
0x180090ef0  mov     [rbp+0D0h+var_78], 4
0x180090ef8  mov     [rbp+0D0h+var_88], 4
0x180090f00  mov     [rbp+0D0h+var_98], 8
0x180090f08  mov     [rbp+0D0h+var_A8], 8
0x180090f10  mov     [rbp+0D0h+var_B8], 8
0x180090f18  test    r14, r14
0x180090f1b  jz      short loc_180090F33
0x180090f1d  mov     rax, r13
0x180090f20  inc     rax
0x180090f23  cmp     [r14+rax*2], dx
0x180090f28  jnz     short loc_180090F20
0x180090f2a  lea     eax, ds:2[rax*2]
0x180090f31  jmp     short loc_180090F3C
0x180090f33  lea     r14, qword_1800AD7F8
0x180090f3a  mov     eax, ecx
0x180090f3c  mov     [rbp+0D0h+var_C8], eax
0x180090f3f  lea     rax, [rsp+1D0h+var_160]
0x180090f44  mov     [rbp+0D0h+var_E0], rax
0x180090f48  mov     [rbp+0D0h+var_D0], r14
0x180090f4c  mov     [rbp+0D0h+var_C4], edx
0x180090f4f  mov     [rbp+0D0h+var_D8], 8
0x180090f57  test    rdi, rdi
0x180090f5a  jz      short loc_180090F70
0x180090f5c  inc     r13
0x180090f5f  cmp     [rdi+r13*2], dx
0x180090f64  jnz     short loc_180090F5C
0x180090f66  lea     ecx, ds:2[r13*2]
0x180090f6e  jmp     short loc_180090F77
0x180090f70  lea     rdi, qword_1800AD7F8
0x180090f77  lea     rax, [rbx+160h]
0x180090f7e  mov     [rbp+0D0h+var_E8], ecx
0x180090f81  mov     [rbp+0D0h+var_100], rax
0x180090f85  add     r8, 8; int
0x180090f89  lea     rax, [rbx+150h]
0x180090f90  mov     [rbp+0D0h+var_E4], edx
0x180090f93  mov     [rbp+0D0h+var_110], rax
0x180090f97  lea     rdx, qword_1800CDE90; int
0x180090f9e  lea     rax, [rsp+1D0h+var_1A0]
0x180090fa3  mov     [rbp+0D0h+var_F0], rdi
0x180090fa7  mov     [rbp+0D0h+var_120], rax
0x180090fab  mov     rcx, rsi; int
0x180090fae  lea     rax, [rsp+1D0h+var_158]
0x180090fb3  mov     [rbp+0D0h+var_F8], 10h
0x180090fbb  mov     [rbp+0D0h+var_130], rax
0x180090fbf  lea     rax, [rbp+0D0h+var_150]
0x180090fc3  mov     [rsp+1D0h+var_1A8], rax; PEVENT_DATA_DESCRIPTOR
0x180090fc8  mov     [rsp+1D0h+var_1B0], 11h; ULONG
0x180090fd0  mov     [rbp+0D0h+var_108], 10h
0x180090fd8  mov     [rbp+0D0h+var_118], 4
0x180090fe0  mov     [rbp+0D0h+var_128], 8
0x180090fe8  call    _tlgWriteTransfer_EventWriteTransfer
0x180090fed  jmp     short loc_180090FF4
0x180090fef  mov     r12, [rsp+1D0h+var_1A0]
0x180090ff4  lea     rcx, [rbx+120h]; this
0x180090ffb  xor     edi, edi
0x180090ffd  cmp     [rcx+18h], edi
0x180091000  jnz     short loc_180091007
0x180091002  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180091007  cmp     dword ptr [rbx+198h], 5
0x18009100e  jnz     short loc_180091045
0x180091010  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180091015  mov     rax, [rax+8]
0x180091019  test    rax, rax
0x18009101c  jz      short loc_180091045
0x18009101e  mov     eax, [rax]
0x180091020  test    eax, eax
0x180091022  jz      short loc_180091045
0x180091024  mov     rax, [rbx+110h]
0x18009102b  cmp     dword ptr [rax], 1
0x18009102e  jnz     short loc_180091045
0x180091030  mov     r9d, r15d; unsigned int
0x180091033  lea     rdx, aActivitystart; "ActivityStart"
0x18009103a  mov     r8, r12; void *
0x18009103d  mov     rcx, rbx; this
0x180091040  call    ?TraceBufferContent@HyperVAsyncIo@HyperVStorageTrace@@AEAAXPEBGPEBXK@Z; HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(ushort const *,void const *,ulong)
0x180091045  mov     rcx, [rbp+0D0h+var_40]
0x18009104c  xor     rcx, rsp; StackCookie
0x18009104f  call    __security_check_cookie
0x180091054  mov     rbx, [rsp+1D0h+arg_8]
0x18009105c  add     rsp, 1A0h
0x180091063  pop     r15
0x180091065  pop     r14
0x180091067  pop     r13
0x180091069  pop     r12
0x18009106b  pop     rdi
0x18009106c  pop     rsi
0x18009106d  pop     rbp
0x18009106e  retn
0x18009106f  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x180091076  call    _Init_thread_header
0x18009107b  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, r13d
0x180091082  jnz     loc_180090D05
0x180091088  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x18009108f  mov     cs:byte_1800E31D4, r12b
0x180091096  mov     cs:byte_1800E31D5, sil
0x18009109d  call    _Init_thread_footer
0x1800910a2  jmp     loc_180090D05
```
