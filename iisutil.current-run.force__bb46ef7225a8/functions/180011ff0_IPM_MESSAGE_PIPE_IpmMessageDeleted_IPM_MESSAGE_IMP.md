# IPM_MESSAGE_PIPE::IpmMessageDeleted(IPM_MESSAGE_IMP *)

- ea: `0x180011ff0`
- end: `0x18001209b`
- name: `?IpmMessageDeleted@IPM_MESSAGE_PIPE@@QEAAXPEAVIPM_MESSAGE_IMP@@@Z`
- size: `171`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this, struct IPM_MESSAGE_IMP *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004910`
- `0x180005b40`
- `0x18000e150`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x180011ff0`

## string_xrefs

- `0x180012078`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18001205b`: `IPM_MESSAGE_PIPE::IpmMessageDeleted m_cMessages = %d\n`
- `0x180012066`: `IPM_MESSAGE_PIPE::IpmMessageDeleted`

## pseudocode

```c
void __fastcall IPM_MESSAGE_PIPE::IpmMessageDeleted(IPM_MESSAGE_PIPE *this, struct IPM_MESSAGE_IMP *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  char v7; // bl

  CReaderWriterLock3::WriteLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  v4 = (_QWORD *)((char *)a2 + 88);
  v5 = *v4;
  if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v6 = (_QWORD *)v4[1], (_QWORD *)*v6 != v4) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  v7 = _InterlockedDecrement((volatile signed __int32 *)this + 9);
  CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x30Du,
      "IPM_MESSAGE_PIPE::IpmMessageDeleted",
      "IPM_MESSAGE_PIPE::IpmMessageDeleted m_cMessages = %d\n",
      v7);
}

```

## disassembly

```asm
0x180011ff0  mov     [rsp+arg_0], rbx
0x180011ff5  mov     [rsp+arg_8], rsi
0x180011ffa  push    rdi
0x180011ffb  sub     rsp, 30h
0x180011fff  mov     rdi, rcx
0x180012002  mov     rbx, rdx
0x180012005  add     rcx, 8; this
0x180012009  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001200e  add     rbx, 58h ; 'X'
0x180012012  mov     rdx, [rbx]
0x180012015  cmp     [rdx+8], rbx
0x180012019  jnz     short loc_180012094
0x18001201b  mov     rax, [rbx+8]
0x18001201f  cmp     [rax], rbx
0x180012022  jnz     short loc_180012094
0x180012024  mov     [rax], rdx
0x180012027  or      ebx, 0FFFFFFFFh
0x18001202a  mov     [rdx+8], rax
0x18001202e  lock xadd [rdi+24h], ebx
0x180012033  lea     rcx, [rdi+8]; this
0x180012037  dec     ebx
0x180012039  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001203e  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180012044  test    al, 3
0x180012046  setnz   cl
0x180012049  bt      eax, 1Ch
0x18001204d  setb    al
0x180012050  test    al, cl
0x180012052  jz      short loc_180012084
0x180012054  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001205b  lea     rax, aIpmMessagePipe_13; "IPM_MESSAGE_PIPE::IpmMessageDeleted m_c"...
0x180012062  mov     dword ptr [rsp+38h+var_10], ebx; char
0x180012066  lea     r9, aIpmMessagePipe_1; "IPM_MESSAGE_PIPE::IpmMessageDeleted"
0x18001206d  mov     r8d, 30Dh; unsigned int
0x180012073  mov     [rsp+38h+var_18], rax; char *
0x180012078  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001207f  call    PuDbgPrint
0x180012084  mov     rbx, [rsp+38h+arg_0]
0x180012089  mov     rsi, [rsp+38h+arg_8]
0x18001208e  add     rsp, 30h
0x180012092  pop     rdi
0x180012093  retn
0x180012094  mov     ecx, 3
0x180012099  int     29h; Win8: RtlFailFast(ecx)
```
