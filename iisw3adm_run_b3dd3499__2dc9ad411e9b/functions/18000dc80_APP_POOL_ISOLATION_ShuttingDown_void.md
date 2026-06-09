# APP_POOL_ISOLATION::ShuttingDown(void)

- ea: `0x18000dc80`
- end: `0x18000dd66`
- name: `?ShuttingDown@APP_POOL_ISOLATION@@QEAAXXZ`
- size: `230`
- prototype: `void __fastcall(APP_POOL_ISOLATION *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800060b8`
- `0x18000a158`

## callees

- `0x18000dc80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000dce8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000dce8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000dcbe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000dcbe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000dccb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000dccb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000dd38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000dd38`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd10`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd10`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd55`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd55`

## pseudocode

```c
void __fastcall APP_POOL_ISOLATION::ShuttingDown(APP_POOL_ISOLATION *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  struct _TP_POOL *v3; // rcx
  void *v4; // rcx

  if ( !*((_DWORD *)this + 7) )
  {
    if ( *((_DWORD *)this + 101) != 1 )
    {
      _InterlockedExchange((volatile __int32 *)this + 101, 1);
      v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 62);
      if ( v2 )
      {
        CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
        CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 62));
        *((_QWORD *)this + 62) = 0;
      }
      v3 = (struct _TP_POOL *)*((_QWORD *)this + 61);
      if ( v3 )
      {
        CloseThreadpool(v3);
        *((_QWORD *)this + 61) = 0;
      }
      if ( *((_DWORD *)this + 120) )
        *((_DWORD *)this + 120) = 0;
    }
    CReaderWriterLock3::WriteLock((APP_POOL_ISOLATION *)((char *)this + 16));
    v4 = (void *)*((_QWORD *)this + 11);
    if ( v4 != (void *)-1LL )
    {
      CloseHandle(v4);
      *((_QWORD *)this + 11) = -1;
    }
    if ( *((_DWORD *)this + 20) )
    {
      DeleteFileW(*((LPCWSTR *)this + 8));
      **((_WORD **)this + 8) = 0;
      *((_DWORD *)this + 20) = 0;
    }
    *((_DWORD *)this + 7) = 1;
    CReaderWriterLock3::WriteUnlock((APP_POOL_ISOLATION *)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000dc80  mov     [rsp+arg_0], rbx
0x18000dc85  push    rdi
0x18000dc86  sub     rsp, 20h
0x18000dc8a  cmp     dword ptr [rcx+1Ch], 0
0x18000dc8e  mov     rbx, rcx
0x18000dc91  jnz     loc_18000DD5B
0x18000dc97  cmp     dword ptr [rcx+194h], 1
0x18000dc9e  jz      short loc_18000DD0C
0x18000dca0  mov     eax, 1
0x18000dca5  xchg    eax, [rcx+194h]
0x18000dcab  mov     rcx, [rcx+1F0h]; ptpcg
0x18000dcb2  test    rcx, rcx
0x18000dcb5  jz      short loc_18000DCDC
0x18000dcb7  xor     r8d, r8d; pvCleanupContext
0x18000dcba  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000dcbe  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000dcc4  mov     rcx, [rbx+1F0h]; ptpcg
0x18000dccb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000dcd1  mov     qword ptr [rbx+1F0h], 0
0x18000dcdc  mov     rcx, [rbx+1E8h]; ptpp
0x18000dce3  test    rcx, rcx
0x18000dce6  jz      short loc_18000DCF9
0x18000dce8  call    cs:__imp_CloseThreadpool
0x18000dcee  mov     qword ptr [rbx+1E8h], 0
0x18000dcf9  cmp     dword ptr [rbx+1E0h], 0
0x18000dd00  jz      short loc_18000DD0C
0x18000dd02  mov     dword ptr [rbx+1E0h], 0
0x18000dd0c  lea     rcx, [rbx+10h]
0x18000dd10  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000dd16  mov     rcx, [rbx+58h]; hObject
0x18000dd1a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000dd1e  jz      short loc_18000DD2E
0x18000dd20  call    cs:__imp_CloseHandle
0x18000dd26  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x18000dd2e  cmp     dword ptr [rbx+50h], 0
0x18000dd32  jz      short loc_18000DD4A
0x18000dd34  mov     rcx, [rbx+40h]; lpFileName
0x18000dd38  call    cs:__imp_DeleteFileW
0x18000dd3e  mov     rdx, [rbx+40h]
0x18000dd42  xor     eax, eax
0x18000dd44  mov     [rdx], ax
0x18000dd47  mov     [rbx+50h], eax
0x18000dd4a  lea     rcx, [rbx+10h]
0x18000dd4e  mov     dword ptr [rbx+1Ch], 1
0x18000dd55  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000dd5b  mov     rbx, [rsp+28h+arg_0]
0x18000dd60  add     rsp, 20h
0x18000dd64  pop     rdi
0x18000dd65  retn
```
