# _TraceString(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,char *)

- ea: `0x1400056c0`
- end: `0x140005826`
- name: `?_TraceString@@YAXW4TraceSource@@EPEBGK1J1PEAD@Z`
- size: `358`
- prototype: `void __fastcall(int, char, __int64, int, __int64, int, wchar_t *Format, va_list Args)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140002980`

## callees

- `0x140005374`
- `0x1400056c0`
- `0x140005a4c`
- `0x140006f10`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400057a9`
- `msvcrt!_vsnwprintf` at `0x1400057a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000570c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000570c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005715`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140005706`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140005706`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000577b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000577b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400057e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400057e4`

## pseudocode

```c
void __fastcall _TraceString(int a1, char a2, __int64 a3, int a4, __int64 a5, int a6, wchar_t *Format, va_list Args)
{
  unsigned int v12; // eax
  void *v13; // rbx
  SIZE_T v14; // rsi
  _WORD *v15; // rax
  unsigned __int64 v16; // rdi
  size_t v17; // rdi
  int v18; // eax
  int v19; // ecx
  void **v20; // [rsp+20h] [rbp-69h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-61h] BYREF
  DWORD CurrentThreadId; // [rsp+38h] [rbp-51h]
  DWORD CurrentProcessId; // [rsp+3Ch] [rbp-4Dh]
  char v24; // [rsp+40h] [rbp-49h]
  int v25; // [rsp+48h] [rbp-41h]
  __int64 v26; // [rsp+50h] [rbp-39h]
  __int64 v27; // [rsp+58h] [rbp-31h]
  int v28; // [rsp+60h] [rbp-29h]
  unsigned int v29; // [rsp+64h] [rbp-25h]
  const wchar_t *v30; // [rsp+68h] [rbp-21h]
  __int64 v31; // [rsp+70h] [rbp-19h]
  __int64 v32; // [rsp+78h] [rbp-11h]

  GetLocalTime(&SystemTime);
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v24 = a2;
  v20 = &CStringTraceEvent::`vftable';
  v25 = a1;
  v26 = a3;
  v27 = a5;
  v28 = a4;
  v31 = 0;
  v32 = 0;
  v12 = a6;
  if ( a6 > 0 )
    v12 = (unsigned __int16)a6 | 0x80070000;
  v29 = v12;
  v30 = 0;
  v13 = 0;
  v14 = 128;
  while ( 1 )
  {
    v14 *= 2LL;
    LocalFree(v13);
    v15 = LocalAlloc(0, v14);
    v13 = v15;
    if ( !v15 )
      break;
    v16 = v14 >> 1;
    if ( !(v14 >> 1) )
      goto LABEL_16;
    if ( v16 > 0x7FFFFFFF )
    {
      *v15 = 0;
LABEL_16:
      LocalFree(v15);
      break;
    }
    v17 = v16 - 1;
    v18 = _vsnwprintf(v15, v17, Format, Args);
    if ( v18 < 0 || v18 > v17 )
    {
      v19 = -2147024774;
LABEL_12:
      *((_WORD *)v13 + v17) = 0;
      goto LABEL_13;
    }
    v19 = 0;
    if ( v18 == v17 )
      goto LABEL_12;
LABEL_13:
    if ( v19 != -2147024774 )
    {
      v30 = (const wchar_t *)v13;
      goto LABEL_18;
    }
  }
  v30 = L"[[Unable to format message]]";
LABEL_18:
  TraceGenericEvent((struct CTraceEvent *)&v20);
  CStringTraceEvent::~CStringTraceEvent((CStringTraceEvent *)&v20);
}

```

## disassembly

```asm
0x1400056c0  push    rbp
0x1400056c2  push    rbx
0x1400056c3  push    rsi
0x1400056c4  push    rdi
0x1400056c5  push    r12
0x1400056c7  push    r14
0x1400056c9  push    r15
0x1400056cb  lea     rbp, [rsp-7]
0x1400056d0  sub     rsp, 90h
0x1400056d7  mov     rax, cs:__security_cookie
0x1400056de  xor     rax, rsp
0x1400056e1  mov     [rbp+37h+var_40], rax
0x1400056e5  mov     r14d, r9d
0x1400056e8  mov     rsi, r8
0x1400056eb  mov     bl, dl
0x1400056ed  mov     edi, ecx
0x1400056ef  mov     r15, [rbp+37h+Format]
0x1400056f3  mov     r12, [rbp+37h+Args]
0x1400056f7  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x1400056fe  mov     [rbp+37h+var_A0], rax
0x140005702  lea     rcx, [rbp+37h+SystemTime]; lpSystemTime
0x140005706  call    cs:__imp_GetLocalTime
0x14000570c  call    cs:__imp_GetCurrentThreadId
0x140005712  mov     [rbp+37h+var_88], eax
0x140005715  call    cs:__imp_GetCurrentProcessId
0x14000571b  mov     [rbp+37h+var_84], eax
0x14000571e  mov     [rbp+37h+var_80], bl
0x140005721  lea     rax, ??_7CStringTraceEvent@@6B@; const CStringTraceEvent::`vftable'
0x140005728  mov     [rbp+37h+var_A0], rax
0x14000572c  mov     [rbp+37h+var_78], edi
0x14000572f  mov     [rbp+37h+var_70], rsi
0x140005733  mov     rax, [rbp+37h+arg_20]
0x140005737  mov     [rbp+37h+var_68], rax
0x14000573b  mov     [rbp+37h+var_60], r14d
0x14000573f  xor     r14d, r14d
0x140005742  mov     [rbp+37h+var_50], r14
0x140005746  mov     [rbp+37h+var_48], r14
0x14000574a  mov     eax, [rbp+37h+arg_28]
0x14000574d  test    eax, eax
0x14000574f  js      short loc_14000575B
0x140005751  jle     short loc_14000575B
0x140005753  movzx   eax, ax
0x140005756  or      eax, 80070000h
0x14000575b  mov     [rbp+37h+var_5C], eax
0x14000575e  mov     [rbp+37h+var_58], r14
0x140005762  mov     rbx, r14
0x140005765  mov     esi, 80h
0x14000576a  add     rsi, rsi
0x14000576d  mov     rcx, rbx; hMem
0x140005770  call    cs:__imp_LocalFree
0x140005776  mov     rdx, rsi; uBytes
0x140005779  xor     ecx, ecx; uFlags
0x14000577b  call    cs:__imp_LocalAlloc
0x140005781  mov     rbx, rax
0x140005784  test    rax, rax
0x140005787  jz      short loc_1400057EA
0x140005789  mov     rdi, rsi
0x14000578c  shr     rdi, 1
0x14000578f  jz      short loc_1400057E1
0x140005791  cmp     rdi, 7FFFFFFFh
0x140005798  ja      short loc_1400057DD
0x14000579a  dec     rdi
0x14000579d  mov     r9, r12; Args
0x1400057a0  mov     r8, r15; Format
0x1400057a3  mov     rdx, rdi; BufferCount
0x1400057a6  mov     rcx, rax; Buffer
0x1400057a9  call    cs:__imp__vsnwprintf
0x1400057af  test    eax, eax
0x1400057b1  js      short loc_1400057C1
0x1400057b3  cdqe
0x1400057b5  cmp     rax, rdi
0x1400057b8  ja      short loc_1400057C1
0x1400057ba  mov     ecx, r14d
0x1400057bd  jnz     short loc_1400057CB
0x1400057bf  jmp     short loc_1400057C6
0x1400057c1  mov     ecx, 8007007Ah
0x1400057c6  mov     [rbx+rdi*2], r14w
0x1400057cb  cmp     ecx, 8007007Ah
0x1400057d1  jz      short loc_14000576A
0x1400057d3  test    ecx, ecx
0x1400057d5  js      short loc_1400057E1
0x1400057d7  mov     [rbp+37h+var_58], rbx
0x1400057db  jmp     short loc_1400057F5
0x1400057dd  mov     [rax], r14w
0x1400057e1  mov     rcx, rbx; hMem
0x1400057e4  call    cs:__imp_LocalFree
0x1400057ea  lea     rax, aUnableToFormat; "[[Unable to format message]]"
0x1400057f1  mov     [rbp+37h+var_58], rax
0x1400057f5  lea     rcx, [rbp+37h+var_A0]; struct CTraceEvent *
0x1400057f9  call    ?TraceGenericEvent@@YAXAEAVCTraceEvent@@@Z; TraceGenericEvent(CTraceEvent &)
0x1400057fe  nop
0x1400057ff  lea     rcx, [rbp+37h+var_A0]; this
0x140005803  call    ??1CStringTraceEvent@@UEAA@XZ; CStringTraceEvent::~CStringTraceEvent(void)
0x140005808  mov     rcx, [rbp+37h+var_40]
0x14000580c  xor     rcx, rsp; StackCookie
0x14000580f  call    __security_check_cookie
0x140005814  add     rsp, 90h
0x14000581b  pop     r15
0x14000581d  pop     r14
0x14000581f  pop     r12
0x140005821  pop     rdi
0x140005822  pop     rsi
0x140005823  pop     rbx
0x140005824  pop     rbp
0x140005825  retn
```
