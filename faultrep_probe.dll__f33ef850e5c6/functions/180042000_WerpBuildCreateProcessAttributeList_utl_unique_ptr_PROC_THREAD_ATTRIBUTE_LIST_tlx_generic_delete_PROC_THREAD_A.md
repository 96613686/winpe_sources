# WerpBuildCreateProcessAttributeList(utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>> *,void * *,ulong *,void * *,ulong,ulong *,ushort *)

- ea: `0x180042000`
- end: `0x1800424d4`
- name: `?WerpBuildCreateProcessAttributeList@@YAJPEAV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@PEAPEAXPEAK1K2PEAG@Z`
- size: `1236`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000d864`
- `0x180041bdc`

## callees

- `0x180003617`
- `0x180042000`
- `0x1800424dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800420e0`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180042168`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800420e0`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180042168`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180042232`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800422ab`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180042335`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800423ae`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004242d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180042232`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800422ab`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180042335`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800423ae`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004242d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180042493`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180042493`
- `ntdll!DbgPrintEx` at `0x1800421bb`
- `ntdll!DbgPrintEx` at `0x1800421f8`
- `ntdll!DbgPrintEx` at `0x180042480`
- `ntdll!DbgPrintEx` at `0x1800421bb`
- `ntdll!DbgPrintEx` at `0x1800421f8`
- `ntdll!DbgPrintEx` at `0x180042480`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180042149`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180042149`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004203f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800424bd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004203f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800424bd`

## string_xrefs

- `0x18004211f`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x1800421a5`: `WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n`
- `0x18004226c`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/PARENT_PROCESS failed: %u.\n`
- `0x1800422e5`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/EXTENDED_FLAGS failed: %u.\n`
- `0x18004236f`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/HANDLE_LIST failed: %u.\n`
- `0x1800423e8`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/CHILD_PROCESS failed: %u.\n`
- `0x180042467`: `WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/MACHINE_TYPE failed: %u.\n`

## pseudocode

```c
__int64 __fastcall WerpBuildCreateProcessAttributeList(
        void **a1,
        _QWORD *a2,
        _DWORD *a3,
        void *a4,
        unsigned int a5,
        PVOID a6,
        PVOID a7)
{
  void *v8; // rcx
  PVOID v9; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rbx
  int v13; // r9d
  int v14; // r8d
  int v15; // edx
  _DWORD *v16; // rsi
  int v17; // ecx
  _WORD *v18; // rdi
  int v19; // eax
  DWORD v20; // r15d
  int v21; // eax
  int v22; // ebx
  int v23; // edi
  DWORD v24; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v25; // rax
  int LastError; // eax
  int v27; // esi
  DWORD v28; // eax
  int v29; // r15d
  DWORD CurrentProcessId_0; // eax
  int v31; // eax
  int v32; // esi
  DWORD v33; // eax
  int v34; // eax
  int v35; // esi
  DWORD v36; // eax
  int v37; // eax
  int v38; // esi
  DWORD v39; // eax
  int v40; // eax
  int v41; // esi
  DWORD v42; // eax
  int v43; // eax
  int v44; // esi
  DWORD v45; // eax
  void *v46; // rcx
  SIZE_T cbSize; // [rsp+20h] [rbp-58h]
  SIZE_T cbSizea; // [rsp+20h] [rbp-58h]
  SIZE_T cbSizeb; // [rsp+20h] [rbp-58h]
  SIZE_T cbSizec; // [rsp+20h] [rbp-58h]
  SIZE_T cbSized; // [rsp+20h] [rbp-58h]
  PVOID lpPreviousValue; // [rsp+28h] [rbp-50h]
  PVOID lpPreviousValuea; // [rsp+28h] [rbp-50h]
  PVOID lpPreviousValueb; // [rsp+28h] [rbp-50h]
  PVOID lpPreviousValuec; // [rsp+28h] [rbp-50h]
  PVOID lpPreviousValued; // [rsp+28h] [rbp-50h]
  ULONG_PTR Size; // [rsp+88h] [rbp+10h] BYREF
  PVOID lpValue; // [rsp+98h] [rbp+20h]

  lpValue = a4;
  v8 = *a1;
  v9 = a4;
  Size = 0;
  v12 = 0;
  *a1 = 0;
  if ( v8 )
  {
    VirtualFree(v8, 0, 0x8000u);
    v9 = lpValue;
  }
  if ( !a2 || (v13 = 1, !*a2) )
    v13 = 0;
  if ( !a3 || (v14 = 1, !*a3) )
    v14 = 0;
  if ( !v9 || (v15 = 1, !a5) )
    v15 = 0;
  v16 = a6;
  if ( !a6 || (v17 = 1, !*(_DWORD *)a6) )
    v17 = 0;
  v18 = a7;
  if ( !a7 || (v19 = 1, !*(_WORD *)a7) )
    v19 = 0;
  v20 = v13 + v14 + v15 + v17 + v19;
  if ( !v20 )
  {
    v29 = 0;
    goto LABEL_39;
  }
  if ( InitializeProcThreadAttributeList(0, v20, 0, &Size) || (unsigned int)WerpGetLastError() == 122 )
  {
    v25 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAlloc(0, Size, 0x1000u, 4u);
    v12 = v25;
    if ( !v25 )
    {
      v23 = -2147024882;
      CurrentProcessId_0 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR Failed to allocate attribute list: HRESULT %08X.\n",
        CurrentProcessId_0,
        421,
        -2147024882);
      return (unsigned int)v23;
    }
    if ( !InitializeProcThreadAttributeList(v25, v20, 0, &Size) )
    {
      LastError = WerpGetLastError();
      v27 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v28 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n",
        v28,
        434,
        v27);
      v29 = 0;
      goto LABEL_85;
    }
    v29 = 1;
LABEL_39:
    if ( a2 && *a2 && !UpdateProcThreadAttribute(v12, 0, 0x20000u, a2, 8u, 0, 0) )
    {
      v31 = WerpGetLastError();
      v32 = v31;
      if ( v31 > 0 )
        v23 = (unsigned __int16)v31 | 0x80070000;
      else
        v23 = v31;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v33 = GetCurrentProcessId_0();
      LODWORD(lpPreviousValue) = v32;
      LODWORD(cbSize) = 455;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/PARENT_PROCESS failed: %u.\n",
        v33,
        cbSize,
        lpPreviousValue);
    }
    else if ( a3 && *a3 && !UpdateProcThreadAttribute(v12, 0, 0x60001u, a3, 4u, 0, 0) )
    {
      v34 = WerpGetLastError();
      v35 = v34;
      if ( v34 > 0 )
        v23 = (unsigned __int16)v34 | 0x80070000;
      else
        v23 = v34;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v36 = GetCurrentProcessId_0();
      LODWORD(lpPreviousValuea) = v35;
      LODWORD(cbSizea) = 474;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/EXTENDED_FLAGS failed: %u.\n",
        v36,
        cbSizea,
        lpPreviousValuea);
    }
    else if ( lpValue && a5 && !UpdateProcThreadAttribute(v12, 0, 0x20002u, lpValue, 8LL * a5, 0, 0) )
    {
      v37 = WerpGetLastError();
      v38 = v37;
      if ( v37 > 0 )
        v23 = (unsigned __int16)v37 | 0x80070000;
      else
        v23 = v37;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v39 = GetCurrentProcessId_0();
      LODWORD(lpPreviousValueb) = v38;
      LODWORD(cbSizeb) = 493;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/HANDLE_LIST failed: %u.\n",
        v39,
        cbSizeb,
        lpPreviousValueb);
    }
    else if ( v16 && *v16 && !UpdateProcThreadAttribute(v12, 0, 0x2000Eu, v16, 4u, 0, 0) )
    {
      v40 = WerpGetLastError();
      v41 = v40;
      if ( v40 > 0 )
        v23 = (unsigned __int16)v40 | 0x80070000;
      else
        v23 = v40;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v42 = GetCurrentProcessId_0();
      LODWORD(lpPreviousValuec) = v41;
      LODWORD(cbSizec) = 512;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/CHILD_PROCESS failed: %u.\n",
        v42,
        cbSizec,
        lpPreviousValuec);
    }
    else
    {
      if ( !v18 || !*v18 || UpdateProcThreadAttribute(v12, 0, 0x20019u, v18, 2u, 0, 0) )
      {
        v46 = *a1;
        *a1 = v12;
        v23 = v12 == 0;
        if ( !v46 )
          return (unsigned int)v23;
LABEL_89:
        VirtualFree(v46, 0, 0x8000u);
        return (unsigned int)v23;
      }
      v43 = WerpGetLastError();
      v44 = v43;
      if ( v43 > 0 )
        v23 = (unsigned __int16)v43 | 0x80070000;
      else
        v23 = v43;
      if ( v23 >= 0 )
        v23 = -2147467259;
      v45 = GetCurrentProcessId_0();
      LODWORD(lpPreviousValued) = v44;
      LODWORD(cbSized) = 532;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR UpdateProcThreadAttribute/MACHINE_TYPE failed: %u.\n",
        v45,
        cbSized,
        lpPreviousValued);
    }
    if ( !v12 )
      return (unsigned int)v23;
LABEL_85:
    if ( v29 )
      DeleteProcThreadAttributeList(v12);
    v46 = v12;
    goto LABEL_89;
  }
  v21 = WerpGetLastError();
  v22 = v21;
  if ( v21 > 0 )
    v23 = (unsigned __int16)v21 | 0x80070000;
  else
    v23 = v21;
  if ( v23 >= 0 )
    v23 = -2147467259;
  v24 = GetCurrentProcessId_0();
  DbgPrintEx(0x96u, 0, "WER/ReportFault/%u:%u: ERROR InitializeProcThreadAttributeList failed: %u.\n", v24, 408, v22);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180042000  mov     r11, rsp
0x180042003  mov     [r11+20h], r9
0x180042007  push    rbx
0x180042008  push    rbp
0x180042009  push    rsi
0x18004200a  push    rdi
0x18004200b  push    r13
0x18004200d  push    r14
0x18004200f  push    r15
0x180042011  sub     rsp, 40h
0x180042015  xor     r10d, r10d
0x180042018  mov     r13, rcx
0x18004201b  mov     rcx, [rcx]; lpAddress
0x18004201e  mov     rax, r9
0x180042021  mov     [r11+10h], r10
0x180042025  mov     r14, r8
0x180042028  mov     rbp, rdx
0x18004202b  mov     ebx, r10d
0x18004202e  mov     [r13+0], r10
0x180042032  test    rcx, rcx
0x180042035  jz      short loc_180042050
0x180042037  xor     edx, edx; dwSize
0x180042039  mov     r8d, 8000h; dwFreeType
0x18004203f  call    cs:__imp_VirtualFree
0x180042045  mov     rax, [rsp+78h+lpValue]
0x18004204d  xor     r10d, r10d
0x180042050  mov     r11d, 1
0x180042056  test    rbp, rbp
0x180042059  jz      short loc_180042064
0x18004205b  mov     r9d, r11d
0x18004205e  cmp     [rbp+0], r10
0x180042062  jnz     short loc_180042067
0x180042064  mov     r9d, r10d
0x180042067  test    r14, r14
0x18004206a  jz      short loc_180042074
0x18004206c  mov     r8d, r11d
0x18004206f  cmp     [r14], r10d
0x180042072  jnz     short loc_180042077
0x180042074  mov     r8d, r10d
0x180042077  test    rax, rax
0x18004207a  jz      short loc_180042089
0x18004207c  mov     edx, r11d
0x18004207f  cmp     [rsp+78h+arg_20], r10d
0x180042087  jnz     short loc_18004208C
0x180042089  mov     edx, r10d
0x18004208c  mov     rsi, [rsp+78h+arg_28]
0x180042094  test    rsi, rsi
0x180042097  jz      short loc_1800420A1
0x180042099  mov     ecx, r11d
0x18004209c  cmp     [rsi], r10d
0x18004209f  jnz     short loc_1800420A4
0x1800420a1  mov     ecx, r10d
0x1800420a4  mov     rdi, [rsp+78h+arg_30]
0x1800420ac  test    rdi, rdi
0x1800420af  jz      short loc_1800420BA
0x1800420b1  mov     eax, r11d
0x1800420b4  cmp     [rdi], r10w
0x1800420b8  jnz     short loc_1800420BD
0x1800420ba  mov     eax, r10d
0x1800420bd  lea     r15d, [rcx+rax]
0x1800420c1  add     r15d, edx
0x1800420c4  add     r15d, r8d
0x1800420c7  add     r15d, r9d
0x1800420ca  jz      loc_180042203
0x1800420d0  lea     r9, [rsp+78h+Size]; lpSize
0x1800420d8  xor     r8d, r8d; dwFlags
0x1800420db  mov     edx, r15d; dwAttributeCount
0x1800420de  xor     ecx, ecx; lpAttributeList
0x1800420e0  call    cs:__imp_InitializeProcThreadAttributeList
0x1800420e6  test    eax, eax
0x1800420e8  jnz     short loc_180042133
0x1800420ea  call    WerpGetLastError
0x1800420ef  cmp     eax, 7Ah ; 'z'
0x1800420f2  jz      short loc_180042133
0x1800420f4  call    WerpGetLastError
0x1800420f9  mov     ebx, eax
0x1800420fb  test    eax, eax
0x1800420fd  jg      short loc_180042103
0x1800420ff  mov     edi, eax
0x180042101  jmp     short loc_18004210C
0x180042103  movzx   edi, bx
0x180042106  or      edi, 80070000h
0x18004210c  test    edi, edi
0x18004210e  mov     eax, 80004005h
0x180042113  cmovns  edi, eax
0x180042116  call    GetCurrentProcessId_0
0x18004211b  mov     dword ptr [rsp+78h+lpPreviousValue], ebx
0x18004211f  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x180042126  mov     dword ptr [rsp+78h+cbSize], 198h
0x18004212e  jmp     loc_1800421EE
0x180042133  mov     rdx, [rsp+78h+Size]; dwSize
0x18004213b  mov     r9d, 4; flProtect
0x180042141  mov     r8d, 1000h; flAllocationType
0x180042147  xor     ecx, ecx; lpAddress
0x180042149  call    cs:__imp_VirtualAlloc
0x18004214f  mov     rbx, rax
0x180042152  test    rax, rax
0x180042155  jz      short loc_1800421D1
0x180042157  lea     r9, [rsp+78h+Size]; lpSize
0x18004215f  xor     r8d, r8d; dwFlags
0x180042162  mov     edx, r15d; dwAttributeCount
0x180042165  mov     rcx, rax; lpAttributeList
0x180042168  call    cs:__imp_InitializeProcThreadAttributeList
0x18004216e  xor     r10d, r10d
0x180042171  test    eax, eax
0x180042173  jnz     short loc_1800421C9
0x180042175  call    WerpGetLastError
0x18004217a  xor     ebp, ebp
0x18004217c  mov     esi, eax
0x18004217e  test    eax, eax
0x180042180  jg      short loc_180042186
0x180042182  mov     edi, eax
0x180042184  jmp     short loc_18004218F
0x180042186  movzx   edi, si
0x180042189  or      edi, 80070000h
0x18004218f  mov     eax, 80004005h
0x180042194  test    edi, edi
0x180042196  cmovns  edi, eax
0x180042199  call    GetCurrentProcessId_0
0x18004219e  mov     r9d, eax
0x1800421a1  mov     dword ptr [rsp+78h+lpPreviousValue], esi
0x1800421a5  lea     r8, aWerReportfault_0; "WER/ReportFault/%u:%u: ERROR Initialize"...
0x1800421ac  mov     dword ptr [rsp+78h+cbSize], 1B2h
0x1800421b4  xor     edx, edx; Level
0x1800421b6  mov     ecx, 96h; ComponentId
0x1800421bb  call    cs:__imp_DbgPrintEx
0x1800421c1  mov     r15d, ebp
0x1800421c4  jmp     loc_18004248B
0x1800421c9  mov     r15d, 1
0x1800421cf  jmp     short loc_180042206
0x1800421d1  mov     edi, 8007000Eh
0x1800421d6  call    GetCurrentProcessId_0
0x1800421db  mov     dword ptr [rsp+78h+lpPreviousValue], edi
0x1800421df  lea     r8, aWerReportfault_7; "WER/ReportFault/%u:%u: ERROR Failed to "...
0x1800421e6  mov     dword ptr [rsp+78h+cbSize], 1A5h
0x1800421ee  mov     r9d, eax
0x1800421f1  xor     edx, edx; Level
0x1800421f3  mov     ecx, 96h; ComponentId
0x1800421f8  call    cs:__imp_DbgPrintEx
0x1800421fe  jmp     loc_1800424C3
0x180042203  mov     r15d, ebx
0x180042206  test    rbp, rbp
0x180042209  jz      short loc_180042280
0x18004220b  cmp     [rbp+0], r10
0x18004220f  jz      short loc_180042280
0x180042211  mov     [rsp+78h+lpReturnSize], r10; lpReturnSize
0x180042216  mov     r9, rbp; lpValue
0x180042219  mov     [rsp+78h+lpPreviousValue], r10; lpPreviousValue
0x18004221e  xor     edx, edx; dwFlags
0x180042220  mov     r8d, 20000h; Attribute
0x180042226  mov     [rsp+78h+cbSize], 8; cbSize
0x18004222f  mov     rcx, rbx; lpAttributeList
0x180042232  call    cs:__imp_UpdateProcThreadAttribute
0x180042238  xor     r10d, r10d
0x18004223b  test    eax, eax
0x18004223d  jnz     short loc_180042280
0x18004223f  call    WerpGetLastError
0x180042244  xor     ebp, ebp
0x180042246  mov     esi, eax
0x180042248  test    eax, eax
0x18004224a  jg      short loc_180042250
0x18004224c  mov     edi, eax
0x18004224e  jmp     short loc_180042259
0x180042250  movzx   edi, si
0x180042253  or      edi, 80070000h
0x180042259  test    edi, edi
0x18004225b  mov     eax, 80004005h
0x180042260  cmovns  edi, eax
0x180042263  call    GetCurrentProcessId_0
0x180042268  mov     dword ptr [rsp+78h+lpPreviousValue], esi
0x18004226c  lea     r8, aWerReportfault_24; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x180042273  mov     dword ptr [rsp+78h+cbSize], 1C7h
0x18004227b  jmp     loc_180042476
0x180042280  test    r14, r14
0x180042283  jz      short loc_1800422F9
0x180042285  cmp     [r14], r10d
0x180042288  jz      short loc_1800422F9
0x18004228a  mov     [rsp+78h+lpReturnSize], r10; lpReturnSize
0x18004228f  mov     r9, r14; lpValue
0x180042292  mov     [rsp+78h+lpPreviousValue], r10; lpPreviousValue
0x180042297  xor     edx, edx; dwFlags
0x180042299  mov     r8d, 60001h; Attribute
0x18004229f  mov     [rsp+78h+cbSize], 4; cbSize
0x1800422a8  mov     rcx, rbx; lpAttributeList
0x1800422ab  call    cs:__imp_UpdateProcThreadAttribute
0x1800422b1  xor     r10d, r10d
0x1800422b4  test    eax, eax
0x1800422b6  jnz     short loc_1800422F9
0x1800422b8  call    WerpGetLastError
0x1800422bd  xor     ebp, ebp
0x1800422bf  mov     esi, eax
0x1800422c1  test    eax, eax
0x1800422c3  jg      short loc_1800422C9
0x1800422c5  mov     edi, eax
0x1800422c7  jmp     short loc_1800422D2
0x1800422c9  movzx   edi, si
0x1800422cc  or      edi, 80070000h
0x1800422d2  test    edi, edi
0x1800422d4  mov     eax, 80004005h
0x1800422d9  cmovns  edi, eax
0x1800422dc  call    GetCurrentProcessId_0
0x1800422e1  mov     dword ptr [rsp+78h+lpPreviousValue], esi
0x1800422e5  lea     r8, aWerReportfault_18; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x1800422ec  mov     dword ptr [rsp+78h+cbSize], 1DAh
0x1800422f4  jmp     loc_180042476
0x1800422f9  mov     r9, [rsp+78h+lpValue]; lpValue
0x180042301  test    r9, r9
0x180042304  jz      short loc_180042383
0x180042306  cmp     [rsp+78h+arg_20], r10d
0x18004230e  jz      short loc_180042383
0x180042310  mov     eax, [rsp+78h+arg_20]
0x180042317  xor     edx, edx; dwFlags
0x180042319  mov     [rsp+78h+lpReturnSize], r10; lpReturnSize
0x18004231e  mov     r8d, 20002h; Attribute
0x180042324  shl     rax, 3
0x180042328  mov     rcx, rbx; lpAttributeList
0x18004232b  mov     [rsp+78h+lpPreviousValue], r10; lpPreviousValue
0x180042330  mov     [rsp+78h+cbSize], rax; cbSize
0x180042335  call    cs:__imp_UpdateProcThreadAttribute
0x18004233b  xor     r10d, r10d
0x18004233e  test    eax, eax
0x180042340  jnz     short loc_180042383
0x180042342  call    WerpGetLastError
0x180042347  xor     ebp, ebp
0x180042349  mov     esi, eax
0x18004234b  test    eax, eax
0x18004234d  jg      short loc_180042353
0x18004234f  mov     edi, eax
0x180042351  jmp     short loc_18004235C
0x180042353  movzx   edi, si
0x180042356  or      edi, 80070000h
0x18004235c  test    edi, edi
0x18004235e  mov     eax, 80004005h
0x180042363  cmovns  edi, eax
0x180042366  call    GetCurrentProcessId_0
0x18004236b  mov     dword ptr [rsp+78h+lpPreviousValue], esi
0x18004236f  lea     r8, aWerReportfault_1; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x180042376  mov     dword ptr [rsp+78h+cbSize], 1EDh
0x18004237e  jmp     loc_180042476
0x180042383  test    rsi, rsi
0x180042386  jz      short loc_1800423F9
0x180042388  cmp     [rsi], r10d
0x18004238b  jz      short loc_1800423F9
0x18004238d  mov     [rsp+78h+lpReturnSize], r10; lpReturnSize
0x180042392  mov     r9, rsi; lpValue
0x180042395  mov     [rsp+78h+lpPreviousValue], r10; lpPreviousValue
0x18004239a  xor     edx, edx; dwFlags
0x18004239c  mov     r8d, 2000Eh; Attribute
0x1800423a2  mov     [rsp+78h+cbSize], 4; cbSize
0x1800423ab  mov     rcx, rbx; lpAttributeList
0x1800423ae  call    cs:__imp_UpdateProcThreadAttribute
0x1800423b4  xor     r10d, r10d
0x1800423b7  test    eax, eax
0x1800423b9  jnz     short loc_1800423F9
0x1800423bb  call    WerpGetLastError
0x1800423c0  xor     ebp, ebp
0x1800423c2  mov     esi, eax
0x1800423c4  test    eax, eax
0x1800423c6  jg      short loc_1800423CC
0x1800423c8  mov     edi, eax
0x1800423ca  jmp     short loc_1800423D5
0x1800423cc  movzx   edi, si
0x1800423cf  or      edi, 80070000h
0x1800423d5  test    edi, edi
0x1800423d7  mov     eax, 80004005h
0x1800423dc  cmovns  edi, eax
0x1800423df  call    GetCurrentProcessId_0
0x1800423e4  mov     dword ptr [rsp+78h+lpPreviousValue], esi
0x1800423e8  lea     r8, aWerReportfault_3; "WER/ReportFault/%u:%u: ERROR UpdateProc"...
0x1800423ef  mov     dword ptr [rsp+78h+cbSize], 200h
0x1800423f7  jmp     short loc_180042476
0x1800423f9  test    rdi, rdi
0x1800423fc  jz      loc_18004249E
0x180042402  cmp     [rdi], r10w
0x180042406  jz      loc_18004249E
0x18004240c  mov     [rsp+78h+lpReturnSize], r10; lpReturnSize
0x180042411  mov     r9, rdi; lpValue
0x180042414  mov     [rsp+78h+lpPreviousValue], r10; lpPreviousValue
0x180042419  xor     edx, edx; dwFlags
0x18004241b  mov     r8d, 20019h; Attribute
0x180042421  mov     [rsp+78h+cbSize], 2; cbSize
0x18004242a  mov     rcx, rbx; lpAttributeList
0x18004242d  call    cs:__imp_UpdateProcThreadAttribute
0x180042433  xor     r10d, r10d
0x180042436  test    eax, eax
0x180042438  jnz     short loc_18004249E
0x18004243a  call    WerpGetLastError
0x18004243f  xor     ebp, ebp
0x180042441  mov     esi, eax
0x180042443  test    eax, eax
0x180042445  jg      short loc_18004244B
0x180042447  mov     edi, eax
0x180042449  jmp     short loc_180042454
0x18004244b  movzx   edi, si
0x18004244e  or      edi, 80070000h
0x180042454  test    edi, edi
0x180042456  mov     eax, 80004005h
0x18004245b  cmovns  edi, eax
0x18004245e  call    GetCurrentProcessId_0
0x180042463  mov     dword ptr [rsp+78h+lpPreviousValue], esi
  ... truncated ...
```
