# NgcUtils::NgcKeyName::BuildNgcKeyNameString(std::vector<uchar,std::allocator<uchar>> const &,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180014790`
- end: `0x180014b53`
- name: `?BuildNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@22PEAV64@@Z`
- size: `963`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fdc0`
- `0x180010050`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000ce74`
- `0x180012e40`
- `0x180013834`
- `0x180014768`
- `0x180014790`
- `0x180014c24`
- `0x180014da8`
- `0x180014e34`
- `0x180014eb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001484b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001484b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800147d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800147d6`
- `RPCRT4!UuidToStringW` at `0x18001487e`
- `RPCRT4!UuidToStringW` at `0x18001487e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::NgcKeyName::BuildNgcKeyNameString(
        PSID *a1,
        const UUID *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned __int8 *v11; // rdx
  RPC_STATUS v13; // eax
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int128 *p_Src; // rcx
  unsigned __int64 v23; // rdx
  __int128 *v24; // rcx
  unsigned __int64 v25; // rdx
  __int128 *v26; // rcx
  unsigned __int64 v27; // rdx
  __int128 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // [rsp+30h] [rbp-79h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-71h] BYREF
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-69h] BYREF
  RPC_WSTR *p_StringUuid; // [rsp+48h] [rbp-61h] BYREF
  __int16 v38; // [rsp+50h] [rbp-59h]
  __int128 Src; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int64 v40; // [rsp+68h] [rbp-41h]
  unsigned __int64 v41; // [rsp+70h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v42[2]; // [rsp+78h] [rbp-31h] BYREF
  int *v43; // [rsp+98h] [rbp-11h]
  __int64 v44; // [rsp+A0h] [rbp-9h]

  StringSid = 0;
  if ( !ConvertSidToStringSidW(*a1, &StringSid) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_7;
    v11 = (unsigned __int8 *)byte_180068721;
LABEL_6:
    v43 = &v34;
    v44 = 4;
    v34 = v10;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, v11, 0, 0, 3u, v42);
LABEL_7:
    if ( StringSid )
      LocalFree(StringSid);
    return v10;
  }
  StringUuid = 0;
  v13 = UuidToStringW(a2, &StringUuid);
  v10 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_7;
    v11 = (unsigned __int8 *)word_1800686E2;
    goto LABEL_6;
  }
  p_StringUuid = &StringUuid;
  v38 = 256;
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( StringSid[v15] );
  v16 = -1;
  do
    ++v16;
  while ( StringUuid[v16] );
  v17 = v16 + v15;
  if ( v16 + v15 < v15
    || (v18 = v17 + *(_QWORD *)(a3 + 16), v18 < v17)
    || (v19 = v18 + *(_QWORD *)(a4 + 16), v19 < v18)
    || (v20 = v19 + *(_QWORD *)(a5 + 16), v20 < v19)
    || v20 + 4 < v20 )
  {
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  }
  Src = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(Src) = 0;
  std::wstring::reserve(&Src);
  std::wstring::append(&Src, StringSid);
  v21 = v40;
  p_Src = &Src;
  if ( v40 >= v41 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
  }
  else
  {
    ++v40;
    if ( v41 > 7 )
      p_Src = (__int128 *)Src;
    *(_DWORD *)((char *)p_Src + 2 * v21) = 47;
  }
  std::wstring::append(&Src, StringUuid);
  v23 = v40;
  v24 = &Src;
  if ( v40 >= v41 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
  }
  else
  {
    ++v40;
    if ( v41 > 7 )
      v24 = (__int128 *)Src;
    *(_DWORD *)((char *)v24 + 2 * v23) = 47;
  }
  std::wstring::append(&Src);
  v25 = v40;
  v26 = &Src;
  if ( v40 >= v41 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
  }
  else
  {
    ++v40;
    if ( v41 > 7 )
      v26 = (__int128 *)Src;
    *(_DWORD *)((char *)v26 + 2 * v25) = 47;
  }
  std::wstring::append(&Src);
  v27 = v40;
  v28 = &Src;
  if ( v40 >= v41 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
  }
  else
  {
    ++v40;
    if ( v41 > 7 )
      v28 = (__int128 *)Src;
    *(_DWORD *)((char *)v28 + 2 * v27) = 47;
  }
  std::wstring::append(&Src);
  v31 = -1;
  do
    ++v31;
  while ( StringSid[v31] );
  if ( v31 > 0xFF )
    goto LABEL_56;
  do
    ++v14;
  while ( StringUuid[v14] );
  if ( v14 > 0x24
    || *(_QWORD *)(a3 + 16) > 0x104u
    || *(_QWORD *)(a4 + 16) > 0x104u
    || *(_QWORD *)(a5 + 16) > 0x104u
    || v40 > 0x433 )
  {
LABEL_56:
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v34 = -2147024809;
      v43 = &v34;
      v44 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)&unk_1800686A8, 0, 0, 3u, v42);
    }
    std::wstring::~wstring(&Src, v29, v30);
    wil::details::ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65___::operator()(&p_StringUuid);
    if ( StringSid )
      LocalFree(StringSid);
    return 2147942487LL;
  }
  else
  {
    std::wstring::operator=(a6, &Src);
    std::wstring::~wstring(&Src, v32, v33);
    wil::details::ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65___::operator()(&p_StringUuid);
    if ( StringSid )
      LocalFree(StringSid);
    return 0;
  }
}

```

## disassembly

```asm
0x180014790  push    rbp
0x180014792  push    rbx
0x180014793  push    rsi
0x180014794  push    rdi
0x180014795  push    r12
0x180014797  push    r13
0x180014799  push    r14
0x18001479b  push    r15
0x18001479d  lea     rbp, [rsp-0Fh]
0x1800147a2  sub     rsp, 0B8h
0x1800147a9  mov     rax, cs:__security_cookie
0x1800147b0  xor     rax, rsp
0x1800147b3  mov     [rbp+47h+var_48], rax
0x1800147b7  mov     r14, r9
0x1800147ba  mov     r15, r8
0x1800147bd  mov     rbx, rdx
0x1800147c0  mov     rsi, [rbp+47h+arg_20]
0x1800147c4  mov     r12, [rbp+47h+arg_28]
0x1800147c8  xor     r13d, r13d
0x1800147cb  mov     [rbp+47h+StringSid], r13
0x1800147cf  lea     rdx, [rbp+47h+StringSid]; StringSid
0x1800147d3  mov     rcx, [rcx]; Sid
0x1800147d6  call    cs:__imp_ConvertSidToStringSidW
0x1800147dc  test    eax, eax
0x1800147de  jnz     loc_180014873
0x1800147e4  call    cs:__imp_GetLastError
0x1800147ea  mov     ebx, eax
0x1800147ec  test    eax, eax
0x1800147ee  jle     short loc_1800147F9
0x1800147f0  movzx   ebx, ax
0x1800147f3  or      ebx, 80070000h
0x1800147f9  mov     eax, cs:dword_180075000
0x1800147ff  cmp     eax, 2
0x180014802  jbe     short loc_180014842
0x180014804  lea     rdx, byte_180068721
0x18001480b  lea     rax, [rbp+47h+var_C0]
0x18001480f  mov     [rbp+47h+var_58], rax
0x180014813  lea     rax, [rbp+47h+var_78]
0x180014817  xor     r9d, r9d
0x18001481a  mov     [rsp+0F0h+var_C8], rax
0x18001481f  xor     r8d, r8d
0x180014822  mov     [rsp+0F0h+var_D0], 3
0x18001482a  mov     [rbp+47h+var_50], 4
0x180014832  mov     [rbp+47h+var_C0], ebx
0x180014835  lea     rcx, dword_180075000
0x18001483c  call    _tlgWriteTransfer_EventWriteTransfer
0x180014841  nop
0x180014842  mov     rcx, [rbp+47h+StringSid]; hMem
0x180014846  test    rcx, rcx
0x180014849  jz      short loc_180014851
0x18001484b  call    cs:__imp_LocalFree
0x180014851  mov     eax, ebx
0x180014853  mov     rcx, [rbp+47h+var_48]
0x180014857  xor     rcx, rsp; StackCookie
0x18001485a  call    __security_check_cookie
0x18001485f  add     rsp, 0B8h
0x180014866  pop     r15
0x180014868  pop     r14
0x18001486a  pop     r13
0x18001486c  pop     r12
0x18001486e  pop     rdi
0x18001486f  pop     rsi
0x180014870  pop     rbx
0x180014871  pop     rbp
0x180014872  retn
0x180014873  mov     [rbp+47h+StringUuid], r13
0x180014877  lea     rdx, [rbp+47h+StringUuid]; StringUuid
0x18001487b  mov     rcx, rbx; Uuid
0x18001487e  call    cs:__imp_UuidToStringW
0x180014884  mov     ebx, eax
0x180014886  test    eax, eax
0x180014888  jz      short loc_1800148AC
0x18001488a  jle     short loc_180014895
0x18001488c  movzx   ebx, ax
0x18001488f  or      ebx, 80070000h
0x180014895  mov     eax, cs:dword_180075000
0x18001489b  cmp     eax, 2
0x18001489e  jbe     short loc_180014842
0x1800148a0  lea     rdx, word_1800686E2
0x1800148a7  jmp     loc_18001480B
0x1800148ac  lea     rax, [rbp+47h+StringUuid]
0x1800148b0  mov     [rbp+47h+var_A8], rax
0x1800148b4  mov     [rbp+47h+var_A0], 100h
0x1800148ba  mov     rcx, [rbp+47h+StringSid]
0x1800148be  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800148c2  mov     rax, rdi
0x1800148c5  inc     rax
0x1800148c8  cmp     [rcx+rax*2], r13w
0x1800148cd  jnz     short loc_1800148C5
0x1800148cf  mov     rdx, [rbp+47h+StringUuid]
0x1800148d3  mov     rcx, rdi
0x1800148d6  inc     rcx
0x1800148d9  cmp     [rdx+rcx*2], r13w
0x1800148de  jnz     short loc_1800148D6
0x1800148e0  lea     rdx, [rcx+rax]
0x1800148e4  cmp     rdx, rax
0x1800148e7  jb      loc_180014B4D
0x1800148ed  mov     rcx, [r15+10h]
0x1800148f1  add     rcx, rdx
0x1800148f4  cmp     rcx, rdx
0x1800148f7  jb      loc_180014B4D
0x1800148fd  mov     rdx, [r14+10h]
0x180014901  add     rdx, rcx
0x180014904  cmp     rdx, rcx
0x180014907  jb      loc_180014B4D
0x18001490d  mov     rcx, [rsi+10h]
0x180014911  add     rcx, rdx
0x180014914  cmp     rcx, rdx
0x180014917  jb      loc_180014B4D
0x18001491d  lea     rdx, [rcx+4]
0x180014921  cmp     rdx, rcx
0x180014924  jb      loc_180014B4D
0x18001492a  xorps   xmm0, xmm0
0x18001492d  movups  [rbp+47h+Src], xmm0
0x180014931  mov     [rbp+47h+var_88], r13
0x180014935  mov     [rbp+47h+var_80], 7
0x18001493d  mov     word ptr [rbp+47h+Src], r13w
0x180014942  lea     rcx, [rbp+47h+Src]
0x180014946  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18001494b  mov     rdx, [rbp+47h+StringSid]; void *
0x18001494f  lea     rcx, [rbp+47h+Src]; Src
0x180014953  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180014958  mov     rdx, [rbp+47h+var_88]
0x18001495c  lea     rcx, [rbp+47h+Src]; Src
0x180014960  mov     ebx, 2Fh ; '/'
0x180014965  cmp     rdx, [rbp+47h+var_80]
0x180014969  jnb     short loc_180014982
0x18001496b  lea     rax, [rdx+1]
0x18001496f  mov     [rbp+47h+var_88], rax
0x180014973  cmp     [rbp+47h+var_80], 7
0x180014978  cmova   rcx, qword ptr [rbp+47h+Src]
0x18001497d  mov     [rcx+rdx*2], ebx
0x180014980  jmp     short loc_18001498A
0x180014982  mov     r9d, ebx
0x180014985  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18001498a  mov     rdx, [rbp+47h+StringUuid]; void *
0x18001498e  lea     rcx, [rbp+47h+Src]; Src
0x180014992  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180014997  mov     rdx, [rbp+47h+var_88]
0x18001499b  lea     rcx, [rbp+47h+Src]; Src
0x18001499f  cmp     rdx, [rbp+47h+var_80]
0x1800149a3  jnb     short loc_1800149C0
0x1800149a5  lea     rax, [rdx+1]
0x1800149a9  mov     [rbp+47h+var_88], rax
0x1800149ad  cmp     [rbp+47h+var_80], 7
0x1800149b2  cmova   rcx, qword ptr [rbp+47h+Src]
0x1800149b7  mov     dword ptr [rcx+rdx*2], 2Fh ; '/'
0x1800149be  jmp     short loc_1800149C8
0x1800149c0  mov     r9d, ebx
0x1800149c3  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800149c8  mov     rdx, r15
0x1800149cb  lea     rcx, [rbp+47h+Src]; Src
0x1800149cf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800149d4  mov     rdx, [rbp+47h+var_88]
0x1800149d8  lea     rcx, [rbp+47h+Src]; Src
0x1800149dc  cmp     rdx, [rbp+47h+var_80]
0x1800149e0  jnb     short loc_1800149FD
0x1800149e2  lea     rax, [rdx+1]
0x1800149e6  mov     [rbp+47h+var_88], rax
0x1800149ea  cmp     [rbp+47h+var_80], 7
0x1800149ef  cmova   rcx, qword ptr [rbp+47h+Src]
0x1800149f4  mov     dword ptr [rcx+rdx*2], 2Fh ; '/'
0x1800149fb  jmp     short loc_180014A05
0x1800149fd  mov     r9d, ebx
0x180014a00  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180014a05  mov     rdx, r14
0x180014a08  lea     rcx, [rbp+47h+Src]; Src
0x180014a0c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180014a11  mov     rdx, [rbp+47h+var_88]
0x180014a15  lea     rcx, [rbp+47h+Src]; Src
0x180014a19  cmp     rdx, [rbp+47h+var_80]
0x180014a1d  jnb     short loc_180014A3A
0x180014a1f  lea     rax, [rdx+1]
0x180014a23  mov     [rbp+47h+var_88], rax
0x180014a27  cmp     [rbp+47h+var_80], 7
0x180014a2c  cmova   rcx, qword ptr [rbp+47h+Src]
0x180014a31  mov     dword ptr [rcx+rdx*2], 2Fh ; '/'
0x180014a38  jmp     short loc_180014A42
0x180014a3a  mov     r9d, ebx
0x180014a3d  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180014a42  mov     rdx, rsi
0x180014a45  lea     rcx, [rbp+47h+Src]; Src
0x180014a49  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180014a4e  mov     rcx, [rbp+47h+StringSid]
0x180014a52  mov     rax, rdi
0x180014a55  inc     rax
0x180014a58  cmp     [rcx+rax*2], r13w
0x180014a5d  jnz     short loc_180014A55
0x180014a5f  cmp     rax, 0FFh
0x180014a65  ja      short loc_180014AD3
0x180014a67  mov     rax, [rbp+47h+StringUuid]
0x180014a6b  inc     rdi
0x180014a6e  cmp     [rax+rdi*2], r13w
0x180014a73  jnz     short loc_180014A6B
0x180014a75  cmp     rdi, 24h ; '$'
0x180014a79  ja      short loc_180014AD3
0x180014a7b  mov     eax, 104h
0x180014a80  cmp     [r15+10h], rax
0x180014a84  ja      short loc_180014AD3
0x180014a86  cmp     [r14+10h], rax
0x180014a8a  ja      short loc_180014AD3
0x180014a8c  cmp     [rsi+10h], rax
0x180014a90  ja      short loc_180014AD3
0x180014a92  cmp     [rbp+47h+var_88], 433h
0x180014a9a  ja      short loc_180014AD3
0x180014a9c  lea     rdx, [rbp+47h+Src]
0x180014aa0  mov     rcx, r12
0x180014aa3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014aa8  nop
0x180014aa9  lea     rcx, [rbp+47h+Src]
0x180014aad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014ab2  nop
0x180014ab3  lea     rcx, [rbp+47h+var_A8]
0x180014ab7  call    wil__details__ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65_____operator__
0x180014abc  nop
0x180014abd  mov     rcx, [rbp+47h+StringSid]; hMem
0x180014ac1  test    rcx, rcx
0x180014ac4  jz      short loc_180014ACC
0x180014ac6  call    cs:__imp_LocalFree
0x180014acc  xor     eax, eax
0x180014ace  jmp     loc_180014853
0x180014ad3  mov     eax, cs:dword_180075000
0x180014ad9  cmp     eax, 2
0x180014adc  jbe     short loc_180014B20
0x180014ade  mov     [rbp+47h+var_C0], 80070057h
0x180014ae5  lea     rax, [rbp+47h+var_C0]
0x180014ae9  mov     [rbp+47h+var_58], rax
0x180014aed  mov     [rbp+47h+var_50], 4
0x180014af5  lea     rax, [rbp+47h+var_78]
0x180014af9  mov     [rsp+0F0h+var_C8], rax
0x180014afe  mov     [rsp+0F0h+var_D0], 3
0x180014b06  xor     r9d, r9d
0x180014b09  xor     r8d, r8d
0x180014b0c  lea     rdx, unk_1800686A8
0x180014b13  lea     rcx, dword_180075000
0x180014b1a  call    _tlgWriteTransfer_EventWriteTransfer
0x180014b1f  nop
0x180014b20  lea     rcx, [rbp+47h+Src]
0x180014b24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014b29  nop
0x180014b2a  lea     rcx, [rbp+47h+var_A8]
0x180014b2e  call    wil__details__ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65_____operator__
0x180014b33  nop
0x180014b34  mov     rcx, [rbp+47h+StringSid]; hMem
0x180014b38  test    rcx, rcx
0x180014b3b  jz      short loc_180014B43
0x180014b3d  call    cs:__imp_LocalFree
0x180014b43  mov     eax, 80070057h
0x180014b48  jmp     loc_180014853
0x180014b4d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
