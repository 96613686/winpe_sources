# CTSCredManAssistant::SaveCreds(ushort const *,ushort const *,uchar *,ulong,int)

- ea: `0x1400ad4a4`
- end: `0x1400ada14`
- name: `?SaveCreds@CTSCredManAssistant@@QEAAJPEBG0PEAEKH@Z`
- size: `1392`
- prototype: `__int64 __usercall@<rax>(CTSCredManAssistant *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400b72e4`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14009693c`
- `0x1400ab084`
- `0x1400ac96c`
- `0x1400acf70`
- `0x1400ad4a4`
- `0x140113390`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400ad571`
- `KERNEL32!LocalFree` at `0x1400ad580`
- `KERNEL32!LocalFree` at `0x1400ad5a9`
- `KERNEL32!LocalFree` at `0x1400ad571`
- `KERNEL32!LocalFree` at `0x1400ad580`
- `KERNEL32!LocalFree` at `0x1400ad5a9`
- `KERNEL32!GetLastError` at `0x1400ad612`
- `KERNEL32!GetLastError` at `0x1400ad640`
- `KERNEL32!GetLastError` at `0x1400ad8a1`
- `KERNEL32!GetLastError` at `0x1400ad8da`
- `KERNEL32!GetLastError` at `0x1400ad612`
- `KERNEL32!GetLastError` at `0x1400ad640`
- `KERNEL32!GetLastError` at `0x1400ad8a1`
- `KERNEL32!GetLastError` at `0x1400ad8da`
- `ADVAPI32!CredWriteW` at `0x1400ad892`
- `ADVAPI32!CredWriteW` at `0x1400ad8cc`
- `ADVAPI32!CredWriteW` at `0x1400ad892`
- `ADVAPI32!CredWriteW` at `0x1400ad8cc`
- `ADVAPI32!CredGetSessionTypes` at `0x1400ad5e4`
- `ADVAPI32!CredGetSessionTypes` at `0x1400ad5e4`

## string_xrefs

- `0x1400ad6f0`: `PrepareForCredWriteOld failed`
- `0x1400ad811`: `PrepareForCredWriteNew failed`
- `0x1400ad923`: `CredWrite failed`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::SaveCreds(
        CTSCredManAssistant *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbAuthBuffer,
        int a6)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // ebx
  _BYTE *v11; // rax
  __int64 v12; // rcx
  int v14; // ebx
  CTSCredManAssistant *v15; // rcx
  const unsigned __int16 *v16; // r8
  DWORD LastError; // ebx
  unsigned int v18; // eax
  signed int v19; // eax
  int v20; // esi
  unsigned int v21; // eax
  int v22; // edx
  const char *v23; // rcx
  unsigned int v24; // eax
  DWORD v25; // ecx
  DWORD v26; // edx
  signed int v27; // eax
  signed int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // [rsp+60h] [rbp-89h] BYREF
  unsigned int v33; // [rsp+64h] [rbp-85h] BYREF
  HLOCAL v34; // [rsp+68h] [rbp-81h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-79h] BYREF
  HLOCAL v36; // [rsp+78h] [rbp-71h] BYREF
  struct _CREDENTIALW Credential; // [rsp+80h] [rbp-69h] BYREF
  DWORD MaximumPersist[8]; // [rsp+D0h] [rbp-19h] BYREF

  memset_0(&Credential, 0, sizeof(Credential));
  v32 = 0;
  hMem = 0;
  v36 = 0;
  v34 = 0;
  v33 = 0;
  memset(MaximumPersist, 0, 28);
  if ( cbAuthBuffer < 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
LABEL_6:
    v10 = -2147024809;
    goto LABEL_7;
  }
  v14 = *(_DWORD *)a4;
  if ( !CredGetSessionTypes(7u, MaximumPersist) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
        v18,
        LastError);
    }
    v19 = GetLastError();
    v10 = v19;
    if ( v19 > 0 )
      v10 = (unsigned __int16)v19 | 0x80070000;
    goto LABEL_7;
  }
  MaximumPersist[6] = 2;
  if ( v14 == 2 )
  {
    v20 = a6;
    v10 = CTSCredManAssistant::PrepareForCredWriteOld(
            v15,
            a2,
            v16,
            a4,
            cbAuthBuffer,
            &v32,
            (unsigned __int16 **)&hMem,
            (unsigned __int16 **)&v36,
            (unsigned __int8 **)&v34,
            &v33,
            a6);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      v22 = 70;
      v23 = "PrepareForCredWriteOld failed";
      goto LABEL_30;
    }
  }
  else
  {
    if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v31, v14);
      }
      goto LABEL_6;
    }
    v20 = a6;
    if ( a6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v24);
      }
      goto LABEL_6;
    }
    v10 = CTSCredManAssistant::PrepareForCredWriteNew(
            this,
            a2,
            L"TERMSRV",
            a4,
            cbAuthBuffer,
            &v32,
            (unsigned __int16 **)&hMem,
            (unsigned __int16 **)&v36,
            (unsigned __int8 **)&v34,
            &v33);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      v22 = 72;
      v23 = "PrepareForCredWriteNew failed";
LABEL_30:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
        v21,
        (__int64)v23,
        v10);
      goto LABEL_7;
    }
  }
  v25 = v32;
  v26 = MaximumPersist[v32];
  if ( v26 > 2 )
  {
    MaximumPersist[v32] = 2;
    goto LABEL_44;
  }
  if ( v26 )
  {
LABEL_44:
    if ( !v20 )
    {
      CTSCredManAssistant::DeleteSavedCreds(this, a2, L"TERMSRV", 0, v25 == 2);
      v25 = v32;
    }
    Credential.TargetName = (LPWSTR)hMem;
    Credential.CredentialBlob = (LPBYTE)v34;
    Credential.CredentialBlobSize = v33;
    Credential.Type = v25;
    Credential.Persist = MaximumPersist[v25];
    Credential.UserName = (LPWSTR)v36;
    if ( !CredWriteW(&Credential, 0) )
    {
      v27 = GetLastError();
      v10 = v27;
      if ( v27 > 0 )
        v10 = (unsigned __int16)v27 | 0x80070000;
    }
    if ( v10 == -2147024809 )
    {
      if ( v32 != 2 )
      {
LABEL_55:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
            v29,
            (__int64)"CredWrite failed",
            v10);
        }
        goto LABEL_7;
      }
      Credential.TargetName = a2;
      v10 = 0;
      if ( CredWriteW(&Credential, 0) )
        goto LABEL_7;
      v28 = GetLastError();
      v10 = v28;
      if ( v28 > 0 )
        v10 = (unsigned __int16)v28 | 0x80070000;
    }
    if ( v10 >= 0 )
      goto LABEL_7;
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v30, 0);
  }
  v10 = -2147024891;
LABEL_7:
  if ( hMem )
    LocalFree(hMem);
  if ( v36 )
    LocalFree(v36);
  v11 = v34;
  if ( v34 )
  {
    v12 = v33;
    if ( v33 )
    {
      do
      {
        *v11++ = 0;
        --v12;
      }
      while ( v12 );
    }
    LocalFree(v34);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400ad4a4  mov     [rsp-8+arg_10], rbx
0x1400ad4a9  push    rbp
0x1400ad4aa  push    rsi
0x1400ad4ab  push    rdi
0x1400ad4ac  push    r12
0x1400ad4ae  push    r13
0x1400ad4b0  push    r14
0x1400ad4b2  push    r15
0x1400ad4b4  lea     rbp, [rsp-17h]
0x1400ad4b9  sub     rsp, 100h
0x1400ad4c0  mov     rax, cs:__security_cookie
0x1400ad4c7  xor     rax, rsp
0x1400ad4ca  mov     [rbp+47h+var_40], rax
0x1400ad4ce  mov     r15, rdx
0x1400ad4d1  mov     r13, rcx
0x1400ad4d4  xor     edx, edx; Val
0x1400ad4d6  lea     rcx, [rbp+47h+Credential]; void *
0x1400ad4da  mov     r14, r9
0x1400ad4dd  lea     r8d, [rdx+50h]; Size
0x1400ad4e1  call    memset_0
0x1400ad4e6  mov     r12d, [rbp+47h+arg_20]
0x1400ad4ea  xor     esi, esi
0x1400ad4ec  mov     [rsp+130h+var_D0], esi
0x1400ad4f0  xorps   xmm0, xmm0
0x1400ad4f3  mov     [rbp+47h+hMem], rsi
0x1400ad4f7  mov     [rbp+47h+var_B8], rsi
0x1400ad4fb  mov     [rsp+130h+var_C8], rsi
0x1400ad500  lea     edi, [rsi+1]
0x1400ad503  mov     [rsp+130h+var_CC], esi
0x1400ad507  movups  xmmword ptr [rbp+47h+MaximumPersist], xmm0
0x1400ad50b  movups  xmmword ptr [rbp+47h+MaximumPersist+0Ch], xmm0
0x1400ad50f  cmp     r12d, 4
0x1400ad513  jnb     loc_1400AD5D8
0x1400ad519  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad520  lea     rax, WPP_GLOBAL_Control
0x1400ad527  cmp     rcx, rax
0x1400ad52a  jz      short loc_1400AD55D
0x1400ad52c  test    [rcx+1Ch], dil
0x1400ad530  jz      short loc_1400AD55D
0x1400ad532  lea     edi, [rsi+2]
0x1400ad535  cmp     [rcx+19h], dil
0x1400ad539  jb      short loc_1400AD55D
0x1400ad53b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad540  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad547  lea     edx, [rsi+44h]
0x1400ad54a  mov     r9d, eax
0x1400ad54d  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ad554  mov     rcx, [rcx+10h]
0x1400ad558  call    WPP_SF_d
0x1400ad55d  mov     r14d, 1
0x1400ad563  mov     ebx, 80070057h
0x1400ad568  mov     rcx, [rbp+47h+hMem]; hMem
0x1400ad56c  test    rcx, rcx
0x1400ad56f  jz      short loc_1400AD577
0x1400ad571  call    cs:__imp_LocalFree
0x1400ad577  mov     rcx, [rbp+47h+var_B8]; hMem
0x1400ad57b  test    rcx, rcx
0x1400ad57e  jz      short loc_1400AD586
0x1400ad580  call    cs:__imp_LocalFree
0x1400ad586  mov     rax, [rsp+130h+var_C8]
0x1400ad58b  test    rax, rax
0x1400ad58e  jz      short loc_1400AD5AF
0x1400ad590  mov     ecx, [rsp+130h+var_CC]
0x1400ad594  test    rcx, rcx
0x1400ad597  jz      short loc_1400AD5A4
0x1400ad599  mov     byte ptr [rax], 0
0x1400ad59c  add     rax, r14
0x1400ad59f  sub     rcx, r14
0x1400ad5a2  jnz     short loc_1400AD599
0x1400ad5a4  mov     rcx, [rsp+130h+var_C8]; hMem
0x1400ad5a9  call    cs:__imp_LocalFree
0x1400ad5af  mov     eax, ebx
0x1400ad5b1  mov     rcx, [rbp+47h+var_40]
0x1400ad5b5  xor     rcx, rsp; StackCookie
0x1400ad5b8  call    __security_check_cookie
0x1400ad5bd  mov     rbx, [rsp+130h+arg_10]
0x1400ad5c5  add     rsp, 100h
0x1400ad5cc  pop     r15
0x1400ad5ce  pop     r14
0x1400ad5d0  pop     r13
0x1400ad5d2  pop     r12
0x1400ad5d4  pop     rdi
0x1400ad5d5  pop     rsi
0x1400ad5d6  pop     rbp
0x1400ad5d7  retn
0x1400ad5d8  mov     ebx, [r14]
0x1400ad5db  lea     rdx, [rbp+47h+MaximumPersist]; MaximumPersist
0x1400ad5df  mov     ecx, 7; MaximumPersistCount
0x1400ad5e4  call    cs:__imp_CredGetSessionTypes
0x1400ad5ea  test    eax, eax
0x1400ad5ec  jnz     short loc_1400AD660
0x1400ad5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad5f5  lea     rax, WPP_GLOBAL_Control
0x1400ad5fc  cmp     rcx, rax
0x1400ad5ff  jz      short loc_1400AD640
0x1400ad601  test    [rcx+1Ch], dil
0x1400ad605  jz      short loc_1400AD640
0x1400ad607  mov     edi, 2
0x1400ad60c  cmp     [rcx+19h], dil
0x1400ad610  jb      short loc_1400AD640
0x1400ad612  call    cs:__imp_GetLastError
0x1400ad618  mov     ebx, eax
0x1400ad61a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad61f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad626  lea     edx, [rdi+43h]
0x1400ad629  mov     r9d, eax
0x1400ad62c  mov     [rsp+130h+cbAuthBuffer], ebx
0x1400ad630  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ad637  mov     rcx, [rcx+10h]
0x1400ad63b  call    WPP_SF_Dd
0x1400ad640  call    cs:__imp_GetLastError
0x1400ad646  mov     ebx, eax
0x1400ad648  test    eax, eax
0x1400ad64a  jle     short loc_1400AD655
0x1400ad64c  movzx   ebx, ax
0x1400ad64f  or      ebx, 80070000h
0x1400ad655  mov     r14d, 1
0x1400ad65b  jmp     loc_1400AD568
0x1400ad660  mov     edi, 2
0x1400ad665  mov     [rbp+47h+var_48], edi
0x1400ad668  cmp     ebx, edi
0x1400ad66a  jnz     loc_1400AD71F
0x1400ad670  mov     esi, [rbp+47h+arg_28]
0x1400ad673  lea     rax, [rsp+130h+var_CC]
0x1400ad678  mov     [rsp+130h+var_E0], esi; int
0x1400ad67c  mov     r9, r14; unsigned __int8 *
0x1400ad67f  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1400ad684  mov     rdx, r15; unsigned __int16 *
0x1400ad687  lea     rax, [rsp+130h+var_C8]
0x1400ad68c  mov     [rsp+130h+var_F0], rax; unsigned __int8 **
0x1400ad691  lea     rax, [rbp+47h+var_B8]
0x1400ad695  mov     [rsp+130h+var_F8], rax; unsigned __int16 **
0x1400ad69a  lea     rax, [rbp+47h+hMem]
0x1400ad69e  mov     [rsp+130h+var_100], rax; unsigned __int16 **
0x1400ad6a3  lea     rax, [rsp+130h+var_D0]
0x1400ad6a8  mov     [rsp+130h+var_108], rax; unsigned int *
0x1400ad6ad  mov     [rsp+130h+cbAuthBuffer], r12d; cbAuthBuffer
0x1400ad6b2  call    ?PrepareForCredWriteOld@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2H@Z; CTSCredManAssistant::PrepareForCredWriteOld(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *,int)
0x1400ad6b7  mov     ebx, eax
0x1400ad6b9  test    eax, eax
0x1400ad6bb  jns     loc_1400AD81D
0x1400ad6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad6c8  lea     rax, WPP_GLOBAL_Control
0x1400ad6cf  cmp     rcx, rax
0x1400ad6d2  jz      short loc_1400AD655
0x1400ad6d4  test    byte ptr [rcx+1Ch], 8
0x1400ad6d8  jz      loc_1400AD655
0x1400ad6de  cmp     [rcx+19h], dil
0x1400ad6e2  jb      loc_1400AD655
0x1400ad6e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad6ed  lea     edx, [rdi+44h]
0x1400ad6f0  lea     rcx, aPrepareforcred; "PrepareForCredWriteOld failed"
0x1400ad6f7  mov     dword ptr [rsp+130h+var_108], ebx
0x1400ad6fb  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ad702  mov     qword ptr [rsp+130h+cbAuthBuffer], rcx
0x1400ad707  mov     r9d, eax
0x1400ad70a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad711  mov     rcx, [rcx+10h]
0x1400ad715  call    WPP_SF_DsD
0x1400ad71a  jmp     loc_1400AD655
0x1400ad71f  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ad724  test    eax, eax
0x1400ad726  jz      loc_1400AD9B7
0x1400ad72c  mov     esi, [rbp+47h+arg_28]
0x1400ad72f  test    esi, esi
0x1400ad731  jz      short loc_1400AD78C
0x1400ad733  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad73a  lea     rax, WPP_GLOBAL_Control
0x1400ad741  mov     r14d, 1
0x1400ad747  cmp     rcx, rax
0x1400ad74a  jz      loc_1400AD563
0x1400ad750  test    [rcx+1Ch], r14b
0x1400ad754  jz      loc_1400AD563
0x1400ad75a  cmp     [rcx+19h], dil
0x1400ad75e  jb      loc_1400AD563
0x1400ad764  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad769  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad770  lea     edx, [r14+46h]
0x1400ad774  mov     r9d, eax
0x1400ad777  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ad77e  mov     rcx, [rcx+10h]
0x1400ad782  call    WPP_SF_d
0x1400ad787  jmp     loc_1400AD563
0x1400ad78c  lea     rax, [rsp+130h+var_CC]
0x1400ad791  mov     r9, r14; unsigned __int8 *
0x1400ad794  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1400ad799  lea     r8, aTermsrv; "TERMSRV"
0x1400ad7a0  lea     rax, [rsp+130h+var_C8]
0x1400ad7a5  mov     rdx, r15; unsigned __int16 *
0x1400ad7a8  mov     [rsp+130h+var_F0], rax; unsigned __int8 **
0x1400ad7ad  mov     rcx, r13; this
0x1400ad7b0  lea     rax, [rbp+47h+var_B8]
0x1400ad7b4  mov     [rsp+130h+var_F8], rax; unsigned __int16 **
0x1400ad7b9  lea     rax, [rbp+47h+hMem]
0x1400ad7bd  mov     [rsp+130h+var_100], rax; unsigned __int16 **
0x1400ad7c2  lea     rax, [rsp+130h+var_D0]
0x1400ad7c7  mov     [rsp+130h+var_108], rax; unsigned int *
0x1400ad7cc  mov     [rsp+130h+cbAuthBuffer], r12d; unsigned int
0x1400ad7d1  call    ?PrepareForCredWriteNew@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2@Z; CTSCredManAssistant::PrepareForCredWriteNew(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *)
0x1400ad7d6  mov     ebx, eax
0x1400ad7d8  test    eax, eax
0x1400ad7da  jns     short loc_1400AD81D
0x1400ad7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad7e3  lea     rax, WPP_GLOBAL_Control
0x1400ad7ea  cmp     rcx, rax
0x1400ad7ed  jz      loc_1400AD655
0x1400ad7f3  test    byte ptr [rcx+1Ch], 8
0x1400ad7f7  jz      loc_1400AD655
0x1400ad7fd  cmp     [rcx+19h], dil
0x1400ad801  jb      loc_1400AD655
0x1400ad807  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad80c  mov     edx, 48h ; 'H'
0x1400ad811  lea     rcx, aPrepareforcred_0; "PrepareForCredWriteNew failed"
0x1400ad818  jmp     loc_1400AD6F7
0x1400ad81d  mov     ecx, [rsp+130h+var_D0]
0x1400ad821  mov     edx, [rbp+rcx*4+47h+MaximumPersist]
0x1400ad825  cmp     edx, edi
0x1400ad827  jbe     loc_1400AD957
0x1400ad82d  mov     [rbp+rcx*4+47h+MaximumPersist], edi
0x1400ad831  mov     r14d, 1
0x1400ad837  test    esi, esi
0x1400ad839  jnz     short loc_1400AD860
0x1400ad83b  xor     eax, eax
0x1400ad83d  lea     r8, aTermsrv; "TERMSRV"
0x1400ad844  cmp     ecx, edi
0x1400ad846  mov     rdx, r15; unsigned __int16 *
0x1400ad849  mov     rcx, r13; this
0x1400ad84c  cmovz   eax, r14d
0x1400ad850  xor     r9d, r9d; unsigned int
0x1400ad853  mov     [rsp+130h+cbAuthBuffer], eax; unsigned int
0x1400ad857  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400ad85c  mov     ecx, [rsp+130h+var_D0]
0x1400ad860  mov     rax, [rbp+47h+hMem]
0x1400ad864  xor     edx, edx; Flags
0x1400ad866  mov     [rbp+47h+Credential.TargetName], rax
0x1400ad86a  mov     rax, [rsp+130h+var_C8]
0x1400ad86f  mov     [rbp+47h+Credential.CredentialBlob], rax
0x1400ad873  mov     eax, [rsp+130h+var_CC]
0x1400ad877  mov     [rbp+47h+Credential.CredentialBlobSize], eax
0x1400ad87a  mov     eax, ecx
0x1400ad87c  mov     [rbp+47h+Credential.Type], ecx
0x1400ad87f  mov     ecx, [rbp+rax*4+47h+MaximumPersist]
0x1400ad883  mov     rax, [rbp+47h+var_B8]
0x1400ad887  mov     [rbp+47h+Credential.Persist], ecx
0x1400ad88a  lea     rcx, [rbp+47h+Credential]; Credential
0x1400ad88e  mov     [rbp+47h+Credential.UserName], rax
0x1400ad892  call    cs:__imp_CredWriteW
0x1400ad898  mov     esi, 80070000h
0x1400ad89d  test    eax, eax
0x1400ad89f  jnz     short loc_1400AD8B2
0x1400ad8a1  call    cs:__imp_GetLastError
0x1400ad8a7  mov     ebx, eax
0x1400ad8a9  test    eax, eax
0x1400ad8ab  jle     short loc_1400AD8B2
0x1400ad8ad  movzx   ebx, ax
0x1400ad8b0  or      ebx, esi
0x1400ad8b2  cmp     ebx, 80070057h
0x1400ad8b8  jnz     short loc_1400AD8EB
0x1400ad8ba  cmp     [rsp+130h+var_D0], edi
0x1400ad8be  jnz     short loc_1400AD8F3
0x1400ad8c0  xor     edx, edx; Flags
0x1400ad8c2  mov     [rbp+47h+Credential.TargetName], r15
0x1400ad8c6  lea     rcx, [rbp+47h+Credential]; Credential
0x1400ad8ca  xor     ebx, ebx
0x1400ad8cc  call    cs:__imp_CredWriteW
0x1400ad8d2  test    eax, eax
0x1400ad8d4  jnz     loc_1400AD568
0x1400ad8da  call    cs:__imp_GetLastError
0x1400ad8e0  mov     ebx, eax
0x1400ad8e2  test    eax, eax
0x1400ad8e4  jle     short loc_1400AD8EB
0x1400ad8e6  movzx   ebx, ax
0x1400ad8e9  or      ebx, esi
0x1400ad8eb  test    ebx, ebx
0x1400ad8ed  jns     loc_1400AD568
0x1400ad8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad8fa  lea     rax, WPP_GLOBAL_Control
0x1400ad901  cmp     rcx, rax
0x1400ad904  jz      loc_1400AD568
0x1400ad90a  test    byte ptr [rcx+1Ch], 8
0x1400ad90e  jz      loc_1400AD568
0x1400ad914  cmp     [rcx+19h], dil
0x1400ad918  jb      loc_1400AD568
0x1400ad91e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad923  lea     rcx, aCredwriteFaile; "CredWrite failed"
0x1400ad92a  mov     dword ptr [rsp+130h+var_108], ebx
0x1400ad92e  mov     qword ptr [rsp+130h+cbAuthBuffer], rcx
0x1400ad933  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ad93a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad941  mov     edx, 4Bh ; 'K'
0x1400ad946  mov     r9d, eax
0x1400ad949  mov     rcx, [rcx+10h]
0x1400ad94d  call    WPP_SF_DsD
0x1400ad952  jmp     loc_1400AD568
0x1400ad957  test    edx, edx
0x1400ad959  jnz     loc_1400AD831
0x1400ad95f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad966  lea     rax, WPP_GLOBAL_Control
0x1400ad96d  lea     r14d, [rdx+1]
0x1400ad971  cmp     rcx, rax
  ... truncated ...
```
