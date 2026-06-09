# CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18002c6f0`
- end: `0x18002c8c2`
- name: `?IsAutoVerifierRelatedIssue@CAutoVerifierPlugin@@AEAAJPEAHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d040`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18002bcf8`
- `0x18002bf54`
- `0x18002c6f0`
- `0x18003e5a8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c7cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c7cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c8aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c8aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c780`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c780`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(CAutoVerifierPlugin *a1, _DWORD *a2, _QWORD *a3)
{
  _WORD *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  HMODULE v12; // rdi
  const WCHAR *v13; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v16; // ebx
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-20h] BYREF
  HINSTANCE v19; // [rsp+38h] [rbp-18h] BYREF
  HMODULE v20; // [rsp+40h] [rbp-10h]
  char v21; // [rsp+98h] [rbp+48h] BYREF
  int v22; // [rsp+A0h] [rbp+50h] BYREF
  HINSTANCE v23; // [rsp+A8h] [rbp+58h] BYREF

  v23 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  lpLibFileName = 0;
  v22 = 0;
  *a2 = 0;
  v6 = (_WORD *)*a3;
  a3[1] = v6;
  *v6 = 0;
  if ( (int)CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(a1, &v23, &lpLibFileName, &v19, &v22) < 0 )
  {
    v11 = 0;
LABEL_3:
    v12 = 0;
    goto LABEL_28;
  }
  if ( !v23 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
  v13 = lpLibFileName;
  if ( !lpLibFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
  Library = LoadLibraryExW(v13, 0, 0);
  v12 = Library;
  v20 = Library;
  if ( !Library )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    v11 = -2147467259;
    goto LABEL_3;
  }
  ProcAddress = GetProcAddress(Library, "VerifierGetInfoForException");
  if ( ProcAddress )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, HINSTANCE, char *, char *, char *))ProcAddress)(
            *((_QWORD *)a1 + 98),
            v23,
            (char *)a1 + 800,
            &v21,
            (char *)a1 + 8);
    if ( v16 >= 0 )
    {
      if ( v21 )
      {
        if ( *((_QWORD *)a1 + 1) )
        {
          *a2 = 1;
          if ( v19 )
            CAutoVerifierPlugin::GetOriginalBucket((__int64)a1, (__int64)v19, a3);
        }
      }
      v11 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
          (unsigned int)v16);
      v11 = v16 | 0x10000000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    v11 = -2147467259;
  }
LABEL_28:
  if ( ((unsigned __int64)v12 & -(__int64)(v22 != 0)) != 0 )
    FreeLibrary((HMODULE)((unsigned __int64)v12 & -(__int64)(v22 != 0)));
  return v11;
}

```

## disassembly

```asm
0x18002c6f0  push    rbp
0x18002c6f2  push    rbx
0x18002c6f3  push    rdi
0x18002c6f4  push    r12
0x18002c6f6  push    r13
0x18002c6f8  push    r14
0x18002c6fa  push    r15
0x18002c6fc  mov     rbp, rsp
0x18002c6ff  sub     rsp, 50h
0x18002c703  mov     r12, r8
0x18002c706  mov     r13, rdx
0x18002c709  mov     r14, rcx
0x18002c70c  xor     r15d, r15d
0x18002c70f  mov     [rbp+arg_18], r15
0x18002c713  mov     [rbp+var_10], r15
0x18002c717  mov     [rbp+var_18], r15
0x18002c71b  mov     [rbp+arg_8], r15b
0x18002c71f  mov     [rbp+lpLibFileName], r15
0x18002c723  mov     [rbp+arg_10], r15d
0x18002c727  mov     [rdx], r15d
0x18002c72a  mov     r8, [r8]
0x18002c72d  mov     [r12+8], r8
0x18002c732  mov     [r8], r15w
0x18002c736  lea     rax, [rbp+arg_10]
0x18002c73a  mov     [rsp+50h+var_30], rax; int *
0x18002c73f  lea     r9, [rbp+var_18]; HINSTANCE *
0x18002c743  lea     r8, [rbp+lpLibFileName]; wchar_t **
0x18002c747  lea     rdx, [rbp+arg_18]; HINSTANCE *
0x18002c74b  call    ?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z; CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)
0x18002c750  test    eax, eax
0x18002c752  jns     short loc_18002C75F
0x18002c754  mov     ebx, r15d
0x18002c757  mov     rdi, r15
0x18002c75a  jmp     loc_18002C89D
0x18002c75f  cmp     [rbp+arg_18], r15
0x18002c763  jnz     short loc_18002C76A
0x18002c765  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c76a  mov     rbx, [rbp+lpLibFileName]
0x18002c76e  test    rbx, rbx
0x18002c771  jnz     short loc_18002C778
0x18002c773  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c778  xor     r8d, r8d; dwFlags
0x18002c77b  xor     edx, edx; hFile
0x18002c77d  mov     rcx, rbx; lpLibFileName
0x18002c780  call    cs:__imp_LoadLibraryExW
0x18002c786  mov     rdi, rax
0x18002c789  mov     [rbp+var_10], rax
0x18002c78d  test    rax, rax
0x18002c790  jnz     short loc_18002C7C5
0x18002c792  lea     rax, WPP_GLOBAL_Control
0x18002c799  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7a0  cmp     rcx, rax
0x18002c7a3  jz      short loc_18002C7BE
0x18002c7a5  test    byte ptr [rcx+1Ch], 1
0x18002c7a9  jz      short loc_18002C7BE
0x18002c7ab  lea     edx, [rdi+0Fh]
0x18002c7ae  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002c7b5  mov     rcx, [rcx+10h]
0x18002c7b9  call    WPP_SF_
0x18002c7be  mov     ebx, 80004005h
0x18002c7c3  jmp     short loc_18002C757
0x18002c7c5  lea     rdx, aVerifiergetinf; "VerifierGetInfoForException"
0x18002c7cc  mov     rcx, rax; hModule
0x18002c7cf  call    cs:__imp_GetProcAddress
0x18002c7d5  test    rax, rax
0x18002c7d8  jnz     short loc_18002C812
0x18002c7da  lea     rax, WPP_GLOBAL_Control
0x18002c7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7e8  cmp     rcx, rax
0x18002c7eb  jz      short loc_18002C808
0x18002c7ed  test    byte ptr [rcx+1Ch], 1
0x18002c7f1  jz      short loc_18002C808
0x18002c7f3  mov     edx, 10h
0x18002c7f8  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002c7ff  mov     rcx, [rcx+10h]
0x18002c803  call    WPP_SF_
0x18002c808  mov     ebx, 80004005h
0x18002c80d  jmp     loc_18002C89D
0x18002c812  lea     r15, [r14+8]
0x18002c816  lea     r8, [r14+320h]
0x18002c81d  mov     [rsp+50h+var_30], r15
0x18002c822  lea     r9, [rbp+arg_8]
0x18002c826  mov     rdx, [rbp+arg_18]
0x18002c82a  mov     rcx, [r14+310h]
0x18002c831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c836  mov     ebx, eax
0x18002c838  test    eax, eax
0x18002c83a  jns     short loc_18002C873
0x18002c83c  lea     rax, WPP_GLOBAL_Control
0x18002c843  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c84a  cmp     rcx, rax
0x18002c84d  jz      short loc_18002C86D
0x18002c84f  test    byte ptr [rcx+1Ch], 1
0x18002c853  jz      short loc_18002C86D
0x18002c855  mov     edx, 11h
0x18002c85a  mov     r9d, ebx
0x18002c85d  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002c864  mov     rcx, [rcx+10h]
0x18002c868  call    WPP_SF_d
0x18002c86d  bts     ebx, 1Ch
0x18002c871  jmp     short loc_18002C89D
0x18002c873  cmp     [rbp+arg_8], 0
0x18002c877  jz      short loc_18002C89B
0x18002c879  cmp     qword ptr [r15], 0
0x18002c87d  jz      short loc_18002C89B
0x18002c87f  mov     dword ptr [r13+0], 1
0x18002c887  mov     rdx, [rbp+var_18]
0x18002c88b  test    rdx, rdx
0x18002c88e  jz      short loc_18002C89B
0x18002c890  mov     r8, r12
0x18002c893  mov     rcx, r14
0x18002c896  call    ?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18002c89b  xor     ebx, ebx
0x18002c89d  mov     ecx, [rbp+arg_10]
0x18002c8a0  neg     ecx
0x18002c8a2  sbb     rcx, rcx
0x18002c8a5  and     rcx, rdi; hLibModule
0x18002c8a8  jz      short loc_18002C8B0
0x18002c8aa  call    cs:__imp_FreeLibrary
0x18002c8b0  mov     eax, ebx
0x18002c8b2  add     rsp, 50h
0x18002c8b6  pop     r15
0x18002c8b8  pop     r14
0x18002c8ba  pop     r13
0x18002c8bc  pop     r12
0x18002c8be  pop     rdi
0x18002c8bf  pop     rbx
0x18002c8c0  pop     rbp
0x18002c8c1  retn
```
