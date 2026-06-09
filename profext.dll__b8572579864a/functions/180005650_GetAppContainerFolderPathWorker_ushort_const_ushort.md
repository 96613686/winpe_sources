# GetAppContainerFolderPathWorker(ushort const *,ushort * *)

- ea: `0x180005650`
- end: `0x180005904`
- name: `?GetAppContainerFolderPathWorker@@YAJPEBGPEAPEAG@Z`
- size: `692`
- prototype: `__int64 __fastcall(char *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x180005650`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000571d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000571d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058f1`
- `profapi!__imp_GetAppContainerPath` at `0x18000569b`
- `profapi!__imp_GetAppContainerPath` at `0x18000569b`

## string_xrefs

- `0x1800056d8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800057dd`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000580e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180005833`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180005865`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800058c4`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180005877`: `Sid %ls path %ls size %Iu`
- `0x1800058d3`: `Sid %ls path %ls size %Iu`
- `0x180005802`: `Sid %ls`
- `0x1800056df`: `Sid %ls path %ls`

## pseudocode

```c
__int64 __fastcall GetAppContainerFolderPathWorker(char *a1, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  int AppContainerPath; // edi
  _WORD *i; // rax
  unsigned __int64 v8; // rsi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int16 *v14; // r9
  unsigned __int16 *v15; // rax
  unsigned int v16; // edi
  int v17; // [rsp+20h] [rbp-258h]
  _BYTE v18[528]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( a1 )
  {
    if ( a2 )
    {
      v4 = 260;
      AppContainerPath = GetAppContainerPath(a1, v18, 260);
      if ( AppContainerPath < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xBC3,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)AppContainerPath,
          (int)"Sid %ls",
          a1);
        return (unsigned int)AppContainerPath;
      }
      else
      {
        for ( i = v18; *i; ++i )
        {
          if ( !--v4 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0xBC7,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)0x80070057LL,
              (int)"Sid %ls path %ls",
              a1,
              v18);
            return 2147942487LL;
          }
        }
        v8 = 261 - v4;
        v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * (261 - v4));
        v10 = v9;
        if ( v9 )
        {
          if ( v8 )
          {
            if ( v8 > 0x7FFFFFFF )
            {
              v16 = -2147024809;
              *v9 = 0;
            }
            else
            {
              v11 = 2147483646;
              v12 = (unsigned __int16 *)v18;
              v13 = v8;
              v14 = v9;
              do
              {
                if ( !v11 )
                  break;
                if ( !*v12 )
                  break;
                *v14++ = *v12++;
                --v11;
                --v13;
              }
              while ( v13 );
              v15 = v14 - 1;
              v16 = -2147024774;
              if ( v13 )
              {
                v15 = v14;
                v16 = 0;
              }
              *v15 = 0;
              if ( v13 )
              {
                *a2 = v10;
                return 0;
              }
            }
          }
          else
          {
            v16 = -2147024809;
          }
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xBCE,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)v16,
            (int)"Sid %ls path %ls size %Iu",
            a1,
            v18,
            v8);
          CoTaskMemFree(v10);
          return v16;
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xBCB,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)0x8007000ELL,
            (int)"Sid %ls path %ls size %Iu",
            a1,
            v18,
            v8);
          return 2147942414LL;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBBD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)0x80070057LL,
        v17);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBBC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v17);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180005650  push    rbp
0x180005652  push    rdi
0x180005653  push    r14
0x180005655  sub     rsp, 260h
0x18000565c  mov     rax, cs:__security_cookie
0x180005663  xor     rax, rsp
0x180005666  mov     [rsp+278h+var_28], rax
0x18000566e  mov     r14, rdx
0x180005671  mov     rbp, rcx
0x180005674  test    rcx, rcx
0x180005677  jz      loc_1800057D5
0x18000567d  test    rdx, rdx
0x180005680  jz      loc_18000582B
0x180005686  mov     [rsp+278h+arg_10], rbx
0x18000568e  lea     rdx, [rsp+278h+var_238]
0x180005693  mov     ebx, 104h
0x180005698  mov     r8d, ebx
0x18000569b  call    cs:__imp_GetAppContainerPath
0x1800056a2  nop     dword ptr [rax+rax+00h]
0x1800056a7  mov     edi, eax
0x1800056a9  test    eax, eax
0x1800056ab  js      loc_1800057FA
0x1800056b1  lea     rax, [rsp+278h+var_238]
0x1800056b6  cmp     word ptr [rax], 0
0x1800056ba  jz      short loc_180005709
0x1800056bc  add     rax, 2
0x1800056c0  sub     rbx, 1
0x1800056c4  jnz     short loc_1800056B6
0x1800056c6  mov     rcx, [rsp+278h]; this
0x1800056ce  lea     rax, [rsp+278h+var_238]
0x1800056d3  mov     [rsp+278h+var_248], rax
0x1800056d8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800056df  lea     rax, aSidLsPathLs; "Sid %ls path %ls"
0x1800056e6  mov     [rsp+278h+var_250], rbp; char *
0x1800056eb  mov     edi, 80070057h
0x1800056f0  mov     qword ptr [rsp+278h+var_258], rax; int
0x1800056f5  mov     r9d, edi; char *
0x1800056f8  mov     edx, 0BC7h; void *
0x1800056fd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005702  mov     eax, edi
0x180005704  jmp     loc_1800057B0
0x180005709  mov     [rsp+278h+arg_18], rsi
0x180005711  mov     esi, 105h
0x180005716  sub     rsi, rbx
0x180005719  lea     rcx, [rsi+rsi]; cb
0x18000571d  call    cs:__imp_CoTaskMemAlloc
0x180005724  nop     dword ptr [rax+rax+00h]
0x180005729  mov     rbx, rax
0x18000572c  test    rax, rax
0x18000572f  jz      loc_180005853
0x180005735  test    rsi, rsi
0x180005738  jz      loc_1800058A3
0x18000573e  cmp     rsi, 7FFFFFFFh
0x180005745  ja      loc_18000589C
0x18000574b  mov     ecx, 7FFFFFFEh
0x180005750  lea     rdx, [rsp+278h+var_238]
0x180005755  mov     r8, rsi
0x180005758  mov     r9, rax
0x18000575b  nop     dword ptr [rax+rax+00h]
0x180005760  test    rcx, rcx
0x180005763  jz      short loc_180005782
0x180005765  movzx   eax, word ptr [rdx]
0x180005768  test    ax, ax
0x18000576b  jz      short loc_180005782
0x18000576d  mov     [r9], ax
0x180005771  add     rdx, 2
0x180005775  add     r9, 2
0x180005779  dec     rcx
0x18000577c  sub     r8, 1
0x180005780  jnz     short loc_180005760
0x180005782  test    r8, r8
0x180005785  lea     rax, [r9-2]
0x180005789  mov     edi, 8007007Ah
0x18000578e  cmovnz  rax, r9
0x180005792  xor     ecx, ecx
0x180005794  test    r8, r8
0x180005797  cmovnz  edi, ecx
0x18000579a  mov     [rax], cx
0x18000579d  jz      loc_1800058B2
0x1800057a3  mov     [r14], rbx
0x1800057a6  xor     eax, eax
0x1800057a8  mov     rsi, [rsp+278h+arg_18]
0x1800057b0  mov     rbx, [rsp+278h+arg_10]
0x1800057b8  mov     rcx, [rsp+278h+var_28]
0x1800057c0  xor     rcx, rsp; StackCookie
0x1800057c3  call    __security_check_cookie
0x1800057c8  add     rsp, 260h
0x1800057cf  pop     r14
0x1800057d1  pop     rdi
0x1800057d2  pop     rbp
0x1800057d3  retn
0x1800057d5  mov     rcx, [rsp+278h]; this
0x1800057dd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800057e4  mov     edi, 80070057h
0x1800057e9  mov     edx, 0BBCh; void *
0x1800057ee  mov     r9d, edi; char *
0x1800057f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057f6  mov     eax, edi
0x1800057f8  jmp     short loc_1800057B8
0x1800057fa  mov     rcx, [rsp+278h]; this
0x180005802  lea     rax, aSidLs; "Sid %ls"
0x180005809  mov     [rsp+278h+var_250], rbp; char *
0x18000580e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005815  mov     r9d, edi; char *
0x180005818  mov     qword ptr [rsp+278h+var_258], rax; int
0x18000581d  mov     edx, 0BC3h; void *
0x180005822  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005827  mov     eax, edi
0x180005829  jmp     short loc_1800057B0
0x18000582b  mov     rcx, [rsp+278h]; this
0x180005833  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000583a  mov     edi, 80070057h
0x18000583f  mov     edx, 0BBDh; void *
0x180005844  mov     r9d, edi; char *
0x180005847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000584c  mov     eax, edi
0x18000584e  jmp     loc_1800057B8
0x180005853  mov     rcx, [rsp+278h]; this
0x18000585b  lea     rax, [rsp+278h+var_238]
0x180005860  mov     [rsp+278h+var_240], rsi
0x180005865  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000586c  mov     [rsp+278h+var_248], rax
0x180005871  mov     r9d, 8007000Eh; char *
0x180005877  lea     rax, aSidLsPathLsSiz; "Sid %ls path %ls size %Iu"
0x18000587e  mov     [rsp+278h+var_250], rbp; char *
0x180005883  mov     edx, 0BCBh; void *
0x180005888  mov     qword ptr [rsp+278h+var_258], rax; int
0x18000588d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005892  mov     eax, 8007000Eh
0x180005897  jmp     loc_1800057A8
0x18000589c  mov     edi, 80070057h
0x1800058a1  jmp     short loc_1800058AD
0x1800058a3  mov     edi, 80070057h
0x1800058a8  test    rsi, rsi
0x1800058ab  jz      short loc_1800058B2
0x1800058ad  xor     ecx, ecx
0x1800058af  mov     [rax], cx
0x1800058b2  mov     rcx, [rsp+278h]; this
0x1800058ba  lea     rax, [rsp+278h+var_238]
0x1800058bf  mov     [rsp+278h+var_240], rsi
0x1800058c4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800058cb  mov     [rsp+278h+var_248], rax
0x1800058d0  mov     r9d, edi; char *
0x1800058d3  lea     rax, aSidLsPathLsSiz; "Sid %ls path %ls size %Iu"
0x1800058da  mov     [rsp+278h+var_250], rbp; char *
0x1800058df  mov     edx, 0BCEh; void *
0x1800058e4  mov     qword ptr [rsp+278h+var_258], rax; int
0x1800058e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800058ee  mov     rcx, rbx; pv
0x1800058f1  call    cs:__imp_CoTaskMemFree
0x1800058f8  nop     dword ptr [rax+rax+00h]
0x1800058fd  mov     eax, edi
0x1800058ff  jmp     loc_1800057A8
```
