# PAC_ConvertInfo3ToInfo4(_NETLOGON_VALIDATION_SAM_INFO3 *,_UNICODE_STRING *,_UNICODE_STRING *,_NETLOGON_VALIDATION_SAM_INFO4 * *)

- ea: `0x18000ad2c`
- end: `0x18000b052`
- name: `?PAC_ConvertInfo3ToInfo4@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_UNICODE_STRING@@1PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _NETLOGON_VALIDATION_SAM_INFO4 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006ba0`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18000ad2c`
- `0x18000b058`
- `0x180064574`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aefd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b018`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000aeb7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000af36`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000aeb7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000af36`
- `ntdll!RtlLengthRequiredSid` at `0x18000aec7`
- `ntdll!RtlLengthRequiredSid` at `0x18000aec7`
- `ntdll!RtlCopySid` at `0x18000af29`
- `ntdll!RtlCopySid` at `0x18000af29`
- `ntdll!RtlSubAuthoritySid` at `0x18000af45`
- `ntdll!RtlSubAuthoritySid` at `0x18000af45`

## pseudocode

```c
__int64 __fastcall PAC_ConvertInfo3ToInfo4(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a4)
{
  struct _NETLOGON_VALIDATION_SAM_INFO4 **v7; // r12
  unsigned int v8; // r15d
  _OWORD *v9; // rcx
  _DWORD *v10; // rbx
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v11; // rax
  __int64 v12; // rdx
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm1
  int v21; // ecx
  _DWORD *v22; // rax
  unsigned int v23; // edi
  unsigned int v24; // r13d
  __int64 v25; // r12
  __int64 v26; // r14
  ULONG v27; // eax
  void *v28; // rdi
  size_t v29; // r13
  HLOCAL v30; // rax
  PUCHAR v31; // rax
  ULONG v32; // edx
  int v33; // eax
  int v34; // eax
  unsigned __int8 *v35; // r14
  unsigned int i; // esi
  void *v37; // rcx
  unsigned int v39; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int8 *v40; // [rsp+28h] [rbp-D8h] BYREF
  ULONG DestinationSidLength; // [rsp+30h] [rbp-D0h]
  ULONG SubAuthority; // [rsp+34h] [rbp-CCh]
  PSID SourceSid; // [rsp+38h] [rbp-C8h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 **v44; // [rsp+40h] [rbp-C0h]
  _BYTE v45[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v46[164]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+F8h] [rbp-8h]
  unsigned int v48; // [rsp+160h] [rbp+60h]
  _DWORD *v49; // [rsp+168h] [rbp+68h]
  __int128 v50; // [rsp+170h] [rbp+70h]
  __int128 v51; // [rsp+180h] [rbp+80h]

  v44 = a4;
  v7 = a4;
  memset_0(v46, 0, 0x1DCu);
  v8 = 0;
  v9 = v45;
  v10 = 0;
  v11 = a1;
  v12 = 2;
  do
  {
    v13 = *((_OWORD *)v11 + 1);
    *v9 = *(_OWORD *)v11;
    v14 = *((_OWORD *)v11 + 2);
    v9[1] = v13;
    v15 = *((_OWORD *)v11 + 3);
    v9[2] = v14;
    v16 = *((_OWORD *)v11 + 4);
    v9[3] = v15;
    v17 = *((_OWORD *)v11 + 5);
    v9[4] = v16;
    v18 = *((_OWORD *)v11 + 6);
    v9[5] = v17;
    v19 = *((_OWORD *)v11 + 7);
    v11 = (struct _NETLOGON_VALIDATION_SAM_INFO3 *)((char *)v11 + 128);
    v9[6] = v18;
    v9[7] = v19;
    v9 += 8;
    --v12;
  }
  while ( v12 );
  v20 = *((_OWORD *)v11 + 1);
  *v9 = *(_OWORD *)v11;
  v9[1] = v20;
  if ( a2 )
    v51 = (__int128)*a2;
  if ( a3 )
    v50 = (__int128)*a3;
  if ( (*((_DWORD *)a1 + 42) & 0x200) != 0 && (v21 = *((_DWORD *)a1 + 74)) != 0 )
  {
    v8 = v21 + *((_DWORD *)a1 + 68);
    v22 = MIDL_user_allocate(16LL * v8);
    v10 = v22;
    if ( !v22 )
      return (unsigned int)-1073741670;
    memcpy_0(v22, *((const void **)a1 + 35), 16LL * *((unsigned int *)a1 + 68));
    v24 = *((_DWORD *)a1 + 68);
    v25 = 0;
    while ( 1 )
    {
      v39 = v24;
      if ( (unsigned int)v25 >= *((_DWORD *)a1 + 74) )
        break;
      v26 = 2LL * v24;
      v10[4 * v24 + 2] = *(_DWORD *)(*((_QWORD *)a1 + 38) + 8 * v25 + 4);
      LODWORD(v40) = *(_DWORD *)(*((_QWORD *)a1 + 38) + 8 * v25);
      SourceSid = (PSID)*((_QWORD *)a1 + 36);
      SubAuthority = *RtlSubAuthorityCountSid(SourceSid);
      v27 = RtlLengthRequiredSid(SubAuthority + 1);
      DestinationSidLength = v27;
      if ( KerbGlobalPackageState == 1 )
      {
        v28 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(v27);
        if ( !v28 )
          goto LABEL_21;
      }
      else
      {
        v29 = v27;
        v30 = LocalAlloc(0, v27);
        v28 = v30;
        if ( !v30 )
          goto LABEL_21;
        memset_0(v30, 0, v29);
        v24 = v39;
      }
      if ( RtlCopySid(DestinationSidLength, v28, SourceSid) < 0 )
      {
        KerbFree(v28);
LABEL_21:
        v23 = -1073741670;
        *(_QWORD *)&v10[2 * v26] = 0;
        goto LABEL_29;
      }
      v31 = RtlSubAuthorityCountSid(v28);
      v32 = SubAuthority;
      ++*v31;
      ++v24;
      v25 = (unsigned int)(v25 + 1);
      *RtlSubAuthoritySid(v28, v32) = (unsigned int)v40;
      *(_QWORD *)&v10[2 * v26] = v28;
    }
    v7 = v44;
    v33 = v47 | 0x20;
    v48 = v8;
    v49 = v10;
  }
  else
  {
    v33 = v47;
  }
  v40 = 0;
  v47 = v33 & 0xFFFFFDFF;
  v39 = 0;
  v34 = PAC_EncodeValidationInformationEx((struct _NETLOGON_VALIDATION_SAM_INFO4 *)v45, &v40, &v39);
  v35 = v40;
  v23 = v34;
  if ( v34 >= 0 )
    v23 = PAC_DecodeValidationInformationEx(v40, v39, v7);
  if ( v35 )
    KerbFree(v35);
  if ( v10 )
  {
LABEL_29:
    for ( i = *((_DWORD *)a1 + 68); i < v8; ++i )
    {
      v37 = *(void **)&v10[4 * i];
      if ( v37 )
      {
        if ( KerbGlobalPackageState == 1 )
          ((void (*)(void))LsaFunctions->FreeLsaHeap)();
        else
          LocalFree(v37);
      }
    }
    KerbFree(v10);
  }
  return v23;
}

```

## disassembly

```asm
0x18000ad2c  push    rbp
0x18000ad2e  push    rbx
0x18000ad2f  push    rsi
0x18000ad30  push    rdi
0x18000ad31  push    r12
0x18000ad33  push    r13
0x18000ad35  push    r14
0x18000ad37  push    r15
0x18000ad39  lea     rbp, [rsp-148h]
0x18000ad41  sub     rsp, 248h
0x18000ad48  mov     rax, cs:__security_cookie
0x18000ad4f  xor     rax, rsp
0x18000ad52  mov     [rbp+180h+var_50], rax
0x18000ad59  mov     rdi, r8
0x18000ad5c  mov     [rsp+280h+var_240], r9
0x18000ad61  mov     r14, rdx
0x18000ad64  mov     rsi, rcx
0x18000ad67  xor     edx, edx; Val
0x18000ad69  lea     rcx, [rsp+280h+var_22C]; void *
0x18000ad6e  mov     r8d, 1DCh; Size
0x18000ad74  mov     r12, r9
0x18000ad77  call    memset_0
0x18000ad7c  xor     r15d, r15d
0x18000ad7f  lea     rcx, [rsp+280h+var_230]
0x18000ad84  xor     ebx, ebx
0x18000ad86  mov     rax, rsi
0x18000ad89  lea     edx, [rbx+2]
0x18000ad8c  lea     r8d, [rdx+7Eh]
0x18000ad90  movups  xmm0, xmmword ptr [rax]
0x18000ad93  movups  xmm1, xmmword ptr [rax+10h]
0x18000ad97  movups  xmmword ptr [rcx], xmm0
0x18000ad9a  movups  xmm0, xmmword ptr [rax+20h]
0x18000ad9e  movups  xmmword ptr [rcx+10h], xmm1
0x18000ada2  movups  xmm1, xmmword ptr [rax+30h]
0x18000ada6  movups  xmmword ptr [rcx+20h], xmm0
0x18000adaa  movups  xmm0, xmmword ptr [rax+40h]
0x18000adae  movups  xmmword ptr [rcx+30h], xmm1
0x18000adb2  movups  xmm1, xmmword ptr [rax+50h]
0x18000adb6  movups  xmmword ptr [rcx+40h], xmm0
0x18000adba  movups  xmm0, xmmword ptr [rax+60h]
0x18000adbe  movups  xmmword ptr [rcx+50h], xmm1
0x18000adc2  movups  xmm1, xmmword ptr [rax+70h]
0x18000adc6  add     rax, r8
0x18000adc9  movups  xmmword ptr [rcx+60h], xmm0
0x18000adcd  movups  xmmword ptr [rcx+70h], xmm1
0x18000add1  add     rcx, r8
0x18000add4  sub     rdx, 1
0x18000add8  jnz     short loc_18000AD90
0x18000adda  movups  xmm0, xmmword ptr [rax]
0x18000addd  movups  xmm1, xmmword ptr [rax+10h]
0x18000ade1  movups  xmmword ptr [rcx], xmm0
0x18000ade4  movups  xmmword ptr [rcx+10h], xmm1
0x18000ade8  test    r14, r14
0x18000adeb  jz      short loc_18000ADF9
0x18000aded  movups  xmm0, xmmword ptr [r14]
0x18000adf1  movdqu  [rbp+180h+var_100], xmm0
0x18000adf9  test    rdi, rdi
0x18000adfc  jz      short loc_18000AE06
0x18000adfe  movups  xmm0, xmmword ptr [rdi]
0x18000ae01  movdqu  [rbp+180h+var_110], xmm0
0x18000ae06  test    dword ptr [rsi+0A8h], 200h
0x18000ae10  jz      loc_18000AF87
0x18000ae16  mov     ecx, [rsi+128h]
0x18000ae1c  test    ecx, ecx
0x18000ae1e  jz      loc_18000AF87
0x18000ae24  mov     r15d, [rsi+110h]
0x18000ae2b  add     r15d, ecx
0x18000ae2e  mov     ecx, r15d
0x18000ae31  shl     rcx, 4; size
0x18000ae35  call    MIDL_user_allocate
0x18000ae3a  mov     rbx, rax
0x18000ae3d  test    rax, rax
0x18000ae40  jnz     short loc_18000AE4C
0x18000ae42  mov     edi, 0C000009Ah
0x18000ae47  jmp     loc_18000B02D
0x18000ae4c  mov     r8d, [rsi+110h]
0x18000ae53  mov     rcx, rbx; void *
0x18000ae56  mov     rdx, [rsi+118h]; Src
0x18000ae5d  shl     r8, 4; Size
0x18000ae61  call    memcpy_0
0x18000ae66  mov     r13d, [rsi+110h]
0x18000ae6d  xor     r12d, r12d
0x18000ae70  mov     [rsp+280h+var_260], r13d
0x18000ae75  cmp     r12d, [rsi+128h]
0x18000ae7c  jnb     loc_18000AF72
0x18000ae82  mov     rax, [rsi+130h]
0x18000ae89  mov     r14d, r13d
0x18000ae8c  add     r14, r14
0x18000ae8f  mov     ecx, [rax+r12*8+4]
0x18000ae94  mov     [rbx+r14*8+8], ecx
0x18000ae99  mov     rax, [rsi+130h]
0x18000aea0  mov     eax, [rax+r12*8]
0x18000aea4  mov     dword ptr [rsp+280h+var_258], eax
0x18000aea8  mov     rax, [rsi+120h]
0x18000aeaf  mov     rcx, rax; Sid
0x18000aeb2  mov     [rsp+280h+SourceSid], rax
0x18000aeb7  call    cs:__imp_RtlSubAuthorityCountSid
0x18000aebd  movzx   eax, byte ptr [rax]
0x18000aec0  mov     [rsp+280h+SubAuthority], eax
0x18000aec4  lea     ecx, [rax+1]; SubAuthorityCount
0x18000aec7  call    cs:__imp_RtlLengthRequiredSid
0x18000aecd  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1
0x18000aed4  mov     edx, eax; uBytes
0x18000aed6  mov     [rsp+280h+DestinationSidLength], edx
0x18000aeda  jnz     short loc_18000AEF8
0x18000aedc  mov     rcx, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA
0x18000aee3  mov     rax, [rcx+28h]
0x18000aee7  mov     ecx, edx
0x18000aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeee  mov     rdi, rax
0x18000aef1  test    rax, rax
0x18000aef4  jz      short loc_18000AF65
0x18000aef6  jmp     short loc_18000AF1D
0x18000aef8  xor     ecx, ecx; uFlags
0x18000aefa  mov     r13, rdx
0x18000aefd  call    cs:__imp_LocalAlloc
0x18000af03  mov     rdi, rax
0x18000af06  test    rax, rax
0x18000af09  jz      short loc_18000AF65
0x18000af0b  mov     r8, r13; Size
0x18000af0e  xor     edx, edx; Val
0x18000af10  mov     rcx, rax; void *
0x18000af13  call    memset_0
0x18000af18  mov     r13d, [rsp+280h+var_260]
0x18000af1d  mov     r8, [rsp+280h+SourceSid]; SourceSid
0x18000af22  mov     rdx, rdi; DestinationSid
0x18000af25  mov     ecx, [rsp+280h+DestinationSidLength]; DestinationSidLength
0x18000af29  call    cs:__imp_RtlCopySid
0x18000af2f  mov     rcx, rdi; Sid
0x18000af32  test    eax, eax
0x18000af34  js      short loc_18000AF60
0x18000af36  call    cs:__imp_RtlSubAuthorityCountSid
0x18000af3c  mov     edx, [rsp+280h+SubAuthority]; SubAuthority
0x18000af40  mov     rcx, rdi; Sid
0x18000af43  inc     byte ptr [rax]
0x18000af45  call    cs:__imp_RtlSubAuthoritySid
0x18000af4b  mov     ecx, dword ptr [rsp+280h+var_258]
0x18000af4f  inc     r13d
0x18000af52  inc     r12d
0x18000af55  mov     [rax], ecx
0x18000af57  mov     [rbx+r14*8], rdi
0x18000af5b  jmp     loc_18000AE70
0x18000af60  call    KerbFree
0x18000af65  xor     eax, eax
0x18000af67  mov     edi, 0C000009Ah
0x18000af6c  mov     [rbx+r14*8], rax
0x18000af70  jmp     short loc_18000AFE4
0x18000af72  mov     eax, [rbp+180h+var_188]
0x18000af75  mov     r12, [rsp+280h+var_240]
0x18000af7a  or      eax, 20h
0x18000af7d  mov     [rbp+180h+var_120], r15d
0x18000af81  mov     [rbp+180h+var_118], rbx
0x18000af85  jmp     short loc_18000AF8A
0x18000af87  mov     eax, [rbp+180h+var_188]
0x18000af8a  btr     eax, 9
0x18000af8e  mov     [rsp+280h+var_258], 0
0x18000af97  lea     r8, [rsp+280h+var_260]; unsigned int *
0x18000af9c  mov     [rbp+180h+var_188], eax
0x18000af9f  lea     rdx, [rsp+280h+var_258]; unsigned __int8 **
0x18000afa4  mov     [rsp+280h+var_260], 0
0x18000afac  lea     rcx, [rsp+280h+var_230]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x18000afb1  call    ?PAC_EncodeValidationInformationEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z
0x18000afb6  mov     r14, [rsp+280h+var_258]
0x18000afbb  mov     edi, eax
0x18000afbd  test    eax, eax
0x18000afbf  js      short loc_18000AFD2
0x18000afc1  mov     edx, [rsp+280h+var_260]; unsigned int
0x18000afc5  mov     r8, r12; struct _NETLOGON_VALIDATION_SAM_INFO4 **
0x18000afc8  mov     rcx, r14; unsigned __int8 *
0x18000afcb  call    ?PAC_DecodeValidationInformationEx@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z
0x18000afd0  mov     edi, eax
0x18000afd2  test    r14, r14
0x18000afd5  jz      short loc_18000AFDF
0x18000afd7  mov     rcx, r14
0x18000afda  call    KerbFree
0x18000afdf  test    rbx, rbx
0x18000afe2  jz      short loc_18000B02D
0x18000afe4  mov     esi, [rsi+110h]
0x18000afea  mov     r14, rbx
0x18000afed  jmp     short loc_18000B020
0x18000afef  mov     eax, esi
0x18000aff1  add     rax, rax
0x18000aff4  mov     rcx, [r14+rax*8]; hMem
0x18000aff8  test    rcx, rcx
0x18000affb  jz      short loc_18000B01E
0x18000affd  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1
0x18000b004  jnz     short loc_18000B018
0x18000b006  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA
0x18000b00d  mov     rax, [rax+30h]
0x18000b011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b016  jmp     short loc_18000B01E
0x18000b018  call    cs:__imp_LocalFree
0x18000b01e  inc     esi
0x18000b020  cmp     esi, r15d
0x18000b023  jb      short loc_18000AFEF
0x18000b025  mov     rcx, rbx
0x18000b028  call    KerbFree
0x18000b02d  mov     eax, edi
0x18000b02f  mov     rcx, [rbp+180h+var_50]
0x18000b036  xor     rcx, rsp; StackCookie
0x18000b039  call    __security_check_cookie
0x18000b03e  add     rsp, 248h
0x18000b045  pop     r15
0x18000b047  pop     r14
0x18000b049  pop     r13
0x18000b04b  pop     r12
0x18000b04d  pop     rdi
0x18000b04e  pop     rsi
0x18000b04f  pop     rbx
0x18000b050  pop     rbp
0x18000b051  retn
```
