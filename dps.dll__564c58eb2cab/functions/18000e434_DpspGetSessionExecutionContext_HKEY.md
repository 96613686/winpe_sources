# DpspGetSessionExecutionContext(HKEY__ *)

- ea: `0x18000e434`
- end: `0x18000e4c1`
- name: `?DpspGetSessionExecutionContext@@YA?AW4HOSTTYPE@@PEAUHKEY__@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ed8c`

## callees

- `0x180008ea0`
- `0x18000e434`
- `0x1800178a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e46e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e489`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e49f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e46e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e489`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e49f`

## string_xrefs

- `0x18000e482`: `LocalServiceNoNetwork`
- `0x18000e498`: `LocalService`

## pseudocode

```c
__int64 __fastcall DpspGetSessionExecutionContext(HKEY a1)
{
  unsigned int v1; // ebx
  __int64 v3; // [rsp+48h] [rbp+10h] BYREF
  __int64 v4; // [rsp+50h] [rbp+18h]

  v4 = 0;
  v1 = 0;
  if ( (int)WdipRegReadValueAlloc(a1, L"ExecutionContext", (__int64)&v3) >= 0 )
  {
    if ( (unsigned int)_o__wcsicmp(v4, L"LocalSystemNetworkRestricted") )
    {
      if ( (unsigned int)_o__wcsicmp(v4, L"LocalServiceNoNetwork") )
        v1 = _o__wcsicmp(v4, L"LocalService") == 0;
    }
    else
    {
      v1 = 2;
    }
  }
  WdipFree(v4);
  return v1;
}

```

## disassembly

```asm
0x18000e434  mov     r11, rsp
0x18000e437  push    rbx
0x18000e438  sub     rsp, 30h
0x18000e43c  lea     rax, [r11+10h]
0x18000e440  mov     qword ptr [r11+18h], 0
0x18000e448  lea     r9, [r11+18h]
0x18000e44c  mov     [r11-18h], rax
0x18000e450  lea     rdx, aExecutionconte; "ExecutionContext"
0x18000e457  xor     ebx, ebx
0x18000e459  call    WdipRegReadValueAlloc
0x18000e45e  test    eax, eax
0x18000e460  js      short loc_18000E4AF
0x18000e462  mov     rcx, [rsp+38h+arg_10]
0x18000e467  lea     rdx, aLocalsystemnet; "LocalSystemNetworkRestricted"
0x18000e46e  call    cs:__imp__o__wcsicmp
0x18000e474  test    eax, eax
0x18000e476  jnz     short loc_18000E47D
0x18000e478  lea     ebx, [rax+2]
0x18000e47b  jmp     short loc_18000E4AF
0x18000e47d  mov     rcx, [rsp+38h+arg_10]
0x18000e482  lea     rdx, aLocalserviceno; "LocalServiceNoNetwork"
0x18000e489  call    cs:__imp__o__wcsicmp
0x18000e48f  test    eax, eax
0x18000e491  jz      short loc_18000E4AF
0x18000e493  mov     rcx, [rsp+38h+arg_10]
0x18000e498  lea     rdx, aLocalservice; "LocalService"
0x18000e49f  call    cs:__imp__o__wcsicmp
0x18000e4a5  test    eax, eax
0x18000e4a7  mov     ecx, 1
0x18000e4ac  cmovz   ebx, ecx
0x18000e4af  mov     rcx, [rsp+38h+arg_10]
0x18000e4b4  call    WdipFree
0x18000e4b9  mov     eax, ebx
0x18000e4bb  add     rsp, 30h
0x18000e4bf  pop     rbx
0x18000e4c0  retn
```
