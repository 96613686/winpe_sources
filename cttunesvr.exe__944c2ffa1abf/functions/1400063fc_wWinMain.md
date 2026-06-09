# wWinMain

- ea: `0x1400063fc`
- end: `0x14000643f`
- name: `wWinMain`
- size: `67`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001380`

## callees

- `0x140005ce4`
- `0x140005f38`
- `0x1400063fc`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x140006416`
- `KERNEL32!GetCommandLineW` at `0x140006416`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LPWSTR CommandLineW; // rax
  __int64 v6; // rcx
  int v7[6]; // [rsp+20h] [rbp-18h] BYREF

  if ( ATL::CAtlBaseModule::m_bInitFailed )
    return -1;
  v7[0] = 0;
  CommandLineW = GetCommandLineW();
  if ( (unsigned __int8)ATL::CAtlExeModuleT<CcttunesvrModule>::ParseCommandLine(v6, CommandLineW, v7) == 1 )
    return ATL::CAtlExeModuleT<CcttunesvrModule>::Run();
  else
    return v7[0];
}

```

## disassembly

```asm
0x1400063fc  sub     rsp, 38h
0x140006400  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x140006407  jz      short loc_14000640E
0x140006409  or      eax, 0FFFFFFFFh
0x14000640c  jmp     short loc_14000643A
0x14000640e  mov     [rsp+38h+var_18], 0
0x140006416  call    cs:__imp_GetCommandLineW
0x14000641c  mov     rdx, rax
0x14000641f  lea     r8, [rsp+38h+var_18]
0x140006424  call    ?ParseCommandLine@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@QEAA_NPEBGPEAJ@Z; ATL::CAtlExeModuleT<CcttunesvrModule>::ParseCommandLine(ushort const *,long *)
0x140006429  cmp     al, 1
0x14000642b  jnz     short loc_140006436
0x14000642d  add     rsp, 38h
0x140006431  jmp     ?Run@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@QEAAJH@Z; ATL::CAtlExeModuleT<CcttunesvrModule>::Run(int)
0x140006436  mov     eax, [rsp+38h+var_18]
0x14000643a  add     rsp, 38h
0x14000643e  retn
```
