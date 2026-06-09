# IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,int,ulong,ulong,void *,ulong,void *)

- ea: `0x18002af70`
- end: `0x18002b375`
- name: `?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z`
- size: `1029`
- prototype: `__int64 __fastcall(HANDLE *, int, int, unsigned int, unsigned int, void *, unsigned int, void *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b380`
- `0x18002b3c0`
- `0x18002b880`

## callees

- `0x180005aa0`
- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x18000f810`
- `0x180014288`
- `0x180016f20`
- `0x180029644`
- `0x18002a054`
- `0x18002a13c`
- `0x18002af70`
- `0x18002e516`
- `0x18002e560`
- `0x18002f010`

## string_xrefs

- `0x18002b049`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002b074`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002b02c`: `IPM2_MESSAGE_PIPE::WriteMessage failed, hr = %x\n`
- `0x18002b037`: `IPM2_MESSAGE_PIPE::WriteMessage`
- `0x18002b066`: `IPM2_MESSAGE_PIPE::WriteMessage`
- `0x18002b0a2`: `IPM2_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n`
- `0x18002b109`: `IPM2_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n`
- `0x18002b1a3`: `IPM2_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n`
- `0x18002b2ee`: `IPM2_MESSAGE_PIPE::WriteMessage failed Ipm2WriteFile, hr = %x\n`

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
0x18002af70  mov     [rsp+arg_10], rbx
0x18002af75  push    rbp
0x18002af76  push    rsi
0x18002af77  push    rdi
0x18002af78  push    r12
0x18002af7a  push    r13
0x18002af7c  push    r14
0x18002af7e  push    r15
0x18002af80  sub     rsp, 90h
0x18002af87  mov     rax, cs:__security_cookie
0x18002af8e  xor     rax, rsp
0x18002af91  mov     [rsp+0C8h+var_40], rax
0x18002af99  mov     rax, [rsp+0C8h+arg_28]
0x18002afa1  xor     r12d, r12d
0x18002afa4  test    r8d, r8d
0x18002afa7  mov     [rsp+0C8h+Src], rax
0x18002afac  mov     rax, [rsp+0C8h+arg_38]
0x18002afb4  mov     r13, rcx
0x18002afb7  mov     ecx, [rsp+0C8h+arg_20]
0x18002afbe  setz    r12b
0x18002afc2  mov     [rsp+0C8h+var_68], rax
0x18002afc7  xorps   xmm0, xmm0
0x18002afca  mov     [rsp+0C8h+var_7C], r9d
0x18002afcf  mov     eax, ecx
0x18002afd1  mov     r9d, edx
0x18002afd4  mov     [rsp+0C8h+var_80], edx
0x18002afd8  mov     edx, [rsp+0C8h+arg_30]
0x18002afdf  mov     sil, 3
0x18002afe2  mov     r8d, edx
0x18002afe5  mov     [rsp+0C8h+var_88], ecx
0x18002afe9  add     r8, 10h
0x18002afed  mov     [rsp+0C8h+var_78], 0
0x18002aff6  add     rax, r8
0x18002aff9  mov     [rsp+0C8h+var_58], rdx
0x18002affe  mov     r8d, 0FFFFFFFFh
0x18002b004  mov     [rsp+0C8h+Size], rcx
0x18002b009  movups  [rsp+0C8h+Buffer], xmm0
0x18002b00e  cmp     rax, r8
0x18002b011  jbe     short loc_18002B05A
0x18002b013  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x18002b01a  mov     ebx, 80070216h
0x18002b01f  jz      loc_18002B33D
0x18002b025  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b02c  lea     rax, aIpm2MessagePip_24; "IPM2_MESSAGE_PIPE::WriteMessage failed,"...
0x18002b033  mov     dword ptr [rsp+0C8h+var_A0], ebx; char
0x18002b037  lea     r9, aIpm2MessagePip_20; "IPM2_MESSAGE_PIPE::WriteMessage"
0x18002b03e  mov     r8d, 5F6h; unsigned int
0x18002b044  mov     [rsp+0C8h+var_A8], rax; char *
0x18002b049  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b050  call    PuDbgPrint
0x18002b055  jmp     loc_18002B33D
0x18002b05a  mov     eax, 1
0x18002b05f  lea     r15d, [rdx+10h]
0x18002b063  add     r15d, ecx
0x18002b066  lea     rbp, aIpm2MessagePip_20; "IPM2_MESSAGE_PIPE::WriteMessage"
0x18002b06d  cmp     r15d, 10000h
0x18002b074  lea     r14, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b07b  cmova   r12d, eax
0x18002b07f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002b085  test    sil, al
0x18002b088  mov     [rsp+0C8h+var_84], r12d
0x18002b08d  setnz   cl
0x18002b090  bt      eax, 1Ch
0x18002b094  setb    al
0x18002b097  test    al, cl
0x18002b099  jz      short loc_18002B0CD
0x18002b09b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b0a2  lea     rax, aIpm2MessagePip_26; "IPM2_MESSAGE_PIPE::WriteMessage called "...
0x18002b0a9  mov     [rsp+0C8h+var_90], r15d
0x18002b0ae  mov     r8d, 60Ah; unsigned int
0x18002b0b4  mov     [rsp+0C8h+var_98], edx
0x18002b0b8  mov     rdx, r14; char *
0x18002b0bb  mov     dword ptr [rsp+0C8h+var_A0], r9d; char
0x18002b0c0  mov     r9, rbp; char *
0x18002b0c3  mov     [rsp+0C8h+var_A8], rax; char *
0x18002b0c8  call    PuDbgPrint
0x18002b0cd  mov     r8d, r12d; int
0x18002b0d0  lea     rcx, [rsp+0C8h+var_78]; struct IPM2_MESSAGE_IMP **
0x18002b0d5  mov     rdx, r13; struct IPM2_MESSAGE_PIPE *
0x18002b0d8  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x18002b0dd  mov     rdi, [rsp+0C8h+var_78]
0x18002b0e2  mov     ebx, eax
0x18002b0e4  test    eax, eax
0x18002b0e6  jns     short loc_18002B122
0x18002b0e8  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x18002b0ef  jz      loc_18002B325
0x18002b0f5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b0fc  mov     r9, rbp; char *
0x18002b0ff  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x18002b103  mov     r8d, 613h; unsigned int
0x18002b109  lea     rax, aIpm2MessagePip_14; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x18002b110  mov     rdx, r14; char *
0x18002b113  mov     [rsp+0C8h+var_A8], rax; char *
0x18002b118  call    PuDbgPrint
0x18002b11d  jmp     loc_18002B325
0x18002b122  mov     eax, [rsp+0C8h+var_80]
0x18002b126  mov     dword ptr [rsp+0C8h+Buffer], eax
0x18002b12a  mov     eax, [rsp+0C8h+var_7C]
0x18002b12e  mov     dword ptr [rsp+0C8h+Buffer+8], eax
0x18002b135  mov     dword ptr [rsp+0C8h+Buffer+0Ch], 0
0x18002b140  mov     dword ptr [rsp+0C8h+Buffer+4], r15d
0x18002b145  mov     dword ptr [rdi+0Ch], 1
0x18002b14c  test    r12d, r12d
0x18002b14f  jz      short loc_18002B169
0x18002b151  mov     rdx, [rsp+0C8h+var_68]
0x18002b156  mov     eax, [rsp+0C8h+arg_30]
0x18002b15d  mov     [rdi+18h], rdx
0x18002b161  mov     [rdi+10h], eax
0x18002b164  jmp     loc_18002B214
0x18002b169  mov     edx, r15d; unsigned int
0x18002b16c  mov     rcx, rdi; this
0x18002b16f  call    ?AllocateDataLength@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::AllocateDataLength(ulong)
0x18002b174  mov     ebx, eax
0x18002b176  test    eax, eax
0x18002b178  jns     short loc_18002B1B9
0x18002b17a  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x18002b181  jz      loc_18002B325
0x18002b187  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b18e  mov     r9, rbp; char *
0x18002b191  mov     [rsp+0C8h+var_98], r15d
0x18002b196  mov     r8d, 62Bh; unsigned int
0x18002b19c  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x18002b1a0  mov     rdx, r14; char *
0x18002b1a3  lea     rax, aIpm2MessagePip_16; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x18002b1aa  mov     [rsp+0C8h+var_A8], rax; char *
0x18002b1af  call    PuDbgPrint
0x18002b1b4  jmp     loc_18002B325
0x18002b1b9  cmp     [rsp+0C8h+var_88], 0
0x18002b1be  mov     rax, [rdi+18h]
0x18002b1c2  movups  xmm0, [rsp+0C8h+Buffer]
0x18002b1c7  mov     rbx, [rsp+0C8h+Size]
0x18002b1cc  movdqu  xmmword ptr [rax], xmm0
0x18002b1d0  jz      short loc_18002B1E7
0x18002b1d2  mov     rcx, [rdi+18h]
0x18002b1d6  mov     r8, rbx; Size
0x18002b1d9  mov     rdx, [rsp+0C8h+Src]; Src
0x18002b1de  add     rcx, 10h; void *
0x18002b1e2  call    memcpy_0
0x18002b1e7  cmp     [rsp+0C8h+arg_30], 0
0x18002b1ef  jz      short loc_18002B210
0x18002b1f1  mov     rdx, [rsp+0C8h+var_68]; Src
0x18002b1f6  test    rdx, rdx
0x18002b1f9  jz      short loc_18002B210
0x18002b1fb  mov     rcx, [rdi+18h]
0x18002b1ff  mov     r8, [rsp+0C8h+var_58]; Size
0x18002b204  add     rcx, 10h
0x18002b208  add     rcx, rbx; void *
0x18002b20b  call    memcpy_0
0x18002b210  mov     [rdi+10h], r15d
0x18002b214  lea     rcx, [r13+10h]; this
0x18002b218  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002b21d  lea     r12, [r13+8]
0x18002b221  mov     rcx, r12; this
0x18002b224  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18002b229  mov     rcx, [r13+20h]; hFile
0x18002b22d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b231  jnz     short loc_18002B245
0x18002b233  mov     rcx, r12; this
0x18002b236  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002b23b  mov     ebx, 8007006Dh
0x18002b240  jmp     loc_18002B325
0x18002b245  cmp     [rsp+0C8h+var_84], 0
0x18002b24a  jz      short loc_18002B2A5
0x18002b24c  lea     r15, [rdi+38h]
0x18002b250  mov     r8d, 10h; unsigned int
0x18002b256  mov     r9, r15; struct _OVERLAPPED *
0x18002b259  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x18002b25e  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x18002b263  mov     ebx, eax
0x18002b265  test    eax, eax
0x18002b267  js      short loc_18002B2C9
0x18002b269  mov     eax, [rsp+0C8h+var_88]
0x18002b26d  test    eax, eax
0x18002b26f  jz      short loc_18002B28B
0x18002b271  mov     rdx, [rsp+0C8h+Src]; lpBuffer
0x18002b276  mov     r9, r15; struct _OVERLAPPED *
0x18002b279  mov     rcx, [r13+20h]; hFile
0x18002b27d  mov     r8d, eax; unsigned int
0x18002b280  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x18002b285  mov     ebx, eax
0x18002b287  test    eax, eax
0x18002b289  js      short loc_18002B2C9
0x18002b28b  mov     r8d, [rsp+0C8h+arg_30]; unsigned int
0x18002b293  mov     r9, r15; struct _OVERLAPPED *
0x18002b296  mov     rdx, [rdi+18h]; lpBuffer
0x18002b29a  mov     rcx, [r13+20h]; hFile
0x18002b29e  call    ?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)
0x18002b2a3  jmp     short loc_18002B2C7
0x18002b2a5  mov     rax, [rdi]
0x18002b2a8  mov     rcx, rdi
0x18002b2ab  mov     rax, [rax]
0x18002b2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2b3  mov     rdx, [rdi+18h]; lpBuffer
0x18002b2b7  lea     r9, [rdi+38h]; lpOverlapped
0x18002b2bb  mov     rcx, [r13+20h]; hFile
0x18002b2bf  mov     r8d, r15d; nNumberOfBytesToWrite
0x18002b2c2  call    ?Ipm2WriteFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2WriteFile(void *,void *,ulong,_OVERLAPPED *)
0x18002b2c7  mov     ebx, eax
0x18002b2c9  mov     rcx, r12; this
0x18002b2cc  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002b2d1  lea     rcx, [r13+10h]; this
0x18002b2d5  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002b2da  test    ebx, ebx
0x18002b2dc  jns     short loc_18002B325
0x18002b2de  test    byte ptr cs:g_dwDebugFlagsIISUtil, sil
0x18002b2e5  jz      short loc_18002B30F
0x18002b2e7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b2ee  lea     rax, aIpm2MessagePip_22; "IPM2_MESSAGE_PIPE::WriteMessage failed "...
0x18002b2f5  mov     dword ptr [rsp+0C8h+var_A0], ebx; char
0x18002b2f9  mov     r9, rbp; char *
0x18002b2fc  mov     r8d, 689h; unsigned int
0x18002b302  mov     [rsp+0C8h+var_A8], rax; char *
0x18002b307  mov     rdx, r14; char *
0x18002b30a  call    PuDbgPrint
0x18002b30f  cmp     [rsp+0C8h+var_84], 0
0x18002b314  jnz     short loc_18002B325
0x18002b316  mov     rax, [rdi]
0x18002b319  mov     rcx, rdi
0x18002b31c  mov     rax, [rax+8]
0x18002b320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b325  test    rdi, rdi
0x18002b328  jz      short loc_18002B339
0x18002b32a  mov     rax, [rdi]
0x18002b32d  mov     rcx, rdi
0x18002b330  mov     rax, [rax+8]
0x18002b334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b339  test    ebx, ebx
0x18002b33b  jns     short loc_18002B347
0x18002b33d  mov     edx, ebx; int
0x18002b33f  mov     rcx, r13; this
0x18002b342  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x18002b347  mov     eax, ebx
0x18002b349  mov     rcx, [rsp+0C8h+var_40]
0x18002b351  xor     rcx, rsp; StackCookie
0x18002b354  call    __security_check_cookie
0x18002b359  mov     rbx, [rsp+0C8h+arg_10]
0x18002b361  add     rsp, 90h
0x18002b368  pop     r15
0x18002b36a  pop     r14
0x18002b36c  pop     r13
0x18002b36e  pop     r12
0x18002b370  pop     rdi
0x18002b371  pop     rsi
0x18002b372  pop     rbp
0x18002b373  retn
```
