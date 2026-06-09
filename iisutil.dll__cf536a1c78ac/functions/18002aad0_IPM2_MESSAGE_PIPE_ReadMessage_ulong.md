# IPM2_MESSAGE_PIPE::ReadMessage(ulong)

- ea: `0x18002aad0`
- end: `0x18002acd2`
- name: `?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z`
- size: `514`
- prototype: `__int64 __fastcall(HANDLE *this, DWORD nNumberOfBytesToRead)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800291f0`
- `0x18002a430`
- `0x18002ad80`

## callees

- `0x180005aa0`
- `0x180008000`
- `0x18000f810`
- `0x180014288`
- `0x180016f20`
- `0x180029644`
- `0x180029c0c`
- `0x18002aad0`
- `0x18002f010`

## string_xrefs

- `0x18002ab21`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002ab71`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002abca`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002ac7f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002ab0f`: `IPM2_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x18002ab1a`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x18002ab66`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x18002abbf`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x18002ac6d`: `IPM2_MESSAGE_PIPE::ReadMessage`
- `0x18002ab78`: `IPM2_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x18002abdb`: `IPM2_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`
- `0x18002ac62`: `IPM2_MESSAGE_PIPE::ReadMessage failed Ipm2ReadFile, hr = %x\n`

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
0x18002aad0  mov     r11, rsp
0x18002aad3  mov     [r11+8], rbx
0x18002aad7  mov     [r11+10h], rbp
0x18002aadb  push    rsi
0x18002aadc  push    rdi
0x18002aadd  push    r14
0x18002aadf  sub     rsp, 40h
0x18002aae3  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002aae9  mov     ebp, edx
0x18002aaeb  test    al, 3
0x18002aaed  mov     qword ptr [r11+18h], 0
0x18002aaf5  mov     rsi, rcx
0x18002aaf8  setnz   r8b
0x18002aafc  bt      eax, 1Ch
0x18002ab00  setb    al
0x18002ab03  test    al, r8b
0x18002ab06  jz      short loc_18002AB37
0x18002ab08  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002ab0f  lea     rax, aIpm2MessagePip_17; "IPM2_MESSAGE_PIPE::ReadMessage called w"...
0x18002ab16  mov     dword ptr [rsp+58h+var_30], edx; char
0x18002ab1a  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x18002ab21  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002ab28  mov     [r11-38h], rax
0x18002ab2c  mov     r8d, 556h; unsigned int
0x18002ab32  call    PuDbgPrint
0x18002ab37  xor     r8d, r8d; int
0x18002ab3a  lea     rcx, [rsp+58h+arg_10]; struct IPM2_MESSAGE_IMP **
0x18002ab3f  mov     rdx, rsi; struct IPM2_MESSAGE_PIPE *
0x18002ab42  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x18002ab47  mov     rdi, [rsp+58h+arg_10]
0x18002ab4c  mov     ebx, eax
0x18002ab4e  test    eax, eax
0x18002ab50  jns     short loc_18002AB94
0x18002ab52  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002ab59  jz      loc_18002AC9A
0x18002ab5f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002ab66  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x18002ab6d  mov     dword ptr [rsp+58h+var_30], eax; char
0x18002ab71  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002ab78  lea     rax, aIpm2MessagePip_5; "IPM2_MESSAGE_PIPE::ReadMessage failed C"...
0x18002ab7f  mov     r8d, 55Fh; unsigned int
0x18002ab85  mov     [rsp+58h+var_38], rax; char *
0x18002ab8a  call    PuDbgPrint
0x18002ab8f  jmp     loc_18002AC9A
0x18002ab94  mov     edx, ebp; unsigned int
0x18002ab96  mov     dword ptr [rdi+0Ch], 0
0x18002ab9d  mov     rcx, rdi; this
0x18002aba0  call    ?AllocateDataLength@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::AllocateDataLength(ulong)
0x18002aba5  mov     ebx, eax
0x18002aba7  test    eax, eax
0x18002aba9  jns     short loc_18002ABF1
0x18002abab  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002abb2  jz      loc_18002AC9A
0x18002abb8  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002abbf  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x18002abc6  mov     [rsp+58h+var_28], ebp
0x18002abca  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002abd1  mov     dword ptr [rsp+58h+var_30], eax; char
0x18002abd5  mov     r8d, 56Ch; unsigned int
0x18002abdb  lea     rax, aIpm2MessagePip_9; "IPM2_MESSAGE_PIPE::ReadMessage failed a"...
0x18002abe2  mov     [rsp+58h+var_38], rax; char *
0x18002abe7  call    PuDbgPrint
0x18002abec  jmp     loc_18002AC9A
0x18002abf1  lea     r14, [rsi+8]
0x18002abf5  mov     rcx, r14; this
0x18002abf8  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18002abfd  cmp     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18002ac02  jnz     short loc_18002AC16
0x18002ac04  mov     rcx, r14; this
0x18002ac07  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002ac0c  mov     ebx, 8007006Dh
0x18002ac11  jmp     loc_18002AC9A
0x18002ac16  mov     rax, [rdi]
0x18002ac19  mov     rcx, rdi
0x18002ac1c  mov     rax, [rax]
0x18002ac1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac24  mov     rdx, [rdi+18h]; lpBuffer
0x18002ac28  lea     r9, [rdi+38h]; lpOverlapped
0x18002ac2c  mov     rcx, [rsi+20h]; hFile
0x18002ac30  mov     r8d, ebp; nNumberOfBytesToRead
0x18002ac33  call    ?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)
0x18002ac38  mov     rcx, r14; this
0x18002ac3b  mov     ebx, eax
0x18002ac3d  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002ac42  test    ebx, ebx
0x18002ac44  jns     short loc_18002AC9A
0x18002ac46  cmp     ebx, 800703E5h
0x18002ac4c  jnz     short loc_18002AC52
0x18002ac4e  xor     ebx, ebx
0x18002ac50  jmp     short loc_18002AC9A
0x18002ac52  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002ac59  jz      short loc_18002AC8B
0x18002ac5b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002ac62  lea     rax, aIpm2MessagePip_29; "IPM2_MESSAGE_PIPE::ReadMessage failed I"...
0x18002ac69  mov     dword ptr [rsp+58h+var_30], ebx; char
0x18002ac6d  lea     r9, aIpm2MessagePip_11; "IPM2_MESSAGE_PIPE::ReadMessage"
0x18002ac74  mov     r8d, 590h; unsigned int
0x18002ac7a  mov     [rsp+58h+var_38], rax; char *
0x18002ac7f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002ac86  call    PuDbgPrint
0x18002ac8b  mov     rax, [rdi]
0x18002ac8e  mov     rcx, rdi
0x18002ac91  mov     rax, [rax+8]
0x18002ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac9a  test    rdi, rdi
0x18002ac9d  jz      short loc_18002ACAE
0x18002ac9f  mov     rax, [rdi]
0x18002aca2  mov     rcx, rdi
0x18002aca5  mov     rax, [rax+8]
0x18002aca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acae  test    ebx, ebx
0x18002acb0  jns     short loc_18002ACBC
0x18002acb2  mov     edx, ebx; int
0x18002acb4  mov     rcx, rsi; this
0x18002acb7  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x18002acbc  mov     rbp, [rsp+58h+arg_8]
0x18002acc1  mov     eax, ebx
0x18002acc3  mov     rbx, [rsp+58h+arg_0]
0x18002acc8  add     rsp, 40h
0x18002accc  pop     r14
0x18002acce  pop     rdi
0x18002accf  pop     rsi
0x18002acd0  retn
```
