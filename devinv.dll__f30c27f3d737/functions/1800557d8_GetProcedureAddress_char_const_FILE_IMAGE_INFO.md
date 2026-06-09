# GetProcedureAddress(char const *,_FILE_IMAGE_INFO *)

- ea: `0x1800557d8`
- end: `0x180055bdf`
- name: `?GetProcedureAddress@@YAPEAXPEBDPEAU_FILE_IMAGE_INFO@@@Z`
- size: `1031`
- prototype: `void *(const char *, struct _FILE_IMAGE_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180055c90`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800538cc`
- `0x1800557d8`
- `0x180055be8`
- `0x18005644c`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `dbghelp!ImageDirectoryEntryToData` at `0x180055805`
- `dbghelp!ImageDirectoryEntryToData` at `0x180055805`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055bc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055bc1`

## string_xrefs

- `0x18005582a`: `GetProcedureAddress`
- `0x180055872`: `GetProcedureAddress`
- `0x1800558f2`: `GetProcedureAddress`
- `0x180055947`: `GetProcedureAddress`
- `0x180055a2e`: `GetProcedureAddress`
- `0x180055a7e`: `GetProcedureAddress`
- `0x180055b19`: `GetProcedureAddress`
- `0x180055b63`: `GetProcedureAddress`
- `0x1800558eb`: `Invalid Export Directory Entry size returned: %u`
- `0x18005596b`: `Invalid Export Directory Entry size returned: %u`
- `0x1800559a2`: `Invalid Export Directory Entry size returned: %u`

## pseudocode

```c
unsigned __int64 __fastcall GetProcedureAddress(const char *a1, PVOID *a2)
{
  __int64 v3; // rsi
  unsigned int *v4; // rax
  unsigned int *v5; // rdi
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  ULONG v10; // ebx
  FILE *v11; // rax
  FILE *v12; // rax
  unsigned int *v13; // r15
  unsigned __int64 v14; // r14
  const char *v15; // rcx
  unsigned __int64 v16; // r12
  int ProcedureOrdinal; // eax
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  ULONG v25; // [rsp+80h] [rbp+8h] BYREF
  int v26; // [rsp+84h] [rbp+Ch]

  v26 = HIDWORD(a1);
  v25 = 0;
  v3 = 0;
  v4 = (unsigned int *)ImageDirectoryEntryToData(a2[3], 0, 0, &v25);
  v5 = v4;
  if ( v4 )
  {
    if ( v25 >= 0x28 )
    {
      v13 = (unsigned int *)MapRelativeAddress((struct _FILE_IMAGE_INFO *)a2, v4[8]);
      v14 = MapRelativeAddress((struct _FILE_IMAGE_INFO *)a2, v5[9]);
      v16 = MapRelativeAddress((struct _FILE_IMAGE_INFO *)a2, v5[7]);
      if ( v16 && v14 && v13 )
      {
        ProcedureOrdinal = GetProcedureOrdinal(v15, (struct _FILE_IMAGE_INFO *)a2, v5[6], v13);
        if ( ProcedureOrdinal >= 0 )
        {
          _mm_lfence();
          return MapRelativeAddress(
                   (struct _FILE_IMAGE_INFO *)a2,
                   *(_DWORD *)(v16 + 4LL * *(unsigned __int16 *)(v14 + 2LL * ProcedureOrdinal)));
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
        {
          AslLogCallPrintf(3, "GetProcedureAddress", 561, "Procedure [%hs] not found.", "Microsoft_WDF_UMDF_Version");
        }
        else
        {
          AslLogCallPrintf(2, "GetProcedureAddress", 565, "Procedure [%hs] not found.", "Microsoft_WDF_UMDF_Version");
          if ( EnableDevInvStdErrLog )
          {
            v18 = o___acrt_iob_func_0(2u);
            fprintf(v18, "Warning: %s, %u: ", "GetProcedureAddress", 565);
            v19 = o___acrt_iob_func_0(2u);
            fprintf(v19, "Procedure [%hs] not found.", "Microsoft_WDF_UMDF_Version");
            v20 = o___acrt_iob_func_0(2u);
            fprintf(v20, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(50331648, "Procedure [%hs] not found.", "Microsoft_WDF_UMDF_Version");
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(1, "GetProcedureAddress", 542, "MapRelativeAddress failed on exported Functions");
      }
      else
      {
        AslLogCallPrintf(2, "GetProcedureAddress", 546, "MapRelativeAddress failed on exported Functions");
        if ( EnableDevInvStdErrLog )
        {
          v21 = o___acrt_iob_func_0(2u);
          fprintf(v21, "Error: %s, %u: ", "GetProcedureAddress", 546);
          v22 = o___acrt_iob_func_0(2u);
          fprintf(v22, "MapRelativeAddress failed on exported Functions");
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "MapRelativeAddress failed on exported Functions");
      }
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetProcedureAddress", 517, "Invalid Export Directory Entry size returned: %u", v25);
    }
    else
    {
      AslLogCallPrintf(2, "GetProcedureAddress", 521, "Invalid Export Directory Entry size returned: %u", v25);
      if ( EnableDevInvStdErrLog )
      {
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "Error: %s, %u: ", "GetProcedureAddress", 521);
        v10 = v25;
        v11 = o___acrt_iob_func_0(2u);
        fprintf(v11, "Invalid Export Directory Entry size returned: %u", v10);
        v12 = o___acrt_iob_func_0(2u);
        fprintf(v12, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Invalid Export Directory Entry size returned: %u", v25);
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
  {
    AslLogCallPrintf(3, "GetProcedureAddress", 505, "Image does not have an exports section.");
  }
  else
  {
    AslLogCallPrintf(2, "GetProcedureAddress", 509, "Image does not have an exports section.");
    if ( EnableDevInvStdErrLog )
    {
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "Warning: %s, %u: ", "GetProcedureAddress", 509);
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Image does not have an exports section.");
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(50331648, "Image does not have an exports section.");
  }
  return v3;
}

```

## disassembly

```asm
0x1800557d8  mov     rax, rsp
0x1800557db  mov     [rax+8], rcx
0x1800557df  push    rbx
0x1800557e0  push    rsi
0x1800557e1  push    rdi
0x1800557e2  push    r12
0x1800557e4  push    r14
0x1800557e6  push    r15
0x1800557e8  sub     rsp, 48h
0x1800557ec  mov     rbx, rdx
0x1800557ef  mov     dword ptr [rax+8], 0
0x1800557f6  xor     esi, esi
0x1800557f8  xor     r8d, r8d; DirectoryEntry
0x1800557fb  lea     r9, [rax+8]; Size
0x1800557ff  xor     edx, edx; MappedAsImage
0x180055801  mov     rcx, [rbx+18h]; Base
0x180055805  call    cs:__imp_ImageDirectoryEntryToData
0x18005580b  mov     rdi, rax
0x18005580e  test    rax, rax
0x180055811  jnz     loc_1800558D1
0x180055817  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005581e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180055823  lea     r9, aImageDoesNotHa; "Image does not have an exports section."
0x18005582a  lea     rdx, aGetproceduread; "GetProcedureAddress"
0x180055831  test    al, al
0x180055833  jz      short loc_180055848
0x180055835  mov     r8d, 1F9h
0x18005583b  lea     ecx, [rsi+3]
0x18005583e  call    AslLogCallPrintf
0x180055843  jmp     loc_1800558CC
0x180055848  mov     ebx, 1FDh
0x18005584d  mov     r8d, ebx
0x180055850  mov     edi, 2
0x180055855  mov     ecx, edi
0x180055857  call    AslLogCallPrintf
0x18005585c  cmp     cs:EnableDevInvStdErrLog, 0
0x180055863  jz      short loc_1800558B1
0x180055865  mov     ecx, edi; Ix
0x180055867  call    _o___acrt_iob_func_0
0x18005586c  mov     rcx, rax; Stream
0x18005586f  mov     r9d, ebx
0x180055872  lea     r8, aGetproceduread; "GetProcedureAddress"
0x180055879  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180055880  call    fprintf
0x180055885  mov     ecx, edi; Ix
0x180055887  call    _o___acrt_iob_func_0
0x18005588c  mov     rcx, rax; Stream
0x18005588f  lea     rdx, aImageDoesNotHa; "Image does not have an exports section."
0x180055896  call    fprintf
0x18005589b  mov     ecx, edi; Ix
0x18005589d  call    _o___acrt_iob_func_0
0x1800558a2  mov     rcx, rax; Stream
0x1800558a5  lea     rdx, asc_18011EAD8; "\n"
0x1800558ac  call    fprintf
0x1800558b1  cmp     cs:g_DeviceMapLogFunction, 0
0x1800558b9  jz      short loc_1800558CC
0x1800558bb  lea     rdx, aImageDoesNotHa; "Image does not have an exports section."
0x1800558c2  mov     ecx, 3000000h
0x1800558c7  call    TraceMessageCallback
0x1800558cc  jmp     loc_180055BCE
0x1800558d1  cmp     [rsp+78h+arg_0], 28h ; '('
0x1800558d9  jnb     loc_1800559B8
0x1800558df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800558e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800558eb  lea     r9, aInvalidExportD; "Invalid Export Directory Entry size ret"...
0x1800558f2  lea     rdx, aGetproceduread; "GetProcedureAddress"
0x1800558f9  test    al, al
0x1800558fb  mov     eax, [rsp+78h+arg_0]
0x180055902  mov     dword ptr [rsp+78h+var_58], eax
0x180055906  jz      short loc_18005591D
0x180055908  mov     r8d, 205h
0x18005590e  mov     ecx, 1
0x180055913  call    AslLogCallPrintf
0x180055918  jmp     loc_1800559B3
0x18005591d  mov     ebx, 209h
0x180055922  mov     r8d, ebx
0x180055925  mov     edi, 2
0x18005592a  mov     ecx, edi
0x18005592c  call    AslLogCallPrintf
0x180055931  cmp     cs:EnableDevInvStdErrLog, 0
0x180055938  jz      short loc_180055990
0x18005593a  mov     ecx, edi; Ix
0x18005593c  call    _o___acrt_iob_func_0
0x180055941  mov     rcx, rax; Stream
0x180055944  mov     r9d, ebx
0x180055947  lea     r8, aGetproceduread; "GetProcedureAddress"
0x18005594e  lea     rdx, Format; "Error: %s, %u: "
0x180055955  call    fprintf
0x18005595a  mov     ebx, [rsp+78h+arg_0]
0x180055961  mov     ecx, edi; Ix
0x180055963  call    _o___acrt_iob_func_0
0x180055968  mov     r8d, ebx
0x18005596b  lea     rdx, aInvalidExportD; "Invalid Export Directory Entry size ret"...
0x180055972  mov     rcx, rax; Stream
0x180055975  call    fprintf
0x18005597a  mov     ecx, edi; Ix
0x18005597c  call    _o___acrt_iob_func_0
0x180055981  mov     rcx, rax; Stream
0x180055984  lea     rdx, asc_18011EAD8; "\n"
0x18005598b  call    fprintf
0x180055990  cmp     cs:g_DeviceMapLogFunction, 0
0x180055998  jz      short loc_1800559B3
0x18005599a  mov     r8d, [rsp+78h+arg_0]
0x1800559a2  lea     rdx, aInvalidExportD; "Invalid Export Directory Entry size ret"...
0x1800559a9  mov     ecx, 2000000h
0x1800559ae  call    TraceMessageCallback
0x1800559b3  jmp     loc_180055BCE
0x1800559b8  mov     edx, [rax+20h]; unsigned int
0x1800559bb  mov     rcx, rbx; struct _FILE_IMAGE_INFO *
0x1800559be  call    ?MapRelativeAddress@@YA_KPEAU_FILE_IMAGE_INFO@@K@Z; MapRelativeAddress(_FILE_IMAGE_INFO *,ulong)
0x1800559c3  mov     r15, rax
0x1800559c6  mov     edx, [rdi+24h]; unsigned int
0x1800559c9  mov     rcx, rbx; struct _FILE_IMAGE_INFO *
0x1800559cc  call    ?MapRelativeAddress@@YA_KPEAU_FILE_IMAGE_INFO@@K@Z; MapRelativeAddress(_FILE_IMAGE_INFO *,ulong)
0x1800559d1  mov     r14, rax
0x1800559d4  mov     edx, [rdi+1Ch]; unsigned int
0x1800559d7  mov     rcx, rbx; struct _FILE_IMAGE_INFO *
0x1800559da  call    ?MapRelativeAddress@@YA_KPEAU_FILE_IMAGE_INFO@@K@Z; MapRelativeAddress(_FILE_IMAGE_INFO *,ulong)
0x1800559df  mov     r12, rax
0x1800559e2  test    rax, rax
0x1800559e5  jz      loc_180055B06
0x1800559eb  test    r14, r14
0x1800559ee  jz      loc_180055B06
0x1800559f4  test    r15, r15
0x1800559f7  jz      loc_180055B06
0x1800559fd  mov     r9, r15; unsigned int *
0x180055a00  mov     r8d, [rdi+18h]; unsigned int
0x180055a04  mov     rdx, rbx; struct _FILE_IMAGE_INFO *
0x180055a07  call    ?GetProcedureOrdinal@@YAHPEBDPEAU_FILE_IMAGE_INFO@@KPEAK@Z; GetProcedureOrdinal(char const *,_FILE_IMAGE_INFO *,ulong,ulong *)
0x180055a0c  test    eax, eax
0x180055a0e  jns     loc_180055AE3
0x180055a14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180055a1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180055a20  lea     rbx, Str1; "Microsoft_WDF_UMDF_Version"
0x180055a27  lea     r9, aProcedureHsNot; "Procedure [%hs] not found."
0x180055a2e  lea     rdx, aGetproceduread; "GetProcedureAddress"
0x180055a35  mov     [rsp+78h+var_58], rbx
0x180055a3a  test    al, al
0x180055a3c  jz      short loc_180055A53
0x180055a3e  mov     r8d, 231h
0x180055a44  mov     ecx, 3
0x180055a49  call    AslLogCallPrintf
0x180055a4e  jmp     loc_180055ADE
0x180055a53  mov     r14d, 235h
0x180055a59  mov     r8d, r14d
0x180055a5c  mov     edi, 2
0x180055a61  mov     ecx, edi
0x180055a63  call    AslLogCallPrintf
0x180055a68  cmp     cs:EnableDevInvStdErrLog, 0
0x180055a6f  jz      short loc_180055AC0
0x180055a71  mov     ecx, edi; Ix
0x180055a73  call    _o___acrt_iob_func_0
0x180055a78  mov     rcx, rax; Stream
0x180055a7b  mov     r9d, r14d
0x180055a7e  lea     r8, aGetproceduread; "GetProcedureAddress"
0x180055a85  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180055a8c  call    fprintf
0x180055a91  mov     ecx, edi; Ix
0x180055a93  call    _o___acrt_iob_func_0
0x180055a98  mov     rcx, rax; Stream
0x180055a9b  mov     r8, rbx
0x180055a9e  lea     rdx, aProcedureHsNot; "Procedure [%hs] not found."
0x180055aa5  call    fprintf
0x180055aaa  mov     ecx, edi; Ix
0x180055aac  call    _o___acrt_iob_func_0
0x180055ab1  mov     rcx, rax; Stream
0x180055ab4  lea     rdx, asc_18011EAD8; "\n"
0x180055abb  call    fprintf
0x180055ac0  cmp     cs:g_DeviceMapLogFunction, 0
0x180055ac8  jz      short loc_180055ADE
0x180055aca  mov     r8, rbx
0x180055acd  lea     rdx, aProcedureHsNot; "Procedure [%hs] not found."
0x180055ad4  mov     ecx, 3000000h
0x180055ad9  call    TraceMessageCallback
0x180055ade  jmp     loc_180055BCE
0x180055ae3  lfence
0x180055ae6  cdqe
0x180055ae8  movzx   edx, word ptr [r14+rax*2]
0x180055aed  mov     edx, [r12+rdx*4]; unsigned int
0x180055af1  mov     rcx, rbx; struct _FILE_IMAGE_INFO *
0x180055af4  call    ?MapRelativeAddress@@YA_KPEAU_FILE_IMAGE_INFO@@K@Z; MapRelativeAddress(_FILE_IMAGE_INFO *,ulong)
0x180055af9  mov     rsi, rax
0x180055afc  mov     [rsp+78h+var_48], rax
0x180055b01  jmp     loc_180055BCE
0x180055b06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180055b0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180055b12  lea     r9, aMaprelativeadd; "MapRelativeAddress failed on exported F"...
0x180055b19  lea     rdx, aGetproceduread; "GetProcedureAddress"
0x180055b20  test    al, al
0x180055b22  jz      short loc_180055B39
0x180055b24  mov     r8d, 21Eh
0x180055b2a  mov     ecx, 1
0x180055b2f  call    AslLogCallPrintf
0x180055b34  jmp     loc_180055BBD
0x180055b39  mov     ebx, 222h
0x180055b3e  mov     r8d, ebx
0x180055b41  mov     edi, 2
0x180055b46  mov     ecx, edi
0x180055b48  call    AslLogCallPrintf
0x180055b4d  cmp     cs:EnableDevInvStdErrLog, 0
0x180055b54  jz      short loc_180055BA2
0x180055b56  mov     ecx, edi; Ix
0x180055b58  call    _o___acrt_iob_func_0
0x180055b5d  mov     rcx, rax; Stream
0x180055b60  mov     r9d, ebx
0x180055b63  lea     r8, aGetproceduread; "GetProcedureAddress"
0x180055b6a  lea     rdx, Format; "Error: %s, %u: "
0x180055b71  call    fprintf
0x180055b76  mov     ecx, edi; Ix
0x180055b78  call    _o___acrt_iob_func_0
0x180055b7d  mov     rcx, rax; Stream
0x180055b80  lea     rdx, aMaprelativeadd; "MapRelativeAddress failed on exported F"...
0x180055b87  call    fprintf
0x180055b8c  mov     ecx, edi; Ix
0x180055b8e  call    _o___acrt_iob_func_0
0x180055b93  mov     rcx, rax; Stream
0x180055b96  lea     rdx, asc_18011EAD8; "\n"
0x180055b9d  call    fprintf
0x180055ba2  cmp     cs:g_DeviceMapLogFunction, 0
0x180055baa  jz      short loc_180055BBD
0x180055bac  lea     rdx, aMaprelativeadd; "MapRelativeAddress failed on exported F"...
0x180055bb3  mov     ecx, 2000000h
0x180055bb8  call    TraceMessageCallback
0x180055bbd  jmp     short loc_180055BCE
0x180055bbf  mov     ecx, eax; dwErrCode
0x180055bc1  call    cs:__imp_SetLastError
0x180055bc7  xor     esi, esi
0x180055bc9  mov     [rsp+78h+var_48], rsi
0x180055bce  mov     rax, rsi
0x180055bd1  add     rsp, 48h
0x180055bd5  pop     r15
0x180055bd7  pop     r14
0x180055bd9  pop     r12
0x180055bdb  pop     rdi
0x180055bdc  pop     rsi
0x180055bdd  pop     rbx
0x180055bde  retn
```
