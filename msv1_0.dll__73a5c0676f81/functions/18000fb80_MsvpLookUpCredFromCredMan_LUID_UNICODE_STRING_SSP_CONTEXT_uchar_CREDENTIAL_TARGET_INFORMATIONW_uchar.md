# MsvpLookUpCredFromCredMan(_LUID *,_UNICODE_STRING *,_SSP_CONTEXT *,uchar,_CREDENTIAL_TARGET_INFORMATIONW *,uchar *)

- ea: `0x18000fb80`
- end: `0x18000ffa7`
- name: `?MsvpLookUpCredFromCredMan@@YAJPEAU_LUID@@PEAU_UNICODE_STRING@@PEAU_SSP_CONTEXT@@EPEAU_CREDENTIAL_TARGET_INFORMATIONW@@PEAE@Z`
- size: `1063`
- prototype: `__int64 __fastcall(struct _LUID *, struct _UNICODE_STRING *, struct _SSP_CONTEXT *, unsigned __int8, struct _CREDENTIAL_TARGET_INFORMATIONW *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800268dc`

## callees

- `0x18000fb80`
- `0x18000ffb0`
- `0x180010b14`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18006bcf0`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000fef7`
- `ntdll!RtlInitUnicodeString` at `0x18000fef7`
- `SspiCli!SspiPrepareForCredRead` at `0x18000fd72`
- `SspiCli!SspiPrepareForCredRead` at `0x18000febc`
- `SspiCli!SspiPrepareForCredRead` at `0x18000fd72`
- `SspiCli!SspiPrepareForCredRead` at `0x18000febc`
- `SspiCli!SspiLocalFree` at `0x18000ff5a`
- `SspiCli!SspiLocalFree` at `0x18000ff6c`
- `SspiCli!SspiLocalFree` at `0x18000ff5a`
- `SspiCli!SspiLocalFree` at `0x18000ff6c`

## pseudocode

```c
__int64 __fastcall MsvpLookUpCredFromCredMan(
        struct _LUID *a1,
        struct _UNICODE_STRING *a2,
        struct _SSP_CONTEXT *a3,
        char a4,
        struct _CREDENTIAL_TARGET_INFORMATIONW *a5,
        unsigned __int8 *a6)
{
  int v6; // r15d
  __int128 v9; // xmm1
  int v10; // r12d
  char *p_pCredmanCredentialType; // rbx
  unsigned int v12; // edi
  __int64 v13; // r8
  const WCHAR *TargetName; // rdx
  SECURITY_STATUS v16; // eax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  char *v25; // rax
  struct _UNICODE_STRING *p_DestinationString; // rdx
  _QWORD v27[8]; // [rsp+0h] [rbp-40h] BYREF
  ULONG pCredmanCredentialType; // [rsp+40h] [rbp+0h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp+8h] BYREF
  PCWSTR ppszCredmanTargetName; // [rsp+50h] [rbp+10h] BYREF
  _DWORD v31[2]; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int8 *v32; // [rsp+60h] [rbp+20h]
  _OWORD v33[3]; // [rsp+70h] [rbp+30h] BYREF
  const WCHAR *v34; // [rsp+A0h] [rbp+60h]
  int v35; // [rsp+A8h] [rbp+68h]
  int v36; // [rsp+ACh] [rbp+6Ch]
  ULONG *v37; // [rsp+B0h] [rbp+70h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp+80h] BYREF
  _DWORD AuthIdentity[3]; // [rsp+E0h] [rbp+A0h] BYREF
  __int64 v40; // [rsp+ECh] [rbp+ACh]
  __int64 v41; // [rsp+F4h] [rbp+B4h]
  int v42; // [rsp+FCh] [rbp+BCh]
  __int16 v43; // [rsp+100h] [rbp+C0h]
  __int64 v44; // [rsp+102h] [rbp+C2h]
  int v45; // [rsp+10Ah] [rbp+CAh]
  int v46; // [rsp+10Eh] [rbp+CEh]
  __int16 v47; // [rsp+112h] [rbp+D2h]
  __int128 v48; // [rsp+114h] [rbp+D4h]
  __int64 v49; // [rsp+124h] [rbp+E4h]

  v6 = (int)a1;
  v27[6] = a6;
  v47 = 28;
  v9 = *(_OWORD *)&a5->DnsServerName;
  v10 = (int)a3;
  v33[0] = *(_OWORD *)&a5->TargetName;
  p_pCredmanCredentialType = 0;
  v33[2] = *(_OWORD *)&a5->DnsDomainName;
  v43 = 28;
  v33[1] = v9;
  v35 = *(_QWORD *)&a5->Flags;
  DestinationString = 0;
  v34 = L"NTLM";
  v32 = a6;
  SourceString = 0;
  ppszCredmanTargetName = 0;
  pCredmanCredentialType = 0;
  v40 = 0;
  v41 = 0;
  v44 = 0;
  v45 = 0;
  v49 = 0;
  v31[0] = 2;
  v48 = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
  v31[1] = 3;
  AuthIdentity[1] = 8;
  v46 = 1835008;
  AuthIdentity[0] = 513;
  AuthIdentity[2] = 76;
  v42 = 48;
  v36 = 2;
  v37 = v31;
  v12 = CopyCredManCredentials((_DWORD)a1, (_DWORD)a2, (unsigned int)v33, (_DWORD)a3, a4, 1, (__int64)a6);
  if ( v12 != -1073741275 )
    goto LABEL_2;
  TargetName = a5->TargetName;
  if ( a5->TargetName )
  {
    v16 = SspiPrepareForCredRead(AuthIdentity, TargetName, &pCredmanCredentialType, &ppszCredmanTargetName);
    if ( v16 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v24 = 173;
      goto LABEL_28;
    }
  }
  if ( a2 )
  {
    v17 = a2->Length + 2LL;
    if ( v17 > g_ulMaxStackAllocSize )
      goto LABEL_45;
    v18 = v17 + g_ulAdditionalProbeSize + 8;
    if ( v18 < v17 || !(unsigned int)VerifyStackAvailable(v18, TargetName, v13) )
      goto LABEL_45;
    v19 = v17 + 23;
    if ( v17 + 23 <= v17 + 8 )
      v19 = 0xFFFFFFFFFFFFFF0LL;
    v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
    v21 = alloca(v20);
    v22 = alloca(v20);
    p_pCredmanCredentialType = (char *)&pCredmanCredentialType;
    if ( v27 == (_QWORD *)-64LL
      || (pCredmanCredentialType = 1801679955, (p_pCredmanCredentialType = (char *)&SourceString) == 0) )
    {
LABEL_45:
      if ( v17 + 8 >= v17 )
      {
        v25 = (char *)((__int64 (*)(void))g_pfnAllocate)();
        p_pCredmanCredentialType = v25;
        if ( v25 )
        {
          *(_DWORD *)v25 = 1885431112;
          p_pCredmanCredentialType = v25 + 8;
        }
      }
    }
    if ( !p_pCredmanCredentialType )
    {
      v12 = -1073741670;
      goto LABEL_2;
    }
    memcpy_0(p_pCredmanCredentialType, a2->Buffer, a2->Length);
    *(_WORD *)&p_pCredmanCredentialType[2 * ((unsigned __int64)a2->Length >> 1)] = 0;
    v16 = SspiPrepareForCredRead(AuthIdentity, (PCWSTR)p_pCredmanCredentialType, &pCredmanCredentialType, &SourceString);
    if ( v16 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v24 = 174;
LABEL_28:
      WPP_SF_d(v23[2], v24, WPP_9d14a29214673930ad919c44725bb8be_Traceguids, (unsigned int)v16);
LABEL_29:
      v12 = -1073741275;
      goto LABEL_2;
    }
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  p_DestinationString = &DestinationString;
  *(_QWORD *)&v33[0] = ppszCredmanTargetName;
  v36 = 1;
  v37 = &pCredmanCredentialType;
  v35 = v35 & 0x40 | 1;
  if ( !SourceString )
    LODWORD(p_DestinationString) = 0;
  v12 = CopyCredManCredentials(v6, (_DWORD)p_DestinationString, (unsigned int)v33, v10, a4, 0, (__int64)v32);
LABEL_2:
  if ( SourceString )
    SspiLocalFree((PVOID)SourceString);
  if ( ppszCredmanTargetName )
    SspiLocalFree((PVOID)ppszCredmanTargetName);
  if ( p_pCredmanCredentialType && *((_DWORD *)p_pCredmanCredentialType - 2) == 1885431112 )
    ((void (__fastcall *)(char *, _UNKNOWN **))g_pfnFree)(p_pCredmanCredentialType - 8, &WPP_GLOBAL_Control);
  if ( (int)(v12 + 0x80000000) >= 0
    && v12 != -1073741275
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_9d14a29214673930ad919c44725bb8be_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x18000fb80  push    rbp
0x18000fb82  push    rbx
0x18000fb83  push    rsi
0x18000fb84  push    rdi
0x18000fb85  push    r12
0x18000fb87  push    r13
0x18000fb89  push    r14
0x18000fb8b  push    r15
0x18000fb8d  sub     rsp, 148h
0x18000fb94  lea     rbp, [rsp+40h]
0x18000fb99  mov     rax, cs:__security_cookie
0x18000fba0  xor     rax, rbp
0x18000fba3  mov     [rbp+140h+var_50], rax
0x18000fbaa  mov     rsi, [rbp+140h+arg_20]
0x18000fbb1  mov     r15, rcx
0x18000fbb4  mov     rcx, [rbp+140h+arg_28]
0x18000fbbb  mov     eax, 1Ch
0x18000fbc0  mov     [rsp+180h+var_150], rcx
0x18000fbc5  mov     r14, rdx
0x18000fbc8  xor     edx, edx
0x18000fbca  mov     [rbp+140h+var_6E], ax
0x18000fbd1  movaps  xmm0, xmmword ptr [rsi]
0x18000fbd4  movzx   r13d, r9b
0x18000fbd8  movaps  xmm1, xmmword ptr [rsi+10h]
0x18000fbdc  mov     r12, r8
0x18000fbdf  movaps  [rbp+140h+var_110], xmm0
0x18000fbe3  mov     ebx, edx
0x18000fbe5  movaps  xmm0, xmmword ptr [rsi+20h]
0x18000fbe9  movaps  [rbp+140h+var_F0], xmm0
0x18000fbed  xorps   xmm0, xmm0
0x18000fbf0  mov     [rbp+140h+var_80], ax
0x18000fbf7  lea     rax, pszPackageName; "NTLM"
0x18000fbfe  movaps  [rbp+140h+var_100], xmm1
0x18000fc02  movaps  xmm1, xmmword ptr [rsi+30h]
0x18000fc06  movaps  [rbp+140h+var_E0], xmm1
0x18000fc0a  movups  xmmword ptr [rbp+140h+DestinationString.Length], xmm0
0x18000fc11  mov     qword ptr [rbp+140h+var_E0], rax
0x18000fc15  lea     rax, [rbp+140h+var_128]
0x18000fc19  movups  xmm0, cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x18000fc20  mov     [rbp+140h+var_120], rcx
0x18000fc24  mov     rcx, r15
0x18000fc27  mov     [rbp+140h+SourceString], rdx
0x18000fc2b  mov     [rbp+140h+ppszCredmanTargetName], rdx
0x18000fc2f  mov     [rbp+140h+pCredmanCredentialType], edx
0x18000fc32  mov     [rbp+140h+var_94], rdx
0x18000fc39  mov     [rbp+140h+var_8C], rdx
0x18000fc40  mov     [rbp+140h+var_7E], rdx
0x18000fc47  mov     [rbp+140h+var_76], edx
0x18000fc4d  mov     [rbp+140h+var_5C], rdx
0x18000fc54  mov     rdx, r14
0x18000fc57  mov     [rsp+180h+var_158], 1
0x18000fc5c  mov     [rsp+180h+var_160], r9b
0x18000fc61  mov     r9, r8
0x18000fc64  lea     r8, [rbp+140h+var_110]
0x18000fc68  mov     [rbp+140h+var_128], 2
0x18000fc6f  movups  [rbp+140h+var_6C], xmm0
0x18000fc76  mov     [rbp+140h+var_124], 3
0x18000fc7d  mov     [rbp+140h+var_9C], 8
0x18000fc87  mov     [rbp+140h+var_72], 1C0000h
0x18000fc91  mov     [rbp+140h+AuthIdentity], 201h
0x18000fc9b  mov     [rbp+140h+var_98], 4Ch ; 'L'
0x18000fca5  mov     [rbp+140h+var_84], 30h ; '0'
0x18000fcaf  mov     dword ptr [rbp+140h+var_E0+0Ch], 2
0x18000fcb6  mov     [rbp+140h+var_D0], rax
0x18000fcba  call    CopyCredManCredentials
0x18000fcbf  lea     rdx, WPP_GLOBAL_Control
0x18000fcc6  mov     edi, eax
0x18000fcc8  cmp     eax, 0C0000225h
0x18000fccd  jz      loc_18000FD5B
0x18000fcd3  mov     rcx, [rbp+140h+SourceString]; DataBuffer
0x18000fcd7  test    rcx, rcx
0x18000fcda  jnz     loc_18000FF5A
0x18000fce0  mov     rcx, [rbp+140h+ppszCredmanTargetName]; DataBuffer
0x18000fce4  test    rcx, rcx
0x18000fce7  jnz     loc_18000FF6C
0x18000fced  test    rbx, rbx
0x18000fcf0  jnz     loc_18000FF7E
0x18000fcf6  mov     ecx, 80000000h
0x18000fcfb  lea     eax, [rdi+rcx]
0x18000fcfe  test    ecx, eax
0x18000fd00  jz      short loc_18000FD27
0x18000fd02  mov     eax, edi
0x18000fd04  mov     rcx, [rbp+140h+var_50]
0x18000fd0b  xor     rcx, rbp; StackCookie
0x18000fd0e  call    __security_check_cookie
0x18000fd13  lea     rsp, [rbp+108h]
0x18000fd1a  pop     r15
0x18000fd1c  pop     r14
0x18000fd1e  pop     r13
0x18000fd20  pop     r12
0x18000fd22  pop     rdi
0x18000fd23  pop     rsi
0x18000fd24  pop     rbx
0x18000fd25  pop     rbp
0x18000fd26  retn
0x18000fd27  cmp     edi, 0C0000225h
0x18000fd2d  jz      short loc_18000FD02
0x18000fd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd36  cmp     rcx, rdx
0x18000fd39  jz      short loc_18000FD02
0x18000fd3b  test    byte ptr [rcx+1Ch], 1
0x18000fd3f  jz      short loc_18000FD02
0x18000fd41  mov     rcx, [rcx+10h]
0x18000fd45  lea     r8, WPP_9d14a29214673930ad919c44725bb8be_Traceguids
0x18000fd4c  mov     edx, 0AFh
0x18000fd51  mov     r9d, edi
0x18000fd54  call    WPP_SF_d
0x18000fd59  jmp     short loc_18000FD02
0x18000fd5b  mov     rdx, [rsi]; pszTargetName
0x18000fd5e  test    rdx, rdx
0x18000fd61  jz      short loc_18000FD80
0x18000fd63  lea     r9, [rbp+140h+ppszCredmanTargetName]; ppszCredmanTargetName
0x18000fd67  lea     r8, [rbp+140h+pCredmanCredentialType]; pCredmanCredentialType
0x18000fd6b  lea     rcx, [rbp+140h+AuthIdentity]; AuthIdentity
0x18000fd72  call    cs:__imp_SspiPrepareForCredRead
0x18000fd78  test    eax, eax
0x18000fd7a  js      loc_18000FE18
0x18000fd80  test    r14, r14
0x18000fd83  jz      loc_18000FEFD
0x18000fd89  movzx   edi, word ptr [r14]
0x18000fd8d  add     rdi, 2
0x18000fd91  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000fd98  ja      loc_18000FE61
0x18000fd9e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000fda5  add     rcx, 8
0x18000fda9  add     rcx, rdi
0x18000fdac  cmp     rcx, rdi
0x18000fdaf  jb      loc_18000FE61
0x18000fdb5  call    VerifyStackAvailable
0x18000fdba  test    eax, eax
0x18000fdbc  jz      loc_18000FE61
0x18000fdc2  lea     rax, [rdi+8]
0x18000fdc6  lea     rcx, [rax+0Fh]
0x18000fdca  cmp     rcx, rax
0x18000fdcd  ja      short loc_18000FDD9
0x18000fdcf  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000fdd9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000fddd  mov     rax, rcx
0x18000fde0  call    _alloca_probe
0x18000fde5  sub     rsp, rcx
0x18000fde8  lea     rbx, [rsp+180h+pCredmanCredentialType]
0x18000fded  test    rbx, rbx
0x18000fdf0  jz      short loc_18000FE61
0x18000fdf2  mov     dword ptr [rbx], 6B637453h
0x18000fdf8  add     rbx, 8
0x18000fdfc  jz      short loc_18000FE61
0x18000fdfe  test    rbx, rbx
0x18000fe01  jnz     loc_18000FE8D
0x18000fe07  mov     edi, 0C000009Ah
0x18000fe0c  lea     rdx, WPP_GLOBAL_Control
0x18000fe13  jmp     loc_18000FCD3
0x18000fe18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe1f  lea     rdx, WPP_GLOBAL_Control
0x18000fe26  cmp     rcx, rdx
0x18000fe29  jz      short loc_18000FE57
0x18000fe2b  test    byte ptr [rcx+1Ch], 2
0x18000fe2f  jz      short loc_18000FE57
0x18000fe31  mov     edx, 0ADh
0x18000fe36  jmp     short loc_18000FE3D
0x18000fe38  mov     edx, 0AEh
0x18000fe3d  mov     rcx, [rcx+10h]
0x18000fe41  lea     r8, WPP_9d14a29214673930ad919c44725bb8be_Traceguids
0x18000fe48  mov     r9d, eax
0x18000fe4b  call    WPP_SF_d
0x18000fe50  lea     rdx, WPP_GLOBAL_Control
0x18000fe57  mov     edi, 0C0000225h
0x18000fe5c  jmp     loc_18000FCD3
0x18000fe61  lea     rcx, [rdi+8]
0x18000fe65  cmp     rcx, rdi
0x18000fe68  jb      short loc_18000FDFE
0x18000fe6a  mov     rax, cs:g_pfnAllocate
0x18000fe71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe76  mov     rbx, rax
0x18000fe79  test    rax, rax
0x18000fe7c  jz      short loc_18000FDFE
0x18000fe7e  mov     dword ptr [rax], 70616548h
0x18000fe84  add     rbx, 8
0x18000fe88  jmp     loc_18000FDFE
0x18000fe8d  movzx   r8d, word ptr [r14]; Size
0x18000fe91  mov     rcx, rbx; void *
0x18000fe94  mov     rdx, [r14+8]; Src
0x18000fe98  call    memcpy_0
0x18000fe9d  movzx   ecx, word ptr [r14]
0x18000fea1  lea     r9, [rbp+140h+SourceString]; ppszCredmanTargetName
0x18000fea5  shr     rcx, 1
0x18000fea8  lea     r8, [rbp+140h+pCredmanCredentialType]; pCredmanCredentialType
0x18000feac  xor     eax, eax
0x18000feae  mov     rdx, rbx; pszTargetName
0x18000feb1  mov     [rbx+rcx*2], ax
0x18000feb5  lea     rcx, [rbp+140h+AuthIdentity]; AuthIdentity
0x18000febc  call    cs:__imp_SspiPrepareForCredRead
0x18000fec2  test    eax, eax
0x18000fec4  jns     short loc_18000FEEC
0x18000fec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fecd  lea     rdx, WPP_GLOBAL_Control
0x18000fed4  cmp     rcx, rdx
0x18000fed7  jz      loc_18000FE57
0x18000fedd  test    byte ptr [rcx+1Ch], 2
0x18000fee1  jz      loc_18000FE57
0x18000fee7  jmp     loc_18000FE38
0x18000feec  mov     rdx, [rbp+140h+SourceString]; SourceString
0x18000fef0  lea     rcx, [rbp+140h+DestinationString]; DestinationString
0x18000fef7  call    cs:__imp_RtlInitUnicodeString
0x18000fefd  mov     rax, [rbp+140h+ppszCredmanTargetName]
0x18000ff01  lea     rdx, [rbp+140h+DestinationString]
0x18000ff08  mov     qword ptr [rbp+140h+var_110], rax
0x18000ff0c  lea     r8, [rbp+140h+var_110]
0x18000ff10  lea     rax, [rbp+140h+pCredmanCredentialType]
0x18000ff14  mov     dword ptr [rbp+140h+var_E0+0Ch], 1
0x18000ff1b  mov     [rbp+140h+var_D0], rax
0x18000ff1f  mov     r9, r12
0x18000ff22  mov     eax, dword ptr [rbp+140h+var_E0+8]
0x18000ff25  mov     rcx, r15
0x18000ff28  and     eax, 40h
0x18000ff2b  or      eax, 1
0x18000ff2e  mov     dword ptr [rbp+140h+var_E0+8], eax
0x18000ff31  xor     eax, eax
0x18000ff33  cmp     [rbp+140h+SourceString], rax
0x18000ff37  cmovz   rdx, rax
0x18000ff3b  mov     rax, [rbp+140h+var_120]
0x18000ff3f  mov     [rsp+180h+var_150], rax
0x18000ff44  mov     [rsp+180h+var_158], 0
0x18000ff49  mov     [rsp+180h+var_160], r13b
0x18000ff4e  call    CopyCredManCredentials
0x18000ff53  mov     edi, eax
0x18000ff55  jmp     loc_18000FE0C
0x18000ff5a  call    cs:__imp_SspiLocalFree
0x18000ff60  lea     rdx, WPP_GLOBAL_Control
0x18000ff67  jmp     loc_18000FCE0
0x18000ff6c  call    cs:__imp_SspiLocalFree
0x18000ff72  lea     rdx, WPP_GLOBAL_Control
0x18000ff79  jmp     loc_18000FCED
0x18000ff7e  cmp     dword ptr [rbx-8], 70616548h
0x18000ff85  lea     rcx, [rbx-8]
0x18000ff89  jnz     loc_18000FCF6
0x18000ff8f  mov     rax, cs:g_pfnFree
0x18000ff96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff9b  lea     rdx, WPP_GLOBAL_Control
0x18000ffa2  jmp     loc_18000FCF6
```
