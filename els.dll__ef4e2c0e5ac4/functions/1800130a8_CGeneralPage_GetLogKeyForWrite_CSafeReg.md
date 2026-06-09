# CGeneralPage::_GetLogKeyForWrite(CSafeReg *)

- ea: `0x1800130a8`
- end: `0x1800131b0`
- name: `?_GetLogKeyForWrite@CGeneralPage@@IEAAJPEAVCSafeReg@@@Z`
- size: `264`
- prototype: `int(CGeneralPage *__hidden this, struct CSafeReg *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180013370`
- `0x180013810`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x1800130a8`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x1800222d0`

## string_xrefs

- `0x1800130e0`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGeneralPage::_GetLogKeyForWrite(CGeneralPage *this, struct CSafeReg *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  HCURSOR v8; // r8
  const WCHAR *v9; // rdx
  int v10; // ebx
  HKEY v11; // rdx
  const unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  HKEY phkResult; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v16[4]; // [rsp+28h] [rbp-28h] BYREF

  std::wstring::wstring(v16);
  phkResult = 0;
  std::wstring::assign(v16, L"SYSTEM\\CurrentControlSet\\Services\\EventLog");
  v4 = std::char_traits<unsigned short>::length(L"\\");
  std::wstring::append(v16, v5, v4);
  v6 = std::char_traits<unsigned short>::length(*((_QWORD *)this + 7) + 554LL);
  std::wstring::append(v16, v7, v6);
  v9 = (const WCHAR *)((*((_QWORD *)this + 7) + 32LL) & -(__int64)(*(_WORD *)(*((_QWORD *)this + 7) + 32LL) != 0));
  if ( v9 )
  {
    v10 = CSafeReg::Connect(&phkResult, v9, v8);
    if ( v10 < 0 )
      goto LABEL_8;
    v11 = phkResult;
  }
  else
  {
    v11 = HKEY_LOCAL_MACHINE;
  }
  v12 = (const unsigned __int16 *)v16;
  if ( v16[3] >= (unsigned __int16 *)8 )
    v12 = v16[0];
  v10 = CSafeReg::Open(a2, v11, v12, 2u);
LABEL_8:
  CSafeReg::Close((CSafeReg *)&phkResult);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v16, v13, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800130a8  mov     [rsp-8+arg_10], rbx
0x1800130ad  mov     [rsp-8+arg_18], rdi
0x1800130b2  push    rbp
0x1800130b3  mov     rbp, rsp
0x1800130b6  sub     rsp, 50h
0x1800130ba  mov     rax, cs:__security_cookie
0x1800130c1  xor     rax, rsp
0x1800130c4  mov     [rbp+var_8], rax
0x1800130c8  mov     rdi, rdx
0x1800130cb  mov     rbx, rcx
0x1800130ce  lea     rcx, [rbp+var_28]
0x1800130d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800130d7  nop
0x1800130d8  mov     [rbp+phkResult], 0
0x1800130e0  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800130e7  lea     rcx, [rbp+var_28]
0x1800130eb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800130f0  lea     rcx, SubBlock; "\\"
0x1800130f7  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800130fc  mov     r8, rax
0x1800130ff  mov     rdx, rcx
0x180013102  lea     rcx, [rbp+var_28]
0x180013106  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001310b  mov     rcx, [rbx+38h]
0x18001310f  add     rcx, 22Ah
0x180013116  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001311b  mov     r8, rax
0x18001311e  mov     rdx, rcx
0x180013121  lea     rcx, [rbp+var_28]
0x180013125  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001312a  mov     rcx, [rbx+38h]
0x18001312e  add     rcx, 20h ; ' '
0x180013132  movzx   eax, word ptr [rcx]
0x180013135  neg     ax
0x180013138  sbb     rdx, rdx
0x18001313b  and     rdx, rcx; lpMachineName
0x18001313e  jz      short loc_180013155
0x180013140  lea     rcx, [rbp+phkResult]; phkResult
0x180013144  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180013149  mov     ebx, eax
0x18001314b  test    eax, eax
0x18001314d  js      short loc_18001317A
0x18001314f  mov     rdx, [rbp+phkResult]
0x180013153  jmp     short loc_18001315C
0x180013155  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001315c  lea     r8, [rbp+var_28]
0x180013160  cmp     [rbp+var_10], 8
0x180013165  mov     r9d, 2; unsigned int
0x18001316b  cmovnb  r8, [rbp+var_28]; unsigned __int16 *
0x180013170  mov     rcx, rdi; this
0x180013173  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180013178  mov     ebx, eax
0x18001317a  lea     rcx, [rbp+phkResult]; this
0x18001317e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180013183  nop
0x180013184  xor     r8d, r8d
0x180013187  mov     dl, 1
0x180013189  lea     rcx, [rbp+var_28]
0x18001318d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013192  mov     eax, ebx
0x180013194  mov     rcx, [rbp+var_8]
0x180013198  xor     rcx, rsp; StackCookie
0x18001319b  call    __security_check_cookie
0x1800131a0  mov     rbx, [rsp+50h+arg_10]
0x1800131a5  mov     rdi, [rsp+50h+arg_18]
0x1800131aa  add     rsp, 50h
0x1800131ae  pop     rbp
0x1800131af  retn
```
