# MoniterBrokeredClipboardOwner(ulong)

- ea: `0x1800393d0`
- end: `0x1800394b3`
- name: `?MoniterBrokeredClipboardOwner@@YAXK@Z`
- size: `227`
- prototype: `void __fastcall(unsigned int dwSourceProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x1800393d0`
- `0x180041f68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800393e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800393e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039461`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180039453`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180039453`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003948e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003948e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039414`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039414`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003943c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003947a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003943c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003947a`

## pseudocode

```c
void __fastcall MoniterBrokeredClipboardOwner(DWORD dwSourceProcessId)
{
  ClpboardOwnerState *v2; // rax
  ClpboardOwnerState *v3; // rbx
  HANDLE v4; // rax
  signed int LastError; // eax
  signed int v6; // edi
  unsigned int v7; // edx
  PTP_WAIT ThreadpoolWait; // rax
  signed int v9; // eax
  signed int v10; // edi

  v2 = (ClpboardOwnerState *)HeapAlloc(g_hHeap, 0, 0x10u);
  v3 = v2;
  if ( v2 )
  {
    v2->waiter = 0;
    v2->hProcess = 0;
    v4 = OpenProcess(0x100000u, 0, dwSourceProcessId);
    v3->hProcess = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      RoOriginateError((unsigned int)v6, 0);
      if ( v6 < 0 )
        goto LABEL_11;
    }
    ThreadpoolWait = CreateThreadpoolWait(
                       (PTP_WAIT_CALLBACK)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                       v3,
                       0);
    v3->waiter = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      RoOriginateError((unsigned int)v10, 0);
      if ( v10 < 0 )
        goto LABEL_11;
    }
    SetThreadpoolWait(v3->waiter, v3->hProcess, 0);
    v3 = (ClpboardOwnerState *)_InterlockedExchange64((volatile __int64 *)&s_pCurrentOwnerWaitInfo, (__int64)v3);
    if ( v3 )
LABEL_11:
      ClpboardOwnerState::`scalar deleting destructor'(v3, v7);
  }
}

```

## disassembly

```asm
0x1800393d0  mov     [rsp+arg_0], rbx
0x1800393d5  push    rdi
0x1800393d6  sub     rsp, 20h
0x1800393da  xor     edx, edx; dwFlags
0x1800393dc  mov     edi, dwSourceProcessId
0x1800393de  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800393e5  lea     r8d, [rdx+10h]; dwBytes
0x1800393e9  call    cs:__imp_HeapAlloc
0x1800393ef  mov     rbx, rax
0x1800393f2  test    rax, rax
0x1800393f5  jz      loc_1800394A8
0x1800393fb  mov     r8d, edi; dwProcessId
0x1800393fe  mov     qword ptr [rax], 0
0x180039405  xor     edx, edx; bInheritHandle
0x180039407  mov     qword ptr [rax+8], 0
0x18003940f  mov     dwSourceProcessId, 100000h; dwDesiredAccess
0x180039414  call    cs:__imp_OpenProcess
0x18003941a  mov     [rbx+8], rax
0x18003941e  test    rax, rax
0x180039421  jnz     short loc_180039446
0x180039423  call    cs:__imp_GetLastError
0x180039429  mov     edi, eax
0x18003942b  test    eax, eax
0x18003942d  jle     short loc_180039438
0x18003942f  movzx   edi, ax
0x180039432  or      edi, 80070000h
0x180039438  xor     edx, edx
0x18003943a  mov     dwSourceProcessId, edi
0x18003943c  call    cs:__imp_RoOriginateError
0x180039442  test    edi, edi
0x180039444  js      short loc_1800394A0
0x180039446  xor     r8d, r8d; pcbe
0x180039449  lea     rcx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; pfnwa
0x180039450  mov     rdx, rbx; pv
0x180039453  call    cs:__imp_CreateThreadpoolWait
0x180039459  mov     [rbx], rax
0x18003945c  test    rax, rax
0x18003945f  jnz     short loc_180039484
0x180039461  call    cs:__imp_GetLastError
0x180039467  mov     edi, eax
0x180039469  test    eax, eax
0x18003946b  jle     short loc_180039476
0x18003946d  movzx   edi, ax
0x180039470  or      edi, 80070000h
0x180039476  xor     edx, edx
0x180039478  mov     dwSourceProcessId, edi
0x18003947a  call    cs:__imp_RoOriginateError
0x180039480  test    edi, edi
0x180039482  js      short loc_1800394A0
0x180039484  mov     rdx, [rbx+8]; h
0x180039488  xor     r8d, r8d; pftTimeout
0x18003948b  mov     rcx, [rbx]; pwa
0x18003948e  call    cs:__imp_SetThreadpoolWait
0x180039494  xchg    rbx, cs:s_pCurrentOwnerWaitInfo
0x18003949b  test    rbx, rbx
0x18003949e  jz      short loc_1800394A8
0x1800394a0  mov     rcx, rbx; this
0x1800394a3  call    ??_GClpboardOwnerState@@QEAAPEAXI@Z; ClpboardOwnerState::`scalar deleting destructor'(uint)
0x1800394a8  mov     rbx, [rsp+28h+arg_0]
0x1800394ad  add     rsp, 20h
0x1800394b1  pop     rdi
0x1800394b2  retn
```
