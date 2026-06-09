# RepoMan::DownloadManagerBase<>::ValidateTasks(IRepoOperation *,IRepoFileTasks *)

- ea: `0x1800b2f50`
- end: `0x1800b3296`
- name: `?ValidateTasks@?$DownloadManagerBase@$$V@RepoMan@@UEAAJPEAUIRepoOperation@@PEAUIRepoFileTasks@@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008574`
- `0x180013b14`
- `0x18001bb78`
- `0x1800b2f50`
- `0x1800b4bb4`
- `0x1800b6878`
- `0x18018aed8`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b30c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b31c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b30c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b31c2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b30be`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b31bb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b30be`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800b31bb`

## string_xrefs

- `0x1800b2ff8`: `tasks`
- `0x1800b2f7b`: `DownloadManagerBase::ValidateTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RepoMan::DownloadManagerBase<>::ValidateTasks(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  const char *v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  RepoMan *v12; // rcx
  const char *v13; // r9
  unsigned int v14; // eax
  const char *v15; // r9
  _BYTE *v16; // rax
  size_t v17; // r8
  void *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // r8d
  __int64 result; // rax
  __int64 v23; // [rsp+30h] [rbp-98h] BYREF
  __int64 v24; // [rsp+38h] [rbp-90h] BYREF
  __int64 v25; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v26[16]; // [rsp+48h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-70h] BYREF
  __m128i si128; // [rsp+68h] [rbp-60h]
  _BYTE v29[40]; // [rsp+78h] [rbp-50h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-28h]

  RepoMan::Tracer::Tracer(v29, 2, "DownloadManagerBase::ValidateTasks");
  v24 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 24LL))(
         *(_QWORD *)(a1 + 48) + 8LL,
         &v24);
  try
  {
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v6, 536, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v7);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        537,
        (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
        (unsigned int)"user cancelled.",
        -1941503743,
        8);
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LODWORD(Block[0]) = *(_DWORD *)"tasks";
    WORD2(Block[0]) = (unsigned __int8)aTasks[4];
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 56LL))(a3);
    RepoMan::Logger::CreateValue((unsigned int)&v25, 3, 11, (unsigned int)Block, v8);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v25);
    v9 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    }
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v10 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v10 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v10);
    }
    v23 = 0;
    v11 = *(_QWORD *)(a1 + 56);
    if ( v11 )
    {
      v12 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, &v23);
      RepoMan::RaiseExceptionIfFailed(v12, 543, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v13);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, &v23);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v14, 547, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v15);
    }
    v16 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    *(_OWORD *)Block = 0;
    si128 = 0;
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    std::string::_Construct<1,char const *>(Block, v16, v17);
    std::make_shared<RepoMan::Folder,std::string>(v26, Block);
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v18 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v18 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v18);
    }
    RepoMan::DownloadManagerBase<>::DoValidateTasks(a1, a2, a3, (unsigned int)&v24, a1 + 56, (__int64)v26);
    std::shared_ptr<std::vector<unsigned char>>::~shared_ptr<std::vector<unsigned char>>(v26);
    v19 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v29);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", (const char *)0x22A, v21);
  }
  return result;
}

```

## disassembly

```asm
0x1800b2f50  mov     [rsp+arg_18], rbx
0x1800b2f55  push    rsi
0x1800b2f56  push    rdi
0x1800b2f57  push    r14
0x1800b2f59  sub     rsp, 0B0h
0x1800b2f60  mov     rax, cs:__security_cookie
0x1800b2f67  xor     rax, rsp
0x1800b2f6a  mov     [rsp+0C8h+var_20], rax
0x1800b2f72  mov     r14, r8
0x1800b2f75  mov     rsi, rdx
0x1800b2f78  mov     rbx, rcx
0x1800b2f7b  lea     r8, aDownloadmanage; "DownloadManagerBase::ValidateTasks"
0x1800b2f82  mov     edx, 2
0x1800b2f87  lea     rcx, [rsp+0C8h+var_50]
0x1800b2f8c  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800b2f91  nop
0x1800b2f92  mov     [rsp+0C8h+var_90], 0
0x1800b2f9b  mov     rcx, [rbx+30h]
0x1800b2f9f  add     rcx, 8
0x1800b2fa3  mov     rax, [rcx]
0x1800b2fa6  lea     rdx, [rsp+0C8h+var_90]
0x1800b2fab  mov     rax, [rax+18h]
0x1800b2faf  call    cs:__guard_dispatch_icall_fptr
0x1800b2fb5  mov     ecx, eax; this
0x1800b2fb7  lea     r8, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800b2fbe  mov     edx, 218h; int
0x1800b2fc3  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800b2fc8  mov     rcx, [rsp+0C8h+var_90]
0x1800b2fcd  mov     rax, [rcx]
0x1800b2fd0  mov     rax, [rax+20h]
0x1800b2fd4  call    cs:__guard_dispatch_icall_fptr
0x1800b2fda  test    eax, eax
0x1800b2fdc  jnz     loc_1800B326E
0x1800b2fe2  xorps   xmm0, xmm0
0x1800b2fe5  movups  xmmword ptr [rsp+0C8h+Block], xmm0
0x1800b2fea  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000005
0x1800b2ff2  movdqu  [rsp+0C8h+var_60], xmm0
0x1800b2ff8  mov     eax, dword ptr cs:aTasks; "tasks"
0x1800b2ffe  mov     dword ptr [rsp+0C8h+Block], eax
0x1800b3002  mov     al, byte ptr cs:aTasks+4; "s"
0x1800b3008  mov     byte ptr [rsp+0C8h+Block+4], al
0x1800b300c  mov     byte ptr [rsp+0C8h+Block+5], 0
0x1800b3011  mov     rax, [r14]
0x1800b3014  mov     rcx, r14
0x1800b3017  mov     rax, [rax+38h]
0x1800b301b  call    cs:__guard_dispatch_icall_fptr
0x1800b3021  mov     eax, eax
0x1800b3023  mov     [rsp+0C8h+Reserved], rax
0x1800b3028  lea     r9, [rsp+0C8h+Block]
0x1800b302d  mov     edx, 3
0x1800b3032  lea     r8d, [rdx+8]
0x1800b3036  lea     rcx, [rsp+0C8h+var_88]
0x1800b303b  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800b3040  mov     rcx, [rsp+0C8h+var_28]
0x1800b3048  mov     rax, [rcx]
0x1800b304b  lea     rdx, [rsp+0C8h+var_88]
0x1800b3050  mov     rax, [rax+30h]
0x1800b3054  call    cs:__guard_dispatch_icall_fptr
0x1800b305a  nop
0x1800b305b  mov     rcx, [rsp+0C8h+var_88]
0x1800b3060  test    rcx, rcx
0x1800b3063  jz      short loc_1800B307C
0x1800b3065  mov     [rsp+0C8h+var_88], 0
0x1800b306e  mov     rax, [rcx]
0x1800b3071  mov     rax, [rax+8]
0x1800b3075  call    cs:__guard_dispatch_icall_fptr
0x1800b307b  nop
0x1800b307c  mov     rax, qword ptr [rsp+0C8h+var_60+8]
0x1800b3081  cmp     rax, 0Fh
0x1800b3085  jbe     short loc_1800B30CB
0x1800b3087  mov     rcx, [rsp+0C8h+Block]; Block
0x1800b308c  mov     rdx, rcx
0x1800b308f  inc     rax
0x1800b3092  cmp     rax, 1000h
0x1800b3098  jb      short loc_1800B30C5
0x1800b309a  mov     rcx, [rcx-8]
0x1800b309e  sub     rdx, rcx
0x1800b30a1  lea     rax, [rdx-8]
0x1800b30a5  cmp     rax, 1Fh
0x1800b30a9  jbe     short loc_1800B30C5
0x1800b30ab  mov     [rsp+0C8h+Reserved], 0; Reserved
0x1800b30b4  xor     r9d, r9d; LineNo
0x1800b30b7  xor     r8d, r8d; FileName
0x1800b30ba  xor     edx, edx; FunctionName
0x1800b30bc  xor     ecx, ecx; Expression
0x1800b30be  call    cs:__imp__invoke_watson
0x1800b30c5  call    cs:__imp_free
0x1800b30cb  mov     [rsp+0C8h+var_98], 0
0x1800b30d4  lea     rdi, [rbx+38h]
0x1800b30d8  mov     rcx, [rdi]
0x1800b30db  lea     rdx, [rsp+0C8h+var_98]
0x1800b30e0  test    rcx, rcx
0x1800b30e3  jz      short loc_1800B3107
0x1800b30e5  mov     rax, [rcx]
0x1800b30e8  mov     rax, [rax+28h]
0x1800b30ec  call    cs:__guard_dispatch_icall_fptr
0x1800b30f2  mov     ecx, eax; this
0x1800b30f4  lea     r8, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800b30fb  mov     edx, 21Fh; int
0x1800b3100  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800b3105  jmp     short loc_1800B312A
0x1800b3107  mov     rax, [rsi]
0x1800b310a  mov     rcx, rsi
0x1800b310d  mov     rax, [rax+28h]
0x1800b3111  call    cs:__guard_dispatch_icall_fptr
0x1800b3117  mov     ecx, eax; this
0x1800b3119  lea     r8, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800b3120  mov     edx, 223h; int
0x1800b3125  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800b312a  mov     rcx, [rsp+0C8h+var_98]
0x1800b312f  mov     rax, [rcx]
0x1800b3132  mov     rax, [rax+18h]
0x1800b3136  call    cs:__guard_dispatch_icall_fptr
0x1800b313c  xorps   xmm0, xmm0
0x1800b313f  movups  xmmword ptr [rsp+0C8h+Block], xmm0
0x1800b3144  xorps   xmm1, xmm1
0x1800b3147  movdqu  [rsp+0C8h+var_60], xmm1
0x1800b314d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b3151  inc     r8
0x1800b3154  cmp     byte ptr [rax+r8], 0
0x1800b3159  jnz     short loc_1800B3151
0x1800b315b  mov     rdx, rax
0x1800b315e  lea     rcx, [rsp+0C8h+Block]
0x1800b3163  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800b3168  nop
0x1800b3169  lea     rdx, [rsp+0C8h+Block]
0x1800b316e  lea     rcx, [rsp+0C8h+var_80]
0x1800b3173  call    ??$make_shared@VFolder@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$shared_ptr@VFolder@RepoMan@@@0@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_shared<RepoMan::Folder,std::string>(std::string &&)
0x1800b3178  nop
0x1800b3179  mov     rax, qword ptr [rsp+0C8h+var_60+8]
0x1800b317e  cmp     rax, 0Fh
0x1800b3182  jbe     short loc_1800B31C8
0x1800b3184  mov     rcx, [rsp+0C8h+Block]; Block
0x1800b3189  mov     rdx, rcx
0x1800b318c  inc     rax
0x1800b318f  cmp     rax, 1000h
0x1800b3195  jb      short loc_1800B31C2
0x1800b3197  mov     rcx, [rcx-8]
0x1800b319b  sub     rdx, rcx
0x1800b319e  lea     rax, [rdx-8]
0x1800b31a2  cmp     rax, 1Fh
0x1800b31a6  jbe     short loc_1800B31C2
0x1800b31a8  mov     [rsp+0C8h+Reserved], 0; Reserved
0x1800b31b1  xor     r9d, r9d; LineNo
0x1800b31b4  xor     r8d, r8d; FileName
0x1800b31b7  xor     edx, edx; FunctionName
0x1800b31b9  xor     ecx, ecx; Expression
0x1800b31bb  call    cs:__imp__invoke_watson
0x1800b31c2  call    cs:__imp_free
0x1800b31c8  lea     rax, [rsp+0C8h+var_80]
0x1800b31cd  mov     [rsp+0C8h+var_A0], rax
0x1800b31d2  mov     [rsp+0C8h+Reserved], rdi
0x1800b31d7  lea     r9, [rsp+0C8h+var_90]
0x1800b31dc  mov     r8, r14
0x1800b31df  mov     rdx, rsi
0x1800b31e2  mov     rcx, rbx
0x1800b31e5  call    ?DoValidateTasks@?$DownloadManagerBase@$$V@RepoMan@@QEAAXPEAUIRepoOperation@@PEAUIRepoFileTasks@@AEAV?$ComPtr@UIRepoProgress@@@2@AEAV?$ComPtr@UIRepoOperation@@@2@AEAV?$shared_ptr@VFolder@RepoMan@@@std@@@Z; RepoMan::DownloadManagerBase<>::DoValidateTasks(IRepoOperation *,IRepoFileTasks *,RepoMan::ComPtr<IRepoProgress> &,RepoMan::ComPtr<IRepoOperation> &,std::shared_ptr<RepoMan::Folder> &)
0x1800b31ea  nop
0x1800b31eb  lea     rcx, [rsp+0C8h+var_80]
0x1800b31f0  call    ??1?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<uchar>>::~shared_ptr<std::vector<uchar>>(void)
0x1800b31f5  nop
0x1800b31f6  mov     rcx, [rsp+0C8h+var_98]
0x1800b31fb  test    rcx, rcx
0x1800b31fe  jz      short loc_1800B3217
0x1800b3200  mov     [rsp+0C8h+var_98], 0
0x1800b3209  mov     rax, [rcx]
0x1800b320c  mov     rax, [rax+10h]
0x1800b3210  call    cs:__guard_dispatch_icall_fptr
0x1800b3216  nop
0x1800b3217  mov     rcx, [rsp+0C8h+var_90]
0x1800b321c  test    rcx, rcx
0x1800b321f  jz      short loc_1800B3238
0x1800b3221  mov     [rsp+0C8h+var_90], 0
0x1800b322a  mov     rax, [rcx]
0x1800b322d  mov     rax, [rax+10h]
0x1800b3231  call    cs:__guard_dispatch_icall_fptr
0x1800b3237  nop
0x1800b3238  lea     rcx, [rsp+0C8h+var_50]; this
0x1800b323d  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x1800b3242  xor     eax, eax
0x1800b3244  jmp     short loc_1800B324A
0x1800b3246  mov     eax, dword ptr [rsp+0C8h+var_98]
0x1800b324a  mov     rcx, [rsp+0C8h+var_20]
0x1800b3252  xor     rcx, rsp; StackCookie
0x1800b3255  call    __security_check_cookie
0x1800b325a  mov     rbx, [rsp+0C8h+arg_18]
0x1800b3262  add     rsp, 0B0h
0x1800b3269  pop     r14
0x1800b326b  pop     rdi
0x1800b326c  pop     rsi
0x1800b326d  retn
0x1800b326e  mov     dword ptr [rsp+0C8h+Reserved], 8
0x1800b3276  mov     r9d, 8C470101h
0x1800b327c  lea     r8, aUserCancelled; "user cancelled."
0x1800b3283  lea     rdx, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800b328a  mov     ecx, 219h
0x1800b328f  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
