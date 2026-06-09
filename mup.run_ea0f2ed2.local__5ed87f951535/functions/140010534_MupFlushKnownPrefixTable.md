# MupFlushKnownPrefixTable

- ea: `0x140010534`
- end: `0x140010675`
- name: `MupFlushKnownPrefixTable`
- size: `321`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1400122a0`
- `0x140012dd0`
- `0x1400135c0`
- `0x140016490`
- `0x140016710`
- `0x140019cc0`

## callees

- `0x140002a14`
- `0x1400036c8`
- `0x140010534`
- `0x140010e48`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010590`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010590`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010625`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010625`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001057b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001057b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010631`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010631`

## pseudocode

```c
void __fastcall MupFlushKnownPrefixTable(__int64 a1, __int64 a2, char a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x13u,
      (__int64)WPP_ea0133f9b224365980f4880a222ef939_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v6 = (__int64 *)qword_14000A9E0;
  while ( v6 != &qword_14000A9E0 )
  {
    v7 = v6 - 15;
    v6 = (__int64 *)*v6;
    if ( (!a2 || v7[13] == a2) && (!a1 || v7[9] == a1) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_Zq(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x14u,
          (__int64)WPP_ea0133f9b224365980f4880a222ef939_Traceguids,
          (const wchar_t *)v7 + 40,
          v7);
      }
      if ( !*((_DWORD *)v7 + 34) || a3 )
        MupiRemoveKnownPrefixEntry((char *)v7);
    }
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x15u,
      (__int64)WPP_ea0133f9b224365980f4880a222ef939_Traceguids);
  }
}

```

## disassembly

```asm
0x140010534  push    rbx
0x140010536  push    rbp
0x140010537  push    rsi
0x140010538  push    rdi
0x140010539  push    r13
0x14001053b  push    r14
0x14001053d  sub     rsp, 38h
0x140010541  mov     r14b, r8b
0x140010544  mov     rsi, rdx
0x140010547  mov     rbp, rcx
0x14001054a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010551  lea     r13, WPP_GLOBAL_Control
0x140010558  cmp     rcx, r13
0x14001055b  jz      short loc_14001057B
0x14001055d  test    dword ptr [rcx+2Ch], 4000000h
0x140010564  jz      short loc_14001057B
0x140010566  mov     rcx, [rcx+18h]
0x14001056a  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x140010571  mov     edx, 13h
0x140010576  call    WPP_SF_
0x14001057b  call    cs:__imp_KeEnterCriticalRegion
0x140010582  nop     dword ptr [rax+rax+00h]
0x140010587  mov     dl, 1; Wait
0x140010589  lea     rcx, Resource; Resource
0x140010590  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140010597  nop     dword ptr [rax+rax+00h]
0x14001059c  mov     rdi, cs:qword_14000A9E0
0x1400105a3  jmp     short loc_140010612
0x1400105a5  lea     rbx, [rdi-78h]
0x1400105a9  mov     rdi, [rdi]
0x1400105ac  test    rsi, rsi
0x1400105af  jz      short loc_1400105B7
0x1400105b1  cmp     [rbx+68h], rsi
0x1400105b5  jnz     short loc_140010619
0x1400105b7  test    rbp, rbp
0x1400105ba  jz      short loc_1400105C2
0x1400105bc  cmp     [rbx+48h], rbp
0x1400105c0  jnz     short loc_140010619
0x1400105c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105c9  cmp     rcx, r13
0x1400105cc  jz      short loc_1400105FC
0x1400105ce  test    dword ptr [rcx+2Ch], 4000000h
0x1400105d5  jz      short loc_1400105F5
0x1400105d7  mov     rcx, [rcx+18h]
0x1400105db  lea     r9, [rbx+50h]
0x1400105df  mov     edx, 14h
0x1400105e4  mov     [rsp+68h+var_48], rbx
0x1400105e9  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x1400105f0  call    WPP_SF_Zq
0x1400105f5  lea     rax, qword_14000A9E0
0x1400105fc  cmp     dword ptr [rbx+88h], 0
0x140010603  jz      short loc_14001060A
0x140010605  test    r14b, r14b
0x140010608  jz      short loc_140010619
0x14001060a  mov     rcx, rbx; P
0x14001060d  call    MupiRemoveKnownPrefixEntry
0x140010612  lea     rax, qword_14000A9E0
0x140010619  cmp     rdi, rax
0x14001061c  jnz     short loc_1400105A5
0x14001061e  lea     rcx, Resource; Resource
0x140010625  call    cs:__imp_ExReleaseResourceLite
0x14001062c  nop     dword ptr [rax+rax+00h]
0x140010631  call    cs:__imp_KeLeaveCriticalRegion
0x140010638  nop     dword ptr [rax+rax+00h]
0x14001063d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010644  cmp     rcx, r13
0x140010647  jz      short loc_140010667
0x140010649  test    dword ptr [rcx+2Ch], 4000000h
0x140010650  jz      short loc_140010667
0x140010652  mov     rcx, [rcx+18h]
0x140010656  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001065d  mov     edx, 15h
0x140010662  call    WPP_SF_
0x140010667  add     rsp, 38h
0x14001066b  pop     r14
0x14001066d  pop     r13
0x14001066f  pop     rdi
0x140010670  pop     rsi
0x140010671  pop     rbp
0x140010672  pop     rbx
0x140010673  retn
```
