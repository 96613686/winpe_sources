# FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)

- ea: `0x180095308`
- end: `0x180095433`
- name: `?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z`
- size: `299`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18009934c`
- `0x180099b5c`

## callees

- `0x18006f520`
- `0x180095308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800953a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800953c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800953a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800953c5`
- `fwbase!FwStringCopy` at `0x1800953b1`
- `fwbase!FwStringCopy` at `0x1800953eb`
- `fwbase!FwStringCopy` at `0x1800953b1`
- `fwbase!FwStringCopy` at `0x1800953eb`
- `fwbase!FwReportReturnError` at `0x180095376`
- `fwbase!FwReportReturnError` at `0x18009540d`
- `fwbase!FwReportReturnError` at `0x180095376`
- `fwbase!FwReportReturnError` at `0x18009540d`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800953fa`
- `FWPolicyIOMgr!FwFreeSets` at `0x1800953fa`
- `FWPolicyIOMgr!FwEnumSets` at `0x180095361`
- `FWPolicyIOMgr!FwEnumSets` at `0x180095361`

## pseudocode

```c
__int64 __fastcall FwGetSetName(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // ebp
  int v7; // eax
  __int64 v8; // r8
  int v9; // ebx
  unsigned int v10; // edx
  int v11; // r14d
  _QWORD *v12; // rdi
  int v13; // esi
  __int64 v14; // r8
  _QWORD *v16; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-50h] BYREF

  v6 = a2;
  v16 = 0;
  v17 = 0;
  v7 = FwEnumSets(a1, a2, a3, &v16, &v17, 196608, 0);
  v9 = v7;
  if ( v7 < 0 )
  {
    FwReportReturnError("FwGetSetName", (unsigned int)v7, v8);
    goto LABEL_14;
  }
  v10 = v17;
  v11 = 0;
  v12 = v16;
  v13 = 0;
  if ( v17 )
  {
    while ( v6 )
    {
      if ( v6 == 1 )
      {
        if ( !(unsigned int)_o__wcsicmp(v12[2], a4) )
        {
          v9 = FwStringCopy(v12[3], a5);
          v11 = 1;
        }
LABEL_9:
        if ( v11 == 1 )
          goto LABEL_14;
        v10 = v17;
      }
      v12 = (_QWORD *)*v12;
      if ( ++v13 >= v10 )
        goto LABEL_14;
    }
    if ( !(unsigned int)_o__wcsicmp(v12[2], a4) )
    {
      v9 = FwStringCopy(v12[3], a5);
      goto LABEL_14;
    }
    goto LABEL_9;
  }
LABEL_14:
  FwFreeSets(v16, v6);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwGetSetName", (unsigned int)v9, v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180095308  mov     r11, rsp
0x18009530b  push    rbx
0x18009530c  push    rbp
0x18009530d  push    rsi
0x18009530e  push    rdi
0x18009530f  push    r12
0x180095311  push    r14
0x180095313  push    r15
0x180095315  sub     rsp, 60h
0x180095319  mov     rax, cs:__security_cookie
0x180095320  xor     rax, rsp
0x180095323  mov     [rsp+98h+var_48], rax
0x180095328  mov     r15, [rsp+98h+arg_20]
0x180095330  lea     rax, [r11-50h]
0x180095334  mov     r12, r9
0x180095337  mov     [rsp+98h+var_68], 0
0x18009533f  mov     [rsp+98h+var_70], 30000h
0x180095347  lea     r9, [r11-58h]
0x18009534b  mov     [r11-78h], rax
0x18009534f  mov     ebp, edx
0x180095351  mov     qword ptr [r11-58h], 0
0x180095359  mov     [rsp+98h+var_50], 0
0x180095361  call    cs:__imp_FwEnumSets
0x180095367  mov     ebx, eax
0x180095369  test    eax, eax
0x18009536b  jns     short loc_18009537E
0x18009536d  mov     edx, eax
0x18009536f  lea     rcx, aFwgetsetname; "FwGetSetName"
0x180095376  call    cs:__imp_FwReportReturnError
0x18009537c  jmp     short loc_1800953F3
0x18009537e  mov     edx, [rsp+98h+var_50]
0x180095382  xor     r14d, r14d
0x180095385  mov     rdi, [rsp+98h+var_58]
0x18009538a  xor     esi, esi
0x18009538c  test    edx, edx
0x18009538e  jz      short loc_1800953F3
0x180095390  test    ebp, ebp
0x180095392  jz      short loc_1800953BE
0x180095394  cmp     ebp, 1
0x180095397  jnz     short loc_1800953D9
0x180095399  mov     rcx, [rdi+10h]
0x18009539d  mov     rdx, r12
0x1800953a0  call    cs:__imp__o__wcsicmp
0x1800953a6  test    eax, eax
0x1800953a8  jnz     short loc_1800953CF
0x1800953aa  mov     rcx, [rdi+18h]
0x1800953ae  mov     rdx, r15
0x1800953b1  call    cs:__imp_FwStringCopy
0x1800953b7  mov     ebx, eax
0x1800953b9  mov     r14d, ebp
0x1800953bc  jmp     short loc_1800953CF
0x1800953be  mov     rcx, [rdi+10h]
0x1800953c2  mov     rdx, r12
0x1800953c5  call    cs:__imp__o__wcsicmp
0x1800953cb  test    eax, eax
0x1800953cd  jz      short loc_1800953E4
0x1800953cf  cmp     r14d, 1
0x1800953d3  jz      short loc_1800953F3
0x1800953d5  mov     edx, [rsp+98h+var_50]
0x1800953d9  mov     rdi, [rdi]
0x1800953dc  inc     esi
0x1800953de  cmp     esi, edx
0x1800953e0  jb      short loc_180095390
0x1800953e2  jmp     short loc_1800953F3
0x1800953e4  mov     rcx, [rdi+18h]
0x1800953e8  mov     rdx, r15
0x1800953eb  call    cs:__imp_FwStringCopy
0x1800953f1  mov     ebx, eax
0x1800953f3  mov     rcx, [rsp+98h+var_58]
0x1800953f8  mov     edx, ebp
0x1800953fa  call    cs:__imp_FwFreeSets
0x180095400  test    ebx, ebx
0x180095402  jns     short loc_180095415
0x180095404  mov     edx, ebx
0x180095406  lea     rcx, aFwgetsetname; "FwGetSetName"
0x18009540d  call    cs:__imp_FwReportReturnError
0x180095413  mov     ebx, eax
0x180095415  mov     eax, ebx
0x180095417  mov     rcx, [rsp+98h+var_48]
0x18009541c  xor     rcx, rsp; StackCookie
0x18009541f  call    __security_check_cookie
0x180095424  add     rsp, 60h
0x180095428  pop     r15
0x18009542a  pop     r14
0x18009542c  pop     r12
0x18009542e  pop     rdi
0x18009542f  pop     rsi
0x180095430  pop     rbp
0x180095431  pop     rbx
0x180095432  retn
```
