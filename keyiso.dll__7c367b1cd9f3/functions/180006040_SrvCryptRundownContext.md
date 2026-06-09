# SrvCryptRundownContext

- ea: `0x180006040`
- end: `0x1800060fe`
- name: `SrvCryptRundownContext`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004470`
- `0x180006040`
- `0x180006104`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006098`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006098`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000606a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000606a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006080`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006080`

## string_xrefs

- `0x1800060d4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180006079`: `SKCacheFlush`

## pseudocode

```c
__int64 __fastcall SrvCryptRundownContext(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  HMODULE phModule; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = a1;
  if ( a1 )
  {
    phModule = 0;
    if ( GetModuleHandleExW(0, L"NCRYPTPROV", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "SKCacheFlush");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD))ProcAddress)(*(unsigned int *)(a1 + 16));
      FreeLibrary(phModule);
    }
    SrvRemoveContextFromList(&v8);
    return 0;
  }
  else
  {
    v5 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        248);
  }
  return v5;
}

```

## disassembly

```asm
0x180006040  push    rbx
0x180006042  sub     rsp, 40h
0x180006046  mov     [rsp+48h+arg_8], rcx
0x18000604b  mov     rbx, rcx
0x18000604e  test    rcx, rcx
0x180006051  jz      short loc_1800060B2
0x180006053  lea     r8, [rsp+48h+phModule]; phModule
0x180006058  mov     [rsp+48h+phModule], 0
0x180006061  lea     rdx, ModuleName; "NCRYPTPROV"
0x180006068  xor     ecx, ecx; dwFlags
0x18000606a  call    cs:__imp_GetModuleHandleExW
0x180006070  test    eax, eax
0x180006072  jz      short loc_18000609E
0x180006074  mov     rcx, [rsp+48h+phModule]; hModule
0x180006079  lea     rdx, aSkcacheflush; "SKCacheFlush"
0x180006080  call    cs:__imp_GetProcAddress
0x180006086  test    rax, rax
0x180006089  jz      short loc_180006093
0x18000608b  mov     ecx, [rbx+10h]
0x18000608e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006093  mov     rcx, [rsp+48h+phModule]; hLibModule
0x180006098  call    cs:__imp_FreeLibrary
0x18000609e  lea     rcx, [rsp+48h+arg_8]
0x1800060a3  call    SrvRemoveContextFromList
0x1800060a8  xor     ebx, ebx
0x1800060aa  mov     eax, ebx
0x1800060ac  add     rsp, 40h
0x1800060b0  pop     rbx
0x1800060b1  retn
0x1800060b2  mov     ebx, 80090026h
0x1800060b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060be  lea     rax, WPP_GLOBAL_Control
0x1800060c5  cmp     rcx, rax
0x1800060c8  jz      short loc_1800060AA
0x1800060ca  test    byte ptr [rcx+1Ch], 1
0x1800060ce  jz      short loc_1800060AA
0x1800060d0  mov     rcx, [rcx+10h]
0x1800060d4  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800060db  mov     [rsp+48h+var_18], 1F8h
0x1800060e3  lea     r9, aStatus; "Status"
0x1800060ea  mov     [rsp+48h+var_20], rax
0x1800060ef  mov     [rsp+48h+var_28], 80090026h
0x1800060f7  call    WPP_SF_sDsd
0x1800060fc  jmp     short loc_1800060AA
```
