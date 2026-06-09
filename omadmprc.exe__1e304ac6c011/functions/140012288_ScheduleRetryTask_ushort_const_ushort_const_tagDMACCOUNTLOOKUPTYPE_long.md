# ScheduleRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,long)

- ea: `0x140012288`
- end: `0x14001237f`
- name: `?ScheduleRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@J@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14001401c`

## callees

- `0x14000b708`
- `0x14000c084`
- `0x14000ed04`
- `0x14000fc54`
- `0x140011ac8`
- `0x140012060`
- `0x140012288`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140012352`
- `msvcrt!??3@YAXPEAX@Z` at `0x140012352`

## string_xrefs

- `0x14001232d`: `ScheduleRetryTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ScheduleRetryTask(unsigned __int16 *a1, WCHAR *a2, __int64 a3, int a4)
{
  int v6; // ecx
  unsigned int v7; // ebx
  __int64 v8; // rax
  COmaDmPrcLogger *Logger; // rax
  const unsigned __int16 *v10; // r8
  _BYTE v12[32]; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int16 *v13[3]; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp-18h]

  if ( a4 == -2102657013 )
    return (unsigned int)ScheduleBackOffRetryTask(a1, a2);
  if ( (unsigned int)(a4 + 2147012894) <= 0x1E )
  {
    v6 = 1476427821;
    if ( _bittest(&v6, a4 + 2147012894) )
      return (unsigned int)ScheduleNetworkRetryTask(a1);
  }
  if ( a4 == -2147012816 )
    return (unsigned int)ScheduleNetworkRetryTask(a1);
  v7 = -2147024809;
  v14 = 7;
  v13[2] = 0;
  LOWORD(v13[0]) = 0;
  v8 = std::wstring::wstring(v12, a2);
  GetInitiationIDFromKeyPath(v8, v13);
  Logger = COmaDmPrcLogger::GetLogger();
  v10 = (const unsigned __int16 *)v13;
  if ( v14 >= 8 )
    v10 = v13[0];
  COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(
    Logger,
    a1,
    v10,
    L"ScheduleRetryTask",
    L"ScheduleRetryTask",
    -2147024809);
  if ( v14 >= 8 )
    operator delete(v13[0]);
  return v7;
}

```

## disassembly

```asm
0x140012288  mov     [rsp+arg_10], rbx
0x14001228d  push    rdi
0x14001228e  sub     rsp, 80h
0x140012295  mov     rax, cs:__security_cookie
0x14001229c  xor     rax, rsp
0x14001229f  mov     [rsp+88h+var_10], rax
0x1400122a4  mov     rdi, rcx
0x1400122a7  cmp     r9d, 82AC000Bh
0x1400122ae  jnz     short loc_1400122B7
0x1400122b0  call    ?ScheduleBackOffRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@@Z; ScheduleBackOffRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE)
0x1400122b5  jmp     short loc_1400122DE
0x1400122b7  lea     eax, [r9+7FF8D11Eh]
0x1400122be  cmp     eax, 1Eh
0x1400122c1  ja      short loc_1400122CD
0x1400122c3  mov     ecx, 5800802Dh
0x1400122c8  bt      ecx, eax
0x1400122cb  jb      short loc_1400122D6
0x1400122cd  cmp     r9d, 80072F30h
0x1400122d4  jnz     short loc_1400122E2
0x1400122d6  mov     rcx, rdi; unsigned __int16 *
0x1400122d9  call    ?ScheduleNetworkRetryTask@@YAJPEBG@Z; ScheduleNetworkRetryTask(ushort const *)
0x1400122de  mov     ebx, eax
0x1400122e0  jmp     short loc_14001235E
0x1400122e2  mov     ebx, 80070057h
0x1400122e7  mov     [rsp+88h+var_18], 7
0x1400122f0  xor     eax, eax
0x1400122f2  mov     [rsp+88h+var_20], rax
0x1400122f7  mov     word ptr [rsp+88h+var_30], ax
0x1400122fc  lea     rcx, [rsp+88h+var_50]; void *
0x140012301  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140012306  lea     rdx, [rsp+88h+var_30]
0x14001230b  mov     rcx, rax
0x14001230e  call    ?GetInitiationIDFromKeyPath@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetInitiationIDFromKeyPath(std::wstring,std::wstring &)
0x140012313  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140012318  lea     r8, [rsp+88h+var_30]
0x14001231d  cmp     [rsp+88h+var_18], 8
0x140012323  cmovnb  r8, [rsp+88h+var_30]; unsigned __int16 *
0x140012329  mov     [rsp+88h+var_60], ebx; int
0x14001232d  lea     r9, aScheduleretryt; "ScheduleRetryTask"
0x140012334  mov     [rsp+88h+var_68], r9; unsigned __int16 *
0x140012339  mov     rdx, rdi; unsigned __int16 *
0x14001233c  mov     rcx, rax; this
0x14001233f  call    ?LogOmaDmPrcScheduleRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x140012344  nop
0x140012345  cmp     [rsp+88h+var_18], 8
0x14001234b  jb      short loc_14001235E
0x14001234d  mov     rcx, [rsp+88h+var_30]
0x140012352  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140012359  nop     dword ptr [rax+rax+00h]
0x14001235e  mov     eax, ebx
0x140012360  mov     rcx, [rsp+88h+var_10]
0x140012365  xor     rcx, rsp; StackCookie
0x140012368  call    __security_check_cookie
0x14001236d  mov     rbx, [rsp+88h+arg_10]
0x140012375  add     rsp, 80h
0x14001237c  pop     rdi
0x14001237d  retn
```
