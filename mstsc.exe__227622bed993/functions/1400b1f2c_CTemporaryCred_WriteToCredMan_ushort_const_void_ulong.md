# CTemporaryCred::WriteToCredMan(ushort const *,void *,ulong)

- ea: `0x1400b1f2c`
- end: `0x1400b229a`
- name: `?WriteToCredMan@CTemporaryCred@@QEAAJPEBGPEAXK@Z`
- size: `878`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400ad188`

## callees

- `0x140003b08`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b1f2c`
- `0x1400b22a0`
- `0x1400b2348`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x1400b2161`
- `SHCORE!SHStrDupW` at `0x1400b2161`
- `KERNEL32!LocalFree` at `0x1400b2261`
- `KERNEL32!LocalFree` at `0x1400b2261`
- `KERNEL32!GetLastError` at `0x1400b21f3`
- `KERNEL32!GetLastError` at `0x1400b21f3`
- `ADVAPI32!CredWriteW` at `0x1400b21e9`
- `ADVAPI32!CredWriteW` at `0x1400b21e9`

## string_xrefs

- `0x1400b2152`: `s_DeleteCredHelper failed`

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
0x1400b1f2c  mov     [rsp-8+arg_8], rbx
0x1400b1f31  mov     [rsp-8+arg_10], rsi
0x1400b1f36  push    rbp
0x1400b1f37  push    rdi
0x1400b1f38  push    r14
0x1400b1f3a  lea     rbp, [rsp-47h]
0x1400b1f3f  sub     rsp, 90h
0x1400b1f46  mov     rdi, rdx
0x1400b1f49  mov     [rbp+57h+Block], 0
0x1400b1f51  xor     edx, edx; Val
0x1400b1f53  mov     [rbp+57h+var_70], 0
0x1400b1f5b  mov     rsi, r8
0x1400b1f5e  mov     [rbp+57h+var_68], 0
0x1400b1f66  mov     r14, rcx
0x1400b1f69  mov     ebx, r9d
0x1400b1f6c  lea     rcx, [rbp+57h+Credential]; void *
0x1400b1f70  lea     r8d, [rdx+50h]; Size
0x1400b1f74  call    memset_0
0x1400b1f79  cmp     qword ptr [r14], 0
0x1400b1f7d  jz      short loc_1400B1FD4
0x1400b1f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1f86  lea     rax, WPP_GLOBAL_Control
0x1400b1f8d  cmp     rcx, rax
0x1400b1f90  jz      short loc_1400B1FCA
0x1400b1f92  test    byte ptr [rcx+1Ch], 8
0x1400b1f96  jz      short loc_1400B1FCA
0x1400b1f98  cmp     byte ptr [rcx+19h], 2
0x1400b1f9c  jb      short loc_1400B1FCA
0x1400b1f9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1faa  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b1fb1  mov     edx, 0Dh
0x1400b1fb6  mov     dword ptr [rsp+0A0h+var_80], 800704DFh
0x1400b1fbe  mov     r9d, eax
0x1400b1fc1  mov     rcx, [rcx+10h]
0x1400b1fc5  call    WPP_SF_Dd
0x1400b1fca  mov     ebx, 800704DFh
0x1400b1fcf  jmp     loc_1400B2259
0x1400b1fd4  test    rdi, rdi
0x1400b1fd7  jnz     short loc_1400B202C
0x1400b1fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1fe0  lea     rax, WPP_GLOBAL_Control
0x1400b1fe7  cmp     rcx, rax
0x1400b1fea  jz      short loc_1400B2022
0x1400b1fec  test    byte ptr [rcx+1Ch], 8
0x1400b1ff0  jz      short loc_1400B2022
0x1400b1ff2  cmp     byte ptr [rcx+19h], 2
0x1400b1ff6  jb      short loc_1400B2022
0x1400b1ff8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1ffd  lea     edx, [rdi+0Eh]
0x1400b2000  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2007  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b200e  mov     r9d, eax
0x1400b2011  mov     dword ptr [rsp+0A0h+var_80], 80070057h
0x1400b2019  mov     rcx, [rcx+10h]
0x1400b201d  call    WPP_SF_Dd
0x1400b2022  mov     ebx, 80070057h
0x1400b2027  jmp     loc_1400B2259
0x1400b202c  test    rsi, rsi
0x1400b202f  jnz     short loc_1400B205A
0x1400b2031  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2038  lea     rax, WPP_GLOBAL_Control
0x1400b203f  cmp     rcx, rax
0x1400b2042  jz      short loc_1400B2022
0x1400b2044  test    byte ptr [rcx+1Ch], 8
0x1400b2048  jz      short loc_1400B2022
0x1400b204a  cmp     byte ptr [rcx+19h], 2
0x1400b204e  jb      short loc_1400B2022
0x1400b2050  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2055  lea     edx, [rsi+0Fh]
0x1400b2058  jmp     short loc_1400B2000
0x1400b205a  test    ebx, ebx
0x1400b205c  jnz     short loc_1400B208A
0x1400b205e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2065  lea     rax, WPP_GLOBAL_Control
0x1400b206c  cmp     rcx, rax
0x1400b206f  jz      short loc_1400B2022
0x1400b2071  test    byte ptr [rcx+1Ch], 8
0x1400b2075  jz      short loc_1400B2022
0x1400b2077  cmp     byte ptr [rcx+19h], 2
0x1400b207b  jb      short loc_1400B2022
0x1400b207d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2082  lea     edx, [rbx+10h]
0x1400b2085  jmp     loc_1400B2000
0x1400b208a  lea     rax, [rbp+57h+var_68]
0x1400b208e  mov     edx, ebx; unsigned int
0x1400b2090  lea     r9, [rbp+57h+var_70]; unsigned __int16 **
0x1400b2094  mov     [rsp+0A0h+var_80], rax; unsigned __int64 *
0x1400b2099  lea     r8, [rbp+57h+Block]; unsigned __int16 **
0x1400b209d  mov     rcx, rsi; void *
0x1400b20a0  call    ?s_UnpackAuthBlob@CTemporaryCred@@KAJPEAXKPEAPEAG1PEA_K@Z; CTemporaryCred::s_UnpackAuthBlob(void *,ulong,ushort * *,ushort * *,unsigned __int64 *)
0x1400b20a5  mov     ebx, eax
0x1400b20a7  test    eax, eax
0x1400b20a9  jns     short loc_1400B210F
0x1400b20ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b20b2  lea     rax, WPP_GLOBAL_Control
0x1400b20b9  cmp     rcx, rax
0x1400b20bc  jz      loc_1400B2259
0x1400b20c2  test    byte ptr [rcx+1Ch], 8
0x1400b20c6  jz      loc_1400B2259
0x1400b20cc  cmp     byte ptr [rcx+19h], 2
0x1400b20d0  jb      loc_1400B2259
0x1400b20d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b20db  mov     edx, 11h
0x1400b20e0  lea     rcx, aSUnpackauthblo; "s_UnpackAuthBlob failed"
0x1400b20e7  mov     [rsp+0A0h+var_78], ebx
0x1400b20eb  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b20f2  mov     [rsp+0A0h+var_80], rcx
0x1400b20f7  mov     r9d, eax
0x1400b20fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2101  mov     rcx, [rcx+10h]
0x1400b2105  call    WPP_SF_DsD
0x1400b210a  jmp     loc_1400B2259
0x1400b210f  mov     rcx, rdi; unsigned __int16 *
0x1400b2112  call    ?s_DeleteCredHelper@CTemporaryCred@@KAJPEBG@Z; CTemporaryCred::s_DeleteCredHelper(ushort const *)
0x1400b2117  mov     ebx, eax
0x1400b2119  test    eax, eax
0x1400b211b  jns     short loc_1400B215B
0x1400b211d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2124  lea     rax, WPP_GLOBAL_Control
0x1400b212b  cmp     rcx, rax
0x1400b212e  jz      loc_1400B2259
0x1400b2134  test    byte ptr [rcx+1Ch], 8
0x1400b2138  jz      loc_1400B2259
0x1400b213e  cmp     byte ptr [rcx+19h], 2
0x1400b2142  jb      loc_1400B2259
0x1400b2148  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b214d  mov     edx, 12h
0x1400b2152  lea     rcx, aSDeletecredhel; "s_DeleteCredHelper failed"
0x1400b2159  jmp     short loc_1400B20E7
0x1400b215b  mov     rdx, r14; ppwsz
0x1400b215e  mov     rcx, rdi; psz
0x1400b2161  call    cs:__imp_SHStrDupW
0x1400b2167  mov     ebx, eax
0x1400b2169  test    eax, eax
0x1400b216b  jns     short loc_1400B21AE
0x1400b216d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2174  lea     rax, WPP_GLOBAL_Control
0x1400b217b  cmp     rcx, rax
0x1400b217e  jz      loc_1400B2259
0x1400b2184  test    byte ptr [rcx+1Ch], 8
0x1400b2188  jz      loc_1400B2259
0x1400b218e  cmp     byte ptr [rcx+19h], 2
0x1400b2192  jb      loc_1400B2259
0x1400b2198  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b219d  mov     edx, 13h
0x1400b21a2  lea     rcx, aShstrdupFailed; "SHStrDup failed"
0x1400b21a9  jmp     loc_1400B20E7
0x1400b21ae  lea     rax, pszPassword
0x1400b21b5  mov     [rbp+57h+Credential.Type], 2
0x1400b21bc  mov     [rbp+57h+Credential.Comment], rax
0x1400b21c0  lea     rcx, [rbp+57h+Credential]; Credential
0x1400b21c4  mov     rax, [rbp+57h+Block]
0x1400b21c8  xor     edx, edx; Flags
0x1400b21ca  mov     [rbp+57h+Credential.UserName], rax
0x1400b21ce  mov     rax, [rbp+57h+var_70]
0x1400b21d2  mov     [rbp+57h+Credential.CredentialBlob], rax
0x1400b21d6  mov     eax, dword ptr [rbp+57h+var_68]
0x1400b21d9  add     eax, eax
0x1400b21db  mov     [rbp+57h+Credential.TargetName], rdi
0x1400b21df  mov     [rbp+57h+Credential.CredentialBlobSize], eax
0x1400b21e2  mov     [rbp+57h+Credential.Persist], 1
0x1400b21e9  call    cs:__imp_CredWriteW
0x1400b21ef  test    eax, eax
0x1400b21f1  jnz     short loc_1400B226E
0x1400b21f3  call    cs:__imp_GetLastError
0x1400b21f9  mov     ebx, eax
0x1400b21fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2202  lea     rax, WPP_GLOBAL_Control
0x1400b2209  cmp     rcx, rax
0x1400b220c  jz      short loc_1400B2242
0x1400b220e  test    byte ptr [rcx+1Ch], 8
0x1400b2212  jz      short loc_1400B2242
0x1400b2214  cmp     byte ptr [rcx+19h], 2
0x1400b2218  jb      short loc_1400B2242
0x1400b221a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b221f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2226  lea     r8, WPP_7a786f151b5038a913c484dfbc61b568_Traceguids
0x1400b222d  mov     edx, 14h
0x1400b2232  mov     dword ptr [rsp+0A0h+var_80], ebx
0x1400b2236  mov     r9d, eax
0x1400b2239  mov     rcx, [rcx+10h]
0x1400b223d  call    WPP_SF_Dd
0x1400b2242  test    ebx, ebx
0x1400b2244  jle     short loc_1400B224F
0x1400b2246  movzx   ebx, bx
0x1400b2249  or      ebx, 80070000h
0x1400b224f  test    ebx, ebx
0x1400b2251  mov     eax, 80004005h
0x1400b2256  cmovns  ebx, eax
0x1400b2259  mov     rcx, [r14]; hMem
0x1400b225c  test    rcx, rcx
0x1400b225f  jz      short loc_1400B226E
0x1400b2261  call    cs:__imp_LocalFree
0x1400b2267  mov     qword ptr [r14], 0
0x1400b226e  mov     rcx, [rbp+57h+Block]; Block
0x1400b2272  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b2277  mov     rcx, [rbp+57h+var_70]; Block
0x1400b227b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b2280  lea     r11, [rsp+0A0h+var_10]
0x1400b2288  mov     eax, ebx
0x1400b228a  mov     rbx, [r11+28h]
0x1400b228e  mov     rsi, [r11+30h]
0x1400b2292  mov     rsp, r11
0x1400b2295  pop     r14
0x1400b2297  pop     rdi
0x1400b2298  pop     rbp
0x1400b2299  retn
```
