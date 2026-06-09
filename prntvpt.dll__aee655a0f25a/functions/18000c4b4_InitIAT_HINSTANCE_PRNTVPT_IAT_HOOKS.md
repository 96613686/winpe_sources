# InitIAT(HINSTANCE__ *,_PRNTVPT_IAT_HOOKS *)

- ea: `0x18000c4b4`
- end: `0x18000c6a3`
- name: `?InitIAT@@YAHPEAUHINSTANCE__@@PEAU_PRNTVPT_IAT_HOOKS@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(HINSTANCE hModule, struct _PRNTVPT_IAT_HOOKS *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a640`

## callees

- `0x18000c4b4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c4c4`
- `KERNEL32!GetProcAddress` at `0x18000c4db`
- `KERNEL32!GetProcAddress` at `0x18000c4f2`
- `KERNEL32!GetProcAddress` at `0x18000c509`
- `KERNEL32!GetProcAddress` at `0x18000c520`
- `KERNEL32!GetProcAddress` at `0x18000c537`
- `KERNEL32!GetProcAddress` at `0x18000c54e`
- `KERNEL32!GetProcAddress` at `0x18000c565`
- `KERNEL32!GetProcAddress` at `0x18000c57c`
- `KERNEL32!GetProcAddress` at `0x18000c593`
- `KERNEL32!GetProcAddress` at `0x18000c5aa`
- `KERNEL32!GetProcAddress` at `0x18000c5c1`
- `KERNEL32!GetProcAddress` at `0x18000c5d8`
- `KERNEL32!GetProcAddress` at `0x18000c5ef`
- `KERNEL32!GetProcAddress` at `0x18000c606`
- `KERNEL32!GetProcAddress` at `0x18000c4c4`
- `KERNEL32!GetProcAddress` at `0x18000c4db`
- `KERNEL32!GetProcAddress` at `0x18000c4f2`
- `KERNEL32!GetProcAddress` at `0x18000c509`
- `KERNEL32!GetProcAddress` at `0x18000c520`
- `KERNEL32!GetProcAddress` at `0x18000c537`
- `KERNEL32!GetProcAddress` at `0x18000c54e`
- `KERNEL32!GetProcAddress` at `0x18000c565`
- `KERNEL32!GetProcAddress` at `0x18000c57c`
- `KERNEL32!GetProcAddress` at `0x18000c593`
- `KERNEL32!GetProcAddress` at `0x18000c5aa`
- `KERNEL32!GetProcAddress` at `0x18000c5c1`
- `KERNEL32!GetProcAddress` at `0x18000c5d8`
- `KERNEL32!GetProcAddress` at `0x18000c5ef`
- `KERNEL32!GetProcAddress` at `0x18000c606`

## string_xrefs

- `0x18000c4ba`: `PTOpenProviderEx`

## pseudocode

```c
__int64 __fastcall InitIAT(HINSTANCE hModule, struct _PRNTVPT_IAT_HOOKS *a2)
{
  FARPROC ProcAddress; // rax
  bool v4; // zf
  __int64 result; // rax

  g_pfnPrntvptIAT = GetProcAddress(hModule, "PTOpenProviderEx");
  qword_1800321D8 = (__int64)GetProcAddress(hModule, "PTCloseProvider");
  qword_1800321E0 = (__int64)GetProcAddress(hModule, "PTGetPrintCapabilities");
  qword_1800321E8 = (__int64)GetProcAddress(hModule, "PTMergeAndValidatePrintTicket");
  qword_1800321F0 = (__int64)GetProcAddress(hModule, "PTConvertPrintTicketToDevMode");
  qword_1800321F8 = (__int64)GetProcAddress(hModule, "PTGetPrintDeviceCapabilities");
  qword_180032200 = (__int64)GetProcAddress(hModule, "PTGetPrintDeviceResources");
  qword_180032208 = (__int64)GetProcAddress(hModule, "PTReleaseMemory");
  qword_180032210 = (__int64)GetProcAddress(hModule, "PTConvertDevModeToPrintTicket");
  qword_180032218 = (__int64)GetProcAddress(hModule, "GetPrintCapabilitiesThunk2");
  qword_180032220 = (__int64)GetProcAddress(hModule, "MergeAndValidatePrintTicketThunk2");
  qword_180032228 = (__int64)GetProcAddress(hModule, "ConvertDevModeToPrintTicketThunk2");
  qword_180032230 = (__int64)GetProcAddress(hModule, "ConvertPrintTicketToDevModeThunk2");
  qword_180032238 = (__int64)GetProcAddress(hModule, "GetPrintDeviceCapabilitiesThunk2");
  ProcAddress = GetProcAddress(hModule, "GetPrintDeviceResourcesThunk2");
  qword_180032240 = (__int64)ProcAddress;
  if ( !g_pfnPrntvptIAT )
    return 0;
  if ( !qword_1800321D8 )
    return 0;
  if ( !qword_1800321E0 )
    return 0;
  if ( !qword_1800321E8 )
    return 0;
  if ( !qword_1800321F0 )
    return 0;
  if ( !qword_1800321F8 )
    return 0;
  if ( !qword_180032200 )
    return 0;
  if ( !qword_180032208 )
    return 0;
  if ( !qword_180032210 )
    return 0;
  if ( !qword_180032218 )
    return 0;
  if ( !qword_180032220 )
    return 0;
  if ( !qword_180032228 )
    return 0;
  if ( !qword_180032230 )
    return 0;
  if ( !qword_180032238 )
    return 0;
  v4 = ProcAddress == 0;
  result = 1;
  if ( v4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000c4b4  push    rbx
0x18000c4b6  sub     rsp, 20h
0x18000c4ba  lea     rdx, aPtopenprovider_1; "PTOpenProviderEx"
0x18000c4c1  mov     rbx, rcx
0x18000c4c4  call    cs:__imp_GetProcAddress
0x18000c4ca  lea     rdx, aPtcloseprovide_0; "PTCloseProvider"
0x18000c4d1  mov     rcx, rbx; hModule
0x18000c4d4  mov     cs:?g_pfnPrntvptIAT@@3U_PRNTVPT_IAT_HOOKS@@A, rax; _PRNTVPT_IAT_HOOKS g_pfnPrntvptIAT
0x18000c4db  call    cs:__imp_GetProcAddress
0x18000c4e1  lea     rdx, aPtgetprintcapa_0; "PTGetPrintCapabilities"
0x18000c4e8  mov     rcx, rbx; hModule
0x18000c4eb  mov     cs:qword_1800321D8, rax
0x18000c4f2  call    cs:__imp_GetProcAddress
0x18000c4f8  lea     rdx, aPtmergeandvali_0; "PTMergeAndValidatePrintTicket"
0x18000c4ff  mov     rcx, rbx; hModule
0x18000c502  mov     cs:qword_1800321E0, rax
0x18000c509  call    cs:__imp_GetProcAddress
0x18000c50f  lea     rdx, aPtconvertprint_0; "PTConvertPrintTicketToDevMode"
0x18000c516  mov     rcx, rbx; hModule
0x18000c519  mov     cs:qword_1800321E8, rax
0x18000c520  call    cs:__imp_GetProcAddress
0x18000c526  lea     rdx, aPtgetprintdevi_2; "PTGetPrintDeviceCapabilities"
0x18000c52d  mov     rcx, rbx; hModule
0x18000c530  mov     cs:qword_1800321F0, rax
0x18000c537  call    cs:__imp_GetProcAddress
0x18000c53d  lea     rdx, aPtgetprintdevi_1; "PTGetPrintDeviceResources"
0x18000c544  mov     rcx, rbx; hModule
0x18000c547  mov     cs:qword_1800321F8, rax
0x18000c54e  call    cs:__imp_GetProcAddress
0x18000c554  lea     rdx, aPtreleasememor_0; "PTReleaseMemory"
0x18000c55b  mov     rcx, rbx; hModule
0x18000c55e  mov     cs:qword_180032200, rax
0x18000c565  call    cs:__imp_GetProcAddress
0x18000c56b  lea     rdx, aPtconvertdevmo_0; "PTConvertDevModeToPrintTicket"
0x18000c572  mov     rcx, rbx; hModule
0x18000c575  mov     cs:qword_180032208, rax
0x18000c57c  call    cs:__imp_GetProcAddress
0x18000c582  lea     rdx, aGetprintcapabi_1; "GetPrintCapabilitiesThunk2"
0x18000c589  mov     rcx, rbx; hModule
0x18000c58c  mov     cs:qword_180032210, rax
0x18000c593  call    cs:__imp_GetProcAddress
0x18000c599  lea     rdx, aMergeandvalida_1; "MergeAndValidatePrintTicketThunk2"
0x18000c5a0  mov     rcx, rbx; hModule
0x18000c5a3  mov     cs:qword_180032218, rax
0x18000c5aa  call    cs:__imp_GetProcAddress
0x18000c5b0  lea     rdx, aConvertdevmode_1; "ConvertDevModeToPrintTicketThunk2"
0x18000c5b7  mov     rcx, rbx; hModule
0x18000c5ba  mov     cs:qword_180032220, rax
0x18000c5c1  call    cs:__imp_GetProcAddress
0x18000c5c7  lea     rdx, aConvertprintti_1; "ConvertPrintTicketToDevModeThunk2"
0x18000c5ce  mov     rcx, rbx; hModule
0x18000c5d1  mov     cs:qword_180032228, rax
0x18000c5d8  call    cs:__imp_GetProcAddress
0x18000c5de  lea     rdx, aGetprintdevice_3; "GetPrintDeviceCapabilitiesThunk2"
0x18000c5e5  mov     rcx, rbx; hModule
0x18000c5e8  mov     cs:qword_180032230, rax
0x18000c5ef  call    cs:__imp_GetProcAddress
0x18000c5f5  lea     rdx, aGetprintdevice_4; "GetPrintDeviceResourcesThunk2"
0x18000c5fc  mov     rcx, rbx; hModule
0x18000c5ff  mov     cs:qword_180032238, rax
0x18000c606  call    cs:__imp_GetProcAddress
0x18000c60c  xor     ecx, ecx
0x18000c60e  mov     cs:qword_180032240, rax
0x18000c615  cmp     cs:?g_pfnPrntvptIAT@@3U_PRNTVPT_IAT_HOOKS@@A, rcx; _PRNTVPT_IAT_HOOKS g_pfnPrntvptIAT
0x18000c61c  jz      short loc_18000C69B
0x18000c61e  cmp     cs:qword_1800321D8, rcx
0x18000c625  jz      short loc_18000C69B
0x18000c627  cmp     cs:qword_1800321E0, rcx
0x18000c62e  jz      short loc_18000C69B
0x18000c630  cmp     cs:qword_1800321E8, rcx
0x18000c637  jz      short loc_18000C69B
0x18000c639  cmp     cs:qword_1800321F0, rcx
0x18000c640  jz      short loc_18000C69B
0x18000c642  cmp     cs:qword_1800321F8, rcx
0x18000c649  jz      short loc_18000C69B
0x18000c64b  cmp     cs:qword_180032200, rcx
0x18000c652  jz      short loc_18000C69B
0x18000c654  cmp     cs:qword_180032208, rcx
0x18000c65b  jz      short loc_18000C69B
0x18000c65d  cmp     cs:qword_180032210, rcx
0x18000c664  jz      short loc_18000C69B
0x18000c666  cmp     cs:qword_180032218, rcx
0x18000c66d  jz      short loc_18000C69B
0x18000c66f  cmp     cs:qword_180032220, rcx
0x18000c676  jz      short loc_18000C69B
0x18000c678  cmp     cs:qword_180032228, rcx
0x18000c67f  jz      short loc_18000C69B
0x18000c681  cmp     cs:qword_180032230, rcx
0x18000c688  jz      short loc_18000C69B
0x18000c68a  cmp     cs:qword_180032238, rcx
0x18000c691  jz      short loc_18000C69B
0x18000c693  test    rax, rax
0x18000c696  lea     eax, [rcx+1]
0x18000c699  jnz     short loc_18000C69D
0x18000c69b  mov     eax, ecx
0x18000c69d  add     rsp, 20h
0x18000c6a1  pop     rbx
0x18000c6a2  retn
```
