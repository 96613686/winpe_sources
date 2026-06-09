# EapUpdateMasterUserData

- ea: `0x18001ce44`
- end: `0x18001d100`
- name: `EapUpdateMasterUserData`
- size: `700`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180027ae4`
- `0x18002a76c`

## callees

- `0x180004710`
- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180017460`
- `0x180017540`
- `0x18001c80c`
- `0x18001ce44`
- `0x1800214f0`
- `0x18002eec8`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18001cf35`
- `MobileNetworking!AllocateMemory` at `0x18001cf35`
- `MobileNetworking!FreeMemory` at `0x18001d0b5`
- `MobileNetworking!FreeMemory` at `0x18001d0b5`

## string_xrefs

- `0x18001cf24`: `EapUpdateMasterUserData`
- `0x18001d0aa`: `EapUpdateMasterUserData`

## pseudocode

```c
__int64 __fastcall EapUpdateMasterUserData(__int64 *a1, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 v4; // rsi
  __int64 v8; // rcx
  __int128 v9; // xmm6
  unsigned int v10; // edi
  __int64 v11; // r12
  _QWORD *v12; // rcx
  unsigned int Memory; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int IsUsingExplicitCreds; // eax
  __int64 v19; // rcx
  _OWORD *v21[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v22; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+48h] BYREF

  v4 = *a1;
  v21[0] = 0;
  v23 = 0;
  v8 = *(_QWORD *)(v4 + 2744);
  v9 = 0;
  v10 = *(_DWORD *)(v4 + 20);
  v11 = *(_QWORD *)(v4 + 2760);
  if ( v8 )
    v9 = *(_OWORD *)(*(unsigned int *)(v8 + 64) + v8 + 4);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !v11 || !a3 || !a2 )
  {
    v14 = 87;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 1) != 0 )
      WPP_SF_d(v12[7], 51, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v10);
    goto LABEL_33;
  }
  v22 = v9;
  Memory = OneXSetEapUserData((__int64)v12, v11, &v22, a2, a3, 0, &v23);
  v14 = Memory;
  if ( Memory != 234 )
  {
    if ( Memory )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v17 = 54;
        goto LABEL_14;
      }
      goto LABEL_33;
    }
LABEL_20:
    Memory = SupplicantSetUserProfile(v4 + 2384, v23, v21[0]);
    v14 = Memory;
    if ( Memory )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v17 = 55;
        goto LABEL_14;
      }
    }
    else if ( byte_18003DF42 < 0 )
    {
      IsUsingExplicitCreds = SupplicantIsUsingExplicitCreds(v4 + 2384);
      McTemplateU0qq_EtwEventWriteTransfer(v19, Save, v10, IsUsingExplicitCreds);
    }
    goto LABEL_33;
  }
  Memory = AllocateMemory(v23, v21, "EapUpdateMasterUserData", 516);
  v14 = Memory;
  if ( Memory )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v17 = 52;
LABEL_14:
      WPP_SF_dd(v16[7], v17, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v10, Memory);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  v22 = v9;
  Memory = OneXSetEapUserData(v15, v11, &v22, a2, a3, v21[0], &v23);
  v14 = Memory;
  if ( !Memory )
  {
    OneXSetEapUserDataFlag(v21[0], a4);
    goto LABEL_20;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v17 = 53;
    goto LABEL_14;
  }
LABEL_33:
  FreeMemory(v21, "EapUpdateMasterUserData", 543);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18001ce44  push    rbp
0x18001ce46  push    rbx
0x18001ce47  push    rsi
0x18001ce48  push    rdi
0x18001ce49  push    r12
0x18001ce4b  push    r13
0x18001ce4d  push    r14
0x18001ce4f  push    r15
0x18001ce51  mov     rbp, rsp
0x18001ce54  sub     rsp, 78h
0x18001ce58  mov     rsi, [rcx]
0x18001ce5b  xor     ebx, ebx
0x18001ce5d  mov     [rbp+var_38], rbx
0x18001ce61  mov     r13d, r9d
0x18001ce64  movaps  [rsp+78h+var_18], xmm6
0x18001ce69  mov     r14, r8
0x18001ce6c  mov     r15d, edx
0x18001ce6f  mov     [rbp+arg_0], ebx
0x18001ce72  mov     rcx, [rsi+0AB8h]
0x18001ce79  xorps   xmm6, xmm6
0x18001ce7c  mov     edi, [rsi+14h]
0x18001ce7f  mov     r12, [rsi+0AC8h]
0x18001ce86  test    rcx, rcx
0x18001ce89  jz      short loc_18001CE93
0x18001ce8b  mov     eax, [rcx+40h]
0x18001ce8e  movups  xmm6, xmmword ptr [rax+rcx+4]
0x18001ce93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce9a  lea     rax, WPP_GLOBAL_Control
0x18001cea1  cmp     rcx, rax
0x18001cea4  jz      short loc_18001CED2
0x18001cea6  test    dword ptr [rcx+44h], 800h
0x18001cead  jz      short loc_18001CED2
0x18001ceaf  mov     rcx, [rcx+38h]
0x18001ceb3  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001ceba  mov     edx, 32h ; '2'
0x18001cebf  call    WPP_SF_
0x18001cec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cecb  lea     rax, WPP_GLOBAL_Control
0x18001ced2  test    r12, r12
0x18001ced5  jz      loc_18001D077
0x18001cedb  test    r14, r14
0x18001cede  jz      loc_18001D077
0x18001cee4  test    r15d, r15d
0x18001cee7  jz      loc_18001D077
0x18001ceed  lea     rax, [rbp+arg_0]
0x18001cef1  movdqa  [rbp+var_28], xmm6
0x18001cef6  mov     [rsp+78h+var_48], rax
0x18001cefb  lea     r8, [rbp+var_28]
0x18001ceff  mov     [rsp+78h+var_50], rbx
0x18001cf04  mov     r9d, r15d
0x18001cf07  mov     rdx, r12
0x18001cf0a  mov     [rsp+78h+var_58], r14
0x18001cf0f  call    OneXSetEapUserData
0x18001cf14  mov     ebx, eax
0x18001cf16  cmp     eax, 0EAh
0x18001cf1b  jnz     loc_18001D02D
0x18001cf21  mov     ecx, [rbp+arg_0]
0x18001cf24  lea     r8, aEapupdatemaste_0; "EapUpdateMasterUserData"
0x18001cf2b  mov     r9d, 204h
0x18001cf31  lea     rdx, [rbp+var_38]
0x18001cf35  call    cs:__imp_AllocateMemory
0x18001cf3b  mov     ebx, eax
0x18001cf3d  test    eax, eax
0x18001cf3f  jz      short loc_18001CF83
0x18001cf41  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf48  lea     rsi, WPP_GLOBAL_Control
0x18001cf4f  cmp     rcx, rsi
0x18001cf52  jz      loc_18001D0A4
0x18001cf58  test    byte ptr [rcx+44h], 1
0x18001cf5c  jz      loc_18001D0A4
0x18001cf62  mov     edx, 34h ; '4'
0x18001cf67  mov     rcx, [rcx+38h]
0x18001cf6b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001cf72  mov     r9d, edi
0x18001cf75  mov     dword ptr [rsp+78h+var_58], eax
0x18001cf79  call    WPP_SF_dd
0x18001cf7e  jmp     loc_18001D0A4
0x18001cf83  lea     rax, [rbp+arg_0]
0x18001cf87  movdqa  [rbp+var_28], xmm6
0x18001cf8c  mov     [rsp+78h+var_48], rax
0x18001cf91  lea     r8, [rbp+var_28]
0x18001cf95  mov     rax, [rbp+var_38]
0x18001cf99  mov     r9d, r15d
0x18001cf9c  mov     [rsp+78h+var_50], rax
0x18001cfa1  mov     rdx, r12
0x18001cfa4  mov     [rsp+78h+var_58], r14
0x18001cfa9  call    OneXSetEapUserData
0x18001cfae  mov     ebx, eax
0x18001cfb0  test    eax, eax
0x18001cfb2  jz      short loc_18001CFDC
0x18001cfb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfbb  lea     rsi, WPP_GLOBAL_Control
0x18001cfc2  cmp     rcx, rsi
0x18001cfc5  jz      loc_18001D0A4
0x18001cfcb  test    byte ptr [rcx+44h], 1
0x18001cfcf  jz      loc_18001D0A4
0x18001cfd5  mov     edx, 35h ; '5'
0x18001cfda  jmp     short loc_18001CF67
0x18001cfdc  mov     rcx, [rbp+var_38]
0x18001cfe0  mov     edx, r13d
0x18001cfe3  call    OneXSetEapUserDataFlag
0x18001cfe8  mov     r8, [rbp+var_38]
0x18001cfec  lea     rcx, [rsi+950h]
0x18001cff3  mov     edx, [rbp+arg_0]
0x18001cff6  call    SupplicantSetUserProfile
0x18001cffb  mov     ebx, eax
0x18001cffd  test    eax, eax
0x18001cfff  jnz     short loc_18001D054
0x18001d001  cmp     cs:byte_18003DF42, al
0x18001d007  jge     loc_18001D09D
0x18001d00d  lea     rcx, [rsi+950h]
0x18001d014  call    SupplicantIsUsingExplicitCreds
0x18001d019  mov     r9d, eax
0x18001d01c  lea     rdx, Save
0x18001d023  mov     r8d, edi
0x18001d026  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001d02b  jmp     short loc_18001D09D
0x18001d02d  test    eax, eax
0x18001d02f  jz      short loc_18001CFE8
0x18001d031  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d038  lea     rsi, WPP_GLOBAL_Control
0x18001d03f  cmp     rcx, rsi
0x18001d042  jz      short loc_18001D0A4
0x18001d044  test    byte ptr [rcx+44h], 1
0x18001d048  jz      short loc_18001D0A4
0x18001d04a  mov     edx, 36h ; '6'
0x18001d04f  jmp     loc_18001CF67
0x18001d054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d05b  lea     rsi, WPP_GLOBAL_Control
0x18001d062  cmp     rcx, rsi
0x18001d065  jz      short loc_18001D0A4
0x18001d067  test    byte ptr [rcx+44h], 1
0x18001d06b  jz      short loc_18001D0A4
0x18001d06d  mov     edx, 37h ; '7'
0x18001d072  jmp     loc_18001CF67
0x18001d077  mov     ebx, 57h ; 'W'
0x18001d07c  cmp     rcx, rax
0x18001d07f  jz      short loc_18001D09D
0x18001d081  test    byte ptr [rcx+44h], 1
0x18001d085  jz      short loc_18001D09D
0x18001d087  mov     rcx, [rcx+38h]
0x18001d08b  lea     edx, [rbx-24h]
0x18001d08e  mov     r9d, edi
0x18001d091  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d098  call    WPP_SF_d
0x18001d09d  lea     rsi, WPP_GLOBAL_Control
0x18001d0a4  mov     r8d, 21Fh
0x18001d0aa  lea     rdx, aEapupdatemaste_0; "EapUpdateMasterUserData"
0x18001d0b1  lea     rcx, [rbp+var_38]
0x18001d0b5  call    cs:__imp_FreeMemory
0x18001d0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0c2  cmp     rcx, rsi
0x18001d0c5  jz      short loc_18001D0E8
0x18001d0c7  test    dword ptr [rcx+44h], 800h
0x18001d0ce  jz      short loc_18001D0E8
0x18001d0d0  mov     rcx, [rcx+38h]
0x18001d0d4  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001d0db  mov     edx, 38h ; '8'
0x18001d0e0  mov     r9d, ebx
0x18001d0e3  call    WPP_SF_D
0x18001d0e8  movaps  xmm6, [rsp+78h+var_18]
0x18001d0ed  mov     eax, ebx
0x18001d0ef  add     rsp, 78h
0x18001d0f3  pop     r15
0x18001d0f5  pop     r14
0x18001d0f7  pop     r13
0x18001d0f9  pop     r12
0x18001d0fb  pop     rdi
0x18001d0fc  pop     rsi
0x18001d0fd  pop     rbx
0x18001d0fe  pop     rbp
0x18001d0ff  retn
```
