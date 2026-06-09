# NOTIFICATION_THREAD::FreeMonitor(CONFIG_MONITOR *)

- ea: `0x180050f6c`
- end: `0x180051025`
- name: `?FreeMonitor@NOTIFICATION_THREAD@@QEAAXPEAUCONFIG_MONITOR@@@Z`
- size: `185`
- prototype: `void(NOTIFICATION_THREAD *__hidden this, struct CONFIG_MONITOR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051090`
- `0x180051510`

## callees

- `0x18001c20c`
- `0x1800507fc`
- `0x180050f6c`
- `0x18005102c`
- `0x1800516b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051010`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050f87`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050fa6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050f87`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050fa6`

## pseudocode

```c
void __fastcall NOTIFICATION_THREAD::FreeMonitor(NOTIFICATION_THREAD *this, struct CONFIG_MONITOR *a2)
{
  CReaderWriterLock3 *v3; // rcx
  char IsSchemaMonitor; // al
  HANDLE ProcessHeap; // rax

  v3 = (struct CONFIG_MONITOR *)((char *)a2 + 88);
  if ( *((_DWORD *)a2 + 21) )
  {
    CReaderWriterLock3::WriteUnlock(v3);
  }
  else
  {
    CReaderWriterLock3::WriteUnlock(v3);
    CONFIG_CACHE::PurgePath(*((CONFIG_CACHE **)this + 4), *(const unsigned __int16 **)a2, *((_DWORD *)a2 + 18));
    if ( !*((_DWORD *)a2 + 21) )
      return;
  }
  NOTIFICATION_THREAD::CloseHandles(a2);
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
  {
    IsSchemaMonitor = CONFIG_MONITOR::IsSchemaMonitor(a2);
    McTemplateU0pzzzttt_EtwEventWriteTransfer(
      *((_QWORD *)a2 + 3) == -1,
      (unsigned int)NATIVERD_EVENT_FILE_CHANGE_NOTIFICATION_MONITOR_DESTROYED,
      (_DWORD)a2,
      *(_QWORD *)a2,
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2),
      *((_DWORD *)a2 + 19),
      *((_QWORD *)a2 + 3) == -1,
      IsSchemaMonitor);
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a2);
  _InterlockedDecrement((volatile signed __int32 *)this + 15);
}

```

## disassembly

```asm
0x180050f6c  mov     [rsp+arg_0], rbx
0x180050f71  push    rdi
0x180050f72  sub     rsp, 50h
0x180050f76  mov     eax, [rdx+54h]
0x180050f79  mov     rdi, rcx
0x180050f7c  lea     rcx, [rdx+58h]
0x180050f80  mov     rbx, rdx
0x180050f83  test    eax, eax
0x180050f85  jnz     short loc_180050FA6
0x180050f87  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180050f8d  mov     r8d, [rbx+48h]; unsigned int
0x180050f91  mov     rdx, [rbx]; unsigned __int16 *
0x180050f94  mov     rcx, [rdi+20h]; this
0x180050f98  call    ?PurgePath@CONFIG_CACHE@@QEAAJPEBGK@Z; CONFIG_CACHE::PurgePath(ushort const *,ulong)
0x180050f9d  mov     eax, [rbx+54h]
0x180050fa0  test    eax, eax
0x180050fa2  jz      short loc_18005101A
0x180050fa4  jmp     short loc_180050FAC
0x180050fa6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180050fac  mov     rcx, rbx; struct CONFIG_MONITOR *
0x180050faf  call    ?CloseHandles@NOTIFICATION_THREAD@@CAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::CloseHandles(CONFIG_MONITOR *)
0x180050fb4  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x180050fbb  jz      short loc_180051002
0x180050fbd  mov     rcx, rbx; this
0x180050fc0  call    ?IsSchemaMonitor@CONFIG_MONITOR@@QEAAHXZ; CONFIG_MONITOR::IsSchemaMonitor(void)
0x180050fc5  mov     r9, [rbx]
0x180050fc8  lea     rdx, NATIVERD_EVENT_FILE_CHANGE_NOTIFICATION_MONITOR_DESTROYED
0x180050fcf  mov     [rsp+58h+var_18], eax
0x180050fd3  xor     ecx, ecx
0x180050fd5  mov     eax, [rbx+4Ch]
0x180050fd8  mov     r8, rbx
0x180050fdb  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180050fe0  setz    cl
0x180050fe3  mov     [rsp+58h+var_20], ecx
0x180050fe7  mov     [rsp+58h+var_28], eax
0x180050feb  mov     rax, [rbx+10h]
0x180050fef  mov     [rsp+58h+var_30], rax
0x180050ff4  mov     rax, [rbx+8]
0x180050ff8  mov     [rsp+58h+var_38], rax
0x180050ffd  call    McTemplateU0pzzzttt_EtwEventWriteTransfer
0x180051002  call    cs:__imp_GetProcessHeap
0x180051008  mov     r8, rbx; lpMem
0x18005100b  xor     edx, edx; dwFlags
0x18005100d  mov     rcx, rax; hHeap
0x180051010  call    cs:__imp_HeapFree
0x180051016  lock dec dword ptr [rdi+3Ch]
0x18005101a  mov     rbx, [rsp+58h+arg_0]
0x18005101f  add     rsp, 50h
0x180051023  pop     rdi
0x180051024  retn
```
