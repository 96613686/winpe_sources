# MupiRemoveKnownPrefixEntry

- ea: `0x140010e48`
- end: `0x140010f11`
- name: `MupiRemoveKnownPrefixEntry`
- size: `201`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140003008`
- `0x140010534`
- `0x14001067c`
- `0x140010950`
- `0x140010b5c`
- `0x14001d744`

## callees

- `0x1400036c8`
- `0x1400108f0`
- `0x140010e48`

## import_xrefs

- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140010e93`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140010e93`
- `ntoskrnl!KeCancelTimer` at `0x140010ed4`
- `ntoskrnl!KeCancelTimer` at `0x140010ed4`

## pseudocode

```c
__int64 __fastcall MupiRemoveKnownPrefixEntry(char *P)
{
  char **v2; // rdx
  PVOID *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_Zq(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      (unsigned int)WPP_ea0133f9b224365980f4880a222ef939_Traceguids,
      (_DWORD)P + 80,
      (char)P);
  }
  RtlRemoveUnicodePrefix(*((PUNICODE_PREFIX_TABLE *)P + 9), (PUNICODE_PREFIX_TABLE_ENTRY)(P + 16));
  *((_QWORD *)P + 9) = 0;
  v2 = (char **)*((_QWORD *)P + 15);
  if ( v2[1] != P + 120 || (v3 = (PVOID *)*((_QWORD *)P + 16), *v3 != P + 120) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = (char *)v3;
  if ( !--dword_14000AA00 )
    KeCancelTimer(&MupiPrefixGarbageCollectionTimer);
  dword_14000A9FC -= *((_DWORD *)P + 2);
  if ( *((_DWORD *)P + 34) )
    dword_14000AA08 -= *((_DWORD *)P + 2);
  return MupiFreeKnownPrefixEntry(P);
}

```

## disassembly

```asm
0x140010e48  push    rbx
0x140010e4a  sub     rsp, 30h
0x140010e4e  mov     rbx, rcx
0x140010e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e58  lea     rax, WPP_GLOBAL_Control
0x140010e5f  cmp     rcx, rax
0x140010e62  jz      short loc_140010E8B
0x140010e64  test    dword ptr [rcx+2Ch], 2000000h
0x140010e6b  jz      short loc_140010E8B
0x140010e6d  mov     rcx, [rcx+18h]
0x140010e71  lea     r9, [rbx+50h]
0x140010e75  mov     edx, 1Ah
0x140010e7a  mov     [rsp+38h+var_18], rbx
0x140010e7f  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x140010e86  call    WPP_SF_Zq
0x140010e8b  mov     rcx, [rbx+48h]; PrefixTable
0x140010e8f  lea     rdx, [rbx+10h]; PrefixTableEntry
0x140010e93  call    cs:__imp_RtlRemoveUnicodePrefix
0x140010e9a  nop     dword ptr [rax+rax+00h]
0x140010e9f  lea     rax, [rbx+78h]
0x140010ea3  mov     qword ptr [rbx+48h], 0
0x140010eab  mov     rdx, [rax]
0x140010eae  cmp     [rdx+8], rax
0x140010eb2  jnz     short loc_140010F0A
0x140010eb4  mov     rcx, [rax+8]
0x140010eb8  cmp     [rcx], rax
0x140010ebb  jnz     short loc_140010F0A
0x140010ebd  mov     [rcx], rdx
0x140010ec0  mov     [rdx+8], rcx
0x140010ec4  add     cs:dword_14000AA00, 0FFFFFFFFh
0x140010ecb  jnz     short loc_140010EE0
0x140010ecd  lea     rcx, MupiPrefixGarbageCollectionTimer; PKTIMER
0x140010ed4  call    cs:__imp_KeCancelTimer
0x140010edb  nop     dword ptr [rax+rax+00h]
0x140010ee0  mov     eax, [rbx+8]
0x140010ee3  sub     cs:dword_14000A9FC, eax
0x140010ee9  cmp     dword ptr [rbx+88h], 0
0x140010ef0  jz      short loc_140010EFB
0x140010ef2  mov     eax, [rbx+8]
0x140010ef5  sub     cs:dword_14000AA08, eax
0x140010efb  mov     rcx, rbx; P
0x140010efe  call    MupiFreeKnownPrefixEntry
0x140010f03  add     rsp, 30h
0x140010f07  pop     rbx
0x140010f08  retn
0x140010f0a  mov     ecx, 3
0x140010f0f  int     29h; Win8: RtlFailFast(ecx)
```
