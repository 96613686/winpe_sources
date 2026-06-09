# AERegisterSysTrayApp(uint)

- ea: `0x180006604`
- end: `0x1800066ac`
- name: `?AERegisterSysTrayApp@@YAHI@Z`
- size: `168`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001d90`
- `0x180006974`

## callees

- `0x1800065d8`
- `0x180006604`
- `0x180006f94`
- `0x180007798`
- `0x1800077c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006649`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006649`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180006622`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180006622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006652`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006652`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006635`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006635`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000669b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000669b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000665f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000665f`

## string_xrefs

- `0x180006614`: `Local\ShellReadyEvent`

## pseudocode

```c
__int64 __fastcall AERegisterSysTrayApp(unsigned int a1)
{
  unsigned int v1; // edi
  int v3; // ebx
  HANDLE v4; // rax
  void *v5; // rsi
  unsigned __int64 v6; // rcx
  CQueryContinue *v7; // rax
  CQueryContinue *v8; // rax
  CQueryContinue *v9; // rbx

  v1 = 0;
  v3 = 30;
  while ( 1 )
  {
    v4 = OpenEventW(0x100000u, 0, L"Local\\ShellReadyEvent");
    v5 = v4;
    if ( v4 )
      break;
    Sleep(0x2710u);
    if ( --v3 <= 0 )
      return v1;
  }
  WaitForSingleObject(v4, 0xFFFFFFFF);
  CloseHandle(v5);
  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v7 = (CQueryContinue *)operator new(v6);
    if ( v7 )
    {
      v8 = CQueryContinue::CQueryContinue(v7);
      v9 = v8;
      if ( v8 )
      {
        LOBYTE(v1) = (unsigned int)CQueryContinue::DoBalloon(v8, a1) == 0;
        operator delete(v9);
      }
    }
    CoUninitialize();
  }
  return v1;
}

```

## disassembly

```asm
0x180006604  push    rbx
0x180006606  push    rbp
0x180006607  push    rsi
0x180006608  push    rdi
0x180006609  sub     rsp, 28h
0x18000660d  xor     edi, edi
0x18000660f  mov     ebp, ecx
0x180006611  lea     ebx, [rdi+1Eh]
0x180006614  lea     r8, Name; "Local\\ShellReadyEvent"
0x18000661b  xor     edx, edx; bInheritHandle
0x18000661d  mov     ecx, 100000h; dwDesiredAccess
0x180006622  call    cs:__imp_OpenEventW
0x180006628  mov     rsi, rax
0x18000662b  test    rax, rax
0x18000662e  jnz     short loc_180006643
0x180006630  mov     ecx, 2710h; dwMilliseconds
0x180006635  call    cs:__imp_Sleep
0x18000663b  dec     ebx
0x18000663d  test    ebx, ebx
0x18000663f  jg      short loc_180006614
0x180006641  jmp     short loc_1800066A1
0x180006643  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006646  mov     rcx, rsi; hHandle
0x180006649  call    cs:__imp_WaitForSingleObject
0x18000664f  mov     rcx, rsi; hObject
0x180006652  call    cs:__imp_CloseHandle
0x180006658  mov     edx, 2; dwCoInit
0x18000665d  xor     ecx, ecx; pvReserved
0x18000665f  call    cs:__imp_CoInitializeEx
0x180006665  test    eax, eax
0x180006667  js      short loc_1800066A1
0x180006669  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000666e  test    rax, rax
0x180006671  jz      short loc_18000669B
0x180006673  mov     rcx, rax; this
0x180006676  call    ??0CQueryContinue@@QEAA@XZ; CQueryContinue::CQueryContinue(void)
0x18000667b  mov     rbx, rax
0x18000667e  test    rax, rax
0x180006681  jz      short loc_18000669B
0x180006683  mov     edx, ebp; unsigned int
0x180006685  mov     rcx, rax; this
0x180006688  call    ?DoBalloon@CQueryContinue@@QEAAJI@Z; CQueryContinue::DoBalloon(uint)
0x18000668d  test    eax, eax
0x18000668f  mov     rcx, rbx; void *
0x180006692  setz    dil
0x180006696  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000669b  call    cs:__imp_CoUninitialize
0x1800066a1  mov     eax, edi
0x1800066a3  add     rsp, 28h
0x1800066a7  pop     rdi
0x1800066a8  pop     rsi
0x1800066a9  pop     rbp
0x1800066aa  pop     rbx
0x1800066ab  retn
```
