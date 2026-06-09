# SmbCeUpdateSessionEntryAndVNetRootContext

- ea: `0x14004f920`
- end: `0x14004fa4e`
- name: `SmbCeUpdateSessionEntryAndVNetRootContext`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047fb0`

## callees

- `0x140001e40`
- `0x140002470`
- `0x14000dfa8`
- `0x140042d00`
- `0x14004f920`
- `0x140053db0`

## string_xrefs

- `0x14004f9a6`: `SmbCeUpdateSessionEntryAndVNetRootContext`
- `0x14004fa0e`: `SmbCeUpdateSessionEntryAndVNetRootContext`
- `0x14004fa2a`: `SmbCeUpdateSessionEntryAndVNetRootContext`

## pseudocode

```c
__int64 __fastcall SmbCeUpdateSessionEntryAndVNetRootContext(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  int v4; // eax

  v1 = *(_QWORD *)(a1 + 88);
  if ( v1 )
    v3 = *(_QWORD *)(v1 + 96);
  else
    v3 = 0;
  v4 = *(_DWORD *)(a1 + 72);
  if ( (v4 & 0x100) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
    MRxSmbTrackRefCount(v3, "SmbCeUpdateSessionEntryAndVNetRootContext", 2787);
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
    SmbCeCompleteSessionEntryInitialization(v3, *(_DWORD *)(a1 + 248), *(_BYTE *)(a1 + 254));
    *(_DWORD *)(a1 + 72) &= ~0x100u;
    v4 = *(_DWORD *)(a1 + 72);
  }
  if ( (v4 & 0x200) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
    MRxSmbTrackRefCount(v1, "SmbCeUpdateSessionEntryAndVNetRootContext", 2803);
    SmbReferenceRecord(v1 + 136, "SmbCeUpdateSessionEntryAndVNetRootContext", 2803);
    _InterlockedIncrement((volatile signed __int32 *)(v1 + 8));
    SmbCeCompleteVNetRootContextInitialization((PVOID)v1);
    *(_DWORD *)(a1 + 72) &= ~0x200u;
  }
  return 0;
}

```

## disassembly

```asm
0x14004f920  mov     [rsp+arg_8], rbx
0x14004f925  mov     [rsp+arg_10], rbp
0x14004f92a  push    rdi
0x14004f92b  sub     rsp, 20h
0x14004f92f  mov     rbx, [rcx+58h]
0x14004f933  mov     rdi, rcx
0x14004f936  mov     [rsp+28h+arg_0], rsi
0x14004f93b  test    rbx, rbx
0x14004f93e  jz      short loc_14004F972
0x14004f940  mov     rsi, [rbx+60h]
0x14004f944  mov     eax, [rcx+48h]
0x14004f947  lea     rbp, WPP_GLOBAL_Control
0x14004f94e  bt      eax, 8
0x14004f952  jb      short loc_14004F976
0x14004f954  mov     rsi, [rsp+28h+arg_0]
0x14004f959  bt      eax, 9
0x14004f95d  jb      short loc_14004F9DE
0x14004f95f  mov     rbx, [rsp+28h+arg_8]
0x14004f964  xor     eax, eax
0x14004f966  mov     rbp, [rsp+28h+arg_10]
0x14004f96b  add     rsp, 20h
0x14004f96f  pop     rdi
0x14004f970  retn
0x14004f972  xor     esi, esi
0x14004f974  jmp     short loc_14004F944
0x14004f976  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004f97d  cmp     rcx, rbp
0x14004f980  jz      short loc_14004F9A0
0x14004f982  test    dword ptr [rcx+2Ch], 400h
0x14004f989  jz      short loc_14004F9A0
0x14004f98b  mov     rcx, [rcx+18h]
0x14004f98f  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004f996  mov     edx, 33h ; '3'
0x14004f99b  call    WPP_SF_
0x14004f9a0  mov     r8d, 0AE3h
0x14004f9a6  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004f9ad  mov     rcx, rsi
0x14004f9b0  call    MRxSmbTrackRefCount
0x14004f9b5  lock inc dword ptr [rsi+8]
0x14004f9b9  movzx   r8d, byte ptr [rdi+0FEh]
0x14004f9c1  mov     rcx, rsi
0x14004f9c4  mov     edx, [rdi+0F8h]
0x14004f9ca  call    SmbCeCompleteSessionEntryInitialization
0x14004f9cf  and     dword ptr [rdi+48h], 0FFFFFEFFh
0x14004f9d6  mov     eax, [rdi+48h]
0x14004f9d9  jmp     loc_14004F954
0x14004f9de  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004f9e5  cmp     rcx, rbp
0x14004f9e8  jz      short loc_14004FA08
0x14004f9ea  test    dword ptr [rcx+2Ch], 400h
0x14004f9f1  jz      short loc_14004FA08
0x14004f9f3  mov     rcx, [rcx+18h]
0x14004f9f7  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004f9fe  mov     edx, 34h ; '4'
0x14004fa03  call    WPP_SF_
0x14004fa08  mov     r8d, 0AF3h
0x14004fa0e  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004fa15  mov     rcx, rbx
0x14004fa18  call    MRxSmbTrackRefCount
0x14004fa1d  lea     rcx, [rbx+88h]
0x14004fa24  mov     r8d, 0AF3h
0x14004fa2a  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004fa31  call    SmbReferenceRecord
0x14004fa36  lock inc dword ptr [rbx+8]
0x14004fa3a  mov     rcx, rbx; P
0x14004fa3d  call    SmbCeCompleteVNetRootContextInitialization
0x14004fa42  and     dword ptr [rdi+48h], 0FFFFFDFFh
0x14004fa49  jmp     loc_14004F95F
```
