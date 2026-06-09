# IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)

- ea: `0x180005184`
- end: `0x1800053c5`
- name: `?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct IPM_MESSAGE_IMP **, struct IPM_MESSAGE_PIPE *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003a10`
- `0x1800053d0`
- `0x180005b40`
- `0x180010080`

## callees

- `0x180005110`
- `0x180005184`
- `0x180007300`
- `0x1800081e0`
- `0x18000e150`
- `0x1800183f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005312`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005312`
- `api-ms-win-core-threadpool-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000533e`
- `api-ms-win-core-threadpool-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000533e`

## string_xrefs

- `0x1800052c7`: `IPM_MESSAGE_PIPE::IpmMessageCreated m_cMessages = %d\n`
- `0x1800052d3`: `IPM_MESSAGE_PIPE::IpmMessageCreated`
- `0x180005239`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800052e5`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800053af`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18000521c`: `IPM_MESSAGE_PIPE::CreateMessage failed allocation of IPM_MESSAGE_IMP, hr = %x\n`
- `0x180005227`: `IPM_MESSAGE_IMP::CreateMessage`
- `0x1800053a4`: `IPM_MESSAGE_IMP::CreateMessage`
- `0x180005381`: `IPM_MESSAGE_PIPE::CreateMessage failed CreateEvent, hr = %x\n`
- `0x180005390`: `IPM_MESSAGE_PIPE::CreateMessage failed RegisterWaitForSingleObject, hr = %x\n`

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
0x180005184  push    rbx
0x180005186  push    rbp
0x180005187  push    rsi
0x180005188  push    rdi
0x180005189  push    r14
0x18000518b  push    r15
0x18000518d  sub     rsp, 38h
0x180005191  mov     rsi, rcx
0x180005194  mov     qword ptr [rcx], 0
0x18000519b  mov     ecx, 70h ; 'p'; Size
0x1800051a0  mov     ebp, r8d
0x1800051a3  mov     rbx, rdx
0x1800051a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800051ab  mov     rdi, rax
0x1800051ae  test    rax, rax
0x1800051b1  jz      short loc_180005207
0x1800051b3  lea     rax, ??_7IPM_MESSAGE_IMP@@6B@; const IPM_MESSAGE_IMP::`vftable'
0x1800051ba  mov     dword ptr [rdi+10h], 0
0x1800051c1  lea     rcx, [rbx+8]; this
0x1800051c5  mov     [rdi], rax
0x1800051c8  mov     qword ptr [rdi+18h], 0
0x1800051d0  mov     [rdi+20h], rbx
0x1800051d4  mov     qword ptr [rdi+28h], 0
0x1800051dc  mov     dword ptr [rdi+30h], 0
0x1800051e3  mov     dword ptr [rdi+68h], 0
0x1800051ea  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800051ef  lea     rcx, [rbx+28h]
0x1800051f3  mov     rdx, [rcx+8]
0x1800051f7  cmp     [rdx], rcx
0x1800051fa  jz      loc_180005280
0x180005200  mov     ecx, 3
0x180005205  int     29h; Win8: RtlFailFast(ecx)
0x180005207  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18000520e  mov     ebx, 8007000Eh
0x180005213  jz      short loc_180005271
0x180005215  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000521c  lea     rax, aIpmMessagePipe_26; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005223  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180005227  lea     r9, aIpmMessageImpC; "IPM_MESSAGE_IMP::CreateMessage"
0x18000522e  mov     r8d, 652h; unsigned int
0x180005234  mov     [rsp+68h+var_48], rax; char *
0x180005239  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005240  call    PuDbgPrint
0x180005245  jmp     short loc_180005271
0x180005247  call    cs:__imp_GetLastError
0x18000524d  mov     ebx, eax
0x18000524f  test    eax, eax
0x180005251  jle     short loc_18000525C
0x180005253  movzx   ebx, ax
0x180005256  or      ebx, 80070000h
0x18000525c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180005263  jnz     loc_180005390
0x180005269  mov     rcx, rdi; this
0x18000526c  call    ??_GIPM_MESSAGE_IMP@@AEAAPEAXI@Z; IPM_MESSAGE_IMP::`scalar deleting destructor'(uint)
0x180005271  mov     eax, ebx
0x180005273  add     rsp, 38h
0x180005277  pop     r15
0x180005279  pop     r14
0x18000527b  pop     rdi
0x18000527c  pop     rsi
0x18000527d  pop     rbp
0x18000527e  pop     rbx
0x18000527f  retn
0x180005280  lea     rax, [rdi+58h]
0x180005284  mov     r15d, 1
0x18000528a  mov     [rax], rcx
0x18000528d  mov     [rax+8], rdx
0x180005291  mov     [rdx], rax
0x180005294  mov     [rcx+8], rax
0x180005298  lock xadd [rbx+24h], r15d
0x18000529e  lea     rcx, [rbx+8]; this
0x1800052a2  inc     r15d
0x1800052a5  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800052aa  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800052b0  test    al, 3
0x1800052b2  setnz   cl
0x1800052b5  bt      eax, 1Ch
0x1800052b9  setb    al
0x1800052bc  test    al, cl
0x1800052be  jz      short loc_1800052F1
0x1800052c0  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800052c7  lea     rax, aIpmMessagePipe_3; "IPM_MESSAGE_PIPE::IpmMessageCreated m_c"...
0x1800052ce  mov     dword ptr [rsp+68h+var_40], r15d; char
0x1800052d3  lea     r9, aIpmMessagePipe_18; "IPM_MESSAGE_PIPE::IpmMessageCreated"
0x1800052da  mov     r8d, 2EBh; unsigned int
0x1800052e0  mov     [rsp+68h+var_48], rax; char *
0x1800052e5  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800052ec  call    PuDbgPrint
0x1800052f1  xorps   xmm0, xmm0
0x1800052f4  xor     r9d, r9d; lpName
0x1800052f7  movups  xmmword ptr [rdi+38h], xmm0
0x1800052fb  xor     r8d, r8d; bInitialState
0x1800052fe  xor     ecx, ecx; lpEventAttributes
0x180005300  movups  xmmword ptr [rdi+48h], xmm0
0x180005304  mov     dword ptr [rdi+8], 504D494Dh
0x18000530b  lea     edx, [r9+1]; bManualReset
0x18000530f  mov     [rdi+68h], ebp
0x180005312  call    cs:__imp_CreateEventW
0x180005318  test    rax, rax
0x18000531b  jz      short loc_18000535F
0x18000531d  mov     [rdi+50h], rax
0x180005321  test    ebp, ebp
0x180005323  jnz     short loc_180005351
0x180005325  or      r9d, 0FFFFFFFFh
0x180005329  mov     dword ptr [rsp+68h+var_48], 8
0x180005331  mov     r8, rdi
0x180005334  lea     rdx, ?MessagePipeCompletion@IPM_MESSAGE_PIPE@@SAXPEAXE@Z; IPM_MESSAGE_PIPE::MessagePipeCompletion(void *,uchar)
0x18000533b  mov     rcx, rax
0x18000533e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180005344  test    rax, rax
0x180005347  jz      loc_180005247
0x18000534d  mov     [rdi+28h], rax
0x180005351  xor     ebx, ebx
0x180005353  lock inc dword ptr [rdi+30h]
0x180005357  mov     [rsi], rdi
0x18000535a  jmp     loc_180005271
0x18000535f  call    cs:__imp_GetLastError
0x180005365  mov     ebx, eax
0x180005367  test    eax, eax
0x180005369  jle     short loc_180005374
0x18000536b  movzx   ebx, ax
0x18000536e  or      ebx, 80070000h
0x180005374  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18000537b  jz      loc_180005269
0x180005381  lea     rax, aIpmMessagePipe_32; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005388  mov     r8d, 662h
0x18000538e  jmp     short loc_18000539D
0x180005390  lea     rax, aIpmMessagePipe_22; "IPM_MESSAGE_PIPE::CreateMessage failed "...
0x180005397  mov     r8d, 688h; unsigned int
0x18000539d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800053a4  lea     r9, aIpmMessageImpC; "IPM_MESSAGE_IMP::CreateMessage"
0x1800053ab  mov     dword ptr [rsp+68h+var_40], ebx; char
0x1800053af  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800053b6  mov     [rsp+68h+var_48], rax; char *
0x1800053bb  call    PuDbgPrint
0x1800053c0  jmp     loc_180005269
```
