# PnpCleanMain

- ea: `0x180001cd4`
- end: `0x180002181`
- name: `PnpCleanMain`
- size: `1197`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180001c00`

## callees

- `0x180001cd4`
- `0x1800043a0`
- `0x180004c14`
- `0x180006dc4`
- `0x180007dec`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001d54`
- `msvcrt!_wcsicmp` at `0x180001d71`
- `msvcrt!_wcsicmp` at `0x180001d8e`
- `msvcrt!_wcsicmp` at `0x180001dab`
- `msvcrt!_wcsicmp` at `0x180001de2`
- `msvcrt!_wcsicmp` at `0x180001e07`
- `msvcrt!_wcsicmp` at `0x180001e2a`
- `msvcrt!_wcsicmp` at `0x180001e50`
- `msvcrt!_wcsicmp` at `0x180001d54`
- `msvcrt!_wcsicmp` at `0x180001d71`
- `msvcrt!_wcsicmp` at `0x180001d8e`
- `msvcrt!_wcsicmp` at `0x180001dab`
- `msvcrt!_wcsicmp` at `0x180001de2`
- `msvcrt!_wcsicmp` at `0x180001e07`
- `msvcrt!_wcsicmp` at `0x180001e2a`
- `msvcrt!_wcsicmp` at `0x180001e50`
- `KERNEL32!SetConsoleCtrlHandler` at `0x180001d07`
- `KERNEL32!SetConsoleCtrlHandler` at `0x180001d07`

## string_xrefs

- `0x180001da0`: `NOREMOVE`
- `0x180001ecf`: `Processes devices and drivers that may be removed from the system.`
- `0x180001ee3`: `PNPCLEAN [/DEVICES] [/DRIVERS] [/FILES] [/MAXCLEAN] [/NOREMOVE]`
- `0x180001f0e`: `         /DEVICES            Removes devices missing for the default time period`
- `0x180001f32`: `         /DRIVERS            Removes redundant drivers from the system`
- `0x180001f56`: `         /FILES              Removes files/directories that are no longer needed that are related to devices and drivers.`
- `0x180001fea`: `                             installed on some device to be processed for removal.`
- `0x18000200e`: `                             For /FILES this currently has no effect on what is removed.`
- `0x180002032`: `         /NOREMOVE           Evaluate items only, do not remove`

## pseudocode

```c
__int64 __fastcall PnpCleanMain(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // ecx
  int v8; // r14d
  __int64 v9; // rbp
  int v10; // r15d
  int v11; // r13d
  __int64 v12; // r12
  __int64 v13; // rcx
  int v14; // eax
  int v15; // edi
  int v16; // ebp
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v25; // [rsp+40h] [rbp-48h]
  int v26; // [rsp+44h] [rbp-44h]
  int v28; // [rsp+A0h] [rbp+18h]

  SetConsoleCtrlHandler(PnpCleanCtrlHandler, 1);
  v7 = 0;
  v8 = 1;
  v9 = 0;
  v28 = 0;
  v10 = 0;
  v26 = 0;
  v11 = 0;
  v25 = 0;
  v12 = 0;
  if ( a1 <= 0 )
  {
    v15 = 0;
    v16 = 0;
    goto LABEL_26;
  }
  while ( 1 )
  {
    v13 = *(_QWORD *)(a2 + 8 * v9);
    if ( ((*(_WORD *)v13 - 45) & 0xFFFD) != 0 )
      goto LABEL_8;
    if ( !_wcsicmp((const wchar_t *)(v13 + 2), L"?")
      || !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"h")
      || !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"help") )
    {
      break;
    }
    if ( !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"NOREMOVE") )
    {
      v8 = 0;
LABEL_8:
      v7 = v28;
      goto LABEL_9;
    }
    if ( !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"DEVICES") )
    {
      v7 = 1;
      v28 = 1;
      goto LABEL_9;
    }
    if ( !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"DRIVERS") )
    {
      v26 = 1;
      goto LABEL_8;
    }
    if ( !_wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"FILES") )
    {
      v25 = 1;
      goto LABEL_8;
    }
    v14 = _wcsicmp((const wchar_t *)(*(_QWORD *)(a2 + 8 * v9) + 2LL), L"MAXCLEAN");
    v7 = v28;
    if ( v14 )
    {
      v12 = *(_QWORD *)(a2 + 8 * v9);
      goto LABEL_21;
    }
    v10 = 1;
LABEL_9:
    v9 = (unsigned int)(v9 + 1);
    if ( (int)v9 >= a1 )
      goto LABEL_21;
  }
  v7 = v28;
  v11 = 1;
LABEL_21:
  v15 = v26;
  v16 = v25;
  if ( !v7 && !v26 && !v25 )
LABEL_26:
    v11 = 1;
  if ( v12 )
  {
    PnpCleanSetupLogCallback(a4, 1, 0, "Unknown argument specified \"%ws\"", v12);
    goto LABEL_30;
  }
  if ( v11 )
  {
LABEL_30:
    PnpCleanSetupLogCallback(a4, 1, 0, "Processes devices and drivers that may be removed from the system.");
    PnpCleanSetupLogCallback(a4, 1, 0, "PNPCLEAN [/DEVICES] [/DRIVERS] [/FILES] [/MAXCLEAN] [/NOREMOVE]");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "         /DEVICES            Removes devices missing for the default time period");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(a4, 1, 0, "         /DRIVERS            Removes redundant drivers from the system");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "         /FILES              Removes files/directories that are no longer needed that are related to devices and drivers.");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(a4, 1, 0, "         /MAXCLEAN           Performs maximum cleanup");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "                             For /DEVICES this will set the time period to 0 so that");
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "                             every missing device will be processed for removal.");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "                             For /DRIVERS this will allow every driver that is not");
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "                             installed on some device to be processed for removal.");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(
      a4,
      1,
      0,
      "                             For /FILES this currently has no effect on what is removed.");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    PnpCleanSetupLogCallback(a4, 1, 0, "         /NOREMOVE           Evaluate items only, do not remove");
    PnpCleanSetupLogCallback(a4, 1, 0, byte_18000C0B5);
    return 13;
  }
  else
  {
    v17 = 0;
    if ( v7 )
    {
      v18 = (v8 == 0) | 2;
      if ( !v10 )
        v18 = v8 == 0;
      v19 = PnpCleanDevicesEx(
              v8 == 0,
              (unsigned int)PnpCleanSetupLogCallback,
              (unsigned int)PnpCleanMainStatusCallback,
              0,
              (__int64)PnpCleanSetupLogCallback,
              a4,
              v18);
      if ( v19 )
      {
        v17 = v19;
        PnpCleanSetupLogCallback(a4, 3, 0, "Failed to cleanup devices, Err = 0x%lx", v19);
      }
    }
    if ( v15 )
    {
      v20 = (v8 == 0) | 2;
      if ( !v10 )
        v20 = v8 == 0;
      v21 = PnpCleanDriversEx(
              v8 == 0,
              (__int64)PnpCleanSetupLogCallback,
              (__int64)PnpCleanMainStatusCallback,
              0,
              (__int64 (__fastcall *)())PnpCleanSetupLogCallback,
              a4,
              v20);
      if ( v21 )
      {
        v17 = v21;
        PnpCleanSetupLogCallback(a4, 3, 0, "Failed to cleanup drivers, Err = 0x%lx", v21);
      }
    }
    if ( v16 )
    {
      v22 = (v8 == 0) | 2;
      if ( !v10 )
        v22 = v8 == 0;
      v23 = PnpCleanFiles(
              (__int64)PnpCleanMainStatusCallback,
              0,
              (__int64 (__fastcall *)())PnpCleanSetupLogCallback,
              a4,
              v22);
      if ( v23 )
      {
        v17 = v23;
        PnpCleanSetupLogCallback(a4, 3, 0, "Failed to cleanup files, Err = 0x%lx", v23);
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x180001cd4  mov     [rsp+arg_8], rbx
0x180001cd9  mov     [rsp+arg_10], r8
0x180001cde  mov     [rsp+arg_0], ecx
0x180001ce2  push    rbp
0x180001ce3  push    rsi
0x180001ce4  push    rdi
0x180001ce5  push    r12
0x180001ce7  push    r13
0x180001ce9  push    r14
0x180001ceb  push    r15
0x180001ced  sub     rsp, 50h
0x180001cf1  mov     rdi, rdx
0x180001cf4  mov     ebx, ecx
0x180001cf6  mov     ebp, 1
0x180001cfb  lea     rcx, PnpCleanCtrlHandler; HandlerRoutine
0x180001d02  mov     edx, ebp; Add
0x180001d04  mov     rsi, r9
0x180001d07  call    cs:__imp_SetConsoleCtrlHandler
0x180001d0d  xor     ecx, ecx
0x180001d0f  mov     r14d, ebp
0x180001d12  xor     ebp, ebp
0x180001d14  mov     dword ptr [rsp+88h+arg_10], ecx
0x180001d1b  xor     r15d, r15d
0x180001d1e  mov     [rsp+88h+var_44], ecx
0x180001d22  xor     r13d, r13d
0x180001d25  mov     [rsp+88h+var_48], ecx
0x180001d29  xor     r12d, r12d
0x180001d2c  test    ebx, ebx
0x180001d2e  jle     loc_180001E93
0x180001d34  mov     rcx, [rdi+rbp*8]
0x180001d38  mov     edx, 0FFFDh
0x180001d3d  movzx   eax, word ptr [rcx]
0x180001d40  sub     ax, 2Dh ; '-'
0x180001d44  test    dx, ax
0x180001d47  jnz     short loc_180001DB8
0x180001d49  add     rcx, 2; String1
0x180001d4d  lea     rdx, String2; "?"
0x180001d54  call    cs:__imp__wcsicmp
0x180001d5a  test    eax, eax
0x180001d5c  jz      loc_180001E70
0x180001d62  mov     rcx, [rdi+rbp*8]
0x180001d66  lea     rdx, asc_18000BB78; "h"
0x180001d6d  add     rcx, 2; String1
0x180001d71  call    cs:__imp__wcsicmp
0x180001d77  test    eax, eax
0x180001d79  jz      loc_180001E70
0x180001d7f  mov     rcx, [rdi+rbp*8]
0x180001d83  lea     rdx, aHelp; "help"
0x180001d8a  add     rcx, 2; String1
0x180001d8e  call    cs:__imp__wcsicmp
0x180001d94  test    eax, eax
0x180001d96  jz      loc_180001E70
0x180001d9c  mov     rcx, [rdi+rbp*8]
0x180001da0  lea     rdx, aNoremove; "NOREMOVE"
0x180001da7  add     rcx, 2; String1
0x180001dab  call    cs:__imp__wcsicmp
0x180001db1  test    eax, eax
0x180001db3  jnz     short loc_180001DD3
0x180001db5  xor     r14d, r14d
0x180001db8  mov     ecx, dword ptr [rsp+88h+arg_10]
0x180001dbf  inc     ebp
0x180001dc1  cmp     ebp, [rsp+88h+arg_0]
0x180001dc8  jl      loc_180001D34
0x180001dce  jmp     loc_180001E7D
0x180001dd3  mov     rcx, [rdi+rbp*8]
0x180001dd7  lea     rdx, aDevices; "DEVICES"
0x180001dde  add     rcx, 2; String1
0x180001de2  call    cs:__imp__wcsicmp
0x180001de8  test    eax, eax
0x180001dea  jnz     short loc_180001DF8
0x180001dec  lea     ecx, [rax+1]
0x180001def  mov     dword ptr [rsp+88h+arg_10], ecx
0x180001df6  jmp     short loc_180001DBF
0x180001df8  mov     rcx, [rdi+rbp*8]
0x180001dfc  lea     rdx, aDrivers; "DRIVERS"
0x180001e03  add     rcx, 2; String1
0x180001e07  call    cs:__imp__wcsicmp
0x180001e0d  test    eax, eax
0x180001e0f  jnz     short loc_180001E1B
0x180001e11  mov     [rsp+88h+var_44], 1
0x180001e19  jmp     short loc_180001DB8
0x180001e1b  mov     rcx, [rdi+rbp*8]
0x180001e1f  lea     rdx, aFiles; "FILES"
0x180001e26  add     rcx, 2; String1
0x180001e2a  call    cs:__imp__wcsicmp
0x180001e30  test    eax, eax
0x180001e32  jnz     short loc_180001E41
0x180001e34  mov     [rsp+88h+var_48], 1
0x180001e3c  jmp     loc_180001DB8
0x180001e41  mov     rcx, [rdi+rbp*8]
0x180001e45  lea     rdx, aMaxclean; "MAXCLEAN"
0x180001e4c  add     rcx, 2; String1
0x180001e50  call    cs:__imp__wcsicmp
0x180001e56  mov     ecx, dword ptr [rsp+88h+arg_10]
0x180001e5d  test    eax, eax
0x180001e5f  jnz     short loc_180001E6A
0x180001e61  lea     r15d, [rax+1]
0x180001e65  jmp     loc_180001DBF
0x180001e6a  mov     r12, [rdi+rbp*8]
0x180001e6e  jmp     short loc_180001E7D
0x180001e70  mov     ecx, dword ptr [rsp+88h+arg_10]
0x180001e77  mov     r13d, 1
0x180001e7d  mov     edi, [rsp+88h+var_44]
0x180001e81  mov     ebp, [rsp+88h+var_48]
0x180001e85  test    ecx, ecx
0x180001e87  jnz     short loc_180001E9D
0x180001e89  test    edi, edi
0x180001e8b  jnz     short loc_180001E9D
0x180001e8d  test    ebp, ebp
0x180001e8f  jnz     short loc_180001E9D
0x180001e91  jmp     short loc_180001E97
0x180001e93  mov     edi, ecx
0x180001e95  mov     ebp, ecx
0x180001e97  mov     r13d, 1
0x180001e9d  test    r12, r12
0x180001ea0  jz      short loc_180001EC1
0x180001ea2  xor     r8d, r8d
0x180001ea5  mov     [rsp+88h+var_68], r12
0x180001eaa  lea     r9, aUnknownArgumen; "Unknown argument specified \"%ws\""
0x180001eb1  mov     rcx, rsi
0x180001eb4  lea     edi, [r8+1]
0x180001eb8  mov     edx, edi
0x180001eba  call    PnpCleanSetupLogCallback
0x180001ebf  jmp     short loc_180001ECF
0x180001ec1  test    r13d, r13d
0x180001ec4  jz      loc_180002060
0x180001eca  mov     edi, 1
0x180001ecf  lea     r9, aProcessesDevic; "Processes devices and drivers that may "...
0x180001ed6  xor     r8d, r8d
0x180001ed9  mov     edx, edi
0x180001edb  mov     rcx, rsi
0x180001ede  call    PnpCleanSetupLogCallback
0x180001ee3  lea     r9, aPnpcleanDevice; "PNPCLEAN [/DEVICES] [/DRIVERS] [/FILES]"...
0x180001eea  xor     r8d, r8d
0x180001eed  mov     edx, edi
0x180001eef  mov     rcx, rsi
0x180001ef2  call    PnpCleanSetupLogCallback
0x180001ef7  lea     rbx, byte_18000C0B5
0x180001efe  xor     r8d, r8d
0x180001f01  mov     r9, rbx
0x180001f04  mov     edx, edi
0x180001f06  mov     rcx, rsi
0x180001f09  call    PnpCleanSetupLogCallback
0x180001f0e  lea     r9, aDevicesRemoves; "         /DEVICES            Removes de"...
0x180001f15  xor     r8d, r8d
0x180001f18  mov     edx, edi
0x180001f1a  mov     rcx, rsi
0x180001f1d  call    PnpCleanSetupLogCallback
0x180001f22  mov     r9, rbx
0x180001f25  xor     r8d, r8d
0x180001f28  mov     edx, edi
0x180001f2a  mov     rcx, rsi
0x180001f2d  call    PnpCleanSetupLogCallback
0x180001f32  lea     r9, aDriversRemoves; "         /DRIVERS            Removes re"...
0x180001f39  xor     r8d, r8d
0x180001f3c  mov     edx, edi
0x180001f3e  mov     rcx, rsi
0x180001f41  call    PnpCleanSetupLogCallback
0x180001f46  mov     r9, rbx
0x180001f49  xor     r8d, r8d
0x180001f4c  mov     edx, edi
0x180001f4e  mov     rcx, rsi
0x180001f51  call    PnpCleanSetupLogCallback
0x180001f56  lea     r9, aFilesRemovesFi; "         /FILES              Removes fi"...
0x180001f5d  xor     r8d, r8d
0x180001f60  mov     edx, edi
0x180001f62  mov     rcx, rsi
0x180001f65  call    PnpCleanSetupLogCallback
0x180001f6a  mov     r9, rbx
0x180001f6d  xor     r8d, r8d
0x180001f70  mov     edx, edi
0x180001f72  mov     rcx, rsi
0x180001f75  call    PnpCleanSetupLogCallback
0x180001f7a  lea     r9, aMaxcleanPerfor; "         /MAXCLEAN           Performs m"...
0x180001f81  xor     r8d, r8d
0x180001f84  mov     edx, edi
0x180001f86  mov     rcx, rsi
0x180001f89  call    PnpCleanSetupLogCallback
0x180001f8e  mov     r9, rbx
0x180001f91  xor     r8d, r8d
0x180001f94  mov     edx, edi
0x180001f96  mov     rcx, rsi
0x180001f99  call    PnpCleanSetupLogCallback
0x180001f9e  lea     r9, aForDevicesThis; "                             For /DEVIC"...
0x180001fa5  xor     r8d, r8d
0x180001fa8  mov     edx, edi
0x180001faa  mov     rcx, rsi
0x180001fad  call    PnpCleanSetupLogCallback
0x180001fb2  lea     r9, aEveryMissingDe; "                             every miss"...
0x180001fb9  xor     r8d, r8d
0x180001fbc  mov     edx, edi
0x180001fbe  mov     rcx, rsi
0x180001fc1  call    PnpCleanSetupLogCallback
0x180001fc6  mov     r9, rbx
0x180001fc9  xor     r8d, r8d
0x180001fcc  mov     edx, edi
0x180001fce  mov     rcx, rsi
0x180001fd1  call    PnpCleanSetupLogCallback
0x180001fd6  lea     r9, aForDriversThis; "                             For /DRIVE"...
0x180001fdd  xor     r8d, r8d
0x180001fe0  mov     edx, edi
0x180001fe2  mov     rcx, rsi
0x180001fe5  call    PnpCleanSetupLogCallback
0x180001fea  lea     r9, aInstalledOnSom; "                             installed "...
0x180001ff1  xor     r8d, r8d
0x180001ff4  mov     edx, edi
0x180001ff6  mov     rcx, rsi
0x180001ff9  call    PnpCleanSetupLogCallback
0x180001ffe  mov     r9, rbx
0x180002001  xor     r8d, r8d
0x180002004  mov     edx, edi
0x180002006  mov     rcx, rsi
0x180002009  call    PnpCleanSetupLogCallback
0x18000200e  lea     r9, aForFilesThisCu; "                             For /FILES"...
0x180002015  xor     r8d, r8d
0x180002018  mov     edx, edi
0x18000201a  mov     rcx, rsi
0x18000201d  call    PnpCleanSetupLogCallback
0x180002022  mov     r9, rbx
0x180002025  xor     r8d, r8d
0x180002028  mov     edx, edi
0x18000202a  mov     rcx, rsi
0x18000202d  call    PnpCleanSetupLogCallback
0x180002032  lea     r9, aNoremoveEvalua; "         /NOREMOVE           Evaluate i"...
0x180002039  xor     r8d, r8d
0x18000203c  mov     edx, edi
0x18000203e  mov     rcx, rsi
0x180002041  call    PnpCleanSetupLogCallback
0x180002046  mov     r9, rbx
0x180002049  xor     r8d, r8d
0x18000204c  mov     edx, edi
0x18000204e  mov     rcx, rsi
0x180002051  call    PnpCleanSetupLogCallback
0x180002056  mov     ebx, 0Dh
0x18000205b  jmp     loc_180002167
0x180002060  xor     ebx, ebx
0x180002062  lea     rdx, PnpCleanSetupLogCallback
0x180002069  lea     r13, PnpCleanMainStatusCallback
0x180002070  lea     r12d, [rbx+3]
0x180002074  test    ecx, ecx
0x180002076  jz      short loc_1800020CA
0x180002078  xor     ecx, ecx
0x18000207a  mov     r8, r13
0x18000207d  test    r14d, r14d
0x180002080  setz    cl
0x180002083  mov     eax, ecx
0x180002085  or      eax, 2
0x180002088  test    r15d, r15d
0x18000208b  cmovz   eax, ecx
0x18000208e  xor     r9d, r9d
0x180002091  mov     [rsp+88h+var_58], eax
0x180002095  mov     [rsp+88h+var_60], rsi
0x18000209a  mov     [rsp+88h+var_68], rdx
0x18000209f  call    PnpCleanDevicesEx
0x1800020a4  test    eax, eax
0x1800020a6  jz      short loc_1800020C3
0x1800020a8  lea     r9, aFailedToCleanu; "Failed to cleanup devices, Err = 0x%lx"
0x1800020af  mov     dword ptr [rsp+88h+var_68], eax
0x1800020b3  xor     r8d, r8d
0x1800020b6  mov     edx, r12d
0x1800020b9  mov     rcx, rsi
0x1800020bc  mov     ebx, eax
0x1800020be  call    PnpCleanSetupLogCallback
0x1800020c3  lea     rdx, PnpCleanSetupLogCallback
0x1800020ca  test    edi, edi
0x1800020cc  jz      short loc_180002119
0x1800020ce  xor     ecx, ecx
0x1800020d0  mov     r8, r13
0x1800020d3  test    r14d, r14d
0x1800020d6  setz    cl
0x1800020d9  mov     eax, ecx
0x1800020db  or      eax, 2
0x1800020de  test    r15d, r15d
0x1800020e1  cmovz   eax, ecx
0x1800020e4  xor     r9d, r9d
0x1800020e7  mov     [rsp+88h+var_58], eax
0x1800020eb  mov     [rsp+88h+var_60], rsi
0x1800020f0  mov     [rsp+88h+var_68], rdx
0x1800020f5  call    PnpCleanDriversEx
0x1800020fa  test    eax, eax
0x1800020fc  jz      short loc_180002119
0x1800020fe  lea     r9, aFailedToCleanu_0; "Failed to cleanup drivers, Err = 0x%lx"
0x180002105  mov     dword ptr [rsp+88h+var_68], eax
0x180002109  xor     r8d, r8d
0x18000210c  mov     edx, r12d
0x18000210f  mov     rcx, rsi
0x180002112  mov     ebx, eax
0x180002114  call    PnpCleanSetupLogCallback
0x180002119  test    ebp, ebp
0x18000211b  jz      short loc_180002167
0x18000211d  xor     edx, edx
0x18000211f  lea     r8, PnpCleanSetupLogCallback
0x180002126  test    r14d, r14d
0x180002129  mov     r9, rsi
0x18000212c  mov     rcx, r13
0x18000212f  setz    dl
0x180002132  mov     eax, edx
0x180002134  or      eax, 2
0x180002137  test    r15d, r15d
0x18000213a  cmovz   eax, edx
  ... truncated ...
```
