# IPM2_MESSAGE_PIPE::IpmMessageDeleted(IPM2_MESSAGE_IMP *)

- ea: `0x18002a370`
- end: `0x18002a41c`
- name: `?IpmMessageDeleted@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z`
- size: `172`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, struct IPM2_MESSAGE_IMP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002900c`

## callees

- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x18002a370`

## string_xrefs

- `0x18002a3f8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a3db`: `IPM2_MESSAGE_PIPE::IpmMessageDeleted m_cMessages = %d\n`
- `0x18002a3e6`: `IPM2_MESSAGE_PIPE::IpmMessageDeleted`

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
0x18002a370  mov     [rsp+arg_0], rbx
0x18002a375  mov     [rsp+arg_8], rsi
0x18002a37a  push    rdi
0x18002a37b  sub     rsp, 30h
0x18002a37f  mov     rdi, rcx
0x18002a382  mov     rbx, rdx
0x18002a385  add     rcx, 18h; this
0x18002a389  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002a38e  add     rbx, 58h ; 'X'
0x18002a392  mov     rdx, [rbx]
0x18002a395  cmp     [rdx+8], rbx
0x18002a399  jnz     short loc_18002A415
0x18002a39b  mov     rax, [rbx+8]
0x18002a39f  cmp     [rax], rbx
0x18002a3a2  jnz     short loc_18002A415
0x18002a3a4  mov     [rax], rdx
0x18002a3a7  or      ebx, 0FFFFFFFFh
0x18002a3aa  mov     [rdx+8], rax
0x18002a3ae  lock xadd [rdi+34h], ebx
0x18002a3b3  lea     rcx, [rdi+18h]; this
0x18002a3b7  dec     ebx
0x18002a3b9  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002a3be  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a3c4  test    al, 3
0x18002a3c6  setnz   cl
0x18002a3c9  bt      eax, 1Ch
0x18002a3cd  setb    al
0x18002a3d0  test    al, cl
0x18002a3d2  jz      short loc_18002A404
0x18002a3d4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a3db  lea     rax, aIpm2MessagePip_2; "IPM2_MESSAGE_PIPE::IpmMessageDeleted m_"...
0x18002a3e2  mov     dword ptr [rsp+38h+var_10], ebx; char
0x18002a3e6  lea     r9, aIpm2MessagePip_25; "IPM2_MESSAGE_PIPE::IpmMessageDeleted"
0x18002a3ed  mov     r8d, 274h; unsigned int
0x18002a3f3  mov     [rsp+38h+var_18], rax; char *
0x18002a3f8  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a3ff  call    PuDbgPrint
0x18002a404  mov     rbx, [rsp+38h+arg_0]
0x18002a409  mov     rsi, [rsp+38h+arg_8]
0x18002a40e  add     rsp, 30h
0x18002a412  pop     rdi
0x18002a413  retn
0x18002a415  mov     ecx, 3
0x18002a41a  int     29h; Win8: RtlFailFast(ecx)
```
