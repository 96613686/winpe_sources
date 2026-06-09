# IPM_MESSAGE_PIPE::IpmMessageCreated(IPM_MESSAGE_IMP *)

- ea: `0x1800038a0`
- end: `0x1800039bd`
- name: `?IpmMessageCreated@IPM_MESSAGE_PIPE@@QEAAXPEAVIPM_MESSAGE_IMP@@@Z`
- size: `285`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this, struct IPM_MESSAGE_IMP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800038a0`
- `0x1800039d0`
- `0x180007180`
- `0x180007300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003905`

## string_xrefs

- `0x180003960`: `IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x18000396c`: `IPM_MESSAGE_PIPE::IpmMessageCreated`
- `0x18000397e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`

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
0x1800038a0  mov     [rsp+arg_0], rbx
0x1800038a5  mov     [rsp+arg_8], rsi
0x1800038aa  push    rdi
0x1800038ab  sub     rsp, 30h
0x1800038af  mov     eax, [rcx+0Ch]
0x1800038b2  mov     rsi, rdx
0x1800038b5  mov     rdi, rcx
0x1800038b8  test    eax, eax
0x1800038ba  jnz     short loc_1800038DB
0x1800038bc  mov     ecx, [rcx+8]
0x1800038bf  test    cx, cx
0x1800038c2  jnz     short loc_1800038DB
0x1800038c4  lea     edx, [rcx+10000h]
0x1800038ca  mov     eax, ecx
0x1800038cc  or      edx, 0FFFFh
0x1800038d2  lock cmpxchg [rdi+8], edx
0x1800038d7  cmp     ecx, eax
0x1800038d9  jz      short loc_180003905
0x1800038db  lea     rcx, [rdi+8]; this
0x1800038df  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x1800038e4  test    al, al
0x1800038e6  jnz     short loc_1800038F1
0x1800038e8  lea     rcx, [rdi+8]; this
0x1800038ec  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x1800038f1  mov     rdx, [rdi+30h]
0x1800038f5  lea     rcx, [rdi+28h]
0x1800038f9  cmp     [rdx], rcx
0x1800038fc  jz      short loc_180003916
0x1800038fe  mov     ecx, 3
0x180003903  int     29h; Win8: RtlFailFast(ecx)
0x180003905  call    cs:__imp_GetCurrentThreadId
0x18000390b  and     eax, 0FFFFFFFCh
0x18000390e  or      eax, 1
0x180003911  xchg    eax, [rdi+0Ch]
0x180003914  jmp     short loc_1800038F1
0x180003916  lea     rax, [rsi+58h]
0x18000391a  mov     r8d, 1
0x180003920  mov     [rax], rcx
0x180003923  mov     [rax+8], rdx
0x180003927  mov     [rdx], rax
0x18000392a  mov     [rcx+8], rax
0x18000392e  lock xadd [rdi+24h], r8d
0x180003934  mov     eax, [rdi+0Ch]
0x180003937  inc     r8d
0x18000393a  dec     eax
0x18000393c  test    al, 3
0x18000393e  jz      short loc_18000399A
0x180003940  xchg    eax, [rdi+0Ch]
0x180003943  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180003949  test    al, 3
0x18000394b  setnz   cl
0x18000394e  bt      eax, 1Ch
0x180003952  setb    al
0x180003955  test    al, cl
0x180003957  jz      short loc_18000398A
0x180003959  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003960  lea     rax, aIpmMessagePipe_3; "IPM_MESSAGE_PIPE::IpmMessageCreated m_c"...
0x180003967  mov     dword ptr [rsp+38h+var_10], r8d; char
0x18000396c  lea     r9, aIpmMessagePipe_18; "IPM_MESSAGE_PIPE::IpmMessageCreated"
0x180003973  mov     r8d, 2EBh; unsigned int
0x180003979  mov     [rsp+38h+var_18], rax; char *
0x18000397e  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003985  call    PuDbgPrint
0x18000398a  mov     rbx, [rsp+38h+arg_0]
0x18000398f  mov     rsi, [rsp+38h+arg_8]
0x180003994  add     rsp, 30h
0x180003998  pop     rdi
0x180003999  retn
0x18000399a  xor     eax, eax
0x18000399c  xchg    eax, [rdi+0Ch]
0x18000399f  mov     edx, [rdi+8]
0x1800039a2  mov     eax, edx
0x1800039a4  lea     ecx, [rdx-10000h]
0x1800039aa  and     ecx, 0FFFF0000h
0x1800039b0  lock cmpxchg [rdi+8], ecx
0x1800039b5  cmp     edx, eax
0x1800039b7  jz      short loc_180003943
0x1800039b9  pause
0x1800039bb  jmp     short loc_18000399F
```
