# MsvpMapConnectedUserLogon(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180013d2c`
- end: `0x180014158`
- name: `?MsvpMapConnectedUserLogon@@YAJPEAU_UNICODE_STRING@@00@Z`
- size: `1068`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a470`

## callees

- `0x18000e090`
- `0x180013d2c`
- `0x1800205b4`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18002fb90`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180013e89`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180013e89`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013f79`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013fad`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013f79`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013fad`
- `ntdll!RtlAppendUnicodeToString` at `0x180013f95`
- `ntdll!RtlAppendUnicodeToString` at `0x180013f95`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800140a9`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800140a9`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800140b9`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800140b9`
- `SAMSRV!SamrCloseHandle` at `0x1800140cb`
- `SAMSRV!SamrCloseHandle` at `0x1800140cb`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180013f2f`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180013f2f`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x180013dbb`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x180013dbb`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByName` at `0x180013eb0`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByName` at `0x180013eb0`

## pseudocode

```c
__int64 __fastcall MsvpMapConnectedUserLogon(
        struct _UNICODE_STRING *Source,
        unsigned __int64 i,
        struct _UNICODE_STRING *a3)
{
  PCUNICODE_STRING v4; // r14
  struct _UNICODE_STRING *p_Destination; // rsi
  int IsTargetLocalhost; // edi
  int v7; // r15d
  int v8; // eax
  size_t Length; // rbx
  PWSTR Buffer; // rdx
  unsigned __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rbx
  unsigned __int16 v14; // ax
  WCHAR *v15; // rax
  WCHAR *v16; // r14
  unsigned __int64 v17; // rax
  WCHAR *v18; // rbx
  char *v19; // rcx
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+78h] [rbp-88h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Str[256]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[304]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v29; // [rsp+3D0h] [rbp+2D0h] BYREF

  v22 = 0;
  v23 = 0;
  v4 = (PCUNICODE_STRING)i;
  v21 = 0;
  p_Destination = Source;
  IsTargetLocalhost = -1073741275;
  v26 = 0;
  v25 = 0;
  Destination = 0;
  if ( (Source->Length & 1) != 0 || Source->Length > 0x200u )
    goto LABEL_42;
  if ( !NlpWorkstation || (unsigned int)GetDefaultIdentityProvider(&v26) )
    goto LABEL_43;
  v7 = 0;
  for ( i = 0; (unsigned int)i < p_Destination->Length >> 1; i = (unsigned int)(i + 1) )
  {
    if ( p_Destination->Buffer[(unsigned int)i] == 64 )
    {
      v7 = 1;
      break;
    }
  }
  if ( v4->Length )
  {
    if ( (v4->Length & 1) != 0 || v4->Length > 0x1FEu )
      goto LABEL_42;
    if ( v4->Length == 2 && *v4->Buffer == 46 )
      goto LABEL_23;
    IsTargetLocalhost = SspIsTargetLocalhost(0, v4, &v21);
    if ( IsTargetLocalhost < 0 )
      goto LABEL_43;
    v8 = v21;
    IsTargetLocalhost = -1073741275;
  }
  else
  {
    v8 = 1;
  }
  if ( !v8 )
  {
    Length = v4->Length;
    Buffer = v4->Buffer;
    v21 = 0;
    memcpy_0(Str, Buffer, Length);
    v11 = Length & 0xFFFFFFFFFFFFFFFEuLL;
    if ( v11 >= 0x200 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)Str + v11) = 0;
    if ( wcschr(Str, 0x2Eu) )
    {
      if ( v7 )
        goto LABEL_43;
      *(_DWORD *)&Destination.Length = 67239936;
      Destination.Buffer = (PWSTR)&v29;
      IsTargetLocalhost = RtlAppendUnicodeStringToString(&Destination, p_Destination);
      if ( IsTargetLocalhost < 0 )
        goto LABEL_43;
      IsTargetLocalhost = RtlAppendUnicodeToString(&Destination, L"@");
      if ( IsTargetLocalhost < 0 )
        goto LABEL_43;
      IsTargetLocalhost = RtlAppendUnicodeStringToString(&Destination, v4);
      if ( IsTargetLocalhost < 0 )
        goto LABEL_43;
      p_Destination = &Destination;
      goto LABEL_24;
    }
    v21 = 296;
    if ( (unsigned int)GetIdentityProviderInfoByName(Str, v28, &v21) || (v28[32] & 1) == 0 )
      goto LABEL_43;
  }
LABEL_23:
  if ( !v7 )
    goto LABEL_43;
LABEL_24:
  if ( NlpSamInitialized || (IsTargetLocalhost = NlSamInitialize(), IsTargetLocalhost >= 0) )
  {
    v12 = SamIGetUserLogonInformation2(NlpSamDomainHandle, 0x4000, p_Destination, 4, 1179648, 0, &v22, &v25, &v23);
    IsTargetLocalhost = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -1073741709 )
        goto LABEL_43;
      goto LABEL_28;
    }
    v13 = v22;
    if ( !*(_QWORD *)(v22 + 480) || (v14 = *(_WORD *)(v22 + 432)) == 0 || !*(_QWORD *)(v22 + 440) )
    {
LABEL_28:
      IsTargetLocalhost = -1073741275;
      goto LABEL_43;
    }
    if ( v14 <= 0x1FEu )
    {
      a3->MaximumLength = p_Destination->Length + v14 + 4;
      v15 = (WCHAR *)((__int64 (*)(void))qword_180088390)();
      v16 = v15;
      if ( v15 )
      {
        a3->Buffer = v15;
        memcpy_0(v15, *(const void **)(v13 + 440), *(unsigned __int16 *)(v13 + 432));
        v17 = (unsigned __int64)*(unsigned __int16 *)(v13 + 432) >> 1;
        v16[v17] = 92;
        v18 = &v16[v17 + 1];
        memcpy_0(v18, p_Destination->Buffer, p_Destination->Length);
        v19 = (char *)&v18[(unsigned __int64)p_Destination->Length >> 1];
        *(_WORD *)v19 = 0;
        a3->Length = 2 * ((__int64)(unsigned int)((_DWORD)v19 - LODWORD(a3->Buffer)) >> 1);
      }
      else
      {
        a3->MaximumLength = 0;
        IsTargetLocalhost = -1073741670;
      }
      goto LABEL_43;
    }
LABEL_42:
    IsTargetLocalhost = -1073741811;
  }
LABEL_43:
  SamIFreeSidAndAttributesList(&v25, i);
  if ( v22 )
    SamIFree_UserInternal6Information(v22);
  if ( v23 )
    SamrCloseHandle(&v23);
  if ( IsTargetLocalhost < 0 )
  {
    if ( a3->Buffer )
    {
      ((void (*)(void))qword_180088398)();
      *a3 = 0;
    }
    if ( IsTargetLocalhost != -1073741275
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
        (unsigned int)IsTargetLocalhost);
    }
  }
  return (unsigned int)IsTargetLocalhost;
}

```

## disassembly

```asm
0x180013d2c  mov     [rsp-8+arg_18], rbx
0x180013d31  push    rbp
0x180013d32  push    rsi
0x180013d33  push    rdi
0x180013d34  push    r12
0x180013d36  push    r13
0x180013d38  push    r14
0x180013d3a  push    r15
0x180013d3c  lea     rbp, [rsp-6F0h]
0x180013d44  sub     rsp, 7F0h
0x180013d4b  mov     rax, cs:__security_cookie
0x180013d52  xor     rax, rsp
0x180013d55  mov     [rbp+720h+var_40], rax
0x180013d5c  xor     r13d, r13d
0x180013d5f  xorps   xmm0, xmm0
0x180013d62  xorps   xmm1, xmm1
0x180013d65  mov     [rsp+820h+var_7C8], r13
0x180013d6a  mov     r12, r8
0x180013d6d  mov     [rsp+820h+var_7C0], r13
0x180013d72  mov     r14, rdx
0x180013d75  mov     [rsp+820h+var_7D0], r13d
0x180013d7a  lea     ebx, [r13+1]
0x180013d7e  mov     rsi, rcx
0x180013d81  mov     edi, 0C0000225h
0x180013d86  movups  [rbp+720h+var_798], xmm0
0x180013d8a  movups  [rsp+820h+var_7A8], xmm0
0x180013d8f  movups  xmmword ptr [rsp+820h+Destination.Length], xmm1
0x180013d94  test    [rcx], bl
0x180013d96  jnz     loc_18001409F
0x180013d9c  mov     eax, 200h
0x180013da1  cmp     [rcx], ax
0x180013da4  ja      loc_18001409F
0x180013daa  cmp     cs:NlpWorkstation, r13b
0x180013db1  jz      loc_1800140A4
0x180013db7  lea     rcx, [rbp+720h+var_798]
0x180013dbb  call    cs:__imp_GetDefaultIdentityProvider
0x180013dc1  test    eax, eax
0x180013dc3  jnz     loc_1800140A4
0x180013dc9  movzx   r8d, word ptr [rsi]
0x180013dcd  mov     r15d, r13d
0x180013dd0  shr     r8d, 1
0x180013dd3  mov     edx, r13d
0x180013dd6  cmp     edx, r8d
0x180013dd9  jnb     short loc_180013DEF
0x180013ddb  mov     rax, [rsi+8]
0x180013ddf  mov     ecx, edx
0x180013de1  cmp     word ptr [rax+rcx*2], 40h ; '@'
0x180013de6  jz      short loc_180013DEC
0x180013de8  add     edx, ebx
0x180013dea  jmp     short loc_180013DD6
0x180013dec  mov     r15d, ebx
0x180013def  mov     eax, 1FEh
0x180013df4  mov     ecx, 2Eh ; '.'
0x180013df9  cmp     [r14], r13w
0x180013dfd  jz      short loc_180013E4A
0x180013dff  test    [r14], bl
0x180013e02  jnz     loc_18001409F
0x180013e08  cmp     [r14], ax
0x180013e0c  ja      loc_18001409F
0x180013e12  cmp     word ptr [r14], 2
0x180013e17  jnz     short loc_180013E26
0x180013e19  mov     rax, [r14+8]
0x180013e1d  cmp     [rax], cx
0x180013e20  jz      loc_180013ECB
0x180013e26  lea     r8, [rsp+820h+var_7D0]
0x180013e2b  mov     rdx, r14
0x180013e2e  xor     ecx, ecx
0x180013e30  call    SspIsTargetLocalhost
0x180013e35  mov     edi, eax
0x180013e37  test    eax, eax
0x180013e39  js      loc_1800140A4
0x180013e3f  mov     eax, [rsp+820h+var_7D0]
0x180013e43  mov     edi, 0C0000225h
0x180013e48  jmp     short loc_180013E4C
0x180013e4a  mov     eax, ebx
0x180013e4c  test    eax, eax
0x180013e4e  jnz     short loc_180013ECB
0x180013e50  movzx   ebx, word ptr [r14]
0x180013e54  lea     rcx, [rbp+720h+Str]; void *
0x180013e58  mov     rdx, [r14+8]; Src
0x180013e5c  mov     r8d, ebx; Size
0x180013e5f  mov     [rsp+820h+var_7D0], r13d
0x180013e64  call    memcpy_0
0x180013e69  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180013e6d  cmp     rbx, 200h
0x180013e74  jnb     loc_180013FC7
0x180013e7a  mov     edx, 2Eh ; '.'; Ch
0x180013e7f  mov     [rbp+rbx+720h+Str], r13w
0x180013e85  lea     rcx, [rbp+720h+Str]; Str
0x180013e89  call    cs:__imp_wcschr
0x180013e8f  test    rax, rax
0x180013e92  jnz     loc_180013F54
0x180013e98  lea     r8, [rsp+820h+var_7D0]
0x180013e9d  mov     [rsp+820h+var_7D0], 128h
0x180013ea5  lea     rdx, [rbp+720h+var_580]
0x180013eac  lea     rcx, [rbp+720h+Str]
0x180013eb0  call    cs:__imp_GetIdentityProviderInfoByName
0x180013eb6  test    eax, eax
0x180013eb8  jnz     loc_1800140A4
0x180013ebe  test    [rbp+720h+var_560], 1
0x180013ec5  jz      loc_1800140A4
0x180013ecb  test    r15d, r15d
0x180013ece  jz      loc_1800140A4
0x180013ed4  cmp     cs:NlpSamInitialized, r13b
0x180013edb  jnz     short loc_180013EEC
0x180013edd  call    NlSamInitialize
0x180013ee2  mov     edi, eax
0x180013ee4  test    eax, eax
0x180013ee6  js      loc_1800140A4
0x180013eec  mov     rcx, cs:NlpSamDomainHandle
0x180013ef3  lea     rax, [rsp+820h+var_7C0]
0x180013ef8  mov     [rsp+820h+var_7E0], rax
0x180013efd  mov     r14d, 4
0x180013f03  lea     rax, [rsp+820h+var_7A8]
0x180013f08  mov     r9d, r14d
0x180013f0b  mov     [rsp+820h+var_7E8], rax
0x180013f10  mov     r8, rsi
0x180013f13  lea     rax, [rsp+820h+var_7C8]
0x180013f18  mov     edx, 4000h
0x180013f1d  mov     [rsp+820h+var_7F0], rax
0x180013f22  mov     [rsp+820h+var_7F8], r13
0x180013f27  mov     [rsp+820h+var_800], 120000h
0x180013f2f  call    cs:__imp_SamIGetUserLogonInformation2
0x180013f35  mov     edi, eax
0x180013f37  test    eax, eax
0x180013f39  jns     loc_180013FCD
0x180013f3f  cmp     eax, 0C0000073h
0x180013f44  jnz     loc_1800140A4
0x180013f4a  mov     edi, 0C0000225h
0x180013f4f  jmp     loc_1800140A4
0x180013f54  test    r15d, r15d
0x180013f57  jnz     loc_1800140A4
0x180013f5d  lea     rax, [rbp+720h+var_450]
0x180013f64  mov     dword ptr [rsp+820h+Destination.Length], 4020000h
0x180013f6c  mov     rdx, rsi; Source
0x180013f6f  mov     [rsp+820h+Destination.Buffer], rax
0x180013f74  lea     rcx, [rsp+820h+Destination]; Destination
0x180013f79  call    cs:__imp_RtlAppendUnicodeStringToString
0x180013f7f  mov     edi, eax
0x180013f81  test    eax, eax
0x180013f83  js      loc_1800140A4
0x180013f89  lea     rdx, Source; "@"
0x180013f90  lea     rcx, [rsp+820h+Destination]; Destination
0x180013f95  call    cs:__imp_RtlAppendUnicodeToString
0x180013f9b  mov     edi, eax
0x180013f9d  test    eax, eax
0x180013f9f  js      loc_1800140A4
0x180013fa5  mov     rdx, r14; Source
0x180013fa8  lea     rcx, [rsp+820h+Destination]; Destination
0x180013fad  call    cs:__imp_RtlAppendUnicodeStringToString
0x180013fb3  mov     edi, eax
0x180013fb5  test    eax, eax
0x180013fb7  js      loc_1800140A4
0x180013fbd  lea     rsi, [rsp+820h+Destination]
0x180013fc2  jmp     loc_180013ED4
0x180013fc7  call    __report_rangecheckfailure
0x180013fcd  mov     rbx, [rsp+820h+var_7C8]
0x180013fd2  cmp     [rbx+1E0h], r13
0x180013fd9  jz      loc_180013F4A
0x180013fdf  movzx   eax, word ptr [rbx+1B0h]
0x180013fe6  test    ax, ax
0x180013fe9  jz      loc_180013F4A
0x180013fef  cmp     [rbx+1B8h], r13
0x180013ff6  jz      loc_180013F4A
0x180013ffc  mov     ecx, 1FEh
0x180014001  cmp     ax, cx
0x180014004  ja      loc_18001409F
0x18001400a  add     ax, [rsi]
0x18001400d  add     ax, r14w
0x180014011  movzx   ecx, ax
0x180014014  mov     [r12+2], cx
0x18001401a  mov     rax, cs:qword_180088390
0x180014021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014026  mov     r14, rax
0x180014029  test    rax, rax
0x18001402c  jnz     short loc_18001403B
0x18001402e  mov     [r12+2], r13w
0x180014034  mov     edi, 0C000009Ah
0x180014039  jmp     short loc_1800140A4
0x18001403b  mov     [r12+8], r14
0x180014040  mov     rcx, r14; void *
0x180014043  movzx   r8d, word ptr [rbx+1B0h]; Size
0x18001404b  mov     rdx, [rbx+1B8h]; Src
0x180014052  call    memcpy_0
0x180014057  movzx   eax, word ptr [rbx+1B0h]
0x18001405e  shr     rax, 1
0x180014061  mov     word ptr [r14+rax*2], 5Ch ; '\'
0x180014068  inc     rax
0x18001406b  movzx   r8d, word ptr [rsi]; Size
0x18001406f  mov     rdx, [rsi+8]; Src
0x180014073  lea     rbx, [r14+rax*2]
0x180014077  mov     rcx, rbx; void *
0x18001407a  call    memcpy_0
0x18001407f  movzx   eax, word ptr [rsi]
0x180014082  shr     rax, 1
0x180014085  lea     rcx, [rbx+rax*2]
0x180014089  mov     [rcx], r13w
0x18001408d  sub     ecx, [r12+8]
0x180014092  sar     rcx, 1
0x180014095  add     cx, cx
0x180014098  mov     [r12], cx
0x18001409d  jmp     short loc_1800140A4
0x18001409f  mov     edi, 0C000000Dh
0x1800140a4  lea     rcx, [rsp+820h+var_7A8]
0x1800140a9  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800140af  mov     rcx, [rsp+820h+var_7C8]
0x1800140b4  test    rcx, rcx
0x1800140b7  jz      short loc_1800140BF
0x1800140b9  call    cs:__imp_SamIFree_UserInternal6Information
0x1800140bf  cmp     [rsp+820h+var_7C0], r13
0x1800140c4  jz      short loc_1800140D1
0x1800140c6  lea     rcx, [rsp+820h+var_7C0]
0x1800140cb  call    cs:__imp_SamrCloseHandle
0x1800140d1  test    edi, edi
0x1800140d3  jns     short loc_18001412C
0x1800140d5  mov     rcx, [r12+8]
0x1800140da  test    rcx, rcx
0x1800140dd  jz      short loc_1800140F3
0x1800140df  mov     rax, cs:qword_180088398
0x1800140e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140eb  xorps   xmm0, xmm0
0x1800140ee  movups  xmmword ptr [r12], xmm0
0x1800140f3  cmp     edi, 0C0000225h
0x1800140f9  jz      short loc_18001412C
0x1800140fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014102  lea     rax, WPP_GLOBAL_Control
0x180014109  cmp     rcx, rax
0x18001410c  jz      short loc_18001412C
0x18001410e  test    byte ptr [rcx+1Ch], 2
0x180014112  jz      short loc_18001412C
0x180014114  mov     rcx, [rcx+10h]
0x180014118  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18001411f  mov     edx, 8Eh
0x180014124  mov     r9d, edi
0x180014127  call    WPP_SF_d
0x18001412c  mov     eax, edi
0x18001412e  mov     rcx, [rbp+720h+var_40]
0x180014135  xor     rcx, rsp; StackCookie
0x180014138  call    __security_check_cookie
0x18001413d  mov     rbx, [rsp+820h+arg_18]
0x180014145  add     rsp, 7F0h
0x18001414c  pop     r15
0x18001414e  pop     r14
0x180014150  pop     r13
0x180014152  pop     r12
0x180014154  pop     rdi
0x180014155  pop     rsi
0x180014156  pop     rbp
0x180014157  retn
```
