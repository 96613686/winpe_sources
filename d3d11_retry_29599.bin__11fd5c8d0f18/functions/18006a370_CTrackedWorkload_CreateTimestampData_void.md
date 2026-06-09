# CTrackedWorkload::CreateTimestampData(void)

- ea: `0x18006a370`
- end: `0x18006a757`
- name: `?CreateTimestampData@CTrackedWorkload@@AEAAXXZ`
- size: `999`
- prototype: `void __fastcall(CTrackedWorkload *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18009d474`

## callees

- `0x18001e2a0`
- `0x180022400`
- `0x18002bd20`
- `0x1800356b8`
- `0x18005a574`
- `0x180060c90`
- `0x18006a370`
- `0x18006a760`
- `0x18006c1e8`
- `0x1800a0484`
- `0x1800a0aa4`
- `0x1800a2d14`
- `0x1800cb0a4`
- `0x1800cb210`
- `0x1800cb32c`
- `0x1800cb374`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006a609`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006a609`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18006a630`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18006a630`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a648`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a648`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a55b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a594`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a5c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a55b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a594`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006a5c4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18006a666`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18006a666`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTrackedWorkload::CreateTimestampData(CTrackedWorkload *this)
{
  __int64 *v2; // rsi
  unsigned __int64 v3; // rdx
  __int64 v4; // r8
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rsi
  __int64 v15; // r15
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  SafeHANDLE *v21; // rbx
  SafeHANDLE *v22; // r14
  SafeHANDLE *i; // rbx
  HANDLE EventA; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE Thread; // rax
  int ClockCalibrationAndFrequency; // eax
  int v29; // eax
  void *v30; // rcx
  void *v31; // rbx
  __int64 v32; // rax
  void *v33; // [rsp+70h] [rbp+40h] BYREF
  D3D11_QUERY_DESC v34; // [rsp+78h] [rbp+48h] BYREF
  struct D3D11_QUERY_DESC v35; // [rsp+80h] [rbp+50h] BYREF
  LARGE_INTEGER Frequency; // [rsp+88h] [rbp+58h] BYREF

  v34 = (D3D11_QUERY_DESC)2LL;
  v35 = (struct D3D11_QUERY_DESC)3LL;
  v2 = (__int64 *)((char *)this + 344);
  v3 = *((unsigned int *)this + 57);
  v4 = *((_QWORD *)this + 43);
  v5 = 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 44) - v4) >> 4);
  if ( v3 >= v5 )
  {
    if ( v3 > v5 )
    {
      if ( v3 <= 0xCCCCCCCCCCCCCCCDuLL * ((v2[2] - v4) >> 4) )
        v2[1] = std::_Uninitialized_value_construct_n<std::allocator<TrackedWorkloadInstance>>(v2[1], v3 - v5);
      else
        std::vector<TrackedWorkloadInstance>::_Resize_reallocate<std::_Value_init_tag>(v2);
    }
  }
  else
  {
    v6 = v4 + 80 * v3;
    std::_Destroy_range<std::allocator<TrackedWorkloadInstance>>(v6, v2[1]);
    v2[1] = v6;
  }
  v7 = (unsigned int)(2 * *((_DWORD *)this + 57));
  v8 = *((_QWORD *)this + 41);
  v9 = *((_QWORD *)this + 40);
  v10 = (v8 - v9) >> 3;
  if ( v7 >= v10 )
  {
    if ( v7 > v10 )
    {
      if ( v7 <= (*((_QWORD *)this + 42) - v9) >> 3 )
      {
        v11 = v8 + 8 * (v7 - v10);
        std::_Zero_range<unsigned __int64 *>(*((_QWORD *)this + 41), v11);
        *((_QWORD *)this + 41) = v11;
      }
      else
      {
        std::vector<unsigned __int64>::_Resize_reallocate<std::_Value_init_tag>(
          (char *)this + 320,
          (unsigned int)(2 * *((_DWORD *)this + 57)));
      }
    }
  }
  else
  {
    *((_QWORD *)this + 41) = v9 + 8LL * (unsigned int)(2 * *((_DWORD *)this + 57));
  }
  v12 = *v2;
  v13 = v2[1];
  if ( *v2 != v13 )
  {
    v14 = v12 + 24;
    do
    {
      v15 = v14;
      do
      {
        v16 = CDevice::CreateQuery((CDevice *)(*((_QWORD *)this + 20) + 16LL), &v34, (struct ID3D11Query **)(v15 + 8));
        ThrowFailure(v16);
        v17 = CDevice::CreateQuery((CDevice *)(*((_QWORD *)this + 20) + 16LL), &v35, (struct ID3D11Query **)(v15 + 16));
        ThrowFailure(v17);
        v15 += 24;
      }
      while ( v15 != v14 + 48 );
      v12 += 80;
      v14 += 80;
    }
    while ( v12 != v13 );
  }
  v18 = (unsigned int)(2 * *((_DWORD *)this + 57));
  v19 = *((_QWORD *)this + 48);
  v20 = (*((_QWORD *)this + 49) - v19) >> 3;
  if ( v18 >= v20 )
  {
    if ( v18 > v20 )
    {
      if ( v18 <= (*((_QWORD *)this + 50) - v19) >> 3 )
        *((_QWORD *)this + 49) = std::_Uninitialized_value_construct_n<std::allocator<SafeHANDLE>>(*((SafeHANDLE **)this + 49));
      else
        std::vector<SafeHANDLE>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 384);
    }
  }
  else
  {
    v21 = (SafeHANDLE *)(v19 + 8 * v18);
    std::_Destroy_range<std::allocator<SafeHANDLE>>(v21);
    *((_QWORD *)this + 49) = v21;
  }
  v22 = (SafeHANDLE *)*((_QWORD *)this + 49);
  for ( i = (SafeHANDLE *)*((_QWORD *)this + 48); i != v22; i = (SafeHANDLE *)((char *)i + 8) )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    SafeHANDLE::operator=(i, EventA);
    if ( !*(_QWORD *)i )
      ThrowFailure(-2147467259);
  }
  v25 = CreateEventA(0, 0, 0, 0);
  SafeHANDLE::operator=((CTrackedWorkload *)((char *)this + 408), v25);
  if ( !*((_QWORD *)this + 51) )
    ThrowFailure(-2147467259);
  v26 = CreateEventA(0, 0, 0, 0);
  SafeHANDLE::operator=((CTrackedWorkload *)((char *)this + 416), v26);
  if ( !*((_QWORD *)this + 52) )
    ThrowFailure(-2147467259);
  Thread = CreateThread(0, 0, CTrackedWorkload::TimestampMonitoringThreadEntry, this, 0, 0);
  SafeHANDLE::operator=((CTrackedWorkload *)((char *)this + 424), Thread);
  if ( !*((_QWORD *)this + 53) )
    ThrowFailure(-2147467259);
  if ( !SetThreadPriority(*((HANDLE *)this + 53), 15) )
    ThrowFailure(-2147467259);
  if ( WaitForSingleObject(*((HANDLE *)this + 52), 0xFFFFFFFF) )
    ThrowFailure(-2147467259);
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  *((LARGE_INTEGER *)this + 54) = Frequency;
  ClockCalibrationAndFrequency = NDXGI::CDevice::GetClockCalibrationAndFrequency(
                                   *(_QWORD *)(*((_QWORD *)this + 20) + 1232LL),
                                   *((unsigned int *)this + 93),
                                   (char *)this + 304,
                                   (char *)this + 312,
                                   (char *)this + 296);
  ThrowFailure(ClockCalibrationAndFrequency);
  v33 = 0;
  v29 = CDevice::CreateFence(
          (CDevice *)(*((_QWORD *)this + 20) + 16LL),
          *((unsigned int *)this + 62),
          D3D11_FENCE_FLAG_NONE,
          &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7,
          &v33);
  ThrowFailure(v29);
  ++*((_DWORD *)this + 62);
  v30 = v33;
  v31 = v33;
  if ( *((void **)this + 30) != v33 )
  {
    if ( v33 )
    {
      CLockOwnerChild<CDevice,0>::UCAddUse((char *)v33 + 152);
      v30 = v33;
    }
    v32 = *((_QWORD *)this + 30);
    if ( v32 )
    {
      CLockOwnerChild<CDevice,0>::UCReleaseUse(v32 + 152);
      v30 = v33;
    }
    *((_QWORD *)this + 30) = v31;
  }
  if ( v30 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
}

```

## disassembly

```asm
0x18006a370  push    rbp
0x18006a372  push    rbx
0x18006a373  push    rsi
0x18006a374  push    rdi
0x18006a375  push    r12
0x18006a377  push    r14
0x18006a379  push    r15
0x18006a37b  mov     rbp, rsp
0x18006a37e  sub     rsp, 30h
0x18006a382  mov     rdi, rcx
0x18006a385  mov     qword ptr [rbp+arg_8.Query], 2
0x18006a38d  mov     qword ptr [rbp+arg_10.Query], 3
0x18006a395  lea     rsi, [rcx+158h]
0x18006a39c  mov     edx, [rcx+0E4h]
0x18006a3a2  mov     r8, [rsi]
0x18006a3a5  mov     rcx, [rsi+8]
0x18006a3a9  sub     rcx, r8
0x18006a3ac  sar     rcx, 4
0x18006a3b0  mov     r9, 0CCCCCCCCCCCCCCCDh
0x18006a3ba  imul    rcx, r9
0x18006a3be  cmp     rdx, rcx
0x18006a3c1  jnb     short loc_18006A3E0
0x18006a3c3  lea     rbx, [rdx+rdx*4]
0x18006a3c7  shl     rbx, 4
0x18006a3cb  add     rbx, r8
0x18006a3ce  mov     rdx, [rsi+8]
0x18006a3d2  mov     rcx, rbx
0x18006a3d5  call    ??$_Destroy_range@V?$allocator@UTrackedWorkloadInstance@@@std@@@std@@YAXPEAUTrackedWorkloadInstance@@QEAU1@AEAV?$allocator@UTrackedWorkloadInstance@@@0@@Z; std::_Destroy_range<std::allocator<TrackedWorkloadInstance>>(TrackedWorkloadInstance *,TrackedWorkloadInstance * const,std::allocator<TrackedWorkloadInstance> &)
0x18006a3da  mov     [rsi+8], rbx
0x18006a3de  jmp     short loc_18006A410
0x18006a3e0  jbe     short loc_18006A410
0x18006a3e2  mov     rax, [rsi+10h]
0x18006a3e6  sub     rax, r8
0x18006a3e9  sar     rax, 4
0x18006a3ed  imul    rax, r9
0x18006a3f1  cmp     rdx, rax
0x18006a3f4  jbe     short loc_18006A400
0x18006a3f6  mov     rcx, rsi
0x18006a3f9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UTrackedWorkloadInstance@@V?$allocator@UTrackedWorkloadInstance@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<TrackedWorkloadInstance>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006a3fe  jmp     short loc_18006A410
0x18006a400  sub     rdx, rcx
0x18006a403  mov     rcx, [rsi+8]
0x18006a407  call    ??$_Uninitialized_value_construct_n@V?$allocator@UTrackedWorkloadInstance@@@std@@@std@@YAPEAUTrackedWorkloadInstance@@PEAU1@_KAEAV?$allocator@UTrackedWorkloadInstance@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<TrackedWorkloadInstance>>(TrackedWorkloadInstance *,unsigned __int64,std::allocator<TrackedWorkloadInstance> &)
0x18006a40c  mov     [rsi+8], rax
0x18006a410  lea     r14, [rdi+140h]
0x18006a417  mov     eax, [rdi+0E4h]
0x18006a41d  add     eax, eax
0x18006a41f  mov     ecx, eax
0x18006a421  mov     r9, [r14+8]
0x18006a425  mov     r8, [r14]
0x18006a428  mov     rdx, r9
0x18006a42b  sub     rdx, r8
0x18006a42e  sar     rdx, 3
0x18006a432  cmp     rcx, rdx
0x18006a435  jnb     short loc_18006A441
0x18006a437  lea     rax, [r8+rax*8]
0x18006a43b  mov     [r14+8], rax
0x18006a43f  jmp     short loc_18006A476
0x18006a441  jbe     short loc_18006A476
0x18006a443  mov     rax, [r14+10h]
0x18006a447  sub     rax, r8
0x18006a44a  sar     rax, 3
0x18006a44e  cmp     rcx, rax
0x18006a451  jbe     short loc_18006A460
0x18006a453  mov     rdx, rcx
0x18006a456  mov     rcx, r14
0x18006a459  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_KV?$allocator@_K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<unsigned __int64>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006a45e  jmp     short loc_18006A476
0x18006a460  sub     rcx, rdx
0x18006a463  lea     rbx, [r9+rcx*8]
0x18006a467  mov     rdx, rbx
0x18006a46a  mov     rcx, r9
0x18006a46d  call    ??$_Zero_range@PEA_K@std@@YAPEA_KQEA_K0@Z; std::_Zero_range<unsigned __int64 *>(unsigned __int64 * const,unsigned __int64 * const)
0x18006a472  mov     [r14+8], rbx
0x18006a476  mov     rbx, [rsi]
0x18006a479  mov     r14, [rsi+8]
0x18006a47d  cmp     rbx, r14
0x18006a480  jz      short loc_18006A4E6
0x18006a482  lea     rsi, [rbx+18h]
0x18006a486  mov     r15, rsi
0x18006a489  lea     r12, [rsi+30h]
0x18006a48d  cmp     rsi, r12
0x18006a490  jz      short loc_18006A4D9
0x18006a492  lea     r8, [r15+8]; struct ID3D11Query **
0x18006a496  mov     rcx, [rdi+0A0h]
0x18006a49d  add     rcx, 10h; this
0x18006a4a1  lea     rdx, [rbp+arg_8]; struct D3D11_QUERY_DESC *
0x18006a4a5  call    ?CreateQuery@CDevice@@UEAAJPEBUD3D11_QUERY_DESC@@PEAPEAUID3D11Query@@@Z; CDevice::CreateQuery(D3D11_QUERY_DESC const *,ID3D11Query * *)
0x18006a4aa  mov     ecx, eax; int
0x18006a4ac  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a4b1  lea     r8, [r15+10h]; struct ID3D11Query **
0x18006a4b5  mov     rcx, [rdi+0A0h]
0x18006a4bc  add     rcx, 10h; this
0x18006a4c0  lea     rdx, [rbp+arg_10]; struct D3D11_QUERY_DESC *
0x18006a4c4  call    ?CreateQuery@CDevice@@UEAAJPEBUD3D11_QUERY_DESC@@PEAPEAUID3D11Query@@@Z; CDevice::CreateQuery(D3D11_QUERY_DESC const *,ID3D11Query * *)
0x18006a4c9  mov     ecx, eax; int
0x18006a4cb  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a4d0  add     r15, 18h
0x18006a4d4  cmp     r15, r12
0x18006a4d7  jnz     short loc_18006A492
0x18006a4d9  add     rbx, 50h ; 'P'
0x18006a4dd  add     rsi, 50h ; 'P'
0x18006a4e1  cmp     rbx, r14
0x18006a4e4  jnz     short loc_18006A486
0x18006a4e6  lea     rsi, [rdi+180h]
0x18006a4ed  mov     eax, [rdi+0E4h]
0x18006a4f3  add     eax, eax
0x18006a4f5  mov     edx, eax
0x18006a4f7  mov     r8, [rsi]
0x18006a4fa  mov     rcx, [rsi+8]
0x18006a4fe  sub     rcx, r8
0x18006a501  sar     rcx, 3
0x18006a505  cmp     rdx, rcx
0x18006a508  jnb     short loc_18006A520
0x18006a50a  lea     rbx, [r8+rax*8]
0x18006a50e  mov     rdx, [rsi+8]
0x18006a512  mov     rcx, rbx; this
0x18006a515  call    ??$_Destroy_range@V?$allocator@VSafeHANDLE@@@std@@@std@@YAXPEAVSafeHANDLE@@QEAV1@AEAV?$allocator@VSafeHANDLE@@@0@@Z; std::_Destroy_range<std::allocator<SafeHANDLE>>(SafeHANDLE *,SafeHANDLE * const,std::allocator<SafeHANDLE> &)
0x18006a51a  mov     [rsi+8], rbx
0x18006a51e  jmp     short loc_18006A54C
0x18006a520  jbe     short loc_18006A54C
0x18006a522  mov     rax, [rsi+10h]
0x18006a526  sub     rax, r8
0x18006a529  sar     rax, 3
0x18006a52d  cmp     rdx, rax
0x18006a530  jbe     short loc_18006A53C
0x18006a532  mov     rcx, rsi
0x18006a535  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@VSafeHANDLE@@V?$allocator@VSafeHANDLE@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<SafeHANDLE>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006a53a  jmp     short loc_18006A54C
0x18006a53c  sub     rdx, rcx
0x18006a53f  mov     rcx, [rsi+8]; this
0x18006a543  call    ??$_Uninitialized_value_construct_n@V?$allocator@VSafeHANDLE@@@std@@@std@@YAPEAVSafeHANDLE@@PEAV1@_KAEAV?$allocator@VSafeHANDLE@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<SafeHANDLE>>(SafeHANDLE *,unsigned __int64,std::allocator<SafeHANDLE> &)
0x18006a548  mov     [rsi+8], rax
0x18006a54c  mov     r14, [rsi+8]
0x18006a550  mov     rbx, [rsi]
0x18006a553  mov     r15d, 80004005h
0x18006a559  jmp     short loc_18006A57E
0x18006a55b  call    cs:__imp_CreateEventA
0x18006a561  mov     rdx, rax; void *
0x18006a564  mov     rcx, rbx; this
0x18006a567  call    ??4SafeHANDLE@@QEAAAEAV0@PEAX@Z; SafeHANDLE::operator=(void *)
0x18006a56c  cmp     qword ptr [rbx], 0
0x18006a570  jnz     short loc_18006A57A
0x18006a572  mov     ecx, r15d; int
0x18006a575  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a57a  add     rbx, 8
0x18006a57e  xor     r9d, r9d; lpName
0x18006a581  xor     r8d, r8d; bInitialState
0x18006a584  xor     edx, edx; bManualReset
0x18006a586  xor     ecx, ecx; lpEventAttributes
0x18006a588  cmp     rbx, r14
0x18006a58b  jnz     short loc_18006A55B
0x18006a58d  lea     rbx, [rdi+198h]
0x18006a594  call    cs:__imp_CreateEventA
0x18006a59a  mov     rdx, rax; void *
0x18006a59d  mov     rcx, rbx; this
0x18006a5a0  call    ??4SafeHANDLE@@QEAAAEAV0@PEAX@Z; SafeHANDLE::operator=(void *)
0x18006a5a5  cmp     qword ptr [rbx], 0
0x18006a5a9  jnz     short loc_18006A5B3
0x18006a5ab  mov     ecx, r15d; int
0x18006a5ae  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a5b3  lea     rsi, [rdi+1A0h]
0x18006a5ba  xor     r9d, r9d; lpName
0x18006a5bd  xor     r8d, r8d; bInitialState
0x18006a5c0  xor     edx, edx; bManualReset
0x18006a5c2  xor     ecx, ecx; lpEventAttributes
0x18006a5c4  call    cs:__imp_CreateEventA
0x18006a5ca  mov     rdx, rax; void *
0x18006a5cd  mov     rcx, rsi; this
0x18006a5d0  call    ??4SafeHANDLE@@QEAAAEAV0@PEAX@Z; SafeHANDLE::operator=(void *)
0x18006a5d5  cmp     qword ptr [rsi], 0
0x18006a5d9  jnz     short loc_18006A5E3
0x18006a5db  mov     ecx, r15d; int
0x18006a5de  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a5e3  lea     rbx, [rdi+1A8h]
0x18006a5ea  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x18006a5f3  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x18006a5fb  mov     r9, rdi; lpParameter
0x18006a5fe  lea     r8, ?TimestampMonitoringThreadEntry@CTrackedWorkload@@CAKPEAX@Z; lpStartAddress
0x18006a605  xor     edx, edx; dwStackSize
0x18006a607  xor     ecx, ecx; lpThreadAttributes
0x18006a609  call    cs:__imp_CreateThread
0x18006a60f  mov     rdx, rax; void *
0x18006a612  mov     rcx, rbx; this
0x18006a615  call    ??4SafeHANDLE@@QEAAAEAV0@PEAX@Z; SafeHANDLE::operator=(void *)
0x18006a61a  cmp     qword ptr [rbx], 0
0x18006a61e  jnz     short loc_18006A628
0x18006a620  mov     ecx, r15d; int
0x18006a623  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a628  mov     edx, 0Fh; nPriority
0x18006a62d  mov     rcx, [rbx]; hThread
0x18006a630  call    cs:__imp_SetThreadPriority
0x18006a636  test    eax, eax
0x18006a638  jnz     short loc_18006A642
0x18006a63a  mov     ecx, r15d; int
0x18006a63d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a642  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006a645  mov     rcx, [rsi]; hHandle
0x18006a648  call    cs:__imp_WaitForSingleObject
0x18006a64e  test    eax, eax
0x18006a650  jz      short loc_18006A65A
0x18006a652  mov     ecx, r15d; int
0x18006a655  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a65a  mov     qword ptr [rbp+Frequency], 0
0x18006a662  lea     rcx, [rbp+Frequency]; lpFrequency
0x18006a666  call    cs:__imp_QueryPerformanceFrequency
0x18006a66c  mov     rax, qword ptr [rbp+Frequency]
0x18006a670  mov     [rdi+1B0h], rax
0x18006a677  lea     rax, [rdi+128h]
0x18006a67e  lea     r9, [rdi+138h]
0x18006a685  lea     r8, [rdi+130h]
0x18006a68c  mov     rcx, [rdi+0A0h]
0x18006a693  mov     qword ptr [rsp+30h+dwCreationFlags], rax
0x18006a698  mov     edx, [rdi+174h]
0x18006a69e  mov     rcx, [rcx+4D0h]
0x18006a6a5  call    ?GetClockCalibrationAndFrequency@CDevice@NDXGI@@QEAAJW4DXGK_ENGINE_TYPE@@PEA_K11@Z; NDXGI::CDevice::GetClockCalibrationAndFrequency(DXGK_ENGINE_TYPE,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18006a6aa  mov     ecx, eax; int
0x18006a6ac  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a6b1  mov     [rbp+arg_0], 0
0x18006a6b9  mov     edx, [rdi+0F8h]; unsigned __int64
0x18006a6bf  mov     rcx, [rdi+0A0h]
0x18006a6c6  add     rcx, 10h; this
0x18006a6ca  lea     rax, [rbp+arg_0]
0x18006a6ce  mov     qword ptr [rsp+30h+dwCreationFlags], rax; void **
0x18006a6d3  lea     r9, _GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7; struct _GUID *
0x18006a6da  xor     r8d, r8d; enum D3D11_FENCE_FLAG
0x18006a6dd  call    ?CreateFence@CDevice@@UEAAJ_KW4D3D11_FENCE_FLAG@@AEBU_GUID@@PEAPEAX@Z; CDevice::CreateFence(unsigned __int64,D3D11_FENCE_FLAG,_GUID const &,void * *)
0x18006a6e2  mov     ecx, eax; int
0x18006a6e4  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006a6e9  inc     dword ptr [rdi+0F8h]
0x18006a6ef  mov     rcx, [rbp+arg_0]
0x18006a6f3  mov     rbx, rcx
0x18006a6f6  cmp     [rdi+0F0h], rcx
0x18006a6fd  jz      short loc_18006A737
0x18006a6ff  test    rcx, rcx
0x18006a702  jz      short loc_18006A714
0x18006a704  add     rcx, 98h
0x18006a70b  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18006a710  mov     rcx, [rbp+arg_0]
0x18006a714  mov     rax, [rdi+0F0h]
0x18006a71b  test    rax, rax
0x18006a71e  jz      short loc_18006A730
0x18006a720  lea     rcx, [rax+98h]
0x18006a727  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18006a72c  mov     rcx, [rbp+arg_0]
0x18006a730  mov     [rdi+0F0h], rbx
0x18006a737  test    rcx, rcx
0x18006a73a  jz      short loc_18006A748
0x18006a73c  mov     rax, [rcx]
0x18006a73f  mov     rax, [rax+10h]
0x18006a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a748  add     rsp, 30h
0x18006a74c  pop     r15
0x18006a74e  pop     r14
0x18006a750  pop     r12
0x18006a752  pop     rdi
0x18006a753  pop     rsi
0x18006a754  pop     rbx
0x18006a755  pop     rbp
0x18006a756  retn
```
