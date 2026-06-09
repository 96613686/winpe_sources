# LoadDynamicCalls

- ea: `0x1800084a0`
- end: `0x180008699`
- name: `LoadDynamicCalls`
- size: `505`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800081f0`
- `0x180008400`
- `0x18000d468`
- `0x180195a68`
- `0x1801bf360`
- `0x1801bf408`
- `0x1801bf65c`

## callees

- `0x1800084a0`
- `0x180008b6c`
- `0x180008c14`
- `0x1800185f4`
- `0x180027430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008610`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180008675`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180008675`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000856e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000856e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180008522`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180008522`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800084dd`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800084dd`

## pseudocode

```c
__int64 __fastcall LoadDynamicCalls(__int64 a1)
{
  unsigned int v3; // edi
  __int64 v4; // rsi
  FARPROC *i; // r14
  FARPROC ProcAddress; // rax
  const void *v7; // rdx
  signed int v8; // ebx
  signed int LastError; // eax
  __int64 v10; // rcx
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 40) )
    return 0;
  if ( !(unsigned __int8)RtlMrdataAcquireSectionWriteAccess() )
    return 2147500034LL;
  RtlRunOnceExecuteOnce(&g_RunOnceMrdataCommitObtained, RunOnceObtainMrdataCommit, &g_NtDllCalls, 0);
  if ( !(unsigned __int8)RtlMrdataAcquireSectionWriteAccess() )
    __fastfail(0x22u);
  RtlMrdataReleaseSectionWriteAccess(&g_NtDllCalls);
  if ( *(_DWORD *)(a1 + 44) )
  {
    v8 = *(_DWORD *)(a1 + 44);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_18;
  }
  memset_0(*(void **)(a1 + 24), 0, 8LL * *(unsigned int *)(a1 + 8));
  *(_QWORD *)(a1 + 32) = LoadLibraryExA(*(LPCSTR *)a1, 0, 0);
  if ( !*(_QWORD *)(a1 + 32) )
  {
    *(_DWORD *)(a1 + 44) = GetLastError();
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    RtlMrdataReleaseSectionWriteAccess(&g_NtDllCalls);
    return (unsigned int)v8;
  }
  v3 = 0;
  *(_DWORD *)(a1 + 40) = 1;
  v4 = *(_QWORD *)(a1 + 16);
  for ( i = *(FARPROC **)(a1 + 24); ; ++i )
  {
    if ( v3 >= *(_DWORD *)(a1 + 8) )
    {
      RtlMrdataReleaseSectionWriteAccess(&g_NtDllCalls);
      return 0;
    }
    ProcAddress = GetProcAddress(*(HMODULE *)(a1 + 32), *(LPCSTR *)v4);
    *i = ProcAddress;
    if ( !ProcAddress )
    {
      if ( *(_DWORD *)(v4 + 8) )
        break;
    }
    v4 += 16;
    ++v3;
  }
  if ( *(_DWORD *)(a1 + 40) )
  {
    RtlMrdataObtainSectionWriteAccess::RtlMrdataObtainSectionWriteAccess((RtlMrdataObtainSectionWriteAccess *)&v11, v7);
    *(_DWORD *)(a1 + 44) = 0;
    memset_0(*(void **)(a1 + 24), 0, 8LL * *(unsigned int *)(a1 + 8));
    FreeLibrary(*(HMODULE *)(a1 + 32));
    v10 = v11;
    *(_QWORD *)(a1 + 32) = 0;
    *(_DWORD *)(a1 + 40) = 0;
    RtlMrdataReleaseSectionWriteAccess(v10);
  }
  RtlMrdataReleaseSectionWriteAccess(&g_NtDllCalls);
  return 2147942527LL;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  sub     rsp, 20h
0x1800084a6  mov     eax, [rcx+28h]
0x1800084a9  mov     rbx, rcx
0x1800084ac  test    eax, eax
0x1800084ae  jz      short loc_1800084B8
0x1800084b0  xor     eax, eax
0x1800084b2  add     rsp, 20h
0x1800084b6  pop     rbx
0x1800084b7  retn
0x1800084b8  call    RtlMrdataAcquireSectionWriteAccess
0x1800084bd  test    al, al
0x1800084bf  jz      loc_1800085FC
0x1800084c5  xor     r9d, r9d
0x1800084c8  lea     r8, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x1800084cf  lea     rdx, ?RunOnceObtainMrdataCommit@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; RunOnceObtainMrdataCommit(_RTL_RUN_ONCE *,void *,void * *)
0x1800084d6  lea     rcx, ?g_RunOnceMrdataCommitObtained@@3T_RTL_RUN_ONCE@@C; _RTL_RUN_ONCE volatile g_RunOnceMrdataCommitObtained
0x1800084dd  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800084e3  call    RtlMrdataAcquireSectionWriteAccess
0x1800084e8  test    al, al
0x1800084ea  jz      loc_180008630
0x1800084f0  lea     rcx, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x1800084f7  call    RtlMrdataReleaseSectionWriteAccess
0x1800084fc  mov     eax, [rbx+2Ch]
0x1800084ff  test    eax, eax
0x180008501  jnz     loc_1800085E1
0x180008507  mov     r8d, [rbx+8]
0x18000850b  xor     edx, edx; Val
0x18000850d  mov     rcx, [rbx+18h]; void *
0x180008511  shl     r8, 3; Size
0x180008515  call    memset_0
0x18000851a  mov     rcx, [rbx]; lpLibFileName
0x18000851d  xor     r8d, r8d; dwFlags
0x180008520  xor     edx, edx; hFile
0x180008522  call    cs:__imp_LoadLibraryExA
0x180008528  mov     [rbx+20h], rax
0x18000852c  mov     rax, [rbx+20h]
0x180008530  test    rax, rax
0x180008533  jz      loc_180008607
0x180008539  mov     [rsp+28h+arg_8], rsi
0x18000853e  mov     [rsp+28h+arg_10], rdi
0x180008543  xor     edi, edi
0x180008545  mov     dword ptr [rbx+28h], 1
0x18000854c  mov     rsi, [rbx+10h]
0x180008550  mov     [rsp+28h+arg_18], r14
0x180008555  mov     r14, [rbx+18h]
0x180008559  nop     dword ptr [rax+00000000h]
0x180008560  mov     eax, [rbx+8]
0x180008563  cmp     edi, eax
0x180008565  jnb     short loc_1800085BF
0x180008567  mov     rdx, [rsi]; lpProcName
0x18000856a  mov     rcx, [rbx+20h]; hModule
0x18000856e  call    cs:__imp_GetProcAddress
0x180008574  mov     [r14], rax
0x180008577  test    rax, rax
0x18000857a  jz      short loc_180008588
0x18000857c  add     r14, 8
0x180008580  add     rsi, 10h
0x180008584  inc     edi
0x180008586  jmp     short loc_180008560
0x180008588  mov     eax, [rsi+8]
0x18000858b  test    eax, eax
0x18000858d  jz      short loc_18000857C
0x18000858f  mov     eax, [rbx+28h]
0x180008592  test    eax, eax
0x180008594  jnz     loc_18000864D
0x18000859a  lea     rcx, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x1800085a1  call    RtlMrdataReleaseSectionWriteAccess
0x1800085a6  mov     rdi, [rsp+28h+arg_10]
0x1800085ab  mov     eax, 8007007Fh
0x1800085b0  mov     rsi, [rsp+28h+arg_8]
0x1800085b5  mov     r14, [rsp+28h+arg_18]
0x1800085ba  jmp     loc_1800084B2
0x1800085bf  lea     rcx, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x1800085c6  call    RtlMrdataReleaseSectionWriteAccess
0x1800085cb  mov     rdi, [rsp+28h+arg_10]
0x1800085d0  xor     eax, eax
0x1800085d2  mov     rsi, [rsp+28h+arg_8]
0x1800085d7  mov     r14, [rsp+28h+arg_18]
0x1800085dc  jmp     loc_1800084B2
0x1800085e1  mov     ebx, [rbx+2Ch]
0x1800085e4  test    ebx, ebx
0x1800085e6  jg      short loc_180008637
0x1800085e8  lea     rcx, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x1800085ef  call    RtlMrdataReleaseSectionWriteAccess
0x1800085f4  mov     eax, ebx
0x1800085f6  add     rsp, 20h
0x1800085fa  pop     rbx
0x1800085fb  retn
0x1800085fc  mov     eax, 80004002h
0x180008601  add     rsp, 20h
0x180008605  pop     rbx
0x180008606  retn
0x180008607  call    cs:__imp_GetLastError
0x18000860d  mov     [rbx+2Ch], eax
0x180008610  call    cs:__imp_GetLastError
0x180008616  mov     ebx, eax
0x180008618  test    eax, eax
0x18000861a  jg      short loc_180008642
0x18000861c  lea     rcx, ?g_NtDllCalls@@3U_NTDLL_CALLS@@C; _NTDLL_CALLS volatile g_NtDllCalls
0x180008623  call    RtlMrdataReleaseSectionWriteAccess
0x180008628  mov     eax, ebx
0x18000862a  add     rsp, 20h
0x18000862e  pop     rbx
0x18000862f  retn
0x180008630  mov     ecx, 22h ; '"'
0x180008635  int     29h; Win8: RtlFailFast(ecx)
0x180008637  movzx   ebx, bx
0x18000863a  or      ebx, 80070000h
0x180008640  jmp     short loc_1800085E8
0x180008642  movzx   ebx, ax
0x180008645  or      ebx, 80070000h
0x18000864b  jmp     short loc_18000861C
0x18000864d  lea     rcx, [rsp+28h+arg_0]; this
0x180008652  call    ??0RtlMrdataObtainSectionWriteAccess@@QEAA@PEBX@Z; RtlMrdataObtainSectionWriteAccess::RtlMrdataObtainSectionWriteAccess(void const *)
0x180008657  mov     dword ptr [rbx+2Ch], 0
0x18000865e  xor     edx, edx; Val
0x180008660  mov     r8d, [rbx+8]
0x180008664  mov     rcx, [rbx+18h]; void *
0x180008668  shl     r8, 3; Size
0x18000866c  call    memset_0
0x180008671  mov     rcx, [rbx+20h]; hLibModule
0x180008675  call    cs:__imp_FreeLibrary
0x18000867b  mov     rcx, [rsp+28h+arg_0]
0x180008680  mov     qword ptr [rbx+20h], 0
0x180008688  mov     dword ptr [rbx+28h], 0
0x18000868f  call    RtlMrdataReleaseSectionWriteAccess
0x180008694  jmp     loc_18000859A
```
