# memory_pool<4096,task_allocator>::allocate(void)

- ea: `0x180014494`
- end: `0x180014505`
- name: `?allocate@?$memory_pool@$0BAAA@Vtask_allocator@@@@QEAAPEAXXZ`
- size: `113`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012988`
- `0x180015938`

## callees

- `0x180014494`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800144c2`
- `KERNEL32!EnterCriticalSection` at `0x1800144c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800144db`
- `KERNEL32!LeaveCriticalSection` at `0x1800144e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800144db`
- `KERNEL32!LeaveCriticalSection` at `0x1800144e9`
- `KERNEL32!TryEnterCriticalSection` at `0x1800144a6`
- `KERNEL32!TryEnterCriticalSection` at `0x1800144a6`
- `KERNEL32!SwitchToThread` at `0x1800144b7`
- `KERNEL32!SwitchToThread` at `0x1800144b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800144f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800144f4`

## pseudocode

```c
PRTL_CRITICAL_SECTION_DEBUG *__fastcall memory_pool<4096,task_allocator>::allocate(
        LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // edi
  PRTL_CRITICAL_SECTION_DEBUG *DebugInfo; // rdi

  v2 = 0;
  while ( !TryEnterCriticalSection(lpCriticalSection) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(lpCriticalSection);
      break;
    }
    SwitchToThread();
  }
  DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG *)lpCriticalSection[1].DebugInfo;
  if ( DebugInfo )
  {
    lpCriticalSection[1].DebugInfo = *DebugInfo;
    LeaveCriticalSection(lpCriticalSection);
    return DebugInfo;
  }
  else
  {
    LeaveCriticalSection(lpCriticalSection);
    return (PRTL_CRITICAL_SECTION_DEBUG *)CoTaskMemAlloc(0x1000u);
  }
}

```

## disassembly

```asm
0x180014494  mov     [rsp+arg_0], rbx
0x180014499  push    rdi
0x18001449a  sub     rsp, 20h
0x18001449e  mov     rbx, rcx
0x1800144a1  xor     edi, edi
0x1800144a3  mov     rcx, rbx; lpCriticalSection
0x1800144a6  call    cs:__imp_TryEnterCriticalSection
0x1800144ac  test    eax, eax
0x1800144ae  jnz     short loc_1800144C8
0x1800144b0  inc     edi
0x1800144b2  cmp     edi, 64h ; 'd'
0x1800144b5  jge     short loc_1800144BF
0x1800144b7  call    cs:__imp_SwitchToThread
0x1800144bd  jmp     short loc_1800144A3
0x1800144bf  mov     rcx, rbx; lpCriticalSection
0x1800144c2  call    cs:__imp_EnterCriticalSection
0x1800144c8  mov     rdi, [rbx+28h]
0x1800144cc  test    rdi, rdi
0x1800144cf  jz      short loc_1800144E6
0x1800144d1  mov     rcx, [rdi]
0x1800144d4  mov     [rbx+28h], rcx
0x1800144d8  mov     rcx, rbx; lpCriticalSection
0x1800144db  call    cs:__imp_LeaveCriticalSection
0x1800144e1  mov     rax, rdi
0x1800144e4  jmp     short loc_1800144FA
0x1800144e6  mov     rcx, rbx; lpCriticalSection
0x1800144e9  call    cs:__imp_LeaveCriticalSection
0x1800144ef  mov     ecx, 1000h; cb
0x1800144f4  call    cs:__imp_CoTaskMemAlloc
0x1800144fa  mov     rbx, [rsp+28h+arg_0]
0x1800144ff  add     rsp, 20h
0x180014503  pop     rdi
0x180014504  retn
```
