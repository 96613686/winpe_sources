# PerfDiagDm::InitializeDirectUI(void)

- ea: `0x1800be3fc`
- end: `0x1800be49a`
- name: `?InitializeDirectUI@PerfDiagDm@@YAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(PerfDiagDm *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800beef4`

## callees

- `0x1800be3fc`
- `0x1800bf624`

## import_xrefs

- `ole32!CoInitializeEx` at `0x1800be412`
- `ole32!CoInitializeEx` at `0x1800be412`
- `ole32!CoUninitialize` at `0x1800be488`
- `ole32!CoUninitialize` at `0x1800be488`
- `DUI70!InitProcessPriv` at `0x1800be435`
- `DUI70!InitProcessPriv` at `0x1800be435`
- `DUI70!UnInitProcessPriv` at `0x1800be482`
- `DUI70!UnInitProcessPriv` at `0x1800be482`
- `DUI70!InitThread` at `0x1800be446`
- `DUI70!InitThread` at `0x1800be446`
- `DUI70!UnInitThread` at `0x1800be475`
- `DUI70!UnInitThread` at `0x1800be475`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::InitializeDirectUI(PerfDiagDm *this)
{
  HRESULT inited; // ebx
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  inited = CoInitializeEx(0, 2u);
  if ( inited >= 0 )
  {
    LOBYTE(v2) = 1;
    inited = InitProcessPriv(14, &_ImageBase, v2);
    if ( inited >= 0 )
    {
      inited = InitThread(2, v3, v4);
      if ( inited >= 0 )
      {
        v6 = 0x400000000008LL;
        if ( (unsigned int)IsolationAwareInitCommonControlsEx(&v6) )
          return 0;
        inited = -2147467259;
        UnInitThread();
      }
      UnInitProcessPriv(&_ImageBase);
    }
    CoUninitialize();
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800be3fc  push    rbx
0x1800be3fe  sub     rsp, 30h
0x1800be402  mov     edx, 2; dwCoInit
0x1800be407  mov     [rsp+38h+arg_0], 0
0x1800be410  xor     ecx, ecx; pvReserved
0x1800be412  call    cs:__imp_CoInitializeEx
0x1800be418  mov     ebx, eax
0x1800be41a  test    eax, eax
0x1800be41c  js      short loc_1800BE48E
0x1800be41e  mov     r9b, 1
0x1800be421  mov     [rsp+38h+var_18], 1
0x1800be426  mov     r8b, r9b
0x1800be429  lea     rdx, __ImageBase
0x1800be430  mov     ecx, 0Eh
0x1800be435  call    cs:__imp_InitProcessPriv
0x1800be43b  mov     ebx, eax
0x1800be43d  test    eax, eax
0x1800be43f  js      short loc_1800BE488
0x1800be441  mov     ecx, 2
0x1800be446  call    cs:__imp_InitThread
0x1800be44c  mov     ebx, eax
0x1800be44e  test    eax, eax
0x1800be450  js      short loc_1800BE47B
0x1800be452  lea     rcx, [rsp+38h+arg_0]
0x1800be457  mov     dword ptr [rsp+38h+arg_0], 8
0x1800be45f  mov     dword ptr [rsp+38h+arg_0+4], 4000h
0x1800be467  call    IsolationAwareInitCommonControlsEx
0x1800be46c  test    eax, eax
0x1800be46e  jnz     short loc_1800BE496
0x1800be470  mov     ebx, 80004005h
0x1800be475  call    cs:__imp_UnInitThread
0x1800be47b  lea     rcx, __ImageBase
0x1800be482  call    cs:__imp_UnInitProcessPriv
0x1800be488  call    cs:__imp_CoUninitialize
0x1800be48e  mov     eax, ebx
0x1800be490  add     rsp, 30h
0x1800be494  pop     rbx
0x1800be495  retn
0x1800be496  xor     ebx, ebx
0x1800be498  jmp     short loc_1800BE48E
```
