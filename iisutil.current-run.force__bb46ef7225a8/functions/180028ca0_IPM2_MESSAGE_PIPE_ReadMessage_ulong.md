# IPM2_MESSAGE_PIPE::ReadMessage(ulong)

- ea: `0x180028ca0`
- end: `0x180028ea1`
- name: `?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z`
- size: `513`
- prototype: `__int64 __fastcall(IPM2_MESSAGE_PIPE *__hidden this, DWORD nNumberOfBytesToRead)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027520`
- `0x180028630`
- `0x180028f50`

## callees

- `0x180004f40`
- `0x180007300`
- `0x18000e850`
- `0x18001382c`
- `0x180016330`
- `0x180027934`
- `0x180027e9c`
- `0x180028ca0`
- `0x18002d010`

## string_xrefs

- `0x180028cf1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028d41`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028d9a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028e4f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028cdf`: `IPM2_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x180028cea`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x180028d36`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x180028d8f`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x180028e3d`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x180028d48`: `IPM2_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x180028dab`: `IPM2_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`
- `0x180028e32`: `IPM2_MESSAGE_PIPE::ReadMessage failed Ipm2ReadFile, hr = %x\n`

## pseudocode

```c
__int64 __fastcall IPM2_MESSAGE_PIPE::ReadMessage(HANDLE *this, DWORD nNumberOfBytesToRead)
{
  int v4; // eax
  IPM2_MESSAGE_IMP *v5; // rdi
  int File; // ebx
  int DataLength; // eax
  IPM2_MESSAGE_IMP *v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x556u,
      "IPM2_MESSAGE_PIPE::ReadMessage",
      "IPM2_MESSAGE_PIPE::ReadMessage called with size=%d\n",
      nNumberOfBytesToRead);
  v4 = IPM2_MESSAGE_IMP::CreateMessage(&v9, (struct IPM2_MESSAGE_PIPE *)this, 0);
  v5 = v9;
  File = v4;
  if ( v4 >= 0 )
  {
    *((_DWORD *)v9 + 3) = 0;
    DataLength = IPM2_MESSAGE_IMP::AllocateDataLength(v5, nNumberOfBytesToRead);
    File = DataLength;
    if ( DataLength >= 0 )
    {
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(this + 1));
      if ( this[4] == (HANDLE)-1LL )
      {
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(this + 1));
        File = -2147024787;
      }
      else
      {
        (**(void (__fastcall ***)(IPM2_MESSAGE_IMP *))v5)(v5);
        File = Ipm2ReadFile(this[4], *((void **)v5 + 3), nNumberOfBytesToRead, (LPOVERLAPPED)((char *)v5 + 56));
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(this + 1));
        if ( File < 0 )
        {
          if ( File == -2147023899 )
          {
            File = 0;
          }
          else
          {
            if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
              PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
                0x590u,
                "IPM2_MESSAGE_PIPE::ReadMessage",
                "IPM2_MESSAGE_PIPE::ReadMessage failed Ipm2ReadFile, hr = %x\n",
                File);
            (*(void (__fastcall **)(IPM2_MESSAGE_IMP *))(*(_QWORD *)v5 + 8LL))(v5);
          }
        }
      }
    }
    else if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x56Cu,
        "IPM2_MESSAGE_PIPE::ReadMessage",
        "IPM2_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n",
        DataLength);
    }
  }
  else if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
  {
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x55Fu,
      "IPM2_MESSAGE_PIPE::ReadMessage",
      "IPM2_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n",
      v4);
  }
  if ( v5 )
    (*(void (__fastcall **)(IPM2_MESSAGE_IMP *))(*(_QWORD *)v5 + 8LL))(v5);
  if ( File < 0 )
    IPM2_MESSAGE_PIPE::NotifyPipeDisconnected((IPM2_MESSAGE_PIPE *)this, File);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x180028ca0  mov     r11, rsp
0x180028ca3  mov     [r11+8], rbx
0x180028ca7  mov     [r11+10h], rbp
0x180028cab  push    rsi
0x180028cac  push    rdi
0x180028cad  push    r14
0x180028caf  sub     rsp, 40h
0x180028cb3  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180028cb9  mov     ebp, edx
0x180028cbb  test    al, 3
0x180028cbd  mov     qword ptr [r11+18h], 0
0x180028cc5  mov     rsi, rcx
0x180028cc8  setnz   r8b
0x180028ccc  bt      eax, 1Ch
0x180028cd0  setb    al
0x180028cd3  test    al, r8b
0x180028cd6  jz      short loc_180028D07
0x180028cd8  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028cdf  lea     rax, aIpm2MessagePip_17; "IPM2_MESSAGE_PIPE::ReadMessage called w"...
0x180028ce6  mov     dword ptr [rsp+58h+var_30], edx; char
0x180028cea  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x180028cf1  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028cf8  mov     [r11-38h], rax
0x180028cfc  mov     r8d, 556h; unsigned int
0x180028d02  call    PuDbgPrint
0x180028d07  xor     r8d, r8d; int
0x180028d0a  lea     rcx, [rsp+58h+arg_10]; struct IPM2_MESSAGE_IMP **
0x180028d0f  mov     rdx, rsi; struct IPM2_MESSAGE_PIPE *
0x180028d12  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x180028d17  mov     rdi, [rsp+58h+arg_10]
0x180028d1c  mov     ebx, eax
0x180028d1e  test    eax, eax
0x180028d20  jns     short loc_180028D64
0x180028d22  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028d29  jz      loc_180028E6A
0x180028d2f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028d36  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x180028d3d  mov     dword ptr [rsp+58h+var_30], eax; char
0x180028d41  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028d48  lea     rax, aIpm2MessagePip_5; "IPM2_MESSAGE_PIPE::ReadMessage failed C"...
0x180028d4f  mov     r8d, 55Fh; unsigned int
0x180028d55  mov     [rsp+58h+var_38], rax; char *
0x180028d5a  call    PuDbgPrint
0x180028d5f  jmp     loc_180028E6A
0x180028d64  mov     edx, ebp; unsigned int
0x180028d66  mov     dword ptr [rdi+0Ch], 0
0x180028d6d  mov     rcx, rdi; this
0x180028d70  call    ?AllocateDataLength@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::AllocateDataLength(ulong)
0x180028d75  mov     ebx, eax
0x180028d77  test    eax, eax
0x180028d79  jns     short loc_180028DC1
0x180028d7b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028d82  jz      loc_180028E6A
0x180028d88  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028d8f  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x180028d96  mov     [rsp+58h+var_28], ebp
0x180028d9a  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028da1  mov     dword ptr [rsp+58h+var_30], eax; char
0x180028da5  mov     r8d, 56Ch; unsigned int
0x180028dab  lea     rax, aIpm2MessagePip_9; "IPM2_MESSAGE_PIPE::ReadMessage failed a"...
0x180028db2  mov     [rsp+58h+var_38], rax; char *
0x180028db7  call    PuDbgPrint
0x180028dbc  jmp     loc_180028E6A
0x180028dc1  lea     r14, [rsi+8]
0x180028dc5  mov     rcx, r14; this
0x180028dc8  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180028dcd  cmp     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x180028dd2  jnz     short loc_180028DE6
0x180028dd4  mov     rcx, r14; this
0x180028dd7  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180028ddc  mov     ebx, 8007006Dh
0x180028de1  jmp     loc_180028E6A
0x180028de6  mov     rax, [rdi]
0x180028de9  mov     rcx, rdi
0x180028dec  mov     rax, [rax]
0x180028def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028df4  mov     rdx, [rdi+18h]; lpBuffer
0x180028df8  lea     r9, [rdi+38h]; lpOverlapped
0x180028dfc  mov     rcx, [rsi+20h]; hFile
0x180028e00  mov     r8d, ebp; nNumberOfBytesToRead
0x180028e03  call    ?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)
0x180028e08  mov     rcx, r14; this
0x180028e0b  mov     ebx, eax
0x180028e0d  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180028e12  test    ebx, ebx
0x180028e14  jns     short loc_180028E6A
0x180028e16  cmp     ebx, 800703E5h
0x180028e1c  jnz     short loc_180028E22
0x180028e1e  xor     ebx, ebx
0x180028e20  jmp     short loc_180028E6A
0x180028e22  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028e29  jz      short loc_180028E5B
0x180028e2b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028e32  lea     rax, aIpm2MessagePip_29; "IPM2_MESSAGE_PIPE::ReadMessage failed I"...
0x180028e39  mov     dword ptr [rsp+58h+var_30], ebx; char
0x180028e3d  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x180028e44  mov     r8d, 590h; unsigned int
0x180028e4a  mov     [rsp+58h+var_38], rax; char *
0x180028e4f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028e56  call    PuDbgPrint
0x180028e5b  mov     rax, [rdi]
0x180028e5e  mov     rcx, rdi
0x180028e61  mov     rax, [rax+8]
0x180028e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e6a  test    rdi, rdi
0x180028e6d  jz      short loc_180028E7E
0x180028e6f  mov     rax, [rdi]
0x180028e72  mov     rcx, rdi
0x180028e75  mov     rax, [rax+8]
0x180028e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e7e  test    ebx, ebx
0x180028e80  jns     short loc_180028E8C
0x180028e82  mov     edx, ebx; int
0x180028e84  mov     rcx, rsi; this
0x180028e87  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180028e8c  mov     rbp, [rsp+58h+arg_8]
0x180028e91  mov     eax, ebx
0x180028e93  mov     rbx, [rsp+58h+arg_0]
0x180028e98  add     rsp, 40h
0x180028e9c  pop     r14
0x180028e9e  pop     rdi
0x180028e9f  pop     rsi
0x180028ea0  retn
```
