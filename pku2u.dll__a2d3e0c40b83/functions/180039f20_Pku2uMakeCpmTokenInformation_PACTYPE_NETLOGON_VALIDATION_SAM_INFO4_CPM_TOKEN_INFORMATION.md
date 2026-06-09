# Pku2uMakeCpmTokenInformation(_PACTYPE *,_NETLOGON_VALIDATION_SAM_INFO4 *,CPM_TOKEN_INFORMATION * *)

- ea: `0x180039f20`
- end: `0x18003a4d2`
- name: `?Pku2uMakeCpmTokenInformation@@YAJPEAU_PACTYPE@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAUCPM_TOKEN_INFORMATION@@@Z`
- size: `1458`
- prototype: `__int64 __fastcall(struct _PACTYPE *, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct CPM_TOKEN_INFORMATION **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001bf0`

## callees

- `0x180018870`
- `0x18001a524`
- `0x180023cb8`
- `0x180023ce0`
- `0x180038a30`
- `0x180038e0c`
- `0x180039f20`
- `0x18003ab04`
- `0x18003ac00`
- `0x180044f8c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18003a37a`
- `ntdll!RtlCopySid` at `0x18003a3e3`
- `ntdll!RtlCopySid` at `0x18003a37a`
- `ntdll!RtlCopySid` at `0x18003a3e3`
- `ntdll!RtlLengthSid` at `0x18003a120`
- `ntdll!RtlLengthSid` at `0x18003a15b`
- `ntdll!RtlLengthSid` at `0x18003a190`
- `ntdll!RtlLengthSid` at `0x18003a1c8`
- `ntdll!RtlLengthSid` at `0x18003a1d3`
- `ntdll!RtlLengthSid` at `0x18003a363`
- `ntdll!RtlLengthSid` at `0x18003a3cb`
- `ntdll!RtlLengthSid` at `0x18003a120`
- `ntdll!RtlLengthSid` at `0x18003a15b`
- `ntdll!RtlLengthSid` at `0x18003a190`
- `ntdll!RtlLengthSid` at `0x18003a1c8`
- `ntdll!RtlLengthSid` at `0x18003a1d3`
- `ntdll!RtlLengthSid` at `0x18003a363`
- `ntdll!RtlLengthSid` at `0x18003a3cb`

## pseudocode

```c
__int64 __fastcall Pku2uMakeCpmTokenInformation(
        struct _PACTYPE *a1,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a2,
        struct CPM_TOKEN_INFORMATION **a3)
{
  struct _PACTYPE *v5; // rcx
  struct _PAC_INFO_BUFFER *v6; // r8
  struct _PAC_INFO_BUFFER *v7; // r13
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  struct _PACTYPE *v10; // rcx
  struct _PAC_INFO_BUFFER *v11; // r8
  struct _PAC_INFO_BUFFER *v12; // r15
  int v14; // ebx
  struct _PAC_INFO_BUFFER *v15; // r8
  struct _PAC_INFO_BUFFER *v16; // rax
  ULONG v17; // r14d
  unsigned int v18; // ebx
  PSID *v19; // rdi
  int v20; // eax
  unsigned int v21; // r15d
  unsigned int *v22; // r12
  ULONG v23; // ecx
  void *v24; // rbx
  ULONG v25; // edi
  ULONG v26; // edx
  ULONG v27; // ecx
  _QWORD *v28; // rax
  _QWORD *v29; // r15
  char *v30; // r14
  void *v31; // rcx
  void *v32; // rdi
  char *v33; // r14
  unsigned int i; // ebx
  unsigned int v35; // r12d
  ULONG v36; // eax
  __int64 v37; // rbx
  ULONG v38; // eax
  __int64 v39; // rbx
  struct _PAC_INFO_BUFFER *v40; // rax
  struct _PAC_TOKEN_SECURITY_ATTRIBUTES *v41; // rax
  struct _SECURITY_CAPABILITIES *v42; // rcx
  unsigned int Size; // [rsp+20h] [rbp-30h]
  struct _PAC_TOKEN_SECURITY_ATTRIBUTES *v44; // [rsp+28h] [rbp-28h] BYREF
  struct _SECURITY_CAPABILITIES *v45; // [rsp+30h] [rbp-20h] BYREF
  struct _PAC_INFO_BUFFER *v46; // [rsp+38h] [rbp-18h]
  void *Src; // [rsp+40h] [rbp-10h]
  struct _PAC_INFO_BUFFER *v48; // [rsp+48h] [rbp-8h]
  _QWORD *v50; // [rsp+A8h] [rbp+58h] BYREF

  v7 = PAC_Find(a1, 0xDu, (struct _PAC_INFO_BUFFER *)a3);
  if ( !v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 3221225701LL;
    v9 = 63;
LABEL_13:
    WPP_SF_(v8[2], v9, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
    return 3221225701LL;
  }
  v48 = PAC_Find(v5, 0x100u, v6);
  if ( !v48 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 3221225701LL;
    v9 = 64;
    goto LABEL_13;
  }
  v12 = PAC_Find(v10, 0x101u, v11);
  v46 = v12;
  if ( !v12 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 3221225701LL;
    v9 = 65;
    goto LABEL_13;
  }
  Src = (void *)*((_QWORD *)v7 + 1);
  Size = *((_DWORD *)v7 + 1);
  v45 = 0;
  v14 = Pku2uUnmarshalTokenSecurityCapabilitiesBuffer(*((char **)v12 + 1), *((_DWORD *)v12 + 1), &v45);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)v14);
    goto LABEL_65;
  }
  v16 = PAC_Find(a1, 0x102u, v15);
  if ( v16 )
  {
    v44 = 0;
    if ( (int)Pku2uUnmarshalTokenSecurityAttributesBuffer(*((char **)v16 + 1), *((_DWORD *)v16 + 1), &v44) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
      wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v44);
      goto LABEL_23;
    }
    v17 = 128;
    v18 = *((_DWORD *)a2 + 39);
    LODWORD(v50) = v18;
    v19 = (PSID *)((char *)a2 + 224);
    if ( v18 )
      v17 = v18 * (RtlLengthSid(*v19) + 4) + 128;
    if ( (*((_BYTE *)a2 + 168) & 0x20) != 0 )
    {
      v20 = *((_DWORD *)a2 + 68);
      v18 += v20;
      LODWORD(v50) = v18;
      v21 = 0;
      if ( v20 )
      {
        do
          v17 += RtlLengthSid(*(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v21++));
        while ( v21 < *((_DWORD *)a2 + 68) );
        v19 = (PSID *)((char *)a2 + 224);
      }
      v12 = v46;
    }
    v22 = (unsigned int *)((char *)a2 + 148);
    if ( *((_DWORD *)a2 + 37) )
    {
      v23 = v17 + 2 * (RtlLengthSid(*((PSID *)a2 + 28)) + 4);
    }
    else
    {
      if ( !*((_DWORD *)a2 + 68) )
      {
LABEL_39:
        wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v44);
        v14 = -1073741232;
        goto LABEL_65;
      }
      v24 = (void *)**((_QWORD **)a2 + 35);
      v25 = RtlLengthSid(*v19);
      v23 = v25 + v17 + RtlLengthSid(v24) + 4;
      v22 = (unsigned int *)((char *)a2 + 148);
      v18 = (unsigned int)v50;
    }
    v26 = v23 + 16 * v18;
    v27 = v26 - 16;
    if ( Src && Size )
    {
      v27 = v26 + ((Size + 3) & 0xFFFFFFFC);
      v22 = (unsigned int *)((char *)a2 + 148);
    }
    v28 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v27 + *((_DWORD *)v48 + 1) + *((_DWORD *)v12 + 1));
    v29 = v28;
    v50 = v28;
    if ( !v28 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v50);
      wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v44);
      v14 = -1073741670;
      goto LABEL_65;
    }
    v28[3] = v28 + 13;
    *((_DWORD *)v28 + 26) = 0;
    v30 = (char *)&v28[2 * v18 + 14];
    v31 = Src;
    if ( Src && Size )
    {
      v28[8] = v30;
      v32 = v30 + 16;
      *((_QWORD *)v30 + 1) = v30 + 16;
      *(_DWORD *)v30 = Size;
      v30 += Size + 16;
      memcpy_0(v32, v31, Size);
    }
    *(_DWORD *)v29 = *((_DWORD *)a2 + 4);
    *((_DWORD *)v29 + 1) = *((_DWORD *)a2 + 5);
    if ( *((_DWORD *)a2 + 37) )
    {
      v29[1] = v30;
      v30 += KerbCopyDomainRelativeSid(v30, *((PSID *)a2 + 28), *v22);
    }
    v29[4] = v30;
    v33 = &v30[KerbCopyDomainRelativeSid(v30, *((PSID *)a2 + 28), *((_DWORD *)a2 + 38))];
    for ( i = 0; i < *((_DWORD *)a2 + 39); ++i )
    {
      *(_DWORD *)(v29[3] + 16 * (*(unsigned int *)v29[3] + 1LL)) = *(_DWORD *)(*((_QWORD *)a2 + 20) + 8LL * i + 4);
      *(_QWORD *)(v29[3] + 16LL * *(unsigned int *)v29[3] + 8) = v33;
      v33 += KerbCopyDomainRelativeSid(v33, *((PSID *)a2 + 28), *(_DWORD *)(*((_QWORD *)a2 + 20) + 8LL * i));
      ++*(_DWORD *)v29[3];
    }
    if ( (*((_BYTE *)a2 + 168) & 0x20) != 0 )
    {
      v35 = 0;
      if ( !v29[1] )
      {
        v29[1] = v33;
        v36 = RtlLengthSid(**((PSID **)a2 + 35));
        v37 = v36;
        RtlCopySid(v36, v33, **((PSID **)a2 + 35));
        v33 += v37;
        v35 = 1;
      }
      for ( ; v35 < *((_DWORD *)a2 + 68); ++v35 )
      {
        *(_DWORD *)(v29[3] + 16 * (*(unsigned int *)v29[3] + 1LL)) = *(_DWORD *)(*((_QWORD *)a2 + 35) + 16LL * v35 + 8);
        *(_QWORD *)(v29[3] + 16LL * *(unsigned int *)v29[3] + 8) = v33;
        v38 = RtlLengthSid(*(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v35));
        v39 = v38;
        RtlCopySid(v38, v33, *(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v35));
        v33 += v39;
        ++*(_DWORD *)v29[3];
      }
    }
    if ( *((_DWORD *)v7 + 1) )
    {
      v29[8] = v33;
      memcpy_0(v33, *((const void **)v7 + 1), *((unsigned int *)v7 + 1));
      v33 += *((unsigned int *)v7 + 1);
    }
    v40 = v48;
    if ( *((_DWORD *)v48 + 1) )
    {
      v29[5] = v33;
      memcpy_0(v33, *((const void **)v40 + 1), *((unsigned int *)v40 + 1));
    }
    if ( v29[1] )
    {
      v29[6] = 0;
      v29[7] = 0;
      v50 = 0;
      *a3 = (struct CPM_TOKEN_INFORMATION *)v29;
      v41 = v44;
      v44 = 0;
      v29[12] = v41;
      v42 = v45;
      v45 = 0;
      *((_QWORD *)*a3 + 11) = v42;
      wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v50);
      wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v44);
      v14 = 0;
      goto LABEL_65;
    }
    wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v50);
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
LABEL_23:
  v14 = -1073741595;
LABEL_65:
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v45);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180039f20  mov     [rsp-38h+arg_0], rbx
0x180039f25  mov     [rsp-38h+arg_10], r8
0x180039f2a  push    rbp
0x180039f2b  push    rsi
0x180039f2c  push    rdi
0x180039f2d  push    r12
0x180039f2f  push    r13
0x180039f31  push    r14
0x180039f33  push    r15
0x180039f35  mov     rbp, rsp
0x180039f38  sub     rsp, 50h
0x180039f3c  mov     rsi, rdx
0x180039f3f  mov     rdi, rcx
0x180039f42  mov     edx, 0Dh; unsigned int
0x180039f47  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180039f4c  mov     r13, rax
0x180039f4f  test    rax, rax
0x180039f52  jnz     short loc_180039F77
0x180039f54  lea     rax, WPP_GLOBAL_Control
0x180039f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f62  cmp     rcx, rax
0x180039f65  jz      loc_180039FED
0x180039f6b  test    byte ptr [rcx+1Ch], 1
0x180039f6f  jz      short loc_180039FED
0x180039f71  lea     edx, [r13+3Fh]
0x180039f75  jmp     short loc_180039FDD
0x180039f77  mov     edx, 100h; unsigned int
0x180039f7c  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180039f81  mov     [rbp+var_8], rax
0x180039f85  test    rax, rax
0x180039f88  jnz     short loc_180039FAA
0x180039f8a  lea     rax, WPP_GLOBAL_Control
0x180039f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f98  cmp     rcx, rax
0x180039f9b  jz      short loc_180039FED
0x180039f9d  test    byte ptr [rcx+1Ch], 1
0x180039fa1  jz      short loc_180039FED
0x180039fa3  mov     edx, 40h ; '@'
0x180039fa8  jmp     short loc_180039FDD
0x180039faa  mov     edx, 101h; unsigned int
0x180039faf  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180039fb4  mov     r15, rax
0x180039fb7  mov     [rbp+var_18], rax
0x180039fbb  test    rax, rax
0x180039fbe  jnz     short loc_180039FF7
0x180039fc0  lea     rax, WPP_GLOBAL_Control
0x180039fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180039fce  cmp     rcx, rax
0x180039fd1  jz      short loc_180039FED
0x180039fd3  test    byte ptr [rcx+1Ch], 1
0x180039fd7  jz      short loc_180039FED
0x180039fd9  lea     edx, [r15+41h]
0x180039fdd  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180039fe4  mov     rcx, [rcx+10h]
0x180039fe8  call    WPP_SF_
0x180039fed  mov     eax, 0C00000E5h
0x180039ff2  jmp     loc_18003A4BA
0x180039ff7  mov     rax, [r13+8]
0x180039ffb  mov     [rbp+Src], rax
0x180039fff  mov     eax, [r13+4]
0x18003a003  mov     dword ptr [rbp+Size], eax
0x18003a006  mov     [rbp+var_20], 0
0x18003a00e  lea     r8, [rbp+var_20]; struct _SECURITY_CAPABILITIES **
0x18003a012  mov     edx, [r15+4]; unsigned int
0x18003a016  mov     rcx, [r15+8]; unsigned __int8 *
0x18003a01a  call    ?Pku2uUnmarshalTokenSecurityCapabilitiesBuffer@@YAJPEAEKPEAPEAU_SECURITY_CAPABILITIES@@@Z; Pku2uUnmarshalTokenSecurityCapabilitiesBuffer(uchar *,ulong,_SECURITY_CAPABILITIES * *)
0x18003a01f  mov     ebx, eax
0x18003a021  test    eax, eax
0x18003a023  jns     short loc_18003A063
0x18003a025  lea     rax, WPP_GLOBAL_Control
0x18003a02c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a033  cmp     rcx, rax
0x18003a036  jz      loc_18003A4AF
0x18003a03c  test    byte ptr [rcx+1Ch], 1
0x18003a040  jz      loc_18003A4AF
0x18003a046  mov     edx, 42h ; 'B'
0x18003a04b  mov     r9d, ebx
0x18003a04e  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18003a055  mov     rcx, [rcx+10h]
0x18003a059  call    WPP_SF_d
0x18003a05e  jmp     loc_18003A4AF
0x18003a063  mov     edx, 102h; unsigned int
0x18003a068  mov     rcx, rdi; struct _PACTYPE *
0x18003a06b  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18003a070  test    rax, rax
0x18003a073  jnz     short loc_18003A0AD
0x18003a075  lea     rax, WPP_GLOBAL_Control
0x18003a07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a083  cmp     rcx, rax
0x18003a086  jz      short loc_18003A0A3
0x18003a088  test    byte ptr [rcx+1Ch], 1
0x18003a08c  jz      short loc_18003A0A3
0x18003a08e  mov     edx, 43h ; 'C'
0x18003a093  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18003a09a  mov     rcx, [rcx+10h]
0x18003a09e  call    WPP_SF_
0x18003a0a3  mov     ebx, 0C00000E5h
0x18003a0a8  jmp     loc_18003A4AF
0x18003a0ad  mov     [rbp+var_28], 0
0x18003a0b5  lea     r8, [rbp+var_28]; struct _PAC_TOKEN_SECURITY_ATTRIBUTES **
0x18003a0b9  mov     edx, [rax+4]; unsigned int
0x18003a0bc  mov     rcx, [rax+8]; unsigned __int8 *
0x18003a0c0  call    ?Pku2uUnmarshalTokenSecurityAttributesBuffer@@YAJPEAEKPEAPEAU_PAC_TOKEN_SECURITY_ATTRIBUTES@@@Z; Pku2uUnmarshalTokenSecurityAttributesBuffer(uchar *,ulong,_PAC_TOKEN_SECURITY_ATTRIBUTES * *)
0x18003a0c5  test    eax, eax
0x18003a0c7  jns     short loc_18003A103
0x18003a0c9  lea     rax, WPP_GLOBAL_Control
0x18003a0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0d7  cmp     rcx, rax
0x18003a0da  jz      short loc_18003A0F8
0x18003a0dc  test    byte ptr [rcx+1Ch], 1
0x18003a0e0  jz      short loc_18003A0F8
0x18003a0e2  mov     edx, 44h ; 'D'
0x18003a0e7  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x18003a0ee  mov     rcx, [rcx+10h]
0x18003a0f2  call    WPP_SF_
0x18003a0f7  nop
0x18003a0f8  lea     rcx, [rbp+var_28]
0x18003a0fc  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003a101  jmp     short loc_18003A0A3
0x18003a103  mov     r14d, 80h
0x18003a109  mov     ebx, [rsi+9Ch]
0x18003a10f  mov     dword ptr [rbp+arg_18], ebx
0x18003a112  lea     rdi, [rsi+0E0h]
0x18003a119  test    ebx, ebx
0x18003a11b  jz      short loc_18003A12F
0x18003a11d  mov     rcx, [rdi]; Sid
0x18003a120  call    cs:__imp_RtlLengthSid
0x18003a126  add     eax, 4
0x18003a129  imul    eax, ebx
0x18003a12c  add     r14d, eax
0x18003a12f  test    byte ptr [rsi+0A8h], 20h
0x18003a136  jz      short loc_18003A17B
0x18003a138  mov     eax, [rsi+110h]
0x18003a13e  add     ebx, eax
0x18003a140  mov     dword ptr [rbp+arg_18], ebx
0x18003a143  xor     r15d, r15d
0x18003a146  test    eax, eax
0x18003a148  jz      short loc_18003A177
0x18003a14a  mov     eax, r15d
0x18003a14d  add     rax, rax
0x18003a150  mov     rcx, [rsi+118h]
0x18003a157  mov     rcx, [rcx+rax*8]; Sid
0x18003a15b  call    cs:__imp_RtlLengthSid
0x18003a161  add     r14d, eax
0x18003a164  inc     r15d
0x18003a167  cmp     r15d, [rsi+110h]
0x18003a16e  jb      short loc_18003A14A
0x18003a170  lea     rdi, [rsi+0E0h]
0x18003a177  mov     r15, [rbp+var_18]
0x18003a17b  lea     r12, [rsi+94h]
0x18003a182  cmp     dword ptr [r12], 0
0x18003a187  jz      short loc_18003A19F
0x18003a189  mov     rcx, [rsi+0E0h]; Sid
0x18003a190  call    cs:__imp_RtlLengthSid
0x18003a196  lea     ecx, [rax+4]
0x18003a199  lea     ecx, [r14+rcx*2]
0x18003a19d  jmp     short loc_18003A1EC
0x18003a19f  cmp     dword ptr [rsi+110h], 0
0x18003a1a6  ja      short loc_18003A1BB
0x18003a1a8  lea     rcx, [rbp+var_28]
0x18003a1ac  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x18003a1b1  mov     ebx, 0C0000250h
0x18003a1b6  jmp     loc_18003A4AF
0x18003a1bb  mov     rax, [rsi+118h]
0x18003a1c2  mov     rbx, [rax]
0x18003a1c5  mov     rcx, [rdi]; Sid
0x18003a1c8  call    cs:__imp_RtlLengthSid
0x18003a1ce  mov     edi, eax
0x18003a1d0  mov     rcx, rbx; Sid
0x18003a1d3  call    cs:__imp_RtlLengthSid
0x18003a1d9  lea     ecx, [r14+rax]
0x18003a1dd  add     ecx, 4
0x18003a1e0  add     ecx, edi
0x18003a1e2  lea     r12, [rsi+94h]
0x18003a1e9  mov     ebx, dword ptr [rbp+arg_18]
0x18003a1ec  mov     edx, ebx
0x18003a1ee  shl     edx, 4
0x18003a1f1  add     edx, ecx
0x18003a1f3  lea     ecx, [rdx-10h]
0x18003a1f6  xor     edi, edi
0x18003a1f8  cmp     [rbp+Src], rdi
0x18003a1fc  jz      short loc_18003A214
0x18003a1fe  mov     eax, dword ptr [rbp+Size]
0x18003a201  test    eax, eax
0x18003a203  jz      short loc_18003A214
0x18003a205  lea     ecx, [rax+3]
0x18003a208  and     ecx, 0FFFFFFFCh
0x18003a20b  add     ecx, edx
0x18003a20d  lea     r12, [rsi+94h]
0x18003a214  mov     eax, [r15+4]
0x18003a218  mov     rdx, [rbp+var_8]
0x18003a21c  add     eax, [rdx+4]
0x18003a21f  lea     edx, [rcx+rax]; unsigned __int64
0x18003a222  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003a229  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18003a22e  mov     r15, rax
0x18003a231  mov     [rbp+arg_18], rax
0x18003a235  test    rax, rax
0x18003a238  jz      loc_18003A497
0x18003a23e  lea     r8, [rax+68h]
0x18003a242  mov     [rax+18h], r8
0x18003a246  mov     [r8], edi
0x18003a249  mov     r14d, ebx
0x18003a24c  shl     r14, 4
0x18003a250  add     r14, 8
0x18003a254  add     r14, r8
0x18003a257  mov     rcx, [rbp+Src]
0x18003a25b  test    rcx, rcx
0x18003a25e  jz      short loc_18003A28A
0x18003a260  mov     eax, dword ptr [rbp+Size]
0x18003a263  test    eax, eax
0x18003a265  jz      short loc_18003A28A
0x18003a267  mov     [r15+40h], r14
0x18003a26b  lea     rdi, [r14+10h]
0x18003a26f  mov     [r14+8], rdi
0x18003a273  mov     [r14], eax
0x18003a276  lea     r14, [rax+rdi]
0x18003a27a  mov     r8d, eax; Size
0x18003a27d  mov     rdx, rcx; Src
0x18003a280  mov     rcx, rdi; void *
0x18003a283  call    memcpy_0
0x18003a288  xor     edi, edi
0x18003a28a  mov     eax, [rsi+10h]
0x18003a28d  mov     [r15], eax
0x18003a290  mov     eax, [rsi+14h]
0x18003a293  mov     [r15+4], eax
0x18003a297  cmp     [rsi+94h], edi
0x18003a29d  jz      short loc_18003A2BB
0x18003a29f  mov     [r15+8], r14
0x18003a2a3  mov     r8d, [r12]; unsigned int
0x18003a2a7  mov     rdx, [rsi+0E0h]; SourceSid
0x18003a2ae  mov     rcx, r14; Sid
0x18003a2b1  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x18003a2b6  mov     eax, eax
0x18003a2b8  add     r14, rax
0x18003a2bb  mov     [r15+20h], r14
0x18003a2bf  mov     r8d, [rsi+98h]; unsigned int
0x18003a2c6  mov     rdx, [rsi+0E0h]; SourceSid
0x18003a2cd  mov     rcx, r14; Sid
0x18003a2d0  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x18003a2d5  mov     eax, eax
0x18003a2d7  add     r14, rax
0x18003a2da  mov     ebx, edi
0x18003a2dc  cmp     [rsi+9Ch], edi
0x18003a2e2  jbe     short loc_18003A33F
0x18003a2e4  mov     r9d, ebx
0x18003a2e7  mov     rdx, [r15+18h]
0x18003a2eb  mov     rax, [rsi+0A0h]
0x18003a2f2  mov     ecx, [rdx]
0x18003a2f4  inc     rcx
0x18003a2f7  add     rcx, rcx
0x18003a2fa  mov     eax, [rax+r9*8+4]
0x18003a2ff  mov     [rdx+rcx*8], eax
0x18003a302  mov     rcx, [r15+18h]
0x18003a306  mov     eax, [rcx]
0x18003a308  add     rax, rax
0x18003a30b  mov     [rcx+rax*8+8], r14
0x18003a310  mov     r8, [rsi+0A0h]
0x18003a317  mov     r8d, [r8+r9*8]; unsigned int
0x18003a31b  mov     rdx, [rsi+0E0h]; SourceSid
0x18003a322  mov     rcx, r14; Sid
0x18003a325  call    ?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z; KerbCopyDomainRelativeSid(void *,void *,ulong)
0x18003a32a  mov     eax, eax
0x18003a32c  add     r14, rax
0x18003a32f  mov     rax, [r15+18h]
0x18003a333  inc     dword ptr [rax]
0x18003a335  inc     ebx
0x18003a337  cmp     ebx, [rsi+9Ch]
0x18003a33d  jb      short loc_18003A2E4
0x18003a33f  test    byte ptr [rsi+0A8h], 20h
0x18003a346  jz      loc_18003A400
0x18003a34c  mov     r12d, edi
0x18003a34f  cmp     [r15+8], rdi
0x18003a353  jnz     short loc_18003A389
0x18003a355  mov     [r15+8], r14
0x18003a359  mov     rcx, [rsi+118h]
0x18003a360  mov     rcx, [rcx]; Sid
0x18003a363  call    cs:__imp_RtlLengthSid
0x18003a369  mov     ebx, eax
0x18003a36b  mov     r8, [rsi+118h]
0x18003a372  mov     r8, [r8]; SourceSid
0x18003a375  mov     rdx, r14; DestinationSid
0x18003a378  mov     ecx, eax; DestinationSidLength
0x18003a37a  call    cs:__imp_RtlCopySid
0x18003a380  add     r14, rbx
0x18003a383  mov     r12d, 1
0x18003a389  cmp     r12d, [rsi+110h]
0x18003a390  jnb     short loc_18003A400
0x18003a392  mov     edi, r12d
0x18003a395  add     rdi, rdi
0x18003a398  mov     rdx, [r15+18h]
0x18003a39c  mov     rax, [rsi+118h]
0x18003a3a3  mov     ecx, [rdx]
0x18003a3a5  inc     rcx
0x18003a3a8  add     rcx, rcx
0x18003a3ab  mov     eax, [rax+rdi*8+8]
0x18003a3af  mov     [rdx+rcx*8], eax
0x18003a3b2  mov     rcx, [r15+18h]
0x18003a3b6  mov     eax, [rcx]
0x18003a3b8  add     rax, rax
  ... truncated ...
```
