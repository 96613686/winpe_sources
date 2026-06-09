# IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)

- ea: `0x180016f20`
- end: `0x18001701b`
- name: `?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z`
- size: `251`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800298e0`
- `0x18002a430`
- `0x18002aad0`
- `0x18002af70`

## callees

- `0x180008000`
- `0x180016f20`
- `0x180017030`
- `0x18002ad80`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f86`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180016f6f`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180016f6f`

## string_xrefs

- `0x180016ff6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

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
0x180016f20  push    rbx
0x180016f22  sub     rsp, 30h
0x180016f26  cmp     dword ptr [rcx+50h], 0
0x180016f2a  mov     rbx, rcx
0x180016f2d  mov     [rsp+38h+arg_0], 0
0x180016f35  jz      short loc_180016FA3
0x180016f37  cmp     dword ptr [rcx+58h], 4
0x180016f3b  jz      short loc_180016FA3
0x180016f3d  mov     eax, 3
0x180016f42  xchg    eax, [rcx+58h]
0x180016f45  cmp     eax, 2
0x180016f48  jnz     short loc_180016FA8
0x180016f4a  mov     rcx, [rcx+28h]
0x180016f4e  test    rcx, rcx
0x180016f51  jz      short loc_180016F5F
0x180016f53  mov     rax, [rcx]
0x180016f56  mov     rax, [rax+10h]
0x180016f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f5f  cmp     dword ptr [rbx+30h], 0
0x180016f63  jz      short loc_180016FA8
0x180016f65  cmp     dword ptr [rbx+50h], 1
0x180016f69  jnz     short loc_180016FA8
0x180016f6b  mov     rcx, [rbx+20h]; hNamedPipe
0x180016f6f  call    cs:__imp_DisconnectNamedPipe
0x180016f76  nop     dword ptr [rax+rax+00h]
0x180016f7b  test    eax, eax
0x180016f7d  jnz     short loc_180016FAF
0x180016f7f  mov     dword ptr [rbx+54h], 1
0x180016f86  call    cs:__imp_GetLastError
0x180016f8d  nop     dword ptr [rax+rax+00h]
0x180016f92  test    eax, eax
0x180016f94  jle     short loc_180016F9E
0x180016f96  movzx   eax, ax
0x180016f99  or      eax, 80070000h
0x180016f9e  mov     edx, eax; int
0x180016fa0  mov     rcx, rbx; this
0x180016fa3  call    ?LegacyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::LegacyPipeDisconnected(long)
0x180016fa8  add     rsp, 30h
0x180016fac  pop     rbx
0x180016fad  retn
0x180016faf  lea     rdx, [rsp+38h+arg_0]; int *
0x180016fb4  mov     rcx, rbx; this
0x180016fb7  call    ?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z; IPM2_MESSAGE_PIPE::StartNamedPipe(int *)
0x180016fbc  test    eax, eax
0x180016fbe  js      short loc_180016F7F
0x180016fc0  cmp     [rsp+38h+arg_0], 0
0x180016fc5  jz      short loc_180016FA8
0x180016fc7  mov     rcx, [rbx+28h]
0x180016fcb  mov     rax, [rcx]
0x180016fce  mov     rax, [rax+8]
0x180016fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fd7  test    eax, eax
0x180016fd9  jns     short loc_180016FA8
0x180016fdb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016fe2  jz      short loc_180016FA8
0x180016fe4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016feb  lea     r9, aIpm2MessagePip_19; "IPM2_MESSAGE_PIPE::NotifyPipeDisconnect"...
0x180016ff2  mov     dword ptr [rsp+38h+var_10], eax; char
0x180016ff6  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016ffd  lea     rax, aIpm2MessagePip_40; "IPM2_MESSAGE_PIPE::NotifyPipeDisconnect"...
0x180017004  mov     r8d, 455h; unsigned int
0x18001700a  mov     [rsp+38h+var_18], rax; char *
0x18001700f  call    PuDbgPrint
0x180017014  add     rsp, 30h
0x180017018  pop     rbx
0x180017019  retn
```
