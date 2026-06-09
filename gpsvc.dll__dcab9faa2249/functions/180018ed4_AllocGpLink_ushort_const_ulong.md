# AllocGpLink(ushort const *,ulong)

- ea: `0x180018ed4`
- end: `0x180019182`
- name: `?AllocGpLink@@YAPEAU_GPLINK@@PEBGK@Z`
- size: `686`
- prototype: `unsigned __int16 **__fastcall(const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800167b0`
- `0x18003e060`

## callees

- `0x18000a504`
- `0x180018ed4`
- `0x18002c690`
- `0x180049bc0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001908e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001915d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001908e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001915d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ff1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f67`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018f81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018fe3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018f81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018fe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001909f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001909f`

## string_xrefs

- `0x180019124`: `AllocGpLink: pwszGPO is null`
- `0x180019149`: `AllocGpLink: pwszGPO is null`
- `0x1800190c9`: `AllocGpLink: pwszPath is null`
- `0x1800190f9`: `AllocGpLink: pwszPath is null`
- `0x180019045`: `AllocGpLink: GPO %s has enforced link.`
- `0x18001906d`: `AllocGpLink: GPO %s has enforced link.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int16 **__fastcall AllocGpLink(const unsigned __int16 *a1, char a2)
{
  unsigned __int64 v4; // r14
  __int64 cchCount2; // rdi
  DWORD LastError; // ebx
  unsigned __int64 v7; // rcx
  unsigned __int16 **v8; // rax
  unsigned __int16 **v9; // rdi
  DWORD v10; // ecx
  unsigned __int16 *v11; // rax
  unsigned __int16 **v13; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T uBytes; // [rsp+38h] [rbp-30h] BYREF
  DWORD v15; // [rsp+40h] [rbp-28h]
  WCHAR String2[8]; // [rsp+48h] [rbp-20h] BYREF

  wcscpy(String2, L"LDAP://");
  v4 = -1;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( String2[cchCount2] );
  LastError = GetLastError();
  v15 = LastError;
  uBytes = 0;
  if ( !a1 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"AllocGpLink: pwszGPO is null");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"AllocGpLink: pwszGPO is null");
      }
    }
    goto LABEL_39;
  }
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( v7 > (unsigned int)cchCount2 && CompareStringW(0x7Fu, 1u, a1, cchCount2, String2, cchCount2) == 2 )
    a1 += (int)cchCount2;
  v8 = (unsigned __int16 **)LocalAlloc(0x40u, 0x18u);
  v9 = v8;
  if ( !v8 )
  {
    v10 = GetLastError();
LABEL_40:
    SetLastError(v10);
    return 0;
  }
  v13 = v8;
  if ( !a1 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"AllocGpLink: pwszPath is null");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"AllocGpLink: pwszPath is null");
      }
    }
    goto LABEL_17;
  }
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 + 1 < v4 || (int)ULongLongMult(v4 + 1, 2u, &uBytes) < 0 )
  {
    LocalFree(v9);
    v10 = 534;
    goto LABEL_40;
  }
  v11 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
  *v9 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
LABEL_17:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v13);
LABEL_39:
    v10 = LastError;
    goto LABEL_40;
  }
  StringCchCopyW(v11, v4 + 1, a1);
  *((_DWORD *)v9 + 2) = (a2 & 1) == 0;
  if ( (a2 & 2) != 0 )
  {
    *((_DWORD *)v9 + 3) = 1;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"AllocGpLink: GPO %s has enforced link.", *v9);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"AllocGpLink: GPO %s has enforced link.", *v9);
      }
    }
  }
  v13 = 0;
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v13);
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x180018ed4  push    rbp
0x180018ed6  push    rbx
0x180018ed7  push    rsi
0x180018ed8  push    rdi
0x180018ed9  push    r12
0x180018edb  push    r13
0x180018edd  push    r14
0x180018edf  push    r15
0x180018ee1  mov     rbp, rsp
0x180018ee4  sub     rsp, 68h
0x180018ee8  mov     rax, cs:__security_cookie
0x180018eef  xor     rax, rsp
0x180018ef2  mov     [rbp+var_10], rax
0x180018ef6  mov     r12d, edx
0x180018ef9  mov     rsi, rcx
0x180018efc  movups  xmm0, xmmword ptr cs:aLdap; "LDAP://"
0x180018f03  movdqu  xmmword ptr [rbp+String2], xmm0
0x180018f08  lea     rax, [rbp+String2]
0x180018f0c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180018f10  mov     rdi, r14
0x180018f13  xor     r13d, r13d
0x180018f16  inc     rdi
0x180018f19  cmp     [rax+rdi*2], r13w
0x180018f1e  jnz     short loc_180018F16
0x180018f20  call    cs:__imp_GetLastError
0x180018f26  mov     ebx, eax
0x180018f28  mov     [rbp+var_28], eax
0x180018f2b  mov     [rbp+uBytes], r13
0x180018f2f  test    rsi, rsi
0x180018f32  jz      loc_18001910F
0x180018f38  mov     rcx, r14
0x180018f3b  inc     rcx
0x180018f3e  cmp     [rsi+rcx*2], r13w
0x180018f43  jnz     short loc_180018F3B
0x180018f45  mov     eax, edi
0x180018f47  cmp     rcx, rax
0x180018f4a  jbe     short loc_180018F79
0x180018f4c  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018f50  lea     rax, [rbp+String2]
0x180018f54  mov     [rsp+68h+lpString2], rax; lpString2
0x180018f59  mov     r9d, edi; cchCount1
0x180018f5c  mov     r8, rsi; lpString1
0x180018f5f  mov     edx, 1; dwCmpFlags
0x180018f64  lea     ecx, [rdx+7Eh]; Locale
0x180018f67  call    cs:__imp_CompareStringW
0x180018f6d  cmp     eax, 2
0x180018f70  jnz     short loc_180018F79
0x180018f72  movsxd  rax, edi
0x180018f75  lea     rsi, [rsi+rax*2]
0x180018f79  mov     edx, 18h; uBytes
0x180018f7e  lea     ecx, [rdx+28h]; uFlags
0x180018f81  call    cs:__imp_LocalAlloc
0x180018f87  mov     rdi, rax
0x180018f8a  test    rax, rax
0x180018f8d  jnz     short loc_180018F9D
0x180018f8f  call    cs:__imp_GetLastError
0x180018f95  nop
0x180018f96  mov     ecx, eax
0x180018f98  jmp     loc_18001915D
0x180018f9d  mov     [rbp+var_38], rdi
0x180018fa1  test    rsi, rsi
0x180018fa4  jz      loc_1800190B0
0x180018faa  inc     r14
0x180018fad  cmp     [rsi+r14*2], r13w
0x180018fb2  jnz     short loc_180018FAA
0x180018fb4  lea     r15, [r14+1]
0x180018fb8  cmp     r15, r14
0x180018fbb  jb      loc_18001909C
0x180018fc1  lea     r8, [rbp+uBytes]; unsigned __int64 *
0x180018fc5  mov     edx, 2; unsigned __int64
0x180018fca  mov     rcx, r15; unsigned __int64
0x180018fcd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180018fd2  test    eax, eax
0x180018fd4  js      loc_18001909C
0x180018fda  mov     rdx, [rbp+uBytes]; uBytes
0x180018fde  mov     ecx, 40h ; '@'; uFlags
0x180018fe3  call    cs:__imp_LocalAlloc
0x180018fe9  mov     [rdi], rax
0x180018fec  test    rax, rax
0x180018fef  jnz     short loc_180019007
0x180018ff1  call    cs:__imp_GetLastError
0x180018ff7  mov     ebx, eax
0x180018ff9  lea     rcx, [rbp+var_38]
0x180018ffd  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180019002  jmp     loc_18001915B
0x180019007  mov     r8, rsi; unsigned __int16 *
0x18001900a  mov     rdx, r15; unsigned __int64
0x18001900d  mov     rcx, rax; unsigned __int16 *
0x180019010  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019015  mov     eax, r12d
0x180019018  not     eax
0x18001901a  and     eax, 1
0x18001901d  mov     [rdi+8], eax
0x180019020  test    r12b, 2
0x180019024  jz      short loc_18001907E
0x180019026  mov     dword ptr [rdi+0Ch], 1
0x18001902d  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180019034  jz      short loc_18001907E
0x180019036  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001903d  test    rax, rax
0x180019040  jz      short loc_180019058
0x180019042  mov     r8, [rdi]
0x180019045  lea     rdx, aAllocgplinkGpo; "AllocGpLink: GPO %s has enforced link."
0x18001904c  mov     ecx, 4
0x180019051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019056  jmp     short loc_18001907E
0x180019058  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18001905f  jz      short loc_18001907E
0x180019061  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019068  jz      short loc_18001907E
0x18001906a  mov     r8, [rdi]
0x18001906d  lea     rdx, aAllocgplinkGpo; "AllocGpLink: GPO %s has enforced link."
0x180019074  mov     ecx, 4; unsigned int
0x180019079  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001907e  mov     [rbp+var_38], r13
0x180019082  lea     rcx, [rbp+var_38]
0x180019086  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001908b  nop
0x18001908c  mov     ecx, ebx; dwErrCode
0x18001908e  call    cs:__imp_SetLastError
0x180019094  mov     rax, rdi
0x180019097  jmp     loc_180019165
0x18001909c  mov     rcx, rdi; hMem
0x18001909f  call    cs:__imp_LocalFree
0x1800190a5  nop
0x1800190a6  mov     ecx, 216h
0x1800190ab  jmp     loc_18001915D
0x1800190b0  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800190b7  jz      loc_180018FF9
0x1800190bd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800190c4  test    rax, rax
0x1800190c7  jz      short loc_1800190DF
0x1800190c9  lea     rdx, aAllocgplinkPws_0; "AllocGpLink: pwszPath is null"
0x1800190d0  mov     ecx, 2
0x1800190d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190da  jmp     loc_180018FF9
0x1800190df  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800190e6  jz      loc_180018FF9
0x1800190ec  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800190f3  jz      loc_180018FF9
0x1800190f9  lea     rdx, aAllocgplinkPws_0; "AllocGpLink: pwszPath is null"
0x180019100  mov     ecx, 2; unsigned int
0x180019105  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001910a  jmp     loc_180018FF9
0x18001910f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180019116  jz      short loc_18001915B
0x180019118  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001911f  test    rax, rax
0x180019122  jz      short loc_180019137
0x180019124  lea     rdx, aAllocgplinkPws; "AllocGpLink: pwszGPO is null"
0x18001912b  mov     ecx, 2
0x180019130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019135  jmp     short loc_18001915B
0x180019137  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18001913e  jz      short loc_18001915B
0x180019140  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019147  jz      short loc_18001915B
0x180019149  lea     rdx, aAllocgplinkPws; "AllocGpLink: pwszGPO is null"
0x180019150  mov     ecx, 2; unsigned int
0x180019155  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001915a  nop
0x18001915b  mov     ecx, ebx; dwErrCode
0x18001915d  call    cs:__imp_SetLastError
0x180019163  xor     eax, eax
0x180019165  mov     rcx, [rbp+var_10]
0x180019169  xor     rcx, rsp; StackCookie
0x18001916c  call    __security_check_cookie
0x180019171  add     rsp, 68h
0x180019175  pop     r15
0x180019177  pop     r14
0x180019179  pop     r13
0x18001917b  pop     r12
0x18001917d  pop     rdi
0x18001917e  pop     rsi
0x18001917f  pop     rbx
0x180019180  pop     rbp
0x180019181  retn
```
