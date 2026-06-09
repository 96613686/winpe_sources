# IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)

- ea: `0x180005d00`
- end: `0x180005f5a`
- name: `?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z`
- size: `602`
- prototype: `__int64 __fastcall(struct IPM_MESSAGE_IMP **, struct IPM_MESSAGE_PIPE *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004490`
- `0x180005f60`
- `0x180006730`
- `0x180011210`

## callees

- `0x180005c80`
- `0x180005d00`
- `0x180008000`
- `0x180008f20`
- `0x18000f350`
- `0x180019230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005e95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005e95`
- `api-ms-win-core-threadpool-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005ec7`
- `api-ms-win-core-threadpool-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180005ec7`

## string_xrefs

- `0x180005e4a`: `IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x180005e56`: `IPM_MESSAGE_PIPE::IpmMessageCreated`
- `0x180005db5`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005e68`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005f44`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005d98`: `IPM_MESSAGE_PIPE::CreateMessage failed allocation of IPM_MESSAGE_IMP, hr = %x\n`
- `0x180005da3`: `IPM_MESSAGE_IMP::CreateMessage`
- `0x180005f39`: `IPM_MESSAGE_IMP::CreateMessage`
- `0x180005f16`: `IPM_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n`
- `0x180005f25`: `IPM_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n`

## pseudocode

```c
__int64 __fastcall IPM_MESSAGE_IMP::CreateMessage(struct IPM_MESSAGE_IMP **a1, struct IPM_MESSAGE_PIPE *a2, int a3)
{
  char *v6; // rdi
  struct IPM_MESSAGE_PIPE **v7; // rdx
  unsigned int v8; // ebx
  signed int LastError; // eax
  unsigned int v10; // edx
  char v12; // r15
  HANDLE EventW; // rax
  __int64 v14; // rax
  signed int v15; // eax
  char *v16; // rax
  unsigned int v17; // r8d

  *a1 = 0;
  v6 = (char *)operator new(0x70u);
  if ( v6 )
  {
    *((_DWORD *)v6 + 4) = 0;
    *(_QWORD *)v6 = &IPM_MESSAGE_IMP::`vftable';
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = a2;
    *((_QWORD *)v6 + 5) = 0;
    *((_DWORD *)v6 + 12) = 0;
    *((_DWORD *)v6 + 26) = 0;
    CReaderWriterLock3::WriteLock((struct IPM_MESSAGE_PIPE *)((char *)a2 + 8));
    v7 = (struct IPM_MESSAGE_PIPE **)*((_QWORD *)a2 + 6);
    if ( *v7 != (struct IPM_MESSAGE_PIPE *)((char *)a2 + 40) )
      __fastfail(3u);
    *((_QWORD *)v6 + 11) = (char *)a2 + 40;
    *((_QWORD *)v6 + 12) = v7;
    *v7 = (struct IPM_MESSAGE_PIPE *)(v6 + 88);
    *((_QWORD *)a2 + 6) = v6 + 88;
    v12 = _InterlockedIncrement((volatile signed __int32 *)a2 + 9);
    CReaderWriterLock3::WriteUnlock((struct IPM_MESSAGE_PIPE *)((char *)a2 + 8));
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x2EBu,
        "IPM_MESSAGE_PIPE::IpmMessageCreated",
        "IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n",
        v12);
    *(_OWORD *)(v6 + 56) = 0;
    *(_OWORD *)(v6 + 72) = 0;
    *((_DWORD *)v6 + 2) = 1347242317;
    *((_DWORD *)v6 + 26) = a3;
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW )
    {
      *((_QWORD *)v6 + 10) = EventW;
      if ( a3 )
      {
LABEL_17:
        v8 = 0;
        _InterlockedIncrement((volatile signed __int32 *)v6 + 12);
        *a1 = (struct IPM_MESSAGE_IMP *)v6;
        return v8;
      }
      v14 = RegisterWaitForSingleObjectEx(EventW, IPM_MESSAGE_PIPE::MessagePipeCompletion, v6, 0xFFFFFFFFLL, 8);
      if ( v14 )
      {
        *((_QWORD *)v6 + 5) = v14;
        goto LABEL_17;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
        goto LABEL_9;
      v16 = "IPM_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n";
      v17 = 1672;
    }
    else
    {
      v15 = GetLastError();
      v8 = v15;
      if ( v15 > 0 )
        v8 = (unsigned __int16)v15 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
        goto LABEL_9;
      v16 = "IPM_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n";
      v17 = 1634;
    }
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      v17,
      "IPM_MESSAGE_IMP::CreateMessage",
      v16,
      v8);
LABEL_9:
    IPM_MESSAGE_IMP::`scalar deleting destructor'((IPM_MESSAGE_IMP *)v6, v10);
    return v8;
  }
  v8 = -2147024882;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x652u,
      "IPM_MESSAGE_IMP::CreateMessage",
      "IPM_MESSAGE_PIPE::CreateMessage failed allocation of IPM_MESSAGE_IMP, hr = %x\n",
      14);
  return v8;
}

```

## disassembly

```asm
0x180005d00  push    rbx
0x180005d02  push    rbp
0x180005d03  push    rsi
0x180005d04  push    rdi
0x180005d05  push    r14
0x180005d07  push    r15
0x180005d09  sub     rsp, 38h
0x180005d0d  mov     rsi, rcx
0x180005d10  mov     qword ptr [rcx], 0
0x180005d17  mov     ecx, 70h ; 'p'; Size
0x180005d1c  mov     ebp, r8d
0x180005d1f  mov     rbx, rdx
0x180005d22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d27  mov     rdi, rax
0x180005d2a  test    rax, rax
0x180005d2d  jz      short loc_180005D83
0x180005d2f  lea     rax, ??_7IPM_MESSAGE_IMP@@6B@; const IPM_MESSAGE_IMP::`vftable'
0x180005d36  mov     dword ptr [rdi+10h], 0
0x180005d3d  lea     rcx, [rbx+8]; this
0x180005d41  mov     [rdi], rax
0x180005d44  mov     qword ptr [rdi+18h], 0
0x180005d4c  mov     [rdi+20h], rbx
0x180005d50  mov     qword ptr [rdi+28h], 0
0x180005d58  mov     dword ptr [rdi+30h], 0
0x180005d5f  mov     dword ptr [rdi+68h], 0
0x180005d66  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180005d6b  lea     rcx, [rbx+28h]
0x180005d6f  mov     rdx, [rcx+8]
0x180005d73  cmp     [rdx], rcx
0x180005d76  jz      loc_180005E03
0x180005d7c  mov     ecx, 3
0x180005d81  int     29h; Win8: RtlFailFast(ecx)
0x180005d83  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180005d8a  mov     ebx, 8007000Eh
0x180005d8f  jz      short loc_180005DF3
0x180005d91  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005d98  lea     rax, aIpmMessagePipe_26; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005d9f  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180005da3  lea     r9, aIpmMessageImpC; "IPM_MESSAGE_IMP::CreateMessage"
0x180005daa  mov     r8d, 652h; unsigned int
0x180005db0  mov     [rsp+68h+var_48], rax; char *
0x180005db5  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005dbc  call    PuDbgPrint
0x180005dc1  jmp     short loc_180005DF3
0x180005dc3  call    cs:__imp_GetLastError
0x180005dca  nop     dword ptr [rax+rax+00h]
0x180005dcf  mov     ebx, eax
0x180005dd1  test    eax, eax
0x180005dd3  jle     short loc_180005DDE
0x180005dd5  movzx   ebx, ax
0x180005dd8  or      ebx, 80070000h
0x180005dde  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180005de5  jnz     loc_180005F25
0x180005deb  mov     rcx, rdi; this
0x180005dee  call    ??_GIPM_MESSAGE_IMP@@AEAAPEAXI@Z; IPM_MESSAGE_IMP::`scalar deleting destructor'(uint)
0x180005df3  mov     eax, ebx
0x180005df5  add     rsp, 38h
0x180005df9  pop     r15
0x180005dfb  pop     r14
0x180005dfd  pop     rdi
0x180005dfe  pop     rsi
0x180005dff  pop     rbp
0x180005e00  pop     rbx
0x180005e01  retn
0x180005e03  lea     rax, [rdi+58h]
0x180005e07  mov     r15d, 1
0x180005e0d  mov     [rax], rcx
0x180005e10  mov     [rax+8], rdx
0x180005e14  mov     [rdx], rax
0x180005e17  mov     [rcx+8], rax
0x180005e1b  lock xadd [rbx+24h], r15d
0x180005e21  lea     rcx, [rbx+8]; this
0x180005e25  inc     r15d
0x180005e28  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180005e2d  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180005e33  test    al, 3
0x180005e35  setnz   cl
0x180005e38  bt      eax, 1Ch
0x180005e3c  setb    al
0x180005e3f  test    al, cl
0x180005e41  jz      short loc_180005E74
0x180005e43  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005e4a  lea     rax, aIpmMessagePipe_3; "IPM_MESSAGE_PIPE::IpmMessageCreated m_c"...
0x180005e51  mov     dword ptr [rsp+68h+var_40], r15d; char
0x180005e56  lea     r9, aIpmMessagePipe_18; "IPM_MESSAGE_PIPE::IpmMessageCreated"
0x180005e5d  mov     r8d, 2EBh; unsigned int
0x180005e63  mov     [rsp+68h+var_48], rax; char *
0x180005e68  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005e6f  call    PuDbgPrint
0x180005e74  xorps   xmm0, xmm0
0x180005e77  xor     r9d, r9d; lpName
0x180005e7a  movups  xmmword ptr [rdi+38h], xmm0
0x180005e7e  xor     r8d, r8d; bInitialState
0x180005e81  xor     ecx, ecx; lpEventAttributes
0x180005e83  movups  xmmword ptr [rdi+48h], xmm0
0x180005e87  mov     dword ptr [rdi+8], 504D494Dh
0x180005e8e  lea     edx, [r9+1]; bManualReset
0x180005e92  mov     [rdi+68h], ebp
0x180005e95  call    cs:__imp_CreateEventW
0x180005e9c  nop     dword ptr [rax+rax+00h]
0x180005ea1  test    rax, rax
0x180005ea4  jz      short loc_180005EEE
0x180005ea6  mov     [rdi+50h], rax
0x180005eaa  test    ebp, ebp
0x180005eac  jnz     short loc_180005EE0
0x180005eae  or      r9d, 0FFFFFFFFh
0x180005eb2  mov     dword ptr [rsp+68h+var_48], 8
0x180005eba  mov     r8, rdi
0x180005ebd  lea     rdx, ?MessagePipeCompletion@IPM_MESSAGE_PIPE@@SAXPEAXE@Z; IPM_MESSAGE_PIPE::MessagePipeCompletion(void *,uchar)
0x180005ec4  mov     rcx, rax
0x180005ec7  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180005ece  nop     dword ptr [rax+rax+00h]
0x180005ed3  test    rax, rax
0x180005ed6  jz      loc_180005DC3
0x180005edc  mov     [rdi+28h], rax
0x180005ee0  xor     ebx, ebx
0x180005ee2  lock inc dword ptr [rdi+30h]
0x180005ee6  mov     [rsi], rdi
0x180005ee9  jmp     loc_180005DF3
0x180005eee  call    cs:__imp_GetLastError
0x180005ef5  nop     dword ptr [rax+rax+00h]
0x180005efa  mov     ebx, eax
0x180005efc  test    eax, eax
0x180005efe  jle     short loc_180005F09
0x180005f00  movzx   ebx, ax
0x180005f03  or      ebx, 80070000h
0x180005f09  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180005f10  jz      loc_180005DEB
0x180005f16  lea     rax, aIpmMessagePipe_32; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005f1d  mov     r8d, 662h
0x180005f23  jmp     short loc_180005F32
0x180005f25  lea     rax, aIpmMessagePipe_22; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005f2c  mov     r8d, 688h; unsigned int
0x180005f32  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005f39  lea     r9, aIpmMessageImpC; "IPM_MESSAGE_IMP::CreateMessage"
0x180005f40  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180005f44  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005f4b  mov     [rsp+68h+var_48], rax; char *
0x180005f50  call    PuDbgPrint
0x180005f55  jmp     loc_180005DEB
```
