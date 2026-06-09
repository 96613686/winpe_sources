# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl> *,_GUID const &,void * *)

- ea: `0x1800099f4`
- end: `0x180009a8a`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `150`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bdb0`

## callees

- `0x1800099f4`
- `0x18000b5c0`
- `0x18000b99c`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  void **v4; // r8
  Microsoft::WRL::FtmBase *v5; // r11
  int CanCastTo; // ebx
  _QWORD *v7; // r8
  int v8; // r9d
  __int64 v9; // r11

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  else
  {
    CanCastTo = Microsoft::WRL::FtmBase::CanCastTo(v5, a2, v4);
    if ( CanCastTo == -2147467262 )
    {
      if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_e094208a_86fa_460b_8afa_2fc14ec39138) )
      {
        *v7 = v9 + 32;
        CanCastTo = 0;
      }
      else
      {
        CanCastTo = v8;
      }
    }
    if ( CanCastTo >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    return (unsigned int)CanCastTo;
  }
}

```

## disassembly

```asm
0x1800099f4  mov     [rsp+arg_0], rbx
0x1800099f9  push    rdi
0x1800099fa  sub     rsp, 20h
0x1800099fe  mov     rdi, rdx
0x180009a01  mov     r11, rcx
0x180009a04  mov     qword ptr [r8], 0
0x180009a0b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180009a12  mov     rcx, rdi; struct _GUID *
0x180009a15  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009a1a  mov     rcx, r11; this
0x180009a1d  test    eax, eax
0x180009a1f  jnz     short loc_180009A6E
0x180009a21  mov     rdx, rdi; struct _GUID *
0x180009a24  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x180009a29  mov     ebx, eax
0x180009a2b  mov     r9d, 80004002h
0x180009a31  cmp     eax, r9d
0x180009a34  jnz     short loc_180009A57
0x180009a36  lea     rdx, _GUID_e094208a_86fa_460b_8afa_2fc14ec39138; struct _GUID *
0x180009a3d  mov     rcx, rdi; struct _GUID *
0x180009a40  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180009a45  test    eax, eax
0x180009a47  jz      short loc_180009A54
0x180009a49  lea     rax, [r11+20h]
0x180009a4d  mov     [r8], rax
0x180009a50  xor     ebx, ebx
0x180009a52  jmp     short loc_180009A57
0x180009a54  mov     ebx, r9d
0x180009a57  test    ebx, ebx
0x180009a59  js      short loc_180009A6A
0x180009a5b  mov     rcx, [r8]
0x180009a5e  mov     rax, [rcx]
0x180009a61  mov     rax, [rax+8]
0x180009a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a6a  mov     eax, ebx
0x180009a6c  jmp     short loc_180009A7F
0x180009a6e  mov     [r8], r11
0x180009a71  mov     rax, [r11]
0x180009a74  mov     rax, [rax+8]
0x180009a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7d  xor     eax, eax
0x180009a7f  mov     rbx, [rsp+28h+arg_0]
0x180009a84  add     rsp, 20h
0x180009a88  pop     rdi
0x180009a89  retn
```
