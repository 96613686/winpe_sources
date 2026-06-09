# MsgBase::Send(ulong)

- ea: `0x18000fcf0`
- end: `0x1800100ae`
- name: `?Send@MsgBase@@QEAAJK@Z`
- size: `958`
- prototype: `__int64 __fastcall(MsgBase *__hidden this, unsigned int)`
- caller_count: `18`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb3c`
- `0x18000e6a4`
- `0x18000e8c4`
- `0x18000e960`
- `0x18000fb50`
- `0x180019180`
- `0x180019cfc`
- `0x18001ea24`
- `0x18001ea90`
- `0x180024ad0`
- `0x18002d958`
- `0x18002ef30`
- `0x180055800`
- `0x18007750c`
- `0x18007a034`
- `0x180082e90`
- `0x180087b5c`
- `0x180087ba4`

## callees

- `0x18000e160`
- `0x18000f450`
- `0x18000fcf0`
- `0x18002dae0`
- `0x180043548`
- `0x18005ba10`
- `0x1800831b8`
- `0x180087ba4`
- `0x18008ced0`
- `0x1800b4434`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!NtAlpcDeletePortSection` at `0x18000fdb5`
- `ntdll!NtAlpcDeletePortSection` at `0x18000fdb5`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fd90`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fec6`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fd90`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000fec6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fd2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fee2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fd2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fee2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ff6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ff6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001002a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001002a`

## pseudocode

```c
__int64 __fastcall MsgBase::Send(MsgBase *this)
{
  unsigned int v2; // ebp
  struct tagSYSTHREAD *SYSTHREAD; // rbx
  int v4; // ecx
  int v6; // esi
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  struct _ALPC_MESSAGE_ATTRIBUTES *v11; // r14
  int v12; // r8d
  __int64 v13; // r8
  _DWORD *v14; // rcx
  tagSYSTHREAD **v15; // rax
  CCtfClientPort *v16; // rsi
  struct _ALPC_MESSAGE_ATTRIBUTES *MessageAttributes; // rax
  void *v18; // [rsp+40h] [rbp-98h] BYREF
  __int64 v19; // [rsp+48h] [rbp-90h] BYREF
  __int64 v20; // [rsp+50h] [rbp-88h] BYREF
  _QWORD v21[3]; // [rsp+60h] [rbp-78h] BYREF
  int v22; // [rsp+78h] [rbp-60h]
  int v23; // [rsp+80h] [rbp-58h]
  int v24; // [rsp+88h] [rbp-50h]
  int v25; // [rsp+8Ch] [rbp-4Ch]
  int v26; // [rsp+90h] [rbp-48h]
  int v27; // [rsp+94h] [rbp-44h]
  int v28; // [rsp+98h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+A0h] [rbp-38h] BYREF

  v2 = -2147467259;
  SYSTHREAD = GetSYSTHREAD();
  if ( !SYSTHREAD || g_dwTLSIndexForFLS == -1 || TlsGetValue(g_dwTLSIndexForFLS) )
    return 2147500037LL;
  v8 = *((_QWORD *)SYSTHREAD + 7);
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 48));
  }
  else
  {
    v15 = (tagSYSTHREAD **)LocalAlloc(0x40u, 0x50u);
    v16 = (CCtfClientPort *)v15;
    if ( v15 )
    {
      v15[5] = SYSTHREAD;
      ++*((_DWORD *)SYSTHREAD + 87);
      v15[1] = 0;
      v15[2] = 0;
      v15[3] = 0;
      v15[4] = 0;
      *v15 = (tagSYSTHREAD *)&CCtfClientPort::`vftable';
      *((_DWORD *)v15 + 12) = 1;
      v15[7] = (tagSYSTHREAD *)&CStructArray<char>::`vftable';
      v15[9] = 0;
      v15[8] = 0;
      tagSYSTHREAD::LockThreadMessageWindow(v15[5]);
      CCtfClientPort::Open(v16);
    }
    else
    {
      v16 = 0;
    }
    *((_QWORD *)SYSTHREAD + 7) = v16;
  }
  v9 = *((_QWORD *)SYSTHREAD + 7);
  if ( v9 )
  {
    if ( !*(_QWORD *)(v9 + 8) )
    {
      if ( g_dwTLSIndexForFLS == -1 )
        goto LABEL_17;
      if ( TlsGetValue(g_dwTLSIndexForFLS) )
        goto LABEL_17;
      v14 = *(_DWORD **)(v9 + 40);
      v21[0] = 4194328;
      v21[1] = 0;
      v21[2] = 0;
      v22 = 0;
      v23 = 0;
      v24 = v14[27];
      v25 = v14[26];
      v26 = v14[28];
      v27 = v14[29];
      v28 = v14[34];
      if ( !CAlpcPort::Open((CAlpcPort *)v9, (struct MsgConnect *)v21, v13) )
        goto LABEL_17;
    }
    v10 = *((_DWORD *)this + 10);
    v11 = 0;
    v18 = 0;
    if ( (v10 & 0x4000000) == 0 )
    {
LABEL_25:
      v12 = *((_DWORD *)this + 10);
      if ( (v12 & 0x1000000) != 0 )
      {
        if ( Microsoft_Windows_TSF_msctfEnableBits < 0 )
          McTemplateU0qqQ4_EventWriteTransfer(
            v4,
            (unsigned int)SendingNotification,
            v12,
            *((_DWORD *)this + 12),
            (__int64)this + 56);
        v6 = NtAlpcSendWaitReceivePort(*(_QWORD *)(v9 + 8), 0x10000, this, v11, 0, 0, 0, 0);
      }
      else
      {
        v20 = *((__int16 *)this + 1);
        v19 = -1000000;
        if ( Microsoft_Windows_TSF_msctfEnableBits < 0 )
          McTemplateU0qqQ4_EventWriteTransfer(
            v4,
            (unsigned int)SendSyncRequest_Start,
            v12,
            *((_DWORD *)this + 12),
            (__int64)this + 56);
        v6 = NtAlpcSendWaitReceivePort(*(_QWORD *)(v9 + 8), 0x20000, this, v11, this, &v20, 0, &v19);
        if ( Microsoft_Windows_TSF_msctfEnableBits < 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_TSF_msctf_Context,
            (const EVENT_DESCRIPTOR *)SendSyncRequest_End,
            v7,
            1u,
            &v29);
      }
      if ( v18 )
      {
        NtAlpcDeletePortSection(*(_QWORD *)(v9 + 8), 0);
        v18 = 0;
      }
      if ( v11 )
        LocalFree(v11);
      if ( v6 == -1073741769 )
      {
        CAlpcPort::Close((CAlpcPort *)v9);
      }
      else if ( v6 >= 0 && v6 != 258 )
      {
        v2 = *((_DWORD *)this + 13);
      }
      goto LABEL_17;
    }
    *((_DWORD *)this + 10) = v10 & 0xFBFFFFFF;
    MessageAttributes = CreateMessageAttributes(0x40000000u);
    v11 = MessageAttributes;
    if ( MessageAttributes )
    {
      if ( (int)CreateDataView(*(void **)(v9 + 8), (const void **)this, MessageAttributes, &v18) >= 0 )
        goto LABEL_25;
      LocalFree(v11);
    }
LABEL_17:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 48), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000fcf0  push    rbx
0x18000fcf2  push    rbp
0x18000fcf3  push    rdi
0x18000fcf4  sub     rsp, 0C0h
0x18000fcfb  mov     rax, cs:__security_cookie
0x18000fd02  xor     rax, rsp
0x18000fd05  mov     [rsp+0D8h+var_28], rax
0x18000fd0d  mov     rdi, rcx
0x18000fd10  mov     ebp, 80004005h
0x18000fd15  call    ?GetSYSTHREAD@@YAPEAUtagSYSTHREAD@@XZ; GetSYSTHREAD(void)
0x18000fd1a  mov     rbx, rax
0x18000fd1d  test    rax, rax
0x18000fd20  jz      short loc_18000FD3C
0x18000fd22  mov     ecx, cs:?g_dwTLSIndexForFLS@@3KA; dwTlsIndex
0x18000fd28  cmp     ecx, 0FFFFFFFFh
0x18000fd2b  jz      short loc_18000FD3C
0x18000fd2d  call    cs:__imp_TlsGetValue
0x18000fd33  test    rax, rax
0x18000fd36  jz      loc_18000FE31
0x18000fd3c  mov     eax, ebp
0x18000fd3e  jmp     loc_18000FE16
0x18000fd43  cmp     cs:Microsoft_Windows_TSF_msctfEnableBits, r15b
0x18000fd4a  movsx   rax, word ptr [rdi+2]
0x18000fd4f  mov     [rsp+0D8h+var_88], rax
0x18000fd54  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFF0BDC0h
0x18000fd5d  jl      loc_180010047
0x18000fd63  mov     rcx, [rbx+8]
0x18000fd67  lea     rax, [rsp+0D8h+var_90]
0x18000fd6c  mov     [rsp+0D8h+var_A0], rax
0x18000fd71  mov     r9, r14
0x18000fd74  lea     rax, [rsp+0D8h+var_88]
0x18000fd79  mov     [rsp+0D8h+var_A8], r15
0x18000fd7e  mov     [rsp+0D8h+var_B0], rax
0x18000fd83  mov     r8, rdi
0x18000fd86  mov     edx, 20000h
0x18000fd8b  mov     [rsp+0D8h+var_B8], rdi
0x18000fd90  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000fd96  cmp     cs:Microsoft_Windows_TSF_msctfEnableBits, r15b
0x18000fd9d  mov     esi, eax
0x18000fd9f  jl      loc_180010065
0x18000fda5  mov     r8, [rsp+0D8h+var_98]
0x18000fdaa  test    r8, r8
0x18000fdad  jz      short loc_18000FDC0
0x18000fdaf  mov     rcx, [rbx+8]
0x18000fdb3  xor     edx, edx
0x18000fdb5  call    cs:__imp_NtAlpcDeletePortSection
0x18000fdbb  mov     [rsp+0D8h+var_98], r15
0x18000fdc0  test    r14, r14
0x18000fdc3  jz      short loc_18000FDCE
0x18000fdc5  mov     rcx, r14; hMem
0x18000fdc8  call    cs:__imp_LocalFree
0x18000fdce  cmp     esi, 0C0000037h
0x18000fdd4  jz      loc_18001003A
0x18000fdda  test    esi, esi
0x18000fddc  js      short loc_18000FDE9
0x18000fdde  cmp     esi, 102h
0x18000fde4  jz      short loc_18000FDE9
0x18000fde6  mov     ebp, [rdi+34h]
0x18000fde9  mov     ecx, 0FFFFFFFFh
0x18000fdee  lock xadd [rbx+30h], ecx
0x18000fdf3  cmp     ecx, 1
0x18000fdf6  jz      loc_18000FFD6
0x18000fdfc  mov     rsi, [rsp+0D8h+arg_8]
0x18000fe04  mov     eax, ebp
0x18000fe06  mov     r14, [rsp+0D8h+arg_10]
0x18000fe0e  mov     r15, [rsp+0D8h+arg_18]
0x18000fe16  mov     rcx, [rsp+0D8h+var_28]
0x18000fe1e  xor     rcx, rsp; StackCookie
0x18000fe21  call    __security_check_cookie
0x18000fe26  add     rsp, 0C0h
0x18000fe2d  pop     rdi
0x18000fe2e  pop     rbp
0x18000fe2f  pop     rbx
0x18000fe30  retn
0x18000fe31  mov     rax, [rbx+38h]
0x18000fe35  mov     [rsp+0D8h+arg_10], r14
0x18000fe3d  mov     r14d, 40h ; '@'
0x18000fe43  mov     [rsp+0D8h+arg_18], r15
0x18000fe4b  xor     r15d, r15d
0x18000fe4e  mov     [rsp+0D8h+arg_8], rsi
0x18000fe56  test    rax, rax
0x18000fe59  jz      loc_18000FF64
0x18000fe5f  lock inc dword ptr [rax+30h]
0x18000fe63  mov     rbx, [rbx+38h]
0x18000fe67  test    rbx, rbx
0x18000fe6a  jz      short loc_18000FDFC
0x18000fe6c  cmp     [rbx+8], r15
0x18000fe70  jz      short loc_18000FED3
0x18000fe72  mov     eax, [rdi+28h]
0x18000fe75  mov     r14, r15
0x18000fe78  mov     [rsp+0D8h+var_98], r15
0x18000fe7d  bt      eax, 1Ah
0x18000fe81  jb      loc_18000FFEE
0x18000fe87  mov     r8d, [rdi+28h]
0x18000fe8b  bt      r8d, 18h
0x18000fe90  jnb     loc_18000FD43
0x18000fe96  cmp     cs:Microsoft_Windows_TSF_msctfEnableBits, r15b
0x18000fe9d  jl      loc_180010090
0x18000fea3  mov     rcx, [rbx+8]
0x18000fea7  mov     r9, r14
0x18000feaa  mov     [rsp+0D8h+var_A0], r15
0x18000feaf  mov     r8, rdi
0x18000feb2  mov     [rsp+0D8h+var_A8], r15
0x18000feb7  mov     edx, 10000h
0x18000febc  mov     [rsp+0D8h+var_B0], r15
0x18000fec1  mov     [rsp+0D8h+var_B8], r15
0x18000fec6  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000fecc  mov     esi, eax
0x18000fece  jmp     loc_18000FDA5
0x18000fed3  mov     ecx, cs:?g_dwTLSIndexForFLS@@3KA; dwTlsIndex
0x18000fed9  cmp     ecx, 0FFFFFFFFh
0x18000fedc  jz      loc_18000FDE9
0x18000fee2  call    cs:__imp_TlsGetValue
0x18000fee8  test    rax, rax
0x18000feeb  jnz     loc_18000FDE9
0x18000fef1  mov     rcx, [rbx+28h]
0x18000fef5  lea     rdx, [rsp+0D8h+var_78]; struct MsgConnect *
0x18000fefa  mov     [rsp+0D8h+var_78], 400018h
0x18000ff03  mov     [rsp+0D8h+var_70], r15
0x18000ff08  mov     [rsp+0D8h+var_68], r15
0x18000ff0d  mov     [rsp+0D8h+var_60], r15d
0x18000ff12  mov     [rsp+0D8h+var_58], r15d
0x18000ff1a  mov     eax, [rcx+6Ch]
0x18000ff1d  mov     [rsp+0D8h+var_50], eax
0x18000ff24  mov     eax, [rcx+68h]
0x18000ff27  mov     [rsp+0D8h+var_4C], eax
0x18000ff2e  mov     eax, [rcx+70h]
0x18000ff31  mov     [rsp+0D8h+var_48], eax
0x18000ff38  mov     eax, [rcx+74h]
0x18000ff3b  mov     [rsp+0D8h+var_44], eax
0x18000ff42  mov     eax, [rcx+88h]
0x18000ff48  mov     rcx, rbx; this
0x18000ff4b  mov     [rsp+0D8h+var_40], eax
0x18000ff52  call    ?Open@CAlpcPort@@QEAA_NPEAUMsgConnect@@@Z; CAlpcPort::Open(MsgConnect *)
0x18000ff57  test    al, al
0x18000ff59  jnz     loc_18000FE72
0x18000ff5f  jmp     loc_18000FDE9
0x18000ff64  mov     edx, 50h ; 'P'; uBytes
0x18000ff69  mov     ecx, r14d; uFlags
0x18000ff6c  call    cs:__imp_LocalAlloc
0x18000ff72  mov     rsi, rax
0x18000ff75  test    rax, rax
0x18000ff78  jz      loc_180010035
0x18000ff7e  mov     [rax+28h], rbx
0x18000ff82  inc     dword ptr [rbx+15Ch]
0x18000ff88  mov     [rax+8], r15
0x18000ff8c  mov     [rax+10h], r15
0x18000ff90  mov     [rax+18h], r15
0x18000ff94  mov     [rax+20h], r15
0x18000ff98  lea     rax, ??_7CCtfClientPort@@6B@; const CCtfClientPort::`vftable'
0x18000ff9f  mov     [rsi], rax
0x18000ffa2  lea     rax, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x18000ffa9  mov     dword ptr [rsi+30h], 1
0x18000ffb0  mov     [rsi+38h], rax
0x18000ffb4  mov     [rsi+48h], r15
0x18000ffb8  mov     [rsi+40h], r15
0x18000ffbc  mov     rcx, [rsi+28h]; this
0x18000ffc0  call    ?LockThreadMessageWindow@tagSYSTHREAD@@QEAAPEAUHWND__@@XZ; tagSYSTHREAD::LockThreadMessageWindow(void)
0x18000ffc5  mov     rcx, rsi; this
0x18000ffc8  call    ?Open@CCtfClientPort@@QEAA_NXZ; CCtfClientPort::Open(void)
0x18000ffcd  mov     [rbx+38h], rsi
0x18000ffd1  jmp     loc_18000FE63
0x18000ffd6  mov     rcx, [rbx]
0x18000ffd9  mov     edx, 1
0x18000ffde  mov     rax, [rcx]
0x18000ffe1  mov     rcx, rbx
0x18000ffe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe9  jmp     loc_18000FDFC
0x18000ffee  btr     eax, 1Ah
0x18000fff2  mov     ecx, 40000000h; unsigned int
0x18000fff7  mov     [rdi+28h], eax
0x18000fffa  call    ?CreateMessageAttributes@@YAPEAU_ALPC_MESSAGE_ATTRIBUTES@@K@Z; CreateMessageAttributes(ulong)
0x18000ffff  mov     r14, rax
0x180010002  test    rax, rax
0x180010005  jz      loc_18000FDE9
0x18001000b  mov     rcx, [rbx+8]; void *
0x18001000f  lea     r9, [rsp+0D8h+var_98]; void **
0x180010014  mov     r8, rax; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180010017  mov     rdx, rdi; struct MsgBase *
0x18001001a  call    ?CreateDataView@@YAJPEAXPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@AEAPEAX@Z; CreateDataView(void *,MsgBase *,_ALPC_MESSAGE_ATTRIBUTES *,void * &)
0x18001001f  test    eax, eax
0x180010021  jns     loc_18000FE87
0x180010027  mov     rcx, r14; hMem
0x18001002a  call    cs:__imp_LocalFree
0x180010030  jmp     loc_18000FDE9
0x180010035  mov     rsi, r15
0x180010038  jmp     short loc_18000FFCD
0x18001003a  mov     rcx, rbx; this
0x18001003d  call    ?Close@CAlpcPort@@QEAAXXZ; CAlpcPort::Close(void)
0x180010042  jmp     loc_18000FDE9
0x180010047  mov     r9d, [rdi+30h]
0x18001004b  lea     rax, [rdi+38h]
0x18001004f  lea     rdx, SendSyncRequest_Start
0x180010056  mov     [rsp+0D8h+var_B8], rax
0x18001005b  call    McTemplateU0qqQ4_EventWriteTransfer
0x180010060  jmp     loc_18000FD63
0x180010065  lea     rax, [rsp+0D8h+var_38]
0x18001006d  mov     r9d, 1
0x180010073  lea     rdx, SendSyncRequest_End
0x18001007a  mov     [rsp+0D8h+var_B8], rax
0x18001007f  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x180010086  call    McGenEventWrite_EventWriteTransfer
0x18001008b  jmp     loc_18000FDA5
0x180010090  mov     r9d, [rdi+30h]
0x180010094  lea     rax, [rdi+38h]
0x180010098  lea     rdx, SendingNotification
0x18001009f  mov     [rsp+0D8h+var_B8], rax
0x1800100a4  call    McTemplateU0qqQ4_EventWriteTransfer
0x1800100a9  jmp     loc_18000FEA3
```
