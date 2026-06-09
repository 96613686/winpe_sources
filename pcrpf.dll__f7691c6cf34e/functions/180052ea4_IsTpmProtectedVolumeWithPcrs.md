# IsTpmProtectedVolumeWithPcrs

- ea: `0x180052ea4`
- end: `0x180053009`
- name: `IsTpmProtectedVolumeWithPcrs`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180051ee0`
- `0x180052030`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000dfa0`
- `0x18002d5ec`
- `0x180052a54`
- `0x180052ea4`

## import_xrefs

- `FVEAPI!FveGetStatus` at `0x180052efb`
- `FVEAPI!FveGetStatus` at `0x180052efb`

## string_xrefs

- `0x180052f24`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052f57`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052fa0`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052fd7`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`

## pseudocode

```c
__int64 __fastcall IsTpmProtectedVolumeWithPcrs(__int64 a1, int a2, _BYTE *a3)
{
  unsigned int Status; // ebx
  int BitLockerPcrBitmapForVolume; // eax
  const char *v9; // [rsp+28h] [rbp-D0h]
  int v10[4]; // [rsp+30h] [rbp-C8h] BYREF
  _DWORD v11[2]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v12[4]; // [rsp+48h] [rbp-B0h] BYREF
  int v13; // [rsp+4Ch] [rbp-ACh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *a3 = 0;
  memset_0(v12, 0, 0x88u);
  v11[0] = 40;
  v11[1] = 3;
  Status = FveGetStatus(a1, v11);
  if ( (Status & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA8,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)Status,
      (unsigned __int64)"FveGetStatus",
      v9);
    return Status;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    0xAAu,
    "IsTpmProtectedVolumeWithPcrs",
    "fveStatus = 0x%x",
    v13);
  if ( (v13 & 0x4000) != 0 && (v13 & 1) != 0 && (v13 & 0x400) == 0 && (v13 & 0x200) != 0 )
  {
    v10[0] = 0;
    BitLockerPcrBitmapForVolume = GetBitLockerPcrBitmapForVolume(a1, v10);
    Status = BitLockerPcrBitmapForVolume;
    if ( BitLockerPcrBitmapForVolume < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)BitLockerPcrBitmapForVolume);
      return Status;
    }
    if ( (a2 & v10[0]) != 0 )
      *a3 = 1;
  }
  else
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      0xB0u,
      "IsTpmProtectedVolumeWithPcrs",
      "Volume is not boot partition or BitLocker is not enabled or BitLocker is suspended or does not have TPM protector.");
  }
  return 0;
}

```

## disassembly

```asm
0x180052ea4  mov     [rsp+arg_8], rbx
0x180052ea9  push    rbp
0x180052eaa  push    rsi
0x180052eab  push    rdi
0x180052eac  sub     rsp, 0E0h
0x180052eb3  mov     rax, cs:__security_cookie
0x180052eba  xor     rax, rsp
0x180052ebd  mov     [rsp+0F8h+var_28], rax
0x180052ec5  mov     rdi, r8
0x180052ec8  mov     byte ptr [r8], 0
0x180052ecc  mov     esi, edx
0x180052ece  mov     rbp, rcx
0x180052ed1  xor     edx, edx; Val
0x180052ed3  lea     rcx, [rsp+0F8h+var_B0]; void *
0x180052ed8  mov     r8d, 88h; Size
0x180052ede  call    memset_0
0x180052ee3  lea     rdx, [rsp+0F8h+var_B8]
0x180052ee8  mov     [rsp+0F8h+var_B8], 28h ; '('
0x180052ef0  mov     rcx, rbp
0x180052ef3  mov     [rsp+0F8h+var_B4], 3
0x180052efb  call    cs:__imp_FveGetStatus
0x180052f02  nop     dword ptr [rax+rax+00h]
0x180052f07  mov     ebx, eax
0x180052f09  test    eax, eax
0x180052f0b  jns     short loc_180052F3C
0x180052f0d  mov     rcx, [rsp+0F8h]; this
0x180052f15  lea     rax, aFvegetstatus_0; "FveGetStatus"
0x180052f1c  mov     r9d, ebx; char *
0x180052f1f  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180052f24  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052f2b  mov     edx, 0A8h; void *
0x180052f30  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052f35  mov     eax, ebx
0x180052f37  jmp     loc_180052FE5
0x180052f3c  mov     eax, [rsp+0F8h+var_AC]
0x180052f40  lea     r9, aFvestatus0xX; "fveStatus = 0x%x"
0x180052f47  lea     r8, aIstpmprotected; "IsTpmProtectedVolumeWithPcrs"
0x180052f4e  mov     [rsp+0F8h+var_D8], eax; int
0x180052f52  mov     edx, 0AAh; unsigned int
0x180052f57  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052f5e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052f63  mov     eax, [rsp+0F8h+var_AC]
0x180052f67  bt      eax, 0Eh
0x180052f6b  jnb     short loc_180052FC4
0x180052f6d  test    al, 1
0x180052f6f  jz      short loc_180052FC4
0x180052f71  bt      eax, 0Ah
0x180052f75  jb      short loc_180052FC4
0x180052f77  bt      eax, 9
0x180052f7b  jnb     short loc_180052FC4
0x180052f7d  lea     rdx, [rsp+0F8h+var_C8]
0x180052f82  mov     [rsp+0F8h+var_C8], 0
0x180052f8a  mov     rcx, rbp
0x180052f8d  call    GetBitLockerPcrBitmapForVolume
0x180052f92  mov     ebx, eax
0x180052f94  test    eax, eax
0x180052f96  jns     short loc_180052FB9
0x180052f98  mov     rcx, [rsp+0F8h]; this
0x180052fa0  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052fa7  mov     r9d, eax; char *
0x180052faa  mov     edx, 0B5h; void *
0x180052faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052fb4  jmp     loc_180052F35
0x180052fb9  test    [rsp+0F8h+var_C8], esi
0x180052fbd  jz      short loc_180052FE3
0x180052fbf  mov     byte ptr [rdi], 1
0x180052fc2  jmp     short loc_180052FE3
0x180052fc4  lea     r9, aVolumeIsNotBoo; "Volume is not boot partition or BitLock"...
0x180052fcb  mov     edx, 0B0h; unsigned int
0x180052fd0  lea     r8, aIstpmprotected; "IsTpmProtectedVolumeWithPcrs"
0x180052fd7  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052fde  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052fe3  xor     eax, eax
0x180052fe5  mov     rcx, [rsp+0F8h+var_28]
0x180052fed  xor     rcx, rsp; StackCookie
0x180052ff0  call    __security_check_cookie
0x180052ff5  mov     rbx, [rsp+0F8h+arg_8]
0x180052ffd  add     rsp, 0E0h
0x180053004  pop     rdi
0x180053005  pop     rsi
0x180053006  pop     rbp
0x180053007  retn
```
