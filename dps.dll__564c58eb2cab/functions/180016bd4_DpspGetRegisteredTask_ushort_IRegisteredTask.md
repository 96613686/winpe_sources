# DpspGetRegisteredTask(ushort *,IRegisteredTask * *)

- ea: `0x180016bd4`
- end: `0x180016c76`
- name: `?DpspGetRegisteredTask@@YAJPEAGPEAPEAUIRegisteredTask@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180008990`

## callees

- `0x180009090`
- `0x180016bd4`
- `0x180016da4`
- `0x180019010`

## string_xrefs

- `0x180016c58`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180016c51`: `DpspGetRegisteredTask`

## pseudocode

```c
__int64 __fastcall DpspGetRegisteredTask(unsigned __int16 *a1, struct IRegisteredTask **a2)
{
  int Args; // eax
  unsigned int v5; // ebx
  int v6; // eax

  Args = DpspVerifyTaskFolder();
  v5 = Args;
  if ( Args >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IRegisteredTask **))(*(_QWORD *)g_pTaskFolder
                                                                                           + 104LL))(
           g_pTaskFolder,
           a1,
           a2);
    v5 = v6;
    if ( v6 >= 0 )
    {
      if ( !*a2 )
      {
        v5 = -2147467259;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
          (int)L"DpspGetRegisteredTask",
          302,
          (int)L"Error = %d",
          5);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (int)L"DpspGetRegisteredTask",
        300,
        (int)L"Error = %d",
        v6);
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (int)L"DpspGetRegisteredTask",
      294,
      (int)L"Error = %d",
      Args);
  }
  return v5;
}

```

## disassembly

```asm
0x180016bd4  mov     [rsp+arg_0], rbx
0x180016bd9  mov     [rsp+arg_8], rsi
0x180016bde  push    rdi
0x180016bdf  sub     rsp, 30h
0x180016be3  mov     rdi, rdx
0x180016be6  mov     rsi, rcx
0x180016be9  call    ?DpspVerifyTaskFolder@@YAJXZ; DpspVerifyTaskFolder(void)
0x180016bee  mov     ebx, eax
0x180016bf0  test    eax, eax
0x180016bf2  jns     short loc_180016C03
0x180016bf4  movzx   ecx, ax
0x180016bf7  mov     r8d, 126h
0x180016bfd  mov     dword ptr [rsp+38h+Args], ecx
0x180016c01  jmp     short loc_180016C4A
0x180016c03  mov     rcx, cs:g_pTaskFolder
0x180016c0a  mov     r8, rdi
0x180016c0d  mov     rdx, rsi
0x180016c10  mov     rax, [rcx]
0x180016c13  mov     rax, [rax+68h]
0x180016c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c1c  mov     ebx, eax
0x180016c1e  test    eax, eax
0x180016c20  jns     short loc_180016C31
0x180016c22  movzx   eax, ax
0x180016c25  mov     r8d, 12Ch
0x180016c2b  mov     dword ptr [rsp+38h+Args], eax
0x180016c2f  jmp     short loc_180016C4A
0x180016c31  cmp     qword ptr [rdi], 0
0x180016c35  jnz     short loc_180016C64
0x180016c37  mov     ebx, 80004005h
0x180016c3c  mov     dword ptr [rsp+38h+Args], 4005h; Args
0x180016c44  mov     r8d, 12Eh; int
0x180016c4a  lea     r9, aErrorD; "Error = %d"
0x180016c51  lea     rdx, aDpspgetregiste; "DpspGetRegisteredTask"
0x180016c58  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016c5f  call    WdipTraceError
0x180016c64  mov     rsi, [rsp+38h+arg_8]
0x180016c69  mov     eax, ebx
0x180016c6b  mov     rbx, [rsp+38h+arg_0]
0x180016c70  add     rsp, 30h
0x180016c74  pop     rdi
0x180016c75  retn
```
