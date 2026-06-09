# IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)

- ea: `0x180027934`
- end: `0x180027b2d`
- name: `?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z`
- size: `505`
- prototype: `static int(struct IPM2_MESSAGE_IMP **, struct IPM2_MESSAGE_PIPE *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180028ca0`
- `0x180028f50`
- `0x180029130`

## callees

- `0x180007300`
- `0x1800183f8`
- `0x1800274f4`
- `0x180027934`
- `0x1800284b0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a61`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800279cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800279cb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180027a57`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180027a57`
- `api-ms-win-core-threadpool-l1-1-0!UnregisterWaitEx` at `0x180027b06`
- `api-ms-win-core-threadpool-l1-1-0!UnregisterWaitEx` at `0x180027b06`

## string_xrefs

- `0x180027a17`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027aea`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027acd`: `IPM2_MESSAGE_PIPE::CreateMessage failed allocation of IPM2_MESSAGE_IMP, hr = %x\n`
- `0x180027a0c`: `IPM2_MESSAGE_IMP::CreateMessage`
- `0x180027ad8`: `IPM2_MESSAGE_IMP::CreateMessage`
- `0x1800279f8`: `IPM2_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n`
- `0x180027a7f`: `IPM2_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n`

## pseudocode

```c
__int64 __fastcall IPM2_MESSAGE_IMP::CreateMessage(struct IPM2_MESSAGE_IMP **a1, struct IPM2_MESSAGE_PIPE *a2, int a3)
{
  unsigned int v6; // edx
  char *v7; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  char *v11; // rax
  unsigned int v12; // r8d
  signed int v13; // eax
  void *phNewWaitObject; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  phNewWaitObject = 0;
  v7 = (char *)operator new(0x70u);
  if ( !v7 )
  {
    v10 = -2147024882;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x6CAu,
        "IPM2_MESSAGE_IMP::CreateMessage",
        "IPM2_MESSAGE_PIPE::CreateMessage failed allocation of IPM2_MESSAGE_IMP, hr = %x\n",
        14);
    goto LABEL_18;
  }
  *((_DWORD *)v7 + 4) = 0;
  *(_QWORD *)v7 = &IPM2_MESSAGE_IMP::`vftable';
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 4) = a2;
  *((_QWORD *)v7 + 5) = 0;
  *((_DWORD *)v7 + 12) = 0;
  *((_DWORD *)v7 + 26) = 0;
  IPM2_MESSAGE_PIPE::IpmMessageCreated(a2, (struct IPM2_MESSAGE_IMP *)v7);
  *(_OWORD *)(v7 + 56) = 0;
  *(_OWORD *)(v7 + 72) = 0;
  *((_DWORD *)v7 + 2) = 843925837;
  *((_DWORD *)v7 + 26) = a3;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      v11 = "IPM2_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n";
      v12 = 1754;
LABEL_7:
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        v12,
        "IPM2_MESSAGE_IMP::CreateMessage",
        v11,
        v10);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  *((_QWORD *)v7 + 10) = EventW;
  if ( a3 )
  {
LABEL_15:
    v10 = 0;
    (**(void (__fastcall ***)(void *))v7)(v7);
    *a1 = (struct IPM2_MESSAGE_IMP *)v7;
LABEL_18:
    v7 = 0;
    goto LABEL_19;
  }
  if ( RegisterWaitForSingleObject(
         &phNewWaitObject,
         EventW,
         (WAITORTIMERCALLBACK)IPM2_MESSAGE_PIPE::MessagePipeCompletion,
         v7,
         0xFFFFFFFF,
         8u) )
  {
    *((_QWORD *)v7 + 5) = phNewWaitObject;
    phNewWaitObject = 0;
    goto LABEL_15;
  }
  v13 = GetLastError();
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
  {
    v11 = "IPM2_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n";
    v12 = 1782;
    goto LABEL_7;
  }
LABEL_19:
  if ( phNewWaitObject )
  {
    UnregisterWaitEx(phNewWaitObject, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    phNewWaitObject = 0;
  }
  if ( v7 )
    IPM2_MESSAGE_IMP::`scalar deleting destructor'((IPM2_MESSAGE_IMP *)v7, v6);
  return v10;
}

```

## disassembly

```asm
0x180027934  push    rbx
0x180027936  push    rbp
0x180027937  push    rsi
0x180027938  push    rdi
0x180027939  sub     rsp, 38h
0x18002793d  mov     rsi, rcx
0x180027940  mov     qword ptr [rcx], 0
0x180027947  mov     ecx, 70h ; 'p'; Size
0x18002794c  mov     [rsp+58h+phNewWaitObject], 0
0x180027955  mov     ebx, r8d
0x180027958  mov     rbp, rdx
0x18002795b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027960  mov     rdi, rax
0x180027963  test    rax, rax
0x180027966  jz      loc_180027AB8
0x18002796c  lea     rax, ??_7IPM2_MESSAGE_IMP@@6B@; const IPM2_MESSAGE_IMP::`vftable'
0x180027973  mov     dword ptr [rdi+10h], 0
0x18002797a  mov     rdx, rdi; struct IPM2_MESSAGE_IMP *
0x18002797d  mov     [rdi], rax
0x180027980  mov     rcx, rbp; this
0x180027983  mov     qword ptr [rdi+18h], 0
0x18002798b  mov     [rdi+20h], rbp
0x18002798f  mov     qword ptr [rdi+28h], 0
0x180027997  mov     dword ptr [rdi+30h], 0
0x18002799e  mov     dword ptr [rdi+68h], 0
0x1800279a5  call    ?IpmMessageCreated@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z; IPM2_MESSAGE_PIPE::IpmMessageCreated(IPM2_MESSAGE_IMP *)
0x1800279aa  xorps   xmm0, xmm0
0x1800279ad  xor     r9d, r9d; lpName
0x1800279b0  movups  xmmword ptr [rdi+38h], xmm0
0x1800279b4  xor     r8d, r8d; bInitialState
0x1800279b7  xor     ecx, ecx; lpEventAttributes
0x1800279b9  movups  xmmword ptr [rdi+48h], xmm0
0x1800279bd  mov     dword ptr [rdi+8], 324D494Dh
0x1800279c4  lea     edx, [r9+1]; bManualReset
0x1800279c8  mov     [rdi+68h], ebx
0x1800279cb  call    cs:__imp_CreateEventW
0x1800279d1  test    rax, rax
0x1800279d4  jnz     short loc_180027A2D
0x1800279d6  call    cs:__imp_GetLastError
0x1800279dc  mov     ebx, eax
0x1800279de  test    eax, eax
0x1800279e0  jle     short loc_1800279EB
0x1800279e2  movzx   ebx, ax
0x1800279e5  or      ebx, 80070000h
0x1800279eb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800279f2  jz      loc_180027AF8
0x1800279f8  lea     rax, aIpm2MessagePip_6; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x1800279ff  mov     r8d, 6DAh; unsigned int
0x180027a05  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027a0c  lea     r9, aIpm2MessageImp; "IPM2_MESSAGE_IMP::CreateMessage"
0x180027a13  mov     [rsp+58h+dwFlags], ebx; char
0x180027a17  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027a1e  mov     qword ptr [rsp+58h+dwMilliseconds], rax; char *
0x180027a23  call    PuDbgPrint
0x180027a28  jmp     loc_180027AF8
0x180027a2d  mov     [rdi+50h], rax
0x180027a31  test    ebx, ebx
0x180027a33  jnz     short loc_180027AA3
0x180027a35  mov     [rsp+58h+dwFlags], 8; dwFlags
0x180027a3d  lea     r8, ?MessagePipeCompletion@IPM2_MESSAGE_PIPE@@SAXPEAXE@Z; Callback
0x180027a44  mov     r9, rdi; Context
0x180027a47  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180027a4f  mov     rdx, rax; hObject
0x180027a52  lea     rcx, [rsp+58h+phNewWaitObject]; phNewWaitObject
0x180027a57  call    cs:__imp_RegisterWaitForSingleObject
0x180027a5d  test    eax, eax
0x180027a5f  jnz     short loc_180027A91
0x180027a61  call    cs:__imp_GetLastError
0x180027a67  mov     ebx, eax
0x180027a69  test    eax, eax
0x180027a6b  jle     short loc_180027A76
0x180027a6d  movzx   ebx, ax
0x180027a70  or      ebx, 80070000h
0x180027a76  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027a7d  jz      short loc_180027AF8
0x180027a7f  lea     rax, aIpm2MessagePip_38; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x180027a86  mov     r8d, 6F6h
0x180027a8c  jmp     loc_180027A05
0x180027a91  mov     rax, [rsp+58h+phNewWaitObject]
0x180027a96  mov     [rdi+28h], rax
0x180027a9a  mov     [rsp+58h+phNewWaitObject], 0
0x180027aa3  mov     rax, [rdi]
0x180027aa6  xor     ebx, ebx
0x180027aa8  mov     rcx, rdi
0x180027aab  mov     rax, [rax]
0x180027aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ab3  mov     [rsi], rdi
0x180027ab6  jmp     short loc_180027AF6
0x180027ab8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027abf  mov     ebx, 8007000Eh
0x180027ac4  jz      short loc_180027AF6
0x180027ac6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027acd  lea     rax, aIpm2MessagePip_36; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x180027ad4  mov     [rsp+58h+dwFlags], ebx; char
0x180027ad8  lea     r9, aIpm2MessageImp; "IPM2_MESSAGE_IMP::CreateMessage"
0x180027adf  mov     r8d, 6CAh; unsigned int
0x180027ae5  mov     qword ptr [rsp+58h+dwMilliseconds], rax; char *
0x180027aea  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027af1  call    PuDbgPrint
0x180027af6  xor     edi, edi
0x180027af8  mov     rcx, [rsp+58h+phNewWaitObject]; WaitHandle
0x180027afd  test    rcx, rcx
0x180027b00  jz      short loc_180027B15
0x180027b02  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180027b06  call    cs:__imp_UnregisterWaitEx
0x180027b0c  mov     [rsp+58h+phNewWaitObject], 0
0x180027b15  test    rdi, rdi
0x180027b18  jz      short loc_180027B22
0x180027b1a  mov     rcx, rdi; this
0x180027b1d  call    ??_GIPM2_MESSAGE_IMP@@AEAAPEAXI@Z; IPM2_MESSAGE_IMP::`scalar deleting destructor'(uint)
0x180027b22  mov     eax, ebx
0x180027b24  add     rsp, 38h
0x180027b28  pop     rdi
0x180027b29  pop     rsi
0x180027b2a  pop     rbp
0x180027b2b  pop     rbx
0x180027b2c  retn
```
