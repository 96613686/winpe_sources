# NOTIFICATION_THREAD::RemoveMonitor(CONFIG_MONITOR *)

- ea: `0x180051248`
- end: `0x1800512ae`
- name: `?RemoveMonitor@NOTIFICATION_THREAD@@QEAAXPEAUCONFIG_MONITOR@@@Z`
- size: `102`
- prototype: `void(NOTIFICATION_THREAD *__hidden this, struct CONFIG_MONITOR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a450`
- `0x18004bbbc`
- `0x18004f600`

## callees

- `0x18001c20c`
- `0x180051248`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051263`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051263`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051271`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051271`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005127d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005127d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18005129d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18005129d`

## pseudocode

```c
void __fastcall NOTIFICATION_THREAD::RemoveMonitor(NOTIFICATION_THREAD *this, struct CONFIG_MONITOR *a2)
{
  HANDLE ProcessHeap; // rax

  if ( *((_DWORD *)a2 + 20) )
  {
    NOTIFICATION_THREAD::CloseHandles(a2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a2);
  }
  else
  {
    CReaderWriterLock3::WriteLock((struct CONFIG_MONITOR *)((char *)a2 + 88));
    if ( !*((_DWORD *)a2 + 21) )
    {
      *((_DWORD *)a2 + 21) = 1;
      NOTIFICATION_THREAD::CloseHandles(a2);
    }
    CReaderWriterLock3::WriteUnlock((struct CONFIG_MONITOR *)((char *)a2 + 88));
  }
}

```

## disassembly

```asm
0x180051248  mov     [rsp+arg_0], rbx
0x18005124d  push    rdi
0x18005124e  sub     rsp, 20h
0x180051252  cmp     dword ptr [rdx+50h], 0
0x180051256  mov     rbx, rdx
0x180051259  jz      short loc_180051279
0x18005125b  mov     rcx, rdx; struct CONFIG_MONITOR *
0x18005125e  call    ?CloseHandles@NOTIFICATION_THREAD@@CAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::CloseHandles(CONFIG_MONITOR *)
0x180051263  call    cs:__imp_GetProcessHeap
0x180051269  mov     r8, rbx; lpMem
0x18005126c  xor     edx, edx; dwFlags
0x18005126e  mov     rcx, rax; hHeap
0x180051271  call    cs:__imp_HeapFree
0x180051277  jmp     short loc_1800512A3
0x180051279  lea     rcx, [rdx+58h]
0x18005127d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180051283  mov     eax, [rbx+54h]
0x180051286  test    eax, eax
0x180051288  jnz     short loc_180051299
0x18005128a  mov     rcx, rbx; struct CONFIG_MONITOR *
0x18005128d  mov     dword ptr [rbx+54h], 1
0x180051294  call    ?CloseHandles@NOTIFICATION_THREAD@@CAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::CloseHandles(CONFIG_MONITOR *)
0x180051299  lea     rcx, [rbx+58h]
0x18005129d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800512a3  mov     rbx, [rsp+28h+arg_0]
0x1800512a8  add     rsp, 20h
0x1800512ac  pop     rdi
0x1800512ad  retn
```
