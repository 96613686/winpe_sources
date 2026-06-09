# IPM2_MESSAGE_PIPE::IpmMessageCreated(IPM2_MESSAGE_IMP *)

- ea: `0x1800284b0`
- end: `0x18002855f`
- name: `?IpmMessageCreated@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z`
- size: `175`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, struct IPM2_MESSAGE_IMP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027934`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x1800284b0`

## string_xrefs

- `0x180028543`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028526`: `IPM2_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x180028531`: `IPM2_MESSAGE_PIPE::IpmMessageCreated`

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
0x1800284b0  mov     [rsp+arg_0], rbx
0x1800284b5  mov     [rsp+arg_8], rsi
0x1800284ba  push    rdi
0x1800284bb  sub     rsp, 30h
0x1800284bf  mov     rbx, rcx
0x1800284c2  mov     rdi, rdx
0x1800284c5  add     rcx, 18h; this
0x1800284c9  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800284ce  lea     rcx, [rbx+38h]
0x1800284d2  mov     r8, [rcx+8]
0x1800284d6  cmp     [r8], rcx
0x1800284d9  jz      short loc_1800284E2
0x1800284db  mov     ecx, 3
0x1800284e0  int     29h; Win8: RtlFailFast(ecx)
0x1800284e2  lea     rax, [rdi+58h]
0x1800284e6  mov     edi, 1
0x1800284eb  mov     [rax], rcx
0x1800284ee  mov     [rax+8], r8
0x1800284f2  mov     [r8], rax
0x1800284f5  mov     [rcx+8], rax
0x1800284f9  lock xadd [rbx+34h], edi
0x1800284fe  lea     rcx, [rbx+18h]; this
0x180028502  inc     edi
0x180028504  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180028509  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002850f  test    al, 3
0x180028511  setnz   cl
0x180028514  bt      eax, 1Ch
0x180028518  setb    al
0x18002851b  test    al, cl
0x18002851d  jz      short loc_18002854F
0x18002851f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028526  lea     rax, aIpm2MessagePip_21; "IPM2_MESSAGE_PIPE::IpmMessageCreated m_"...
0x18002852d  mov     dword ptr [rsp+38h+var_10], edi; char
0x180028531  lea     r9, aIpm2MessagePip_23; "IPM2_MESSAGE_PIPE::IpmMessageCreated"
0x180028538  mov     r8d, 252h; unsigned int
0x18002853e  mov     [rsp+38h+var_18], rax; char *
0x180028543  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002854a  call    PuDbgPrint
0x18002854f  mov     rbx, [rsp+38h+arg_0]
0x180028554  mov     rsi, [rsp+38h+arg_8]
0x180028559  add     rsp, 30h
0x18002855d  pop     rdi
0x18002855e  retn
```
