# SvcEngUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18000947c`
- end: `0x180009587`
- name: `?SvcEngUpdateServiceStatus@@YAJKKK@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, DWORD, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800082c0`
- `0x180008390`
- `0x180008f30`
- `0x18000c200`

## callees

- `0x180001cf0`
- `0x18000947c`
- `0x18000a850`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009565`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009565`

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
  if ( (byte_18001B741 & 4) != 0 )
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
    McGenEventWrite_EventWriteTransfer(a1, EnterpriseDiagnosticsDcSvcEngUpdateServiceStatus, a3, 4, v11);
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
      ServiceStatus.dwCheckPoint = dword_18001B4F8++;
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
0x18000947c  push    rbp
0x18000947e  push    rbx
0x18000947f  push    rsi
0x180009480  push    rdi
0x180009481  push    r14
0x180009483  lea     rbp, [rsp-37h]
0x180009488  sub     rsp, 0A0h
0x18000948f  mov     rax, cs:__security_cookie
0x180009496  xor     rax, rsp
0x180009499  mov     [rbp+57h+var_30], rax
0x18000949d  test    cs:byte_18001B741, 4
0x1800094a4  mov     r14d, r8d
0x1800094a7  mov     esi, edx
0x1800094a9  mov     ebx, ecx
0x1800094ab  jz      short loc_180009502
0x1800094ad  lea     rax, [rbp+57h+var_90]
0x1800094b1  mov     [rbp+57h+var_88], edx
0x1800094b4  mov     [rbp+57h+var_60], rax
0x1800094b8  lea     rdx, EnterpriseDiagnosticsDcSvcEngUpdateServiceStatus
0x1800094bf  lea     rax, [rbp+57h+var_88]
0x1800094c3  mov     [rbp+57h+var_80], r8d
0x1800094c7  mov     [rbp+57h+var_50], rax
0x1800094cb  mov     r9d, 4
0x1800094d1  lea     rax, [rbp+57h+var_80]
0x1800094d5  mov     [rbp+57h+var_90], ecx
0x1800094d8  mov     [rbp+57h+var_40], rax
0x1800094dc  lea     rax, [rbp+57h+var_70]
0x1800094e0  mov     [rsp+0C0h+var_A0], rax
0x1800094e5  mov     [rbp+57h+var_58], 4
0x1800094ed  mov     [rbp+57h+var_48], 4
0x1800094f5  mov     [rbp+57h+var_38], 4
0x1800094fd  call    McGenEventWrite_EventWriteTransfer
0x180009502  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180009509  test    rcx, rcx
0x18000950c  jnz     short loc_180009515
0x18000950e  mov     edi, 8000FFFFh
0x180009513  jmp     short loc_18000956B
0x180009515  xor     eax, eax
0x180009517  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000951d  xor     edi, edi
0x18000951f  mov     cs:ServiceStatus.dwWin32ExitCode, esi
0x180009525  cmp     ebx, 2
0x180009528  mov     cs:ServiceStatus.dwWaitHint, r14d
0x18000952f  setnz   al
0x180009532  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x180009538  cmp     ebx, 4
0x18000953b  jz      short loc_180009558
0x18000953d  cmp     ebx, 1
0x180009540  jz      short loc_180009558
0x180009542  mov     eax, cs:dword_18001B4F8
0x180009548  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000954e  inc     eax
0x180009550  mov     cs:dword_18001B4F8, eax
0x180009556  jmp     short loc_18000955E
0x180009558  mov     cs:ServiceStatus.dwCheckPoint, edi
0x18000955e  lea     rdx, ServiceStatus; lpServiceStatus
0x180009565  call    cs:__imp_SetServiceStatus
0x18000956b  mov     eax, edi
0x18000956d  mov     rcx, [rbp+57h+var_30]
0x180009571  xor     rcx, rsp; StackCookie
0x180009574  call    __security_check_cookie
0x180009579  add     rsp, 0A0h
0x180009580  pop     r14
0x180009582  pop     rdi
0x180009583  pop     rsi
0x180009584  pop     rbx
0x180009585  pop     rbp
0x180009586  retn
```
