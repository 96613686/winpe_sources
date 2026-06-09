# FTP_SESSION::ExpandMessage(char const *,STRA *,STRA *)

- ea: `0x18003393c`
- end: `0x180033c69`
- name: `?ExpandMessage@FTP_SESSION@@QEAAJPEBDPEAVSTRA@@1@Z`
- size: `813`
- prototype: `__int64 __fastcall(FTP_SESSION *this, const char *, struct STRA *, struct STRA *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800365cc`
- `0x180036780`
- `0x180039e28`
- `0x18003b6a0`

## callees

- `0x18002be4c`
- `0x18003393c`
- `0x180036b78`
- `0x18004701b`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180033a01`
- `msvcrt!_strnicmp` at `0x180033acd`
- `msvcrt!_strnicmp` at `0x180033b6f`
- `msvcrt!_strnicmp` at `0x180033b97`
- `msvcrt!_strnicmp` at `0x180033bb7`
- `msvcrt!_strnicmp` at `0x180033bdd`
- `msvcrt!_strnicmp` at `0x180033a01`
- `msvcrt!_strnicmp` at `0x180033acd`
- `msvcrt!_strnicmp` at `0x180033b6f`
- `msvcrt!_strnicmp` at `0x180033b97`
- `msvcrt!_strnicmp` at `0x180033bb7`
- `msvcrt!_strnicmp` at `0x180033bdd`
- `msvcrt!strchr` at `0x180033977`
- `msvcrt!strchr` at `0x180033992`
- `msvcrt!strchr` at `0x180033977`
- `msvcrt!strchr` at `0x180033992`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180033a1b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180033ae7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180033a1b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180033ae7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180033b57`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180033c2b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180033b57`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180033c2b`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180033b15`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180033b15`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180033b28`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180033b28`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800339b0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180033b43`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800339b0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180033b43`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033a9e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033c11`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033c3f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033a9e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033c11`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180033c3f`

## string_xrefs

- `0x1800339f7`: `%AvailableBytesInHomeDirectory%`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SESSION::ExpandMessage(FTP_SESSION *this, const char *a2, struct STRA *a3, struct STRA *a4)
{
  char *v8; // rax
  const char *v9; // rdi
  char *v10; // r12
  int v11; // ebx
  char *v12; // rdx
  size_t v13; // rsi
  const char *v14; // rdx
  char *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rdx
  int v19; // eax
  __int64 v20; // r9
  unsigned __int64 v22; // [rsp+20h] [rbp-79h] BYREF
  char v23[32]; // [rsp+28h] [rbp-71h] BYREF
  const char *v24; // [rsp+48h] [rbp-51h]
  unsigned int v25; // [rsp+58h] [rbp-41h]
  char v26[32]; // [rsp+60h] [rbp-39h] BYREF
  const char *v27; // [rsp+80h] [rbp-19h]

  while ( 1 )
  {
    v8 = strchr(a2, 37);
    v9 = v8;
    if ( !v8 )
      break;
    v10 = strchr(v8 + 1, 37);
    if ( !v10 )
      break;
    v11 = STRA::Append(a3, a2, (_DWORD)v9 - (_DWORD)a2);
    if ( v11 < 0 )
      return (unsigned int)v11;
    if ( !strncmp_0(v9, "%%", (unsigned int)((_DWORD)v10 - (_DWORD)v9 + 1)) )
    {
      v12 = "%";
      goto LABEL_42;
    }
    v13 = (unsigned int)((_DWORD)v10 - (_DWORD)v9 + 1);
    if ( (_DWORD)v10 - (_DWORD)v9 == 30 )
    {
      if ( _strnicmp(v9, "%AvailableBytesInHomeDirectory%", (unsigned int)v13) )
        goto LABEL_43;
      STRA::STRA((STRA *)v26, v23, (_DWORD)v10 - (_DWORD)v9 + 2);
      v22 = 0;
      if ( !a4 || !*((_DWORD *)a4 + 12) )
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 132) + 40LL))(*((_QWORD *)this + 132)) )
        {
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *))(**((_QWORD **)this + 132) + 112LL))(
                  *((_QWORD *)this + 132),
                  *((_QWORD *)this + 606),
                  &v22);
          if ( v11 < 0 || (v11 = FormatFileSizeA(v22, (struct STRA *)v26), v11 < 0) )
          {
LABEL_44:
            v15 = v26;
LABEL_45:
            STRA::~STRA((STRA *)v15);
            return (unsigned int)v11;
          }
          v14 = v27;
LABEL_16:
          v11 = STRA::Append(a3, v14);
          if ( v11 < 0 )
            goto LABEL_44;
LABEL_17:
          v15 = v26;
LABEL_29:
          STRA::~STRA((STRA *)v15);
          goto LABEL_43;
        }
        if ( !a4 )
          goto LABEL_17;
      }
      v14 = (const char *)*((_QWORD *)a4 + 4);
      goto LABEL_16;
    }
    if ( (_DWORD)v10 - (_DWORD)v9 == 9 )
    {
      if ( !_strnicmp(v9, "%SiteName%", v13) )
      {
        STRA::STRA((STRA *)v23, v26, (_DWORD)v10 - (_DWORD)v9 + 55);
        v16 = *((_QWORD *)this + 12);
        v17 = *(_QWORD *)(v16 + 8);
        v18 = (const unsigned __int16 *)&dword_18004D454;
        if ( *((_DWORD *)this + 1197) == 65001 )
        {
          if ( v17 )
            v18 = *(const unsigned __int16 **)(v16 + 8);
          v19 = STRA::CopyWToUTF8Unescaped((STRA *)v23, v18);
        }
        else
        {
          if ( v17 )
            v18 = *(const unsigned __int16 **)(v16 + 8);
          v19 = STRA::CopyW((STRA *)v23, v18);
        }
        v11 = v19;
        if ( v19 < 0 )
        {
          v15 = v23;
          goto LABEL_45;
        }
        v11 = STRA::Append(a3, v24, v25);
        v15 = v23;
        if ( v11 < 0 )
          goto LABEL_45;
        goto LABEL_29;
      }
      if ( !_strnicmp(v9, "%UserName%", 0xAu) )
      {
        v12 = (char *)*((_QWORD *)this + 75);
        goto LABEL_42;
      }
    }
    if ( (_DWORD)v10 - (_DWORD)v9 != 10 )
      goto LABEL_51;
    if ( !_strnicmp(v9, "%SessionId%", v13) )
    {
      v12 = (char *)*((_QWORD *)this + 38);
      goto LABEL_42;
    }
    if ( !_strnicmp(v9, "%BytesSent%", 0xBu) )
    {
      v20 = *((_QWORD *)this + 8) + *((_QWORD *)this + 10);
    }
    else
    {
LABEL_51:
      if ( (_DWORD)v10 - (_DWORD)v9 != 14 || _strnicmp(v9, "%BytesReceived%", 0xFu) )
        goto LABEL_43;
      v20 = *((_QWORD *)this + 9) + *((_QWORD *)this + 11);
    }
    v11 = StringCbPrintfA(v23, 0x1Eu, "%I64u", v20);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v12 = v23;
LABEL_42:
    v11 = STRA::Append(a3, v12);
    if ( v11 < 0 )
      return (unsigned int)v11;
LABEL_43:
    a2 = v10 + 1;
  }
  return (unsigned int)STRA::Append(a3, a2);
}

```

## disassembly

```asm
0x18003393c  push    rbp
0x18003393e  push    rbx
0x18003393f  push    rsi
0x180033940  push    rdi
0x180033941  push    r12
0x180033943  push    r13
0x180033945  push    r14
0x180033947  push    r15
0x180033949  lea     rbp, [rsp-1Fh]
0x18003394e  sub     rsp, 0B8h
0x180033955  mov     rax, cs:__security_cookie
0x18003395c  xor     rax, rsp
0x18003395f  mov     [rbp+57h+var_50], rax
0x180033963  mov     r13, r9
0x180033966  mov     r14, r8
0x180033969  mov     rbx, rdx
0x18003396c  mov     r15, rcx
0x18003396f  mov     edx, 25h ; '%'; Val
0x180033974  mov     rcx, rbx; Str
0x180033977  call    cs:__imp_strchr
0x18003397d  mov     rdi, rax
0x180033980  test    rax, rax
0x180033983  jz      loc_180033C39
0x180033989  lea     rcx, [rax+1]; Str
0x18003398d  mov     edx, 25h ; '%'; Val
0x180033992  call    cs:__imp_strchr
0x180033998  mov     r12, rax
0x18003399b  test    rax, rax
0x18003399e  jz      loc_180033C39
0x1800339a4  mov     r8d, edi
0x1800339a7  sub     r8d, ebx
0x1800339aa  mov     rdx, rbx
0x1800339ad  mov     rcx, r14
0x1800339b0  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x1800339b6  mov     ebx, eax
0x1800339b8  test    eax, eax
0x1800339ba  js      loc_180033C47
0x1800339c0  mov     ebx, r12d
0x1800339c3  sub     ebx, edi
0x1800339c5  inc     ebx
0x1800339c7  mov     r8d, ebx; MaxCount
0x1800339ca  lea     rdx, Str2; "%%"
0x1800339d1  mov     rcx, rdi; Str1
0x1800339d4  call    strncmp_0
0x1800339d9  test    eax, eax
0x1800339db  jnz     short loc_1800339E9
0x1800339dd  lea     rdx, asc_180053F24; "%"
0x1800339e4  jmp     loc_180033C0E
0x1800339e9  mov     esi, ebx
0x1800339eb  cmp     ebx, 1Fh
0x1800339ee  jnz     loc_180033AB7
0x1800339f4  mov     r8d, esi; MaxCount
0x1800339f7  lea     rdx, aAvailablebytes; "%AvailableBytesInHomeDirectory%"
0x1800339fe  mov     rcx, rdi; String1
0x180033a01  call    cs:__imp__strnicmp
0x180033a07  test    eax, eax
0x180033a09  jnz     loc_180033C1D
0x180033a0f  lea     r8d, [rbx+1]
0x180033a13  lea     rdx, [rbp+57h+var_C8]
0x180033a17  lea     rcx, [rbp+57h+var_90]
0x180033a1b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180033a21  nop
0x180033a22  mov     [rbp+57h+var_D0], 0
0x180033a2a  test    r13, r13
0x180033a2d  jz      short loc_180033A36
0x180033a2f  cmp     dword ptr [r13+30h], 0
0x180033a34  jnz     short loc_180033A97
0x180033a36  mov     rcx, [r15+420h]
0x180033a3d  mov     rax, [rcx]
0x180033a40  mov     rax, [rax+28h]
0x180033a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a49  test    eax, eax
0x180033a4b  jz      short loc_180033A92
0x180033a4d  mov     rcx, [r15+420h]
0x180033a54  mov     rax, [rcx]
0x180033a57  lea     r8, [rbp+57h+var_D0]
0x180033a5b  mov     rdx, [r15+12F0h]
0x180033a62  mov     rax, [rax+70h]
0x180033a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a6b  mov     ebx, eax
0x180033a6d  test    eax, eax
0x180033a6f  js      loc_180033C27
0x180033a75  lea     rdx, [rbp+57h+var_90]; struct STRA *
0x180033a79  mov     rcx, [rbp+57h+var_D0]; unsigned __int64
0x180033a7d  call    ?FormatFileSizeA@@YAJ_KPEAVSTRA@@@Z; FormatFileSizeA(unsigned __int64,STRA *)
0x180033a82  mov     ebx, eax
0x180033a84  test    eax, eax
0x180033a86  js      loc_180033C27
0x180033a8c  mov     rdx, [rbp+57h+var_70]
0x180033a90  jmp     short loc_180033A9B
0x180033a92  test    r13, r13
0x180033a95  jz      short loc_180033AAE
0x180033a97  mov     rdx, [r13+20h]
0x180033a9b  mov     rcx, r14
0x180033a9e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180033aa4  mov     ebx, eax
0x180033aa6  test    eax, eax
0x180033aa8  js      loc_180033C27
0x180033aae  lea     rcx, [rbp+57h+var_90]
0x180033ab2  jmp     loc_180033B57
0x180033ab7  cmp     ebx, 0Ah
0x180033aba  jnz     loc_180033B85
0x180033ac0  mov     r8, rsi; MaxCount
0x180033ac3  lea     rdx, aSitename; "%SiteName%"
0x180033aca  mov     rcx, rdi; String1
0x180033acd  call    cs:__imp__strnicmp
0x180033ad3  test    eax, eax
0x180033ad5  jnz     loc_180033B62
0x180033adb  lea     r8d, [rbx+36h]
0x180033adf  lea     rdx, [rbp+57h+var_90]
0x180033ae3  lea     rcx, [rbp+57h+var_C8]
0x180033ae7  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180033aed  nop
0x180033aee  mov     rax, [r15+60h]
0x180033af2  mov     rcx, [rax+8]
0x180033af6  lea     rdx, dword_18004D454
0x180033afd  cmp     dword ptr [r15+12B4h], 0FDE9h
0x180033b08  jnz     short loc_180033B1D
0x180033b0a  test    rcx, rcx
0x180033b0d  cmovnz  rdx, rcx
0x180033b11  lea     rcx, [rbp+57h+var_C8]
0x180033b15  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180033b1b  jmp     short loc_180033B2E
0x180033b1d  test    rcx, rcx
0x180033b20  cmovnz  rdx, rcx
0x180033b24  lea     rcx, [rbp+57h+var_C8]
0x180033b28  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180033b2e  mov     ebx, eax
0x180033b30  test    eax, eax
0x180033b32  js      loc_180033C33
0x180033b38  mov     r8d, [rbp+57h+var_98]
0x180033b3c  mov     rdx, [rbp+57h+var_A8]
0x180033b40  mov     rcx, r14
0x180033b43  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180033b49  mov     ebx, eax
0x180033b4b  lea     rcx, [rbp+57h+var_C8]
0x180033b4f  test    eax, eax
0x180033b51  js      loc_180033C2B
0x180033b57  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180033b5d  jmp     loc_180033C1D
0x180033b62  mov     r8, rsi; MaxCount
0x180033b65  lea     rdx, aUsername; "%UserName%"
0x180033b6c  mov     rcx, rdi; String1
0x180033b6f  call    cs:__imp__strnicmp
0x180033b75  test    eax, eax
0x180033b77  jnz     short loc_180033B85
0x180033b79  mov     rdx, [r15+258h]
0x180033b80  jmp     loc_180033C0E
0x180033b85  cmp     ebx, 0Bh
0x180033b88  jnz     short loc_180033BCB
0x180033b8a  mov     r8, rsi; MaxCount
0x180033b8d  lea     rdx, aSessionid; "%SessionId%"
0x180033b94  mov     rcx, rdi; String1
0x180033b97  call    cs:__imp__strnicmp
0x180033b9d  test    eax, eax
0x180033b9f  jnz     short loc_180033BAA
0x180033ba1  mov     rdx, [r15+130h]
0x180033ba8  jmp     short loc_180033C0E
0x180033baa  mov     r8, rsi; MaxCount
0x180033bad  lea     rdx, aBytessent; "%BytesSent%"
0x180033bb4  mov     rcx, rdi; String1
0x180033bb7  call    cs:__imp__strnicmp
0x180033bbd  test    eax, eax
0x180033bbf  jnz     short loc_180033BCB
0x180033bc1  mov     r9, [r15+50h]
0x180033bc5  add     r9, [r15+40h]
0x180033bc9  jmp     short loc_180033BEF
0x180033bcb  cmp     ebx, 0Fh
0x180033bce  jnz     short loc_180033C1D
0x180033bd0  mov     r8d, ebx; MaxCount
0x180033bd3  lea     rdx, aBytesreceived; "%BytesReceived%"
0x180033bda  mov     rcx, rdi; String1
0x180033bdd  call    cs:__imp__strnicmp
0x180033be3  test    eax, eax
0x180033be5  jnz     short loc_180033C1D
0x180033be7  mov     r9, [r15+58h]
0x180033beb  add     r9, [r15+48h]
0x180033bef  lea     r8, aI64u; "%I64u"
0x180033bf6  mov     edx, 1Eh; unsigned __int64
0x180033bfb  lea     rcx, [rbp+57h+var_C8]; char *
0x180033bff  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180033c04  test    eax, eax
0x180033c06  mov     ebx, eax
0x180033c08  js      short loc_180033C47
0x180033c0a  lea     rdx, [rbp+57h+var_C8]
0x180033c0e  mov     rcx, r14
0x180033c11  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180033c17  mov     ebx, eax
0x180033c19  test    eax, eax
0x180033c1b  js      short loc_180033C47
0x180033c1d  lea     rbx, [r12+1]
0x180033c22  jmp     loc_18003396F
0x180033c27  lea     rcx, [rbp+57h+var_90]
0x180033c2b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180033c31  jmp     short loc_180033C47
0x180033c33  lea     rcx, [rbp+57h+var_C8]
0x180033c37  jmp     short loc_180033C2B
0x180033c39  mov     rdx, rbx
0x180033c3c  mov     rcx, r14
0x180033c3f  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180033c45  mov     ebx, eax
0x180033c47  mov     eax, ebx
0x180033c49  mov     rcx, [rbp+57h+var_50]
0x180033c4d  xor     rcx, rsp; StackCookie
0x180033c50  call    __security_check_cookie
0x180033c55  add     rsp, 0B8h
0x180033c5c  pop     r15
0x180033c5e  pop     r14
0x180033c60  pop     r13
0x180033c62  pop     r12
0x180033c64  pop     rdi
0x180033c65  pop     rsi
0x180033c66  pop     rbx
0x180033c67  pop     rbp
0x180033c68  retn
```
