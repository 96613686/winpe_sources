# TSyncThreadContext::DoWork(void)

- ea: `0x14001d428`
- end: `0x14001d534`
- name: `?DoWork@TSyncThreadContext@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(TSyncThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001e750`

## callees

- `0x1400086f8`
- `0x140011728`
- `0x14001bdcc`
- `0x14001c368`
- `0x14001cce4`
- `0x14001cd70`
- `0x14001d428`
- `0x14001fd58`
- `0x140063010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14001d485`
- `KERNEL32!SetEvent` at `0x14001d485`

## string_xrefs

- `0x14001d447`: `TSyncThreadContext::DoWork`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TSyncThreadContext::DoWork(TSyncThreadContext *this)
{
  const wchar_t *v2; // r9
  int LastErrorAsFailHRNoBreak; // edi
  char *v4; // rcx
  NCoreLibrary *v5; // rcx
  __int64 v6; // rbx
  _BYTE v7[56]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (const wchar_t *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v2 = *(const wchar_t **)v2;
  EtwEnterExitEventPipelineRAII::EtwEnterExitEventPipelineRAII(
    (EtwEnterExitEventPipelineRAII *)v7,
    L"TSyncThreadContext::DoWork",
    *((_DWORD *)this + 6),
    v2);
  LastErrorAsFailHRNoBreak = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 40LL))(*(_QWORD *)this);
  if ( *(_BYTE *)(*((_QWORD *)this + 1) + 257LL)
    || (v4 = (char *)*((_QWORD *)this + 2), (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL)
    || SetEvent(v4) )
  {
LABEL_8:
    if ( LastErrorAsFailHRNoBreak >= 0 )
      goto LABEL_10;
    goto LABEL_9;
  }
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v5);
    goto LABEL_8;
  }
LABEL_9:
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 24LL))(
    *((_QWORD *)this + 1) + 24LL,
    (unsigned int)LastErrorAsFailHRNoBreak,
    0);
LABEL_10:
  VerifyThreadComState(*(struct IPrintPipelineFilter **)this);
  v6 = *((_QWORD *)this + 1);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v6 + 168)) == *(_DWORD *)(v6 + 252) )
  {
    TImgPipelineManager::CleanupFilters((TImgPipelineManager *)v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids);
    }
    TImgPipelineManager::CallPipelineDone((TImgPipelineManager *)v6);
  }
  EtwEnterExitEventPipelineRAII::~EtwEnterExitEventPipelineRAII((EtwEnterExitEventPipelineRAII *)v7);
}

```

## disassembly

```asm
0x14001d428  mov     [rsp+arg_0], rbx
0x14001d42d  push    rdi
0x14001d42e  sub     rsp, 50h
0x14001d432  mov     rbx, rcx
0x14001d435  lea     r9, [rcx+20h]
0x14001d439  cmp     qword ptr [r9+18h], 7
0x14001d43e  jbe     short loc_14001D443
0x14001d440  mov     r9, [r9]; wchar_t *
0x14001d443  mov     r8d, [rcx+18h]; unsigned int
0x14001d447  lea     rdx, aTsyncthreadcon; "TSyncThreadContext::DoWork"
0x14001d44e  lea     rcx, [rsp+58h+var_38]; this
0x14001d453  call    ??0EtwEnterExitEventPipelineRAII@@QEAA@PEB_WI0@Z; EtwEnterExitEventPipelineRAII::EtwEnterExitEventPipelineRAII(wchar_t const *,uint,wchar_t const *)
0x14001d458  nop
0x14001d459  mov     rcx, [rbx]
0x14001d45c  mov     rax, [rcx]
0x14001d45f  mov     rax, [rax+28h]
0x14001d463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d468  mov     edi, eax
0x14001d46a  mov     rcx, [rbx+8]
0x14001d46e  cmp     byte ptr [rcx+101h], 0
0x14001d475  jnz     short loc_14001D49A
0x14001d477  mov     rcx, [rbx+10h]; hEvent
0x14001d47b  lea     rdx, [rcx-1]
0x14001d47f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14001d483  ja      short loc_14001D49A
0x14001d485  call    cs:__imp_SetEvent
0x14001d48b  test    eax, eax
0x14001d48d  jnz     short loc_14001D49A
0x14001d48f  test    edi, edi
0x14001d491  js      short loc_14001D49E
0x14001d493  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14001d498  mov     edi, eax
0x14001d49a  test    edi, edi
0x14001d49c  jns     short loc_14001D4B7
0x14001d49e  mov     rcx, [rbx+8]
0x14001d4a2  add     rcx, 18h
0x14001d4a6  mov     rax, [rcx]
0x14001d4a9  xor     r8d, r8d
0x14001d4ac  mov     edx, edi
0x14001d4ae  mov     rax, [rax+18h]
0x14001d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d4b7  mov     rcx, [rbx]; struct IPrintPipelineFilter *
0x14001d4ba  call    ?VerifyThreadComState@@YAXPEAUIPrintPipelineFilter@@@Z; VerifyThreadComState(IPrintPipelineFilter *)
0x14001d4bf  mov     rbx, [rbx+8]
0x14001d4c3  mov     eax, 1
0x14001d4c8  lock xadd [rbx+0A8h], eax
0x14001d4d0  inc     eax
0x14001d4d2  cmp     eax, [rbx+0FCh]
0x14001d4d8  jnz     short loc_14001D51F
0x14001d4da  mov     rcx, rbx; this
0x14001d4dd  call    ?CleanupFilters@TImgPipelineManager@@AEAAXXZ; TImgPipelineManager::CleanupFilters(void)
0x14001d4e2  lea     rax, WPP_GLOBAL_Control
0x14001d4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d4f0  cmp     rcx, rax
0x14001d4f3  jz      short loc_14001D516
0x14001d4f5  test    byte ptr [rcx+1Ch], 8
0x14001d4f9  jz      short loc_14001D516
0x14001d4fb  cmp     byte ptr [rcx+19h], 3
0x14001d4ff  jb      short loc_14001D516
0x14001d501  mov     edx, 19h
0x14001d506  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001d50d  mov     rcx, [rcx+10h]
0x14001d511  call    WPP_SF_
0x14001d516  mov     rcx, rbx; this
0x14001d519  call    ?CallPipelineDone@TImgPipelineManager@@AEAAXXZ; TImgPipelineManager::CallPipelineDone(void)
0x14001d51e  nop
0x14001d51f  lea     rcx, [rsp+58h+var_38]; this
0x14001d524  call    ??1EtwEnterExitEventPipelineRAII@@UEAA@XZ; EtwEnterExitEventPipelineRAII::~EtwEnterExitEventPipelineRAII(void)
0x14001d529  mov     rbx, [rsp+58h+arg_0]
0x14001d52e  add     rsp, 50h
0x14001d532  pop     rdi
0x14001d533  retn
```
