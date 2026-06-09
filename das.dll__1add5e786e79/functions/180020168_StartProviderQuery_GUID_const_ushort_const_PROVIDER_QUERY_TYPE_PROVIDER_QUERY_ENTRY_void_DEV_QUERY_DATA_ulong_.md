# StartProviderQuery(_GUID const *,ushort const *,_PROVIDER_QUERY_TYPE,_PROVIDER_QUERY_ENTRY *,void *,_DEV_QUERY_DATA *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEV_QUERY_PARAMETER const *,_DAS_LOCKED_LIST *,void *)

- ea: `0x180020168`
- end: `0x180020886`
- name: `?StartProviderQuery@@YAJPEBU_GUID@@PEBGW4_PROVIDER_QUERY_TYPE@@PEAU_PROVIDER_QUERY_ENTRY@@PEAXPEAU_DEV_QUERY_DATA@@KPEBU_DEVPROPCOMPKEY@@KPEBU_DEV_QUERY_PARAMETER@@PEAU_DAS_LOCKED_LIST@@4@Z`
- size: `1822`
- prototype: `int __high(const struct _GUID *, const unsigned __int16 *, enum _PROVIDER_QUERY_TYPE, struct _PROVIDER_QUERY_ENTRY *, void *, struct _DEV_QUERY_DATA *, unsigned int, const struct _DEVPROPCOMPKEY *, unsigned int, const struct _DEV_QUERY_PARAMETER *, struct _DAS_LOCKED_LIST *, void *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014b08`
- `0x180020084`
- `0x1800535c4`

## callees

- `0x180009590`
- `0x1800168dc`
- `0x180020168`
- `0x18002088c`
- `0x180023e3c`
- `0x18003bc80`
- `0x18004c950`
- `0x18005e894`
- `0x180062604`
- `0x1800626a0`
- `0x1800628d0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020318`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020318`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800202a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800202a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002038e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002038e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020844`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180020384`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180020384`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartProviderQuery(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6,
        unsigned int a7,
        void *a8,
        int a9,
        __int64 a10,
        struct _DAS_LOCKED_LIST *a11,
        void *a12)
{
  void *v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // r15
  int started; // ebx
  __int64 v17; // r15
  __int64 **v18; // r15
  GUID *v19; // r8
  signed int LastError; // eax
  _QWORD *v21; // r12
  __int64 *v22; // r8
  GUID *v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v27; // r10
  __int64 v28; // r11
  int v29; // eax
  __int64 v30; // rcx
  __int64 (__fastcall *v31)(__int64, __int64, _QWORD, void *, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64, _DWORD); // rbx
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r10
  __int64 v35; // r11
  __int64 v36; // rcx
  __int64 v37; // r11
  __int64 (__fastcall *v38)(__int64 *, _QWORD, _QWORD, void *, int, __int64, int, __int64, __int64, __int64, _DWORD); // rax
  __int64 (__fastcall *v39)(__int64 *, _QWORD, _QWORD, void *, int, __int64, int, __int64, __int64, __int64, _DWORD); // r11
  void *v40; // rdx
  __int64 v41; // rcx
  __int64 *v42; // r10
  __int64 v43; // r11
  __int64 (__fastcall *v44)(__int64 *, _QWORD, void *, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64, _DWORD); // r11
  int v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+28h] [rbp-D8h]
  __int64 v48; // [rsp+28h] [rbp-D8h]
  __int64 v49; // [rsp+30h] [rbp-D0h]
  int v50; // [rsp+30h] [rbp-D0h]
  wil::details *v51; // [rsp+38h] [rbp-C8h]
  __int64 v52; // [rsp+38h] [rbp-C8h]
  __int64 v53; // [rsp+40h] [rbp-C0h]
  __int64 v54; // [rsp+48h] [rbp-B8h]
  __int64 v55; // [rsp+78h] [rbp-88h] BYREF
  __int64 v56; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h] BYREF
  void *DuplicateTokenHandle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  __int128 v61; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v62; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v63[2]; // [rsp+D0h] [rbp-30h]
  __int128 v64; // [rsp+E0h] [rbp-20h]
  __int128 v65; // [rsp+F0h] [rbp-10h]
  __int128 v66; // [rsp+100h] [rbp+0h]
  __int128 v67; // [rsp+110h] [rbp+10h]

  v60 = a2;
  v14 = a8;
  v15 = (struct _RTL_CRITICAL_SECTION *)a11;
  v57 = 0;
  DuplicateTokenHandle = 0;
  v59 = 0;
  v55 = 0;
  v56 = 0;
  v61 = *a6;
  v62 = a6[1];
  *(_OWORD *)v63 = a6[2];
  v64 = a6[3];
  v65 = a6[4];
  v66 = a6[5];
  v67 = a6[6];
  if ( *((_DWORD *)a6 + 4) == 6 )
  {
    v14 = a8;
    if ( (*((_DWORD *)a6 + 10) & 6) == 6 )
      LODWORD(v63[1]) &= ~2u;
  }
  if ( (*((_BYTE *)a6 + 40) & 2) == 0 )
  {
    LODWORD(v65) = a7;
    *((_QWORD *)&v65 + 1) = v14;
  }
  LODWORD(v67) = a9;
  *((_QWORD *)&v67 + 1) = a10;
  if ( *(_DWORD *)(a4 + 24) )
  {
    started = StartRemoteQueryStub(a1, a3, a4, &v61, a12);
    goto LABEL_64;
  }
  v17 = *(_QWORD *)(a4 + 56);
  AcquireSRWLockExclusive((PSRWLOCK)(v17 + 128));
  if ( *(_QWORD *)(v17 + 136) || (started = ProviderContext::LoadAndInitializeDll((ProviderContext *)v17), started >= 0) )
  {
    started = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(v17 + 136))(v17 + 24, &IID_IClassFactory, &v57);
    if ( started < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_91edd21030e531619c269f99d7a31287_Traceguids,
        (unsigned int)started);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(v17 + 128));
  if ( started >= 0 )
  {
    v18 = (__int64 **)(a4 + 32);
    if ( a3 )
    {
      v19 = &IID_IAepServiceQuery;
      if ( a3 != 2 )
        v19 = &IID_IFederatedAepStoreQuery;
    }
    else
    {
      v19 = &IID_IAepQuery;
    }
    started = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v57 + 24LL))(
                v57,
                0,
                v19,
                a4 + 32);
    if ( !started )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(a4 + 56) + 72LL)
        || !a12
        || DuplicateToken(a12, (SECURITY_IMPERSONATION_LEVEL)(started + 2), &DuplicateTokenHandle) )
      {
        goto LABEL_79;
      }
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      if ( !started )
      {
LABEL_79:
        v21 = (_QWORD *)(a4 + 40);
        started = CQueryCallback::Create(
                    a3,
                    **(unsigned __int16 ***)(a4 + 56),
                    v60,
                    a7,
                    a8,
                    v47,
                    v49,
                    v51,
                    (int)v63[1],
                    a5,
                    (__int64)DuplicateTokenHandle,
                    (__int64 *)(a4 + 40));
        if ( !started )
        {
          DuplicateTokenHandle = 0;
          if ( a3 )
          {
            if ( a3 == 2 )
            {
              v22 = &v55;
              v23 = &GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d;
            }
            else
            {
              v22 = &v56;
              v23 = &GUID_09a26ea8_87fc_4b14_99c8_157168c0070d;
            }
          }
          else
          {
            v22 = &v59;
            v23 = &GUID_48780fb0_e908_4af1_b350_ef52f6a634e6;
          }
          started = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v21)(*v21, v23, v22);
          if ( started >= 0 )
          {
            if ( (_DWORD)v62 == 6 || !DWORD1(v62) )
            {
              if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                McTemplateU0zp_EventWriteTransfer(v24, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), a6);
              v42 = *v18;
              v43 = **v18;
              if ( a3 )
              {
                v44 = *(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64, _DWORD))(v43 + 24);
                if ( a3 == 2 )
                  v29 = v44(
                          v42,
                          a7,
                          a8,
                          (unsigned int)v66,
                          *((_QWORD *)&v66 + 1),
                          v67,
                          *((_QWORD *)&v67 + 1),
                          *((_QWORD *)&v64 + 1),
                          v55,
                          v63[1]);
                else
                  v29 = v44(
                          v42,
                          a7,
                          a8,
                          (unsigned int)v66,
                          *((_QWORD *)&v66 + 1),
                          v67,
                          *((_QWORD *)&v67 + 1),
                          *((_QWORD *)&v64 + 1),
                          v56,
                          v63[1]);
              }
              else
              {
                v29 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64, _DWORD))(v43 + 24))(
                        v42,
                        a7,
                        a8,
                        (unsigned int)v66,
                        *((_QWORD *)&v66 + 1),
                        v67,
                        *((_QWORD *)&v67 + 1),
                        *((_QWORD *)&v64 + 1),
                        v59,
                        v63[1]);
              }
            }
            else
            {
              if ( DWORD1(v62) != 1 )
              {
                if ( DWORD1(v62) == 2 )
                {
                  started = DafMakeProviderAepIdsList(v63[0], **(LPCWCH **)(a4 + 56));
                  if ( !started )
                  {
                    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                      McTemplateU0zp_EventWriteTransfer(v36, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), a6);
                    v37 = **v18;
                    if ( a3 )
                    {
                      v39 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, void *, int, __int64, int, __int64, __int64, __int64, _DWORD))(v37 + 40);
                      if ( a3 == 2 )
                        v54 = v55;
                      else
                        v54 = v56;
                      v53 = *((_QWORD *)&v64 + 1);
                      v52 = *((_QWORD *)&v67 + 1);
                      v50 = v67;
                      v48 = *((_QWORD *)&v66 + 1);
                      v46 = v66;
                      v38 = v39;
                    }
                    else
                    {
                      v54 = v59;
                      v53 = *((_QWORD *)&v64 + 1);
                      v52 = *((_QWORD *)&v67 + 1);
                      v50 = v67;
                      v48 = *((_QWORD *)&v66 + 1);
                      v46 = v66;
                      v38 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, void *, int, __int64, int, __int64, __int64, __int64, _DWORD))(v37 + 40);
                    }
                    started = v38(*v18, 0, a7, a8, v46, v48, v50, v52, v53, v54, v63[1]);
                    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                      McTemplateU0zp_EventWriteTransfer(v41, CREATE_PROVIDER_QUERY_STOP, **(_QWORD **)(a4 + 56), a6);
                    wil::details::FreeProcessHeap(0, v40);
                  }
                }
                goto LABEL_63;
              }
              if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
                McTemplateU0zp_EventWriteTransfer(v24, CREATE_PROVIDER_QUERY_START, **(_QWORD **)(a4 + 56), a6);
              if ( a3 )
              {
                v31 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, void *, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64, _DWORD))(**v18 + 32);
                v32 = DafProviderAepIdOffset(*((_QWORD *)&v62 + 1));
                v29 = v31(
                        v35,
                        v33 + 2LL * v32,
                        a7,
                        a8,
                        v66,
                        *((_QWORD *)&v66 + 1),
                        v67,
                        *((_QWORD *)&v67 + 1),
                        *((_QWORD *)&v64 + 1),
                        v34,
                        v63[1]);
              }
              else
              {
                v25 = DafProviderAepIdOffset(*((_QWORD *)&v62 + 1));
                v29 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void *, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD))(v27 + 32))(
                        v28,
                        v26 + 2LL * v25,
                        a7,
                        a8,
                        v66,
                        *((_QWORD *)&v66 + 1),
                        v67,
                        *((_QWORD *)&v67 + 1),
                        *((_QWORD *)&v64 + 1),
                        *v21,
                        v63[1]);
              }
            }
            started = v29;
            if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 8) != 0 )
              McTemplateU0zp_EventWriteTransfer(v30, CREATE_PROVIDER_QUERY_STOP, **(_QWORD **)(a4 + 56), a6);
          }
        }
      }
    }
  }
LABEL_63:
  v15 = (struct _RTL_CRITICAL_SECTION *)a11;
LABEL_64:
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( started )
    RemoveProviderQuery(*(_DWORD *)(a4 + 24), (RTL_SRWLOCK *)a4, v15);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180020168  push    rbp
0x18002016a  push    rbx
0x18002016b  push    rsi
0x18002016c  push    rdi
0x18002016d  push    r12
0x18002016f  push    r13
0x180020171  push    r14
0x180020173  push    r15
0x180020175  lea     rbp, [rsp-38h]
0x18002017a  sub     rsp, 138h
0x180020181  mov     rax, cs:__security_cookie
0x180020188  xor     rax, rsp
0x18002018b  mov     [rbp+70h+var_50], rax
0x18002018f  mov     rdi, r9
0x180020192  mov     esi, r8d
0x180020195  mov     [rbp+70h+var_D0], rdx
0x180020199  mov     r10, rcx
0x18002019c  mov     r14, [rbp+70h+arg_28]
0x1800201a3  mov     rax, [rbp+70h+arg_38]
0x1800201aa  mov     [rsp+170h+var_108], rax
0x1800201af  mov     rdx, [rbp+70h+arg_48]
0x1800201b6  mov     r15, [rbp+70h+arg_50]
0x1800201bd  mov     [rsp+170h+var_110], r15
0x1800201c2  mov     rcx, [rbp+70h+arg_58]
0x1800201c9  mov     [rsp+170h+ExistingTokenHandle], rcx
0x1800201ce  mov     [rbp+70h+var_E8], 0
0x1800201d6  mov     [rbp+70h+DuplicateTokenHandle], 0
0x1800201de  mov     [rbp+70h+var_D8], 0
0x1800201e6  mov     [rsp+170h+var_F8], 0
0x1800201ef  mov     [rbp+70h+var_F0], 0
0x1800201f7  movups  xmm0, xmmword ptr [r14]
0x1800201fb  movaps  [rbp+70h+var_C0], xmm0
0x1800201ff  movups  xmm1, xmmword ptr [r14+10h]
0x180020204  movaps  [rbp+70h+var_B0], xmm1
0x180020208  movups  xmm0, xmmword ptr [r14+20h]
0x18002020d  movaps  xmmword ptr [rbp+70h+var_A0], xmm0
0x180020211  movups  xmm1, xmmword ptr [r14+30h]
0x180020216  movaps  [rbp+70h+var_90], xmm1
0x18002021a  movups  xmm0, xmmword ptr [r14+40h]
0x18002021f  movaps  [rbp+70h+var_80], xmm0
0x180020223  movups  xmm1, xmmword ptr [r14+50h]
0x180020228  movaps  [rbp+70h+var_70], xmm1
0x18002022c  movups  xmm0, xmmword ptr [r14+60h]
0x180020231  movaps  [rbp+70h+var_60], xmm0
0x180020235  cmp     dword ptr [r14+10h], 6
0x18002023a  jnz     short loc_180020250
0x18002023c  mov     eax, [r14+28h]
0x180020240  and     eax, 6
0x180020243  cmp     al, 6
0x180020245  mov     rax, [rsp+170h+var_108]
0x18002024a  jnz     short loc_180020250
0x18002024c  and     dword ptr [rbp+70h+var_A0+8], 0FFFFFFFDh
0x180020250  mov     r13d, [rbp+70h+arg_30]
0x180020257  test    byte ptr [r14+28h], 2
0x18002025c  jnz     short loc_180020266
0x18002025e  mov     dword ptr [rbp+70h+var_80], r13d
0x180020262  mov     qword ptr [rbp+70h+var_80+8], rax
0x180020266  mov     eax, [rbp+70h+arg_40]
0x18002026c  mov     dword ptr [rbp+70h+var_60], eax
0x18002026f  mov     qword ptr [rbp+70h+var_60+8], rdx
0x180020273  cmp     dword ptr [r9+18h], 0
0x180020278  jz      short loc_180020297
0x18002027a  mov     [rsp+170h+var_150], rcx
0x18002027f  lea     r9, [rbp+70h+var_C0]
0x180020283  mov     r8, rdi
0x180020286  mov     edx, esi
0x180020288  mov     rcx, r10
0x18002028b  call    ?StartRemoteQueryStub@@YAJPEBU_GUID@@W4_PROVIDER_QUERY_TYPE@@PEAU_PROVIDER_QUERY_ENTRY@@PEAU_DEV_QUERY_DATA@@PEAX@Z; StartRemoteQueryStub(_GUID const *,_PROVIDER_QUERY_TYPE,_PROVIDER_QUERY_ENTRY *,_DEV_QUERY_DATA *,void *)
0x180020290  mov     ebx, eax
0x180020292  jmp     loc_1800207E6
0x180020297  mov     r15, [r9+38h]
0x18002029b  lea     r12, [r15+80h]
0x1800202a2  mov     rcx, r12; SRWLock
0x1800202a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800202ab  cmp     qword ptr [r15+88h], 0
0x1800202b3  jnz     short loc_1800202C3
0x1800202b5  mov     rcx, r15; this
0x1800202b8  call    ?LoadAndInitializeDll@ProviderContext@@IEAAJXZ; ProviderContext::LoadAndInitializeDll(void)
0x1800202bd  mov     ebx, eax
0x1800202bf  test    eax, eax
0x1800202c1  js      short loc_180020315
0x1800202c3  lea     rcx, [r15+18h]
0x1800202c7  lea     r8, [rbp+70h+var_E8]
0x1800202cb  lea     rdx, IID_IClassFactory
0x1800202d2  mov     rax, [r15+88h]
0x1800202d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202de  mov     ebx, eax
0x1800202e0  test    eax, eax
0x1800202e2  jns     short loc_180020315
0x1800202e4  lea     rax, WPP_GLOBAL_Control
0x1800202eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202f2  cmp     rcx, rax
0x1800202f5  jz      short loc_180020315
0x1800202f7  cmp     byte ptr [rcx+19h], 2
0x1800202fb  jb      short loc_180020315
0x1800202fd  mov     edx, 11h
0x180020302  mov     r9d, ebx
0x180020305  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x18002030c  mov     rcx, [rcx+10h]
0x180020310  call    WPP_SF_D
0x180020315  mov     rcx, r12; SRWLock
0x180020318  call    cs:__imp_ReleaseSRWLockExclusive
0x18002031e  nop
0x18002031f  test    ebx, ebx
0x180020321  js      loc_1800207E1
0x180020327  lea     r15, [rdi+20h]
0x18002032b  test    esi, esi
0x18002032d  jnz     short loc_180020338
0x18002032f  lea     r8, IID_IAepQuery
0x180020336  jmp     short loc_18002034B
0x180020338  cmp     esi, 2
0x18002033b  lea     r8, IID_IAepServiceQuery
0x180020342  jz      short loc_18002034B
0x180020344  lea     r8, IID_IFederatedAepStoreQuery
0x18002034b  mov     rcx, [rbp+70h+var_E8]
0x18002034f  mov     rax, [rcx]
0x180020352  mov     r9, r15
0x180020355  xor     edx, edx
0x180020357  mov     rax, [rax+18h]
0x18002035b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020360  mov     ebx, eax
0x180020362  test    eax, eax
0x180020364  jnz     loc_1800207E1
0x18002036a  mov     rax, [rdi+38h]
0x18002036e  cmp     [rax+48h], ebx
0x180020371  jz      short loc_1800203AB
0x180020373  mov     rcx, [rsp+170h+ExistingTokenHandle]; ExistingTokenHandle
0x180020378  test    rcx, rcx
0x18002037b  jz      short loc_1800203AB
0x18002037d  lea     r8, [rbp+70h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180020381  lea     edx, [rbx+2]; ImpersonationLevel
0x180020384  call    cs:__imp_DuplicateToken
0x18002038a  test    eax, eax
0x18002038c  jnz     short loc_1800203AB
0x18002038e  call    cs:__imp_GetLastError
0x180020394  mov     ebx, eax
0x180020396  test    eax, eax
0x180020398  jle     short loc_1800203A3
0x18002039a  movzx   ebx, ax
0x18002039d  or      ebx, 80070000h
0x1800203a3  test    ebx, ebx
0x1800203a5  jnz     loc_1800207E1
0x1800203ab  mov     rax, [rbp+70h+DuplicateTokenHandle]
0x1800203af  lea     r12, [rdi+28h]
0x1800203b3  mov     rdx, [rdi+38h]
0x1800203b7  mov     [rsp+170h+var_118], r12
0x1800203bc  mov     [rsp+170h+var_120], rax
0x1800203c1  mov     rax, [rbp+70h+arg_20]
0x1800203c8  mov     [rsp+170h+var_128], rax
0x1800203cd  mov     eax, dword ptr [rbp+70h+var_A0+8]
0x1800203d0  mov     dword ptr [rsp+170h+var_130], eax
0x1800203d4  mov     rax, [rsp+170h+var_108]
0x1800203d9  mov     [rsp+170h+var_150], rax
0x1800203de  mov     r9d, r13d
0x1800203e1  mov     r8, [rbp+70h+var_D0]
0x1800203e5  mov     rdx, [rdx]
0x1800203e8  mov     ecx, esi
0x1800203ea  call    ?Create@CQueryCallback@@SAJW4_PROVIDER_QUERY_TYPE@@PEBG1KPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@1KPEAX4PEAPEAV1@@Z; CQueryCallback::Create(_PROVIDER_QUERY_TYPE,ushort const *,ushort const *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ushort const *,ulong,void *,void *,CQueryCallback * *)
0x1800203ef  mov     ebx, eax
0x1800203f1  test    eax, eax
0x1800203f3  jnz     loc_1800207E1
0x1800203f9  mov     [rbp+70h+DuplicateTokenHandle], 0
0x180020401  mov     rcx, [r12]
0x180020405  mov     rax, [rcx]
0x180020408  mov     rax, [rax]
0x18002040b  test    esi, esi
0x18002040d  jnz     short loc_18002041C
0x18002040f  lea     r8, [rbp+70h+var_D8]
0x180020413  lea     rdx, _GUID_48780fb0_e908_4af1_b350_ef52f6a634e6
0x18002041a  jmp     short loc_18002043A
0x18002041c  cmp     esi, 2
0x18002041f  jnz     short loc_18002042F
0x180020421  lea     r8, [rsp+170h+var_F8]
0x180020426  lea     rdx, _GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d
0x18002042d  jmp     short loc_18002043A
0x18002042f  lea     r8, [rbp+70h+var_F0]
0x180020433  lea     rdx, _GUID_09a26ea8_87fc_4b14_99c8_157168c0070d
0x18002043a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002043f  mov     ebx, eax
0x180020441  test    eax, eax
0x180020443  js      loc_1800207E1
0x180020449  cmp     dword ptr [rbp+70h+var_B0], 6
0x18002044d  jz      loc_1800206E6
0x180020453  mov     eax, dword ptr [rbp+70h+var_B0+4]
0x180020456  test    eax, eax
0x180020458  jz      loc_1800206E6
0x18002045e  cmp     eax, 1
0x180020461  jnz     loc_180020594
0x180020467  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x18002046e  jz      short loc_180020486
0x180020470  mov     r8, [rdi+38h]
0x180020474  mov     r9, r14
0x180020477  mov     r8, [r8]
0x18002047a  lea     rdx, CREATE_PROVIDER_QUERY_START
0x180020481  call    McTemplateU0zp_EventWriteTransfer
0x180020486  mov     r11, [r15]
0x180020489  mov     r10, [r11]
0x18002048c  mov     r8, qword ptr [rbp+70h+var_B0+8]
0x180020490  mov     rcx, r8
0x180020493  test    esi, esi
0x180020495  jnz     short loc_1800204E8
0x180020497  call    DafProviderAepIdOffset
0x18002049c  mov     ecx, eax
0x18002049e  lea     rdx, [r8+rcx*2]
0x1800204a2  mov     eax, dword ptr [rbp+70h+var_A0+8]
0x1800204a5  mov     dword ptr [rsp+170h+var_120], eax
0x1800204a9  mov     r9, [r12]
0x1800204ad  mov     [rsp+170h+var_128], r9
0x1800204b2  mov     r9, qword ptr [rbp+70h+var_90+8]
0x1800204b6  mov     [rsp+170h+var_130], r9
0x1800204bb  mov     r9, qword ptr [rbp+70h+var_60+8]
0x1800204bf  mov     [rsp+170h+var_138], r9
0x1800204c4  mov     r9d, dword ptr [rbp+70h+var_60]
0x1800204c8  mov     dword ptr [rsp+170h+var_140], r9d
0x1800204cd  mov     r9, qword ptr [rbp+70h+var_70+8]
0x1800204d1  mov     [rsp+170h+var_148], r9
0x1800204d6  mov     r9d, dword ptr [rbp+70h+var_70]
0x1800204da  mov     dword ptr [rsp+170h+var_150], r9d
0x1800204df  mov     rax, [r10+20h]
0x1800204e3  jmp     loc_18002057F
0x1800204e8  mov     rbx, [r10+20h]
0x1800204ec  cmp     esi, 2
0x1800204ef  jnz     short loc_180020538
0x1800204f1  mov     r10, [rsp+170h+var_F8]
0x1800204f6  call    DafProviderAepIdOffset
0x1800204fb  mov     ecx, eax
0x1800204fd  lea     rdx, [r8+rcx*2]
0x180020501  mov     eax, dword ptr [rbp+70h+var_A0+8]
0x180020504  mov     dword ptr [rsp+170h+var_120], eax
0x180020508  mov     [rsp+170h+var_128], r10
0x18002050d  mov     rax, qword ptr [rbp+70h+var_90+8]
0x180020511  mov     [rsp+170h+var_130], rax
0x180020516  mov     rax, qword ptr [rbp+70h+var_60+8]
0x18002051a  mov     [rsp+170h+var_138], rax
0x18002051f  mov     eax, dword ptr [rbp+70h+var_60]
0x180020522  mov     dword ptr [rsp+170h+var_140], eax
0x180020526  mov     rax, qword ptr [rbp+70h+var_70+8]
0x18002052a  mov     [rsp+170h+var_148], rax
0x18002052f  mov     eax, dword ptr [rbp+70h+var_70]
0x180020532  mov     dword ptr [rsp+170h+var_150], eax
0x180020536  jmp     short loc_18002057C
0x180020538  mov     r10, [rbp+70h+var_F0]
0x18002053c  call    DafProviderAepIdOffset
0x180020541  mov     ecx, eax
0x180020543  lea     rdx, [r8+rcx*2]
0x180020547  mov     eax, dword ptr [rbp+70h+var_A0+8]
0x18002054a  mov     dword ptr [rsp+170h+var_120], eax
0x18002054e  mov     [rsp+170h+var_128], r10
0x180020553  mov     rcx, qword ptr [rbp+70h+var_90+8]
0x180020557  mov     [rsp+170h+var_130], rcx
0x18002055c  mov     rcx, qword ptr [rbp+70h+var_60+8]
0x180020560  mov     [rsp+170h+var_138], rcx
0x180020565  mov     ecx, dword ptr [rbp+70h+var_60]
0x180020568  mov     dword ptr [rsp+170h+var_140], ecx
0x18002056c  mov     rcx, qword ptr [rbp+70h+var_70+8]
0x180020570  mov     [rsp+170h+var_148], rcx
0x180020575  mov     ecx, dword ptr [rbp+70h+var_70]
0x180020578  mov     dword ptr [rsp+170h+var_150], ecx
0x18002057c  mov     rax, rbx
0x18002057f  mov     r9, [rsp+170h+var_108]
0x180020584  mov     r8d, r13d
0x180020587  mov     rcx, r11
0x18002058a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002058f  jmp     loc_1800207C0
0x180020594  cmp     eax, 2
0x180020597  jnz     loc_1800207E1
0x18002059d  mov     [rsp+170h+ExistingTokenHandle], 0
0x1800205a6  mov     rdx, [rdi+38h]
0x1800205aa  lea     r8, [rsp+170h+ExistingTokenHandle]
0x1800205af  mov     rdx, [rdx]; lpString2
0x1800205b2  mov     rcx, [rbp+70h+var_A0]; unsigned __int16 *
0x1800205b6  call    DafMakeProviderAepIdsList
0x1800205bb  mov     ebx, eax
0x1800205bd  test    eax, eax
0x1800205bf  jnz     loc_1800207E1
0x1800205c5  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 8
0x1800205cc  jz      short loc_1800205E4
0x1800205ce  mov     r8, [rdi+38h]
0x1800205d2  mov     r9, r14
0x1800205d5  mov     r8, [r8]
0x1800205d8  lea     rdx, CREATE_PROVIDER_QUERY_START
0x1800205df  call    McTemplateU0zp_EventWriteTransfer
0x1800205e4  mov     r10, [r15]
0x1800205e7  mov     r11, [r10]
0x1800205ea  mov     eax, dword ptr [rbp+70h+var_A0+8]
0x1800205ed  mov     dword ptr [rsp+170h+var_120], eax
0x1800205f1  test    esi, esi
0x1800205f3  jnz     short loc_18002062D
0x1800205f5  mov     rax, [rbp+70h+var_D8]
0x1800205f9  mov     [rsp+170h+var_128], rax
0x1800205fe  mov     rdx, qword ptr [rbp+70h+var_90+8]
0x180020602  mov     [rsp+170h+var_130], rdx
0x180020607  mov     rdx, qword ptr [rbp+70h+var_60+8]
0x18002060b  mov     [rsp+170h+var_138], rdx
0x180020610  mov     edx, dword ptr [rbp+70h+var_60]
0x180020613  mov     dword ptr [rsp+170h+var_140], edx
0x180020617  mov     rdx, qword ptr [rbp+70h+var_70+8]
0x18002061b  mov     [rsp+170h+var_148], rdx
0x180020620  mov     edx, dword ptr [rbp+70h+var_70]
0x180020623  mov     dword ptr [rsp+170h+var_150], edx
  ... truncated ...
```
