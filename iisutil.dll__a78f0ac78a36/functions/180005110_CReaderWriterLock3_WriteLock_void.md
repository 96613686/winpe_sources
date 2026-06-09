# CReaderWriterLock3::WriteLock(void)

- ea: `0x180005110`
- end: `0x18000517c`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002570`
- `0x180004150`
- `0x180005184`
- `0x1800053d0`
- `0x180005b40`
- `0x180008220`
- `0x18000a950`
- `0x18000fbd0`
- `0x180010080`
- `0x180011090`
- `0x180011ff0`
- `0x180012f10`
- `0x180014450`
- `0x180015990`
- `0x180016430`
- `0x180016690`
- `0x180019ea0`
- `0x18001a110`
- `0x18001a310`
- `0x180026d10`
- `0x180027bb0`
- `0x1800284b0`
- `0x180028570`
- `0x180029130`
- `0x180029730`
- `0x180029cd0`
- `0x18002bdc0`

## callees

- `0x180005110`
- `0x180007180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000513d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000515d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000513d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000515d`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // edx

  if ( *((_DWORD *)this + 1)
    || (unsigned __int16)*(_DWORD *)this
    || (v2 = *(_DWORD *)this,
        v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2)) )
  {
    if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)this + 1);
    else
      CReaderWriterLock3::_WriteLockSpin(this);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
}

```

## disassembly

```asm
0x180005110  push    rbx
0x180005112  sub     rsp, 20h
0x180005116  mov     eax, [rcx+4]
0x180005119  mov     rbx, rcx
0x18000511c  test    eax, eax
0x18000511e  jnz     short loc_18000513D
0x180005120  mov     edx, [rcx]
0x180005122  test    dx, dx
0x180005125  jnz     short loc_18000513D
0x180005127  lea     ecx, [rdx+10000h]
0x18000512d  mov     eax, edx
0x18000512f  or      ecx, 0FFFFh
0x180005135  lock cmpxchg [rbx], ecx
0x180005139  cmp     edx, eax
0x18000513b  jz      short loc_18000515D
0x18000513d  call    cs:__imp_GetCurrentThreadId
0x180005143  mov     ecx, [rbx+4]
0x180005146  and     eax, 0FFFFFFFCh
0x180005149  and     ecx, 0FFFFFFFCh
0x18000514c  cmp     ecx, eax
0x18000514e  jz      short loc_180005172
0x180005150  mov     rcx, rbx; this
0x180005153  add     rsp, 20h
0x180005157  pop     rbx
0x180005158  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000515d  call    cs:__imp_GetCurrentThreadId
0x180005163  and     eax, 0FFFFFFFCh
0x180005166  or      eax, 1
0x180005169  xchg    eax, [rbx+4]
0x18000516c  add     rsp, 20h
0x180005170  pop     rbx
0x180005171  retn
0x180005172  lock inc dword ptr [rbx+4]
0x180005176  add     rsp, 20h
0x18000517a  pop     rbx
0x18000517b  retn
```
