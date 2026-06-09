# ResealBitLockerVolume

- ea: `0x180053898`
- end: `0x180053969`
- name: `ResealBitLockerVolume`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051ee0`
- `0x180052030`

## callees

- `0x180009c64`
- `0x18002d5ec`
- `0x180053898`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x180053922`
- `FVEAPI!FveCommitChanges` at `0x180053922`
- `FVEAPI!FveKeyManagement` at `0x1800538e1`
- `FVEAPI!FveKeyManagement` at `0x1800538e1`

## string_xrefs

- `0x1800538aa`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`

## pseudocode

```c
__int64 __fastcall ResealBitLockerVolume(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v6; // [rsp+38h] [rbp+10h] BYREF

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    0x91u,
    "ResealBitLockerVolume",
    "Resealing BitLocker volume");
  v6 = 0;
  v2 = FveKeyManagement(a1, 4, &v6);
  if ( v2 < 0 )
  {
    v3 = 147;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)v2);
    return (unsigned int)v2;
  }
  if ( (v6 & 8) == 0 )
  {
    v2 = -2147418113;
    v3 = 148;
    goto LABEL_3;
  }
  v2 = FveCommitChanges(a1);
  if ( v2 < 0 )
  {
    v3 = 149;
    goto LABEL_3;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    0x96u,
    "ResealBitLockerVolume",
    "Resealed");
  return 0;
}

```

## disassembly

```asm
0x180053898  mov     [rsp+arg_0], rbx
0x18005389d  mov     [rsp+arg_10], rsi
0x1800538a2  push    rdi; int
0x1800538a3  sub     rsp, 20h
0x1800538a7  mov     rdi, rcx
0x1800538aa  lea     rsi, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800538b1  mov     rcx, rsi; char *
0x1800538b4  lea     r9, aResealingBitlo; "Resealing BitLocker volume"
0x1800538bb  lea     r8, aResealbitlocke_0; "ResealBitLockerVolume"
0x1800538c2  mov     edx, 91h; unsigned int
0x1800538c7  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800538cc  lea     r8, [rsp+28h+arg_8]
0x1800538d1  mov     [rsp+28h+arg_8], 0
0x1800538d9  mov     edx, 4
0x1800538de  mov     rcx, rdi
0x1800538e1  call    cs:__imp_FveKeyManagement
0x1800538e8  nop     dword ptr [rax+rax+00h]
0x1800538ed  mov     ebx, eax
0x1800538ef  test    eax, eax
0x1800538f1  jns     short loc_18005390C
0x1800538f3  mov     edx, 93h; void *
0x1800538f8  mov     rcx, [rsp+28h]; this
0x1800538fd  mov     r9d, ebx; char *
0x180053900  mov     r8, rsi; unsigned int
0x180053903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053908  mov     eax, ebx
0x18005390a  jmp     short loc_180053958
0x18005390c  test    byte ptr [rsp+28h+arg_8], 8
0x180053911  jnz     short loc_18005391F
0x180053913  mov     ebx, 8000FFFFh
0x180053918  mov     edx, 94h
0x18005391d  jmp     short loc_1800538F8
0x18005391f  mov     rcx, rdi
0x180053922  call    cs:__imp_FveCommitChanges
0x180053929  nop     dword ptr [rax+rax+00h]
0x18005392e  mov     ebx, eax
0x180053930  test    eax, eax
0x180053932  jns     short loc_18005393B
0x180053934  mov     edx, 95h
0x180053939  jmp     short loc_1800538F8
0x18005393b  lea     r9, aResealed; "Resealed"
0x180053942  mov     edx, 96h; unsigned int
0x180053947  lea     r8, aResealbitlocke_0; "ResealBitLockerVolume"
0x18005394e  mov     rcx, rsi; char *
0x180053951  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180053956  xor     eax, eax
0x180053958  mov     rbx, [rsp+28h+arg_0]
0x18005395d  mov     rsi, [rsp+28h+arg_10]
0x180053962  add     rsp, 20h
0x180053966  pop     rdi
0x180053967  retn
```
