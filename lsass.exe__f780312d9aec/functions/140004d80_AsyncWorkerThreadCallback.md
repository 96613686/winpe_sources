# AsyncWorkerThreadCallback

- ea: `0x140004d80`
- end: `0x140004ed0`
- name: `AsyncWorkerThreadCallback`
- size: `336`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _OWORD *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400016c0`
- `0x14000481c`
- `0x1400049c8`
- `0x140004d80`
- `0x140005044`
- `0x140006010`

## import_xrefs

- `ntdll!NtClose` at `0x140004eb3`
- `ntdll!NtClose` at `0x140004eb3`
- `ntdll!RtlEnterCriticalSection` at `0x140004dbf`
- `ntdll!RtlEnterCriticalSection` at `0x140004dbf`
- `ntdll!RtlLeaveCriticalSection` at `0x140004e06`
- `ntdll!RtlLeaveCriticalSection` at `0x140004e06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140004d9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140004ea9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140004d9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140004ea9`
- `SspiSrv!SspirDeleteSecurityContext` at `0x140004e72`
- `SspiSrv!SspirDeleteSecurityContext` at `0x140004e72`

## pseudocode

```c
void __fastcall AsyncWorkerThreadCallback(PTP_CALLBACK_INSTANCE Instance, _OWORD *Context)
{
  void *v3; // r10
  void (__fastcall *v4)(__int128 *, const wchar_t *, void **); // rax
  __int64 v5; // rdx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  unsigned int v9; // eax
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  TlsSetValue(dwTlsIndex, Context + 2);
  v3 = qword_14000C208;
  if ( qword_14000C208 )
    goto LABEL_9;
  v10 = Context[1];
  RtlEnterCriticalSection(&InitConnectionCriticalSection);
  if ( !qword_14000C208 )
  {
    if ( gLsapSspiExtension )
    {
      v4 = *(void (__fastcall **)(__int128 *, const wchar_t *, void **))(gLsapSspiExtension + 128);
      if ( v4 )
        v4(&v10, L"AsyncKsecDD", &qword_14000C208);
    }
  }
  RtlLeaveCriticalSection(&InitConnectionCriticalSection);
  v3 = qword_14000C208;
  if ( qword_14000C208 )
  {
LABEL_9:
    v6 = *((_DWORD *)Context + 2);
    if ( !v6 )
    {
      AsyncAcquireCredentialsHandle(v3, (struct _KsecIoctlIpcFunctionCall *)Context);
      goto LABEL_23;
    }
    v7 = v6 - 1;
    if ( !v7 || (v8 = v7 - 1) == 0 )
    {
      AsyncProcessSecurityContext(v3, (struct _KsecIoctlIpcFunctionCall *)Context);
      goto LABEL_23;
    }
    if ( v8 == 1 )
    {
      if ( gLsapSspiExtension && *(_QWORD *)(gLsapSspiExtension + 64) )
      {
        if ( *((_DWORD *)Context + 10) >= 0x50u )
        {
          v9 = SspirDeleteSecurityContext(v3, Context + 1, (char *)Context + 56, 0, v10, *((_QWORD *)&v10 + 1));
          if ( !*((_DWORD *)Context + 18) )
            goto LABEL_23;
          v5 = v9;
        }
        else
        {
          v5 = 3221225507LL;
        }
      }
      else
      {
        v5 = 3221225659LL;
      }
    }
    else
    {
      v5 = 3221225474LL;
    }
  }
  else
  {
    v5 = 3221225792LL;
  }
  SendStatusOnlyResponse(Context, v5);
LABEL_23:
  TlsSetValue(dwTlsIndex, 0);
  NtClose(*((HANDLE *)Context + 4));
  LsapFreeLsaHeap(Context);
}

```

## disassembly

```asm
0x140004d80  mov     [rsp+arg_0], rbx
0x140004d85  mov     [rsp+arg_8], rsi
0x140004d8a  push    rdi
0x140004d8b  sub     rsp, 30h
0x140004d8f  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x140004d95  mov     rbx, rdx
0x140004d98  add     rdx, 20h ; ' '; lpTlsValue
0x140004d9c  call    cs:__imp_TlsSetValue
0x140004da2  mov     r10, cs:qword_14000C208
0x140004da9  test    r10, r10
0x140004dac  jnz     short loc_140004E27
0x140004dae  movups  xmm0, xmmword ptr [rbx+10h]
0x140004db2  lea     rcx, ?InitConnectionCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140004db9  movdqu  [rsp+38h+var_18], xmm0
0x140004dbf  call    cs:__imp_RtlEnterCriticalSection
0x140004dc5  cmp     cs:qword_14000C208, 0
0x140004dcd  jnz     short loc_140004DFF
0x140004dcf  mov     rax, cs:gLsapSspiExtension
0x140004dd6  test    rax, rax
0x140004dd9  jz      short loc_140004DFF
0x140004ddb  mov     rax, [rax+80h]
0x140004de2  test    rax, rax
0x140004de5  jz      short loc_140004DFF
0x140004de7  lea     r8, qword_14000C208
0x140004dee  lea     rdx, aAsyncksecdd; "AsyncKsecDD"
0x140004df5  lea     rcx, [rsp+38h+var_18]
0x140004dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dff  lea     rcx, ?InitConnectionCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140004e06  call    cs:__imp_RtlLeaveCriticalSection
0x140004e0c  mov     r10, cs:qword_14000C208
0x140004e13  test    r10, r10
0x140004e16  jnz     short loc_140004E27
0x140004e18  mov     edx, 0C0000140h
0x140004e1d  mov     rcx, rbx
0x140004e20  call    SendStatusOnlyResponse
0x140004e25  jmp     short loc_140004EA1
0x140004e27  mov     ecx, [rbx+8]
0x140004e2a  test    ecx, ecx
0x140004e2c  jz      short loc_140004E96
0x140004e2e  sub     ecx, 1
0x140004e31  jz      short loc_140004E89
0x140004e33  sub     ecx, 1
0x140004e36  jz      short loc_140004E89
0x140004e38  cmp     ecx, 1
0x140004e3b  jz      short loc_140004E44
0x140004e3d  mov     edx, 0C0000002h
0x140004e42  jmp     short loc_140004E1D
0x140004e44  mov     rax, cs:gLsapSspiExtension
0x140004e4b  test    rax, rax
0x140004e4e  jz      short loc_140004E82
0x140004e50  cmp     qword ptr [rax+40h], 0
0x140004e55  jz      short loc_140004E82
0x140004e57  cmp     dword ptr [rbx+28h], 50h ; 'P'
0x140004e5b  jnb     short loc_140004E64
0x140004e5d  mov     edx, 0C0000023h
0x140004e62  jmp     short loc_140004E1D
0x140004e64  lea     r8, [rbx+38h]
0x140004e68  xor     r9d, r9d
0x140004e6b  lea     rdx, [rbx+10h]
0x140004e6f  mov     rcx, r10
0x140004e72  call    cs:__imp_SspirDeleteSecurityContext
0x140004e78  cmp     dword ptr [rbx+48h], 0
0x140004e7c  jz      short loc_140004EA1
0x140004e7e  mov     edx, eax
0x140004e80  jmp     short loc_140004E1D
0x140004e82  mov     edx, 0C00000BBh
0x140004e87  jmp     short loc_140004E1D
0x140004e89  mov     rdx, rbx; struct _KsecIoctlIpcFunctionCall *
0x140004e8c  mov     rcx, r10; void *
0x140004e8f  call    ?AsyncProcessSecurityContext@@YAXPEAXPEAU_KsecIoctlIpcFunctionCall@@@Z; AsyncProcessSecurityContext(void *,_KsecIoctlIpcFunctionCall *)
0x140004e94  jmp     short loc_140004EA1
0x140004e96  mov     rdx, rbx; struct _KsecIoctlIpcFunctionCall *
0x140004e99  mov     rcx, r10; void *
0x140004e9c  call    ?AsyncAcquireCredentialsHandle@@YAXPEAXPEAU_KsecIoctlIpcFunctionCall@@@Z; AsyncAcquireCredentialsHandle(void *,_KsecIoctlIpcFunctionCall *)
0x140004ea1  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x140004ea7  xor     edx, edx; lpTlsValue
0x140004ea9  call    cs:__imp_TlsSetValue
0x140004eaf  mov     rcx, [rbx+20h]; Handle
0x140004eb3  call    cs:__imp_NtClose
0x140004eb9  mov     rcx, rbx
0x140004ebc  mov     rbx, [rsp+38h+arg_0]
0x140004ec1  mov     rsi, [rsp+38h+arg_8]
0x140004ec6  add     rsp, 30h
0x140004eca  pop     rdi
0x140004ecb  jmp     LsapFreeLsaHeap
```
