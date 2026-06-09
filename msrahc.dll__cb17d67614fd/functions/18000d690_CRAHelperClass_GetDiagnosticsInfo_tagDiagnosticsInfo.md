# CRAHelperClass::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x18000d690`
- end: `0x18000d729`
- name: `?GetDiagnosticsInfo@CRAHelperClass@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CRAHelperClass *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d690`
- `0x180014660`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d6d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d6d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRAHelperClass::GetDiagnosticsInfo(CRAHelperClass *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v4; // rax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  unsigned int v7; // ebx

  if ( a2 )
  {
    *a2 = 0;
    v4 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
    if ( v4 )
    {
      v4->cost = 600;
      v4->flags = 0x80000000;
      *a2 = v4;
      return 0;
    }
    else
    {
      v7 = -2147024882;
      CEventLogger::LogError(
        v6,
        v5,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        0x36Du,
        L"CRAHelperClass::GetDiagnosticsInfo",
        0x8007000E);
    }
    return v7;
  }
  else
  {
    CEventLogger::LogError(
      this,
      0,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x364u,
      L"CRAHelperClass::GetDiagnosticsInfo",
      0x80070057);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000d690  push    rbx
0x18000d692  sub     rsp, 30h
0x18000d696  mov     rbx, rdx
0x18000d699  test    rdx, rdx
0x18000d69c  jnz     short loc_18000D6CB
0x18000d69e  lea     rax, aCrahelperclass_10; "CRAHelperClass::GetDiagnosticsInfo"
0x18000d6a5  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x18000d6ad  mov     r9d, 364h; unsigned int
0x18000d6b3  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000d6b8  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000d6bf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000d6c4  mov     eax, 80070057h
0x18000d6c9  jmp     short loc_18000D723
0x18000d6cb  mov     ecx, 8; cb
0x18000d6d0  mov     qword ptr [rdx], 0
0x18000d6d7  call    cs:__imp_CoTaskMemAlloc
0x18000d6dd  test    rax, rax
0x18000d6e0  jnz     short loc_18000D70F
0x18000d6e2  lea     rax, aCrahelperclass_10; "CRAHelperClass::GetDiagnosticsInfo"
0x18000d6e9  mov     [rsp+38h+var_10], 8007000Eh; unsigned int
0x18000d6f1  mov     r9d, 36Dh; unsigned int
0x18000d6f7  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000d6fc  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000d703  mov     ebx, 8007000Eh
0x18000d708  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000d70d  jmp     short loc_18000D721
0x18000d70f  mov     dword ptr [rax], 258h
0x18000d715  mov     dword ptr [rax+4], 80000000h
0x18000d71c  mov     [rbx], rax
0x18000d71f  xor     ebx, ebx
0x18000d721  mov     eax, ebx
0x18000d723  add     rsp, 30h
0x18000d727  pop     rbx
0x18000d728  retn
```
