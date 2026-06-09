# GetFileLastWriteTime(ushort const *,unsigned __int64 *)

- ea: `0x1800548ec`
- end: `0x180054d21`
- name: `?GetFileLastWriteTime@@YAJPEBGPEA_K@Z`
- size: `1077`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800153ac`
- `0x180016838`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800538cc`
- `0x1800548ec`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c34`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180054b37`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180054b37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054943`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054943`

## string_xrefs

- `0x18005498a`: `GetFileLastWriteTime`
- `0x1800549e3`: `GetFileLastWriteTime`
- `0x180054a53`: `GetFileLastWriteTime`
- `0x180054ab8`: `GetFileLastWriteTime`
- `0x180054b6a`: `GetFileLastWriteTime`
- `0x180054bc0`: `GetFileLastWriteTime`
- `0x180054c64`: `GetFileLastWriteTime`
- `0x180054cab`: `GetFileLastWriteTime`
- `0x180054a62`: `File not found. Path: (%ws) [%#x]`
- `0x180054a97`: `0x%x File not found. Path: (%ws)`
- `0x180054ad8`: `0x%x File not found. Path: (%ws)`
- `0x180054b11`: `0x%x File not found. Path: (%ws)`
- `0x180054995`: `Failed to open file [%#x]`
- `0x1800549b1`: `Failed to open file: 0x%x`
- `0x180054b75`: `Failed to get file last write time [%#x]`
- `0x180054b91`: `Failed to get file last write time 0x%x`

## pseudocode

```c
__int64 __fastcall GetFileLastWriteTime(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  HANDLE FileW; // rax
  void *v5; // r15
  signed int LastError; // eax
  unsigned int v7; // ebx
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  signed int v14; // eax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  DWORD dwHighDateTime; // ecx
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v22; // rax
  __int64 v23; // [rsp+20h] [rbp-38h]
  __int64 v24; // [rsp+28h] [rbp-30h]
  struct _FILETIME LastWriteTime; // [rsp+60h] [rbp+8h] BYREF

  LastWriteTime = 0;
  if ( a1 && a2 )
  {
    FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    v5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 + 2147024894 <= 1 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
        {
          LODWORD(v24) = v7;
          AslLogCallPrintf(3, "GetFileLastWriteTime", 2018, "File not found. Path: (%ws) [%#x]", a1, v24);
        }
        else
        {
          LODWORD(v23) = v7;
          AslLogCallPrintf(2, "GetFileLastWriteTime", 2022, "0x%x File not found. Path: (%ws)", v23, a1);
          if ( EnableDevInvStdErrLog )
          {
            v11 = o___acrt_iob_func_0(2u);
            fprintf(v11, "Warning: %s, %u: ", "GetFileLastWriteTime", 2022);
            v12 = o___acrt_iob_func_0(2u);
            fprintf(v12, "0x%x File not found. Path: (%ws)", v7, a1);
            v13 = o___acrt_iob_func_0(2u);
            fprintf(v13, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(50331648, "0x%x File not found. Path: (%ws)", v7, a1);
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(1, "GetFileLastWriteTime", 2029, "Failed to open file [%#x]", v7);
      }
      else
      {
        AslLogCallPrintf(2, "GetFileLastWriteTime", 2033, "Failed to open file: 0x%x", v7);
        if ( EnableDevInvStdErrLog )
        {
          v8 = o___acrt_iob_func_0(2u);
          fprintf(v8, "Error: %s, %u: ", "GetFileLastWriteTime", 2033);
          v9 = o___acrt_iob_func_0(2u);
          fprintf(v9, "Failed to open file: 0x%x", v7);
          v10 = o___acrt_iob_func_0(2u);
          fprintf(v10, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Failed to open file: 0x%x", v7);
      }
    }
    else
    {
      if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
      {
        v7 = 0;
        dwHighDateTime = LastWriteTime.dwHighDateTime;
        *(_DWORD *)a2 = LastWriteTime.dwLowDateTime;
        *((_DWORD *)a2 + 1) = dwHighDateTime;
      }
      else
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
        {
          AslLogCallPrintf(1, "GetFileLastWriteTime", 2046, "Failed to get file last write time [%#x]", v7);
        }
        else
        {
          AslLogCallPrintf(2, "GetFileLastWriteTime", 2050, "Failed to get file last write time 0x%x", v7);
          if ( EnableDevInvStdErrLog )
          {
            v15 = o___acrt_iob_func_0(2u);
            fprintf(v15, "Error: %s, %u: ", "GetFileLastWriteTime", 2050);
            v16 = o___acrt_iob_func_0(2u);
            fprintf(v16, "Failed to get file last write time 0x%x", v7);
            v17 = o___acrt_iob_func_0(2u);
            fprintf(v17, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "Failed to get file last write time 0x%x", v7);
        }
      }
      CloseHandle(v5);
    }
    if ( (v7 & 0x80000000) == 0 && !*a2 )
      return (unsigned int)-2147467263;
    return v7;
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetFileLastWriteTime", 1991, "NULL argument in call to function");
    }
    else
    {
      AslLogCallPrintf(2, "GetFileLastWriteTime", 1995, "NULL argument in call to function");
      if ( EnableDevInvStdErrLog )
      {
        v20 = o___acrt_iob_func_0(2u);
        fprintf(v20, "Error: %s, %u: ", "GetFileLastWriteTime", 1995);
        v21 = o___acrt_iob_func_0(2u);
        fprintf(v21, "NULL argument in call to function");
        v22 = o___acrt_iob_func_0(2u);
        fprintf(v22, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "NULL argument in call to function");
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800548ec  mov     rax, rsp
0x1800548ef  mov     [rax+10h], rbx
0x1800548f3  mov     [rax+18h], rsi
0x1800548f7  push    rdi
0x1800548f8  push    r14
0x1800548fa  push    r15
0x1800548fc  sub     rsp, 40h
0x180054900  mov     qword ptr [rax+8], 0
0x180054908  mov     r14, rdx
0x18005490b  mov     rsi, rcx
0x18005490e  test    rcx, rcx
0x180054911  jz      loc_180054C51
0x180054917  test    rdx, rdx
0x18005491a  jz      loc_180054C51
0x180054920  mov     qword ptr [rax-28h], 0
0x180054928  mov     edi, 3
0x18005492d  mov     dword ptr [rax-30h], 2000000h
0x180054934  xor     r9d, r9d; lpSecurityAttributes
0x180054937  mov     edx, 80000000h; dwDesiredAccess
0x18005493c  mov     [rax-38h], edi
0x18005493f  lea     r8d, [rdi+4]; dwShareMode
0x180054943  call    cs:__imp_CreateFileW
0x180054949  mov     r15, rax
0x18005494c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054950  jnz     loc_180054B2A
0x180054956  call    cs:__imp_GetLastError
0x18005495c  mov     ebx, eax
0x18005495e  test    eax, eax
0x180054960  jle     short loc_18005496B
0x180054962  movzx   ebx, ax
0x180054965  or      ebx, 80070000h
0x18005496b  lea     eax, [rbx+7FF8FFFEh]
0x180054971  cmp     eax, 1
0x180054974  jbe     loc_180054A47
0x18005497a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180054981  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054986  mov     dword ptr [rsp+58h+var_38], ebx
0x18005498a  lea     rdx, aGetfilelastwri; "GetFileLastWriteTime"
0x180054991  test    al, al
0x180054993  jz      short loc_1800549B1
0x180054995  lea     r9, aFailedToOpenFi_0; "Failed to open file [%#x]"
0x18005499c  mov     r8d, 7EDh
0x1800549a2  mov     ecx, 1
0x1800549a7  call    AslLogCallPrintf
0x1800549ac  jmp     loc_180054C3A
0x1800549b1  lea     rsi, aFailedToOpenFi; "Failed to open file: 0x%x"
0x1800549b8  mov     r15d, 7F1h
0x1800549be  mov     edi, 2
0x1800549c3  mov     r9, rsi
0x1800549c6  mov     r8d, r15d
0x1800549c9  mov     ecx, edi
0x1800549cb  call    AslLogCallPrintf
0x1800549d0  cmp     cs:EnableDevInvStdErrLog, 0
0x1800549d7  jz      short loc_180054A24
0x1800549d9  mov     ecx, edi; Ix
0x1800549db  call    _o___acrt_iob_func_0
0x1800549e0  mov     rcx, rax; Stream
0x1800549e3  lea     r8, aGetfilelastwri; "GetFileLastWriteTime"
0x1800549ea  mov     r9d, r15d
0x1800549ed  lea     rdx, Format; "Error: %s, %u: "
0x1800549f4  call    fprintf
0x1800549f9  mov     ecx, edi; Ix
0x1800549fb  call    _o___acrt_iob_func_0
0x180054a00  mov     rcx, rax; Stream
0x180054a03  mov     r8d, ebx
0x180054a06  mov     rdx, rsi; Format
0x180054a09  call    fprintf
0x180054a0e  mov     ecx, edi; Ix
0x180054a10  call    _o___acrt_iob_func_0
0x180054a15  mov     rcx, rax; Stream
0x180054a18  lea     rdx, asc_18011EAD8; "\n"
0x180054a1f  call    fprintf
0x180054a24  cmp     cs:g_DeviceMapLogFunction, 0
0x180054a2c  jz      loc_180054C3A
0x180054a32  mov     r8d, ebx
0x180054a35  mov     rdx, rsi
0x180054a38  mov     ecx, 2000000h
0x180054a3d  call    TraceMessageCallback
0x180054a42  jmp     loc_180054C3A
0x180054a47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180054a4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054a53  lea     rdx, aGetfilelastwri; "GetFileLastWriteTime"
0x180054a5a  test    al, al
0x180054a5c  jz      short loc_180054A80
0x180054a5e  mov     dword ptr [rsp+58h+var_30], ebx
0x180054a62  lea     r9, aFileNotFoundPa; "File not found. Path: (%ws) [%#x]"
0x180054a69  mov     r8d, 7E2h
0x180054a6f  mov     [rsp+58h+var_38], rsi
0x180054a74  mov     ecx, edi
0x180054a76  call    AslLogCallPrintf
0x180054a7b  jmp     loc_180054C3A
0x180054a80  mov     r15d, 7E6h
0x180054a86  mov     [rsp+58h+var_30], rsi
0x180054a8b  mov     edi, 2
0x180054a90  mov     dword ptr [rsp+58h+var_38], ebx
0x180054a94  mov     r8d, r15d
0x180054a97  lea     r9, a0xXFileNotFoun; "0x%x File not found. Path: (%ws)"
0x180054a9e  mov     ecx, edi
0x180054aa0  call    AslLogCallPrintf
0x180054aa5  cmp     cs:EnableDevInvStdErrLog, 0
0x180054aac  jz      short loc_180054B00
0x180054aae  mov     ecx, edi; Ix
0x180054ab0  call    _o___acrt_iob_func_0
0x180054ab5  mov     rcx, rax; Stream
0x180054ab8  lea     r8, aGetfilelastwri; "GetFileLastWriteTime"
0x180054abf  mov     r9d, r15d
0x180054ac2  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180054ac9  call    fprintf
0x180054ace  mov     ecx, edi; Ix
0x180054ad0  call    _o___acrt_iob_func_0
0x180054ad5  mov     rcx, rax; Stream
0x180054ad8  lea     rdx, a0xXFileNotFoun; "0x%x File not found. Path: (%ws)"
0x180054adf  mov     r9, rsi
0x180054ae2  mov     r8d, ebx
0x180054ae5  call    fprintf
0x180054aea  mov     ecx, edi; Ix
0x180054aec  call    _o___acrt_iob_func_0
0x180054af1  mov     rcx, rax; Stream
0x180054af4  lea     rdx, asc_18011EAD8; "\n"
0x180054afb  call    fprintf
0x180054b00  cmp     cs:g_DeviceMapLogFunction, 0
0x180054b08  jz      loc_180054C3A
0x180054b0e  mov     r9, rsi
0x180054b11  lea     rdx, a0xXFileNotFoun; "0x%x File not found. Path: (%ws)"
0x180054b18  mov     r8d, ebx
0x180054b1b  mov     ecx, 3000000h
0x180054b20  call    TraceMessageCallback
0x180054b25  jmp     loc_180054C3A
0x180054b2a  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x180054b2f  xor     r8d, r8d; lpLastAccessTime
0x180054b32  xor     edx, edx; lpCreationTime
0x180054b34  mov     rcx, r15; hFile
0x180054b37  call    cs:__imp_GetFileTime
0x180054b3d  test    eax, eax
0x180054b3f  jnz     loc_180054C20
0x180054b45  call    cs:__imp_GetLastError
0x180054b4b  mov     ebx, eax
0x180054b4d  test    eax, eax
0x180054b4f  jle     short loc_180054B5A
0x180054b51  movzx   ebx, ax
0x180054b54  or      ebx, 80070000h
0x180054b5a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180054b61  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054b66  mov     dword ptr [rsp+58h+var_38], ebx
0x180054b6a  lea     rdx, aGetfilelastwri; "GetFileLastWriteTime"
0x180054b71  test    al, al
0x180054b73  jz      short loc_180054B91
0x180054b75  lea     r9, aFailedToGetFil_4; "Failed to get file last write time [%#x"...
0x180054b7c  mov     r8d, 7FEh
0x180054b82  mov     ecx, 1
0x180054b87  call    AslLogCallPrintf
0x180054b8c  jmp     loc_180054C31
0x180054b91  lea     rsi, aFailedToGetFil_2; "Failed to get file last write time 0x%x"
0x180054b98  mov     edi, 2
0x180054b9d  mov     r9, rsi
0x180054ba0  mov     ecx, edi
0x180054ba2  mov     r8d, 802h
0x180054ba8  call    AslLogCallPrintf
0x180054bad  cmp     cs:EnableDevInvStdErrLog, 0
0x180054bb4  jz      short loc_180054C04
0x180054bb6  mov     ecx, edi; Ix
0x180054bb8  call    _o___acrt_iob_func_0
0x180054bbd  mov     rcx, rax; Stream
0x180054bc0  lea     r8, aGetfilelastwri; "GetFileLastWriteTime"
0x180054bc7  mov     r9d, 802h
0x180054bcd  lea     rdx, Format; "Error: %s, %u: "
0x180054bd4  call    fprintf
0x180054bd9  mov     ecx, edi; Ix
0x180054bdb  call    _o___acrt_iob_func_0
0x180054be0  mov     rcx, rax; Stream
0x180054be3  mov     r8d, ebx
0x180054be6  mov     rdx, rsi; Format
0x180054be9  call    fprintf
0x180054bee  mov     ecx, edi; Ix
0x180054bf0  call    _o___acrt_iob_func_0
0x180054bf5  mov     rcx, rax; Stream
0x180054bf8  lea     rdx, asc_18011EAD8; "\n"
0x180054bff  call    fprintf
0x180054c04  cmp     cs:g_DeviceMapLogFunction, 0
0x180054c0c  jz      short loc_180054C31
0x180054c0e  mov     r8d, ebx
0x180054c11  mov     rdx, rsi
0x180054c14  mov     ecx, 2000000h
0x180054c19  call    TraceMessageCallback
0x180054c1e  jmp     short loc_180054C31
0x180054c20  mov     eax, [rsp+58h+LastWriteTime.dwLowDateTime]
0x180054c24  xor     ebx, ebx
0x180054c26  mov     ecx, [rsp+58h+LastWriteTime.dwHighDateTime]
0x180054c2a  mov     [r14], eax
0x180054c2d  mov     [r14+4], ecx
0x180054c31  mov     rcx, r15; hObject
0x180054c34  call    cs:__imp_CloseHandle
0x180054c3a  test    ebx, ebx
0x180054c3c  js      short loc_180054C4A
0x180054c3e  cmp     qword ptr [r14], 0
0x180054c42  mov     eax, 80004001h
0x180054c47  cmovz   ebx, eax
0x180054c4a  mov     eax, ebx
0x180054c4c  jmp     loc_180054D0D
0x180054c51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180054c58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054c5d  lea     r9, aNullArgumentIn; "NULL argument in call to function"
0x180054c64  lea     rdx, aGetfilelastwri; "GetFileLastWriteTime"
0x180054c6b  test    al, al
0x180054c6d  jz      short loc_180054C84
0x180054c6f  mov     r8d, 7C7h
0x180054c75  mov     ecx, 1
0x180054c7a  call    AslLogCallPrintf
0x180054c7f  jmp     loc_180054D08
0x180054c84  mov     ebx, 7CBh
0x180054c89  mov     edi, 2
0x180054c8e  mov     r8d, ebx
0x180054c91  mov     ecx, edi
0x180054c93  call    AslLogCallPrintf
0x180054c98  cmp     cs:EnableDevInvStdErrLog, 0
0x180054c9f  jz      short loc_180054CED
0x180054ca1  mov     ecx, edi; Ix
0x180054ca3  call    _o___acrt_iob_func_0
0x180054ca8  mov     rcx, rax; Stream
0x180054cab  lea     r8, aGetfilelastwri; "GetFileLastWriteTime"
0x180054cb2  mov     r9d, ebx
0x180054cb5  lea     rdx, Format; "Error: %s, %u: "
0x180054cbc  call    fprintf
0x180054cc1  mov     ecx, edi; Ix
0x180054cc3  call    _o___acrt_iob_func_0
0x180054cc8  mov     rcx, rax; Stream
0x180054ccb  lea     rdx, aNullArgumentIn; "NULL argument in call to function"
0x180054cd2  call    fprintf
0x180054cd7  mov     ecx, edi; Ix
0x180054cd9  call    _o___acrt_iob_func_0
0x180054cde  mov     rcx, rax; Stream
0x180054ce1  lea     rdx, asc_18011EAD8; "\n"
0x180054ce8  call    fprintf
0x180054ced  cmp     cs:g_DeviceMapLogFunction, 0
0x180054cf5  jz      short loc_180054D08
0x180054cf7  lea     rdx, aNullArgumentIn; "NULL argument in call to function"
0x180054cfe  mov     ecx, 2000000h
0x180054d03  call    TraceMessageCallback
0x180054d08  mov     eax, 80070057h
0x180054d0d  mov     rbx, [rsp+58h+arg_8]
0x180054d12  mov     rsi, [rsp+58h+arg_10]
0x180054d17  add     rsp, 40h
0x180054d1b  pop     r15
0x180054d1d  pop     r14
0x180054d1f  pop     rdi
0x180054d20  retn
```
