# AsyncUnbufferedFileReader::Read(uchar *,ulong,ulong &)

- ea: `0x1400ad380`
- end: `0x1400ad849`
- name: `?Read@AsyncUnbufferedFileReader@@UEAAPEAVFrsStatus@@PEAEKAEAK@Z`
- size: `1225`
- prototype: `struct FrsStatus *__fastcall(AsyncUnbufferedFileReader *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x1400046cc`
- `0x14000bbc5`
- `0x1400a8f38`
- `0x1400a92f4`
- `0x1400aae38`
- `0x1400aaf34`
- `0x1400ac258`
- `0x1400ad380`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x1400ad4af`
- `KERNEL32!GetFileSizeEx` at `0x1400ad4af`
- `KERNEL32!GetLastError` at `0x1400ad4cd`
- `KERNEL32!GetLastError` at `0x1400ad4cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad4bf`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad672`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad7df`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad4bf`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad672`
- `KERNEL32!GetCurrentThreadId` at `0x1400ad7df`

## string_xrefs

- `0x1400ad3c0`: `AsyncUnbufferedFileReader::Read`
- `0x1400ad570`: `AsyncUnbufferedFileReader::Read`
- `0x1400ad494`: `AsyncUnbufferedFileReader::Read`
- `0x1400ad691`: `AsyncUnbufferedFileReader::Read`
- `0x1400ad802`: `AsyncUnbufferedFileReader::Read`

## pseudocode

```c
struct FrsStatus *__fastcall AsyncUnbufferedFileReader::Read(
        AsyncUnbufferedFileReader *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v5; // r15
  struct FrsStatus *Buffer; // r12
  _DWORD *v8; // rbx
  void *v9; // rcx
  DWORD v10; // ebx
  DWORD LastError; // eax
  _DWORD *v12; // rsi
  void *v13; // rax
  size_t v14; // r8
  DWORD CurrentThreadId; // eax
  unsigned int v16; // edx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // edx
  __int64 v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rcx
  AsyncUnbufferedFileReader *v24; // [rsp+78h] [rbp+7h] BYREF
  const wchar_t *v25; // [rsp+80h] [rbp+Fh] BYREF
  int v26; // [rsp+88h] [rbp+17h]
  int v27; // [rsp+8Ch] [rbp+1Bh]
  const wchar_t *v28; // [rsp+90h] [rbp+1Fh]
  unsigned int v30; // [rsp+E8h] [rbp+77h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+F0h] [rbp+7Fh] BYREF

  v30 = a3;
  v5 = 0;
  *a4 = 0;
  Buffer = 0;
  if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v25 = L"AsyncUnbufferedFileReader::Read";
    v28 = L"ASYN";
    v26 = 1532;
    v27 = 5;
    FileSize.QuadPart = (LONGLONG)this;
    dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int,unsigned long,int,int>(
      (unsigned int)&v25,
      (_DWORD)this + 160,
      (unsigned int)&FileSize,
      (_DWORD)this + 144,
      (__int64)this + 96,
      (__int64)this + 100,
      (__int64)this + 104,
      (__int64)this + 108,
      (__int64)this + 88,
      (__int64)this + 92,
      (__int64)this + 160,
      (__int64)&v30,
      (__int64)this + 188,
      (__int64)this + 8);
  }
  v8 = (_DWORD *)((char *)this + 144);
  if ( *((_DWORD *)this + 36) != 1 )
  {
    v12 = (_DWORD *)((char *)this + 188);
    if ( *v8 != 2 )
    {
      CurrentThreadId = GetCurrentThreadId();
      Buffer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                     1,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                     "AsyncUnbufferedFileReader::Read",
                                     1575,
                                     CurrentThreadId,
                                     0);
      if ( Buffer )
        goto LABEL_27;
    }
    goto LABEL_20;
  }
  v9 = (void *)*((_QWORD *)this + 4);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v9, &FileSize) )
  {
    v10 = GetCurrentThreadId();
    LastError = GetLastError();
    Buffer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                   LastError,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                   "AsyncUnbufferedFileReader::Read",
                                   1546,
                                   v10,
                                   0);
    v8 = (_DWORD *)((char *)this + 144);
  }
  *((_QWORD *)this + 14) = 0;
  v12 = (_DWORD *)((char *)this + 188);
  *((_DWORD *)this + 47) = 1;
  if ( !Buffer )
    Buffer = AsyncBuffers::InitializeAsyncBuffers(
               (AsyncUnbufferedFileReader *)((char *)this + 48),
               *((HANDLE *)this + 4),
               FileSize.QuadPart);
  if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugAsyncIo)
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v26 = 1557;
    v25 = L"AsyncUnbufferedFileReader::Read";
    v27 = 5;
    v28 = L"ASYN";
    v24 = this;
    v8 = (_DWORD *)((char *)this + 144);
    dbgobj::DbgPrint<unsigned short,unsigned __int64,enum AsyncUnbufferedFileReader::State,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,unsigned long,int,unsigned __int64,unsigned long,unsigned long>(
      (unsigned int)&v25,
      (_DWORD)this + 160,
      (unsigned int)&v24,
      (_DWORD)this + 144,
      (__int64)this + 96,
      (__int64)this + 100,
      (__int64)this + 104,
      (__int64)this + 108,
      (__int64)this + 88,
      (__int64)this + 92,
      (__int64)this + 160,
      (__int64)&FileSize,
      (__int64)this + 64,
      (__int64)this + 60);
  }
  if ( !Buffer )
  {
    v13 = operator_new(saturated_mul(*((unsigned int *)this + 15), 4u));
    v14 = 4LL * *((unsigned int *)this + 15);
    *((_QWORD *)this + 19) = v13;
    memset_0(v13, 0, v14);
    *((_DWORD *)this + 40) = 0;
    *v8 = 2;
    *((_QWORD *)this + 25) = 0;
LABEL_20:
    if ( !*((_DWORD *)this + 2) && !*v12 )
    {
      Buffer = AsyncUnbufferedFileReader::GetNextReadBuffer(this);
      if ( !Buffer )
      {
        if ( *((_DWORD *)this + 23)
          && (v16 = *((_DWORD *)this + 46),
              *(_DWORD *)(*((_QWORD *)this + 19) + 4LL * *((unsigned int *)this + 24)) > v16) )
        {
          *((_DWORD *)this + 27) += v16;
          *((_DWORD *)this + 47) = 1;
        }
        else
        {
          *((_DWORD *)this + 2) = 1;
        }
      }
    }
  }
LABEL_27:
  while ( !Buffer )
  {
    if ( *((_DWORD *)this + 2) )
      goto LABEL_43;
    v17 = *a4;
    if ( (unsigned int)v17 >= v30 )
      goto LABEL_42;
    if ( *((_DWORD *)this + 23) )
    {
      v18 = *((unsigned int *)this + 24);
      v19 = v30 - v17;
      if ( v30 - (unsigned int)v17 >= *(_DWORD *)(*((_QWORD *)this + 19) + 4 * v18) - *((_DWORD *)this + 27) )
        v19 = *(_DWORD *)(*((_QWORD *)this + 19) + 4 * v18) - *((_DWORD *)this + 27);
      v20 = v19;
      if ( a2 )
        memcpy_0(
          &a2[v17],
          (const void *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8 * v18) + *((unsigned int *)this + 27)),
          v19);
      *((_DWORD *)this + 27) += v20;
      *a4 += v20;
      *((_QWORD *)this + 2) += v20;
    }
    if ( *((_DWORD *)this + 27) == *(_DWORD *)(*((_QWORD *)this + 19) + 4LL * *((unsigned int *)this + 24)) )
    {
      Buffer = AsyncUnbufferedFileReader::GetNextReadBuffer(this);
      if ( !Buffer && !*((_DWORD *)this + 23) && *((_DWORD *)this + 40) )
      {
        if ( !*a4 )
          *((_DWORD *)this + 2) = 1;
LABEL_42:
        if ( !*((_DWORD *)this + 2) )
          return (struct FrsStatus *)v5;
LABEL_43:
        AsyncBuffers::FreeAsyncBuffers((AsyncUnbufferedFileReader *)((char *)this + 48));
        return (struct FrsStatus *)v5;
      }
    }
  }
  v21 = GetCurrentThreadId();
  return (struct FrsStatus *)FrsStatusList::PushNewError(
                               v22,
                               *((unsigned int *)Buffer + 1),
                               *((unsigned int *)Buffer + 2),
                               *(unsigned int *)Buffer,
                               "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                               "AsyncUnbufferedFileReader::Read",
                               1667,
                               v21,
                               Buffer);
}

```

## disassembly

```asm
0x1400ad380  mov     rax, rsp
0x1400ad383  mov     [rax+8], rbx
0x1400ad387  mov     [rax+18h], r8d
0x1400ad38b  mov     [rax+10h], rdx
0x1400ad38f  push    rbp
0x1400ad390  push    rsi
0x1400ad391  push    rdi
0x1400ad392  push    r12
0x1400ad394  push    r13
0x1400ad396  push    r14
0x1400ad398  push    r15
0x1400ad39a  lea     rbp, [rax-5Fh]
0x1400ad39e  sub     rsp, 90h
0x1400ad3a5  mov     r14, rcx
0x1400ad3a8  xor     r15d, r15d
0x1400ad3ab  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400ad3b2  mov     [r9], r15d
0x1400ad3b5  mov     r12d, r15d
0x1400ad3b8  mov     r13, r9
0x1400ad3bb  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400ad3c0  lea     rcx, aAsyncunbuffere_6; "AsyncUnbufferedFileReader::Read"
0x1400ad3c7  lea     rdx, aAsyn; "ASYN"
0x1400ad3ce  test    eax, eax
0x1400ad3d0  jz      loc_1400AD488
0x1400ad3d6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ad3dd  test    rax, rax
0x1400ad3e0  jz      loc_1400AD488
0x1400ad3e6  cmp     [rax+40h], r15d
0x1400ad3ea  jz      loc_1400AD488
0x1400ad3f0  cmp     dword ptr [rax+38h], 5
0x1400ad3f4  jl      loc_1400AD488
0x1400ad3fa  mov     [rbp+57h+var_48], rcx
0x1400ad3fe  lea     rax, [r14+8]
0x1400ad402  mov     [rsp+68h], rax
0x1400ad407  lea     rcx, [r14+0BCh]
0x1400ad40e  mov     [rsp+0C0h+var_60], rcx
0x1400ad413  lea     rax, [rbp+57h+arg_10]
0x1400ad417  mov     [rsp+0C0h+var_68], rax
0x1400ad41c  lea     r8, [r14+5Ch]
0x1400ad420  mov     [rbp+57h+var_38], rdx
0x1400ad424  lea     r10, [r14+58h]
0x1400ad428  lea     rdx, [r14+0A0h]
0x1400ad42f  mov     [rbp+57h+var_40], 5FCh
0x1400ad436  mov     [rsp+0C0h+var_70], rdx
0x1400ad43b  lea     r11, [r14+6Ch]
0x1400ad43f  mov     [rsp+0C0h+var_78], r8
0x1400ad444  lea     rbx, [r14+68h]
0x1400ad448  mov     [rsp+0C0h+var_80], r10
0x1400ad44d  lea     rdi, [r14+64h]
0x1400ad451  mov     [rsp+0C0h+var_88], r11
0x1400ad456  lea     rsi, [r14+60h]
0x1400ad45a  mov     [rsp+0C0h+var_90], rbx
0x1400ad45f  lea     r9, [r14+90h]
0x1400ad466  mov     [rsp+0C0h+var_98], rdi
0x1400ad46b  lea     r8, [rbp+57h+FileSize]
0x1400ad46f  lea     rcx, [rbp+57h+var_48]
0x1400ad473  mov     [rsp+0C0h+var_A0], rsi
0x1400ad478  mov     [rbp+57h+var_3C], 5
0x1400ad47f  mov     qword ptr [rbp+57h+FileSize], r14
0x1400ad483  call    ??$DbgPrint@G_KW4State@AsyncUnbufferedFileReader@@KKKKKKHKHH@dbgobj@@QEAA_KPEBGAEB_KAEBW4State@AsyncUnbufferedFileReader@@AEBK33333AEBH344@Z; dbgobj::DbgPrint<ushort,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,int,int>(ushort const *,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &,ulong const &,int const &,int const &)
0x1400ad488  lea     rbx, [r14+90h]
0x1400ad48f  mov     edi, 1
0x1400ad494  lea     rsi, aAsyncunbuffere_18; "AsyncUnbufferedFileReader::Read"
0x1400ad49b  cmp     [rbx], edi
0x1400ad49d  jnz     loc_1400AD666
0x1400ad4a3  mov     rcx, [r14+20h]; hFile
0x1400ad4a7  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1400ad4ab  mov     qword ptr [rbp+57h+FileSize], r15
0x1400ad4af  call    cs:__imp_GetFileSizeEx
0x1400ad4b6  nop     dword ptr [rax+rax+00h]
0x1400ad4bb  test    eax, eax
0x1400ad4bd  jnz     short loc_1400AD512
0x1400ad4bf  call    cs:__imp_GetCurrentThreadId
0x1400ad4c6  nop     dword ptr [rax+rax+00h]
0x1400ad4cb  mov     ebx, eax
0x1400ad4cd  call    cs:__imp_GetLastError
0x1400ad4d4  nop     dword ptr [rax+rax+00h]
0x1400ad4d9  mov     [rsp+0C0h+var_80], r15
0x1400ad4de  lea     rcx, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ad4e5  mov     dword ptr [rsp+0C0h+var_88], ebx
0x1400ad4e9  mov     r9d, edi
0x1400ad4ec  mov     dword ptr [rsp+0C0h+var_90], 60Ah
0x1400ad4f4  xor     r8d, r8d
0x1400ad4f7  mov     [rsp+0C0h+var_98], rsi
0x1400ad4fc  mov     edx, eax
0x1400ad4fe  mov     [rsp+0C0h+var_A0], rcx
0x1400ad503  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ad508  mov     r12, rax
0x1400ad50b  lea     rbx, [r14+90h]
0x1400ad512  mov     [r14+70h], r15
0x1400ad516  lea     rsi, [r14+0BCh]
0x1400ad51d  mov     [rsi], edi
0x1400ad51f  test    r12, r12
0x1400ad522  jnz     short loc_1400AD538
0x1400ad524  mov     r8, qword ptr [rbp+57h+FileSize]; unsigned __int64
0x1400ad528  lea     rcx, [r14+30h]; this
0x1400ad52c  mov     rdx, [r14+20h]; FileHandle
0x1400ad530  call    ?InitializeAsyncBuffers@AsyncBuffers@@IEAAPEAVFrsStatus@@PEAX_K@Z; AsyncBuffers::InitializeAsyncBuffers(void *,unsigned __int64)
0x1400ad535  mov     r12, rax
0x1400ad538  lea     rcx, ?DebugAsyncIo@Settings@@3VCDebugAsyncIo@1@A; Settings::CDebugAsyncIo Settings::DebugAsyncIo
0x1400ad53f  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1400ad544  test    eax, eax
0x1400ad546  jz      loc_1400AD611
0x1400ad54c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400ad553  test    rax, rax
0x1400ad556  jz      loc_1400AD611
0x1400ad55c  cmp     [rax+40h], r15d
0x1400ad560  jz      loc_1400AD611
0x1400ad566  cmp     dword ptr [rax+38h], 5
0x1400ad56a  jl      loc_1400AD611
0x1400ad570  lea     rax, aAsyncunbuffere_6; "AsyncUnbufferedFileReader::Read"
0x1400ad577  mov     [rbp+57h+var_40], 615h
0x1400ad57e  mov     [rbp+57h+var_48], rax
0x1400ad582  lea     rcx, [r14+40h]
0x1400ad586  lea     rax, aAsyn; "ASYN"
0x1400ad58d  mov     [rbp+57h+var_3C], 5
0x1400ad594  mov     [rbp+57h+var_38], rax
0x1400ad598  lea     rdx, [r14+0A0h]
0x1400ad59f  lea     rax, [r14+3Ch]
0x1400ad5a3  mov     [rbp+57h+var_50], r14
0x1400ad5a7  mov     [rsp+68h], rax
0x1400ad5ac  lea     r8, [r14+5Ch]
0x1400ad5b0  mov     [rsp+0C0h+var_60], rcx
0x1400ad5b5  lea     rax, [rbp+57h+FileSize]
0x1400ad5b9  mov     [rsp+0C0h+var_68], rax
0x1400ad5be  lea     r9, [r14+58h]
0x1400ad5c2  mov     [rsp+0C0h+var_70], rdx
0x1400ad5c7  lea     r10, [r14+6Ch]
0x1400ad5cb  mov     [rsp+0C0h+var_78], r8
0x1400ad5d0  lea     r11, [r14+68h]
0x1400ad5d4  mov     [rsp+0C0h+var_80], r9
0x1400ad5d9  lea     rbx, [r14+64h]
0x1400ad5dd  mov     [rsp+0C0h+var_88], r10
0x1400ad5e2  lea     rdi, [r14+60h]
0x1400ad5e6  mov     [rsp+0C0h+var_90], r11
0x1400ad5eb  lea     r8, [rbp+57h+var_50]
0x1400ad5ef  mov     [rsp+0C0h+var_98], rbx
0x1400ad5f4  lea     rcx, [rbp+57h+var_48]
0x1400ad5f8  lea     rbx, [r14+90h]
0x1400ad5ff  mov     [rsp+0C0h+var_A0], rdi
0x1400ad604  mov     r9, rbx
0x1400ad607  call    ??$DbgPrint@G_KW4State@AsyncUnbufferedFileReader@@KKKKKKH_KKK@dbgobj@@QEAA_KPEBGAEB_KAEBW4State@AsyncUnbufferedFileReader@@AEBK33333AEBH133@Z; dbgobj::DbgPrint<ushort,unsigned __int64,AsyncUnbufferedFileReader::State,ulong,ulong,ulong,ulong,ulong,ulong,int,unsigned __int64,ulong,ulong>(ushort const *,unsigned __int64 const &,AsyncUnbufferedFileReader::State const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,ulong const &,int const &,unsigned __int64 const &,ulong const &,ulong const &)
0x1400ad60c  mov     edi, 1
0x1400ad611  test    r12, r12
0x1400ad614  jnz     loc_1400AD705
0x1400ad61a  mov     ecx, [r14+3Ch]
0x1400ad61e  lea     eax, [r12+4]
0x1400ad623  mul     rcx
0x1400ad626  lea     rcx, [r12-1]
0x1400ad62b  cmovo   rax, rcx
0x1400ad62f  mov     rcx, rax; unsigned __int64
0x1400ad632  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1400ad637  mov     r8d, [r14+3Ch]
0x1400ad63b  xor     edx, edx; Val
0x1400ad63d  shl     r8, 2; Size
0x1400ad641  mov     rcx, rax; void *
0x1400ad644  mov     [r14+98h], rax
0x1400ad64b  call    memset_0
0x1400ad650  mov     [r14+0A0h], r15d
0x1400ad657  mov     dword ptr [rbx], 2
0x1400ad65d  mov     [r14+0C8h], r15
0x1400ad664  jmp     short loc_1400AD6BC
0x1400ad666  cmp     dword ptr [rbx], 2
0x1400ad669  lea     rsi, [r14+0BCh]
0x1400ad670  jz      short loc_1400AD6BC
0x1400ad672  call    cs:__imp_GetCurrentThreadId
0x1400ad679  nop     dword ptr [rax+rax+00h]
0x1400ad67e  mov     [rsp+0C0h+var_80], r15
0x1400ad683  lea     rcx, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ad68a  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400ad68e  mov     r9d, edi
0x1400ad691  lea     rax, aAsyncunbuffere_18; "AsyncUnbufferedFileReader::Read"
0x1400ad698  mov     dword ptr [rsp+0C0h+var_90], 627h
0x1400ad6a0  mov     [rsp+0C0h+var_98], rax
0x1400ad6a5  xor     r8d, r8d
0x1400ad6a8  mov     edx, edi
0x1400ad6aa  mov     [rsp+0C0h+var_A0], rcx
0x1400ad6af  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ad6b4  mov     r12, rax
0x1400ad6b7  test    rax, rax
0x1400ad6ba  jnz     short loc_1400AD705
0x1400ad6bc  cmp     [r14+8], r15d
0x1400ad6c0  jnz     short loc_1400AD705
0x1400ad6c2  cmp     [rsi], r15d
0x1400ad6c5  jnz     short loc_1400AD705
0x1400ad6c7  mov     rcx, r14; this
0x1400ad6ca  call    ?GetNextReadBuffer@AsyncUnbufferedFileReader@@AEAAPEAVFrsStatus@@XZ; AsyncUnbufferedFileReader::GetNextReadBuffer(void)
0x1400ad6cf  mov     r12, rax
0x1400ad6d2  test    rax, rax
0x1400ad6d5  jnz     short loc_1400AD705
0x1400ad6d7  cmp     [r14+5Ch], r15d
0x1400ad6db  jz      short loc_1400AD6F4
0x1400ad6dd  mov     ecx, [r14+60h]
0x1400ad6e1  mov     rax, [r14+98h]
0x1400ad6e8  mov     edx, [r14+0B8h]
0x1400ad6ef  cmp     [rax+rcx*4], edx
0x1400ad6f2  ja      short loc_1400AD6FA
0x1400ad6f4  mov     [r14+8], edi
0x1400ad6f8  jmp     short loc_1400AD705
0x1400ad6fa  add     [r14+6Ch], edx
0x1400ad6fe  mov     [r14+0BCh], edi
0x1400ad705  mov     rdi, [rbp+57h+arg_8]
0x1400ad709  test    r12, r12
0x1400ad70c  jnz     loc_1400AD7DF
0x1400ad712  cmp     [r14+8], r15d
0x1400ad716  jnz     loc_1400AD7D4
0x1400ad71c  mov     r8d, [r13+0]
0x1400ad720  mov     edx, [rbp+57h+arg_10]
0x1400ad723  cmp     r8d, edx
0x1400ad726  jnb     loc_1400AD7CE
0x1400ad72c  cmp     [r14+5Ch], r15d
0x1400ad730  jbe     short loc_1400AD77B
0x1400ad732  mov     r9d, [r14+60h]
0x1400ad736  sub     edx, r8d
0x1400ad739  mov     rax, [r14+98h]
0x1400ad740  mov     ecx, [rax+r9*4]
0x1400ad744  sub     ecx, [r14+6Ch]
0x1400ad748  cmp     edx, ecx
0x1400ad74a  cmovnb  edx, ecx
0x1400ad74d  mov     ebx, edx
0x1400ad74f  test    rdi, rdi
0x1400ad752  jz      short loc_1400AD76C
0x1400ad754  mov     rax, [r14+48h]
0x1400ad758  lea     rcx, [rdi+r8]; void *
0x1400ad75c  mov     edx, [r14+6Ch]
0x1400ad760  mov     r8d, ebx; Size
0x1400ad763  add     rdx, [rax+r9*8]; Src
0x1400ad767  call    memcpy_0
0x1400ad76c  add     [r14+6Ch], ebx
0x1400ad770  mov     rax, rbx
0x1400ad773  add     [r13+0], ebx
0x1400ad777  add     [r14+10h], rax
0x1400ad77b  mov     rax, r14
0x1400ad77e  mov     ecx, [rax+60h]
0x1400ad781  mov     rax, [r14+98h]
0x1400ad788  mov     ecx, [rax+rcx*4]
0x1400ad78b  cmp     [r14+6Ch], ecx
0x1400ad78f  jnz     loc_1400AD709
0x1400ad795  mov     rcx, r14; this
0x1400ad798  call    ?GetNextReadBuffer@AsyncUnbufferedFileReader@@AEAAPEAVFrsStatus@@XZ; AsyncUnbufferedFileReader::GetNextReadBuffer(void)
0x1400ad79d  mov     r12, rax
0x1400ad7a0  test    rax, rax
0x1400ad7a3  jnz     loc_1400AD709
0x1400ad7a9  cmp     [r14+5Ch], r15d
0x1400ad7ad  jnz     loc_1400AD709
0x1400ad7b3  cmp     [r14+0A0h], r15d
0x1400ad7ba  jz      loc_1400AD709
0x1400ad7c0  cmp     [r13+0], r15d
0x1400ad7c4  jnz     short loc_1400AD7CE
0x1400ad7c6  mov     dword ptr [r14+8], 1
0x1400ad7ce  cmp     [r14+8], r15d
0x1400ad7d2  jz      short loc_1400AD82A
0x1400ad7d4  lea     rcx, [r14+30h]; this
0x1400ad7d8  call    ?FreeAsyncBuffers@AsyncBuffers@@IEAAXXZ; AsyncBuffers::FreeAsyncBuffers(void)
0x1400ad7dd  jmp     short loc_1400AD82A
0x1400ad7df  call    cs:__imp_GetCurrentThreadId
0x1400ad7e6  nop     dword ptr [rax+rax+00h]
0x1400ad7eb  mov     r9d, [r12]
0x1400ad7ef  mov     r8d, [r12+8]
0x1400ad7f4  mov     edx, [r12+4]
0x1400ad7f9  mov     [rsp+0C0h+var_80], r12
0x1400ad7fe  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400ad802  lea     rax, aAsyncunbuffere_18; "AsyncUnbufferedFileReader::Read"
0x1400ad809  mov     dword ptr [rsp+0C0h+var_90], 683h
0x1400ad811  mov     [rsp+0C0h+var_98], rax
0x1400ad816  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ad81d  mov     [rsp+0C0h+var_A0], rax
0x1400ad822  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ad827  mov     r15, rax
0x1400ad82a  mov     rbx, [rsp+0C0h+arg_0]
0x1400ad832  mov     rax, r15
0x1400ad835  add     rsp, 90h
0x1400ad83c  pop     r15
0x1400ad83e  pop     r14
0x1400ad840  pop     r13
0x1400ad842  pop     r12
0x1400ad844  pop     rdi
0x1400ad845  pop     rsi
0x1400ad846  pop     rbp
0x1400ad847  retn
```
