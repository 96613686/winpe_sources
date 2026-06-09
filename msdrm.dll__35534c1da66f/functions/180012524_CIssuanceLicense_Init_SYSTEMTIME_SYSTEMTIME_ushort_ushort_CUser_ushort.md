# CIssuanceLicense::Init(_SYSTEMTIME *,_SYSTEMTIME *,ushort *,ushort *,CUser *,ushort *)

- ea: `0x180012524`
- end: `0x18001274f`
- name: `?Init@CIssuanceLicense@@QEAAJPEAU_SYSTEMTIME@@0PEAG1PEAVCUser@@1@Z`
- size: `555`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, SYSTEMTIME *lpSystemTime, SYSTEMTIME *, unsigned __int16 *, unsigned __int16 *, struct CUser *, wchar_t *Str)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004970`
- `0x180013a08`

## callees

- `0x180001284`
- `0x180009d3c`
- `0x180012524`
- `0x18001f8e0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001258b`
- `msvcrt!wcsstr` at `0x1800125a0`
- `msvcrt!wcsstr` at `0x1800125b5`
- `msvcrt!wcsstr` at `0x18001258b`
- `msvcrt!wcsstr` at `0x1800125a0`
- `msvcrt!wcsstr` at `0x1800125b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012736`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012736`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012556`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180012671`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180012671`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001263b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001265a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001263b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001265a`

## string_xrefs

- `0x180012596`: `Microsoft Rights Template`
- `0x1800125ab`: `Microsoft Official Rights Template`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::Init(
        CIssuanceLicense *this,
        SYSTEMTIME *lpSystemTime,
        SYSTEMTIME *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct CUser *a6,
        wchar_t *Str)
{
  struct _RTL_CRITICAL_SECTION *v11; // r13
  CDRMCBase *v12; // rcx
  int OwnerXML; // ebx
  wchar_t *v14; // rsi
  CDRMCBase *v15; // rcx
  __int64 v16; // rax
  unsigned __int16 *v17; // rsi
  CDRMCBase *v18; // rcx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-68h] BYREF
  __int64 v21; // [rsp+28h] [rbp-60h]
  char *v22; // [rsp+30h] [rbp-58h]
  FILETIME FileTime2; // [rsp+90h] [rbp+8h] BYREF

  v21 = -2;
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v22 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  OwnerXML = 0;
  FileTime = 0;
  FileTime2 = 0;
  v14 = Str;
  if ( Str && !wcsstr(Str, L"Microsoft Rights Label") )
  {
    if ( !wcsstr(v14, L"Microsoft Rights Template") && !wcsstr(v14, L"Microsoft Official Rights Template") )
    {
      OwnerXML = -2147024809;
      goto LABEL_33;
    }
    OwnerXML = CDRMCBase::DuplicateStringEx(v15, v14, (unsigned __int16 **)this + 93);
    if ( OwnerXML < 0 )
      goto LABEL_33;
    v12 = (CDRMCBase *)*((_QWORD *)this + 93);
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v12 + v16) );
    *((_DWORD *)this + 188) = v16;
    *((_DWORD *)this + 183) = 1;
  }
  if ( !a6 || (OwnerXML = CIssuanceLicense::CreateOwnerXML(this, a6), OwnerXML >= 0) )
  {
    if ( lpSystemTime && a3 )
    {
      if ( !SystemTimeToFileTime(lpSystemTime, &FileTime)
        || !SystemTimeToFileTime(a3, &FileTime2)
        || CompareFileTime(&FileTime, &FileTime2) != -1 )
      {
        OwnerXML = -2147168431;
        goto LABEL_33;
      }
      *(SYSTEMTIME *)((char *)this + 588) = *lpSystemTime;
      *(SYSTEMTIME *)((char *)this + 604) = *a3;
      if ( *((_DWORD *)this + 183) )
        *((_DWORD *)this + 184) = 1;
    }
    v17 = a5;
    if ( a4 )
    {
      if ( *a4 )
      {
        OwnerXML = CDRMCBase::DuplicateStringEx(v12, a4, (unsigned __int16 **)this + 78);
        if ( OwnerXML < 0 )
          goto LABEL_33;
        goto LABEL_23;
      }
    }
    else if ( !a5 )
    {
      goto LABEL_33;
    }
    operator delete(*((void **)this + 78));
    *((_QWORD *)this + 78) = 0;
LABEL_23:
    if ( v17 && *v17 )
    {
      OwnerXML = CDRMCBase::DuplicateStringEx(v18, v17, (unsigned __int16 **)this + 79);
      if ( OwnerXML < 0 )
        goto LABEL_33;
    }
    else
    {
      operator delete(*((void **)this + 79));
      *((_QWORD *)this + 79) = 0;
    }
    if ( *((_DWORD *)this + 183) )
      *((_DWORD *)this + 184) = 1;
  }
LABEL_33:
  LeaveCriticalSection(v11);
  return (unsigned int)OwnerXML;
}

```

## disassembly

```asm
0x180012524  push    rbx
0x180012526  push    rbp
0x180012527  push    rsi
0x180012528  push    rdi
0x180012529  push    r12
0x18001252b  push    r13
0x18001252d  push    r14
0x18001252f  push    r15
0x180012531  sub     rsp, 48h
0x180012535  mov     [rsp+88h+var_60], 0FFFFFFFFFFFFFFFEh
0x18001253e  mov     rbp, r9
0x180012541  mov     r15, r8
0x180012544  mov     r12, rdx
0x180012547  mov     rdi, rcx
0x18001254a  lea     r13, [rcx+58h]
0x18001254e  mov     [rsp+88h+var_58], r13
0x180012553  mov     rcx, r13; lpCriticalSection
0x180012556  call    cs:__imp_EnterCriticalSection
0x18001255c  nop
0x18001255d  xor     r14d, r14d
0x180012560  mov     ebx, r14d
0x180012563  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], r14
0x180012568  mov     qword ptr [rsp+88h+FileTime2.dwLowDateTime], r14
0x180012570  mov     rsi, [rsp+88h+Str]
0x180012578  test    rsi, rsi
0x18001257b  jz      loc_18001260A
0x180012581  lea     rdx, aMicrosoftRight; "Microsoft Rights Label"
0x180012588  mov     rcx, rsi; Str
0x18001258b  call    cs:__imp_wcsstr
0x180012591  test    rax, rax
0x180012594  jnz     short loc_18001260A
0x180012596  lea     rdx, aMicrosoftRight_0; "Microsoft Rights Template"
0x18001259d  mov     rcx, rsi; Str
0x1800125a0  call    cs:__imp_wcsstr
0x1800125a6  test    rax, rax
0x1800125a9  jnz     short loc_1800125CA
0x1800125ab  lea     rdx, aMicrosoftOffic; "Microsoft Official Rights Template"
0x1800125b2  mov     rcx, rsi; Str
0x1800125b5  call    cs:__imp_wcsstr
0x1800125bb  test    rax, rax
0x1800125be  jnz     short loc_1800125CA
0x1800125c0  mov     ebx, 80070057h
0x1800125c5  jmp     loc_180012733
0x1800125ca  lea     r14, [rdi+2E8h]
0x1800125d1  mov     r8, r14; unsigned __int16 **
0x1800125d4  mov     rdx, rsi; unsigned __int16 *
0x1800125d7  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x1800125dc  mov     ebx, eax
0x1800125de  test    eax, eax
0x1800125e0  js      loc_180012733
0x1800125e6  mov     rcx, [r14]
0x1800125e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800125ed  xor     r14d, r14d
0x1800125f0  inc     rax
0x1800125f3  cmp     [rcx+rax*2], r14w
0x1800125f8  jnz     short loc_1800125F0
0x1800125fa  mov     [rdi+2F0h], eax
0x180012600  mov     dword ptr [rdi+2DCh], 1
0x18001260a  mov     rdx, [rsp+88h+arg_28]; struct CUser *
0x180012612  test    rdx, rdx
0x180012615  jz      short loc_180012629
0x180012617  mov     rcx, rdi; this
0x18001261a  call    ?CreateOwnerXML@CIssuanceLicense@@AEAAJPEAVCUser@@@Z; CIssuanceLicense::CreateOwnerXML(CUser *)
0x18001261f  mov     ebx, eax
0x180012621  test    eax, eax
0x180012623  js      loc_180012733
0x180012629  test    r12, r12
0x18001262c  jz      short loc_1800126A8
0x18001262e  test    r15, r15
0x180012631  jz      short loc_1800126A8
0x180012633  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x180012638  mov     rcx, r12; lpSystemTime
0x18001263b  call    cs:__imp_SystemTimeToFileTime
0x180012641  test    eax, eax
0x180012643  jnz     short loc_18001264F
0x180012645  mov     ebx, 8004CF51h
0x18001264a  jmp     loc_180012733
0x18001264f  lea     rdx, [rsp+88h+FileTime2]; lpFileTime
0x180012657  mov     rcx, r15; lpSystemTime
0x18001265a  call    cs:__imp_SystemTimeToFileTime
0x180012660  test    eax, eax
0x180012662  jz      short loc_180012645
0x180012664  lea     rdx, [rsp+88h+FileTime2]; lpFileTime2
0x18001266c  lea     rcx, [rsp+88h+FileTime]; lpFileTime1
0x180012671  call    cs:__imp_CompareFileTime
0x180012677  cmp     eax, 0FFFFFFFFh
0x18001267a  jnz     short loc_180012645
0x18001267c  movups  xmm0, xmmword ptr [r12]
0x180012681  movdqu  xmmword ptr [rdi+24Ch], xmm0
0x180012689  movups  xmm1, xmmword ptr [r15]
0x18001268d  movdqu  xmmword ptr [rdi+25Ch], xmm1
0x180012695  cmp     [rdi+2DCh], r14d
0x18001269c  jz      short loc_1800126A8
0x18001269e  mov     dword ptr [rdi+2E0h], 1
0x1800126a8  mov     rsi, [rsp+88h+arg_20]
0x1800126b0  test    rbp, rbp
0x1800126b3  jnz     short loc_1800126EF
0x1800126b5  test    rsi, rsi
0x1800126b8  jz      short loc_180012733
0x1800126ba  mov     rcx, [rdi+270h]; Block
0x1800126c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126c6  mov     [rdi+270h], r14
0x1800126cd  test    rsi, rsi
0x1800126d0  jz      short loc_18001270D
0x1800126d2  cmp     [rsi], r14w
0x1800126d6  jz      short loc_18001270D
0x1800126d8  lea     r8, [rdi+278h]; unsigned __int16 **
0x1800126df  mov     rdx, rsi; unsigned __int16 *
0x1800126e2  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x1800126e7  mov     ebx, eax
0x1800126e9  test    eax, eax
0x1800126eb  js      short loc_180012733
0x1800126ed  jmp     short loc_180012720
0x1800126ef  cmp     [rbp+0], r14w
0x1800126f4  jz      short loc_1800126BA
0x1800126f6  lea     r8, [rdi+270h]; unsigned __int16 **
0x1800126fd  mov     rdx, rbp; unsigned __int16 *
0x180012700  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x180012705  mov     ebx, eax
0x180012707  test    eax, eax
0x180012709  js      short loc_180012733
0x18001270b  jmp     short loc_1800126CD
0x18001270d  mov     rcx, [rdi+278h]; Block
0x180012714  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012719  mov     [rdi+278h], r14
0x180012720  cmp     [rdi+2DCh], r14d
0x180012727  jz      short loc_180012733
0x180012729  mov     dword ptr [rdi+2E0h], 1
0x180012733  mov     rcx, r13; lpCriticalSection
0x180012736  call    cs:__imp_LeaveCriticalSection
0x18001273c  mov     eax, ebx
0x18001273e  add     rsp, 48h
0x180012742  pop     r15
0x180012744  pop     r14
0x180012746  pop     r13
0x180012748  pop     r12
0x18001274a  pop     rdi
0x18001274b  pop     rsi
0x18001274c  pop     rbp
0x18001274d  pop     rbx
0x18001274e  retn
```
