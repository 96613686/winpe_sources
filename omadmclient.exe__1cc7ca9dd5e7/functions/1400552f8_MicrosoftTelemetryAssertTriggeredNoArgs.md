# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1400552f8`
- end: `0x1400553a7`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `59`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d860`
- `0x140014894`
- `0x140015660`
- `0x140015d88`
- `0x1400165b0`
- `0x140016d30`
- `0x140016dec`
- `0x14001da10`
- `0x14001dbb0`
- `0x14001dcf0`
- `0x14001de40`
- `0x14001e010`
- `0x14001e100`
- `0x14001e2e0`
- `0x14001e4f0`
- `0x1400211e0`
- `0x140022fac`
- `0x140026628`
- `0x140026eac`
- `0x140027510`
- `0x140027ad0`
- `0x140027e10`
- `0x1400280f0`
- `0x140028328`
- `0x1400285f0`
- `0x140028940`
- `0x1400294c0`
- `0x14002a60c`
- `0x14002ae20`
- `0x14002b2d4`
- `0x14002b464`
- `0x14002c19c`
- `0x14002c550`
- `0x14002d1d4`
- `0x14002da10`
- `0x14002e410`
- `0x14002f3c0`
- `0x14002fcec`
- `0x1400305d0`
- `0x140030eb0`
- `0x140031980`
- `0x140031fc0`
- `0x140039d60`
- `0x14003af40`
- `0x14003b9f0`
- `0x14003d890`
- `0x14003fb98`
- `0x1400409e0`
- `0x140040ef0`
- `0x1400410b0`

## callees

- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140055339`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140055339`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140055319`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140055319`

## string_xrefs

- `0x14005530d`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredNoArgs()
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
0x1400552f8  push    rbp
0x1400552fa  mov     rbp, rsp
0x1400552fd  sub     rsp, 60h
0x140055301  lea     r8, [rbp+phModule]; phModule
0x140055305  mov     [rbp+phModule], 0
0x14005530d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140055314  mov     ecx, 2; dwFlags
0x140055319  call    cs:__imp_GetModuleHandleExA
0x140055320  nop     dword ptr [rax+rax+00h]
0x140055325  test    eax, eax
0x140055327  jz      short loc_1400553A0
0x140055329  mov     rcx, [rbp+phModule]; hModule
0x14005532d  test    rcx, rcx
0x140055330  jz      short loc_1400553A0
0x140055332  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140055339  call    cs:__imp_GetProcAddress
0x140055340  nop     dword ptr [rax+rax+00h]
0x140055345  mov     rdx, rax
0x140055348  test    rax, rax
0x14005534b  jz      short loc_1400553A0
0x14005534d  xor     eax, eax
0x14005534f  lea     rcx, [rbp+var_40]
0x140055353  mov     [rbp+var_10], eax
0x140055356  xorps   xmm0, xmm0
0x140055359  movups  [rbp+var_20], xmm0
0x14005535d  lea     rax, __ImageBase
0x140055364  movups  [rbp+var_40], xmm0
0x140055368  mov     qword ptr [rbp+var_40+8], rax
0x14005536c  mov     rax, [rbp+8]
0x140055370  movups  [rbp+var_30], xmm0
0x140055374  mov     qword ptr [rbp+var_30], rax
0x140055378  or      eax, 0FFFFFFFFh
0x14005537b  mov     dword ptr [rbp+var_20+8], eax
0x14005537e  mov     dword ptr [rbp+var_20+0Ch], eax
0x140055381  mov     rax, rdx
0x140055384  mov     dword ptr [rbp+var_40], 0Bh
0x14005538b  mov     byte ptr [rbp+var_10], 1
0x14005538f  mov     byte ptr [rbp+var_30+8], 0
0x140055393  mov     qword ptr [rbp+var_20], 0
0x14005539b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400553a0  add     rsp, 60h
0x1400553a4  pop     rbp
0x1400553a5  retn
```
