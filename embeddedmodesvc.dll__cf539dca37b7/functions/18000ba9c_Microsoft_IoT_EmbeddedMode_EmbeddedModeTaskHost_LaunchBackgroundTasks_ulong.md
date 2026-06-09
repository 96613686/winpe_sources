# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(ulong)

- ea: `0x18000ba9c`
- end: `0x18000bb3c`
- name: `?LaunchBackgroundTasks@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJK@Z`
- size: `160`
- prototype: `__int64 __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007cec`
- `0x18000b6a4`

## callees

- `0x180008378`
- `0x18000ba64`
- `0x18000ba9c`
- `0x18000bb44`
- `0x180010db8`

## string_xrefs

- `0x18000bae4`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`
- `0x18000bb20`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this,
        __int64 a2)
{
  int v2; // ebx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  Microsoft::IoT::ShellExtension::CCBTLauncher *v7; // [rsp+78h] [rbp+20h] BYREF

  v7 = 0;
  v2 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession(this, a2, &v7);
  if ( v2 >= 0 )
  {
    if ( v7 )
    {
      v3 = Microsoft::IoT::ShellExtension::CCBTLauncher::AsyncLaunchCBT(v7);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
          (const char *)(unsigned int)v3,
          v5);
    }
  }
  Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(&v7);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ba9c  push    rbx
0x18000ba9e  sub     rsp, 50h
0x18000baa2  mov     [rsp+58h+arg_18], 0
0x18000baab  lea     r8, [rsp+58h+arg_18]
0x18000bab0  call    ?LauncherFromSession@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@AEAAJKAEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@4@@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession(ulong,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &)
0x18000bab5  mov     ebx, eax
0x18000bab7  test    eax, eax
0x18000bab9  jns     short loc_18000BAC9
0x18000babb  lea     rcx, [rsp+58h+arg_18]
0x18000bac0  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x18000bac5  mov     eax, ebx
0x18000bac7  jmp     short loc_18000BB35
0x18000bac9  mov     rcx, [rsp+58h+arg_18]; this
0x18000bace  test    rcx, rcx
0x18000bad1  jz      short loc_18000BAF6
0x18000bad3  call    ?AsyncLaunchCBT@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::AsyncLaunchCBT(void)
0x18000bad8  mov     rcx, [rsp+58h]; this
0x18000badd  test    eax, eax
0x18000badf  jns     short loc_18000BAF6
0x18000bae1  mov     r9d, eax; char *
0x18000bae4  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000baeb  mov     edx, 4Ch ; 'L'; void *
0x18000baf0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000baf5  nop
0x18000baf6  mov     dword ptr [rsp+58h+arg_10], ebx
0x18000bafa  lea     rcx, [rsp+58h+arg_18]
0x18000baff  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x18000bb04  nop
0x18000bb05  jmp     short loc_18000BB31
0x18000bb07  cmp     dword ptr [rsp+58h+arg_10], 0
0x18000bb0c  jge     short loc_18000BB31
0x18000bb0e  jmp     short loc_18000BB16
0x18000bb10  jmp     short loc_18000BB16
0x18000bb12  jmp     short loc_18000BB16
0x18000bb14  jmp     short $+2
0x18000bb16  mov     rcx, [rsp+58h]; this
0x18000bb1b  mov     r9d, dword ptr [rsp+58h+arg_10]; char *
0x18000bb20  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000bb27  mov     edx, 4Fh ; 'O'; void *
0x18000bb2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bb31  mov     eax, dword ptr [rsp+58h+arg_10]
0x18000bb35  add     rsp, 50h
0x18000bb39  pop     rbx
0x18000bb3a  retn
```
