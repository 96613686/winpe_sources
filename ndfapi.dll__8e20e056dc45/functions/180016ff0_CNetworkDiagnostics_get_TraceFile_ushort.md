# CNetworkDiagnostics::get_TraceFile(ushort * *)

- ea: `0x180016ff0`
- end: `0x18001707e`
- name: `?get_TraceFile@CNetworkDiagnostics@@UEAAJPEAPEAG@Z`
- size: `142`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180016ff0`
- `0x18001b640`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001700f`
- `KERNEL32!EnterCriticalSection` at `0x18001700f`
- `KERNEL32!LeaveCriticalSection` at `0x180017066`
- `KERNEL32!LeaveCriticalSection` at `0x180017066`
- `ole32!CoTaskMemFree` at `0x18001705d`
- `ole32!CoTaskMemFree` at `0x18001705d`
- `OLEAUT32!__imp_SysAllocString` at `0x180017044`
- `OLEAUT32!__imp_SysAllocString` at `0x180017044`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::get_TraceFile(CNetworkDiagnostics *this, unsigned __int16 **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HRESULT TraceFile; // ebx
  void *v6; // rcx
  unsigned __int16 *v7; // rax
  LPCWSTR TraceFileLocation; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( *((int *)this + 30) >= 3 )
  {
    v6 = (void *)*((_QWORD *)this + 2);
    TraceFileLocation = 0;
    TraceFile = NdfGetTraceFile(v6, &TraceFileLocation);
    if ( TraceFile >= 0 )
    {
      v7 = SysAllocString(TraceFileLocation);
      *a2 = v7;
      if ( !v7 )
        TraceFile = -2147024882;
      CoTaskMemFree((LPVOID)TraceFileLocation);
    }
  }
  else
  {
    TraceFile = -2147024120;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)TraceFile;
}

```

## disassembly

```asm
0x180016ff0  mov     [rsp+arg_8], rbx
0x180016ff5  mov     [rsp+arg_10], rsi
0x180016ffa  push    rdi
0x180016ffb  sub     rsp, 20h
0x180016fff  lea     rdi, [rcx+80h]
0x180017006  mov     rbx, rcx
0x180017009  mov     rcx, rdi; lpCriticalSection
0x18001700c  mov     rsi, rdx
0x18001700f  call    cs:__imp_EnterCriticalSection
0x180017015  cmp     dword ptr [rbx+78h], 3
0x180017019  jge     short loc_180017022
0x18001701b  mov     ebx, 80070308h
0x180017020  jmp     short loc_180017063
0x180017022  mov     rcx, [rbx+10h]; Handle
0x180017026  lea     rdx, [rsp+28h+TraceFileLocation]; TraceFileLocation
0x18001702b  mov     [rsp+28h+TraceFileLocation], 0
0x180017034  call    NdfGetTraceFile
0x180017039  mov     ebx, eax
0x18001703b  test    eax, eax
0x18001703d  js      short loc_180017063
0x18001703f  mov     rcx, [rsp+28h+TraceFileLocation]; psz
0x180017044  call    cs:__imp_SysAllocString
0x18001704a  test    rax, rax
0x18001704d  mov     [rsi], rax
0x180017050  mov     ecx, 8007000Eh
0x180017055  cmovz   ebx, ecx
0x180017058  mov     rcx, [rsp+28h+TraceFileLocation]; pv
0x18001705d  call    cs:__imp_CoTaskMemFree
0x180017063  mov     rcx, rdi; lpCriticalSection
0x180017066  call    cs:__imp_LeaveCriticalSection
0x18001706c  mov     rsi, [rsp+28h+arg_10]
0x180017071  mov     eax, ebx
0x180017073  mov     rbx, [rsp+28h+arg_8]
0x180017078  add     rsp, 20h
0x18001707c  pop     rdi
0x18001707d  retn
```
