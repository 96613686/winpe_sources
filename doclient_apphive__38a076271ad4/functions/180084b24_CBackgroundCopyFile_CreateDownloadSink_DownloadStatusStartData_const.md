# CBackgroundCopyFile::_CreateDownloadSink(DownloadStatusStartData const &)

- ea: `0x180084b24`
- end: `0x180084fe6`
- name: `?_CreateDownloadSink@CBackgroundCopyFile@@AEAAJAEBUDownloadStatusStartData@@@Z`
- size: `1218`
- prototype: `__int64 __fastcall(CBackgroundCopyFile *__hidden this, const struct DownloadStatusStartData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180081ab0`

## callees

- `0x18000933c`
- `0x18000f014`
- `0x1800199b4`
- `0x180019c5c`
- `0x180071330`
- `0x180084b24`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800f2428`
- `0x1800f33f0`
- `0x1800f3fcc`
- `0x1800f8320`
- `0x1801085b4`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084c35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084f99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084c35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084f99`

## string_xrefs

- `0x180084c14`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084ed5`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084b79`: `CBackgroundCopyFile::_CreateDownloadSink`
- `0x180084cfb`: `CBackgroundCopyFile::_CreateDownloadSink`
- `0x180084e1e`: `CBackgroundCopyFile::_CreateDownloadSink`
- `0x180084b60`: `!IsComplete()`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBackgroundCopyFile::_CreateDownloadSink(
        CBackgroundCopyFile *this,
        const struct DownloadStatusStartData *a2)
{
  _QWORD *v4; // r13
  const char *v5; // r9
  bool v6; // zf
  __int64 result; // rax
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  char *v13; // r12
  __int64 v14; // r14
  void *v15; // rax
  __int64 v16; // r14
  void *v17; // rax
  int v18; // eax
  unsigned int v19; // r14d
  volatile signed __int32 *v20; // r14
  int v21; // [rsp+20h] [rbp-B8h]
  int v22; // [rsp+20h] [rbp-B8h]
  int v23[2]; // [rsp+40h] [rbp-98h]
  int v24[2]; // [rsp+40h] [rbp-98h]
  _QWORD v25[4]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    if ( (*(unsigned __int8 (__fastcall **)(CBackgroundCopyFile *))(*(_QWORD *)this + 8LL))(this) )
    {
      LogMessage(
        2u,
        "CBackgroundCopyFile::_CreateDownloadSink",
        0x5F4u,
        "TelemetryAssert (%s): %s",
        "!IsComplete()",
        "Failed");
      DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    }
    if ( (unsigned int)mtx_do_lock((char *)this + 264) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 85) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 85) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v4 = (_QWORD *)((char *)this + 448);
    if ( *((_QWORD *)this + 45) )
    {
      if ( *v4 == *((_QWORD *)this + 57) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5FC,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
          (const char *)0x80D0200BLL,
          v21);
        v6 = (*((_DWORD *)this + 85))-- == 1;
        if ( v6 )
        {
          *((_DWORD *)this + 84) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
        }
        return 2161123339LL;
      }
      if ( *((_BYTE *)this + 493) )
      {
        v8 = *((_QWORD *)a2 + 4);
        if ( v8 )
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
        v9 = (volatile signed __int32 *)*((_QWORD *)a2 + 3);
        v10 = (volatile signed __int32 *)*((_QWORD *)a2 + 4);
        (*(void (__fastcall **)(volatile signed __int32 *, char *))(*(_QWORD *)v9 + 112LL))(v9, (char *)this + 448);
        v11 = _RTDynamicCast(
                (_DWORD)v9,
                0,
                (unsigned int)&IDownloadSink `RTTI Type Descriptor',
                (unsigned int)&CHttpRangesSink `RTTI Type Descriptor',
                0);
        v12 = *((_QWORD *)this + 46);
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
        v25[0] = *((_QWORD *)this + 45);
        v25[1] = *((_QWORD *)this + 46);
        std::atomic<std::shared_ptr<HttpResponseInfo>>::operator=(v11 + 64, v25);
      }
      else
      {
        if ( !*((_QWORD *)a2 + 1) )
        {
          LogMessage(
            2u,
            "CBackgroundCopyFile::_CreateDownloadSink",
            0x608u,
            "TelemetryAssert (%s): %s",
            "startData.totalFileSize != 0",
            "Failed");
          DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
        }
        *(_QWORD *)v23 = *((_QWORD *)a2 + 2);
        v10 = (volatile signed __int32 *)operator new(0x228u);
        *((_DWORD *)v10 + 2) = 1;
        *((_DWORD *)v10 + 3) = 1;
        *(_QWORD *)v10 = &std::_Ref_count_obj2<CDownloadSinkStreamRanges>::`vftable';
        v9 = v10 + 4;
        CDownloadSinkStreamRanges::CDownloadSinkStreamRanges(
          (_DWORD)v10 + 16,
          (_DWORD)this,
          v23[0],
          (_DWORD)this + 400,
          (__int64)this + 360,
          (__int64)this + 448,
          *((_QWORD *)a2 + 1));
      }
    }
    else
    {
      v13 = (char *)this + (*((_QWORD *)this + 12) != 0 ? 80LL : 48LL);
      if ( *v4 == *((_QWORD *)this + 57) )
      {
        v14 = *((_QWORD *)a2 + 2);
        v10 = (volatile signed __int32 *)operator new(0x1F0u);
        *((_DWORD *)v10 + 2) = 1;
        *((_DWORD *)v10 + 3) = 1;
        *(_QWORD *)v10 = &std::_Ref_count_obj2<CDownloadSinkFile>::`vftable';
        v9 = v10 + 4;
        v15 = (void *)std::string::string(v25, v13);
        CDownloadSinkFile::CDownloadSinkFile((_DWORD)v10 + 16, (int)this, v14, (_DWORD)this + 400, v15);
      }
      else
      {
        if ( !*((_QWORD *)a2 + 1) )
        {
          LogMessage(
            2u,
            "CBackgroundCopyFile::_CreateDownloadSink",
            0x617u,
            "TelemetryAssert (%s): %s",
            "startData.totalFileSize != 0",
            "Failed");
          DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
        }
        *(_QWORD *)v24 = *((_QWORD *)a2 + 2);
        v10 = (volatile signed __int32 *)operator new(0x250u);
        *((_DWORD *)v10 + 2) = 1;
        *((_DWORD *)v10 + 3) = 1;
        *(_QWORD *)v10 = &std::_Ref_count_obj2<CDownloadSinkFileRanges>::`vftable';
        v9 = v10 + 4;
        v16 = *((_QWORD *)a2 + 1);
        v17 = (void *)std::string::string(v26, v13);
        CDownloadSinkFileRanges::CDownloadSinkFileRanges(
          (_DWORD)v10 + 16,
          (int)this,
          v24[0],
          (_DWORD)this + 400,
          v17,
          (__int64)this + 448,
          v16);
      }
    }
    v18 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    v19 = v18;
    if ( v18 >= 0 )
    {
      *((_QWORD *)this + 43) = v9;
      v20 = (volatile signed __int32 *)*((_QWORD *)this + 44);
      *((_QWORD *)this + 44) = v10;
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
      v6 = (*((_DWORD *)this + 85))-- == 1;
      if ( v6 )
      {
        *((_DWORD *)this + 84) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
      }
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61D,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
        (const char *)(unsigned int)v18,
        v22);
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v6 = (*((_DWORD *)this + 85))-- == 1;
      if ( v6 )
      {
        *((_DWORD *)this + 84) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
      }
      result = v19;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x622,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180084b24  mov     [rsp+arg_10], rbx
0x180084b29  mov     [rsp+arg_18], rsi
0x180084b2e  push    rdi
0x180084b2f  push    r12
0x180084b31  push    r13
0x180084b33  push    r14
0x180084b35  push    r15
0x180084b37  sub     rsp, 0B0h
0x180084b3e  mov     r14, rdx
0x180084b41  mov     r15, rcx
0x180084b44  mov     rax, [rcx]
0x180084b47  mov     rax, [rax+8]
0x180084b4b  call    _guard_dispatch_icall
0x180084b50  lea     rdi, aFailed; "Failed"
0x180084b57  test    al, al
0x180084b59  jz      short loc_180084B98
0x180084b5b  mov     [rsp+0D8h+var_B0], rdi
0x180084b60  lea     rax, aIscomplete; "!IsComplete()"
0x180084b67  mov     [rsp+0D8h+var_B8], rax
0x180084b6c  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180084b73  mov     r8d, 5F4h; unsigned int
0x180084b79  lea     rdx, aCbackgroundcop_29; "CBackgroundCopyFile::_CreateDownloadSin"...
0x180084b80  mov     ecx, 2; unsigned __int8
0x180084b85  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084b8a  or      ebx, 0FFFFFFFFh
0x180084b8d  mov     edx, ebx; unsigned int
0x180084b8f  mov     ecx, ebx; unsigned int
0x180084b91  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180084b96  jmp     short loc_180084B9B
0x180084b98  or      ebx, 0FFFFFFFFh
0x180084b9b  xorps   xmm0, xmm0
0x180084b9e  movups  [rsp+0D8h+var_78], xmm0
0x180084ba3  lea     rsi, [r15+108h]
0x180084baa  mov     qword ptr [rsp+0D8h+var_78], rsi
0x180084baf  mov     byte ptr [rsp+0D8h+var_78+8], 0
0x180084bb4  mov     rcx, rsi
0x180084bb7  call    mtx_do_lock
0x180084bbc  xor     ecx, ecx
0x180084bbe  test    eax, eax
0x180084bc0  jnz     loc_180084FCB
0x180084bc6  mov     eax, [rsi+4Ch]
0x180084bc9  cmp     eax, 7FFFFFFFh
0x180084bce  jz      loc_180084FD5
0x180084bd4  mov     byte ptr [rsp+0D8h+var_78+8], 1
0x180084bd9  xorps   xmm1, xmm1
0x180084bdc  movdqu  [rsp+0D8h+var_90], xmm1
0x180084be2  lea     r12, [r15+168h]
0x180084be9  lea     r13, [r15+1C0h]
0x180084bf0  cmp     [r12], rcx
0x180084bf4  jz      loc_180084D7C
0x180084bfa  mov     rax, [r13+8]
0x180084bfe  cmp     [r13+0], rax
0x180084c02  jnz     short loc_180084C42
0x180084c04  mov     rcx, [rsp+0D8h]; this
0x180084c0c  mov     edi, 80D0200Bh
0x180084c11  mov     r9d, edi; char *
0x180084c14  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180084c1b  mov     edx, 5FCh; void *
0x180084c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084c25  nop
0x180084c26  or      ebx, 0FFFFFFFFh
0x180084c29  add     [rsi+4Ch], ebx
0x180084c2c  jnz     short loc_180084C3B
0x180084c2e  mov     [rsi+48h], ebx
0x180084c31  lea     rcx, [rsi+10h]; SRWLock
0x180084c35  call    cs:__imp_ReleaseSRWLockExclusive
0x180084c3b  mov     eax, edi
0x180084c3d  jmp     loc_180084FAE
0x180084c42  cmp     [r15+1EDh], cl
0x180084c49  jz      loc_180084CD7
0x180084c4f  mov     rax, [r14+20h]
0x180084c53  test    rax, rax
0x180084c56  jz      short loc_180084C5C
0x180084c58  lock inc dword ptr [rax+8]
0x180084c5c  mov     rbx, [r14+18h]
0x180084c60  mov     qword ptr [rsp+0D8h+var_90], rbx
0x180084c65  mov     rdi, [r14+20h]
0x180084c69  mov     qword ptr [rsp+0D8h+var_90+8], rdi
0x180084c6e  mov     rax, [rbx]
0x180084c71  mov     rdx, r13
0x180084c74  mov     rcx, rbx
0x180084c77  mov     rax, [rax+70h]
0x180084c7b  call    _guard_dispatch_icall
0x180084c80  mov     dword ptr [rsp+0D8h+var_B8], 0
0x180084c88  lea     r9, ??_R0?AVCHttpRangesSink@@@8; CHttpRangesSink `RTTI Type Descriptor'
0x180084c8f  lea     r8, ??_R0?AVIDownloadSink@@@8; IDownloadSink `RTTI Type Descriptor'
0x180084c96  xor     edx, edx
0x180084c98  mov     rcx, rbx
0x180084c9b  call    __RTDynamicCast
0x180084ca0  mov     rdx, rax
0x180084ca3  mov     rcx, [r12+8]
0x180084ca8  test    rcx, rcx
0x180084cab  jz      short loc_180084CB1
0x180084cad  lock inc dword ptr [rcx+8]
0x180084cb1  mov     rax, [r12]
0x180084cb5  mov     [rsp+0D8h+var_68], rax
0x180084cba  mov     rax, [r12+8]
0x180084cbf  mov     [rsp+0D8h+var_60], rax
0x180084cc4  lea     rcx, [rdx+40h]
0x180084cc8  lea     rdx, [rsp+0D8h+var_68]
0x180084ccd  call    ??4?$atomic@V?$shared_ptr@UHttpResponseInfo@@@std@@@std@@QEAAXV?$shared_ptr@UHttpResponseInfo@@@1@@Z; std::atomic<std::shared_ptr<HttpResponseInfo>>::operator=(std::shared_ptr<HttpResponseInfo>)
0x180084cd2  jmp     loc_180084EB4
0x180084cd7  cmp     [r14+8], rcx
0x180084cdb  jnz     short loc_180084D15
0x180084cdd  mov     [rsp+0D8h+var_B0], rdi
0x180084ce2  lea     rax, aStartdataTotal; "startData.totalFileSize != 0"
0x180084ce9  mov     [rsp+0D8h+var_B8], rax
0x180084cee  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180084cf5  mov     r8d, 608h; unsigned int
0x180084cfb  lea     rdx, aCbackgroundcop_29; "CBackgroundCopyFile::_CreateDownloadSin"...
0x180084d02  mov     ecx, 2; unsigned __int8
0x180084d07  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084d0c  mov     edx, ebx; unsigned int
0x180084d0e  mov     ecx, ebx; unsigned int
0x180084d10  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180084d15  mov     rax, [r14+10h]
0x180084d19  mov     qword ptr [rsp+0D8h+var_98], rax
0x180084d1e  mov     ecx, 228h; Size
0x180084d23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180084d28  mov     rdi, rax
0x180084d2b  mov     [rsp+0D8h+var_80], rax
0x180084d30  mov     dword ptr [rax+8], 1
0x180084d37  mov     dword ptr [rax+0Ch], 1
0x180084d3e  lea     rax, ??_7?$_Ref_count_obj2@VCDownloadSinkStreamRanges@@@std@@6B@; const std::_Ref_count_obj2<CDownloadSinkStreamRanges>::`vftable'
0x180084d45  mov     [rdi], rax
0x180084d48  lea     rbx, [rdi+10h]
0x180084d4c  mov     rax, [r14+8]
0x180084d50  mov     [rsp+0D8h+var_A8], rax
0x180084d55  mov     [rsp+0D8h+var_B0], r13
0x180084d5a  mov     [rsp+0D8h+var_B8], r12
0x180084d5f  lea     r9, [r15+190h]
0x180084d66  mov     r8, qword ptr [rsp+0D8h+var_98]
0x180084d6b  mov     rdx, r15
0x180084d6e  mov     rcx, rbx
0x180084d71  call    ??0CDownloadSinkStreamRanges@@QEAA@AEAVIDownloadRequest@@AEAVCMetaInfo@@AEBV?$shared_ptr@VCCipher@@@std@@AEBV?$shared_ptr@VIDownloadStream@@@4@AEBV?$vector@UDownloadRange@@V?$allocator@UDownloadRange@@@std@@@4@_K@Z; CDownloadSinkStreamRanges::CDownloadSinkStreamRanges(IDownloadRequest &,CMetaInfo &,std::shared_ptr<CCipher> const &,std::shared_ptr<IDownloadStream> const &,std::vector<DownloadRange> const &,unsigned __int64)
0x180084d76  nop
0x180084d77  jmp     loc_180084EAA
0x180084d7c  mov     rax, [r15+60h]
0x180084d80  neg     rax
0x180084d83  sbb     r12, r12
0x180084d86  and     r12d, 20h
0x180084d8a  add     r12, 30h ; '0'
0x180084d8e  add     r12, r15
0x180084d91  mov     rax, [r13+8]
0x180084d95  cmp     [r13+0], rax
0x180084d99  jnz     short loc_180084DFA
0x180084d9b  mov     r14, [r14+10h]
0x180084d9f  mov     ecx, 1F0h; Size
0x180084da4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180084da9  mov     rdi, rax
0x180084dac  mov     [rsp+0D8h+var_80], rax
0x180084db1  mov     dword ptr [rax+8], 1
0x180084db8  mov     dword ptr [rax+0Ch], 1
0x180084dbf  lea     rax, ??_7?$_Ref_count_obj2@VCDownloadSinkFile@@@std@@6B@; const std::_Ref_count_obj2<CDownloadSinkFile>::`vftable'
0x180084dc6  mov     [rdi], rax
0x180084dc9  lea     rbx, [rdi+10h]
0x180084dcd  mov     rdx, r12
0x180084dd0  lea     rcx, [rsp+0D8h+var_68]
0x180084dd5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180084dda  mov     [rsp+0D8h+var_B8], rax; void *
0x180084ddf  lea     r9, [r15+190h]; int
0x180084de6  mov     r8, r14; int
0x180084de9  mov     rdx, r15; int
0x180084dec  mov     rcx, rbx; int
0x180084def  call    ??0CDownloadSinkFile@@QEAA@AEAVIDownloadRequest@@AEAVCMetaInfo@@AEBV?$shared_ptr@VCCipher@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; CDownloadSinkFile::CDownloadSinkFile(IDownloadRequest &,CMetaInfo &,std::shared_ptr<CCipher> const &,std::string)
0x180084df4  nop
0x180084df5  jmp     loc_180084EAA
0x180084dfa  cmp     [r14+8], rcx
0x180084dfe  jnz     short loc_180084E38
0x180084e00  mov     [rsp+0D8h+var_B0], rdi
0x180084e05  lea     rax, aStartdataTotal; "startData.totalFileSize != 0"
0x180084e0c  mov     [rsp+0D8h+var_B8], rax
0x180084e11  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180084e18  mov     r8d, 617h; unsigned int
0x180084e1e  lea     rdx, aCbackgroundcop_29; "CBackgroundCopyFile::_CreateDownloadSin"...
0x180084e25  mov     ecx, 2; unsigned __int8
0x180084e2a  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084e2f  mov     edx, ebx; unsigned int
0x180084e31  mov     ecx, ebx; unsigned int
0x180084e33  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180084e38  mov     rax, [r14+10h]
0x180084e3c  mov     qword ptr [rsp+0D8h+var_98], rax
0x180084e41  mov     ecx, 250h; Size
0x180084e46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180084e4b  mov     rdi, rax
0x180084e4e  mov     [rsp+0D8h+var_80], rax
0x180084e53  mov     dword ptr [rax+8], 1
0x180084e5a  mov     dword ptr [rax+0Ch], 1
0x180084e61  lea     rax, ??_7?$_Ref_count_obj2@VCDownloadSinkFileRanges@@@std@@6B@; const std::_Ref_count_obj2<CDownloadSinkFileRanges>::`vftable'
0x180084e68  mov     [rdi], rax
0x180084e6b  lea     rbx, [rdi+10h]
0x180084e6f  mov     r14, [r14+8]
0x180084e73  mov     rdx, r12
0x180084e76  lea     rcx, [rsp+0D8h+var_48]
0x180084e7e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180084e83  mov     [rsp+0D8h+var_A8], r14; __int64
0x180084e88  mov     [rsp+0D8h+var_B0], r13; __int64
0x180084e8d  mov     [rsp+0D8h+var_B8], rax; int
0x180084e92  lea     r9, [r15+190h]; int
0x180084e99  mov     r8, qword ptr [rsp+0D8h+var_98]; int
0x180084e9e  mov     rdx, r15; int
0x180084ea1  mov     rcx, rbx; int
0x180084ea4  call    ??0CDownloadSinkFileRanges@@QEAA@AEAVIDownloadRequest@@AEAVCMetaInfo@@AEBV?$shared_ptr@VCCipher@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@AEBV?$vector@UDownloadRange@@V?$allocator@UDownloadRange@@@std@@@4@_K@Z; CDownloadSinkFileRanges::CDownloadSinkFileRanges(IDownloadRequest &,CMetaInfo &,std::shared_ptr<CCipher> const &,std::string,std::vector<DownloadRange> const &,unsigned __int64)
0x180084ea9  nop
0x180084eaa  mov     qword ptr [rsp+0D8h+var_90], rbx
0x180084eaf  mov     qword ptr [rsp+0D8h+var_90+8], rdi
0x180084eb4  mov     rax, [rbx]
0x180084eb7  mov     rcx, rbx
0x180084eba  mov     rax, [rax+10h]
0x180084ebe  call    _guard_dispatch_icall
0x180084ec3  mov     r14d, eax
0x180084ec6  test    eax, eax
0x180084ec8  jns     short loc_180084F3A
0x180084eca  mov     rcx, [rsp+0D8h]; this
0x180084ed2  mov     r9d, eax; char *
0x180084ed5  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180084edc  mov     edx, 61Dh; void *
0x180084ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084ee6  nop
0x180084ee7  or      ebx, 0FFFFFFFFh
0x180084eea  test    rdi, rdi
0x180084eed  jz      short loc_180084F23
0x180084eef  mov     eax, ebx
0x180084ef1  lock xadd [rdi+8], eax
0x180084ef6  add     eax, ebx
0x180084ef8  jnz     short loc_180084F23
0x180084efa  mov     rax, [rdi]
0x180084efd  mov     rcx, rdi
0x180084f00  mov     rax, [rax]
0x180084f03  call    _guard_dispatch_icall
0x180084f08  mov     eax, ebx
0x180084f0a  lock xadd [rdi+0Ch], eax
0x180084f0f  add     eax, ebx
0x180084f11  jnz     short loc_180084F23
0x180084f13  mov     rax, [rdi]
0x180084f16  mov     rcx, rdi
0x180084f19  mov     rax, [rax+8]
0x180084f1d  call    _guard_dispatch_icall
0x180084f22  nop
0x180084f23  add     [rsi+4Ch], ebx
0x180084f26  jnz     short loc_180084F35
0x180084f28  mov     [rsi+48h], ebx
0x180084f2b  lea     rcx, [rsi+10h]; SRWLock
0x180084f2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180084f35  mov     eax, r14d
0x180084f38  jmp     short loc_180084FAE
0x180084f3a  mov     [r15+158h], rbx
0x180084f41  mov     r14, [r15+160h]
0x180084f48  mov     [r15+160h], rdi
0x180084f4f  or      ebx, 0FFFFFFFFh
0x180084f52  test    r14, r14
0x180084f55  jz      short loc_180084F8D
0x180084f57  mov     eax, ebx
0x180084f59  lock xadd [r14+8], eax
0x180084f5f  add     eax, ebx
0x180084f61  jnz     short loc_180084F8D
0x180084f63  mov     rax, [r14]
0x180084f66  mov     rcx, r14
0x180084f69  mov     rax, [rax]
0x180084f6c  call    _guard_dispatch_icall
0x180084f71  mov     eax, ebx
0x180084f73  lock xadd [r14+0Ch], eax
0x180084f79  add     eax, ebx
0x180084f7b  jnz     short loc_180084F8D
0x180084f7d  mov     rax, [r14]
0x180084f80  mov     rcx, r14
0x180084f83  mov     rax, [rax+8]
0x180084f87  call    _guard_dispatch_icall
0x180084f8c  nop
0x180084f8d  add     [rsi+4Ch], ebx
0x180084f90  jnz     short loc_180084F9F
0x180084f92  mov     [rsi+48h], ebx
0x180084f95  lea     rcx, [rsi+10h]; SRWLock
0x180084f99  call    cs:__imp_ReleaseSRWLockExclusive
0x180084f9f  xor     eax, eax
0x180084fa1  jmp     short loc_180084FAE
0x180084fa3  mov     eax, 8007000Eh
0x180084fa8  jmp     short loc_180084FAE
0x180084faa  mov     eax, [rsp+0D8h+var_98]
0x180084fae  lea     r11, [rsp+0D8h+var_28]
0x180084fb6  mov     rbx, [r11+40h]
0x180084fba  mov     rsi, [r11+48h]
0x180084fbe  mov     rsp, r11
0x180084fc1  pop     r15
0x180084fc3  pop     r14
0x180084fc5  pop     r13
0x180084fc7  pop     r12
0x180084fc9  pop     rdi
0x180084fca  retn
0x180084fcb  mov     ecx, 5; int
0x180084fd0  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180084fd5  dec     eax
0x180084fd7  mov     [rsi+4Ch], eax
0x180084fda  mov     ecx, 6; int
0x180084fdf  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
