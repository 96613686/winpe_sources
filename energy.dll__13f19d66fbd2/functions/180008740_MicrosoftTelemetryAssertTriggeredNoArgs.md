# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180008740`
- end: `0x1800087e2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `191`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e70`
- `0x1800043a0`
- `0x1800056dc`
- `0x180005fa4`
- `0x180006de0`
- `0x180006ec0`
- `0x180007830`
- `0x180007920`
- `0x180008f30`
- `0x180009d88`
- `0x18000b734`
- `0x18000b9ec`
- `0x18000ce84`
- `0x18000f3f0`
- `0x18000f420`
- `0x18000f788`
- `0x1800103f0`
- `0x180010ac4`
- `0x1800110c4`
- `0x1800110f0`
- `0x180011fd4`
- `0x180012064`
- `0x18001292c`
- `0x180012a98`
- `0x180012ac4`
- `0x180013260`
- `0x180013f50`
- `0x18001464c`
- `0x18001489c`
- `0x180014e08`
- `0x180014e34`
- `0x180014ec4`
- `0x180014fd0`
- `0x18001520c`
- `0x180015860`
- `0x180015900`
- `0x180015b18`
- `0x180016698`
- `0x1800168ac`
- `0x180018338`
- `0x18001872c`
- `0x18001db80`
- `0x18001e7f4`
- `0x18001f44c`
- `0x180023560`
- `0x180025018`
- `0x180025fc8`
- `0x18002647c`
- `0x1800276f0`
- `0x18002b690`

## callees

- `0x180008740`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000877b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000877b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180008761`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180008761`

## string_xrefs

- `0x180008755`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+40h] [rbp-20h]
  __int64 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+50h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
  HMODULE phModule; // [rsp+70h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v6 = 1;
        v2[1] = &_ImageBase;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        v4 = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180008740  push    rbp
0x180008742  mov     rbp, rsp
0x180008745  sub     rsp, 60h
0x180008749  lea     r8, [rbp+phModule]; phModule
0x18000874d  mov     [rbp+phModule], 0
0x180008755  lea     rdx, ModuleName; "ntdll.dll"
0x18000875c  mov     ecx, 2; dwFlags
0x180008761  call    cs:__imp_GetModuleHandleExA
0x180008767  test    eax, eax
0x180008769  jz      short loc_1800087DC
0x18000876b  mov     rcx, [rbp+phModule]; hModule
0x18000876f  test    rcx, rcx
0x180008772  jz      short loc_1800087DC
0x180008774  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000877b  call    cs:__imp_GetProcAddress
0x180008781  mov     rdx, rax
0x180008784  test    rax, rax
0x180008787  jz      short loc_1800087DC
0x180008789  xor     eax, eax
0x18000878b  lea     rcx, [rbp+var_40]
0x18000878f  mov     [rbp+var_10], eax
0x180008792  xorps   xmm0, xmm0
0x180008795  movups  [rbp+var_20], xmm0
0x180008799  lea     rax, __ImageBase
0x1800087a0  movups  [rbp+var_40], xmm0
0x1800087a4  mov     qword ptr [rbp+var_40+8], rax
0x1800087a8  mov     rax, [rbp+8]
0x1800087ac  movups  [rbp+var_30], xmm0
0x1800087b0  mov     qword ptr [rbp+var_30], rax
0x1800087b4  or      eax, 0FFFFFFFFh
0x1800087b7  mov     dword ptr [rbp+var_20+8], eax
0x1800087ba  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800087bd  mov     rax, rdx
0x1800087c0  mov     dword ptr [rbp+var_40], 0Bh
0x1800087c7  mov     byte ptr [rbp+var_10], 1
0x1800087cb  mov     byte ptr [rbp+var_30+8], 0
0x1800087cf  mov     qword ptr [rbp+var_20], 0
0x1800087d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087dc  add     rsp, 60h
0x1800087e0  pop     rbp
0x1800087e1  retn
```
