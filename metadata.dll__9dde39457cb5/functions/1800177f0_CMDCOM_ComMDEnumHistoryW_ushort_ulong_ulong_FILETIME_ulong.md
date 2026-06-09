# CMDCOM::ComMDEnumHistoryW(ushort *,ulong *,ulong *,_FILETIME *,ulong)

- ea: `0x1800177f0`
- end: `0x180017a2f`
- name: `?ComMDEnumHistoryW@CMDCOM@@UEAAJPEAGPEAK1PEAU_FILETIME@@K@Z`
- size: `575`
- prototype: `int(CMDCOM *__hidden this, unsigned __int16 *, unsigned int *, unsigned int *, struct _FILETIME *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800177f0`
- `0x18001d91c`
- `0x1800309d0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800179ac`
- `msvcrt!wcscpy_s` at `0x1800179ac`
- `KERNEL32!WaitForSingleObject` at `0x18001788f`
- `KERNEL32!WaitForSingleObject` at `0x18001788f`
- `KERNEL32!ReleaseSemaphore` at `0x1800179e5`
- `KERNEL32!ReleaseSemaphore` at `0x1800179e5`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001790d`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017920`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017935`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001794a`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001790d`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017920`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017935`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001794a`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x1800178c7`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x1800178e2`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x1800178c7`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x1800178e2`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001795c`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001795c`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001782b`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001782b`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800179ef`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800179fd`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800179ef`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800179fd`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDEnumHistoryW(
        CMDCOM *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        struct _FILETIME *a5,
        unsigned int a6)
{
  int v9; // ebx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rax
  int v12; // ebx
  int v13; // eax
  const WCHAR *StrW; // rax
  unsigned int v16; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-85h] BYREF
  struct _FILETIME v18; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v19[128]; // [rsp+40h] [rbp-79h] BYREF

  STRAU::STRAU((STRAU *)v19);
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v9 = 0;
    while ( a2[v9] )
    {
      if ( ++v9 >= 100 )
      {
        if ( v9 == 100 )
          goto LABEL_33;
        break;
      }
    }
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
    v10 = -1;
    if ( *a2 )
    {
      if ( !STRAU::Copy((STRAU *)v19, a2) )
        goto LABEL_16;
      if ( (unsigned int)(v9 - 1) > 0x62 )
      {
        v12 = -2147024872;
        goto LABEL_32;
      }
      if ( a2[v9 - 1] == 92 )
      {
LABEL_21:
        if ( STRAU::Append((STRAU *)v19, g_wszRealFileNameWithoutPathWithoutExtension)
          && STRAU::Append((STRAU *)v19, L"_??????????_??????????")
          && STRAU::Append((STRAU *)v19, g_wszRealFileNameExtension) )
        {
          StrW = STRAU::QueryStrW((STRAU *)v19);
          v12 = EnumFiles(StrW, a6, &v16, &v17, &v18);
          if ( v12 >= 0 )
          {
            if ( !*a2 )
            {
              do
                ++v10;
              while ( g_wszHistoryFileDir[v10] );
              if ( v10 >= 0x64 )
              {
                v12 = -2147024774;
                goto LABEL_32;
              }
              wcscpy_s(a2, 0x64u, g_wszHistoryFileDir);
            }
            *a3 = v16;
            *a4 = v17;
            *a5 = v18;
          }
LABEL_32:
          ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
          STRAU::~STRAU((STRAU *)v19);
          return (unsigned int)v12;
        }
LABEL_16:
        v12 = -2147024888;
        goto LABEL_32;
      }
      v13 = STRAU::Append((STRAU *)v19, L"\\");
    }
    else
    {
      v11 = -1;
      do
        ++v11;
      while ( g_wszHistoryFileDir[v11] );
      if ( v11 > 0x63 )
      {
        v12 = -2147024809;
        goto LABEL_32;
      }
      v13 = STRAU::Copy((STRAU *)v19, g_wszHistoryFileDir);
    }
    if ( !v13 )
      goto LABEL_16;
    goto LABEL_21;
  }
LABEL_33:
  STRAU::~STRAU((STRAU *)v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800177f0  mov     [rsp-8+arg_0], rbx
0x1800177f5  push    rbp
0x1800177f6  push    rsi
0x1800177f7  push    rdi
0x1800177f8  push    r12
0x1800177fa  push    r13
0x1800177fc  push    r14
0x1800177fe  push    r15
0x180017800  lea     rbp, [rsp-17h]
0x180017805  sub     rsp, 0D0h
0x18001780c  mov     rax, cs:__security_cookie
0x180017813  xor     rax, rsp
0x180017816  mov     [rbp+47h+var_40], rax
0x18001781a  mov     r12, [rbp+47h+arg_20]
0x18001781e  lea     rcx, [rbp+47h+var_C0]
0x180017822  mov     r15, r9
0x180017825  mov     r14, r8
0x180017828  mov     rdi, rdx
0x18001782b  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180017831  xor     r13d, r13d
0x180017834  mov     [rsp+100h+var_D0], r13d
0x180017839  mov     [rsp+100h+var_CC], r13d
0x18001783e  mov     qword ptr [rsp+100h+var_C8.dwLowDateTime], r13
0x180017843  test    rdi, rdi
0x180017846  jz      loc_1800179F9
0x18001784c  test    r14, r14
0x18001784f  jz      loc_1800179F9
0x180017855  test    r15, r15
0x180017858  jz      loc_1800179F9
0x18001785e  test    r12, r12
0x180017861  jz      loc_1800179F9
0x180017867  mov     ebx, r13d
0x18001786a  mov     eax, ebx
0x18001786c  cmp     [rdi+rax*2], r13w
0x180017871  jz      short loc_180017885
0x180017873  inc     ebx
0x180017875  mov     eax, ebx
0x180017877  cmp     ebx, 64h ; 'd'
0x18001787a  jl      short loc_18001786A
0x18001787c  cmp     eax, 64h ; 'd'
0x18001787f  jz      loc_1800179F9
0x180017885  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x18001788c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001788f  call    cs:__imp_WaitForSingleObject
0x180017895  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017899  cmp     [rdi], r13w
0x18001789d  jnz     short loc_1800178DB
0x18001789f  mov     rdx, cs:?g_wszHistoryFileDir@@3PEAGEA; ushort * g_wszHistoryFileDir
0x1800178a6  mov     rax, rsi
0x1800178a9  inc     rax
0x1800178ac  cmp     [rdx+rax*2], r13w
0x1800178b1  jnz     short loc_1800178A9
0x1800178b3  cmp     rax, 63h ; 'c'
0x1800178b7  jbe     short loc_1800178C3
0x1800178b9  mov     ebx, 80070057h
0x1800178be  jmp     loc_1800179D7
0x1800178c3  lea     rcx, [rbp+47h+var_C0]
0x1800178c7  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x1800178cd  test    eax, eax
0x1800178cf  jnz     short loc_180017915
0x1800178d1  mov     ebx, 80070008h
0x1800178d6  jmp     loc_1800179D7
0x1800178db  mov     rdx, rdi
0x1800178de  lea     rcx, [rbp+47h+var_C0]
0x1800178e2  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x1800178e8  test    eax, eax
0x1800178ea  jz      short loc_1800178D1
0x1800178ec  lea     eax, [rbx-1]
0x1800178ef  cmp     eax, 62h ; 'b'
0x1800178f2  ja      loc_1800179D2
0x1800178f8  mov     eax, ebx
0x1800178fa  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180017900  jz      short loc_180017915
0x180017902  lea     rdx, asc_180033DA8; "\\"
0x180017909  lea     rcx, [rbp+47h+var_C0]
0x18001790d  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180017913  jmp     short loc_1800178CD
0x180017915  mov     rdx, cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA; ushort * g_wszRealFileNameWithoutPathWithoutExtension
0x18001791c  lea     rcx, [rbp+47h+var_C0]
0x180017920  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180017926  test    eax, eax
0x180017928  jz      short loc_1800178D1
0x18001792a  lea     rdx, asc_18003A640; "_??????????_??????????"
0x180017931  lea     rcx, [rbp+47h+var_C0]
0x180017935  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x18001793b  test    eax, eax
0x18001793d  jz      short loc_1800178D1
0x18001793f  mov     rdx, cs:?g_wszRealFileNameExtension@@3PEAGEA; ushort * g_wszRealFileNameExtension
0x180017946  lea     rcx, [rbp+47h+var_C0]
0x18001794a  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180017950  test    eax, eax
0x180017952  jz      loc_1800178D1
0x180017958  lea     rcx, [rbp+47h+var_C0]
0x18001795c  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x180017962  mov     edx, [rbp+47h+arg_28]; unsigned int
0x180017965  lea     r9, [rsp+100h+var_CC]; unsigned int *
0x18001796a  mov     rcx, rax; lpFileName
0x18001796d  lea     r8, [rsp+100h+var_D0]; unsigned int *
0x180017972  lea     rax, [rsp+100h+var_C8]
0x180017977  mov     [rsp+100h+var_E0], rax; struct _FILETIME *
0x18001797c  call    ?EnumFiles@@YAJPEAGKPEAK1PEAU_FILETIME@@@Z; EnumFiles(ushort *,ulong,ulong *,ulong *,_FILETIME *)
0x180017981  mov     ebx, eax
0x180017983  test    eax, eax
0x180017985  js      short loc_1800179D7
0x180017987  cmp     [rdi], r13w
0x18001798b  jnz     short loc_1800179B2
0x18001798d  mov     r8, cs:?g_wszHistoryFileDir@@3PEAGEA; Source
0x180017994  inc     rsi
0x180017997  cmp     [r8+rsi*2], r13w
0x18001799c  jnz     short loc_180017994
0x18001799e  cmp     rsi, 64h ; 'd'
0x1800179a2  jnb     short loc_1800179CB
0x1800179a4  mov     edx, 64h ; 'd'; SizeInWords
0x1800179a9  mov     rcx, rdi; Destination
0x1800179ac  call    cs:__imp_wcscpy_s
0x1800179b2  mov     eax, [rsp+100h+var_D0]
0x1800179b6  mov     [r14], eax
0x1800179b9  mov     eax, [rsp+100h+var_CC]
0x1800179bd  mov     [r15], eax
0x1800179c0  mov     rax, qword ptr [rsp+100h+var_C8.dwLowDateTime]
0x1800179c5  mov     [r12], rax
0x1800179c9  jmp     short loc_1800179D7
0x1800179cb  mov     ebx, 8007007Ah
0x1800179d0  jmp     short loc_1800179D7
0x1800179d2  mov     ebx, 80070018h
0x1800179d7  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x1800179de  xor     r8d, r8d; lpPreviousCount
0x1800179e1  lea     edx, [r8+1]; lReleaseCount
0x1800179e5  call    cs:__imp_ReleaseSemaphore
0x1800179eb  lea     rcx, [rbp+47h+var_C0]
0x1800179ef  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x1800179f5  mov     eax, ebx
0x1800179f7  jmp     short loc_180017A08
0x1800179f9  lea     rcx, [rbp+47h+var_C0]
0x1800179fd  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180017a03  mov     eax, 80070057h
0x180017a08  mov     rcx, [rbp+47h+var_40]
0x180017a0c  xor     rcx, rsp; StackCookie
0x180017a0f  call    __security_check_cookie
0x180017a14  mov     rbx, [rsp+100h+arg_0]
0x180017a1c  add     rsp, 0D0h
0x180017a23  pop     r15
0x180017a25  pop     r14
0x180017a27  pop     r13
0x180017a29  pop     r12
0x180017a2b  pop     rdi
0x180017a2c  pop     rsi
0x180017a2d  pop     rbp
0x180017a2e  retn
```
