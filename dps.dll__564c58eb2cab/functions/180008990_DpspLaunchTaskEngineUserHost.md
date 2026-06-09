# DpspLaunchTaskEngineUserHost

- ea: `0x180008990`
- end: `0x180008aaf`
- name: `DpspLaunchTaskEngineUserHost`
- size: `287`
- prototype: `__int64 __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b484`

## callees

- `0x180008990`
- `0x180009090`
- `0x180016bd4`
- `0x180016c7c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008a04`
- `OLEAUT32!__imp_SysAllocString` at `0x180008a04`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a88`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a88`

## string_xrefs

- `0x1800089cd`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180008a79`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x1800089c6`: `DpspLaunchTaskEngineUserHost`
- `0x180008a72`: `DpspLaunchTaskEngineUserHost`

## pseudocode

```c
__int64 __fastcall DpspLaunchTaskEngineUserHost(unsigned int a1, void *a2)
{
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rax
  OLECHAR *v6; // rdi
  int Args; // eax
  int v8; // eax
  struct IRegisteredTask *v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  if ( a2 )
  {
    if ( g_pTaskService )
    {
      v5 = SysAllocString(L"ResolutionHost");
      v6 = v5;
      if ( v5 )
      {
        Args = DpspGetRegisteredTask(v5, &v10);
        v4 = Args;
        if ( Args >= 0 )
        {
          v8 = DpspRunTask(v10, a1, a2);
          v4 = v8;
          if ( v8 < 0 )
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
              (int)L"DpspLaunchTaskEngineUserHost",
              419,
              (int)L"Error = %d",
              v8);
        }
        else
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
            (int)L"DpspLaunchTaskEngineUserHost",
            413,
            (int)L"Error = %d",
            Args);
        }
        SysFreeString(v6);
      }
      else
      {
        v4 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
          (int)L"DpspLaunchTaskEngineUserHost",
          408,
          (int)L"Error = %d",
          14);
      }
    }
    else
    {
      v4 = -2147467259;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (int)L"DpspLaunchTaskEngineUserHost",
        405,
        (int)L"Error = %d",
        5);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (int)L"DpspLaunchTaskEngineUserHost",
      403,
      (int)L"Error = %d",
      87);
  }
  if ( v10 )
    ((void (__fastcall *)(struct IRegisteredTask *))v10->lpVtbl->Release)(v10);
  return v4;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  push    rbp
0x180008993  push    rsi
0x180008994  push    rdi
0x180008995  sub     rsp, 38h
0x180008999  mov     [rsp+58h+arg_8], 0
0x1800089a2  mov     rsi, rdx
0x1800089a5  mov     ebp, ecx
0x1800089a7  test    rdx, rdx
0x1800089aa  jnz     short loc_1800089DE
0x1800089ac  mov     ebx, 80070057h
0x1800089b1  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800089b9  mov     r8d, 193h; int
0x1800089bf  lea     r9, aErrorD; "Error = %d"
0x1800089c6  lea     rdx, aDpsplaunchtask; "DpspLaunchTaskEngineUserHost"
0x1800089cd  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800089d4  call    WdipTraceError
0x1800089d9  jmp     loc_180008A8E
0x1800089de  cmp     cs:g_pTaskService, 0
0x1800089e6  jnz     short loc_1800089FD
0x1800089e8  mov     ebx, 80004005h
0x1800089ed  mov     dword ptr [rsp+58h+Args], 4005h
0x1800089f5  mov     r8d, 195h
0x1800089fb  jmp     short loc_1800089BF
0x1800089fd  lea     rcx, psz; "ResolutionHost"
0x180008a04  call    cs:__imp_SysAllocString
0x180008a0a  mov     rdi, rax
0x180008a0d  test    rax, rax
0x180008a10  jnz     short loc_180008A27
0x180008a12  mov     ebx, 8007000Eh
0x180008a17  mov     dword ptr [rsp+58h+Args], 0Eh
0x180008a1f  mov     r8d, 198h
0x180008a25  jmp     short loc_1800089BF
0x180008a27  lea     rdx, [rsp+58h+arg_8]; struct IRegisteredTask **
0x180008a2c  mov     rcx, rdi; unsigned __int16 *
0x180008a2f  call    ?DpspGetRegisteredTask@@YAJPEAGPEAPEAUIRegisteredTask@@@Z; DpspGetRegisteredTask(ushort *,IRegisteredTask * *)
0x180008a34  mov     ebx, eax
0x180008a36  test    eax, eax
0x180008a38  jns     short loc_180008A49
0x180008a3a  movzx   ecx, ax
0x180008a3d  mov     r8d, 19Dh
0x180008a43  mov     dword ptr [rsp+58h+Args], ecx
0x180008a47  jmp     short loc_180008A6B
0x180008a49  mov     rcx, [rsp+58h+arg_8]; struct IRegisteredTask *
0x180008a4e  mov     r8, rsi; void *
0x180008a51  mov     edx, ebp; unsigned int
0x180008a53  call    ?DpspRunTask@@YAJPEAUIRegisteredTask@@KPEAX@Z; DpspRunTask(IRegisteredTask *,ulong,void *)
0x180008a58  mov     ebx, eax
0x180008a5a  test    eax, eax
0x180008a5c  jns     short loc_180008A85
0x180008a5e  movzx   eax, ax
0x180008a61  mov     r8d, 1A3h; int
0x180008a67  mov     dword ptr [rsp+58h+Args], eax; Args
0x180008a6b  lea     r9, aErrorD; "Error = %d"
0x180008a72  lea     rdx, aDpsplaunchtask; "DpspLaunchTaskEngineUserHost"
0x180008a79  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008a80  call    WdipTraceError
0x180008a85  mov     rcx, rdi; bstrString
0x180008a88  call    cs:__imp_SysFreeString
0x180008a8e  mov     rcx, [rsp+58h+arg_8]
0x180008a93  test    rcx, rcx
0x180008a96  jz      short loc_180008AA4
0x180008a98  mov     rax, [rcx]
0x180008a9b  mov     rax, [rax+10h]
0x180008a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa4  mov     eax, ebx
0x180008aa6  add     rsp, 38h
0x180008aaa  pop     rdi
0x180008aab  pop     rsi
0x180008aac  pop     rbp
0x180008aad  pop     rbx
0x180008aae  retn
```
