# LookUpTableFlushComplete

- ea: `0x180024404`
- end: `0x180024774`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000df08`
- `0x180024110`
- `0x180024910`
- `0x180024970`
- `0x180024a30`

## callees

- `0x18000196c`
- `0x180002154`
- `0x18000fcd0`
- `0x18002404c`
- `0x180024404`
- `0x1800249e8`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v3 + 272) )
    {
      if ( (unsigned int)dword_1800352C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800352C0, 0x200000000000LL) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          *(_QWORD *)(*(_QWORD *)(a1 + 328) + 8LL),
          (__int64)byte_18002E5A5);
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x180024404  push    rbp
0x180024406  push    rbx
0x180024407  push    rsi
0x180024408  push    rdi
0x180024409  lea     rbp, [rsp-98h]
0x180024411  sub     rsp, 238h
0x180024418  mov     rax, cs:__security_cookie
0x18002441f  xor     rax, rsp
0x180024422  mov     [rbp+0B0h+var_28], rax
0x180024429  mov     edx, [rcx+100h]
0x18002442f  xor     edi, edi
0x180024431  mov     rbx, rcx
0x180024434  test    edx, edx
0x180024436  jz      loc_180024759
0x18002443c  call    UpdateInternalStatsOnFlush
0x180024441  lea     esi, [rdi+20h]
0x180024444  cmp     [rcx+110h], rdi
0x18002444b  jz      loc_180024749
0x180024451  mov     eax, cs:dword_1800352C0
0x180024457  cmp     eax, 5
0x18002445a  jbe     loc_18002472F
0x180024460  mov     rdx, 200000000000h
0x18002446a  lea     rcx, dword_1800352C0
0x180024471  call    _tlgKeywordOn
0x180024476  test    al, al
0x180024478  jz      loc_18002472F
0x18002447e  lea     ecx, [rdi+2Ah]
0x180024481  mov     [rbp+0B0h+var_130], 4
0x180024485  lea     rax, aSummarycount; "SummaryCount"
0x18002448c  mov     [rbp+0B0h+var_B0], cx
0x180024490  mov     [rbp+0B0h+var_C8], rax
0x180024494  lea     eax, [rdi+18h]
0x180024497  mov     [rbp+0B0h+var_C0], ax
0x18002449b  mov     eax, [rbx+134h]
0x1800244a1  mov     [rbp+0B0h+var_118], rax
0x1800244a5  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800244ac  mov     [rbp+0B0h+var_B8], rax
0x1800244b0  mov     eax, [rbx+130h]
0x1800244b6  mov     [rbp+0B0h+var_110], rax
0x1800244ba  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1800244c1  mov     [rbp+0B0h+var_A8], rax
0x1800244c5  mov     eax, [rbx+12Ch]
0x1800244cb  mov     [rbp+0B0h+var_108], rax
0x1800244cf  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800244d6  mov     [rbp+0B0h+var_98], rax
0x1800244da  mov     eax, [rbx+128h]
0x1800244e0  mov     [rbp+0B0h+var_100], rax
0x1800244e4  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x1800244eb  mov     [rbp+0B0h+var_88], rax
0x1800244ef  mov     eax, [rbx+124h]
0x1800244f5  mov     [rbp+0B0h+var_F8], rax
0x1800244f9  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180024500  mov     [rbp+0B0h+var_78], rax
0x180024504  mov     rax, [rbx+110h]
0x18002450b  mov     [rbp+0B0h+var_F0], rax
0x18002450f  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180024516  mov     [rbp+0B0h+var_68], rax
0x18002451a  lea     eax, [rdi+26h]
0x18002451d  mov     [rbp+0B0h+var_60], ax
0x180024521  mov     eax, [rbx+120h]
0x180024527  mov     [rbp+0B0h+var_E8], rax
0x18002452b  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180024532  mov     [rbp+0B0h+var_58], rax
0x180024536  mov     rax, [rbx+118h]
0x18002453d  mov     [rbp+0B0h+var_E0], rax
0x180024541  lea     rax, aNumflushes; "NumFlushes"
0x180024548  mov     [rbp+0B0h+var_48], rax
0x18002454c  lea     eax, [rdi+14h]
0x18002454f  mov     [rbp+0B0h+var_40], ax
0x180024553  mov     rax, [rbx+148h]
0x18002455a  mov     [rbp+0B0h+var_A0], cx
0x18002455e  mov     [rbp+0B0h+var_90], cx
0x180024562  lea     ecx, [rdi+22h]
0x180024565  mov     [rbp+0B0h+var_124], 1
0x18002456c  mov     [rbp+0B0h+var_12F], 4
0x180024570  mov     [rbp+0B0h+var_12E], 4
0x180024574  mov     [rbp+0B0h+var_12D], 4
0x180024578  mov     [rbp+0B0h+var_12C], 4
0x18002457c  mov     [rbp+0B0h+var_80], cx
0x180024580  mov     [rbp+0B0h+var_12B], 4
0x180024584  mov     [rbp+0B0h+var_70], cx
0x180024588  mov     [rbp+0B0h+var_12A], 4
0x18002458c  mov     [rbp+0B0h+var_129], 4
0x180024590  mov     [rbp+0B0h+var_50], si
0x180024594  mov     [rbp+0B0h+var_128], 4
0x180024598  mov     rcx, [rax+8]
0x18002459c  lea     rax, [rbp+0B0h+var_38]
0x1800245a0  mov     [rbp+0B0h+var_D8], rax
0x1800245a4  lea     rax, [rbp+0B0h+var_130]
0x1800245a8  mov     [rsp+250h+var_138], rax
0x1800245b0  lea     rax, [rbp+0B0h+var_124]
0x1800245b4  mov     [rsp+250h+var_140], rax
0x1800245bc  lea     rax, [rbp+0B0h+var_C8]
0x1800245c0  movups  xmm0, xmmword ptr [rcx-10h]
0x1800245c4  mov     [rsp+250h+var_148], rax
0x1800245cc  lea     rax, [rbp+0B0h+var_12F]
0x1800245d0  mov     [rsp+250h+var_150], rax
0x1800245d8  lea     rax, [rbp+0B0h+var_118]
0x1800245dc  mov     [rsp+250h+var_158], rax
0x1800245e4  lea     rax, [rbp+0B0h+var_B8]
0x1800245e8  mov     [rsp+250h+var_160], rax
0x1800245f0  lea     rax, [rbp+0B0h+var_12E]
0x1800245f4  movdqu  [rbp+0B0h+var_38], xmm0
0x1800245f9  mov     [rbp+0B0h+var_127], dil
0x1800245fd  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180024604  mov     [rbp+0B0h+var_11C], 12Ch
0x18002460b  mov     [rbp+0B0h+var_D0], 1000000h
0x180024613  mov     [rsp+250h+var_168], rax
0x18002461b  lea     rdx, byte_18002E5A5
0x180024622  lea     rax, [rbp+0B0h+var_110]
0x180024626  mov     [rsp+250h+var_170], rax
0x18002462e  lea     rax, [rbp+0B0h+var_A8]
0x180024632  mov     [rsp+250h+var_178], rax
0x18002463a  lea     rax, [rbp+0B0h+var_12D]
0x18002463e  mov     [rsp+250h+var_180], rax
0x180024646  lea     rax, [rbp+0B0h+var_108]
0x18002464a  mov     [rsp+250h+var_188], rax
0x180024652  lea     rax, [rbp+0B0h+var_98]
0x180024656  mov     [rsp+250h+var_190], rax
0x18002465e  lea     rax, [rbp+0B0h+var_12C]
0x180024662  mov     [rsp+250h+var_198], rax
0x18002466a  lea     rax, [rbp+0B0h+var_100]
0x18002466e  mov     [rsp+250h+var_1A0], rax
0x180024676  lea     rax, [rbp+0B0h+var_88]
0x18002467a  mov     [rsp+250h+var_1A8], rax
0x180024682  lea     rax, [rbp+0B0h+var_12B]
0x180024686  mov     [rsp+250h+var_1B0], rax
0x18002468e  lea     rax, [rbp+0B0h+var_F8]
0x180024692  mov     [rsp+250h+var_1B8], rax
0x18002469a  lea     rax, [rbp+0B0h+var_78]
0x18002469e  mov     [rsp+250h+var_1C0], rax
0x1800246a6  lea     rax, [rbp+0B0h+var_12A]
0x1800246aa  mov     [rsp+250h+var_1C8], rax
0x1800246b2  lea     rax, [rbp+0B0h+var_F0]
0x1800246b6  mov     [rsp+250h+var_1D0], rax
0x1800246be  lea     rax, [rbp+0B0h+var_68]
0x1800246c2  mov     [rsp+250h+var_1D8], rax
0x1800246c7  lea     rax, [rbp+0B0h+var_129]
0x1800246cb  mov     [rsp+250h+var_1E0], rax
0x1800246d0  lea     rax, [rbp+0B0h+var_E8]
0x1800246d4  mov     [rsp+250h+var_1E8], rax
0x1800246d9  lea     rax, [rbp+0B0h+var_58]
0x1800246dd  mov     [rsp+250h+var_1F0], rax
0x1800246e2  lea     rax, [rbp+0B0h+var_128]
0x1800246e6  mov     [rsp+250h+var_1F8], rax
0x1800246eb  lea     rax, [rbp+0B0h+var_E0]
0x1800246ef  mov     [rsp+250h+var_200], rax
0x1800246f4  lea     rax, [rbp+0B0h+var_48]
0x1800246f8  mov     [rsp+250h+var_208], rax
0x1800246fd  lea     rax, [rbp+0B0h+var_D8]
0x180024701  mov     [rsp+250h+var_210], rax
0x180024706  lea     rax, [rbp+0B0h+var_127]
0x18002470a  mov     [rsp+250h+var_218], rax
0x18002470f  lea     rax, [rbp+0B0h+var_120]
0x180024713  mov     [rsp+250h+var_220], rax
0x180024718  lea     rax, [rbp+0B0h+var_11C]
0x18002471c  mov     [rsp+250h+var_228], rax
0x180024721  lea     rax, [rbp+0B0h+var_D0]
0x180024725  mov     [rsp+250h+var_230], rax
0x18002472a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18002472f  xorps   xmm0, xmm0
0x180024732  xor     eax, eax
0x180024734  movups  xmmword ptr [rbx+110h], xmm0
0x18002473b  movups  xmmword ptr [rbx+120h], xmm0
0x180024742  mov     [rbx+130h], rax
0x180024749  mov     edx, edi
0x18002474b  mov     rcx, rbx
0x18002474e  call    FlushLookUpTableBucket
0x180024753  inc     edi
0x180024755  cmp     edi, esi
0x180024757  jb      short loc_180024749
0x180024759  mov     rcx, [rbp+0B0h+var_28]
0x180024760  xor     rcx, rsp; StackCookie
0x180024763  call    __security_check_cookie
0x180024768  add     rsp, 238h
0x18002476f  pop     rdi
0x180024770  pop     rsi
0x180024771  pop     rbx
0x180024772  pop     rbp
0x180024773  retn
```
