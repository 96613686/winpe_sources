# VerifyInboundDefaultSecureState(void *,int *,_tag_FW_PROFILE_TYPE)

- ea: `0x180007a00`
- end: `0x180007e2a`
- name: `?VerifyInboundDefaultSecureState@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `1066`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006874`
- `0x180035c10`

## callees

- `0x180005e0c`
- `0x180007a00`
- `0x180009210`
- `0x18001e960`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007a79`
- `ntdll!EtwEventWrite` at `0x180007b0d`
- `ntdll!EtwEventWrite` at `0x180007b63`
- `ntdll!EtwEventWrite` at `0x180007bf8`
- `ntdll!EtwEventWrite` at `0x180007a79`
- `ntdll!EtwEventWrite` at `0x180007b0d`
- `ntdll!EtwEventWrite` at `0x180007b63`
- `ntdll!EtwEventWrite` at `0x180007bf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007b86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007b86`

## pseudocode

```c
__int64 __fastcall VerifyInboundDefaultSecureState(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  FwPolicy2 *v8; // r10
  __int64 v9; // rcx
  int v10; // eax
  int v11; // esi
  FwPolicy2 *v12; // rax
  int active; // eax
  int v15; // [rsp+40h] [rbp-58h] BYREF
  int v16; // [rsp+44h] [rbp-54h] BYREF
  int v17; // [rsp+48h] [rbp-50h] BYREF
  int v18; // [rsp+4Ch] [rbp-4Ch] BYREF

  v17 = 4;
  v16 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids);
  *a2 = 0;
  v15 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v6 = Int_FWGetOrSetConfig(1, a1, 3, a3, 1, (__int64)&v16, (__int64)&v17, (__int64)&v15);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v6);
LABEL_10:
    v8 = WPP_GLOBAL_Control;
  }
  v9 = g_Provider;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v8 = WPP_GLOBAL_Control;
    v9 = g_Provider;
  }
  if ( v7 == 2 )
  {
    v10 = 0;
    v16 = 0;
  }
  else
  {
    if ( v7 )
    {
      if ( (int)v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v8 + 2), 44, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v7);
      return v7;
    }
    v10 = v16;
  }
  v7 = 0;
  if ( v10 )
  {
    *a2 = 1;
    return v7;
  }
  v15 = 0;
  if ( v9 )
  {
    EtwEventWrite(v9, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v8 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v11 = Int_FWGetOrSetConfig(1, a1, 17, a3, 1, (__int64)&v18, (__int64)&v17, (__int64)&v15);
  if ( !v11 )
    goto LABEL_23;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
      (unsigned int)v11);
LABEL_23:
    v12 = WPP_GLOBAL_Control;
  }
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 == 2 )
    goto LABEL_27;
  if ( v11 )
  {
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    else
      v7 = v11;
    if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 45, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v7);
  }
  else
  {
    if ( v18 )
      goto LABEL_27;
    v15 = 0;
    active = ActiveBlockInboundRulesExist(a1, &v15, a3);
    v7 = active;
    if ( active < 0 )
    {
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids,
          (unsigned int)active);
      return v7;
    }
    if ( v15 )
    {
LABEL_27:
      *a2 = 1;
      return v7;
    }
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, a3);
    *a2 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180007a00  push    rbx
0x180007a02  push    rbp
0x180007a03  push    rdi
0x180007a04  push    r12
0x180007a06  push    r14
0x180007a08  push    r15
0x180007a0a  sub     rsp, 68h
0x180007a0e  mov     rax, cs:__security_cookie
0x180007a15  xor     rax, rsp
0x180007a18  mov     [rsp+98h+var_48], rax
0x180007a1d  xor     r15d, r15d
0x180007a20  mov     [rsp+98h+var_50], 4
0x180007a28  mov     [rsp+98h+var_54], r15d
0x180007a2d  mov     ebp, r8d
0x180007a30  mov     [rsp+98h+var_4C], r15d
0x180007a35  mov     rdi, rdx
0x180007a38  mov     r14, rcx
0x180007a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a42  lea     r12, WPP_GLOBAL_Control
0x180007a49  cmp     rcx, r12
0x180007a4c  jz      short loc_180007A58
0x180007a4e  test    byte ptr [rcx+1Ch], 8
0x180007a52  jnz     loc_180007D2F
0x180007a58  mov     [rdi], r15d
0x180007a5b  mov     rcx, cs:g_Provider
0x180007a62  mov     [rsp+98h+var_58], r15d
0x180007a67  test    rcx, rcx
0x180007a6a  jz      short loc_180007A85
0x180007a6c  xor     r9d, r9d
0x180007a6f  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007a76  xor     r8d, r8d
0x180007a79  call    cs:__imp_EtwEventWrite
0x180007a80  nop     dword ptr [rax+rax+00h]
0x180007a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a8c  cmp     rcx, r12
0x180007a8f  jz      short loc_180007A9B
0x180007a91  test    byte ptr [rcx+1Ch], 8
0x180007a95  jnz     loc_180007D49
0x180007a9b  call    cs:__imp_GetTickCount64
0x180007aa2  nop     dword ptr [rax+rax+00h]
0x180007aa7  lea     rax, [rsp+98h+var_58]
0x180007aac  mov     r9d, ebp
0x180007aaf  mov     [rsp+98h+var_60], rax
0x180007ab4  mov     r8d, 3
0x180007aba  lea     rax, [rsp+98h+var_50]
0x180007abf  mov     rdx, r14
0x180007ac2  mov     [rsp+98h+var_68], rax
0x180007ac7  mov     ecx, 1
0x180007acc  lea     rax, [rsp+98h+var_54]
0x180007ad1  mov     [rsp+98h+var_70], rax
0x180007ad6  mov     [rsp+98h+var_78], 1
0x180007ade  call    Int_FWGetOrSetConfig
0x180007ae3  mov     ebx, eax
0x180007ae5  test    eax, eax
0x180007ae7  jnz     loc_180007C45
0x180007aed  mov     r10, cs:WPP_GLOBAL_Control
0x180007af4  mov     rcx, cs:g_Provider
0x180007afb  test    rcx, rcx
0x180007afe  jz      short loc_180007B27
0x180007b00  xor     r9d, r9d
0x180007b03  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007b0a  xor     r8d, r8d
0x180007b0d  call    cs:__imp_EtwEventWrite
0x180007b14  nop     dword ptr [rax+rax+00h]
0x180007b19  mov     r10, cs:WPP_GLOBAL_Control
0x180007b20  mov     rcx, cs:g_Provider
0x180007b27  cmp     ebx, 2
0x180007b2a  jz      loc_180007D63
0x180007b30  test    ebx, ebx
0x180007b32  jnz     loc_180007CB4
0x180007b38  mov     eax, [rsp+98h+var_54]
0x180007b3c  mov     ebx, r15d
0x180007b3f  test    eax, eax
0x180007b41  jnz     loc_180007C3D
0x180007b47  mov     [rsp+98h+var_38], rsi
0x180007b4c  mov     [rsp+98h+var_58], r15d
0x180007b51  test    rcx, rcx
0x180007b54  jz      short loc_180007B76
0x180007b56  xor     r9d, r9d
0x180007b59  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007b60  xor     r8d, r8d
0x180007b63  call    cs:__imp_EtwEventWrite
0x180007b6a  nop     dword ptr [rax+rax+00h]
0x180007b6f  mov     r10, cs:WPP_GLOBAL_Control
0x180007b76  cmp     r10, r12
0x180007b79  jz      short loc_180007B86
0x180007b7b  test    byte ptr [r10+1Ch], 8
0x180007b80  jnz     loc_180007D6F
0x180007b86  call    cs:__imp_GetTickCount64
0x180007b8d  nop     dword ptr [rax+rax+00h]
0x180007b92  lea     rax, [rsp+98h+var_58]
0x180007b97  mov     r9d, ebp
0x180007b9a  mov     [rsp+98h+var_60], rax
0x180007b9f  mov     r8d, 11h
0x180007ba5  lea     rax, [rsp+98h+var_50]
0x180007baa  mov     rdx, r14
0x180007bad  mov     [rsp+98h+var_68], rax
0x180007bb2  mov     ecx, 1
0x180007bb7  lea     rax, [rsp+98h+var_4C]
0x180007bbc  mov     [rsp+98h+var_70], rax
0x180007bc1  mov     [rsp+98h+var_78], 1
0x180007bc9  call    Int_FWGetOrSetConfig
0x180007bce  mov     esi, eax
0x180007bd0  test    eax, eax
0x180007bd2  jnz     loc_180007C7D
0x180007bd8  mov     rax, cs:WPP_GLOBAL_Control
0x180007bdf  mov     rcx, cs:g_Provider
0x180007be6  test    rcx, rcx
0x180007be9  jz      short loc_180007C0B
0x180007beb  xor     r9d, r9d
0x180007bee  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007bf5  xor     r8d, r8d
0x180007bf8  call    cs:__imp_EtwEventWrite
0x180007bff  nop     dword ptr [rax+rax+00h]
0x180007c04  mov     rax, cs:WPP_GLOBAL_Control
0x180007c0b  cmp     esi, 2
0x180007c0e  jnz     loc_180007D89
0x180007c14  mov     dword ptr [rdi], 1
0x180007c1a  mov     rsi, [rsp+98h+var_38]
0x180007c1f  mov     eax, ebx
0x180007c21  mov     rcx, [rsp+98h+var_48]
0x180007c26  xor     rcx, rsp; StackCookie
0x180007c29  call    __security_check_cookie
0x180007c2e  add     rsp, 68h
0x180007c32  pop     r15
0x180007c34  pop     r14
0x180007c36  pop     r12
0x180007c38  pop     rdi
0x180007c39  pop     rbp
0x180007c3a  pop     rbx
0x180007c3b  retn
0x180007c3d  mov     dword ptr [rdi], 1
0x180007c43  jmp     short loc_180007C1F
0x180007c45  mov     r10, cs:WPP_GLOBAL_Control
0x180007c4c  cmp     r10, r12
0x180007c4f  jz      loc_180007AF4
0x180007c55  test    byte ptr [r10+1Ch], 1
0x180007c5a  jz      loc_180007AF4
0x180007c60  mov     rcx, [r10+10h]
0x180007c64  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007c6b  mov     edx, 6Ah ; 'j'
0x180007c70  mov     r9d, ebx
0x180007c73  call    WPP_SF_d
0x180007c78  jmp     loc_180007AED
0x180007c7d  mov     rax, cs:WPP_GLOBAL_Control
0x180007c84  cmp     rax, r12
0x180007c87  jz      loc_180007BDF
0x180007c8d  test    byte ptr [rax+1Ch], 1
0x180007c91  jz      loc_180007BDF
0x180007c97  mov     rcx, [rax+10h]
0x180007c9b  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007ca2  mov     edx, 6Ah ; 'j'
0x180007ca7  mov     r9d, esi
0x180007caa  call    WPP_SF_d
0x180007caf  jmp     loc_180007BD8
0x180007cb4  jle     short loc_180007CBF
0x180007cb6  movzx   ebx, bx
0x180007cb9  or      ebx, 80070000h
0x180007cbf  cmp     r10, r12
0x180007cc2  jz      loc_180007C1F
0x180007cc8  test    byte ptr [r10+1Ch], 1
0x180007ccd  jz      loc_180007C1F
0x180007cd3  mov     rcx, [r10+10h]
0x180007cd7  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007cde  mov     edx, 2Ch ; ','
0x180007ce3  mov     r9d, ebx
0x180007ce6  call    WPP_SF_d
0x180007ceb  jmp     loc_180007C1F
0x180007cf0  jg      short loc_180007D24
0x180007cf2  mov     ebx, esi
0x180007cf4  cmp     rax, r12
0x180007cf7  jz      loc_180007C1A
0x180007cfd  test    byte ptr [rax+1Ch], 1
0x180007d01  jz      loc_180007C1A
0x180007d07  mov     rcx, [rax+10h]
0x180007d0b  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007d12  mov     edx, 2Dh ; '-'
0x180007d17  mov     r9d, ebx
0x180007d1a  call    WPP_SF_d
0x180007d1f  jmp     loc_180007C1A
0x180007d24  movzx   ebx, si
0x180007d27  or      ebx, 80070000h
0x180007d2d  jmp     short loc_180007CF4
0x180007d2f  mov     rcx, [rcx+10h]
0x180007d33  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007d3a  mov     edx, 2Bh ; '+'
0x180007d3f  call    WPP_SF_
0x180007d44  jmp     loc_180007A58
0x180007d49  mov     rcx, [rcx+10h]
0x180007d4d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007d54  mov     edx, 69h ; 'i'
0x180007d59  call    WPP_SF_
0x180007d5e  jmp     loc_180007A9B
0x180007d63  mov     eax, r15d
0x180007d66  mov     [rsp+98h+var_54], eax
0x180007d6a  jmp     loc_180007B3C
0x180007d6f  mov     rcx, [r10+10h]
0x180007d73  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007d7a  mov     edx, 69h ; 'i'
0x180007d7f  call    WPP_SF_
0x180007d84  jmp     loc_180007B86
0x180007d89  test    esi, esi
0x180007d8b  jnz     loc_180007CF0
0x180007d91  cmp     [rsp+98h+var_4C], ebx
0x180007d95  jnz     loc_180007C14
0x180007d9b  mov     r8d, ebp
0x180007d9e  mov     [rsp+98h+var_58], r15d
0x180007da3  lea     rdx, [rsp+98h+var_58]
0x180007da8  mov     rcx, r14
0x180007dab  call    ?ActiveBlockInboundRulesExist@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; ActiveBlockInboundRulesExist(void *,int *,_tag_FW_PROFILE_TYPE)
0x180007db0  mov     ebx, eax
0x180007db2  test    eax, eax
0x180007db4  jns     short loc_180007DED
0x180007db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dbd  cmp     rcx, r12
0x180007dc0  jz      loc_180007C1A
0x180007dc6  test    byte ptr [rcx+1Ch], 1
0x180007dca  jz      loc_180007C1A
0x180007dd0  mov     rcx, [rcx+10h]
0x180007dd4  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007ddb  mov     edx, 2Eh ; '.'
0x180007de0  mov     r9d, eax
0x180007de3  call    WPP_SF_d
0x180007de8  jmp     loc_180007C1A
0x180007ded  cmp     [rsp+98h+var_58], r15d
0x180007df2  jnz     loc_180007C14
0x180007df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dff  cmp     rcx, r12
0x180007e02  jz      short loc_180007E22
0x180007e04  test    byte ptr [rcx+1Ch], 4
0x180007e08  jz      short loc_180007E22
0x180007e0a  mov     rcx, [rcx+10h]
0x180007e0e  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007e15  mov     edx, 2Fh ; '/'
0x180007e1a  mov     r9d, ebp
0x180007e1d  call    WPP_SF_d
0x180007e22  mov     [rdi], r15d
0x180007e25  jmp     loc_180007C1A
```
