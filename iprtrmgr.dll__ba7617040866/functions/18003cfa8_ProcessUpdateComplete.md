# ProcessUpdateComplete

- ea: `0x18003cfa8`
- end: `0x18003d33b`
- name: `ProcessUpdateComplete`
- size: `915`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x18003cce8`
- `0x18003cfa8`
- `0x18003fc84`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003d2fe`
- `KERNEL32!CloseHandle` at `0x18003d30b`
- `KERNEL32!CloseHandle` at `0x18003d2fe`
- `KERNEL32!CloseHandle` at `0x18003d30b`
- `KERNEL32!GetLastError` at `0x18003d296`
- `KERNEL32!GetLastError` at `0x18003d296`
- `KERNEL32!HeapAlloc` at `0x18003d167`
- `KERNEL32!HeapAlloc` at `0x18003d167`
- `KERNEL32!SetEvent` at `0x18003d1e3`
- `KERNEL32!SetEvent` at `0x18003d271`
- `KERNEL32!SetEvent` at `0x18003d1e3`
- `KERNEL32!SetEvent` at `0x18003d271`

## string_xrefs

- `0x18003d01c`: `ProcessUpdateComplete`
- `0x18003d0a2`: `ProcessUpdateComplete: Couldnt find the ICB for interface %d`
- `0x18003d114`: `ProcessUpdateComplete: No DIM event found in ICB - ERROR`
- `0x18003d187`: `ProcessUpdateComplete: Error allocating %d bytes`
- `0x18003d237`: `ProcessUpdateComplete: Notifying DIM of update route completion`
- `0x18003d29f`: `ProcessUpdateComplete: Error %d setting event for notifying completion of update routes for %ws`

## pseudocode

```c
__int64 __fastcall ProcessUpdateComplete(__int64 a1, unsigned int *a2)
{
  char v4; // al
  __int64 v5; // rcx
  __int64 i; // rdi
  __int64 v7; // rdx
  void *v9; // rsi
  __int128 *v10; // r9
  unsigned int v11; // ebx
  _DWORD *v12; // rax
  __int128 *v13; // r9
  _QWORD *v14; // rdx
  __int128 *v15; // r9
  __int64 v16; // rbx
  DWORD LastError; // eax
  __int128 *v18; // r9
  __int128 v19; // [rsp+38h] [rbp-870h] BYREF
  int v20; // [rsp+48h] [rbp-860h] BYREF
  __int128 v21; // [rsp+4Ch] [rbp-85Ch]
  __int128 v22; // [rsp+5Ch] [rbp-84Ch]
  int v23; // [rsp+6Ch] [rbp-83Ch]
  int v24; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v25[2044]; // [rsp+74h] [rbp-834h] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v23 = 0;
  v4 = Microsoft_Windows_RRASEnableBits;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Entered: %ws", L"ProcessUpdateComplete");
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
      v4 = Microsoft_Windows_RRASEnableBits;
    }
  }
  v5 = ICBList;
  for ( i = 0; (__int64 *)v5 != &ICBList; v5 = *(_QWORD *)v5 )
  {
    i = v5;
    if ( *(_DWORD *)(v5 + 16) == *a2 )
      break;
  }
  v7 = *a2;
  if ( *(_DWORD *)(i + 16) == (_DWORD)v7 )
  {
    if ( !a2[2] )
      ConvertRoutesToAutoStatic(*(unsigned int *)(a1 + 60), v7, i);
    v9 = *(void **)(i + 192);
    *(_QWORD *)(i + 192) = 0;
    if ( v9 )
    {
      v11 = 8;
      v12 = HeapAlloc(IPRouterHeap, 8u, 0x18u);
      if ( v12 )
      {
        v12[4] = a2[2];
        v14 = *(_QWORD **)(i + 208);
        if ( *v14 != i + 200 )
          __fastfail(3u);
        *(_QWORD *)v12 = i + 200;
        *((_QWORD *)v12 + 1) = v14;
        *v14 = v12;
        *(_QWORD *)(i + 208) = v12;
        ProcessSaveInterfaceConfigInfo(*(unsigned int *)(i + 16));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v15 = &v19;
          LOWORD(v20) = 0;
          if ( i != -688 )
            LODWORD(v15) = i + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)L"ProcessUpdateComplete: Notifying DIM of update route completion",
            (_DWORD)v15,
            *(_QWORD *)(i + 72),
            (__int64)&v20);
        }
        if ( SetEvent(v9) )
        {
          CloseHandle(v9);
          return 0;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = *(_QWORD *)(a1 + 24);
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(
            &v24,
            L"ProcessUpdateComplete: Error %d setting event for notifying completion of update routes for %ws",
            v16,
            LastError);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v18 = &v19;
            if ( i != -688 )
              LODWORD(v18) = i + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v24,
              (_DWORD)v18,
              *(_QWORD *)(i + 72),
              (__int64)&v20);
          }
        }
        v11 = 1003;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v24, L"ProcessUpdateComplete: Error allocating %d bytes", 24);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v13 = &v19;
            if ( i != -688 )
              LODWORD(v13) = i + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v24,
              (_DWORD)v13,
              *(_QWORD *)(i + 72),
              (__int64)&v20);
          }
        }
        SetEvent(v9);
      }
      CloseHandle(v9);
      return v11;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v10 = &v19;
      LOWORD(v20) = 0;
      if ( i != -688 )
        LODWORD(v10) = i + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"ProcessUpdateComplete: No DIM event found in ICB - ERROR",
        (_DWORD)v10,
        *(_QWORD *)(i + 72),
        (__int64)&v20);
    }
    return 1003;
  }
  else
  {
    if ( v4 < 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"ProcessUpdateComplete: Couldnt find the ICB for interface %d", (unsigned int)v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18003cfa8  mov     [rsp+arg_10], rbx
0x18003cfad  push    rsi
0x18003cfae  push    rdi
0x18003cfaf  push    r13
0x18003cfb1  push    r14
0x18003cfb3  push    r15
0x18003cfb5  sub     rsp, 880h
0x18003cfbc  mov     rax, cs:__security_cookie
0x18003cfc3  xor     rax, rsp
0x18003cfc6  mov     [rsp+8A8h+var_38], rax
0x18003cfce  mov     r14, rdx
0x18003cfd1  mov     r15, rcx
0x18003cfd4  xor     eax, eax
0x18003cfd6  lea     rcx, [rsp+8A8h+var_834]; void *
0x18003cfdb  xor     edx, edx; Val
0x18003cfdd  mov     [rsp+8A8h+var_838], eax
0x18003cfe1  mov     r8d, 7FCh; Size
0x18003cfe7  call    memset_0
0x18003cfec  xor     eax, eax
0x18003cfee  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003cff5  xorps   xmm0, xmm0
0x18003cff8  mov     [rsp+8A8h+var_860], eax
0x18003cffc  mov     [rsp+8A8h+var_83C], eax
0x18003d000  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003d007  movups  [rsp+8A8h+var_85C], xmm0
0x18003d00c  movups  [rsp+8A8h+var_84C], xmm0
0x18003d011  movups  [rsp+8A8h+var_870], xmm0
0x18003d016  test    al, al
0x18003d018  jns     short loc_18003D05F
0x18003d01a  xor     eax, eax
0x18003d01c  lea     r8, aProcessupdatec_4; "ProcessUpdateComplete"
0x18003d023  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003d02a  mov     word ptr [rsp+8A8h+var_838], ax
0x18003d02f  lea     rcx, [rsp+8A8h+var_838]
0x18003d034  call    FormatRRASErrorString
0x18003d039  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003d040  test    al, al
0x18003d042  jns     short loc_18003D05F
0x18003d044  lea     r8, [rsp+8A8h+var_838]
0x18003d049  mov     rcx, r13
0x18003d04c  lea     rdx, RasRtrmgrTraceInfo
0x18003d053  call    McTemplateU0z_EventWriteTransfer
0x18003d058  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003d05f  mov     rcx, cs:ICBList
0x18003d066  lea     r8, ICBList
0x18003d06d  xor     edi, edi
0x18003d06f  cmp     rcx, r8
0x18003d072  jz      short loc_18003D087
0x18003d074  mov     edx, [r14]
0x18003d077  mov     rdi, rcx
0x18003d07a  cmp     [rcx+10h], edx
0x18003d07d  jz      short loc_18003D087
0x18003d07f  mov     rcx, [rcx]
0x18003d082  cmp     rcx, r8
0x18003d085  jnz     short loc_18003D077
0x18003d087  mov     edx, [r14]
0x18003d08a  cmp     [rdi+10h], edx
0x18003d08d  jz      short loc_18003D0D5
0x18003d08f  test    al, al
0x18003d091  jns     short loc_18003D0CB
0x18003d093  xor     eax, eax
0x18003d095  lea     rcx, [rsp+8A8h+var_838]
0x18003d09a  mov     r8d, edx
0x18003d09d  mov     word ptr [rsp+8A8h+var_838], ax
0x18003d0a2  lea     rdx, aProcessupdatec_1; "ProcessUpdateComplete: Couldnt find the"...
0x18003d0a9  call    FormatRRASErrorString
0x18003d0ae  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003d0b5  jge     short loc_18003D0CB
0x18003d0b7  lea     r8, [rsp+8A8h+var_838]
0x18003d0bc  mov     rcx, r13
0x18003d0bf  lea     rdx, RasRtrmgrTraceInfo
0x18003d0c6  call    McTemplateU0z_EventWriteTransfer
0x18003d0cb  mov     eax, 57h ; 'W'
0x18003d0d0  jmp     loc_18003D313
0x18003d0d5  cmp     dword ptr [r14+8], 0
0x18003d0da  jnz     short loc_18003D0E8
0x18003d0dc  mov     ecx, [r15+3Ch]
0x18003d0e0  mov     r8, rdi
0x18003d0e3  call    ConvertRoutesToAutoStatic
0x18003d0e8  mov     rsi, [rdi+0C0h]
0x18003d0ef  mov     qword ptr [rdi+0C0h], 0
0x18003d0fa  test    rsi, rsi
0x18003d0fd  jnz     short loc_18003D155
0x18003d0ff  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003d106  jz      short loc_18003D14B
0x18003d108  xor     eax, eax
0x18003d10a  lea     r9, [rsp+8A8h+var_870]
0x18003d10f  mov     word ptr [rsp+8A8h+var_860], ax
0x18003d114  lea     r8, aProcessupdatec_2; "ProcessUpdateComplete: No DIM event fou"...
0x18003d11b  lea     rax, [rdi+2B0h]
0x18003d122  mov     rcx, r13
0x18003d125  test    rax, rax
0x18003d128  lea     rdx, RasRtrMgrParamTraceError
0x18003d12f  cmovnz  r9, rax
0x18003d133  lea     rax, [rsp+8A8h+var_860]
0x18003d138  mov     [rsp+8A8h+var_880], rax
0x18003d13d  mov     rax, [rdi+48h]
0x18003d141  mov     [rsp+8A8h+var_888], rax
0x18003d146  call    McTemplateU0zjzz_EventWriteTransfer
0x18003d14b  mov     eax, 3EBh
0x18003d150  jmp     loc_18003D313
0x18003d155  mov     rcx, cs:IPRouterHeap; hHeap
0x18003d15c  mov     ebx, 8
0x18003d161  mov     edx, ebx; dwFlags
0x18003d163  lea     r8d, [rbx+10h]; dwBytes
0x18003d167  call    cs:__imp_HeapAlloc
0x18003d16d  mov     rcx, rax
0x18003d170  test    rax, rax
0x18003d173  jnz     short loc_18003D1EE
0x18003d175  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003d17c  jz      short loc_18003D1E0
0x18003d17e  lea     r8d, [rbx+10h]
0x18003d182  mov     word ptr [rsp+8A8h+var_838], ax
0x18003d187  lea     rdx, aProcessupdatec_3; "ProcessUpdateComplete: Error allocating"...
0x18003d18e  mov     word ptr [rsp+8A8h+var_860], ax
0x18003d193  lea     rcx, [rsp+8A8h+var_838]
0x18003d198  call    FormatRRASErrorString
0x18003d19d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003d1a4  jz      short loc_18003D1E0
0x18003d1a6  lea     rax, [rdi+2B0h]
0x18003d1ad  mov     rcx, r13
0x18003d1b0  test    rax, rax
0x18003d1b3  lea     r9, [rsp+8A8h+var_870]
0x18003d1b8  lea     r8, [rsp+8A8h+var_838]
0x18003d1bd  cmovnz  r9, rax
0x18003d1c1  lea     rdx, RasRtrMgrParamTraceError
0x18003d1c8  lea     rax, [rsp+8A8h+var_860]
0x18003d1cd  mov     [rsp+8A8h+var_880], rax
0x18003d1d2  mov     rax, [rdi+48h]
0x18003d1d6  mov     [rsp+8A8h+var_888], rax
0x18003d1db  call    McTemplateU0zjzz_EventWriteTransfer
0x18003d1e0  mov     rcx, rsi; hEvent
0x18003d1e3  call    cs:__imp_SetEvent
0x18003d1e9  jmp     loc_18003D2FB
0x18003d1ee  mov     eax, [r14+8]
0x18003d1f2  mov     [rcx+10h], eax
0x18003d1f5  lea     rax, [rdi+0C8h]
0x18003d1fc  mov     rdx, [rax+8]
0x18003d200  cmp     [rdx], rax
0x18003d203  jz      short loc_18003D20C
0x18003d205  mov     ecx, 3
0x18003d20a  int     29h; Win8: RtlFailFast(ecx)
0x18003d20c  mov     [rcx], rax
0x18003d20f  mov     [rcx+8], rdx
0x18003d213  mov     [rdx], rcx
0x18003d216  mov     [rax+8], rcx
0x18003d21a  mov     ecx, [rdi+10h]
0x18003d21d  call    ProcessSaveInterfaceConfigInfo
0x18003d222  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003d229  jz      short loc_18003D26E
0x18003d22b  xor     eax, eax
0x18003d22d  lea     r9, [rsp+8A8h+var_870]
0x18003d232  mov     word ptr [rsp+8A8h+var_860], ax
0x18003d237  lea     r8, aProcessupdatec_0; "ProcessUpdateComplete: Notifying DIM of"...
0x18003d23e  lea     rax, [rdi+2B0h]
0x18003d245  mov     rcx, r13
0x18003d248  test    rax, rax
0x18003d24b  lea     rdx, RasRtrmgrParamTraceInfo
0x18003d252  cmovnz  r9, rax
0x18003d256  lea     rax, [rsp+8A8h+var_860]
0x18003d25b  mov     [rsp+8A8h+var_880], rax
0x18003d260  mov     rax, [rdi+48h]
0x18003d264  mov     [rsp+8A8h+var_888], rax
0x18003d269  call    McTemplateU0zjzz_EventWriteTransfer
0x18003d26e  mov     rcx, rsi; hEvent
0x18003d271  call    cs:__imp_SetEvent
0x18003d277  test    eax, eax
0x18003d279  jnz     loc_18003D308
0x18003d27f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003d286  jz      short loc_18003D2F6
0x18003d288  mov     rbx, [r15+18h]
0x18003d28c  mov     word ptr [rsp+8A8h+var_838], ax
0x18003d291  mov     word ptr [rsp+8A8h+var_860], ax
0x18003d296  call    cs:__imp_GetLastError
0x18003d29c  mov     r8, rbx
0x18003d29f  lea     rdx, aProcessupdatec; "ProcessUpdateComplete: Error %d setting"...
0x18003d2a6  mov     r9d, eax
0x18003d2a9  lea     rcx, [rsp+8A8h+var_838]
0x18003d2ae  call    FormatRRASErrorString
0x18003d2b3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003d2ba  jz      short loc_18003D2F6
0x18003d2bc  lea     rax, [rdi+2B0h]
0x18003d2c3  mov     rcx, r13
0x18003d2c6  test    rax, rax
0x18003d2c9  lea     r9, [rsp+8A8h+var_870]
0x18003d2ce  lea     r8, [rsp+8A8h+var_838]
0x18003d2d3  cmovnz  r9, rax
0x18003d2d7  lea     rdx, RasRtrMgrParamTraceError
0x18003d2de  lea     rax, [rsp+8A8h+var_860]
0x18003d2e3  mov     [rsp+8A8h+var_880], rax
0x18003d2e8  mov     rax, [rdi+48h]
0x18003d2ec  mov     [rsp+8A8h+var_888], rax
0x18003d2f1  call    McTemplateU0zjzz_EventWriteTransfer
0x18003d2f6  mov     ebx, 3EBh
0x18003d2fb  mov     rcx, rsi; hObject
0x18003d2fe  call    cs:__imp_CloseHandle
0x18003d304  mov     eax, ebx
0x18003d306  jmp     short loc_18003D313
0x18003d308  mov     rcx, rsi; hObject
0x18003d30b  call    cs:__imp_CloseHandle
0x18003d311  xor     eax, eax
0x18003d313  mov     rcx, [rsp+8A8h+var_38]
0x18003d31b  xor     rcx, rsp; StackCookie
0x18003d31e  call    __security_check_cookie
0x18003d323  mov     rbx, [rsp+8A8h+arg_10]
0x18003d32b  add     rsp, 880h
0x18003d332  pop     r15
0x18003d334  pop     r14
0x18003d336  pop     r13
0x18003d338  pop     rdi
0x18003d339  pop     rsi
0x18003d33a  retn
```
