# IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)

- ea: `0x180029644`
- end: `0x18002985c`
- name: `?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z`
- size: `536`
- prototype: `__int64 __fastcall(struct IPM2_MESSAGE_IMP **, struct IPM2_MESSAGE_PIPE *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002aad0`
- `0x18002ad80`
- `0x18002af70`

## callees

- `0x180008000`
- `0x180019230`
- `0x1800291c4`
- `0x180029644`
- `0x18002a2b0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029783`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800296db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800296db`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180029773`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180029773`
- `api-ms-win-core-threadpool-l1-1-0!UnregisterWaitEx` at `0x18002982e`
- `api-ms-win-core-threadpool-l1-1-0!UnregisterWaitEx` at `0x18002982e`

## string_xrefs

- `0x180029733`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029812`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800297f5`: `IPM2_MESSAGE_PIPE::CreateMessage failed allocation of IPM2_MESSAGE_IMP, hr = %x\n`
- `0x180029728`: `IPM2_MESSAGE_IMP::CreateMessage`
- `0x180029800`: `IPM2_MESSAGE_IMP::CreateMessage`
- `0x180029714`: `IPM2_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n`
- `0x1800297a7`: `IPM2_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n`

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
0x180029644  push    rbx
0x180029646  push    rbp
0x180029647  push    rsi
0x180029648  push    rdi
0x180029649  sub     rsp, 38h
0x18002964d  mov     rsi, rcx
0x180029650  mov     qword ptr [rcx], 0
0x180029657  mov     ecx, 70h ; 'p'; Size
0x18002965c  mov     [rsp+58h+phNewWaitObject], 0
0x180029665  mov     ebx, r8d
0x180029668  mov     rbp, rdx
0x18002966b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029670  mov     rdi, rax
0x180029673  test    rax, rax
0x180029676  jz      loc_1800297E0
0x18002967c  lea     rax, ??_7IPM2_MESSAGE_IMP@@6B@; const IPM2_MESSAGE_IMP::`vftable'
0x180029683  mov     dword ptr [rdi+10h], 0
0x18002968a  mov     rdx, rdi; struct IPM2_MESSAGE_IMP *
0x18002968d  mov     [rdi], rax
0x180029690  mov     rcx, rbp; this
0x180029693  mov     qword ptr [rdi+18h], 0
0x18002969b  mov     [rdi+20h], rbp
0x18002969f  mov     qword ptr [rdi+28h], 0
0x1800296a7  mov     dword ptr [rdi+30h], 0
0x1800296ae  mov     dword ptr [rdi+68h], 0
0x1800296b5  call    ?IpmMessageCreated@IPM2_MESSAGE_PIPE@@QEAAXPEAVIPM2_MESSAGE_IMP@@@Z; IPM2_MESSAGE_PIPE::IpmMessageCreated(IPM2_MESSAGE_IMP *)
0x1800296ba  xorps   xmm0, xmm0
0x1800296bd  xor     r9d, r9d; lpName
0x1800296c0  movups  xmmword ptr [rdi+38h], xmm0
0x1800296c4  xor     r8d, r8d; bInitialState
0x1800296c7  xor     ecx, ecx; lpEventAttributes
0x1800296c9  movups  xmmword ptr [rdi+48h], xmm0
0x1800296cd  mov     dword ptr [rdi+8], 324D494Dh
0x1800296d4  lea     edx, [r9+1]; bManualReset
0x1800296d8  mov     [rdi+68h], ebx
0x1800296db  call    cs:__imp_CreateEventW
0x1800296e2  nop     dword ptr [rax+rax+00h]
0x1800296e7  test    rax, rax
0x1800296ea  jnz     short loc_180029749
0x1800296ec  call    cs:__imp_GetLastError
0x1800296f3  nop     dword ptr [rax+rax+00h]
0x1800296f8  mov     ebx, eax
0x1800296fa  test    eax, eax
0x1800296fc  jle     short loc_180029707
0x1800296fe  movzx   ebx, ax
0x180029701  or      ebx, 80070000h
0x180029707  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002970e  jz      loc_180029820
0x180029714  lea     rax, aIpm2MessagePip_6; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x18002971b  mov     r8d, 6DAh; unsigned int
0x180029721  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029728  lea     r9, aIpm2MessageImp; "IPM2_MESSAGE_IMP::CreateMessage"
0x18002972f  mov     [rsp+58h+dwFlags], ebx; char
0x180029733  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002973a  mov     qword ptr [rsp+58h+dwMilliseconds], rax; char *
0x18002973f  call    PuDbgPrint
0x180029744  jmp     loc_180029820
0x180029749  mov     [rdi+50h], rax
0x18002974d  test    ebx, ebx
0x18002974f  jnz     short loc_1800297CB
0x180029751  mov     [rsp+58h+dwFlags], 8; dwFlags
0x180029759  lea     r8, ?MessagePipeCompletion@IPM2_MESSAGE_PIPE@@SAXPEAXE@Z; Callback
0x180029760  mov     r9, rdi; Context
0x180029763  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18002976b  mov     rdx, rax; hObject
0x18002976e  lea     rcx, [rsp+58h+phNewWaitObject]; phNewWaitObject
0x180029773  call    cs:__imp_RegisterWaitForSingleObject
0x18002977a  nop     dword ptr [rax+rax+00h]
0x18002977f  test    eax, eax
0x180029781  jnz     short loc_1800297B9
0x180029783  call    cs:__imp_GetLastError
0x18002978a  nop     dword ptr [rax+rax+00h]
0x18002978f  mov     ebx, eax
0x180029791  test    eax, eax
0x180029793  jle     short loc_18002979E
0x180029795  movzx   ebx, ax
0x180029798  or      ebx, 80070000h
0x18002979e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800297a5  jz      short loc_180029820
0x1800297a7  lea     rax, aIpm2MessagePip_38; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x1800297ae  mov     r8d, 6F6h
0x1800297b4  jmp     loc_180029721
0x1800297b9  mov     rax, [rsp+58h+phNewWaitObject]
0x1800297be  mov     [rdi+28h], rax
0x1800297c2  mov     [rsp+58h+phNewWaitObject], 0
0x1800297cb  mov     rax, [rdi]
0x1800297ce  xor     ebx, ebx
0x1800297d0  mov     rcx, rdi
0x1800297d3  mov     rax, [rax]
0x1800297d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297db  mov     [rsi], rdi
0x1800297de  jmp     short loc_18002981E
0x1800297e0  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800297e7  mov     ebx, 8007000Eh
0x1800297ec  jz      short loc_18002981E
0x1800297ee  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800297f5  lea     rax, aIpm2MessagePip_36; "IPM2_MESSAGE_PIPE::CreateMessage failed"...
0x1800297fc  mov     [rsp+58h+dwFlags], ebx; char
0x180029800  lea     r9, aIpm2MessageImp; "IPM2_MESSAGE_IMP::CreateMessage"
0x180029807  mov     r8d, 6CAh; unsigned int
0x18002980d  mov     qword ptr [rsp+58h+dwMilliseconds], rax; char *
0x180029812  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029819  call    PuDbgPrint
0x18002981e  xor     edi, edi
0x180029820  mov     rcx, [rsp+58h+phNewWaitObject]; WaitHandle
0x180029825  test    rcx, rcx
0x180029828  jz      short loc_180029843
0x18002982a  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002982e  call    cs:__imp_UnregisterWaitEx
0x180029835  nop     dword ptr [rax+rax+00h]
0x18002983a  mov     [rsp+58h+phNewWaitObject], 0
0x180029843  test    rdi, rdi
0x180029846  jz      short loc_180029850
0x180029848  mov     rcx, rdi; this
0x18002984b  call    ??_GIPM2_MESSAGE_IMP@@AEAAPEAXI@Z; IPM2_MESSAGE_IMP::`scalar deleting destructor'(uint)
0x180029850  mov     eax, ebx
0x180029852  add     rsp, 38h
0x180029856  pop     rdi
0x180029857  pop     rsi
0x180029858  pop     rbp
0x180029859  pop     rbx
0x18002985a  retn
```
