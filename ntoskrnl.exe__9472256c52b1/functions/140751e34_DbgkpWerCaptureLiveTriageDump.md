# DbgkpWerCaptureLiveTriageDump

- ea: `0x140751e34`
- end: `0x140751fa5`
- name: `DbgkpWerCaptureLiveTriageDump`
- size: `369`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1407522b4`

## callees

- `0x1402a2f90`
- `0x1402e38d0`
- `0x140542a90`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x140751e34`
- `0x1407525cc`
- `0x140adc04c`
- `0x140bb1410`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140751f5e`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140751f5e`

## string_xrefs

- `0x140751f01`: `DBGK: KeCapturePersistentThreadState failed\n`
- `0x140751e5d`: `DBGK: Creating mini live dump. ComponentName %ws\n`
- `0x140751f4f`: `DBGK: DbgkpWerWriteTriageDump failed, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall DbgkpWerCaptureLiveTriageDump(__int64 a1)
{
  __int64 Pool2; // rax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  struct _CONTEXT ContextRecord; // [rsp+40h] [rbp-4E8h] BYREF

  DbgPrintEx(5u, 3u, "DBGK: Creating mini live dump. ComponentName %ws\n", a1);
  *(_DWORD *)(a1 + 80) = 67108860;
  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
  Pool2 = ExAllocatePool2(256, 0x40000, 1466393156);
  *(_QWORD *)(a1 + 136) = Pool2;
  if ( Pool2 )
  {
    RtlCaptureContext(&ContextRecord);
    v4 = KeCapturePersistentThreadState(
           (__int64)&ContextRecord,
           0,
           *(_DWORD *)(a1 + 32),
           *(_QWORD *)(a1 + 40),
           *(_QWORD *)(a1 + 48),
           *(_QWORD *)(a1 + 56),
           *(_QWORD *)(a1 + 64),
           *(_QWORD *)(a1 + 136));
    if ( v4 )
    {
      *(_DWORD *)(a1 + 144) = v4;
      v5 = DbgkpWerInvokeCallbacks(a1);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v6 = DbgkpWerWriteTriageDump(a1);
        v3 = v6;
        if ( v6 >= 0 )
        {
          v7 = WerLiveKernelSubmitReport(*(_QWORD *)(a1 + 96), 0);
          v3 = v7;
          if ( v7 >= 0 )
            *(_DWORD *)(a1 + 104) |= 1u;
          else
            DbgPrintEx(
              5u,
              0,
              "DBGK: DbgkpWerCaptureLiveTriageDump: WerLiveKernelSubmitReport failed with status 0x%X\n",
              (unsigned int)v7);
        }
        else
        {
          DbgPrintEx(5u, 0, "DBGK: DbgkpWerWriteTriageDump failed, status 0x%X\n", (unsigned int)v6);
        }
      }
      else
      {
        DbgPrintEx(5u, 0, "DBGK: DbgkpWerInvokeCallbacks failed, status 0x%X\n", (unsigned int)v5);
      }
    }
    else
    {
      DbgPrintEx(5u, 0, "DBGK: KeCapturePersistentThreadState failed\n");
      return (unsigned int)-1073741823;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v3;
}

```

## disassembly

```asm
0x140751e34  mov     [rsp+arg_8], rbx
0x140751e39  mov     [rsp+arg_10], rsi
0x140751e3e  push    rdi
0x140751e3f  sub     rsp, 520h
0x140751e46  mov     rax, cs:__security_cookie
0x140751e4d  xor     rax, rsp
0x140751e50  mov     [rsp+528h+var_18], rax
0x140751e58  mov     edx, 3; Level
0x140751e5d  lea     r8, aDbgkCreatingMi; "DBGK: Creating mini live dump. Componen"...
0x140751e64  mov     rdi, rcx
0x140751e67  mov     r9, rcx
0x140751e6a  lea     esi, [rdx+2]
0x140751e6d  mov     ecx, esi; ComponentId
0x140751e6f  call    DbgPrintEx
0x140751e74  xor     edx, edx; Val
0x140751e76  mov     dword ptr [rdi+50h], 3FFFFFCh
0x140751e7d  mov     r8d, 4D0h; Size
0x140751e83  lea     rcx, [rsp+528h+ContextRecord]; void *
0x140751e88  call    memset_0
0x140751e8d  mov     edx, 40000h
0x140751e92  mov     ecx, 100h
0x140751e97  mov     r8d, 57676244h
0x140751e9d  call    ExAllocatePool2
0x140751ea2  mov     [rdi+88h], rax
0x140751ea9  test    rax, rax
0x140751eac  jnz     short loc_140751EB8
0x140751eae  mov     ebx, 0C0000017h
0x140751eb3  jmp     loc_140751F7D
0x140751eb8  lea     rcx, [rsp+528h+ContextRecord]; ContextRecord
0x140751ebd  call    RtlCaptureContext
0x140751ec2  mov     rax, [rdi+88h]
0x140751ec9  lea     rcx, [rsp+528h+ContextRecord]
0x140751ece  mov     r9, [rdi+28h]
0x140751ed2  xor     edx, edx
0x140751ed4  mov     r8d, [rdi+20h]
0x140751ed8  mov     [rsp+528h+var_4F0], rax
0x140751edd  mov     rax, [rdi+40h]
0x140751ee1  mov     [rsp+528h+var_4F8], rax
0x140751ee6  mov     rax, [rdi+38h]
0x140751eea  mov     [rsp+528h+var_500], rax
0x140751eef  mov     rax, [rdi+30h]
0x140751ef3  mov     [rsp+528h+var_508], rax
0x140751ef8  call    KeCapturePersistentThreadState
0x140751efd  test    eax, eax
0x140751eff  jnz     short loc_140751F18
0x140751f01  lea     r8, aDbgkKecapturep; "DBGK: KeCapturePersistentThreadState fa"...
0x140751f08  xor     edx, edx; Level
0x140751f0a  mov     ecx, esi; ComponentId
0x140751f0c  call    DbgPrintEx
0x140751f11  mov     ebx, 0C0000001h
0x140751f16  jmp     short loc_140751F7D
0x140751f18  mov     rcx, rdi
0x140751f1b  mov     [rdi+90h], eax
0x140751f21  call    DbgkpWerInvokeCallbacks
0x140751f26  mov     ebx, eax
0x140751f28  test    eax, eax
0x140751f2a  jns     short loc_140751F41
0x140751f2c  lea     r8, aDbgkDbgkpwerin; "DBGK: DbgkpWerInvokeCallbacks failed, s"...
0x140751f33  mov     r9d, eax
0x140751f36  xor     edx, edx; Level
0x140751f38  mov     ecx, esi; ComponentId
0x140751f3a  call    DbgPrintEx
0x140751f3f  jmp     short loc_140751F7D
0x140751f41  mov     rcx, rdi
0x140751f44  call    DbgkpWerWriteTriageDump
0x140751f49  mov     ebx, eax
0x140751f4b  test    eax, eax
0x140751f4d  jns     short loc_140751F58
0x140751f4f  lea     r8, aDbgkDbgkpwerwr; "DBGK: DbgkpWerWriteTriageDump failed, s"...
0x140751f56  jmp     short loc_140751F33
0x140751f58  mov     rcx, [rdi+60h]
0x140751f5c  xor     edx, edx
0x140751f5e  call    cs:__imp_WerLiveKernelSubmitReport
0x140751f65  nop     dword ptr [rax+rax+00h]
0x140751f6a  mov     ebx, eax
0x140751f6c  test    eax, eax
0x140751f6e  jns     short loc_140751F79
0x140751f70  lea     r8, aDbgkDbgkpwerca; "DBGK: DbgkpWerCaptureLiveTriageDump: We"...
0x140751f77  jmp     short loc_140751F33
0x140751f79  or      dword ptr [rdi+68h], 1
0x140751f7d  mov     eax, ebx
0x140751f7f  mov     rcx, [rsp+528h+var_18]
0x140751f87  xor     rcx, rsp; StackCookie
0x140751f8a  call    __security_check_cookie
0x140751f8f  lea     r11, [rsp+528h+var_8]
0x140751f97  mov     rbx, [r11+18h]
0x140751f9b  mov     rsi, [r11+20h]
0x140751f9f  mov     rsp, r11
0x140751fa2  pop     rdi
0x140751fa3  retn
```
