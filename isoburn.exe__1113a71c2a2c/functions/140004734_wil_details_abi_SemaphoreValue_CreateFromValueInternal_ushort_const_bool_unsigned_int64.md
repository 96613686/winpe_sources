# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004734`
- end: `0x140004941`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003ecc`

## callees

- `0x140001fa0`
- `0x140004734`
- `0x1400056c0`
- `0x140007d5c`
- `0x140008ec8`
- `0x140009a1c`
- `0x140009a2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000482d`
- `KERNEL32!GetLastError` at `0x14000483b`
- `KERNEL32!GetLastError` at `0x1400048b7`
- `KERNEL32!GetLastError` at `0x1400048c6`
- `KERNEL32!GetLastError` at `0x14000482d`
- `KERNEL32!GetLastError` at `0x14000483b`
- `KERNEL32!GetLastError` at `0x1400048b7`
- `KERNEL32!GetLastError` at `0x1400048c6`
- `KERNEL32!SetLastError` at `0x140004858`
- `KERNEL32!SetLastError` at `0x1400048dd`
- `KERNEL32!SetLastError` at `0x140004858`
- `KERNEL32!SetLastError` at `0x1400048dd`
- `KERNEL32!CloseHandle` at `0x140004847`
- `KERNEL32!CloseHandle` at `0x1400048d1`
- `KERNEL32!CloseHandle` at `0x140004847`
- `KERNEL32!CloseHandle` at `0x1400048d1`
- `KERNEL32!CreateSemaphoreExW` at `0x1400047f8`
- `KERNEL32!CreateSemaphoreExW` at `0x140004894`
- `KERNEL32!CreateSemaphoreExW` at `0x1400047f8`
- `KERNEL32!CreateSemaphoreExW` at `0x140004894`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004734  mov     [rsp+arg_8], rbx
0x140004739  mov     [rsp+arg_10], rbp
0x14000473e  push    rsi
0x14000473f  push    rdi
0x140004740  push    r12
0x140004742  push    r14
0x140004744  push    r15
0x140004746  sub     rsp, 250h
0x14000474d  mov     rax, cs:__security_cookie
0x140004754  xor     rax, rsp
0x140004757  mov     [rsp+278h+var_38], rax
0x14000475f  mov     rax, 0C000000000000000h
0x140004769  mov     rbp, r9
0x14000476c  mov     r8, rdx
0x14000476f  mov     rdi, rcx
0x140004772  test    rax, r9
0x140004775  jnz     loc_140004928
0x14000477b  xor     r12d, r12d
0x14000477e  lea     rax, [rsp+278h+Name]
0x140004783  mov     ecx, 7FFFFFFEh
0x140004788  mov     edx, 104h
0x14000478d  lea     esi, [r12+1]
0x140004792  test    rcx, rcx
0x140004795  jz      short loc_1400047B5
0x140004797  movzx   r9d, word ptr [r8]
0x14000479b  test    r9w, r9w
0x14000479f  jz      short loc_1400047B5
0x1400047a1  mov     [rax], r9w
0x1400047a5  add     r8, 2
0x1400047a9  add     rax, 2
0x1400047ad  sub     rcx, rsi
0x1400047b0  sub     rdx, rsi; unsigned __int64
0x1400047b3  jnz     short loc_140004792
0x1400047b5  test    rdx, rdx
0x1400047b8  lea     rcx, [rax-2]
0x1400047bc  lea     r8, aP0; "_p0"
0x1400047c3  cmovnz  rcx, rax
0x1400047c7  mov     [rcx], r12w
0x1400047cb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400047d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400047d5  mov     edx, ebp
0x1400047d7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400047df  and     edx, 7FFFFFFFh; lInitialCount
0x1400047e5  mov     [rsp+278h+dwFlags], r12d; int
0x1400047ea  mov     r8d, esi
0x1400047ed  lea     r9, [rsp+278h+Name]; lpName
0x1400047f2  cmova   r8d, edx; lMaximumCount
0x1400047f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1400047f8  call    cs:__imp_CreateSemaphoreExW
0x1400047fe  mov     r15, rax
0x140004801  test    rax, rax
0x140004804  jnz     short loc_14000482D
0x140004806  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000480b  mov     ebx, eax
0x14000480d  test    eax, eax
0x14000480f  jns     short loc_140004861
0x140004811  mov     edx, 8Bh; void *
0x140004816  mov     rcx, [rsp+278h]; this
0x14000481e  mov     r9d, ebx; char *
0x140004821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004826  mov     eax, ebx
0x140004828  jmp     loc_1400048E9
0x14000482d  call    cs:__imp_GetLastError
0x140004833  mov     rbx, [rdi]
0x140004836  test    rbx, rbx
0x140004839  jz      short loc_14000485E
0x14000483b  call    cs:__imp_GetLastError
0x140004841  mov     rcx, rbx; hObject
0x140004844  mov     r14d, eax
0x140004847  call    cs:__imp_CloseHandle
0x14000484d  test    eax, eax
0x14000484f  jz      loc_14000492E
0x140004855  mov     ecx, r14d; dwErrCode
0x140004858  call    cs:__imp_SetLastError
0x14000485e  mov     [rdi], r15
0x140004861  lea     r8, asc_140012488; "h"
0x140004868  shr     rbp, 1Fh
0x14000486c  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004871  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004876  test    ebp, ebp
0x140004878  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004880  lea     r9, [rsp+278h+Name]; lpName
0x140004885  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x14000488a  cmovnz  esi, ebp
0x14000488d  mov     edx, ebp; lInitialCount
0x14000488f  mov     r8d, esi; lMaximumCount
0x140004892  xor     ecx, ecx; lpSemaphoreAttributes
0x140004894  call    cs:__imp_CreateSemaphoreExW
0x14000489a  mov     rsi, rax
0x14000489d  test    rax, rax
0x1400048a0  jnz     short loc_1400048B7
0x1400048a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400048a7  mov     ebx, eax
0x1400048a9  test    eax, eax
0x1400048ab  jns     short loc_1400048E7
0x1400048ad  mov     edx, 90h
0x1400048b2  jmp     loc_140004816
0x1400048b7  call    cs:__imp_GetLastError
0x1400048bd  mov     rbx, [rdi+8]
0x1400048c1  test    rbx, rbx
0x1400048c4  jz      short loc_1400048E3
0x1400048c6  call    cs:__imp_GetLastError
0x1400048cc  mov     rcx, rbx; hObject
0x1400048cf  mov     ebp, eax
0x1400048d1  call    cs:__imp_CloseHandle
0x1400048d7  test    eax, eax
0x1400048d9  jz      short loc_140004915
0x1400048db  mov     ecx, ebp; dwErrCode
0x1400048dd  call    cs:__imp_SetLastError
0x1400048e3  mov     [rdi+8], rsi
0x1400048e7  xor     eax, eax
0x1400048e9  mov     rcx, [rsp+278h+var_38]
0x1400048f1  xor     rcx, rsp; StackCookie
0x1400048f4  call    __security_check_cookie
0x1400048f9  lea     r11, [rsp+278h+var_28]
0x140004901  mov     rbx, [r11+38h]
0x140004905  mov     rbp, [r11+40h]
0x140004909  mov     rsp, r11
0x14000490c  pop     r15
0x14000490e  pop     r14
0x140004910  pop     r12
0x140004912  pop     rdi
0x140004913  pop     rsi
0x140004914  retn
0x140004915  mov     rcx, [rsp+278h]; this
0x14000491d  mov     edx, 0A0Bh; void *
0x140004922  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004928  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000492e  mov     rcx, [rsp+278h]; this
0x140004936  mov     edx, 0A0Bh; void *
0x14000493b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
