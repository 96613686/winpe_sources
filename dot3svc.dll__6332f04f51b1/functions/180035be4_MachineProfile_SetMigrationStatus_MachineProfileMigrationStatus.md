# MachineProfile::_SetMigrationStatus(MachineProfileMigrationStatus)

- ea: `0x180035be4`
- end: `0x180035cc0`
- name: `?_SetMigrationStatus@MachineProfile@@AEAAJW4MachineProfileMigrationStatus@@@Z`
- size: `220`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003597c`
- `0x180035cc8`

## callees

- `0x18000a9c0`
- `0x180024c88`
- `0x180035be4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035c59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035c59`

## pseudocode

```c
int __fastcall MachineProfile::_SetMigrationStatus(__int64 a1, unsigned int a2)
{
  HKEY v4; // rcx
  unsigned int v5; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 17, &WPP_1cf9d866e54432687271528bd30a9afa_Traceguids, a2);
  }
  v4 = *(HKEY *)(a1 + 8);
  Data = a2;
  v5 = RegSetValueExW(v4, L"machineProfileMigrationStatus", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x77,
             (unsigned int)"onecoreuap\\net\\dot3\\dot3migration\\machineprofile.cpp",
             (const char *)v5,
             lpData);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 18, &WPP_1cf9d866e54432687271528bd30a9afa_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180035be4  mov     [rsp+arg_0], rbx
0x180035be9  mov     [rsp+arg_10], rbp
0x180035bee  push    rdi
0x180035bef  sub     rsp, 30h
0x180035bf3  mov     ebx, edx
0x180035bf5  mov     rdi, rcx
0x180035bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bff  lea     rbp, WPP_GLOBAL_Control
0x180035c06  cmp     rcx, rbp
0x180035c09  jz      short loc_180035C2F
0x180035c0b  cmp     byte ptr [rcx+19h], 4
0x180035c0f  jb      short loc_180035C2F
0x180035c11  test    byte ptr [rcx+1Ch], 1
0x180035c15  jz      short loc_180035C2F
0x180035c17  mov     rcx, [rcx+10h]
0x180035c1b  lea     r8, WPP_1cf9d866e54432687271528bd30a9afa_Traceguids
0x180035c22  mov     edx, 11h
0x180035c27  mov     r9d, ebx
0x180035c2a  call    WPP_SF_d
0x180035c2f  mov     rcx, [rdi+8]; hKey
0x180035c33  lea     rax, [rsp+38h+Data]
0x180035c38  mov     [rsp+38h+cbData], 4; cbData
0x180035c40  lea     rdx, aMachineprofile; "machineProfileMigrationStatus"
0x180035c47  mov     r9d, 4; dwType
0x180035c4d  mov     [rsp+38h+lpData], rax; unsigned int
0x180035c52  xor     r8d, r8d; Reserved
0x180035c55  mov     [rsp+38h+Data], ebx
0x180035c59  call    cs:__imp_RegSetValueExW
0x180035c5f  test    eax, eax
0x180035c61  jz      short loc_180035C7E
0x180035c63  mov     rcx, [rsp+38h]; this
0x180035c68  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dot3\\dot3migration\\m"...
0x180035c6f  mov     r9d, eax; char *
0x180035c72  mov     edx, 77h ; 'w'; void *
0x180035c77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035c7c  jmp     short loc_180035CB0
0x180035c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c85  cmp     rcx, rbp
0x180035c88  jz      short loc_180035CAE
0x180035c8a  cmp     byte ptr [rcx+19h], 4
0x180035c8e  jb      short loc_180035CAE
0x180035c90  test    byte ptr [rcx+1Ch], 1
0x180035c94  jz      short loc_180035CAE
0x180035c96  mov     rcx, [rcx+10h]
0x180035c9a  lea     r8, WPP_1cf9d866e54432687271528bd30a9afa_Traceguids
0x180035ca1  mov     edx, 12h
0x180035ca6  xor     r9d, r9d
0x180035ca9  call    WPP_SF_d
0x180035cae  xor     eax, eax
0x180035cb0  mov     rbx, [rsp+38h+arg_0]
0x180035cb5  mov     rbp, [rsp+38h+arg_10]
0x180035cba  add     rsp, 30h
0x180035cbe  pop     rdi
0x180035cbf  retn
```
