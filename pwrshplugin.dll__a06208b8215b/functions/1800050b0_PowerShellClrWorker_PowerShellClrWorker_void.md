# PowerShellClrWorker::PowerShellClrWorker(void)

- ea: `0x1800050b0`
- end: `0x18000519d`
- name: `??0PowerShellClrWorker@@QEAA@XZ`
- size: `237`
- prototype: `PowerShellClrWorker *__fastcall(PowerShellClrWorker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003158`

## callees

- `0x180001098`
- `0x1800050b0`
- `0x180007428`

## string_xrefs

- `0x1800050fe`: `InitPlugin`
- `0x180005109`: `ShutdownPlugin`
- `0x180005114`: `WSManPluginShell`
- `0x18000511f`: `WSManPluginReleaseShellContext`
- `0x18000512a`: `WSManPluginCommand`
- `0x180005135`: `WSManPluginReleaseCommandContext`
- `0x180005140`: `WSManPluginSend`
- `0x18000514b`: `WSManPluginReceive`
- `0x180005156`: `WSManPluginSignal`
- `0x180005161`: `WSManPluginConnect`

## pseudocode

```c
PowerShellClrWorker *__fastcall PowerShellClrWorker::PowerShellClrWorker(PowerShellClrWorker *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *(_QWORD *)this = &PowerShellClrWorker::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v2 = operator new(8u);
  if ( v2 )
    *v2 = &NativeMsh::PwrshCommonOutputDefault::`vftable';
  *((_QWORD *)this + 3) = v2;
  NativeMsh::PwrshCommon::PwrshCommon((PowerShellClrWorker *)((char *)this + 32));
  *((_QWORD *)this + 7) = "InitPlugin";
  *((_QWORD *)this + 8) = "ShutdownPlugin";
  *((_QWORD *)this + 9) = "WSManPluginShell";
  *((_QWORD *)this + 10) = "WSManPluginReleaseShellContext";
  *((_QWORD *)this + 11) = "WSManPluginCommand";
  *((_QWORD *)this + 12) = "WSManPluginReleaseCommandContext";
  *((_QWORD *)this + 13) = "WSManPluginSend";
  *((_QWORD *)this + 14) = "WSManPluginReceive";
  *((_QWORD *)this + 15) = "WSManPluginSignal";
  *((_QWORD *)this + 16) = "WSManPluginConnect";
  v3 = operator new(8u);
  if ( v3 )
    *v3 = &NativeMsh::WinSystemCallFacade::`vftable';
  *((_QWORD *)this + 17) = v3;
  return this;
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp+arg_0], rcx
0x1800050b5  push    rbx
0x1800050b6  sub     rsp, 20h
0x1800050ba  mov     rbx, rcx
0x1800050bd  lea     rax, ??_7PowerShellClrWorker@@6B@; const PowerShellClrWorker::`vftable'
0x1800050c4  mov     [rcx], rax
0x1800050c7  mov     qword ptr [rcx+8], 0
0x1800050cf  mov     qword ptr [rcx+10h], 0
0x1800050d7  mov     ecx, 8; Size
0x1800050dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050e1  test    rax, rax
0x1800050e4  jz      short loc_1800050F0
0x1800050e6  lea     rcx, ??_7PwrshCommonOutputDefault@NativeMsh@@6B@; const NativeMsh::PwrshCommonOutputDefault::`vftable'
0x1800050ed  mov     [rax], rcx
0x1800050f0  mov     [rbx+18h], rax
0x1800050f4  lea     rcx, [rbx+20h]; this
0x1800050f8  call    ??0PwrshCommon@NativeMsh@@QEAA@XZ; NativeMsh::PwrshCommon::PwrshCommon(void)
0x1800050fd  nop
0x1800050fe  lea     rax, aInitplugin; "InitPlugin"
0x180005105  mov     [rbx+38h], rax
0x180005109  lea     rax, aShutdownplugin; "ShutdownPlugin"
0x180005110  mov     [rbx+40h], rax
0x180005114  lea     rax, aWsmanpluginshe_0; "WSManPluginShell"
0x18000511b  mov     [rbx+48h], rax
0x18000511f  lea     rax, aWsmanpluginrel_2; "WSManPluginReleaseShellContext"
0x180005126  mov     [rbx+50h], rax
0x18000512a  lea     rax, aWsmanplugincom_0; "WSManPluginCommand"
0x180005131  mov     [rbx+58h], rax
0x180005135  lea     rax, aWsmanpluginrel_1; "WSManPluginReleaseCommandContext"
0x18000513c  mov     [rbx+60h], rax
0x180005140  lea     rax, aWsmanpluginsen_1; "WSManPluginSend"
0x180005147  mov     [rbx+68h], rax
0x18000514b  lea     rax, aWsmanpluginrec_1; "WSManPluginReceive"
0x180005152  mov     [rbx+70h], rax
0x180005156  lea     rax, aWsmanpluginsig_0; "WSManPluginSignal"
0x18000515d  mov     [rbx+78h], rax
0x180005161  lea     rax, aWsmanplugincon_1; "WSManPluginConnect"
0x180005168  mov     [rbx+80h], rax
0x18000516f  mov     ecx, 8; Size
0x180005174  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005179  mov     [rsp+28h+arg_0], rax
0x18000517e  test    rax, rax
0x180005181  jz      short loc_18000518D
0x180005183  lea     rcx, ??_7WinSystemCallFacade@NativeMsh@@6B@; const NativeMsh::WinSystemCallFacade::`vftable'
0x18000518a  mov     [rax], rcx
0x18000518d  mov     [rbx+88h], rax
0x180005194  mov     rax, rbx
0x180005197  add     rsp, 20h
0x18000519b  pop     rbx
0x18000519c  retn
```
