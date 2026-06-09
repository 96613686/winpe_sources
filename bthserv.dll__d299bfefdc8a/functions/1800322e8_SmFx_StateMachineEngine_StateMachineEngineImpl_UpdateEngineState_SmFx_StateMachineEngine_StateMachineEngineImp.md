# SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)

- ea: `0x1800322e8`
- end: `0x180032384`
- name: `?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z`
- size: `156`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180031040`
- `0x180031d9c`
- `0x180032048`

## callees

- `0x180031278`
- `0x1800322e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032361`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032361`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003236e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003236e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(__int64 a1, int a2)
{
  __int16 v3; // di

  *(_DWORD *)(a1 + 972) = a2;
  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 1024));
  }
  else if ( a2 == 5 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
  }
  else
  {
    if ( *(_BYTE *)(a1 + 964) )
      v3 = *(_WORD *)(*(_QWORD *)(a1 + 872) + 2LL * *(unsigned __int8 *)(a1 + 964) - 2);
    else
      v3 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
    if ( !v3 )
      SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(
        (SmFx::StateMachineEngine::StateMachineEngineImpl *)a1,
        1);
  }
}

```

## disassembly

```asm
0x1800322e8  mov     [rsp+arg_0], rbx
0x1800322ed  mov     [rsp+arg_8], rsi
0x1800322f2  push    rdi
0x1800322f3  sub     rsp, 20h
0x1800322f7  lea     eax, [rdx-3]
0x1800322fa  mov     [rcx+3CCh], edx
0x180032300  mov     rbx, rcx
0x180032303  cmp     eax, 1
0x180032306  jbe     short loc_18003235A
0x180032308  cmp     edx, 5
0x18003230b  jnz     short loc_18003231C
0x18003230d  add     rcx, 3D0h; lpCriticalSection
0x180032314  call    cs:__imp_LeaveCriticalSection
0x18003231a  jmp     short loc_180032374
0x18003231c  movzx   eax, byte ptr [rcx+3C4h]
0x180032323  xor     esi, esi
0x180032325  test    al, al
0x180032327  jnz     short loc_18003232D
0x180032329  mov     edi, esi
0x18003232b  jmp     short loc_18003233C
0x18003232d  mov     rcx, rax
0x180032330  mov     rax, [rbx+368h]
0x180032337  movzx   edi, word ptr [rax+rcx*2-2]
0x18003233c  lea     rcx, [rbx+3D0h]; lpCriticalSection
0x180032343  call    cs:__imp_LeaveCriticalSection
0x180032349  test    di, di
0x18003234c  jnz     short loc_180032374
0x18003234e  mov     dl, 1; bool
0x180032350  mov     rcx, rbx; this
0x180032353  call    ?Destroy@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAX_N@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(bool)
0x180032358  jmp     short loc_180032374
0x18003235a  add     rcx, 3D0h; lpCriticalSection
0x180032361  call    cs:__imp_LeaveCriticalSection
0x180032367  mov     rcx, [rbx+400h]; pwk
0x18003236e  call    cs:__imp_SubmitThreadpoolWork
0x180032374  mov     rbx, [rsp+28h+arg_0]
0x180032379  mov     rsi, [rsp+28h+arg_8]
0x18003237e  add     rsp, 20h
0x180032382  pop     rdi
0x180032383  retn
```
