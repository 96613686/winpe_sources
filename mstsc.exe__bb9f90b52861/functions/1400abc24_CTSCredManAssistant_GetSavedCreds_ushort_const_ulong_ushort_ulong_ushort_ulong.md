# CTSCredManAssistant::GetSavedCreds(ushort const *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x1400abc24`
- end: `0x1400abf4b`
- name: `?GetSavedCreds@CTSCredManAssistant@@QEAAJPEBGKPEAGK1K@Z`
- size: `807`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, DWORD Type, unsigned __int16 *, unsigned int, LPCWSTR TargetName, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400ada1c`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14009693c`
- `0x1400abc24`
- `0x1400abf54`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400abf3a`
- `KERNEL32!LocalFree` at `0x1400abf3a`
- `KERNEL32!GetLastError` at `0x1400abcfc`
- `KERNEL32!GetLastError` at `0x1400abded`
- `KERNEL32!GetLastError` at `0x1400abcfc`
- `KERNEL32!GetLastError` at `0x1400abded`
- `ADVAPI32!CredFree` at `0x1400abf2c`
- `ADVAPI32!CredFree` at `0x1400abf2c`
- `ADVAPI32!CredReadW` at `0x1400abcee`
- `ADVAPI32!CredReadW` at `0x1400abde3`
- `ADVAPI32!CredReadW` at `0x1400abcee`
- `ADVAPI32!CredReadW` at `0x1400abde3`

## string_xrefs

- `0x1400abef8`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::GetSavedCreds(
        CTSCredManAssistant *this,
        const unsigned __int16 *a2,
        DWORD Type,
        unsigned __int16 *a4,
        unsigned int a5,
        WCHAR *TargetName)
{
  WCHAR *v6; // rdi
  signed int TargetForExtednedCredential; // ebx
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  signed int LastError; // eax
  const unsigned __int16 *UserName; // r8
  unsigned int v18; // eax
  int v19; // edx
  signed int v21; // [rsp+28h] [rbp-40h]
  signed int v22; // [rsp+28h] [rbp-40h]
  PCREDENTIALW Credential[7]; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  Credential[0] = 0;
  TargetName = 0;
  if ( Type != 6 )
  {
    if ( CredReadW(a2, Type, 0, Credential) )
      goto LABEL_36;
    LastError = GetLastError();
    TargetForExtednedCredential = LastError;
    if ( LastError > 0 )
      TargetForExtednedCredential = (unsigned __int16)LastError | 0x80070000;
    if ( TargetForExtednedCredential != -2147024809 )
    {
      if ( TargetForExtednedCredential < 0 )
      {
        if ( TargetForExtednedCredential == -2147023728
          || TargetForExtednedCredential == -2147024891
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 26;
LABEL_19:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
          CurrentThreadActivityIdPrefix,
          TargetForExtednedCredential);
        goto LABEL_50;
      }
LABEL_37:
      if ( !a4 )
        goto LABEL_50;
      UserName = Credential[0]->UserName;
      if ( UserName )
      {
        TargetForExtednedCredential = StringCchCopyW(a4, a5, UserName);
        if ( TargetForExtednedCredential >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 27;
      }
      else
      {
        TargetForExtednedCredential = StringCchCopyW(a4, a5, &pszPassword);
        if ( TargetForExtednedCredential >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 28;
      }
      v22 = TargetForExtednedCredential;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
        v18,
        (__int64)"StringCchCopy failed!",
        v22);
      goto LABEL_50;
    }
LABEL_24:
    TargetForExtednedCredential = -2147023728;
    goto LABEL_50;
  }
  if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v15);
    }
    goto LABEL_24;
  }
  TargetForExtednedCredential = CTSCredManAssistant::GetTargetForExtednedCredential(this, a2, &TargetName);
  if ( TargetForExtednedCredential >= 0 )
  {
    v6 = TargetName;
    if ( !CredReadW(TargetName, 6u, 0, Credential) )
    {
      v12 = GetLastError();
      TargetForExtednedCredential = v12;
      if ( v12 > 0 )
        TargetForExtednedCredential = (unsigned __int16)v12 | 0x80070000;
      if ( TargetForExtednedCredential < 0 )
      {
        if ( TargetForExtednedCredential == -2147023728
          || TargetForExtednedCredential == -2147024891
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 24;
        goto LABEL_19;
      }
      goto LABEL_37;
    }
LABEL_36:
    TargetForExtednedCredential = 0;
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = TargetForExtednedCredential;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
      v11,
      (__int64)"GetTargetForExtednedCredential failed",
      v21);
  }
  v6 = TargetName;
LABEL_50:
  if ( Credential[0] )
    CredFree(Credential[0]);
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)TargetForExtednedCredential;
}

```

## disassembly

```asm
0x1400abc24  mov     r11, rsp
0x1400abc27  push    rbx
0x1400abc28  push    rbp
0x1400abc29  push    rsi
0x1400abc2a  push    rdi
0x1400abc2b  sub     rsp, 48h
0x1400abc2f  xor     edi, edi
0x1400abc31  mov     qword ptr [r11-38h], 0
0x1400abc39  mov     [r11+30h], rdi
0x1400abc3d  mov     rsi, r9
0x1400abc40  mov     eax, r8d
0x1400abc43  mov     rbx, rdx
0x1400abc46  mov     rbp, rcx
0x1400abc49  cmp     r8d, 6
0x1400abc4d  jnz     loc_1400ABDD6
0x1400abc53  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400abc58  test    eax, eax
0x1400abc5a  jz      loc_1400ABD89
0x1400abc60  lea     r8, [rsp+68h+TargetName]; unsigned __int16 **
0x1400abc68  mov     rdx, rbx; unsigned __int16 *
0x1400abc6b  mov     rcx, rbp; this
0x1400abc6e  call    ?GetTargetForExtednedCredential@CTSCredManAssistant@@AEAAJPEBGPEAPEAG@Z; CTSCredManAssistant::GetTargetForExtednedCredential(ushort const *,ushort * *)
0x1400abc73  mov     ebx, eax
0x1400abc75  test    eax, eax
0x1400abc77  jns     short loc_1400ABCD7
0x1400abc79  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abc80  lea     rax, WPP_GLOBAL_Control
0x1400abc87  cmp     rcx, rax
0x1400abc8a  jz      short loc_1400ABCCA
0x1400abc8c  test    byte ptr [rcx+1Ch], 8
0x1400abc90  jz      short loc_1400ABCCA
0x1400abc92  cmp     byte ptr [rcx+19h], 2
0x1400abc96  jb      short loc_1400ABCCA
0x1400abc98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abc9d  lea     rcx, aGettargetforex; "GetTargetForExtednedCredential failed"
0x1400abca4  mov     [rsp+68h+var_40], ebx
0x1400abca8  mov     [rsp+68h+var_48], rcx
0x1400abcad  lea     edx, [rdi+17h]
0x1400abcb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abcb7  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400abcbe  mov     r9d, eax
0x1400abcc1  mov     rcx, [rcx+10h]
0x1400abcc5  call    WPP_SF_DsD
0x1400abcca  mov     rdi, [rsp+68h+TargetName]
0x1400abcd2  jmp     loc_1400ABF22
0x1400abcd7  mov     rdi, [rsp+68h+TargetName]
0x1400abcdf  lea     r9, [rsp+68h+Credential]; Credential
0x1400abce4  xor     r8d, r8d; Flags
0x1400abce7  mov     rcx, rdi; TargetName
0x1400abcea  lea     edx, [r8+6]; Type
0x1400abcee  call    cs:__imp_CredReadW
0x1400abcf4  test    eax, eax
0x1400abcf6  jnz     loc_1400ABE60
0x1400abcfc  call    cs:__imp_GetLastError
0x1400abd02  mov     ebx, eax
0x1400abd04  test    eax, eax
0x1400abd06  jle     short loc_1400ABD11
0x1400abd08  movzx   ebx, ax
0x1400abd0b  or      ebx, 80070000h
0x1400abd11  test    ebx, ebx
0x1400abd13  jns     loc_1400ABE62
0x1400abd19  cmp     ebx, 80070490h
0x1400abd1f  jz      loc_1400ABF22
0x1400abd25  cmp     ebx, 80070005h
0x1400abd2b  jz      loc_1400ABF22
0x1400abd31  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abd38  lea     rax, WPP_GLOBAL_Control
0x1400abd3f  cmp     rcx, rax
0x1400abd42  jz      loc_1400ABF22
0x1400abd48  test    byte ptr [rcx+1Ch], 1
0x1400abd4c  jz      loc_1400ABF22
0x1400abd52  cmp     byte ptr [rcx+19h], 2
0x1400abd56  jb      loc_1400ABF22
0x1400abd5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abd61  mov     edx, 18h
0x1400abd66  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abd6d  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400abd74  mov     r9d, eax
0x1400abd77  mov     dword ptr [rsp+68h+var_48], ebx
0x1400abd7b  mov     rcx, [rcx+10h]
0x1400abd7f  call    WPP_SF_Dd
0x1400abd84  jmp     loc_1400ABF22
0x1400abd89  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abd90  lea     rax, WPP_GLOBAL_Control
0x1400abd97  cmp     rcx, rax
0x1400abd9a  jz      short loc_1400ABDCC
0x1400abd9c  test    byte ptr [rcx+1Ch], 1
0x1400abda0  jz      short loc_1400ABDCC
0x1400abda2  cmp     byte ptr [rcx+19h], 2
0x1400abda6  jb      short loc_1400ABDCC
0x1400abda8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abdad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abdb4  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400abdbb  mov     edx, 19h
0x1400abdc0  mov     r9d, eax
0x1400abdc3  mov     rcx, [rcx+10h]
0x1400abdc7  call    WPP_SF_d
0x1400abdcc  mov     ebx, 80070490h
0x1400abdd1  jmp     loc_1400ABF22
0x1400abdd6  lea     r9, [rsp+68h+Credential]; Credential
0x1400abddb  xor     r8d, r8d; Flags
0x1400abdde  mov     edx, eax; Type
0x1400abde0  mov     rcx, rbx; TargetName
0x1400abde3  call    cs:__imp_CredReadW
0x1400abde9  test    eax, eax
0x1400abdeb  jnz     short loc_1400ABE60
0x1400abded  call    cs:__imp_GetLastError
0x1400abdf3  mov     ebx, eax
0x1400abdf5  test    eax, eax
0x1400abdf7  jle     short loc_1400ABE02
0x1400abdf9  movzx   ebx, ax
0x1400abdfc  or      ebx, 80070000h
0x1400abe02  cmp     ebx, 80070057h
0x1400abe08  jz      short loc_1400ABDCC
0x1400abe0a  test    ebx, ebx
0x1400abe0c  jns     short loc_1400ABE62
0x1400abe0e  cmp     ebx, 80070490h
0x1400abe14  jz      loc_1400ABF22
0x1400abe1a  cmp     ebx, 80070005h
0x1400abe20  jz      loc_1400ABF22
0x1400abe26  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abe2d  lea     rax, WPP_GLOBAL_Control
0x1400abe34  cmp     rcx, rax
0x1400abe37  jz      loc_1400ABF22
0x1400abe3d  test    byte ptr [rcx+1Ch], 1
0x1400abe41  jz      loc_1400ABF22
0x1400abe47  cmp     byte ptr [rcx+19h], 2
0x1400abe4b  jb      loc_1400ABF22
0x1400abe51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abe56  mov     edx, 1Ah
0x1400abe5b  jmp     loc_1400ABD66
0x1400abe60  xor     ebx, ebx
0x1400abe62  test    rsi, rsi
0x1400abe65  jz      loc_1400ABF22
0x1400abe6b  mov     rax, [rsp+68h+Credential]
0x1400abe70  mov     rcx, rsi; unsigned __int16 *
0x1400abe73  mov     edx, [rsp+68h+arg_20]; unsigned __int64
0x1400abe7a  mov     r8, [rax+48h]; unsigned __int16 *
0x1400abe7e  test    r8, r8
0x1400abe81  jz      short loc_1400ABEBD
0x1400abe83  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400abe88  mov     ebx, eax
0x1400abe8a  test    eax, eax
0x1400abe8c  jns     loc_1400ABF22
0x1400abe92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abe99  lea     rax, WPP_GLOBAL_Control
0x1400abea0  cmp     rcx, rax
0x1400abea3  jz      short loc_1400ABF22
0x1400abea5  test    byte ptr [rcx+1Ch], 8
0x1400abea9  jz      short loc_1400ABF22
0x1400abeab  cmp     byte ptr [rcx+19h], 2
0x1400abeaf  jb      short loc_1400ABF22
0x1400abeb1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abeb6  mov     edx, 1Bh
0x1400abebb  jmp     short loc_1400ABEF8
0x1400abebd  lea     r8, pszPassword; unsigned __int16 *
0x1400abec4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400abec9  mov     ebx, eax
0x1400abecb  test    eax, eax
0x1400abecd  jns     short loc_1400ABF22
0x1400abecf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abed6  lea     rax, WPP_GLOBAL_Control
0x1400abedd  cmp     rcx, rax
0x1400abee0  jz      short loc_1400ABF22
0x1400abee2  test    byte ptr [rcx+1Ch], 8
0x1400abee6  jz      short loc_1400ABF22
0x1400abee8  cmp     byte ptr [rcx+19h], 2
0x1400abeec  jb      short loc_1400ABF22
0x1400abeee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400abef3  mov     edx, 1Ch
0x1400abef8  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x1400abeff  mov     [rsp+68h+var_40], ebx
0x1400abf03  mov     [rsp+68h+var_48], rcx
0x1400abf08  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400abf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abf16  mov     r9d, eax
0x1400abf19  mov     rcx, [rcx+10h]
0x1400abf1d  call    WPP_SF_DsD
0x1400abf22  mov     rcx, [rsp+68h+Credential]; Buffer
0x1400abf27  test    rcx, rcx
0x1400abf2a  jz      short loc_1400ABF32
0x1400abf2c  call    cs:__imp_CredFree
0x1400abf32  test    rdi, rdi
0x1400abf35  jz      short loc_1400ABF40
0x1400abf37  mov     rcx, rdi; hMem
0x1400abf3a  call    cs:__imp_LocalFree
0x1400abf40  mov     eax, ebx
0x1400abf42  add     rsp, 48h
0x1400abf46  pop     rdi
0x1400abf47  pop     rsi
0x1400abf48  pop     rbp
0x1400abf49  pop     rbx
0x1400abf4a  retn
```
