# MFCreateMediaEvent

- ea: `0x180047fd0`
- end: `0x1800482fb`
- name: `MFCreateMediaEvent`
- size: `811`
- prototype: `HRESULT __stdcall(MediaEventType met, const GUID *const guidExtendedType, HRESULT hrStatus, const PROPVARIANT *pvValue, IMFMediaEvent **ppEvent)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180047fd0`
- `0x18004845c`
- `0x18011fff0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004800e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004800e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800480a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800480a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048084`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048164`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048084`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048164`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048096`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048176`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048096`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048176`

## pseudocode

```c
HRESULT __stdcall MFCreateMediaEvent(
        MediaEventType met,
        const GUID *const guidExtendedType,
        HRESULT hrStatus,
        const PROPVARIANT *pvValue,
        IMFMediaEvent **ppEvent)
{
  GUID v8; // xmm6
  IMFMediaEvent *v9; // rbx
  HRESULT v10; // esi
  IMFMediaEvent_vtbl *v11; // rcx
  CMFMediaEvent *v13; // rax
  CMFMediaEvent *v14; // rbx
  IRestrictedErrorInfo *m_pErrorInfo; // rcx

  if ( !ppEvent )
    return -2147467261;
  v8 = *guidExtendedType;
  EnterCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
  v9 = (IMFMediaEvent *)&stru_1801FC158.m_pHead[-5];
  if ( !stru_1801FC158.m_pHead )
    v9 = 0;
  if ( v9 )
  {
    stru_1801FC158.m_pHead = (CPooledObject *)v9[16].__vftable;
    v10 = 0;
    v9->AddRef(v9);
    v9[17].__vftable = (IMFMediaEvent_vtbl *)&stru_1801FC158;
    v11 = v9[14].__vftable;
    HIDWORD(v9[7].__vftable) = met;
    LODWORD(v9[10].__vftable) = hrStatus;
    *(GUID *)&v9[8].__vftable = v8;
    if ( v11 )
    {
      (*((void (__fastcall **)(IMFMediaEvent_vtbl *))v11->QueryInterface + 2))(v11);
      v9[14].__vftable = 0;
    }
    if ( hrStatus < 0
      && hrStatus != -2147023441
      && hrStatus != -1072875780
      && hrStatus != -1072873851
      && hrStatus != -2147024882 )
    {
      s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v9[14]);
      if ( !v9[14].__vftable )
      {
        s_pErrorInfoHandler->Capture(s_pErrorInfoHandler, hrStatus);
        s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v9[14]);
      }
    }
    PropVariantClear((PROPVARIANT *)&v9[11].__vftable);
    if ( pvValue )
      PropVariantCopy((PROPVARIANT *)&v9[11].__vftable, pvValue);
    *ppEvent = v9;
  }
  else
  {
    v13 = (CMFMediaEvent *)operator new(0x98u);
    v14 = v13;
    if ( v13 )
    {
      CMFMediaEvent::CMFMediaEvent(v13);
      v14[1].m_Lock.m_SRWLock.Ptr = 0;
      *(_QWORD *)&v14[1].m_Lock.m_OwningThreadId = 0;
      v14->CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::IMFMediaEvent::IMFAttributes::IUnknown::__vftable = (CMFMediaEvent_vtbl *)&CMediaEventPooled::`vftable'{for `CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>'};
      v14->CPoolableObject::__vftable = (CPoolableObject_vtbl *)&CMediaEventPooled::`vftable'{for `CPoolableObject'};
      v14[1].CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::IMFMediaEvent::IMFAttributes::IUnknown::__vftable = (CMFMediaEvent_vtbl *)&CMediaEventPooled::`vftable';
      LODWORD(v14[1].m_pEntries) = 0;
      m_pErrorInfo = v14->m_pErrorInfo;
      v14->m_met = met;
      v14->m_hrStatus = hrStatus;
      v14->m_guidExtendedType = v8;
      if ( m_pErrorInfo )
      {
        m_pErrorInfo->Release(m_pErrorInfo);
        v14->m_pErrorInfo = 0;
      }
      if ( hrStatus < 0
        && hrStatus != -2147023441
        && hrStatus != -1072875780
        && hrStatus != -1072873851
        && hrStatus != -2147024882 )
      {
        s_pErrorInfoHandler->Get(s_pErrorInfoHandler, &v14->m_pErrorInfo);
        if ( !v14->m_pErrorInfo )
        {
          s_pErrorInfoHandler->Capture(s_pErrorInfoHandler, hrStatus);
          s_pErrorInfoHandler->Get(s_pErrorInfoHandler, &v14->m_pErrorInfo);
        }
      }
      PropVariantClear((PROPVARIANT *)&v14->m_pvValue);
      if ( pvValue )
        PropVariantCopy((PROPVARIANT *)&v14->m_pvValue, pvValue);
      v10 = 0;
      if ( stru_1801FC158.m_dwCount < stru_1801FC158.m_dwMaxSize && stru_1801FC158.m_fEnabled )
      {
        *(_QWORD *)&v14[1].m_Lock.m_OwningThreadId = &stru_1801FC158;
        ++stru_1801FC158.m_dwCount;
      }
      *ppEvent = v14;
    }
    else
    {
      v10 = -2147024882;
    }
  }
  LeaveCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
  return v10;
}

```

## disassembly

```asm
0x180047fd0  mov     [rsp+arg_10], rbp
0x180047fd5  push    rdi
0x180047fd6  push    r14
0x180047fd8  push    r15
0x180047fda  sub     rsp, 30h
0x180047fde  mov     rdi, [rsp+48h+ppEvent]
0x180047fe3  mov     rbp, r9
0x180047fe6  mov     r14d, r8d
0x180047fe9  mov     r15d, ecx
0x180047fec  test    rdi, rdi
0x180047fef  jz      loc_1800480CC
0x180047ff5  mov     [rsp+48h+arg_0], rbx
0x180047ffa  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x180048001  mov     [rsp+48h+arg_8], rsi
0x180048006  movaps  [rsp+48h+var_28], xmm6
0x18004800b  movups  xmm6, xmmword ptr [rdx]
0x18004800e  call    cs:__imp_EnterCriticalSection
0x180048014  mov     rcx, cs:stru_1801FC158.m_pHead
0x18004801b  xor     eax, eax
0x18004801d  test    rcx, rcx
0x180048020  lea     rbx, [rcx-78h]
0x180048024  cmovz   rbx, rax
0x180048028  test    rbx, rbx
0x18004802b  jz      loc_1800480E0
0x180048031  mov     rax, [rbx+80h]
0x180048038  mov     rcx, rbx
0x18004803b  mov     cs:stru_1801FC158.m_pHead, rax
0x180048042  xor     esi, esi
0x180048044  mov     rax, [rbx]
0x180048047  mov     rax, [rax+8]
0x18004804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048050  lea     rax, stru_1801FC158
0x180048057  mov     [rbx+88h], rax
0x18004805e  mov     rcx, [rbx+70h]
0x180048062  mov     [rbx+3Ch], r15d
0x180048066  mov     [rbx+50h], r14d
0x18004806a  movups  xmmword ptr [rbx+40h], xmm6
0x18004806e  test    rcx, rcx
0x180048071  jnz     loc_180048194
0x180048077  test    r14d, r14d
0x18004807a  js      loc_1800481D3
0x180048080  lea     rcx, [rbx+58h]; pvar
0x180048084  call    cs:__imp_PropVariantClear
0x18004808a  test    rbp, rbp
0x18004808d  jz      short loc_18004809C
0x18004808f  mov     rdx, rbp; pvarSrc
0x180048092  lea     rcx, [rbx+58h]; pvarDest
0x180048096  call    cs:__imp_PropVariantCopy
0x18004809c  mov     [rdi], rbx
0x18004809f  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x1800480a6  call    cs:__imp_LeaveCriticalSection
0x1800480ac  movaps  xmm6, [rsp+48h+var_28]
0x1800480b1  mov     eax, esi
0x1800480b3  mov     rsi, [rsp+48h+arg_8]
0x1800480b8  mov     rbx, [rsp+48h+arg_0]
0x1800480bd  mov     rbp, [rsp+48h+arg_10]
0x1800480c2  add     rsp, 30h
0x1800480c6  pop     r15
0x1800480c8  pop     r14
0x1800480ca  pop     rdi
0x1800480cb  retn
0x1800480cc  mov     rbp, [rsp+48h+arg_10]
0x1800480d1  mov     eax, 80004003h
0x1800480d6  add     rsp, 30h
0x1800480da  pop     r15
0x1800480dc  pop     r14
0x1800480de  pop     rdi
0x1800480df  retn
0x1800480e0  mov     ecx, 98h; Size
0x1800480e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800480ea  mov     rbx, rax
0x1800480ed  test    rax, rax
0x1800480f0  jz      loc_1800481C9
0x1800480f6  mov     rcx, rax; this
0x1800480f9  call    ??0CMFMediaEvent@@QEAA@XZ; CMFMediaEvent::CMFMediaEvent(void)
0x1800480fe  mov     qword ptr [rbx+80h], 0
0x180048109  lea     rax, ??_7CMediaEventPooled@@6B?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@@; const CMediaEventPooled::`vftable'{for `CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>'}
0x180048110  mov     qword ptr [rbx+88h], 0
0x18004811b  mov     [rbx], rax
0x18004811e  lea     rax, ??_7CMediaEventPooled@@6BCPoolableObject@@@; const CMediaEventPooled::`vftable'{for `CPoolableObject'}
0x180048125  mov     [rbx+30h], rax
0x180048129  lea     rax, ??_7CMediaEventPooled@@6B@; const CMediaEventPooled::`vftable'
0x180048130  mov     [rbx+78h], rax
0x180048134  mov     dword ptr [rbx+90h], 0
0x18004813e  mov     rcx, [rbx+70h]
0x180048142  mov     [rbx+3Ch], r15d
0x180048146  mov     [rbx+50h], r14d
0x18004814a  movups  xmmword ptr [rbx+40h], xmm6
0x18004814e  test    rcx, rcx
0x180048151  jnz     loc_18004825A
0x180048157  test    r14d, r14d
0x18004815a  js      loc_180048273
0x180048160  lea     rcx, [rbx+58h]; pvar
0x180048164  call    cs:__imp_PropVariantClear
0x18004816a  test    rbp, rbp
0x18004816d  jz      short loc_18004817C
0x18004816f  mov     rdx, rbp; pvarSrc
0x180048172  lea     rcx, [rbx+58h]; pvarDest
0x180048176  call    cs:__imp_PropVariantCopy
0x18004817c  mov     eax, cs:stru_1801FC158.m_dwMaxSize
0x180048182  xor     esi, esi
0x180048184  cmp     cs:stru_1801FC158.m_dwCount, eax
0x18004818a  jb      short loc_1800481A9
0x18004818c  mov     [rdi], rbx
0x18004818f  jmp     loc_18004809F
0x180048194  mov     rax, [rcx]
0x180048197  mov     rax, [rax+10h]
0x18004819b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481a0  mov     [rbx+70h], rsi
0x1800481a4  jmp     loc_180048077
0x1800481a9  mov     eax, cs:stru_1801FC158.m_fEnabled
0x1800481af  test    eax, eax
0x1800481b1  jz      short loc_18004818C
0x1800481b3  lea     rax, stru_1801FC158
0x1800481ba  mov     [rbx+88h], rax
0x1800481c1  inc     cs:stru_1801FC158.m_dwCount
0x1800481c7  jmp     short loc_18004818C
0x1800481c9  mov     esi, 8007000Eh
0x1800481ce  jmp     loc_18004809F
0x1800481d3  cmp     r14d, 800705AFh
0x1800481da  jz      loc_180048080
0x1800481e0  cmp     r14d, 0C00D36FCh
0x1800481e7  jz      loc_180048080
0x1800481ed  cmp     r14d, 0C00D3E85h
0x1800481f4  jz      loc_180048080
0x1800481fa  cmp     r14d, 8007000Eh
0x180048201  jz      loc_180048080
0x180048207  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x18004820e  lea     rdx, [rbx+70h]
0x180048212  mov     rax, [rcx]
0x180048215  mov     rax, [rax+8]
0x180048219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004821e  cmp     [rbx+70h], rsi
0x180048222  jnz     loc_180048080
0x180048228  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x18004822f  mov     edx, r14d
0x180048232  mov     rax, [rcx]
0x180048235  mov     rax, [rax+10h]
0x180048239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004823e  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x180048245  lea     rdx, [rbx+70h]
0x180048249  mov     rax, [rcx]
0x18004824c  mov     rax, [rax+8]
0x180048250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048255  jmp     loc_180048080
0x18004825a  mov     rax, [rcx]
0x18004825d  mov     rax, [rax+10h]
0x180048261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048266  mov     qword ptr [rbx+70h], 0
0x18004826e  jmp     loc_180048157
0x180048273  cmp     r14d, 800705AFh
0x18004827a  jz      loc_180048160
0x180048280  cmp     r14d, 0C00D36FCh
0x180048287  jz      loc_180048160
0x18004828d  cmp     r14d, 0C00D3E85h
0x180048294  jz      loc_180048160
0x18004829a  cmp     r14d, 8007000Eh
0x1800482a1  jz      loc_180048160
0x1800482a7  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x1800482ae  lea     rdx, [rbx+70h]
0x1800482b2  mov     rax, [rcx]
0x1800482b5  mov     rax, [rax+8]
0x1800482b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482be  cmp     qword ptr [rbx+70h], 0
0x1800482c3  jnz     loc_180048160
0x1800482c9  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x1800482d0  mov     edx, r14d
0x1800482d3  mov     rax, [rcx]
0x1800482d6  mov     rax, [rax+10h]
0x1800482da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482df  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x1800482e6  lea     rdx, [rbx+70h]
0x1800482ea  mov     rax, [rcx]
0x1800482ed  mov     rax, [rax+8]
0x1800482f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f6  jmp     loc_180048160
```
