# SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)

- ea: `0x180034240`
- end: `0x180034302`
- name: `?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180032de0`
- `0x180033c18`
- `0x180033ef0`

## callees

- `0x180033054`
- `0x180034240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003426c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003426c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342d2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800342e5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800342e5`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(__int64 a1, int a2)
{
  __int64 v3; // rax
  __int16 v4; // di

  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    *(_DWORD *)(a1 + 972) = a2;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 1024));
  }
  else if ( a2 == 5 )
  {
    *(_DWORD *)(a1 + 972) = 5;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
  }
  else
  {
    v3 = *(unsigned __int8 *)(a1 + 964);
    *(_DWORD *)(a1 + 972) = a2;
    if ( (_BYTE)v3 )
      v4 = *(_WORD *)(*(_QWORD *)(a1 + 872) + 2 * v3 - 2);
    else
      v4 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
    if ( !v4 )
      SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(
        (SmFx::StateMachineEngine::StateMachineEngineImpl *)a1,
        1);
  }
}

```

## disassembly

```asm
0x180034240  mov     [rsp+arg_0], rbx
0x180034245  mov     [rsp+arg_8], rsi
0x18003424a  push    rdi
0x18003424b  sub     rsp, 20h
0x18003424f  lea     eax, [rdx-3]
0x180034252  mov     rbx, rcx
0x180034255  cmp     eax, 1
0x180034258  jbe     short loc_1800342C5
0x18003425a  cmp     edx, 5
0x18003425d  jnz     short loc_18003427A
0x18003425f  mov     [rcx+3CCh], edx
0x180034265  add     rcx, 3D0h; lpCriticalSection
0x18003426c  call    cs:__imp_LeaveCriticalSection
0x180034273  nop     dword ptr [rax+rax+00h]
0x180034278  jmp     short loc_1800342F1
0x18003427a  movzx   eax, byte ptr [rcx+3C4h]
0x180034281  xor     esi, esi
0x180034283  mov     [rcx+3CCh], edx
0x180034289  test    al, al
0x18003428b  jnz     short loc_180034292
0x18003428d  movzx   edi, si
0x180034290  jmp     short loc_1800342A1
0x180034292  mov     rcx, rax
0x180034295  mov     rax, [rbx+368h]
0x18003429c  movzx   edi, word ptr [rax+rcx*2-2]
0x1800342a1  lea     rcx, [rbx+3D0h]; lpCriticalSection
0x1800342a8  call    cs:__imp_LeaveCriticalSection
0x1800342af  nop     dword ptr [rax+rax+00h]
0x1800342b4  test    di, di
0x1800342b7  jnz     short loc_1800342F1
0x1800342b9  mov     dl, 1; bool
0x1800342bb  mov     rcx, rbx; this
0x1800342be  call    ?Destroy@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAX_N@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(bool)
0x1800342c3  jmp     short loc_1800342F1
0x1800342c5  mov     [rcx+3CCh], edx
0x1800342cb  add     rcx, 3D0h; lpCriticalSection
0x1800342d2  call    cs:__imp_LeaveCriticalSection
0x1800342d9  nop     dword ptr [rax+rax+00h]
0x1800342de  mov     rcx, [rbx+400h]; pwk
0x1800342e5  call    cs:__imp_SubmitThreadpoolWork
0x1800342ec  nop     dword ptr [rax+rax+00h]
0x1800342f1  mov     rbx, [rsp+28h+arg_0]
0x1800342f6  mov     rsi, [rsp+28h+arg_8]
0x1800342fb  add     rsp, 20h
0x1800342ff  pop     rdi
0x180034300  retn
```
