# IPM2_MESSAGE_PIPE::IpmMessageDeleted(IPM2_MESSAGE_IMP *)

- ea: `0x180028570`
- end: `0x18002861b`
- name: `?IpmMessageDeleted@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z`
- size: `171`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, struct IPM2_MESSAGE_IMP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002734c`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x180028570`

## string_xrefs

- `0x1800285f8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800285db`: `IPM2_MESSAGE_PIPE::IpmMessageDeleted m_cMessages = %d\n`
- `0x1800285e6`: `IPM2_MESSAGE_PIPE::IpmMessageDeleted`

## pseudocode

```c
void __fastcall IPM2_MESSAGE_PIPE::IpmMessageDeleted(IPM2_MESSAGE_PIPE *this, struct IPM2_MESSAGE_IMP *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  char v7; // bl

  CReaderWriterLock3::WriteLock((IPM2_MESSAGE_PIPE *)((char *)this + 24));
  v4 = (_QWORD *)((char *)a2 + 88);
  v5 = *v4;
  if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v6 = (_QWORD *)v4[1], (_QWORD *)*v6 != v4) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  v7 = _InterlockedDecrement((volatile signed __int32 *)this + 13);
  CReaderWriterLock3::WriteUnlock((IPM2_MESSAGE_PIPE *)((char *)this + 24));
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x274u,
      "IPM2_MESSAGE_PIPE::IpmMessageDeleted",
      "IPM2_MESSAGE_PIPE::IpmMessageDeleted m_cMessages = %d\n",
      v7);
}

```

## disassembly

```asm
0x180028570  mov     [rsp+arg_0], rbx
0x180028575  mov     [rsp+arg_8], rsi
0x18002857a  push    rdi
0x18002857b  sub     rsp, 30h
0x18002857f  mov     rdi, rcx
0x180028582  mov     rbx, rdx
0x180028585  add     rcx, 18h; this
0x180028589  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002858e  add     rbx, 58h ; 'X'
0x180028592  mov     rdx, [rbx]
0x180028595  cmp     [rdx+8], rbx
0x180028599  jnz     short loc_180028614
0x18002859b  mov     rax, [rbx+8]
0x18002859f  cmp     [rax], rbx
0x1800285a2  jnz     short loc_180028614
0x1800285a4  mov     [rax], rdx
0x1800285a7  or      ebx, 0FFFFFFFFh
0x1800285aa  mov     [rdx+8], rax
0x1800285ae  lock xadd [rdi+34h], ebx
0x1800285b3  lea     rcx, [rdi+18h]; this
0x1800285b7  dec     ebx
0x1800285b9  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800285be  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800285c4  test    al, 3
0x1800285c6  setnz   cl
0x1800285c9  bt      eax, 1Ch
0x1800285cd  setb    al
0x1800285d0  test    al, cl
0x1800285d2  jz      short loc_180028604
0x1800285d4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800285db  lea     rax, aIpm2MessagePip_2; "IPM2_MESSAGE_PIPE::IpmMessageDeleted m_"...
0x1800285e2  mov     dword ptr [rsp+38h+var_10], ebx; char
0x1800285e6  lea     r9, aIpm2MessagePip_25; "IPM2_MESSAGE_PIPE::IpmMessageDeleted"
0x1800285ed  mov     r8d, 274h; unsigned int
0x1800285f3  mov     [rsp+38h+var_18], rax; char *
0x1800285f8  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800285ff  call    PuDbgPrint
0x180028604  mov     rbx, [rsp+38h+arg_0]
0x180028609  mov     rsi, [rsp+38h+arg_8]
0x18002860e  add     rsp, 30h
0x180028612  pop     rdi
0x180028613  retn
0x180028614  mov     ecx, 3
0x180028619  int     29h; Win8: RtlFailFast(ecx)
```
