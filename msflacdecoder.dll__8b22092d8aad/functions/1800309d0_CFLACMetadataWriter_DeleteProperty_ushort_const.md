# CFLACMetadataWriter::DeleteProperty(ushort const *)

- ea: `0x1800309d0`
- end: `0x180030e33`
- name: `?DeleteProperty@CFLACMetadataWriter@@UEAAJPEBG@Z`
- size: `1123`
- prototype: `__int64 __fastcall(CFLACMetadataWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002e340`

## callees

- `0x1800018e4`
- `0x180016b24`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180030064`
- `0x1800309d0`
- `0x180031bdc`
- `0x180032900`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d70`

## string_xrefs

- `0x180030a46`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030ac5`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030b71`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030bf0`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030c50`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030ccd`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030d4b`: `CFLACMetadataWriter::DeleteProperty`
- `0x180030dca`: `CFLACMetadataWriter::DeleteProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACMetadataWriter::DeleteProperty(CFLACMetadataWriter *this, char *a2)
{
  void *v4; // r14
  __int64 i; // rbx
  char *v6; // rax
  char *v7; // r8
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdx
  unsigned int v11; // esi
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v15; // ecx
  unsigned int v16; // ecx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  signed __int64 v25; // rdx
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  void *v33; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 6) )
    {
      v11 = -1072873843;
      goto LABEL_65;
    }
    v6 = *(char **)(*((_QWORD *)this + 2) + 8 * i);
    v7 = (char *)(a2 - v6);
    do
    {
      v8 = *(unsigned __int16 *)&v7[(_QWORD)v6];
      v9 = *(unsigned __int16 *)v6 - v8;
      if ( v9 )
        break;
      v6 += 2;
    }
    while ( v8 );
    if ( !v9 )
      break;
  }
  v4 = *(void **)(*((_QWORD *)this + 2) + 8 * i);
  v33 = v4;
  if ( !(unsigned int)CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 16, (unsigned int)i) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CFLACMetadataWriter::DeleteProperty", 138);
    v11 = -1072875845;
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CFLACMetadataWriter::DeleteProperty", 138, -1072875845);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        -1072875845);
    goto LABEL_19;
  }
  v15 = *((_DWORD *)this + 24);
  if ( !v15 || (unsigned int)i > v15 - 1 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CFLACMetadataWriter::DeleteProperty", 142);
    v11 = -1072875845;
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v31, "CFLACMetadataWriter::DeleteProperty", 142, -1072875845);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        -1072875845);
LABEL_19:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
LABEL_65:
    if ( v4 )
      operator delete(v4);
    return v11;
  }
  v16 = v15 - i - 1;
  if ( v16 )
    memmove_0(
      (void *)(*((_QWORD *)this + 11) + 24 * i),
      (const void *)(*((_QWORD *)this + 11) + 24LL * (unsigned int)(i + 1)),
      24LL * v16);
  --*((_DWORD *)this + 24);
  if ( !(unsigned int)CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 64, (unsigned int)i) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CFLACMetadataWriter::DeleteProperty", 146);
    v11 = -1072875845;
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v20, "CFLACMetadataWriter::DeleteProperty", 146, -1072875845);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        -1072875845);
    goto LABEL_19;
  }
  if ( !(unsigned int)CTEntryArray<unsigned short const *>::Add((char *)this + 40, &v33) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CFLACMetadataWriter::DeleteProperty", 150);
    v11 = -2147024882;
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v24, "CFLACMetadataWriter::DeleteProperty", 150, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        -2147024882);
    goto LABEL_19;
  }
  v11 = 0;
  v25 = (char *)L"WM/Picture" - a2;
  do
  {
    v26 = *(unsigned __int16 *)&a2[v25];
    v27 = *(unsigned __int16 *)a2 - v26;
    if ( v27 )
      break;
    a2 += 2;
  }
  while ( v26 );
  if ( !v27 )
    *((_BYTE *)this + 129) = 0;
  return v11;
}

```

## disassembly

```asm
0x1800309d0  mov     [rsp+arg_8], rbx
0x1800309d5  mov     [rsp+arg_10], rbp
0x1800309da  push    rsi
0x1800309db  push    rdi
0x1800309dc  push    r14
0x1800309de  sub     rsp, 30h
0x1800309e2  mov     rbp, rdx
0x1800309e5  mov     rdi, rcx
0x1800309e8  xor     r14d, r14d
0x1800309eb  xor     ebx, ebx
0x1800309ed  cmp     ebx, [rdi+18h]
0x1800309f0  jnb     loc_180030E0C
0x1800309f6  mov     rax, [rdi+10h]
0x1800309fa  mov     r10, [rax+rbx*8]
0x1800309fe  mov     rax, r10
0x180030a01  mov     r8, rbp
0x180030a04  sub     r8, r10
0x180030a07  movzx   ecx, word ptr [rax]
0x180030a0a  movzx   edx, word ptr [rax+r8]
0x180030a0f  sub     ecx, edx
0x180030a11  jnz     short loc_180030A1B
0x180030a13  add     rax, 2
0x180030a17  test    edx, edx
0x180030a19  jnz     short loc_180030A07
0x180030a1b  test    ecx, ecx
0x180030a1d  jz      short loc_180030A23
0x180030a1f  inc     ebx
0x180030a21  jmp     short loc_1800309ED
0x180030a23  mov     r14, r10
0x180030a26  mov     [rsp+48h+arg_0], r10
0x180030a2b  mov     edx, ebx
0x180030a2d  lea     rcx, [rdi+10h]
0x180030a31  call    ?RemoveAt@?$CTEntryArray@_K@@QEAAHKK@Z; CTEntryArray<unsigned __int64>::RemoveAt(ulong,ulong)
0x180030a36  test    eax, eax
0x180030a38  jnz     loc_180030B11
0x180030a3e  mov     ebp, 8Ah
0x180030a43  mov     r8d, ebp; int
0x180030a46  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030a4d  lea     rcx, [rsp+48h+arg_0]; this
0x180030a52  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030a57  nop
0x180030a58  mov     ebx, 0C00D36BBh
0x180030a5d  mov     esi, ebx
0x180030a5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a66  test    rcx, rcx
0x180030a69  jnz     short loc_180030AAC
0x180030a6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030a71  mov     rcx, rax
0x180030a74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a7b  test    rax, rax
0x180030a7e  jz      short loc_180030A9E
0x180030a80  mov     rax, [rax]
0x180030a83  mov     edx, 7F0h
0x180030a88  mov     rax, [rax+8]
0x180030a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a91  test    eax, eax
0x180030a93  jz      short loc_180030A9E
0x180030a95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a9c  jmp     short loc_180030AAC
0x180030a9e  lea     rcx, qword_18006EB20; this
0x180030aa5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030aac  cmp     byte ptr [rcx+8], 0
0x180030ab0  jz      short loc_180030AD4
0x180030ab2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030ab7  cmp     [rax+7CCh], ebx
0x180030abd  jz      short loc_180030AD4
0x180030abf  mov     r9d, ebx; int
0x180030ac2  mov     r8d, ebp; int
0x180030ac5  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030acc  mov     rcx, rax; this
0x180030acf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030ad4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030ad9  cmp     al, 1
0x180030adb  jb      short loc_180030B02
0x180030add  lea     r9, [rdi-8]
0x180030ae1  mov     edx, 0Eh
0x180030ae6  mov     [rsp+48h+var_28], ebx
0x180030aea  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180030af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030af8  mov     rcx, [rcx+10h]
0x180030afc  call    WPP_SF_qd
0x180030b01  nop
0x180030b02  lea     rcx, [rsp+48h+arg_0]; this
0x180030b07  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180030b0c  jmp     loc_180030E11
0x180030b11  mov     ecx, [rdi+60h]
0x180030b14  cmp     ecx, 1
0x180030b17  jb      loc_180030D43
0x180030b1d  lea     eax, [rcx-1]
0x180030b20  cmp     ebx, eax
0x180030b22  ja      loc_180030D43
0x180030b28  sub     ecx, ebx
0x180030b2a  sub     ecx, 1
0x180030b2d  jz      short loc_180030B53
0x180030b2f  mov     r9, [rdi+58h]
0x180030b33  lea     r8, [rcx+rcx*2]
0x180030b37  shl     r8, 3; Size
0x180030b3b  lea     eax, [rbx+1]
0x180030b3e  lea     rax, [rax+rax*2]
0x180030b42  lea     rdx, [r9+rax*8]; Src
0x180030b46  lea     rax, [rbx+rbx*2]
0x180030b4a  lea     rcx, [r9+rax*8]; void *
0x180030b4e  call    memmove_0
0x180030b53  dec     dword ptr [rdi+60h]
0x180030b56  lea     rcx, [rdi+40h]
0x180030b5a  mov     edx, ebx
0x180030b5c  call    ?RemoveAt@?$CTEntryArray@_K@@QEAAHKK@Z; CTEntryArray<unsigned __int64>::RemoveAt(ulong,ulong)
0x180030b61  test    eax, eax
0x180030b63  jnz     loc_180030C32
0x180030b69  mov     ebp, 92h
0x180030b6e  mov     r8d, ebp; int
0x180030b71  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030b78  lea     rcx, [rsp+48h+arg_0]; this
0x180030b7d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030b82  nop
0x180030b83  mov     ebx, 0C00D36BBh
0x180030b88  mov     esi, ebx
0x180030b8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030b91  test    rcx, rcx
0x180030b94  jnz     short loc_180030BD7
0x180030b96  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030b9c  mov     rcx, rax
0x180030b9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ba6  test    rax, rax
0x180030ba9  jz      short loc_180030BC9
0x180030bab  mov     rax, [rax]
0x180030bae  mov     edx, 7F0h
0x180030bb3  mov     rax, [rax+8]
0x180030bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bbc  test    eax, eax
0x180030bbe  jz      short loc_180030BC9
0x180030bc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030bc7  jmp     short loc_180030BD7
0x180030bc9  lea     rcx, qword_18006EB20; this
0x180030bd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030bd7  cmp     byte ptr [rcx+8], 0
0x180030bdb  jz      short loc_180030BFF
0x180030bdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030be2  cmp     [rax+7CCh], ebx
0x180030be8  jz      short loc_180030BFF
0x180030bea  mov     r9d, ebx; int
0x180030bed  mov     r8d, ebp; int
0x180030bf0  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030bf7  mov     rcx, rax; this
0x180030bfa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030bff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030c04  cmp     al, 1
0x180030c06  jb      short loc_180030C2D
0x180030c08  lea     r9, [rdi-8]
0x180030c0c  mov     edx, 10h
0x180030c11  mov     [rsp+48h+var_28], ebx
0x180030c15  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180030c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c23  mov     rcx, [rcx+10h]
0x180030c27  call    WPP_SF_qd
0x180030c2c  nop
0x180030c2d  jmp     loc_180030B02
0x180030c32  lea     rcx, [rdi+28h]
0x180030c36  lea     rdx, [rsp+48h+arg_0]
0x180030c3b  call    ?Add@?$CTEntryArray@PEBG@@QEAAHAEBQEBGPEAK@Z; CTEntryArray<ushort const *>::Add(ushort const * const &,ulong *)
0x180030c40  test    eax, eax
0x180030c42  jnz     loc_180030D0F
0x180030c48  mov     ebx, 96h
0x180030c4d  mov     r8d, ebx; int
0x180030c50  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030c57  lea     rcx, [rsp+48h+arg_0]; this
0x180030c5c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030c61  nop
0x180030c62  mov     esi, 8007000Eh
0x180030c67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c6e  test    rcx, rcx
0x180030c71  jnz     short loc_180030CB4
0x180030c73  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030c79  mov     rcx, rax
0x180030c7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c83  test    rax, rax
0x180030c86  jz      short loc_180030CA6
0x180030c88  mov     rax, [rax]
0x180030c8b  mov     edx, 7F0h
0x180030c90  mov     rax, [rax+8]
0x180030c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c99  test    eax, eax
0x180030c9b  jz      short loc_180030CA6
0x180030c9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ca4  jmp     short loc_180030CB4
0x180030ca6  lea     rcx, qword_18006EB20; this
0x180030cad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030cb4  cmp     byte ptr [rcx+8], 0
0x180030cb8  jz      short loc_180030CDC
0x180030cba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030cbf  cmp     [rax+7CCh], esi
0x180030cc5  jz      short loc_180030CDC
0x180030cc7  mov     r9d, esi; int
0x180030cca  mov     r8d, ebx; int
0x180030ccd  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030cd4  mov     rcx, rax; this
0x180030cd7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030cdc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030ce1  cmp     al, 1
0x180030ce3  jb      short loc_180030D0A
0x180030ce5  lea     r9, [rdi-8]
0x180030ce9  mov     edx, 11h
0x180030cee  mov     [rsp+48h+var_28], esi
0x180030cf2  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180030cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d00  mov     rcx, [rcx+10h]
0x180030d04  call    WPP_SF_qd
0x180030d09  nop
0x180030d0a  jmp     loc_180030B02
0x180030d0f  xor     esi, esi
0x180030d11  lea     rdx, aWmPicture; "WM/Picture"
0x180030d18  sub     rdx, rbp
0x180030d1b  movzx   eax, word ptr [rbp+0]
0x180030d1f  movzx   ecx, word ptr [rdx+rbp]
0x180030d23  sub     eax, ecx
0x180030d25  jnz     short loc_180030D2F
0x180030d27  add     rbp, 2
0x180030d2b  test    ecx, ecx
0x180030d2d  jnz     short loc_180030D1B
0x180030d2f  test    eax, eax
0x180030d31  jnz     loc_180030E1E
0x180030d37  mov     [rdi+81h], sil
0x180030d3e  jmp     loc_180030E1E
0x180030d43  mov     ebp, 8Eh
0x180030d48  mov     r8d, ebp; int
0x180030d4b  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030d52  lea     rcx, [rsp+48h+arg_0]; this
0x180030d57  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030d5c  nop
0x180030d5d  mov     ebx, 0C00D36BBh
0x180030d62  mov     esi, ebx
0x180030d64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d6b  test    rcx, rcx
0x180030d6e  jnz     short loc_180030DB1
0x180030d70  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030d76  mov     rcx, rax
0x180030d79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d80  test    rax, rax
0x180030d83  jz      short loc_180030DA3
0x180030d85  mov     rax, [rax]
0x180030d88  mov     edx, 7F0h
0x180030d8d  mov     rax, [rax+8]
0x180030d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d96  test    eax, eax
0x180030d98  jz      short loc_180030DA3
0x180030d9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030da1  jmp     short loc_180030DB1
0x180030da3  lea     rcx, qword_18006EB20; this
0x180030daa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030db1  cmp     byte ptr [rcx+8], 0
0x180030db5  jz      short loc_180030DD9
0x180030db7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030dbc  cmp     [rax+7CCh], ebx
0x180030dc2  jz      short loc_180030DD9
0x180030dc4  mov     r9d, ebx; int
0x180030dc7  mov     r8d, ebp; int
0x180030dca  lea     rdx, aCflacmetadataw_3; "CFLACMetadataWriter::DeleteProperty"
0x180030dd1  mov     rcx, rax; this
0x180030dd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030dd9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030dde  cmp     al, 1
0x180030de0  jb      short loc_180030E07
0x180030de2  lea     r9, [rdi-8]
0x180030de6  mov     edx, 0Fh
0x180030deb  mov     [rsp+48h+var_28], ebx
0x180030def  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180030df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dfd  mov     rcx, [rcx+10h]
0x180030e01  call    WPP_SF_qd
0x180030e06  nop
0x180030e07  jmp     loc_180030B02
0x180030e0c  mov     esi, 0C00D3E8Dh
0x180030e11  test    r14, r14
0x180030e14  jz      short loc_180030E1E
0x180030e16  mov     rcx, r14; Block
0x180030e19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030e1e  mov     eax, esi
0x180030e20  mov     rbx, [rsp+48h+arg_8]
0x180030e25  mov     rbp, [rsp+48h+arg_10]
0x180030e2a  add     rsp, 30h
0x180030e2e  pop     r14
0x180030e30  pop     rdi
0x180030e31  pop     rsi
0x180030e32  retn
```
