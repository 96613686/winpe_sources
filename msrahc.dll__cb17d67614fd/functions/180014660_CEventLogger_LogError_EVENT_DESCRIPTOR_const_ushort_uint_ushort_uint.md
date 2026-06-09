# CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)

- ea: `0x180014660`
- end: `0x1800147e0`
- name: `?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z`
- size: `384`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `70`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c998`
- `0x18000cb0c`
- `0x18000cc10`
- `0x18000ccd0`
- `0x18000cdf8`
- `0x18000ceb0`
- `0x18000d100`
- `0x18000d690`
- `0x18000d730`
- `0x18000da10`
- `0x18000e008`
- `0x18000e170`
- `0x18000e4d0`
- `0x18000e9b0`
- `0x18000ebe0`
- `0x18000eea0`
- `0x18000f010`
- `0x18000f340`
- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`
- `0x180010718`
- `0x180010adc`
- `0x180010d70`
- `0x180010fc0`
- `0x180011170`
- `0x180011224`
- `0x180011344`
- `0x180011424`
- `0x1800114d0`
- `0x180011874`
- `0x18001194c`
- `0x180011af8`
- `0x180011b8c`
- `0x180011c10`
- `0x180011df8`
- `0x1800120b0`
- `0x18001223c`
- `0x18001297c`
- `0x180012a74`
- `0x180012df0`
- `0x180013730`
- `0x180013b00`
- `0x180013e40`
- `0x1800140c4`
- `0x1800149bc`
- `0x180014c24`
- `0x180014da0`

## callees

- `0x180006b48`
- `0x180014660`
- `0x180014958`
- `0x18001a5a2`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800147a8`
- `ADVAPI32!EventWrite` at `0x1800147a8`
- `KERNEL32!GetLastError` at `0x1800146f4`
- `KERNEL32!GetLastError` at `0x1800146f4`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogError(
        CEventLogger *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  DWORD LastError; // eax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  unsigned int *v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  unsigned __int16 v23[128]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[128]; // [rsp+180h] [rbp+80h] BYREF

  v13 = 0;
  LODWORD(v12) = a4;
  v14 = 0;
  memset_0(v23, 0, sizeof(v23));
  memset_0(v24, 0, sizeof(v24));
  StringCchPrintfW(v23, 0x80u, L"%d", a4, v12);
  LastError = a6;
  if ( !a6 )
  {
    LastError = GetLastError();
    a6 = LastError;
  }
  StringCchPrintfW(v24, 0x80u, L"%x", LastError);
  if ( (int)StringCbLengthW(a3, v9, &v13) < 0 || (int)StringCbLengthW(a5, v10, &v14) < 0 )
    return 2147500037LL;
  UserData.Ptr = (ULONGLONG)a3;
  UserData.Size = v13 + 2;
  UserData.Reserved = 0;
  v16 = &v12;
  v17 = 4;
  v19 = v14 + 2;
  v21 = &a6;
  v18 = a5;
  v20 = 0;
  v22 = 4;
  return EventWrite(g_Logger, &Recoverable_Error, 4u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180014660  mov     [rsp-8+arg_0], rbx
0x180014665  push    rbp
0x180014666  push    rsi
0x180014667  push    rdi
0x180014668  lea     rbp, [rsp-190h]
0x180014670  sub     rsp, 290h
0x180014677  mov     rax, cs:__security_cookie
0x18001467e  xor     rax, rsp
0x180014681  mov     [rbp+1A0h+var_20], rax
0x180014688  mov     rdi, [rbp+1A0h+arg_20]
0x18001468f  lea     rcx, [rbp+1A0h+var_220]; void *
0x180014693  mov     ebx, r9d
0x180014696  mov     [rsp+2A0h+var_278], 0
0x18001469f  mov     rsi, r8
0x1800146a2  mov     dword ptr [rsp+2A0h+var_280], ebx
0x1800146a6  mov     r8d, 100h; Size
0x1800146ac  mov     [rsp+2A0h+var_270], 0
0x1800146b5  xor     edx, edx; Val
0x1800146b7  call    memset_0
0x1800146bc  xor     edx, edx; Val
0x1800146be  lea     rcx, [rbp+1A0h+var_120]; void *
0x1800146c5  mov     r8d, 100h; Size
0x1800146cb  call    memset_0
0x1800146d0  mov     r9d, ebx
0x1800146d3  lea     r8, aD; "%d"
0x1800146da  mov     ebx, 80h
0x1800146df  lea     rcx, [rbp+1A0h+var_220]; unsigned __int16 *
0x1800146e3  mov     edx, ebx; unsigned __int64
0x1800146e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800146ea  mov     eax, [rbp+1A0h+arg_28]
0x1800146f0  test    eax, eax
0x1800146f2  jnz     short loc_180014700
0x1800146f4  call    cs:__imp_GetLastError
0x1800146fa  mov     [rbp+1A0h+arg_28], eax
0x180014700  mov     r9d, eax
0x180014703  lea     r8, asc_180021BA8; "%x"
0x18001470a  mov     rdx, rbx; unsigned __int64
0x18001470d  lea     rcx, [rbp+1A0h+var_120]; unsigned __int16 *
0x180014714  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014719  lea     r8, [rsp+2A0h+var_278]; unsigned __int64 *
0x18001471e  mov     rcx, rsi; unsigned __int16 *
0x180014721  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014726  test    eax, eax
0x180014728  js      loc_1800147B9
0x18001472e  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x180014733  mov     rcx, rdi; unsigned __int16 *
0x180014736  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001473b  test    eax, eax
0x18001473d  js      short loc_1800147B9
0x18001473f  mov     eax, dword ptr [rsp+2A0h+var_278]
0x180014743  lea     r9, [rsp+2A0h+UserData]; UserData
0x180014748  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x18001474f  lea     rdx, Recoverable_Error; EventDescriptor
0x180014756  add     eax, 2
0x180014759  mov     [rsp+2A0h+UserData.Ptr], rsi
0x18001475e  mov     [rsp+2A0h+UserData.Size], eax
0x180014762  mov     r8d, 4; UserDataCount
0x180014768  lea     rax, [rsp+2A0h+var_280]
0x18001476d  mov     dword ptr [rsp+2A0h+UserData.0Ch], 0
0x180014775  mov     [rsp+2A0h+var_250], rax
0x18001477a  mov     eax, dword ptr [rsp+2A0h+var_270]
0x18001477e  add     eax, 2
0x180014781  mov     [rsp+2A0h+var_248], r8
0x180014786  mov     [rsp+2A0h+var_238], eax
0x18001478a  lea     rax, [rbp+1A0h+arg_28]
0x180014791  mov     [rsp+2A0h+var_230], rax
0x180014796  mov     [rsp+2A0h+var_240], rdi
0x18001479b  mov     [rsp+2A0h+var_234], 0
0x1800147a3  mov     [rsp+2A0h+var_228], r8
0x1800147a8  call    cs:__imp_EventWrite
0x1800147ae  neg     eax
0x1800147b0  sbb     eax, eax
0x1800147b2  and     eax, 80004005h
0x1800147b7  jmp     short loc_1800147BE
0x1800147b9  mov     eax, 80004005h
0x1800147be  mov     rcx, [rbp+1A0h+var_20]
0x1800147c5  xor     rcx, rsp; StackCookie
0x1800147c8  call    __security_check_cookie
0x1800147cd  mov     rbx, [rsp+2A0h+arg_0]
0x1800147d5  add     rsp, 290h
0x1800147dc  pop     rdi
0x1800147dd  pop     rsi
0x1800147de  pop     rbp
0x1800147df  retn
```
