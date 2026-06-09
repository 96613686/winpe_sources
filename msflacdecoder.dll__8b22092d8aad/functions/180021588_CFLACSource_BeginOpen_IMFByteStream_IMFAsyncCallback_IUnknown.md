# CFLACSource::BeginOpen(IMFByteStream *,IMFAsyncCallback *,IUnknown *)

- ea: `0x180021588`
- end: `0x18002190a`
- name: `?BeginOpen@CFLACSource@@QEAAJPEAUIMFByteStream@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `898`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct IMFByteStream *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001fff0`
- `0x18002cca0`

## callees

- `0x180020398`
- `0x180020484`
- `0x180021588`
- `0x1800234fc`
- `0x1800264ac`
- `0x180027b80`
- `0x180027d54`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800218ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800218ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215ca`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002177a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002177a`
- `MFPlat!MFCreateAsyncResult` at `0x180021800`
- `MFPlat!MFCreateAsyncResult` at `0x180021800`
- `MFPlat!MFCreateEventQueue` at `0x180021661`
- `MFPlat!MFCreateEventQueue` at `0x180021661`
- `MFPlat!MFCreateSample` at `0x180021727`
- `MFPlat!MFCreateSample` at `0x180021727`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFLACSource::BeginOpen(
        CFLACSource *this,
        struct IMFByteStream *a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // r15
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  char v12; // al
  unsigned int v13; // ebx
  int v15; // [rsp+70h] [rbp+30h] BYREF
  char *v16; // [rsp+78h] [rbp+38h]
  HRESULT v17; // [rsp+88h] [rbp+48h]
  int v18; // [rsp+8Ch] [rbp+4Ch]

  v18 = HIDWORD(a4);
  v17 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  v16 = (char *)this + 184;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v15 = 0;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( *((_DWORD *)this + 56) )
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 110, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
        v17 = -1072875854;
      }
      else
      {
        v17 = MFCreateEventQueue((IMFMediaEventQueue **)this + 29);
        if ( v17 >= 0 )
        {
          v17 = ((__int64 (__fastcall *)(struct IMFByteStream *, int *))a2->lpVtbl->GetCapabilities)(a2, &v15);
          if ( v17 >= 0 )
          {
            if ( (v15 & 4) == 0 )
              *((_BYTE *)this + 388) = 0;
            if ( (v15 & 1) != 0 )
            {
              v10 = *((_QWORD *)this + 34);
              if ( v10 )
              {
                *((_QWORD *)this + 34) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              }
              v17 = MFCreateSample((IMFSample **)this + 34);
              if ( v17 >= 0 )
              {
                v11 = *((_QWORD *)this + 51);
                if ( v11 )
                {
                  *((_QWORD *)this + 51) = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                }
                v17 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)this + 51);
                if ( v17 >= 0 )
                {
                  *((_DWORD *)this + 56) = 1;
                  *((_QWORD *)this + 39) = a2;
                  ((void (__fastcall *)(struct IMFByteStream *))a2->lpVtbl->AddRef)(a2);
                  v17 = CBuffReader::Initalize((CFLACSource *)((char *)this + 328), 0x10000u);
                  if ( v17 >= 0 )
                  {
                    v17 = MFCreateAsyncResult(0, a3, 0, (IMFAsyncResult **)this + 31);
                    if ( v17 >= 0 )
                    {
                      v12 = *((_BYTE *)this + 389);
                      if ( v12 == 1 )
                      {
                        *((_BYTE *)this + 389) = 3;
                        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 14) + 56LL))((char *)this + 112);
                      }
                      else if ( (v12 & 8) != 0 )
                      {
                        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 14) + 40LL))((char *)this + 112, 6);
                      }
                      if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 14) + 176LL))((char *)this + 112) )
                      {
                        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 27),
                            118,
                            &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
                        v17 = -1072875845;
                      }
                      else
                      {
                        v17 = CFLACSource::RequestData(this);
                        if ( v17 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v9 = 119;
                          goto LABEL_50;
                        }
                      }
                    }
                    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v9 = 117;
                      goto LABEL_50;
                    }
                  }
                  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v9 = 116;
                    goto LABEL_50;
                  }
                }
                else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 115;
                  goto LABEL_50;
                }
              }
              else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 114;
                goto LABEL_50;
              }
            }
            else
            {
              if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 113, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
              v17 = -2147467259;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 112;
            goto LABEL_50;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 111;
          goto LABEL_50;
        }
      }
    }
    else
    {
      v17 = -2147467261;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 109;
        goto LABEL_50;
      }
    }
  }
  else
  {
    v17 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 108;
LABEL_50:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v8);
    }
  }
  v13 = v17;
  LeaveCriticalSection(v7);
  return v13;
}

```

## disassembly

```asm
0x180021588  mov     [rsp-28h+arg_10], rbx
0x18002158d  mov     [rsp-28h+arg_18], r9
0x180021592  push    rbp
0x180021593  push    rsi
0x180021594  push    rdi
0x180021595  push    r14
0x180021597  push    r15
0x180021599  mov     rbp, rsp
0x18002159c  sub     rsp, 40h
0x1800215a0  mov     r14, r8
0x1800215a3  mov     rsi, rdx
0x1800215a6  mov     rbx, rcx
0x1800215a9  mov     dword ptr [rbp+arg_18], 0
0x1800215b0  mov     [rbp+var_10], rcx
0x1800215b4  lea     rax, [rbp+arg_18]
0x1800215b8  mov     [rbp+var_8], rax
0x1800215bc  lea     r15, [rcx+0B8h]
0x1800215c3  mov     [rbp+arg_8], r15
0x1800215c7  mov     rcx, r15; lpCriticalSection
0x1800215ca  call    cs:__imp_EnterCriticalSection
0x1800215d0  nop
0x1800215d1  mov     [rbp+arg_0], 0
0x1800215d8  test    rsi, rsi
0x1800215db  jnz     short loc_1800215FA
0x1800215dd  mov     ecx, 80004003h
0x1800215e2  mov     dword ptr [rbp+arg_18], ecx
0x1800215e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800215ea  cmp     al, 1
0x1800215ec  jb      loc_1800218E7
0x1800215f2  lea     edx, [rsi+6Ch]
0x1800215f5  jmp     loc_1800218C9
0x1800215fa  test    r14, r14
0x1800215fd  jnz     short loc_18002161D
0x1800215ff  mov     ecx, 80004003h
0x180021604  mov     dword ptr [rbp+arg_18], ecx
0x180021607  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002160c  cmp     al, 1
0x18002160e  jb      loc_1800218E7
0x180021614  lea     edx, [r14+6Dh]
0x180021618  jmp     loc_1800218C9
0x18002161d  cmp     dword ptr [rbx+0E0h], 0
0x180021624  jz      short loc_18002165A
0x180021626  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002162b  cmp     al, 1
0x18002162d  jb      short loc_18002164E
0x18002162f  mov     edx, 6Eh ; 'n'
0x180021634  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x18002163b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021642  mov     rcx, [rcx+0D8h]
0x180021649  call    WPP_SF_
0x18002164e  mov     dword ptr [rbp+arg_18], 0C00D36B2h
0x180021655  jmp     loc_1800218E7
0x18002165a  lea     rcx, [rbx+0E8h]; ppMediaEventQueue
0x180021661  call    cs:__imp_MFCreateEventQueue
0x180021667  mov     ecx, eax
0x180021669  mov     dword ptr [rbp+arg_18], eax
0x18002166c  test    eax, eax
0x18002166e  jns     short loc_180021687
0x180021670  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021675  cmp     al, 1
0x180021677  jb      loc_1800218E7
0x18002167d  mov     edx, 6Fh ; 'o'
0x180021682  jmp     loc_1800218C9
0x180021687  mov     rax, [rsi]
0x18002168a  lea     rdx, [rbp+arg_0]
0x18002168e  mov     rcx, rsi
0x180021691  mov     rax, [rax+18h]
0x180021695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002169a  mov     ecx, eax
0x18002169c  mov     dword ptr [rbp+arg_18], eax
0x18002169f  test    eax, eax
0x1800216a1  jns     short loc_1800216BA
0x1800216a3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800216a8  cmp     al, 1
0x1800216aa  jb      loc_1800218E7
0x1800216b0  mov     edx, 70h ; 'p'
0x1800216b5  jmp     loc_1800218C9
0x1800216ba  test    byte ptr [rbp+arg_0], 4
0x1800216be  jnz     short loc_1800216C7
0x1800216c0  mov     byte ptr [rbx+184h], 0
0x1800216c7  test    byte ptr [rbp+arg_0], 1
0x1800216cb  jnz     short loc_180021701
0x1800216cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800216d2  cmp     al, 1
0x1800216d4  jb      short loc_1800216F5
0x1800216d6  mov     edx, 71h ; 'q'
0x1800216db  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800216e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216e9  mov     rcx, [rcx+0D8h]
0x1800216f0  call    WPP_SF_
0x1800216f5  mov     dword ptr [rbp+arg_18], 80004005h
0x1800216fc  jmp     loc_1800218E7
0x180021701  lea     rdi, [rbx+110h]
0x180021708  mov     rcx, [rdi]
0x18002170b  test    rcx, rcx
0x18002170e  jz      short loc_180021724
0x180021710  mov     qword ptr [rdi], 0
0x180021717  mov     rax, [rcx]
0x18002171a  mov     rax, [rax+10h]
0x18002171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021723  nop
0x180021724  mov     rcx, rdi; ppIMFSample
0x180021727  call    cs:__imp_MFCreateSample
0x18002172d  mov     ecx, eax
0x18002172f  mov     dword ptr [rbp+arg_18], eax
0x180021732  test    eax, eax
0x180021734  jns     short loc_18002174D
0x180021736  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002173b  cmp     al, 1
0x18002173d  jb      loc_1800218E7
0x180021743  mov     edx, 72h ; 'r'
0x180021748  jmp     loc_1800218C9
0x18002174d  lea     rdi, [rbx+198h]
0x180021754  mov     rcx, [rdi]
0x180021757  test    rcx, rcx
0x18002175a  jz      short loc_180021770
0x18002175c  mov     qword ptr [rdi], 0
0x180021763  mov     rax, [rcx]
0x180021766  mov     rax, [rax+10h]
0x18002176a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002176f  nop
0x180021770  mov     rdx, rdi; ppv
0x180021773  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18002177a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180021780  mov     ecx, eax
0x180021782  mov     dword ptr [rbp+arg_18], eax
0x180021785  test    eax, eax
0x180021787  jns     short loc_1800217A0
0x180021789  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002178e  cmp     al, 1
0x180021790  jb      loc_1800218E7
0x180021796  mov     edx, 73h ; 's'
0x18002179b  jmp     loc_1800218C9
0x1800217a0  mov     dword ptr [rbx+0E0h], 1
0x1800217aa  mov     [rbx+138h], rsi
0x1800217b1  mov     rax, [rsi]
0x1800217b4  mov     rcx, rsi
0x1800217b7  mov     rax, [rax+8]
0x1800217bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c0  lea     rcx, [rbx+148h]; this
0x1800217c7  mov     edx, 10000h; unsigned int
0x1800217cc  call    ?Initalize@CBuffReader@@QEAAJK@Z; CBuffReader::Initalize(ulong)
0x1800217d1  mov     ecx, eax
0x1800217d3  mov     dword ptr [rbp+arg_18], eax
0x1800217d6  test    eax, eax
0x1800217d8  jns     short loc_1800217F1
0x1800217da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800217df  cmp     al, 1
0x1800217e1  jb      loc_1800218E7
0x1800217e7  mov     edx, 74h ; 't'
0x1800217ec  jmp     loc_1800218C9
0x1800217f1  lea     r9, [rbx+0F8h]; ppAsyncResult
0x1800217f8  xor     r8d, r8d; punkState
0x1800217fb  mov     rdx, r14; pCallback
0x1800217fe  xor     ecx, ecx; punkObject
0x180021800  call    cs:__imp_MFCreateAsyncResult
0x180021806  mov     ecx, eax
0x180021808  mov     dword ptr [rbp+arg_18], eax
0x18002180b  test    eax, eax
0x18002180d  jns     short loc_180021826
0x18002180f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021814  cmp     al, 1
0x180021816  jb      loc_1800218E7
0x18002181c  mov     edx, 75h ; 'u'
0x180021821  jmp     loc_1800218C9
0x180021826  mov     al, [rbx+185h]
0x18002182c  cmp     al, 1
0x18002182e  jnz     short loc_180021849
0x180021830  mov     byte ptr [rbx+185h], 3
0x180021837  lea     rcx, [rbx+70h]
0x18002183b  mov     rax, [rcx]
0x18002183e  mov     rax, [rax+38h]
0x180021842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021847  jmp     short loc_180021862
0x180021849  test    al, 8
0x18002184b  jz      short loc_180021862
0x18002184d  lea     rcx, [rbx+70h]
0x180021851  mov     rax, [rcx]
0x180021854  mov     edx, 6
0x180021859  mov     rax, [rax+28h]
0x18002185d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021862  lea     rcx, [rbx+70h]
0x180021866  mov     rax, [rcx]
0x180021869  mov     rax, [rax+0B0h]
0x180021870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021875  test    eax, eax
0x180021877  jz      short loc_1800218AA
0x180021879  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002187e  cmp     al, 1
0x180021880  jb      short loc_1800218A1
0x180021882  mov     edx, 76h ; 'v'
0x180021887  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x18002188e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021895  mov     rcx, [rcx+0D8h]
0x18002189c  call    WPP_SF_
0x1800218a1  mov     dword ptr [rbp+arg_18], 0C00D36BBh
0x1800218a8  jmp     short loc_1800218E7
0x1800218aa  mov     rcx, rbx; this
0x1800218ad  call    ?RequestData@CFLACSource@@AEAAJXZ; CFLACSource::RequestData(void)
0x1800218b2  mov     ecx, eax
0x1800218b4  mov     dword ptr [rbp+arg_18], eax
0x1800218b7  test    eax, eax
0x1800218b9  jns     short loc_1800218E7
0x1800218bb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800218c0  cmp     al, 1
0x1800218c2  jb      short loc_1800218E7
0x1800218c4  mov     edx, 77h ; 'w'
0x1800218c9  mov     [rsp+40h+var_20], ecx
0x1800218cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218d4  mov     r9, rbx
0x1800218d7  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800218de  mov     rcx, [rcx+10h]
0x1800218e2  call    WPP_SF_qd
0x1800218e7  mov     ebx, dword ptr [rbp+arg_18]
0x1800218ea  mov     rcx, r15; lpCriticalSection
0x1800218ed  call    cs:__imp_LeaveCriticalSection
0x1800218f3  nop
0x1800218f4  mov     eax, ebx
0x1800218f6  mov     rbx, [rsp+40h+arg_10]
0x1800218fe  add     rsp, 40h
0x180021902  pop     r15
0x180021904  pop     r14
0x180021906  pop     rdi
0x180021907  pop     rsi
0x180021908  pop     rbp
0x180021909  retn
```
