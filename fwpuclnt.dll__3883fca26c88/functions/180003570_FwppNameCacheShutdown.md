# FwppNameCacheShutdown

- ea: `0x180003570`
- end: `0x180003640`
- name: `FwppNameCacheShutdown`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003240`

## callees

- `0x180003570`
- `0x180003648`
- `0x180011984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800035fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800035fa`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18000359e`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18000359e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003632`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003621`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003621`

## pseudocode

```c
void FwppNameCacheShutdown()
{
  __int64 *v0; // rbx
  __int64 *v1; // rcx

  byte_18007C401 = 1;
  if ( !gFwpProcessShutdown && byte_18007C400 )
  {
    while ( !TryEnterCriticalSection(&gNameCacheState) )
      Sleep(0xAu);
    FwppSessionListDestroy();
    v0 = (__int64 *)qword_18007C440;
    while ( v0 != &qword_18007C440 )
    {
      v1 = v0;
      v0 = (__int64 *)*v0;
      FwpDestroyWorkEntry(v1);
    }
    if ( hObject )
      CloseHandle(hObject);
    hObject = 0;
    if ( dword_18007C3F8 )
    {
      DeleteCriticalSection(&gNameCacheState);
      dword_18007C3F8 = 0;
    }
  }
}

```

## disassembly

```asm
0x180003570  mov     [rsp+arg_0], rbx
0x180003575  push    rbp
0x180003576  sub     rsp, 20h
0x18000357a  cmp     cs:gFwpProcessShutdown, 0
0x180003581  mov     cs:byte_18007C401, 1
0x180003588  jnz     loc_180003610
0x18000358e  cmp     cs:byte_18007C400, 0
0x180003595  jz      short loc_180003610
0x180003597  lea     rcx, gNameCacheState; lpCriticalSection
0x18000359e  call    cs:__imp_TryEnterCriticalSection
0x1800035a5  nop     dword ptr [rax+rax+00h]
0x1800035aa  test    eax, eax
0x1800035ac  jz      short loc_18000361C
0x1800035ae  call    FwppSessionListDestroy
0x1800035b3  mov     rbx, cs:qword_18007C440
0x1800035ba  lea     rbp, qword_18007C440
0x1800035c1  jmp     short loc_1800035CE
0x1800035c3  mov     rcx, rbx
0x1800035c6  mov     rbx, [rbx]
0x1800035c9  call    FwpDestroyWorkEntry
0x1800035ce  cmp     rbx, rbp
0x1800035d1  jnz     short loc_1800035C3
0x1800035d3  mov     rcx, cs:hObject; hObject
0x1800035da  test    rcx, rcx
0x1800035dd  jnz     short loc_180003632
0x1800035df  cmp     cs:dword_18007C3F8, 0
0x1800035e6  mov     cs:hObject, 0
0x1800035f1  jz      short loc_180003610
0x1800035f3  lea     rcx, gNameCacheState; lpCriticalSection
0x1800035fa  call    cs:__imp_DeleteCriticalSection
0x180003601  nop     dword ptr [rax+rax+00h]
0x180003606  mov     cs:dword_18007C3F8, 0
0x180003610  mov     rbx, [rsp+28h+arg_0]
0x180003615  add     rsp, 20h
0x180003619  pop     rbp
0x18000361a  retn
0x18000361c  mov     ecx, 0Ah; dwMilliseconds
0x180003621  call    cs:__imp_Sleep
0x180003628  nop     dword ptr [rax+rax+00h]
0x18000362d  jmp     loc_180003597
0x180003632  call    cs:__imp_CloseHandle
0x180003639  nop     dword ptr [rax+rax+00h]
0x18000363e  jmp     short loc_1800035DF
```
