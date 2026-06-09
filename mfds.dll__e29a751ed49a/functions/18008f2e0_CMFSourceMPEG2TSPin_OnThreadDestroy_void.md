# CMFSourceMPEG2TSPin::OnThreadDestroy(void)

- ea: `0x18008f2e0`
- end: `0x18008f3d1`
- name: `?OnThreadDestroy@CMFSourceMPEG2TSPin@@MEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CMFSourceMPEG2TSPin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180090b50`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800381d8`
- `0x18008f2e0`
- `0x180092898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f35b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f35b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f346`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f39d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18008f38d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18008f38d`

## string_xrefs

- `0x18008f2f2`: `CMFSourceMPEG2TSPin::OnThreadDestroy`

## pseudocode

```c
__int64 __fastcall CMFSourceMPEG2TSPin::OnThreadDestroy(CMFSourceMPEG2TSPin *this)
{
  int v2; // edi
  void *v3; // rcx
  char v5; // [rsp+30h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v5, "CMFSourceMPEG2TSPin::OnThreadDestroy", 3867);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 57, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids);
  _InterlockedExchange((volatile __int32 *)this + 107, 1);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v2 = *((_DWORD *)this + 153);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( v2 )
    CAMEvent::Wait((CMFSourceMPEG2TSPin *)((char *)this + 528), 0xFFFFFFFF);
  v3 = (void *)*((_QWORD *)this + 78);
  *((_BYTE *)this + 460) = 1;
  if ( v3 )
  {
    if ( !AvRevertMmThreadCharacteristics(v3) )
      GetLastError();
    *((_QWORD *)this + 78) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v5);
  return 0;
}

```

## disassembly

```asm
0x18008f2e0  mov     [rsp+arg_8], rbx
0x18008f2e5  mov     [rsp+arg_10], rsi
0x18008f2ea  push    rdi
0x18008f2eb  sub     rsp, 20h
0x18008f2ef  mov     rsi, rcx
0x18008f2f2  lea     rdx, aCmfsourcempeg2; "CMFSourceMPEG2TSPin::OnThreadDestroy"
0x18008f2f9  lea     rcx, [rsp+28h+arg_0]; this
0x18008f2fe  mov     r8d, 0F1Bh; int
0x18008f304  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008f309  cmp     cs:byte_1800EACCB, 8
0x18008f310  jb      short loc_18008F331
0x18008f312  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f319  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x18008f320  mov     edx, 39h ; '9'
0x18008f325  mov     rcx, [rcx+88h]
0x18008f32c  call    WPP_SF_
0x18008f331  mov     eax, 1
0x18008f336  lea     rbx, [rsi+1E8h]
0x18008f33d  xchg    eax, [rsi+1ACh]
0x18008f343  mov     rcx, rbx; lpCriticalSection
0x18008f346  call    cs:__imp_EnterCriticalSection
0x18008f34d  nop     dword ptr [rax+rax+00h]
0x18008f352  mov     edi, [rsi+264h]
0x18008f358  mov     rcx, rbx; lpCriticalSection
0x18008f35b  call    cs:__imp_LeaveCriticalSection
0x18008f362  nop     dword ptr [rax+rax+00h]
0x18008f367  test    edi, edi
0x18008f369  jz      short loc_18008F37A
0x18008f36b  lea     rcx, [rsi+210h]; this
0x18008f372  or      edx, 0FFFFFFFFh; unsigned int
0x18008f375  call    ?Wait@CAMEvent@@QEAAHK@Z; CAMEvent::Wait(ulong)
0x18008f37a  mov     rcx, [rsi+270h]; AvrtHandle
0x18008f381  mov     byte ptr [rsi+1CCh], 1
0x18008f388  test    rcx, rcx
0x18008f38b  jz      short loc_18008F3B4
0x18008f38d  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18008f394  nop     dword ptr [rax+rax+00h]
0x18008f399  test    eax, eax
0x18008f39b  jnz     short loc_18008F3A9
0x18008f39d  call    cs:__imp_GetLastError
0x18008f3a4  nop     dword ptr [rax+rax+00h]
0x18008f3a9  mov     qword ptr [rsi+270h], 0
0x18008f3b4  lea     rcx, [rsp+28h+arg_0]; this
0x18008f3b9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008f3be  mov     rbx, [rsp+28h+arg_8]
0x18008f3c3  xor     eax, eax
0x18008f3c5  mov     rsi, [rsp+28h+arg_10]
0x18008f3ca  add     rsp, 20h
0x18008f3ce  pop     rdi
0x18008f3cf  retn
```
