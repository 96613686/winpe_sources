# IPM_MESSAGE_PIPE::IpmMessageCreated(IPM_MESSAGE_IMP *)

- ea: `0x180004320`
- end: `0x180004444`
- name: `?IpmMessageCreated@IPM_MESSAGE_PIPE@@QEAAXPEAVIPM_MESSAGE_IMP@@@Z`
- size: `292`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this, struct IPM_MESSAGE_IMP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004320`
- `0x180004450`
- `0x180007e60`
- `0x180008000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004385`

## string_xrefs

- `0x1800043e6`: `IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x1800043f2`: `IPM_MESSAGE_PIPE::IpmMessageCreated`
- `0x180004404`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`

## pseudocode

```c
void __fastcall IPM_MESSAGE_PIPE::IpmMessageCreated(IPM_MESSAGE_PIPE *this, struct IPM_MESSAGE_IMP *a2)
{
  signed __int32 v4; // ecx
  IPM_MESSAGE_PIPE **v5; // rdx
  char v6; // r8
  signed __int32 v7; // edx

  if ( *((_DWORD *)this + 3)
    || (v4 = *((_DWORD *)this + 2), (_WORD)v4)
    || v4 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v4 + 0x10000) | 0xFFFF, v4) )
  {
    if ( !CReaderWriterLock3::_TryWriteLock2((IPM_MESSAGE_PIPE *)((char *)this + 8)) )
      CReaderWriterLock3::_WriteLockSpin((IPM_MESSAGE_PIPE *)((char *)this + 8));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  v5 = (IPM_MESSAGE_PIPE **)*((_QWORD *)this + 6);
  if ( *v5 != (IPM_MESSAGE_PIPE *)((char *)this + 40) )
    __fastfail(3u);
  *((_QWORD *)a2 + 11) = (char *)this + 40;
  *((_QWORD *)a2 + 12) = v5;
  *v5 = (struct IPM_MESSAGE_IMP *)((char *)a2 + 88);
  *((_QWORD *)this + 6) = (char *)a2 + 88;
  v6 = _InterlockedIncrement((volatile signed __int32 *)this + 9);
  if ( ((*((_BYTE *)this + 12) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 3, *((_DWORD *)this + 3) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, 0);
    while ( 1 )
    {
      v7 = *((_DWORD *)this + 2);
      if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v7 - 0x10000) & 0xFFFF0000, v7) )
        break;
      _mm_pause();
    }
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x2EBu,
      "IPM_MESSAGE_PIPE::IpmMessageCreated",
      "IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n",
      v6);
}

```

## disassembly

```asm
0x180004320  mov     [rsp+arg_0], rbx
0x180004325  mov     [rsp+arg_8], rsi
0x18000432a  push    rdi
0x18000432b  sub     rsp, 30h
0x18000432f  mov     eax, [rcx+0Ch]
0x180004332  mov     rsi, rdx
0x180004335  mov     rdi, rcx
0x180004338  test    eax, eax
0x18000433a  jnz     short loc_18000435B
0x18000433c  mov     ecx, [rcx+8]
0x18000433f  test    cx, cx
0x180004342  jnz     short loc_18000435B
0x180004344  lea     edx, [rcx+10000h]
0x18000434a  mov     eax, ecx
0x18000434c  or      edx, 0FFFFh
0x180004352  lock cmpxchg [rdi+8], edx
0x180004357  cmp     ecx, eax
0x180004359  jz      short loc_180004385
0x18000435b  lea     rcx, [rdi+8]; this
0x18000435f  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180004364  test    al, al
0x180004366  jnz     short loc_180004371
0x180004368  lea     rcx, [rdi+8]; this
0x18000436c  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180004371  mov     rdx, [rdi+30h]
0x180004375  lea     rcx, [rdi+28h]
0x180004379  cmp     [rdx], rcx
0x18000437c  jz      short loc_18000439C
0x18000437e  mov     ecx, 3
0x180004383  int     29h; Win8: RtlFailFast(ecx)
0x180004385  call    cs:__imp_GetCurrentThreadId
0x18000438c  nop     dword ptr [rax+rax+00h]
0x180004391  and     eax, 0FFFFFFFCh
0x180004394  or      eax, 1
0x180004397  xchg    eax, [rdi+0Ch]
0x18000439a  jmp     short loc_180004371
0x18000439c  lea     rax, [rsi+58h]
0x1800043a0  mov     r8d, 1
0x1800043a6  mov     [rax], rcx
0x1800043a9  mov     [rax+8], rdx
0x1800043ad  mov     [rdx], rax
0x1800043b0  mov     [rcx+8], rax
0x1800043b4  lock xadd [rdi+24h], r8d
0x1800043ba  mov     eax, [rdi+0Ch]
0x1800043bd  inc     r8d
0x1800043c0  dec     eax
0x1800043c2  test    al, 3
0x1800043c4  jz      short loc_180004421
0x1800043c6  xchg    eax, [rdi+0Ch]
0x1800043c9  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800043cf  test    al, 3
0x1800043d1  setnz   cl
0x1800043d4  bt      eax, 1Ch
0x1800043d8  setb    al
0x1800043db  test    al, cl
0x1800043dd  jz      short loc_180004410
0x1800043df  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800043e6  lea     rax, aIpmMessagePipe_3; "IPM_MESSAGE_PIPE::IpmMessageCreated m_c"...
0x1800043ed  mov     dword ptr [rsp+38h+var_10], r8d; char
0x1800043f2  lea     r9, aIpmMessagePipe_18; "IPM_MESSAGE_PIPE::IpmMessageCreated"
0x1800043f9  mov     r8d, 2EBh; unsigned int
0x1800043ff  mov     [rsp+38h+var_18], rax; char *
0x180004404  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000440b  call    PuDbgPrint
0x180004410  mov     rbx, [rsp+38h+arg_0]
0x180004415  mov     rsi, [rsp+38h+arg_8]
0x18000441a  add     rsp, 30h
0x18000441e  pop     rdi
0x18000441f  retn
0x180004421  xor     eax, eax
0x180004423  xchg    eax, [rdi+0Ch]
0x180004426  mov     edx, [rdi+8]
0x180004429  mov     eax, edx
0x18000442b  lea     ecx, [rdx-10000h]
0x180004431  and     ecx, 0FFFF0000h
0x180004437  lock cmpxchg [rdi+8], ecx
0x18000443c  cmp     edx, eax
0x18000443e  jz      short loc_1800043C9
0x180004440  pause
0x180004442  jmp     short loc_180004426
```
