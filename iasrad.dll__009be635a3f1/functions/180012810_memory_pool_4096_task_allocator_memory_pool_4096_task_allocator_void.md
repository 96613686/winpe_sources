# memory_pool<4096,task_allocator>::~memory_pool<4096,task_allocator>(void)

- ea: `0x180012810`
- end: `0x180012890`
- name: `??1?$memory_pool@$0BAAA@Vtask_allocator@@@@QEAA@XZ`
- size: `128`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014630`
- `0x18002fdc0`

## callees

- `0x180012810`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012843`
- `KERNEL32!EnterCriticalSection` at `0x180012843`
- `KERNEL32!LeaveCriticalSection` at `0x180012858`
- `KERNEL32!LeaveCriticalSection` at `0x180012858`
- `KERNEL32!DeleteCriticalSection` at `0x180012889`
- `KERNEL32!TryEnterCriticalSection` at `0x180012827`
- `KERNEL32!TryEnterCriticalSection` at `0x180012827`
- `KERNEL32!SwitchToThread` at `0x180012838`
- `KERNEL32!SwitchToThread` at `0x180012838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012869`

## pseudocode

```c
void __fastcall memory_pool<4096,task_allocator>::~memory_pool<4096,task_allocator>(
        LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rbx

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
  DebugInfo = lpCriticalSection[1].DebugInfo;
  lpCriticalSection[1].DebugInfo = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( DebugInfo )
  {
    do
    {
      v4 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
      CoTaskMemFree(DebugInfo);
      DebugInfo = v4;
    }
    while ( v4 );
  }
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180012810  mov     [rsp+arg_0], rbx
0x180012815  mov     [rsp+arg_8], rsi
0x18001281a  push    rdi
0x18001281b  sub     rsp, 20h
0x18001281f  mov     rdi, rcx
0x180012822  xor     ebx, ebx
0x180012824  mov     rcx, rdi; lpCriticalSection
0x180012827  call    cs:__imp_TryEnterCriticalSection
0x18001282d  test    eax, eax
0x18001282f  jnz     short loc_180012849
0x180012831  inc     ebx
0x180012833  cmp     ebx, 64h ; 'd'
0x180012836  jge     short loc_180012840
0x180012838  call    cs:__imp_SwitchToThread
0x18001283e  jmp     short loc_180012824
0x180012840  mov     rcx, rdi; lpCriticalSection
0x180012843  call    cs:__imp_EnterCriticalSection
0x180012849  mov     rsi, [rdi+28h]
0x18001284d  mov     rcx, rdi; lpCriticalSection
0x180012850  mov     qword ptr [rdi+28h], 0
0x180012858  call    cs:__imp_LeaveCriticalSection
0x18001285e  test    rsi, rsi
0x180012861  jz      short loc_180012877
0x180012863  mov     rbx, [rsi]
0x180012866  mov     rcx, rsi; pv
0x180012869  call    cs:__imp_CoTaskMemFree
0x18001286f  mov     rsi, rbx
0x180012872  test    rbx, rbx
0x180012875  jnz     short loc_180012863
0x180012877  mov     rcx, rdi
0x18001287a  mov     rbx, [rsp+28h+arg_0]
0x18001287f  mov     rsi, [rsp+28h+arg_8]
0x180012884  add     rsp, 20h
0x180012888  pop     rdi
0x180012889  jmp     cs:__imp_DeleteCriticalSection
```
