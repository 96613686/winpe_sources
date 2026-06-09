# DumpRunningProcessesLoadedDllDetector_DeleteTask(void)

- ea: `0x18008a4c4`
- end: `0x18008a872`
- name: `?DumpRunningProcessesLoadedDllDetector_DeleteTask@@YAKXZ`
- size: `942`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008b4f0`

## callees

- `0x180012920`
- `0x18008a4c4`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008a71e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008a71e`
- `OLEAUT32!__imp_SysAllocString` at `0x18008a5eb`
- `OLEAUT32!__imp_SysAllocString` at `0x18008a64d`
- `OLEAUT32!__imp_SysAllocString` at `0x18008a5eb`
- `OLEAUT32!__imp_SysAllocString` at `0x18008a64d`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a7f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a800`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a7f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18008a800`
- `OLEAUT32!__imp_VariantInit` at `0x18008a52a`
- `OLEAUT32!__imp_VariantInit` at `0x18008a52a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008a550`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008a550`

## string_xrefs

- `0x18008a5f9`: `Failed to allocate task folder name`
- `0x18008a65b`: `Failed to allocate task name`
- `0x18008a4f1`: `PcaDumpRunningProcessesLoadedDllDetect`
- `0x18008a55c`: `Failed to create a task scheduler [%x]`
- `0x18008a502`: `Deleting %ws task...`
- `0x18008a6c3`: `Task %ws is currently running, stopping it before deletion`
- `0x18008a4dd`: `DumpRunningProcessesLoadedDllDetector_DeleteTask`
- `0x18008a700`: `Successfully stopped task %ws`
- `0x18008a6f1`: `Failed to stop running task %ws [%x]`
- `0x18008a73a`: `Failed to get task state [%x]`
- `0x18008a726`: `Task %ws state: %d (not running)`
- `0x18008a76b`: `Failed to get task %ws [%x]`
- `0x18008a75c`: `Task %ws does not exist, nothing to delete`
- `0x18008a7b2`: `Task %ws does not exist, nothing to delete`
- `0x18008a7d3`: `Successfully deleted task %ws`
- `0x18008a7c1`: `Failed to delete task [%x]`

## pseudocode

```c
__int64 DumpRunningProcessesLoadedDllDetector_DeleteTask(void)
{
  OLECHAR *v0; // rsi
  OLECHAR *v1; // rdi
  HRESULT v2; // ebx
  const char *v3; // r9
  int v4; // r8d
  __int64 v5; // rax
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v7; // rax
  const char *v8; // r9
  int v9; // r8d
  BSTR v10; // rax
  int v11; // eax
  const char *v12; // r9
  int v13; // r8d
  int v14; // ecx
  const char *v15; // r9
  int v16; // r8d
  int v17; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-79h] BYREF
  __int128 v20; // [rsp+50h] [rbp-59h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-49h]
  VARIANTARG v22; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v23; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG v24; // [rsp+B0h] [rbp+7h] BYREF
  int v25; // [rsp+110h] [rbp+67h] BYREF
  __int64 v26; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+120h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+128h] [rbp+7Fh] BYREF

  v0 = 0;
  ppv = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  AslLogCallPrintf(
    3,
    (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask",
    1700,
    (unsigned int)"Deleting %ws task...");
  VariantInit(&pvarg);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v2 < 0 )
  {
    v3 = "Failed to create a task scheduler [%x]";
    v4 = 1710;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask", v4, (_DWORD)v3);
    goto LABEL_33;
  }
  v20 = *(_OWORD *)&pvarg.vt;
  v5 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v22 = pvarg;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v5 + 80);
  v23 = pvarg;
  v24 = pvarg;
  v2 = v6(ppv, &v24, &v23, &v22, &v20);
  if ( v2 < 0 )
  {
    v3 = "Failed to connect to scheduler [%x]";
    v4 = 1717;
    goto LABEL_3;
  }
  v7 = SysAllocString(L"Microsoft\\Windows\\Application Experience");
  v0 = v7;
  if ( !v7 )
  {
    v8 = "Failed to allocate task folder name";
    v9 = 1725;
LABEL_8:
    v2 = -2147024888;
    AslLogCallPrintf(1, (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask", v9, (_DWORD)v8);
    goto LABEL_33;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v7, &v27);
  if ( v2 < 0 )
  {
    v3 = "Failed to get scheduler folder [%x]";
    v4 = 1732;
    goto LABEL_3;
  }
  v10 = SysAllocString(L"PcaDumpRunningProcessesLoadedDllDetect");
  v1 = v10;
  if ( !v10 )
  {
    v8 = "Failed to allocate task name";
    v9 = 1740;
    goto LABEL_8;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v27 + 104LL))(v27, v10, &v26);
  if ( v11 >= 0 )
  {
    if ( v26 )
    {
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 72LL))(v26, &v25) < 0 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask",
          1768,
          (unsigned int)"Failed to get task state [%x]");
        goto LABEL_27;
      }
      if ( v25 != 4 )
      {
        v12 = "Task %ws state: %d (not running)";
        v13 = 1765;
        v14 = 3;
LABEL_26:
        AslLogCallPrintf(v14, (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask", v13, (_DWORD)v12);
LABEL_27:
        v17 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v27 + 120LL))(v27, v1, 0);
        v2 = v17;
        if ( v17 >= 0 )
        {
          v15 = "Successfully deleted task %ws";
          v16 = 1795;
        }
        else
        {
          if ( v17 != -2147024894 )
          {
            v3 = "Failed to delete task [%x]";
            v4 = 1790;
            goto LABEL_3;
          }
          v15 = "Task %ws does not exist, nothing to delete";
          v16 = 1787;
        }
        goto LABEL_32;
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask",
        1751,
        (unsigned int)"Task %ws is currently running, stopping it before deletion");
      if ( (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 184LL))(v26, 0) >= 0 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask",
          1759,
          (unsigned int)"Successfully stopped task %ws");
        Sleep(0x3E8u);
        goto LABEL_27;
      }
      v12 = "Failed to stop running task %ws [%x]";
      v13 = 1756;
LABEL_25:
      v14 = 1;
      goto LABEL_26;
    }
LABEL_24:
    v12 = "Failed to get task %ws [%x]";
    v13 = 1777;
    goto LABEL_25;
  }
  if ( v11 != -2147024894 )
    goto LABEL_24;
  v15 = "Task %ws does not exist, nothing to delete";
  v16 = 1773;
LABEL_32:
  AslLogCallPrintf(3, (unsigned int)"DumpRunningProcessesLoadedDllDetector_DeleteTask", v16, (_DWORD)v15);
  v2 = 0;
LABEL_33:
  SysFreeString(v0);
  SysFreeString(v1);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v2 < 0 )
  {
    if ( (v2 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v2;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008a4c4  push    rbp
0x18008a4c6  push    rbx
0x18008a4c7  push    rsi
0x18008a4c8  push    rdi
0x18008a4c9  push    r12
0x18008a4cb  push    r13
0x18008a4cd  push    r15
0x18008a4cf  lea     rbp, [rsp-27h]
0x18008a4d4  sub     rsp, 0D0h
0x18008a4db  xor     esi, esi
0x18008a4dd  lea     r15, aDumprunningpro; "DumpRunningProcessesLoadedDllDetector_D"...
0x18008a4e4  xorps   xmm0, xmm0
0x18008a4e7  mov     [rbp+57h+arg_18], rsi
0x18008a4eb  xor     eax, eax
0x18008a4ed  mov     [rbp+57h+arg_10], rsi
0x18008a4f1  lea     r13, aPcadumprunning_1; "PcaDumpRunningProcessesLoadedDllDetect"
0x18008a4f8  mov     [rbp+57h+arg_8], rsi
0x18008a4fc  lea     ecx, [rsi+3]
0x18008a4ff  mov     [rbp+57h+arg_0], esi
0x18008a502  lea     r9, aDeletingWsTask; "Deleting %ws task..."
0x18008a509  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18008a50d  mov     r8d, 6A4h
0x18008a513  mov     [rsp+100h+ppv], r13
0x18008a518  mov     rdx, r15
0x18008a51b  xor     edi, edi
0x18008a51d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18008a521  call    AslLogCallPrintf
0x18008a526  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18008a52a  call    cs:__imp_VariantInit
0x18008a530  lea     rax, [rbp+57h+arg_18]
0x18008a534  xor     edx, edx; pUnkOuter
0x18008a536  lea     r12d, [rsi+1]
0x18008a53a  mov     [rsp+100h+ppv], rax; ppv
0x18008a53f  mov     r8d, r12d; dwClsContext
0x18008a542  lea     r9, IID_ITaskService; riid
0x18008a549  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008a550  call    cs:__imp_CoCreateInstance
0x18008a556  mov     ebx, eax
0x18008a558  test    eax, eax
0x18008a55a  jns     short loc_18008A57D
0x18008a55c  lea     r9, aFailedToCreate_6; "Failed to create a task scheduler [%x]"
0x18008a563  mov     r8d, 6AEh
0x18008a569  mov     rdx, r15
0x18008a56c  mov     ecx, r12d
0x18008a56f  mov     dword ptr [rsp+100h+ppv], eax
0x18008a573  call    AslLogCallPrintf
0x18008a578  jmp     loc_18008A7F4
0x18008a57d  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18008a581  lea     rdx, [rbp+57h+var_B0]
0x18008a585  mov     rcx, [rbp+57h+arg_18]
0x18008a589  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18008a58e  lea     r9, [rbp+57h+var_90]
0x18008a592  mov     [rsp+100h+ppv], rdx
0x18008a597  lea     r8, [rbp+57h+var_70]
0x18008a59b  lea     rdx, [rbp+57h+var_50]
0x18008a59f  movaps  [rbp+57h+var_B0], xmm1
0x18008a5a3  mov     rax, [rcx]
0x18008a5a6  movsd   [rbp+57h+var_A0], xmm0
0x18008a5ab  movaps  [rbp+57h+var_90], xmm1
0x18008a5af  movsd   [rbp+57h+var_80], xmm0
0x18008a5b4  mov     rax, [rax+50h]
0x18008a5b8  movaps  [rbp+57h+var_70], xmm1
0x18008a5bc  movsd   [rbp+57h+var_60], xmm0
0x18008a5c1  movaps  [rbp+57h+var_50], xmm1
0x18008a5c5  movsd   [rbp+57h+var_40], xmm0
0x18008a5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5cf  mov     ebx, eax
0x18008a5d1  test    eax, eax
0x18008a5d3  jns     short loc_18008A5E4
0x18008a5d5  lea     r9, aFailedToConnec; "Failed to connect to scheduler [%x]"
0x18008a5dc  mov     r8d, 6B5h
0x18008a5e2  jmp     short loc_18008A569
0x18008a5e4  lea     rcx, psz; "Microsoft\\Windows\\Application Experie"...
0x18008a5eb  call    cs:__imp_SysAllocString
0x18008a5f1  mov     rsi, rax
0x18008a5f4  test    rax, rax
0x18008a5f7  jnz     short loc_18008A61B
0x18008a5f9  lea     r9, aFailedToAlloca_6; "Failed to allocate task folder name"
0x18008a600  mov     r8d, 6BDh
0x18008a606  mov     rdx, r15
0x18008a609  mov     ecx, r12d
0x18008a60c  mov     ebx, 80070008h
0x18008a611  call    AslLogCallPrintf
0x18008a616  jmp     loc_18008A7F4
0x18008a61b  mov     rcx, [rbp+57h+arg_18]
0x18008a61f  lea     r8, [rbp+57h+arg_10]
0x18008a623  mov     rdx, rsi
0x18008a626  mov     rax, [rcx]
0x18008a629  mov     rax, [rax+38h]
0x18008a62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a632  mov     ebx, eax
0x18008a634  test    eax, eax
0x18008a636  jns     short loc_18008A64A
0x18008a638  lea     r9, aFailedToGetSch; "Failed to get scheduler folder [%x]"
0x18008a63f  mov     r8d, 6C4h
0x18008a645  jmp     loc_18008A569
0x18008a64a  mov     rcx, r13; psz
0x18008a64d  call    cs:__imp_SysAllocString
0x18008a653  mov     rdi, rax
0x18008a656  test    rax, rax
0x18008a659  jnz     short loc_18008A66A
0x18008a65b  lea     r9, aFailedToAlloca_17; "Failed to allocate task name"
0x18008a662  mov     r8d, 6CCh
0x18008a668  jmp     short loc_18008A606
0x18008a66a  mov     rcx, [rbp+57h+arg_10]
0x18008a66e  lea     r8, [rbp+57h+arg_8]
0x18008a672  mov     rdx, rdi
0x18008a675  mov     rax, [rcx]
0x18008a678  mov     rax, [rax+68h]
0x18008a67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a681  test    eax, eax
0x18008a683  js      loc_18008A755
0x18008a689  mov     rcx, [rbp+57h+arg_8]
0x18008a68d  test    rcx, rcx
0x18008a690  jz      loc_18008A76B
0x18008a696  mov     rax, [rcx]
0x18008a699  lea     rdx, [rbp+57h+arg_0]
0x18008a69d  mov     rax, [rax+48h]
0x18008a6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a6a6  mov     rdx, r15
0x18008a6a9  test    eax, eax
0x18008a6ab  js      loc_18008A73A
0x18008a6b1  mov     eax, [rbp+57h+arg_0]
0x18008a6b4  cmp     eax, 4
0x18008a6b7  jnz     short loc_18008A726
0x18008a6b9  lea     ebx, [rax-1]
0x18008a6bc  mov     [rsp+100h+ppv], r13
0x18008a6c1  mov     ecx, ebx
0x18008a6c3  lea     r9, aTaskWsIsCurren; "Task %ws is currently running, stopping"...
0x18008a6ca  mov     r8d, 6D7h
0x18008a6d0  call    AslLogCallPrintf
0x18008a6d5  mov     rcx, [rbp+57h+arg_8]
0x18008a6d9  xor     edx, edx
0x18008a6db  mov     rax, [rcx]
0x18008a6de  mov     rax, [rax+0B8h]
0x18008a6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a6ea  mov     rdx, r15
0x18008a6ed  test    eax, eax
0x18008a6ef  jns     short loc_18008A700
0x18008a6f1  lea     r9, aFailedToStopRu; "Failed to stop running task %ws [%x]"
0x18008a6f8  mov     r8d, 6DCh
0x18008a6fe  jmp     short loc_18008A77B
0x18008a700  lea     r9, aSuccessfullySt; "Successfully stopped task %ws"
0x18008a707  mov     [rsp+100h+ppv], r13
0x18008a70c  mov     r8d, 6DFh
0x18008a712  mov     ecx, ebx
0x18008a714  call    AslLogCallPrintf
0x18008a719  mov     ecx, 3E8h; dwMilliseconds
0x18008a71e  call    cs:__imp_Sleep
0x18008a724  jmp     short loc_18008A78C
0x18008a726  lea     r9, aTaskWsStateDNo; "Task %ws state: %d (not running)"
0x18008a72d  mov     r8d, 6E5h
0x18008a733  mov     ecx, 3
0x18008a738  jmp     short loc_18008A77E
0x18008a73a  lea     r9, aFailedToGetTas_0; "Failed to get task state [%x]"
0x18008a741  mov     dword ptr [rsp+100h+ppv], eax
0x18008a745  mov     r8d, 6E8h
0x18008a74b  mov     ecx, r12d
0x18008a74e  call    AslLogCallPrintf
0x18008a753  jmp     short loc_18008A78C
0x18008a755  cmp     eax, 80070002h
0x18008a75a  jnz     short loc_18008A76B
0x18008a75c  lea     r9, aTaskWsDoesNotE; "Task %ws does not exist, nothing to del"...
0x18008a763  mov     r8d, 6EDh
0x18008a769  jmp     short loc_18008A7E0
0x18008a76b  lea     r9, aFailedToGetTas_1; "Failed to get task %ws [%x]"
0x18008a772  mov     r8d, 6F1h
0x18008a778  mov     rdx, r15
0x18008a77b  mov     ecx, r12d
0x18008a77e  mov     [rsp+100h+var_D8], eax
0x18008a782  mov     [rsp+100h+ppv], r13
0x18008a787  call    AslLogCallPrintf
0x18008a78c  mov     rcx, [rbp+57h+arg_10]
0x18008a790  xor     r8d, r8d
0x18008a793  mov     rdx, rdi
0x18008a796  mov     rax, [rcx]
0x18008a799  mov     rax, [rax+78h]
0x18008a79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a7a2  mov     ebx, eax
0x18008a7a4  test    eax, eax
0x18008a7a6  jns     short loc_18008A7D3
0x18008a7a8  mov     rdx, r15
0x18008a7ab  cmp     eax, 80070002h
0x18008a7b0  jnz     short loc_18008A7C1
0x18008a7b2  lea     r9, aTaskWsDoesNotE; "Task %ws does not exist, nothing to del"...
0x18008a7b9  mov     r8d, 6FBh
0x18008a7bf  jmp     short loc_18008A7E3
0x18008a7c1  lea     r9, aFailedToDelete_7; "Failed to delete task [%x]"
0x18008a7c8  mov     r8d, 6FEh
0x18008a7ce  jmp     loc_18008A56C
0x18008a7d3  lea     r9, aSuccessfullyDe; "Successfully deleted task %ws"
0x18008a7da  mov     r8d, 703h
0x18008a7e0  mov     rdx, r15
0x18008a7e3  mov     ecx, 3
0x18008a7e8  mov     [rsp+100h+ppv], r13
0x18008a7ed  call    AslLogCallPrintf
0x18008a7f2  xor     ebx, ebx
0x18008a7f4  mov     rcx, rsi; bstrString
0x18008a7f7  call    cs:__imp_SysFreeString
0x18008a7fd  mov     rcx, rdi; bstrString
0x18008a800  call    cs:__imp_SysFreeString
0x18008a806  mov     rcx, [rbp+57h+arg_8]
0x18008a80a  test    rcx, rcx
0x18008a80d  jz      short loc_18008A81B
0x18008a80f  mov     rax, [rcx]
0x18008a812  mov     rax, [rax+10h]
0x18008a816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a81b  mov     rcx, [rbp+57h+arg_10]
0x18008a81f  test    rcx, rcx
0x18008a822  jz      short loc_18008A830
0x18008a824  mov     rax, [rcx]
0x18008a827  mov     rax, [rax+10h]
0x18008a82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a830  mov     rcx, [rbp+57h+arg_18]
0x18008a834  test    rcx, rcx
0x18008a837  jz      short loc_18008A845
0x18008a839  mov     rax, [rcx]
0x18008a83c  mov     rax, [rax+10h]
0x18008a840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a845  test    ebx, ebx
0x18008a847  js      short loc_18008A84D
0x18008a849  xor     ebx, ebx
0x18008a84b  jmp     short loc_18008A85E
0x18008a84d  mov     eax, ebx
0x18008a84f  and     eax, 1FFF0000h
0x18008a854  cmp     eax, 70000h
0x18008a859  jnz     short loc_18008A85E
0x18008a85b  movzx   ebx, bx
0x18008a85e  mov     eax, ebx
0x18008a860  add     rsp, 0D0h
0x18008a867  pop     r15
0x18008a869  pop     r13
0x18008a86b  pop     r12
0x18008a86d  pop     rdi
0x18008a86e  pop     rsi
0x18008a86f  pop     rbx
0x18008a870  pop     rbp
0x18008a871  retn
```
