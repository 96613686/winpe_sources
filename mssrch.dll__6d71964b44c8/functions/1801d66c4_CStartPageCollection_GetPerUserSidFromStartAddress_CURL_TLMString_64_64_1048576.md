# CStartPageCollection::GetPerUserSidFromStartAddress(CURL *,TLMString<64,64,1048576> &)

- ea: `0x1801d66c4`
- end: `0x1801d687f`
- name: `?GetPerUserSidFromStartAddress@CStartPageCollection@@QEAAJPEAVCURL@@AEAV?$TLMString@$0EA@$0EA@$0BAAAAA@@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004fd84`
- `0x1801d6eec`

## callees

- `0x180027190`
- `0x18002751c`
- `0x18002dc6c`
- `0x18008011c`
- `0x1800a1684`
- `0x1800a1700`
- `0x1801244c0`
- `0x18012540e`
- `0x1801ba77c`
- `0x1801d66c4`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d677a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d677a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d67c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d67c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801d67df`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801d67df`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801d67a2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801d67a2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801d6770`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801d6770`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStartPageCollection::GetPerUserSidFromStartAddress(__int64 a1, __int64 a2, __int64 a3)
{
  signed int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rax
  signed int LastError; // eax
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v13; // [rsp+3Ch] [rbp-C4h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  _BYTE v15[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[528]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  CURL::GetHost(a2, &v12);
  if ( v13 > 2 )
  {
    v7 = *(_QWORD *)(v14 + 8);
    if ( *(_WORD *)(v7 + 2LL * v12) == 123 && *(_WORD *)(v7 + 2LL * (v13 + v12 - 1)) == 125 )
    {
      v8 = CLMSubStr::Mid(&v12, v15, 1, v13 - 2);
      CLMString::operator=(a3, v8);
      Sid = 0;
      if ( ConvertStringSidToSidW(*(LPCWSTR *)(a3 + 8), &Sid) )
        goto LABEL_21;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      CLMString::Truncate((CLMString *)a3, 0);
      if ( v6 >= 0 )
      {
LABEL_21:
        if ( !IsValidSid(Sid) )
        {
          v6 = -2147023559;
          CLMString::Truncate((CLMString *)a3, 0);
        }
      }
      if ( Sid )
        LocalFree(Sid);
    }
  }
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && !*(_DWORD *)(a3 + 20) )
  {
    Sid = 0;
    memset_0(v16, 0, 0x208u);
    if ( (int)Microsoft::WRL::ComPtr<IUrlConverter>::As<IVolumePathConverter>(a1 + 416, &Sid) >= 0
      && (*(int (__fastcall **)(PSID, _QWORD, _BYTE *, __int64))(*(_QWORD *)Sid + 48LL))(
           Sid,
           *(_QWORD *)(a2 + 32),
           v16,
           260) >= 0 )
    {
      CLMString::operator=(a3, v16);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Sid);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801d66c4  push    rbp
0x1801d66c6  push    rbx
0x1801d66c7  push    rsi
0x1801d66c8  push    rdi
0x1801d66c9  push    r14
0x1801d66cb  lea     rbp, [rsp-180h]
0x1801d66d3  sub     rsp, 280h
0x1801d66da  mov     rax, cs:__security_cookie
0x1801d66e1  xor     rax, rsp
0x1801d66e4  mov     [rbp+1A0h+var_30], rax
0x1801d66eb  mov     rdi, r8
0x1801d66ee  mov     rsi, rdx
0x1801d66f1  mov     r14, rcx
0x1801d66f4  xor     ebx, ebx
0x1801d66f6  lea     rdx, [rsp+2A0h+var_268]
0x1801d66fb  mov     rcx, rsi
0x1801d66fe  call    ?GetHost@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetHost(void)
0x1801d6703  mov     r9d, [rsp+2A0h+var_264]
0x1801d6708  cmp     r9d, 2
0x1801d670c  jbe     loc_1801D67CB
0x1801d6712  mov     rax, [rsp+2A0h+var_260]
0x1801d6717  mov     rdx, [rax+8]
0x1801d671b  mov     ecx, [rsp+2A0h+var_268]
0x1801d671f  lea     r8d, [rbx+7Bh]
0x1801d6723  cmp     r8w, [rdx+rcx*2]
0x1801d6728  jnz     loc_1801D67CB
0x1801d672e  dec     ecx
0x1801d6730  add     ecx, r9d
0x1801d6733  lea     eax, [rbx+7Dh]
0x1801d6736  cmp     ax, [rdx+rcx*2]
0x1801d673a  jnz     loc_1801D67CB
0x1801d6740  add     r9d, 0FFFFFFFEh
0x1801d6744  lea     r8d, [rbx+1]
0x1801d6748  lea     rdx, [rsp+2A0h+var_258]
0x1801d674d  lea     rcx, [rsp+2A0h+var_268]
0x1801d6752  call    ?Mid@CLMSubStr@@QEBA?AV1@II@Z; CLMSubStr::Mid(uint,uint)
0x1801d6757  mov     rdx, rax
0x1801d675a  mov     rcx, rdi
0x1801d675d  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x1801d6762  mov     [rsp+2A0h+Sid], rbx
0x1801d6767  lea     rdx, [rsp+2A0h+Sid]; Sid
0x1801d676c  mov     rcx, [rdi+8]; StringSid
0x1801d6770  call    cs:__imp_ConvertStringSidToSidW
0x1801d6776  test    eax, eax
0x1801d6778  jnz     short loc_1801D679D
0x1801d677a  call    cs:__imp_GetLastError
0x1801d6780  mov     ebx, eax
0x1801d6782  test    eax, eax
0x1801d6784  jle     short loc_1801D678F
0x1801d6786  movzx   ebx, ax
0x1801d6789  or      ebx, 80070000h
0x1801d678f  xor     edx, edx; unsigned int
0x1801d6791  mov     rcx, rdi; this
0x1801d6794  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x1801d6799  test    ebx, ebx
0x1801d679b  js      short loc_1801D67BB
0x1801d679d  mov     rcx, [rsp+2A0h+Sid]; pSid
0x1801d67a2  call    cs:__imp_IsValidSid
0x1801d67a8  test    eax, eax
0x1801d67aa  jnz     short loc_1801D67BB
0x1801d67ac  mov     ebx, 80070539h
0x1801d67b1  xor     edx, edx; unsigned int
0x1801d67b3  mov     rcx, rdi; this
0x1801d67b6  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x1801d67bb  mov     rcx, [rsp+2A0h+Sid]; hMem
0x1801d67c0  test    rcx, rcx
0x1801d67c3  jz      short loc_1801D67CB
0x1801d67c5  call    cs:__imp_LocalFree
0x1801d67cb  xor     r9d, r9d; Context
0x1801d67ce  xor     r8d, r8d; Parameter
0x1801d67d1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801d67d8  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801d67df  call    cs:__imp_InitOnceExecuteOnce
0x1801d67e5  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, 0; bool g_isPerUserCatalogEnabled
0x1801d67ec  jz      short loc_1801D6860
0x1801d67ee  cmp     dword ptr [rdi+14h], 0
0x1801d67f2  jnz     short loc_1801D6860
0x1801d67f4  mov     [rsp+2A0h+Sid], 0
0x1801d67fd  xor     edx, edx; Val
0x1801d67ff  mov     r8d, 208h; Size
0x1801d6805  lea     rcx, [rsp+2A0h+var_240]; void *
0x1801d680a  call    memset_0
0x1801d680f  lea     rcx, [r14+1A0h]
0x1801d6816  lea     rdx, [rsp+2A0h+Sid]
0x1801d681b  call    ??$As@UIVolumePathConverter@@@?$ComPtr@UIUrlConverter@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVolumePathConverter@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUrlConverter>::As<IVolumePathConverter>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IVolumePathConverter>>)
0x1801d6820  test    eax, eax
0x1801d6822  js      short loc_1801D6856
0x1801d6824  mov     rcx, [rsp+2A0h+Sid]
0x1801d6829  mov     rax, [rcx]
0x1801d682c  mov     r9d, 104h
0x1801d6832  lea     r8, [rsp+2A0h+var_240]
0x1801d6837  mov     rdx, [rsi+20h]
0x1801d683b  mov     rax, [rax+30h]
0x1801d683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6844  test    eax, eax
0x1801d6846  js      short loc_1801D6856
0x1801d6848  lea     rdx, [rsp+2A0h+var_240]
0x1801d684d  mov     rcx, rdi
0x1801d6850  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801d6855  nop
0x1801d6856  lea     rcx, [rsp+2A0h+Sid]
0x1801d685b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801d6860  mov     eax, ebx
0x1801d6862  mov     rcx, [rbp+1A0h+var_30]
0x1801d6869  xor     rcx, rsp; StackCookie
0x1801d686c  call    __security_check_cookie
0x1801d6871  add     rsp, 280h
0x1801d6878  pop     r14
0x1801d687a  pop     rdi
0x1801d687b  pop     rsi
0x1801d687c  pop     rbx
0x1801d687d  pop     rbp
0x1801d687e  retn
```
