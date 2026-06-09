# IsBackgroundExtensionContract(ushort const *)

- ea: `0x180081a88`
- end: `0x180081b74`
- name: `?IsBackgroundExtensionContract@@YA_NPEBG@Z`
- size: `236`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180082a10`

## callees

- `0x180081a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180081b4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180081b4b`

## string_xrefs

- `0x180081aba`: `Windows.UpdateTask`
- `0x180081aaf`: `Windows.PreInstalledConfigTask`
- `0x180081a9f`: `Windows.BackgroundTasks`
- `0x180081ac5`: `Windows.AppService`
- `0x180081afc`: `Windows.PrintWorkflowBackgroundTask`
- `0x180081af1`: `Windows.UserDataTaskDataProvider`
- `0x180081b1d`: `Windows.PrintSupportExtension`

## pseudocode

```c
char __fastcall IsBackgroundExtensionContract(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  _QWORD v4[14]; // [rsp+20h] [rbp-19h]

  v4[0] = L"Windows.BackgroundTasks";
  v2 = 0;
  v4[1] = L"Windows.PreInstalledConfigTask";
  v4[2] = L"Windows.UpdateTask";
  v4[3] = L"Windows.AppService";
  v4[4] = L"Windows.AppointmentDataProvider";
  v4[5] = L"Windows.ContactDataProvider";
  v4[6] = L"Windows.EmailDataProvider";
  v4[7] = L"Windows.UserDataTaskDataProvider";
  v4[8] = L"Windows.PrintWorkflowBackgroundTask";
  v4[9] = L"Windows.BarcodeScannerProvider";
  v4[10] = L"Windows.PosPaymentConnector";
  v4[11] = L"Windows.PrintSupportExtension";
  v4[12] = L"Windows.PrintSupportWorkflow";
  v4[13] = L"Windows.PrintSupportVirtualPrinterWorkflow";
  while ( (unsigned int)v2 < 0xE )
  {
    if ( !(unsigned int)_o__wcsicmp(a1, v4[v2]) )
      return 1;
    v2 = (unsigned int)(v2 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180081a88  mov     [rsp-8+arg_0], rbx
0x180081a8d  mov     [rsp-8+arg_8], rdi
0x180081a92  push    rbp
0x180081a93  lea     rbp, [rsp-57h]
0x180081a98  sub     rsp, 90h
0x180081a9f  lea     rax, aWindowsBackgro; "Windows.BackgroundTasks"
0x180081aa6  mov     rdi, rcx
0x180081aa9  mov     [rbp+57h+var_70], rax
0x180081aad  xor     ebx, ebx
0x180081aaf  lea     rax, aWindowsPreinst; "Windows.PreInstalledConfigTask"
0x180081ab6  mov     [rbp+57h+var_68], rax
0x180081aba  lea     rax, aWindowsUpdatet; "Windows.UpdateTask"
0x180081ac1  mov     [rbp+57h+var_60], rax
0x180081ac5  lea     rax, aWindowsAppserv; "Windows.AppService"
0x180081acc  mov     [rbp+57h+var_58], rax
0x180081ad0  lea     rax, aWindowsAppoint; "Windows.AppointmentDataProvider"
0x180081ad7  mov     [rbp+57h+var_50], rax
0x180081adb  lea     rax, aWindowsContact_5; "Windows.ContactDataProvider"
0x180081ae2  mov     [rbp+57h+var_48], rax
0x180081ae6  lea     rax, aWindowsEmailda; "Windows.EmailDataProvider"
0x180081aed  mov     [rbp+57h+var_40], rax
0x180081af1  lea     rax, aWindowsUserdat_0; "Windows.UserDataTaskDataProvider"
0x180081af8  mov     [rbp+57h+var_38], rax
0x180081afc  lea     rax, aWindowsPrintwo; "Windows.PrintWorkflowBackgroundTask"
0x180081b03  mov     [rbp+57h+var_30], rax
0x180081b07  lea     rax, aWindowsBarcode_0; "Windows.BarcodeScannerProvider"
0x180081b0e  mov     [rbp+57h+var_28], rax
0x180081b12  lea     rax, aWindowsPospaym; "Windows.PosPaymentConnector"
0x180081b19  mov     [rbp+57h+var_20], rax
0x180081b1d  lea     rax, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x180081b24  mov     [rbp+57h+var_18], rax
0x180081b28  lea     rax, aWindowsPrintsu; "Windows.PrintSupportWorkflow"
0x180081b2f  mov     [rbp+57h+var_10], rax
0x180081b33  lea     rax, aWindowsPrintsu_0; "Windows.PrintSupportVirtualPrinterWorkf"...
0x180081b3a  mov     [rbp+57h+var_8], rax
0x180081b3e  cmp     ebx, 0Eh
0x180081b41  jnb     short loc_180081B5D
0x180081b43  mov     rdx, [rbp+rbx*8+57h+var_70]
0x180081b48  mov     rcx, rdi
0x180081b4b  call    cs:__imp__o__wcsicmp
0x180081b51  test    eax, eax
0x180081b53  jz      short loc_180081B59
0x180081b55  inc     ebx
0x180081b57  jmp     short loc_180081B3E
0x180081b59  mov     al, 1
0x180081b5b  jmp     short loc_180081B5F
0x180081b5d  xor     al, al
0x180081b5f  lea     r11, [rsp+90h+var_s0]
0x180081b67  mov     rbx, [r11+10h]
0x180081b6b  mov     rdi, [r11+18h]
0x180081b6f  mov     rsp, r11
0x180081b72  pop     rbp
0x180081b73  retn
```
