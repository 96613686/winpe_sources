# SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &)

- ea: `0x180031c74`
- end: `0x180031d93`
- name: `?Initialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@@Z`
- size: `287`
- prototype: `signed int __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *this, const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001db80`

## callees

- `0x180031c74`
- `0x180031d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180031cc3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180031cc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031cf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031cf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031cea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180031d3b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180031d3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this,
        const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *a2)
{
  char *v2; // rbx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  unsigned __int8 v6; // cl
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  signed int result; // eax
  PTP_WORK ThreadpoolWork; // rax

  v2 = (char *)this + 976;
  v4 = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 888) = *(_OWORD *)a2;
  v5 = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 904) = v4;
  *(_QWORD *)&v4 = *((_QWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 920) = v5;
  *((_QWORD *)this + 117) = v4;
  if ( !*((_BYTE *)this + 1016) )
  {
    InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 976), 0xFA0u);
    v2[40] = 1;
  }
  v6 = 16;
  if ( *((_BYTE *)this + 937) )
    v6 = *((_BYTE *)this + 937);
  v7 = 2LL * v6;
  *((_BYTE *)this + 864) = v6;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, v7);
  *((_QWORD *)this + 109) = v9;
  if ( !v9 )
    return -1073741670;
  if ( !*((_BYTE *)this + 936) )
    goto LABEL_17;
  if ( *((_QWORD *)this + 128) )
    return -1073278049;
  ThreadpoolWork = CreateThreadpoolWork(
                     lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_,
                     (char *)this + 1024,
                     0);
  *((_QWORD *)this + 128) = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    *((_QWORD *)this + 130) = this;
    *((_QWORD *)this + 129) = lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_;
LABEL_17:
    SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(this);
    return 0;
  }
  if ( (int)GetLastError() > 0 )
    result = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    result = GetLastError();
  if ( result >= 0 )
    goto LABEL_17;
  return result;
}

```

## disassembly

```asm
0x180031c74  mov     [rsp+arg_0], rbx
0x180031c79  push    rdi
0x180031c7a  sub     rsp, 20h
0x180031c7e  movups  xmm0, xmmword ptr [rdx]
0x180031c81  lea     rbx, [rcx+3D0h]
0x180031c88  mov     rdi, rcx
0x180031c8b  movups  xmm1, xmmword ptr [rdx+10h]
0x180031c8f  movups  xmmword ptr [rcx+378h], xmm0
0x180031c96  movups  xmm0, xmmword ptr [rdx+20h]
0x180031c9a  movups  xmmword ptr [rcx+388h], xmm1
0x180031ca1  movsd   xmm1, qword ptr [rdx+30h]
0x180031ca6  movups  xmmword ptr [rcx+398h], xmm0
0x180031cad  movsd   qword ptr [rcx+3A8h], xmm1
0x180031cb5  cmp     byte ptr [rbx+28h], 0
0x180031cb9  jnz     short loc_180031CCD
0x180031cbb  mov     edx, 0FA0h; dwSpinCount
0x180031cc0  mov     rcx, rbx; lpCriticalSection
0x180031cc3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180031cc9  mov     byte ptr [rbx+28h], 1
0x180031ccd  movzx   eax, byte ptr [rdi+3A9h]
0x180031cd4  mov     ecx, 10h
0x180031cd9  test    al, al
0x180031cdb  cmovnz  ecx, eax
0x180031cde  movzx   ebx, cl
0x180031ce1  add     rbx, rbx
0x180031ce4  mov     [rdi+360h], cl
0x180031cea  call    cs:__imp_GetProcessHeap
0x180031cf0  mov     r8, rbx; dwBytes
0x180031cf3  xor     edx, edx; dwFlags
0x180031cf5  mov     rcx, rax; hHeap
0x180031cf8  call    cs:__imp_HeapAlloc
0x180031cfe  mov     [rdi+368h], rax
0x180031d05  test    rax, rax
0x180031d08  jnz     short loc_180031D11
0x180031d0a  mov     eax, 0C000009Ah
0x180031d0f  jmp     short loc_180031D88
0x180031d11  cmp     byte ptr [rdi+3A8h], 0
0x180031d18  jz      short loc_180031D7E
0x180031d1a  lea     rbx, [rdi+400h]
0x180031d21  cmp     qword ptr [rbx], 0
0x180031d25  jz      short loc_180031D2E
0x180031d27  mov     eax, 0C007139Fh
0x180031d2c  jmp     short loc_180031D88
0x180031d2e  xor     r8d, r8d; pcbe
0x180031d31  lea     rcx, _lambda_8a03d23fdee2c1785e106aafab25a0f7____lambda_invoker_cdecl_; pfnwk
0x180031d38  mov     rdx, rbx; pv
0x180031d3b  call    cs:__imp_CreateThreadpoolWork
0x180031d41  mov     [rbx], rax
0x180031d44  test    rax, rax
0x180031d47  jnz     short loc_180031D6F
0x180031d49  call    cs:__imp_GetLastError
0x180031d4f  test    eax, eax
0x180031d51  jg      short loc_180031D5B
0x180031d53  call    cs:__imp_GetLastError
0x180031d59  jmp     short loc_180031D69
0x180031d5b  call    cs:__imp_GetLastError
0x180031d61  movzx   eax, ax
0x180031d64  or      eax, 0C0070000h
0x180031d69  test    eax, eax
0x180031d6b  jns     short loc_180031D7E
0x180031d6d  jmp     short loc_180031D88
0x180031d6f  lea     rax, _lambda_c276094d149607b901f7fae525da7e78____lambda_invoker_cdecl_
0x180031d76  mov     [rbx+10h], rdi
0x180031d7a  mov     [rbx+8], rax
0x180031d7e  mov     rcx, rdi; this
0x180031d81  call    ?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)
0x180031d86  xor     eax, eax
0x180031d88  mov     rbx, [rsp+28h+arg_0]
0x180031d8d  add     rsp, 20h
0x180031d91  pop     rdi
0x180031d92  retn
```
