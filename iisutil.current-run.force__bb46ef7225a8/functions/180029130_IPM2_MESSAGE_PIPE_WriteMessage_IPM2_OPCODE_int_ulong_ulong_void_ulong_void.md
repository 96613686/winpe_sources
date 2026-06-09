# IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,int,ulong,ulong,void *,ulong,void *)

- ea: `0x180029130`
- end: `0x180029534`
- name: `?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z`
- size: `1028`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029540`
- `0x180029580`
- `0x180029a40`

## callees

- `0x180004f40`
- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x18000e850`
- `0x18001382c`
- `0x180016330`
- `0x180027934`
- `0x18002828c`
- `0x180028360`
- `0x180029130`
- `0x18002c476`
- `0x18002c4c0`
- `0x18002d010`

## string_xrefs

- `0x180029209`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029234`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800291ec`: `IPM2_MESSAGE_PIPE::WriteMessage failed, hr = %x\n`
- `0x1800291f7`: `IPM2_MESSAGE_PIPE::WriteMessage`
- `0x180029226`: `IPM2_MESSAGE_PIPE::WriteMessage`
- `0x180029262`: `IPM2_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n`
- `0x1800292c9`: `IPM2_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n`
- `0x180029363`: `IPM2_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n`
- `0x1800294ae`: `IPM2_MESSAGE_PIPE::WriteMessage failed Ipm2WriteFile, hr = %x\n`

## pseudocode

```c
__int64 __fastcall IPM2_MESSAGE_PIPE::WriteMessage(
        HANDLE *a1,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        void *a8)
{
  BOOL v9; // r12d
  int v10; // ebx
  unsigned int v11; // r15d
  int v12; // eax
  IPM2_MESSAGE_IMP *v13; // rdi
  int DataLength; // eax
  size_t v15; // rbx
  HANDLE v16; // rcx
  int v17; // eax
  IPM2_MESSAGE_IMP *v21; // [rsp+50h] [rbp-78h] BYREF
  size_t Size; // [rsp+58h] [rbp-70h]
  void *v23; // [rsp+60h] [rbp-68h]
  void *Src; // [rsp+68h] [rbp-60h]
  size_t v25; // [rsp+70h] [rbp-58h]
  __int128 Buffer; // [rsp+78h] [rbp-50h] BYREF

  Src = a6;
  v9 = a3 == 0;
  v23 = a8;
  v21 = 0;
  v25 = a7;
  Size = a5;
  Buffer = 0;
  if ( a7 + 16LL + (unsigned __int64)a5 > 0xFFFFFFFF )
  {
    v10 = -2147024362;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x5F6u,
        "IPM2_MESSAGE_PIPE::WriteMessage",
        "IPM2_MESSAGE_PIPE::WriteMessage failed, hr = %x\n",
        22);
LABEL_39:
    IPM2_MESSAGE_PIPE::NotifyPipeDisconnected((IPM2_MESSAGE_PIPE *)a1, v10);
    return (unsigned int)v10;
  }
  v11 = a5 + a7 + 16;
  if ( v11 > 0x10000 )
    v9 = 1;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x60Au,
      "IPM2_MESSAGE_PIPE::WriteMessage",
      "IPM2_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n",
      a2);
  v12 = IPM2_MESSAGE_IMP::CreateMessage(&v21, (struct IPM2_MESSAGE_PIPE *)a1, v9);
  v13 = v21;
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x613u,
        "IPM2_MESSAGE_PIPE::WriteMessage",
        "IPM2_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n",
        v12);
    goto LABEL_36;
  }
  LODWORD(Buffer) = a2;
  *((_QWORD *)&Buffer + 1) = a4;
  DWORD1(Buffer) = a5 + a7 + 16;
  *((_DWORD *)v21 + 3) = 1;
  if ( v9 )
  {
    *((_QWORD *)v13 + 3) = v23;
    *((_DWORD *)v13 + 4) = a7;
    goto LABEL_22;
  }
  DataLength = IPM2_MESSAGE_IMP::AllocateDataLength(v13, v11);
  v10 = DataLength;
  if ( DataLength >= 0 )
  {
    v15 = Size;
    *(_OWORD *)*((_QWORD *)v13 + 3) = Buffer;
    if ( a5 )
      memcpy_0((void *)(*((_QWORD *)v13 + 3) + 16LL), Src, v15);
    if ( a7 && v23 )
      memcpy_0((void *)(v15 + *((_QWORD *)v13 + 3) + 16LL), v23, v25);
    *((_DWORD *)v13 + 4) = v11;
LABEL_22:
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 2));
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(a1 + 1));
    v16 = a1[4];
    if ( v16 == (HANDLE)-1LL )
    {
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(a1 + 1));
      v10 = -2147024787;
      goto LABEL_36;
    }
    if ( v9 )
    {
      v10 = Ipm2WriteFileChunked(v16, &Buffer, 0x10u, (struct _OVERLAPPED *)((char *)v13 + 56));
      if ( v10 < 0
        || a5 && (v10 = Ipm2WriteFileChunked(a1[4], Src, a5, (struct _OVERLAPPED *)((char *)v13 + 56)), v10 < 0) )
      {
LABEL_31:
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(a1 + 1));
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 2));
        if ( v10 < 0 )
        {
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x689u,
              "IPM2_MESSAGE_PIPE::WriteMessage",
              "IPM2_MESSAGE_PIPE::WriteMessage failed Ipm2WriteFile, hr = %x\n",
              v10);
          if ( !v9 )
            (*(void (__fastcall **)(IPM2_MESSAGE_IMP *))(*(_QWORD *)v13 + 8LL))(v13);
        }
        goto LABEL_36;
      }
      v17 = Ipm2WriteFileChunked(a1[4], *((LPCVOID *)v13 + 3), a7, (struct _OVERLAPPED *)((char *)v13 + 56));
    }
    else
    {
      (**(void (__fastcall ***)(IPM2_MESSAGE_IMP *))v13)(v13);
      v17 = Ipm2WriteFile(a1[4], *((LPCVOID *)v13 + 3), v11, (LPOVERLAPPED)((char *)v13 + 56));
    }
    v10 = v17;
    goto LABEL_31;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x62Bu,
      "IPM2_MESSAGE_PIPE::WriteMessage",
      "IPM2_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n",
      DataLength);
LABEL_36:
  if ( v13 )
    (*(void (__fastcall **)(IPM2_MESSAGE_IMP *))(*(_QWORD *)v13 + 8LL))(v13);
  if ( v10 < 0 )
    goto LABEL_39;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180029130  mov     [rsp+arg_10], rbx
0x180029135  push    rbp
0x180029136  push    rsi
0x180029137  push    rdi
0x180029138  push    r12
0x18002913a  push    r13
0x18002913c  push    r14
0x18002913e  push    r15
0x180029140  sub     rsp, 90h
0x180029147  mov     rax, cs:__security_cookie
0x18002914e  xor     rax, rsp
0x180029151  mov     [rsp+0C8h+var_40], rax
0x180029159  mov     rax, [rsp+0C8h+arg_28]
0x180029161  xor     r12d, r12d
0x180029164  test    r8d, r8d
0x180029167  mov     [rsp+0C8h+Src], rax
0x18002916c  mov     rax, [rsp+0C8h+arg_38]
0x180029174  mov     r13, rcx
0x180029177  mov     ecx, [rsp+0C8h+arg_20]
0x18002917e  setz    r12b
0x180029182  mov     [rsp+0C8h+var_68], rax
0x180029187  xorps   xmm0, xmm0
0x18002918a  mov     [rsp+0C8h+var_7C], r9d
0x18002918f  mov     eax, ecx
0x180029191  mov     r9d, edx
0x180029194  mov     [rsp+0C8h+var_80], edx
0x180029198  mov     edx, [rsp+0C8h+arg_30]
0x18002919f  mov     sil, 3
0x1800291a2  mov     r8d, edx
0x1800291a5  mov     [rsp+0C8h+var_88], ecx
0x1800291a9  add     r8, 10h
0x1800291ad  mov     [rsp+0C8h+var_78], 0
0x1800291b6  add     rax, r8
0x1800291b9  mov     [rsp+0C8h+var_58], rdx
0x1800291be  mov     r8d, 0FFFFFFFFh
0x1800291c4  mov     [rsp+0C8h+Size], rcx
0x1800291c9  movups  [rsp+0C8h+Buffer], xmm0
0x1800291ce  cmp     rax, r8
0x1800291d1  jbe     short loc_18002921A
0x1800291d3  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x1800291da  mov     ebx, 80070216h
0x1800291df  jz      loc_1800294FD
0x1800291e5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800291ec  lea     rax, aIpm2MessagePip_24; "IPM2_MESSAGE_PIPE::WriteMessage failed,"...
0x1800291f3  mov     dword ptr [rsp+0C8h+var_A0], ebx; char
0x1800291f7  lea     r9, aIpm2MessagePip_20; "IPM2_MESSAGE_PIPE::WriteMessage"
0x1800291fe  mov     r8d, 5F6h; unsigned int
0x180029204  mov     [rsp+0C8h+var_A8], rax; char *
0x180029209  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029210  call    PuDbgPrint
0x180029215  jmp     loc_1800294FD
0x18002921a  mov     eax, 1
0x18002921f  lea     r15d, [rdx+10h]
0x180029223  add     r15d, ecx
0x180029226  lea     rbp, aIpm2MessagePip_20; "IPM2_MESSAGE_PIPE::WriteMessage"
0x18002922d  cmp     r15d, 10000h
0x180029234  lea     r14, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002923b  cmova   r12d, eax
0x18002923f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029245  test    sil, al
0x180029248  mov     [rsp+0C8h+var_84], r12d
0x18002924d  setnz   cl
0x180029250  bt      eax, 1Ch
0x180029254  setb    al
0x180029257  test    al, cl
0x180029259  jz      short loc_18002928D
0x18002925b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029262  lea     rax, aIpm2MessagePip_26; "IPM2_MESSAGE_PIPE::WriteMessage called "...
0x180029269  mov     [rsp+0C8h+var_90], r15d
0x18002926e  mov     r8d, 60Ah; unsigned int
0x180029274  mov     [rsp+0C8h+var_98], edx
0x180029278  mov     rdx, r14; char *
0x18002927b  mov     dword ptr [rsp+0C8h+var_A0], r9d; char
0x180029280  mov     r9, rbp; char *
0x180029283  mov     [rsp+0C8h+var_A8], rax; char *
0x180029288  call    PuDbgPrint
0x18002928d  mov     r8d, r12d; int
0x180029290  lea     rcx, [rsp+0C8h+var_78]; struct IPM2_MESSAGE_IMP **
0x180029295  mov     rdx, r13; struct IPM2_MESSAGE_PIPE *
0x180029298  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x18002929d  mov     rdi, [rsp+0C8h+var_78]
0x1800292a2  mov     ebx, eax
0x1800292a4  test    eax, eax
0x1800292a6  jns     short loc_1800292E2
0x1800292a8  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x1800292af  jz      loc_1800294E5
0x1800292b5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800292bc  mov     r9, rbp; char *
0x1800292bf  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x1800292c3  mov     r8d, 613h; unsigned int
0x1800292c9  lea     rax, aIpm2MessagePip_14; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x1800292d0  mov     rdx, r14; char *
0x1800292d3  mov     [rsp+0C8h+var_A8], rax; char *
0x1800292d8  call    PuDbgPrint
0x1800292dd  jmp     loc_1800294E5
0x1800292e2  mov     eax, [rsp+0C8h+var_80]
0x1800292e6  mov     dword ptr [rsp+0C8h+Buffer], eax
0x1800292ea  mov     eax, [rsp+0C8h+var_7C]
0x1800292ee  mov     dword ptr [rsp+0C8h+Buffer+8], eax
0x1800292f5  mov     dword ptr [rsp+0C8h+Buffer+0Ch], 0
0x180029300  mov     dword ptr [rsp+0C8h+Buffer+4], r15d
0x180029305  mov     dword ptr [rdi+0Ch], 1
0x18002930c  test    r12d, r12d
0x18002930f  jz      short loc_180029329
0x180029311  mov     rdx, [rsp+0C8h+var_68]
0x180029316  mov     eax, [rsp+0C8h+arg_30]
0x18002931d  mov     [rdi+18h], rdx
0x180029321  mov     [rdi+10h], eax
0x180029324  jmp     loc_1800293D4
0x180029329  mov     edx, r15d; unsigned int
0x18002932c  mov     rcx, rdi; this
0x18002932f  call    ?AllocateDataLength@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::AllocateDataLength(ulong)
0x180029334  mov     ebx, eax
0x180029336  test    eax, eax
0x180029338  jns     short loc_180029379
0x18002933a  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x180029341  jz      loc_1800294E5
0x180029347  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002934e  mov     r9, rbp; char *
0x180029351  mov     [rsp+0C8h+var_98], r15d
0x180029356  mov     r8d, 62Bh; unsigned int
0x18002935c  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x180029360  mov     rdx, r14; char *
0x180029363  lea     rax, aIpm2MessagePip_16; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x18002936a  mov     [rsp+0C8h+var_A8], rax; char *
0x18002936f  call    PuDbgPrint
0x180029374  jmp     loc_1800294E5
0x180029379  cmp     [rsp+0C8h+var_88], 0
0x18002937e  mov     rax, [rdi+18h]
0x180029382  movups  xmm0, [rsp+0C8h+Buffer]
0x180029387  mov     rbx, [rsp+0C8h+Size]
0x18002938c  movdqu  xmmword ptr [rax], xmm0
0x180029390  jz      short loc_1800293A7
0x180029392  mov     rcx, [rdi+18h]
0x180029396  mov     r8, rbx; Size
0x180029399  mov     rdx, [rsp+0C8h+Src]; Src
0x18002939e  add     rcx, 10h; void *
0x1800293a2  call    memcpy_0
0x1800293a7  cmp     [rsp+0C8h+arg_30], 0
0x1800293af  jz      short loc_1800293D0
0x1800293b1  mov     rdx, [rsp+0C8h+var_68]; Src
0x1800293b6  test    rdx, rdx
0x1800293b9  jz      short loc_1800293D0
0x1800293bb  mov     rcx, [rdi+18h]
0x1800293bf  mov     r8, [rsp+0C8h+var_58]; Size
0x1800293c4  add     rcx, 10h
0x1800293c8  add     rcx, rbx; void *
0x1800293cb  call    memcpy_0
0x1800293d0  mov     [rdi+10h], r15d
0x1800293d4  lea     rcx, [r13+10h]; this
0x1800293d8  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800293dd  lea     r12, [r13+8]
0x1800293e1  mov     rcx, r12; this
0x1800293e4  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800293e9  mov     rcx, [r13+20h]; hFile
0x1800293ed  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800293f1  jnz     short loc_180029405
0x1800293f3  mov     rcx, r12; this
0x1800293f6  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800293fb  mov     ebx, 8007006Dh
0x180029400  jmp     loc_1800294E5
0x180029405  cmp     [rsp+0C8h+var_84], 0
0x18002940a  jz      short loc_180029465
0x18002940c  lea     r15, [rdi+38h]
0x180029410  mov     r8d, 10h; unsigned int
0x180029416  mov     r9, r15; struct _OVERLAPPED *
0x180029419  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x18002941e  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x180029423  mov     ebx, eax
0x180029425  test    eax, eax
0x180029427  js      short loc_180029489
0x180029429  mov     eax, [rsp+0C8h+var_88]
0x18002942d  test    eax, eax
0x18002942f  jz      short loc_18002944B
0x180029431  mov     rdx, [rsp+0C8h+Src]; lpBuffer
0x180029436  mov     r9, r15; struct _OVERLAPPED *
0x180029439  mov     rcx, [r13+20h]; hFile
0x18002943d  mov     r8d, eax; unsigned int
0x180029440  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x180029445  mov     ebx, eax
0x180029447  test    eax, eax
0x180029449  js      short loc_180029489
0x18002944b  mov     r8d, [rsp+0C8h+arg_30]; unsigned int
0x180029453  mov     r9, r15; struct _OVERLAPPED *
0x180029456  mov     rdx, [rdi+18h]; lpBuffer
0x18002945a  mov     rcx, [r13+20h]; hFile
0x18002945e  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x180029463  jmp     short loc_180029487
0x180029465  mov     rax, [rdi]
0x180029468  mov     rcx, rdi
0x18002946b  mov     rax, [rax]
0x18002946e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029473  mov     rdx, [rdi+18h]; lpBuffer
0x180029477  lea     r9, [rdi+38h]; lpOverlapped
0x18002947b  mov     rcx, [r13+20h]; hFile
0x18002947f  mov     r8d, r15d; nNumberOfBytesToWrite
0x180029482  call    ?Ipm2WriteFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFile(void *,void *,ulong,_OVERLAPPED *)
0x180029487  mov     ebx, eax
0x180029489  mov     rcx, r12; this
0x18002948c  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180029491  lea     rcx, [r13+10h]; this
0x180029495  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002949a  test    ebx, ebx
0x18002949c  jns     short loc_1800294E5
0x18002949e  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x1800294a5  jz      short loc_1800294CF
0x1800294a7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800294ae  lea     rax, aIpm2MessagePip_22; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x1800294b5  mov     dword ptr [rsp+0C8h+var_A0], ebx; char
0x1800294b9  mov     r9, rbp; char *
0x1800294bc  mov     r8d, 689h; unsigned int
0x1800294c2  mov     [rsp+0C8h+var_A8], rax; char *
0x1800294c7  mov     rdx, r14; char *
0x1800294ca  call    PuDbgPrint
0x1800294cf  cmp     [rsp+0C8h+var_84], 0
0x1800294d4  jnz     short loc_1800294E5
0x1800294d6  mov     rax, [rdi]
0x1800294d9  mov     rcx, rdi
0x1800294dc  mov     rax, [rax+8]
0x1800294e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294e5  test    rdi, rdi
0x1800294e8  jz      short loc_1800294F9
0x1800294ea  mov     rax, [rdi]
0x1800294ed  mov     rcx, rdi
0x1800294f0  mov     rax, [rax+8]
0x1800294f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294f9  test    ebx, ebx
0x1800294fb  jns     short loc_180029507
0x1800294fd  mov     edx, ebx; int
0x1800294ff  mov     rcx, r13; this
0x180029502  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180029507  mov     eax, ebx
0x180029509  mov     rcx, [rsp+0C8h+var_40]
0x180029511  xor     rcx, rsp; StackCookie
0x180029514  call    __security_check_cookie
0x180029519  mov     rbx, [rsp+0C8h+arg_10]
0x180029521  add     rsp, 90h
0x180029528  pop     r15
0x18002952a  pop     r14
0x18002952c  pop     r13
0x18002952e  pop     r12
0x180029530  pop     rdi
0x180029531  pop     rsi
0x180029532  pop     rbp
0x180029533  retn
```
