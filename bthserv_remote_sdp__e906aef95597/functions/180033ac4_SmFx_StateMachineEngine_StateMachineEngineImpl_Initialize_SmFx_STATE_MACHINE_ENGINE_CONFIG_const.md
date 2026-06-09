# SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &)

- ea: `0x180033ac4`
- end: `0x180033c11`
- name: `?Initialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@@Z`
- size: `333`
- prototype: `__int64 __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this, const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f5ac`

## callees

- `0x180033ac4`
- `0x180033c18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180033b13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180033b13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033b40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033b40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033b54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bd2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180033ba0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180033ba0`

## pseudocode

```c
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
0x180033ac4  mov     [rsp+arg_0], rbx
0x180033ac9  push    rdi
0x180033aca  sub     rsp, 20h
0x180033ace  movups  xmm0, xmmword ptr [rdx]
0x180033ad1  lea     rbx, [rcx+3D0h]
0x180033ad8  mov     rdi, rcx
0x180033adb  movups  xmm1, xmmword ptr [rdx+10h]
0x180033adf  movups  xmmword ptr [rcx+378h], xmm0
0x180033ae6  movups  xmm0, xmmword ptr [rdx+20h]
0x180033aea  movups  xmmword ptr [rcx+388h], xmm1
0x180033af1  movsd   xmm1, qword ptr [rdx+30h]
0x180033af6  movups  xmmword ptr [rcx+398h], xmm0
0x180033afd  movsd   qword ptr [rcx+3A8h], xmm1
0x180033b05  cmp     byte ptr [rbx+28h], 0
0x180033b09  jnz     short loc_180033B23
0x180033b0b  mov     edx, 0FA0h; dwSpinCount
0x180033b10  mov     rcx, rbx; lpCriticalSection
0x180033b13  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180033b1a  nop     dword ptr [rax+rax+00h]
0x180033b1f  mov     byte ptr [rbx+28h], 1
0x180033b23  movzx   eax, byte ptr [rdi+3A9h]
0x180033b2a  mov     ecx, 10h
0x180033b2f  test    al, al
0x180033b31  cmovnz  ecx, eax
0x180033b34  movzx   ebx, cl
0x180033b37  add     rbx, rbx
0x180033b3a  mov     [rdi+360h], cl
0x180033b40  call    cs:__imp_GetProcessHeap
0x180033b47  nop     dword ptr [rax+rax+00h]
0x180033b4c  mov     r8, rbx; dwBytes
0x180033b4f  xor     edx, edx; dwFlags
0x180033b51  mov     rcx, rax; hHeap
0x180033b54  call    cs:__imp_HeapAlloc
0x180033b5b  nop     dword ptr [rax+rax+00h]
0x180033b60  mov     [rdi+368h], rax
0x180033b67  test    rax, rax
0x180033b6a  jnz     short loc_180033B76
0x180033b6c  mov     eax, 0C000009Ah
0x180033b71  jmp     loc_180033C05
0x180033b76  cmp     byte ptr [rdi+3A8h], 0
0x180033b7d  jz      short loc_180033BFB
0x180033b7f  lea     rbx, [rdi+400h]
0x180033b86  cmp     qword ptr [rbx], 0
0x180033b8a  jz      short loc_180033B93
0x180033b8c  mov     eax, 0C007139Fh
0x180033b91  jmp     short loc_180033C05
0x180033b93  xor     r8d, r8d; pcbe
0x180033b96  lea     rcx, _lambda_8a03d23fdee2c1785e106aafab25a0f7____lambda_invoker_cdecl_; pfnwk
0x180033b9d  mov     rdx, rbx; pv
0x180033ba0  call    cs:__imp_CreateThreadpoolWork
0x180033ba7  nop     dword ptr [rax+rax+00h]
0x180033bac  mov     [rbx], rax
0x180033baf  test    rax, rax
0x180033bb2  jnz     short loc_180033BEC
0x180033bb4  call    cs:__imp_GetLastError
0x180033bbb  nop     dword ptr [rax+rax+00h]
0x180033bc0  test    eax, eax
0x180033bc2  jg      short loc_180033BD2
0x180033bc4  call    cs:__imp_GetLastError
0x180033bcb  nop     dword ptr [rax+rax+00h]
0x180033bd0  jmp     short loc_180033BE6
0x180033bd2  call    cs:__imp_GetLastError
0x180033bd9  nop     dword ptr [rax+rax+00h]
0x180033bde  movzx   eax, ax
0x180033be1  or      eax, 0C0070000h
0x180033be6  test    eax, eax
0x180033be8  jns     short loc_180033BFB
0x180033bea  jmp     short loc_180033C05
0x180033bec  lea     rax, _lambda_c276094d149607b901f7fae525da7e78____lambda_invoker_cdecl_
0x180033bf3  mov     [rbx+10h], rdi
0x180033bf7  mov     [rbx+8], rax
0x180033bfb  mov     rcx, rdi; this
0x180033bfe  call    ?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)
0x180033c03  xor     eax, eax
0x180033c05  mov     rbx, [rsp+28h+arg_0]
0x180033c0a  add     rsp, 20h
0x180033c0e  pop     rdi
0x180033c0f  retn
```
