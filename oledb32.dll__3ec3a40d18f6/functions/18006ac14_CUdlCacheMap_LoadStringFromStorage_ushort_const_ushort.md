# CUdlCacheMap::LoadStringFromStorage(ushort const *,ushort * *)

- ea: `0x18006ac14`
- end: `0x18006af88`
- name: `?LoadStringFromStorage@CUdlCacheMap@@QEAAJPEBGPEAPEAG@Z`
- size: `884`
- prototype: `int(CUdlCacheMap *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x18006aa90`
- `0x18006c0d0`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002adb4`
- `0x18002ec26`
- `0x18005f2e0`
- `0x180069348`
- `0x1800693d8`
- `0x18006a844`
- `0x18006ac14`
- `0x18006af90`
- `0x18006b0d4`
- `0x18006b1dc`
- `0x18006b2d0`

## import_xrefs

- `MSDART!mpMalloc` at `0x18006ad5f`
- `MSDART!mpMalloc` at `0x18006ad5f`
- `MSDART!mpFree` at `0x18006ac89`
- `MSDART!mpFree` at `0x18006ac89`
- `MSDART!MpHeapAlloc` at `0x18006adc5`
- `MSDART!MpHeapAlloc` at `0x18006adc5`
- `KERNEL32!AcquireSRWLockShared` at `0x18006acdd`
- `KERNEL32!AcquireSRWLockShared` at `0x18006acdd`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006ad01`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006ad01`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006ad11`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006ad11`

## string_xrefs

- `0x18006ae25`: `<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> `
- `0x18006ae7d`: `<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> `
- `0x18006af39`: `<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> `
- `0x18006ae3f`: `<CUdlCacheMap::LoadStringFromStorage|Trace|HR> `
- `0x18006ae99`: `<CUdlCacheMap::LoadStringFromStorage|Trace|HR> `
- `0x18006aefd`: `<CUdlCacheMap::LoadStringFromStorage|Trace|HR> `
- `0x18006af59`: `<CUdlCacheMap::LoadStringFromStorage|Trace|HR> `
- `0x18006ad95`: `<CopyStringForInternalUse|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUdlCacheMap::LoadStringFromStorage(
        CUdlCacheMap *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  CUdlCacheMap *v5; // rdi
  __int64 v6; // rdx
  unsigned int StringFromDisk; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int16 *v10; // rdi
  __int64 v11; // rdx
  signed __int32 v12; // r14d
  __int64 v13; // rdx
  int v14; // esi
  __int64 v15; // rax
  void *v16; // rax
  void *v17; // r13
  unsigned int v18; // r15d
  size_t v19; // rax
  size_t v20; // rbx
  unsigned int v22; // esi
  int v23; // [rsp+30h] [rbp-10h] BYREF
  char *v24; // [rsp+38h] [rbp-8h]
  size_t Size; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v26; // [rsp+90h] [rbp+50h] BYREF

  Size = (size_t)this;
  v26 = 0;
  if ( !a3 || (*a3 = 0, !a2) )
  {
    StringFromDisk = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      return StringFromDisk;
    OLEDBTraceErr(-2147024809, L"<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> ", 0x786u);
    if ( (bidGblFlags & 2) == 0 )
      return StringFromDisk;
    v11 = 1972233;
    return (unsigned int)bidTraceHR(
                           off_1800C8468[0],
                           v11,
                           L"<CUdlCacheMap::LoadStringFromStorage|Trace|HR> ",
                           StringFromDisk);
  }
  v5 = _UdlCacheMap;
  if ( !*((_BYTE *)_UdlCacheMap + 60) )
  {
    StringFromDisk = LoadStringFromDisk(a2, (const wchar_t **)&v26);
    v10 = v26;
    if ( (StringFromDisk & 0x80000000) == 0 )
      StringFromDisk = CopyStringForExternUse(a3, v26 + 64);
    mpFree(v10, v6, v8, v9);
    if ( (bidGblFlags & 2) == 0 )
      return StringFromDisk;
    v11 = 1984521;
    return (unsigned int)bidTraceHR(
                           off_1800C8468[0],
                           v11,
                           L"<CUdlCacheMap::LoadStringFromStorage|Trace|HR> ",
                           StringFromDisk);
  }
  v12 = _InterlockedIncrement((volatile signed __int32 *)_UdlCacheMap + 16);
  if ( !v12 )
  {
    CUdlCacheMap::CleanUpCache(v5);
    v12 = _InterlockedIncrement((volatile signed __int32 *)v5 + 16);
  }
  v24 = (char *)v5 + 8;
  v23 = 1;
  AcquireSRWLockShared((PSRWLOCK)v5 + 1);
  Size = 0;
  if ( (unsigned int)TCMHashTableLocked<unsigned short const *,CUdlCacheValue *>::Lookup(v5, a2, &Size)
    || (ReleaseSRWLockShared((PSRWLOCK)v5 + 1),
        v23 = 2,
        AcquireSRWLockExclusive((PSRWLOCK)v5 + 1),
        (unsigned int)TCMHashTableLocked<unsigned short const *,CUdlCacheValue *>::Lookup(v5, a2, &Size)) )
  {
    v20 = Size;
  }
  else
  {
    v14 = LoadStringFromDisk(a2, (const wchar_t **)&v26);
    if ( v14 < 0 )
      goto LABEL_44;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    Size = (unsigned int)(2 * v15 + 2);
    v16 = (void *)mpMalloc((unsigned int)Size, v13);
    v17 = v16;
    v18 = -2147024882;
    if ( v16 )
    {
      v14 = 0;
      memcpy_0(v16, a2, Size);
    }
    else
    {
      v14 = -2147024882;
    }
    if ( (bidGblFlags & 2) != 0 )
      v14 = bidTraceHR(off_1800C8468[0], 2241545, L"<CopyStringForInternalUse|Trace|HR> ", (unsigned int)v14);
    if ( v14 < 0 )
      goto LABEL_44;
    v19 = MpHeapAlloc(g_hHeapHandle, 19922944, 32);
    v20 = v19;
    Size = v19;
    if ( !v19 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> ", 0x7BAu);
        if ( (bidGblFlags & 2) != 0 )
          v18 = bidTraceHR(off_1800C8468[0], 2025481, L"<CUdlCacheMap::LoadStringFromStorage|Trace|HR> ", 2147942414LL);
      }
      goto LABEL_27;
    }
    *(_DWORD *)v19 = 0;
    *(_QWORD *)(v19 + 8) = v26;
    *(_QWORD *)(v19 + 16) = v17;
    *(_DWORD *)(v19 + 24) = v12;
    Size = v19;
    _InterlockedIncrement((volatile signed __int32 *)v19);
    v14 = TCMHashTableLocked<unsigned short const *,CUdlCacheValue *>::SetAtEx(v5, v17, &Size);
    if ( v14 < 0 )
    {
LABEL_44:
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v14, L"<CUdlCacheMap::LoadStringFromStorage|OLEDB|ERR> ", 0x7C5u);
        if ( (bidGblFlags & 2) != 0 )
          v14 = bidTraceHR(
                  off_1800C8468[0],
                  2036745,
                  L"<CUdlCacheMap::LoadStringFromStorage|Trace|HR> ",
                  (unsigned int)v14);
      }
      v18 = v14;
LABEL_27:
      CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v23);
      return v18;
    }
  }
  *(_DWORD *)(v20 + 24) = v12;
  v22 = CopyStringForExternUse(a3, (const unsigned __int16 *)(*(_QWORD *)(v20 + 8) + 128LL));
  CUdlCacheValue::Release((CUdlCacheValue *)v20);
  if ( *((_DWORD *)v5 + 7) > *((_DWORD *)v5 + 14) )
  {
    CAutoRWLock::ReadOrWriteUnlock((CAutoRWLock *)&v23);
    CUdlCacheMap::PurgeExpiredEntries(v5);
  }
  if ( (bidGblFlags & 2) != 0 )
    v22 = bidTraceHR(off_1800C8468[0], 2055177, L"<CUdlCacheMap::LoadStringFromStorage|Trace|HR> ", v22);
  CAutoRWLock::~CAutoRWLock((CAutoRWLock *)&v23);
  return v22;
}

```

## disassembly

```asm
0x18006ac14  mov     [rsp-38h+arg_8], rbx
0x18006ac19  mov     [rsp-38h+Size], rcx
0x18006ac1e  push    rbp
0x18006ac1f  push    rsi
0x18006ac20  push    rdi
0x18006ac21  push    r12
0x18006ac23  push    r13
0x18006ac25  push    r14
0x18006ac27  push    r15
0x18006ac29  mov     rbp, rsp
0x18006ac2c  sub     rsp, 40h
0x18006ac30  mov     r12, r8
0x18006ac33  mov     rbx, rdx
0x18006ac36  xor     r15d, r15d
0x18006ac39  mov     [rbp+arg_10], r15
0x18006ac3d  test    r8, r8
0x18006ac40  jz      loc_18006AF24
0x18006ac46  mov     [r8], r15
0x18006ac49  test    rdx, rdx
0x18006ac4c  jz      loc_18006AF24
0x18006ac52  mov     rdi, cs:?_UdlCacheMap@@3PEAVCUdlCacheMap@@EA; CUdlCacheMap * _UdlCacheMap
0x18006ac59  cmp     [rdi+3Ch], r15b
0x18006ac5d  jnz     short loc_18006ACA6
0x18006ac5f  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18006ac63  mov     rcx, rbx; lpFileName
0x18006ac66  call    ?LoadStringFromDisk@@YAJPEBGPEAPEAG@Z; LoadStringFromDisk(ushort const *,ushort * *)
0x18006ac6b  mov     ebx, eax
0x18006ac6d  mov     rdi, [rbp+arg_10]
0x18006ac71  test    eax, eax
0x18006ac73  js      short loc_18006AC86
0x18006ac75  lea     rdx, [rdi+80h]; unsigned __int16 *
0x18006ac7c  mov     rcx, r12; unsigned __int16 **
0x18006ac7f  call    ?CopyStringForExternUse@@YAJPEAPEAGPEBG@Z; CopyStringForExternUse(ushort * *,ushort const *)
0x18006ac84  mov     ebx, eax
0x18006ac86  mov     rcx, rdi
0x18006ac89  call    cs:__imp_mpFree
0x18006ac8f  test    byte ptr cs:_bidGblFlags, 2
0x18006ac96  jz      loc_18006AF6E
0x18006ac9c  mov     edx, 1E4809h
0x18006aca1  jmp     loc_18006AF56
0x18006aca6  mov     r13d, 1
0x18006acac  mov     r14d, r13d
0x18006acaf  lock xadd [rdi+40h], r14d
0x18006acb5  add     r14d, r13d
0x18006acb8  jnz     short loc_18006ACCE
0x18006acba  mov     rcx, rdi; this
0x18006acbd  call    ?CleanUpCache@CUdlCacheMap@@QEAAXXZ; CUdlCacheMap::CleanUpCache(void)
0x18006acc2  mov     r14d, r13d
0x18006acc5  lock xadd [rdi+40h], r14d
0x18006accb  add     r14d, r13d
0x18006acce  lea     rsi, [rdi+8]
0x18006acd2  mov     [rbp+var_8], rsi
0x18006acd6  mov     [rbp+var_10], r13d
0x18006acda  mov     rcx, rsi; SRWLock
0x18006acdd  call    cs:__imp_AcquireSRWLockShared
0x18006ace3  mov     [rbp+Size], r15
0x18006ace7  lea     r8, [rbp+Size]
0x18006aceb  mov     rdx, rbx
0x18006acee  mov     rcx, rdi
0x18006acf1  call    ?Lookup@?$TCMHashTableLocked@PEBGPEAVCUdlCacheValue@@@@QEAAHPEBGAEAPEAVCUdlCacheValue@@H@Z; TCMHashTableLocked<ushort const *,CUdlCacheValue *>::Lookup(ushort const *,CUdlCacheValue * &,int)
0x18006acf6  test    eax, eax
0x18006acf8  jnz     loc_18006AEB6
0x18006acfe  mov     rcx, rsi; SRWLock
0x18006ad01  call    cs:__imp_ReleaseSRWLockShared
0x18006ad07  mov     [rbp+var_10], 2
0x18006ad0e  mov     rcx, rsi; SRWLock
0x18006ad11  call    cs:__imp_AcquireSRWLockExclusive
0x18006ad17  lea     r8, [rbp+Size]
0x18006ad1b  mov     rdx, rbx
0x18006ad1e  mov     rcx, rdi
0x18006ad21  call    ?Lookup@?$TCMHashTableLocked@PEBGPEAVCUdlCacheValue@@@@QEAAHPEBGAEAPEAVCUdlCacheValue@@H@Z; TCMHashTableLocked<ushort const *,CUdlCacheValue *>::Lookup(ushort const *,CUdlCacheValue * &,int)
0x18006ad26  test    eax, eax
0x18006ad28  jnz     loc_18006AEB6
0x18006ad2e  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18006ad32  mov     rcx, rbx; lpFileName
0x18006ad35  call    ?LoadStringFromDisk@@YAJPEBGPEAPEAG@Z; LoadStringFromDisk(ushort const *,ushort * *)
0x18006ad3a  mov     esi, eax
0x18006ad3c  test    eax, eax
0x18006ad3e  js      loc_18006AE16
0x18006ad44  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006ad48  inc     rax
0x18006ad4b  cmp     [rbx+rax*2], r15w
0x18006ad50  jnz     short loc_18006AD48
0x18006ad52  lea     eax, ds:2[rax*2]
0x18006ad59  mov     [rbp+Size], rax
0x18006ad5d  mov     ecx, eax
0x18006ad5f  call    cs:__imp_mpMalloc
0x18006ad65  mov     r13, rax
0x18006ad68  mov     r15d, 8007000Eh
0x18006ad6e  test    rax, rax
0x18006ad71  jz      short loc_18006AD86
0x18006ad73  xor     esi, esi
0x18006ad75  mov     r8, [rbp+Size]; Size
0x18006ad79  mov     rdx, rbx; Src
0x18006ad7c  mov     rcx, rax; void *
0x18006ad7f  call    memcpy_0
0x18006ad84  jmp     short loc_18006AD89
0x18006ad86  mov     esi, r15d
0x18006ad89  test    byte ptr cs:_bidGblFlags, 2
0x18006ad90  jz      short loc_18006ADAF
0x18006ad92  mov     r9d, esi
0x18006ad95  lea     r8, aCopystringfori; "<CopyStringForInternalUse|Trace|HR> "
0x18006ad9c  mov     edx, 223409h
0x18006ada1  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006ada8  call    _bidTraceHR
0x18006adad  mov     esi, eax
0x18006adaf  test    esi, esi
0x18006adb1  js      short loc_18006AE16
0x18006adb3  mov     edx, 1300000h
0x18006adb8  mov     r8d, 20h ; ' '
0x18006adbe  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18006adc5  call    cs:__imp_MpHeapAlloc
0x18006adcb  mov     rbx, rax
0x18006adce  mov     [rbp+Size], rax
0x18006add2  test    rax, rax
0x18006add5  jz      loc_18006AE6D
0x18006addb  mov     dword ptr [rax], 0
0x18006ade1  mov     rax, [rbp+arg_10]
0x18006ade5  mov     [rbx+8], rax
0x18006ade9  mov     [rbx+10h], r13
0x18006aded  mov     [rbx+18h], r14d
0x18006adf1  mov     [rbp+Size], rbx
0x18006adf5  test    rbx, rbx
0x18006adf8  jz      short loc_18006AE6D
0x18006adfa  lock inc dword ptr [rbx]
0x18006adfd  lea     r8, [rbp+Size]
0x18006ae01  mov     rdx, r13
0x18006ae04  mov     rcx, rdi
0x18006ae07  call    ?SetAtEx@?$TCMHashTableLocked@PEBGPEAVCUdlCacheValue@@@@QEAAJPEBGAEAPEAVCUdlCacheValue@@HPEAPEAUCAssoc@1@@Z; TCMHashTableLocked<ushort const *,CUdlCacheValue *>::SetAtEx(ushort const *,CUdlCacheValue * &,int,TCMHashTableLocked<ushort const *,CUdlCacheValue *>::CAssoc * *)
0x18006ae0c  mov     esi, eax
0x18006ae0e  test    eax, eax
0x18006ae10  jns     loc_18006AEBA
0x18006ae16  test    byte ptr cs:_bidGblFlags, 2
0x18006ae1d  jz      short loc_18006AE59
0x18006ae1f  mov     r8d, 7C5h; unsigned int
0x18006ae25  lea     rdx, aCudlcachemapLo; "<CUdlCacheMap::LoadStringFromStorage|OL"...
0x18006ae2c  mov     ecx, esi; int
0x18006ae2e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006ae33  test    byte ptr cs:_bidGblFlags, 2
0x18006ae3a  jz      short loc_18006AE59
0x18006ae3c  mov     r9d, esi
0x18006ae3f  lea     r8, aCudlcachemapLo_0; "<CUdlCacheMap::LoadStringFromStorage|Tr"...
0x18006ae46  mov     edx, 1F1409h
0x18006ae4b  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006ae52  call    _bidTraceHR
0x18006ae57  mov     esi, eax
0x18006ae59  mov     r15d, esi
0x18006ae5c  lea     rcx, [rbp+var_10]; this
0x18006ae60  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18006ae65  mov     eax, r15d
0x18006ae68  jmp     loc_18006AF70
0x18006ae6d  mov     eax, cs:_bidGblFlags
0x18006ae73  test    al, 2
0x18006ae75  jz      short loc_18006AE5C
0x18006ae77  mov     r8d, 7BAh; unsigned int
0x18006ae7d  lea     rdx, aCudlcachemapLo; "<CUdlCacheMap::LoadStringFromStorage|OL"...
0x18006ae84  mov     ecx, r15d; int
0x18006ae87  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006ae8c  mov     eax, cs:_bidGblFlags
0x18006ae92  test    al, 2
0x18006ae94  jz      short loc_18006AE5C
0x18006ae96  mov     r9d, r15d
0x18006ae99  lea     r8, aCudlcachemapLo_0; "<CUdlCacheMap::LoadStringFromStorage|Tr"...
0x18006aea0  mov     edx, 1EE809h
0x18006aea5  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006aeac  call    _bidTraceHR
0x18006aeb1  mov     r15d, eax
0x18006aeb4  jmp     short loc_18006AE5C
0x18006aeb6  mov     rbx, [rbp+Size]
0x18006aeba  mov     [rbx+18h], r14d
0x18006aebe  mov     rdx, [rbx+8]
0x18006aec2  sub     rdx, 0FFFFFFFFFFFFFF80h; unsigned __int16 *
0x18006aec6  mov     rcx, r12; unsigned __int16 **
0x18006aec9  call    ?CopyStringForExternUse@@YAJPEAPEAGPEBG@Z; CopyStringForExternUse(ushort * *,ushort const *)
0x18006aece  mov     esi, eax
0x18006aed0  mov     rcx, rbx; this
0x18006aed3  call    ?Release@CUdlCacheValue@@QEAAKXZ; CUdlCacheValue::Release(void)
0x18006aed8  mov     eax, [rdi+38h]
0x18006aedb  cmp     [rdi+1Ch], eax
0x18006aede  jbe     short loc_18006AEF1
0x18006aee0  lea     rcx, [rbp+var_10]; this
0x18006aee4  call    ?ReadOrWriteUnlock@CAutoRWLock@@QEAAXXZ; CAutoRWLock::ReadOrWriteUnlock(void)
0x18006aee9  mov     rcx, rdi; this
0x18006aeec  call    ?PurgeExpiredEntries@CUdlCacheMap@@QEAAXXZ; CUdlCacheMap::PurgeExpiredEntries(void)
0x18006aef1  test    byte ptr cs:_bidGblFlags, 2
0x18006aef8  jz      short loc_18006AF17
0x18006aefa  mov     r9d, esi
0x18006aefd  lea     r8, aCudlcachemapLo_0; "<CUdlCacheMap::LoadStringFromStorage|Tr"...
0x18006af04  mov     edx, 1F5C09h
0x18006af09  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006af10  call    _bidTraceHR
0x18006af15  mov     esi, eax
0x18006af17  lea     rcx, [rbp+var_10]; this
0x18006af1b  call    ??1CAutoRWLock@@QEAA@XZ; CAutoRWLock::~CAutoRWLock(void)
0x18006af20  mov     eax, esi
0x18006af22  jmp     short loc_18006AF70
0x18006af24  mov     eax, cs:_bidGblFlags
0x18006af2a  mov     ebx, 80070057h
0x18006af2f  test    al, 2
0x18006af31  jz      short loc_18006AF6E
0x18006af33  mov     r8d, 786h; unsigned int
0x18006af39  lea     rdx, aCudlcachemapLo; "<CUdlCacheMap::LoadStringFromStorage|OL"...
0x18006af40  mov     ecx, ebx; int
0x18006af42  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006af47  mov     eax, cs:_bidGblFlags
0x18006af4d  test    al, 2
0x18006af4f  jz      short loc_18006AF6E
0x18006af51  mov     edx, 1E1809h
0x18006af56  mov     r9d, ebx
0x18006af59  lea     r8, aCudlcachemapLo_0; "<CUdlCacheMap::LoadStringFromStorage|Tr"...
0x18006af60  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006af67  call    _bidTraceHR
0x18006af6c  mov     ebx, eax
0x18006af6e  mov     eax, ebx
0x18006af70  mov     rbx, [rsp+40h+arg_8]
0x18006af78  add     rsp, 40h
0x18006af7c  pop     r15
0x18006af7e  pop     r14
0x18006af80  pop     r13
0x18006af82  pop     r12
0x18006af84  pop     rdi
0x18006af85  pop     rsi
0x18006af86  pop     rbp
0x18006af87  retn
```
