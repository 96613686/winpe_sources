# CBackgroundCopyJob::_GetTotalSizeBytes(std::shared_ptr<CConfigValue> &)

- ea: `0x180092914`
- end: `0x180092d67`
- name: `?_GetTotalSizeBytes@CBackgroundCopyJob@@AEAAJAEAV?$shared_ptr@VCConfigValue@@@std@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(CBackgroundCopyJob *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180089678`

## callees

- `0x18000933c`
- `0x18000cdd0`
- `0x18001dfc4`
- `0x18001fe68`
- `0x180021eb4`
- `0x1800261a8`
- `0x180026364`
- `0x180084098`
- `0x180089e64`
- `0x180092914`
- `0x1800944a8`
- `0x1800e8988`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092969`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800929b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800929cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180092d16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800929b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800929cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180092d16`

## string_xrefs

- `0x18009299d`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180092a04`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180092a79`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180092b45`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x180092bcb`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBackgroundCopyJob::_GetTotalSizeBytes(RTL_SRWLOCK *this, unsigned __int8 **a2)
{
  RTL_SRWLOCK *v4; // rsi
  char v5; // r13
  CBackgroundCopyFile **Ptr; // rcx
  int Property; // eax
  const char *v8; // r9
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // r14d
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rdi
  PVOID v16; // rdi
  __int64 HttpParams; // rax
  int v18; // eax
  unsigned int v19; // r14d
  volatile signed __int32 *v20; // rdi
  __int64 v21; // rbx
  volatile signed __int32 *v22; // rdi
  _DWORD *v23; // rax
  volatile signed __int32 *v24; // rdi
  volatile signed __int32 *v25; // rdi
  char *v26; // [rsp+20h] [rbp-1F8h] BYREF
  volatile signed __int32 *v27; // [rsp+28h] [rbp-1F0h]
  __int128 v28; // [rsp+30h] [rbp-1E8h] BYREF
  RTL_SRWLOCK *v29; // [rsp+40h] [rbp-1D8h]
  __int64 v30; // [rsp+48h] [rbp-1D0h]
  _BYTE v31[96]; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v32[38]; // [rsp+B0h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v4 = this + 28;
  v29 = this + 28;
  v5 = 1;
  v30 = 1;
  AcquireSRWLockShared(this + 28);
  try
  {
    Ptr = (CBackgroundCopyFile **)this[8].Ptr;
    if ( Ptr != this[9].Ptr )
    {
      Property = CBackgroundCopyFile::GetProperty(*Ptr);
      v9 = Property;
      if ( Property < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x924,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)Property,
          (int)v26);
        ReleaseSRWLockShared(v4);
        return v9;
      }
      goto LABEL_39;
    }
    if ( !v4 )
      std::_Throw_system_error(1);
    ReleaseSRWLockShared(v4);
    v5 = 0;
    LOBYTE(v30) = 0;
    v28 = 0;
    v11 = CConfigStore::Find(&this[2], 1, &v28);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v14 = v28;
      if ( (_QWORD)v28 )
      {
        memset(v32, 0, 0x128u);
        v16 = this[11].Ptr;
        HttpParams = CJobSharedData::GetHttpParams(this[31].Ptr, v31);
        CContentSizeRetriever::CContentSizeRetriever(v32, HttpParams, v16);
        if ( *(_BYTE *)(v14 + 32) != 7 )
          std::_Throw_bad_variant_access();
        v18 = CContentSizeRetriever::DoConnect(v32, v14, 1);
        v19 = v18;
        if ( v18 >= 0 )
        {
          v21 = v32[13];
          if ( v32[13] )
          {
            v23 = operator new(0x38u);
            v23[2] = 1;
            v23[3] = 1;
            *(_QWORD *)v23 = &std::_Ref_count_obj2<CConfigValue>::`vftable';
            *((_QWORD *)v23 + 2) = v21;
            *((_BYTE *)v23 + 48) = 5;
            v26 = (char *)(v23 + 4);
            v27 = v23;
            std::shared_ptr<_EXCEPTION_RECORD const>::operator=(a2, &v26);
            v24 = v27;
            if ( v27 )
            {
              if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
                if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
              }
            }
            CBackgroundCopyJob::SetDownloadProperty((CBackgroundCopyJob *)this, (char *)0x15, a2, 0);
            CContentSizeRetriever::~CContentSizeRetriever((CContentSizeRetriever *)v32);
            v25 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
            if ( *((_QWORD *)&v28 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
                if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
              }
            }
LABEL_39:
            if ( v5 )
              ReleaseSRWLockShared(v4);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x933,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)0x80070490LL,
            (int)v26);
          CContentSizeRetriever::~CContentSizeRetriever((CContentSizeRetriever *)v32);
          v22 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
          if ( *((_QWORD *)&v28 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          result = 2147943568LL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x930,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
            (const char *)(unsigned int)v18,
            (int)v26);
          CContentSizeRetriever::~CContentSizeRetriever((CContentSizeRetriever *)v32);
          v20 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
          if ( *((_QWORD *)&v28 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
            }
          }
          result = v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x92D,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)0x80070490LL,
          (int)v26);
        v15 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
        if ( *((_QWORD *)&v28 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        result = 2147943568LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92C,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v11,
        (int)v26);
      v13 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      result = v12;
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
                           (void *)0x93A,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180092914  mov     [rsp+arg_10], rbx
0x180092919  mov     [rsp+arg_18], rsi
0x18009291e  push    rdi
0x18009291f  push    r12
0x180092921  push    r13
0x180092923  push    r14
0x180092925  push    r15
0x180092927  sub     rsp, 1F0h
0x18009292e  mov     rax, cs:__security_cookie
0x180092935  xor     rax, rsp
0x180092938  mov     [rsp+218h+var_38], rax
0x180092940  mov     r12, rdx
0x180092943  mov     r15, rcx
0x180092946  xorps   xmm0, xmm0
0x180092949  movups  [rsp+218h+var_1D8], xmm0
0x18009294e  lea     rsi, [rcx+0E0h]
0x180092955  mov     qword ptr [rsp+218h+var_1D8], rsi
0x18009295a  mov     ebx, 1
0x18009295f  mov     r13b, bl
0x180092962  mov     byte ptr [rsp+218h+var_1D8+8], bl
0x180092966  mov     rcx, rsi; SRWLock
0x180092969  call    cs:__imp_AcquireSRWLockShared
0x18009296f  nop
0x180092970  mov     rcx, [r15+40h]
0x180092974  cmp     rcx, [r15+48h]
0x180092978  jz      short loc_1800929BF
0x18009297a  mov     r8, r12
0x18009297d  lea     edx, [rbx+3]
0x180092980  mov     rcx, [rcx]
0x180092983  call    ?GetProperty@CBackgroundCopyFile@@QEAAJW4DownloadFileProperty@@AEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CBackgroundCopyFile::GetProperty(DownloadFileProperty,std::shared_ptr<CConfigValue> &)
0x180092988  mov     ebx, eax
0x18009298a  test    eax, eax
0x18009298c  jns     loc_180092D0E
0x180092992  mov     rcx, [rsp+218h]; this
0x18009299a  mov     r9d, eax; char *
0x18009299d  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800929a4  mov     edx, 924h; void *
0x1800929a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800929ae  nop
0x1800929af  mov     rcx, rsi; SRWLock
0x1800929b2  call    cs:__imp_ReleaseSRWLockShared
0x1800929b8  mov     eax, ebx
0x1800929ba  jmp     loc_180092D2B
0x1800929bf  test    rsi, rsi
0x1800929c2  jz      loc_180092D5E
0x1800929c8  mov     rcx, rsi; SRWLock
0x1800929cb  call    cs:__imp_ReleaseSRWLockShared
0x1800929d1  xor     r13b, r13b
0x1800929d4  mov     byte ptr [rsp+218h+var_1D8+8], r13b
0x1800929d9  xorps   xmm1, xmm1
0x1800929dc  movdqu  [rsp+218h+var_1E8], xmm1
0x1800929e2  lea     rcx, [r15+10h]
0x1800929e6  lea     r8, [rsp+218h+var_1E8]
0x1800929eb  mov     edx, ebx
0x1800929ed  call    ?Find@CConfigStore@@QEBAJHAEAV?$shared_ptr@VCConfigValue@@@std@@@Z; CConfigStore::Find(int,std::shared_ptr<CConfigValue> &)
0x1800929f2  mov     r14d, eax
0x1800929f5  test    eax, eax
0x1800929f7  jns     short loc_180092A5F
0x1800929f9  mov     rcx, [rsp+218h]; this
0x180092a01  mov     r9d, eax; char *
0x180092a04  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180092a0b  mov     edx, 92Ch; void *
0x180092a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092a15  nop
0x180092a16  mov     rdi, qword ptr [rsp+218h+var_1E8+8]
0x180092a1b  test    rdi, rdi
0x180092a1e  jz      short loc_180092A57
0x180092a20  or      ebx, 0FFFFFFFFh
0x180092a23  mov     eax, ebx
0x180092a25  lock xadd [rdi+8], eax
0x180092a2a  add     eax, ebx
0x180092a2c  jnz     short loc_180092A57
0x180092a2e  mov     rax, [rdi]
0x180092a31  mov     rcx, rdi
0x180092a34  mov     rax, [rax]
0x180092a37  call    _guard_dispatch_icall
0x180092a3c  mov     eax, ebx
0x180092a3e  lock xadd [rdi+0Ch], eax
0x180092a43  add     eax, ebx
0x180092a45  jnz     short loc_180092A57
0x180092a47  mov     rax, [rdi]
0x180092a4a  mov     rcx, rdi
0x180092a4d  mov     rax, [rax+8]
0x180092a51  call    _guard_dispatch_icall
0x180092a56  nop
0x180092a57  mov     eax, r14d
0x180092a5a  jmp     loc_180092D2B
0x180092a5f  mov     rbx, qword ptr [rsp+218h+var_1E8]
0x180092a64  test    rbx, rbx
0x180092a67  jnz     short loc_180092AD3
0x180092a69  mov     rcx, [rsp+218h]; this
0x180092a71  mov     esi, 80070490h
0x180092a76  mov     r9d, esi; char *
0x180092a79  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180092a80  mov     edx, 92Dh; void *
0x180092a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092a8a  nop
0x180092a8b  mov     rdi, qword ptr [rsp+218h+var_1E8+8]
0x180092a90  test    rdi, rdi
0x180092a93  jz      short loc_180092ACC
0x180092a95  or      ebx, 0FFFFFFFFh
0x180092a98  mov     eax, ebx
0x180092a9a  lock xadd [rdi+8], eax
0x180092a9f  add     eax, ebx
0x180092aa1  jnz     short loc_180092ACC
0x180092aa3  mov     rax, [rdi]
0x180092aa6  mov     rcx, rdi
0x180092aa9  mov     rax, [rax]
0x180092aac  call    _guard_dispatch_icall
0x180092ab1  mov     ecx, ebx
0x180092ab3  lock xadd [rdi+0Ch], ecx
0x180092ab8  add     ecx, ebx
0x180092aba  jnz     short loc_180092ACC
0x180092abc  mov     rcx, [rdi]
0x180092abf  mov     rax, [rcx+8]
0x180092ac3  mov     rcx, rdi
0x180092ac6  call    _guard_dispatch_icall
0x180092acb  nop
0x180092acc  mov     eax, esi
0x180092ace  jmp     loc_180092D2B
0x180092ad3  xor     edx, edx; Val
0x180092ad5  mov     r8d, 128h; Size
0x180092adb  lea     rcx, [rsp+218h+var_168]; void *
0x180092ae3  call    memset
0x180092ae8  mov     rdi, [r15+58h]
0x180092aec  lea     rdx, [rsp+218h+var_1C8]
0x180092af1  mov     rcx, [r15+0F8h]
0x180092af8  call    ?GetHttpParams@CJobSharedData@@QEBA?AVCHttpParameters@@XZ; CJobSharedData::GetHttpParams(void)
0x180092afd  mov     r8, rdi
0x180092b00  mov     rdx, rax
0x180092b03  lea     rcx, [rsp+218h+var_168]
0x180092b0b  call    ??0CContentSizeRetriever@@QEAA@VCHttpParameters@@PEAVTraceLoggingCorrelationVector@@@Z; CContentSizeRetriever::CContentSizeRetriever(CHttpParameters,TraceLoggingCorrelationVector *)
0x180092b10  nop
0x180092b11  cmp     byte ptr [rbx+20h], 7
0x180092b15  jnz     loc_180092D58
0x180092b1b  mov     edi, 1
0x180092b20  mov     r8d, edi
0x180092b23  mov     rdx, rbx
0x180092b26  lea     rcx, [rsp+218h+var_168]
0x180092b2e  call    ?DoConnect@CContentSizeRetriever@@QEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@Z; CContentSizeRetriever::DoConnect(std::string const &,uint)
0x180092b33  mov     r14d, eax
0x180092b36  test    eax, eax
0x180092b38  jns     short loc_180092BAE
0x180092b3a  mov     rcx, [rsp+218h]; this
0x180092b42  mov     r9d, eax; char *
0x180092b45  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180092b4c  mov     edx, 930h; void *
0x180092b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092b56  nop
0x180092b57  lea     rcx, [rsp+218h+var_168]; this
0x180092b5f  call    ??1CContentSizeRetriever@@QEAA@XZ; CContentSizeRetriever::~CContentSizeRetriever(void)
0x180092b64  nop
0x180092b65  mov     rdi, qword ptr [rsp+218h+var_1E8+8]
0x180092b6a  test    rdi, rdi
0x180092b6d  jz      short loc_180092BA6
0x180092b6f  or      ebx, 0FFFFFFFFh
0x180092b72  mov     eax, ebx
0x180092b74  lock xadd [rdi+8], eax
0x180092b79  add     eax, ebx
0x180092b7b  jnz     short loc_180092BA6
0x180092b7d  mov     rax, [rdi]
0x180092b80  mov     rcx, rdi
0x180092b83  mov     rax, [rax]
0x180092b86  call    _guard_dispatch_icall
0x180092b8b  mov     eax, ebx
0x180092b8d  lock xadd [rdi+0Ch], eax
0x180092b92  add     eax, ebx
0x180092b94  jnz     short loc_180092BA6
0x180092b96  mov     rax, [rdi]
0x180092b99  mov     rcx, rdi
0x180092b9c  mov     rax, [rax+8]
0x180092ba0  call    _guard_dispatch_icall
0x180092ba5  nop
0x180092ba6  mov     eax, r14d
0x180092ba9  jmp     loc_180092D2B
0x180092bae  mov     rbx, [rsp+218h+var_100]
0x180092bb6  test    rbx, rbx
0x180092bb9  jnz     short loc_180092C33
0x180092bbb  mov     rcx, [rsp+218h]; this
0x180092bc3  mov     esi, 80070490h
0x180092bc8  mov     r9d, esi; char *
0x180092bcb  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180092bd2  mov     edx, 933h; void *
0x180092bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092bdc  nop
0x180092bdd  lea     rcx, [rsp+218h+var_168]; this
0x180092be5  call    ??1CContentSizeRetriever@@QEAA@XZ; CContentSizeRetriever::~CContentSizeRetriever(void)
0x180092bea  nop
0x180092beb  mov     rdi, qword ptr [rsp+218h+var_1E8+8]
0x180092bf0  test    rdi, rdi
0x180092bf3  jz      short loc_180092C2C
0x180092bf5  or      ebx, 0FFFFFFFFh
0x180092bf8  mov     eax, ebx
0x180092bfa  lock xadd [rdi+8], eax
0x180092bff  add     eax, ebx
0x180092c01  jnz     short loc_180092C2C
0x180092c03  mov     rax, [rdi]
0x180092c06  mov     rcx, rdi
0x180092c09  mov     rax, [rax]
0x180092c0c  call    _guard_dispatch_icall
0x180092c11  mov     eax, ebx
0x180092c13  lock xadd [rdi+0Ch], eax
0x180092c18  add     eax, ebx
0x180092c1a  jnz     short loc_180092C2C
0x180092c1c  mov     rax, [rdi]
0x180092c1f  mov     rcx, rdi
0x180092c22  mov     rax, [rax+8]
0x180092c26  call    _guard_dispatch_icall
0x180092c2b  nop
0x180092c2c  mov     eax, esi
0x180092c2e  jmp     loc_180092D2B
0x180092c33  mov     ecx, 38h ; '8'; Size
0x180092c38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180092c3d  mov     [rax+8], edi
0x180092c40  mov     [rax+0Ch], edi
0x180092c43  lea     rcx, ??_7?$_Ref_count_obj2@VCConfigValue@@@std@@6B@; const std::_Ref_count_obj2<CConfigValue>::`vftable'
0x180092c4a  mov     [rax], rcx
0x180092c4d  lea     rcx, [rax+10h]
0x180092c51  mov     [rcx], rbx
0x180092c54  mov     byte ptr [rcx+20h], 5
0x180092c58  mov     [rsp+218h+var_1F8], rcx
0x180092c5d  mov     [rsp+218h+var_1F0], rax
0x180092c62  lea     rdx, [rsp+218h+var_1F8]
0x180092c67  mov     rcx, r12
0x180092c6a  call    ??4?$shared_ptr@$$CBU_EXCEPTION_RECORD@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_EXCEPTION_RECORD const>::operator=(std::shared_ptr<_EXCEPTION_RECORD const> &&)
0x180092c6f  mov     rdi, [rsp+218h+var_1F0]
0x180092c74  or      ebx, 0FFFFFFFFh
0x180092c77  test    rdi, rdi
0x180092c7a  jz      short loc_180092CAF
0x180092c7c  mov     eax, ebx
0x180092c7e  lock xadd [rdi+8], eax
0x180092c83  add     eax, ebx
0x180092c85  jnz     short loc_180092CAF
0x180092c87  mov     rax, [rdi]
0x180092c8a  mov     rcx, rdi
0x180092c8d  mov     rax, [rax]
0x180092c90  call    _guard_dispatch_icall
0x180092c95  mov     eax, ebx
0x180092c97  lock xadd [rdi+0Ch], eax
0x180092c9c  add     eax, ebx
0x180092c9e  jnz     short loc_180092CAF
0x180092ca0  mov     rax, [rdi]
0x180092ca3  mov     rcx, rdi
0x180092ca6  mov     rax, [rax+8]
0x180092caa  call    _guard_dispatch_icall
0x180092caf  xor     r9d, r9d
0x180092cb2  mov     r8, r12
0x180092cb5  lea     edx, [r9+15h]; char *
0x180092cb9  mov     rcx, r15; this
0x180092cbc  call    ?SetDownloadProperty@CBackgroundCopyJob@@QEAAJIAEBV?$shared_ptr@VCConfigValue@@@std@@_N@Z; CBackgroundCopyJob::SetDownloadProperty(uint,std::shared_ptr<CConfigValue> const &,bool)
0x180092cc1  nop
0x180092cc2  lea     rcx, [rsp+218h+var_168]; this
0x180092cca  call    ??1CContentSizeRetriever@@QEAA@XZ; CContentSizeRetriever::~CContentSizeRetriever(void)
0x180092ccf  nop
0x180092cd0  mov     rdi, qword ptr [rsp+218h+var_1E8+8]
0x180092cd5  test    rdi, rdi
0x180092cd8  jz      short loc_180092D0E
0x180092cda  mov     eax, ebx
0x180092cdc  lock xadd [rdi+8], eax
0x180092ce1  add     eax, ebx
0x180092ce3  jnz     short loc_180092D0E
0x180092ce5  mov     rax, [rdi]
0x180092ce8  mov     rcx, rdi
0x180092ceb  mov     rax, [rax]
0x180092cee  call    _guard_dispatch_icall
0x180092cf3  mov     eax, ebx
0x180092cf5  lock xadd [rdi+0Ch], eax
0x180092cfa  add     eax, ebx
0x180092cfc  jnz     short loc_180092D0E
0x180092cfe  mov     rax, [rdi]
0x180092d01  mov     rcx, rdi
0x180092d04  mov     rax, [rax+8]
0x180092d08  call    _guard_dispatch_icall
0x180092d0d  nop
0x180092d0e  test    r13b, r13b
0x180092d11  jz      short loc_180092D1C
0x180092d13  mov     rcx, rsi; SRWLock
0x180092d16  call    cs:__imp_ReleaseSRWLockShared
0x180092d1c  xor     eax, eax
0x180092d1e  jmp     short loc_180092D2B
0x180092d20  mov     eax, 8007000Eh
0x180092d25  jmp     short loc_180092D2B
0x180092d27  mov     eax, dword ptr [rsp+218h+var_1F8]
0x180092d2b  mov     rcx, [rsp+218h+var_38]
0x180092d33  xor     rcx, rsp; StackCookie
0x180092d36  call    __security_check_cookie
0x180092d3b  lea     r11, [rsp+218h+var_28]
0x180092d43  mov     rbx, [r11+40h]
0x180092d47  mov     rsi, [r11+48h]
0x180092d4b  mov     rsp, r11
0x180092d4e  pop     r15
0x180092d50  pop     r14
0x180092d52  pop     r13
0x180092d54  pop     r12
0x180092d56  pop     rdi
0x180092d57  retn
0x180092d58  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x180092d5e  mov     ecx, ebx
0x180092d60  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
