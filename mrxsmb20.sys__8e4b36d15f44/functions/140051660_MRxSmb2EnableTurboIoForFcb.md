# MRxSmb2EnableTurboIoForFcb

- ea: `0x140051660`
- end: `0x14005177f`
- name: `MRxSmb2EnableTurboIoForFcb`
- size: `287`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x14001cc00`

## callees

- `0x14002a6a8`
- `0x14002bc68`
- `0x140051660`

## import_xrefs

- `rdbss!RxEnableTurboIo` at `0x1400516ff`
- `rdbss!RxEnableTurboIo` at `0x1400516ff`
- `rdbss!RxOpenFileObjectForTurboIo` at `0x1400516a5`
- `rdbss!RxOpenFileObjectForTurboIo` at `0x1400516a5`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051670`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005173c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051670`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005173c`

## pseudocode

```c
__int64 __fastcall MRxSmb2EnableTurboIoForFcb(__int64 a1)
{
  _QWORD *v2; // rdi
  int v3; // esi
  __int64 v4; // rbx
  __int64 ConfigurationBlock; // rax
  __int64 v6; // rdx
  __int64 v7; // r8

  v2 = (_QWORD *)(a1 + 56);
  if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 507) || *(_QWORD *)(*v2 + 128LL) )
  {
    v3 = -1073741637;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v4 = *(_QWORD *)(*v2 + 128LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock(WPP_GLOBAL_Control);
      WPP_SF_qqDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        a1,
        *v2,
        *(unsigned __int8 *)(ConfigurationBlock + 507),
        v4);
    }
  }
  else
  {
    v3 = RxOpenFileObjectForTurboIo(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL), *v2, &MRxSmb2TurboIoDispatch);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids, a1, *v2, v3);
    }
    if ( v3 >= 0 )
      RxEnableTurboIo(*v2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140051660  push    rbx
0x140051662  push    rbp
0x140051663  push    rsi
0x140051664  push    rdi
0x140051665  sub     rsp, 48h
0x140051669  mov     rbp, rcx
0x14005166c  lea     rdi, [rcx+38h]
0x140051670  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140051677  nop     dword ptr [rax+rax+00h]
0x14005167c  cmp     byte ptr [rax+1FBh], 0
0x140051683  jz      loc_14005170D
0x140051689  mov     rdx, [rdi]
0x14005168c  cmp     qword ptr [rdx+80h], 0
0x140051694  jnz     short loc_14005170D
0x140051696  mov     rcx, [rbp+30h]
0x14005169a  lea     r8, MRxSmb2TurboIoDispatch
0x1400516a1  mov     rcx, [rcx+30h]
0x1400516a5  call    cs:__imp_RxOpenFileObjectForTurboIo
0x1400516ac  nop     dword ptr [rax+rax+00h]
0x1400516b1  mov     esi, eax
0x1400516b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516ba  lea     rax, WPP_GLOBAL_Control
0x1400516c1  cmp     rcx, rax
0x1400516c4  jz      short loc_1400516F8
0x1400516c6  mov     edx, [rcx+2Ch]
0x1400516c9  test    dl, 2
0x1400516cc  jz      short loc_1400516F8
0x1400516ce  cmp     byte ptr [rcx+29h], 4
0x1400516d2  jb      short loc_1400516F8
0x1400516d4  mov     rax, [rdi]
0x1400516d7  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x1400516de  mov     rcx, [rcx+18h]
0x1400516e2  mov     edx, 14h
0x1400516e7  mov     [rsp+68h+var_40], esi
0x1400516eb  mov     r9, rbp
0x1400516ee  mov     [rsp+68h+var_48], rax
0x1400516f3  call    WPP_SF_qqD
0x1400516f8  test    esi, esi
0x1400516fa  js      short loc_140051773
0x1400516fc  mov     rcx, [rdi]
0x1400516ff  call    cs:__imp_RxEnableTurboIo
0x140051706  nop     dword ptr [rax+rax+00h]
0x14005170b  jmp     short loc_140051773
0x14005170d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051714  lea     rax, WPP_GLOBAL_Control
0x14005171b  mov     esi, 0C00000BBh
0x140051720  cmp     rcx, rax
0x140051723  jz      short loc_140051773
0x140051725  mov     eax, [rcx+2Ch]
0x140051728  test    al, 2
0x14005172a  jz      short loc_140051773
0x14005172c  cmp     byte ptr [rcx+29h], 4
0x140051730  jb      short loc_140051773
0x140051732  mov     rax, [rdi]
0x140051735  mov     rbx, [rax+80h]
0x14005173c  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140051743  nop     dword ptr [rax+rax+00h]
0x140051748  mov     [rsp+68h+var_38], rbx
0x14005174d  mov     r9, rbp
0x140051750  movzx   ecx, byte ptr [rax+1FBh]
0x140051757  mov     rax, [rdi]
0x14005175a  mov     [rsp+68h+var_40], ecx
0x14005175e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051765  mov     [rsp+68h+var_48], rax
0x14005176a  mov     rcx, [rcx+18h]
0x14005176e  call    WPP_SF_qqDq
0x140051773  mov     eax, esi
0x140051775  add     rsp, 48h
0x140051779  pop     rdi
0x14005177a  pop     rsi
0x14005177b  pop     rbp
0x14005177c  pop     rbx
0x14005177d  retn
```
