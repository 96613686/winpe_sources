# LOCALIZED_STRING::GetLocalizedString(char const *,ushort * *)

- ea: `0x18002ad38`
- end: `0x18002b038`
- name: `?GetLocalizedString@LOCALIZED_STRING@@AEAAJPEBDPEAPEAG@Z`
- size: `768`
- prototype: `int(LOCALIZED_STRING *__hidden this, const char *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800144cc`
- `0x18002aa80`

## callees

- `0x180002b60`
- `0x180014110`
- `0x1800183f8`
- `0x180018438`
- `0x180019890`
- `0x18002ad38`
- `0x18002c0d0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af6e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002af61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002af61`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ae04`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ae73`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ae04`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002ae73`

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
0x18002ad38  mov     [rsp-8+arg_18], rbx
0x18002ad3d  push    rbp
0x18002ad3e  push    rsi
0x18002ad3f  push    rdi
0x18002ad40  push    r12
0x18002ad42  push    r13
0x18002ad44  push    r14
0x18002ad46  push    r15
0x18002ad48  lea     rbp, [rsp-0C0h]
0x18002ad50  sub     rsp, 1C0h
0x18002ad57  mov     rax, cs:__security_cookie
0x18002ad5e  xor     rax, rsp
0x18002ad61  mov     [rbp+0F0h+var_40], rax
0x18002ad68  mov     rbx, rdx
0x18002ad6b  mov     [rsp+1F0h+var_1C0], rcx
0x18002ad70  xor     edx, edx; Val
0x18002ad72  mov     [rsp+1F0h+pulNumLanguages], 0
0x18002ad7a  mov     r12, r8
0x18002ad7d  mov     [rsp+1F0h+pcchLanguagesBuffer], 0
0x18002ad85  mov     r13, rcx
0x18002ad88  lea     rcx, [rbp+0F0h+var_BE]; void *
0x18002ad8c  lea     r8d, [rdx+7Eh]; Size
0x18002ad90  call    memset_0
0x18002ad95  lea     rax, [rbp+0F0h+var_C0]
0x18002ad99  mov     [rbp+0F0h+var_154], 100h
0x18002ad9f  mov     [rbp+0F0h+Src], rax
0x18002ada3  mov     ecx, 80h
0x18002ada8  xor     eax, eax
0x18002adaa  mov     [rbp+0F0h+var_158], ecx
0x18002adad  mov     [rbp+0F0h+var_C0], ax
0x18002adb1  mov     byte ptr [rbp+0F0h+var_140], al
0x18002adb4  lea     rax, [rbp+0F0h+var_140]
0x18002adb8  mov     [rsp+1F0h+var_198], rax
0x18002adbd  mov     [rbp+0F0h+var_150], 0
0x18002adc4  mov     [rsp+1F0h+var_190], ecx
0x18002adc8  mov     [rsp+1F0h+var_18C], 100h
0x18002adcf  mov     [rsp+1F0h+var_188], 0
0x18002add8  mov     [rsp+1F0h+var_1C8], 0
0x18002ade0  test    rbx, rbx
0x18002ade3  jz      loc_18002AFF3
0x18002ade9  test    r12, r12
0x18002adec  jz      loc_18002AFF3
0x18002adf2  lea     edi, [rcx-38h]
0x18002adf5  xor     r8d, r8d; pwszLanguagesBuffer
0x18002adf8  mov     ecx, edi; dwFlags
0x18002adfa  lea     r9, [rsp+1F0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002adff  lea     rdx, [rsp+1F0h+pulNumLanguages]; pulNumLanguages
0x18002ae04  call    cs:__imp_GetThreadPreferredUILanguages
0x18002ae0a  test    eax, eax
0x18002ae0c  jnz     short loc_18002AE2C
0x18002ae0e  call    cs:__imp_GetLastError
0x18002ae14  mov     ebx, eax
0x18002ae16  test    eax, eax
0x18002ae18  jle     loc_18002AFF8
0x18002ae1e  movzx   ebx, ax
0x18002ae21  or      ebx, 80070000h
0x18002ae27  jmp     loc_18002AFF8
0x18002ae2c  xor     esi, esi
0x18002ae2e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ae32  lea     r14d, [rsi+2]
0x18002ae36  cmp     [rsp+1F0h+pulNumLanguages], esi
0x18002ae3a  jz      short loc_18002AE9B
0x18002ae3c  mov     ecx, [rsp+1F0h+pcchLanguagesBuffer]
0x18002ae40  mov     eax, r14d
0x18002ae43  mul     rcx
0x18002ae46  cmovb   rax, r8
0x18002ae4a  mov     rcx, rax; Size
0x18002ae4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ae52  mov     rsi, rax
0x18002ae55  test    rax, rax
0x18002ae58  jnz     short loc_18002AE64
0x18002ae5a  mov     ebx, 80070008h
0x18002ae5f  jmp     loc_18002AFF8
0x18002ae64  lea     r9, [rsp+1F0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002ae69  mov     r8, rax; pwszLanguagesBuffer
0x18002ae6c  lea     rdx, [rsp+1F0h+pulNumLanguages]; pulNumLanguages
0x18002ae71  mov     ecx, edi; dwFlags
0x18002ae73  call    cs:__imp_GetThreadPreferredUILanguages
0x18002ae79  test    eax, eax
0x18002ae7b  jnz     short loc_18002AE9B
0x18002ae7d  call    cs:__imp_GetLastError
0x18002ae83  mov     ebx, eax
0x18002ae85  test    eax, eax
0x18002ae87  jle     loc_18002AFE9
0x18002ae8d  movzx   ebx, ax
0x18002ae90  or      ebx, 80070000h
0x18002ae96  jmp     loc_18002AFE9
0x18002ae9b  mov     rdx, rbx; char *
0x18002ae9e  lea     rcx, [rsp+1F0h+var_180]; this
0x18002aea3  xor     edi, edi
0x18002aea5  call    ?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002aeaa  mov     ebx, eax
0x18002aeac  test    eax, eax
0x18002aeae  js      loc_18002AFCA
0x18002aeb4  mov     r8d, [rbp+0F0h+var_150]
0x18002aeb8  lea     r9d, [rdi+1]; int
0x18002aebc  mov     rdx, [rbp+0F0h+Src]; Src
0x18002aec0  xor     ecx, ecx
0x18002aec2  mov     [rbp+0F0h+var_140], ecx
0x18002aec5  add     r8d, r8d; Size
0x18002aec8  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18002aecd  mov     dword ptr [rsp+1F0h+var_188], r14d
0x18002aed2  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x18002aed7  test    eax, eax
0x18002aed9  jnz     short loc_18002AEE5
0x18002aedb  mov     ebx, 8007000Eh
0x18002aee0  jmp     loc_18002AFCA
0x18002aee5  mov     rdx, [rsp+1F0h+var_198]; unsigned __int16 *
0x18002aeea  lea     r8, [rsp+1F0h+var_1C8]; unsigned int *
0x18002aeef  call    ?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z; PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)
0x18002aef4  test    eax, eax
0x18002aef6  jnz     short loc_18002AF16
0x18002aef8  call    cs:__imp_GetLastError
0x18002aefe  mov     ebx, eax
0x18002af00  test    eax, eax
0x18002af02  jle     loc_18002AFCA
0x18002af08  movzx   ebx, ax
0x18002af0b  or      ebx, 80070000h
0x18002af11  jmp     loc_18002AFCA
0x18002af16  mov     r14d, 40h ; '@'
0x18002af1c  xor     r15d, r15d
0x18002af1f  test    r15d, r15d
0x18002af22  jnz     loc_18002AFC4
0x18002af28  mov     ecx, r14d
0x18002af2b  lea     eax, [r15+2]
0x18002af2f  mul     rcx
0x18002af32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002af39  cmovb   rax, rcx
0x18002af3d  mov     rcx, rax; Size
0x18002af40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002af45  mov     rdi, rax
0x18002af48  test    rax, rax
0x18002af4b  jz      short loc_18002AFBD
0x18002af4d  mov     edx, [r13+428h]; uID
0x18002af54  mov     r9d, r14d; cchBufferMax
0x18002af57  mov     rcx, [r13+448h]; hInstance
0x18002af5e  mov     r8, rax; lpBuffer
0x18002af61  call    cs:__imp_LoadStringW
0x18002af67  mov     r13d, eax
0x18002af6a  test    eax, eax
0x18002af6c  jnz     short loc_18002AF87
0x18002af6e  call    cs:__imp_GetLastError
0x18002af74  mov     ebx, eax
0x18002af76  test    eax, eax
0x18002af78  jle     short loc_18002AF83
0x18002af7a  movzx   ebx, ax
0x18002af7d  or      ebx, 80070000h
0x18002af83  test    ebx, ebx
0x18002af85  js      short loc_18002AFCA
0x18002af87  lea     eax, [r13+1]
0x18002af8b  cmp     eax, r14d
0x18002af8e  jnz     short loc_18002AFAD
0x18002af90  mov     rcx, rdi; Block
0x18002af93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002af98  xor     edi, edi
0x18002af9a  add     r14d, r14d
0x18002af9d  cmp     r14d, 10000h
0x18002afa4  jbe     short loc_18002AFB3
0x18002afa6  mov     ebx, 80070057h
0x18002afab  jmp     short loc_18002AFCA
0x18002afad  mov     r15d, 1
0x18002afb3  mov     r13, [rsp+1F0h+var_1C0]
0x18002afb8  jmp     loc_18002AF1F
0x18002afbd  mov     ebx, 80070008h
0x18002afc2  jmp     short loc_18002AFCA
0x18002afc4  mov     [r12], rdi
0x18002afc8  xor     edi, edi
0x18002afca  lea     r8, [rsp+1F0h+var_1C8]; unsigned int *
0x18002afcf  mov     rdx, rsi; unsigned __int16 *
0x18002afd2  call    ?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z; PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)
0x18002afd7  test    rdi, rdi
0x18002afda  jz      short loc_18002AFE4
0x18002afdc  mov     rcx, rdi; Block
0x18002afdf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002afe4  test    rsi, rsi
0x18002afe7  jz      short loc_18002AFF8
0x18002afe9  mov     rcx, rsi; Block
0x18002afec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aff1  jmp     short loc_18002AFF8
0x18002aff3  mov     ebx, 80070057h
0x18002aff8  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18002affd  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b002  lea     rcx, [rsp+1F0h+var_180]; this
0x18002b007  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b00c  mov     eax, ebx
0x18002b00e  mov     rcx, [rbp+0F0h+var_40]
0x18002b015  xor     rcx, rsp; StackCookie
0x18002b018  call    __security_check_cookie
0x18002b01d  mov     rbx, [rsp+1F0h+arg_18]
0x18002b025  add     rsp, 1C0h
0x18002b02c  pop     r15
0x18002b02e  pop     r14
0x18002b030  pop     r13
0x18002b032  pop     r12
0x18002b034  pop     rdi
0x18002b035  pop     rsi
0x18002b036  pop     rbp
0x18002b037  retn
```
