# LQSCreateInternal

- ea: `0x180027830`
- end: `0x180027a10`
- name: `LQSCreateInternal`
- size: `480`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001d438`
- `0x180050e90`

## callees

- `0x180009924`
- `0x1800261a4`
- `0x180027780`
- `0x180027830`
- `0x180027ec4`
- `0x180029950`
- `0x18002c61c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!_waccess` at `0x1800278f5`
- `msvcrt!_waccess` at `0x1800278f5`
- `KERNEL32!LeaveCriticalSection` at `0x1800278e2`
- `KERNEL32!LeaveCriticalSection` at `0x180027943`
- `KERNEL32!LeaveCriticalSection` at `0x1800279a3`
- `KERNEL32!LeaveCriticalSection` at `0x1800279e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800278e2`
- `KERNEL32!LeaveCriticalSection` at `0x180027943`
- `KERNEL32!LeaveCriticalSection` at `0x1800279a3`
- `KERNEL32!LeaveCriticalSection` at `0x1800279e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LQSCreateInternal(
        unsigned int a1,
        wchar_t *a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        struct tagPROPVARIANT *a7,
        _HLQS **a8)
{
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  _HLQS *v16; // rdi
  int v17; // eax
  unsigned int v18; // esi
  _HLQS *v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  _RTL_CRITICAL_SECTION *v21; // [rsp+40h] [rbp-C0h]
  wchar_t FileName[312]; // [rsp+50h] [rbp-B0h] BYREF

  v20 = a4;
  v21 = &stru_18013A368;
  CCriticalSection::Lock((CCriticalSection *)&stru_18013A368);
  v19 = 0;
  v11 = LQSFilePath(a1, FileName, a2, a3, &v20);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( !_waccess(FileName, 0) )
      v12 = -1072824315;
    v13 = LQSCreateHandle_0(a2, FileName);
    v14 = v13;
    if ( v13 < 0 )
    {
      LogMsgHR(v13, (wchar_t *)L"lqs", 0x47Fu);
      P<_HLQS>::~P<_HLQS>(&v19);
      LeaveCriticalSection(&stru_18013A368);
      return v14;
    }
    v16 = v19;
    if ( v12 != -1072824315 )
    {
      v17 = LQSSetProperties((LPCWSTR *)v19, a5, a6, a7, 1);
      v18 = v17;
      if ( v17 < 0 )
      {
        LogMsgHR(v17, (wchar_t *)L"lqs", 0x14u);
        P<_HLQS>::~P<_HLQS>(&v19);
        LeaveCriticalSection(&stru_18013A368);
        return v18;
      }
    }
    ++*((_DWORD *)v19 + 6);
    *a8 = v16;
    v19 = 0;
    if ( v12 < 0 )
      LogMsgHR(v12, (wchar_t *)L"lqs", 0x1Eu);
    P<_HLQS>::~P<_HLQS>(&v19);
    LeaveCriticalSection(&stru_18013A368);
  }
  else
  {
    LogMsgHR(v11, (wchar_t *)L"lqs", 0x461u);
    P<_HLQS>::~P<_HLQS>(&v19);
    LeaveCriticalSection(&stru_18013A368);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027830  push    rbp
0x180027832  push    rbx
0x180027833  push    rsi
0x180027834  push    rdi
0x180027835  push    r12
0x180027837  push    r13
0x180027839  push    r14
0x18002783b  push    r15
0x18002783d  lea     rbp, [rsp-1D8h]
0x180027845  sub     rsp, 2D8h
0x18002784c  mov     rax, cs:__security_cookie
0x180027853  xor     rax, rsp
0x180027856  mov     [rbp+210h+var_50], rax
0x18002785d  mov     rbx, r8
0x180027860  mov     r12, rdx
0x180027863  mov     edi, ecx
0x180027865  mov     [rsp+310h+var_2D8], r9d
0x18002786a  mov     rsi, [rbp+210h+arg_28]
0x180027871  mov     r15, [rbp+210h+arg_30]
0x180027878  mov     r14, [rbp+210h+arg_38]
0x18002787f  lea     r13, stru_18013A368
0x180027886  mov     [rsp+310h+var_2D0], r13
0x18002788b  mov     rcx, r13; this
0x18002788e  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180027893  nop
0x180027894  mov     [rsp+310h+var_2E0], 0
0x18002789d  lea     rax, [rsp+310h+var_2D8]
0x1800278a2  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800278a7  mov     r9, rbx
0x1800278aa  mov     r8, r12
0x1800278ad  lea     rdx, [rsp+310h+FileName]
0x1800278b2  mov     ecx, edi
0x1800278b4  call    LQSFilePath
0x1800278b9  mov     ebx, eax
0x1800278bb  test    eax, eax
0x1800278bd  jns     short loc_1800278EE
0x1800278bf  mov     r8d, 461h; unsigned __int16
0x1800278c5  lea     rdx, aLqs_0; "lqs"
0x1800278cc  mov     ecx, eax; int
0x1800278ce  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800278d3  nop
0x1800278d4  lea     rcx, [rsp+310h+var_2E0]
0x1800278d9  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x1800278de  nop
0x1800278df  mov     rcx, r13; lpCriticalSection
0x1800278e2  call    cs:__imp_LeaveCriticalSection
0x1800278e8  nop
0x1800278e9  jmp     loc_1800279EB
0x1800278ee  xor     edx, edx; AccessMode
0x1800278f0  lea     rcx, [rsp+310h+FileName]; FileName
0x1800278f5  call    cs:__imp__waccess
0x1800278fb  mov     ecx, 0C00E0005h
0x180027900  test    eax, eax
0x180027902  cmovz   ebx, ecx
0x180027905  lea     r9, [rsp+310h+var_2E0]
0x18002790a  mov     r8d, edi
0x18002790d  lea     rdx, [rsp+310h+FileName]; wchar_t *
0x180027912  mov     rcx, r12; wchar_t *
0x180027915  call    LQSCreateHandle_0
0x18002791a  mov     edi, eax
0x18002791c  test    eax, eax
0x18002791e  jns     short loc_180027951
0x180027920  mov     r8d, 47Fh; unsigned __int16
0x180027926  lea     rdx, aLqs_0; "lqs"
0x18002792d  mov     ecx, eax; int
0x18002792f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180027934  nop
0x180027935  lea     rcx, [rsp+310h+var_2E0]
0x18002793a  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x18002793f  nop
0x180027940  mov     rcx, r13; lpCriticalSection
0x180027943  call    cs:__imp_LeaveCriticalSection
0x180027949  nop
0x18002794a  mov     eax, edi
0x18002794c  jmp     loc_1800279ED
0x180027951  mov     rdi, [rsp+310h+var_2E0]
0x180027956  cmp     ebx, 0C00E0005h
0x18002795c  jz      short loc_1800279AE
0x18002795e  mov     [rsp+310h+var_2F0], 1; int
0x180027966  mov     r9, r15; struct tagPROPVARIANT *
0x180027969  mov     r8, rsi; unsigned int *
0x18002796c  mov     edx, [rbp+210h+arg_20]; unsigned int
0x180027972  mov     rcx, rdi; this
0x180027975  call    ?LQSSetProperties@@YAJPEAXKQEAKQEAUtagPROPVARIANT@@H@Z; LQSSetProperties(void *,ulong,ulong * const,tagPROPVARIANT * const,int)
0x18002797a  mov     esi, eax
0x18002797c  test    eax, eax
0x18002797e  jns     short loc_1800279AE
0x180027980  mov     r8d, 14h; unsigned __int16
0x180027986  lea     rdx, aLqs_0; "lqs"
0x18002798d  mov     ecx, eax; int
0x18002798f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180027994  nop
0x180027995  lea     rcx, [rsp+310h+var_2E0]
0x18002799a  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x18002799f  nop
0x1800279a0  mov     rcx, r13; lpCriticalSection
0x1800279a3  call    cs:__imp_LeaveCriticalSection
0x1800279a9  nop
0x1800279aa  mov     eax, esi
0x1800279ac  jmp     short loc_1800279ED
0x1800279ae  inc     dword ptr [rdi+18h]
0x1800279b1  mov     [r14], rdi
0x1800279b4  mov     [rsp+310h+var_2E0], 0
0x1800279bd  test    ebx, ebx
0x1800279bf  jns     short loc_1800279D6
0x1800279c1  mov     r8d, 1Eh; unsigned __int16
0x1800279c7  lea     rdx, aLqs_0; "lqs"
0x1800279ce  mov     ecx, ebx; int
0x1800279d0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800279d5  nop
0x1800279d6  lea     rcx, [rsp+310h+var_2E0]
0x1800279db  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x1800279e0  nop
0x1800279e1  mov     rcx, r13; lpCriticalSection
0x1800279e4  call    cs:__imp_LeaveCriticalSection
0x1800279ea  nop
0x1800279eb  mov     eax, ebx
0x1800279ed  mov     rcx, [rbp+210h+var_50]
0x1800279f4  xor     rcx, rsp; StackCookie
0x1800279f7  call    __security_check_cookie
0x1800279fc  add     rsp, 2D8h
0x180027a03  pop     r15
0x180027a05  pop     r14
0x180027a07  pop     r13
0x180027a09  pop     r12
0x180027a0b  pop     rdi
0x180027a0c  pop     rsi
0x180027a0d  pop     rbx
0x180027a0e  pop     rbp
0x180027a0f  retn
```
