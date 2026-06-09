# MkvMfSourceLib::MkvMfSource::OnAsyncRead(void)

- ea: `0x1800159e8`
- end: `0x180015b53`
- name: `?OnAsyncRead@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a6d0`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011720`
- `0x1800159e8`
- `0x180044570`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b2e`

## string_xrefs

- `0x180015a22`: `MkvMfSourceLib::MkvMfSource::OnAsyncRead`
- `0x180015abd`: `OnAsyncRead AsyncReadCompletion failed.`
- `0x180015af7`: `OnAsyncRead AsyncContinue failed.`

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
0x1800159e8  push    rbx
0x1800159ea  push    rbp
0x1800159eb  push    rsi
0x1800159ec  push    rdi
0x1800159ed  sub     rsp, 58h
0x1800159f1  mov     rax, cs:__security_cookie
0x1800159f8  xor     rax, rsp
0x1800159fb  mov     [rsp+78h+var_38], rax
0x180015a00  mov     rsi, rcx
0x180015a03  lea     rbp, [rcx+68h]
0x180015a07  mov     [rsp+78h+var_50], rbp
0x180015a0c  mov     rcx, rbp; lpCriticalSection
0x180015a0f  call    cs:__imp_EnterCriticalSection
0x180015a16  nop     dword ptr [rax+rax+00h]
0x180015a1b  nop
0x180015a1c  mov     r8d, 5BFh; int
0x180015a22  lea     rdx, aMkvmfsourcelib_146; "MkvMfSourceLib::MkvMfSource::OnAsyncRea"...
0x180015a29  lea     rcx, [rsp+78h+var_58]; this
0x180015a2e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015a33  nop
0x180015a34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015a3b  cmp     byte ptr [rcx+8], 0
0x180015a3f  jz      short loc_180015A9D
0x180015a41  cmp     qword ptr [rsi+2B0h], 0
0x180015a49  jz      short loc_180015A9D
0x180015a4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015a50  mov     rdi, rax
0x180015a53  mov     rdx, [rsi+2B0h]
0x180015a5a  mov     rcx, [rdx]
0x180015a5d  mov     rax, [rcx+128h]
0x180015a64  mov     rcx, rdx
0x180015a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6c  mov     ebx, eax
0x180015a6e  mov     r8, [rsi+2B0h]
0x180015a75  mov     rcx, [r8]
0x180015a78  mov     rax, [rcx+118h]
0x180015a7f  lea     rdx, [rsp+78h+var_48]
0x180015a84  mov     rcx, r8
0x180015a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a8c  movups  xmm0, xmmword ptr [rax]
0x180015a8f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180015a97  mov     [rdi+7E0h], ebx
0x180015a9d  mov     [rsp+78h+var_48], rsi
0x180015aa2  cmp     qword ptr [rsi+90h], 0
0x180015aaa  jnz     short loc_180015AB3
0x180015aac  mov     ebx, 1
0x180015ab1  jmp     short loc_180015B20
0x180015ab3  mov     eax, [rsi+1E0h]
0x180015ab9  test    eax, eax
0x180015abb  jns     short loc_180015AD7
0x180015abd  lea     rdx, aOnasyncreadAsy_0; "OnAsyncRead AsyncReadCompletion failed."
0x180015ac4  mov     r8d, eax; int
0x180015ac7  mov     rcx, rsi; this
0x180015aca  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180015acf  nop
0x180015ad0  mov     ebx, 2
0x180015ad5  jmp     short loc_180015B20
0x180015ad7  mov     ebx, 1
0x180015adc  cmp     eax, ebx
0x180015ade  jnz     short loc_180015B08
0x180015ae0  lea     rdx, [rsi+1E8h]; struct IMFAsyncCallback *
0x180015ae7  lea     rcx, [rsi+0B8h]; this
0x180015aee  call    ?AsyncReadContinue@MkvReader@@QEAAJPEAUIMFAsyncCallback@@@Z; MkvReader::AsyncReadContinue(IMFAsyncCallback *)
0x180015af3  test    eax, eax
0x180015af5  jns     short loc_180015B00
0x180015af7  lea     rdx, aOnasyncreadAsy; "OnAsyncRead AsyncContinue failed."
0x180015afe  jmp     short loc_180015AC4
0x180015b00  cmp     eax, ebx
0x180015b02  jnz     short loc_180015B08
0x180015b04  xor     ebx, ebx
0x180015b06  jmp     short loc_180015B20
0x180015b08  movsxd  rcx, dword ptr [rsi+218h]
0x180015b0f  add     rcx, rsi
0x180015b12  mov     rax, [rsi+210h]
0x180015b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b1e  mov     ebx, eax
0x180015b20  lea     rcx, [rsp+78h+var_58]; this
0x180015b25  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015b2a  nop
0x180015b2b  mov     rcx, rbp; lpCriticalSection
0x180015b2e  call    cs:__imp_LeaveCriticalSection
0x180015b35  nop     dword ptr [rax+rax+00h]
0x180015b3a  mov     eax, ebx
0x180015b3c  mov     rcx, [rsp+78h+var_38]
0x180015b41  xor     rcx, rsp; StackCookie
0x180015b44  call    __security_check_cookie
0x180015b49  add     rsp, 58h
0x180015b4d  pop     rdi
0x180015b4e  pop     rsi
0x180015b4f  pop     rbp
0x180015b50  pop     rbx
0x180015b51  retn
```
