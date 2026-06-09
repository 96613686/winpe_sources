# InstallMiniportDevice(ushort const *)

- ea: `0x18000c7f0`
- end: `0x18000c8c6`
- name: `?InstallMiniportDevice@@YAJPEBG@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800097d0`

## callees

- `0x18000c000`
- `0x18000c164`
- `0x18000c268`
- `0x18000c7f0`
- `0x18000ca8c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c8a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c8a7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c812`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c812`

## string_xrefs

- `0x18000c835`: `InstallMiniportDevice: CoInitializeEx failed with 0x%x`
- `0x18000c88a`: `InstallMiniportDevice: HrInstallNetComponent failed with 0x%x`

## pseudocode

```c
__int64 __fastcall InstallMiniportDevice(const unsigned __int16 *a1)
{
  int INetCfg; // ebx
  BOOL v3; // esi
  const unsigned __int16 *v4; // rdx
  struct INetCfg *v5; // rdi
  int v6; // eax
  struct INetCfg *v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  INetCfg = CoInitializeEx(0, 6u);
  if ( (int)(INetCfg + 0x80000000) < 0 || INetCfg == -2147417850 )
  {
    v3 = INetCfg >= 0;
    INetCfg = HrGetINetCfg(1, (LPVOID *)&v8);
    if ( INetCfg >= 0 )
    {
      v4 = a1;
      v5 = v8;
      v6 = HrInstallNetComponent(v8, v4);
      INetCfg = v6;
      if ( v6 < 0 )
        RasDiagTrace("InstallMiniportDevice: HrInstallNetComponent failed with 0x%x", v6);
      else
        INetCfg = ((__int64 (__fastcall *)(struct INetCfg *))v5->lpVtbl->Apply)(v5);
      HrReleaseINetCfg(1, v5);
    }
    if ( v3 )
      CoUninitialize();
  }
  else
  {
    RasDiagTrace("InstallMiniportDevice: CoInitializeEx failed with 0x%x", INetCfg);
  }
  return (unsigned int)INetCfg;
}

```

## disassembly

```asm
0x18000c7f0  mov     [rsp+arg_0], rbx
0x18000c7f5  mov     [rsp+arg_10], rsi
0x18000c7fa  push    rdi
0x18000c7fb  sub     rsp, 20h
0x18000c7ff  mov     rdi, rcx
0x18000c802  mov     [rsp+28h+arg_8], 0
0x18000c80b  xor     ecx, ecx; pvReserved
0x18000c80d  mov     edx, 6; dwCoInit
0x18000c812  call    cs:__imp_CoInitializeEx
0x18000c819  nop     dword ptr [rax+rax+00h]
0x18000c81e  mov     ecx, 80000000h
0x18000c823  mov     ebx, eax
0x18000c825  add     eax, ecx
0x18000c827  test    ecx, eax
0x18000c829  jnz     short loc_18000C843
0x18000c82b  cmp     ebx, 80010106h
0x18000c831  jz      short loc_18000C843
0x18000c833  mov     edx, ebx
0x18000c835  lea     rcx, aInstallminipor_0; "InstallMiniportDevice: CoInitializeEx f"...
0x18000c83c  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c841  jmp     short loc_18000C8B3
0x18000c843  not     ebx
0x18000c845  lea     rdx, [rsp+28h+arg_8]; struct INetCfg **
0x18000c84a  shr     ebx, 1Fh
0x18000c84d  mov     ecx, 1; int
0x18000c852  mov     esi, ebx
0x18000c854  call    ?HrGetINetCfg@@YAJHPEAPEAUINetCfg@@@Z; HrGetINetCfg(int,INetCfg * *)
0x18000c859  mov     ebx, eax
0x18000c85b  test    eax, eax
0x18000c85d  js      short loc_18000C8A3
0x18000c85f  mov     rdx, rdi; unsigned __int16 *
0x18000c862  mov     rdi, [rsp+28h+arg_8]
0x18000c867  mov     rcx, rdi; struct INetCfg *
0x18000c86a  call    ?HrInstallNetComponent@@YAJPEAUINetCfg@@PEBG@Z; HrInstallNetComponent(INetCfg *,ushort const *)
0x18000c86f  mov     ebx, eax
0x18000c871  test    eax, eax
0x18000c873  js      short loc_18000C888
0x18000c875  mov     rax, [rdi]
0x18000c878  mov     rcx, rdi
0x18000c87b  mov     rax, [rax+28h]
0x18000c87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c884  mov     ebx, eax
0x18000c886  jmp     short loc_18000C896
0x18000c888  mov     edx, eax
0x18000c88a  lea     rcx, aInstallminipor; "InstallMiniportDevice: HrInstallNetComp"...
0x18000c891  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c896  mov     rdx, rdi; struct INetCfg *
0x18000c899  mov     ecx, 1; int
0x18000c89e  call    ?HrReleaseINetCfg@@YAJHPEAUINetCfg@@@Z; HrReleaseINetCfg(int,INetCfg *)
0x18000c8a3  test    esi, esi
0x18000c8a5  jz      short loc_18000C8B3
0x18000c8a7  call    cs:__imp_CoUninitialize
0x18000c8ae  nop     dword ptr [rax+rax+00h]
0x18000c8b3  mov     rsi, [rsp+28h+arg_10]
0x18000c8b8  mov     eax, ebx
0x18000c8ba  mov     rbx, [rsp+28h+arg_0]
0x18000c8bf  add     rsp, 20h
0x18000c8c3  pop     rdi
0x18000c8c4  retn
```
