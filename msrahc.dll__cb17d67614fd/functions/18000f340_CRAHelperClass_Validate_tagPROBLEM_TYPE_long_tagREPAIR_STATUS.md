# CRAHelperClass::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x18000f340`
- end: `0x18000f418`
- name: `?Validate@CRAHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f340`
- `0x180014660`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f405`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRAHelperClass::Validate(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 v6; // rax
  signed int v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // edi
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  if ( a4 )
  {
    *a4 = RS_DEFERRED;
    v6 = *(_QWORD *)this;
    v12 = 0;
    pv[0] = 0;
    v7 = (*(__int64 (__fastcall **)(CRAHelperClass *, const wchar_t *, LPVOID *, int *, int *))(v6 + 48))(
           this,
           L"Validation",
           pv,
           a3,
           &v12);
    v10 = v7;
    if ( v7 >= 0 )
      *a4 = 2 - (((v12 - 1) & 0xFFFFFFFD) != 0);
    else
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x609u,
        L"CRAHelperClass::Validate",
        v7);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v10;
  }
  else
  {
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x5FAu,
      L"CRAHelperClass::Validate",
      0x80070057);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000f340  mov     [rsp+arg_0], rbx
0x18000f345  push    rdi
0x18000f346  sub     rsp, 40h
0x18000f34a  mov     rbx, r9
0x18000f34d  test    r9, r9
0x18000f350  jnz     short loc_18000F382
0x18000f352  lea     rax, aCrahelperclass_2; "CRAHelperClass::Validate"
0x18000f359  mov     [rsp+48h+var_20], 80070057h; unsigned int
0x18000f361  mov     r9d, 5FAh; unsigned int
0x18000f367  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18000f36c  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000f373  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000f378  mov     eax, 80070057h
0x18000f37d  jmp     loc_18000F40D
0x18000f382  mov     dword ptr [r9], 3
0x18000f389  lea     rdx, [rsp+48h+arg_18]
0x18000f38e  mov     rax, [rcx]
0x18000f391  mov     r9, r8
0x18000f394  mov     [rsp+48h+var_28], rdx
0x18000f399  lea     r8, [rsp+48h+pv]
0x18000f39e  lea     rdx, aValidation; "Validation"
0x18000f3a5  mov     [rsp+48h+arg_18], 0
0x18000f3ad  mov     [rsp+48h+pv], 0
0x18000f3b6  mov     rax, [rax+30h]
0x18000f3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3bf  mov     edi, eax
0x18000f3c1  test    eax, eax
0x18000f3c3  jns     short loc_18000F3E9
0x18000f3c5  mov     [rsp+48h+var_20], eax; unsigned int
0x18000f3c9  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000f3d0  lea     rax, aCrahelperclass_2; "CRAHelperClass::Validate"
0x18000f3d7  mov     r9d, 609h; unsigned int
0x18000f3dd  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18000f3e2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000f3e7  jmp     short loc_18000F3FB
0x18000f3e9  mov     eax, [rsp+48h+arg_18]
0x18000f3ed  dec     eax
0x18000f3ef  and     eax, 0FFFFFFFDh
0x18000f3f2  neg     eax
0x18000f3f4  sbb     eax, eax
0x18000f3f6  add     eax, 2
0x18000f3f9  mov     [rbx], eax
0x18000f3fb  mov     rcx, [rsp+48h+pv]; pv
0x18000f400  test    rcx, rcx
0x18000f403  jz      short loc_18000F40B
0x18000f405  call    cs:__imp_CoTaskMemFree
0x18000f40b  mov     eax, edi
0x18000f40d  mov     rbx, [rsp+48h+arg_0]
0x18000f412  add     rsp, 40h
0x18000f416  pop     rdi
0x18000f417  retn
```
