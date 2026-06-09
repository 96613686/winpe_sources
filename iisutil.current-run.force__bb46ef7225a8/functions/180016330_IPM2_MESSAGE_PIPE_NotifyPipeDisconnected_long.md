# IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)

- ea: `0x180016330`
- end: `0x18001641d`
- name: `?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z`
- size: `237`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180027bb0`
- `0x180028630`
- `0x180028ca0`
- `0x180029130`

## callees

- `0x180007300`
- `0x180016330`
- `0x180016430`
- `0x180028f50`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016390`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18001637f`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18001637f`

## string_xrefs

- `0x1800163f9`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

## pseudocode

```c
void __fastcall IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(IPM2_MESSAGE_PIPE *this, int a2)
{
  bool v2; // zf
  IPM2_MESSAGE_PIPE *v3; // rbx
  __int64 v4; // rcx
  signed int LastError; // eax
  int v6; // eax
  int v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 20) == 0;
  v3 = this;
  v7 = 0;
  if ( v2 || *((_DWORD *)this + 22) == 4 )
    goto LABEL_12;
  if ( _InterlockedExchange((volatile __int32 *)this + 22, 3) == 2 )
  {
    v4 = *((_QWORD *)this + 5);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( *((_DWORD *)v3 + 12) && *((_DWORD *)v3 + 20) == 1 )
    {
      if ( DisconnectNamedPipe(*((HANDLE *)v3 + 4)) && (int)IPM2_MESSAGE_PIPE::StartNamedPipe(v3, &v7) >= 0 )
      {
        if ( v7 )
        {
          v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 5) + 8LL))(*((_QWORD *)v3 + 5));
          if ( v6 < 0 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x455u,
              "IPM2_MESSAGE_PIPE::NotifyPipeDisconnected",
              "IPM2_MESSAGE_PIPE::NotifyPipeDisconnected m_pAcceptor->PipeConnected failed hr=0x%08x\n",
              v6);
        }
        return;
      }
      *((_DWORD *)v3 + 21) = 1;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      a2 = LastError;
      this = v3;
LABEL_12:
      IPM2_MESSAGE_PIPE::LegacyPipeDisconnected(this, a2);
    }
  }
}

```

## disassembly

```asm
0x180016330  push    rbx
0x180016332  sub     rsp, 30h
0x180016336  cmp     dword ptr [rcx+50h], 0
0x18001633a  mov     rbx, rcx
0x18001633d  mov     [rsp+38h+arg_0], 0
0x180016345  jz      short loc_1800163A7
0x180016347  cmp     dword ptr [rcx+58h], 4
0x18001634b  jz      short loc_1800163A7
0x18001634d  mov     eax, 3
0x180016352  xchg    eax, [rcx+58h]
0x180016355  cmp     eax, 2
0x180016358  jnz     short loc_1800163AC
0x18001635a  mov     rcx, [rcx+28h]
0x18001635e  test    rcx, rcx
0x180016361  jz      short loc_18001636F
0x180016363  mov     rax, [rcx]
0x180016366  mov     rax, [rax+10h]
0x18001636a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001636f  cmp     dword ptr [rbx+30h], 0
0x180016373  jz      short loc_1800163AC
0x180016375  cmp     dword ptr [rbx+50h], 1
0x180016379  jnz     short loc_1800163AC
0x18001637b  mov     rcx, [rbx+20h]; hNamedPipe
0x18001637f  call    cs:__imp_DisconnectNamedPipe
0x180016385  test    eax, eax
0x180016387  jnz     short loc_1800163B2
0x180016389  mov     dword ptr [rbx+54h], 1
0x180016390  call    cs:__imp_GetLastError
0x180016396  test    eax, eax
0x180016398  jle     short loc_1800163A2
0x18001639a  movzx   eax, ax
0x18001639d  or      eax, 80070000h
0x1800163a2  mov     edx, eax; int
0x1800163a4  mov     rcx, rbx; this
0x1800163a7  call    ?LegacyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::LegacyPipeDisconnected(long)
0x1800163ac  add     rsp, 30h
0x1800163b0  pop     rbx
0x1800163b1  retn
0x1800163b2  lea     rdx, [rsp+38h+arg_0]; int *
0x1800163b7  mov     rcx, rbx; this
0x1800163ba  call    ?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z; IPM2_MESSAGE_PIPE::StartNamedPipe(int *)
0x1800163bf  test    eax, eax
0x1800163c1  js      short loc_180016389
0x1800163c3  cmp     [rsp+38h+arg_0], 0
0x1800163c8  jz      short loc_1800163AC
0x1800163ca  mov     rcx, [rbx+28h]
0x1800163ce  mov     rax, [rcx]
0x1800163d1  mov     rax, [rax+8]
0x1800163d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163da  test    eax, eax
0x1800163dc  jns     short loc_1800163AC
0x1800163de  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800163e5  jz      short loc_1800163AC
0x1800163e7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800163ee  lea     r9, aIpm2MessagePip_19; "IPM2_MESSAGE_PIPE::NotifyPipeDisconnect"...
0x1800163f5  mov     dword ptr [rsp+38h+var_10], eax; char
0x1800163f9  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016400  lea     rax, aIpm2MessagePip_40; "IPM2_MESSAGE_PIPE::NotifyPipeDisconnect"...
0x180016407  mov     r8d, 455h; unsigned int
0x18001640d  mov     [rsp+38h+var_18], rax; char *
0x180016412  call    PuDbgPrint
0x180016417  add     rsp, 30h
0x18001641b  pop     rbx
0x18001641c  retn
```
