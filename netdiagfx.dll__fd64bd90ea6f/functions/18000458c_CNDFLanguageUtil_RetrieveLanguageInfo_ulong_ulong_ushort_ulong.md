# CNDFLanguageUtil::RetrieveLanguageInfo(ulong,ulong *,ushort * *,ulong *)

- ea: `0x18000458c`
- end: `0x18000468d`
- name: `?RetrieveLanguageInfo@CNDFLanguageUtil@@AEAAJKPEAKPEAPEAG0@Z`
- size: `257`
- prototype: `int(CNDFLanguageUtil *__hidden this, unsigned int, unsigned int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004694`

## callees

- `0x1800040b4`
- `0x18000458c`
- `0x18002c802`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004619`
- `KERNEL32!GetLastError` at `0x180004637`
- `KERNEL32!GetLastError` at `0x180004619`
- `KERNEL32!GetLastError` at `0x180004637`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800045cb`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x18000460f`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800045cb`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x18000460f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800045dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800045dd`

## pseudocode

```c
__int64 __fastcall CNDFLanguageUtil::RetrieveLanguageInfo(
        CNDFLanguageUtil *this,
        DWORD a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  signed int v10; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  unsigned int *v13; // rcx
  ULONG v14; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-18h] BYREF
  WCHAR *v17; // [rsp+28h] [rbp-10h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+70h] [rbp+38h] BYREF
  int v19; // [rsp+74h] [rbp+3Ch]

  v19 = HIDWORD(this);
  pulNumLanguages = 0;
  v17 = 0;
  pcchLanguagesBuffer = 0;
  GetThreadPreferredUILanguages(a2, &pulNumLanguages, 0, &pcchLanguagesBuffer);
  if ( pcchLanguagesBuffer )
  {
    v8 = (WCHAR *)CoTaskMemAlloc(2LL * pcchLanguagesBuffer);
    v9 = v8;
    if ( v8 )
    {
      v17 = v8;
      v10 = 0;
      memset_0(v8, 0, 2LL * pcchLanguagesBuffer);
      if ( !GetThreadPreferredUILanguages(a2, &pulNumLanguages, v9, &pcchLanguagesBuffer) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_11;
    }
    v10 = -2147024882;
  }
  else
  {
    v12 = GetLastError();
    v10 = v12;
    if ( !v12 )
    {
      v10 = -2147467259;
      goto LABEL_14;
    }
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
  }
  v9 = 0;
LABEL_11:
  if ( v10 >= 0 )
  {
    v13 = a5;
    *a3 = pulNumLanguages;
    v14 = pcchLanguagesBuffer;
    *a4 = v9;
    *v13 = v14;
    v17 = 0;
  }
LABEL_14:
  TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000458c  mov     qword ptr [rsp-30h+pcchLanguagesBuffer], rcx
0x180004591  push    rbp
0x180004592  push    rbx
0x180004593  push    rsi
0x180004594  push    rdi
0x180004595  push    r14
0x180004597  push    r15
0x180004599  mov     rbp, rsp
0x18000459c  sub     rsp, 38h
0x1800045a0  mov     esi, edx
0x1800045a2  mov     [rbp+pulNumLanguages], 0
0x1800045a9  mov     r14, r9
0x1800045ac  mov     [rbp+var_10], 0
0x1800045b4  mov     r15, r8
0x1800045b7  mov     [rbp+pcchLanguagesBuffer], 0
0x1800045be  mov     ecx, esi; dwFlags
0x1800045c0  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800045c4  xor     r8d, r8d; pwszLanguagesBuffer
0x1800045c7  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1800045cb  call    cs:__imp_GetThreadPreferredUILanguages
0x1800045d1  mov     eax, [rbp+pcchLanguagesBuffer]
0x1800045d4  test    eax, eax
0x1800045d6  jz      short loc_180004637
0x1800045d8  mov     ecx, eax
0x1800045da  add     rcx, rcx; cb
0x1800045dd  call    cs:__imp_CoTaskMemAlloc
0x1800045e3  mov     rdi, rax
0x1800045e6  test    rax, rax
0x1800045e9  jz      short loc_180004630
0x1800045eb  mov     r8d, [rbp+pcchLanguagesBuffer]
0x1800045ef  xor     edx, edx; Val
0x1800045f1  add     r8, r8; Size
0x1800045f4  mov     [rbp+var_10], rax
0x1800045f8  mov     rcx, rax; void *
0x1800045fb  xor     ebx, ebx
0x1800045fd  call    memset_0
0x180004602  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180004606  mov     r8, rdi; pwszLanguagesBuffer
0x180004609  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x18000460d  mov     ecx, esi; dwFlags
0x18000460f  call    cs:__imp_GetThreadPreferredUILanguages
0x180004615  test    eax, eax
0x180004617  jnz     short loc_180004650
0x180004619  call    cs:__imp_GetLastError
0x18000461f  mov     ebx, eax
0x180004621  test    eax, eax
0x180004623  jle     short loc_180004650
0x180004625  movzx   ebx, ax
0x180004628  or      ebx, 80070000h
0x18000462e  jmp     short loc_180004650
0x180004630  mov     ebx, 8007000Eh
0x180004635  jmp     short loc_18000464E
0x180004637  call    cs:__imp_GetLastError
0x18000463d  mov     ebx, eax
0x18000463f  test    eax, eax
0x180004641  jz      short loc_180004670
0x180004643  jle     short loc_18000464E
0x180004645  movzx   ebx, ax
0x180004648  or      ebx, 80070000h
0x18000464e  xor     edi, edi
0x180004650  test    ebx, ebx
0x180004652  js      short loc_180004675
0x180004654  mov     eax, [rbp+pulNumLanguages]
0x180004657  mov     rcx, [rbp+arg_20]
0x18000465b  mov     [r15], eax
0x18000465e  mov     eax, [rbp+pcchLanguagesBuffer]
0x180004661  mov     [r14], rdi
0x180004664  mov     [rcx], eax
0x180004666  mov     [rbp+var_10], 0
0x18000466e  jmp     short loc_180004675
0x180004670  mov     ebx, 80004005h
0x180004675  lea     rcx, [rbp+var_10]
0x180004679  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18000467e  mov     eax, ebx
0x180004680  add     rsp, 38h
0x180004684  pop     r15
0x180004686  pop     r14
0x180004688  pop     rdi
0x180004689  pop     rsi
0x18000468a  pop     rbx
0x18000468b  pop     rbp
0x18000468c  retn
```
