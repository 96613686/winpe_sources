# CFLACMetadataWriter::FindCommentField(ushort const *,VORBIS_COMMENT_FIELD const * *)

- ea: `0x180030f28`
- end: `0x18003106b`
- name: `?FindCommentField@CFLACMetadataWriter@@AEAAJPEBGPEAPEBUVORBIS_COMMENT_FIELD@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(CFLACMetadataWriter *__hidden this, const unsigned __int16 *, const struct VORBIS_COMMENT_FIELD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180031ca4`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180030f28`
- `0x180031bdc`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f72`

## string_xrefs

- `0x180030f46`: `CFLACMetadataWriter::FindCommentField`
- `0x180030fcf`: `CFLACMetadataWriter::FindCommentField`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACMetadataWriter::FindCommentField(
        CFLACMetadataWriter *this,
        const unsigned __int16 *a2,
        const struct VORBIS_COMMENT_FIELD **a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  const struct VORBIS_COMMENT_FIELD *i; // rax
  const unsigned __int16 *v12; // rcx
  int v13; // r9d
  int v14; // r8d
  char v16; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CFLACMetadataWriter::FindCommentField", 850);
  if ( a3 )
  {
    for ( i = (const struct VORBIS_COMMENT_FIELD *)&VorbisCommentFields;
          *(_QWORD *)i;
          i = (const struct VORBIS_COMMENT_FIELD *)((char *)i + 24) )
    {
      v12 = a2;
      do
      {
        v13 = *(const unsigned __int16 *)((char *)v12 + *(_QWORD *)i - (_QWORD)a2);
        v14 = *v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( !v14 )
      {
        v7 = 0;
        *a3 = i;
        goto LABEL_21;
      }
    }
    v7 = -1072875819;
  }
  else
  {
    v7 = -2147467261;
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CFLACMetadataWriter::FindCommentField", 850, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        this,
        -2147467261);
  }
LABEL_21:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return v7;
}

```

## disassembly

```asm
0x180030f28  mov     [rsp+arg_0], rbx
0x180030f2d  mov     [rsp+arg_8], rsi
0x180030f32  push    rdi
0x180030f33  sub     rsp, 30h
0x180030f37  mov     rdi, r8
0x180030f3a  mov     rbx, rdx
0x180030f3d  mov     rsi, rcx
0x180030f40  mov     r8d, 352h; int
0x180030f46  lea     rdx, aCflacmetadataw; "CFLACMetadataWriter::FindCommentField"
0x180030f4d  lea     rcx, [rsp+38h+arg_10]; this
0x180030f52  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030f57  nop
0x180030f58  test    rdi, rdi
0x180030f5b  jnz     loc_18003100C
0x180030f61  mov     ebx, 80004003h
0x180030f66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f6d  test    rcx, rcx
0x180030f70  jnz     short loc_180030FB3
0x180030f72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030f78  mov     rcx, rax
0x180030f7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f82  test    rax, rax
0x180030f85  jz      short loc_180030FA5
0x180030f87  mov     rax, [rax]
0x180030f8a  mov     edx, 7F0h
0x180030f8f  mov     rax, [rax+8]
0x180030f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f98  test    eax, eax
0x180030f9a  jz      short loc_180030FA5
0x180030f9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030fa3  jmp     short loc_180030FB3
0x180030fa5  lea     rcx, qword_18006EB20; this
0x180030fac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030fb3  cmp     byte ptr [rcx+8], 0
0x180030fb7  jz      short loc_180030FDE
0x180030fb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030fbe  cmp     [rax+7CCh], ebx
0x180030fc4  jz      short loc_180030FDE
0x180030fc6  mov     r9d, ebx; int
0x180030fc9  mov     r8d, 352h; int
0x180030fcf  lea     rdx, aCflacmetadataw; "CFLACMetadataWriter::FindCommentField"
0x180030fd6  mov     rcx, rax; this
0x180030fd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030fde  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030fe3  cmp     al, 1
0x180030fe5  jb      short loc_18003104F
0x180030fe7  mov     edx, 51h ; 'Q'
0x180030fec  mov     [rsp+38h+var_18], ebx
0x180030ff0  mov     r9, rsi
0x180030ff3  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180030ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180031001  mov     rcx, [rcx+10h]
0x180031005  call    WPP_SF_qd
0x18003100a  jmp     short loc_18003104F
0x18003100c  lea     rax, VorbisCommentFields
0x180031013  mov     rdx, [rax]
0x180031016  test    rdx, rdx
0x180031019  jz      short loc_18003104A
0x18003101b  mov     rcx, rbx
0x18003101e  sub     rdx, rbx
0x180031021  movzx   r8d, word ptr [rcx]
0x180031025  movzx   r9d, word ptr [rcx+rdx]
0x18003102a  sub     r8d, r9d
0x18003102d  jnz     short loc_180031038
0x18003102f  add     rcx, 2
0x180031033  test    r9d, r9d
0x180031036  jnz     short loc_180031021
0x180031038  test    r8d, r8d
0x18003103b  jz      short loc_180031043
0x18003103d  add     rax, 18h
0x180031041  jmp     short loc_180031013
0x180031043  xor     ebx, ebx
0x180031045  mov     [rdi], rax
0x180031048  jmp     short loc_18003104F
0x18003104a  mov     ebx, 0C00D36D5h
0x18003104f  lea     rcx, [rsp+38h+arg_10]; this
0x180031054  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180031059  mov     eax, ebx
0x18003105b  mov     rbx, [rsp+38h+arg_0]
0x180031060  mov     rsi, [rsp+38h+arg_8]
0x180031065  add     rsp, 30h
0x180031069  pop     rdi
0x18003106a  retn
```
