# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18001d97c`
- end: `0x18001ddb3`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1079`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001de90`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180003768`
- `0x180003b14`
- `0x18001934c`
- `0x18001ce3c`
- `0x18001d13c`
- `0x18001d97c`
- `0x18001e6b8`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001da5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001dc7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001da5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001dc7a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001da76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001dc98`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001da76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001dc98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  __int64 (__fastcall *v8)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  int v9; // eax
  __int64 (__fastcall *v10)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  unsigned int v11; // eax
  void *v12; // rcx
  void *v13; // rax
  __int64 (__fastcall *v14)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
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
  __int64 (__fastcall *v25)(__int16 *, __int64, __int64, __int64 *); // rax
  int v26; // eax
  unsigned int v27; // eax
  void *v28; // rcx
  void *v29; // rax
  __int64 (__fastcall *v30)(__int16 *, __int64, __int64, __int64 *); // rax
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
  v8 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
  v9 = v8(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
  if ( v9 == 1168 )
  {
    v43.Keyword = 0;
    v10 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
    v9 = v10(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
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
    v14 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
    v9 = v14(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
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
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320) )
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
            std::wstring::wstring(v44, v21);
            LOBYTE(v22) = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                                       v22 + 64,
                                       v34,
                                       v44)
                                   + 8);
            std::wstring::~wstring(v44);
            if ( (_BYTE)v22 )
            {
              v23 = *((_DWORD *)this + 20);
              v24 = v23 - 16;
              if ( v23 < 0x10 )
                v24 = 0;
              LODWORD(v32) = v24;
              v25 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320);
              v26 = v25(&v40, v21, (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0), &v32);
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
                v30 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320);
                v26 = v30(&v40, v21, *((_QWORD *)this + 9) + 16LL, &v32);
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
0x18001d97c  push    rbp
0x18001d97e  push    rbx
0x18001d97f  push    rsi
0x18001d980  push    rdi
0x18001d981  push    r12
0x18001d983  push    r13
0x18001d985  push    r14
0x18001d987  push    r15
0x18001d989  lea     rbp, [rsp-68h]
0x18001d98e  sub     rsp, 168h
0x18001d995  mov     rax, cs:__security_cookie
0x18001d99c  xor     rax, rsp
0x18001d99f  mov     [rbp+0A0h+var_50], rax
0x18001d9a3  mov     rsi, r9
0x18001d9a6  mov     r13, r8
0x18001d9a9  mov     r14, rdx
0x18001d9ac  mov     rdi, rcx
0x18001d9af  xor     edx, edx; Val
0x18001d9b1  lea     r8d, [rdx+6Eh]; Size
0x18001d9b5  lea     rcx, [rbp+0A0h+var_DE]; void *
0x18001d9b9  call    memset_0
0x18001d9be  mov     eax, 70h ; 'p'
0x18001d9c3  mov     [rbp+0A0h+var_E0], ax
0x18001d9c7  movups  xmm0, xmmword ptr [r13+0]
0x18001d9cc  movdqu  [rbp+0A0h+var_C8], xmm0
0x18001d9d1  mov     rax, [rsi]
0x18001d9d4  mov     [rbp+0A0h+var_B8], rax
0x18001d9d8  mov     rax, [rsi+8]
0x18001d9dc  mov     [rbp+0A0h+var_B0], rax
0x18001d9e0  mov     eax, [rdi+40h]
0x18001d9e3  mov     dword ptr [rsp+1A0h+Size], eax
0x18001d9e7  lea     rbx, [rdi+120h]
0x18001d9ee  mov     rcx, rbx
0x18001d9f1  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001d9f6  lea     rcx, [rsp+1A0h+Size]
0x18001d9fb  mov     [rsp+1A0h+var_180], rcx
0x18001da00  mov     r9, [rdi+38h]
0x18001da04  xor     r8d, r8d
0x18001da07  xor     edx, edx
0x18001da09  lea     rcx, [rbp+0A0h+var_E0]
0x18001da0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da12  cmp     eax, 490h
0x18001da17  jnz     short loc_18001DA45
0x18001da19  mov     [rbp+0A0h+var_B0], 0
0x18001da21  mov     rcx, rbx
0x18001da24  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001da29  lea     rcx, [rsp+1A0h+Size]
0x18001da2e  mov     [rsp+1A0h+var_180], rcx
0x18001da33  mov     r9, [rdi+38h]
0x18001da37  xor     r8d, r8d
0x18001da3a  xor     edx, edx
0x18001da3c  lea     rcx, [rbp+0A0h+var_E0]
0x18001da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da45  cmp     eax, 7Ah ; 'z'
0x18001da48  jnz     short loc_18001DABA
0x18001da4a  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001da4e  cmp     eax, [rdi+40h]
0x18001da51  jbe     short loc_18001DABE
0x18001da53  mov     rcx, [rdi+38h]; Block
0x18001da57  test    rcx, rcx
0x18001da5a  jz      short loc_18001DA74
0x18001da5c  call    cs:__imp_free
0x18001da63  nop     dword ptr [rax+rax+00h]
0x18001da68  mov     qword ptr [rdi+38h], 0
0x18001da70  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001da74  mov     ecx, eax; Size
0x18001da76  call    cs:__imp_malloc
0x18001da7d  nop     dword ptr [rax+rax+00h]
0x18001da82  mov     [rdi+38h], rax
0x18001da86  test    rax, rax
0x18001da89  jz      loc_18001DD89
0x18001da8f  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001da93  mov     [rdi+40h], eax
0x18001da96  mov     rcx, rbx
0x18001da99  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001da9e  lea     rcx, [rsp+1A0h+Size]
0x18001daa3  mov     [rsp+1A0h+var_180], rcx
0x18001daa8  mov     r9, [rdi+38h]
0x18001daac  xor     r8d, r8d
0x18001daaf  xor     edx, edx
0x18001dab1  lea     rcx, [rbp+0A0h+var_E0]
0x18001dab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daba  test    eax, eax
0x18001dabc  jz      short loc_18001DAC8
0x18001dabe  mov     eax, 1
0x18001dac3  jmp     loc_18001DD92
0x18001dac8  mov     rcx, [rdi+38h]
0x18001dacc  cmp     qword ptr [rcx+28h], 0
0x18001dad1  jnz     short loc_18001DAE0
0x18001dad3  mov     rax, [rsi+8]
0x18001dad7  test    rax, rax
0x18001dada  jz      short loc_18001DAE0
0x18001dadc  mov     [rcx+28h], rax
0x18001dae0  mov     rdx, [rdi+38h]
0x18001dae4  mov     [rsp+1A0h+var_168], rdx
0x18001dae9  lea     rcx, [rdi+58h]
0x18001daed  lea     rax, [rsp+1A0h+Size]
0x18001daf2  mov     [rsp+1A0h+var_180], rax
0x18001daf7  lea     r9, [rsp+1A0h+var_168]
0x18001dafc  mov     r8d, dword ptr [rsp+1A0h+Size]
0x18001db01  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18001db06  movups  xmm0, xmmword ptr [r14]
0x18001db0a  movaps  [rsp+1A0h+var_140], xmm0
0x18001db0f  movups  xmm1, xmmword ptr [r14+10h]
0x18001db14  movaps  [rsp+1A0h+var_130], xmm1
0x18001db19  movups  xmm0, xmmword ptr [r14+20h]
0x18001db1e  movaps  [rbp+0A0h+var_120], xmm0
0x18001db22  movups  xmm1, xmmword ptr [r14+30h]
0x18001db27  movaps  [rbp+0A0h+var_110], xmm1
0x18001db2b  movups  xmm0, xmmword ptr [r14+40h]
0x18001db30  movaps  [rbp+0A0h+var_100], xmm0
0x18001db34  movsd   xmm1, qword ptr [r14+50h]
0x18001db3a  movsd   [rbp+0A0h+var_F0], xmm1
0x18001db3f  movups  xmm0, xmmword ptr cs:EventMetadataGuid.Data1
0x18001db46  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001db4c  mov     dword ptr [rsp+1A0h+var_140+4], 20h ; ' '
0x18001db54  mov     rax, [rsp+1A0h+var_168]
0x18001db59  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001db5d  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001db61  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001db64  lea     rcx, [rax+30h]
0x18001db68  cmp     rcx, 0FFB8h
0x18001db6f  ja      short loc_18001DB97
0x18001db71  mov     rcx, [rdi+10h]
0x18001db75  mov     rax, [rcx]
0x18001db78  xor     r9d, r9d
0x18001db7b  xor     r8d, r8d
0x18001db7e  lea     rdx, [rsp+1A0h+var_140]
0x18001db83  mov     rax, [rax+0C0h]
0x18001db8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db8f  test    eax, eax
0x18001db91  js      loc_18001DD92
0x18001db97  lea     r15, [rdi+140h]
0x18001db9e  mov     rcx, r15
0x18001dba1  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001dba6  test    rax, rax
0x18001dba9  jz      loc_18001DD90
0x18001dbaf  xor     esi, esi
0x18001dbb1  mov     rcx, [rdi+38h]
0x18001dbb5  cmp     esi, [rcx+64h]
0x18001dbb8  jnb     loc_18001DD90
0x18001dbbe  lea     rdx, [rsi+rsi*2]
0x18001dbc2  test    byte ptr [rcx+rdx*8+70h], 1
0x18001dbc7  jnz     loc_18001DD82
0x18001dbcd  mov     eax, [rcx+rdx*8+7Ch]
0x18001dbd1  test    eax, eax
0x18001dbd3  jz      loc_18001DD82
0x18001dbd9  lea     r12, [rcx+rax]
0x18001dbdd  lea     rcx, [rdi+28h]
0x18001dbe1  mov     r8, r13
0x18001dbe4  lea     rdx, [rsp+1A0h+var_160]
0x18001dbe9  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18001dbee  mov     rbx, [rax]
0x18001dbf1  mov     rdx, r12
0x18001dbf4  lea     rcx, [rbp+0A0h+var_70]
0x18001dbf8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001dbfd  nop
0x18001dbfe  lea     r8, [rbp+0A0h+var_70]
0x18001dc02  lea     rdx, [rsp+1A0h+var_150]
0x18001dc07  lea     rcx, [rbx+40h]
0x18001dc0b  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001dc10  mov     bl, [rax+8]
0x18001dc13  lea     rcx, [rbp+0A0h+var_70]
0x18001dc17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dc1c  test    bl, bl
0x18001dc1e  jz      loc_18001DD82
0x18001dc24  mov     ecx, [rdi+50h]
0x18001dc27  lea     ebx, [rcx-10h]
0x18001dc2a  xor     eax, eax
0x18001dc2c  cmp     ecx, 10h
0x18001dc2f  cmovb   ebx, eax
0x18001dc32  mov     dword ptr [rsp+1A0h+var_168], ebx
0x18001dc36  mov     rcx, r15
0x18001dc39  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001dc3e  mov     rcx, [rdi+48h]
0x18001dc42  lea     rdx, [rcx+10h]
0x18001dc46  neg     rcx
0x18001dc49  sbb     r8, r8
0x18001dc4c  and     r8, rdx
0x18001dc4f  lea     r9, [rsp+1A0h+var_168]
0x18001dc54  mov     rdx, r12
0x18001dc57  lea     rcx, [rbp+0A0h+var_E0]
0x18001dc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc60  cmp     eax, 7Ah ; 'z'
0x18001dc63  jnz     short loc_18001DCDC
0x18001dc65  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001dc69  cmp     eax, ebx
0x18001dc6b  jbe     loc_18001DD82
0x18001dc71  mov     rcx, [rdi+48h]; Block
0x18001dc75  test    rcx, rcx
0x18001dc78  jz      short loc_18001DC92
0x18001dc7a  call    cs:__imp_free
0x18001dc81  nop     dword ptr [rax+rax+00h]
0x18001dc86  mov     qword ptr [rdi+48h], 0
0x18001dc8e  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001dc92  mov     ecx, eax
0x18001dc94  add     rcx, 10h; Size
0x18001dc98  call    cs:__imp_malloc
0x18001dc9f  nop     dword ptr [rax+rax+00h]
0x18001dca4  mov     [rdi+48h], rax
0x18001dca8  test    rax, rax
0x18001dcab  jz      loc_18001DD89
0x18001dcb1  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001dcb5  add     eax, 10h
0x18001dcb8  mov     [rdi+50h], eax
0x18001dcbb  mov     rcx, r15
0x18001dcbe  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001dcc3  mov     r8, [rdi+48h]
0x18001dcc7  add     r8, 10h
0x18001dccb  lea     r9, [rsp+1A0h+var_168]
0x18001dcd0  mov     rdx, r12
0x18001dcd3  lea     rcx, [rbp+0A0h+var_E0]
0x18001dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcdc  test    eax, eax
0x18001dcde  jnz     loc_18001DD82
0x18001dce4  movups  xmm0, xmmword ptr [r14]
0x18001dce8  movaps  [rsp+1A0h+var_140], xmm0
0x18001dced  movups  xmm1, xmmword ptr [r14+10h]
0x18001dcf2  movaps  [rsp+1A0h+var_130], xmm1
0x18001dcf7  movups  xmm0, xmmword ptr [r14+20h]
0x18001dcfc  movaps  [rbp+0A0h+var_120], xmm0
0x18001dd00  movups  xmm1, xmmword ptr [r14+30h]
0x18001dd05  movaps  [rbp+0A0h+var_110], xmm1
0x18001dd09  movups  xmm0, xmmword ptr [r14+40h]
0x18001dd0e  movaps  [rbp+0A0h+var_100], xmm0
0x18001dd12  movsd   xmm1, qword ptr [r14+50h]
0x18001dd18  movsd   [rbp+0A0h+var_F0], xmm1
0x18001dd1d  movups  xmm0, xmmword ptr cs:EventMetadataGuid.Data1
0x18001dd24  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001dd2a  mov     dword ptr [rsp+1A0h+var_140+4], 21h ; '!'
0x18001dd32  movups  xmm0, xmmword ptr [r13+0]
0x18001dd37  mov     rax, [rdi+48h]
0x18001dd3b  movdqu  xmmword ptr [rax], xmm0
0x18001dd3f  mov     rax, [rdi+48h]
0x18001dd43  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001dd47  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001dd4b  add     eax, 10h
0x18001dd4e  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001dd51  mov     ecx, eax
0x18001dd53  add     rcx, 30h ; '0'
0x18001dd57  cmp     rcx, 0FFB8h
0x18001dd5e  ja      short loc_18001DD82
0x18001dd60  mov     rcx, [rdi+10h]
0x18001dd64  mov     rax, [rcx]
0x18001dd67  xor     r9d, r9d
0x18001dd6a  xor     r8d, r8d
0x18001dd6d  lea     rdx, [rsp+1A0h+var_140]
0x18001dd72  mov     rax, [rax+0C0h]
0x18001dd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd7e  test    eax, eax
0x18001dd80  js      short loc_18001DD92
0x18001dd82  inc     esi
0x18001dd84  jmp     loc_18001DBB1
0x18001dd89  mov     eax, 8007000Eh
0x18001dd8e  jmp     short loc_18001DD92
0x18001dd90  xor     eax, eax
0x18001dd92  mov     rcx, [rbp+0A0h+var_50]
0x18001dd96  xor     rcx, rsp; StackCookie
0x18001dd99  call    __security_check_cookie
0x18001dd9e  add     rsp, 168h
0x18001dda5  pop     r15
0x18001dda7  pop     r14
0x18001dda9  pop     r13
0x18001ddab  pop     r12
0x18001ddad  pop     rdi
0x18001ddae  pop     rsi
0x18001ddaf  pop     rbx
0x18001ddb0  pop     rbp
0x18001ddb1  retn
```
