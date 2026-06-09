# LookUpTableFlushComplete

- ea: `0x14001d8c0`
- end: `0x14001dc30`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001d870`
- `0x14001dca0`
- `0x14001dd00`
- `0x14001ddc0`

## callees

- `0x140002124`
- `0x14000cfb0`
- `0x14001d7b8`
- `0x14001d8c0`
- `0x14001dd78`
- `0x14001e050`

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
      if ( (unsigned int)dword_140029078 > 5 && tlgKeywordOn((__int64)&dword_140029078, 0x200000000000LL) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          *(_QWORD *)(*(_QWORD *)(a1 + 328) + 8LL),
          (__int64)byte_140023759);
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
0x14001d8c0  push    rbp
0x14001d8c2  push    rbx
0x14001d8c3  push    rsi
0x14001d8c4  push    rdi
0x14001d8c5  lea     rbp, [rsp-98h]
0x14001d8cd  sub     rsp, 238h
0x14001d8d4  mov     rax, cs:__security_cookie
0x14001d8db  xor     rax, rsp
0x14001d8de  mov     [rbp+0B0h+var_28], rax
0x14001d8e5  mov     edx, [rcx+100h]
0x14001d8eb  xor     edi, edi
0x14001d8ed  mov     rbx, rcx
0x14001d8f0  test    edx, edx
0x14001d8f2  jz      loc_14001DC15
0x14001d8f8  call    UpdateInternalStatsOnFlush
0x14001d8fd  lea     esi, [rdi+20h]
0x14001d900  cmp     [rcx+110h], rdi
0x14001d907  jz      loc_14001DC05
0x14001d90d  mov     eax, cs:dword_140029078
0x14001d913  cmp     eax, 5
0x14001d916  jbe     loc_14001DBEB
0x14001d91c  mov     rdx, 200000000000h
0x14001d926  lea     rcx, dword_140029078
0x14001d92d  call    _tlgKeywordOn
0x14001d932  test    al, al
0x14001d934  jz      loc_14001DBEB
0x14001d93a  lea     ecx, [rdi+2Ah]
0x14001d93d  mov     [rbp+0B0h+var_130], 4
0x14001d941  lea     rax, aSummarycount; "SummaryCount"
0x14001d948  mov     [rbp+0B0h+var_B0], cx
0x14001d94c  mov     [rbp+0B0h+var_C8], rax
0x14001d950  lea     eax, [rdi+18h]
0x14001d953  mov     [rbp+0B0h+var_C0], ax
0x14001d957  mov     eax, [rbx+134h]
0x14001d95d  mov     [rbp+0B0h+var_118], rax
0x14001d961  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x14001d968  mov     [rbp+0B0h+var_B8], rax
0x14001d96c  mov     eax, [rbx+130h]
0x14001d972  mov     [rbp+0B0h+var_110], rax
0x14001d976  lea     rax, aNumallocationf; "NumAllocationFailures"
0x14001d97d  mov     [rbp+0B0h+var_A8], rax
0x14001d981  mov     eax, [rbx+12Ch]
0x14001d987  mov     [rbp+0B0h+var_108], rax
0x14001d98b  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x14001d992  mov     [rbp+0B0h+var_98], rax
0x14001d996  mov     eax, [rbx+128h]
0x14001d99c  mov     [rbp+0B0h+var_100], rax
0x14001d9a0  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x14001d9a7  mov     [rbp+0B0h+var_88], rax
0x14001d9ab  mov     eax, [rbx+124h]
0x14001d9b1  mov     [rbp+0B0h+var_F8], rax
0x14001d9b5  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x14001d9bc  mov     [rbp+0B0h+var_78], rax
0x14001d9c0  mov     rax, [rbx+110h]
0x14001d9c7  mov     [rbp+0B0h+var_F0], rax
0x14001d9cb  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x14001d9d2  mov     [rbp+0B0h+var_68], rax
0x14001d9d6  lea     eax, [rdi+26h]
0x14001d9d9  mov     [rbp+0B0h+var_60], ax
0x14001d9dd  mov     eax, [rbx+120h]
0x14001d9e3  mov     [rbp+0B0h+var_E8], rax
0x14001d9e7  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x14001d9ee  mov     [rbp+0B0h+var_58], rax
0x14001d9f2  mov     rax, [rbx+118h]
0x14001d9f9  mov     [rbp+0B0h+var_E0], rax
0x14001d9fd  lea     rax, aNumflushes; "NumFlushes"
0x14001da04  mov     [rbp+0B0h+var_48], rax
0x14001da08  lea     eax, [rdi+14h]
0x14001da0b  mov     [rbp+0B0h+var_40], ax
0x14001da0f  mov     rax, [rbx+148h]
0x14001da16  mov     [rbp+0B0h+var_A0], cx
0x14001da1a  mov     [rbp+0B0h+var_90], cx
0x14001da1e  lea     ecx, [rdi+22h]
0x14001da21  mov     [rbp+0B0h+var_124], 1
0x14001da28  mov     [rbp+0B0h+var_12F], 4
0x14001da2c  mov     [rbp+0B0h+var_12E], 4
0x14001da30  mov     [rbp+0B0h+var_12D], 4
0x14001da34  mov     [rbp+0B0h+var_12C], 4
0x14001da38  mov     [rbp+0B0h+var_80], cx
0x14001da3c  mov     [rbp+0B0h+var_12B], 4
0x14001da40  mov     [rbp+0B0h+var_70], cx
0x14001da44  mov     [rbp+0B0h+var_12A], 4
0x14001da48  mov     [rbp+0B0h+var_129], 4
0x14001da4c  mov     [rbp+0B0h+var_50], si
0x14001da50  mov     [rbp+0B0h+var_128], 4
0x14001da54  mov     rcx, [rax+8]
0x14001da58  lea     rax, [rbp+0B0h+var_38]
0x14001da5c  mov     [rbp+0B0h+var_D8], rax
0x14001da60  lea     rax, [rbp+0B0h+var_130]
0x14001da64  mov     [rsp+250h+var_138], rax
0x14001da6c  lea     rax, [rbp+0B0h+var_124]
0x14001da70  mov     [rsp+250h+var_140], rax
0x14001da78  lea     rax, [rbp+0B0h+var_C8]
0x14001da7c  movups  xmm0, xmmword ptr [rcx-10h]
0x14001da80  mov     [rsp+250h+var_148], rax
0x14001da88  lea     rax, [rbp+0B0h+var_12F]
0x14001da8c  mov     [rsp+250h+var_150], rax
0x14001da94  lea     rax, [rbp+0B0h+var_118]
0x14001da98  mov     [rsp+250h+var_158], rax
0x14001daa0  lea     rax, [rbp+0B0h+var_B8]
0x14001daa4  mov     [rsp+250h+var_160], rax
0x14001daac  lea     rax, [rbp+0B0h+var_12E]
0x14001dab0  movdqu  [rbp+0B0h+var_38], xmm0
0x14001dab5  mov     [rbp+0B0h+var_127], dil
0x14001dab9  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x14001dac0  mov     [rbp+0B0h+var_11C], 12Ch
0x14001dac7  mov     [rbp+0B0h+var_D0], 1000000h
0x14001dacf  mov     [rsp+250h+var_168], rax
0x14001dad7  lea     rdx, byte_140023759
0x14001dade  lea     rax, [rbp+0B0h+var_110]
0x14001dae2  mov     [rsp+250h+var_170], rax
0x14001daea  lea     rax, [rbp+0B0h+var_A8]
0x14001daee  mov     [rsp+250h+var_178], rax
0x14001daf6  lea     rax, [rbp+0B0h+var_12D]
0x14001dafa  mov     [rsp+250h+var_180], rax
0x14001db02  lea     rax, [rbp+0B0h+var_108]
0x14001db06  mov     [rsp+250h+var_188], rax
0x14001db0e  lea     rax, [rbp+0B0h+var_98]
0x14001db12  mov     [rsp+250h+var_190], rax
0x14001db1a  lea     rax, [rbp+0B0h+var_12C]
0x14001db1e  mov     [rsp+250h+var_198], rax
0x14001db26  lea     rax, [rbp+0B0h+var_100]
0x14001db2a  mov     [rsp+250h+var_1A0], rax
0x14001db32  lea     rax, [rbp+0B0h+var_88]
0x14001db36  mov     [rsp+250h+var_1A8], rax
0x14001db3e  lea     rax, [rbp+0B0h+var_12B]
0x14001db42  mov     [rsp+250h+var_1B0], rax
0x14001db4a  lea     rax, [rbp+0B0h+var_F8]
0x14001db4e  mov     [rsp+250h+var_1B8], rax
0x14001db56  lea     rax, [rbp+0B0h+var_78]
0x14001db5a  mov     [rsp+250h+var_1C0], rax
0x14001db62  lea     rax, [rbp+0B0h+var_12A]
0x14001db66  mov     [rsp+250h+var_1C8], rax
0x14001db6e  lea     rax, [rbp+0B0h+var_F0]
0x14001db72  mov     [rsp+250h+var_1D0], rax
0x14001db7a  lea     rax, [rbp+0B0h+var_68]
0x14001db7e  mov     [rsp+250h+var_1D8], rax
0x14001db83  lea     rax, [rbp+0B0h+var_129]
0x14001db87  mov     [rsp+250h+var_1E0], rax
0x14001db8c  lea     rax, [rbp+0B0h+var_E8]
0x14001db90  mov     [rsp+250h+var_1E8], rax
0x14001db95  lea     rax, [rbp+0B0h+var_58]
0x14001db99  mov     [rsp+250h+var_1F0], rax
0x14001db9e  lea     rax, [rbp+0B0h+var_128]
0x14001dba2  mov     [rsp+250h+var_1F8], rax
0x14001dba7  lea     rax, [rbp+0B0h+var_E0]
0x14001dbab  mov     [rsp+250h+var_200], rax
0x14001dbb0  lea     rax, [rbp+0B0h+var_48]
0x14001dbb4  mov     [rsp+250h+var_208], rax
0x14001dbb9  lea     rax, [rbp+0B0h+var_D8]
0x14001dbbd  mov     [rsp+250h+var_210], rax
0x14001dbc2  lea     rax, [rbp+0B0h+var_127]
0x14001dbc6  mov     [rsp+250h+var_218], rax
0x14001dbcb  lea     rax, [rbp+0B0h+var_120]
0x14001dbcf  mov     [rsp+250h+var_220], rax
0x14001dbd4  lea     rax, [rbp+0B0h+var_11C]
0x14001dbd8  mov     [rsp+250h+var_228], rax
0x14001dbdd  lea     rax, [rbp+0B0h+var_D0]
0x14001dbe1  mov     [rsp+250h+var_230], rax
0x14001dbe6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14001dbeb  xorps   xmm0, xmm0
0x14001dbee  xor     eax, eax
0x14001dbf0  movups  xmmword ptr [rbx+110h], xmm0
0x14001dbf7  movups  xmmword ptr [rbx+120h], xmm0
0x14001dbfe  mov     [rbx+130h], rax
0x14001dc05  mov     edx, edi
0x14001dc07  mov     rcx, rbx
0x14001dc0a  call    FlushLookUpTableBucket
0x14001dc0f  inc     edi
0x14001dc11  cmp     edi, esi
0x14001dc13  jb      short loc_14001DC05
0x14001dc15  mov     rcx, [rbp+0B0h+var_28]
0x14001dc1c  xor     rcx, rsp; StackCookie
0x14001dc1f  call    __security_check_cookie
0x14001dc24  add     rsp, 238h
0x14001dc2b  pop     rdi
0x14001dc2c  pop     rsi
0x14001dc2d  pop     rbx
0x14001dc2e  pop     rbp
0x14001dc2f  retn
```
