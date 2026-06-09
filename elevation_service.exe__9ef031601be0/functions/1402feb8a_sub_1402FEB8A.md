# sub_1402FEB8A

- ea: `0x1402feb8a`
- end: `0x1402fed0c`
- name: `sub_1402FEB8A`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402fed0c`

## callees

- `0x140042c98`
- `0x14005e050`
- `0x140087310`
- `0x140087e00`
- `0x1400ec5e0`
- `0x1400ec980`
- `0x14012fc90`
- `0x1402feb8a`
- `0x1403002f0`
- `0x1403028ec`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1402febd8`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1402febd8`

## string_xrefs

- `0x1402febf3`: `..\..\chrome\installer\util\edge_scoped_impersonation.h`
- `0x1402fec0e`: `..\..\chrome\installer\util\edge_scoped_impersonation.h`
- `0x1402fec42`: `..\..\chrome\installer\util\edge_scoped_impersonation.h`
- `0x1402fec5c`: `..\..\chrome\installer\util\edge_scoped_impersonation.h`
- `0x1402fec81`: `The active user token is invalid.`

## pseudocode

```c
__int64 __fastcall sub_1402FEB8A(_DWORD *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // esi
  const char *v4; // rdx
  __int64 v5; // r8
  int v7; // eax
  __int64 v8; // [rsp+0h] [rbp-178h] BYREF
  _BYTE v9[16]; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v10[288]; // [rsp+38h] [rbp-140h] BYREF
  HANDLE v11[4]; // [rsp+158h] [rbp-20h] BYREF

  v11[0] = 0;
  sub_1403028EC(v11);
  if ( LODWORD(v11[0]) >= 0xFFFFFFF4 || v11[0] == 0 )
  {
    v3 = 315;
    if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_scoped_impersonation.h", 56) <= 0 )
      goto LABEL_10;
    sub_1400EC5E0(v9, "..\\..\\chrome\\installer\\util\\edge_scoped_impersonation.h", 39, 0xFFFFFFFFLL);
    v4 = "The active user token is invalid.";
    v5 = 33;
    goto LABEL_9;
  }
  if ( v11[0] == (HANDLE)-4LL )
  {
    v3 = 0;
    if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_scoped_impersonation.h", 56) <= 0 )
      goto LABEL_10;
    sub_1400EC5E0(v9, "..\\..\\chrome\\installer\\util\\edge_scoped_impersonation.h", 44, 0xFFFFFFFFLL);
    v4 = "Running as interactive user.";
    v5 = 28;
LABEL_9:
    sub_140042C98((__int64)v10, (__int64)v4, v5);
    sub_1400EC980(v9);
    goto LABEL_10;
  }
  if ( ImpersonateLoggedOnUser(v11[0]) )
  {
    *a1 = 0;
    v3 = 0;
  }
  else
  {
    v7 = sub_1403002F0(a1);
    *a1 = v7;
    v3 = 0;
    if ( v7 )
    {
      __debugbreak();
      BUG();
    }
  }
LABEL_10:
  if ( v11[0] != 0 && LODWORD(v11[0]) < 0xFFFFFFF4 )
  {
    LOBYTE(v2) = v11[0] == 0;
    sub_140087E00(v2);
    sub_14005E050(v11[0]);
  }
  if ( _security_cookie != ((unsigned __int64)&v8 ^ (unsigned __int64)v11[1]) )
    __debugbreak();
  return v3;
}

```

## disassembly

```asm
0x1402feb8a  push    rsi
0x1402feb8b  push    rdi
0x1402feb8c  sub     rsp, 168h
0x1402feb93  mov     rsi, rcx
0x1402feb96  mov     rax, cs:__security_cookie
0x1402feb9d  xor     rax, rsp
0x1402feba0  mov     [rsp+178h+var_18], rax
0x1402feba8  lea     rdi, [rsp+178h+var_20]
0x1402febb0  mov     qword ptr [rdi], 0
0x1402febb7  mov     rcx, rdi
0x1402febba  call    sub_1403028EC
0x1402febbf  mov     rcx, [rdi]; hToken
0x1402febc2  test    rcx, rcx
0x1402febc5  setnz   al
0x1402febc8  cmp     ecx, 0FFFFFFF4h
0x1402febcb  setb    dl
0x1402febce  test    al, dl
0x1402febd0  jz      short loc_1402FEC42
0x1402febd2  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1402febd6  jz      short loc_1402FEBF3
0x1402febd8  call    cs:ImpersonateLoggedOnUser
0x1402febde  test    eax, eax
0x1402febe0  jz      loc_1402FECE8
0x1402febe6  mov     dword ptr [rsi], 0
0x1402febec  xor     esi, esi
0x1402febee  jmp     loc_1402FEC9B
0x1402febf3  lea     rcx, aChromeInstalle_1; "..\\..\\chrome\\installer\\util\\edge_s"...
0x1402febfa  mov     edx, 38h ; '8'
0x1402febff  call    sub_140087310
0x1402fec04  xor     esi, esi
0x1402fec06  test    eax, eax
0x1402fec08  jle     loc_1402FEC9B
0x1402fec0e  lea     rdx, aChromeInstalle_1; "..\\..\\chrome\\installer\\util\\edge_s"...
0x1402fec15  lea     rdi, [rsp+178h+var_150]
0x1402fec1a  mov     rcx, rdi
0x1402fec1d  mov     r8d, 2Ch ; ','
0x1402fec23  mov     r9d, 0FFFFFFFFh
0x1402fec29  call    sub_1400EC5E0
0x1402fec2e  lea     rcx, [rsp+178h+var_140]
0x1402fec33  lea     rdx, aRunningAsInter; "Running as interactive user."
0x1402fec3a  mov     r8d, 1Ch
0x1402fec40  jmp     short loc_1402FEC8E
0x1402fec42  lea     rcx, aChromeInstalle_1; "..\\..\\chrome\\installer\\util\\edge_s"...
0x1402fec49  mov     edx, 38h ; '8'
0x1402fec4e  call    sub_140087310
0x1402fec53  mov     esi, 13Bh
0x1402fec58  test    eax, eax
0x1402fec5a  jle     short loc_1402FEC9B
0x1402fec5c  lea     rdx, aChromeInstalle_1; "..\\..\\chrome\\installer\\util\\edge_s"...
0x1402fec63  lea     rdi, [rsp+178h+var_150]
0x1402fec68  mov     rcx, rdi
0x1402fec6b  mov     r8d, 27h ; '''
0x1402fec71  mov     r9d, 0FFFFFFFFh
0x1402fec77  call    sub_1400EC5E0
0x1402fec7c  lea     rcx, [rsp+178h+var_140]
0x1402fec81  lea     rdx, aTheActiveUserT; "The active user token is invalid."
0x1402fec88  mov     r8d, 21h ; '!'
0x1402fec8e  call    sub_140042C98
0x1402fec93  mov     rcx, rdi
0x1402fec96  call    sub_1400EC980
0x1402fec9b  mov     rax, [rsp+178h+var_20]
0x1402feca3  test    rax, rax
0x1402feca6  setz    cl
0x1402feca9  cmp     eax, 0FFFFFFF4h
0x1402fecac  setnb   al
0x1402fecaf  or      al, cl
0x1402fecb1  jnz     short loc_1402FECC5
0x1402fecb3  call    sub_140087E00
0x1402fecb8  mov     rcx, [rsp+178h+var_20]
0x1402fecc0  call    sub_14005E050
0x1402fecc5  mov     rax, [rsp+178h+var_18]
0x1402feccd  xor     rax, rsp
0x1402fecd0  mov     rcx, cs:__security_cookie
0x1402fecd7  cmp     rcx, rax
0x1402fecda  jnz     short loc_1402FECFB
0x1402fecdc  mov     eax, esi
0x1402fecde  add     rsp, 168h
0x1402fece5  pop     rdi
0x1402fece6  pop     rsi
0x1402fece7  retn
0x1402fece8  mov     rcx, rsi
0x1402feceb  call    sub_1403002F0
0x1402fecf0  mov     [rsi], eax
0x1402fecf2  xor     esi, esi
0x1402fecf4  test    eax, eax
0x1402fecf6  jz      short loc_1402FEC9B
0x1402fecf8  int     3; Trap to Debugger
0x1402fecf9  ud2
0x1402fecfb  mov     rcx, [rsp+178h+var_18]
0x1402fed03  xor     rcx, rsp; StackCookie
0x1402fed06  call    __security_check_cookie
0x1402fed0b  int     3; Trap to Debugger
```
