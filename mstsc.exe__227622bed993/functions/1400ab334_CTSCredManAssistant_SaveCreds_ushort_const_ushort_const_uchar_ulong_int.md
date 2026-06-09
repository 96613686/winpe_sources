# CTSCredManAssistant::SaveCreds(ushort const *,ushort const *,uchar *,ulong,int)

- ea: `0x1400ab334`
- end: `0x1400ab8a4`
- name: `?SaveCreds@CTSCredManAssistant@@QEAAJPEBG0PEAEKH@Z`
- size: `1392`
- prototype: `__int64 __usercall@<rax>(CTSCredManAssistant *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400b5174`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400947cc`
- `0x1400a8f14`
- `0x1400aa7fc`
- `0x1400aae00`
- `0x1400ab334`
- `0x140111220`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400ab401`
- `KERNEL32!LocalFree` at `0x1400ab410`
- `KERNEL32!LocalFree` at `0x1400ab439`
- `KERNEL32!LocalFree` at `0x1400ab401`
- `KERNEL32!LocalFree` at `0x1400ab410`
- `KERNEL32!LocalFree` at `0x1400ab439`
- `KERNEL32!GetLastError` at `0x1400ab4a2`
- `KERNEL32!GetLastError` at `0x1400ab4d0`
- `KERNEL32!GetLastError` at `0x1400ab731`
- `KERNEL32!GetLastError` at `0x1400ab76a`
- `KERNEL32!GetLastError` at `0x1400ab4a2`
- `KERNEL32!GetLastError` at `0x1400ab4d0`
- `KERNEL32!GetLastError` at `0x1400ab731`
- `KERNEL32!GetLastError` at `0x1400ab76a`
- `ADVAPI32!CredWriteW` at `0x1400ab722`
- `ADVAPI32!CredWriteW` at `0x1400ab75c`
- `ADVAPI32!CredWriteW` at `0x1400ab722`
- `ADVAPI32!CredWriteW` at `0x1400ab75c`
- `ADVAPI32!CredGetSessionTypes` at `0x1400ab474`
- `ADVAPI32!CredGetSessionTypes` at `0x1400ab474`

## string_xrefs

- `0x1400ab6a1`: `PrepareForCredWriteNew failed`
- `0x1400ab7b3`: `CredWrite failed`
- `0x1400ab580`: `PrepareForCredWriteOld failed`

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
0x1400ab334  mov     [rsp-8+arg_10], rbx
0x1400ab339  push    rbp
0x1400ab33a  push    rsi
0x1400ab33b  push    rdi
0x1400ab33c  push    r12
0x1400ab33e  push    r13
0x1400ab340  push    r14
0x1400ab342  push    r15
0x1400ab344  lea     rbp, [rsp-17h]
0x1400ab349  sub     rsp, 100h
0x1400ab350  mov     rax, cs:__security_cookie
0x1400ab357  xor     rax, rsp
0x1400ab35a  mov     [rbp+47h+var_40], rax
0x1400ab35e  mov     r15, rdx
0x1400ab361  mov     r13, rcx
0x1400ab364  xor     edx, edx; Val
0x1400ab366  lea     rcx, [rbp+47h+Credential]; void *
0x1400ab36a  mov     r14, r9
0x1400ab36d  lea     r8d, [rdx+50h]; Size
0x1400ab371  call    memset_0
0x1400ab376  mov     r12d, [rbp+47h+arg_20]
0x1400ab37a  xor     esi, esi
0x1400ab37c  mov     [rsp+130h+var_D0], esi
0x1400ab380  xorps   xmm0, xmm0
0x1400ab383  mov     [rbp+47h+hMem], rsi
0x1400ab387  mov     [rbp+47h+var_B8], rsi
0x1400ab38b  mov     [rsp+130h+var_C8], rsi
0x1400ab390  lea     edi, [rsi+1]
0x1400ab393  mov     [rsp+130h+var_CC], esi
0x1400ab397  movups  xmmword ptr [rbp+47h+MaximumPersist], xmm0
0x1400ab39b  movups  xmmword ptr [rbp+47h+MaximumPersist+0Ch], xmm0
0x1400ab39f  cmp     r12d, 4
0x1400ab3a3  jnb     loc_1400AB468
0x1400ab3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab3b0  lea     rax, WPP_GLOBAL_Control
0x1400ab3b7  cmp     rcx, rax
0x1400ab3ba  jz      short loc_1400AB3ED
0x1400ab3bc  test    [rcx+1Ch], dil
0x1400ab3c0  jz      short loc_1400AB3ED
0x1400ab3c2  lea     edi, [rsi+2]
0x1400ab3c5  cmp     [rcx+19h], dil
0x1400ab3c9  jb      short loc_1400AB3ED
0x1400ab3cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab3d7  lea     edx, [rsi+44h]
0x1400ab3da  mov     r9d, eax
0x1400ab3dd  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab3e4  mov     rcx, [rcx+10h]
0x1400ab3e8  call    WPP_SF_d
0x1400ab3ed  mov     r14d, 1
0x1400ab3f3  mov     ebx, 80070057h
0x1400ab3f8  mov     rcx, [rbp+47h+hMem]; hMem
0x1400ab3fc  test    rcx, rcx
0x1400ab3ff  jz      short loc_1400AB407
0x1400ab401  call    cs:__imp_LocalFree
0x1400ab407  mov     rcx, [rbp+47h+var_B8]; hMem
0x1400ab40b  test    rcx, rcx
0x1400ab40e  jz      short loc_1400AB416
0x1400ab410  call    cs:__imp_LocalFree
0x1400ab416  mov     rax, [rsp+130h+var_C8]
0x1400ab41b  test    rax, rax
0x1400ab41e  jz      short loc_1400AB43F
0x1400ab420  mov     ecx, [rsp+130h+var_CC]
0x1400ab424  test    rcx, rcx
0x1400ab427  jz      short loc_1400AB434
0x1400ab429  mov     byte ptr [rax], 0
0x1400ab42c  add     rax, r14
0x1400ab42f  sub     rcx, r14
0x1400ab432  jnz     short loc_1400AB429
0x1400ab434  mov     rcx, [rsp+130h+var_C8]; hMem
0x1400ab439  call    cs:__imp_LocalFree
0x1400ab43f  mov     eax, ebx
0x1400ab441  mov     rcx, [rbp+47h+var_40]
0x1400ab445  xor     rcx, rsp; StackCookie
0x1400ab448  call    __security_check_cookie
0x1400ab44d  mov     rbx, [rsp+130h+arg_10]
0x1400ab455  add     rsp, 100h
0x1400ab45c  pop     r15
0x1400ab45e  pop     r14
0x1400ab460  pop     r13
0x1400ab462  pop     r12
0x1400ab464  pop     rdi
0x1400ab465  pop     rsi
0x1400ab466  pop     rbp
0x1400ab467  retn
0x1400ab468  mov     ebx, [r14]
0x1400ab46b  lea     rdx, [rbp+47h+MaximumPersist]; MaximumPersist
0x1400ab46f  mov     ecx, 7; MaximumPersistCount
0x1400ab474  call    cs:__imp_CredGetSessionTypes
0x1400ab47a  test    eax, eax
0x1400ab47c  jnz     short loc_1400AB4F0
0x1400ab47e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab485  lea     rax, WPP_GLOBAL_Control
0x1400ab48c  cmp     rcx, rax
0x1400ab48f  jz      short loc_1400AB4D0
0x1400ab491  test    [rcx+1Ch], dil
0x1400ab495  jz      short loc_1400AB4D0
0x1400ab497  mov     edi, 2
0x1400ab49c  cmp     [rcx+19h], dil
0x1400ab4a0  jb      short loc_1400AB4D0
0x1400ab4a2  call    cs:__imp_GetLastError
0x1400ab4a8  mov     ebx, eax
0x1400ab4aa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab4af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab4b6  lea     edx, [rdi+43h]
0x1400ab4b9  mov     r9d, eax
0x1400ab4bc  mov     [rsp+130h+cbAuthBuffer], ebx
0x1400ab4c0  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab4c7  mov     rcx, [rcx+10h]
0x1400ab4cb  call    WPP_SF_Dd
0x1400ab4d0  call    cs:__imp_GetLastError
0x1400ab4d6  mov     ebx, eax
0x1400ab4d8  test    eax, eax
0x1400ab4da  jle     short loc_1400AB4E5
0x1400ab4dc  movzx   ebx, ax
0x1400ab4df  or      ebx, 80070000h
0x1400ab4e5  mov     r14d, 1
0x1400ab4eb  jmp     loc_1400AB3F8
0x1400ab4f0  mov     edi, 2
0x1400ab4f5  mov     [rbp+47h+var_48], edi
0x1400ab4f8  cmp     ebx, edi
0x1400ab4fa  jnz     loc_1400AB5AF
0x1400ab500  mov     esi, [rbp+47h+arg_28]
0x1400ab503  lea     rax, [rsp+130h+var_CC]
0x1400ab508  mov     [rsp+130h+var_E0], esi; int
0x1400ab50c  mov     r9, r14; unsigned __int8 *
0x1400ab50f  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1400ab514  mov     rdx, r15; unsigned __int16 *
0x1400ab517  lea     rax, [rsp+130h+var_C8]
0x1400ab51c  mov     [rsp+130h+var_F0], rax; unsigned __int8 **
0x1400ab521  lea     rax, [rbp+47h+var_B8]
0x1400ab525  mov     [rsp+130h+var_F8], rax; unsigned __int16 **
0x1400ab52a  lea     rax, [rbp+47h+hMem]
0x1400ab52e  mov     [rsp+130h+var_100], rax; unsigned __int16 **
0x1400ab533  lea     rax, [rsp+130h+var_D0]
0x1400ab538  mov     [rsp+130h+var_108], rax; unsigned int *
0x1400ab53d  mov     [rsp+130h+cbAuthBuffer], r12d; cbAuthBuffer
0x1400ab542  call    ?PrepareForCredWriteOld@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2H@Z; CTSCredManAssistant::PrepareForCredWriteOld(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *,int)
0x1400ab547  mov     ebx, eax
0x1400ab549  test    eax, eax
0x1400ab54b  jns     loc_1400AB6AD
0x1400ab551  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab558  lea     rax, WPP_GLOBAL_Control
0x1400ab55f  cmp     rcx, rax
0x1400ab562  jz      short loc_1400AB4E5
0x1400ab564  test    byte ptr [rcx+1Ch], 8
0x1400ab568  jz      loc_1400AB4E5
0x1400ab56e  cmp     [rcx+19h], dil
0x1400ab572  jb      loc_1400AB4E5
0x1400ab578  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab57d  lea     edx, [rdi+44h]
0x1400ab580  lea     rcx, aPrepareforcred; "PrepareForCredWriteOld failed"
0x1400ab587  mov     dword ptr [rsp+130h+var_108], ebx
0x1400ab58b  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab592  mov     qword ptr [rsp+130h+cbAuthBuffer], rcx
0x1400ab597  mov     r9d, eax
0x1400ab59a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab5a1  mov     rcx, [rcx+10h]
0x1400ab5a5  call    WPP_SF_DsD
0x1400ab5aa  jmp     loc_1400AB4E5
0x1400ab5af  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ab5b4  test    eax, eax
0x1400ab5b6  jz      loc_1400AB847
0x1400ab5bc  mov     esi, [rbp+47h+arg_28]
0x1400ab5bf  test    esi, esi
0x1400ab5c1  jz      short loc_1400AB61C
0x1400ab5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab5ca  lea     rax, WPP_GLOBAL_Control
0x1400ab5d1  mov     r14d, 1
0x1400ab5d7  cmp     rcx, rax
0x1400ab5da  jz      loc_1400AB3F3
0x1400ab5e0  test    [rcx+1Ch], r14b
0x1400ab5e4  jz      loc_1400AB3F3
0x1400ab5ea  cmp     [rcx+19h], dil
0x1400ab5ee  jb      loc_1400AB3F3
0x1400ab5f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab600  lea     edx, [r14+46h]
0x1400ab604  mov     r9d, eax
0x1400ab607  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab60e  mov     rcx, [rcx+10h]
0x1400ab612  call    WPP_SF_d
0x1400ab617  jmp     loc_1400AB3F3
0x1400ab61c  lea     rax, [rsp+130h+var_CC]
0x1400ab621  mov     r9, r14; unsigned __int8 *
0x1400ab624  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1400ab629  lea     r8, aTermsrv; "TERMSRV"
0x1400ab630  lea     rax, [rsp+130h+var_C8]
0x1400ab635  mov     rdx, r15; unsigned __int16 *
0x1400ab638  mov     [rsp+130h+var_F0], rax; unsigned __int8 **
0x1400ab63d  mov     rcx, r13; this
0x1400ab640  lea     rax, [rbp+47h+var_B8]
0x1400ab644  mov     [rsp+130h+var_F8], rax; unsigned __int16 **
0x1400ab649  lea     rax, [rbp+47h+hMem]
0x1400ab64d  mov     [rsp+130h+var_100], rax; unsigned __int16 **
0x1400ab652  lea     rax, [rsp+130h+var_D0]
0x1400ab657  mov     [rsp+130h+var_108], rax; unsigned int *
0x1400ab65c  mov     [rsp+130h+cbAuthBuffer], r12d; unsigned int
0x1400ab661  call    ?PrepareForCredWriteNew@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2@Z; CTSCredManAssistant::PrepareForCredWriteNew(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *)
0x1400ab666  mov     ebx, eax
0x1400ab668  test    eax, eax
0x1400ab66a  jns     short loc_1400AB6AD
0x1400ab66c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab673  lea     rax, WPP_GLOBAL_Control
0x1400ab67a  cmp     rcx, rax
0x1400ab67d  jz      loc_1400AB4E5
0x1400ab683  test    byte ptr [rcx+1Ch], 8
0x1400ab687  jz      loc_1400AB4E5
0x1400ab68d  cmp     [rcx+19h], dil
0x1400ab691  jb      loc_1400AB4E5
0x1400ab697  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab69c  mov     edx, 48h ; 'H'
0x1400ab6a1  lea     rcx, aPrepareforcred_0; "PrepareForCredWriteNew failed"
0x1400ab6a8  jmp     loc_1400AB587
0x1400ab6ad  mov     ecx, [rsp+130h+var_D0]
0x1400ab6b1  mov     edx, [rbp+rcx*4+47h+MaximumPersist]
0x1400ab6b5  cmp     edx, edi
0x1400ab6b7  jbe     loc_1400AB7E7
0x1400ab6bd  mov     [rbp+rcx*4+47h+MaximumPersist], edi
0x1400ab6c1  mov     r14d, 1
0x1400ab6c7  test    esi, esi
0x1400ab6c9  jnz     short loc_1400AB6F0
0x1400ab6cb  xor     eax, eax
0x1400ab6cd  lea     r8, aTermsrv; "TERMSRV"
0x1400ab6d4  cmp     ecx, edi
0x1400ab6d6  mov     rdx, r15; unsigned __int16 *
0x1400ab6d9  mov     rcx, r13; this
0x1400ab6dc  cmovz   eax, r14d
0x1400ab6e0  xor     r9d, r9d; unsigned int
0x1400ab6e3  mov     [rsp+130h+cbAuthBuffer], eax; unsigned int
0x1400ab6e7  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400ab6ec  mov     ecx, [rsp+130h+var_D0]
0x1400ab6f0  mov     rax, [rbp+47h+hMem]
0x1400ab6f4  xor     edx, edx; Flags
0x1400ab6f6  mov     [rbp+47h+Credential.TargetName], rax
0x1400ab6fa  mov     rax, [rsp+130h+var_C8]
0x1400ab6ff  mov     [rbp+47h+Credential.CredentialBlob], rax
0x1400ab703  mov     eax, [rsp+130h+var_CC]
0x1400ab707  mov     [rbp+47h+Credential.CredentialBlobSize], eax
0x1400ab70a  mov     eax, ecx
0x1400ab70c  mov     [rbp+47h+Credential.Type], ecx
0x1400ab70f  mov     ecx, [rbp+rax*4+47h+MaximumPersist]
0x1400ab713  mov     rax, [rbp+47h+var_B8]
0x1400ab717  mov     [rbp+47h+Credential.Persist], ecx
0x1400ab71a  lea     rcx, [rbp+47h+Credential]; Credential
0x1400ab71e  mov     [rbp+47h+Credential.UserName], rax
0x1400ab722  call    cs:__imp_CredWriteW
0x1400ab728  mov     esi, 80070000h
0x1400ab72d  test    eax, eax
0x1400ab72f  jnz     short loc_1400AB742
0x1400ab731  call    cs:__imp_GetLastError
0x1400ab737  mov     ebx, eax
0x1400ab739  test    eax, eax
0x1400ab73b  jle     short loc_1400AB742
0x1400ab73d  movzx   ebx, ax
0x1400ab740  or      ebx, esi
0x1400ab742  cmp     ebx, 80070057h
0x1400ab748  jnz     short loc_1400AB77B
0x1400ab74a  cmp     [rsp+130h+var_D0], edi
0x1400ab74e  jnz     short loc_1400AB783
0x1400ab750  xor     edx, edx; Flags
0x1400ab752  mov     [rbp+47h+Credential.TargetName], r15
0x1400ab756  lea     rcx, [rbp+47h+Credential]; Credential
0x1400ab75a  xor     ebx, ebx
0x1400ab75c  call    cs:__imp_CredWriteW
0x1400ab762  test    eax, eax
0x1400ab764  jnz     loc_1400AB3F8
0x1400ab76a  call    cs:__imp_GetLastError
0x1400ab770  mov     ebx, eax
0x1400ab772  test    eax, eax
0x1400ab774  jle     short loc_1400AB77B
0x1400ab776  movzx   ebx, ax
0x1400ab779  or      ebx, esi
0x1400ab77b  test    ebx, ebx
0x1400ab77d  jns     loc_1400AB3F8
0x1400ab783  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab78a  lea     rax, WPP_GLOBAL_Control
0x1400ab791  cmp     rcx, rax
0x1400ab794  jz      loc_1400AB3F8
0x1400ab79a  test    byte ptr [rcx+1Ch], 8
0x1400ab79e  jz      loc_1400AB3F8
0x1400ab7a4  cmp     [rcx+19h], dil
0x1400ab7a8  jb      loc_1400AB3F8
0x1400ab7ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab7b3  lea     rcx, aCredwriteFaile; "CredWrite failed"
0x1400ab7ba  mov     dword ptr [rsp+130h+var_108], ebx
0x1400ab7be  mov     qword ptr [rsp+130h+cbAuthBuffer], rcx
0x1400ab7c3  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab7d1  mov     edx, 4Bh ; 'K'
0x1400ab7d6  mov     r9d, eax
0x1400ab7d9  mov     rcx, [rcx+10h]
0x1400ab7dd  call    WPP_SF_DsD
0x1400ab7e2  jmp     loc_1400AB3F8
0x1400ab7e7  test    edx, edx
0x1400ab7e9  jnz     loc_1400AB6C1
0x1400ab7ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab7f6  lea     rax, WPP_GLOBAL_Control
0x1400ab7fd  lea     r14d, [rdx+1]
0x1400ab801  cmp     rcx, rax
  ... truncated ...
```
