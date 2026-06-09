# CEXTLOG::FormatLogBuffer(IInetLogInformation *,char *,ulong *,_SYSTEMTIME *)

- ea: `0x180004160`
- end: `0x180004417`
- name: `?FormatLogBuffer@CEXTLOG@@MEAAHPEAVIInetLogInformation@@PEADPEAKPEAU_SYSTEMTIME@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(ASCLOG_DATETIME_CACHE **this, struct IInetLogInformation *, char *, unsigned int *, LPSYSTEMTIME lpSystemTime)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800022a8`
- `0x180004160`
- `0x180005394`
- `0x18000ec56`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `IisRTL!?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800041ab`
- `IisRTL!?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800041ab`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800041f3`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800043e1`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800041f3`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x1800043e1`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x180004222`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x180004222`
- `KERNEL32!SetLastError` at `0x1800043ba`
- `KERNEL32!SetLastError` at `0x1800043ba`
- `KERNEL32!GetLocalTime` at `0x1800041fe`
- `KERNEL32!GetLocalTime` at `0x1800043ec`
- `KERNEL32!GetLocalTime` at `0x1800041fe`
- `KERNEL32!GetLocalTime` at `0x1800043ec`

## pseudocode

```c
__int64 __fastcall CEXTLOG::FormatLogBuffer(
        ASCLOG_DATETIME_CACHE **this,
        struct IInetLogInformation *a2,
        char *a3,
        unsigned int *a4,
        LPSYSTEMTIME lpSystemTime)
{
  CACHED_DATETIME_FORMATS *v5; // r13
  unsigned int v10; // ebx
  ASCLOG_DATETIME_CACHE *v11; // rcx
  __int64 result; // rax
  unsigned int v13; // ebx
  char *v14; // rdi
  const char *v15; // rdx
  char *v16; // r13
  unsigned int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rbx
  char *v20; // rax
  const char *v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // ecx
  unsigned int v27; // ebx
  __int64 v28; // rdx
  char v29; // cl
  unsigned int v30; // eax
  unsigned int v31; // eax
  ASCLOG_DATETIME_CACHE *v32; // rcx
  unsigned int Size; // [rsp+30h] [rbp-41h] BYREF
  unsigned int Size_4; // [rsp+34h] [rbp-3Dh]
  char v35[11]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v36; // [rsp+43h] [rbp-2Eh]
  char Src[32]; // [rsp+58h] [rbp-19h] BYREF

  v5 = (CACHED_DATETIME_FORMATS *)(this + 198);
  Size = 0;
  EXTLOG_DATETIME_CACHE::SetSystemTime((EXTLOG_DATETIME_CACHE *)(this + 198), lpSystemTime);
  if ( *((_DWORD *)this + 394) != 1414 )
  {
    v10 = CEXTLOG::NormalFormatBuffer((CEXTLOG *)this, a2, a3, a4, lpSystemTime);
    if ( v10 && *((_DWORD *)this + 395) )
    {
      v11 = this[332];
      if ( v11 )
        ASCLOG_DATETIME_CACHE::SetLocalTime(v11, lpSystemTime);
      else
        GetLocalTime(lpSystemTime);
    }
    return v10;
  }
  v13 = 14;
  if ( *a4 < 0xE )
  {
LABEL_37:
    SetLastError(0x7Au);
    result = 0;
    *a4 = v13;
    return result;
  }
  CACHED_DATETIME_FORMATS::GetFormattedDateTime(v5, lpSystemTime, v35);
  *(_QWORD *)a3 = v36;
  a3[8] = 32;
  v14 = a3 + 9;
  v15 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 40LL))(
                        a2,
                        0,
                        &Size);
  v16 = "-";
  v17 = Size;
  if ( !Size )
  {
    v17 = 1;
    v15 = "-";
    Size = 1;
  }
  v18 = v17 + 14;
  Size_4 = v17 + 14;
  if ( v17 + 14 <= *a4 )
  {
    v19 = v17;
    memcpy_0(v14, v15, v17);
    v20 = &v14[v19];
    v18 = Size_4;
    *v20 = 32;
    v14 = v20 + 1;
  }
  v21 = (const char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 64LL))(
                        a2,
                        0,
                        &Size);
  v22 = Size;
  if ( !Size )
  {
    v22 = 1;
    v21 = "-";
    Size = 1;
  }
  v23 = v22 + v18;
  if ( v23 <= *a4 )
  {
    memcpy_0(v14, v21, v22);
    v24 = Size;
    v14[Size] = 32;
    v14 += v24 + 1;
  }
  v25 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 72LL))(
          a2,
          0,
          &Size);
  v26 = Size;
  if ( Size )
  {
    if ( Size <= 0x1000 && v23 + Size <= 0x2800 )
    {
      v16 = (char *)v25;
      goto LABEL_24;
    }
    v26 = 3;
    v16 = szDotDot;
  }
  else
  {
    v26 = 1;
  }
  Size = v26;
LABEL_24:
  v27 = v26 + v23;
  if ( v27 <= *a4 )
  {
    v28 = 0;
    if ( v26 )
    {
      do
      {
        v29 = v16[v28];
        *v14 = v29;
        if ( v29 == 32 )
          *v14 = 43;
        ++v14;
        v28 = (unsigned int)(v28 + 1);
      }
      while ( (unsigned int)v28 < Size );
    }
    *v14++ = 32;
  }
  v30 = (*(__int64 (__fastcall **)(struct IInetLogInformation *))(*(_QWORD *)a2 + 128LL))(a2);
  if ( v30 == 200 && v27 + 5 <= *a4 )
  {
    v13 = v27 + 3;
    *(_DWORD *)v14 = (_DWORD)szHTTPOk;
    v14[4] = byte_180017454;
  }
  else
  {
    v31 = FastDwToA(Src, v30);
    v13 = v31 + v27;
    Size = v31;
    if ( v13 <= *a4 )
    {
      memcpy_0(v14, Src, v31);
      v14 += Size;
    }
    *(_WORD *)v14 = 2573;
  }
  if ( v13 > *a4 )
    goto LABEL_37;
  *a4 = v13;
  if ( *((_DWORD *)this + 395) )
  {
    v32 = this[332];
    if ( v32 )
      ASCLOG_DATETIME_CACHE::SetLocalTime(v32, lpSystemTime);
    else
      GetLocalTime(lpSystemTime);
  }
  return 1;
}

```

## disassembly

```asm
0x180004160  push    rbp
0x180004162  push    rbx
0x180004163  push    rsi
0x180004164  push    rdi
0x180004165  push    r12
0x180004167  push    r13
0x180004169  push    r14
0x18000416b  push    r15
0x18000416d  lea     rbp, [rsp-17h]
0x180004172  sub     rsp, 88h
0x180004179  mov     rax, cs:__security_cookie
0x180004180  xor     rax, rsp
0x180004183  mov     [rbp+4Fh+var_48], rax
0x180004187  mov     r15, [rbp+4Fh+lpSystemTime]
0x18000418b  lea     r13, [rcx+630h]
0x180004192  mov     r12, rdx
0x180004195  mov     dword ptr [rbp+4Fh+Size], 0
0x18000419c  mov     r14, rcx
0x18000419f  mov     rdx, r15
0x1800041a2  mov     rcx, r13
0x1800041a5  mov     rsi, r9
0x1800041a8  mov     rdi, r8
0x1800041ab  call    cs:__imp_?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; EXTLOG_DATETIME_CACHE::SetSystemTime(_SYSTEMTIME *)
0x1800041b1  cmp     dword ptr [r14+628h], 586h
0x1800041bc  jz      short loc_18000420B
0x1800041be  mov     r9, rsi; unsigned int *
0x1800041c1  mov     [rsp+0C0h+var_A0], r15; struct _SYSTEMTIME *
0x1800041c6  mov     r8, rdi; char *
0x1800041c9  mov     rdx, r12; struct IInetLogInformation *
0x1800041cc  mov     rcx, r14; this
0x1800041cf  call    ?NormalFormatBuffer@CEXTLOG@@IEAAHPEAVIInetLogInformation@@PEADPEAKPEAU_SYSTEMTIME@@@Z; CEXTLOG::NormalFormatBuffer(IInetLogInformation *,char *,ulong *,_SYSTEMTIME *)
0x1800041d4  mov     ebx, eax
0x1800041d6  test    eax, eax
0x1800041d8  jz      short loc_180004204
0x1800041da  cmp     dword ptr [r14+62Ch], 0
0x1800041e2  jz      short loc_180004204
0x1800041e4  mov     rcx, [r14+0A60h]
0x1800041eb  test    rcx, rcx
0x1800041ee  jz      short loc_1800041FB
0x1800041f0  mov     rdx, r15
0x1800041f3  call    cs:__imp_?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; ASCLOG_DATETIME_CACHE::SetLocalTime(_SYSTEMTIME *)
0x1800041f9  jmp     short loc_180004204
0x1800041fb  mov     rcx, r15; lpSystemTime
0x1800041fe  call    cs:__imp_GetLocalTime
0x180004204  mov     eax, ebx
0x180004206  jmp     loc_1800043F7
0x18000420b  mov     ebx, 0Eh
0x180004210  cmp     ebx, [rsi]
0x180004212  ja      loc_1800043B5
0x180004218  lea     r8, [rbp+4Fh+var_88]
0x18000421c  mov     rdx, r15
0x18000421f  mov     rcx, r13
0x180004222  call    cs:__imp_?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedDateTime(_SYSTEMTIME const *,char *)
0x180004228  mov     rax, [rbp+4Fh+var_7D]
0x18000422c  lea     r8, [rbp+4Fh+Size]
0x180004230  mov     [rdi], rax
0x180004233  xor     edx, edx
0x180004235  mov     byte ptr [rdi+8], 20h ; ' '
0x180004239  mov     rcx, r12
0x18000423c  mov     rax, [r12]
0x180004240  add     rdi, 9
0x180004244  mov     rax, [rax+28h]
0x180004248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424d  mov     rdx, rax
0x180004250  lea     r13, Src; "-"
0x180004257  mov     eax, dword ptr [rbp+4Fh+Size]
0x18000425a  test    eax, eax
0x18000425c  jnz     short loc_180004267
0x18000425e  lea     eax, [rbx-0Dh]
0x180004261  mov     rdx, r13; Src
0x180004264  mov     dword ptr [rbp+4Fh+Size], eax
0x180004267  lea     ebx, [rax+0Eh]
0x18000426a  mov     dword ptr [rbp+4Fh+Size+4], ebx
0x18000426d  cmp     ebx, [rsi]
0x18000426f  ja      short loc_18000428C
0x180004271  mov     r8d, eax; Size
0x180004274  mov     rcx, rdi; void *
0x180004277  mov     ebx, eax
0x180004279  call    memcpy_0
0x18000427e  lea     rax, [rbx+rdi]
0x180004282  mov     ebx, dword ptr [rbp+4Fh+Size+4]
0x180004285  mov     byte ptr [rax], 20h ; ' '
0x180004288  lea     rdi, [rax+1]
0x18000428c  mov     rax, [r12]
0x180004290  lea     r8, [rbp+4Fh+Size]
0x180004294  xor     edx, edx
0x180004296  mov     rcx, r12
0x180004299  mov     rax, [rax+40h]
0x18000429d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a2  mov     rdx, rax
0x1800042a5  mov     eax, dword ptr [rbp+4Fh+Size]
0x1800042a8  test    eax, eax
0x1800042aa  jnz     short loc_1800042B7
0x1800042ac  mov     eax, 1
0x1800042b1  mov     rdx, r13; Src
0x1800042b4  mov     dword ptr [rbp+4Fh+Size], eax
0x1800042b7  add     ebx, eax
0x1800042b9  cmp     ebx, [rsi]
0x1800042bb  ja      short loc_1800042D5
0x1800042bd  mov     r8d, eax; Size
0x1800042c0  mov     rcx, rdi; void *
0x1800042c3  call    memcpy_0
0x1800042c8  mov     ecx, dword ptr [rbp+4Fh+Size]
0x1800042cb  mov     byte ptr [rcx+rdi], 20h ; ' '
0x1800042cf  inc     rdi
0x1800042d2  add     rdi, rcx
0x1800042d5  mov     rax, [r12]
0x1800042d9  lea     r8, [rbp+4Fh+Size]
0x1800042dd  xor     edx, edx
0x1800042df  mov     rcx, r12
0x1800042e2  mov     rax, [rax+48h]
0x1800042e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042eb  mov     ecx, dword ptr [rbp+4Fh+Size]
0x1800042ee  mov     rdx, rax
0x1800042f1  test    ecx, ecx
0x1800042f3  jnz     short loc_1800042FC
0x1800042f5  mov     ecx, 1
0x1800042fa  jmp     short loc_18000431F
0x1800042fc  cmp     ecx, 1000h
0x180004302  ja      short loc_180004313
0x180004304  lea     eax, [rbx+rcx]
0x180004307  cmp     eax, 2800h
0x18000430c  ja      short loc_180004313
0x18000430e  mov     r13, rdx
0x180004311  jmp     short loc_180004322
0x180004313  mov     ecx, 3
0x180004318  lea     r13, ?szDotDot@@3PADA; char near * szDotDot
0x18000431f  mov     dword ptr [rbp+4Fh+Size], ecx
0x180004322  add     ebx, ecx
0x180004324  cmp     ebx, [rsi]
0x180004326  ja      short loc_18000434C
0x180004328  xor     edx, edx
0x18000432a  test    ecx, ecx
0x18000432c  jz      short loc_180004346
0x18000432e  mov     cl, [rdx+r13]
0x180004332  mov     [rdi], cl
0x180004334  cmp     cl, 20h ; ' '
0x180004337  jnz     short loc_18000433C
0x180004339  mov     byte ptr [rdi], 2Bh ; '+'
0x18000433c  inc     rdi
0x18000433f  inc     edx
0x180004341  cmp     edx, dword ptr [rbp+4Fh+Size]
0x180004344  jb      short loc_18000432E
0x180004346  mov     byte ptr [rdi], 20h ; ' '
0x180004349  inc     rdi
0x18000434c  mov     rax, [r12]
0x180004350  mov     rcx, r12
0x180004353  mov     rax, [rax+80h]
0x18000435a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435f  cmp     eax, 0C8h
0x180004364  jnz     short loc_180004383
0x180004366  lea     ecx, [rbx+5]
0x180004369  cmp     ecx, [rsi]
0x18000436b  ja      short loc_180004383
0x18000436d  mov     eax, cs:?szHTTPOk@@3PADA; char near * szHTTPOk
0x180004373  add     ebx, 3
0x180004376  mov     [rdi], eax
0x180004378  mov     al, cs:byte_180017454
0x18000437e  mov     [rdi+4], al
0x180004381  jmp     short loc_1800043B1
0x180004383  mov     edx, eax; Value
0x180004385  lea     rcx, [rbp+4Fh+Src]; Buffer
0x180004389  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000438e  add     ebx, eax
0x180004390  mov     dword ptr [rbp+4Fh+Size], eax
0x180004393  cmp     ebx, [rsi]
0x180004395  ja      short loc_1800043AC
0x180004397  mov     r8d, eax; Size
0x18000439a  lea     rdx, [rbp+4Fh+Src]; Src
0x18000439e  mov     rcx, rdi; void *
0x1800043a1  call    memcpy_0
0x1800043a6  mov     eax, dword ptr [rbp+4Fh+Size]
0x1800043a9  add     rdi, rax
0x1800043ac  mov     word ptr [rdi], 0A0Dh
0x1800043b1  cmp     ebx, [rsi]
0x1800043b3  jbe     short loc_1800043C6
0x1800043b5  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1800043ba  call    cs:__imp_SetLastError
0x1800043c0  xor     eax, eax
0x1800043c2  mov     [rsi], ebx
0x1800043c4  jmp     short loc_1800043F7
0x1800043c6  mov     [rsi], ebx
0x1800043c8  cmp     dword ptr [r14+62Ch], 0
0x1800043d0  jz      short loc_1800043F2
0x1800043d2  mov     rcx, [r14+0A60h]
0x1800043d9  test    rcx, rcx
0x1800043dc  jz      short loc_1800043E9
0x1800043de  mov     rdx, r15
0x1800043e1  call    cs:__imp_?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; ASCLOG_DATETIME_CACHE::SetLocalTime(_SYSTEMTIME *)
0x1800043e7  jmp     short loc_1800043F2
0x1800043e9  mov     rcx, r15; lpSystemTime
0x1800043ec  call    cs:__imp_GetLocalTime
0x1800043f2  mov     eax, 1
0x1800043f7  mov     rcx, [rbp+4Fh+var_48]
0x1800043fb  xor     rcx, rsp; StackCookie
0x1800043fe  call    __security_check_cookie
0x180004403  add     rsp, 88h
0x18000440a  pop     r15
0x18000440c  pop     r14
0x18000440e  pop     r13
0x180004410  pop     r12
0x180004412  pop     rdi
0x180004413  pop     rsi
0x180004414  pop     rbx
0x180004415  pop     rbp
0x180004416  retn
```
