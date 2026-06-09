# CDDISync::CFreeThreadedLock::Enter(CDevice *)

- ea: `0x18003dcd4`
- end: `0x18003dd63`
- name: `?Enter@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z`
- size: `143`
- prototype: `void __fastcall(struct CDevice *)`
- caller_count: `28`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006f28`
- `0x18000887c`
- `0x180008be8`
- `0x180015a50`
- `0x180016010`
- `0x18002cb00`
- `0x1800303a0`
- `0x18003a3e0`
- `0x18003ad80`
- `0x18003baa0`
- `0x18003bfa0`
- `0x18003ce70`
- `0x18003dc80`
- `0x18003e0e0`
- `0x18003e1c0`
- `0x18003e380`
- `0x18003ee58`
- `0x18003f040`
- `0x18003f524`
- `0x180040240`
- `0x180040640`
- `0x180054720`
- `0x18005fb84`
- `0x180070c30`
- `0x18007128c`
- `0x180074ed8`
- `0x18007538c`
- `0x1800782a0`

## callees

- `0x18003dcd4`

## import_xrefs

- `ntdll!NtFlushProcessWriteBuffers` at `0x18003dd0f`
- `ntdll!NtFlushProcessWriteBuffers` at `0x18003dd0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dcf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dcf0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18003dd55`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18003dd55`

## pseudocode

```c
void __fastcall CDDISync::CFreeThreadedLock::Enter(struct CDevice *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edi
  unsigned int i; // ecx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 1792);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 1792));
  while ( !*((_DWORD *)a1 + 435) )
  {
    v3 = *((_DWORD *)a1 + 434);
    *((_DWORD *)a1 + 433) = -1;
    NtFlushProcessWriteBuffers();
    for ( i = 0; i < v3; ++i )
    {
      if ( !*((_DWORD *)a1 + 432) )
        goto LABEL_6;
      _mm_pause();
    }
    *((_DWORD *)a1 + 433) = 0;
    SleepConditionVariableCS((PCONDITION_VARIABLE)a1 + 229, v1, 1u);
  }
LABEL_6:
  ++*((_DWORD *)a1 + 435);
}

```

## disassembly

```asm
0x18003dcd4  mov     [rsp+arg_0], rbx
0x18003dcd9  mov     [rsp+arg_8], rsi
0x18003dcde  push    rdi
0x18003dcdf  sub     rsp, 20h
0x18003dce3  lea     rsi, [rcx+700h]
0x18003dcea  mov     rbx, rcx
0x18003dced  mov     rcx, rsi; lpCriticalSection
0x18003dcf0  call    cs:__imp_EnterCriticalSection
0x18003dcf6  cmp     dword ptr [rbx+6CCh], 0
0x18003dcfd  jnz     short loc_18003DD25
0x18003dcff  mov     edi, [rbx+6C8h]
0x18003dd05  mov     dword ptr [rbx+6C4h], 0FFFFFFFFh
0x18003dd0f  call    cs:__imp_NtFlushProcessWriteBuffers
0x18003dd15  xor     ecx, ecx
0x18003dd17  cmp     ecx, edi
0x18003dd19  jnb     short loc_18003DD3B
0x18003dd1b  mov     eax, [rbx+6C0h]
0x18003dd21  test    eax, eax
0x18003dd23  jnz     short loc_18003DD5D
0x18003dd25  inc     dword ptr [rbx+6CCh]
0x18003dd2b  mov     rbx, [rsp+28h+arg_0]
0x18003dd30  mov     rsi, [rsp+28h+arg_8]
0x18003dd35  add     rsp, 20h
0x18003dd39  pop     rdi
0x18003dd3a  retn
0x18003dd3b  lea     rcx, [rbx+728h]; ConditionVariable
0x18003dd42  mov     dword ptr [rbx+6C4h], 0
0x18003dd4c  mov     r8d, 1; dwMilliseconds
0x18003dd52  mov     rdx, rsi; CriticalSection
0x18003dd55  call    cs:__imp_SleepConditionVariableCS
0x18003dd5b  jmp     short loc_18003DCF6
0x18003dd5d  pause
0x18003dd5f  inc     ecx
0x18003dd61  jmp     short loc_18003DD17
```
