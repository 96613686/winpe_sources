# CModuleProcessName::Init(ushort const *)

- ea: `0x18001ab98`
- end: `0x18001adc8`
- name: `?Init@CModuleProcessName@@AEAAJPEBG@Z`
- size: `560`
- prototype: `__int64 __fastcall(CModuleProcessName *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002331c`

## callees

- `0x180019b40`
- `0x18001ab98`
- `0x1800246e8`
- `0x180025c18`
- `0x180031670`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001acdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001acdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001abe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001abe6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001adb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001adb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac7f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ac7f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001abf9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001abf9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001ad4b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001ad4b`

## pseudocode

```c
__int64 __fastcall CModuleProcessName::Init(CModuleProcessName *this, const unsigned __int16 *a2)
{
  LPWSTR FileNameW; // rax
  const WCHAR *v3; // rdi
  int v4; // ebx
  char v5; // bp
  int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rax
  const unsigned __int16 **v11; // rsi
  unsigned int i; // ebx
  WCHAR Filename[264]; // [rsp+20h] [rbp-258h] BYREF

  if ( dword_180297758 )
  {
    if ( dword_180297754 )
    {
      return 0;
    }
    else if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      FileNameW = PathFindFileNameW(Filename);
      v3 = FileNameW;
      if ( !FileNameW || (v4 = 0, !*FileNameW) )
      {
        v3 = 0;
        v4 = -2147467259;
      }
      if ( v3 )
      {
        v5 = 0;
        if ( (unsigned int)IsSpartanApp() )
        {
          v3 = L"microsoftedge.exe";
          byte_180297750 = 0;
        }
        if ( (unsigned int)IsSpartanApp() || !IEIsWebPlatformProcess() )
        {
          v6 = 0;
          for ( i = 0; i < 0x34; ++i )
          {
            if ( !StrCmpICW(v3, (LPCWSTR)(&FEATURECONFIG::g_rgszProcessNames)[i]) )
            {
              v11 = (const unsigned __int16 **)(&FEATURECONFIG::g_rgszProcessNames)[i];
              v6 = i + 2;
              if ( !v11 )
                break;
              v4 = 0;
              goto LABEL_21;
            }
          }
        }
        else
        {
          v6 = 1;
          byte_180297750 = 0;
        }
        v7 = -1;
        do
          ++v7;
        while ( v3[v7] );
        v8 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v8 >= (unsigned int)v7 )
        {
          v9 = v7 + 1;
          v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v8);
          v11 = (const unsigned __int16 **)v10;
          if ( v10 )
          {
            v4 = StringCchCopyW(v10, v9, v3);
            if ( v4 < 0 )
            {
              LocalFree(v11);
              v11 = 0;
            }
            else
            {
              v5 = 1;
            }
            if ( v4 >= 0 )
            {
LABEL_21:
              EnterCriticalSection(&CriticalSection);
              if ( !dword_180297754 )
              {
                byte_180297751 = v5;
                v5 = 0;
                dword_180297754 = 1;
                dword_180297740 = v6;
                hMem = v11;
              }
              LeaveCriticalSection(&CriticalSection);
              if ( v5 )
                LocalFree(v11);
            }
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
        else
        {
          return (unsigned int)-2147024362;
        }
      }
    }
    else
    {
      return (unsigned int)HRESULTFromLastErrorError();
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ab98  push    rbx
0x18001ab9a  push    rbp
0x18001ab9b  push    rsi
0x18001ab9c  push    rdi
0x18001ab9d  push    r12
0x18001ab9f  push    r14
0x18001aba1  push    r15
0x18001aba3  sub     rsp, 240h
0x18001abaa  mov     rax, cs:__security_cookie
0x18001abb1  xor     rax, rsp
0x18001abb4  mov     [rsp+278h+var_48], rax
0x18001abbc  xor     r15d, r15d
0x18001abbf  cmp     cs:dword_180297758, r15d
0x18001abc6  jz      loc_18001AD6F
0x18001abcc  cmp     cs:dword_180297754, r15d
0x18001abd3  jnz     loc_18001ADC0
0x18001abd9  mov     r8d, 104h; nSize
0x18001abdf  lea     rdx, [rsp+278h+Filename]; lpFilename
0x18001abe4  xor     ecx, ecx; hModule
0x18001abe6  call    cs:__imp_GetModuleFileNameW
0x18001abec  test    eax, eax
0x18001abee  jz      loc_18001AD83
0x18001abf4  lea     rcx, [rsp+278h+Filename]; pszPath
0x18001abf9  call    cs:__imp_PathFindFileNameW
0x18001abff  mov     rdi, rax
0x18001ac02  test    rax, rax
0x18001ac05  jz      loc_18001AD8F
0x18001ac0b  mov     ebx, r15d
0x18001ac0e  cmp     [rax], r15w
0x18001ac12  jz      loc_18001AD8F
0x18001ac18  test    rdi, rdi
0x18001ac1b  jz      loc_18001ACAF
0x18001ac21  mov     bpl, r15b
0x18001ac24  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x18001ac29  test    eax, eax
0x18001ac2b  jnz     loc_18001AD9C
0x18001ac31  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x18001ac36  test    eax, eax
0x18001ac38  jnz     loc_18001AD2B
0x18001ac3e  call    ?IEIsWebPlatformProcess@@YA_NXZ; IEIsWebPlatformProcess(void)
0x18001ac43  test    al, al
0x18001ac45  jz      loc_18001AD2B
0x18001ac4b  mov     r14d, 1
0x18001ac51  mov     cs:byte_180297750, r15b
0x18001ac58  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ac5c  inc     rax
0x18001ac5f  cmp     [rdi+rax*2], r15w
0x18001ac64  jnz     short loc_18001AC5C
0x18001ac66  lea     ecx, [rax+1]
0x18001ac69  cmp     ecx, eax
0x18001ac6b  jnb     short loc_18001AC74
0x18001ac6d  mov     ebx, 80070216h
0x18001ac72  jmp     short loc_18001ACAF
0x18001ac74  mov     ebx, ecx
0x18001ac76  lea     rdx, [rcx+rcx]; uBytes
0x18001ac7a  mov     ecx, 40h ; '@'; uFlags
0x18001ac7f  call    cs:__imp_LocalAlloc
0x18001ac85  mov     rsi, rax
0x18001ac88  test    rax, rax
0x18001ac8b  jz      loc_18001AD79
0x18001ac91  mov     r8, rdi; unsigned __int16 *
0x18001ac94  mov     edx, ebx; unsigned __int64
0x18001ac96  mov     rcx, rax; unsigned __int16 *
0x18001ac99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac9e  mov     ebx, eax
0x18001aca0  test    eax, eax
0x18001aca2  js      loc_18001ADAF
0x18001aca8  mov     bpl, 1
0x18001acab  test    ebx, ebx
0x18001acad  jns     short loc_18001ACD6
0x18001acaf  mov     eax, ebx
0x18001acb1  mov     rcx, [rsp+278h+var_48]
0x18001acb9  xor     rcx, rsp; StackCookie
0x18001acbc  call    __security_check_cookie
0x18001acc1  add     rsp, 240h
0x18001acc8  pop     r15
0x18001acca  pop     r14
0x18001accc  pop     r12
0x18001acce  pop     rdi
0x18001accf  pop     rsi
0x18001acd0  pop     rbp
0x18001acd1  pop     rbx
0x18001acd2  retn
0x18001acd3  mov     ebx, r15d
0x18001acd6  lea     rcx, CriticalSection; lpCriticalSection
0x18001acdd  call    cs:__imp_EnterCriticalSection
0x18001ace3  cmp     cs:dword_180297754, r15d
0x18001acea  jnz     short loc_18001AD0E
0x18001acec  mov     cs:byte_180297751, bpl
0x18001acf3  mov     bpl, r15b
0x18001acf6  mov     cs:dword_180297754, 1
0x18001ad00  mov     cs:dword_180297740, r14d
0x18001ad07  mov     cs:hMem, rsi
0x18001ad0e  lea     rcx, CriticalSection; lpCriticalSection
0x18001ad15  call    cs:__imp_LeaveCriticalSection
0x18001ad1b  test    bpl, bpl
0x18001ad1e  jz      short loc_18001ACAF
0x18001ad20  mov     rcx, rsi; hMem
0x18001ad23  call    cs:__imp_LocalFree
0x18001ad29  jmp     short loc_18001ACAF
0x18001ad2b  mov     r14d, r15d
0x18001ad2e  mov     ebx, r15d
0x18001ad31  cmp     ebx, 34h ; '4'
0x18001ad34  jnb     loc_18001AC58
0x18001ad3a  movsxd  rsi, ebx
0x18001ad3d  lea     r12, ?g_rgszProcessNames@FEATURECONFIG@@3QBQEBGB; ushort const * const near * const FEATURECONFIG::g_rgszProcessNames
0x18001ad44  mov     rcx, rdi; pszStr1
0x18001ad47  mov     rdx, [r12+rsi*8]; pszStr2
0x18001ad4b  call    cs:__imp_StrCmpICW
0x18001ad51  test    eax, eax
0x18001ad53  jz      short loc_18001AD59
0x18001ad55  inc     ebx
0x18001ad57  jmp     short loc_18001AD31
0x18001ad59  mov     rsi, [r12+rsi*8]
0x18001ad5d  lea     r14d, [rbx+2]
0x18001ad61  test    rsi, rsi
0x18001ad64  jz      loc_18001AC58
0x18001ad6a  jmp     loc_18001ACD3
0x18001ad6f  mov     ebx, 80004005h
0x18001ad74  jmp     loc_18001ACAF
0x18001ad79  mov     ebx, 8007000Eh
0x18001ad7e  jmp     loc_18001ACAF
0x18001ad83  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18001ad88  mov     ebx, eax
0x18001ad8a  jmp     loc_18001ACAF
0x18001ad8f  mov     rdi, r15
0x18001ad92  mov     ebx, 80004005h
0x18001ad97  jmp     loc_18001AC18
0x18001ad9c  lea     rdi, aMicrosoftedgeE; "microsoftedge.exe"
0x18001ada3  mov     cs:byte_180297750, r15b
0x18001adaa  jmp     loc_18001AC31
0x18001adaf  mov     rcx, rsi; hMem
0x18001adb2  call    cs:__imp_LocalFree
0x18001adb8  mov     rsi, r15
0x18001adbb  jmp     loc_18001ACAB
0x18001adc0  mov     ebx, r15d
0x18001adc3  jmp     loc_18001ACAF
```
