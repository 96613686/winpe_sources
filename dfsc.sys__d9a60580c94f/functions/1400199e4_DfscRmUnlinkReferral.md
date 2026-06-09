# DfscRmUnlinkReferral

- ea: `0x1400199e4`
- end: `0x140019b38`
- name: `DfscRmUnlinkReferral`
- size: `340`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140001744`
- `0x140002430`
- `0x140011a78`
- `0x140014d30`
- `0x140015050`
- `0x14001520c`
- `0x14001c310`
- `0x140026d10`

## callees

- `0x1400026a4`
- `0x1400199e4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019aac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019b14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019aac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019b14`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019aa0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019b08`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019aa0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019b08`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140019a7f`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140019a7f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019a15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019acd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019a15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140019acd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019ab8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019ab8`

## pseudocode

```c
void __fastcall DfscRmUnlinkReferral(__int64 a1)
{
  __int64 v1; // rdi
  __int64 *v3; // rbx
  __int64 v4; // rcx
  __int64 **v5; // rax

  v1 = *(_QWORD *)(a1 + 64);
  if ( v1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v1 + 56), 1u);
    if ( *(_QWORD *)(a1 + 64) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          (unsigned int)WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
          a1,
          a1 + 144);
      }
      --*(_DWORD *)(v1 + 44);
      *(_DWORD *)(v1 + 48) -= *(unsigned __int16 *)(a1 + 2);
      if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
      {
        RtlRemoveUnicodePrefix((PUNICODE_PREFIX_TABLE)v1, (PUNICODE_PREFIX_TABLE_ENTRY)(a1 + 72));
        *(_WORD *)(a1 + 12) &= ~1u;
      }
      *(_QWORD *)(a1 + 64) = 0;
    }
    ExReleaseResourceLite((PERESOURCE)(v1 + 56));
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v1 + 160), 1u);
    v3 = (__int64 *)(a1 + 48);
    v4 = *v3;
    if ( *v3 )
    {
      if ( *(__int64 **)(v4 + 8) != v3 || (v5 = (__int64 **)v3[1], *v5 != v3) )
        __fastfail(3u);
      *v5 = (__int64 *)v4;
      *(_QWORD *)(v4 + 8) = v5;
      *(_OWORD *)v3 = 0;
    }
    ExReleaseResourceLite((PERESOURCE)(v1 + 160));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x1400199e4  mov     [rsp+arg_0], rbx
0x1400199e9  mov     [rsp+arg_8], rsi
0x1400199ee  push    rdi
0x1400199ef  sub     rsp, 30h
0x1400199f3  mov     rdi, [rcx+40h]
0x1400199f7  mov     rbx, rcx
0x1400199fa  test    rdi, rdi
0x1400199fd  jz      loc_140019B20
0x140019a03  call    cs:__imp_KeEnterCriticalRegion
0x140019a0a  nop     dword ptr [rax+rax+00h]
0x140019a0f  mov     dl, 1; Wait
0x140019a11  lea     rcx, [rdi+38h]; Resource
0x140019a15  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140019a1c  nop     dword ptr [rax+rax+00h]
0x140019a21  cmp     qword ptr [rbx+40h], 0
0x140019a26  jz      short loc_140019A9C
0x140019a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a2f  lea     rax, WPP_GLOBAL_Control
0x140019a36  cmp     rcx, rax
0x140019a39  jz      short loc_140019A68
0x140019a3b  test    dword ptr [rcx+2Ch], 200000h
0x140019a42  jz      short loc_140019A68
0x140019a44  mov     rcx, [rcx+18h]
0x140019a48  lea     rax, [rbx+90h]
0x140019a4f  mov     edx, 1Ah
0x140019a54  mov     [rsp+38h+var_18], rax
0x140019a59  mov     r9, rbx
0x140019a5c  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x140019a63  call    WPP_SF_qZ
0x140019a68  dec     dword ptr [rdi+2Ch]
0x140019a6b  movzx   eax, word ptr [rbx+2]
0x140019a6f  sub     [rdi+30h], eax
0x140019a72  test    byte ptr [rbx+0Ch], 1
0x140019a76  jz      short loc_140019A94
0x140019a78  lea     rdx, [rbx+48h]; PrefixTableEntry
0x140019a7c  mov     rcx, rdi; PrefixTable
0x140019a7f  call    cs:__imp_RtlRemoveUnicodePrefix
0x140019a86  nop     dword ptr [rax+rax+00h]
0x140019a8b  mov     eax, 0FFFEh
0x140019a90  and     [rbx+0Ch], ax
0x140019a94  mov     qword ptr [rbx+40h], 0
0x140019a9c  lea     rcx, [rdi+38h]; Resource
0x140019aa0  call    cs:__imp_ExReleaseResourceLite
0x140019aa7  nop     dword ptr [rax+rax+00h]
0x140019aac  call    cs:__imp_KeLeaveCriticalRegion
0x140019ab3  nop     dword ptr [rax+rax+00h]
0x140019ab8  call    cs:__imp_KeEnterCriticalRegion
0x140019abf  nop     dword ptr [rax+rax+00h]
0x140019ac4  mov     dl, 1; Wait
0x140019ac6  lea     rcx, [rdi+0A0h]; Resource
0x140019acd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140019ad4  nop     dword ptr [rax+rax+00h]
0x140019ad9  add     rbx, 30h ; '0'
0x140019add  mov     rcx, [rbx]
0x140019ae0  test    rcx, rcx
0x140019ae3  jz      short loc_140019B01
0x140019ae5  cmp     [rcx+8], rbx
0x140019ae9  jnz     short loc_140019B31
0x140019aeb  mov     rax, [rbx+8]
0x140019aef  cmp     [rax], rbx
0x140019af2  jnz     short loc_140019B31
0x140019af4  mov     [rax], rcx
0x140019af7  xorps   xmm0, xmm0
0x140019afa  mov     [rcx+8], rax
0x140019afe  movups  xmmword ptr [rbx], xmm0
0x140019b01  lea     rcx, [rdi+0A0h]; Resource
0x140019b08  call    cs:__imp_ExReleaseResourceLite
0x140019b0f  nop     dword ptr [rax+rax+00h]
0x140019b14  call    cs:__imp_KeLeaveCriticalRegion
0x140019b1b  nop     dword ptr [rax+rax+00h]
0x140019b20  mov     rbx, [rsp+38h+arg_0]
0x140019b25  mov     rsi, [rsp+38h+arg_8]
0x140019b2a  add     rsp, 30h
0x140019b2e  pop     rdi
0x140019b2f  retn
0x140019b31  mov     ecx, 3
0x140019b36  int     29h; Win8: RtlFailFast(ecx)
```
