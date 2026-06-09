# DRMCreateUser

- ea: `0x1800050d0`
- end: `0x1800052cd`
- name: `DRMCreateUser`
- size: `509`
- prototype: `HRESULT __stdcall(PWSTR wszUserName, PWSTR wszUserId, PWSTR wszUserIdType, DRMPUBHANDLE *phUser)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18005a144`

## callees

- `0x180001244`
- `0x18000420c`
- `0x180004328`
- `0x1800046c8`
- `0x1800050d0`
- `0x1800082cc`
- `0x180015e94`
- `0x180016a38`
- `0x180016a9c`
- `0x18001ffd8`

## import_xrefs

- `msvcrt!iswspace` at `0x180005158`
- `msvcrt!iswspace` at `0x180005158`
- `msvcrt!_wcsicmp` at `0x180005204`
- `msvcrt!_wcsicmp` at `0x18000521b`
- `msvcrt!_wcsicmp` at `0x180005232`
- `msvcrt!_wcsicmp` at `0x180005249`
- `msvcrt!_wcsicmp` at `0x180005260`
- `msvcrt!_wcsicmp` at `0x180005204`
- `msvcrt!_wcsicmp` at `0x18000521b`
- `msvcrt!_wcsicmp` at `0x180005232`
- `msvcrt!_wcsicmp` at `0x180005249`
- `msvcrt!_wcsicmp` at `0x180005260`

## string_xrefs

- `0x180005177`: `+DRMCreateUser (username=%ls, userID=%ls, userIdType=%ls)\n`
- `0x1800052b2`: `-DRMCreateUser HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateUser(PWSTR wszUserName, PWSTR wszUserId, PWSTR wszUserIdType, DRMPUBHANDLE *phUser)
{
  PWSTR v7; // rbx
  HRESULT v8; // ebx
  wint_t v9; // ax
  CUser *v10; // rax
  CUser *v11; // rax
  CNameValue *v12; // rbp
  unsigned __int16 *v13; // rbx
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 0;
  v7 = wszUserName;
  if ( (!wszUserName || (unsigned __int8)DRMIsValidStringT<unsigned short>(wszUserName, 0, wszUserIdType, phUser) && *v7)
    && (!wszUserId
     || (unsigned __int8)DRMIsValidStringT<unsigned short>(wszUserId, 0, wszUserIdType, phUser) && *wszUserId)
    && (!wszUserIdType
     || (unsigned __int8)DRMIsValidStringT<unsigned short>(wszUserIdType, 0, wszUserIdType, phUser) && *wszUserIdType)
    && phUser )
  {
    if ( !v7 )
      goto LABEL_17;
    v9 = *v7;
    if ( *v7 )
    {
      do
      {
        if ( !iswspace(v9) )
          break;
        v9 = *++v7;
      }
      while ( *v7 );
      if ( *v7 )
      {
LABEL_17:
        _RTLTRACE("+DRMCreateUser (username=%ls, userID=%ls, userIdType=%ls)\n", v7, wszUserId, wszUserIdType);
        if ( v7 || wszUserId )
        {
          v10 = (CUser *)operator new(0x98u);
          if ( !v10 || (v11 = CUser::CUser(v10), (v12 = v11) == 0) )
          {
            v8 = -2147024882;
            goto LABEL_37;
          }
          if ( v7 )
          {
            v8 = CUser::SetUserName(v11, v7);
            if ( v8 < 0 )
              goto LABEL_35;
          }
          if ( wszUserId )
          {
            v8 = CNameValue::SetValue(v12, wszUserId);
            if ( v8 < 0 )
              goto LABEL_35;
          }
          if ( !wszUserIdType )
            goto LABEL_32;
          v13 = L"Windows";
          if ( _wcsicmp(wszUserIdType, L"Windows") )
          {
            v13 = L"Passport";
            if ( _wcsicmp(wszUserIdType, L"Passport") )
            {
              v13 = L"Internal";
              if ( _wcsicmp(wszUserIdType, L"Internal") )
              {
                v13 = L"Unspecified";
                if ( _wcsicmp(wszUserIdType, L"Unspecified") )
                {
                  v13 = L"Federation";
                  if ( _wcsicmp(wszUserIdType, L"Federation") )
                  {
                    v8 = -2147024809;
                    goto LABEL_35;
                  }
                }
              }
            }
          }
          v8 = CUser::SetUserIdType(v12, v13);
          if ( v8 >= 0 )
          {
LABEL_32:
            v8 = DRMCInt::CreateHandle(7u, v12, &v15);
            if ( v8 >= 0 )
            {
              *phUser = v15;
              goto LABEL_37;
            }
          }
LABEL_35:
          CDRMCBase::Release(v12);
          goto LABEL_37;
        }
      }
    }
  }
  v8 = -2147024809;
LABEL_37:
  _RTLTRACE("-DRMCreateUser HR=%x\n", v8);
  return v8;
}

```

## disassembly

```asm
0x1800050d0  push    rbx
0x1800050d2  push    rbp
0x1800050d3  push    rsi
0x1800050d4  push    rdi
0x1800050d5  push    r14
0x1800050d7  push    r15
0x1800050d9  sub     rsp, 28h
0x1800050dd  xor     r15d, r15d
0x1800050e0  mov     r14, r9
0x1800050e3  mov     [rsp+58h+arg_0], r15d
0x1800050e8  mov     rdi, r8
0x1800050eb  mov     rsi, rdx
0x1800050ee  mov     rbx, rcx
0x1800050f1  test    rcx, rcx
0x1800050f4  jz      short loc_180005107
0x1800050f6  xor     edx, edx
0x1800050f8  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x1800050fd  test    al, al
0x1800050ff  jz      short loc_18000513E
0x180005101  cmp     [rbx], r15w
0x180005105  jz      short loc_18000513E
0x180005107  test    rsi, rsi
0x18000510a  jz      short loc_180005120
0x18000510c  xor     edx, edx
0x18000510e  mov     rcx, rsi
0x180005111  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180005116  test    al, al
0x180005118  jz      short loc_18000513E
0x18000511a  cmp     [rsi], r15w
0x18000511e  jz      short loc_18000513E
0x180005120  test    rdi, rdi
0x180005123  jz      short loc_180005139
0x180005125  xor     edx, edx
0x180005127  mov     rcx, rdi
0x18000512a  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18000512f  test    al, al
0x180005131  jz      short loc_18000513E
0x180005133  cmp     [rdi], r15w
0x180005137  jz      short loc_18000513E
0x180005139  test    r14, r14
0x18000513c  jnz     short loc_180005148
0x18000513e  mov     ebx, 80070057h
0x180005143  jmp     loc_1800052B0
0x180005148  test    rbx, rbx
0x18000514b  jz      short loc_180005174
0x18000514d  movzx   eax, word ptr [rbx]
0x180005150  test    ax, ax
0x180005153  jz      short loc_18000513E
0x180005155  movzx   ecx, ax; C
0x180005158  call    cs:__imp_iswspace
0x18000515e  test    eax, eax
0x180005160  jz      short loc_18000516E
0x180005162  add     rbx, 2
0x180005166  movzx   eax, word ptr [rbx]
0x180005169  test    ax, ax
0x18000516c  jnz     short loc_180005155
0x18000516e  cmp     [rbx], r15w
0x180005172  jz      short loc_18000513E
0x180005174  mov     r9, rdi
0x180005177  lea     rcx, aDrmcreateuserU; "+DRMCreateUser (username=%ls, userID=%l"...
0x18000517e  mov     r8, rsi
0x180005181  mov     rdx, rbx
0x180005184  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180005189  test    rbx, rbx
0x18000518c  jnz     short loc_180005193
0x18000518e  test    rsi, rsi
0x180005191  jz      short loc_18000513E
0x180005193  mov     ecx, 98h; Size
0x180005198  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000519d  test    rax, rax
0x1800051a0  jz      loc_1800052AB
0x1800051a6  mov     rcx, rax; this
0x1800051a9  call    ??0CUser@@QEAA@XZ; CUser::CUser(void)
0x1800051ae  mov     rbp, rax
0x1800051b1  test    rax, rax
0x1800051b4  jz      loc_1800052AB
0x1800051ba  test    rbx, rbx
0x1800051bd  jz      short loc_1800051D4
0x1800051bf  mov     rdx, rbx; unsigned __int16 *
0x1800051c2  mov     rcx, rax; this
0x1800051c5  call    ?SetUserName@CUser@@QEAAJPEAG@Z; CUser::SetUserName(ushort *)
0x1800051ca  mov     ebx, eax
0x1800051cc  test    eax, eax
0x1800051ce  js      loc_1800052A1
0x1800051d4  test    rsi, rsi
0x1800051d7  jz      short loc_1800051EE
0x1800051d9  mov     rdx, rsi; unsigned __int16 *
0x1800051dc  mov     rcx, rbp; this
0x1800051df  call    ?SetValue@CNameValue@@QEAAJPEAG@Z; CNameValue::SetValue(ushort *)
0x1800051e4  mov     ebx, eax
0x1800051e6  test    eax, eax
0x1800051e8  js      loc_1800052A1
0x1800051ee  test    rdi, rdi
0x1800051f1  jz      loc_18000527B
0x1800051f7  lea     rbx, aWindows; "Windows"
0x1800051fe  mov     rcx, rdi; String1
0x180005201  mov     rdx, rbx; String2
0x180005204  call    cs:__imp__wcsicmp
0x18000520a  test    eax, eax
0x18000520c  jz      short loc_18000526A
0x18000520e  lea     rbx, aPassport; "Passport"
0x180005215  mov     rcx, rdi; String1
0x180005218  mov     rdx, rbx; String2
0x18000521b  call    cs:__imp__wcsicmp
0x180005221  test    eax, eax
0x180005223  jz      short loc_18000526A
0x180005225  lea     rbx, aInternal; "Internal"
0x18000522c  mov     rcx, rdi; String1
0x18000522f  mov     rdx, rbx; String2
0x180005232  call    cs:__imp__wcsicmp
0x180005238  test    eax, eax
0x18000523a  jz      short loc_18000526A
0x18000523c  lea     rbx, aUnspecified; "Unspecified"
0x180005243  mov     rcx, rdi; String1
0x180005246  mov     rdx, rbx; String2
0x180005249  call    cs:__imp__wcsicmp
0x18000524f  test    eax, eax
0x180005251  jz      short loc_18000526A
0x180005253  lea     rbx, aFederation; "Federation"
0x18000525a  mov     rcx, rdi; String1
0x18000525d  mov     rdx, rbx; String2
0x180005260  call    cs:__imp__wcsicmp
0x180005266  test    eax, eax
0x180005268  jnz     short loc_18000529C
0x18000526a  mov     rdx, rbx; unsigned __int16 *
0x18000526d  mov     rcx, rbp; this
0x180005270  call    ?SetUserIdType@CUser@@QEAAJPEAG@Z; CUser::SetUserIdType(ushort *)
0x180005275  mov     ebx, eax
0x180005277  test    eax, eax
0x180005279  js      short loc_1800052A1
0x18000527b  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x180005280  mov     rdx, rbp; void *
0x180005283  mov     ecx, 7; unsigned int
0x180005288  call    ?CreateHandle@DRMCInt@@SAJIPEAXPEAK@Z; DRMCInt::CreateHandle(uint,void *,ulong *)
0x18000528d  mov     ebx, eax
0x18000528f  test    eax, eax
0x180005291  js      short loc_1800052A1
0x180005293  mov     eax, [rsp+58h+arg_0]
0x180005297  mov     [r14], eax
0x18000529a  jmp     short loc_1800052B0
0x18000529c  mov     ebx, 80070057h
0x1800052a1  mov     rcx, rbp; this
0x1800052a4  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x1800052a9  jmp     short loc_1800052B0
0x1800052ab  mov     ebx, 8007000Eh
0x1800052b0  mov     edx, ebx
0x1800052b2  lea     rcx, aDrmcreateuserH; "-DRMCreateUser HR=%x\n"
0x1800052b9  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800052be  mov     eax, ebx
0x1800052c0  add     rsp, 28h
0x1800052c4  pop     r15
0x1800052c6  pop     r14
0x1800052c8  pop     rdi
0x1800052c9  pop     rsi
0x1800052ca  pop     rbp
0x1800052cb  pop     rbx
0x1800052cc  retn
```
