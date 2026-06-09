# CCancelRpc::ProcessEvents(void)

- ea: `0x180015f90`
- end: `0x1800160a5`
- name: `?ProcessEvents@CCancelRpc@@AEAAXXZ`
- size: `277`
- prototype: `void __fastcall __noreturn(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015990`

## callees

- `0x1800049ac`
- `0x1800158e0`
- `0x180015f90`

## import_xrefs

- `msvcrt!time` at `0x180016055`
- `msvcrt!time` at `0x180016055`
- `KERNEL32!WaitForMultipleObjects` at `0x18001607a`
- `KERNEL32!WaitForMultipleObjects` at `0x18001607a`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001600a`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001609e`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001600a`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001609e`
- `KERNEL32!SetEvent` at `0x180015fb3`
- `KERNEL32!SetEvent` at `0x180015fb3`
- `ole32!CoUninitialize` at `0x180016084`
- `ole32!CoUninitialize` at `0x180016084`
- `ole32!CoInitializeEx` at `0x180015fa6`
- `ole32!CoInitializeEx` at `0x180015fa6`

## pseudocode

```c
void __fastcall __noreturn CCancelRpc::ProcessEvents(LPCRITICAL_SECTION lpCriticalSection)
{
  HRESULT v2; // eax
  void *SpinCount; // rcx
  __int64 DebugInfo_low; // r9
  HMODULE OwningThread; // rcx
  LONG v6; // edi
  unsigned int LockCount; // kr00_4
  DWORD v8; // r9d
  time_t v9; // rax
  DWORD v10; // eax
  HMODULE v11; // rcx
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = CoInitializeEx(0, 0);
  SpinCount = (void *)lpCriticalSection[2].SpinCount;
  LODWORD(lpCriticalSection[3].DebugInfo) = v2;
  SetEvent(SpinCount);
  DebugInfo_low = LODWORD(lpCriticalSection[3].DebugInfo);
  if ( (int)DebugInfo_low < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        20,
        &WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids,
        DebugInfo_low);
    OwningThread = (HMODULE)lpCriticalSection[3].OwningThread;
    lpCriticalSection[3].OwningThread = 0;
    FreeLibraryAndExitThread(OwningThread, 0);
  }
  v6 = -1;
  LockCount = lpCriticalSection[3].LockCount;
  Handles[0] = lpCriticalSection[2].OwningThread;
  v8 = -1;
  Handles[1] = *(HANDLE *)&lpCriticalSection[2].LockCount;
  while ( 1 )
  {
    v10 = WaitForMultipleObjects(2u, Handles, 0, v8);
    if ( !v10 )
      break;
    if ( v10 == 1 )
    {
      v6 = lpCriticalSection[3].LockCount;
    }
    else if ( HIDWORD(lpCriticalSection[1].OwningThread) )
    {
      v9 = time(0);
      CCancelRpc::CancelRequests(lpCriticalSection, v9 - LockCount / 0x3E8);
    }
    else
    {
      v6 = -1;
    }
    v8 = v6;
  }
  CoUninitialize();
  v11 = (HMODULE)lpCriticalSection[3].OwningThread;
  lpCriticalSection[3].OwningThread = 0;
  FreeLibraryAndExitThread(v11, 0);
}

```

## disassembly

```asm
0x180015f90  mov     [rsp+arg_0], rbx
0x180015f95  mov     [rsp+arg_8], rsi
0x180015f9a  push    rdi
0x180015f9b  sub     rsp, 30h
0x180015f9f  mov     rbx, rcx
0x180015fa2  xor     edx, edx; dwCoInit
0x180015fa4  xor     ecx, ecx; pvReserved
0x180015fa6  call    cs:__imp_CoInitializeEx
0x180015fac  mov     rcx, [rbx+70h]; hEvent
0x180015fb0  mov     [rbx+78h], eax
0x180015fb3  call    cs:__imp_SetEvent
0x180015fb9  mov     r9d, [rbx+78h]
0x180015fbd  test    r9d, r9d
0x180015fc0  jns     short loc_180016011
0x180015fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fc9  lea     rax, WPP_GLOBAL_Control
0x180015fd0  cmp     rcx, rax
0x180015fd3  jz      short loc_180015FF6
0x180015fd5  test    byte ptr [rcx+0BCh], 1
0x180015fdc  jz      short loc_180015FF6
0x180015fde  mov     rcx, [rcx+0B0h]
0x180015fe5  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015fec  mov     edx, 14h
0x180015ff1  call    WPP_SF_d
0x180015ff6  mov     rcx, [rbx+88h]; hLibModule
0x180015ffd  xor     edx, edx; dwExitCode
0x180015fff  mov     qword ptr [rbx+88h], 0
0x18001600a  call    cs:__imp_FreeLibraryAndExitThread
0x180016011  mov     eax, 10624DD3h
0x180016016  or      edi, 0FFFFFFFFh
0x180016019  mul     dword ptr [rbx+80h]
0x18001601f  mov     rax, [rbx+60h]
0x180016023  mov     esi, edx
0x180016025  mov     [rsp+38h+Handles], rax
0x18001602a  mov     rax, [rbx+58h]
0x18001602e  shr     esi, 6
0x180016031  or      r9d, edi
0x180016034  mov     [rsp+38h+var_10], rax
0x180016039  jmp     short loc_18001606E
0x18001603b  cmp     eax, 1
0x18001603e  jnz     short loc_180016048
0x180016040  mov     edi, [rbx+80h]
0x180016046  jmp     short loc_18001606B
0x180016048  cmp     dword ptr [rbx+3Ch], 0
0x18001604c  jnz     short loc_180016053
0x18001604e  or      edi, 0FFFFFFFFh
0x180016051  jmp     short loc_18001606B
0x180016053  xor     ecx, ecx; Time
0x180016055  call    cs:__imp_time
0x18001605b  mov     ecx, esi
0x18001605d  sub     rax, rcx
0x180016060  mov     rcx, rbx; lpCriticalSection
0x180016063  mov     rdx, rax; __int64
0x180016066  call    ?CancelRequests@CCancelRpc@@QEAAX_J@Z; CCancelRpc::CancelRequests(__int64)
0x18001606b  mov     r9d, edi; dwMilliseconds
0x18001606e  xor     r8d, r8d; bWaitAll
0x180016071  lea     rdx, [rsp+38h+Handles]; lpHandles
0x180016076  lea     ecx, [r8+2]; nCount
0x18001607a  call    cs:__imp_WaitForMultipleObjects
0x180016080  test    eax, eax
0x180016082  jnz     short loc_18001603B
0x180016084  call    cs:__imp_CoUninitialize
0x18001608a  mov     rcx, [rbx+88h]; hLibModule
0x180016091  xor     edx, edx; dwExitCode
0x180016093  mov     qword ptr [rbx+88h], 0
0x18001609e  call    cs:__imp_FreeLibraryAndExitThread
```
