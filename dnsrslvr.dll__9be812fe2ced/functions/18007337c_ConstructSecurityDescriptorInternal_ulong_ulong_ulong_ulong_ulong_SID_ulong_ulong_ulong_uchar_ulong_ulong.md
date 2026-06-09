# ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)

- ea: `0x18007337c`
- end: `0x180073754`
- name: `?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z`
- size: `984`
- prototype: `signed int __fastcall(__int64, __int64, __int64, __int64, unsigned int, struct _SID **, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180035c30`

## callees

- `0x18007337c`
- `0x1800776c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007347f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007371e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007347f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007371e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18007354d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073589`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800735c5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073606`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073642`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18007367e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800736ba`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073710`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18007354d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073589`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800735c5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073606`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073642`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18007367e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800736ba`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180073710`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180073475`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18007350b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180073475`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18007350b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800733d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800733d5`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x1800734bd`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x1800734bd`

## pseudocode

```c
signed int __fastcall ConstructSecurityDescriptorInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _SID **a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned int *a12)
{
  signed int result; // eax
  DWORD v13; // ecx
  __int64 i; // rdx
  DWORD v15; // edi
  struct _ACL *v16; // rbx
  __int64 j; // rdi
  struct _SID *v18; // r9
  DWORD v19; // r8d

  a12 = 0;
  result = WxGetProcessUserSID((struct _SID **)&a12);
  if ( result < 0 )
  {
    HIDWORD(a12) = 1240;
    return result;
  }
  v13 = GetLengthSid(a12) + 148;
  if ( a6 && a8 )
  {
    for ( i = 0; i != 4; ++i )
    {
      if ( a6[i] && a8[i] )
        v13 += a7[i] + 8;
    }
  }
  v15 = v13 + 8;
  if ( !v13 )
    v15 = 0;
  if ( v15 + 48 > 0x228 )
  {
    result = -2147024809;
    HIDWORD(a12) = 1301;
    return result;
  }
  *(_OWORD *)a10 = 0;
  *((_WORD *)a10 + 1) = 0x8000;
  *((_WORD *)a10 + 1) = -32752;
  *(_QWORD *)(a10 + 12) = 20;
  *a10 = 1;
  if ( !InitializeAcl((PACL)(a10 + 20), 0x1Cu, 2u) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1321;
LABEL_66:
    if ( result >= 0 )
      return -2147418113;
    return result;
  }
  if ( !AddMandatoryAce((PACL)(a10 + 20), 2u, 0, 1u, c_rgbLowLabelSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1325;
    goto LABEL_66;
  }
  result = 0;
  if ( !v15 )
    return result;
  *((_WORD *)a10 + 1) |= 4u;
  *((_DWORD *)a10 + 4) = 48;
  v16 = (struct _ACL *)(a10 + 48);
  if ( !InitializeAcl((PACL)a10 + 6, v15, 2u) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1338;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, a12) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1342;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, c_rgbBuiltinAdministratorsSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1347;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, c_rgbLocalSystemSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1352;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbBuiltinAnyPackageSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1357;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityInternetClientSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1358;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityInternetClientServerSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1359;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityPrivateNetworkClientServerSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1360;
    goto LABEL_66;
  }
  result = 0;
  if ( a6 && a8 )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      result = 0;
      if ( (unsigned int)j >= 4 )
        break;
      v18 = a6[j];
      if ( v18 )
      {
        v19 = a8[j];
        if ( v19 )
        {
          if ( !AddAccessAllowedAce(v16, 2u, v19, v18) )
          {
            result = GetLastError();
            if ( result > 0 )
              result = (unsigned __int16)result | 0x80070000;
            HIDWORD(a12) = 1371;
            goto LABEL_66;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007337c  mov     rax, rsp
0x18007337f  push    rbx
0x180073380  push    rbp
0x180073381  push    rsi
0x180073382  push    rdi
0x180073383  push    r12
0x180073385  push    r13
0x180073387  push    r14
0x180073389  sub     rsp, 30h
0x18007338d  mov     [rsp+68h+arg_5C], 0
0x180073398  lea     rcx, [rax+60h]; struct _SID **
0x18007339c  mov     qword ptr [rax+60h], 0
0x1800733a4  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x1800733a9  test    eax, eax
0x1800733ab  jns     short loc_1800733BD
0x1800733ad  mov     [rsp+68h+arg_5C], 4D8h
0x1800733b8  jmp     loc_180073745
0x1800733bd  mov     rcx, [rsp+0C8h]; pSid
0x1800733c5  mov     rsi, [rsp+68h+arg_38]
0x1800733cd  mov     r14, [rsp+68h+arg_28]
0x1800733d5  call    cs:__imp_GetLengthSid
0x1800733db  mov     r13d, 4
0x1800733e1  lea     ecx, [rax+94h]
0x1800733e7  test    r14, r14
0x1800733ea  jz      short loc_180073417
0x1800733ec  test    rsi, rsi
0x1800733ef  jz      short loc_180073417
0x1800733f1  mov     r8, [rsp+68h+arg_30]
0x1800733f9  xor     edx, edx
0x1800733fb  cmp     qword ptr [r14+rdx*8], 0
0x180073400  jz      short loc_18007340F
0x180073402  cmp     dword ptr [rsi+rdx*4], 0
0x180073406  jz      short loc_18007340F
0x180073408  add     ecx, 8
0x18007340b  add     ecx, [r8+rdx*4]
0x18007340f  inc     rdx
0x180073412  cmp     rdx, r13
0x180073415  jnz     short loc_1800733FB
0x180073417  test    ecx, ecx
0x180073419  lea     edi, [rcx+8]
0x18007341c  cmovz   edi, ecx
0x18007341f  lea     eax, [rdi+30h]
0x180073422  cmp     eax, 228h
0x180073427  jbe     short loc_18007343E
0x180073429  mov     eax, 80070057h
0x18007342e  mov     [rsp+68h+arg_5C], 515h
0x180073439  jmp     loc_180073745
0x18007343e  mov     rbx, [rsp+68h+arg_48]
0x180073446  mov     r12d, 2
0x18007344c  xorps   xmm0, xmm0
0x18007344f  mov     r8d, r12d; dwAclRevision
0x180073452  movups  xmmword ptr [rbx], xmm0
0x180073455  mov     word ptr [rbx+2], 8000h
0x18007345b  lea     edx, [r12+1Ah]; nAclLength
0x180073460  lea     rcx, [rbx+14h]; pAcl
0x180073464  mov     word ptr [rbx+2], 8010h
0x18007346a  mov     qword ptr [rbx+0Ch], 14h
0x180073472  mov     byte ptr [rbx], 1
0x180073475  call    cs:__imp_InitializeAcl
0x18007347b  test    eax, eax
0x18007347d  jnz     short loc_1800734A1
0x18007347f  call    cs:__imp_GetLastError
0x180073485  test    eax, eax
0x180073487  jle     short loc_180073491
0x180073489  movzx   eax, ax
0x18007348c  or      eax, 80070000h
0x180073491  mov     [rsp+68h+arg_5C], 529h
0x18007349c  jmp     loc_18007373B
0x1800734a1  lea     rax, c_rgbLowLabelSid
0x1800734a8  mov     r9d, 1; MandatoryPolicy
0x1800734ae  xor     r8d, r8d; AceFlags
0x1800734b1  mov     [rsp+68h+pLabelSid], rax; pLabelSid
0x1800734b6  mov     edx, r12d; dwAceRevision
0x1800734b9  lea     rcx, [rbx+14h]; pAcl
0x1800734bd  call    cs:__imp_AddMandatoryAce
0x1800734c3  test    eax, eax
0x1800734c5  jnz     short loc_1800734E9
0x1800734c7  call    cs:__imp_GetLastError
0x1800734cd  test    eax, eax
0x1800734cf  jle     short loc_1800734D9
0x1800734d1  movzx   eax, ax
0x1800734d4  or      eax, 80070000h
0x1800734d9  mov     [rsp+68h+arg_5C], 52Dh
0x1800734e4  jmp     loc_18007373B
0x1800734e9  xor     eax, eax
0x1800734eb  test    edi, edi
0x1800734ed  jz      loc_180073745
0x1800734f3  or      [rbx+2], r13w
0x1800734f8  mov     r8d, r12d; dwAclRevision
0x1800734fb  mov     dword ptr [rbx+10h], 30h ; '0'
0x180073502  mov     edx, edi; nAclLength
0x180073504  add     rbx, 30h ; '0'
0x180073508  mov     rcx, rbx; pAcl
0x18007350b  call    cs:__imp_InitializeAcl
0x180073511  test    eax, eax
0x180073513  jnz     short loc_180073537
0x180073515  call    cs:__imp_GetLastError
0x18007351b  test    eax, eax
0x18007351d  jle     short loc_180073527
0x18007351f  movzx   eax, ax
0x180073522  or      eax, 80070000h
0x180073527  mov     [rsp+68h+arg_5C], 53Ah
0x180073532  jmp     loc_18007373B
0x180073537  mov     r9, [rsp+0C8h]; pSid
0x18007353f  mov     edi, 10000000h
0x180073544  mov     r8d, edi; AccessMask
0x180073547  mov     edx, r12d; dwAceRevision
0x18007354a  mov     rcx, rbx; pAcl
0x18007354d  call    cs:__imp_AddAccessAllowedAce
0x180073553  test    eax, eax
0x180073555  jnz     short loc_180073579
0x180073557  call    cs:__imp_GetLastError
0x18007355d  test    eax, eax
0x18007355f  jle     short loc_180073569
0x180073561  movzx   eax, ax
0x180073564  or      eax, 80070000h
0x180073569  mov     [rsp+68h+arg_5C], 53Eh
0x180073574  jmp     loc_18007373B
0x180073579  lea     r9, c_rgbBuiltinAdministratorsSid; pSid
0x180073580  mov     r8d, edi; AccessMask
0x180073583  mov     edx, r12d; dwAceRevision
0x180073586  mov     rcx, rbx; pAcl
0x180073589  call    cs:__imp_AddAccessAllowedAce
0x18007358f  test    eax, eax
0x180073591  jnz     short loc_1800735B5
0x180073593  call    cs:__imp_GetLastError
0x180073599  test    eax, eax
0x18007359b  jle     short loc_1800735A5
0x18007359d  movzx   eax, ax
0x1800735a0  or      eax, 80070000h
0x1800735a5  mov     [rsp+68h+arg_5C], 543h
0x1800735b0  jmp     loc_18007373B
0x1800735b5  lea     r9, c_rgbLocalSystemSid; pSid
0x1800735bc  mov     r8d, edi; AccessMask
0x1800735bf  mov     edx, r12d; dwAceRevision
0x1800735c2  mov     rcx, rbx; pAcl
0x1800735c5  call    cs:__imp_AddAccessAllowedAce
0x1800735cb  test    eax, eax
0x1800735cd  jnz     short loc_1800735F1
0x1800735cf  call    cs:__imp_GetLastError
0x1800735d5  test    eax, eax
0x1800735d7  jle     short loc_1800735E1
0x1800735d9  movzx   eax, ax
0x1800735dc  or      eax, 80070000h
0x1800735e1  mov     [rsp+68h+arg_5C], 548h
0x1800735ec  jmp     loc_18007373B
0x1800735f1  mov     edi, 0A0100000h
0x1800735f6  lea     r9, c_rgbBuiltinAnyPackageSid; pSid
0x1800735fd  mov     r8d, edi; AccessMask
0x180073600  mov     edx, r12d; dwAceRevision
0x180073603  mov     rcx, rbx; pAcl
0x180073606  call    cs:__imp_AddAccessAllowedAce
0x18007360c  test    eax, eax
0x18007360e  jnz     short loc_180073632
0x180073610  call    cs:__imp_GetLastError
0x180073616  test    eax, eax
0x180073618  jle     short loc_180073622
0x18007361a  movzx   eax, ax
0x18007361d  or      eax, 80070000h
0x180073622  mov     [rsp+68h+arg_5C], 54Dh
0x18007362d  jmp     loc_18007373B
0x180073632  lea     r9, c_rgbCapabilityInternetClientSid; pSid
0x180073639  mov     r8d, edi; AccessMask
0x18007363c  mov     edx, r12d; dwAceRevision
0x18007363f  mov     rcx, rbx; pAcl
0x180073642  call    cs:__imp_AddAccessAllowedAce
0x180073648  test    eax, eax
0x18007364a  jnz     short loc_18007366E
0x18007364c  call    cs:__imp_GetLastError
0x180073652  test    eax, eax
0x180073654  jle     short loc_18007365E
0x180073656  movzx   eax, ax
0x180073659  or      eax, 80070000h
0x18007365e  mov     [rsp+68h+arg_5C], 54Eh
0x180073669  jmp     loc_18007373B
0x18007366e  lea     r9, c_rgbCapabilityInternetClientServerSid; pSid
0x180073675  mov     r8d, edi; AccessMask
0x180073678  mov     edx, r12d; dwAceRevision
0x18007367b  mov     rcx, rbx; pAcl
0x18007367e  call    cs:__imp_AddAccessAllowedAce
0x180073684  test    eax, eax
0x180073686  jnz     short loc_1800736AA
0x180073688  call    cs:__imp_GetLastError
0x18007368e  test    eax, eax
0x180073690  jle     short loc_18007369A
0x180073692  movzx   eax, ax
0x180073695  or      eax, 80070000h
0x18007369a  mov     [rsp+68h+arg_5C], 54Fh
0x1800736a5  jmp     loc_18007373B
0x1800736aa  lea     r9, c_rgbCapabilityPrivateNetworkClientServerSid; pSid
0x1800736b1  mov     r8d, edi; AccessMask
0x1800736b4  mov     edx, r12d; dwAceRevision
0x1800736b7  mov     rcx, rbx; pAcl
0x1800736ba  call    cs:__imp_AddAccessAllowedAce
0x1800736c0  test    eax, eax
0x1800736c2  jnz     short loc_1800736E3
0x1800736c4  call    cs:__imp_GetLastError
0x1800736ca  test    eax, eax
0x1800736cc  jle     short loc_1800736D6
0x1800736ce  movzx   eax, ax
0x1800736d1  or      eax, 80070000h
0x1800736d6  mov     [rsp+68h+arg_5C], 550h
0x1800736e1  jmp     short loc_18007373B
0x1800736e3  xor     eax, eax
0x1800736e5  test    r14, r14
0x1800736e8  jz      short loc_180073745
0x1800736ea  test    rsi, rsi
0x1800736ed  jz      short loc_180073745
0x1800736ef  xor     edi, edi
0x1800736f1  xor     eax, eax
0x1800736f3  cmp     edi, r13d
0x1800736f6  jnb     short loc_180073745
0x1800736f8  mov     r9, [r14+rdi*8]; pSid
0x1800736fc  test    r9, r9
0x1800736ff  jz      short loc_18007371A
0x180073701  mov     r8d, [rsi+rdi*4]; AccessMask
0x180073705  test    r8d, r8d
0x180073708  jz      short loc_18007371A
0x18007370a  mov     edx, r12d; dwAceRevision
0x18007370d  mov     rcx, rbx; pAcl
0x180073710  call    cs:__imp_AddAccessAllowedAce
0x180073716  test    eax, eax
0x180073718  jz      short loc_18007371E
0x18007371a  inc     edi
0x18007371c  jmp     short loc_1800736F1
0x18007371e  call    cs:__imp_GetLastError
0x180073724  test    eax, eax
0x180073726  jle     short loc_180073730
0x180073728  movzx   eax, ax
0x18007372b  or      eax, 80070000h
0x180073730  mov     [rsp+68h+arg_5C], 55Bh
0x18007373b  test    eax, eax
0x18007373d  mov     ecx, 8000FFFFh
0x180073742  cmovns  eax, ecx
0x180073745  add     rsp, 30h
0x180073749  pop     r14
0x18007374b  pop     r13
0x18007374d  pop     r12
0x18007374f  pop     rdi
0x180073750  pop     rsi
0x180073751  pop     rbp
0x180073752  pop     rbx
0x180073753  retn
```
