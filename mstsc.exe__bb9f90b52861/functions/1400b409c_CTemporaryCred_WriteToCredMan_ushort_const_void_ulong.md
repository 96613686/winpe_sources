# CTemporaryCred::WriteToCredMan(ushort const *,void *,ulong)

- ea: `0x1400b409c`
- end: `0x1400b440a`
- name: `?WriteToCredMan@CTemporaryCred@@QEAAJPEBGPEAXK@Z`
- size: `878`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400af2f8`

## callees

- `0x140003b08`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b409c`
- `0x1400b4410`
- `0x1400b44b8`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x1400b42d1`
- `SHCORE!SHStrDupW` at `0x1400b42d1`
- `KERNEL32!LocalFree` at `0x1400b43d1`
- `KERNEL32!LocalFree` at `0x1400b43d1`
- `KERNEL32!GetLastError` at `0x1400b4363`
- `KERNEL32!GetLastError` at `0x1400b4363`
- `ADVAPI32!CredWriteW` at `0x1400b4359`
- `ADVAPI32!CredWriteW` at `0x1400b4359`

## string_xrefs

- `0x1400b42c2`: `s_DeleteCredHelper failed`

## pseudocode

```c
__int64 __fastcall CTemporaryCred::WriteToCredMan(LPWSTR *ppwsz, unsigned __int16 *a2, void *a3, unsigned int a4)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int LastError; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  unsigned int v15; // eax
  unsigned __int16 *v17; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-11h] BYREF
  struct _CREDENTIALW Credential; // [rsp+40h] [rbp-9h] BYREF
  void *Block; // [rsp+B0h] [rbp+67h] BYREF

  Block = 0;
  v17 = 0;
  v18 = 0;
  memset_0(&Credential, 0, sizeof(Credential));
  if ( *ppwsz )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_7a786f151b5038a913c484dfbc61b568_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147023649);
    }
    LastError = -2147023649;
    goto LABEL_49;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 14;
LABEL_12:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      WPP_7a786f151b5038a913c484dfbc61b568_Traceguids,
      v10,
      -2147024809);
LABEL_13:
    LastError = -2147024809;
    goto LABEL_49;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 15;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 16;
    goto LABEL_12;
  }
  LastError = CTemporaryCred::s_UnpackAuthBlob(a3, a4, (unsigned __int16 **)&Block, &v17, &v18);
  if ( LastError >= 0 )
  {
    LastError = CTemporaryCred::s_DeleteCredHelper(a2);
    if ( LastError >= 0 )
    {
      LastError = SHStrDupW(a2, ppwsz);
      if ( LastError >= 0 )
      {
        Credential.Type = 2;
        Credential.Comment = (LPWSTR)&pszPassword;
        Credential.UserName = (LPWSTR)Block;
        Credential.CredentialBlob = (LPBYTE)v17;
        Credential.TargetName = a2;
        Credential.CredentialBlobSize = 2 * v18;
        Credential.Persist = 1;
        if ( CredWriteW(&Credential, 0) )
          goto LABEL_51;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_7a786f151b5038a913c484dfbc61b568_Traceguids,
            v15,
            LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 19;
        v14 = "SHStrDup failed";
        goto LABEL_29;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 18;
      v14 = "s_DeleteCredHelper failed";
      goto LABEL_29;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 17;
    v14 = "s_UnpackAuthBlob failed";
LABEL_29:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)WPP_7a786f151b5038a913c484dfbc61b568_Traceguids,
      v12,
      (__int64)v14,
      LastError);
  }
LABEL_49:
  if ( *ppwsz )
  {
    LocalFree(*ppwsz);
    *ppwsz = 0;
  }
LABEL_51:
  operator delete(Block);
  operator delete(v17);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400b409c  mov     [rsp-8+arg_8], rbx
0x1400b40a1  mov     [rsp-8+arg_10], rsi
0x1400b40a6  push    rbp
0x1400b40a7  push    rdi
0x1400b40a8  push    r14
0x1400b40aa  lea     rbp, [rsp-47h]
0x1400b40af  sub     rsp, 90h
0x1400b40b6  mov     rdi, rdx
0x1400b40b9  mov     [rbp+57h+Block], 0
0x1400b40c1  xor     edx, edx; Val
0x1400b40c3  mov     [rbp+57h+var_70], 0
0x1400b40cb  mov     rsi, r8
0x1400b40ce  mov     [rbp+57h+var_68], 0
0x1400b40d6  mov     r14, rcx
0x1400b40d9  mov     ebx, r9d
0x1400b40dc  lea     rcx, [rbp+57h+Credential]; void *
0x1400b40e0  lea     r8d, [rdx+50h]; Size
0x1400b40e4  call    memset_0
0x1400b40e9  cmp     qword ptr [r14], 0
0x1400b40ed  jz      short loc_1400B4144
0x1400b40ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b40f6  lea     rax, WPP_GLOBAL_Control
0x1400b40fd  cmp     rcx, rax
0x1400b4100  jz      short loc_1400B413A
0x1400b4102  test    byte ptr [rcx+1Ch], 8
0x1400b4106  jz      short loc_1400B413A
0x1400b4108  cmp     byte ptr [rcx+19h], 2
0x1400b410c  jb      short loc_1400B413A
0x1400b410e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b4113  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b411a  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b4121  mov     edx, 0Dh
0x1400b4126  mov     dword ptr [rsp+0A0h+var_80], 800704DFh
0x1400b412e  mov     r9d, eax
0x1400b4131  mov     rcx, [rcx+10h]
0x1400b4135  call    WPP_SF_Dd
0x1400b413a  mov     ebx, 800704DFh
0x1400b413f  jmp     loc_1400B43C9
0x1400b4144  test    rdi, rdi
0x1400b4147  jnz     short loc_1400B419C
0x1400b4149  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4150  lea     rax, WPP_GLOBAL_Control
0x1400b4157  cmp     rcx, rax
0x1400b415a  jz      short loc_1400B4192
0x1400b415c  test    byte ptr [rcx+1Ch], 8
0x1400b4160  jz      short loc_1400B4192
0x1400b4162  cmp     byte ptr [rcx+19h], 2
0x1400b4166  jb      short loc_1400B4192
0x1400b4168  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b416d  lea     edx, [rdi+0Eh]
0x1400b4170  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4177  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b417e  mov     r9d, eax
0x1400b4181  mov     dword ptr [rsp+0A0h+var_80], 80070057h
0x1400b4189  mov     rcx, [rcx+10h]
0x1400b418d  call    WPP_SF_Dd
0x1400b4192  mov     ebx, 80070057h
0x1400b4197  jmp     loc_1400B43C9
0x1400b419c  test    rsi, rsi
0x1400b419f  jnz     short loc_1400B41CA
0x1400b41a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b41a8  lea     rax, WPP_GLOBAL_Control
0x1400b41af  cmp     rcx, rax
0x1400b41b2  jz      short loc_1400B4192
0x1400b41b4  test    byte ptr [rcx+1Ch], 8
0x1400b41b8  jz      short loc_1400B4192
0x1400b41ba  cmp     byte ptr [rcx+19h], 2
0x1400b41be  jb      short loc_1400B4192
0x1400b41c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b41c5  lea     edx, [rsi+0Fh]
0x1400b41c8  jmp     short loc_1400B4170
0x1400b41ca  test    ebx, ebx
0x1400b41cc  jnz     short loc_1400B41FA
0x1400b41ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b41d5  lea     rax, WPP_GLOBAL_Control
0x1400b41dc  cmp     rcx, rax
0x1400b41df  jz      short loc_1400B4192
0x1400b41e1  test    byte ptr [rcx+1Ch], 8
0x1400b41e5  jz      short loc_1400B4192
0x1400b41e7  cmp     byte ptr [rcx+19h], 2
0x1400b41eb  jb      short loc_1400B4192
0x1400b41ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b41f2  lea     edx, [rbx+10h]
0x1400b41f5  jmp     loc_1400B4170
0x1400b41fa  lea     rax, [rbp+57h+var_68]
0x1400b41fe  mov     edx, ebx; unsigned int
0x1400b4200  lea     r9, [rbp+57h+var_70]; unsigned __int16 **
0x1400b4204  mov     [rsp+0A0h+var_80], rax; unsigned __int64 *
0x1400b4209  lea     r8, [rbp+57h+Block]; unsigned __int16 **
0x1400b420d  mov     rcx, rsi; void *
0x1400b4210  call    ?s_UnpackAuthBlob@CTemporaryCred@@KAJPEAXKPEAPEAG1PEA_K@Z; CTemporaryCred::s_UnpackAuthBlob(void *,ulong,ushort * *,ushort * *,unsigned __int64 *)
0x1400b4215  mov     ebx, eax
0x1400b4217  test    eax, eax
0x1400b4219  jns     short loc_1400B427F
0x1400b421b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4222  lea     rax, WPP_GLOBAL_Control
0x1400b4229  cmp     rcx, rax
0x1400b422c  jz      loc_1400B43C9
0x1400b4232  test    byte ptr [rcx+1Ch], 8
0x1400b4236  jz      loc_1400B43C9
0x1400b423c  cmp     byte ptr [rcx+19h], 2
0x1400b4240  jb      loc_1400B43C9
0x1400b4246  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b424b  mov     edx, 11h
0x1400b4250  lea     rcx, aSUnpackauthblo; "s_UnpackAuthBlob failed"
0x1400b4257  mov     [rsp+0A0h+var_78], ebx
0x1400b425b  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b4262  mov     [rsp+0A0h+var_80], rcx
0x1400b4267  mov     r9d, eax
0x1400b426a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4271  mov     rcx, [rcx+10h]
0x1400b4275  call    WPP_SF_DsD
0x1400b427a  jmp     loc_1400B43C9
0x1400b427f  mov     rcx, rdi; unsigned __int16 *
0x1400b4282  call    ?s_DeleteCredHelper@CTemporaryCred@@KAJPEBG@Z; CTemporaryCred::s_DeleteCredHelper(ushort const *)
0x1400b4287  mov     ebx, eax
0x1400b4289  test    eax, eax
0x1400b428b  jns     short loc_1400B42CB
0x1400b428d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4294  lea     rax, WPP_GLOBAL_Control
0x1400b429b  cmp     rcx, rax
0x1400b429e  jz      loc_1400B43C9
0x1400b42a4  test    byte ptr [rcx+1Ch], 8
0x1400b42a8  jz      loc_1400B43C9
0x1400b42ae  cmp     byte ptr [rcx+19h], 2
0x1400b42b2  jb      loc_1400B43C9
0x1400b42b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b42bd  mov     edx, 12h
0x1400b42c2  lea     rcx, aSDeletecredhel; "s_DeleteCredHelper failed"
0x1400b42c9  jmp     short loc_1400B4257
0x1400b42cb  mov     rdx, r14; ppwsz
0x1400b42ce  mov     rcx, rdi; psz
0x1400b42d1  call    cs:__imp_SHStrDupW
0x1400b42d7  mov     ebx, eax
0x1400b42d9  test    eax, eax
0x1400b42db  jns     short loc_1400B431E
0x1400b42dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b42e4  lea     rax, WPP_GLOBAL_Control
0x1400b42eb  cmp     rcx, rax
0x1400b42ee  jz      loc_1400B43C9
0x1400b42f4  test    byte ptr [rcx+1Ch], 8
0x1400b42f8  jz      loc_1400B43C9
0x1400b42fe  cmp     byte ptr [rcx+19h], 2
0x1400b4302  jb      loc_1400B43C9
0x1400b4308  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b430d  mov     edx, 13h
0x1400b4312  lea     rcx, aShstrdupFailed; "SHStrDup failed"
0x1400b4319  jmp     loc_1400B4257
0x1400b431e  lea     rax, pszPassword
0x1400b4325  mov     [rbp+57h+Credential.Type], 2
0x1400b432c  mov     [rbp+57h+Credential.Comment], rax
0x1400b4330  lea     rcx, [rbp+57h+Credential]; Credential
0x1400b4334  mov     rax, [rbp+57h+Block]
0x1400b4338  xor     edx, edx; Flags
0x1400b433a  mov     [rbp+57h+Credential.UserName], rax
0x1400b433e  mov     rax, [rbp+57h+var_70]
0x1400b4342  mov     [rbp+57h+Credential.CredentialBlob], rax
0x1400b4346  mov     eax, dword ptr [rbp+57h+var_68]
0x1400b4349  add     eax, eax
0x1400b434b  mov     [rbp+57h+Credential.TargetName], rdi
0x1400b434f  mov     [rbp+57h+Credential.CredentialBlobSize], eax
0x1400b4352  mov     [rbp+57h+Credential.Persist], 1
0x1400b4359  call    cs:__imp_CredWriteW
0x1400b435f  test    eax, eax
0x1400b4361  jnz     short loc_1400B43DE
0x1400b4363  call    cs:__imp_GetLastError
0x1400b4369  mov     ebx, eax
0x1400b436b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4372  lea     rax, WPP_GLOBAL_Control
0x1400b4379  cmp     rcx, rax
0x1400b437c  jz      short loc_1400B43B2
0x1400b437e  test    byte ptr [rcx+1Ch], 8
0x1400b4382  jz      short loc_1400B43B2
0x1400b4384  cmp     byte ptr [rcx+19h], 2
0x1400b4388  jb      short loc_1400B43B2
0x1400b438a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b438f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4396  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b439d  mov     edx, 14h
0x1400b43a2  mov     dword ptr [rsp+0A0h+var_80], ebx
0x1400b43a6  mov     r9d, eax
0x1400b43a9  mov     rcx, [rcx+10h]
0x1400b43ad  call    WPP_SF_Dd
0x1400b43b2  test    ebx, ebx
0x1400b43b4  jle     short loc_1400B43BF
0x1400b43b6  movzx   ebx, bx
0x1400b43b9  or      ebx, 80070000h
0x1400b43bf  test    ebx, ebx
0x1400b43c1  mov     eax, 80004005h
0x1400b43c6  cmovns  ebx, eax
0x1400b43c9  mov     rcx, [r14]; hMem
0x1400b43cc  test    rcx, rcx
0x1400b43cf  jz      short loc_1400B43DE
0x1400b43d1  call    cs:__imp_LocalFree
0x1400b43d7  mov     qword ptr [r14], 0
0x1400b43de  mov     rcx, [rbp+57h+Block]; Block
0x1400b43e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b43e7  mov     rcx, [rbp+57h+var_70]; Block
0x1400b43eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b43f0  lea     r11, [rsp+0A0h+var_10]
0x1400b43f8  mov     eax, ebx
0x1400b43fa  mov     rbx, [r11+28h]
0x1400b43fe  mov     rsi, [r11+30h]
0x1400b4402  mov     rsp, r11
0x1400b4405  pop     r14
0x1400b4407  pop     rdi
0x1400b4408  pop     rbp
0x1400b4409  retn
```
