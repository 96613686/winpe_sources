# CAccountData::_ReadDisplayLanguage(void)

- ea: `0x18000849c`
- end: `0x1800085af`
- name: `?_ReadDisplayLanguage@CAccountData@@AEAAXXZ`
- size: `275`
- prototype: `void __fastcall(CAccountData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008184`

## callees

- `0x18000626c`
- `0x18000849c`
- `0x1800258c8`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180008511`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180008589`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180008511`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180008589`

## pseudocode

```c
void __fastcall CAccountData::_ReadDisplayLanguage(CAccountData *this)
{
  bool v2; // zf
  BOOL SystemPreferredUILanguages; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-E0h] BYREF
  ULONG pcchLanguagesBuffer[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR pwszLanguagesBuffer[256]; // [rsp+30h] [rbp-D0h] BYREF

  memset_0(pwszLanguagesBuffer, 0, sizeof(pwszLanguagesBuffer));
  v2 = *((_DWORD *)this + 150) == 1;
  pcchLanguagesBuffer[0] = 256;
  *((_DWORD *)this + 156) = 0;
  if ( v2 )
  {
    pulNumLanguages = 0;
    SystemPreferredUILanguages = GetSystemPreferredUILanguages(
                                   0x408u,
                                   &pulNumLanguages,
                                   pwszLanguagesBuffer,
                                   pcchLanguagesBuffer);
    goto LABEL_3;
  }
  if ( (unsigned int)Intl_GetUserUILanguage(*((HKEY *)this + 77), pwszLanguagesBuffer, 256) )
  {
LABEL_4:
    if ( StringCchCopyW((unsigned __int16 *)this + 130, 0x55u, pwszLanguagesBuffer) >= 0 )
      return;
    goto LABEL_5;
  }
  pulNumLanguages = 0;
  SystemPreferredUILanguages = GetSystemPreferredUILanguages(
                                 8u,
                                 &pulNumLanguages,
                                 pwszLanguagesBuffer,
                                 pcchLanguagesBuffer);
  if ( *((_DWORD *)this + 150) == 2 )
  {
    if ( !SystemPreferredUILanguages )
      goto LABEL_5;
    *((_DWORD *)this + 156) = 1;
    goto LABEL_4;
  }
LABEL_3:
  if ( SystemPreferredUILanguages )
    goto LABEL_4;
LABEL_5:
  *((_WORD *)this + 130) = 0;
}

```

## disassembly

```asm
0x18000849c  mov     [rsp-8+arg_8], rbx
0x1800084a1  push    rbp
0x1800084a2  lea     rbp, [rsp-140h]
0x1800084aa  sub     rsp, 240h
0x1800084b1  mov     rax, cs:__security_cookie
0x1800084b8  xor     rax, rsp
0x1800084bb  mov     [rbp+140h+var_10], rax
0x1800084c2  mov     rbx, rcx
0x1800084c5  xor     edx, edx; Val
0x1800084c7  lea     rcx, [rsp+240h+pwszLanguagesBuffer]; void *
0x1800084cc  mov     r8d, 200h; Size
0x1800084d2  call    memset_0
0x1800084d7  cmp     dword ptr [rbx+258h], 1
0x1800084de  mov     r8d, 100h; int
0x1800084e4  mov     [rsp+240h+pcchLanguagesBuffer], r8d
0x1800084e9  mov     dword ptr [rbx+270h], 0
0x1800084f3  jnz     short loc_18000855E
0x1800084f5  lea     r9, [rsp+240h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800084fa  mov     [rsp+240h+pulNumLanguages], 0
0x180008502  lea     r8, [rsp+240h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180008507  mov     ecx, 408h; dwFlags
0x18000850c  lea     rdx, [rsp+240h+pulNumLanguages]; pulNumLanguages
0x180008511  call    cs:__imp_GetSystemPreferredUILanguages
0x180008517  test    eax, eax
0x180008519  jz      short loc_180008535
0x18000851b  lea     rcx, [rbx+104h]; unsigned __int16 *
0x180008522  mov     edx, 55h ; 'U'; unsigned __int64
0x180008527  lea     r8, [rsp+240h+pwszLanguagesBuffer]; unsigned __int16 *
0x18000852c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008531  test    eax, eax
0x180008533  jns     short loc_18000853E
0x180008535  xor     eax, eax
0x180008537  mov     [rbx+104h], ax
0x18000853e  mov     rcx, [rbp+140h+var_10]
0x180008545  xor     rcx, rsp; StackCookie
0x180008548  call    __security_check_cookie
0x18000854d  mov     rbx, [rsp+240h+arg_8]
0x180008555  add     rsp, 240h
0x18000855c  pop     rbp
0x18000855d  retn
0x18000855e  mov     rcx, [rbx+268h]; hKey
0x180008565  lea     rdx, [rsp+240h+pwszLanguagesBuffer]; unsigned __int16 *
0x18000856a  call    ?Intl_GetUserUILanguage@@YAHPEAUHKEY__@@PEAGH@Z; Intl_GetUserUILanguage(HKEY__ *,ushort *,int)
0x18000856f  test    eax, eax
0x180008571  jnz     short loc_18000851B
0x180008573  lea     r9, [rsp+240h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180008578  mov     [rsp+240h+pulNumLanguages], eax
0x18000857c  lea     r8, [rsp+240h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180008581  lea     rdx, [rsp+240h+pulNumLanguages]; pulNumLanguages
0x180008586  lea     ecx, [rax+8]; dwFlags
0x180008589  call    cs:__imp_GetSystemPreferredUILanguages
0x18000858f  cmp     dword ptr [rbx+258h], 2
0x180008596  jnz     loc_180008517
0x18000859c  test    eax, eax
0x18000859e  jz      short loc_180008535
0x1800085a0  mov     dword ptr [rbx+270h], 1
0x1800085aa  jmp     loc_18000851B
```
