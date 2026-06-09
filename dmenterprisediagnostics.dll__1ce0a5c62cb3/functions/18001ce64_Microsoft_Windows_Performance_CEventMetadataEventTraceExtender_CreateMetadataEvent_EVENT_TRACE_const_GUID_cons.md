# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18001ce64`
- end: `0x18001d282`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1054`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001d360`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180003714`
- `0x180003b10`
- `0x180018998`
- `0x18001c358`
- `0x18001c660`
- `0x18001ce64`
- `0x18001db88`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cf44`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d156`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cf44`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001d156`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001cf58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d16e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001cf58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d16e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  FARPROC v8; // rax
  int v9; // eax
  FARPROC v10; // rax
  unsigned int v11; // eax
  void *v12; // rcx
  void *v13; // rax
  FARPROC v14; // rax
  __int64 result; // rax
  __int64 v16; // rcx
  ULONGLONG Keyword; // rax
  __int64 i; // rsi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r12
  __int64 v22; // rbx
  unsigned int v23; // ecx
  unsigned int v24; // ebx
  FARPROC v25; // rax
  int v26; // eax
  unsigned int v27; // eax
  void *v28; // rcx
  void *v29; // rax
  FARPROC v30; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v33[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v34[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v36; // [rsp+70h] [rbp-90h]
  __int128 v37; // [rsp+90h] [rbp-70h]
  __int128 v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  __int16 v40; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[22]; // [rsp+C2h] [rbp-3Eh] BYREF
  struct _GUID v42; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DESCRIPTOR v43; // [rsp+E8h] [rbp-18h]
  _BYTE v44[32]; // [rsp+130h] [rbp+30h] BYREF

  memset_0(v41, 0, 0x6Eu);
  v40 = 112;
  v42 = *a3;
  v43 = *a4;
  LODWORD(Size) = *((_DWORD *)this + 16);
  v8 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 288);
  v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v8)(
         &v40,
         0,
         0,
         *((_QWORD *)this + 7),
         &Size);
  if ( v9 == 1168 )
  {
    v43.Keyword = 0;
    v10 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 288);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v10)(
           &v40,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
  }
  if ( v9 == 122 )
  {
    v11 = Size;
    if ( (unsigned int)Size <= *((_DWORD *)this + 16) )
      return 1;
    v12 = (void *)*((_QWORD *)this + 7);
    if ( v12 )
    {
      free(v12);
      *((_QWORD *)this + 7) = 0;
      v11 = Size;
    }
    v13 = malloc(v11);
    *((_QWORD *)this + 7) = v13;
    if ( !v13 )
      return 2147942414LL;
    *((_DWORD *)this + 16) = Size;
    v14 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 288);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v14)(
           &v40,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
  }
  if ( v9 )
    return 1;
  v16 = *((_QWORD *)this + 7);
  if ( !*(_QWORD *)(v16 + 40) )
  {
    Keyword = a4->Keyword;
    if ( Keyword )
      *(_QWORD *)(v16 + 40) = Keyword;
  }
  v32 = *((_QWORD *)this + 7);
  Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(
    (_DWORD)this + 88,
    v32,
    Size,
    (unsigned int)&v32,
    (__int64)&Size);
  v35 = *(_OWORD *)&a2->Header.Size;
  v36 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v37 = *(_OWORD *)&a2->InstanceId;
  v38 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v39) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(struct _GUID *)&v36.m256i_u64[1] = EventMetadataGuid;
  DWORD1(v35) = 32;
  *((_QWORD *)&v38 + 1) = v32;
  LODWORD(v39) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v35,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 320) )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v19 = *((_QWORD *)this + 7);
        if ( (unsigned int)i >= *(_DWORD *)(v19 + 100) )
          return 0;
        if ( (*(_BYTE *)(v19 + 24 * i + 112) & 1) == 0 )
        {
          v20 = *(unsigned int *)(v19 + 24 * i + 124);
          if ( (_DWORD)v20 )
          {
            v21 = v19 + v20;
            v22 = *(_QWORD *)std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Try_emplace<_GUID const &,>(
                               (char *)this + 40,
                               v33,
                               a3);
            std::wstring::wstring((__int64)v44, v21);
            LOBYTE(v22) = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                                       v22 + 64,
                                       v34,
                                       v44)
                                   + 8);
            std::wstring::~wstring((__int64)v44);
            if ( (_BYTE)v22 )
            {
              v23 = *((_DWORD *)this + 20);
              v24 = v23 - 16;
              if ( v23 < 0x10 )
                v24 = 0;
              LODWORD(v32) = v24;
              v25 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 320);
              v26 = ((__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))v25)(
                      &v40,
                      v21,
                      (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0),
                      &v32);
              if ( v26 == 122 )
              {
                v27 = v32;
                if ( (unsigned int)v32 <= v24 )
                  continue;
                v28 = (void *)*((_QWORD *)this + 9);
                if ( v28 )
                {
                  free(v28);
                  *((_QWORD *)this + 9) = 0;
                  v27 = v32;
                }
                v29 = malloc(v27 + 16LL);
                *((_QWORD *)this + 9) = v29;
                if ( !v29 )
                  return 2147942414LL;
                *((_DWORD *)this + 20) = v32 + 16;
                v30 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)this + 320);
                v26 = ((__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))v30)(
                        &v40,
                        v21,
                        *((_QWORD *)this + 9) + 16LL,
                        &v32);
              }
              if ( !v26 )
              {
                v35 = *(_OWORD *)&a2->Header.Size;
                v36 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
                v37 = *(_OWORD *)&a2->InstanceId;
                v38 = *(_OWORD *)a2->ParentGuid.Data4;
                v39 = *(_QWORD *)&a2->MofLength;
                *(struct _GUID *)&v36.m256i_u64[1] = EventMetadataGuid;
                DWORD1(v35) = 33;
                *(struct _GUID *)*((_QWORD *)this + 9) = *a3;
                *((_QWORD *)&v38 + 1) = *((_QWORD *)this + 9);
                LODWORD(v39) = v32 + 16;
                if ( (unsigned __int64)(unsigned int)(v32 + 16) + 48 <= 0xFFB8 )
                {
                  result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                         + 192LL))(
                             *((_QWORD *)this + 2),
                             &v35,
                             0,
                             0);
                  if ( (int)result < 0 )
                    return result;
                }
              }
            }
          }
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ce64  push    rbp
0x18001ce66  push    rbx
0x18001ce67  push    rsi
0x18001ce68  push    rdi
0x18001ce69  push    r12
0x18001ce6b  push    r13
0x18001ce6d  push    r14
0x18001ce6f  push    r15
0x18001ce71  lea     rbp, [rsp-68h]
0x18001ce76  sub     rsp, 168h
0x18001ce7d  mov     rax, cs:__security_cookie
0x18001ce84  xor     rax, rsp
0x18001ce87  mov     [rbp+0A0h+var_50], rax
0x18001ce8b  mov     rsi, r9
0x18001ce8e  mov     r13, r8
0x18001ce91  mov     r14, rdx
0x18001ce94  mov     rdi, rcx
0x18001ce97  xor     edx, edx; Val
0x18001ce99  lea     r8d, [rdx+6Eh]; Size
0x18001ce9d  lea     rcx, [rbp+0A0h+var_DE]; void *
0x18001cea1  call    memset_0
0x18001cea6  mov     eax, 70h ; 'p'
0x18001ceab  mov     [rbp+0A0h+var_E0], ax
0x18001ceaf  movups  xmm0, xmmword ptr [r13+0]
0x18001ceb4  movdqu  [rbp+0A0h+var_C8], xmm0
0x18001ceb9  mov     rax, [rsi]
0x18001cebc  mov     [rbp+0A0h+var_B8], rax
0x18001cec0  mov     rax, [rsi+8]
0x18001cec4  mov     [rbp+0A0h+var_B0], rax
0x18001cec8  mov     eax, [rdi+40h]
0x18001cecb  mov     dword ptr [rsp+1A0h+Size], eax
0x18001cecf  lea     rbx, [rdi+120h]
0x18001ced6  mov     rcx, rbx
0x18001ced9  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001cede  lea     rcx, [rsp+1A0h+Size]
0x18001cee3  mov     [rsp+1A0h+var_180], rcx
0x18001cee8  mov     r9, [rdi+38h]
0x18001ceec  xor     r8d, r8d
0x18001ceef  xor     edx, edx
0x18001cef1  lea     rcx, [rbp+0A0h+var_E0]
0x18001cef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cefa  cmp     eax, 490h
0x18001ceff  jnz     short loc_18001CF2D
0x18001cf01  mov     [rbp+0A0h+var_B0], 0
0x18001cf09  mov     rcx, rbx
0x18001cf0c  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001cf11  lea     rcx, [rsp+1A0h+Size]
0x18001cf16  mov     [rsp+1A0h+var_180], rcx
0x18001cf1b  mov     r9, [rdi+38h]
0x18001cf1f  xor     r8d, r8d
0x18001cf22  xor     edx, edx
0x18001cf24  lea     rcx, [rbp+0A0h+var_E0]
0x18001cf28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf2d  cmp     eax, 7Ah ; 'z'
0x18001cf30  jnz     short loc_18001CF96
0x18001cf32  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001cf36  cmp     eax, [rdi+40h]
0x18001cf39  jbe     short loc_18001CF9A
0x18001cf3b  mov     rcx, [rdi+38h]; Block
0x18001cf3f  test    rcx, rcx
0x18001cf42  jz      short loc_18001CF56
0x18001cf44  call    cs:__imp_free
0x18001cf4a  mov     qword ptr [rdi+38h], 0
0x18001cf52  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001cf56  mov     ecx, eax; Size
0x18001cf58  call    cs:__imp_malloc
0x18001cf5e  mov     [rdi+38h], rax
0x18001cf62  test    rax, rax
0x18001cf65  jz      loc_18001D259
0x18001cf6b  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001cf6f  mov     [rdi+40h], eax
0x18001cf72  mov     rcx, rbx
0x18001cf75  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001cf7a  lea     rcx, [rsp+1A0h+Size]
0x18001cf7f  mov     [rsp+1A0h+var_180], rcx
0x18001cf84  mov     r9, [rdi+38h]
0x18001cf88  xor     r8d, r8d
0x18001cf8b  xor     edx, edx
0x18001cf8d  lea     rcx, [rbp+0A0h+var_E0]
0x18001cf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf96  test    eax, eax
0x18001cf98  jz      short loc_18001CFA4
0x18001cf9a  mov     eax, 1
0x18001cf9f  jmp     loc_18001D262
0x18001cfa4  mov     rcx, [rdi+38h]
0x18001cfa8  cmp     qword ptr [rcx+28h], 0
0x18001cfad  jnz     short loc_18001CFBC
0x18001cfaf  mov     rax, [rsi+8]
0x18001cfb3  test    rax, rax
0x18001cfb6  jz      short loc_18001CFBC
0x18001cfb8  mov     [rcx+28h], rax
0x18001cfbc  mov     rdx, [rdi+38h]
0x18001cfc0  mov     [rsp+1A0h+var_168], rdx
0x18001cfc5  lea     rcx, [rdi+58h]
0x18001cfc9  lea     rax, [rsp+1A0h+Size]
0x18001cfce  mov     [rsp+1A0h+var_180], rax
0x18001cfd3  lea     r9, [rsp+1A0h+var_168]
0x18001cfd8  mov     r8d, dword ptr [rsp+1A0h+Size]
0x18001cfdd  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18001cfe2  movups  xmm0, xmmword ptr [r14]
0x18001cfe6  movaps  [rsp+1A0h+var_140], xmm0
0x18001cfeb  movups  xmm1, xmmword ptr [r14+10h]
0x18001cff0  movaps  [rsp+1A0h+var_130], xmm1
0x18001cff5  movups  xmm0, xmmword ptr [r14+20h]
0x18001cffa  movaps  [rbp+0A0h+var_120], xmm0
0x18001cffe  movups  xmm1, xmmword ptr [r14+30h]
0x18001d003  movaps  [rbp+0A0h+var_110], xmm1
0x18001d007  movups  xmm0, xmmword ptr [r14+40h]
0x18001d00c  movaps  [rbp+0A0h+var_100], xmm0
0x18001d010  movsd   xmm1, qword ptr [r14+50h]
0x18001d016  movsd   [rbp+0A0h+var_F0], xmm1
0x18001d01b  movups  xmm0, xmmword ptr cs:EventMetadataGuid.Data1
0x18001d022  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001d028  mov     dword ptr [rsp+1A0h+var_140+4], 20h ; ' '
0x18001d030  mov     rax, [rsp+1A0h+var_168]
0x18001d035  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001d039  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001d03d  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001d040  lea     rcx, [rax+30h]
0x18001d044  cmp     rcx, 0FFB8h
0x18001d04b  ja      short loc_18001D073
0x18001d04d  mov     rcx, [rdi+10h]
0x18001d051  mov     rax, [rcx]
0x18001d054  xor     r9d, r9d
0x18001d057  xor     r8d, r8d
0x18001d05a  lea     rdx, [rsp+1A0h+var_140]
0x18001d05f  mov     rax, [rax+0C0h]
0x18001d066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d06b  test    eax, eax
0x18001d06d  js      loc_18001D262
0x18001d073  lea     r15, [rdi+140h]
0x18001d07a  mov     rcx, r15
0x18001d07d  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001d082  test    rax, rax
0x18001d085  jz      loc_18001D260
0x18001d08b  xor     esi, esi
0x18001d08d  mov     rcx, [rdi+38h]
0x18001d091  cmp     esi, [rcx+64h]
0x18001d094  jnb     loc_18001D260
0x18001d09a  lea     rdx, [rsi+rsi*2]
0x18001d09e  test    byte ptr [rcx+rdx*8+70h], 1
0x18001d0a3  jnz     loc_18001D252
0x18001d0a9  mov     eax, [rcx+rdx*8+7Ch]
0x18001d0ad  test    eax, eax
0x18001d0af  jz      loc_18001D252
0x18001d0b5  lea     r12, [rcx+rax]
0x18001d0b9  lea     rcx, [rdi+28h]
0x18001d0bd  mov     r8, r13
0x18001d0c0  lea     rdx, [rsp+1A0h+var_160]
0x18001d0c5  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18001d0ca  mov     rbx, [rax]
0x18001d0cd  mov     rdx, r12
0x18001d0d0  lea     rcx, [rbp+0A0h+var_70]
0x18001d0d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d0d9  nop
0x18001d0da  lea     r8, [rbp+0A0h+var_70]
0x18001d0de  lea     rdx, [rsp+1A0h+var_150]
0x18001d0e3  lea     rcx, [rbx+40h]
0x18001d0e7  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001d0ec  mov     bl, [rax+8]
0x18001d0ef  lea     rcx, [rbp+0A0h+var_70]
0x18001d0f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d0f8  test    bl, bl
0x18001d0fa  jz      loc_18001D252
0x18001d100  mov     ecx, [rdi+50h]
0x18001d103  lea     ebx, [rcx-10h]
0x18001d106  xor     eax, eax
0x18001d108  cmp     ecx, 10h
0x18001d10b  cmovb   ebx, eax
0x18001d10e  mov     dword ptr [rsp+1A0h+var_168], ebx
0x18001d112  mov     rcx, r15
0x18001d115  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001d11a  mov     rcx, [rdi+48h]
0x18001d11e  lea     rdx, [rcx+10h]
0x18001d122  neg     rcx
0x18001d125  sbb     r8, r8
0x18001d128  and     r8, rdx
0x18001d12b  lea     r9, [rsp+1A0h+var_168]
0x18001d130  mov     rdx, r12
0x18001d133  lea     rcx, [rbp+0A0h+var_E0]
0x18001d137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d13c  cmp     eax, 7Ah ; 'z'
0x18001d13f  jnz     short loc_18001D1AC
0x18001d141  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001d145  cmp     eax, ebx
0x18001d147  jbe     loc_18001D252
0x18001d14d  mov     rcx, [rdi+48h]; Block
0x18001d151  test    rcx, rcx
0x18001d154  jz      short loc_18001D168
0x18001d156  call    cs:__imp_free
0x18001d15c  mov     qword ptr [rdi+48h], 0
0x18001d164  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001d168  mov     ecx, eax
0x18001d16a  add     rcx, 10h; Size
0x18001d16e  call    cs:__imp_malloc
0x18001d174  mov     [rdi+48h], rax
0x18001d178  test    rax, rax
0x18001d17b  jz      loc_18001D259
0x18001d181  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001d185  add     eax, 10h
0x18001d188  mov     [rdi+50h], eax
0x18001d18b  mov     rcx, r15
0x18001d18e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001d193  mov     r8, [rdi+48h]
0x18001d197  add     r8, 10h
0x18001d19b  lea     r9, [rsp+1A0h+var_168]
0x18001d1a0  mov     rdx, r12
0x18001d1a3  lea     rcx, [rbp+0A0h+var_E0]
0x18001d1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1ac  test    eax, eax
0x18001d1ae  jnz     loc_18001D252
0x18001d1b4  movups  xmm0, xmmword ptr [r14]
0x18001d1b8  movaps  [rsp+1A0h+var_140], xmm0
0x18001d1bd  movups  xmm1, xmmword ptr [r14+10h]
0x18001d1c2  movaps  [rsp+1A0h+var_130], xmm1
0x18001d1c7  movups  xmm0, xmmword ptr [r14+20h]
0x18001d1cc  movaps  [rbp+0A0h+var_120], xmm0
0x18001d1d0  movups  xmm1, xmmword ptr [r14+30h]
0x18001d1d5  movaps  [rbp+0A0h+var_110], xmm1
0x18001d1d9  movups  xmm0, xmmword ptr [r14+40h]
0x18001d1de  movaps  [rbp+0A0h+var_100], xmm0
0x18001d1e2  movsd   xmm1, qword ptr [r14+50h]
0x18001d1e8  movsd   [rbp+0A0h+var_F0], xmm1
0x18001d1ed  movups  xmm0, xmmword ptr cs:EventMetadataGuid.Data1
0x18001d1f4  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001d1fa  mov     dword ptr [rsp+1A0h+var_140+4], 21h ; '!'
0x18001d202  movups  xmm0, xmmword ptr [r13+0]
0x18001d207  mov     rax, [rdi+48h]
0x18001d20b  movdqu  xmmword ptr [rax], xmm0
0x18001d20f  mov     rax, [rdi+48h]
0x18001d213  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001d217  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001d21b  add     eax, 10h
0x18001d21e  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001d221  mov     ecx, eax
0x18001d223  add     rcx, 30h ; '0'
0x18001d227  cmp     rcx, 0FFB8h
0x18001d22e  ja      short loc_18001D252
0x18001d230  mov     rcx, [rdi+10h]
0x18001d234  mov     rax, [rcx]
0x18001d237  xor     r9d, r9d
0x18001d23a  xor     r8d, r8d
0x18001d23d  lea     rdx, [rsp+1A0h+var_140]
0x18001d242  mov     rax, [rax+0C0h]
0x18001d249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d24e  test    eax, eax
0x18001d250  js      short loc_18001D262
0x18001d252  inc     esi
0x18001d254  jmp     loc_18001D08D
0x18001d259  mov     eax, 8007000Eh
0x18001d25e  jmp     short loc_18001D262
0x18001d260  xor     eax, eax
0x18001d262  mov     rcx, [rbp+0A0h+var_50]
0x18001d266  xor     rcx, rsp; StackCookie
0x18001d269  call    __security_check_cookie
0x18001d26e  add     rsp, 168h
0x18001d275  pop     r15
0x18001d277  pop     r14
0x18001d279  pop     r13
0x18001d27b  pop     r12
0x18001d27d  pop     rdi
0x18001d27e  pop     rsi
0x18001d27f  pop     rbx
0x18001d280  pop     rbp
0x18001d281  retn
```
