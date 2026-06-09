# AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)

- ea: `0x18001d30c`
- end: `0x18001d47c`
- name: `?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cf04`
- `0x180020418`

## callees

- `0x180013d4c`
- `0x18001d30c`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d3f2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001d3f2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d435`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d435`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d403`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d403`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d428`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d428`

## pseudocode

```c
__int64 __fastcall AddTaskWNFTrigger(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rax
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  SAFEARRAY *v11; // rax
  SAFEARRAY *v12; // rbx
  HRESULT v13; // eax
  unsigned int v14; // edi
  __int64 v15; // [rsp+40h] [rbp+20h] BYREF
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+38h] BYREF

  v2 = *a1;
  v16 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v2 + 80))(a1, 12, &v16);
  v5 = v16;
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( !v16 )
      return v6;
LABEL_3:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v5);
    return v6;
  }
  v15 = 0;
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IWnfStateChangeTrigger, &v15);
  v9 = v15;
  v6 = v8;
  if ( v8 < 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 152LL))(v15, 0xFFFFFFFFLL),
        v9 = v15,
        v6 = v10,
        v10 < 0) )
  {
LABEL_6:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v5 = v16;
    if ( !v16 )
      return v6;
    goto LABEL_3;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 184LL))(v15, *a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    v9 = v15;
    goto LABEL_6;
  }
  rgsabound = 0;
  v11 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
LABEL_23:
    ATL::AtlThrowImpl(v13);
  }
  v13 = SafeArrayLock(v11);
  if ( v13 < 0 )
    goto LABEL_23;
  v14 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v15 + 200LL))(v15, v12);
  if ( SafeArrayUnlock(v12) >= 0 )
    SafeArrayDestroy(v12);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v14;
}

```

## disassembly

```asm
0x18001d30c  push    rbp
0x18001d30e  push    rbx
0x18001d30f  push    rdi
0x18001d310  mov     rbp, rsp
0x18001d313  sub     rsp, 20h
0x18001d317  mov     rax, [rcx]
0x18001d31a  lea     r8, [rbp+arg_10]
0x18001d31e  mov     rdi, rdx
0x18001d321  mov     [rbp+arg_10], 0
0x18001d329  mov     edx, 0Ch
0x18001d32e  mov     rax, [rax+50h]
0x18001d332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d337  mov     rcx, [rbp+arg_10]
0x18001d33b  mov     ebx, eax
0x18001d33d  test    eax, eax
0x18001d33f  jns     short loc_18001D359
0x18001d341  test    rcx, rcx
0x18001d344  jz      short loc_18001D352
0x18001d346  mov     rdx, [rcx]
0x18001d349  mov     rax, [rdx+10h]
0x18001d34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d352  mov     eax, ebx
0x18001d354  jmp     loc_18001D467
0x18001d359  mov     [rbp+arg_0], 0
0x18001d361  lea     r8, [rbp+arg_0]
0x18001d365  mov     rax, [rcx]
0x18001d368  lea     rdx, IID_IWnfStateChangeTrigger
0x18001d36f  mov     rax, [rax]
0x18001d372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d377  mov     rcx, [rbp+arg_0]
0x18001d37b  mov     ebx, eax
0x18001d37d  test    eax, eax
0x18001d37f  jns     short loc_18001D3A4
0x18001d381  test    rcx, rcx
0x18001d384  jz      short loc_18001D392
0x18001d386  mov     rdx, [rcx]
0x18001d389  mov     rax, [rdx+10h]
0x18001d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d392  mov     rcx, [rbp+arg_10]
0x18001d396  test    rcx, rcx
0x18001d399  jz      short loc_18001D352
0x18001d39b  mov     rax, [rcx]
0x18001d39e  mov     rax, [rax+10h]
0x18001d3a2  jmp     short loc_18001D34D
0x18001d3a4  mov     rax, [rcx]
0x18001d3a7  or      edx, 0FFFFFFFFh
0x18001d3aa  mov     rax, [rax+98h]
0x18001d3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3b6  mov     rcx, [rbp+arg_0]
0x18001d3ba  mov     ebx, eax
0x18001d3bc  test    eax, eax
0x18001d3be  js      short loc_18001D381
0x18001d3c0  mov     rax, [rcx]
0x18001d3c3  mov     rdx, [rdi]
0x18001d3c6  mov     rax, [rax+0B8h]
0x18001d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d2  mov     ebx, eax
0x18001d3d4  test    eax, eax
0x18001d3d6  jns     short loc_18001D3DE
0x18001d3d8  mov     rcx, [rbp+arg_0]
0x18001d3dc  jmp     short loc_18001D381
0x18001d3de  mov     ecx, 11h; vt
0x18001d3e3  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18001d3eb  lea     r8, [rbp+rgsabound]; rgsabound
0x18001d3ef  lea     edx, [rcx-10h]; cDims
0x18001d3f2  call    cs:__imp_SafeArrayCreate
0x18001d3f8  mov     rbx, rax
0x18001d3fb  test    rax, rax
0x18001d3fe  jz      short loc_18001D46F
0x18001d400  mov     rcx, rbx; psa
0x18001d403  call    cs:__imp_SafeArrayLock
0x18001d409  test    eax, eax
0x18001d40b  js      short loc_18001D474
0x18001d40d  mov     rcx, [rbp+arg_0]
0x18001d411  mov     rdx, rbx
0x18001d414  mov     rax, [rcx]
0x18001d417  mov     rax, [rax+0C8h]
0x18001d41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d423  mov     rcx, rbx; psa
0x18001d426  mov     edi, eax
0x18001d428  call    cs:__imp_SafeArrayUnlock
0x18001d42e  test    eax, eax
0x18001d430  js      short loc_18001D43B
0x18001d432  mov     rcx, rbx; psa
0x18001d435  call    cs:__imp_SafeArrayDestroy
0x18001d43b  mov     rcx, [rbp+arg_0]
0x18001d43f  test    rcx, rcx
0x18001d442  jz      short loc_18001D450
0x18001d444  mov     rax, [rcx]
0x18001d447  mov     rax, [rax+10h]
0x18001d44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d450  mov     rcx, [rbp+arg_10]
0x18001d454  test    rcx, rcx
0x18001d457  jz      short loc_18001D465
0x18001d459  mov     rax, [rcx]
0x18001d45c  mov     rax, [rax+10h]
0x18001d460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d465  mov     eax, edi
0x18001d467  add     rsp, 20h
0x18001d46b  pop     rdi
0x18001d46c  pop     rbx
0x18001d46d  pop     rbp
0x18001d46e  retn
0x18001d46f  mov     eax, 8007000Eh
0x18001d474  mov     ecx, eax; int
0x18001d476  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
