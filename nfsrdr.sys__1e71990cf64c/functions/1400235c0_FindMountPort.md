# FindMountPort

- ea: `0x1400235c0`
- end: `0x140023725`
- name: `FindMountPort`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14002372c`
- `0x140023dd0`

## callees

- `0x14000adb0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400235c0`
- `0x14002d1e4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002360c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002360c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400236ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400236df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400236ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400236df`

## pseudocode

```c
__int64 __fastcall FindMountPort(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  int v7; // ebp
  int v8; // eax
  unsigned int v9; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)a3, 1u);
  v7 = *(_DWORD *)(a3 + 16);
  if ( *(_QWORD *)(a3 + 32) )
  {
    LOBYTE(v6) = 1;
    NfsForceDisconnect(a3, v6);
  }
  v8 = PmapQueryAndProbe(
         a1,
         a2,
         (__int16 *)(a3 + 44),
         *(_DWORD *)(a3 + 12),
         (unsigned int *)(a3 + 16),
         a3 + 8,
         (_QWORD *)(a3 + 24),
         (_QWORD *)(a3 + 32));
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (unsigned int)v8);
LABEL_15:
    ExReleaseResourceLite(*(PERESOURCE *)a3);
    return v9;
  }
  if ( *(_DWORD *)(a3 + 16) != v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    v9 = -1073741628;
    goto LABEL_15;
  }
  ExReleaseResourceLite(*(PERESOURCE *)a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x1400235c0  push    rbx
0x1400235c2  push    rbp
0x1400235c3  push    rsi
0x1400235c4  push    rdi
0x1400235c5  push    r12
0x1400235c7  push    r14
0x1400235c9  push    r15
0x1400235cb  sub     rsp, 50h
0x1400235cf  mov     rbx, r8
0x1400235d2  mov     r14, rdx
0x1400235d5  mov     r15, rcx
0x1400235d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400235df  lea     r12, WPP_GLOBAL_Control
0x1400235e6  cmp     rcx, r12
0x1400235e9  jz      short loc_140023607
0x1400235eb  mov     eax, [rcx+2Ch]
0x1400235ee  test    al, 8
0x1400235f0  jz      short loc_140023607
0x1400235f2  mov     rcx, [rcx+18h]
0x1400235f6  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x1400235fd  mov     edx, 0Ah
0x140023602  call    WPP_SF_
0x140023607  mov     rcx, [rbx]; Resource
0x14002360a  mov     dl, 1; Wait
0x14002360c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140023613  nop     dword ptr [rax+rax+00h]
0x140023618  lea     rdi, [rbx+20h]
0x14002361c  cmp     qword ptr [rdi], 0
0x140023620  lea     rsi, [rbx+10h]
0x140023624  mov     ebp, [rsi]
0x140023626  jz      short loc_140023632
0x140023628  mov     dl, 1
0x14002362a  mov     rcx, rbx
0x14002362d  call    NfsForceDisconnect
0x140023632  mov     r9d, [rbx+0Ch]
0x140023636  lea     rax, [rbx+18h]
0x14002363a  mov     [rsp+88h+var_48], 0
0x14002363f  lea     rcx, [rbx+8]
0x140023643  mov     [rsp+88h+var_50], rdi
0x140023648  lea     r8, [rbx+2Ch]
0x14002364c  mov     [rsp+88h+var_58], rax
0x140023651  mov     rdx, r14
0x140023654  mov     [rsp+88h+var_60], rcx
0x140023659  mov     rcx, r15
0x14002365c  mov     [rsp+88h+var_68], rsi
0x140023661  call    PmapQueryAndProbe
0x140023666  mov     edi, eax
0x140023668  test    eax, eax
0x14002366a  jns     short loc_14002369A
0x14002366c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023673  cmp     rcx, r12
0x140023676  jz      short loc_1400236CB
0x140023678  mov     edx, [rcx+2Ch]
0x14002367b  test    dl, 1
0x14002367e  jz      short loc_1400236CB
0x140023680  mov     rcx, [rcx+18h]
0x140023684  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x14002368b  mov     edx, 0Bh
0x140023690  mov     r9d, eax
0x140023693  call    WPP_SF_d
0x140023698  jmp     short loc_1400236CB
0x14002369a  cmp     [rsi], ebp
0x14002369c  jz      short loc_1400236DC
0x14002369e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236a5  cmp     rcx, r12
0x1400236a8  jz      short loc_1400236C6
0x1400236aa  mov     eax, [rcx+2Ch]
0x1400236ad  test    al, 1
0x1400236af  jz      short loc_1400236C6
0x1400236b1  mov     rcx, [rcx+18h]
0x1400236b5  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x1400236bc  mov     edx, 0Ch
0x1400236c1  call    WPP_SF_
0x1400236c6  mov     edi, 0C00000C4h
0x1400236cb  mov     rcx, [rbx]; Resource
0x1400236ce  call    cs:__imp_ExReleaseResourceLite
0x1400236d5  nop     dword ptr [rax+rax+00h]
0x1400236da  jmp     short loc_140023713
0x1400236dc  mov     rcx, [rbx]; Resource
0x1400236df  call    cs:__imp_ExReleaseResourceLite
0x1400236e6  nop     dword ptr [rax+rax+00h]
0x1400236eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236f2  cmp     rcx, r12
0x1400236f5  jz      short loc_140023713
0x1400236f7  mov     eax, [rcx+2Ch]
0x1400236fa  test    al, 8
0x1400236fc  jz      short loc_140023713
0x1400236fe  mov     rcx, [rcx+18h]
0x140023702  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140023709  mov     edx, 0Dh
0x14002370e  call    WPP_SF_
0x140023713  mov     eax, edi
0x140023715  add     rsp, 50h
0x140023719  pop     r15
0x14002371b  pop     r14
0x14002371d  pop     r12
0x14002371f  pop     rdi
0x140023720  pop     rsi
0x140023721  pop     rbp
0x140023722  pop     rbx
0x140023723  retn
```
