# StartProviderQuery(_GUID const *,ushort const *,_PROVIDER_QUERY_TYPE,_PROVIDER_QUERY_ENTRY *,void *,_DEV_QUERY_DATA *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEV_QUERY_PARAMETER const *,_DAS_LOCKED_LIST *,void *)

- ea: `0x1400160d8`
- end: `0x140016780`
- name: `?StartProviderQuery@@YAJPEBU_GUID@@PEBGW4_PROVIDER_QUERY_TYPE@@PEAU_PROVIDER_QUERY_ENTRY@@PEAXPEAU_DEV_QUERY_DATA@@KPEBU_DEVPROPCOMPKEY@@KPEBU_DEV_QUERY_PARAMETER@@PEAU_DAS_LOCKED_LIST@@4@Z`
- size: `1704`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int, __int64, void *, void *, unsigned int, void *, int, __int64, struct IClassFactory *, HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000aae0`

## callees

- `0x140009090`
- `0x140014d74`
- `0x140015e58`
- `0x1400160d8`
- `0x1400167e4`
- `0x140016d70`
- `0x14001a494`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016737`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1400161f6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1400161f6`

## pseudocode

```c
__int64 __fastcall StartProviderQuery(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        void *a5,
        void *a6,
        unsigned int a7,
        void *a8,
        int a9,
        __int64 a10,
        struct IClassFactory *a11,
        HANDLE ExistingTokenHandle)
{
  void *v14; // r14
  __m128i v15; // xmm6
  __m128i v16; // xmm7
  __m128i v17; // xmm8
  unsigned int v18; // r13d
  int ClassFactory; // ebx
  __int64 **v20; // r15
  GUID *v21; // r8
  signed int LastError; // eax
  _QWORD *v23; // r12
  __int64 *v24; // r8
  GUID *v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  _WORD *v28; // xmm6_8
  __int64 v29; // rdx
  _WORD *v30; // rdx
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // r11
  unsigned __int64 v36; // xmm7_8
  __int64 (__fastcall *v37)(__int64 *, void *, _QWORD, void *, __int32, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int); // rax
  __int64 (__fastcall *v38)(__int64 *, void *, _QWORD, void *, __int32, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int); // r11
  void *v39; // rdi
  __int64 v40; // rcx
  __int64 v41; // r11
  unsigned __int64 v42; // xmm7_8
  __int64 (__fastcall *v43)(__int64 *, _QWORD, void *, _QWORD, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int); // rax
  __int64 (__fastcall *v44)(__int64 *, _QWORD, void *, _QWORD, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int); // r11
  __int64 v46; // [rsp+30h] [rbp-D8h]
  int v47; // [rsp+30h] [rbp-D8h]
  __int64 v48; // [rsp+38h] [rbp-D0h]
  int v49; // [rsp+38h] [rbp-D0h]
  int v50; // [rsp+38h] [rbp-D0h]
  __int64 v51; // [rsp+38h] [rbp-D0h]
  void *v52; // [rsp+40h] [rbp-C8h]
  __int64 v53; // [rsp+40h] [rbp-C8h]
  __int64 v54; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v55; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v56; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v57; // [rsp+48h] [rbp-C0h]
  __int64 v58; // [rsp+48h] [rbp-C0h]
  __int64 v59; // [rsp+50h] [rbp-B8h]
  __int64 v60; // [rsp+50h] [rbp-B8h]
  unsigned int v61; // [rsp+58h] [rbp-B0h]
  void *DuplicateTokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v64[2]; // [rsp+98h] [rbp-70h]
  __int64 v65; // [rsp+158h] [rbp+50h] BYREF
  const unsigned __int16 *v66; // [rsp+160h] [rbp+58h]
  __int64 v67; // [rsp+170h] [rbp+68h] BYREF

  v66 = a2;
  a11 = 0;
  DuplicateTokenHandle = 0;
  v63 = 0;
  v65 = 0;
  v67 = 0;
  v14 = a6;
  v15 = *((__m128i *)a6 + 1);
  *(_OWORD *)v64 = *((_OWORD *)a6 + 2);
  v16 = *((__m128i *)a6 + 3);
  v17 = *((__m128i *)a6 + 5);
  if ( *((_DWORD *)a6 + 4) == 6 && (*((_BYTE *)a6 + 40) & 6) == 6 )
    v18 = (__int64)v64[1] & 0xFFFFFFFD;
  else
    v18 = (unsigned int)v64[1];
  if ( *(_DWORD *)(a4 + 24) )
  {
    ClassFactory = -2147467263;
LABEL_87:
    RemoveProviderQuery(*(_DWORD *)(a4 + 24), (RTL_SRWLOCK *)a4, 0);
    return (unsigned int)ClassFactory;
  }
  ClassFactory = ProviderContext::GetClassFactory(*(RTL_SRWLOCK **)(a4 + 56), &a11);
  if ( ClassFactory >= 0 )
  {
    v20 = (__int64 **)(a4 + 32);
    if ( a3 )
    {
      v21 = &IID_IAepServiceQuery;
      if ( a3 != 2 )
        v21 = &IID_IFederatedAepStoreQuery;
    }
    else
    {
      v21 = &IID_IAepQuery;
    }
    ClassFactory = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64))a11->lpVtbl->CreateInstance)(
                     a11,
                     0,
                     v21,
                     a4 + 32);
    if ( !ClassFactory )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(a4 + 56) + 72LL)
        || !ExistingTokenHandle
        || DuplicateToken(ExistingTokenHandle, (SECURITY_IMPERSONATION_LEVEL)(ClassFactory + 2), &DuplicateTokenHandle) )
      {
        goto LABEL_91;
      }
      LastError = GetLastError();
      ClassFactory = LastError;
      if ( LastError > 0 )
        ClassFactory = (unsigned __int16)LastError | 0x80070000;
      if ( !ClassFactory )
      {
LABEL_91:
        v23 = (_QWORD *)(a4 + 40);
        ClassFactory = CQueryCallback::Create(
                         a3,
                         **(const unsigned __int16 ***)(a4 + 56),
                         v66,
                         a7,
                         a8,
                         v46,
                         v48,
                         v52,
                         v18,
                         a5,
                         DuplicateTokenHandle,
                         (RTL_SRWLOCK **)(a4 + 40));
        if ( !ClassFactory )
        {
          DuplicateTokenHandle = 0;
          if ( a3 )
          {
            if ( a3 == 2 )
            {
              v24 = &v65;
              v25 = &GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d;
            }
            else
            {
              v24 = &v67;
              v25 = &GUID_09a26ea8_87fc_4b14_99c8_157168c0070d;
            }
          }
          else
          {
            v24 = &v63;
            v25 = &GUID_48780fb0_e908_4af1_b350_ef52f6a634e6;
          }
          ClassFactory = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v23)(*v23, v25, v24);
          if ( ClassFactory >= 0 )
          {
            if ( _mm_cvtsi128_si32(v15) == 6 || (v27 = _mm_cvtsi128_si32(_mm_srli_si128(v15, 4))) == 0 )
            {
              if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                McTemplateU0zp_EventWriteTransfer(v26, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), v14);
              v41 = **v20;
              v42 = _mm_srli_si128(v16, 8).m128i_u64[0];
              if ( a3 )
              {
                v44 = *(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int))(v41 + 24);
                if ( a3 == 2 )
                  v58 = v65;
                else
                  v58 = v67;
                v55 = v42;
                v51 = a10;
                v47 = a9;
                v43 = v44;
              }
              else
              {
                v58 = v63;
                v55 = v42;
                v51 = a10;
                v47 = a9;
                v43 = *(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int))(v41 + 24);
              }
              v32 = v43(
                      *v20,
                      a7,
                      a8,
                      (unsigned int)_mm_cvtsi128_si32(v17),
                      _mm_srli_si128(v17, 8).m128i_u64[0],
                      v47,
                      v51,
                      v55,
                      v58,
                      v18);
LABEL_52:
              ClassFactory = v32;
              if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                McTemplateU0zp_EventWriteTransfer(v33, CREATE_PROVIDER_QUERY_STOP, **(_QWORD **)(a4 + 56), v14);
              goto LABEL_76;
            }
            if ( v27 == 1 )
            {
              if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                McTemplateU0zp_EventWriteTransfer(v26, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), v14);
              v28 = (_WORD *)_mm_srli_si128(v15, 8).m128i_u64[0];
              if ( a3 )
              {
                LODWORD(v31) = 0;
                if ( a3 == 2 )
                {
                  if ( *v28 )
                  {
                    while ( !(_DWORD)v31 || v28[(unsigned int)(v31 - 1)] != 35 )
                    {
                      v31 = (unsigned int)(v31 + 1);
                      if ( !v28[v31] )
                        goto LABEL_43;
                    }
                  }
                  else
                  {
LABEL_43:
                    LODWORD(v31) = 0;
                  }
                  v30 = &v28[(unsigned int)v31];
                  v61 = v18;
                  v59 = v65;
                  v56 = _mm_srli_si128(v16, 8).m128i_u64[0];
                  v53 = a10;
                  v49 = a9;
                }
                else
                {
                  if ( *v28 )
                  {
                    while ( !(_DWORD)v31 || v28[(unsigned int)(v31 - 1)] != 35 )
                    {
                      v31 = (unsigned int)(v31 + 1);
                      if ( !v28[v31] )
                        goto LABEL_49;
                    }
                  }
                  else
                  {
LABEL_49:
                    LODWORD(v31) = 0;
                  }
                  v30 = &v28[(unsigned int)v31];
                  v61 = v18;
                  v59 = v67;
                  v56 = _mm_srli_si128(v16, 8).m128i_u64[0];
                  v53 = a10;
                  v49 = a9;
                }
              }
              else
              {
                LODWORD(v29) = 0;
                if ( *v28 )
                {
                  while ( !(_DWORD)v29 || v28[(unsigned int)(v29 - 1)] != 35 )
                  {
                    v29 = (unsigned int)(v29 + 1);
                    if ( !v28[v29] )
                      goto LABEL_36;
                  }
                }
                else
                {
LABEL_36:
                  LODWORD(v29) = 0;
                }
                v30 = &v28[(unsigned int)v29];
                v61 = v18;
                v59 = *v23;
                v56 = _mm_srli_si128(v16, 8).m128i_u64[0];
                v53 = a10;
                v49 = a9;
              }
              v32 = (*(__int64 (__fastcall **)(__int64 *, _WORD *, _QWORD, void *, __int32, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int))(**v20 + 32))(
                      *v20,
                      v30,
                      a7,
                      a8,
                      v17.m128i_i32[0],
                      _mm_srli_si128(v17, 8).m128i_u64[0],
                      v49,
                      v53,
                      v56,
                      v59,
                      v61);
              goto LABEL_52;
            }
            if ( v27 == 2 )
            {
              a6 = 0;
              ClassFactory = DafMakeProviderAepIdsList(v64[0], **(LPCWCH **)(a4 + 56));
              if ( !ClassFactory )
              {
                if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                  McTemplateU0zp_EventWriteTransfer(v34, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), v14);
                v35 = **v20;
                v36 = _mm_srli_si128(v16, 8).m128i_u64[0];
                if ( a3 )
                {
                  v38 = *(__int64 (__fastcall **)(__int64 *, void *, _QWORD, void *, __int32, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int))(v35 + 40);
                  if ( a3 == 2 )
                    v60 = v65;
                  else
                    v60 = v67;
                  v57 = v36;
                  v54 = a10;
                  v50 = a9;
                  v37 = v38;
                }
                else
                {
                  v60 = v63;
                  v57 = v36;
                  v54 = a10;
                  v50 = a9;
                  v37 = *(__int64 (__fastcall **)(__int64 *, void *, _QWORD, void *, __int32, unsigned __int64, int, __int64, unsigned __int64, __int64, unsigned int))(v35 + 40);
                }
                v39 = a6;
                ClassFactory = v37(
                                 *v20,
                                 a6,
                                 a7,
                                 a8,
                                 v17.m128i_i32[0],
                                 _mm_srli_si128(v17, 8).m128i_u64[0],
                                 v50,
                                 v54,
                                 v57,
                                 v60,
                                 v18);
                if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                  McTemplateU0zp_EventWriteTransfer(v40, CREATE_PROVIDER_QUERY_STOP, **(_QWORD **)(a4 + 56), v14);
                MIDL_user_free(v39);
              }
            }
          }
        }
      }
    }
  }
LABEL_76:
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  if ( a11 )
    ((void (__fastcall *)(struct IClassFactory *))a11->lpVtbl->Release)(a11);
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( ClassFactory )
    goto LABEL_87;
  return (unsigned int)ClassFactory;
}

```

## disassembly

```asm
0x1400160d8  mov     rax, rsp
0x1400160db  mov     [rax+18h], rbx
0x1400160df  mov     [rax+10h], rdx
0x1400160e3  mov     [rax+8], rcx
0x1400160e7  push    rbp
0x1400160e8  push    rsi
0x1400160e9  push    rdi
0x1400160ea  push    r12
0x1400160ec  push    r13
0x1400160ee  push    r14
0x1400160f0  push    r15
0x1400160f2  lea     rbp, [rax-48h]
0x1400160f6  sub     rsp, 110h
0x1400160fd  movaps  xmmword ptr [rax-48h], xmm6
0x140016101  movaps  xmmword ptr [rax-58h], xmm7
0x140016105  movaps  xmmword ptr [rax-68h], xmm8
0x14001610a  mov     rsi, r9
0x14001610d  mov     edi, r8d
0x140016110  xor     r12d, r12d
0x140016113  mov     [rbp+40h+arg_50], r12
0x14001611a  mov     [rsp+140h+DuplicateTokenHandle], r12
0x14001611f  mov     [rsp+140h+var_D8], r12
0x140016124  mov     [rbp+40h+arg_0], r12
0x140016128  mov     [rbp+40h+arg_18], r12
0x14001612c  mov     r14, [rbp+40h+arg_28]
0x140016130  movups  xmm6, xmmword ptr [r14+10h]
0x140016135  movups  xmm0, xmmword ptr [r14+20h]
0x14001613a  movaps  xmmword ptr [rbp+40h+var_B0], xmm0
0x14001613e  movups  xmm7, xmmword ptr [r14+30h]
0x140016143  movups  xmm8, xmmword ptr [r14+50h]
0x140016148  cmp     dword ptr [r14+10h], 6
0x14001614d  jnz     short loc_140016164
0x14001614f  mov     eax, [r14+28h]
0x140016153  and     eax, 6
0x140016156  cmp     al, 6
0x140016158  jnz     short loc_140016164
0x14001615a  mov     r13d, dword ptr [rbp+40h+var_B0+8]
0x14001615e  and     r13d, 0FFFFFFFDh
0x140016162  jmp     short loc_140016168
0x140016164  mov     r13d, dword ptr [rbp+40h+var_B0+8]
0x140016168  cmp     [r9+18h], r12d
0x14001616c  jz      short loc_140016178
0x14001616e  mov     ebx, 80004001h
0x140016173  jmp     loc_140016746
0x140016178  lea     rdx, [rbp+40h+arg_50]; struct IClassFactory **
0x14001617f  mov     rcx, [r9+38h]; this
0x140016183  call    ?GetClassFactory@ProviderContext@@QEAAJPEAPEAUIClassFactory@@@Z; ProviderContext::GetClassFactory(IClassFactory * *)
0x140016188  mov     ebx, eax
0x14001618a  test    eax, eax
0x14001618c  js      loc_1400166D5
0x140016192  lea     r15, [rsi+20h]
0x140016196  test    edi, edi
0x140016198  jnz     short loc_1400161A3
0x14001619a  lea     r8, IID_IAepQuery
0x1400161a1  jmp     short loc_1400161B6
0x1400161a3  cmp     edi, 2
0x1400161a6  lea     r8, IID_IAepServiceQuery
0x1400161ad  jz      short loc_1400161B6
0x1400161af  lea     r8, IID_IFederatedAepStoreQuery
0x1400161b6  mov     rcx, [rbp+40h+arg_50]
0x1400161bd  mov     rax, [rcx]
0x1400161c0  mov     r9, r15
0x1400161c3  xor     edx, edx
0x1400161c5  mov     rax, [rax+18h]
0x1400161c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161ce  mov     ebx, eax
0x1400161d0  test    eax, eax
0x1400161d2  jnz     loc_1400166D5
0x1400161d8  mov     rax, [rsi+38h]
0x1400161dc  cmp     [rax+48h], r12d
0x1400161e0  jz      short loc_14001621D
0x1400161e2  mov     rcx, [rbp+40h+ExistingTokenHandle]; ExistingTokenHandle
0x1400161e9  test    rcx, rcx
0x1400161ec  jz      short loc_14001621D
0x1400161ee  lea     r8, [rsp+140h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1400161f3  lea     edx, [rbx+2]; ImpersonationLevel
0x1400161f6  call    cs:__imp_DuplicateToken
0x1400161fc  test    eax, eax
0x1400161fe  jnz     short loc_14001621D
0x140016200  call    cs:__imp_GetLastError
0x140016206  mov     ebx, eax
0x140016208  test    eax, eax
0x14001620a  jle     short loc_140016215
0x14001620c  movzx   ebx, ax
0x14001620f  or      ebx, 80070000h
0x140016215  test    ebx, ebx
0x140016217  jnz     loc_1400166D5
0x14001621d  mov     rax, [rsp+140h+DuplicateTokenHandle]
0x140016222  lea     r12, [rsi+28h]
0x140016226  mov     rdx, [rsi+38h]
0x14001622a  mov     [rsp+140h+var_E8], r12
0x14001622f  mov     [rsp+140h+var_F0], rax
0x140016234  mov     rax, [rbp+40h+arg_20]
0x140016238  mov     [rsp+140h+var_F8], rax
0x14001623d  mov     dword ptr [rsp+140h+var_100], r13d
0x140016242  mov     rax, [rbp+40h+arg_38]
0x140016249  mov     [rsp+140h+var_120], rax
0x14001624e  mov     r9d, [rbp+40h+arg_30]
0x140016255  mov     r8, [rbp+40h+arg_8]
0x140016259  mov     rdx, [rdx]
0x14001625c  mov     ecx, edi
0x14001625e  call    ?Create@CQueryCallback@@SAJW4_PROVIDER_QUERY_TYPE@@PEBG1KPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@1KPEAX4PEAPEAV1@@Z; CQueryCallback::Create(_PROVIDER_QUERY_TYPE,ushort const *,ushort const *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ushort const *,ulong,void *,void *,CQueryCallback * *)
0x140016263  mov     ebx, eax
0x140016265  test    eax, eax
0x140016267  jnz     loc_1400166D2
0x14001626d  mov     [rsp+140h+DuplicateTokenHandle], 0
0x140016276  mov     rcx, [r12]
0x14001627a  mov     rax, [rcx]
0x14001627d  mov     rax, [rax]
0x140016280  test    edi, edi
0x140016282  jnz     short loc_140016292
0x140016284  lea     r8, [rsp+140h+var_D8]
0x140016289  lea     rdx, _GUID_48780fb0_e908_4af1_b350_ef52f6a634e6
0x140016290  jmp     short loc_1400162AF
0x140016292  cmp     edi, 2
0x140016295  jnz     short loc_1400162A4
0x140016297  lea     r8, [rbp+40h+arg_0]
0x14001629b  lea     rdx, _GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d
0x1400162a2  jmp     short loc_1400162AF
0x1400162a4  lea     r8, [rbp+40h+arg_18]
0x1400162a8  lea     rdx, _GUID_09a26ea8_87fc_4b14_99c8_157168c0070d
0x1400162af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162b4  mov     ebx, eax
0x1400162b6  test    eax, eax
0x1400162b8  js      loc_1400166D2
0x1400162be  movd    eax, xmm6
0x1400162c2  cmp     eax, 6
0x1400162c5  jz      loc_1400165E5
0x1400162cb  movdqa  xmm0, xmm6
0x1400162cf  psrldq  xmm0, 4
0x1400162d4  movd    eax, xmm0
0x1400162d8  test    eax, eax
0x1400162da  jz      loc_1400165E5
0x1400162e0  cmp     eax, 1
0x1400162e3  jnz     loc_14001649A
0x1400162e9  test    cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x1400162f0  jz      short loc_140016308
0x1400162f2  mov     r8, [rsi+38h]
0x1400162f6  mov     r9, r14
0x1400162f9  mov     r8, [r8]
0x1400162fc  lea     rdx, CREATE_PROVIDER_QUERY_START
0x140016303  call    McTemplateU0zp_EventWriteTransfer
0x140016308  mov     r11, [r15]
0x14001630b  mov     rax, [r11]
0x14001630e  mov     r10, [rax+20h]
0x140016312  psrldq  xmm6, 8
0x140016317  movq    r8, xmm6
0x14001631c  test    edi, edi
0x14001631e  jnz     short loc_140016382
0x140016320  mov     r9, [r12]
0x140016324  xor     r12d, r12d
0x140016327  mov     edx, r12d
0x14001632a  cmp     [r8], r12w
0x14001632e  jz      short loc_140016348
0x140016330  test    edx, edx
0x140016332  jz      short loc_14001633F
0x140016334  lea     eax, [rdx-1]
0x140016337  cmp     word ptr [r8+rax*2], 23h ; '#'
0x14001633d  jz      short loc_14001634B
0x14001633f  inc     edx
0x140016341  cmp     [r8+rdx*2], r12w
0x140016346  jnz     short loc_140016330
0x140016348  mov     edx, r12d
0x14001634b  mov     eax, edx
0x14001634d  lea     rdx, [r8+rax*2]
0x140016351  mov     dword ptr [rsp+140h+var_F0], r13d
0x140016356  mov     [rsp+140h+var_F8], r9
0x14001635b  psrldq  xmm7, 8
0x140016360  movq    [rsp+140h+var_100], xmm7
0x140016367  mov     rcx, [rbp+40h+arg_48]
0x14001636e  mov     [rsp+140h+var_108], rcx
0x140016373  mov     ecx, [rbp+40h+arg_40]
0x140016379  mov     dword ptr [rsp+140h+var_110], ecx
0x14001637d  jmp     loc_14001643F
0x140016382  xor     r12d, r12d
0x140016385  mov     edx, r12d
0x140016388  cmp     edi, 2
0x14001638b  jnz     short loc_1400163E6
0x14001638d  mov     r9, [rbp+40h+arg_0]
0x140016391  cmp     [r8], r12w
0x140016395  jz      short loc_1400163AF
0x140016397  test    edx, edx
0x140016399  jz      short loc_1400163A6
0x14001639b  lea     eax, [rdx-1]
0x14001639e  cmp     word ptr [r8+rax*2], 23h ; '#'
0x1400163a4  jz      short loc_1400163B2
0x1400163a6  inc     edx
0x1400163a8  cmp     [r8+rdx*2], r12w
0x1400163ad  jnz     short loc_140016397
0x1400163af  mov     edx, r12d
0x1400163b2  mov     eax, edx
0x1400163b4  lea     rdx, [r8+rax*2]
0x1400163b8  mov     dword ptr [rsp+140h+var_F0], r13d
0x1400163bd  mov     [rsp+140h+var_F8], r9
0x1400163c2  psrldq  xmm7, 8
0x1400163c7  movq    [rsp+140h+var_100], xmm7
0x1400163ce  mov     rax, [rbp+40h+arg_48]
0x1400163d5  mov     [rsp+140h+var_108], rax
0x1400163da  mov     eax, [rbp+40h+arg_40]
0x1400163e0  mov     dword ptr [rsp+140h+var_110], eax
0x1400163e4  jmp     short loc_14001643F
0x1400163e6  mov     r9, [rbp+40h+arg_18]
0x1400163ea  cmp     [r8], r12w
0x1400163ee  jz      short loc_140016408
0x1400163f0  test    edx, edx
0x1400163f2  jz      short loc_1400163FF
0x1400163f4  lea     eax, [rdx-1]
0x1400163f7  cmp     word ptr [r8+rax*2], 23h ; '#'
0x1400163fd  jz      short loc_14001640B
0x1400163ff  inc     edx
0x140016401  cmp     [r8+rdx*2], r12w
0x140016406  jnz     short loc_1400163F0
0x140016408  mov     edx, r12d
0x14001640b  mov     eax, edx
0x14001640d  lea     rdx, [r8+rax*2]
0x140016411  mov     dword ptr [rsp+140h+var_F0], r13d
0x140016416  mov     [rsp+140h+var_F8], r9
0x14001641b  psrldq  xmm7, 8
0x140016420  movq    [rsp+140h+var_100], xmm7
0x140016427  mov     r8, [rbp+40h+arg_48]
0x14001642e  mov     [rsp+140h+var_108], r8
0x140016433  mov     r8d, [rbp+40h+arg_40]
0x14001643a  mov     dword ptr [rsp+140h+var_110], r8d
0x14001643f  movdqa  xmm0, xmm8
0x140016444  psrldq  xmm0, 8
0x140016449  movq    [rsp+140h+var_118], xmm0
0x140016450  movss   dword ptr [rsp+140h+var_120], xmm8
0x140016457  mov     r9, [rbp+40h+arg_38]
0x14001645e  mov     r8d, [rbp+40h+arg_30]
0x140016465  mov     rcx, r11
0x140016468  mov     rax, r10
0x14001646b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016470  mov     ebx, eax
0x140016472  test    cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x140016479  jz      loc_1400166D5
0x14001647f  mov     r8, [rsi+38h]
0x140016483  mov     r9, r14
0x140016486  mov     r8, [r8]
0x140016489  lea     rdx, CREATE_PROVIDER_QUERY_STOP
0x140016490  call    McTemplateU0zp_EventWriteTransfer
0x140016495  jmp     loc_1400166D5
0x14001649a  xor     r12d, r12d
0x14001649d  cmp     eax, 2
0x1400164a0  jnz     loc_1400166D5
0x1400164a6  mov     [rbp+40h+arg_28], r12
0x1400164aa  mov     rdx, [rsi+38h]
0x1400164ae  lea     r8, [rbp+40h+arg_28]
0x1400164b2  mov     rdx, [rdx]; lpString2
0x1400164b5  mov     rcx, [rbp+40h+var_B0]; unsigned __int16 *
0x1400164b9  call    DafMakeProviderAepIdsList
0x1400164be  mov     ebx, eax
0x1400164c0  test    eax, eax
0x1400164c2  jnz     loc_1400166D5
0x1400164c8  test    cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x1400164cf  jz      short loc_1400164E7
0x1400164d1  mov     r8, [rsi+38h]
0x1400164d5  mov     r9, r14
0x1400164d8  mov     r8, [r8]
0x1400164db  lea     rdx, CREATE_PROVIDER_QUERY_START
0x1400164e2  call    McTemplateU0zp_EventWriteTransfer
0x1400164e7  mov     r10, [r15]
0x1400164ea  mov     r11, [r10]
0x1400164ed  mov     dword ptr [rsp+140h+var_F0], r13d
0x1400164f2  psrldq  xmm7, 8
0x1400164f7  test    edi, edi
0x1400164f9  jnz     short loc_140016528
0x1400164fb  mov     rax, [rsp+140h+var_D8]
0x140016500  mov     [rsp+140h+var_F8], rax
0x140016505  movq    [rsp+140h+var_100], xmm7
0x14001650c  mov     rax, [rbp+40h+arg_48]
0x140016513  mov     [rsp+140h+var_108], rax
0x140016518  mov     edx, [rbp+40h+arg_40]
0x14001651e  mov     dword ptr [rsp+140h+var_110], edx
0x140016522  mov     rax, [r11+28h]
0x140016526  jmp     short loc_140016582
0x140016528  mov     r11, [r11+28h]
0x14001652c  cmp     edi, 2
0x14001652f  jnz     short loc_140016559
0x140016531  mov     rax, [rbp+40h+arg_0]
0x140016535  mov     [rsp+140h+var_F8], rax
0x14001653a  movq    [rsp+140h+var_100], xmm7
0x140016541  mov     rax, [rbp+40h+arg_48]
0x140016548  mov     [rsp+140h+var_108], rax
0x14001654d  mov     eax, [rbp+40h+arg_40]
0x140016553  mov     dword ptr [rsp+140h+var_110], eax
0x140016557  jmp     short loc_14001657F
0x140016559  mov     rax, [rbp+40h+arg_18]
0x14001655d  mov     [rsp+140h+var_F8], rax
0x140016562  movq    [rsp+140h+var_100], xmm7
0x140016569  mov     rax, [rbp+40h+arg_48]
0x140016570  mov     [rsp+140h+var_108], rax
0x140016575  mov     ecx, [rbp+40h+arg_40]
0x14001657b  mov     dword ptr [rsp+140h+var_110], ecx
0x14001657f  mov     rax, r11
0x140016582  movdqa  xmm0, xmm8
0x140016587  psrldq  xmm0, 8
0x14001658c  movq    [rsp+140h+var_118], xmm0
0x140016593  mov     rdi, [rbp+40h+arg_28]
0x140016597  movss   dword ptr [rsp+140h+var_120], xmm8
0x14001659e  mov     r9, [rbp+40h+arg_38]
  ... truncated ...
```
