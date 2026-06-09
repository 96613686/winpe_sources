# SvcEngUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18000650c`
- end: `0x180006617`
- name: `?SvcEngUpdateServiceStatus@@YAJKKK@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, DWORD, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800061b0`
- `0x180006240`
- `0x180006430`

## callees

- `0x180001a70`
- `0x180004968`
- `0x18000650c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800065f5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800065f5`

## pseudocode

```c
__int64 __fastcall SvcEngUpdateServiceStatus(__int64 a1, DWORD a2, __int64 a3)
{
  DWORD v3; // r14d
  DWORD v5; // ebx
  unsigned int v6; // edi
  int v8; // [rsp+30h] [rbp-39h] BYREF
  DWORD v9; // [rsp+38h] [rbp-31h] BYREF
  int v10; // [rsp+40h] [rbp-29h] BYREF
  char v11[16]; // [rsp+50h] [rbp-19h] BYREF
  int *v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  DWORD *v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  int *v16; // [rsp+80h] [rbp+17h]
  __int64 v17; // [rsp+88h] [rbp+1Fh]

  v3 = a3;
  v5 = a1;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
  {
    v9 = a2;
    v12 = &v8;
    v10 = a3;
    v14 = &v9;
    v8 = a1;
    v16 = &v10;
    v13 = 4;
    v15 = 4;
    v17 = 4;
    McGenEventWrite_EventWriteTransfer(a1, PushRouterSvcEngUpdateServiceStatus, a3, 4, v11);
  }
  if ( hServiceStatus )
  {
    ServiceStatus.dwCurrentState = v5;
    v6 = 0;
    ServiceStatus.dwWin32ExitCode = a2;
    ServiceStatus.dwWaitHint = v3;
    ServiceStatus.dwControlsAccepted = v5 != 2;
    if ( v5 == 4 || v5 == 1 )
      ServiceStatus.dwCheckPoint = 0;
    else
      ServiceStatus.dwCheckPoint = dword_18001C534++;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v6;
}

```

## disassembly

```asm
0x18000650c  push    rbp
0x18000650e  push    rbx
0x18000650f  push    rsi
0x180006510  push    rdi
0x180006511  push    r14
0x180006513  lea     rbp, [rsp-37h]
0x180006518  sub     rsp, 0A0h
0x18000651f  mov     rax, cs:__security_cookie
0x180006526  xor     rax, rsp
0x180006529  mov     [rbp+57h+var_30], rax
0x18000652d  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180006534  mov     r14d, r8d
0x180006537  mov     esi, edx
0x180006539  mov     ebx, ecx
0x18000653b  jz      short loc_180006592
0x18000653d  lea     rax, [rbp+57h+var_90]
0x180006541  mov     [rbp+57h+var_88], edx
0x180006544  mov     [rbp+57h+var_60], rax
0x180006548  lea     rdx, PushRouterSvcEngUpdateServiceStatus
0x18000654f  lea     rax, [rbp+57h+var_88]
0x180006553  mov     [rbp+57h+var_80], r8d
0x180006557  mov     [rbp+57h+var_50], rax
0x18000655b  mov     r9d, 4
0x180006561  lea     rax, [rbp+57h+var_80]
0x180006565  mov     [rbp+57h+var_90], ecx
0x180006568  mov     [rbp+57h+var_40], rax
0x18000656c  lea     rax, [rbp+57h+var_70]
0x180006570  mov     [rsp+0C0h+var_A0], rax
0x180006575  mov     [rbp+57h+var_58], 4
0x18000657d  mov     [rbp+57h+var_48], 4
0x180006585  mov     [rbp+57h+var_38], 4
0x18000658d  call    McGenEventWrite_EventWriteTransfer
0x180006592  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180006599  test    rcx, rcx
0x18000659c  jnz     short loc_1800065A5
0x18000659e  mov     edi, 8000FFFFh
0x1800065a3  jmp     short loc_1800065FB
0x1800065a5  xor     eax, eax
0x1800065a7  mov     cs:ServiceStatus.dwCurrentState, ebx
0x1800065ad  xor     edi, edi
0x1800065af  mov     cs:ServiceStatus.dwWin32ExitCode, esi
0x1800065b5  cmp     ebx, 2
0x1800065b8  mov     cs:ServiceStatus.dwWaitHint, r14d
0x1800065bf  setnz   al
0x1800065c2  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x1800065c8  cmp     ebx, 4
0x1800065cb  jz      short loc_1800065E8
0x1800065cd  cmp     ebx, 1
0x1800065d0  jz      short loc_1800065E8
0x1800065d2  mov     eax, cs:dword_18001C534
0x1800065d8  mov     cs:ServiceStatus.dwCheckPoint, eax
0x1800065de  inc     eax
0x1800065e0  mov     cs:dword_18001C534, eax
0x1800065e6  jmp     short loc_1800065EE
0x1800065e8  mov     cs:ServiceStatus.dwCheckPoint, edi
0x1800065ee  lea     rdx, ServiceStatus; lpServiceStatus
0x1800065f5  call    cs:__imp_SetServiceStatus
0x1800065fb  mov     eax, edi
0x1800065fd  mov     rcx, [rbp+57h+var_30]
0x180006601  xor     rcx, rsp; StackCookie
0x180006604  call    __security_check_cookie
0x180006609  add     rsp, 0A0h
0x180006610  pop     r14
0x180006612  pop     rdi
0x180006613  pop     rsi
0x180006614  pop     rbx
0x180006615  pop     rbp
0x180006616  retn
```
