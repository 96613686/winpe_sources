# CGlobalSurfaceManager::ProcessKernelTokens(void)

- ea: `0x18015a394`
- end: `0x18015a50f`
- name: `?ProcessKernelTokens@CGlobalSurfaceManager@@AEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180233a20`

## callees

- `0x180050270`
- `0x18015a394`
- `0x18015a518`
- `0x18015a5bc`
- `0x18015a8c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015a3d4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015a3d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a48c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a48c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015a3c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015a3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a3de`
- `win32u!NtTokenManagerThread` at `0x18015a4cb`
- `win32u!NtTokenManagerThread` at `0x18015a4cb`

## pseudocode

```c
__int64 __fastcall CGlobalSurfaceManager::ProcessKernelTokens(CGlobalSurfaceManager *this)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+38h] [rbp-20h]

  v8 = *((_QWORD *)this + 16);
  v9 = 0;
  v2 = 0;
  while ( !*((_BYTE *)this + 144) )
  {
    SetLastError(0);
    if ( !ResetEvent(*((HANDLE *)this + 16)) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
        v2 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x183u, 0);
      return v2;
    }
    if ( *((_BYTE *)this + 144) )
      return v2;
    CMmcssTask::Clone((LPCRITICAL_SECTION)((char *)g_pComposition + 728), (LPCRITICAL_SECTION)((char *)this + 408));
    v5 = CGlobalSurfaceManager::EnsureAdapterInfo(this);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v6 = *((_QWORD *)this + 64) - *((_QWORD *)this + 63);
      *(_QWORD *)&v9 = *((_QWORD *)this + 63);
      DWORD2(v9) = -1431655765 * (v6 >> 3);
      v7 = NtTokenManagerThread(&v8);
      if ( v7 < 0 )
      {
        v2 = v7 | 0x10000000;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7 | 0x10000000, 0x1A3u, 0);
      }
      std::vector<CGlobalSurfaceManager::AdapterInfo>::clear((char *)this + 504);
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v5, 0x194u, 0);
      WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18015a394  mov     [rsp+arg_0], rbx
0x18015a399  mov     [rsp+arg_8], rsi
0x18015a39e  push    rdi
0x18015a39f  sub     rsp, 50h
0x18015a3a3  mov     rax, [rcx+80h]
0x18015a3aa  xorps   xmm0, xmm0
0x18015a3ad  mov     [rsp+58h+var_28], rax
0x18015a3b2  mov     rdi, rcx
0x18015a3b5  movups  [rsp+58h+var_20], xmm0
0x18015a3ba  xor     ebx, ebx
0x18015a3bc  cmp     byte ptr [rdi+90h], 0
0x18015a3c3  jnz     short loc_18015A41E
0x18015a3c5  xor     ecx, ecx; dwErrCode
0x18015a3c7  call    cs:__imp_SetLastError
0x18015a3cd  mov     rcx, [rdi+80h]; hEvent
0x18015a3d4  call    cs:__imp_ResetEvent
0x18015a3da  test    eax, eax
0x18015a3dc  jnz     short loc_18015A430
0x18015a3de  call    cs:__imp_GetLastError
0x18015a3e4  mov     ebx, eax
0x18015a3e6  test    eax, eax
0x18015a3e8  jle     short loc_18015A3F3
0x18015a3ea  movzx   ebx, ax
0x18015a3ed  or      ebx, 80070000h
0x18015a3f3  test    ebx, ebx
0x18015a3f5  mov     [rsp+58h+var_30], 0; void *
0x18015a3fe  mov     eax, 88980003h
0x18015a403  mov     [rsp+58h+var_38], 183h; unsigned int
0x18015a40b  cmovns  ebx, eax
0x18015a40e  xor     edx, edx; int *
0x18015a410  mov     r9d, ebx; int
0x18015a413  xor     r8d, r8d; unsigned int
0x18015a416  lea     ecx, [rdx+14h]; unsigned int
0x18015a419  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18015a41e  mov     rsi, [rsp+58h+arg_8]
0x18015a423  mov     eax, ebx
0x18015a425  mov     rbx, [rsp+58h+arg_0]
0x18015a42a  add     rsp, 50h
0x18015a42e  pop     rdi
0x18015a42f  retn
0x18015a430  cmp     byte ptr [rdi+90h], 0
0x18015a437  jnz     short loc_18015A41E
0x18015a439  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18015a440  lea     rdx, [rdi+198h]; LPCRITICAL_SECTION
0x18015a447  add     rcx, 2D8h; lpCriticalSection
0x18015a44e  call    ?Clone@CMmcssTask@@QEBAJPEAV1@@Z; CMmcssTask::Clone(CMmcssTask *)
0x18015a453  mov     rcx, rdi; this
0x18015a456  call    ?EnsureAdapterInfo@CGlobalSurfaceManager@@AEAAJXZ; CGlobalSurfaceManager::EnsureAdapterInfo(void)
0x18015a45b  mov     ebx, eax
0x18015a45d  test    eax, eax
0x18015a45f  jns     short loc_18015A497
0x18015a461  xor     edx, edx; int *
0x18015a463  mov     [rsp+58h+var_30], 0; void *
0x18015a46c  mov     r9d, eax; int
0x18015a46f  mov     [rsp+58h+var_38], 194h; unsigned int
0x18015a477  xor     r8d, r8d; unsigned int
0x18015a47a  lea     ecx, [rdx+14h]; unsigned int
0x18015a47d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18015a482  mov     rcx, [rdi+80h]; hHandle
0x18015a489  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015a48c  call    cs:__imp_WaitForSingleObject
0x18015a492  jmp     loc_18015A3BC
0x18015a497  mov     rcx, [rdi+200h]
0x18015a49e  lea     rsi, [rdi+1F8h]
0x18015a4a5  mov     rax, [rsi]
0x18015a4a8  sub     rcx, rax
0x18015a4ab  mov     qword ptr [rsp+58h+var_20], rax
0x18015a4b0  sar     rcx, 3
0x18015a4b4  mov     rax, 0AAAAAAAAAAAAAAABh
0x18015a4be  imul    rcx, rax
0x18015a4c2  mov     dword ptr [rsp+58h+var_20+8], ecx
0x18015a4c6  lea     rcx, [rsp+58h+var_28]
0x18015a4cb  call    cs:__imp_NtTokenManagerThread
0x18015a4d1  test    eax, eax
0x18015a4d3  js      short loc_18015A4E2
0x18015a4d5  mov     rcx, rsi
0x18015a4d8  call    ?clear@?$vector@VAdapterInfo@CGlobalSurfaceManager@@V?$allocator@VAdapterInfo@CGlobalSurfaceManager@@@std@@@std@@QEAAXXZ; std::vector<CGlobalSurfaceManager::AdapterInfo>::clear(void)
0x18015a4dd  jmp     loc_18015A3BC
0x18015a4e2  mov     ebx, eax
0x18015a4e4  or      ebx, 10000000h
0x18015a4ea  jge     short loc_18015A4D5
0x18015a4ec  xor     edx, edx; int *
0x18015a4ee  mov     [rsp+58h+var_30], 0; void *
0x18015a4f7  mov     r9d, ebx; int
0x18015a4fa  mov     [rsp+58h+var_38], 1A3h; unsigned int
0x18015a502  xor     r8d, r8d; unsigned int
0x18015a505  lea     ecx, [rdx+14h]; unsigned int
0x18015a508  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18015a50d  jmp     short loc_18015A4D5
```
