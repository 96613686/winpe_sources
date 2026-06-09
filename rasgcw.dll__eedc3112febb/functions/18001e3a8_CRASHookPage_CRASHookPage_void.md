# CRASHookPage::~CRASHookPage(void)

- ea: `0x18001e3a8`
- end: `0x18001e4e6`
- name: `??1CRASHookPage@@QEAA@XZ`
- size: `318`
- prototype: `void __fastcall(CRASHookPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800050f0`

## callees

- `0x1800114d8`
- `0x18001e3a8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e4d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e4d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e4c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e4c6`
- `rtutils!TracePrintfExA` at `0x18001e482`
- `rtutils!TracePrintfExA` at `0x18001e482`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e446`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e446`

## pseudocode

```c
void __fastcall CRASHookPage::~CRASHookPage(CRASHookPage *this)
{
  _QWORD *v2; // rdi
  int v3; // eax
  __int64 v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CRASHookPage::`vftable';
  v2 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
  {
    if ( (int)HrEnsureTearOffInterfaceLoaded(*((_QWORD *)this + 3), &IID_IXWizardPropertyBag, (char *)this + 32) >= 0 )
      (*(void (__fastcall **)(_QWORD, char *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)*v2 + 56LL))(
        *v2,
        (char *)this + 8,
        L"RASConnectionDetails",
        0,
        0);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
  }
  if ( *((_DWORD *)this + 12) )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv) >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)this + 12));
      if ( v3 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::~CRASHookPage:RevokeInterfaceFromGlobal failed. hr = %#x", v3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    *((_DWORD *)this + 12) = 0;
  }
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 8) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
}

```

## disassembly

```asm
0x18001e3a8  mov     [rsp+arg_8], rbx
0x18001e3ad  push    rdi
0x18001e3ae  sub     rsp, 30h
0x18001e3b2  mov     rbx, rcx
0x18001e3b5  lea     rax, ??_7CRASHookPage@@6B@; const CRASHookPage::`vftable'
0x18001e3bc  mov     [rcx], rax
0x18001e3bf  lea     rdi, [rcx+20h]
0x18001e3c3  cmp     qword ptr [rdi], 0
0x18001e3c7  jz      short loc_18001E415
0x18001e3c9  mov     r8, rdi
0x18001e3cc  lea     rdx, IID_IXWizardPropertyBag
0x18001e3d3  mov     rcx, [rcx+18h]
0x18001e3d7  call    HrEnsureTearOffInterfaceLoaded
0x18001e3dc  test    eax, eax
0x18001e3de  js      short loc_18001E406
0x18001e3e0  mov     rcx, [rdi]
0x18001e3e3  mov     rax, [rcx]
0x18001e3e6  lea     rdx, [rbx+8]
0x18001e3ea  mov     [rsp+38h+ppv], 0
0x18001e3f3  xor     r9d, r9d
0x18001e3f6  lea     r8, aRasconnectiond_5; "RASConnectionDetails"
0x18001e3fd  mov     rax, [rax+38h]
0x18001e401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e406  mov     rcx, [rdi]
0x18001e409  mov     rax, [rcx]
0x18001e40c  mov     rax, [rax+10h]
0x18001e410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e415  cmp     dword ptr [rbx+30h], 0
0x18001e419  jz      loc_18001E4A0
0x18001e41f  mov     [rsp+38h+arg_0], 0
0x18001e428  lea     rax, [rsp+38h+arg_0]
0x18001e42d  mov     [rsp+38h+ppv], rax; ppv
0x18001e432  lea     r9, IID_IGlobalInterfaceTable; riid
0x18001e439  xor     edx, edx; pUnkOuter
0x18001e43b  lea     r8d, [rdx+1]; dwClsContext
0x18001e43f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001e446  call    cs:__imp_CoCreateInstance
0x18001e44c  test    eax, eax
0x18001e44e  js      short loc_18001E499
0x18001e450  mov     rcx, [rsp+38h+arg_0]
0x18001e455  mov     rax, [rcx]
0x18001e458  mov     edx, [rbx+30h]
0x18001e45b  mov     rax, [rax+20h]
0x18001e45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e464  test    eax, eax
0x18001e466  jns     short loc_18001E488
0x18001e468  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e46e  cmp     ecx, 0FFFFFFFFh
0x18001e471  jz      short loc_18001E488
0x18001e473  mov     r9d, eax
0x18001e476  lea     r8, aCrashookpageCr; "CRASHookPage::~CRASHookPage:RevokeInter"...
0x18001e47d  mov     edx, 0Ch; dwFlags
0x18001e482  call    cs:__imp_TracePrintfExA
0x18001e488  mov     rcx, [rsp+38h+arg_0]
0x18001e48d  mov     rax, [rcx]
0x18001e490  mov     rax, [rax+10h]
0x18001e494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e499  mov     dword ptr [rbx+30h], 0
0x18001e4a0  mov     rcx, [rbx+40h]
0x18001e4a4  test    rcx, rcx
0x18001e4a7  jz      short loc_18001E4BD
0x18001e4a9  mov     rax, [rcx]
0x18001e4ac  mov     rax, [rax+10h]
0x18001e4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4b5  mov     qword ptr [rbx+40h], 0
0x18001e4bd  mov     rbx, [rbx+38h]
0x18001e4c1  test    rbx, rbx
0x18001e4c4  jz      short loc_18001E4DB
0x18001e4c6  call    cs:__imp_GetProcessHeap
0x18001e4cc  mov     r8, rbx; lpMem
0x18001e4cf  xor     edx, edx; dwFlags
0x18001e4d1  mov     rcx, rax; hHeap
0x18001e4d4  call    cs:__imp_HeapFree
0x18001e4da  nop
0x18001e4db  mov     rbx, [rsp+38h+arg_8]
0x18001e4e0  add     rsp, 30h
0x18001e4e4  pop     rdi
0x18001e4e5  retn
```
