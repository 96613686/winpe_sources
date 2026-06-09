# DiagThreadFunc(void *)

- ea: `0x14002ffc0`
- end: `0x1400300ca`
- name: `?DiagThreadFunc@@YAKPEAX@Z`
- size: `266`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400187cc`
- `0x14002ffc0`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400300b5`
- `KERNEL32!SetEvent` at `0x1400300b5`
- `NDFAPI!NdfCloseIncident` at `0x140030088`
- `NDFAPI!NdfCloseIncident` at `0x140030088`
- `NDFAPI!NdfExecuteDiagnosis` at `0x14003005a`
- `NDFAPI!NdfExecuteDiagnosis` at `0x14003005a`
- `NDFAPI!NdfCreateIncident` at `0x140030018`
- `NDFAPI!NdfCreateIncident` at `0x140030018`

## string_xrefs

- `0x14002ffd7`: `DiagThreadFunc`
- `0x140030033`: `DiagThreadFunc`

## pseudocode

```c
__int64 __fastcall DiagThreadFunc(PVOID Parameter)
{
  HRESULT v2; // eax
  CEventLogger *v3; // rcx
  HRESULT v4; // eax
  HRESULT v5; // eax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  NDFHANDLE handle; // [rsp+40h] [rbp+8h] BYREF

  handle = 0;
  if ( Parameter )
  {
    v2 = NdfCreateIncident(
           L"RAHelperClass",
           *((_DWORD *)Parameter + 22),
           *((HELPER_ATTRIBUTE **)Parameter + 10),
           &handle);
    if ( v2 >= 0 )
    {
      v4 = NdfExecuteDiagnosis(handle, 0);
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
          (const char *)(unsigned int)v4,
          v7);
      v5 = NdfCloseIncident(handle);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
          (const char *)(unsigned int)v5,
          v7);
    }
    else
    {
      CEventLogger::LogError(
        v3,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        0xE1u,
        L"DiagThreadFunc",
        v2);
    }
    SetEvent(*((HANDLE *)Parameter + 4));
  }
  else
  {
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0xDBu,
      L"DiagThreadFunc",
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x14002ffc0  push    rbx
0x14002ffc2  sub     rsp, 30h
0x14002ffc6  mov     [rsp+38h+handle], 0
0x14002ffcf  mov     rbx, rcx
0x14002ffd2  test    rcx, rcx
0x14002ffd5  jnz     short loc_140030005
0x14002ffd7  lea     rax, aDiagthreadfunc; "DiagThreadFunc"
0x14002ffde  mov     [rsp+38h+var_10], ecx; unsigned int
0x14002ffe2  mov     r9d, 0DBh; unsigned int
0x14002ffe8  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x14002ffed  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14002fff4  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002fffb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030000  jmp     loc_1400300C1
0x140030005  mov     r8, [rcx+50h]; attributes
0x140030009  lea     r9, [rsp+38h+handle]; handle
0x14003000e  mov     edx, [rcx+58h]; celt
0x140030011  lea     rcx, helperClassName; "RAHelperClass"
0x140030018  call    cs:__imp_NdfCreateIncident
0x14003001f  nop     dword ptr [rax+rax+00h]
0x140030024  test    eax, eax
0x140030026  jns     short loc_140030053
0x140030028  mov     [rsp+38h+var_10], eax; unsigned int
0x14003002c  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030033  lea     rax, aDiagthreadfunc; "DiagThreadFunc"
0x14003003a  mov     r9d, 0E1h; unsigned int
0x140030040  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030047  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x14003004c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030051  jmp     short loc_1400300B1
0x140030053  mov     rcx, [rsp+38h+handle]; handle
0x140030058  xor     edx, edx; hwnd
0x14003005a  call    cs:__imp_NdfExecuteDiagnosis
0x140030061  nop     dword ptr [rax+rax+00h]
0x140030066  test    eax, eax
0x140030068  jns     short loc_140030083
0x14003006a  mov     rcx, [rsp+38h]; this
0x14003006f  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030076  mov     r9d, eax; char *
0x140030079  mov     edx, 0EEh; void *
0x14003007e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140030083  mov     rcx, [rsp+38h+handle]; handle
0x140030088  call    cs:__imp_NdfCloseIncident
0x14003008f  nop     dword ptr [rax+rax+00h]
0x140030094  test    eax, eax
0x140030096  jns     short loc_1400300B1
0x140030098  mov     rcx, [rsp+38h]; this
0x14003009d  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x1400300a4  mov     r9d, eax; char *
0x1400300a7  mov     edx, 0F2h; void *
0x1400300ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400300b1  mov     rcx, [rbx+20h]; hEvent
0x1400300b5  call    cs:__imp_SetEvent
0x1400300bc  nop     dword ptr [rax+rax+00h]
0x1400300c1  xor     eax, eax
0x1400300c3  add     rsp, 30h
0x1400300c7  pop     rbx
0x1400300c8  retn
```
