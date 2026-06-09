# LOCALIZED_STRING::GetLocalizedString(char const *,ushort * *)

- ea: `0x18002cc58`
- end: `0x18002cf83`
- name: `?GetLocalizedString@LOCALIZED_STRING@@AEAAJPEBDPEAPEAG@Z`
- size: `811`
- prototype: `int(LOCALIZED_STRING *__hidden this, const char *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180014fbc`
- `0x18002c998`

## callees

- `0x1800034f0`
- `0x180014b70`
- `0x180019230`
- `0x180019270`
- `0x18001a700`
- `0x18002cc58`
- `0x18002e0f0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ceb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ceb2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ce9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ce9f`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002cd24`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002cd9f`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002cd24`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002cd9f`

## pseudocode

```c
__int64 __fastcall LOCALIZED_STRING::GetLocalizedString(LOCALIZED_STRING *this, const char *a2, unsigned __int16 **a3)
{
  LOCALIZED_STRING *v5; // r13
  signed int LastError; // eax
  signed int v7; // ebx
  WCHAR *v8; // rsi
  WCHAR *v9; // rax
  signed int v10; // eax
  WCHAR *v11; // rdi
  unsigned int v12; // ecx
  signed int v13; // eax
  unsigned int v14; // r14d
  int v15; // r15d
  WCHAR *v16; // rax
  int StringW; // r13d
  signed int v18; // eax
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-E0h] BYREF
  ULONG pulNumLanguages; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v22; // [rsp+28h] [rbp-D8h] BYREF
  LOCALIZED_STRING *v23; // [rsp+30h] [rbp-D0h]
  _BYTE v24[32]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  __int16 v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *Src; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+98h] [rbp-68h]
  __int16 v32; // [rsp+9Ch] [rbp-64h]
  int v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v35; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v36[126]; // [rsp+132h] [rbp+32h] BYREF

  v23 = this;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  v5 = this;
  memset_0(v36, 0, sizeof(v36));
  v32 = 256;
  Src = (unsigned __int16 *)&v35;
  v31 = 128;
  v35 = 0;
  LOBYTE(v34) = 0;
  v25 = (unsigned __int16 *)&v34;
  v33 = 0;
  v26 = 128;
  v27 = 256;
  v28 = 0;
  v22 = 0;
  if ( !a2 || !a3 )
  {
    v7 = -2147024809;
    goto LABEL_37;
  }
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_37;
  }
  v8 = 0;
  if ( pulNumLanguages )
  {
    v9 = (WCHAR *)operator new(saturated_mul(pcchLanguagesBuffer, 2u));
    v8 = v9;
    if ( !v9 )
    {
      v7 = -2147024888;
      goto LABEL_37;
    }
    if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, v9, &pcchLanguagesBuffer) )
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
LABEL_35:
      operator delete(v8);
      goto LABEL_37;
    }
  }
  v11 = 0;
  v7 = STRU::CopyA((STRU *)v29, a2);
  if ( v7 >= 0 )
  {
    v34 = 0;
    LODWORD(v28) = 2;
    if ( (unsigned int)MULTISZ::AuxAppend((MULTISZ *)v24, Src, (unsigned int)(2 * v33), 1) )
    {
      if ( (unsigned int)PrivateSetThreadPreferredUILanguages(v12, v25, &v22) )
      {
        v14 = 64;
        v15 = 0;
        while ( !v15 )
        {
          v16 = (WCHAR *)operator new(saturated_mul(v14, 2u));
          v11 = v16;
          if ( !v16 )
          {
            v7 = -2147024888;
            goto LABEL_32;
          }
          StringW = LoadStringW(*((HINSTANCE *)v5 + 137), *((_DWORD *)v5 + 266), v16, v14);
          if ( !StringW )
          {
            v18 = GetLastError();
            v7 = v18;
            if ( v18 > 0 )
              v7 = (unsigned __int16)v18 | 0x80070000;
            if ( v7 < 0 )
              goto LABEL_32;
          }
          if ( StringW + 1 == v14 )
          {
            operator delete(v11);
            v11 = 0;
            v14 *= 2;
            if ( v14 > 0x10000 )
            {
              v7 = -2147024809;
              goto LABEL_32;
            }
          }
          else
          {
            v15 = 1;
          }
          v5 = v23;
        }
        *a3 = v11;
        v11 = 0;
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
LABEL_32:
  PrivateSetThreadPreferredUILanguages(v12, v8, &v22);
  if ( v11 )
    operator delete(v11);
  if ( v8 )
    goto LABEL_35;
LABEL_37:
  BUFFER::~BUFFER((BUFFER *)v24);
  BUFFER::~BUFFER((BUFFER *)v29);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cc58  mov     [rsp-8+arg_18], rbx
0x18002cc5d  push    rbp
0x18002cc5e  push    rsi
0x18002cc5f  push    rdi
0x18002cc60  push    r12
0x18002cc62  push    r13
0x18002cc64  push    r14
0x18002cc66  push    r15
0x18002cc68  lea     rbp, [rsp-0C0h]
0x18002cc70  sub     rsp, 1C0h
0x18002cc77  mov     rax, cs:__security_cookie
0x18002cc7e  xor     rax, rsp
0x18002cc81  mov     [rbp+0F0h+var_40], rax
0x18002cc88  mov     rbx, rdx
0x18002cc8b  mov     [rsp+1F0h+var_1C0], rcx
0x18002cc90  xor     edx, edx; Val
0x18002cc92  mov     [rsp+1F0h+pulNumLanguages], 0
0x18002cc9a  mov     r12, r8
0x18002cc9d  mov     [rsp+1F0h+pcchLanguagesBuffer], 0
0x18002cca5  mov     r13, rcx
0x18002cca8  lea     rcx, [rbp+0F0h+var_BE]; void *
0x18002ccac  lea     r8d, [rdx+7Eh]; Size
0x18002ccb0  call    memset_0
0x18002ccb5  lea     rax, [rbp+0F0h+var_C0]
0x18002ccb9  mov     [rbp+0F0h+var_154], 100h
0x18002ccbf  mov     [rbp+0F0h+Src], rax
0x18002ccc3  mov     ecx, 80h
0x18002ccc8  xor     eax, eax
0x18002ccca  mov     [rbp+0F0h+var_158], ecx
0x18002cccd  mov     [rbp+0F0h+var_C0], ax
0x18002ccd1  mov     byte ptr [rbp+0F0h+var_140], al
0x18002ccd4  lea     rax, [rbp+0F0h+var_140]
0x18002ccd8  mov     [rsp+1F0h+var_198], rax
0x18002ccdd  mov     [rbp+0F0h+var_150], 0
0x18002cce4  mov     [rsp+1F0h+var_190], ecx
0x18002cce8  mov     [rsp+1F0h+var_18C], 100h
0x18002ccef  mov     [rsp+1F0h+var_188], 0
0x18002ccf8  mov     [rsp+1F0h+var_1C8], 0
0x18002cd00  test    rbx, rbx
0x18002cd03  jz      loc_18002CF3D
0x18002cd09  test    r12, r12
0x18002cd0c  jz      loc_18002CF3D
0x18002cd12  lea     edi, [rcx-38h]
0x18002cd15  xor     r8d, r8d; pwszLanguagesBuffer
0x18002cd18  mov     ecx, edi; dwFlags
0x18002cd1a  lea     r9, [rsp+1F0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002cd1f  lea     rdx, [rsp+1F0h+pulNumLanguages]; pulNumLanguages
0x18002cd24  call    cs:__imp_GetThreadPreferredUILanguages
0x18002cd2b  nop     dword ptr [rax+rax+00h]
0x18002cd30  test    eax, eax
0x18002cd32  jnz     short loc_18002CD58
0x18002cd34  call    cs:__imp_GetLastError
0x18002cd3b  nop     dword ptr [rax+rax+00h]
0x18002cd40  mov     ebx, eax
0x18002cd42  test    eax, eax
0x18002cd44  jle     loc_18002CF42
0x18002cd4a  movzx   ebx, ax
0x18002cd4d  or      ebx, 80070000h
0x18002cd53  jmp     loc_18002CF42
0x18002cd58  xor     esi, esi
0x18002cd5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cd5e  lea     r14d, [rsi+2]
0x18002cd62  cmp     [rsp+1F0h+pulNumLanguages], esi
0x18002cd66  jz      short loc_18002CDD3
0x18002cd68  mov     ecx, [rsp+1F0h+pcchLanguagesBuffer]
0x18002cd6c  mov     eax, r14d
0x18002cd6f  mul     rcx
0x18002cd72  cmovb   rax, r8
0x18002cd76  mov     rcx, rax; Size
0x18002cd79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cd7e  mov     rsi, rax
0x18002cd81  test    rax, rax
0x18002cd84  jnz     short loc_18002CD90
0x18002cd86  mov     ebx, 80070008h
0x18002cd8b  jmp     loc_18002CF42
0x18002cd90  lea     r9, [rsp+1F0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002cd95  mov     r8, rax; pwszLanguagesBuffer
0x18002cd98  lea     rdx, [rsp+1F0h+pulNumLanguages]; pulNumLanguages
0x18002cd9d  mov     ecx, edi; dwFlags
0x18002cd9f  call    cs:__imp_GetThreadPreferredUILanguages
0x18002cda6  nop     dword ptr [rax+rax+00h]
0x18002cdab  test    eax, eax
0x18002cdad  jnz     short loc_18002CDD3
0x18002cdaf  call    cs:__imp_GetLastError
0x18002cdb6  nop     dword ptr [rax+rax+00h]
0x18002cdbb  mov     ebx, eax
0x18002cdbd  test    eax, eax
0x18002cdbf  jle     loc_18002CF33
0x18002cdc5  movzx   ebx, ax
0x18002cdc8  or      ebx, 80070000h
0x18002cdce  jmp     loc_18002CF33
0x18002cdd3  mov     rdx, rbx; char *
0x18002cdd6  lea     rcx, [rsp+1F0h+var_180]; this
0x18002cddb  xor     edi, edi
0x18002cddd  call    ?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002cde2  mov     ebx, eax
0x18002cde4  test    eax, eax
0x18002cde6  js      loc_18002CF14
0x18002cdec  mov     r8d, [rbp+0F0h+var_150]
0x18002cdf0  lea     r9d, [rdi+1]; int
0x18002cdf4  mov     rdx, [rbp+0F0h+Src]; Src
0x18002cdf8  xor     ecx, ecx
0x18002cdfa  mov     [rbp+0F0h+var_140], ecx
0x18002cdfd  add     r8d, r8d; Size
0x18002ce00  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18002ce05  mov     dword ptr [rsp+1F0h+var_188], r14d
0x18002ce0a  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x18002ce0f  test    eax, eax
0x18002ce11  jnz     short loc_18002CE1D
0x18002ce13  mov     ebx, 8007000Eh
0x18002ce18  jmp     loc_18002CF14
0x18002ce1d  mov     rdx, [rsp+1F0h+var_198]; unsigned __int16 *
0x18002ce22  lea     r8, [rsp+1F0h+var_1C8]; unsigned int *
0x18002ce27  call    ?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z; PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)
0x18002ce2c  test    eax, eax
0x18002ce2e  jnz     short loc_18002CE54
0x18002ce30  call    cs:__imp_GetLastError
0x18002ce37  nop     dword ptr [rax+rax+00h]
0x18002ce3c  mov     ebx, eax
0x18002ce3e  test    eax, eax
0x18002ce40  jle     loc_18002CF14
0x18002ce46  movzx   ebx, ax
0x18002ce49  or      ebx, 80070000h
0x18002ce4f  jmp     loc_18002CF14
0x18002ce54  mov     r14d, 40h ; '@'
0x18002ce5a  xor     r15d, r15d
0x18002ce5d  test    r15d, r15d
0x18002ce60  jnz     loc_18002CF0E
0x18002ce66  mov     ecx, r14d
0x18002ce69  lea     eax, [r15+2]
0x18002ce6d  mul     rcx
0x18002ce70  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ce77  cmovb   rax, rcx
0x18002ce7b  mov     rcx, rax; Size
0x18002ce7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ce83  mov     rdi, rax
0x18002ce86  test    rax, rax
0x18002ce89  jz      short loc_18002CF07
0x18002ce8b  mov     edx, [r13+428h]; uID
0x18002ce92  mov     r9d, r14d; cchBufferMax
0x18002ce95  mov     rcx, [r13+448h]; hInstance
0x18002ce9c  mov     r8, rax; lpBuffer
0x18002ce9f  call    cs:__imp_LoadStringW
0x18002cea6  nop     dword ptr [rax+rax+00h]
0x18002ceab  mov     r13d, eax
0x18002ceae  test    eax, eax
0x18002ceb0  jnz     short loc_18002CED1
0x18002ceb2  call    cs:__imp_GetLastError
0x18002ceb9  nop     dword ptr [rax+rax+00h]
0x18002cebe  mov     ebx, eax
0x18002cec0  test    eax, eax
0x18002cec2  jle     short loc_18002CECD
0x18002cec4  movzx   ebx, ax
0x18002cec7  or      ebx, 80070000h
0x18002cecd  test    ebx, ebx
0x18002cecf  js      short loc_18002CF14
0x18002ced1  lea     eax, [r13+1]
0x18002ced5  cmp     eax, r14d
0x18002ced8  jnz     short loc_18002CEF7
0x18002ceda  mov     rcx, rdi; Block
0x18002cedd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cee2  xor     edi, edi
0x18002cee4  add     r14d, r14d
0x18002cee7  cmp     r14d, 10000h
0x18002ceee  jbe     short loc_18002CEFD
0x18002cef0  mov     ebx, 80070057h
0x18002cef5  jmp     short loc_18002CF14
0x18002cef7  mov     r15d, 1
0x18002cefd  mov     r13, [rsp+1F0h+var_1C0]
0x18002cf02  jmp     loc_18002CE5D
0x18002cf07  mov     ebx, 80070008h
0x18002cf0c  jmp     short loc_18002CF14
0x18002cf0e  mov     [r12], rdi
0x18002cf12  xor     edi, edi
0x18002cf14  lea     r8, [rsp+1F0h+var_1C8]; unsigned int *
0x18002cf19  mov     rdx, rsi; unsigned __int16 *
0x18002cf1c  call    ?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z; PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)
0x18002cf21  test    rdi, rdi
0x18002cf24  jz      short loc_18002CF2E
0x18002cf26  mov     rcx, rdi; Block
0x18002cf29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cf2e  test    rsi, rsi
0x18002cf31  jz      short loc_18002CF42
0x18002cf33  mov     rcx, rsi; Block
0x18002cf36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cf3b  jmp     short loc_18002CF42
0x18002cf3d  mov     ebx, 80070057h
0x18002cf42  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18002cf47  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002cf4c  lea     rcx, [rsp+1F0h+var_180]; this
0x18002cf51  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002cf56  mov     eax, ebx
0x18002cf58  mov     rcx, [rbp+0F0h+var_40]
0x18002cf5f  xor     rcx, rsp; StackCookie
0x18002cf62  call    __security_check_cookie
0x18002cf67  mov     rbx, [rsp+1F0h+arg_18]
0x18002cf6f  add     rsp, 1C0h
0x18002cf76  pop     r15
0x18002cf78  pop     r14
0x18002cf7a  pop     r13
0x18002cf7c  pop     r12
0x18002cf7e  pop     rdi
0x18002cf7f  pop     rsi
0x18002cf80  pop     rbp
0x18002cf81  retn
```
