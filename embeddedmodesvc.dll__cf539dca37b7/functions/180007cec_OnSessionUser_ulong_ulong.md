# OnSessionUser(ulong,ulong)

- ea: `0x180007cec`
- end: `0x180007dbf`
- name: `?OnSessionUser@@YAXKK@Z`
- size: `211`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007e50`

## callees

- `0x180007cec`
- `0x180007dd0`
- `0x180008378`
- `0x18000b9cc`
- `0x18000ba9c`
- `0x18000c1a4`

## string_xrefs

- `0x180007d4b`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\servicemain.cpp`
- `0x180007d96`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall OnSessionUser(int a1, unsigned int a2)
{
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v3; // rbx
  int v4; // edi
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v5; // rbx
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v9; // [rsp+40h] [rbp+18h] BYREF

  if ( a1 == 5 )
  {
    if ( !g_fAllowEmbeddedMode )
      return;
    Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(&v9);
    v3 = v9;
    if ( v9 )
    {
      v4 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(v9, a2);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v3);
      if ( v4 >= 0 )
        return;
    }
    else
    {
      v4 = -2147418113;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\servicemain.cpp",
      (const char *)(unsigned int)v4,
      v7);
  }
  else if ( a1 == 6 && g_fAllowEmbeddedMode )
  {
    Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(&v9);
    v5 = v9;
    if ( v9 )
    {
      v6 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::StopUserSession(v9, a2);
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\servicemain.cpp",
          (const char *)(unsigned int)v6,
          v7);
      if ( v5 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v5);
    }
  }
}

```

## disassembly

```asm
0x180007cec  mov     [rsp+arg_0], rbx
0x180007cf1  push    rdi; int
0x180007cf2  sub     rsp, 20h
0x180007cf6  mov     edi, edx
0x180007cf8  cmp     ecx, 5
0x180007cfb  jnz     short loc_180007D5E
0x180007cfd  cmp     cs:?g_fAllowEmbeddedMode@@3_NA, 0; bool g_fAllowEmbeddedMode
0x180007d04  jz      loc_180007DB4
0x180007d0a  lea     rcx, [rsp+28h+arg_10]
0x180007d0f  call    ?Instance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@SA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@XZ; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(void)
0x180007d14  nop
0x180007d15  mov     rbx, [rsp+28h+arg_10]
0x180007d1a  test    rbx, rbx
0x180007d1d  jnz     short loc_180007D26
0x180007d1f  mov     edi, 8000FFFFh
0x180007d24  jmp     short loc_180007D43
0x180007d26  mov     edx, edi; unsigned int
0x180007d28  mov     rcx, rbx; this
0x180007d2b  call    ?LaunchBackgroundTasks@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJK@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(ulong)
0x180007d30  mov     edi, eax
0x180007d32  test    rbx, rbx
0x180007d35  jz      short loc_180007D3F
0x180007d37  mov     rcx, rbx
0x180007d3a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x180007d3f  test    edi, edi
0x180007d41  jns     short loc_180007DB4
0x180007d43  mov     rcx, [rsp+28h]; this
0x180007d48  mov     r9d, edi; char *
0x180007d4b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180007d52  mov     edx, 0BBh; void *
0x180007d57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007d5c  jmp     short loc_180007DB4
0x180007d5e  cmp     ecx, 6
0x180007d61  jnz     short loc_180007DB4
0x180007d63  cmp     cs:?g_fAllowEmbeddedMode@@3_NA, 0; bool g_fAllowEmbeddedMode
0x180007d6a  jz      short loc_180007DB4
0x180007d6c  lea     rcx, [rsp+28h+arg_10]
0x180007d71  call    ?Instance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@SA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@XZ; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(void)
0x180007d76  mov     rbx, [rsp+28h+arg_10]
0x180007d7b  test    rbx, rbx
0x180007d7e  jz      short loc_180007DB4
0x180007d80  mov     edx, edi; unsigned int
0x180007d82  mov     rcx, rbx; this
0x180007d85  call    ?StopUserSession@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJK@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::StopUserSession(ulong)
0x180007d8a  test    eax, eax
0x180007d8c  jns     short loc_180007DA7
0x180007d8e  mov     rcx, [rsp+28h]; this
0x180007d93  mov     r9d, eax; char *
0x180007d96  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180007d9d  mov     edx, 0C6h; void *
0x180007da2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007da7  test    rbx, rbx
0x180007daa  jz      short loc_180007DB4
0x180007dac  mov     rcx, rbx
0x180007daf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x180007db4  mov     rbx, [rsp+28h+arg_0]
0x180007db9  add     rsp, 20h
0x180007dbd  pop     rdi
0x180007dbe  retn
```
