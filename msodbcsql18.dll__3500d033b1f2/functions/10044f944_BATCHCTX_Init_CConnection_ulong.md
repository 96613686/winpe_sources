# BATCHCTX::Init(CConnection *,ulong)

- ea: `0x10044f944`
- end: `0x10044fea4`
- name: `?Init@BATCHCTX@@QEAAJPEAVCConnection@@K@Z`
- size: `1376`
- prototype: `__int64 __fastcall(BATCHCTX *__hidden this, struct CConnection *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x10044c84c`

## callees

- `0x10041847c`
- `0x10044c774`
- `0x10044f944`
- `0x100450260`
- `0x100467174`
- `0x10046c37c`
- `0x10046c3c8`
- `0x100546a24`
- `0x100546aa8`
- `0x100548140`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10044fcaa`
- `KERNEL32!CreateEventW` at `0x10044fd05`
- `KERNEL32!CreateEventW` at `0x10044fcaa`
- `KERNEL32!CreateEventW` at `0x10044fd05`
- `KERNEL32!GetLastError` at `0x10044fcbc`
- `KERNEL32!GetLastError` at `0x10044fd17`
- `KERNEL32!GetLastError` at `0x10044fcbc`
- `KERNEL32!GetLastError` at `0x10044fd17`

## pseudocode

```c
__int64 __fastcall BATCHCTX::Init(BATCHCTX *this, struct CConnection *a2, int a3)
{
  void *v6; // rax
  __int64 v7; // r9
  signed int v8; // ebx
  unsigned __int8 ***v9; // rsi
  void *v10; // rax
  __int64 v11; // rdx
  void *v12; // rcx
  void *v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v19; // rax
  signed int v20; // eax
  __int64 v22; // rax
  SNI_Packet *v23; // rcx
  __int64 v24; // rdx
  int v25; // [rsp+38h] [rbp-39h] BYREF
  struct CConnection *v26; // [rsp+40h] [rbp-31h]
  void (*v27)(void *, struct SNI_Packet *, unsigned int); // [rsp+48h] [rbp-29h]
  void (__fastcall *v28)(void *, struct SNI_Packet *, unsigned int); // [rsp+50h] [rbp-21h]
  __int64 v29; // [rsp+58h] [rbp-19h]
  void *v30; // [rsp+60h] [rbp-11h]
  void *v31; // [rsp+68h] [rbp-9h]
  __int64 v32; // [rsp+70h] [rbp-1h]
  int v33; // [rsp+78h] [rbp+7h]
  __int64 v34; // [rsp+80h] [rbp+Fh]
  int v35; // [rsp+88h] [rbp+17h]
  char v36; // [rsp+8Ch] [rbp+1Bh]
  __int64 v37; // [rsp+90h] [rbp+1Fh]
  __int64 v38; // [rsp+98h] [rbp+27h]
  unsigned int v39; // [rsp+D8h] [rbp+67h] BYREF

  v6 = (void *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 72);
  *((_QWORD *)this + 5) = v6;
  if ( !v6 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v8 = bidTraceHR(0, 875529, 2147942414LL, v7);
    else
      v8 = -2147024882;
    v9 = (unsigned __int8 ***)((char *)this + 48);
    goto LABEL_54;
  }
  memset_0(v6, 0, 0x48u);
  v10 = (void *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 80);
  v9 = (unsigned __int8 ***)((char *)this + 48);
  *((_QWORD *)this + 6) = v10;
  if ( !v10 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 880649;
LABEL_52:
      v8 = bidTraceHR(0, v11, 2147942414LL, v7);
      goto LABEL_54;
    }
    goto LABEL_53;
  }
  memset_0(v10, 0, 0x50u);
  (*v9)[1] = (unsigned __int8 *)8;
  *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Alloc)(
                                                g_pMO,
                                                3133);
  v12 = *(void **)(*((_QWORD *)this + 5) + 48LL);
  if ( !v12 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 888841;
      goto LABEL_52;
    }
LABEL_53:
    v8 = -2147024882;
    goto LABEL_54;
  }
  memset_0(v12, 0, 0xC3Du);
  *(_QWORD *)(*((_QWORD *)this + 5) + 40LL) = 3133;
  v13 = (void *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Alloc)(g_pMO, 1068);
  *((_QWORD *)this + 162) = v13;
  if ( !v13 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 893961;
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  memset_0(v13, 0, 0x42Cu);
  **((_DWORD **)this + 162) = 0;
  *(_DWORD *)(*((_QWORD *)this + 162) + 800LL) = 128;
  if ( !(unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 164)
    || !(unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 165)
    || !(unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 183) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 906249;
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  *(_QWORD *)(*((_QWORD *)this + 5) + 32LL) = 0;
  **((_QWORD **)this + 5) = 0;
  *(_QWORD *)(*((_QWORD *)this + 5) + 8LL) = 0;
  (*v9)[2] = 0;
  if ( a3 )
  {
    v29 = 0;
    v27 = SNIReadAsyncCallback;
    v32 = 0;
    v28 = SNIWriteAsyncCallback;
    v33 = 0;
    v30 = &SNIAddProviderIOCPSafeAsyncCallback;
    v35 = 7;
    v31 = &SNIAddProviderIOCPSafeAsyncCallback;
    v25 = *((_DWORD *)a2 + 8);
    v34 = 0;
    v37 = 0;
    v36 = 0;
    v38 = 0;
    v26 = a2;
    v14 = BATCHCTX::OpenSNISession(this, (struct Sni_Consumer_Info *)&v25, a2, (struct SNI_Conn **)this + 12);
    v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v8 = v14;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v15 = 941065;
LABEL_24:
        _mm_lfence();
        bidTraceHR(0, v15, (unsigned int)v8, v7);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    _mm_lfence();
    _InterlockedExchange((volatile __int32 *)this + 8, 7);
  }
  else
  {
    *((_QWORD *)this + 12) = *((_QWORD *)a2 + 2);
  }
  (*v9)[2] = (unsigned __int8 *)BATCHCTX::SNIPacketAllocEx(this, 1u, 1, *v9, &v39);
  if ( !(*v9)[2] )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 953353;
      goto LABEL_52;
    }
    goto LABEL_53;
  }
  *((_DWORD *)this + 336) = a3;
  v16 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)a2 + 1017);
  if ( (bidGblFlags & 2) != 0 && `CConnection::AddRef'::`7'::_bidPtrSA_030_678[0] )
    bidTraceW(0, 694272, `CConnection::AddRef'::`7'::_bidPtrSA_030_678[0], v16);
  *((_QWORD *)this + 9) = a2;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 180) = EventW;
  if ( EventW )
  {
    *((_QWORD *)this + 179) = 0;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  v8 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v8 = LastError;
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_54;
    v15 = 961545;
    goto LABEL_24;
  }
  v19 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 182) = v19;
  if ( v19 )
  {
    *((_QWORD *)this + 181) = 0;
    v20 = 0;
  }
  else
  {
    v20 = GetLastError();
  }
  v8 = (unsigned __int16)v20 | 0x80070000;
  if ( v20 <= 0 )
    v8 = v20;
  if ( v8 >= 0 )
    return 0;
  if ( (bidGblFlags & 2) != 0 )
  {
    v15 = 964617;
    goto LABEL_24;
  }
LABEL_54:
  v22 = *((_QWORD *)this + 5);
  if ( v22 )
  {
    if ( *(_QWORD *)(v22 + 48) )
    {
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
      *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 5) + 40LL) = 0;
    if ( *((_QWORD *)this + 5) )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    *((_QWORD *)this + 5) = 0;
  }
  if ( *v9 )
  {
    v23 = (SNI_Packet *)(*v9)[2];
    if ( v23 )
    {
      SNIPacketRelease(v23);
      (*v9)[2] = 0;
      **v9 = 0;
    }
    if ( *v9 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    *v9 = 0;
  }
  v24 = *((_QWORD *)this + 162);
  if ( v24 )
  {
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    *((_QWORD *)this + 162) = 0;
  }
  if ( *((_QWORD *)this + 164) )
    MPDeleteCriticalSection((char *)this + 1312, v24);
  if ( *((_QWORD *)this + 165) )
    MPDeleteCriticalSection((char *)this + 1320, v24);
  if ( a3 )
    BATCHCTX::CloseSNISession(this, 0);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(0, 1021961, (unsigned int)v8, v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x10044f944  mov     rax, rsp
0x10044f947  mov     [rax+10h], rbx
0x10044f94b  mov     [rax+18h], rsi
0x10044f94f  mov     [rax+20h], rdi
0x10044f953  push    rbp
0x10044f954  push    r12
0x10044f956  push    r13
0x10044f958  push    r14
0x10044f95a  push    r15
0x10044f95c  lea     rbp, [rax-5Fh]
0x10044f960  sub     rsp, 0A0h
0x10044f967  mov     rdi, rcx
0x10044f96a  mov     r14, rdx
0x10044f96d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044f974  mov     ebx, 48h ; 'H'
0x10044f979  mov     edx, ebx
0x10044f97b  mov     r12d, r8d
0x10044f97e  mov     rax, [rcx]
0x10044f981  mov     rax, [rax+58h]
0x10044f985  call    cs:__guard_dispatch_icall_fptr
0x10044f98b  xor     r13d, r13d
0x10044f98e  mov     [rdi+28h], rax
0x10044f992  test    rax, rax
0x10044f995  jnz     short loc_10044F9C4
0x10044f997  test    byte ptr cs:_bidGblFlags, 2
0x10044f99e  jz      short loc_10044F9B6
0x10044f9a0  mov     edx, 0D5C09h
0x10044f9a5  xor     ecx, ecx
0x10044f9a7  mov     r8d, 8007000Eh
0x10044f9ad  call    _bidTraceHR
0x10044f9b2  mov     ebx, eax
0x10044f9b4  jmp     short loc_10044F9BB
0x10044f9b6  mov     ebx, 8007000Eh
0x10044f9bb  lea     rsi, [rdi+30h]
0x10044f9bf  jmp     loc_10044FD76
0x10044f9c4  mov     r8, rbx; Size
0x10044f9c7  xor     edx, edx; Val
0x10044f9c9  mov     rcx, rax; void *
0x10044f9cc  call    memset_0
0x10044f9d1  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044f9d8  mov     ebx, 50h ; 'P'
0x10044f9dd  mov     edx, ebx
0x10044f9df  mov     rax, [rcx]
0x10044f9e2  mov     rax, [rax+58h]
0x10044f9e6  call    cs:__guard_dispatch_icall_fptr
0x10044f9ec  lea     rsi, [rdi+30h]
0x10044f9f0  mov     [rsi], rax
0x10044f9f3  test    rax, rax
0x10044f9f6  jnz     short loc_10044FA0F
0x10044f9f8  test    byte ptr cs:_bidGblFlags, 2
0x10044f9ff  jz      loc_10044FD71
0x10044fa05  mov     edx, 0D7009h
0x10044fa0a  jmp     loc_10044FD60
0x10044fa0f  mov     r8, rbx; Size
0x10044fa12  xor     edx, edx; Val
0x10044fa14  mov     rcx, rax; void *
0x10044fa17  call    memset_0
0x10044fa1c  mov     rax, [rsi]
0x10044fa1f  mov     ebx, 0C3Dh
0x10044fa24  mov     edx, ebx
0x10044fa26  mov     qword ptr [rax+8], 8
0x10044fa2e  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044fa35  mov     rax, [rcx]
0x10044fa38  mov     rax, [rax+18h]
0x10044fa3c  call    cs:__guard_dispatch_icall_fptr
0x10044fa42  mov     rcx, [rdi+28h]
0x10044fa46  mov     [rcx+30h], rax
0x10044fa4a  mov     rax, [rdi+28h]
0x10044fa4e  mov     rcx, [rax+30h]; void *
0x10044fa52  test    rcx, rcx
0x10044fa55  jnz     short loc_10044FA6E
0x10044fa57  test    byte ptr cs:_bidGblFlags, 2
0x10044fa5e  jz      loc_10044FD71
0x10044fa64  mov     edx, 0D9009h
0x10044fa69  jmp     loc_10044FD60
0x10044fa6e  mov     r8, rbx; Size
0x10044fa71  xor     edx, edx; Val
0x10044fa73  call    memset_0
0x10044fa78  mov     rax, [rdi+28h]
0x10044fa7c  mov     [rax+28h], rbx
0x10044fa80  mov     ebx, 42Ch
0x10044fa85  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044fa8c  mov     edx, ebx
0x10044fa8e  mov     rax, [rcx]
0x10044fa91  mov     rax, [rax+18h]
0x10044fa95  call    cs:__guard_dispatch_icall_fptr
0x10044fa9b  mov     [rdi+510h], rax
0x10044faa2  test    rax, rax
0x10044faa5  jnz     short loc_10044FABE
0x10044faa7  test    byte ptr cs:_bidGblFlags, 2
0x10044faae  jz      loc_10044FD71
0x10044fab4  mov     edx, 0DA409h
0x10044fab9  jmp     loc_10044FD60
0x10044fabe  mov     r8, rbx; Size
0x10044fac1  xor     edx, edx; Val
0x10044fac3  mov     rcx, rax; void *
0x10044fac6  call    memset_0
0x10044facb  mov     rax, [rdi+510h]
0x10044fad2  lea     rcx, [rdi+520h]; struct CCriticalSection **
0x10044fad9  xor     edx, edx
0x10044fadb  mov     [rax], r13d
0x10044fade  mov     rax, [rdi+510h]
0x10044fae5  mov     dword ptr [rax+320h], 80h
0x10044faef  call    MPInitializeCriticalSectionAndSpinCount
0x10044faf4  test    eax, eax
0x10044faf6  jz      loc_10044FD52
0x10044fafc  lea     rcx, [rdi+528h]; struct CCriticalSection **
0x10044fb03  xor     edx, edx
0x10044fb05  call    MPInitializeCriticalSectionAndSpinCount
0x10044fb0a  test    eax, eax
0x10044fb0c  jz      loc_10044FD52
0x10044fb12  lea     rcx, [rdi+5B8h]; struct CCriticalSection **
0x10044fb19  xor     edx, edx
0x10044fb1b  call    MPInitializeCriticalSectionAndSpinCount
0x10044fb20  test    eax, eax
0x10044fb22  jz      loc_10044FD52
0x10044fb28  mov     rax, [rdi+28h]
0x10044fb2c  mov     [rax+20h], r13
0x10044fb30  mov     rax, [rdi+28h]
0x10044fb34  mov     [rax], r13
0x10044fb37  mov     rax, [rdi+28h]
0x10044fb3b  mov     [rax+8], r13
0x10044fb3f  mov     rax, [rsi]
0x10044fb42  mov     [rax+10h], r13
0x10044fb46  test    r12d, r12d
0x10044fb49  jz      loc_10044FBFE
0x10044fb4f  lea     rax, ?SNIReadAsyncCallback@@YAXPEAXPEAVSNI_Packet@@K@Z; SNIReadAsyncCallback(void *,SNI_Packet *,ulong)
0x10044fb56  mov     [rbp+57h+var_70], r13
0x10044fb5a  mov     [rbp+57h+var_80], rax
0x10044fb5e  lea     r9, [rdi+60h]; struct SNI_Conn **
0x10044fb62  lea     rax, ?SNIWriteAsyncCallback@@YAXPEAXPEAVSNI_Packet@@K@Z; SNIWriteAsyncCallback(void *,SNI_Packet *,ulong)
0x10044fb69  mov     [rbp+57h+var_58], r13
0x10044fb6d  mov     [rbp+57h+var_78], rax
0x10044fb71  lea     rdx, [rbp+57h+var_90]; struct Sni_Consumer_Info *
0x10044fb75  lea     rax, ?SNIAddProviderIOCPSafeAsyncCallback@@YAXPEAXW4ProviderNum@@KKW4SNIAuthErrStates@@@Z; SNIAddProviderIOCPSafeAsyncCallback(void *,ProviderNum,ulong,ulong,SNIAuthErrStates)
0x10044fb7c  mov     [rbp+57h+var_50], r13d
0x10044fb80  mov     [rbp+57h+var_68], rax
0x10044fb84  mov     r15d, 7
0x10044fb8a  lea     rax, ?SNIAddProviderIOCPSafeAsyncCallback@@YAXPEAXW4ProviderNum@@KKW4SNIAuthErrStates@@@Z; SNIAddProviderIOCPSafeAsyncCallback(void *,ProviderNum,ulong,ulong,SNIAuthErrStates)
0x10044fb91  mov     [rbp+57h+var_40], r15d
0x10044fb95  mov     [rbp+57h+var_60], rax
0x10044fb99  mov     r8, r14; struct CConnection *
0x10044fb9c  mov     eax, [r14+20h]
0x10044fba0  mov     rcx, rdi; this
0x10044fba3  mov     [rbp+57h+var_90], eax
0x10044fba6  mov     [rbp+57h+var_48], r13
0x10044fbaa  mov     [rbp+57h+var_38], r13
0x10044fbae  mov     [rbp+57h+var_3C], r13b
0x10044fbb2  mov     [rbp+57h+var_30], r13
0x10044fbb6  mov     [rbp+57h+var_88], r14
0x10044fbba  call    ?OpenSNISession@BATCHCTX@@QEAAKPEAUSni_Consumer_Info@@PEAVCConnection@@PEAPEAVSNI_Conn@@@Z; BATCHCTX::OpenSNISession(Sni_Consumer_Info *,CConnection *,SNI_Conn * *)
0x10044fbbf  movzx   ebx, ax
0x10044fbc2  or      ebx, 80070000h
0x10044fbc8  test    eax, eax
0x10044fbca  cmovle  ebx, eax
0x10044fbcd  test    ebx, ebx
0x10044fbcf  jns     short loc_10044FBF5
0x10044fbd1  test    byte ptr cs:_bidGblFlags, 2
0x10044fbd8  jz      loc_10044FD76
0x10044fbde  mov     edx, 0E5C09h
0x10044fbe3  lfence
0x10044fbe6  mov     r8d, ebx
0x10044fbe9  xor     ecx, ecx
0x10044fbeb  call    _bidTraceHR
0x10044fbf0  jmp     loc_10044FD76
0x10044fbf5  lfence
0x10044fbf8  xchg    r15d, [rdi+20h]
0x10044fbfc  jmp     short loc_10044FC06
0x10044fbfe  mov     rax, [r14+10h]
0x10044fc02  mov     [rdi+60h], rax
0x10044fc06  mov     r9, [rsi]; unsigned __int8 **
0x10044fc09  lea     rax, [rbp+57h+arg_0]
0x10044fc0d  mov     r15d, 1
0x10044fc13  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x10044fc18  mov     r8d, r15d; int
0x10044fc1b  mov     edx, r15d; unsigned int
0x10044fc1e  mov     rcx, rdi; this
0x10044fc21  call    ?SNIPacketAllocEx@BATCHCTX@@AEAAPEAVSNI_Packet@@KHPEAPEAEPEAK@Z; BATCHCTX::SNIPacketAllocEx(ulong,int,uchar * *,ulong *)
0x10044fc26  mov     rcx, [rsi]
0x10044fc29  mov     [rcx+10h], rax
0x10044fc2d  mov     rax, [rsi]
0x10044fc30  cmp     [rax+10h], r13
0x10044fc34  jnz     short loc_10044FC4D
0x10044fc36  test    byte ptr cs:_bidGblFlags, 2
0x10044fc3d  jz      loc_10044FD71
0x10044fc43  mov     edx, 0E8C09h
0x10044fc48  jmp     loc_10044FD60
0x10044fc4d  mov     [rdi+540h], r12d
0x10044fc54  mov     r9d, r15d
0x10044fc57  lock xadd [r14+0FE4h], r9d
0x10044fc60  add     r9d, r15d
0x10044fc63  test    byte ptr cs:_bidGblFlags, 2
0x10044fc6a  jz      short loc_10044FC9B
0x10044fc6c  mov     rax, cs:?_bidPtrSA_030_678@?6??AddRef@CConnection@@QEAAKXZ@4REBGEB; ushort const * const `CConnection::AddRef(void)'::`7'::_bidPtrSA_030_678
0x10044fc73  test    rax, rax
0x10044fc76  jz      short loc_10044FC9B
0x10044fc78  mov     eax, [r14+0FE0h]
0x10044fc7f  mov     edx, 0A9800h
0x10044fc84  mov     r8, cs:?_bidPtrSA_030_678@?6??AddRef@CConnection@@QEAAKXZ@4REBGEB; ushort const * const `CConnection::AddRef(void)'::`7'::_bidPtrSA_030_678
0x10044fc8b  xor     ecx, ecx
0x10044fc8d  mov     [rsp+0C0h+var_98], r14
0x10044fc92  mov     dword ptr [rsp+0C0h+var_A0], eax
0x10044fc96  call    _bidTraceW
0x10044fc9b  xor     r9d, r9d; lpName
0x10044fc9e  mov     [rdi+48h], r14
0x10044fca2  mov     r8d, r15d; bInitialState
0x10044fca5  mov     edx, r15d; bManualReset
0x10044fca8  xor     ecx, ecx; lpEventAttributes
0x10044fcaa  call    cs:__imp_CreateEventW
0x10044fcb0  mov     [rdi+5A0h], rax
0x10044fcb7  test    rax, rax
0x10044fcba  jnz     short loc_10044FCC4
0x10044fcbc  call    cs:__imp_GetLastError
0x10044fcc2  jmp     short loc_10044FCCE
0x10044fcc4  mov     [rdi+598h], r13
0x10044fccb  mov     eax, r13d
0x10044fcce  movzx   ebx, ax
0x10044fcd1  mov     r14d, 80070000h
0x10044fcd7  or      ebx, r14d
0x10044fcda  test    eax, eax
0x10044fcdc  cmovle  ebx, eax
0x10044fcdf  test    ebx, ebx
0x10044fce1  jns     short loc_10044FCFA
0x10044fce3  test    byte ptr cs:_bidGblFlags, 2
0x10044fcea  jz      loc_10044FD76
0x10044fcf0  mov     edx, 0EAC09h
0x10044fcf5  jmp     loc_10044FBE3
0x10044fcfa  xor     r9d, r9d; lpName
0x10044fcfd  mov     r8d, r15d; bInitialState
0x10044fd00  mov     edx, r15d; bManualReset
0x10044fd03  xor     ecx, ecx; lpEventAttributes
0x10044fd05  call    cs:__imp_CreateEventW
0x10044fd0b  mov     [rdi+5B0h], rax
0x10044fd12  test    rax, rax
0x10044fd15  jnz     short loc_10044FD1F
0x10044fd17  call    cs:__imp_GetLastError
0x10044fd1d  jmp     short loc_10044FD29
0x10044fd1f  mov     [rdi+5A8h], r13
0x10044fd26  mov     eax, r13d
0x10044fd29  movzx   ebx, ax
0x10044fd2c  or      ebx, r14d
0x10044fd2f  test    eax, eax
0x10044fd31  cmovle  ebx, eax
0x10044fd34  test    ebx, ebx
0x10044fd36  jns     short loc_10044FD4B
0x10044fd38  test    byte ptr cs:_bidGblFlags, 2
0x10044fd3f  jz      short loc_10044FD76
0x10044fd41  mov     edx, 0EB809h
0x10044fd46  jmp     loc_10044FBE3
0x10044fd4b  xor     eax, eax
0x10044fd4d  jmp     loc_10044FE83
0x10044fd52  test    byte ptr cs:_bidGblFlags, 2
0x10044fd59  jz      short loc_10044FD71
0x10044fd5b  mov     edx, 0DD409h
0x10044fd60  mov     r8d, 8007000Eh
0x10044fd66  xor     ecx, ecx
0x10044fd68  call    _bidTraceHR
0x10044fd6d  mov     ebx, eax
0x10044fd6f  jmp     short loc_10044FD76
0x10044fd71  mov     ebx, 8007000Eh
0x10044fd76  mov     rax, [rdi+28h]
0x10044fd7a  test    rax, rax
0x10044fd7d  jz      short loc_10044FDCD
0x10044fd7f  mov     rdx, [rax+30h]
0x10044fd83  test    rdx, rdx
0x10044fd86  jz      short loc_10044FDA4
0x10044fd88  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044fd8f  mov     rax, [rcx]
0x10044fd92  mov     rax, [rax+28h]
0x10044fd96  call    cs:__guard_dispatch_icall_fptr
0x10044fd9c  mov     rax, [rdi+28h]
0x10044fda0  mov     [rax+30h], r13
0x10044fda4  mov     rax, [rdi+28h]
0x10044fda8  mov     [rax+28h], r13
0x10044fdac  mov     rdx, [rdi+28h]
0x10044fdb0  test    rdx, rdx
0x10044fdb3  jz      short loc_10044FDC9
0x10044fdb5  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044fdbc  mov     rax, [rcx]
0x10044fdbf  mov     rax, [rax+68h]
0x10044fdc3  call    cs:__guard_dispatch_icall_fptr
0x10044fdc9  mov     [rdi+28h], r13
0x10044fdcd  mov     rax, [rsi]
0x10044fdd0  test    rax, rax
0x10044fdd3  jz      short loc_10044FE0F
0x10044fdd5  mov     rcx, [rax+10h]; this
0x10044fdd9  test    rcx, rcx
0x10044fddc  jz      short loc_10044FDF0
0x10044fdde  call    SNIPacketRelease
0x10044fde3  mov     rax, [rsi]
0x10044fde6  mov     [rax+10h], r13
0x10044fdea  mov     rax, [rsi]
0x10044fded  mov     [rax], r13
0x10044fdf0  mov     rdx, [rsi]
0x10044fdf3  test    rdx, rdx
0x10044fdf6  jz      short loc_10044FE0C
0x10044fdf8  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10044fdff  mov     rax, [rcx]
0x10044fe02  mov     rax, [rax+68h]
0x10044fe06  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
