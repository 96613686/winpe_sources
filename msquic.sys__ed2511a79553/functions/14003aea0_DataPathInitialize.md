# DataPathInitialize

- ea: `0x14003aea0`
- end: `0x14003b3a6`
- name: `DataPathInitialize`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140034d44`

## callees

- `0x1400394fc`
- `0x140039854`
- `0x14003aea0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ed00`

## import_xrefs

- `NETIO!WskRegister` at `0x14003b17d`
- `NETIO!WskRegister` at `0x14003b17d`
- `NETIO!WskDeregister` at `0x14003b290`
- `NETIO!WskDeregister` at `0x14003b290`
- `NETIO!WskCaptureProviderNPI` at `0x14003b1bd`
- `NETIO!WskCaptureProviderNPI` at `0x14003b1bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b361`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b361`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2bb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2d1`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2e7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2fd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b313`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b329`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b33f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2bb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2d1`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2e7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b2fd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b313`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b329`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b33f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003afef`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b02d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b06b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b0a4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b0dd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b116`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b14f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003afef`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b02d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b06b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b0a4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b0dd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b116`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b14f`
- `ntoskrnl!ExAllocatePool2` at `0x14003af32`
- `ntoskrnl!ExAllocatePool2` at `0x14003af32`

## string_xrefs

- `0x14003af52`: `CXPLAT_DATAPATH`

## pseudocode

```c
__int64 __fastcall DataPathInitialize(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  _QWORD *v6; // r15
  unsigned int v7; // edi
  unsigned int v9; // ebp
  size_t v10; // rbp
  char *Pool2; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  char *v14; // rsi
  int v15; // eax
  unsigned int v16; // ebp
  __int64 v17; // rbx
  NTSTATUS v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // r14
  NTSTATUS v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  const char *v25; // r9
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rbx
  _QWORD v31[2]; // [rsp+50h] [rbp-48h] BYREF
  _WSK_CLIENT_NPI WskClientNpi; // [rsp+60h] [rbp-38h] BYREF
  int v33; // [rsp+A0h] [rbp+8h] BYREF

  v6 = a6;
  v7 = 0;
  WskClientNpi.Dispatch = (const WSK_CLIENT_DISPATCH *)WskAppDispatch;
  WskClientNpi.ClientContext = 0;
  v31[0] = &NPI_WSK_INTERFACE_ID;
  v31[1] = 256;
  v33 = 1;
  if ( !a6 || a2 && (!*a2 || !a2[1]) )
    return (unsigned int)-1073741811;
  v10 = (unsigned int)(688 * CxPlatProcessorCount + 144);
  Pool2 = (char *)ExAllocatePool2(66, v10, 1110598481);
  v14 = Pool2;
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v13, v12, "CXPLAT_DATAPATH", (unsigned int)v10);
    return (unsigned int)-1073741801;
  }
  memset(Pool2, 0, v10);
  if ( a2 )
    *(_OWORD *)v14 = *(_OWORD *)a2;
  v15 = CxPlatProcessorCount;
  *((_QWORD *)v14 + 14) = CxPlatDataPathSocketReceive;
  v16 = 0;
  *((_DWORD *)v14 + 30) = 96;
  *((_DWORD *)v14 + 32) = v15;
  for ( *((_DWORD *)v14 + 31) = 144; v16 < *((_DWORD *)v14 + 32); *(_QWORD *)&v14[v17 + 816] = 0 )
  {
    v17 = 688LL * v16;
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 144],
      0,
      0,
      (POOL_TYPE)512,
      0,
      0x180u,
      0x41316351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 240],
      CxPlatSendBufferPoolAlloc,
      0,
      (POOL_TYPE)512,
      0,
      0x6A8u,
      0x36306351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 336],
      CxPlatSendBufferPoolAlloc,
      0,
      (POOL_TYPE)512,
      0,
      0xF0E8u,
      0x36306351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 432],
      0,
      0,
      (POOL_TYPE)512,
      0,
      0x120u,
      0x36306351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 528],
      0,
      0,
      (POOL_TYPE)512,
      0,
      0x2490u,
      0x36306351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 624],
      0,
      0,
      (POOL_TYPE)512,
      0,
      0x1010u,
      0x36306351u,
      0x400u);
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)&v14[v17 + 720],
      0,
      0,
      (POOL_TYPE)512,
      0,
      0x10010u,
      0x36306351u,
      0x400u);
    ++v16;
  }
  v18 = WskRegister(&WskClientNpi, (PWSK_REGISTRATION)v14 + 3);
  v9 = v18;
  if ( v18 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) != 0 )
      McTemplateU0qs_EtwWriteTransfer(v20, v19, (unsigned int)v18, "WskRegister");
    goto LABEL_28;
  }
  v21 = v14 + 96;
  v22 = WskCaptureProviderNPI((PWSK_REGISTRATION)v14 + 3, 0xFFFFFFFF, (PWSK_PROVIDER_NPI)v14 + 6);
  v9 = v22;
  if ( v22 >= 0 )
  {
    v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)v14 + 13) + 24LL))(
            *v21,
            8,
            4,
            &v33,
            0,
            0,
            0,
            0);
    if ( v26 < 0 && (Microsoft_QuicEnableBits & 4) != 0 )
      McTemplateU0qs_EtwWriteTransfer(v28, v27, (unsigned int)v26, "WskControlClient WSK_TDI_BEHAVIOR");
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD *, _QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)v14 + 13) + 24LL))(
            *v21,
            7,
            16,
            v31,
            0,
            0,
            0,
            0);
    v9 = v22;
    if ( v22 >= 0 )
    {
      CxPlatDataPathQueryRssScalabilityInfo(v14);
      CxPlatDataPathQuerySockoptSupport(v14, a5);
      *v6 = v14;
      return v9;
    }
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_27;
    v25 = "WskControlClient WSK_SET_STATIC_EVENT_CALLBACKS";
    goto LABEL_26;
  }
  if ( (Microsoft_QuicEnableBits & 4) != 0 )
  {
    v25 = "WskCaptureProviderNPI";
LABEL_26:
    McTemplateU0qs_EtwWriteTransfer(v24, v23, (unsigned int)v22, v25);
  }
LABEL_27:
  WskDeregister((PWSK_REGISTRATION)v14 + 3);
LABEL_28:
  if ( *((_DWORD *)v14 + 32) )
  {
    do
    {
      v29 = 688LL * v7;
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 144]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 240]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 336]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 432]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 528]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 624]);
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&v14[v29 + 720]);
      ++v7;
    }
    while ( v7 < *((_DWORD *)v14 + 32) );
  }
  ExFreePoolWithTag(v14, 0x42326351u);
  return v9;
}

```

## disassembly

```asm
0x14003aea0  mov     r11, rsp
0x14003aea3  mov     [r11+10h], rbx
0x14003aea7  mov     [r11+18h], rbp
0x14003aeab  mov     [rsp+arg_0], ecx
0x14003aeaf  push    rsi
0x14003aeb0  push    rdi
0x14003aeb1  push    r13
0x14003aeb3  push    r14
0x14003aeb5  push    r15
0x14003aeb7  sub     rsp, 70h
0x14003aebb  mov     r15, [rsp+98h+arg_28]
0x14003aec3  lea     rax, WskAppDispatch
0x14003aeca  xor     edi, edi
0x14003aecc  mov     [r11-30h], rax
0x14003aed0  mov     [r11-38h], rdi
0x14003aed4  lea     rax, NPI_WSK_INTERFACE_ID
0x14003aedb  mov     [r11-48h], rax
0x14003aedf  mov     rbx, rdx
0x14003aee2  mov     qword ptr [r11-40h], 100h
0x14003aeea  mov     dword ptr [r11+8], 1
0x14003aef2  test    r15, r15
0x14003aef5  jnz     short loc_14003AF01
0x14003aef7  mov     ebp, 0C000000Dh
0x14003aefc  jmp     loc_14003B38A
0x14003af01  test    rbx, rbx
0x14003af04  jz      short loc_14003AF11
0x14003af06  cmp     [rdx], rdi
0x14003af09  jz      short loc_14003AEF7
0x14003af0b  cmp     [rdx+8], rdi
0x14003af0f  jz      short loc_14003AEF7
0x14003af11  imul    eax, cs:CxPlatProcessorCount, 2B0h
0x14003af1b  mov     r14d, 90h
0x14003af21  mov     r8d, 42326351h
0x14003af27  lea     ecx, [r14-4Eh]
0x14003af2b  add     eax, r14d
0x14003af2e  mov     edx, eax
0x14003af30  mov     ebp, eax
0x14003af32  call    cs:__imp_ExAllocatePool2
0x14003af39  nop     dword ptr [rax+rax+00h]
0x14003af3e  mov     rsi, rax
0x14003af41  test    rax, rax
0x14003af44  jnz     short loc_14003AF68
0x14003af46  test    cs:Microsoft_QuicEnableBits, 2
0x14003af4d  jz      short loc_14003AF5E
0x14003af4f  mov     r9d, ebp
0x14003af52  lea     r8, aCxplatDatapath; "CXPLAT_DATAPATH"
0x14003af59  call    McTemplateU0sx_EtwWriteTransfer
0x14003af5e  mov     ebp, 0C0000017h
0x14003af63  jmp     loc_14003B38A
0x14003af68  mov     r8, rbp; Size
0x14003af6b  xor     edx, edx; Val
0x14003af6d  mov     rcx, rsi; void *
0x14003af70  call    memset
0x14003af75  test    rbx, rbx
0x14003af78  jz      short loc_14003AF81
0x14003af7a  movups  xmm0, xmmword ptr [rbx]
0x14003af7d  movdqu  xmmword ptr [rsi], xmm0
0x14003af81  mov     eax, cs:CxPlatProcessorCount
0x14003af87  lea     rcx, CxPlatDataPathSocketReceive
0x14003af8e  mov     [rsi+70h], rcx
0x14003af92  mov     ebp, edi
0x14003af94  mov     dword ptr [rsi+78h], 60h ; '`'
0x14003af9b  mov     [rsi+80h], eax
0x14003afa1  mov     [rsi+7Ch], r14d
0x14003afa5  test    eax, eax
0x14003afa7  jz      loc_14003B171
0x14003afad  mov     r13d, 400h
0x14003afb3  mov     r14d, 200h
0x14003afb9  mov     [rsp+98h+Depth], r13w; Depth
0x14003afbf  lea     rcx, [rsi+90h]
0x14003afc6  mov     eax, ebp
0x14003afc8  mov     r9d, r14d; PoolType
0x14003afcb  imul    rbx, rax, 2B0h
0x14003afd2  mov     [rsp+98h+Tag], 41316351h; Tag
0x14003afda  xor     r8d, r8d; Free
0x14003afdd  add     rcx, rbx; Lookaside
0x14003afe0  mov     [rsp+98h+Size], 180h; Size
0x14003afe9  xor     edx, edx; Allocate
0x14003afeb  mov     [rsp+98h+Flags], edi; Flags
0x14003afef  call    cs:__imp_ExInitializeLookasideListEx
0x14003aff6  nop     dword ptr [rax+rax+00h]
0x14003affb  mov     [rsp+98h+Depth], r13w; Depth
0x14003b001  lea     rcx, [rsi+0F0h]
0x14003b008  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b010  lea     rdx, CxPlatSendBufferPoolAlloc; Allocate
0x14003b017  add     rcx, rbx; Lookaside
0x14003b01a  mov     [rsp+98h+Size], 6A8h; Size
0x14003b023  mov     r9d, r14d; PoolType
0x14003b026  mov     [rsp+98h+Flags], edi; Flags
0x14003b02a  xor     r8d, r8d; Free
0x14003b02d  call    cs:__imp_ExInitializeLookasideListEx
0x14003b034  nop     dword ptr [rax+rax+00h]
0x14003b039  mov     [rsp+98h+Depth], r13w; Depth
0x14003b03f  lea     rcx, [rsi+150h]
0x14003b046  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b04e  lea     rdx, CxPlatSendBufferPoolAlloc; Allocate
0x14003b055  add     rcx, rbx; Lookaside
0x14003b058  mov     [rsp+98h+Size], 0F0E8h; Size
0x14003b061  mov     r9d, r14d; PoolType
0x14003b064  mov     [rsp+98h+Flags], edi; Flags
0x14003b068  xor     r8d, r8d; Free
0x14003b06b  call    cs:__imp_ExInitializeLookasideListEx
0x14003b072  nop     dword ptr [rax+rax+00h]
0x14003b077  mov     [rsp+98h+Depth], r13w; Depth
0x14003b07d  lea     rcx, [rsi+1B0h]
0x14003b084  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b08c  add     rcx, rbx; Lookaside
0x14003b08f  mov     [rsp+98h+Size], 120h; Size
0x14003b098  mov     r9d, r14d; PoolType
0x14003b09b  xor     r8d, r8d; Free
0x14003b09e  mov     [rsp+98h+Flags], edi; Flags
0x14003b0a2  xor     edx, edx; Allocate
0x14003b0a4  call    cs:__imp_ExInitializeLookasideListEx
0x14003b0ab  nop     dword ptr [rax+rax+00h]
0x14003b0b0  mov     [rsp+98h+Depth], r13w; Depth
0x14003b0b6  lea     rcx, [rsi+210h]
0x14003b0bd  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b0c5  add     rcx, rbx; Lookaside
0x14003b0c8  mov     [rsp+98h+Size], 2490h; Size
0x14003b0d1  mov     r9d, r14d; PoolType
0x14003b0d4  xor     r8d, r8d; Free
0x14003b0d7  mov     [rsp+98h+Flags], edi; Flags
0x14003b0db  xor     edx, edx; Allocate
0x14003b0dd  call    cs:__imp_ExInitializeLookasideListEx
0x14003b0e4  nop     dword ptr [rax+rax+00h]
0x14003b0e9  mov     [rsp+98h+Depth], r13w; Depth
0x14003b0ef  lea     rcx, [rsi+270h]
0x14003b0f6  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b0fe  add     rcx, rbx; Lookaside
0x14003b101  mov     [rsp+98h+Size], 1010h; Size
0x14003b10a  mov     r9d, r14d; PoolType
0x14003b10d  xor     r8d, r8d; Free
0x14003b110  mov     [rsp+98h+Flags], edi; Flags
0x14003b114  xor     edx, edx; Allocate
0x14003b116  call    cs:__imp_ExInitializeLookasideListEx
0x14003b11d  nop     dword ptr [rax+rax+00h]
0x14003b122  mov     [rsp+98h+Depth], r13w; Depth
0x14003b128  lea     rcx, [rsi+2D0h]
0x14003b12f  mov     [rsp+98h+Tag], 36306351h; Tag
0x14003b137  add     rcx, rbx; Lookaside
0x14003b13a  mov     [rsp+98h+Size], 10010h; Size
0x14003b143  mov     r9d, r14d; PoolType
0x14003b146  xor     r8d, r8d; Free
0x14003b149  mov     [rsp+98h+Flags], edi; Flags
0x14003b14d  xor     edx, edx; Allocate
0x14003b14f  call    cs:__imp_ExInitializeLookasideListEx
0x14003b156  nop     dword ptr [rax+rax+00h]
0x14003b15b  inc     ebp
0x14003b15d  mov     [rbx+rsi+330h], rdi
0x14003b165  cmp     ebp, [rsi+80h]
0x14003b16b  jb      loc_14003AFB9
0x14003b171  lea     rbx, [rsi+48h]
0x14003b175  mov     rdx, rbx; WskRegistration
0x14003b178  lea     rcx, [rsp+98h+WskClientNpi]; WskClientNpi
0x14003b17d  call    cs:__imp_WskRegister
0x14003b184  nop     dword ptr [rax+rax+00h]
0x14003b189  mov     ebp, eax
0x14003b18b  test    eax, eax
0x14003b18d  jns     short loc_14003B1B0
0x14003b18f  test    cs:Microsoft_QuicEnableBits, 4
0x14003b196  jz      loc_14003B29C
0x14003b19c  lea     r9, aWskregister; "WskRegister"
0x14003b1a3  mov     r8d, eax
0x14003b1a6  call    McTemplateU0qs_EtwWriteTransfer
0x14003b1ab  jmp     loc_14003B29C
0x14003b1b0  lea     r14, [rsi+60h]
0x14003b1b4  or      edx, 0FFFFFFFFh; WaitTimeout
0x14003b1b7  mov     r8, r14; WskProviderNpi
0x14003b1ba  mov     rcx, rbx; WskRegistration
0x14003b1bd  call    cs:__imp_WskCaptureProviderNPI
0x14003b1c4  nop     dword ptr [rax+rax+00h]
0x14003b1c9  mov     ebp, eax
0x14003b1cb  test    eax, eax
0x14003b1cd  jns     short loc_14003B1E8
0x14003b1cf  test    cs:Microsoft_QuicEnableBits, 4
0x14003b1d6  jz      loc_14003B28D
0x14003b1dc  lea     r9, aWskcaptureprov; "WskCaptureProviderNPI"
0x14003b1e3  jmp     loc_14003B285
0x14003b1e8  mov     rax, [rsi+68h]
0x14003b1ec  lea     r9, [rsp+98h+arg_0]
0x14003b1f4  mov     rcx, [r14]
0x14003b1f7  mov     edx, 8
0x14003b1fc  mov     qword ptr [rsp+98h+Depth], rdi
0x14003b201  mov     qword ptr [rsp+98h+Tag], rdi
0x14003b206  mov     rax, [rax+18h]
0x14003b20a  lea     r8d, [rdx-4]
0x14003b20e  mov     [rsp+98h+Size], rdi
0x14003b213  mov     qword ptr [rsp+98h+Flags], rdi
0x14003b218  call    _guard_dispatch_icall
0x14003b21d  test    eax, eax
0x14003b21f  jns     short loc_14003B239
0x14003b221  test    cs:Microsoft_QuicEnableBits, 4
0x14003b228  jz      short loc_14003B239
0x14003b22a  lea     r9, aWskcontrolclie_0; "WskControlClient WSK_TDI_BEHAVIOR"
0x14003b231  mov     r8d, eax
0x14003b234  call    McTemplateU0qs_EtwWriteTransfer
0x14003b239  mov     rax, [rsi+68h]
0x14003b23d  lea     r9, [rsp+98h+var_48]
0x14003b242  mov     rcx, [r14]
0x14003b245  mov     edx, 7
0x14003b24a  mov     qword ptr [rsp+98h+Depth], rdi
0x14003b24f  mov     qword ptr [rsp+98h+Tag], rdi
0x14003b254  mov     rax, [rax+18h]
0x14003b258  lea     r8d, [rdx+9]
0x14003b25c  mov     [rsp+98h+Size], rdi
0x14003b261  mov     qword ptr [rsp+98h+Flags], rdi
0x14003b266  call    _guard_dispatch_icall
0x14003b26b  mov     ebp, eax
0x14003b26d  test    eax, eax
0x14003b26f  jns     loc_14003B36F
0x14003b275  test    cs:Microsoft_QuicEnableBits, 4
0x14003b27c  jz      short loc_14003B28D
0x14003b27e  lea     r9, aWskcontrolclie; "WskControlClient WSK_SET_STATIC_EVENT_C"...
0x14003b285  mov     r8d, eax
0x14003b288  call    McTemplateU0qs_EtwWriteTransfer
0x14003b28d  mov     rcx, rbx; WskRegistration
0x14003b290  call    cs:__imp_WskDeregister
0x14003b297  nop     dword ptr [rax+rax+00h]
0x14003b29c  cmp     [rsi+80h], edi
0x14003b2a2  jbe     loc_14003B359
0x14003b2a8  mov     eax, edi
0x14003b2aa  lea     rcx, [rsi+90h]
0x14003b2b1  imul    rbx, rax, 2B0h
0x14003b2b8  add     rcx, rbx; Lookaside
0x14003b2bb  call    cs:__imp_ExDeleteLookasideListEx
0x14003b2c2  nop     dword ptr [rax+rax+00h]
0x14003b2c7  lea     rcx, [rsi+0F0h]
0x14003b2ce  add     rcx, rbx; Lookaside
0x14003b2d1  call    cs:__imp_ExDeleteLookasideListEx
0x14003b2d8  nop     dword ptr [rax+rax+00h]
0x14003b2dd  lea     rcx, [rsi+150h]
0x14003b2e4  add     rcx, rbx; Lookaside
0x14003b2e7  call    cs:__imp_ExDeleteLookasideListEx
0x14003b2ee  nop     dword ptr [rax+rax+00h]
0x14003b2f3  lea     rcx, [rsi+1B0h]
0x14003b2fa  add     rcx, rbx; Lookaside
0x14003b2fd  call    cs:__imp_ExDeleteLookasideListEx
0x14003b304  nop     dword ptr [rax+rax+00h]
0x14003b309  lea     rcx, [rsi+210h]
0x14003b310  add     rcx, rbx; Lookaside
0x14003b313  call    cs:__imp_ExDeleteLookasideListEx
0x14003b31a  nop     dword ptr [rax+rax+00h]
0x14003b31f  lea     rcx, [rsi+270h]
0x14003b326  add     rcx, rbx; Lookaside
0x14003b329  call    cs:__imp_ExDeleteLookasideListEx
0x14003b330  nop     dword ptr [rax+rax+00h]
0x14003b335  lea     rcx, [rsi+2D0h]
0x14003b33c  add     rcx, rbx; Lookaside
0x14003b33f  call    cs:__imp_ExDeleteLookasideListEx
0x14003b346  nop     dword ptr [rax+rax+00h]
0x14003b34b  inc     edi
0x14003b34d  cmp     edi, [rsi+80h]
0x14003b353  jb      loc_14003B2A8
0x14003b359  mov     edx, 42326351h; Tag
0x14003b35e  mov     rcx, rsi; P
0x14003b361  call    cs:__imp_ExFreePoolWithTag
0x14003b368  nop     dword ptr [rax+rax+00h]
0x14003b36d  jmp     short loc_14003B38A
0x14003b36f  mov     rcx, rsi
0x14003b372  call    CxPlatDataPathQueryRssScalabilityInfo
0x14003b377  mov     rdx, [rsp+98h+arg_20]
0x14003b37f  mov     rcx, rsi
0x14003b382  call    CxPlatDataPathQuerySockoptSupport
0x14003b387  mov     [r15], rsi
0x14003b38a  lea     r11, [rsp+98h+var_28]
0x14003b38f  mov     eax, ebp
0x14003b391  mov     rbx, [r11+38h]
0x14003b395  mov     rbp, [r11+40h]
0x14003b399  mov     rsp, r11
0x14003b39c  pop     r15
0x14003b39e  pop     r14
0x14003b3a0  pop     r13
0x14003b3a2  pop     rdi
0x14003b3a3  pop     rsi
0x14003b3a4  retn
```
