# DhcpRequestParams

- ea: `0x180001490`
- end: `0x180001b49`
- name: `DhcpRequestParams`
- size: `1721`
- prototype: `DWORD __stdcall(DWORD Flags, LPVOID Reserved, LPWSTR AdapterName, LPDHCPCAPI_CLASSID ClassId, DHCPCAPI_PARAMS_ARRAY *__struct_ptr SendParams, DHCPCAPI_PARAMS_ARRAY *__struct_ptr RecdParams, LPBYTE Buffer, LPDWORD pSize, LPWSTR RequestIdStr)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001490`
- `0x180001f90`
- `0x180002620`
- `0x180002760`
- `0x180009920`
- `0x18000f4ec`
- `0x180010aac`
- `0x180012850`
- `0x180012a00`
- `0x180012a40`
- `0x180012ad0`
- `0x180012ba0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001864`
- `RPCRT4!NdrClientCall3` at `0x180001864`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010b9e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010b9e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800017f7`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001896`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800018d3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800017f7`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001896`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800018d3`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001aa4`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001ad4`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001aa4`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001ad4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180001aef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180001aef`
- `WS2_32!__imp_ntohl` at `0x180001925`
- `WS2_32!__imp_ntohl` at `0x1800019a9`
- `WS2_32!__imp_ntohl` at `0x1800019c8`
- `WS2_32!__imp_ntohl` at `0x1800019df`
- `WS2_32!__imp_ntohl` at `0x180001925`
- `WS2_32!__imp_ntohl` at `0x1800019a9`
- `WS2_32!__imp_ntohl` at `0x1800019c8`
- `WS2_32!__imp_ntohl` at `0x1800019df`

## pseudocode

```c
DWORD __stdcall DhcpRequestParams(
        DWORD Flags,
        LPVOID Reserved,
        LPWSTR AdapterName,
        LPDHCPCAPI_CLASSID ClassId,
        DHCPCAPI_PARAMS_ARRAY *SendParams,
        DHCPCAPI_PARAMS_ARRAY *RecdParams,
        LPBYTE Buffer,
        LPDWORD pSize,
        LPWSTR RequestIdStr)
{
  LPWSTR v10; // r13
  DHCPCAPI_PARAMS_ARRAY *v13; // r14
  DWORD Pointer; // ebx
  LPDHCPCAPI_PARAMS *p_Params; // r15
  LPDHCPCAPI_PARAMS Params; // rcx
  LPDHCPCAPI_PARAMS v17; // r9
  ULONG nBytesData; // r8d
  LPBYTE Data; // rdx
  DHCPCAPI_PARAMS_ARRAY *v20; // r12
  DWORD v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // ebx
  __int64 v24; // rdx
  __int64 nParams; // r8
  __int64 v26; // rcx
  LPDHCPCAPI_PARAMS v27; // rax
  unsigned int v28; // r9d
  unsigned int v29; // r10d
  ULONG i; // r8d
  __int64 v31; // rcx
  bool v32; // zf
  char OptionId; // cl
  __int64 v34; // rdx
  __int64 v35; // rax
  LPWSTR CommandLineW; // rax
  int v37; // ecx
  CLIENT_CALL_RETURN v38; // rax
  LPWSTR v39; // rax
  int v40; // ecx
  DWORD v41; // r12d
  unsigned int v42; // r13d
  unsigned int v43; // esi
  __int64 v44; // r14
  u_long v45; // eax
  ULONG v46; // r12d
  u_long *v47; // rbx
  u_long v48; // r13d
  u_long v49; // eax
  u_long v50; // ecx
  __int64 v51; // rsi
  LPDHCPCAPI_PARAMS v52; // rdx
  LPBYTE v54; // [rsp+60h] [rbp-88h]
  u_long Size; // [rsp+70h] [rbp-78h]
  __int128 v56; // [rsp+78h] [rbp-70h] BYREF
  __int128 v57; // [rsp+88h] [rbp-60h]
  __int128 v58; // [rsp+98h] [rbp-50h] BYREF
  int v59; // [rsp+A8h] [rbp-40h]
  __int64 v60; // [rsp+B0h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v61; // [rsp+B8h] [rbp-30h]
  int v62; // [rsp+100h] [rbp+18h]

  v62 = (int)AdapterName;
  v10 = AdapterName;
  v58 = 0;
  v56 = 0;
  v57 = 0;
  v60 = 0;
  v13 = RecdParams;
  v54 = Buffer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_LqSqqqqqS(
      Flags,
      (_DWORD)Reserved,
      (_DWORD)AdapterName,
      Flags,
      (char)Reserved,
      (__int64)AdapterName,
      (char)ClassId,
      (char)SendParams,
      (char)RecdParams,
      (char)Buffer,
      (char)pSize,
      (__int64)RequestIdStr);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 114, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    if ( !v10 )
    {
LABEL_5:
      Pointer = 87;
      goto LABEL_96;
    }
    if ( !pSize )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( (Flags & 3) == 0 )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( (Flags & 0xFFFFFFFC) != 0 )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( Reserved )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( !RecdParams->nParams )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( !Buffer && *pSize )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    if ( ClassId )
    {
      if ( ClassId->Flags )
      {
        Pointer = 87;
        goto LABEL_96;
      }
      if ( !ClassId->Data )
      {
        Pointer = 87;
        goto LABEL_96;
      }
      if ( !ClassId->nBytesData )
      {
        Pointer = 87;
        goto LABEL_96;
      }
    }
    p_Params = &RecdParams->Params;
    Params = RecdParams->Params;
    if ( !Params )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    v17 = SendParams->Params;
    if ( !v17 && SendParams->nParams )
    {
      Pointer = 87;
      goto LABEL_96;
    }
    Pointer = 0;
    if ( (Flags & 1) != 0 )
    {
      if ( ClassId )
        nBytesData = ClassId->nBytesData;
      else
        nBytesData = 0;
      if ( ClassId )
        Data = ClassId->Data;
      else
        LODWORD(Data) = 0;
      v20 = SendParams;
      v21 = DhcpRegistryPersistentRequestParams(
              (int)v10,
              (int)Data,
              nBytesData,
              (int)v17,
              SendParams->nParams,
              (__int64)Params,
              RecdParams->nParams,
              RequestIdStr);
      Pointer = v21;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_DS(1028, 115, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v21, (__int64)v10);
      if ( Pointer )
        goto LABEL_96;
    }
    else
    {
      v20 = SendParams;
    }
    if ( (Flags & 2) != 0 )
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
      nParams = RecdParams->nParams;
      while ( (unsigned int)v24 < (unsigned int)nParams )
      {
        v26 = (unsigned int)v24;
        v27 = *p_Params;
        if ( (*p_Params)[v26].nBytesData || v27[v26].Data )
          goto LABEL_5;
        if ( v27[v26].IsVendor )
          ++v22;
        else
          ++v23;
        v24 = (unsigned int)(v24 + 1);
      }
      LODWORD(v57) = v22;
      LODWORD(v56) = v23;
      if ( v23 )
        *((_QWORD *)&v56 + 1) = DhcpAlloc(v23, v24, nParams);
      else
        *((_QWORD *)&v56 + 1) = 0;
      if ( v22 )
        *((_QWORD *)&v57 + 1) = DhcpAlloc(v22, v24, nParams);
      else
        *((_QWORD *)&v57 + 1) = 0;
      if ( !v23 || *((_QWORD *)&v56 + 1) )
      {
        if ( !v22 || *((_QWORD *)&v57 + 1) )
        {
          v28 = 0;
          v29 = 0;
          for ( i = 0; i < RecdParams->nParams; ++i )
          {
            v31 = i;
            v32 = !(*p_Params)[v31].IsVendor;
            OptionId = (*p_Params)[v31].OptionId;
            if ( v32 )
            {
              v34 = v29;
              v35 = *((_QWORD *)&v56 + 1);
              ++v29;
            }
            else
            {
              v34 = v28;
              v35 = *((_QWORD *)&v57 + 1);
              ++v28;
            }
            *(_BYTE *)(v34 + v35) = OptionId;
          }
          Pointer = DhcpAdapterNameToIfId(v10, &v60);
          if ( !Pointer )
          {
            if ( (xmmword_18001E1E0 & 0x10) != 0 )
            {
              CommandLineW = GetCommandLineW();
              WPP_SF_SS(
                v37,
                116,
                (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
                (_DWORD)v10,
                (__int64)CommandLineW);
            }
            v38.Pointer = NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0xCu,
                            0,
                            0,
                            &v60,
                            ClassId,
                            v20,
                            &v56,
                            &v58).Pointer;
            Pointer = (DWORD)v38.Pointer;
            v61.Pointer = v38.Pointer;
            v59 = (int)v38.Pointer;
            if ( (xmmword_18001E1E0 & 0x10) != 0 )
            {
              v39 = GetCommandLineW();
              WPP_SF_DSS(
                v40,
                117,
                (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
                Pointer,
                (__int64)v10,
                (__int64)v39);
            }
            if ( !Pointer )
            {
              v41 = 0;
              v42 = v58;
              v43 = v58;
              if ( (unsigned int)v58 > 0xC )
              {
                v44 = *((_QWORD *)&v58 + 1);
                do
                {
                  v43 -= 12;
                  v45 = ntohl(*(_DWORD *)(v44 + 8));
                  if ( v43 < v45 )
                    break;
                  v43 -= v45;
                  v41 += v45;
                  v44 += v45 + 12LL;
                }
                while ( v43 > 0xC );
                v42 = v58;
                v13 = RecdParams;
              }
              if ( v43 )
              {
                Pointer = 1359;
                LODWORD(v10) = v62;
              }
              else if ( *pSize >= v41 )
              {
                v46 = 0;
                if ( v42 > 0xC )
                {
                  v47 = (u_long *)*((_QWORD *)&v58 + 1);
                  do
                  {
                    v48 = v42 - 12;
                    v49 = ntohl(v47[2]);
                    v50 = v49;
                    Size = v49;
                    if ( v48 < v49 )
                      break;
                    v42 = v48 - v49;
                    if ( v46 < v13->nParams )
                    {
                      v51 = v46;
                      (*p_Params)[v51].OptionId = ntohl(*v47);
                      (*p_Params)[v51].IsVendor = ntohl(v47[1]) != 0;
                      v50 = Size;
                      (*p_Params)[v51].nBytesData = Size;
                      v52 = *p_Params;
                      if ( Size )
                      {
                        v52[v51].Data = v54;
                        memcpy_0(v54, v47 + 3, Size);
                        v54 += Size;
                        v50 = Size;
                      }
                      else
                      {
                        v52[v51].Data = 0;
                      }
                    }
                    ++v46;
                    v47 = (u_long *)((char *)v47 + v50 + 12);
                  }
                  while ( v42 > 0xC );
                  Pointer = (DWORD)v61.Pointer;
                }
                v13->nParams = v46;
                LODWORD(v10) = v62;
              }
              else
              {
                *pSize = v41;
                Pointer = 234;
                LODWORD(v10) = v62;
              }
            }
          }
        }
        else
        {
          Pointer = 14;
        }
      }
      else
      {
        Pointer = 14;
      }
    }
  }
LABEL_96:
  if ( *((_QWORD *)&v56 + 1) )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)&v56 + 1));
    *((_QWORD *)&v56 + 1) = 0;
  }
  if ( *((_QWORD *)&v57 + 1) )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)&v57 + 1));
    *((_QWORD *)&v57 + 1) = 0;
  }
  if ( *((_QWORD *)&v58 + 1) )
  {
    LocalFree(*((HLOCAL *)&v58 + 1));
    *((_QWORD *)&v58 + 1) = 0;
  }
  LODWORD(v58) = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 118, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, (_DWORD)v10, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180001490  mov     rax, rsp
0x180001493  mov     [rax+8], rbx
0x180001497  mov     [rax+10h], rsi
0x18000149b  mov     [rax+20h], r9
0x18000149f  mov     [rax+18h], r8
0x1800014a3  push    rdi
0x1800014a4  push    r12
0x1800014a6  push    r13
0x1800014a8  push    r14
0x1800014aa  push    r15
0x1800014ac  sub     rsp, 0C0h
0x1800014b3  mov     r15, r9
0x1800014b6  mov     r13, r8
0x1800014b9  mov     rbx, rdx
0x1800014bc  mov     esi, ecx
0x1800014be  xorps   xmm0, xmm0
0x1800014c1  movups  xmmword ptr [rax-50h], xmm0
0x1800014c5  xorps   xmm1, xmm1
0x1800014c8  movups  xmmword ptr [rax-70h], xmm1
0x1800014cc  movups  xmmword ptr [rax-60h], xmm1
0x1800014d0  xor     edi, edi
0x1800014d2  mov     [rax-38h], rdi
0x1800014d6  mov     r12, [rsp+0E8h+RequestIdStr]
0x1800014de  mov     r14, [rsp+0E8h+RecdParams]
0x1800014e6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800014ed  jz      short loc_18000153E
0x1800014ef  mov     [rsp+0E8h+var_90], r12
0x1800014f4  mov     rax, [rsp+0E8h+pSize]
0x1800014fc  mov     [rsp+0E8h+var_98], rax
0x180001501  mov     rax, [rsp+0E8h+Buffer]
0x180001509  mov     [rsp+0E8h+var_88], rax
0x18000150e  mov     [rsp+0E8h+var_A0], rax
0x180001513  mov     [rsp+0E8h+var_A8], r14
0x180001518  mov     rax, [rsp+0E8h+SendParams]
0x180001520  mov     [rsp+0E8h+psz], rax
0x180001525  mov     qword ptr [rsp+0E8h+var_B8], r9
0x18000152a  mov     [rsp+0E8h+var_C0], r8
0x18000152f  mov     qword ptr [rsp+0E8h+var_C8], rdx
0x180001534  mov     r9d, ecx
0x180001537  call    WPP_SF_LqSqqqqqS
0x18000153c  jmp     short loc_18000154B
0x18000153e  mov     rax, [rsp+0E8h+Buffer]
0x180001546  mov     [rsp+0E8h+var_88], rax
0x18000154b  call    DhcpIsFSEGuestSystem
0x180001550  test    eax, eax
0x180001552  jnz     loc_180001A5B
0x180001558  test    r13, r13
0x18000155b  jnz     short loc_180001567
0x18000155d  mov     ebx, 57h ; 'W'
0x180001562  jmp     loc_180001A82
0x180001567  mov     rcx, [rsp+0E8h+pSize]
0x18000156f  test    rcx, rcx
0x180001572  jnz     short loc_18000157E
0x180001574  mov     ebx, 57h ; 'W'
0x180001579  jmp     loc_180001A82
0x18000157e  test    sil, 3
0x180001582  jnz     short loc_18000158E
0x180001584  mov     ebx, 57h ; 'W'
0x180001589  jmp     loc_180001A82
0x18000158e  test    esi, 0FFFFFFFCh
0x180001594  jz      short loc_1800015A0
0x180001596  mov     ebx, 57h ; 'W'
0x18000159b  jmp     loc_180001A82
0x1800015a0  test    rbx, rbx
0x1800015a3  jz      short loc_1800015AF
0x1800015a5  mov     ebx, 57h ; 'W'
0x1800015aa  jmp     loc_180001A82
0x1800015af  mov     eax, [r14]
0x1800015b2  test    eax, eax
0x1800015b4  jnz     short loc_1800015C0
0x1800015b6  mov     ebx, 57h ; 'W'
0x1800015bb  jmp     loc_180001A82
0x1800015c0  cmp     [rsp+0E8h+Buffer], rdi
0x1800015c8  jnz     short loc_1800015D8
0x1800015ca  cmp     [rcx], edi
0x1800015cc  jz      short loc_1800015D8
0x1800015ce  mov     ebx, 57h ; 'W'
0x1800015d3  jmp     loc_180001A82
0x1800015d8  test    r15, r15
0x1800015db  jz      short loc_18000160C
0x1800015dd  cmp     [r15], edi
0x1800015e0  jz      short loc_1800015EC
0x1800015e2  mov     ebx, 57h ; 'W'
0x1800015e7  jmp     loc_180001A82
0x1800015ec  cmp     [r15+8], rdi
0x1800015f0  jnz     short loc_1800015FC
0x1800015f2  mov     ebx, 57h ; 'W'
0x1800015f7  jmp     loc_180001A82
0x1800015fc  cmp     [r15+10h], edi
0x180001600  ja      short loc_18000160C
0x180001602  mov     ebx, 57h ; 'W'
0x180001607  jmp     loc_180001A82
0x18000160c  lea     r15, [r14+8]
0x180001610  mov     rcx, [r15]
0x180001613  test    rcx, rcx
0x180001616  jnz     short loc_180001622
0x180001618  mov     ebx, 57h ; 'W'
0x18000161d  jmp     loc_180001A82
0x180001622  mov     rdx, [rsp+0E8h+SendParams]
0x18000162a  mov     r9, [rdx+8]; int
0x18000162e  test    r9, r9
0x180001631  jnz     short loc_180001641
0x180001633  cmp     [rdx], edi
0x180001635  jz      short loc_180001641
0x180001637  mov     ebx, 57h ; 'W'
0x18000163c  jmp     loc_180001A82
0x180001641  mov     ebx, edi
0x180001643  test    sil, 1
0x180001647  jz      short loc_1800016C5
0x180001649  mov     rdx, [rsp+0E8h+arg_18]
0x180001651  test    rdx, rdx
0x180001654  jz      short loc_18000165C
0x180001656  mov     r8d, [rdx+10h]
0x18000165a  jmp     short loc_18000165F
0x18000165c  mov     r8d, edi; int
0x18000165f  test    rdx, rdx
0x180001662  jz      short loc_18000166A
0x180001664  mov     rdx, [rdx+8]
0x180001668  jmp     short loc_18000166D
0x18000166a  mov     rdx, rdi; int
0x18000166d  mov     [rsp+0E8h+psz], r12; psz
0x180001672  mov     [rsp+0E8h+var_B8], eax; int
0x180001676  mov     [rsp+0E8h+var_C0], rcx; __int64
0x18000167b  mov     r12, [rsp+0E8h+SendParams]
0x180001683  mov     eax, [r12]
0x180001687  mov     [rsp+0E8h+var_C8], eax; int
0x18000168b  mov     rcx, r13; int
0x18000168e  call    DhcpRegistryPersistentRequestParams
0x180001693  mov     ebx, eax
0x180001695  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000169c  jz      short loc_1800016BC
0x18000169e  mov     edx, 73h ; 's'
0x1800016a3  mov     ecx, 404h
0x1800016a8  mov     qword ptr [rsp+0E8h+var_C8], r13
0x1800016ad  mov     r9d, eax
0x1800016b0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800016b7  call    WPP_SF_DS
0x1800016bc  test    ebx, ebx
0x1800016be  jz      short loc_1800016C8
0x1800016c0  jmp     loc_180001A82
0x1800016c5  mov     r12, rdx
0x1800016c8  test    sil, 2
0x1800016cc  jz      loc_180001A82
0x1800016d2  mov     [rsp+0E8h+var_80], r15
0x1800016d7  mov     esi, edi
0x1800016d9  mov     ebx, edi
0x1800016db  mov     edx, edi
0x1800016dd  mov     r8d, [r14]
0x1800016e0  cmp     edx, r8d
0x1800016e3  jnb     short loc_180001713
0x1800016e5  mov     ecx, edx
0x1800016e7  shl     rcx, 5
0x1800016eb  mov     rax, [r15]
0x1800016ee  cmp     [rcx+rax+18h], edi
0x1800016f2  jnz     loc_18000155D
0x1800016f8  cmp     [rcx+rax+10h], rdi
0x1800016fd  jnz     loc_18000155D
0x180001703  cmp     [rcx+rax+8], edi
0x180001707  jz      short loc_18000170D
0x180001709  inc     esi
0x18000170b  jmp     short loc_18000170F
0x18000170d  inc     ebx
0x18000170f  inc     edx
0x180001711  jmp     short loc_1800016E0
0x180001713  mov     [rsp+0E8h+var_60], esi
0x18000171a  mov     [rsp+0E8h+var_70], ebx
0x18000171e  test    ebx, ebx
0x180001720  jz      short loc_180001733
0x180001722  mov     ecx, ebx
0x180001724  call    DhcpAlloc
0x180001729  mov     [rsp+0E8h+lpMem], rax
0x180001731  jmp     short loc_18000173B
0x180001733  mov     [rsp+0E8h+lpMem], rdi
0x18000173b  test    esi, esi
0x18000173d  jz      short loc_180001750
0x18000173f  mov     ecx, esi
0x180001741  call    DhcpAlloc
0x180001746  mov     [rsp+0E8h+var_58], rax
0x18000174e  jmp     short loc_180001758
0x180001750  mov     [rsp+0E8h+var_58], rdi
0x180001758  test    ebx, ebx
0x18000175a  jz      short loc_180001770
0x18000175c  cmp     [rsp+0E8h+lpMem], rdi
0x180001764  jnz     short loc_180001770
0x180001766  mov     ebx, 0Eh
0x18000176b  jmp     loc_180001A82
0x180001770  test    esi, esi
0x180001772  jz      short loc_180001788
0x180001774  cmp     [rsp+0E8h+var_58], rdi
0x18000177c  jnz     short loc_180001788
0x18000177e  mov     ebx, 0Eh
0x180001783  jmp     loc_180001A82
0x180001788  mov     r9d, edi
0x18000178b  mov     r10d, edi
0x18000178e  mov     r8d, edi
0x180001791  cmp     [r14], edi
0x180001794  jbe     short loc_1800017D4
0x180001796  mov     ecx, r8d
0x180001799  shl     rcx, 5
0x18000179d  mov     rax, [r15]
0x1800017a0  cmp     [rcx+rax+8], edi
0x1800017a4  movzx   ecx, byte ptr [rcx+rax+4]
0x1800017a9  jz      short loc_1800017BB
0x1800017ab  mov     edx, r9d
0x1800017ae  mov     rax, [rsp+0E8h+var_58]
0x1800017b6  inc     r9d
0x1800017b9  jmp     short loc_1800017C9
0x1800017bb  mov     edx, r10d
0x1800017be  mov     rax, [rsp+0E8h+lpMem]
0x1800017c6  inc     r10d
0x1800017c9  mov     [rdx+rax], cl
0x1800017cc  inc     r8d
0x1800017cf  cmp     r8d, [r14]
0x1800017d2  jb      short loc_180001796
0x1800017d4  lea     rdx, [rsp+0E8h+var_38]
0x1800017dc  mov     rcx, r13
0x1800017df  call    DhcpAdapterNameToIfId
0x1800017e4  mov     ebx, eax
0x1800017e6  test    eax, eax
0x1800017e8  jnz     loc_180001A82
0x1800017ee  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800017f5  jz      short loc_180001817
0x1800017f7  call    cs:__imp_GetCommandLineW
0x1800017fd  mov     edx, 74h ; 't'
0x180001802  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180001807  mov     r9, r13
0x18000180a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180001811  call    WPP_SF_SS
0x180001816  nop
0x180001817  mov     [rsp+0E8h+Size], rdi
0x18000181c  lea     rax, [rsp+0E8h+var_50]
0x180001824  mov     [rsp+0E8h+var_A8], rax
0x180001829  lea     rax, [rsp+0E8h+var_70]
0x18000182e  mov     [rsp+0E8h+psz], rax
0x180001833  mov     qword ptr [rsp+0E8h+var_B8], r12
0x180001838  mov     rax, [rsp+0E8h+arg_18]
0x180001840  mov     [rsp+0E8h+var_C0], rax
0x180001845  lea     rax, [rsp+0E8h+var_38]
0x18000184d  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180001852  xor     r9d, r9d
0x180001855  xor     r8d, r8d; pReturnValue
0x180001858  mov     edx, 0Ch; nProcNum
0x18000185d  lea     rcx, pProxyInfo; pProxyInfo
0x180001864  call    cs:__imp_NdrClientCall3
0x18000186a  mov     rbx, rax
0x18000186d  mov     [rsp+0E8h+var_30], rax
0x180001875  mov     [rsp+0E8h+Size], rax
0x18000187a  mov     [rsp+0E8h+var_40], eax
0x180001881  jmp     short loc_1800018CA
0x180001883  mov     edi, eax
0x180001885  mov     ebx, eax
0x180001887  mov     [rsp+0E8h+var_30], rbx
0x18000188f  mov     [rsp+0E8h+var_40], eax
0x180001896  call    cs:__imp_GetCommandLineW
0x18000189c  mov     rdx, rax
0x18000189f  mov     ecx, ebx
0x1800018a1  call    TraceRpcException
0x1800018a6  xor     edi, edi
0x1800018a8  mov     rdx, [rsp+0E8h+Buffer]
0x1800018b0  mov     [rsp+0E8h+var_88], rdx
0x1800018b5  mov     r14, [rsp+0E8h+RecdParams]
0x1800018bd  mov     r15, [rsp+0E8h+var_80]
0x1800018c2  mov     r13, [rsp+0E8h+arg_10]
0x1800018ca  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800018d1  jz      short loc_1800018F7
0x1800018d3  call    cs:__imp_GetCommandLineW
0x1800018d9  mov     edx, 75h ; 'u'
0x1800018de  mov     [rsp+0E8h+var_C0], rax
0x1800018e3  mov     qword ptr [rsp+0E8h+var_C8], r13
0x1800018e8  mov     r9d, ebx
0x1800018eb  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800018f2  call    WPP_SF_DSS
0x1800018f7  test    ebx, ebx
0x1800018f9  jnz     loc_180001A82
0x1800018ff  mov     r12d, edi
0x180001902  mov     r13d, [rsp+0E8h+var_50]
0x18000190a  mov     esi, r13d
0x18000190d  mov     rax, [rsp+0E8h+hMem]
0x180001915  cmp     r13d, 0Ch
0x180001919  jbe     short loc_180001952
0x18000191b  mov     r14, rax
0x18000191e  add     esi, 0FFFFFFF4h
0x180001921  mov     ecx, [r14+8]; netlong
0x180001925  call    cs:__imp_ntohl
0x18000192b  cmp     esi, eax
0x18000192d  jb      short loc_180001942
0x18000192f  sub     esi, eax
0x180001931  add     r12d, eax
0x180001934  mov     eax, eax
0x180001936  add     r14, 0Ch
0x18000193a  add     r14, rax
0x18000193d  cmp     esi, 0Ch
0x180001940  ja      short loc_18000191E
0x180001942  mov     r13d, [rsp+0E8h+var_50]
0x18000194a  mov     r14, [rsp+0E8h+RecdParams]
0x180001952  test    esi, esi
0x180001954  jz      short loc_180001968
0x180001956  mov     ebx, 54Fh
0x18000195b  mov     r13, [rsp+0E8h+arg_10]
0x180001963  jmp     loc_180001A82
  ... truncated ...
```
