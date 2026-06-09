# Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(wchar_t *,ShsAttestationFlag,uint,AttestationResult *)

- ea: `0x18000c8ec`
- end: `0x18000ca68`
- name: `?AddCertificatesToCache@HgServiceController@Client@HostGuardian@Microsoft@@AEAAJPEA_WW4ShsAttestationFlag@@IPEAUAttestationResult@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, _WORD *, int, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ca70`
- `0x18000dc5c`

## callees

- `0x180001770`
- `0x180003d0c`
- `0x1800077a0`
- `0x18000b4c4`
- `0x18000b8b0`
- `0x18000c45c`
- `0x18000c8ec`
- `0x18000efe0`

## string_xrefs

- `0x18000c9ec`: `Added certificate to cache`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(
        __int64 a1,
        _WORD *a2,
        int a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned int i; // ebx
  __int64 v9; // rdx
  __int64 v10; // r12
  unsigned __int64 v11; // r8
  unsigned int v12; // r15d
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  char *v18[3]; // [rsp+48h] [rbp-90h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-78h] BYREF
  __int128 v20; // [rsp+78h] [rbp-60h] BYREF
  const wchar_t *v21; // [rsp+88h] [rbp-50h]
  __int64 v22; // [rsp+90h] [rbp-48h]

  if ( !a2 || !a4 || !a5 )
    return 2147942487LL;
  for ( i = 0; i < a4; ++i )
  {
    v9 = *(_QWORD *)(a5 + 24LL * i + 16);
    std::vector<unsigned char>::vector<unsigned char>(v18, v9, v9 + *(unsigned int *)(a5 + 24LL * i + 8));
    v10 = *(_QWORD *)(a1 + 136);
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    std::wstring::_Construct<1,wchar_t const *>(&v20, a2, v11);
    v12 = *(_DWORD *)(a5 + 24LL * i);
    v13 = std::vector<unsigned char>::vector<unsigned char>(v19, (__int64)v18);
    Microsoft::HostGuardian::Client::CertificateCache::AddCertificate(v10, (__int64)v13, v12, (__int64)&v20, a3);
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
    {
      v21 = L"Added certificate to cache";
      v22 = 54;
      McGenEventWrite_EventWriteTransfer(v14, ServiceDebugInformational, v15, 2, &v20);
    }
    std::vector<unsigned char>::~vector<unsigned char>(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c8ec  push    rbx
0x18000c8ee  push    rsi
0x18000c8ef  push    rdi
0x18000c8f0  push    r12
0x18000c8f2  push    r13
0x18000c8f4  push    r14
0x18000c8f6  push    r15
0x18000c8f8  sub     rsp, 0A0h
0x18000c8ff  mov     rax, cs:__security_cookie
0x18000c906  xor     rax, rsp
0x18000c909  mov     [rsp+0D8h+var_40], rax
0x18000c911  mov     r14d, r9d
0x18000c914  mov     [rsp+0D8h+var_A8], r8d
0x18000c919  mov     rsi, rdx
0x18000c91c  mov     r13, rcx
0x18000c91f  mov     rdi, [rsp+0D8h+arg_20]
0x18000c927  xor     eax, eax
0x18000c929  test    rdx, rdx
0x18000c92c  jz      loc_18000CA39
0x18000c932  test    r9d, r9d
0x18000c935  jz      loc_18000CA39
0x18000c93b  test    rdi, rdi
0x18000c93e  jz      loc_18000CA39
0x18000c944  mov     ebx, eax
0x18000c946  cmp     ebx, r14d
0x18000c949  jnb     loc_18000CA35
0x18000c94f  mov     eax, ebx
0x18000c951  lea     r15, [rax+rax*2]
0x18000c955  mov     rdx, [rdi+r15*8+10h]
0x18000c95a  mov     r8d, [rdi+r15*8+8]
0x18000c95f  add     r8, rdx
0x18000c962  lea     rcx, [rsp+0D8h+var_90]
0x18000c967  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000c96c  nop
0x18000c96d  mov     r12, [r13+88h]
0x18000c974  lea     rax, [rsp+0D8h+var_60]
0x18000c979  mov     [rsp+0D8h+var_A0], rax
0x18000c97e  xorps   xmm0, xmm0
0x18000c981  movups  [rsp+0D8h+var_60], xmm0
0x18000c986  xor     eax, eax
0x18000c988  mov     [rsp+0D8h+var_50], rax
0x18000c990  mov     [rsp+0D8h+var_48], rax
0x18000c998  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c99c  inc     r8
0x18000c99f  cmp     [rsi+r8*2], ax
0x18000c9a4  jnz     short loc_18000C99C
0x18000c9a6  mov     rdx, rsi
0x18000c9a9  lea     rcx, [rsp+0D8h+var_60]
0x18000c9ae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000c9b3  nop
0x18000c9b4  mov     r15d, [rdi+r15*8]
0x18000c9b8  lea     rdx, [rsp+0D8h+var_90]
0x18000c9bd  lea     rcx, [rsp+0D8h+var_78]
0x18000c9c2  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000c9c7  nop
0x18000c9c8  mov     ecx, [rsp+0D8h+var_A8]
0x18000c9cc  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x18000c9d0  lea     r9, [rsp+0D8h+var_60]
0x18000c9d5  mov     r8d, r15d
0x18000c9d8  mov     rdx, rax
0x18000c9db  mov     rcx, r12
0x18000c9de  call    ?AddCertificate@CertificateCache@Client@HostGuardian@Microsoft@@QEAAXV?$vector@EV?$allocator@E@std@@@std@@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@W4ShsAttestationFlag@@@Z; Microsoft::HostGuardian::Client::CertificateCache::AddCertificate(std::vector<uchar>,AttestationResultType,std::wstring,ShsAttestationFlag)
0x18000c9e3  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 2
0x18000c9ea  jz      short loc_18000CA24
0x18000c9ec  lea     rax, aAddedCertifica; "Added certificate to cache"
0x18000c9f3  mov     [rsp+0D8h+var_50], rax
0x18000c9fb  mov     [rsp+0D8h+var_48], 36h ; '6'
0x18000ca07  lea     rax, [rsp+0D8h+var_60]
0x18000ca0c  mov     [rsp+0D8h+var_B8], rax
0x18000ca11  mov     r9d, 2
0x18000ca17  lea     rdx, ServiceDebugInformational
0x18000ca1e  call    McGenEventWrite_EventWriteTransfer
0x18000ca23  nop
0x18000ca24  lea     rcx, [rsp+0D8h+var_90]
0x18000ca29  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000ca2e  inc     ebx
0x18000ca30  jmp     loc_18000C946
0x18000ca35  xor     eax, eax
0x18000ca37  jmp     short loc_18000CA44
0x18000ca39  mov     eax, 80070057h
0x18000ca3e  jmp     short loc_18000CA44
0x18000ca40  mov     eax, [rsp+0D8h+var_A8]
0x18000ca44  mov     rcx, [rsp+0D8h+var_40]
0x18000ca4c  xor     rcx, rsp; StackCookie
0x18000ca4f  call    __security_check_cookie
0x18000ca54  add     rsp, 0A0h
0x18000ca5b  pop     r15
0x18000ca5d  pop     r14
0x18000ca5f  pop     r13
0x18000ca61  pop     r12
0x18000ca63  pop     rdi
0x18000ca64  pop     rsi
0x18000ca65  pop     rbx
0x18000ca66  retn
```
