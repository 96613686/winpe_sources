# MkvMfSourceLib::MkvMfSource::OnAsyncRead(void)

- ea: `0x180014ff0`
- end: `0x18001514e`
- name: `?OnAsyncRead@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019b10`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010fd0`
- `0x180014ff0`
- `0x1800427c4`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015017`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015017`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015130`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015130`

## string_xrefs

- `0x180015024`: `MkvMfSourceLib::MkvMfSource::OnAsyncRead`
- `0x1800150bf`: `OnAsyncRead AsyncReadCompletion failed.`
- `0x1800150f9`: `OnAsyncRead AsyncContinue failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::OnAsyncRead(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  unsigned int v5; // ebx
  int Continue; // eax
  const unsigned __int16 *v7; // rdx
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+28h] [rbp-50h]
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 104);
  v10 = a1 + 104;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v9, "MkvMfSourceLib::MkvMfSource::OnAsyncRead", 1471);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 688) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 296LL))(*(_QWORD *)(a1 + 688));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 688) + 280LL))(
                                                            *(_QWORD *)(a1 + 688),
                                                            &v11);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  v11 = a1;
  if ( *(_QWORD *)(a1 + 144) )
  {
    Continue = *(_DWORD *)(a1 + 480);
    if ( Continue < 0 )
    {
      v7 = L"OnAsyncRead AsyncReadCompletion failed.";
LABEL_8:
      MkvMfSourceLib::MkvMfSource::Error((MkvMfSourceLib::MkvMfSource *)a1, v7, Continue);
      v5 = 2;
      goto LABEL_15;
    }
    if ( Continue == 1 )
    {
      Continue = MkvReader::AsyncReadContinue((MkvReader *)(a1 + 184), (struct IMFAsyncCallback *)(a1 + 488));
      if ( Continue < 0 )
      {
        v7 = L"OnAsyncRead AsyncContinue failed.";
        goto LABEL_8;
      }
      if ( Continue == 1 )
      {
        v5 = 0;
        goto LABEL_15;
      }
    }
    v5 = (*(__int64 (__fastcall **)(__int64))(a1 + 528))(a1 + *(int *)(a1 + 536));
    goto LABEL_15;
  }
  v5 = 1;
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v9);
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180014ff0  push    rbx
0x180014ff2  push    rbp
0x180014ff3  push    rsi
0x180014ff4  push    rdi
0x180014ff5  sub     rsp, 58h
0x180014ff9  mov     rax, cs:__security_cookie
0x180015000  xor     rax, rsp
0x180015003  mov     [rsp+78h+var_38], rax
0x180015008  mov     rsi, rcx
0x18001500b  lea     rbp, [rcx+68h]
0x18001500f  mov     [rsp+78h+var_50], rbp
0x180015014  mov     rcx, rbp; lpCriticalSection
0x180015017  call    cs:__imp_EnterCriticalSection
0x18001501d  nop
0x18001501e  mov     r8d, 5BFh; int
0x180015024  lea     rdx, aMkvmfsourcelib_146; "MkvMfSourceLib::MkvMfSource::OnAsyncRea"...
0x18001502b  lea     rcx, [rsp+78h+var_58]; this
0x180015030  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015035  nop
0x180015036  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001503d  cmp     byte ptr [rcx+8], 0
0x180015041  jz      short loc_18001509F
0x180015043  cmp     qword ptr [rsi+2B0h], 0
0x18001504b  jz      short loc_18001509F
0x18001504d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015052  mov     rdi, rax
0x180015055  mov     rdx, [rsi+2B0h]
0x18001505c  mov     rcx, [rdx]
0x18001505f  mov     rax, [rcx+128h]
0x180015066  mov     rcx, rdx
0x180015069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001506e  mov     ebx, eax
0x180015070  mov     r8, [rsi+2B0h]
0x180015077  mov     rcx, [r8]
0x18001507a  mov     rax, [rcx+118h]
0x180015081  lea     rdx, [rsp+78h+var_48]
0x180015086  mov     rcx, r8
0x180015089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001508e  movups  xmm0, xmmword ptr [rax]
0x180015091  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180015099  mov     [rdi+7E0h], ebx
0x18001509f  mov     [rsp+78h+var_48], rsi
0x1800150a4  cmp     qword ptr [rsi+90h], 0
0x1800150ac  jnz     short loc_1800150B5
0x1800150ae  mov     ebx, 1
0x1800150b3  jmp     short loc_180015122
0x1800150b5  mov     eax, [rsi+1E0h]
0x1800150bb  test    eax, eax
0x1800150bd  jns     short loc_1800150D9
0x1800150bf  lea     rdx, aOnasyncreadAsy_0; "OnAsyncRead AsyncReadCompletion failed."
0x1800150c6  mov     r8d, eax; int
0x1800150c9  mov     rcx, rsi; this
0x1800150cc  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x1800150d1  nop
0x1800150d2  mov     ebx, 2
0x1800150d7  jmp     short loc_180015122
0x1800150d9  mov     ebx, 1
0x1800150de  cmp     eax, ebx
0x1800150e0  jnz     short loc_18001510A
0x1800150e2  lea     rdx, [rsi+1E8h]; struct IMFAsyncCallback *
0x1800150e9  lea     rcx, [rsi+0B8h]; this
0x1800150f0  call    ?AsyncReadContinue@MkvReader@@QEAAJPEAUIMFAsyncCallback@@@Z; MkvReader::AsyncReadContinue(IMFAsyncCallback *)
0x1800150f5  test    eax, eax
0x1800150f7  jns     short loc_180015102
0x1800150f9  lea     rdx, aOnasyncreadAsy; "OnAsyncRead AsyncContinue failed."
0x180015100  jmp     short loc_1800150C6
0x180015102  cmp     eax, ebx
0x180015104  jnz     short loc_18001510A
0x180015106  xor     ebx, ebx
0x180015108  jmp     short loc_180015122
0x18001510a  movsxd  rcx, dword ptr [rsi+218h]
0x180015111  add     rcx, rsi
0x180015114  mov     rax, [rsi+210h]
0x18001511b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015120  mov     ebx, eax
0x180015122  lea     rcx, [rsp+78h+var_58]; this
0x180015127  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001512c  nop
0x18001512d  mov     rcx, rbp; lpCriticalSection
0x180015130  call    cs:__imp_LeaveCriticalSection
0x180015136  mov     eax, ebx
0x180015138  mov     rcx, [rsp+78h+var_38]
0x18001513d  xor     rcx, rsp; StackCookie
0x180015140  call    __security_check_cookie
0x180015145  add     rsp, 58h
0x180015149  pop     rdi
0x18001514a  pop     rsi
0x18001514b  pop     rbp
0x18001514c  pop     rbx
0x18001514d  retn
```
