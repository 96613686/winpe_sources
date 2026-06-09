# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180011e90`
- end: `0x180012011`
- name: `?Set@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@6@1111@Z`
- size: `385`
- prototype: `char __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e100`

## callees

- `0x180008760`
- `0x18000b8b0`
- `0x18000c45c`
- `0x180011008`
- `0x180011cc0`
- `0x180011e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011efd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011efd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011fc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011fd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011fc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011fd6`

## string_xrefs

- `0x180011fff`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7)
{
  int v12; // [rsp+20h] [rbp-A1h]
  _BYTE v13[24]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v14[24]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v15[24]; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v16[24]; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v17[24]; // [rsp+A0h] [rbp-21h] BYREF
  _BYTE v18[72]; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  if ( !*(_QWORD *)(a2 + 16) || *a4 == a4[1] || *a5 == a5[1] || *a7 == a7[1] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
      (const char *)0x80070057LL,
      v12);
  AcquireSRWLockExclusive(a1 + 13);
  if ( (unsigned __int8)Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage(
                          (int)a1,
                          a2,
                          (__int64)a5,
                          a6,
                          (__int64)a7) )
  {
    std::vector<unsigned char>::vector<unsigned char>(v13, a7);
    std::vector<unsigned char>::vector<unsigned char>(v14, a6);
    std::vector<unsigned char>::vector<unsigned char>(v15, a5);
    std::vector<unsigned char>::vector<unsigned char>(v16, a4);
    std::vector<unsigned char>::vector<unsigned char>(v17, a3);
    std::unordered_map<std::wstring,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>::_Insert_or_assign<std::wstring const &,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>(
      &a1[5],
      v18,
      a2,
      v13);
    std::vector<unsigned char>::~vector<unsigned char>(v17);
    std::vector<unsigned char>::~vector<unsigned char>(v16);
    std::vector<unsigned char>::~vector<unsigned char>(v15);
    std::vector<unsigned char>::~vector<unsigned char>(v14);
    std::vector<unsigned char>::~vector<unsigned char>(v13);
    if ( a1 != (RTL_SRWLOCK *)-104LL )
      ReleaseSRWLockExclusive(a1 + 13);
    return 1;
  }
  else
  {
    if ( a1 != (RTL_SRWLOCK *)-104LL )
      ReleaseSRWLockExclusive(a1 + 13);
    return 0;
  }
}

```

## disassembly

```asm
0x180011e90  mov     [rsp-8+arg_0], rbx
0x180011e95  mov     [rsp-8+arg_10], r8
0x180011e9a  push    rbp
0x180011e9b  push    rsi
0x180011e9c  push    rdi
0x180011e9d  push    r12
0x180011e9f  push    r13
0x180011ea1  push    r14
0x180011ea3  push    r15
0x180011ea5  lea     rbp, [rsp-0Fh]
0x180011eaa  sub     rsp, 0D0h
0x180011eb1  mov     rdi, r9
0x180011eb4  mov     r15, rdx
0x180011eb7  mov     r13, rcx
0x180011eba  mov     rsi, [rbp+3Fh+arg_30]
0x180011ebe  mov     r14, [rbp+3Fh+arg_20]
0x180011ec2  cmp     qword ptr [rdx+10h], 0
0x180011ec7  jz      short loc_180011EE8
0x180011ec9  mov     rax, [r9+8]
0x180011ecd  cmp     [r9], rax
0x180011ed0  jz      short loc_180011EE8
0x180011ed2  mov     rax, [r14+8]
0x180011ed6  cmp     [r14], rax
0x180011ed9  jz      short loc_180011EE8
0x180011edb  mov     rax, [rsi+8]
0x180011edf  cmp     [rsi], rax
0x180011ee2  jz      short loc_180011EE8
0x180011ee4  xor     al, al
0x180011ee6  jmp     short loc_180011EEA
0x180011ee8  mov     al, 1
0x180011eea  mov     rcx, [rbp+47h]; this
0x180011eee  test    al, al
0x180011ef0  jnz     loc_180011FF9
0x180011ef6  lea     rbx, [r13+68h]
0x180011efa  mov     rcx, rbx; SRWLock
0x180011efd  call    cs:__imp_AcquireSRWLockExclusive
0x180011f03  mov     [rbp+3Fh+arg_8], rbx
0x180011f07  mov     [rsp+100h+var_D0], rsi; __int64
0x180011f0c  mov     r12, [rbp+3Fh+arg_28]
0x180011f10  mov     [rsp+100h+var_D8], r12; __int64
0x180011f15  mov     [rsp+100h+var_E0], r14; __int64
0x180011f1a  mov     r9, rdi
0x180011f1d  mov     r8, [rbp+3Fh+arg_10]
0x180011f21  mov     rdx, r15; int
0x180011f24  mov     rcx, r13; int
0x180011f27  call    ?SaveToStorage@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@6@1111@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage(std::wstring const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &)
0x180011f2c  test    al, al
0x180011f2e  jz      loc_180011FCE
0x180011f34  mov     rdx, rsi
0x180011f37  lea     rcx, [rsp+100h+var_C0]
0x180011f3c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011f41  nop
0x180011f42  mov     rdx, r12
0x180011f45  lea     rcx, [rbp+3Fh+var_A8]
0x180011f49  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011f4e  nop
0x180011f4f  mov     rdx, r14
0x180011f52  lea     rcx, [rbp+3Fh+var_90]
0x180011f56  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011f5b  nop
0x180011f5c  mov     rdx, rdi
0x180011f5f  lea     rcx, [rbp+3Fh+var_78]
0x180011f63  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011f68  nop
0x180011f69  mov     rdx, [rbp+3Fh+arg_10]
0x180011f6d  lea     rcx, [rbp+3Fh+var_60]
0x180011f71  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011f76  nop
0x180011f77  lea     rcx, [r13+28h]
0x180011f7b  lea     r9, [rsp+100h+var_C0]
0x180011f80  mov     r8, r15
0x180011f83  lea     rdx, [rbp+3Fh+var_48]
0x180011f87  call    ??$_Insert_or_assign@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@1@@Z; std::unordered_map<std::wstring,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>::_Insert_or_assign<std::wstring const &,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>(std::wstring const &,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>> &&)
0x180011f8c  nop
0x180011f8d  lea     rcx, [rbp+3Fh+var_60]
0x180011f91  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011f96  lea     rcx, [rbp+3Fh+var_78]
0x180011f9a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011f9f  lea     rcx, [rbp+3Fh+var_90]
0x180011fa3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011fa8  lea     rcx, [rbp+3Fh+var_A8]
0x180011fac  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011fb1  lea     rcx, [rsp+100h+var_C0]
0x180011fb6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011fbb  nop
0x180011fbc  test    rbx, rbx
0x180011fbf  jz      short loc_180011FCA
0x180011fc1  mov     rcx, rbx; SRWLock
0x180011fc4  call    cs:__imp_ReleaseSRWLockExclusive
0x180011fca  mov     al, 1
0x180011fcc  jmp     short loc_180011FDE
0x180011fce  test    rbx, rbx
0x180011fd1  jz      short loc_180011FDC
0x180011fd3  mov     rcx, rbx; SRWLock
0x180011fd6  call    cs:__imp_ReleaseSRWLockExclusive
0x180011fdc  xor     al, al
0x180011fde  mov     rbx, [rsp+100h+arg_0]
0x180011fe6  add     rsp, 0D0h
0x180011fed  pop     r15
0x180011fef  pop     r14
0x180011ff1  pop     r13
0x180011ff3  pop     r12
0x180011ff5  pop     rdi
0x180011ff6  pop     rsi
0x180011ff7  pop     rbp
0x180011ff8  retn
0x180011ff9  mov     r9d, 80070057h; char *
0x180011fff  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180012006  mov     edx, 60h ; '`'; void *
0x18001200b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
