# NlBrowserUpdate(_DOMAIN_INFO *,ulong)

- ea: `0x18003ada4`
- end: `0x18003af1d`
- name: `?NlBrowserUpdate@@YAXPEAU_DOMAIN_INFO@@K@Z`
- size: `377`
- prototype: `void __fastcall(struct _DOMAIN_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180025708`
- `0x180027d78`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x180039a84`
- `0x180039df4`
- `0x18003ada4`
- `0x18003b814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae53`
- `srvcli!NetServerComputerNameDel` at `0x18003aeef`
- `srvcli!NetServerComputerNameDel` at `0x18003aeef`
- `srvcli!I_NetServerSetServiceBitsEx` at `0x18003aea1`
- `srvcli!I_NetServerSetServiceBitsEx` at `0x18003aea1`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003adf8`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003ae47`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003adf8`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003ae47`

## string_xrefs

- `0x18003ae0a`: `Couldn't I_ScSetServiceBits off %ld 0x%lx.\n`
- `0x18003ae59`: `Couldn't I_ScSetServiceBits %ld 0x%lx.\n`
- `0x18003aeb2`: `NlBrowserUpdate: Couldn't I_NetServerSetServiceBitsEx %ld 0x%lx.\n`
- `0x18003af00`: `NlBrowserUpdate: Couldn't NetServerComputerNameDel %ld 0x%lx.\n`

## pseudocode

```c
void __fastcall NlBrowserUpdate(struct _DOMAIN_INFO *a1, unsigned int a2)
{
  int v4; // edi
  int v5; // ebp
  DWORD LastError; // eax
  unsigned int v7; // eax
  DWORD v8; // eax
  LPWSTR *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // eax
  DWORD v12; // eax
  __int64 v13; // [rsp+20h] [rbp-38h]

  if ( a2 == 1 )
  {
    v4 = 1;
  }
  else if ( a2 == 2 )
  {
    v4 = 2;
  }
  else
  {
    v4 = 0;
  }
  if ( (*((_DWORD *)a1 + 148) & 0x1000) != 0 )
  {
    HIDWORD(v13) = 0;
    v5 = I_ScSetServiceBitsW(NlGlobalServiceHandle, 24, 0);
    if ( !v5 )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"Couldn't I_ScSetServiceBits off %ld 0x%lx.\n", LastError, LastError);
    }
    if ( v4 )
    {
      v7 = NlServerType(a2);
      HIDWORD(v13) = 0;
      v5 = I_ScSetServiceBitsW(NlGlobalServiceHandle, v7, 1);
    }
    if ( !v5 )
    {
      v8 = GetLastError();
      NlPrintRoutine(0x100u, L"Couldn't I_ScSetServiceBits %ld 0x%lx.\n", v8, v8);
    }
    v9 = (LPWSTR *)((char *)a1 + 264);
  }
  else
  {
    v9 = (LPWSTR *)((char *)a1 + 264);
    v10 = NlServerType(a2);
    v11 = I_NetServerSetServiceBitsEx(0, *v9, 0, 24, v10, 1);
    if ( v11 )
    {
      LODWORD(v13) = v11;
      NlPrintDomRoutine(0x100u, a1, L"NlBrowserUpdate: Couldn't I_NetServerSetServiceBitsEx %ld 0x%lx.\n", v11, v13);
    }
  }
  if ( a2 == 1 )
  {
    NlBrowserAddName(a1);
  }
  else
  {
    NlBrowserDelName(a1);
    if ( !a2 && (*((_DWORD *)a1 + 148) & 0x1000) == 0 )
    {
      v12 = NetServerComputerNameDel(0, *v9);
      if ( v12 )
      {
        LODWORD(v13) = v12;
        NlPrintDomRoutine(0x100u, a1, L"NlBrowserUpdate: Couldn't NetServerComputerNameDel %ld 0x%lx.\n", v12, v13);
      }
    }
  }
}

```

## disassembly

```asm
0x18003ada4  push    rbx
0x18003ada6  push    rbp
0x18003ada7  push    rsi
0x18003ada8  push    rdi
0x18003ada9  sub     rsp, 38h
0x18003adad  mov     eax, edx
0x18003adaf  mov     esi, edx
0x18003adb1  mov     rbx, rcx
0x18003adb4  sub     eax, 1
0x18003adb7  jz      short loc_18003ADC9
0x18003adb9  cmp     eax, 1
0x18003adbc  jz      short loc_18003ADC2
0x18003adbe  xor     edi, edi
0x18003adc0  jmp     short loc_18003ADCE
0x18003adc2  mov     edi, 2
0x18003adc7  jmp     short loc_18003ADCE
0x18003adc9  mov     edi, 1
0x18003adce  test    dword ptr [rcx+250h], 1000h
0x18003add8  jz      loc_18003AE79
0x18003adde  mov     rcx, cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x18003ade5  xor     r9d, r9d
0x18003ade8  xor     r8d, r8d
0x18003adeb  mov     [rsp+58h+var_38], 0
0x18003adf4  lea     edx, [r9+18h]
0x18003adf8  call    cs:__imp_I_ScSetServiceBitsW
0x18003adfe  mov     ebp, eax
0x18003ae00  test    eax, eax
0x18003ae02  jnz     short loc_18003AE21
0x18003ae04  call    cs:__imp_GetLastError
0x18003ae0a  lea     rdx, aCouldnTIScsets_0; "Couldn't I_ScSetServiceBits off %ld 0x%"...
0x18003ae11  mov     ecx, 100h; unsigned int
0x18003ae16  mov     r9d, eax
0x18003ae19  mov     r8d, eax
0x18003ae1c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ae21  test    edi, edi
0x18003ae23  jz      short loc_18003AE4F
0x18003ae25  mov     ecx, esi; unsigned int
0x18003ae27  call    ?NlServerType@@YAKK@Z; NlServerType(ulong)
0x18003ae2c  mov     rcx, cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x18003ae33  mov     r9d, 1
0x18003ae39  mov     r8d, r9d
0x18003ae3c  mov     [rsp+58h+var_38], 0
0x18003ae45  mov     edx, eax
0x18003ae47  call    cs:__imp_I_ScSetServiceBitsW
0x18003ae4d  mov     ebp, eax
0x18003ae4f  test    ebp, ebp
0x18003ae51  jnz     short loc_18003AE70
0x18003ae53  call    cs:__imp_GetLastError
0x18003ae59  lea     rdx, aCouldnTIScsets; "Couldn't I_ScSetServiceBits %ld 0x%lx."...
0x18003ae60  mov     ecx, 100h; unsigned int
0x18003ae65  mov     r9d, eax
0x18003ae68  mov     r8d, eax
0x18003ae6b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ae70  lea     rdi, [rbx+108h]
0x18003ae77  jmp     short loc_18003AEC6
0x18003ae79  lea     rdi, [rcx+108h]
0x18003ae80  mov     ecx, esi; unsigned int
0x18003ae82  call    ?NlServerType@@YAKK@Z; NlServerType(ulong)
0x18003ae87  mov     rdx, [rdi]
0x18003ae8a  xor     ecx, ecx
0x18003ae8c  mov     [rsp+58h+var_30], 1
0x18003ae94  mov     r9d, 18h
0x18003ae9a  xor     r8d, r8d
0x18003ae9d  mov     dword ptr [rsp+58h+var_38], eax
0x18003aea1  call    cs:__imp_I_NetServerSetServiceBitsEx
0x18003aea7  test    eax, eax
0x18003aea9  jz      short loc_18003AEC6
0x18003aeab  mov     r9d, eax
0x18003aeae  mov     dword ptr [rsp+58h+var_38], eax
0x18003aeb2  lea     r8, aNlbrowserupdat_0; "NlBrowserUpdate: Couldn't I_NetServerSe"...
0x18003aeb9  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003aebc  mov     ecx, 100h; unsigned int
0x18003aec1  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003aec6  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18003aec9  cmp     esi, 1
0x18003aecc  jnz     short loc_18003AED5
0x18003aece  call    ?NlBrowserAddName@@YAXPEAU_DOMAIN_INFO@@@Z; NlBrowserAddName(_DOMAIN_INFO *)
0x18003aed3  jmp     short loc_18003AF14
0x18003aed5  call    ?NlBrowserDelName@@YAXPEAU_DOMAIN_INFO@@@Z; NlBrowserDelName(_DOMAIN_INFO *)
0x18003aeda  test    esi, esi
0x18003aedc  jnz     short loc_18003AF14
0x18003aede  test    dword ptr [rbx+250h], 1000h
0x18003aee8  jnz     short loc_18003AF14
0x18003aeea  mov     rdx, [rdi]; EmulatedServerName
0x18003aeed  xor     ecx, ecx; ServerName
0x18003aeef  call    cs:__imp_NetServerComputerNameDel
0x18003aef5  test    eax, eax
0x18003aef7  jz      short loc_18003AF14
0x18003aef9  mov     r9d, eax
0x18003aefc  mov     dword ptr [rsp+58h+var_38], eax
0x18003af00  lea     r8, aNlbrowserupdat; "NlBrowserUpdate: Couldn't NetServerComp"...
0x18003af07  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003af0a  mov     ecx, 100h; unsigned int
0x18003af0f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003af14  add     rsp, 38h
0x18003af18  pop     rdi
0x18003af19  pop     rsi
0x18003af1a  pop     rbp
0x18003af1b  pop     rbx
0x18003af1c  retn
```
