# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(void)

- ea: `0x18000b9cc`
- end: `0x18000ba5e`
- name: `?Instance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@SA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@XZ`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007cec`
- `0x180008018`
- `0x1800081c4`
- `0x180009690`

## callees

- `0x180007dd0`
- `0x180008378`
- `0x180008778`
- `0x180009b28`
- `0x18000b804`
- `0x18000b9cc`
- `0x18000bea0`

## string_xrefs

- `0x18000ba29`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Instance(
        Microsoft::WRL::FtmBase *a1,
        volatile int *a2)
{
  char *v3; // rax
  Microsoft::WRL::FtmBase *v4; // rcx
  int v5; // eax
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Microsoft::WRL::FtmBase *v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = a1;
  if ( !Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance )
  {
    v3 = (char *)Microsoft::WRL::Details::Make<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost,>(&v9);
    Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::operator=(
      (__int64 *)&Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance,
      v3);
    v4 = v9;
    if ( v9 )
    {
      v9 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v4);
    }
    v5 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A,
        (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
        (const char *)(unsigned int)v5);
  }
  v6 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance;
  *(_QWORD *)a1 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance;
  if ( v6 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference(
      (Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *)((char *)v6 + 44),
      a2);
  return a1;
}

```

## disassembly

```asm
0x18000b9cc  mov     [rsp+arg_0], rcx
0x18000b9d1  push    rbx
0x18000b9d2  sub     rsp, 30h
0x18000b9d6  cmp     cs:?m_spInstance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@0V?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@A, 0; Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost> Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance
0x18000b9de  mov     rbx, rcx
0x18000b9e1  jnz     short loc_18000BA3D
0x18000b9e3  lea     rcx, [rsp+38h+arg_0]
0x18000b9e8  call    ??$Make@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@12@XZ; Microsoft::WRL::Details::Make<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost,>(void)
0x18000b9ed  mov     rdx, rax
0x18000b9f0  lea     rcx, ?m_spInstance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@0V?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@A; Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost> Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance
0x18000b9f7  call    ??4?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::operator=(Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost> &&)
0x18000b9fc  mov     rcx, [rsp+38h+arg_0]
0x18000ba01  test    rcx, rcx
0x18000ba04  jz      short loc_18000BA14
0x18000ba06  mov     [rsp+38h+arg_0], 0
0x18000ba0f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x18000ba14  mov     rcx, cs:?m_spInstance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@0V?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@A; this
0x18000ba1b  call    ?Initialize@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize(void)
0x18000ba20  test    eax, eax
0x18000ba22  jns     short loc_18000BA3D
0x18000ba24  mov     rcx, [rsp+38h]; this
0x18000ba29  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000ba30  mov     r9d, eax; char *
0x18000ba33  mov     edx, 1Ah; void *
0x18000ba38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ba3d  mov     rcx, cs:?m_spInstance@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@0V?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@WRL@4@A; Microsoft::WRL::ComPtr<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost> Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::m_spInstance
0x18000ba44  mov     [rbx], rcx
0x18000ba47  test    rcx, rcx
0x18000ba4a  jz      short loc_18000BA55
0x18000ba4c  add     rcx, 2Ch ; ','; this
0x18000ba50  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000ba55  mov     rax, rbx
0x18000ba58  add     rsp, 30h
0x18000ba5c  pop     rbx
0x18000ba5d  retn
```
