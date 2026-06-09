# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140006810`
- end: `0x140006a3a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005ce8`
- `0x1400060b8`

## callees

- `0x140002190`
- `0x140006810`
- `0x140007708`
- `0x14000a914`
- `0x14000bc1c`
- `0x14000cdec`
- `0x14000cdfc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000693b`
- `KERNEL32!SetLastError` at `0x1400069d6`
- `KERNEL32!SetLastError` at `0x14000693b`
- `KERNEL32!SetLastError` at `0x1400069d6`
- `KERNEL32!CreateSemaphoreExW` at `0x1400068d4`
- `KERNEL32!CreateSemaphoreExW` at `0x140006977`
- `KERNEL32!CreateSemaphoreExW` at `0x1400068d4`
- `KERNEL32!CreateSemaphoreExW` at `0x140006977`
- `KERNEL32!CloseHandle` at `0x14000692a`
- `KERNEL32!CloseHandle` at `0x1400069ca`
- `KERNEL32!CloseHandle` at `0x14000692a`
- `KERNEL32!CloseHandle` at `0x1400069ca`
- `KERNEL32!GetLastError` at `0x140006910`
- `KERNEL32!GetLastError` at `0x14000691e`
- `KERNEL32!GetLastError` at `0x1400069b0`
- `KERNEL32!GetLastError` at `0x1400069bf`
- `KERNEL32!GetLastError` at `0x140006910`
- `KERNEL32!GetLastError` at `0x14000691e`
- `KERNEL32!GetLastError` at `0x1400069b0`
- `KERNEL32!GetLastError` at `0x1400069bf`

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
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
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
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140006810  mov     [rsp+arg_8], rbx
0x140006815  mov     [rsp+arg_10], rbp
0x14000681a  push    rsi
0x14000681b  push    rdi
0x14000681c  push    r12
0x14000681e  push    r14
0x140006820  push    r15
0x140006822  sub     rsp, 250h
0x140006829  mov     rax, cs:__security_cookie
0x140006830  xor     rax, rsp
0x140006833  mov     [rsp+278h+var_38], rax
0x14000683b  mov     rax, 0C000000000000000h
0x140006845  mov     rbp, r9
0x140006848  mov     r8, rdx
0x14000684b  mov     rbx, rcx
0x14000684e  test    rax, r9
0x140006851  jnz     loc_140006A21
0x140006857  xor     r12d, r12d
0x14000685a  lea     rax, [rsp+278h+Name]
0x14000685f  mov     ecx, 7FFFFFFEh
0x140006864  mov     edx, 104h
0x140006869  lea     esi, [r12+1]
0x14000686e  test    rcx, rcx
0x140006871  jz      short loc_140006891
0x140006873  movzx   r9d, word ptr [r8]
0x140006877  test    r9w, r9w
0x14000687b  jz      short loc_140006891
0x14000687d  mov     [rax], r9w
0x140006881  add     r8, 2
0x140006885  add     rax, 2
0x140006889  sub     rcx, rsi
0x14000688c  sub     rdx, rsi; unsigned __int64
0x14000688f  jnz     short loc_14000686E
0x140006891  test    rdx, rdx
0x140006894  lea     rcx, [rax-2]
0x140006898  lea     r8, aP0; "_p0"
0x14000689f  cmovnz  rcx, rax
0x1400068a3  mov     [rcx], r12w
0x1400068a7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400068ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400068b1  mov     edx, ebp
0x1400068b3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400068bb  and     edx, 7FFFFFFFh; lInitialCount
0x1400068c1  mov     [rsp+278h+dwFlags], r12d; int
0x1400068c6  mov     r8d, esi
0x1400068c9  lea     r9, [rsp+278h+Name]; lpName
0x1400068ce  cmova   r8d, edx; lMaximumCount
0x1400068d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400068d4  call    cs:__imp_CreateSemaphoreExW
0x1400068da  mov     r15, rax
0x1400068dd  test    rax, rax
0x1400068e0  jnz     short loc_140006910
0x1400068e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400068e7  mov     edi, eax
0x1400068e9  test    eax, eax
0x1400068eb  jns     short loc_140006944
0x1400068ed  mov     rcx, [rsp+278h]; this
0x1400068f5  lea     r8, aWil; "wil"
0x1400068fc  mov     r9d, eax; char *
0x1400068ff  mov     edx, 8Bh; void *
0x140006904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006909  mov     eax, edi
0x14000690b  jmp     loc_1400069E2
0x140006910  call    cs:__imp_GetLastError
0x140006916  mov     rdi, [rbx]
0x140006919  test    rdi, rdi
0x14000691c  jz      short loc_140006941
0x14000691e  call    cs:__imp_GetLastError
0x140006924  mov     rcx, rdi; hObject
0x140006927  mov     r14d, eax
0x14000692a  call    cs:__imp_CloseHandle
0x140006930  test    eax, eax
0x140006932  jz      loc_140006A27
0x140006938  mov     ecx, r14d; dwErrCode
0x14000693b  call    cs:__imp_SetLastError
0x140006941  mov     [rbx], r15
0x140006944  lea     r8, asc_140013250; "h"
0x14000694b  shr     rbp, 1Fh
0x14000694f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140006954  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006959  test    ebp, ebp
0x14000695b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140006963  lea     r9, [rsp+278h+Name]; lpName
0x140006968  mov     [rsp+278h+dwFlags], r12d; int
0x14000696d  cmovnz  esi, ebp
0x140006970  mov     edx, ebp; lInitialCount
0x140006972  mov     r8d, esi; lMaximumCount
0x140006975  xor     ecx, ecx; lpSemaphoreAttributes
0x140006977  call    cs:__imp_CreateSemaphoreExW
0x14000697d  mov     rsi, rax
0x140006980  test    rax, rax
0x140006983  jnz     short loc_1400069B0
0x140006985  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000698a  mov     ebx, eax
0x14000698c  test    eax, eax
0x14000698e  jns     short loc_1400069E0
0x140006990  mov     rcx, [rsp+278h]; this
0x140006998  lea     r8, aWil; "wil"
0x14000699f  mov     r9d, eax; char *
0x1400069a2  mov     edx, 90h; void *
0x1400069a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400069ac  mov     eax, ebx
0x1400069ae  jmp     short loc_1400069E2
0x1400069b0  call    cs:__imp_GetLastError
0x1400069b6  mov     rdi, [rbx+8]
0x1400069ba  test    rdi, rdi
0x1400069bd  jz      short loc_1400069DC
0x1400069bf  call    cs:__imp_GetLastError
0x1400069c5  mov     rcx, rdi; hObject
0x1400069c8  mov     ebp, eax
0x1400069ca  call    cs:__imp_CloseHandle
0x1400069d0  test    eax, eax
0x1400069d2  jz      short loc_140006A0E
0x1400069d4  mov     ecx, ebp; dwErrCode
0x1400069d6  call    cs:__imp_SetLastError
0x1400069dc  mov     [rbx+8], rsi
0x1400069e0  xor     eax, eax
0x1400069e2  mov     rcx, [rsp+278h+var_38]
0x1400069ea  xor     rcx, rsp; StackCookie
0x1400069ed  call    __security_check_cookie
0x1400069f2  lea     r11, [rsp+278h+var_28]
0x1400069fa  mov     rbx, [r11+38h]
0x1400069fe  mov     rbp, [r11+40h]
0x140006a02  mov     rsp, r11
0x140006a05  pop     r15
0x140006a07  pop     r14
0x140006a09  pop     r12
0x140006a0b  pop     rdi
0x140006a0c  pop     rsi
0x140006a0d  retn
0x140006a0e  mov     rcx, [rsp+278h]; this
0x140006a16  mov     edx, 0A0Bh; void *
0x140006a1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a21  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006a27  mov     rcx, [rsp+278h]; this
0x140006a2f  mov     edx, 0A0Bh; void *
0x140006a34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
