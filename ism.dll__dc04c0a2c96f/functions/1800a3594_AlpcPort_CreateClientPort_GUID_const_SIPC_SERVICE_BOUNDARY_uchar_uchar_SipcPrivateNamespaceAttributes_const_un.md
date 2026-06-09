# AlpcPort::CreateClientPort(_GUID const &,SIPC_SERVICE_BOUNDARY,uchar,uchar,SipcPrivateNamespaceAttributes const &,unsigned __int64,ushort,void *,uint *,SipcPort * *)

- ea: `0x1800a3594`
- end: `0x1800a39fa`
- name: `?CreateClientPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@EEAEBUSipcPrivateNamespaceAttributes@@_KGPEAXPEAIPEAPEAVSipcPort@@@Z`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1801433e0`

## callees

- `0x180078344`
- `0x1800a3594`
- `0x1800a3a00`
- `0x1800a43b0`
- `0x1800a99f0`
- `0x1800a9da4`
- `0x1800abe04`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f2448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3903`
- `ntdll!NtAlpcConnectPort` at `0x1800a38ba`
- `ntdll!NtAlpcConnectPort` at `0x1800a38ba`
- `ntdll!NtDelayExecution` at `0x1800a38f8`
- `ntdll!NtDelayExecution` at `0x1800a38f8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a3795`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a3795`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a373b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a373b`

## pseudocode

```c
__int64 __fastcall AlpcPort::CreateClientPort(
        LARGE_INTEGER a1,
        unsigned int a2,
        char a3,
        char a4,
        __int128 *a5,
        unsigned __int64 a6,
        unsigned __int16 a7,
        __int64 a8,
        unsigned int *a9,
        AlpcPort **a10)
{
  AlpcPort *v11; // rax
  AlpcPort *v12; // rdi
  int v13; // ebx
  __int128 v14; // xmm6
  __int64 v15; // rbx
  __int128 v16; // xmm7
  __int128 v17; // xmm8
  __int128 v18; // xmm9
  __int128 v19; // xmm10
  __int128 v20; // xmm11
  __int128 v21; // xmm12
  __int128 v22; // xmm13
  __int128 v23; // xmm14
  HANDLE FileW; // rax
  __int128 v25; // xmm1
  __int64 v26; // r8
  LARGE_INTEGER v27; // rdx
  __int128 v28; // xmm0
  __int64 v29; // rax
  __int64 v30; // r13
  int v31; // ebx
  LARGE_INTEGER v32; // rax
  signed int LastError; // eax
  char v35; // [rsp+68h] [rbp-A0h]
  unsigned int v36; // [rsp+6Ch] [rbp-9Ch] BYREF
  AlpcPort *v37; // [rsp+70h] [rbp-98h] BYREF
  DWORD BytesReturned[2]; // [rsp+78h] [rbp-90h] BYREF
  HANDLE v39; // [rsp+80h] [rbp-88h] BYREF
  LARGE_INTEGER Interval; // [rsp+88h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-78h] BYREF
  __int64 OutBuffer; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v43[9]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v44[68]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v45[76]; // [rsp+12Ch] [rbp+24h] BYREF
  int InBuffer; // [rsp+178h] [rbp+70h] BYREF
  __int64 v47; // [rsp+17Ch] [rbp+74h]
  _BYTE v48[192]; // [rsp+188h] [rbp+80h] BYREF

  v36 = a2;
  Interval = a1;
  *a9 = 0;
  *a10 = 0;
  v35 = a4;
  v41 = a8;
  v11 = (AlpcPort *)operator new(0x1F8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 )
    v12 = AlpcPort::AlpcPort(v11, a7);
  else
    v12 = 0;
  v37 = v12;
  if ( v12 )
  {
    v13 = SipcPort::Initialize(v12);
    if ( v13 >= 0 )
    {
      memset(&v43[1], 0, 48);
      memset_0(v44, 0, sizeof(v44));
      memset_0(v45, 0, 0x44u);
      v14 = *a5;
      v15 = *((_QWORD *)a5 + 18);
      v16 = a5[1];
      v17 = a5[2];
      LOBYTE(v43[1]) = 2;
      v18 = a5[3];
      BYTE2(v43[1]) = a3;
      v19 = a5[4];
      BYTE3(v43[1]) = v35;
      v20 = a5[5];
      WORD2(v43[5]) = a7;
      v21 = a5[6];
      v22 = a5[7];
      v23 = a5[8];
      if ( a7 )
      {
        FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
        v39 = FileW;
        if ( FileW == (HANDLE)-1LL
          || (InBuffer = 0,
              v47 = 19,
              OutBuffer = 0,
              BytesReturned[0] = 0,
              !DeviceIoControl(FileW, 0x1501E8u, &InBuffer, 0xCu, &OutBuffer, 8u, BytesReturned, 0)) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v13 = -2147418113;
          if ( LastError < 0 )
            v13 = LastError;
          SipcFileHandle::Reset((SipcFileHandle *)&v39);
          goto LABEL_30;
        }
        v43[6] = OutBuffer;
        SipcFileHandle::Reset((SipcFileHandle *)&v39);
      }
      v25 = *(_OWORD *)&v43[3];
      v26 = v36;
      v27 = Interval;
      *((_OWORD *)v12 + 6) = *(_OWORD *)&v43[1];
      v28 = *(_OWORD *)&v43[5];
      *((_OWORD *)v12 + 7) = v25;
      *((_OWORD *)v12 + 8) = v28;
      *((_OWORD *)v12 + 9) = v14;
      *((_OWORD *)v12 + 10) = v16;
      *((_OWORD *)v12 + 11) = v17;
      *((_OWORD *)v12 + 12) = v18;
      *((_OWORD *)v12 + 13) = v19;
      *((_OWORD *)v12 + 14) = v20;
      *((_OWORD *)v12 + 15) = v21;
      *((_OWORD *)v12 + 16) = v22;
      *((_OWORD *)v12 + 17) = v23;
      *((_QWORD *)v12 + 36) = v15;
      *((_DWORD *)v12 + 14) = 15728840;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AlpcPortString::AlpcPortString)(
        v48,
        (LARGE_INTEGER)v27.QuadPart,
        v26);
      if ( a6 > 0xCCCCCCCCCCCCCCCLL || (v29 = MEMORY[0x7FFE0014] + 10 * a6, v29 <= 0) )
        v29 = 0x7FFFFFFFFFFFFFFFLL;
      v30 = v41;
      v43[0] = v29;
      while ( 1 )
      {
        v41 = 368;
        v31 = NtAlpcConnectPort(
                (char *)v12 + 48,
                v48,
                0,
                &AlpcPort::c_clientEndpointAlpcAttributes,
                0x20000,
                v30,
                (char *)v12 + 56,
                &v41,
                0,
                0,
                v43);
        if ( v31 >= 0 )
          break;
        if ( v31 != -1073741772 || MEMORY[0x7FFE0014] >= v43[0] )
        {
          utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(&v37);
          return (unsigned int)(v31 | 0x10000000);
        }
        v32.QuadPart = MEMORY[0x7FFE0014] + 1000000LL;
        if ( v43[0] < MEMORY[0x7FFE0014] + 1000000LL )
          v32 = (LARGE_INTEGER)v43[0];
        Interval = v32;
        NtDelayExecution(1u, &Interval);
      }
      if ( !*((_QWORD *)v12 + 6) )
      {
        utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(&v37);
        return v31 | 0x90000000;
      }
      v36 = 0;
      if ( AlpcMessage::GetMessageData((AlpcPort *)((char *)v12 + 56), 4u, &v36) == 4 )
      {
        *a9 = v36;
        v37 = 0;
        *a10 = v12;
        utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(&v37);
        return 0;
      }
      v13 = -2147418113;
    }
  }
  else
  {
    v13 = -2147024882;
  }
LABEL_30:
  utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(&v37);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a3594  mov     rax, rsp
0x1800a3597  push    rbp
0x1800a3598  push    rbx
0x1800a3599  push    rsi
0x1800a359a  push    rdi
0x1800a359b  push    r12
0x1800a359d  push    r13
0x1800a359f  push    r14
0x1800a35a1  push    r15
0x1800a35a3  lea     rbp, [rax-228h]
0x1800a35aa  sub     rsp, 2E8h
0x1800a35b1  movaps  xmmword ptr [rax-58h], xmm6
0x1800a35b5  movaps  xmmword ptr [rax-68h], xmm7
0x1800a35b9  movaps  xmmword ptr [rax-78h], xmm8
0x1800a35be  movaps  xmmword ptr [rax-88h], xmm9
0x1800a35c6  movaps  xmmword ptr [rax-98h], xmm10
0x1800a35ce  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800a35d6  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800a35de  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800a35e6  movaps  xmmword ptr [rax-0D8h], xmm14
0x1800a35ee  mov     rax, cs:__security_cookie
0x1800a35f5  xor     rax, rsp
0x1800a35f8  mov     [rbp+220h+var_E0], rax
0x1800a35ff  mov     rax, [rbp+220h+arg_38]
0x1800a3606  xor     ebx, ebx
0x1800a3608  mov     r15, [rbp+220h+arg_40]
0x1800a360f  mov     r13b, r8b
0x1800a3612  mov     r12, [rbp+220h+arg_48]
0x1800a3619  mov     r14, [rbp+220h+arg_20]
0x1800a3620  movzx   esi, [rbp+220h+arg_30]
0x1800a3627  mov     dword ptr [rsp+320h+var_2C0+4], edx
0x1800a362b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a3632  mov     qword ptr [rbp+220h+Interval], rcx
0x1800a3636  mov     ecx, 1F8h; unsigned __int64
0x1800a363b  mov     [r15], ebx
0x1800a363e  mov     [r12], rbx
0x1800a3642  mov     byte ptr [rsp+320h+var_2C0], r9b
0x1800a3647  mov     [rbp+220h+var_298], rax
0x1800a364b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a3650  test    rax, rax
0x1800a3653  jz      short loc_1800A3665
0x1800a3655  movzx   edx, si; unsigned __int16
0x1800a3658  mov     rcx, rax; this
0x1800a365b  call    ??0AlpcPort@@AEAA@G@Z; AlpcPort::AlpcPort(ushort)
0x1800a3660  mov     rdi, rax
0x1800a3663  jmp     short loc_1800A3668
0x1800a3665  mov     rdi, rbx
0x1800a3668  mov     [rsp+320h+var_2B8], rdi
0x1800a366d  test    rdi, rdi
0x1800a3670  jnz     short loc_1800A367C
0x1800a3672  mov     ebx, 8007000Eh
0x1800a3677  jmp     loc_1800A3962
0x1800a367c  mov     rcx, rdi; this
0x1800a367f  call    ?Initialize@SipcPort@@IEAAJXZ; SipcPort::Initialize(void)
0x1800a3684  mov     ebx, eax
0x1800a3686  xor     eax, eax
0x1800a3688  test    ebx, ebx
0x1800a368a  js      loc_1800A3962
0x1800a3690  xorps   xmm0, xmm0
0x1800a3693  mov     dword ptr [rbp+220h+var_280], eax
0x1800a3696  lea     ebx, [rax+44h]
0x1800a3699  mov     [rbp+220h+var_25C], rax
0x1800a369d  mov     r8d, ebx; Size
0x1800a36a0  mov     [rbp+220h+var_254], eax
0x1800a36a3  xor     edx, edx; Val
0x1800a36a5  lea     rcx, [rbp+220h+var_240]; void *
0x1800a36a9  movups  [rbp+220h+var_280+4], xmm0
0x1800a36ad  movups  [rbp+220h+var_26C], xmm0
0x1800a36b1  call    memset_0
0x1800a36b6  mov     r8d, ebx; Size
0x1800a36b9  lea     rcx, [rbp+220h+var_1FC]; void *
0x1800a36bd  xor     edx, edx; Val
0x1800a36bf  call    memset_0
0x1800a36c4  movups  xmm6, xmmword ptr [r14]
0x1800a36c8  mov     rbx, [r14+90h]
0x1800a36cf  movups  xmm7, xmmword ptr [r14+10h]
0x1800a36d4  mov     al, byte ptr [rsp+320h+var_2C0]
0x1800a36d8  movups  xmm8, xmmword ptr [r14+20h]
0x1800a36dd  mov     byte ptr [rbp+220h+var_280], 2
0x1800a36e1  movups  xmm9, xmmword ptr [r14+30h]
0x1800a36e6  mov     byte ptr [rbp+220h+var_280+2], r13b
0x1800a36ea  movups  xmm10, xmmword ptr [r14+40h]
0x1800a36ef  mov     byte ptr [rbp+220h+var_280+3], al
0x1800a36f2  movups  xmm11, xmmword ptr [r14+50h]
0x1800a36f7  mov     word ptr [rbp+220h+var_25C], si
0x1800a36fb  movups  xmm12, xmmword ptr [r14+60h]
0x1800a3700  movups  xmm13, xmmword ptr [r14+70h]
0x1800a3705  movups  xmm14, xmmword ptr [r14+80h]
0x1800a370d  xor     r14d, r14d
0x1800a3710  test    si, si
0x1800a3713  jz      loc_1800A37B5
0x1800a3719  mov     [rsp+320h+hTemplateFile], r14; hTemplateFile
0x1800a371e  lea     r8d, [r14+3]; dwShareMode
0x1800a3722  mov     [rsp+320h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800a3727  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x1800a372e  xor     r9d, r9d; lpSecurityAttributes
0x1800a3731  mov     [rsp+320h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a3736  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a373b  call    cs:__imp_CreateFileW
0x1800a3741  mov     [rsp+320h+var_2A8], rax
0x1800a3746  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a374a  jz      loc_1800A3903
0x1800a3750  mov     [rsp+320h+lpOverlapped], r14; lpOverlapped
0x1800a3755  lea     rcx, [rsp+320h+BytesReturned]
0x1800a375a  mov     [rsp+320h+hTemplateFile], rcx; lpBytesReturned
0x1800a375f  lea     r9d, [r14+0Ch]; nInBufferSize
0x1800a3763  lea     rcx, [rbp+220h+OutBuffer]
0x1800a3767  mov     [rsp+320h+dwFlagsAndAttributes], 8; nOutBufferSize
0x1800a376f  mov     qword ptr [rsp+320h+dwCreationDisposition], rcx; lpOutBuffer
0x1800a3774  lea     r8, [rbp+220h+InBuffer]; lpInBuffer
0x1800a3778  mov     rcx, rax; hDevice
0x1800a377b  mov     [rbp+220h+InBuffer], r14d
0x1800a377f  mov     edx, 1501E8h; dwIoControlCode
0x1800a3784  mov     [rbp+220h+var_1AC], 13h
0x1800a378c  mov     [rbp+220h+OutBuffer], r14
0x1800a3790  mov     [rsp+320h+BytesReturned], r14d
0x1800a3795  call    cs:__imp_DeviceIoControl
0x1800a379b  test    eax, eax
0x1800a379d  jz      loc_1800A3903
0x1800a37a3  mov     rax, [rbp+220h+OutBuffer]
0x1800a37a7  lea     rcx, [rsp+320h+var_2A8]; this
0x1800a37ac  mov     [rbp+220h+var_25C+4], rax
0x1800a37b0  call    ?Reset@SipcFileHandle@@QEAAXXZ; SipcFileHandle::Reset(void)
0x1800a37b5  movaps  xmm0, [rbp+220h+var_280]
0x1800a37b9  lea     rsi, [rdi+38h]
0x1800a37bd  movaps  xmm1, xmmword ptr [rbp-50h]
0x1800a37c1  lea     rcx, [rbp+220h+var_1A0]
0x1800a37c8  mov     r8d, dword ptr [rsp+320h+var_2C0+4]
0x1800a37cd  mov     rdx, qword ptr [rbp+220h+Interval]
0x1800a37d1  movups  xmmword ptr [rsi+28h], xmm0
0x1800a37d5  movaps  xmm0, [rbp+220h+var_26C+0Ch]
0x1800a37d9  movups  xmmword ptr [rsi+38h], xmm1
0x1800a37dd  movups  xmmword ptr [rsi+48h], xmm0
0x1800a37e1  movups  xmmword ptr [rsi+58h], xmm6
0x1800a37e5  movups  xmmword ptr [rsi+68h], xmm7
0x1800a37e9  movups  xmmword ptr [rsi+78h], xmm8
0x1800a37ee  movups  xmmword ptr [rsi+88h], xmm9
0x1800a37f6  movups  xmmword ptr [rsi+98h], xmm10
0x1800a37fe  movups  xmmword ptr [rsi+0A8h], xmm11
0x1800a3806  movups  xmmword ptr [rsi+0B8h], xmm12
0x1800a380e  movups  xmmword ptr [rsi+0C8h], xmm13
0x1800a3816  movups  xmmword ptr [rsi+0D8h], xmm14
0x1800a381e  mov     [rsi+0E8h], rbx
0x1800a3825  mov     dword ptr [rsi], 0F000C8h
0x1800a382b  call    ??0AlpcPortString@@QEAA@AEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@@Z; AlpcPortString::AlpcPortString(_GUID const &,SIPC_SERVICE_BOUNDARY)
0x1800a3830  mov     rax, [rbp+220h+arg_28]
0x1800a3837  mov     rdx, 0CCCCCCCCCCCCCCCh
0x1800a3841  mov     rcx, ds:7FFE0014h
0x1800a3849  cmp     rax, rdx
0x1800a384c  ja      short loc_1800A385B
0x1800a384e  lea     rax, [rax+rax*4]
0x1800a3852  lea     rax, [rcx+rax*2]
0x1800a3856  test    rax, rax
0x1800a3859  jg      short loc_1800A3865
0x1800a385b  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800a3865  mov     r13, [rbp+220h+var_298]
0x1800a3869  mov     [rbp+220h+var_288], rax
0x1800a386d  lea     rax, [rbp+220h+var_288]
0x1800a3871  mov     [rbp+220h+var_298], 170h
0x1800a3879  mov     [rsp+320h+var_2D0], rax
0x1800a387e  lea     r9, ?c_clientEndpointAlpcAttributes@AlpcPort@@0U_ALPC_PORT_ATTRIBUTES@@B; _ALPC_PORT_ATTRIBUTES const AlpcPort::c_clientEndpointAlpcAttributes
0x1800a3885  xor     eax, eax
0x1800a3887  lea     rdx, [rbp+220h+var_1A0]
0x1800a388e  mov     [rsp+320h+var_2D8], rax
0x1800a3893  lea     rcx, [rdi+30h]
0x1800a3897  mov     [rsp+320h+var_2E0], rax
0x1800a389c  xor     r8d, r8d
0x1800a389f  lea     rax, [rbp+220h+var_298]
0x1800a38a3  mov     [rsp+320h+lpOverlapped], rax
0x1800a38a8  mov     [rsp+320h+hTemplateFile], rsi
0x1800a38ad  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], r13
0x1800a38b2  mov     [rsp+320h+dwCreationDisposition], 20000h
0x1800a38ba  call    cs:__imp_NtAlpcConnectPort
0x1800a38c0  mov     ebx, eax
0x1800a38c2  xor     eax, eax
0x1800a38c4  test    ebx, ebx
0x1800a38c6  jns     short loc_1800A393B
0x1800a38c8  cmp     ebx, 0C0000034h
0x1800a38ce  jnz     short loc_1800A392B
0x1800a38d0  mov     eax, 7FFE0014h
0x1800a38d5  mov     rax, [rax]
0x1800a38d8  mov     rcx, [rbp+220h+var_288]
0x1800a38dc  cmp     rax, rcx
0x1800a38df  jge     short loc_1800A392B
0x1800a38e1  add     rax, 0F4240h
0x1800a38e7  lea     rdx, [rbp+220h+Interval]; Interval
0x1800a38eb  cmp     rcx, rax
0x1800a38ee  cmovl   rax, rcx
0x1800a38f2  mov     cl, 1; Alertable
0x1800a38f4  mov     qword ptr [rbp+220h+Interval], rax
0x1800a38f8  call    cs:__imp_NtDelayExecution
0x1800a38fe  jmp     loc_1800A386D
0x1800a3903  call    cs:__imp_GetLastError
0x1800a3909  test    eax, eax
0x1800a390b  jle     short loc_1800A3915
0x1800a390d  movzx   eax, ax
0x1800a3910  or      eax, 80070000h
0x1800a3915  test    eax, eax
0x1800a3917  lea     rcx, [rsp+320h+var_2A8]; this
0x1800a391c  mov     ebx, 8000FFFFh
0x1800a3921  cmovs   ebx, eax
0x1800a3924  call    ?Reset@SipcFileHandle@@QEAAXXZ; SipcFileHandle::Reset(void)
0x1800a3929  jmp     short loc_1800A3962
0x1800a392b  lea     rcx, [rsp+320h+var_2B8]
0x1800a3930  call    ??1?$unique_ptr@VAlpcPort@@U?$default_delete@VAlpcPort@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(void)
0x1800a3935  bts     ebx, 1Ch
0x1800a3939  jmp     short loc_1800A399E
0x1800a393b  cmp     [rdi+30h], rax
0x1800a393f  jz      short loc_1800A398E
0x1800a3941  lea     r8, [rsp+320h+var_2C0+4]; void *
0x1800a3946  mov     dword ptr [rsp+320h+var_2C0+4], eax
0x1800a394a  mov     edx, 4; unsigned __int64
0x1800a394f  mov     rcx, rsi; this
0x1800a3952  call    ?GetMessageData@AlpcMessage@@QEBA_K_KPEAX@Z; AlpcMessage::GetMessageData(unsigned __int64,void *)
0x1800a3957  cmp     rax, 4
0x1800a395b  jz      short loc_1800A396E
0x1800a395d  mov     ebx, 8000FFFFh
0x1800a3962  lea     rcx, [rsp+320h+var_2B8]
0x1800a3967  call    ??1?$unique_ptr@VAlpcPort@@U?$default_delete@VAlpcPort@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(void)
0x1800a396c  jmp     short loc_1800A399E
0x1800a396e  mov     eax, dword ptr [rsp+320h+var_2C0+4]
0x1800a3972  lea     rcx, [rsp+320h+var_2B8]
0x1800a3977  mov     [r15], eax
0x1800a397a  xor     eax, eax
0x1800a397c  mov     [rsp+320h+var_2B8], rax
0x1800a3981  mov     [r12], rdi
0x1800a3985  call    ??1?$unique_ptr@VAlpcPort@@U?$default_delete@VAlpcPort@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(void)
0x1800a398a  xor     eax, eax
0x1800a398c  jmp     short loc_1800A39A0
0x1800a398e  lea     rcx, [rsp+320h+var_2B8]
0x1800a3993  call    ??1?$unique_ptr@VAlpcPort@@U?$default_delete@VAlpcPort@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>::~unique_ptr<AlpcPort,utl::default_delete<AlpcPort>>(void)
0x1800a3998  or      ebx, 90000000h
0x1800a399e  mov     eax, ebx
0x1800a39a0  mov     rcx, [rbp+220h+var_E0]
0x1800a39a7  xor     rcx, rsp; StackCookie
0x1800a39aa  call    __security_check_cookie
0x1800a39af  lea     r11, [rsp+320h+var_38]
0x1800a39b7  movaps  xmm6, xmmword ptr [r11-18h]
0x1800a39bc  movaps  xmm7, xmmword ptr [r11-28h]
0x1800a39c1  movaps  xmm8, xmmword ptr [r11-38h]
0x1800a39c6  movaps  xmm9, xmmword ptr [r11-48h]
0x1800a39cb  movaps  xmm10, xmmword ptr [r11-58h]
0x1800a39d0  movaps  xmm11, xmmword ptr [r11-68h]
0x1800a39d5  movaps  xmm12, xmmword ptr [r11-78h]
0x1800a39da  movaps  xmm13, xmmword ptr [r11-88h]
0x1800a39e2  movaps  xmm14, xmmword ptr [r11-98h]
0x1800a39ea  mov     rsp, r11
0x1800a39ed  pop     r15
0x1800a39ef  pop     r14
0x1800a39f1  pop     r13
0x1800a39f3  pop     r12
0x1800a39f5  pop     rdi
0x1800a39f6  pop     rsi
0x1800a39f7  pop     rbx
0x1800a39f8  pop     rbp
0x1800a39f9  retn
```
