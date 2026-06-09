# PsmpEnableNetUsageTracking

- ea: `0x180013e7c`
- end: `0x1800140b3`
- name: `PsmpEnableNetUsageTracking`
- size: `567`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013d68`

## callees

- `0x180013e7c`
- `0x1800179d8`
- `0x180017ca4`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180013ed2`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180013ed2`
- `ntdll!NtCreateWnfStateName` at `0x180013f46`
- `ntdll!NtCreateWnfStateName` at `0x180013f46`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013ef6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013ef6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013fc6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013fc6`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180013f6c`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180013f6c`
- `NduProv!__imp_NduCreateAppContext` at `0x180013f9e`
- `NduProv!__imp_NduCreateAppContext` at `0x180013f9e`

## pseudocode

```c
__int64 __fastcall PsmpEnableNetUsageTracking(__int64 a1)
{
  int WnfStateName; // edi
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // eax
  _QWORD *v7; // rcx
  __int64 v8; // [rsp+20h] [rbp-E0h]
  int v9; // [rsp+28h] [rbp-D8h]
  __int64 *v10; // [rsp+30h] [rbp-D0h]
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v15; // [rsp+60h] [rbp-A0h]
  _BYTE v16[256]; // [rsp+70h] [rbp-90h] BYREF

  LODWORD(v15) = 0;
  v14 = 0;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( (int)RtlRunOnceExecuteOnce(&PsmpNetInit, PsmpNetInitializeCallback, 0, &v12) >= 0 && v12 )
  {
    RtlAcquireSRWLockExclusive(a1 + 328);
    if ( *(_QWORD *)(a1 + 232) )
      goto LABEL_9;
    if ( *(_DWORD *)(a1 + 264)
      || *(_DWORD *)(a1 + 268)
      || (v10 = PsmpNDUDescriptor,
          v9 = 32,
          v8 = 0,
          WnfStateName = NtCreateWnfStateName(a1 + 264, 2, 0),
          WnfStateName >= 0) )
    {
      v3 = *(_QWORD *)(a1 + 8);
      v11 = 256;
      PsmGetPackageFullNameFromKey(v3, v16, &v11);
      v4 = *(_QWORD *)(a1 + 312);
      LODWORD(v14) = 0;
      v15 = v16;
      v5 = NduCreateAppContext(v12, &v14, *(_QWORD *)(v4 + 40), &v13, v8, v9, v10);
      if ( !v5 )
      {
        *(_QWORD *)(a1 + 232) = v13;
LABEL_9:
        WnfStateName = 0;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          WPP_SF_i(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids,
            *(_QWORD *)(a1 + 96));
LABEL_10:
        RtlReleaseSRWLockExclusive(a1 + 328);
        return (unsigned int)WnfStateName;
      }
      v7 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids,
          *(_QWORD *)(a1 + 96),
          v5);
        v7 = WPP_GLOBAL_Control;
      }
      WnfStateName = -1073741823;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_iD(v7[2], 18, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids, *(_QWORD *)(a1 + 96), WnfStateName);
    goto LABEL_10;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_i(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids,
      *(_QWORD *)(a1 + 96));
  return 3221225473LL;
}

```

## disassembly

```asm
0x180013e7c  push    rbp
0x180013e7e  push    rbx
0x180013e7f  push    rdi
0x180013e80  push    r14
0x180013e82  lea     rbp, [rsp-88h]
0x180013e8a  sub     rsp, 188h
0x180013e91  mov     rax, cs:__security_cookie
0x180013e98  xor     rax, rsp
0x180013e9b  mov     [rbp+0A0h+var_30], rax
0x180013e9f  xor     eax, eax
0x180013ea1  lea     r9, [rsp+1A0h+var_158]
0x180013ea6  mov     rbx, rcx
0x180013ea9  mov     qword ptr [rsp+1A0h+var_144], rax
0x180013eae  xor     r8d, r8d
0x180013eb1  mov     [rsp+58h], rax
0x180013eb6  lea     rdx, PsmpNetInitializeCallback
0x180013ebd  mov     [rsp+1A0h+var_150], rax
0x180013ec2  lea     rcx, PsmpNetInit
0x180013ec9  mov     [rsp+1A0h+var_160], eax
0x180013ecd  mov     [rsp+1A0h+var_158], rax
0x180013ed2  call    cs:__imp_RtlRunOnceExecuteOnce
0x180013ed8  test    eax, eax
0x180013eda  js      loc_18001407D
0x180013ee0  cmp     [rsp+1A0h+var_158], 0
0x180013ee6  jz      loc_18001407D
0x180013eec  lea     r14, [rbx+148h]
0x180013ef3  mov     rcx, r14
0x180013ef6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180013efc  cmp     qword ptr [rbx+0E8h], 0
0x180013f04  jnz     loc_180013FB4
0x180013f0a  lea     rcx, [rbx+108h]
0x180013f11  cmp     dword ptr [rcx], 0
0x180013f14  jnz     short loc_180013F56
0x180013f16  cmp     dword ptr [rbx+10Ch], 0
0x180013f1d  jnz     short loc_180013F56
0x180013f1f  xor     r9d, r9d
0x180013f22  lea     rax, PsmpNDUDescriptor
0x180013f29  mov     [rsp+1A0h+var_170], rax
0x180013f2e  xor     r8d, r8d
0x180013f31  mov     [rsp+1A0h+var_178], 20h ; ' '
0x180013f39  mov     [rsp+1A0h+var_180], 0
0x180013f42  lea     edx, [r9+2]
0x180013f46  call    cs:__imp_NtCreateWnfStateName
0x180013f4c  mov     edi, eax
0x180013f4e  test    eax, eax
0x180013f50  js      loc_180013FE7
0x180013f56  mov     rcx, [rbx+8]
0x180013f5a  lea     r8, [rsp+1A0h+var_160]
0x180013f5f  lea     rdx, [rsp+1A0h+var_130]
0x180013f64  mov     [rsp+1A0h+var_160], 100h
0x180013f6c  call    cs:__imp_PsmGetPackageFullNameFromKey
0x180013f72  mov     r8, [rbx+138h]
0x180013f79  lea     rax, [rsp+1A0h+var_130]
0x180013f7e  mov     rcx, [rsp+1A0h+var_158]
0x180013f83  lea     r9, [rsp+1A0h+var_150]
0x180013f88  mov     [rsp+1A0h+var_148], 0
0x180013f90  lea     rdx, [rsp+1A0h+var_148]
0x180013f95  mov     qword ptr [rsp+1A0h+var_144+4], rax
0x180013f9a  mov     r8, [r8+28h]
0x180013f9e  call    cs:__imp_NduCreateAppContext
0x180013fa4  test    eax, eax
0x180013fa6  jnz     short loc_180014019
0x180013fa8  mov     rax, [rsp+1A0h+var_150]
0x180013fad  mov     [rbx+0E8h], rax
0x180013fb4  xor     edi, edi
0x180013fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fbd  test    byte ptr [rcx+1Ch], 1
0x180013fc1  jnz     short loc_180014033
0x180013fc3  mov     rcx, r14
0x180013fc6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013fcc  mov     eax, edi
0x180013fce  mov     rcx, [rbp+0A0h+var_30]
0x180013fd2  xor     rcx, rsp; StackCookie
0x180013fd5  call    __security_check_cookie
0x180013fda  add     rsp, 188h
0x180013fe1  pop     r14
0x180013fe3  pop     rdi
0x180013fe4  pop     rbx
0x180013fe5  pop     rbp
0x180013fe6  retn
0x180013fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fee  test    byte ptr [rcx+1Ch], 1
0x180013ff2  jz      short loc_180013FC3
0x180013ff4  cmp     byte ptr [rcx+19h], 2
0x180013ff8  jb      short loc_180013FC3
0x180013ffa  mov     r9, [rbx+60h]
0x180013ffe  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x180014005  mov     rcx, [rcx+10h]
0x180014009  mov     edx, 12h
0x18001400e  mov     dword ptr [rsp+1A0h+var_180], edi
0x180014012  call    WPP_SF_iD
0x180014017  jmp     short loc_180013FC3
0x180014019  mov     rcx, cs:WPP_GLOBAL_Control
0x180014020  test    byte ptr [rcx+1Ch], 1
0x180014024  jz      short loc_18001402C
0x180014026  cmp     byte ptr [rcx+19h], 2
0x18001402a  jnb     short loc_180014057
0x18001402c  mov     edi, 0C0000001h
0x180014031  jmp     short loc_180013FEE
0x180014033  cmp     byte ptr [rcx+19h], 5
0x180014037  jb      short loc_180013FC3
0x180014039  mov     r9, [rbx+60h]
0x18001403d  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x180014044  mov     rcx, [rcx+10h]
0x180014048  mov     edx, 13h
0x18001404d  call    WPP_SF_i
0x180014052  jmp     loc_180013FC3
0x180014057  mov     r9, [rbx+60h]
0x18001405b  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x180014062  mov     rcx, [rcx+10h]
0x180014066  mov     edx, 11h
0x18001406b  mov     dword ptr [rsp+1A0h+var_180], eax
0x18001406f  call    WPP_SF_iD
0x180014074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001407b  jmp     short loc_18001402C
0x18001407d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014084  test    byte ptr [rcx+1Ch], 1
0x180014088  jz      short loc_1800140A9
0x18001408a  cmp     byte ptr [rcx+19h], 2
0x18001408e  jb      short loc_1800140A9
0x180014090  mov     r9, [rbx+60h]
0x180014094  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x18001409b  mov     rcx, [rcx+10h]
0x18001409f  mov     edx, 10h
0x1800140a4  call    WPP_SF_i
0x1800140a9  mov     eax, 0C0000001h
0x1800140ae  jmp     loc_180013FCE
```
