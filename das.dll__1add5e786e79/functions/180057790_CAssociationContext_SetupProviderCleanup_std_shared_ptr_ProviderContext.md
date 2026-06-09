# CAssociationContext::SetupProviderCleanup(std::shared_ptr<ProviderContext>)

- ea: `0x180057790`
- end: `0x1800578e5`
- name: `?SetupProviderCleanup@CAssociationContext@@IEAAJV?$shared_ptr@VProviderContext@@@std@@@Z`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180055614`
- `0x180055e2c`

## callees

- `0x1800190b4`
- `0x18001a268`
- `0x180057790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057864`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057864`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800577ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800577ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005779f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005779f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057885`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057893`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057893`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005781f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005781f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180057843`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180057843`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180057809`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180057809`

## pseudocode

```c
__int64 __fastcall CAssociationContext::SetupProviderCleanup(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _OWORD *v5; // rax
  unsigned int v6; // ebx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  __int64 v9; // rax
  HMODULE v10; // rcx
  void *v11; // rsi
  HANDLE v12; // rax
  std::_Ref_count_base *v13; // rcx

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x28u);
  *(_QWORD *)(a1 + 368) = v5;
  if ( !v5 )
  {
    v6 = -2147024882;
LABEL_8:
    CloseThreadpoolWork(*(PTP_WORK *)(a1 + 608));
    v9 = *(_QWORD *)(a1 + 368);
    *(_QWORD *)(a1 + 608) = 0;
    v10 = *(HMODULE *)(v9 + 16);
    if ( v10 )
    {
      FreeLibrary(v10);
      *(_QWORD *)(*(_QWORD *)(a1 + 368) + 16LL) = 0;
    }
    v11 = *(void **)(a1 + 368);
    if ( v11 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
      *(_QWORD *)(a1 + 368) = 0;
    }
    goto LABEL_13;
  }
  *v5 = 0;
  v5[1] = 0;
  *((_QWORD *)v5 + 4) = 0;
  if ( GetModuleHandleExW(4u, (LPCWSTR)InitializeAssociationServices, (HMODULE *)(*(_QWORD *)(a1 + 368) + 16LL)) )
  {
    ThreadpoolWork = CreateThreadpoolWork(CAssociationContext::CleanupProviderObjectsCallback, *(PVOID *)(a1 + 368), 0);
    *(_QWORD *)(a1 + 608) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      v6 = 0;
      **(_QWORD **)(a1 + 368) = *(_QWORD *)(a1 + 576);
      std::shared_ptr<ProviderContext>::operator=(*(_QWORD *)(a1 + 368) + 24LL, a2);
      goto LABEL_13;
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 )
    goto LABEL_8;
LABEL_13:
  v13 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  return v6;
}

```

## disassembly

```asm
0x180057790  push    rbx
0x180057792  push    rbp
0x180057793  push    rsi
0x180057794  push    rdi
0x180057795  sub     rsp, 28h
0x180057799  mov     rbp, rdx
0x18005779c  mov     rdi, rcx
0x18005779f  call    cs:__imp_GetProcessHeap
0x1800577a5  xor     edx, edx; dwFlags
0x1800577a7  mov     rcx, rax; hHeap
0x1800577aa  lea     r8d, [rdx+28h]; dwBytes
0x1800577ae  call    cs:__imp_HeapAlloc
0x1800577b4  mov     [rdi+170h], rax
0x1800577bb  test    rax, rax
0x1800577be  jnz     short loc_1800577C7
0x1800577c0  mov     ebx, 8007000Eh
0x1800577c5  jmp     short loc_18005783C
0x1800577c7  xorps   xmm0, xmm0
0x1800577ca  lea     rdx, ?InitializeAssociationServices@@YAJXZ; lpModuleName
0x1800577d1  movups  xmmword ptr [rax], xmm0
0x1800577d4  xor     ecx, ecx
0x1800577d6  movups  xmmword ptr [rax+10h], xmm0
0x1800577da  mov     [rax+20h], rcx
0x1800577de  mov     ecx, 4; dwFlags
0x1800577e3  mov     r8, [rdi+170h]
0x1800577ea  add     r8, 10h; phModule
0x1800577ee  call    cs:__imp_GetModuleHandleExW
0x1800577f4  test    eax, eax
0x1800577f6  jz      short loc_18005781F
0x1800577f8  mov     rdx, [rdi+170h]; pv
0x1800577ff  lea     rcx, ?CleanupProviderObjectsCallback@CAssociationContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180057806  xor     r8d, r8d; pcbe
0x180057809  call    cs:__imp_CreateThreadpoolWork
0x18005780f  mov     [rdi+260h], rax
0x180057816  test    rax, rax
0x180057819  jnz     loc_1800578A6
0x18005781f  call    cs:__imp_GetLastError
0x180057825  mov     ebx, eax
0x180057827  test    eax, eax
0x180057829  jle     short loc_180057834
0x18005782b  movzx   ebx, ax
0x18005782e  or      ebx, 80070000h
0x180057834  test    ebx, ebx
0x180057836  jz      loc_1800578CC
0x18005783c  mov     rcx, [rdi+260h]; pwk
0x180057843  call    cs:__imp_CloseThreadpoolWork
0x180057849  mov     rax, [rdi+170h]
0x180057850  mov     qword ptr [rdi+260h], 0
0x18005785b  mov     rcx, [rax+10h]; hLibModule
0x18005785f  test    rcx, rcx
0x180057862  jz      short loc_180057879
0x180057864  call    cs:__imp_FreeLibrary
0x18005786a  mov     rax, [rdi+170h]
0x180057871  mov     qword ptr [rax+10h], 0
0x180057879  mov     rsi, [rdi+170h]
0x180057880  test    rsi, rsi
0x180057883  jz      short loc_1800578CC
0x180057885  call    cs:__imp_GetProcessHeap
0x18005788b  mov     r8, rsi; lpMem
0x18005788e  xor     edx, edx; dwFlags
0x180057890  mov     rcx, rax; hHeap
0x180057893  call    cs:__imp_HeapFree
0x180057899  mov     qword ptr [rdi+170h], 0
0x1800578a4  jmp     short loc_1800578CC
0x1800578a6  mov     rcx, [rdi+170h]
0x1800578ad  xor     ebx, ebx
0x1800578af  mov     rax, [rdi+240h]
0x1800578b6  mov     rdx, rbp
0x1800578b9  mov     [rcx], rax
0x1800578bc  mov     rcx, [rdi+170h]
0x1800578c3  add     rcx, 18h
0x1800578c7  call    ??4?$shared_ptr@VProviderContext@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ProviderContext>::operator=(std::shared_ptr<ProviderContext> const &)
0x1800578cc  mov     rcx, [rbp+8]; this
0x1800578d0  test    rcx, rcx
0x1800578d3  jz      short loc_1800578DA
0x1800578d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800578da  mov     eax, ebx
0x1800578dc  add     rsp, 28h
0x1800578e0  pop     rdi
0x1800578e1  pop     rsi
0x1800578e2  pop     rbp
0x1800578e3  pop     rbx
0x1800578e4  retn
```
