# CMediaServerCollectionChangeListener::NotifyListQueue::Queue(Windows::Media::Streaming::IBasicDevice *,long)

- ea: `0x180007b44`
- end: `0x180007df9`
- name: `?Queue@NotifyListQueue@CMediaServerCollectionChangeListener@@QEAAJPEAUIBasicDevice@Streaming@Media@Windows@@J@Z`
- size: `693`
- prototype: `int(CMediaServerCollectionChangeListener::NotifyListQueue *__hidden this, struct Windows::Media::Streaming::IBasicDevice *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180008fb0`

## callees

- `0x180007840`
- `0x180007b44`
- `0x180007e00`
- `0x180008430`
- `0x1800097c0`
- `0x18000abc0`
- `0x18000c84c`
- `0x180011ff0`
- `0x180014a00`
- `0x180019b84`
- `0x1800224f8`
- `0x180022a1c`
- `0x180022b74`
- `0x180024ee8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMediaServerCollectionChangeListener::NotifyListQueue::Queue(
        struct _RTL_CRITICAL_SECTION *this,
        struct Windows::Media::Streaming::IBasicDevice *a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode *v6; // r14
  bool v7; // r13
  int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // r15d
  _QWORD *p_Type; // rdi
  char v13; // bl
  int v14; // r15d
  int v15; // ebx
  PCWSTR StringRawBuffer; // rbx
  PRTL_CRITICAL_SECTION_DEBUG i; // rbx
  unsigned int v18; // eax
  unsigned int v19; // edx
  int v21; // [rsp+34h] [rbp-2Ch]
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-18h] BYREF
  char v25; // [rsp+50h] [rbp-10h]
  CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode *v28; // [rsp+B8h] [rbp+58h]

  v5 = this;
  v28 = (CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode *)operator new(0x18u);
  v6 = (CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode *)CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::QueueNode(
                                                                             v28,
                                                                             a2,
                                                                             a3);
  v7 = 0;
  if ( v6 )
  {
    lpCriticalSection = v5;
    v25 = 0;
    v8 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&lpCriticalSection);
    if ( v8 < 0 )
      ATL::AtlThrowImpl(v8);
    v11 = 0;
    p_Type = &v5[1].DebugInfo->Type;
    if ( p_Type )
    {
      v13 = 0;
      v14 = 0;
      if ( p_Type[2] )
      {
        do
        {
          v15 = *((_DWORD *)p_Type + 2);
          v21 = v15;
          v23 = 0;
          if ( (*(int (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v6 + 80LL))(*(_QWORD *)v6, &v23) >= 0 )
          {
            string = 0;
            if ( (*(int (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*p_Type + 80LL))(*p_Type, &string) >= 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                WindowsGetStringRawBuffer(v23, 0);
                WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)StringRawBuffer);
                v15 = v21;
              }
              v7 = (unsigned int)Windows::Internal::String::CompareOrdinal(&v23, &string) == 2;
            }
            Windows::Internal::String::~String(&string);
          }
          if ( v23 )
            WindowsDeleteString(v23);
          if ( !v7 )
            v15 = v14;
          v14 = v15;
          p_Type = (_QWORD *)p_Type[2];
          v7 = 0;
        }
        while ( p_Type[2] );
        v5 = this;
        v13 = 0;
      }
      if ( v14 == a3 )
        CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::`scalar deleting destructor'(v6, v9);
      else
        p_Type[2] = v6;
      v11 = 0;
    }
    else
    {
      v13 = 1;
      v5[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v6;
    }
    if ( v25 )
      LeaveCriticalSection(lpCriticalSection);
    if ( v13 )
    {
      LOBYTE(v10) = 1;
      ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
        &lpCriticalSection,
        v5,
        v10);
      for ( i = v5[1].DebugInfo; i; i = v5[1].DebugInfo )
      {
        LeaveCriticalSection(lpCriticalSection);
        v25 = 0;
        v18 = CMediaServerFolder::MediaServersChangeNotify(
                *(struct Windows::Media::Streaming::IBasicDevice **)&i->Type,
                (LONG)i->CriticalSection);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, v18);
        }
        ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&lpCriticalSection);
        v5[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)i->ProcessLocksList.Flink;
        CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::`scalar deleting destructor'(
          (CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode *)i,
          v19);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids);
      }
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&lpCriticalSection);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v11;
}

```

## disassembly

```asm
0x180007b44  mov     [rsp-38h+arg_8], rbx
0x180007b49  mov     [rsp-38h+arg_10], r8d
0x180007b4e  mov     [rsp-38h+arg_0], rcx
0x180007b53  push    rbp
0x180007b54  push    rsi
0x180007b55  push    rdi
0x180007b56  push    r12
0x180007b58  push    r13
0x180007b5a  push    r14
0x180007b5c  push    r15
0x180007b5e  mov     rbp, rsp
0x180007b61  sub     rsp, 60h
0x180007b65  mov     edi, r8d
0x180007b68  mov     rbx, rdx
0x180007b6b  mov     rsi, rcx
0x180007b6e  mov     ecx, 18h; Size
0x180007b73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b78  mov     [rbp+arg_18], rax
0x180007b7c  mov     r8d, edi; int
0x180007b7f  mov     rdx, rbx; struct Windows::Media::Streaming::IBasicDevice *
0x180007b82  mov     rcx, rax; this
0x180007b85  call    ??0QueueNode@NotifyListQueue@CMediaServerCollectionChangeListener@@QEAA@PEAUIBasicDevice@Streaming@Media@Windows@@J@Z; CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::QueueNode(Windows::Media::Streaming::IBasicDevice *,long)
0x180007b8a  mov     r14, rax
0x180007b8d  xor     r13d, r13d
0x180007b90  test    rax, rax
0x180007b93  jz      loc_180007DD8
0x180007b99  mov     [rbp+lpCriticalSection], rsi
0x180007b9d  mov     [rbp+var_10], r13b
0x180007ba1  lea     rcx, [rbp+lpCriticalSection]
0x180007ba5  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180007baa  test    eax, eax
0x180007bac  jns     short loc_180007BB6
0x180007bae  mov     ecx, eax; int
0x180007bb0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007bb6  mov     r15d, r13d
0x180007bb9  mov     [rbp+var_30], r13d
0x180007bbd  mov     rdi, [rsi+28h]
0x180007bc1  mov     r12d, 1
0x180007bc7  test    rdi, rdi
0x180007bca  jnz     short loc_180007BD8
0x180007bcc  mov     bl, r12b
0x180007bcf  mov     [rsi+28h], r14
0x180007bd3  jmp     loc_180007CF5
0x180007bd8  mov     bl, r13b
0x180007bdb  mov     r15d, r13d
0x180007bde  cmp     [rdi+10h], r13
0x180007be2  jz      loc_180007CDD
0x180007be8  lea     rsi, WPP_GLOBAL_Control
0x180007bef  mov     ebx, [rdi+8]
0x180007bf2  mov     [rbp+var_2C], ebx
0x180007bf5  mov     [rbp+var_20], 0
0x180007bfd  mov     rcx, [r14]
0x180007c00  mov     rax, [rcx]
0x180007c03  lea     rdx, [rbp+var_20]
0x180007c07  mov     rax, [rax+50h]
0x180007c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c10  test    eax, eax
0x180007c12  js      loc_180007CAC
0x180007c18  mov     [rbp+string], 0
0x180007c20  mov     rcx, [rdi]
0x180007c23  mov     rax, [rcx]
0x180007c26  lea     rdx, [rbp+string]
0x180007c2a  mov     rax, [rax+50h]
0x180007c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c33  test    eax, eax
0x180007c35  js      short loc_180007CA2
0x180007c37  mov     rax, cs:WPP_GLOBAL_Control
0x180007c3e  cmp     rax, rsi
0x180007c41  jz      short loc_180007C8A
0x180007c43  test    byte ptr [rax+1Ch], 40h
0x180007c47  jz      short loc_180007C8A
0x180007c49  cmp     byte ptr [rax+19h], 4
0x180007c4d  jb      short loc_180007C8A
0x180007c4f  xor     edx, edx; length
0x180007c51  mov     rcx, [rbp+string]; string
0x180007c55  call    cs:__imp_WindowsGetStringRawBuffer
0x180007c5b  mov     rbx, rax
0x180007c5e  xor     edx, edx; length
0x180007c60  mov     rcx, [rbp+var_20]; string
0x180007c64  call    cs:__imp_WindowsGetStringRawBuffer
0x180007c6a  mov     edx, 18h
0x180007c6f  mov     [rsp+60h+var_40], rbx; __int64
0x180007c74  mov     r9, rax
0x180007c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c7e  mov     rcx, [rcx+10h]; LoggerHandle
0x180007c82  call    WPP_SF_SS
0x180007c87  mov     ebx, [rbp+var_2C]
0x180007c8a  lea     rdx, [rbp+string]; struct Windows::Internal::String *
0x180007c8e  lea     rcx, [rbp+var_20]; this
0x180007c92  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180007c97  movzx   r13d, r13b
0x180007c9b  cmp     eax, 2
0x180007c9e  cmovz   r13d, r12d
0x180007ca2  lea     rcx, [rbp+string]; this
0x180007ca6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180007cab  nop
0x180007cac  mov     rcx, [rbp+var_20]; string
0x180007cb0  test    rcx, rcx
0x180007cb3  jz      short loc_180007CBB
0x180007cb5  call    cs:__imp_WindowsDeleteString
0x180007cbb  test    r13b, r13b
0x180007cbe  cmovz   ebx, r15d
0x180007cc2  mov     r15d, ebx
0x180007cc5  mov     rdi, [rdi+10h]
0x180007cc9  xor     r13d, r13d
0x180007ccc  cmp     [rdi+10h], r13
0x180007cd0  jnz     loc_180007BEF
0x180007cd6  mov     rsi, [rbp+arg_0]
0x180007cda  mov     bl, r13b
0x180007cdd  cmp     r15d, [rbp+arg_10]
0x180007ce1  jz      short loc_180007CE9
0x180007ce3  mov     [rdi+10h], r14
0x180007ce7  jmp     short loc_180007CF1
0x180007ce9  mov     rcx, r14; this
0x180007cec  call    ??_GQueueNode@NotifyListQueue@CMediaServerCollectionChangeListener@@QEAAPEAXI@Z; CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::`scalar deleting destructor'(uint)
0x180007cf1  mov     r15d, [rbp+var_30]
0x180007cf5  cmp     [rbp+var_10], r13b
0x180007cf9  jz      short loc_180007D05
0x180007cfb  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180007cff  call    cs:__imp_LeaveCriticalSection
0x180007d05  test    bl, bl
0x180007d07  jz      loc_180007DDE
0x180007d0d  mov     r8b, r12b
0x180007d10  mov     rdx, rsi
0x180007d13  lea     rcx, [rbp+lpCriticalSection]
0x180007d17  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180007d1c  nop
0x180007d1d  mov     rbx, [rsi+28h]
0x180007d21  test    rbx, rbx
0x180007d24  jz      short loc_180007D98
0x180007d26  lea     rdi, WPP_GLOBAL_Control
0x180007d2d  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180007d31  call    cs:__imp_LeaveCriticalSection
0x180007d37  mov     [rbp+var_10], r13b
0x180007d3b  mov     edx, [rbx+8]; int
0x180007d3e  mov     rcx, [rbx]; struct Windows::Media::Streaming::IBasicDevice *
0x180007d41  call    ?MediaServersChangeNotify@CMediaServerFolder@@SAJPEAUIBasicDevice@Streaming@Media@Windows@@J@Z; CMediaServerFolder::MediaServersChangeNotify(Windows::Media::Streaming::IBasicDevice *,long)
0x180007d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d4d  cmp     rcx, rdi
0x180007d50  jz      short loc_180007D76
0x180007d52  test    byte ptr [rcx+1Ch], 40h
0x180007d56  jz      short loc_180007D76
0x180007d58  cmp     byte ptr [rcx+19h], 4
0x180007d5c  jb      short loc_180007D76
0x180007d5e  mov     edx, 19h
0x180007d63  mov     r9d, eax
0x180007d66  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180007d6d  mov     rcx, [rcx+10h]
0x180007d71  call    WPP_SF_d
0x180007d76  lea     rcx, [rbp+lpCriticalSection]
0x180007d7a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180007d7f  mov     rax, [rbx+10h]
0x180007d83  mov     [rsi+28h], rax
0x180007d87  mov     rcx, rbx; this
0x180007d8a  call    ??_GQueueNode@NotifyListQueue@CMediaServerCollectionChangeListener@@QEAAPEAXI@Z; CMediaServerCollectionChangeListener::NotifyListQueue::QueueNode::`scalar deleting destructor'(uint)
0x180007d8f  mov     rbx, [rsi+28h]
0x180007d93  test    rbx, rbx
0x180007d96  jnz     short loc_180007D2D
0x180007d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d9f  lea     rax, WPP_GLOBAL_Control
0x180007da6  cmp     rcx, rax
0x180007da9  jz      short loc_180007DCD
0x180007dab  test    byte ptr [rcx+1Ch], 40h
0x180007daf  jz      short loc_180007DCD
0x180007db1  cmp     byte ptr [rcx+19h], 4
0x180007db5  jb      short loc_180007DCD
0x180007db7  mov     edx, 1Ah
0x180007dbc  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180007dc3  mov     rcx, [rcx+10h]
0x180007dc7  call    WPP_SF_
0x180007dcc  nop
0x180007dcd  lea     rcx, [rbp+lpCriticalSection]
0x180007dd1  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180007dd6  jmp     short loc_180007DDE
0x180007dd8  mov     r15d, 8007000Eh
0x180007dde  mov     eax, r15d
0x180007de1  mov     rbx, [rsp+60h+arg_8]
0x180007de9  add     rsp, 60h
0x180007ded  pop     r15
0x180007def  pop     r14
0x180007df1  pop     r13
0x180007df3  pop     r12
0x180007df5  pop     rdi
0x180007df6  pop     rsi
0x180007df7  pop     rbp
0x180007df8  retn
```
