# CDataObject::_WriteDisplayName(IStream *)

- ea: `0x1800098e0`
- end: `0x180009a1d`
- name: `?_WriteDisplayName@CDataObject@@AEAAJPEAUIStream@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CDataObject *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009620`

## callees

- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x180005f64`
- `0x1800098e0`
- `0x180016a98`
- `0x18001f858`
- `0x18001f960`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009964`
- `msvcrt!_wcsicmp` at `0x180009964`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataObject::_WriteDisplayName(CDataObject *this, struct IStream *a2)
{
  __int64 v3; // r9
  CLogInfo *v4; // rcx
  unsigned __int16 *DisplayName; // rbx
  const wchar_t *CurrentFocus; // rbx
  const wchar_t *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // rdx
  wchar_t *String2[3]; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-11h]
  _QWORD v19[4]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp+17h] BYREF

  std::wstring::wstring(v19);
  v4 = *(CLogInfo **)(v3 + 16);
  if ( v4 )
  {
    DisplayName = CLogInfo::GetDisplayName(v4);
  }
  else
  {
    CurrentFocus = CComponentData::GetCurrentFocus(*(CComponentData **)(v3 + 32));
    GetComputerNameAsString(String2);
    if ( !CurrentFocus )
    {
      CurrentFocus = (const wchar_t *)String2;
      if ( v18 >= 8 )
        CurrentFocus = String2[0];
    }
    v7 = (const wchar_t *)String2;
    if ( v18 >= 8 )
      v7 = String2[0];
    if ( _wcsicmp(CurrentFocus, v7) )
      v10 = FormatString(v20, 124, CurrentFocus, v9);
    else
      v10 = FormatString(v20, 297, v8, v9);
    std::wstring::operator=(v19, v10);
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(v20, v11, 0);
    DisplayName = (unsigned __int16 *)v19;
    if ( v19[3] >= 8u )
      DisplayName = (unsigned __int16 *)v19[0];
    LOBYTE(v12) = 1;
    std::wstring::_Tidy(String2, v12, 0);
  }
  v13 = -1;
  do
    ++v13;
  while ( DisplayName[v13] );
  v14 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
          a2,
          DisplayName,
          (unsigned int)(2 * v13 + 2),
          0);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v19, v15, 0);
  return v14;
}

```

## disassembly

```asm
0x1800098e0  mov     [rsp-8+arg_10], rbx
0x1800098e5  push    rbp
0x1800098e6  push    rsi
0x1800098e7  push    rdi
0x1800098e8  lea     rbp, [rsp-47h]
0x1800098ed  sub     rsp, 0A0h
0x1800098f4  mov     rax, cs:__security_cookie
0x1800098fb  xor     rax, rsp
0x1800098fe  mov     [rbp+57h+var_20], rax
0x180009902  mov     rdi, rdx
0x180009905  mov     r9, rcx
0x180009908  lea     rcx, [rbp+57h+var_60]
0x18000990c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009911  nop
0x180009912  mov     rcx, [r9+10h]; this
0x180009916  xor     esi, esi
0x180009918  test    rcx, rcx
0x18000991b  jz      short loc_18000992A
0x18000991d  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x180009922  mov     rbx, rax
0x180009925  jmp     loc_1800099C1
0x18000992a  mov     rcx, [r9+20h]; this
0x18000992e  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x180009933  mov     rbx, rax
0x180009936  lea     rcx, [rbp+57h+String2]
0x18000993a  call    ?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetComputerNameAsString(void)
0x18000993f  nop
0x180009940  test    rbx, rbx
0x180009943  jnz     short loc_180009953
0x180009945  lea     rbx, [rbp+57h+String2]
0x180009949  cmp     [rbp+57h+var_68], 8
0x18000994e  cmovnb  rbx, [rbp+57h+String2]
0x180009953  lea     rdx, [rbp+57h+String2]
0x180009957  cmp     [rbp+57h+var_68], 8
0x18000995c  cmovnb  rdx, [rbp+57h+String2]; String2
0x180009961  mov     rcx, rbx; String1
0x180009964  call    cs:__imp__wcsicmp
0x18000996a  lea     rcx, [rbp+57h+var_40]
0x18000996e  test    eax, eax
0x180009970  jnz     short loc_18000997E
0x180009972  mov     edx, 129h
0x180009977  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18000997c  jmp     short loc_18000998B
0x18000997e  mov     r8, rbx
0x180009981  mov     edx, 7Ch ; '|'
0x180009986  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18000998b  mov     rdx, rax
0x18000998e  lea     rcx, [rbp+57h+var_60]
0x180009992  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180009997  xor     r8d, r8d
0x18000999a  mov     dl, 1
0x18000999c  lea     rcx, [rbp+57h+var_40]
0x1800099a0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800099a5  lea     rbx, [rbp+57h+var_60]
0x1800099a9  cmp     [rbp+57h+var_48], 8
0x1800099ae  cmovnb  rbx, [rbp+57h+var_60]
0x1800099b3  xor     r8d, r8d
0x1800099b6  mov     dl, 1
0x1800099b8  lea     rcx, [rbp+57h+String2]
0x1800099bc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800099c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800099c5  inc     r8
0x1800099c8  cmp     [rbx+r8*2], si
0x1800099cd  jnz     short loc_1800099C5
0x1800099cf  mov     rax, [rdi]
0x1800099d2  lea     r8d, ds:2[r8*2]
0x1800099da  xor     r9d, r9d
0x1800099dd  mov     rdx, rbx
0x1800099e0  mov     rcx, rdi
0x1800099e3  mov     rax, [rax+20h]
0x1800099e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ec  mov     ebx, eax
0x1800099ee  xor     r8d, r8d
0x1800099f1  mov     dl, 1
0x1800099f3  lea     rcx, [rbp+57h+var_60]
0x1800099f7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800099fc  mov     eax, ebx
0x1800099fe  mov     rcx, [rbp+57h+var_20]
0x180009a02  xor     rcx, rsp; StackCookie
0x180009a05  call    __security_check_cookie
0x180009a0a  mov     rbx, [rsp+0B0h+arg_10]
0x180009a12  add     rsp, 0A0h
0x180009a19  pop     rdi
0x180009a1a  pop     rsi
0x180009a1b  pop     rbp
0x180009a1c  retn
```
