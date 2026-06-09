# CNDFLanguageUtil::SetThreadLanguage(void)

- ea: `0x180004694`
- end: `0x18000476f`
- name: `?SetThreadLanguage@CNDFLanguageUtil@@QEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(CNDFLanguageUtil *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x180004940`

## callees

- `0x1800040b4`
- `0x18000458c`
- `0x180004694`
- `0x180006710`
- `0x180006d90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004733`
- `KERNEL32!GetLastError` at `0x180004733`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x180004729`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x180004729`

## pseudocode

```c
__int64 __fastcall CNDFLanguageUtil::SetThreadLanguage(CNDFLanguageUtil *this)
{
  int LanguageInfo; // ebx
  CNDFLanguageUtil *v3; // rcx
  signed int LastError; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-10h] BYREF
  ULONG pulNumLanguages; // [rsp+60h] [rbp+20h] BYREF
  PCZZWSTR v8; // [rsp+68h] [rbp+28h] BYREF
  PCZZWSTR pwszLanguagesBuffer; // [rsp+70h] [rbp+30h] BYREF

  LanguageInfo = CNDFLanguageUtil::RetrieveLanguageInfo(
                   this,
                   0x40u,
                   (unsigned int *)this + 2,
                   (unsigned __int16 **)this + 2,
                   (unsigned int *)this + 6);
  if ( LanguageInfo >= 0 )
  {
    v6[0] = &DiagnosticsClient::`vftable';
    v6[1] = *(_QWORD *)this;
    LanguageInfo = DiagnosticsClient::Impersonate((DiagnosticsClient *)v6);
    if ( LanguageInfo >= 0 )
    {
      pwszLanguagesBuffer = 0;
      LanguageInfo = CNDFLanguageUtil::RetrieveLanguageInfo(
                       v3,
                       0x38u,
                       (unsigned int *)&v8,
                       (unsigned __int16 **)&pwszLanguagesBuffer,
                       &pulNumLanguages);
      if ( LanguageInfo >= 0 )
      {
        v8 = pwszLanguagesBuffer;
        pulNumLanguages = 0;
        if ( !SetThreadPreferredUILanguages(8u, pwszLanguagesBuffer, &pulNumLanguages) )
        {
          LastError = GetLastError();
          LanguageInfo = LastError;
          if ( LastError > 0 )
            LanguageInfo = (unsigned __int16)LastError | 0x80070000;
        }
        TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v8);
      }
      DiagnosticsClient::RevertToSelf((DiagnosticsClient *)v6);
      if ( LanguageInfo >= 0 )
        *((_DWORD *)this + 7) = 1;
    }
  }
  return (unsigned int)LanguageInfo;
}

```

## disassembly

```asm
0x180004694  push    rbp
0x180004696  push    rbx
0x180004697  push    rdi
0x180004698  mov     rbp, rsp
0x18000469b  sub     rsp, 40h
0x18000469f  lea     rax, [rcx+18h]
0x1800046a3  mov     edx, 40h ; '@'; unsigned int
0x1800046a8  lea     r9, [rcx+10h]; unsigned __int16 **
0x1800046ac  mov     [rsp+40h+var_20], rax; unsigned int *
0x1800046b1  lea     r8, [rcx+8]; unsigned int *
0x1800046b5  mov     rdi, rcx
0x1800046b8  call    ?RetrieveLanguageInfo@CNDFLanguageUtil@@AEAAJKPEAKPEAPEAG0@Z; CNDFLanguageUtil::RetrieveLanguageInfo(ulong,ulong *,ushort * *,ulong *)
0x1800046bd  mov     ebx, eax
0x1800046bf  test    eax, eax
0x1800046c1  js      loc_180004765
0x1800046c7  lea     rax, ??_7DiagnosticsClient@@6B@; const DiagnosticsClient::`vftable'
0x1800046ce  mov     [rbp+var_10], rax
0x1800046d2  lea     rcx, [rbp+var_10]; this
0x1800046d6  mov     rax, [rdi]
0x1800046d9  mov     [rbp+var_8], rax
0x1800046dd  call    ?Impersonate@DiagnosticsClient@@UEAAJXZ; DiagnosticsClient::Impersonate(void)
0x1800046e2  mov     ebx, eax
0x1800046e4  test    eax, eax
0x1800046e6  js      short loc_180004765
0x1800046e8  lea     rax, [rbp+pulNumLanguages]
0x1800046ec  mov     [rbp+pwszLanguagesBuffer], 0
0x1800046f4  lea     r9, [rbp+pwszLanguagesBuffer]; unsigned __int16 **
0x1800046f8  mov     [rsp+40h+var_20], rax; unsigned int *
0x1800046fd  lea     r8, [rbp+arg_8]; unsigned int *
0x180004701  mov     edx, 38h ; '8'; unsigned int
0x180004706  call    ?RetrieveLanguageInfo@CNDFLanguageUtil@@AEAAJKPEAKPEAPEAG0@Z; CNDFLanguageUtil::RetrieveLanguageInfo(ulong,ulong *,ushort * *,ulong *)
0x18000470b  mov     ebx, eax
0x18000470d  test    eax, eax
0x18000470f  js      short loc_180004751
0x180004711  mov     rdx, [rbp+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180004715  lea     r8, [rbp+pulNumLanguages]; pulNumLanguages
0x180004719  mov     ecx, 8; dwFlags
0x18000471e  mov     [rbp+arg_8], rdx
0x180004722  mov     [rbp+pulNumLanguages], 0
0x180004729  call    cs:__imp_SetThreadPreferredUILanguages
0x18000472f  test    eax, eax
0x180004731  jnz     short loc_180004748
0x180004733  call    cs:__imp_GetLastError
0x180004739  mov     ebx, eax
0x18000473b  test    eax, eax
0x18000473d  jle     short loc_180004748
0x18000473f  movzx   ebx, ax
0x180004742  or      ebx, 80070000h
0x180004748  lea     rcx, [rbp+arg_8]
0x18000474c  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180004751  lea     rcx, [rbp+var_10]; this
0x180004755  call    ?RevertToSelf@DiagnosticsClient@@UEAAJXZ; DiagnosticsClient::RevertToSelf(void)
0x18000475a  test    ebx, ebx
0x18000475c  js      short loc_180004765
0x18000475e  mov     dword ptr [rdi+1Ch], 1
0x180004765  mov     eax, ebx
0x180004767  add     rsp, 40h
0x18000476b  pop     rdi
0x18000476c  pop     rbx
0x18000476d  pop     rbp
0x18000476e  retn
```
