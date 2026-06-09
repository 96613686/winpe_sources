# NlBrowserUpdate(_DOMAIN_INFO *,ulong)

- ea: `0x18003d208`
- end: `0x18003d3a6`
- name: `?NlBrowserUpdate@@YAXPEAU_DOMAIN_INFO@@K@Z`
- size: `414`
- prototype: `void __fastcall(struct _DOMAIN_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800267ec`
- `0x180029218`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18003bda8`
- `0x18003c168`
- `0x18003d208`
- `0x18003dd20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2c9`
- `srvcli!NetServerComputerNameDel` at `0x18003d371`
- `srvcli!NetServerComputerNameDel` at `0x18003d371`
- `srvcli!I_NetServerSetServiceBitsEx` at `0x18003d31d`
- `srvcli!I_NetServerSetServiceBitsEx` at `0x18003d31d`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003d25c`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003d2b7`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003d25c`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18003d2b7`

## string_xrefs

- `0x18003d27a`: `Couldn't I_ScSetServiceBits off %ld 0x%lx.\n`
- `0x18003d2d5`: `Couldn't I_ScSetServiceBits %ld 0x%lx.\n`
- `0x18003d334`: `NlBrowserUpdate: Couldn't I_NetServerSetServiceBitsEx %ld 0x%lx.\n`
- `0x18003d388`: `NlBrowserUpdate: Couldn't NetServerComputerNameDel %ld 0x%lx.\n`

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
0x18003d208  push    rbx
0x18003d20a  push    rbp
0x18003d20b  push    rsi
0x18003d20c  push    rdi
0x18003d20d  sub     rsp, 38h
0x18003d211  mov     eax, edx
0x18003d213  mov     esi, edx
0x18003d215  mov     rbx, rcx
0x18003d218  sub     eax, 1
0x18003d21b  jz      short loc_18003D22D
0x18003d21d  cmp     eax, 1
0x18003d220  jz      short loc_18003D226
0x18003d222  xor     edi, edi
0x18003d224  jmp     short loc_18003D232
0x18003d226  mov     edi, 2
0x18003d22b  jmp     short loc_18003D232
0x18003d22d  mov     edi, 1
0x18003d232  test    dword ptr [rcx+250h], 1000h
0x18003d23c  jz      loc_18003D2F5
0x18003d242  mov     rcx, cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x18003d249  xor     r9d, r9d
0x18003d24c  xor     r8d, r8d
0x18003d24f  mov     [rsp+58h+var_38], 0
0x18003d258  lea     edx, [r9+18h]
0x18003d25c  call    cs:__imp_I_ScSetServiceBitsW
0x18003d263  nop     dword ptr [rax+rax+00h]
0x18003d268  mov     ebp, eax
0x18003d26a  test    eax, eax
0x18003d26c  jnz     short loc_18003D291
0x18003d26e  call    cs:__imp_GetLastError
0x18003d275  nop     dword ptr [rax+rax+00h]
0x18003d27a  lea     rdx, aCouldnTIScsets_0; "Couldn't I_ScSetServiceBits off %ld 0x%"...
0x18003d281  mov     ecx, 100h; unsigned int
0x18003d286  mov     r9d, eax
0x18003d289  mov     r8d, eax
0x18003d28c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d291  test    edi, edi
0x18003d293  jz      short loc_18003D2C5
0x18003d295  mov     ecx, esi; unsigned int
0x18003d297  call    ?NlServerType@@YAKK@Z; NlServerType(ulong)
0x18003d29c  mov     rcx, cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x18003d2a3  mov     r9d, 1
0x18003d2a9  mov     r8d, r9d
0x18003d2ac  mov     [rsp+58h+var_38], 0
0x18003d2b5  mov     edx, eax
0x18003d2b7  call    cs:__imp_I_ScSetServiceBitsW
0x18003d2be  nop     dword ptr [rax+rax+00h]
0x18003d2c3  mov     ebp, eax
0x18003d2c5  test    ebp, ebp
0x18003d2c7  jnz     short loc_18003D2EC
0x18003d2c9  call    cs:__imp_GetLastError
0x18003d2d0  nop     dword ptr [rax+rax+00h]
0x18003d2d5  lea     rdx, aCouldnTIScsets; "Couldn't I_ScSetServiceBits %ld 0x%lx."...
0x18003d2dc  mov     ecx, 100h; unsigned int
0x18003d2e1  mov     r9d, eax
0x18003d2e4  mov     r8d, eax
0x18003d2e7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d2ec  lea     rdi, [rbx+108h]
0x18003d2f3  jmp     short loc_18003D348
0x18003d2f5  lea     rdi, [rcx+108h]
0x18003d2fc  mov     ecx, esi; unsigned int
0x18003d2fe  call    ?NlServerType@@YAKK@Z; NlServerType(ulong)
0x18003d303  mov     rdx, [rdi]
0x18003d306  xor     ecx, ecx
0x18003d308  mov     [rsp+58h+var_30], 1
0x18003d310  mov     r9d, 18h
0x18003d316  xor     r8d, r8d
0x18003d319  mov     dword ptr [rsp+58h+var_38], eax
0x18003d31d  call    cs:__imp_I_NetServerSetServiceBitsEx
0x18003d324  nop     dword ptr [rax+rax+00h]
0x18003d329  test    eax, eax
0x18003d32b  jz      short loc_18003D348
0x18003d32d  mov     r9d, eax
0x18003d330  mov     dword ptr [rsp+58h+var_38], eax
0x18003d334  lea     r8, aNlbrowserupdat_0; "NlBrowserUpdate: Couldn't I_NetServerSe"...
0x18003d33b  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003d33e  mov     ecx, 100h; unsigned int
0x18003d343  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003d348  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18003d34b  cmp     esi, 1
0x18003d34e  jnz     short loc_18003D357
0x18003d350  call    ?NlBrowserAddName@@YAXPEAU_DOMAIN_INFO@@@Z; NlBrowserAddName(_DOMAIN_INFO *)
0x18003d355  jmp     short loc_18003D39C
0x18003d357  call    ?NlBrowserDelName@@YAXPEAU_DOMAIN_INFO@@@Z; NlBrowserDelName(_DOMAIN_INFO *)
0x18003d35c  test    esi, esi
0x18003d35e  jnz     short loc_18003D39C
0x18003d360  test    dword ptr [rbx+250h], 1000h
0x18003d36a  jnz     short loc_18003D39C
0x18003d36c  mov     rdx, [rdi]; EmulatedServerName
0x18003d36f  xor     ecx, ecx; ServerName
0x18003d371  call    cs:__imp_NetServerComputerNameDel
0x18003d378  nop     dword ptr [rax+rax+00h]
0x18003d37d  test    eax, eax
0x18003d37f  jz      short loc_18003D39C
0x18003d381  mov     r9d, eax
0x18003d384  mov     dword ptr [rsp+58h+var_38], eax
0x18003d388  lea     r8, aNlbrowserupdat; "NlBrowserUpdate: Couldn't NetServerComp"...
0x18003d38f  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003d392  mov     ecx, 100h; unsigned int
0x18003d397  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003d39c  add     rsp, 38h
0x18003d3a0  pop     rdi
0x18003d3a1  pop     rsi
0x18003d3a2  pop     rbp
0x18003d3a3  pop     rbx
0x18003d3a4  retn
```
