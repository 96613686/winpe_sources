# FolderCommandHandlerThreadProc(void *)

- ea: `0x1800448b0`
- end: `0x180044981`
- name: `?FolderCommandHandlerThreadProc@@YAKPEAX@Z`
- size: `209`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180019204`

## callees

- `0x180005d80`
- `0x180018d74`
- `0x18001e5b0`
- `0x1800448b0`
- `0x180065010`

## import_xrefs

- `SHELL32!SHGetInstanceExplorer` at `0x1800448d2`
- `SHELL32!SHGetInstanceExplorer` at `0x1800448d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180044965`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180044965`
- `ole32!CoUninitialize` at `0x18004494b`
- `ole32!CoUninitialize` at `0x18004494b`
- `ole32!CoInitializeEx` at `0x1800448ec`
- `ole32!CoInitializeEx` at `0x1800448ec`

## pseudocode

```c
__int64 __fastcall FolderCommandHandlerThreadProc(char *Parameter)
{
  HRESULT v2; // edi
  int v3; // ebp
  struct IUnknown *v4; // rcx
  HMODULE v5; // rsi
  struct IUnknown *v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  if ( SHGetInstanceExplorer(&v7) < 0 )
    v7 = 0;
  v2 = CoInitializeEx(0, 6u);
  if ( v2 < 0 )
  {
    v3 = 0;
  }
  else
  {
    v3 = 1;
    v2 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD))Parameter)(
           Parameter + 8,
           *((_QWORD *)Parameter + 4),
           *((_QWORD *)Parameter + 5));
  }
  v4 = (struct IUnknown *)*((_QWORD *)Parameter + 5);
  if ( v4 )
    ReleaseObj(v4);
  v5 = (HMODULE)*((_QWORD *)Parameter + 6);
  *((_QWORD *)Parameter + 6) = 0;
  std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>((__int64)(Parameter + 8));
  operator delete(Parameter);
  if ( v3 )
    CoUninitialize();
  ReleaseObj(v7);
  if ( v5 )
    FreeLibraryAndExitThread(v5, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800448b0  mov     rax, rsp
0x1800448b3  mov     [rax+10h], rbx
0x1800448b7  mov     [rax+18h], rbp
0x1800448bb  push    rsi
0x1800448bc  push    rdi
0x1800448bd  push    r14
0x1800448bf  sub     rsp, 20h
0x1800448c3  mov     rbx, rcx
0x1800448c6  mov     qword ptr [rax+8], 0
0x1800448ce  lea     rcx, [rax+8]; ppunk
0x1800448d2  call    cs:__imp_SHGetInstanceExplorer
0x1800448d8  test    eax, eax
0x1800448da  jns     short loc_1800448E5
0x1800448dc  mov     [rsp+38h+arg_0], 0
0x1800448e5  mov     edx, 6; dwCoInit
0x1800448ea  xor     ecx, ecx; pvReserved
0x1800448ec  call    cs:__imp_CoInitializeEx
0x1800448f2  mov     edi, eax
0x1800448f4  test    eax, eax
0x1800448f6  js      short loc_180044915
0x1800448f8  mov     r8, [rbx+28h]
0x1800448fc  lea     rcx, [rbx+8]
0x180044900  mov     rdx, [rbx+20h]
0x180044904  mov     ebp, 1
0x180044909  mov     rax, [rbx]
0x18004490c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044911  mov     edi, eax
0x180044913  jmp     short loc_180044917
0x180044915  xor     ebp, ebp
0x180044917  mov     rcx, [rbx+28h]; struct IUnknown *
0x18004491b  test    rcx, rcx
0x18004491e  jz      short loc_180044925
0x180044920  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180044925  mov     rsi, [rbx+30h]
0x180044929  lea     rcx, [rbx+8]
0x18004492d  mov     qword ptr [rbx+30h], 0
0x180044935  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x18004493a  mov     edx, 38h ; '8'; unsigned __int64
0x18004493f  mov     rcx, rbx; void *
0x180044942  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044947  test    ebp, ebp
0x180044949  jz      short loc_180044951
0x18004494b  call    cs:__imp_CoUninitialize
0x180044951  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180044956  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004495b  test    rsi, rsi
0x18004495e  jz      short loc_18004496C
0x180044960  mov     edx, edi; dwExitCode
0x180044962  mov     rcx, rsi; hLibModule
0x180044965  call    cs:__imp_FreeLibraryAndExitThread
0x18004496b  int     3; Trap to Debugger
0x18004496c  mov     rbx, [rsp+38h+arg_8]
0x180044971  mov     eax, edi
0x180044973  mov     rbp, [rsp+38h+arg_10]
0x180044978  add     rsp, 20h
0x18004497c  pop     r14
0x18004497e  pop     rdi
0x18004497f  pop     rsi
0x180044980  retn
```
