# _AttributesFromRunLevelInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x180076830`
- end: `0x180076b68`
- name: `?_AttributesFromRunLevelInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `824`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180005e40`
- `0x180066c10`
- `0x180076830`
- `0x180077d38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800768dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800768dd`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800768c4`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800768c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800769b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800769b7`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800769ad`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800769ad`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800769e0`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180076b32`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800769e0`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180076b32`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180076913`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180076913`

## string_xrefs

- `0x180076941`: `Failed to create activation context [%x]`
- `0x180076a01`: `RequireAdministrator`
- `0x180076af6`: `_SetFileAttributeValue`
- `0x180076ae1`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromRunLevelInfo(const wchar_t ***a1, _DWORD *a2)
{
  __int64 v3; // rsi
  const wchar_t **v4; // rax
  const WCHAR *v5; // r14
  unsigned int v6; // edi
  HANDLE v7; // r14
  DWORD v8; // eax
  DWORD LastError; // eax
  const wchar_t *v10; // rcx
  BOOL v11; // edx
  int v12; // r9d
  __int64 v13; // rax
  _WORD *v14; // rcx
  _WORD *v15; // rdx
  _WORD *v16; // rcx
  _DWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pvBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  wchar_t Ext[264]; // [rsp+A0h] [rbp-60h] BYREF

  pvBuffer = 0;
  v21 = 0;
  v3 = 260;
  v4 = *a1;
  v18[0] = 0;
  memset(&pActCtx, 0, sizeof(pActCtx));
  Ext[0] = 0;
  v5 = *v4;
  if ( _wsplitpath_s(*v4, 0, 0, 0, 0, 0, 0, Ext, 0x104u) || (unsigned int)_o__wcsicmp(Ext, L".EXE") )
    return 0;
  pActCtx.cbSize = 56;
  pActCtx.lpResourceName = (LPCWSTR)1;
  v6 = -2147467259;
  pActCtx.dwFlags = 8;
  pActCtx.lpSource = v5;
  v7 = CreateActCtxW(&pActCtx);
  if ( v7 != (HANDLE)-1LL )
  {
    if ( !QueryActCtxW(0x80000000, v7, 0, 5u, &pvBuffer, 0xCu, 0) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2043, "Failed to query activation context [%x]", LastError);
      ReleaseActCtx(v7);
      return v6;
    }
    if ( HIDWORD(pvBuffer) )
    {
      switch ( HIDWORD(pvBuffer) )
      {
        case 1:
          v10 = L"AsInvoker";
          goto LABEL_19;
        case 2:
          v10 = L"HighestAvailable";
          goto LABEL_19;
        case 3:
          v10 = L"RequireAdministrator";
          goto LABEL_19;
      }
    }
    v10 = L"Unspecified";
LABEL_19:
    _SetFileAttributeValue(v10, 520, 32, a2);
    v11 = v21 != 0;
    v18[0] = v11;
    if ( !a2 )
      goto LABEL_34;
    v12 = dword_18015569C;
    if ( (unsigned int)dword_18015569C > 2 )
    {
      if ( dword_18015569C != 3 )
      {
        if ( dword_18015569C == 4 )
        {
          v13 = 2;
          v14 = v18;
          v15 = a2 + 4488;
          do
          {
            if ( !v13 )
              break;
            if ( !*v14 )
              break;
            *v15++ = *v14++;
            --v13;
            --v3;
          }
          while ( v3 );
          v16 = v15 - 1;
          if ( v3 )
            v16 = v15;
          *v16 = 0;
          if ( !v3 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              33,
              -2147024774);
            goto LABEL_34;
          }
LABEL_33:
          a2[4618] = 33;
          a2[4619] = v12;
          a2[4620] = 1;
        }
LABEL_34:
        ReleaseActCtx(v7);
        return 0;
      }
      a2[4489] = v18[1];
    }
    a2[4488] = v11;
    goto LABEL_33;
  }
  v8 = GetLastError();
  if ( v8 - 1812 <= 2 || v8 == 14001 || v8 == 193 )
  {
    _SetFileAttributeValue(L"Unspecified", 520, 32, a2);
    return 0;
  }
  AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2029, "Failed to create activation context [%x]", v8);
  return v6;
}

```

## disassembly

```asm
0x180076830  mov     [rsp-8+arg_10], rbx
0x180076835  mov     [rsp-8+arg_18], rsi
0x18007683a  push    rbp
0x18007683b  push    rdi
0x18007683c  push    r12
0x18007683e  push    r14
0x180076840  push    r15
0x180076842  lea     rbp, [rsp-1C0h]
0x18007684a  sub     rsp, 2C0h
0x180076851  mov     rax, cs:__security_cookie
0x180076858  xor     rax, rsp
0x18007685b  mov     [rbp+1E0h+var_30], rax
0x180076862  xor     eax, eax
0x180076864  xor     r15d, r15d
0x180076867  mov     [rbp+1E0h+pActCtx.hModule], rax
0x18007686b  xorps   xmm0, xmm0
0x18007686e  mov     [rbp+1E0h+pvBuffer], rax
0x180076872  mov     rbx, rdx
0x180076875  mov     [rbp+1E0h+var_248], eax
0x180076878  mov     esi, 104h
0x18007687d  mov     rax, [rcx]
0x180076880  xor     r9d, r9d; Dir
0x180076883  mov     [rsp+2E0h+ExtCount], rsi; ExtCount
0x180076888  xor     r8d, r8d; DriveCount
0x18007688b  mov     [rsp+2E0h+var_290], r15d
0x180076890  xor     edx, edx; Drive
0x180076892  movups  xmmword ptr [rsp+2E0h+pActCtx.cbSize], xmm0
0x180076897  mov     [rbp+1E0h+var_240], r15w
0x18007689c  movups  xmmword ptr [rsp+2E0h+pActCtx.wProcessorArchitecture], xmm0
0x1800768a1  movups  xmmword ptr [rsp+2E0h+pActCtx.lpResourceName], xmm0
0x1800768a6  mov     r14, [rax]
0x1800768a9  lea     rax, [rbp+1E0h+var_240]
0x1800768ad  mov     [rsp+2E0h+Ext], rax; Ext
0x1800768b2  mov     rcx, r14; FullPath
0x1800768b5  mov     [rsp+2E0h+FilenameCount], r15; FilenameCount
0x1800768ba  mov     [rsp+2E0h+Filename], r15; Filename
0x1800768bf  mov     [rsp+2E0h+DirCount], r15; DirCount
0x1800768c4  call    cs:__imp__wsplitpath_s
0x1800768ca  test    eax, eax
0x1800768cc  jnz     loc_180076B38
0x1800768d2  lea     rdx, aExe; ".EXE"
0x1800768d9  lea     rcx, [rbp+1E0h+var_240]
0x1800768dd  call    cs:__imp__o__wcsicmp
0x1800768e3  test    eax, eax
0x1800768e5  jnz     loc_180076B38
0x1800768eb  lea     r12d, [r15+1]
0x1800768ef  mov     [rsp+2E0h+pActCtx.cbSize], 38h ; '8'
0x1800768f7  lea     rcx, [rsp+2E0h+pActCtx]; pActCtx
0x1800768fc  mov     [rsp+2E0h+pActCtx.lpResourceName], r12
0x180076901  mov     edi, 80004005h
0x180076906  mov     [rsp+2E0h+pActCtx.dwFlags], 8
0x18007690e  mov     [rsp+2E0h+pActCtx.lpSource], r14
0x180076913  call    cs:__imp_CreateActCtxW
0x180076919  mov     r14, rax
0x18007691c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180076920  jnz     short loc_180076985
0x180076922  call    cs:__imp_GetLastError
0x180076928  lea     edx, [rax-714h]
0x18007692e  cmp     edx, 2
0x180076931  jbe     short loc_180076966
0x180076933  cmp     eax, 36B1h
0x180076938  jz      short loc_180076966
0x18007693a  cmp     eax, 0C1h
0x18007693f  jz      short loc_180076966
0x180076941  lea     r9, aFailedToCreate_1; "Failed to create activation context [%x"...
0x180076948  mov     dword ptr [rsp+2E0h+DirCount], eax
0x18007694c  mov     r8d, 7EDh
0x180076952  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x180076959  mov     ecx, r12d
0x18007695c  call    AslLogCallPrintf
0x180076961  jmp     loc_180076B3B
0x180076966  mov     r9, rbx
0x180076969  lea     rcx, aUnspecified; "Unspecified"
0x180076970  mov     edx, 208h
0x180076975  mov     r8d, 20h ; ' '
0x18007697b  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x180076980  jmp     loc_180076B38
0x180076985  mov     [rsp+2E0h+FilenameCount], r15; pcbWrittenOrRequired
0x18007698a  lea     rax, [rbp+1E0h+pvBuffer]
0x18007698e  mov     [rsp+2E0h+Filename], 0Ch; cbBuffer
0x180076997  mov     r9d, 5; ulInfoClass
0x18007699d  xor     r8d, r8d; pvSubInstance
0x1800769a0  mov     [rsp+2E0h+DirCount], rax; pvBuffer
0x1800769a5  mov     rdx, r14; hActCtx
0x1800769a8  mov     ecx, 80000000h; dwFlags
0x1800769ad  call    cs:__imp_QueryActCtxW
0x1800769b3  test    eax, eax
0x1800769b5  jnz     short loc_1800769EB
0x1800769b7  call    cs:__imp_GetLastError
0x1800769bd  lea     r9, aFailedToQueryA; "Failed to query activation context [%x]"
0x1800769c4  mov     r8d, 7FBh
0x1800769ca  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800769d1  mov     dword ptr [rsp+2E0h+DirCount], eax
0x1800769d5  mov     ecx, r12d
0x1800769d8  call    AslLogCallPrintf
0x1800769dd  mov     rcx, r14; hActCtx
0x1800769e0  call    cs:__imp_ReleaseActCtx
0x1800769e6  jmp     loc_180076B3B
0x1800769eb  mov     ecx, dword ptr [rbp+1E0h+pvBuffer+4]
0x1800769ee  test    ecx, ecx
0x1800769f0  jz      short loc_180076A1C
0x1800769f2  sub     ecx, r12d
0x1800769f5  jz      short loc_180076A13
0x1800769f7  sub     ecx, r12d
0x1800769fa  jz      short loc_180076A0A
0x1800769fc  cmp     ecx, r12d
0x1800769ff  jnz     short loc_180076A1C
0x180076a01  lea     rcx, aRequireadminis; "RequireAdministrator"
0x180076a08  jmp     short loc_180076A23
0x180076a0a  lea     rcx, aHighestavailab; "HighestAvailable"
0x180076a11  jmp     short loc_180076A23
0x180076a13  lea     rcx, aAsinvoker; "AsInvoker"
0x180076a1a  jmp     short loc_180076A23
0x180076a1c  lea     rcx, aUnspecified; "Unspecified"
0x180076a23  mov     r9, rbx
0x180076a26  mov     edx, 208h
0x180076a2b  mov     r8d, 20h ; ' '
0x180076a31  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x180076a36  cmp     [rbp+1E0h+var_248], r15d
0x180076a3a  mov     edx, r15d
0x180076a3d  setnz   dl
0x180076a40  mov     [rsp+2E0h+var_290], edx
0x180076a44  test    rbx, rbx
0x180076a47  jz      loc_180076B2F
0x180076a4d  mov     r9d, cs:dword_18015569C
0x180076a54  mov     ecx, r9d
0x180076a57  test    r9d, r9d
0x180076a5a  jz      loc_180076B11
0x180076a60  sub     ecx, r12d
0x180076a63  jz      loc_180076B11
0x180076a69  sub     ecx, r12d
0x180076a6c  jz      loc_180076B11
0x180076a72  sub     ecx, r12d
0x180076a75  jz      loc_180076B07
0x180076a7b  cmp     ecx, r12d
0x180076a7e  jnz     loc_180076B2F
0x180076a84  mov     eax, 2
0x180076a89  lea     rcx, [rsp+2E0h+var_290]
0x180076a8e  lea     rdx, [rbx+4620h]
0x180076a95  test    rax, rax
0x180076a98  jz      short loc_180076AB8
0x180076a9a  movzx   r8d, word ptr [rcx]
0x180076a9e  test    r8w, r8w
0x180076aa2  jz      short loc_180076AB8
0x180076aa4  mov     [rdx], r8w
0x180076aa8  add     rcx, 2
0x180076aac  add     rdx, 2
0x180076ab0  sub     rax, r12
0x180076ab3  sub     rsi, r12
0x180076ab6  jnz     short loc_180076A95
0x180076ab8  mov     rax, rsi
0x180076abb  lea     rcx, [rdx-2]
0x180076abf  neg     rax
0x180076ac2  sbb     r8d, r8d
0x180076ac5  not     r8d
0x180076ac8  and     r8d, 8007007Ah
0x180076acf  test    rsi, rsi
0x180076ad2  cmovnz  rcx, rdx
0x180076ad6  mov     [rcx], r15w
0x180076ada  jnz     short loc_180076B17
0x180076adc  mov     dword ptr [rsp+2E0h+Filename], r8d
0x180076ae1  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180076ae8  mov     r8d, 0C6Ah
0x180076aee  mov     dword ptr [rsp+2E0h+DirCount], 21h ; '!'
0x180076af6  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076afd  mov     ecx, r12d
0x180076b00  call    AslLogCallPrintf
0x180076b05  jmp     short loc_180076B2F
0x180076b07  mov     eax, [rsp+2E0h+var_28C]
0x180076b0b  mov     [rbx+4624h], eax
0x180076b11  mov     [rbx+4620h], edx
0x180076b17  mov     dword ptr [rbx+4828h], 21h ; '!'
0x180076b21  mov     [rbx+482Ch], r9d
0x180076b28  mov     [rbx+4830h], r12d
0x180076b2f  mov     rcx, r14; hActCtx
0x180076b32  call    cs:__imp_ReleaseActCtx
0x180076b38  mov     edi, r15d
0x180076b3b  mov     eax, edi
0x180076b3d  mov     rcx, [rbp+1E0h+var_30]
0x180076b44  xor     rcx, rsp; StackCookie
0x180076b47  call    __security_check_cookie
0x180076b4c  lea     r11, [rsp+2E0h+var_20]
0x180076b54  mov     rbx, [r11+40h]
0x180076b58  mov     rsi, [r11+48h]
0x180076b5c  mov     rsp, r11
0x180076b5f  pop     r15
0x180076b61  pop     r14
0x180076b63  pop     r12
0x180076b65  pop     rdi
0x180076b66  pop     rbp
0x180076b67  retn
```
