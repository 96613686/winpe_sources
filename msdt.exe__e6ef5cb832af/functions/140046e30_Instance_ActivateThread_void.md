# Instance::ActivateThread(void *)

- ea: `0x140046e30`
- end: `0x140047082`
- name: `?ActivateThread@Instance@@SAKPEAX@Z`
- size: `594`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140006fe0`
- `0x14000706c`
- `0x140020420`
- `0x140046e30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140046f67`
- `KERNEL32!GetLastError` at `0x140046f67`
- `KERNEL32!CloseHandle` at `0x140047043`
- `KERNEL32!CloseHandle` at `0x140047043`
- `KERNEL32!HeapAlloc` at `0x140046ecd`
- `KERNEL32!HeapAlloc` at `0x140046ecd`
- `KERNEL32!HeapFree` at `0x140046eaa`
- `KERNEL32!HeapFree` at `0x140047068`
- `KERNEL32!HeapFree` at `0x140046eaa`
- `KERNEL32!HeapFree` at `0x140047068`
- `KERNEL32!GetProcessHeap` at `0x140046e96`
- `KERNEL32!GetProcessHeap` at `0x140046eb6`
- `KERNEL32!GetProcessHeap` at `0x140047054`
- `KERNEL32!GetProcessHeap` at `0x140046e96`
- `KERNEL32!GetProcessHeap` at `0x140046eb6`
- `KERNEL32!GetProcessHeap` at `0x140047054`
- `KERNEL32!SetEvent` at `0x140046f53`
- `KERNEL32!SetEvent` at `0x140046f53`
- `KERNEL32!WaitForMultipleObjects` at `0x140046e66`
- `KERNEL32!WaitForMultipleObjects` at `0x140046e66`
- `KERNEL32!OpenEventW` at `0x140046f29`
- `KERNEL32!OpenEventW` at `0x140046f29`
- `USER32!AllowSetForegroundWindow` at `0x140046f44`
- `USER32!AllowSetForegroundWindow` at `0x140046f44`
- `USER32!SetForegroundWindow` at `0x140046fa6`
- `USER32!SetForegroundWindow` at `0x140046fa6`

## string_xrefs

- `0x140046fc5`: `Instance::ActivateThread`
- `0x140046ff1`: `Instance::ActivateThread`
- `0x14004701e`: `Instance::ActivateThread`

## pseudocode

```c
__int64 __fastcall Instance::ActivateThread(PVOID Parameter)
{
  unsigned __int16 *v1; // rbx
  char *v2; // rdi
  DWORD v3; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  unsigned __int16 *v6; // rax
  int v7; // eax
  signed int LastError; // eax
  bool v9; // sf
  int v10; // r9d
  HANDLE v11; // rax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  v1 = 0;
  Handles[0] = Instance::s_ActivateEvent;
  v2 = 0;
  Handles[1] = Instance::s_CloseEvent;
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( g_ElevatedProcess )
    {
      if ( v2 )
        goto LABEL_14;
      if ( v1 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v1);
      }
      v5 = GetProcessHeap();
      v6 = (unsigned __int16 *)HeapAlloc(v5, 0, 0x800u);
      v1 = v6;
      if ( !v6 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::ActivateThread", 236, -2147024882);
        return 0;
      }
      v7 = StringCchCopyW(v6, 0x400u, Instance::s_Name);
      if ( v7 < 0 )
      {
        v10 = 239;
LABEL_20:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::ActivateThread", v10, v7);
LABEL_27:
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v1);
        return 0;
      }
      v7 = StringCchCatW(v1, 0x400u, L"e");
      if ( v7 < 0 )
      {
        v10 = 245;
        goto LABEL_20;
      }
      v2 = (char *)OpenEventW(2u, 0, Instance::s_Name);
      if ( v2 )
      {
LABEL_14:
        AllowSetForegroundWindow(0xFFFFFFFF);
        if ( !SetEvent(v2) )
        {
          LastError = GetLastError();
          v9 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v9 = LastError < 0;
          }
          if ( v9 )
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::ActivateThread", 263, LastError);
            goto LABEL_24;
          }
        }
      }
    }
    else if ( g_HWND )
    {
      SetForegroundWindow(g_HWND);
    }
  }
  if ( v3 != 1 )
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::ActivateThread", 280, -2147024809);
LABEL_24:
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  if ( v1 )
    goto LABEL_27;
  return 0;
}

```

## disassembly

```asm
0x140046e30  mov     [rsp+arg_0], rbx
0x140046e35  push    rdi
0x140046e36  sub     rsp, 40h
0x140046e3a  mov     rax, cs:?s_ActivateEvent@Instance@@0PEAXEA; void * Instance::s_ActivateEvent
0x140046e41  xor     ebx, ebx
0x140046e43  mov     [rsp+48h+Handles], rax
0x140046e48  xor     edi, edi
0x140046e4a  mov     rax, cs:?s_CloseEvent@Instance@@0PEAXEA; void * Instance::s_CloseEvent
0x140046e51  mov     [rsp+48h+var_10], rax
0x140046e56  xor     r8d, r8d; bWaitAll
0x140046e59  lea     rdx, [rsp+48h+Handles]; lpHandles
0x140046e5e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140046e62  lea     ecx, [r8+2]; nCount
0x140046e66  call    cs:__imp_WaitForMultipleObjects
0x140046e6d  nop     dword ptr [rax+rax+00h]
0x140046e72  test    eax, eax
0x140046e74  jnz     loc_14004700B
0x140046e7a  cmp     cs:?g_ElevatedProcess@@3PEAXEA, 0; void * g_ElevatedProcess
0x140046e82  jz      loc_140046F96
0x140046e88  test    rdi, rdi
0x140046e8b  jnz     loc_140046F41
0x140046e91  test    rbx, rbx
0x140046e94  jz      short loc_140046EB6
0x140046e96  call    cs:__imp_GetProcessHeap
0x140046e9d  nop     dword ptr [rax+rax+00h]
0x140046ea2  mov     r8, rbx; lpMem
0x140046ea5  xor     edx, edx; dwFlags
0x140046ea7  mov     rcx, rax; hHeap
0x140046eaa  call    cs:__imp_HeapFree
0x140046eb1  nop     dword ptr [rax+rax+00h]
0x140046eb6  call    cs:__imp_GetProcessHeap
0x140046ebd  nop     dword ptr [rax+rax+00h]
0x140046ec2  xor     edx, edx; dwFlags
0x140046ec4  mov     r8d, 800h; dwBytes
0x140046eca  mov     rcx, rax; hHeap
0x140046ecd  call    cs:__imp_HeapAlloc
0x140046ed4  nop     dword ptr [rax+rax+00h]
0x140046ed9  mov     rbx, rax
0x140046edc  test    rax, rax
0x140046edf  jz      loc_140046FE3
0x140046ee5  mov     r8, cs:?s_Name@Instance@@0PEAGEA; unsigned __int16 *
0x140046eec  mov     edx, 400h; unsigned __int64
0x140046ef1  mov     rcx, rax; unsigned __int16 *
0x140046ef4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140046ef9  test    eax, eax
0x140046efb  js      loc_140046FBF
0x140046f01  lea     r8, aE; "e"
0x140046f08  mov     edx, 400h; unsigned __int64
0x140046f0d  mov     rcx, rbx; unsigned __int16 *
0x140046f10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140046f15  test    eax, eax
0x140046f17  js      loc_140046FB7
0x140046f1d  mov     r8, cs:?s_Name@Instance@@0PEAGEA; lpName
0x140046f24  xor     edx, edx; bInheritHandle
0x140046f26  lea     ecx, [rdx+2]; dwDesiredAccess
0x140046f29  call    cs:__imp_OpenEventW
0x140046f30  nop     dword ptr [rax+rax+00h]
0x140046f35  mov     rdi, rax
0x140046f38  test    rax, rax
0x140046f3b  jz      loc_140046E56
0x140046f41  or      ecx, 0FFFFFFFFh; dwProcessId
0x140046f44  call    cs:__imp_AllowSetForegroundWindow
0x140046f4b  nop     dword ptr [rax+rax+00h]
0x140046f50  mov     rcx, rdi; hEvent
0x140046f53  call    cs:__imp_SetEvent
0x140046f5a  nop     dword ptr [rax+rax+00h]
0x140046f5f  test    eax, eax
0x140046f61  jnz     loc_140046E56
0x140046f67  call    cs:__imp_GetLastError
0x140046f6e  nop     dword ptr [rax+rax+00h]
0x140046f73  test    eax, eax
0x140046f75  jle     short loc_140046F81
0x140046f77  movzx   eax, ax
0x140046f7a  or      eax, 80070000h
0x140046f7f  test    eax, eax
0x140046f81  jns     loc_140046E56
0x140046f87  mov     [rsp+48h+var_28], eax
0x140046f8b  mov     r9d, 107h
0x140046f91  jmp     loc_14004701E
0x140046f96  mov     rcx, cs:?g_HWND@@3PEAUHWND__@@EA; hWnd
0x140046f9d  test    rcx, rcx
0x140046fa0  jz      loc_140046E56
0x140046fa6  call    cs:__imp_SetForegroundWindow
0x140046fad  nop     dword ptr [rax+rax+00h]
0x140046fb2  jmp     loc_140046E56
0x140046fb7  mov     r9d, 0F5h
0x140046fbd  jmp     short loc_140046FC5
0x140046fbf  mov     r9d, 0EFh
0x140046fc5  lea     r8, aInstanceActiva; "Instance::ActivateThread"
0x140046fcc  mov     [rsp+48h+var_28], eax
0x140046fd0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140046fd7  mov     ecx, 1; Level
0x140046fdc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140046fe1  jmp     short loc_140047054
0x140046fe3  mov     r9d, 0ECh
0x140046fe9  mov     [rsp+48h+var_28], 8007000Eh
0x140046ff1  lea     r8, aInstanceActiva; "Instance::ActivateThread"
0x140046ff8  mov     ecx, 1; Level
0x140046ffd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047004  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047009  jmp     short loc_140047074
0x14004700b  cmp     eax, 1
0x14004700e  jz      short loc_140047036
0x140047010  mov     [rsp+48h+var_28], 80070057h
0x140047018  mov     r9d, 118h
0x14004701e  lea     r8, aInstanceActiva; "Instance::ActivateThread"
0x140047025  mov     ecx, 1; Level
0x14004702a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047031  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047036  lea     rax, [rdi-1]
0x14004703a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004703e  ja      short loc_14004704F
0x140047040  mov     rcx, rdi; hObject
0x140047043  call    cs:__imp_CloseHandle
0x14004704a  nop     dword ptr [rax+rax+00h]
0x14004704f  test    rbx, rbx
0x140047052  jz      short loc_140047074
0x140047054  call    cs:__imp_GetProcessHeap
0x14004705b  nop     dword ptr [rax+rax+00h]
0x140047060  mov     r8, rbx; lpMem
0x140047063  xor     edx, edx; dwFlags
0x140047065  mov     rcx, rax; hHeap
0x140047068  call    cs:__imp_HeapFree
0x14004706f  nop     dword ptr [rax+rax+00h]
0x140047074  mov     rbx, [rsp+48h+arg_0]
0x140047079  xor     eax, eax
0x14004707b  add     rsp, 40h
0x14004707f  pop     rdi
0x140047080  retn
```
