# PSetupGetLocalDataField

- ea: `0x180021020`
- end: `0x1800211d6`
- name: `PSetupGetLocalDataField`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002f48`
- `0x18000d624`
- `0x18001bc44`
- `0x180021020`
- `0x1800217e0`
- `0x180026ed4`
- `0x1800340b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021057`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021057`
- `SETUPAPI!SetupOpenFileQueue` at `0x180021087`
- `SETUPAPI!SetupOpenFileQueue` at `0x180021087`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002113c`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002113c`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180021105`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180021105`
- `SETUPAPI!SetupCloseFileQueue` at `0x180021118`
- `SETUPAPI!SetupCloseFileQueue` at `0x180021118`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x1800210a2`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x1800210a2`

## pseudocode

```c
__int64 __fastcall PSetupGetLocalDataField(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v4; // ebx
  HSPFILEQ v7; // rbp
  BOOL v8; // r15d
  PVOID inited; // r14
  int v10; // eax
  HDEVINFO DeviceInfoList; // rax
  HDEVINFO v12; // rbp
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  _BYTE v17[8]; // [rsp+50h] [rbp-88h] BYREF
  HSPFILEQ v18; // [rsp+58h] [rbp-80h]
  PVOID v19; // [rsp+60h] [rbp-78h]
  __int64 v20; // [rsp+70h] [rbp-68h]
  char v21; // [rsp+98h] [rbp-40h]

  v4 = 0;
  if ( !*(_DWORD *)a3 )
  {
    v16 = AllocStr(*(unsigned __int16 **)(a1 + 8));
    *(_QWORD *)(a3 + 8) = v16;
    if ( !v16 )
      return v4;
    return 1;
  }
  if ( *(_DWORD *)a3 != 1 )
  {
    if ( *(_DWORD *)a3 != 2 )
    {
      SetLastError(0x57u);
      return v4;
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "PSetupGetLocalDataField",
      L"Calling PSetupGetLocalDataField with DRIVER_FLAGS, version=%u, driver name='%ws'",
      *(unsigned int *)(a1 + 96),
      *(_QWORD *)(a1 + 8));
    if ( *(_DWORD *)(a1 + 96) >= 4u )
    {
      v7 = SetupOpenFileQueue();
      if ( v7 == (HSPFILEQ)-1LL )
      {
        v8 = 0;
        inited = 0;
      }
      else
      {
        inited = SetupInitDefaultQueueCallback(HWND_MESSAGE|0x2LL);
        v8 = inited != 0;
      }
      memset_0(v17, 0, 0x50u);
      v18 = v7;
      v4 = 1;
      v21 = 1;
      v19 = inited;
      v20 = a1;
      if ( v8 && (int)InstallV4Driver((struct _SETUP_CONTEXT *)v17) >= 0 )
        v10 = *(_DWORD *)(a1 + 80);
      else
        v10 = 0;
      *(_DWORD *)(a3 + 8) = v10;
      if ( inited )
        SetupTermDefaultQueueCallback(inited);
      if ( v7 != (HSPFILEQ)-1LL )
        SetupCloseFileQueue(v7);
      return v4;
    }
    *(_DWORD *)(a3 + 8) = 0;
    return 1;
  }
  *(_QWORD *)(a3 + 8) = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, 0);
  v12 = DeviceInfoList;
  if ( DeviceInfoList == (HDEVINFO)-1LL )
    return 0;
  if ( ParseInf(DeviceInfoList, (_QWORD *)a1, a2, 0, 0, -1, 0, 0, 0, 0) )
  {
    v14 = *(unsigned __int16 **)(a1 + 200);
    if ( !v14 || (v15 = AllocStr(v14), (*(_QWORD *)(a3 + 8) = v15) != 0) )
      v4 = 1;
  }
  DestroyOnlyPrinterDeviceInfoList(v12);
  return v4;
}

```

## disassembly

```asm
0x180021020  push    rbx
0x180021022  push    rbp
0x180021023  push    rsi
0x180021024  push    rdi
0x180021025  push    r14
0x180021027  push    r15
0x180021029  sub     rsp, 0A8h
0x180021030  mov     rdi, rcx
0x180021033  xor     ebx, ebx
0x180021035  mov     ecx, [r8]
0x180021038  mov     rsi, r8
0x18002103b  mov     r14d, edx
0x18002103e  test    ecx, ecx
0x180021040  jz      loc_1800211AD
0x180021046  sub     ecx, 1
0x180021049  jz      loc_18002112F
0x18002104f  cmp     ecx, 1
0x180021052  jz      short loc_180021062
0x180021054  lea     ecx, [rbx+57h]; dwErrCode
0x180021057  call    cs:__imp_SetLastError
0x18002105d  jmp     loc_1800211C4
0x180021062  mov     r9, [rdi+8]
0x180021066  lea     rdx, aCallingPsetupg; "Calling PSetupGetLocalDataField with DR"...
0x18002106d  mov     r8d, [rdi+60h]
0x180021071  lea     rcx, aPsetupgetlocal_0; "PSetupGetLocalDataField"
0x180021078  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002107d  cmp     dword ptr [rdi+60h], 4
0x180021081  jb      loc_180021123
0x180021087  call    cs:__imp_SetupOpenFileQueue
0x18002108d  mov     rbp, rax
0x180021090  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021094  jnz     short loc_18002109E
0x180021096  xor     r15d, r15d
0x180021099  xor     r14d, r14d
0x18002109c  jmp     short loc_1800210B5
0x18002109e  or      rcx, 0FFFFFFFFFFFFFFFFh; OwnerWindow
0x1800210a2  call    cs:__imp_SetupInitDefaultQueueCallback
0x1800210a8  xor     r15d, r15d
0x1800210ab  mov     r14, rax
0x1800210ae  test    rax, rax
0x1800210b1  setnz   r15b
0x1800210b5  xor     edx, edx; Val
0x1800210b7  lea     rcx, [rsp+0D8h+var_88]; void *
0x1800210bc  lea     r8d, [rdx+50h]; Size
0x1800210c0  call    memset_0
0x1800210c5  mov     [rsp+0D8h+var_80], rbp
0x1800210ca  mov     ebx, 1
0x1800210cf  mov     [rsp+0D8h+var_40], bl
0x1800210d6  mov     [rsp+0D8h+var_78], r14
0x1800210db  mov     [rsp+0D8h+var_68], rdi
0x1800210e0  test    r15d, r15d
0x1800210e3  jz      short loc_1800210F8
0x1800210e5  lea     rcx, [rsp+0D8h+var_88]; struct _SETUP_CONTEXT *
0x1800210ea  call    InstallV4Driver
0x1800210ef  test    eax, eax
0x1800210f1  js      short loc_1800210F8
0x1800210f3  mov     eax, [rdi+50h]
0x1800210f6  jmp     short loc_1800210FA
0x1800210f8  xor     eax, eax
0x1800210fa  mov     [rsi+8], eax
0x1800210fd  test    r14, r14
0x180021100  jz      short loc_18002110B
0x180021102  mov     rcx, r14; Context
0x180021105  call    cs:__imp_SetupTermDefaultQueueCallback
0x18002110b  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18002110f  jz      loc_1800211C4
0x180021115  mov     rcx, rbp; QueueHandle
0x180021118  call    cs:__imp_SetupCloseFileQueue
0x18002111e  jmp     loc_1800211C4
0x180021123  mov     dword ptr [rsi+8], 0
0x18002112a  jmp     loc_1800211BF
0x18002112f  xor     edx, edx; hwndParent
0x180021131  mov     [r8+8], rbx
0x180021135  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18002113c  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180021142  mov     rbp, rax
0x180021145  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021149  jnz     short loc_18002114F
0x18002114b  xor     eax, eax
0x18002114d  jmp     short loc_1800211C6
0x18002114f  mov     [rsp+0D8h+var_90], rbx
0x180021154  xor     r9d, r9d
0x180021157  mov     [rsp+0D8h+var_98], rbx
0x18002115c  mov     r8d, r14d
0x18002115f  mov     [rsp+0D8h+var_A0], ebx
0x180021163  mov     rdx, rdi
0x180021166  mov     [rsp+0D8h+var_A8], rbx
0x18002116b  mov     rcx, rbp
0x18002116e  mov     [rsp+0D8h+var_B0], 0FFFFFFFFFFFFFFFFh
0x180021177  mov     [rsp+0D8h+var_B8], ebx
0x18002117b  call    ParseInf
0x180021180  test    eax, eax
0x180021182  jz      short loc_1800211A3
0x180021184  mov     rcx, [rdi+0C8h]; unsigned __int16 *
0x18002118b  test    rcx, rcx
0x18002118e  jz      short loc_18002119E
0x180021190  call    AllocStr
0x180021195  mov     [rsi+8], rax
0x180021199  test    rax, rax
0x18002119c  jz      short loc_1800211A3
0x18002119e  mov     ebx, 1
0x1800211a3  mov     rcx, rbp
0x1800211a6  call    DestroyOnlyPrinterDeviceInfoList
0x1800211ab  jmp     short loc_1800211C4
0x1800211ad  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800211b1  call    AllocStr
0x1800211b6  mov     [rsi+8], rax
0x1800211ba  test    rax, rax
0x1800211bd  jz      short loc_1800211C4
0x1800211bf  mov     ebx, 1
0x1800211c4  mov     eax, ebx
0x1800211c6  add     rsp, 0A8h
0x1800211cd  pop     r15
0x1800211cf  pop     r14
0x1800211d1  pop     rdi
0x1800211d2  pop     rsi
0x1800211d3  pop     rbp
0x1800211d4  pop     rbx
0x1800211d5  retn
```
