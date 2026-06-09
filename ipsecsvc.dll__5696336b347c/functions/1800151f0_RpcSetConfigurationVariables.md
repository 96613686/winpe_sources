# RpcSetConfigurationVariables

- ea: `0x1800151f0`
- end: `0x1800153bd`
- name: `RpcSetConfigurationVariables`
- size: `461`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000e510`
- `0x18000f660`
- `0x1800151f0`
- `0x180017e80`
- `0x18004d090`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180015396`
- `RPCRT4!RpcRevertToSelf` at `0x180015396`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800152cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800152cc`
- `fwpuclnt!IkeextGetConfigParameters0` at `0x1800152d7`
- `fwpuclnt!IkeextGetConfigParameters0` at `0x1800152d7`
- `fwpuclnt!IkeextSetConfigParameters0` at `0x180015335`
- `fwpuclnt!IkeextSetConfigParameters0` at `0x180015335`

## pseudocode

```c
__int64 __fastcall RpcSetConfigurationVariables(__int64 a1, _DWORD *a2)
{
  unsigned int ConfigParameters0; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // ebx
  bool v9; // zf
  int v10; // eax
  int v12; // [rsp+30h] [rbp-38h] BYREF
  __int128 v13; // [rsp+38h] [rbp-30h] BYREF
  int v14; // [rsp+48h] [rbp-20h]

  v14 = 0;
  v13 = 0;
  v12 = 0;
  ConfigParameters0 = SPDImpersonateClient(&v12);
  v4 = ConfigParameters0;
  if ( ConfigParameters0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 113;
LABEL_5:
      v7 = ConfigParameters0;
LABEL_30:
      WPP_SF_d(v5[2], v6, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids, v7);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v8 = a2[2];
  if ( v8 > 2 || a2[4] >= 2u || a2[5] )
  {
    v4 = 87;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_31;
    v6 = 114;
    goto LABEL_29;
  }
  if ( gcCrlCheck != v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids);
    gcCrlCheck = v8;
    SetEvent(ghForcedPolicyReloadEvent);
  }
  ConfigParameters0 = IkeextGetConfigParameters0(&v13);
  v4 = ConfigParameters0;
  if ( !ConfigParameters0 )
  {
    v9 = a2[6] == 0;
    HIDWORD(v13) = a2[4] & 1;
    v10 = v13;
    if ( !v9 )
      v10 = 1;
    v9 = a2[1] == 0;
    LODWORD(v13) = v10;
    if ( v9 && !*a2 )
    {
      v4 = IkeextSetConfigParameters0(&v13);
      goto LABEL_31;
    }
    v4 = 50;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_31;
    v6 = 117;
LABEL_29:
    v7 = v4;
    goto LABEL_30;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v6 = 116;
    goto LABEL_5;
  }
LABEL_31:
  if ( v12 )
    RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x1800151f0  mov     [rsp+arg_0], rbx
0x1800151f5  mov     [rsp+arg_10], rsi
0x1800151fa  push    rdi
0x1800151fb  sub     rsp, 60h
0x1800151ff  mov     rax, cs:__security_cookie
0x180015206  xor     rax, rsp
0x180015209  mov     [rsp+68h+var_18], rax
0x18001520e  xor     eax, eax
0x180015210  lea     rcx, [rsp+68h+var_38]
0x180015215  xorps   xmm0, xmm0
0x180015218  mov     [rsp+68h+var_20], eax
0x18001521c  movups  [rsp+68h+var_30], xmm0
0x180015221  mov     [rsp+68h+var_38], eax
0x180015225  mov     rsi, rdx
0x180015228  call    SPDImpersonateClient
0x18001522d  mov     ebx, eax
0x18001522f  test    eax, eax
0x180015231  jz      short loc_180015261
0x180015233  mov     rcx, cs:WPP_GLOBAL_Control
0x18001523a  lea     rdi, WPP_GLOBAL_Control
0x180015241  cmp     rcx, rdi
0x180015244  jz      loc_18001538F
0x18001524a  test    byte ptr [rcx+1Ch], 10h
0x18001524e  jz      loc_18001538F
0x180015254  mov     edx, 71h ; 'q'
0x180015259  mov     r9d, eax
0x18001525c  jmp     loc_18001537F
0x180015261  mov     ebx, [rsi+8]
0x180015264  cmp     ebx, 2
0x180015267  ja      loc_18001535B
0x18001526d  cmp     dword ptr [rsi+10h], 2
0x180015271  jnb     loc_18001535B
0x180015277  cmp     dword ptr [rsi+14h], 0
0x18001527b  jnz     loc_18001535B
0x180015281  mov     r9d, cs:gcCrlCheck
0x180015288  lea     rdi, WPP_GLOBAL_Control
0x18001528f  cmp     r9d, ebx
0x180015292  jz      short loc_1800152D2
0x180015294  mov     rcx, cs:WPP_GLOBAL_Control
0x18001529b  cmp     rcx, rdi
0x18001529e  jz      short loc_1800152BF
0x1800152a0  test    byte ptr [rcx+1Ch], 4
0x1800152a4  jz      short loc_1800152BF
0x1800152a6  mov     rcx, [rcx+10h]
0x1800152aa  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x1800152b1  mov     edx, 73h ; 's'
0x1800152b6  mov     [rsp+68h+var_48], ebx
0x1800152ba  call    WPP_SF_dd
0x1800152bf  mov     rcx, cs:ghForcedPolicyReloadEvent; hEvent
0x1800152c6  mov     cs:gcCrlCheck, ebx
0x1800152cc  call    cs:__imp_SetEvent
0x1800152d2  lea     rcx, [rsp+68h+var_30]
0x1800152d7  call    cs:__imp_IkeextGetConfigParameters0
0x1800152dd  mov     ebx, eax
0x1800152df  test    eax, eax
0x1800152e1  jz      short loc_180015307
0x1800152e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152ea  cmp     rcx, rdi
0x1800152ed  jz      loc_18001538F
0x1800152f3  test    byte ptr [rcx+1Ch], 10h
0x1800152f7  jz      loc_18001538F
0x1800152fd  mov     edx, 74h ; 't'
0x180015302  jmp     loc_180015259
0x180015307  movzx   eax, byte ptr [rsi+10h]
0x18001530b  mov     ecx, 1
0x180015310  and     eax, ecx
0x180015312  cmp     dword ptr [rsi+18h], 0
0x180015316  mov     dword ptr [rsp+68h+var_30+0Ch], eax
0x18001531a  mov     eax, dword ptr [rsp+68h+var_30]
0x18001531e  cmova   eax, ecx
0x180015321  cmp     dword ptr [rsi+4], 0
0x180015325  mov     dword ptr [rsp+68h+var_30], eax
0x180015329  jnz     short loc_18001533F
0x18001532b  cmp     dword ptr [rsi], 0
0x18001532e  jnz     short loc_18001533F
0x180015330  lea     rcx, [rsp+68h+var_30]
0x180015335  call    cs:__imp_IkeextSetConfigParameters0
0x18001533b  mov     ebx, eax
0x18001533d  jmp     short loc_18001538F
0x18001533f  mov     ebx, 32h ; '2'
0x180015344  mov     rcx, cs:WPP_GLOBAL_Control
0x18001534b  cmp     rcx, rdi
0x18001534e  jz      short loc_18001538F
0x180015350  test    byte ptr [rcx+1Ch], 10h
0x180015354  jz      short loc_18001538F
0x180015356  lea     edx, [rbx+43h]
0x180015359  jmp     short loc_18001537C
0x18001535b  mov     ebx, 57h ; 'W'
0x180015360  mov     rcx, cs:WPP_GLOBAL_Control
0x180015367  lea     rdi, WPP_GLOBAL_Control
0x18001536e  cmp     rcx, rdi
0x180015371  jz      short loc_18001538F
0x180015373  test    byte ptr [rcx+1Ch], 10h
0x180015377  jz      short loc_18001538F
0x180015379  lea     edx, [rbx+1Bh]
0x18001537c  mov     r9d, ebx
0x18001537f  mov     rcx, [rcx+10h]
0x180015383  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x18001538a  call    WPP_SF_d
0x18001538f  cmp     [rsp+68h+var_38], 0
0x180015394  jz      short loc_18001539C
0x180015396  call    cs:__imp_RpcRevertToSelf
0x18001539c  mov     eax, ebx
0x18001539e  mov     rcx, [rsp+68h+var_18]
0x1800153a3  xor     rcx, rsp; StackCookie
0x1800153a6  call    __security_check_cookie
0x1800153ab  lea     r11, [rsp+68h+var_8]
0x1800153b0  mov     rbx, [r11+10h]
0x1800153b4  mov     rsi, [r11+20h]
0x1800153b8  mov     rsp, r11
0x1800153bb  pop     rdi
0x1800153bc  retn
```
