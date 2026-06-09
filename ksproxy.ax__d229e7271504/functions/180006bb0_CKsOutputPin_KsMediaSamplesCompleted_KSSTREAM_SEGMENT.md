# CKsOutputPin::KsMediaSamplesCompleted(_KSSTREAM_SEGMENT *)

- ea: `0x180006bb0`
- end: `0x180006dda`
- name: `?KsMediaSamplesCompleted@CKsOutputPin@@UEAAJPEAU_KSSTREAM_SEGMENT@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, struct _KSSTREAM_SEGMENT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006bb0`
- `0x18001f1c4`
- `0x180031e14`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180006ce3`
- `KERNEL32!SetEvent` at `0x180006ce3`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c69`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c84`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c9c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006d9b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c69`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c84`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006c9c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006d9b`
- `KERNEL32!ReleaseMutex` at `0x180006cf6`
- `KERNEL32!ReleaseMutex` at `0x180006dc9`
- `KERNEL32!ReleaseMutex` at `0x180006cf6`
- `KERNEL32!ReleaseMutex` at `0x180006dc9`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::KsMediaSamplesCompleted(CKsOutputPin *this, struct _KSSTREAM_SEGMENT *a2)
{
  IMediaSeeking_vtbl *m_pRefClock; // rcx
  IReferenceClock *AddRef; // rax
  IMediaEventSink **v5; // rax
  IMediaEventSink *QueryInterface; // rdx
  IReferenceClock *v7; // rsi
  IReferenceClock_vtbl *v8; // rsi
  __int64 Alignment; // rdi
  void *v10; // rcx
  IReferenceClock_vtbl **v12; // rax

  if ( this->m_CurrentCommunication )
    return 0;
  m_pRefClock = (IMediaSeeking_vtbl *)this->m_pRefClock;
  if ( m_pRefClock )
  {
    AddRef = (IReferenceClock *)m_pRefClock->AddRef;
    if ( m_pRefClock->QueryInterface )
      *((_QWORD *)m_pRefClock->QueryInterface + 1) = AddRef;
    else
      this->m_pRefClock = AddRef;
    v5 = (IMediaEventSink **)m_pRefClock->AddRef;
    QueryInterface = (IMediaEventSink *)m_pRefClock->QueryInterface;
    if ( v5 )
      *v5 = QueryInterface;
    else
      this->m_pSink = QueryInterface;
    if ( SHIDWORD(this->m_tRunStart) >= SLODWORD(this->m_tRunStart) )
    {
      operator delete(m_pRefClock, 0x18u);
    }
    else
    {
      m_pRefClock->AddRef = (unsigned int (__fastcall *)(IUnknown *))this->IMediaSeeking::IUnknown::__vftable;
      ++HIDWORD(this->m_tRunStart);
      this->IMediaSeeking::IUnknown::__vftable = m_pRefClock;
    }
    --this->m_FilterState;
  }
  v7 = this->m_pRefClock;
  if ( !v7 )
    return 0;
  v8 = v7[2].__vftable;
  if ( !v8 )
    return 0;
  Alignment = this->m_CurrentInterface.Alignment;
  WaitForSingleObjectEx(*(HANDLE *)(Alignment + 1040), 0xFFFFFFFF, 0);
  WaitForSingleObjectEx(*(HANDLE *)(Alignment + 1112), 0xFFFFFFFF, 0);
  if ( WaitForSingleObjectEx(*(HANDLE *)(Alignment + 1104), 0, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        206,
        &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
        "CAsyncItemHandler::QueueAsyncItem");
    WaitForSingleObjectEx(*(HANDLE *)(Alignment + 1088), 0xFFFFFFFF, 0);
    v8->QueryInterface = (HRESULT (__fastcall *)(IUnknown *, const _GUID *, void **))(Alignment + 1064);
    v12 = *(IReferenceClock_vtbl ***)(Alignment + 1072);
    v8->AddRef = (unsigned int (__fastcall *)(IUnknown *))v12;
    *v12 = v8;
    *((_QWORD *)v8->QueryInterface + 1) = v8;
    ++*(_DWORD *)(Alignment + 1080);
    ReleaseMutex(*(HANDLE *)(Alignment + 1088));
  }
  else
  {
    *(_QWORD *)(Alignment + 8LL * *(unsigned int *)(Alignment + 1024)) = v8->GetTime;
    *(_QWORD *)(Alignment + 8LL * (unsigned int)(*(_DWORD *)(Alignment + 1024))++ + 512) = v8;
    v10 = *(void **)(Alignment + 1096);
    *(_DWORD *)(Alignment + 1028) = 1;
    SetEvent(v10);
  }
  ReleaseMutex(*(HANDLE *)(Alignment + 1112));
  return 0;
}

```

## disassembly

```asm
0x180006bb0  push    rbx
0x180006bb2  sub     rsp, 20h
0x180006bb6  cmp     dword ptr [rcx+250h], 0
0x180006bbd  mov     rbx, rcx
0x180006bc0  jnz     loc_180006D23
0x180006bc6  mov     rcx, [rcx+150h]; void *
0x180006bcd  mov     [rsp+28h+arg_0], rsi
0x180006bd2  test    rcx, rcx
0x180006bd5  jz      short loc_180006C31
0x180006bd7  mov     rdx, [rcx]
0x180006bda  mov     rax, [rcx+8]
0x180006bde  test    rdx, rdx
0x180006be1  jnz     loc_180006D2C
0x180006be7  mov     [rbx+150h], rax
0x180006bee  mov     rax, [rcx+8]
0x180006bf2  mov     rdx, [rcx]
0x180006bf5  test    rax, rax
0x180006bf8  jz      loc_180006D44
0x180006bfe  mov     [rax], rdx
0x180006c01  mov     eax, [rbx+168h]
0x180006c07  cmp     [rbx+16Ch], eax
0x180006c0d  jge     loc_180006D35
0x180006c13  mov     rax, [rbx+170h]
0x180006c1a  mov     [rcx+8], rax
0x180006c1e  inc     dword ptr [rbx+16Ch]
0x180006c24  mov     [rbx+170h], rcx
0x180006c2b  dec     dword ptr [rbx+160h]
0x180006c31  mov     rsi, [rbx+150h]
0x180006c38  test    rsi, rsi
0x180006c3b  jz      loc_180006D15
0x180006c41  mov     rsi, [rsi+10h]
0x180006c45  test    rsi, rsi
0x180006c48  jz      loc_180006D15
0x180006c4e  mov     [rsp+28h+arg_8], rdi
0x180006c53  xor     r8d, r8d; bAlertable
0x180006c56  mov     rdi, [rbx+258h]
0x180006c5d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180006c62  mov     rcx, [rdi+410h]; hHandle
0x180006c69  call    cs:__imp_WaitForSingleObjectEx
0x180006c70  nop     dword ptr [rax+rax+00h]
0x180006c75  mov     rcx, [rdi+458h]; hHandle
0x180006c7c  xor     r8d, r8d; bAlertable
0x180006c7f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180006c84  call    cs:__imp_WaitForSingleObjectEx
0x180006c8b  nop     dword ptr [rax+rax+00h]
0x180006c90  mov     rcx, [rdi+450h]; hHandle
0x180006c97  xor     r8d, r8d; bAlertable
0x180006c9a  xor     edx, edx; dwMilliseconds
0x180006c9c  call    cs:__imp_WaitForSingleObjectEx
0x180006ca3  nop     dword ptr [rax+rax+00h]
0x180006ca8  test    eax, eax
0x180006caa  jnz     loc_180006D50
0x180006cb0  mov     rax, [rsi+18h]
0x180006cb4  mov     ecx, [rdi+400h]
0x180006cba  mov     [rdi+rcx*8], rax
0x180006cbe  mov     eax, [rdi+400h]
0x180006cc4  mov     [rdi+rax*8+200h], rsi
0x180006ccc  inc     dword ptr [rdi+400h]
0x180006cd2  mov     rcx, [rdi+448h]; hEvent
0x180006cd9  mov     dword ptr [rdi+404h], 1
0x180006ce3  call    cs:__imp_SetEvent
0x180006cea  nop     dword ptr [rax+rax+00h]
0x180006cef  mov     rcx, [rdi+458h]; hMutex
0x180006cf6  call    cs:__imp_ReleaseMutex
0x180006cfd  nop     dword ptr [rax+rax+00h]
0x180006d02  mov     rdi, [rsp+28h+arg_8]
0x180006d07  xor     eax, eax
0x180006d09  mov     rsi, [rsp+28h+arg_0]
0x180006d0e  add     rsp, 20h
0x180006d12  pop     rbx
0x180006d13  retn
0x180006d15  mov     rsi, [rsp+28h+arg_0]
0x180006d1a  xor     eax, eax
0x180006d1c  add     rsp, 20h
0x180006d20  pop     rbx
0x180006d21  retn
0x180006d23  xor     eax, eax
0x180006d25  add     rsp, 20h
0x180006d29  pop     rbx
0x180006d2a  retn
0x180006d2c  mov     [rdx+8], rax
0x180006d30  jmp     loc_180006BEE
0x180006d35  mov     edx, 18h; unsigned __int64
0x180006d3a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006d3f  jmp     loc_180006C2B
0x180006d44  mov     [rbx+158h], rdx
0x180006d4b  jmp     loc_180006C01
0x180006d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d57  lea     rax, WPP_GLOBAL_Control
0x180006d5e  cmp     rcx, rax
0x180006d61  jz      short loc_180006D85
0x180006d63  cmp     byte ptr [rcx+19h], 2
0x180006d67  jb      short loc_180006D85
0x180006d69  mov     rcx, [rcx+10h]
0x180006d6d  lea     r9, aCasyncitemhand_0; "CAsyncItemHandler::QueueAsyncItem"
0x180006d74  mov     edx, 0CEh
0x180006d79  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180006d80  call    WPP_SF_s
0x180006d85  mov     rcx, [rdi+440h]; hHandle
0x180006d8c  lea     rbx, [rdi+428h]
0x180006d93  xor     r8d, r8d; bAlertable
0x180006d96  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180006d9b  call    cs:__imp_WaitForSingleObjectEx
0x180006da2  nop     dword ptr [rax+rax+00h]
0x180006da7  mov     [rsi], rbx
0x180006daa  mov     rax, [rbx+8]
0x180006dae  mov     [rsi+8], rax
0x180006db2  mov     [rax], rsi
0x180006db5  mov     rax, [rsi]
0x180006db8  mov     [rax+8], rsi
0x180006dbc  inc     dword ptr [rdi+438h]
0x180006dc2  mov     rcx, [rdi+440h]; hMutex
0x180006dc9  call    cs:__imp_ReleaseMutex
0x180006dd0  nop     dword ptr [rax+rax+00h]
0x180006dd5  jmp     loc_180006CEF
```
