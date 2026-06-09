# NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SID const *,void * const)

- ea: `0x180025010`
- end: `0x180025415`
- name: `??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z`
- size: `1029`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPCWSTR StringSecurityDescriptor, PSID pSid, __int64)`
- caller_count: `20`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001a014`
- `0x180024648`
- `0x1800322f4`
- `0x18003915c`
- `0x180039790`
- `0x18003caec`
- `0x18003cd8c`
- `0x18003d13c`
- `0x1800402a8`
- `0x180040468`
- `0x180040624`
- `0x1800407e4`
- `0x1800409a0`
- `0x180040b60`
- `0x180040d20`
- `0x180040ec4`
- `0x180041068`
- `0x18004120c`
- `0x180041814`
- `0x1800419e0`

## callees

- `0x1800158e0`
- `0x18001c630`
- `0x180025010`
- `0x18002cb1c`
- `0x18002d16c`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002e850`
- `0x18002e85c`
- `0x18002f7e7`
- `0x180043a40`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180025031`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180025031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002531b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002538b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002531b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002538b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253fb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800250a7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800250a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800250b8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800250b8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025213`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025213`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002527f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002527f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::RpcClient::RpcClient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        int a5,
        LPCWSTR StringSecurityDescriptor,
        PSID pSid,
        __int64 a8)
{
  _QWORD *v9; // r14
  PSID v10; // r12
  DWORD LengthSid; // eax
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  size_t v18; // rdi
  size_t v19; // rcx
  void *v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  size_t v24; // rsi
  int v25; // eax
  LPCWSTR v26; // rdi
  DWORD v28; // ebx
  DWORD LastError; // ebx
  DWORD v30; // ebx
  signed int v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  _BYTE pExceptionObject[88]; // [rsp+30h] [rbp-58h] BYREF
  DWORD nDestinationSidLength; // [rsp+A8h] [rbp+20h] BYREF

  nDestinationSidLength = a4;
  InitializeSRWLock((PSRWLOCK)a1);
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  v9 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 3;
  *(_DWORD *)(a1 + 28) = 1;
  *(_DWORD *)(a1 + 32) = 1;
  *(_DWORD *)(a1 + 36) = a5;
  *(_QWORD *)(a1 + 40) = a8;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  *(_QWORD *)(a1 + 88) = 0;
  v10 = pSid;
  if ( !pSid )
    goto LABEL_31;
  if ( !IsValidSid(pSid) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18006E000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0) )
    {
      nDestinationSidLength = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&unk_1800639C8,
        0,
        0,
        (__int64)&nDestinationSidLength);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, LastError);
    throw (win32_exception *)pExceptionObject;
  }
  LengthSid = GetLengthSid(v10);
  nDestinationSidLength = LengthSid;
  v12 = LengthSid;
  v13 = *(_QWORD *)(a1 + 64);
  v14 = *(_QWORD *)(a1 + 56);
  v15 = v13 - v14;
  if ( LengthSid >= (unsigned __int64)(v13 - v14) )
  {
    if ( LengthSid <= v15 )
      goto LABEL_27;
    v16 = *(_QWORD *)(a1 + 72) - v14;
    if ( LengthSid <= v16 )
    {
      v24 = LengthSid - v15;
      memset_0(*(void **)(a1 + 64), 0, v24);
      *(_QWORD *)(a1 + 64) = v24 + v13;
      goto LABEL_27;
    }
    v17 = v16 >> 1;
    v18 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v16 <= 0x7FFFFFFFFFFFFFFFLL - (v16 >> 1) )
    {
      v18 = v17 + v16;
      if ( v17 + v16 < LengthSid )
        v18 = LengthSid;
      if ( !v18 )
        goto LABEL_18;
      if ( v18 < 0x1000 )
      {
        v9 = operator new(v18);
        goto LABEL_18;
      }
      v19 = v18 + 39;
      if ( v18 + 39 < v18 )
        std::_Throw_bad_array_new_length();
    }
    else
    {
      v19 = 0x8000000000000026uLL;
    }
    v20 = operator new(v19);
    if ( !v20 )
      goto LABEL_22;
    v9 = (_QWORD *)(((unsigned __int64)v20 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v9 - 1) = v20;
LABEL_18:
    memset_0((char *)v9 + v15, 0, v12 - v15);
    memmove_0(v9, *(const void **)(a1 + 56), *(_QWORD *)(a1 + 64) - *(_QWORD *)(a1 + 56));
    v21 = *(_QWORD *)(a1 + 56);
    if ( !v21 )
    {
LABEL_25:
      *(_QWORD *)(a1 + 56) = v9;
      *(_QWORD *)(a1 + 64) = (char *)v9 + v12;
      *(_QWORD *)(a1 + 72) = (char *)v9 + v18;
      goto LABEL_27;
    }
    v22 = *(_QWORD *)(a1 + 72) - v21;
    if ( v22 < 0x1000 )
    {
      v23 = *(void **)(a1 + 56);
      goto LABEL_24;
    }
    v23 = *(void **)(v21 - 8);
    if ( (unsigned __int64)(v21 - (_QWORD)v23 - 8) <= 0x1F )
    {
      v22 += 39LL;
LABEL_24:
      operator delete(v23, v22);
      goto LABEL_25;
    }
LABEL_22:
    __fastfail(5u);
  }
  *(_QWORD *)(a1 + 64) = LengthSid + v14;
LABEL_27:
  if ( !CopySid(nDestinationSidLength, *(PSID *)(a1 + 56), v10) )
  {
    v30 = GetLastError();
    if ( (unsigned int)dword_18006E000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0) )
    {
      nDestinationSidLength = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)byte_1800639F9,
        0,
        0,
        (__int64)&nDestinationSidLength);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, v30);
    throw (win32_exception *)pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 24) == 3 )
  {
    v25 = *(_DWORD *)(a1 + 28);
    if ( (v25 & 1) != 0 )
      *(_DWORD *)(a1 + 28) = v25 | 0x10;
  }
LABEL_31:
  v26 = StringSecurityDescriptor;
  if ( *((_QWORD *)StringSecurityDescriptor + 2) )
  {
    if ( *(_QWORD *)(a1 + 88) )
    {
      if ( !(**(unsigned __int8 (__fastcall ***)(__int64))(a1 + 80))(a1 + 80) )
      {
        v31 = GetLastError();
        if ( v31 > 0 )
          v31 = (unsigned __int16)v31 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
        JUMPOUT(0x180025414LL);
      }
      *(_QWORD *)(a1 + 88) = 0;
    }
    if ( *((_QWORD *)v26 + 3) > 7u )
      v26 = *(LPCWSTR *)v26;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v26, 1u, (PSECURITY_DESCRIPTOR *)(a1 + 88), 0) )
    {
      v28 = GetLastError();
      if ( (unsigned int)dword_18006E000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0) )
      {
        nDestinationSidLength = v28;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)&unk_180063988,
          0,
          0,
          (__int64)&nDestinationSidLength);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, v28);
      throw (win32_exception *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180025010  mov     [rsp+arg_8], rbx
0x180025015  mov     [rsp+nDestinationSidLength], r9d
0x18002501a  mov     [rsp+arg_0], rcx
0x18002501f  push    rbp
0x180025020  push    rsi
0x180025021  push    rdi
0x180025022  push    r12
0x180025024  push    r13
0x180025026  push    r14
0x180025028  push    r15
0x18002502a  sub     rsp, 50h
0x18002502e  mov     rbx, rcx
0x180025031  call    cs:__imp_InitializeSRWLock
0x180025037  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18002503e  mov     [rbx+8], rax
0x180025042  xor     r14d, r14d
0x180025045  mov     [rbx+10h], r14
0x180025049  mov     dword ptr [rbx+18h], 3
0x180025050  mov     dword ptr [rbx+1Ch], 1
0x180025057  mov     dword ptr [rbx+20h], 1
0x18002505e  mov     eax, [rsp+88h+arg_20]
0x180025065  mov     [rbx+24h], eax
0x180025068  mov     rax, [rsp+88h+arg_38]
0x180025070  mov     [rbx+28h], rax
0x180025074  mov     [rbx+30h], r14d
0x180025078  mov     [rbx+38h], r14
0x18002507c  mov     [rbx+40h], r14
0x180025080  mov     [rbx+48h], r14
0x180025084  lea     rax, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18002508b  mov     [rbx+50h], rax
0x18002508f  mov     [rbx+58h], r14
0x180025093  mov     r12, [rsp+88h+pSid]
0x18002509b  test    r12, r12
0x18002509e  jz      loc_180025234
0x1800250a4  mov     rcx, r12; pSid
0x1800250a7  call    cs:__imp_IsValidSid
0x1800250ad  test    eax, eax
0x1800250af  jz      loc_18002531B
0x1800250b5  mov     rcx, r12; pSid
0x1800250b8  call    cs:__imp_GetLengthSid
0x1800250be  mov     [rsp+88h+nDestinationSidLength], eax
0x1800250c5  mov     esi, eax
0x1800250c7  mov     rdi, [rbx+40h]
0x1800250cb  mov     rdx, [rbx+38h]
0x1800250cf  mov     rbp, rdi
0x1800250d2  sub     rbp, rdx
0x1800250d5  cmp     rsi, rbp
0x1800250d8  jnb     short loc_1800250E7
0x1800250da  lea     rcx, [rsi+rdx]
0x1800250de  mov     [rbx+40h], rcx
0x1800250e2  jmp     loc_180025205
0x1800250e7  jbe     loc_180025205
0x1800250ed  mov     rcx, [rbx+48h]
0x1800250f1  sub     rcx, rdx
0x1800250f4  cmp     rsi, rcx
0x1800250f7  jbe     loc_1800251ED
0x1800250fd  mov     rdx, rcx
0x180025100  shr     rdx, 1
0x180025103  mov     rdi, 7FFFFFFFFFFFFFFFh
0x18002510d  mov     rax, rdi
0x180025110  sub     rax, rdx
0x180025113  cmp     rcx, rax
0x180025116  jbe     short loc_18002513E
0x180025118  mov     rcx, 8000000000000026h; Size
0x180025122  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025127  test    rax, rax
0x18002512a  jz      loc_1800251C5
0x180025130  lea     r14, [rax+27h]
0x180025134  and     r14, 0FFFFFFFFFFFFFFE0h
0x180025138  mov     [r14-8], rax
0x18002513c  jmp     short loc_180025171
0x18002513e  lea     rdi, [rdx+rcx]
0x180025142  cmp     rdi, rsi
0x180025145  cmovb   rdi, rsi
0x180025149  test    rdi, rdi
0x18002514c  jz      short loc_180025171
0x18002514e  cmp     rdi, 1000h
0x180025155  jb      short loc_180025166
0x180025157  lea     rcx, [rdi+27h]
0x18002515b  cmp     rcx, rdi
0x18002515e  jbe     loc_180025315
0x180025164  jmp     short loc_180025122
0x180025166  mov     rcx, rdi; Size
0x180025169  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002516e  mov     r14, rax
0x180025171  mov     r8, rsi
0x180025174  sub     r8, rbp; Size
0x180025177  lea     rcx, [r14+rbp]; void *
0x18002517b  xor     edx, edx; Val
0x18002517d  call    memset_0
0x180025182  mov     rdx, [rbx+38h]; Src
0x180025186  mov     r8, [rbx+40h]
0x18002518a  sub     r8, rdx; Size
0x18002518d  mov     rcx, r14; void *
0x180025190  call    memmove_0
0x180025195  mov     rax, [rbx+38h]
0x180025199  test    rax, rax
0x18002519c  jz      short loc_1800251D4
0x18002519e  mov     rdx, [rbx+48h]
0x1800251a2  sub     rdx, rax; unsigned __int64
0x1800251a5  cmp     rdx, 1000h
0x1800251ac  jb      short loc_1800251CC
0x1800251ae  mov     rcx, [rax-8]
0x1800251b2  sub     rax, rcx
0x1800251b5  sub     rax, 8
0x1800251b9  cmp     rax, 1Fh
0x1800251bd  ja      short loc_1800251C5
0x1800251bf  add     rdx, 27h ; '''
0x1800251c3  jmp     short loc_1800251CF
0x1800251c5  mov     ecx, 5
0x1800251ca  int     29h; Win8: RtlFailFast(ecx)
0x1800251cc  mov     rcx, rax; void *
0x1800251cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800251d4  mov     [rbx+38h], r14
0x1800251d8  lea     rax, [rsi+r14]
0x1800251dc  mov     [rbx+40h], rax
0x1800251e0  lea     rax, [r14+rdi]
0x1800251e4  mov     [rbx+48h], rax
0x1800251e8  xor     r14d, r14d
0x1800251eb  jmp     short loc_180025205
0x1800251ed  sub     rsi, rbp
0x1800251f0  mov     r8, rsi; Size
0x1800251f3  xor     edx, edx; Val
0x1800251f5  mov     rcx, rdi; void *
0x1800251f8  call    memset_0
0x1800251fd  lea     rax, [rsi+rdi]
0x180025201  mov     [rbx+40h], rax
0x180025205  mov     r8, r12; pSourceSid
0x180025208  mov     rdx, [rbx+38h]; pDestinationSid
0x18002520c  mov     ecx, [rsp+88h+nDestinationSidLength]; nDestinationSidLength
0x180025213  call    cs:__imp_CopySid
0x180025219  test    eax, eax
0x18002521b  jz      loc_18002538B
0x180025221  cmp     dword ptr [rbx+18h], 3
0x180025225  jnz     short loc_180025234
0x180025227  mov     eax, [rbx+1Ch]
0x18002522a  test    al, 1
0x18002522c  jz      short loc_180025234
0x18002522e  or      eax, 10h
0x180025231  mov     [rbx+1Ch], eax
0x180025234  mov     rdi, [rsp+88h+StringSecurityDescriptor]
0x18002523c  cmp     qword ptr [rdi+10h], 0
0x180025241  jz      short loc_180025289
0x180025243  cmp     qword ptr [rbx+58h], 0
0x180025248  jz      short loc_180025266
0x18002524a  mov     rax, [rbx+50h]
0x18002524e  lea     rcx, [rbx+50h]
0x180025252  mov     rax, [rax]
0x180025255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002525a  test    al, al
0x18002525c  jz      loc_1800253FB
0x180025262  mov     [rbx+58h], r14
0x180025266  cmp     qword ptr [rdi+18h], 7
0x18002526b  jbe     short loc_180025270
0x18002526d  mov     rdi, [rdi]
0x180025270  xor     r9d, r9d; SecurityDescriptorSize
0x180025273  lea     r8, [rbx+58h]; SecurityDescriptor
0x180025277  mov     edx, 1; StringSDRevision
0x18002527c  mov     rcx, rdi; StringSecurityDescriptor
0x18002527f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180025285  test    eax, eax
0x180025287  jz      short loc_1800252A4
0x180025289  mov     rax, rbx
0x18002528c  mov     rbx, [rsp+88h+arg_8]
0x180025294  add     rsp, 50h
0x180025298  pop     r15
0x18002529a  pop     r14
0x18002529c  pop     r13
0x18002529e  pop     r12
0x1800252a0  pop     rdi
0x1800252a1  pop     rsi
0x1800252a2  pop     rbp
0x1800252a3  retn
0x1800252a4  call    cs:__imp_GetLastError
0x1800252aa  nop
0x1800252ab  mov     ebx, eax
0x1800252ad  mov     ecx, cs:dword_18006E000
0x1800252b3  cmp     ecx, 2
0x1800252b6  jbe     short loc_1800252F7
0x1800252b8  xor     edx, edx
0x1800252ba  lea     rcx, dword_18006E000
0x1800252c1  call    _tlgKeywordOn
0x1800252c6  test    al, al
0x1800252c8  jz      short loc_1800252F7
0x1800252ca  mov     [rsp+88h+nDestinationSidLength], ebx
0x1800252d1  lea     rax, [rsp+88h+nDestinationSidLength]
0x1800252d9  mov     [rsp+88h+var_68], rax
0x1800252de  xor     r9d, r9d
0x1800252e1  xor     r8d, r8d
0x1800252e4  lea     rdx, unk_180063988
0x1800252eb  lea     rcx, dword_18006E000
0x1800252f2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800252f7  mov     edx, ebx; unsigned int
0x1800252f9  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800252fe  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x180025303  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18002530a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002530f  call    _CxxThrowException_0
0x180025315  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18002531b  call    cs:__imp_GetLastError
0x180025321  mov     ebx, eax
0x180025323  mov     ecx, cs:dword_18006E000
0x180025329  cmp     ecx, 2
0x18002532c  jbe     short loc_18002536D
0x18002532e  xor     edx, edx
0x180025330  lea     rcx, dword_18006E000
0x180025337  call    _tlgKeywordOn
0x18002533c  test    al, al
0x18002533e  jz      short loc_18002536D
0x180025340  mov     [rsp+88h+nDestinationSidLength], ebx
0x180025347  lea     rax, [rsp+88h+nDestinationSidLength]
0x18002534f  mov     [rsp+88h+var_68], rax
0x180025354  xor     r9d, r9d
0x180025357  xor     r8d, r8d
0x18002535a  lea     rdx, unk_1800639C8
0x180025361  lea     rcx, dword_18006E000
0x180025368  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002536d  mov     edx, ebx; unsigned int
0x18002536f  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180025374  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x180025379  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x180025380  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180025385  call    _CxxThrowException_0
0x18002538b  call    cs:__imp_GetLastError
0x180025391  mov     ebx, eax
0x180025393  mov     ecx, cs:dword_18006E000
0x180025399  cmp     ecx, 2
0x18002539c  jbe     short loc_1800253DD
0x18002539e  xor     edx, edx
0x1800253a0  lea     rcx, dword_18006E000
0x1800253a7  call    _tlgKeywordOn
0x1800253ac  test    al, al
0x1800253ae  jz      short loc_1800253DD
0x1800253b0  mov     [rsp+88h+nDestinationSidLength], ebx
0x1800253b7  lea     rax, [rsp+88h+nDestinationSidLength]
0x1800253bf  mov     [rsp+88h+var_68], rax
0x1800253c4  xor     r9d, r9d
0x1800253c7  xor     r8d, r8d
0x1800253ca  lea     rdx, byte_1800639F9
0x1800253d1  lea     rcx, dword_18006E000
0x1800253d8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800253dd  mov     edx, ebx; unsigned int
0x1800253df  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800253e4  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x1800253e9  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x1800253f0  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800253f5  call    _CxxThrowException_0
0x1800253fb  call    cs:__imp_GetLastError
0x180025401  test    eax, eax
0x180025403  jle     short loc_18002540D
0x180025405  movzx   eax, ax
0x180025408  or      eax, 80070000h
0x18002540d  mov     ecx, eax; this
0x18002540f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
