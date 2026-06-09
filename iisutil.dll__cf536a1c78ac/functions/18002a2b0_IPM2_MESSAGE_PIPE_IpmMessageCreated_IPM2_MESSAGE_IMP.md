# IPM2_MESSAGE_PIPE::IpmMessageCreated(IPM2_MESSAGE_IMP *)

- ea: `0x18002a2b0`
- end: `0x18002a360`
- name: `?IpmMessageCreated@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z`
- size: `176`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, struct IPM2_MESSAGE_IMP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180029644`

## callees

- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x18002a2b0`

## string_xrefs

- `0x18002a343`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a326`: `IPM2_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x18002a331`: `IPM2_MESSAGE_PIPE::IpmMessageCreated`

## pseudocode

```c
void __fastcall IPM2_MESSAGE_PIPE::IpmMessageCreated(IPM2_MESSAGE_PIPE *this, struct IPM2_MESSAGE_IMP *a2)
{
  IPM2_MESSAGE_PIPE **v4; // r8
  char v5; // di

  CReaderWriterLock3::WriteLock((IPM2_MESSAGE_PIPE *)((char *)this + 24));
  v4 = (IPM2_MESSAGE_PIPE **)*((_QWORD *)this + 8);
  if ( *v4 != (IPM2_MESSAGE_PIPE *)((char *)this + 56) )
    __fastfail(3u);
  *((_QWORD *)a2 + 11) = (char *)this + 56;
  *((_QWORD *)a2 + 12) = v4;
  *v4 = (struct IPM2_MESSAGE_IMP *)((char *)a2 + 88);
  *((_QWORD *)this + 8) = (char *)a2 + 88;
  v5 = _InterlockedIncrement((volatile signed __int32 *)this + 13);
  CReaderWriterLock3::WriteUnlock((IPM2_MESSAGE_PIPE *)((char *)this + 24));
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x252u,
      "IPM2_MESSAGE_PIPE::IpmMessageCreated",
      "IPM2_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n",
      v5);
}

```

## disassembly

```asm
0x18002a2b0  mov     [rsp+arg_0], rbx
0x18002a2b5  mov     [rsp+arg_8], rsi
0x18002a2ba  push    rdi
0x18002a2bb  sub     rsp, 30h
0x18002a2bf  mov     rbx, rcx
0x18002a2c2  mov     rdi, rdx
0x18002a2c5  add     rcx, 18h; this
0x18002a2c9  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002a2ce  lea     rcx, [rbx+38h]
0x18002a2d2  mov     r8, [rcx+8]
0x18002a2d6  cmp     [r8], rcx
0x18002a2d9  jz      short loc_18002A2E2
0x18002a2db  mov     ecx, 3
0x18002a2e0  int     29h; Win8: RtlFailFast(ecx)
0x18002a2e2  lea     rax, [rdi+58h]
0x18002a2e6  mov     edi, 1
0x18002a2eb  mov     [rax], rcx
0x18002a2ee  mov     [rax+8], r8
0x18002a2f2  mov     [r8], rax
0x18002a2f5  mov     [rcx+8], rax
0x18002a2f9  lock xadd [rbx+34h], edi
0x18002a2fe  lea     rcx, [rbx+18h]; this
0x18002a302  inc     edi
0x18002a304  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002a309  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a30f  test    al, 3
0x18002a311  setnz   cl
0x18002a314  bt      eax, 1Ch
0x18002a318  setb    al
0x18002a31b  test    al, cl
0x18002a31d  jz      short loc_18002A34F
0x18002a31f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a326  lea     rax, aIpm2MessagePip_21; "IPM2_MESSAGE_PIPE::IpmMessageCreated m_"...
0x18002a32d  mov     dword ptr [rsp+38h+var_10], edi; char
0x18002a331  lea     r9, aIpm2MessagePip_23; "IPM2_MESSAGE_PIPE::IpmMessageCreated"
0x18002a338  mov     r8d, 252h; unsigned int
0x18002a33e  mov     [rsp+38h+var_18], rax; char *
0x18002a343  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a34a  call    PuDbgPrint
0x18002a34f  mov     rbx, [rsp+38h+arg_0]
0x18002a354  mov     rsi, [rsp+38h+arg_8]
0x18002a359  add     rsp, 30h
0x18002a35d  pop     rdi
0x18002a35e  retn
```
