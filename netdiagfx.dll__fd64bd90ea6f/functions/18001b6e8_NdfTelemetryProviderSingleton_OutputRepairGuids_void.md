# NdfTelemetryProviderSingleton::OutputRepairGuids(void)

- ea: `0x18001b6e8`
- end: `0x18001b7ed`
- name: `?OutputRepairGuids@NdfTelemetryProviderSingleton@@QEAAQEBGXZ`
- size: `261`
- prototype: `const unsigned __int16 *__fastcall(NdfTelemetryProviderSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180018ae4`

## callees

- `0x180016e14`
- `0x1800181c4`
- `0x18001b6e8`
- `0x18001d530`
- `0x18001d5e8`
- `0x18002c840`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b747`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b747`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b7b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b7b7`

## pseudocode

```c
const unsigned __int16 *__fastcall NdfTelemetryProviderSingleton::OutputRepairGuids(
        NdfTelemetryProviderSingleton *this)
{
  __int64 *v1; // rsi
  __int64 v2; // rbx
  __int64 v3; // rdi
  const wchar_t *v4; // rdx
  __int64 v5; // rax
  _QWORD v7[4]; // [rsp+20h] [rbp-38h] BYREF

  v7[3] = 7;
  v7[2] = 0;
  LOWORD(v7[0]) = 0;
  v1 = &qword_180041D30;
  std::wstring::operator=(&qword_180041D30, v7);
  std::wstring::_Tidy(v7, 1, 0);
  AcquireSRWLockExclusive(&stru_180041D08);
  v2 = *((_QWORD *)&xmmword_180041D80 + 1);
  v3 = xmmword_180041D90;
  while ( v2 != v3 )
  {
    v4 = &dword_180033E1C;
    if ( qword_180041D40 )
      v4 = L"; ";
    v5 = std::operator+<unsigned short>(v7, v4, v2);
    std::wstring::append(&qword_180041D30, v5, 0, -1);
    std::wstring::_Tidy(v7, 1, 0);
    v2 += 32;
  }
  ReleaseSRWLockExclusive(&stru_180041D08);
  if ( (unsigned __int64)qword_180041D48 >= 8 )
    return (const unsigned __int16 *)qword_180041D30;
  return (const unsigned __int16 *)v1;
}

```

## disassembly

```asm
0x18001b6e8  mov     r11, rsp
0x18001b6eb  mov     [r11+8], rbx
0x18001b6ef  mov     [r11+10h], rsi
0x18001b6f3  push    rdi
0x18001b6f4  sub     rsp, 50h
0x18001b6f8  mov     rax, cs:__security_cookie
0x18001b6ff  xor     rax, rsp
0x18001b702  mov     [rsp+58h+var_18], rax
0x18001b707  mov     qword ptr [r11-20h], 7
0x18001b70f  mov     qword ptr [r11-28h], 0
0x18001b717  xor     eax, eax
0x18001b719  mov     word ptr [rsp+58h+var_38], ax
0x18001b71e  lea     rdx, [r11-38h]
0x18001b722  lea     rsi, qword_180041D30
0x18001b729  mov     rcx, rsi
0x18001b72c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001b731  xor     r8d, r8d
0x18001b734  mov     dl, 1
0x18001b736  lea     rcx, [rsp+58h+var_38]
0x18001b73b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b740  lea     rcx, stru_180041D08; SRWLock
0x18001b747  call    cs:__imp_AcquireSRWLockExclusive
0x18001b74d  mov     rbx, qword ptr cs:xmmword_180041D80+8
0x18001b754  mov     rdi, qword ptr cs:xmmword_180041D90
0x18001b75b  cmp     rbx, rdi
0x18001b75e  jz      short loc_18001B7B0
0x18001b760  lea     rdx, dword_180033E1C
0x18001b767  lea     rax, asc_180036D48; "; "
0x18001b76e  cmp     cs:qword_180041D40, 0
0x18001b776  cmovnz  rdx, rax
0x18001b77a  mov     r8, rbx
0x18001b77d  lea     rcx, [rsp+58h+var_38]
0x18001b782  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18001b787  nop
0x18001b788  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001b78c  xor     r8d, r8d
0x18001b78f  mov     rdx, rax
0x18001b792  mov     rcx, rsi
0x18001b795  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001b79a  nop
0x18001b79b  xor     r8d, r8d
0x18001b79e  mov     dl, 1
0x18001b7a0  lea     rcx, [rsp+58h+var_38]
0x18001b7a5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b7aa  add     rbx, 20h ; ' '
0x18001b7ae  jmp     short loc_18001B75B
0x18001b7b0  lea     rcx, stru_180041D08; SRWLock
0x18001b7b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b7bd  cmp     cs:qword_180041D48, 8
0x18001b7c5  cmovnb  rsi, cs:qword_180041D30
0x18001b7cd  mov     rax, rsi
0x18001b7d0  mov     rcx, [rsp+58h+var_18]
0x18001b7d5  xor     rcx, rsp; StackCookie
0x18001b7d8  call    __security_check_cookie
0x18001b7dd  mov     rbx, [rsp+58h+arg_0]
0x18001b7e2  mov     rsi, [rsp+58h+arg_8]
0x18001b7e7  add     rsp, 50h
0x18001b7eb  pop     rdi
0x18001b7ec  retn
```
