# MoniterBrokeredClipboardOwner(ulong)

- ea: `0x18003d4f0`
- end: `0x18003d604`
- name: `?MoniterBrokeredClipboardOwner@@YAXK@Z`
- size: `276`
- prototype: `void __fastcall(unsigned int dwSourceProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dbc0`

## callees

- `0x18003d4f0`
- `0x1800441cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d509`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d59c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d59c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003d588`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003d588`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003d5d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003d5d8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003d534`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003d534`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d568`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d5bb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d568`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003d5bb`

## pseudocode

```c
void __fastcall MoniterBrokeredClipboardOwner(DWORD dwSourceProcessId)
{
  HANDLE *v2; // rax
  HANDLE *v3; // rbx
  HANDLE v4; // rax
  signed int LastError; // eax
  signed int v6; // edi
  unsigned int v7; // edx
  ClpboardOwnerState *v8; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  signed int v10; // eax
  signed int v11; // edi
  __int64 v12; // rbx

  v2 = (HANDLE *)HeapAlloc(g_hHeap, 0, 0x10u);
  v3 = v2;
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
    v4 = OpenProcess(0x100000u, 0, dwSourceProcessId);
    v3[1] = v4;
    if ( v4 )
      goto LABEL_15;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    RoOriginateError((unsigned int)v6, 0);
    v8 = (ClpboardOwnerState *)v3;
    if ( v6 >= 0 )
    {
LABEL_15:
      ThreadpoolWait = CreateThreadpoolWait(
                         (PTP_WAIT_CALLBACK)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                         v3,
                         0);
      *v3 = ThreadpoolWait;
      if ( ThreadpoolWait )
        goto LABEL_10;
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      RoOriginateError((unsigned int)v11, 0);
      v8 = (ClpboardOwnerState *)v3;
      if ( v11 >= 0 )
      {
LABEL_10:
        SetThreadpoolWait((PTP_WAIT)*v3, v3[1], 0);
        v12 = _InterlockedExchange64((volatile __int64 *)&s_pCurrentOwnerWaitInfo, (__int64)v3);
        if ( !v12 )
          return;
        v8 = (ClpboardOwnerState *)v12;
      }
    }
    ClpboardOwnerState::`scalar deleting destructor'(v8, v7);
  }
}

```

## disassembly

```asm
0x18003d4f0  mov     [rsp+arg_0], rbx
0x18003d4f5  push    rdi
0x18003d4f6  sub     rsp, 20h
0x18003d4fa  xor     edx, edx; dwFlags
0x18003d4fc  mov     edi, dwSourceProcessId
0x18003d4fe  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003d505  lea     r8d, [rdx+10h]; dwBytes
0x18003d509  call    cs:__imp_HeapAlloc
0x18003d510  nop     dword ptr [rax+rax+00h]
0x18003d515  mov     rbx, rax
0x18003d518  test    rax, rax
0x18003d51b  jz      loc_18003D5F8
0x18003d521  and     qword ptr [rax], 0
0x18003d525  mov     r8d, edi; dwProcessId
0x18003d528  and     qword ptr [rax+8], 0
0x18003d52d  xor     edx, edx; bInheritHandle
0x18003d52f  mov     dwSourceProcessId, 100000h; dwDesiredAccess
0x18003d534  call    cs:__imp_OpenProcess
0x18003d53b  nop     dword ptr [rax+rax+00h]
0x18003d540  mov     [rbx+8], rax
0x18003d544  test    rax, rax
0x18003d547  jnz     short loc_18003D57B
0x18003d549  call    cs:__imp_GetLastError
0x18003d550  nop     dword ptr [rax+rax+00h]
0x18003d555  mov     edi, eax
0x18003d557  test    eax, eax
0x18003d559  jle     short loc_18003D564
0x18003d55b  movzx   edi, ax
0x18003d55e  or      edi, 80070000h
0x18003d564  xor     edx, edx
0x18003d566  mov     dwSourceProcessId, edi
0x18003d568  call    cs:__imp_RoOriginateError
0x18003d56f  nop     dword ptr [rax+rax+00h]
0x18003d574  mov     rcx, rbx
0x18003d577  test    edi, edi
0x18003d579  js      short loc_18003D5F3
0x18003d57b  xor     r8d, r8d; pcbe
0x18003d57e  lea     rcx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; pfnwa
0x18003d585  mov     rdx, rbx; pv
0x18003d588  call    cs:__imp_CreateThreadpoolWait
0x18003d58f  nop     dword ptr [rax+rax+00h]
0x18003d594  mov     [rbx], rax
0x18003d597  test    rax, rax
0x18003d59a  jnz     short loc_18003D5CE
0x18003d59c  call    cs:__imp_GetLastError
0x18003d5a3  nop     dword ptr [rax+rax+00h]
0x18003d5a8  mov     edi, eax
0x18003d5aa  test    eax, eax
0x18003d5ac  jle     short loc_18003D5B7
0x18003d5ae  movzx   edi, ax
0x18003d5b1  or      edi, 80070000h
0x18003d5b7  xor     edx, edx
0x18003d5b9  mov     dwSourceProcessId, edi
0x18003d5bb  call    cs:__imp_RoOriginateError
0x18003d5c2  nop     dword ptr [rax+rax+00h]
0x18003d5c7  mov     rcx, rbx
0x18003d5ca  test    edi, edi
0x18003d5cc  js      short loc_18003D5F3
0x18003d5ce  mov     rdx, [rbx+8]; h
0x18003d5d2  xor     r8d, r8d; pftTimeout
0x18003d5d5  mov     rcx, [rbx]; pwa
0x18003d5d8  call    cs:__imp_SetThreadpoolWait
0x18003d5df  nop     dword ptr [rax+rax+00h]
0x18003d5e4  xchg    rbx, cs:s_pCurrentOwnerWaitInfo
0x18003d5eb  test    rbx, rbx
0x18003d5ee  jz      short loc_18003D5F8
0x18003d5f0  mov     rcx, rbx; this
0x18003d5f3  call    ??_GClpboardOwnerState@@QEAAPEAXI@Z; ClpboardOwnerState::`scalar deleting destructor'(uint)
0x18003d5f8  mov     rbx, [rsp+28h+arg_0]
0x18003d5fd  add     rsp, 20h
0x18003d601  pop     rdi
0x18003d602  retn
```
