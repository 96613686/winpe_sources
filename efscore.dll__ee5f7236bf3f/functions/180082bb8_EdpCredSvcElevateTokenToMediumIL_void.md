# EdpCredSvcElevateTokenToMediumIL(void *)

- ea: `0x180082bb8`
- end: `0x180082d54`
- name: `?EdpCredSvcElevateTokenToMediumIL@@YAJPEAX@Z`
- size: `412`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a0190`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180082bb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082bdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082bcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082d34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082bcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082d34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082d42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082c2f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082c2f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180082cc4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180082cc4`

## pseudocode

```c
__int64 __fastcall EdpCredSvcElevateTokenToMediumIL(HANDLE TokenHandle)
{
  HANDLE ProcessHeap; // rax
  char *v3; // rax
  _DWORD *v4; // rsi
  unsigned int v5; // ebx
  char *v6; // rbp
  int v7; // ecx
  signed int LastError; // eax
  int v9; // ecx
  signed int v10; // eax
  HANDLE v11; // rax
  DWORD cbSid; // [rsp+78h] [rbp+10h] BYREF

  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v3 = (char *)HeapAlloc(ProcessHeap, 8u, 0x54u);
  v4 = v3;
  if ( v3 )
  {
    v6 = v3 + 16;
    v5 = 0;
    if ( CreateWellKnownSid(WinMediumLabelSid, 0, v3 + 16, &cbSid) )
      goto LABEL_7;
    fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 236);
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v5,
                38,
                236) >= 0 )
    {
LABEL_7:
      *(_QWORD *)v4 = v6;
      v4[2] = 96;
      if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, 0x54u) )
      {
        fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 254);
        v10 = GetLastError();
        v5 = v10;
        if ( v10 > 0 )
          v5 = (unsigned __int16)v10 | 0x80070000;
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v5,
          38,
          254);
      }
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v4);
  }
  else
  {
    v5 = -2147024882;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 38, 226);
  }
  return v5;
}

```

## disassembly

```asm
0x180082bb8  push    rbx
0x180082bba  push    rbp
0x180082bbb  push    rsi
0x180082bbc  push    r14
0x180082bbe  sub     rsp, 48h
0x180082bc2  mov     r14, rcx
0x180082bc5  mov     [rsp+68h+cbSid], 44h ; 'D'
0x180082bcd  call    cs:__imp_GetProcessHeap
0x180082bd3  mov     edx, 8; dwFlags
0x180082bd8  mov     rcx, rax; hHeap
0x180082bdb  lea     r8d, [rdx+4Ch]; dwBytes
0x180082bdf  call    cs:__imp_HeapAlloc
0x180082be5  mov     rsi, rax
0x180082be8  test    rax, rax
0x180082beb  jnz     short loc_180082C1C
0x180082bed  mov     rcx, cs:g_hPublisher
0x180082bf4  lea     r9d, [rax+26h]
0x180082bf8  mov     r8d, 8007000Eh
0x180082bfe  mov     [rsp+68h+var_48], 2E2h
0x180082c06  lea     rdx, EFS_TRACE_ERROR
0x180082c0d  mov     ebx, 8007000Eh
0x180082c12  call    fnEfsLogTrace1
0x180082c17  jmp     loc_180082D48
0x180082c1c  lea     rbp, [rax+10h]
0x180082c20  xor     ebx, ebx
0x180082c22  lea     r9, [rsp+68h+cbSid]; cbSid
0x180082c27  mov     r8, rbp; pSid
0x180082c2a  xor     edx, edx; DomainSid
0x180082c2c  lea     ecx, [rbx+43h]; WellKnownSidType
0x180082c2f  call    cs:__imp_CreateWellKnownSid
0x180082c35  test    eax, eax
0x180082c37  jnz     short loc_180082CAA
0x180082c39  lea     r9d, [rbx+26h]
0x180082c3d  mov     [rsp+68h+var_48], 2ECh
0x180082c45  lea     r8, sourceString
0x180082c4c  lea     rdx, EFS_TRACE_START_EVENT
0x180082c53  call    fnEfsLogTrace1Strings
0x180082c58  call    cs:__imp_GetLastError
0x180082c5e  mov     ebx, eax
0x180082c60  test    eax, eax
0x180082c62  jle     short loc_180082C6D
0x180082c64  movzx   ebx, ax
0x180082c67  or      ebx, 80070000h
0x180082c6d  mov     rcx, cs:g_hPublisher
0x180082c74  lea     r9, sourceString
0x180082c7b  mov     [rsp+68h+var_38], 2ECh
0x180082c83  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180082c8a  mov     [rsp+68h+var_40], 26h ; '&'
0x180082c92  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180082c99  mov     [rsp+68h+var_48], ebx
0x180082c9d  call    fnEfsLogTrace1String1Dword
0x180082ca2  test    eax, eax
0x180082ca4  js      loc_180082D34
0x180082caa  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180082cb0  mov     [rsi], rbp
0x180082cb3  mov     r8, rsi; TokenInformation
0x180082cb6  mov     dword ptr [rsi+8], 60h ; '`'
0x180082cbd  mov     rcx, r14; TokenHandle
0x180082cc0  lea     edx, [r9-3Bh]; TokenInformationClass
0x180082cc4  call    cs:__imp_SetTokenInformation
0x180082cca  test    eax, eax
0x180082ccc  jnz     short loc_180082D34
0x180082cce  mov     ebp, 2FEh
0x180082cd3  lea     r9d, [rax+26h]
0x180082cd7  lea     r8, sourceString
0x180082cde  mov     [rsp+68h+var_48], ebp
0x180082ce2  lea     rdx, EFS_TRACE_START_EVENT
0x180082ce9  call    fnEfsLogTrace1Strings
0x180082cee  call    cs:__imp_GetLastError
0x180082cf4  mov     ebx, eax
0x180082cf6  test    eax, eax
0x180082cf8  jle     short loc_180082D03
0x180082cfa  movzx   ebx, ax
0x180082cfd  or      ebx, 80070000h
0x180082d03  mov     rcx, cs:g_hPublisher
0x180082d0a  lea     r9, sourceString
0x180082d11  mov     [rsp+68h+var_38], ebp
0x180082d15  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180082d1c  mov     [rsp+68h+var_40], 26h ; '&'
0x180082d24  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180082d2b  mov     [rsp+68h+var_48], ebx
0x180082d2f  call    fnEfsLogTrace1String1Dword
0x180082d34  call    cs:__imp_GetProcessHeap
0x180082d3a  mov     r8, rsi; lpMem
0x180082d3d  xor     edx, edx; dwFlags
0x180082d3f  mov     rcx, rax; hHeap
0x180082d42  call    cs:__imp_HeapFree
0x180082d48  mov     eax, ebx
0x180082d4a  add     rsp, 48h
0x180082d4e  pop     r14
0x180082d50  pop     rsi
0x180082d51  pop     rbp
0x180082d52  pop     rbx
0x180082d53  retn
```
