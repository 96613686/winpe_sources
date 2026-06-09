# CalibrationTask::ThreadProc(void *)

- ea: `0x180020290`
- end: `0x18002032d`
- name: `?ThreadProc@CalibrationTask@@CAKPEAX@Z`
- size: `157`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180020290`
- `0x18002e614`
- `0x18004b680`
- `0x180084010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800202da`
- `ntdll!RtlPublishWnfStateData` at `0x1800202da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180020326`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180020326`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800202a2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800202a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002030e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002030e`

## pseudocode

```c
void __fastcall __noreturn CalibrationTask::ThreadProc(HMODULE *Parameter)
{
  int v2; // esi
  int refreshed; // edi
  HMODULE v4; // rbp

  v2 = 0;
  refreshed = CoInitializeEx(0, 0);
  if ( refreshed < 0 || (v2 = 1, refreshed = InternalRefreshCalibration(0, 0), refreshed < 0) )
  {
    v4 = *Parameter;
    if ( !v2 )
      goto LABEL_6;
  }
  else
  {
    RtlPublishWnfStateData(WNF_DX_COLOR_PROFILE_CHANGE, 0, 0, 0, 0);
    v4 = *Parameter;
  }
  (*(void (__fastcall **)(HMODULE, _QWORD))(*(_QWORD *)Parameter[1] + 32LL))(Parameter[1], (unsigned int)refreshed);
  (*(void (__fastcall **)(HMODULE))(*(_QWORD *)Parameter[1] + 16LL))(Parameter[1]);
  CoUninitialize();
LABEL_6:
  operator delete(Parameter);
  FreeLibraryAndExitThread(v4, 0);
}

```

## disassembly

```asm
0x180020290  push    rbx
0x180020292  push    rbp
0x180020293  push    rsi
0x180020294  push    rdi
0x180020295  sub     rsp, 38h
0x180020299  mov     rbx, rcx
0x18002029c  xor     edx, edx; dwCoInit
0x18002029e  xor     ecx, ecx; pvReserved
0x1800202a0  xor     esi, esi
0x1800202a2  call    cs:__imp_CoInitializeEx
0x1800202a8  mov     edi, eax
0x1800202aa  test    eax, eax
0x1800202ac  js      short loc_1800202E5
0x1800202ae  xor     edx, edx
0x1800202b0  xor     ecx, ecx; lpString1
0x1800202b2  mov     esi, 1
0x1800202b7  call    InternalRefreshCalibration
0x1800202bc  mov     edi, eax
0x1800202be  test    eax, eax
0x1800202c0  js      short loc_1800202E5
0x1800202c2  mov     rcx, cs:WNF_DX_COLOR_PROFILE_CHANGE
0x1800202c9  xor     r9d, r9d
0x1800202cc  xor     r8d, r8d
0x1800202cf  mov     [rsp+58h+var_38], 0
0x1800202d8  xor     edx, edx
0x1800202da  call    cs:__imp_RtlPublishWnfStateData
0x1800202e0  mov     rbp, [rbx]
0x1800202e3  jmp     short loc_1800202EC
0x1800202e5  mov     rbp, [rbx]
0x1800202e8  test    esi, esi
0x1800202ea  jz      short loc_180020314
0x1800202ec  mov     rcx, [rbx+8]
0x1800202f0  mov     edx, edi
0x1800202f2  mov     rax, [rcx]
0x1800202f5  mov     rax, [rax+20h]
0x1800202f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202fe  mov     rcx, [rbx+8]
0x180020302  mov     rax, [rcx]
0x180020305  mov     rax, [rax+10h]
0x180020309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002030e  call    cs:__imp_CoUninitialize
0x180020314  mov     edx, 10h; unsigned __int64
0x180020319  mov     rcx, rbx; void *
0x18002031c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020321  xor     edx, edx; dwExitCode
0x180020323  mov     rcx, rbp; hLibModule
0x180020326  call    cs:__imp_FreeLibraryAndExitThread
```
