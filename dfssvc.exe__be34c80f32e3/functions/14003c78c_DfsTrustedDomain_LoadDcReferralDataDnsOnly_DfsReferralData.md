# DfsTrustedDomain::LoadDcReferralDataDnsOnly(DfsReferralData *)

- ea: `0x14003c78c`
- end: `0x14003cb8c`
- name: `?LoadDcReferralDataDnsOnly@DfsTrustedDomain@@AEAAKPEAVDfsReferralData@@@Z`
- size: `1024`
- prototype: `unsigned int __fastcall(DfsTrustedDomain *__hidden this, struct DfsReferralData *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14003bee4`

## callees

- `0x1400011d0`
- `0x140005a94`
- `0x140005b28`
- `0x1400096ac`
- `0x14000fd24`
- `0x1400152c8`
- `0x14002ff9c`
- `0x14003c78c`
- `0x14003ccd0`
- `0x1400586a8`

## import_xrefs

- `msvcrt!free` at `0x14003cb64`
- `msvcrt!free` at `0x14003cb64`
- `msvcrt!malloc` at `0x14003c8bb`
- `msvcrt!malloc` at `0x14003c8bb`
- `logoncli!DsGetDcCloseW` at `0x14003c92c`
- `logoncli!DsGetDcCloseW` at `0x14003c9bf`
- `logoncli!DsGetDcCloseW` at `0x14003c92c`
- `logoncli!DsGetDcCloseW` at `0x14003c9bf`
- `logoncli!DsGetDcNextW` at `0x14003c8a2`
- `logoncli!DsGetDcNextW` at `0x14003c8a2`
- `logoncli!DsGetDcOpenW` at `0x14003c82a`
- `logoncli!DsGetDcOpenW` at `0x14003c82a`
- `netutils!NetApiBufferFree` at `0x14003cb55`
- `netutils!NetApiBufferFree` at `0x14003cb55`

## pseudocode

```c
__int64 __fastcall DfsTrustedDomain::LoadDcReferralDataDnsOnly(DfsTrustedDomain *this, struct DfsReferralData *a2)
{
  unsigned int v4; // r14d
  DWORD DcOpenW; // eax
  unsigned int inited; // edi
  void **p_Block; // rbx
  DWORD DcNextW; // eax
  _QWORD *v9; // rax
  __int64 v10; // rax
  bool v11; // cf
  size_t v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  unsigned int *v15; // rcx
  void **v16; // rbx
  unsigned int v17; // r14d
  LPVOID *v18; // rsi
  LPVOID *v19; // rbx
  void *Block; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v22; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int8 v23; // [rsp+90h] [rbp+30h] BYREF
  HANDLE GetDcContextHandle; // [rsp+A0h] [rbp+40h] BYREF
  LPWSTR DnsHostName; // [rsp+A8h] [rbp+48h] BYREF

  GetDcContextHandle = 0;
  DnsHostName = 0;
  Block = 0;
  v4 = 0;
  v23 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_ZZd(
      *((_QWORD *)pWppControl + 2),
      16,
      (_DWORD)this + 16,
      (_DWORD)this,
      (__int64)this + 16,
      *((_BYTE *)this + 32));
  }
  DcOpenW = DsGetDcOpenW(*((LPCWSTR *)this + 1), 0, 0, 0, 0, 0, &GetDcContextHandle);
  inited = DcOpenW;
  if ( !DcOpenW )
  {
    p_Block = &Block;
    while ( 1 )
    {
      DcNextW = DsGetDcNextW(GetDcContextHandle, 0, 0, &DnsHostName);
      inited = DcNextW;
      if ( DcNextW )
        break;
      v9 = malloc(0x10u);
      *p_Block = v9;
      if ( !v9 )
      {
        DsGetDcCloseW(GetDcContextHandle);
        goto LABEL_62;
      }
      *v9 = DnsHostName;
      *((_QWORD *)*p_Block + 1) = 0;
      p_Block = (void **)((char *)*p_Block + 8);
      ++v4;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)pWppControl + 2), 20, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DnsHostName);
      }
    }
    if ( DcNextW == 259 )
    {
      inited = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)pWppControl + 2), 18, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && pWppControl
           && (pWppControl[7] & 0x20) != 0
           && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 19, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DcNextW);
    }
    DsGetDcCloseW(GetDcContextHandle);
    if ( !v4 )
    {
LABEL_62:
      v18 = (LPVOID *)Block;
      while ( v18 )
      {
        v19 = v18;
        v18 = (LPVOID *)v18[1];
        NetApiBufferFree(*v19);
        free(v19);
      }
      return inited;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 21, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v4);
    }
    v10 = 56LL * v4;
    if ( !is_mul_ok(v4, 0x38u) )
      v10 = -1;
    v11 = __CFADD__(v10, 8);
    v12 = v10 + 8;
    if ( v11 )
      v12 = -1;
    v13 = operator new(v12);
    if ( v13 )
    {
      v14 = v13 + 1;
      *v13 = v4;
      `vector constructor iterator'(v13 + 1, 0x38u, v4, (void *(*)(void *))DfsReplica::DfsReplica);
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)a2 + 6) = v14;
    if ( !v14 )
    {
      inited = 8;
      goto LABEL_62;
    }
    v15 = pWppControl;
    v16 = &Block;
    inited = 0;
    *((_DWORD *)a2 + 10) = v4;
    v17 = 0;
    while ( 1 )
    {
      if ( !*v16 )
        goto LABEL_62;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && v15
        && (v15[7] & 0x20) != 0
        && *((_BYTE *)v15 + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)v15 + 2), 22, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, *(_QWORD *)*v16);
      }
      inited = DfsRtlInitUnicodeStringEx(&v22, *(_QWORD *)*v16);
      if ( !inited )
      {
        inited = DfsReplica::SetTargetServer((DfsReplica *)(*((_QWORD *)a2 + 6) + 56LL * v17), &v22, &v23);
        v15 = pWppControl;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || !pWppControl
          || (pWppControl[7] & 0x20) == 0
          || *((_BYTE *)pWppControl + 25) < 2u )
        {
          goto LABEL_61;
        }
        WPP_SF_ZD(
          *((_QWORD *)pWppControl + 2),
          23,
          (unsigned int)WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids,
          (unsigned int)&v22,
          inited);
      }
      v15 = pWppControl;
LABEL_61:
      ++v17;
      v16 = (void **)((char *)*v16 + 8);
      if ( inited )
        goto LABEL_62;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 17, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DcOpenW);
  }
  return inited;
}

```

## disassembly

```asm
0x14003c78c  mov     [rsp-28h+arg_8], rbx
0x14003c791  push    rbp
0x14003c792  push    rsi
0x14003c793  push    rdi
0x14003c794  push    r14
0x14003c796  push    r15
0x14003c798  mov     rbp, rsp
0x14003c79b  sub     rsp, 60h
0x14003c79f  and     [rbp+GetDcContextHandle], 0
0x14003c7a4  xorps   xmm0, xmm0
0x14003c7a7  and     [rbp+DnsHostName], 0
0x14003c7ac  mov     r15, rdx
0x14003c7af  and     [rbp+Block], 0
0x14003c7b4  mov     rbx, rcx
0x14003c7b7  xor     r14d, r14d
0x14003c7ba  mov     [rbp+arg_0], 0
0x14003c7be  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x14003c7c2  lea     rsi, WPP_GLOBAL_Control
0x14003c7c9  cmp     cs:WPP_GLOBAL_Control, rsi
0x14003c7d0  jz      short loc_14003C80B
0x14003c7d2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c7d9  test    rcx, rcx
0x14003c7dc  jz      short loc_14003C80B
0x14003c7de  test    byte ptr [rcx+1Ch], 20h
0x14003c7e2  jz      short loc_14003C80B
0x14003c7e4  cmp     byte ptr [rcx+19h], 2
0x14003c7e8  jb      short loc_14003C80B
0x14003c7ea  movzx   eax, byte ptr [rbx+20h]
0x14003c7ee  lea     r8, [rbx+10h]
0x14003c7f2  mov     rcx, [rcx+10h]
0x14003c7f6  lea     edx, [r14+10h]
0x14003c7fa  mov     [rsp+60h+DcFlags], eax; DcFlags
0x14003c7fe  mov     r9, rbx
0x14003c801  mov     [rsp+60h+DnsForestName], r8; DnsForestName
0x14003c806  call    WPP_SF_ZZd
0x14003c80b  mov     rcx, [rbx+8]; DnsName
0x14003c80f  lea     rax, [rbp+GetDcContextHandle]
0x14003c813  mov     [rsp+60h+RetGetDcContext], rax; RetGetDcContext
0x14003c818  xor     r9d, r9d; DomainGuid
0x14003c81b  and     [rsp+60h+DcFlags], r14d
0x14003c820  xor     r8d, r8d; SiteName
0x14003c823  and     [rsp+60h+DnsForestName], r14
0x14003c828  xor     edx, edx; OptionFlags
0x14003c82a  call    cs:__imp_DsGetDcOpenW
0x14003c831  nop     dword ptr [rax+rax+00h]
0x14003c836  mov     edi, eax
0x14003c838  test    eax, eax
0x14003c83a  jz      short loc_14003C88A
0x14003c83c  cmp     cs:WPP_GLOBAL_Control, rsi
0x14003c843  jz      loc_14003CB75
0x14003c849  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c850  test    rcx, rcx
0x14003c853  jz      loc_14003CB75
0x14003c859  test    byte ptr [rcx+1Ch], 20h
0x14003c85d  jz      loc_14003CB75
0x14003c863  cmp     byte ptr [rcx+19h], 2
0x14003c867  jb      loc_14003CB75
0x14003c86d  mov     rcx, [rcx+10h]
0x14003c871  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c878  mov     edx, 11h
0x14003c87d  mov     r9d, eax
0x14003c880  call    WPP_SF_D
0x14003c885  jmp     loc_14003CB75
0x14003c88a  lea     rbx, [rbp+Block]
0x14003c88e  lea     rsi, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c895  mov     rcx, [rbp+GetDcContextHandle]; GetDcContextHandle
0x14003c899  lea     r9, [rbp+DnsHostName]; DnsHostName
0x14003c89d  xor     r8d, r8d; SockAddresses
0x14003c8a0  xor     edx, edx; SockAddressCount
0x14003c8a2  call    cs:__imp_DsGetDcNextW
0x14003c8a9  nop     dword ptr [rax+rax+00h]
0x14003c8ae  mov     edi, eax
0x14003c8b0  test    eax, eax
0x14003c8b2  jnz     loc_14003C93D
0x14003c8b8  lea     ecx, [rax+10h]; Size
0x14003c8bb  call    cs:__imp_malloc
0x14003c8c2  nop     dword ptr [rax+rax+00h]
0x14003c8c7  mov     [rbx], rax
0x14003c8ca  test    rax, rax
0x14003c8cd  jz      short loc_14003C928
0x14003c8cf  mov     rcx, [rbp+DnsHostName]
0x14003c8d3  mov     [rax], rcx
0x14003c8d6  mov     rax, [rbx]
0x14003c8d9  and     qword ptr [rax+8], 0
0x14003c8de  mov     rbx, [rbx]
0x14003c8e1  add     rbx, 8
0x14003c8e5  inc     r14d
0x14003c8e8  lea     rax, WPP_GLOBAL_Control
0x14003c8ef  cmp     cs:WPP_GLOBAL_Control, rax
0x14003c8f6  jz      short loc_14003C895
0x14003c8f8  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c8ff  test    rcx, rcx
0x14003c902  jz      short loc_14003C895
0x14003c904  test    byte ptr [rcx+1Ch], 20h
0x14003c908  jz      short loc_14003C895
0x14003c90a  cmp     byte ptr [rcx+19h], 2
0x14003c90e  jb      short loc_14003C895
0x14003c910  mov     r9, [rbp+DnsHostName]
0x14003c914  lea     edx, [rdi+14h]
0x14003c917  mov     rcx, [rcx+10h]
0x14003c91b  mov     r8, rsi
0x14003c91e  call    WPP_SF_S
0x14003c923  jmp     loc_14003C895
0x14003c928  mov     rcx, [rbp+GetDcContextHandle]; GetDcContextHandle
0x14003c92c  call    cs:__imp_DsGetDcCloseW
0x14003c933  nop     dword ptr [rax+rax+00h]
0x14003c938  jmp     loc_14003CB45
0x14003c93d  cmp     eax, 103h
0x14003c942  jnz     short loc_14003C97F
0x14003c944  xor     edi, edi
0x14003c946  lea     rbx, WPP_GLOBAL_Control
0x14003c94d  cmp     cs:WPP_GLOBAL_Control, rbx
0x14003c954  jz      short loc_14003C9BB
0x14003c956  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c95d  test    rcx, rcx
0x14003c960  jz      short loc_14003C9BB
0x14003c962  test    byte ptr [rcx+1Ch], 20h
0x14003c966  jz      short loc_14003C9BB
0x14003c968  cmp     byte ptr [rcx+19h], 2
0x14003c96c  jb      short loc_14003C9BB
0x14003c96e  mov     rcx, [rcx+10h]
0x14003c972  lea     edx, [rdi+12h]
0x14003c975  mov     r8, rsi
0x14003c978  call    WPP_SF_
0x14003c97d  jmp     short loc_14003C9BB
0x14003c97f  lea     rbx, WPP_GLOBAL_Control
0x14003c986  cmp     cs:WPP_GLOBAL_Control, rbx
0x14003c98d  jz      short loc_14003C9BB
0x14003c98f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c996  test    rcx, rcx
0x14003c999  jz      short loc_14003C9BB
0x14003c99b  test    byte ptr [rcx+1Ch], 20h
0x14003c99f  jz      short loc_14003C9BB
0x14003c9a1  cmp     byte ptr [rcx+19h], 2
0x14003c9a5  jb      short loc_14003C9BB
0x14003c9a7  mov     rcx, [rcx+10h]
0x14003c9ab  mov     edx, 13h
0x14003c9b0  mov     r9d, eax
0x14003c9b3  mov     r8, rsi
0x14003c9b6  call    WPP_SF_D
0x14003c9bb  mov     rcx, [rbp+GetDcContextHandle]; GetDcContextHandle
0x14003c9bf  call    cs:__imp_DsGetDcCloseW
0x14003c9c6  nop     dword ptr [rax+rax+00h]
0x14003c9cb  test    r14d, r14d
0x14003c9ce  jz      loc_14003CB45
0x14003c9d4  cmp     cs:WPP_GLOBAL_Control, rbx
0x14003c9db  jz      short loc_14003CA09
0x14003c9dd  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c9e4  test    rcx, rcx
0x14003c9e7  jz      short loc_14003CA09
0x14003c9e9  test    byte ptr [rcx+1Ch], 20h
0x14003c9ed  jz      short loc_14003CA09
0x14003c9ef  cmp     byte ptr [rcx+19h], 2
0x14003c9f3  jb      short loc_14003CA09
0x14003c9f5  mov     rcx, [rcx+10h]
0x14003c9f9  mov     edx, 15h
0x14003c9fe  mov     r9d, r14d
0x14003ca01  mov     r8, rsi
0x14003ca04  call    WPP_SF_D
0x14003ca09  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14003ca10  mov     edi, r14d
0x14003ca13  mov     eax, 38h ; '8'
0x14003ca18  mul     rdi
0x14003ca1b  cmovo   rax, rcx
0x14003ca1f  add     rax, 8
0x14003ca23  cmovb   rax, rcx
0x14003ca27  mov     rcx, rax; Size
0x14003ca2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003ca2f  test    rax, rax
0x14003ca32  jz      short loc_14003CA54
0x14003ca34  lea     rbx, [rax+8]
0x14003ca38  mov     [rax], rdi
0x14003ca3b  mov     rcx, rbx; void *
0x14003ca3e  lea     r9, ??0DfsReplica@@QEAA@XZ; void *(*)(void *)
0x14003ca45  mov     r8d, edi; unsigned __int64
0x14003ca48  mov     edx, 38h ; '8'; unsigned __int64
0x14003ca4d  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14003ca52  jmp     short loc_14003CA56
0x14003ca54  xor     ebx, ebx
0x14003ca56  mov     [r15+30h], rbx
0x14003ca5a  test    rbx, rbx
0x14003ca5d  jnz     short loc_14003CA67
0x14003ca5f  lea     edi, [rbx+8]
0x14003ca62  jmp     loc_14003CB45
0x14003ca67  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003ca6e  lea     rbx, [rbp+Block]
0x14003ca72  xor     edi, edi
0x14003ca74  mov     [r15+28h], r14d
0x14003ca78  xor     r14d, r14d
0x14003ca7b  mov     r9, [rbx]
0x14003ca7e  test    r9, r9
0x14003ca81  jz      loc_14003CB45
0x14003ca87  lea     rax, WPP_GLOBAL_Control
0x14003ca8e  cmp     cs:WPP_GLOBAL_Control, rax
0x14003ca95  jz      short loc_14003CABC
0x14003ca97  test    rcx, rcx
0x14003ca9a  jz      short loc_14003CABC
0x14003ca9c  test    byte ptr [rcx+1Ch], 20h
0x14003caa0  jz      short loc_14003CABC
0x14003caa2  cmp     byte ptr [rcx+19h], 2
0x14003caa6  jb      short loc_14003CABC
0x14003caa8  mov     r9, [r9]
0x14003caab  mov     edx, 16h
0x14003cab0  mov     rcx, [rcx+10h]
0x14003cab4  mov     r8, rsi
0x14003cab7  call    WPP_SF_S
0x14003cabc  mov     rdx, [rbx]
0x14003cabf  lea     rcx, [rbp+var_18]
0x14003cac3  mov     rdx, [rdx]
0x14003cac6  call    DfsRtlInitUnicodeStringEx
0x14003cacb  mov     edi, eax
0x14003cacd  test    eax, eax
0x14003cacf  jnz     short loc_14003CB2C
0x14003cad1  mov     eax, r14d
0x14003cad4  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x14003cad8  imul    rcx, rax, 38h ; '8'
0x14003cadc  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x14003cae0  add     rcx, [r15+30h]; this
0x14003cae4  call    ?SetTargetServer@DfsReplica@@QEAAKPEAU_UNICODE_STRING@@PEAE@Z; DfsReplica::SetTargetServer(_UNICODE_STRING *,uchar *)
0x14003cae9  mov     edi, eax
0x14003caeb  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003caf2  lea     rax, WPP_GLOBAL_Control
0x14003caf9  cmp     cs:WPP_GLOBAL_Control, rax
0x14003cb00  jz      short loc_14003CB33
0x14003cb02  test    rcx, rcx
0x14003cb05  jz      short loc_14003CB33
0x14003cb07  test    byte ptr [rcx+1Ch], 20h
0x14003cb0b  jz      short loc_14003CB33
0x14003cb0d  cmp     byte ptr [rcx+19h], 2
0x14003cb11  jb      short loc_14003CB33
0x14003cb13  mov     rcx, [rcx+10h]
0x14003cb17  lea     r9, [rbp+var_18]
0x14003cb1b  mov     edx, 17h
0x14003cb20  mov     dword ptr [rsp+60h+DnsForestName], edi
0x14003cb24  mov     r8, rsi
0x14003cb27  call    WPP_SF_ZD
0x14003cb2c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003cb33  mov     rbx, [rbx]
0x14003cb36  inc     r14d
0x14003cb39  add     rbx, 8
0x14003cb3d  test    edi, edi
0x14003cb3f  jz      loc_14003CA7B
0x14003cb45  mov     rsi, [rbp+Block]
0x14003cb49  jmp     short loc_14003CB70
0x14003cb4b  mov     rbx, rsi
0x14003cb4e  mov     rsi, [rsi+8]
0x14003cb52  mov     rcx, [rbx]; Buffer
0x14003cb55  call    cs:__imp_NetApiBufferFree
0x14003cb5c  nop     dword ptr [rax+rax+00h]
0x14003cb61  mov     rcx, rbx; Block
0x14003cb64  call    cs:__imp_free
0x14003cb6b  nop     dword ptr [rax+rax+00h]
0x14003cb70  test    rsi, rsi
0x14003cb73  jnz     short loc_14003CB4B
0x14003cb75  mov     rbx, [rsp+60h+arg_8]
0x14003cb7d  mov     eax, edi
0x14003cb7f  add     rsp, 60h
0x14003cb83  pop     r15
0x14003cb85  pop     r14
0x14003cb87  pop     rdi
0x14003cb88  pop     rsi
0x14003cb89  pop     rbp
0x14003cb8a  retn
```
