# QUEUE::Dequeue(void)

- ea: `0x180004040`
- end: `0x1800040b9`
- name: `?Dequeue@QUEUE@@QEAAPEAVQUEUE_RECORD@@XZ`
- size: `121`
- prototype: `ULONG_PTR *__fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042e0`
- `0x1800050cc`

## callees

- `0x180004040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000409e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000409e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000404d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000404d`
- `iisutil!WriteRefTraceLog` at `0x180004065`
- `iisutil!WriteRefTraceLog` at `0x180004065`

## pseudocode

```c
ULONG_PTR *__fastcall QUEUE::Dequeue(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE LockSemaphore; // rcx
  LPCRITICAL_SECTION v3; // rcx
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rax
  ULONG_PTR *p_SpinCount; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v6; // rdx

  EnterCriticalSection(lpCriticalSection);
  LockSemaphore = lpCriticalSection[1].LockSemaphore;
  --LODWORD(lpCriticalSection[1].OwningThread);
  if ( LockSemaphore )
    WriteRefTraceLog(LockSemaphore, LODWORD(lpCriticalSection[1].OwningThread), lpCriticalSection);
  v3 = lpCriticalSection + 1;
  DebugInfo = (struct _RTL_CRITICAL_SECTION *)lpCriticalSection[1].DebugInfo;
  if ( DebugInfo == &lpCriticalSection[1] )
  {
    p_SpinCount = 0;
  }
  else
  {
    if ( *(LPCRITICAL_SECTION *)&DebugInfo->LockCount != v3
      || (v6 = DebugInfo->DebugInfo, DebugInfo->DebugInfo->CriticalSection != DebugInfo) )
    {
      __fastfail(3u);
    }
    v3->DebugInfo = v6;
    p_SpinCount = &DebugInfo[-1].SpinCount;
    v6->CriticalSection = v3;
    HIDWORD(lpCriticalSection[1].OwningThread) -= LODWORD(DebugInfo->OwningThread);
  }
  LeaveCriticalSection(lpCriticalSection);
  return p_SpinCount;
}

```

## disassembly

```asm
0x180004040  mov     [rsp+arg_0], rbx
0x180004045  push    rdi
0x180004046  sub     rsp, 20h
0x18000404a  mov     rbx, rcx
0x18000404d  call    cs:__imp_EnterCriticalSection
0x180004053  mov     rcx, [rbx+40h]
0x180004057  dec     dword ptr [rbx+38h]
0x18000405a  test    rcx, rcx
0x18000405d  jz      short loc_18000406B
0x18000405f  mov     edx, [rbx+38h]
0x180004062  mov     r8, rbx
0x180004065  call    cs:__imp_WriteRefTraceLog
0x18000406b  lea     rcx, [rbx+28h]
0x18000406f  mov     rax, [rcx]
0x180004072  cmp     rax, rcx
0x180004075  jnz     short loc_18000407B
0x180004077  xor     edi, edi
0x180004079  jmp     short loc_18000409B
0x18000407b  cmp     [rax+8], rcx
0x18000407f  jnz     short loc_1800040B2
0x180004081  mov     rdx, [rax]
0x180004084  cmp     [rdx+8], rax
0x180004088  jnz     short loc_1800040B2
0x18000408a  mov     [rcx], rdx
0x18000408d  lea     rdi, [rax-8]
0x180004091  mov     [rdx+8], rcx
0x180004095  mov     ecx, [rdi+18h]
0x180004098  sub     [rbx+3Ch], ecx
0x18000409b  mov     rcx, rbx; lpCriticalSection
0x18000409e  call    cs:__imp_LeaveCriticalSection
0x1800040a4  mov     rbx, [rsp+28h+arg_0]
0x1800040a9  mov     rax, rdi
0x1800040ac  add     rsp, 20h
0x1800040b0  pop     rdi
0x1800040b1  retn
0x1800040b2  mov     ecx, 3
0x1800040b7  int     29h; Win8: RtlFailFast(ecx)
```
