# VerifyTrustXP

- ea: `0x140010fd4`
- end: `0x140011197`
- name: `VerifyTrustXP`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000ed30`

## callees

- `0x14000929c`
- `0x140010fd4`
- `0x14001619a`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140011107`
- `KERNEL32!GetProcAddress` at `0x140011107`
- `KERNEL32!GetLastError` at `0x140011112`
- `KERNEL32!GetLastError` at `0x140011154`
- `KERNEL32!GetLastError` at `0x140011112`
- `KERNEL32!GetLastError` at `0x140011154`
- `KERNEL32!FreeLibrary` at `0x140011175`
- `KERNEL32!FreeLibrary` at `0x140011175`

## string_xrefs

- `0x1400110e6`: `wintrust.dll`

## pseudocode

```c
__int64 __fastcall VerifyTrustXP(__int64 a1, const OLECHAR *a2, int a3, __int128 *a4, int a5)
{
  int v9; // eax
  HMODULE v10; // rsi
  signed int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  int v14; // eax
  signed int LastError; // eax
  HMODULE hModule; // [rsp+20h] [rbp-A1h] BYREF
  _DWORD v18[6]; // [rsp+30h] [rbp-91h] BYREF
  int v19; // [rsp+48h] [rbp-79h]
  int v20; // [rsp+4Ch] [rbp-75h]
  int v21; // [rsp+50h] [rbp-71h]
  int *v22; // [rsp+58h] [rbp-69h]
  int v23; // [rsp+60h] [rbp-61h]
  __int64 v24; // [rsp+68h] [rbp-59h]
  __int64 v25; // [rsp+70h] [rbp-51h]
  int v26; // [rsp+78h] [rbp-49h]
  int v27; // [rsp+90h] [rbp-31h] BYREF
  __int128 v28; // [rsp+94h] [rbp-2Dh]
  __int64 v29; // [rsp+A8h] [rbp-19h]
  int v30; // [rsp+B0h] [rbp-11h]
  const OLECHAR *v31; // [rsp+B8h] [rbp-9h]
  int v32; // [rsp+C0h] [rbp-1h]
  const OLECHAR *v33; // [rsp+C8h] [rbp+7h]
  _DWORD v34[4]; // [rsp+D0h] [rbp+Fh] BYREF

  v34[0] = 11191659;
  v34[1] = 298896708;
  v34[2] = -1073692020;
  v34[3] = -292175281;
  hModule = 0;
  memset_0(&v27, 0, 0x40u);
  v27 = 64;
  if ( a4 )
    v28 = *a4;
  v29 = a1;
  v30 = 2 * a3;
  v32 = 2 * a3;
  if ( a2 )
  {
    v31 = a2;
    v33 = a2;
  }
  else
  {
    v31 = &Default;
    v33 = &Default;
  }
  memset_0(v18, 0, 0x58u);
  v18[0] = 88;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a5 )
  {
    v19 = 1;
    v26 = 0;
  }
  else
  {
    v19 = 2;
    v26 = 256;
  }
  v21 = 3;
  v22 = &v27;
  v9 = SafeLoadLibrary("wintrust.dll", &hModule);
  v10 = hModule;
  v11 = v9;
  if ( v9 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "WinVerifyTrust");
    if ( ProcAddress )
    {
      v14 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v34, v18);
      v11 = v14;
      if ( !v14 )
        goto LABEL_21;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_21:
        if ( a5 )
          goto LABEL_22;
        LastError = GetLastError();
        v11 = LastError;
        if ( !LastError )
          goto LABEL_22;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 >= 0 )
LABEL_22:
          v11 = 0;
      }
    }
    else
    {
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
    }
  }
  if ( v10 )
    FreeLibrary(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140010fd4  push    rbp
0x140010fd6  push    rbx
0x140010fd7  push    rsi
0x140010fd8  push    rdi
0x140010fd9  push    r14
0x140010fdb  lea     rbp, [rsp-2Fh]
0x140010fe0  sub     rsp, 0F0h
0x140010fe7  mov     rax, cs:__security_cookie
0x140010fee  xor     rax, rsp
0x140010ff1  mov     [rbp+4Fh+var_30], rax
0x140010ff5  mov     rbx, rdx
0x140010ff8  mov     [rbp+4Fh+var_40], 0AAC56Bh
0x140010fff  xor     edx, edx; Val
0x140011001  mov     [rbp+4Fh+var_3C], 11D0CD44h
0x140011008  mov     r14d, r8d
0x14001100b  mov     [rbp+4Fh+var_38], 0C000C28Ch
0x140011012  mov     rsi, rcx
0x140011015  mov     [rbp+4Fh+var_34], 0EE95C24Fh
0x14001101c  lea     rcx, [rbp+4Fh+var_80]; void *
0x140011020  mov     [rsp+110h+hModule], 0
0x140011029  lea     r8d, [rdx+40h]; Size
0x14001102d  mov     rdi, r9
0x140011030  call    memset_0
0x140011035  mov     [rbp+4Fh+var_80], 40h ; '@'
0x14001103c  test    rdi, rdi
0x14001103f  jz      short loc_140011049
0x140011041  movups  xmm0, xmmword ptr [rdi]
0x140011044  movdqu  [rbp+4Fh+var_7C], xmm0
0x140011049  mov     [rbp+4Fh+var_68], rsi
0x14001104d  lea     eax, [r14+r14]
0x140011051  mov     [rbp+4Fh+var_60], eax
0x140011054  mov     [rbp+4Fh+var_50], eax
0x140011057  test    rbx, rbx
0x14001105a  jnz     short loc_14001106D
0x14001105c  lea     rcx, Default
0x140011063  mov     [rbp+4Fh+var_58], rcx
0x140011067  mov     [rbp+4Fh+var_48], rcx
0x14001106b  jmp     short loc_140011075
0x14001106d  mov     [rbp+4Fh+var_58], rbx
0x140011071  mov     [rbp+4Fh+var_48], rbx
0x140011075  mov     ebx, 58h ; 'X'
0x14001107a  lea     rcx, [rsp+110h+var_E0]; void *
0x14001107f  mov     r8d, ebx; Size
0x140011082  xor     edx, edx; Val
0x140011084  call    memset_0
0x140011089  mov     r14d, [rbp+4Fh+arg_20]
0x14001108d  mov     [rsp+110h+var_E0], ebx
0x140011091  mov     [rbp+4Fh+var_C4], 0
0x140011098  mov     [rbp+4Fh+var_B0], 0
0x14001109f  mov     [rbp+4Fh+var_A8], 0
0x1400110a7  mov     [rbp+4Fh+var_A0], 0
0x1400110af  test    r14d, r14d
0x1400110b2  jz      short loc_1400110C4
0x1400110b4  mov     [rbp+4Fh+var_C8], 1
0x1400110bb  mov     [rbp+4Fh+var_98], 0
0x1400110c2  jmp     short loc_1400110D2
0x1400110c4  mov     [rbp+4Fh+var_C8], 2
0x1400110cb  mov     [rbp+4Fh+var_98], 100h
0x1400110d2  lea     rax, [rbp+4Fh+var_80]
0x1400110d6  mov     [rbp+4Fh+var_C0], 3
0x1400110dd  lea     rdx, [rsp+110h+hModule]
0x1400110e2  mov     [rbp+4Fh+var_B8], rax
0x1400110e6  lea     rcx, aWintrustDll; "wintrust.dll"
0x1400110ed  call    SafeLoadLibrary
0x1400110f2  mov     rsi, [rsp+110h+hModule]
0x1400110f7  mov     ebx, eax
0x1400110f9  test    eax, eax
0x1400110fb  js      short loc_14001116D
0x1400110fd  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x140011104  mov     rcx, rsi; hModule
0x140011107  call    cs:__imp_GetProcAddress
0x14001110d  test    rax, rax
0x140011110  jnz     short loc_140011129
0x140011112  call    cs:__imp_GetLastError
0x140011118  mov     ebx, eax
0x14001111a  test    eax, eax
0x14001111c  jle     short loc_14001116D
0x14001111e  movzx   ebx, ax
0x140011121  or      ebx, 80070000h
0x140011127  jmp     short loc_14001116D
0x140011129  lea     r8, [rsp+110h+var_E0]
0x14001112e  xor     ecx, ecx
0x140011130  lea     rdx, [rbp+4Fh+var_40]
0x140011134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011139  mov     ebx, eax
0x14001113b  mov     edi, 80070000h
0x140011140  test    eax, eax
0x140011142  jz      short loc_14001114F
0x140011144  jle     short loc_14001114B
0x140011146  movzx   ebx, ax
0x140011149  or      ebx, edi
0x14001114b  test    ebx, ebx
0x14001114d  js      short loc_14001116D
0x14001114f  test    r14d, r14d
0x140011152  jnz     short loc_14001116B
0x140011154  call    cs:__imp_GetLastError
0x14001115a  mov     ebx, eax
0x14001115c  test    eax, eax
0x14001115e  jz      short loc_14001116B
0x140011160  jle     short loc_140011167
0x140011162  movzx   ebx, ax
0x140011165  or      ebx, edi
0x140011167  test    ebx, ebx
0x140011169  js      short loc_14001116D
0x14001116b  xor     ebx, ebx
0x14001116d  test    rsi, rsi
0x140011170  jz      short loc_14001117B
0x140011172  mov     rcx, rsi; hLibModule
0x140011175  call    cs:__imp_FreeLibrary
0x14001117b  mov     eax, ebx
0x14001117d  mov     rcx, [rbp+4Fh+var_30]
0x140011181  xor     rcx, rsp; StackCookie
0x140011184  call    __security_check_cookie
0x140011189  add     rsp, 0F0h
0x140011190  pop     r14
0x140011192  pop     rdi
0x140011193  pop     rsi
0x140011194  pop     rbx
0x140011195  pop     rbp
0x140011196  retn
```
