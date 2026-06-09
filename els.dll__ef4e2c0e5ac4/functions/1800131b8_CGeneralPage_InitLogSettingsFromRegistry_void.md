# CGeneralPage::_InitLogSettingsFromRegistry(void)

- ea: `0x1800131b8`
- end: `0x18001336a`
- name: `?_InitLogSettingsFromRegistry@CGeneralPage@@IEAAXXZ`
- size: `434`
- prototype: `void __fastcall(CGeneralPage *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180013810`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x1800131b8`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x18001aef4`
- `0x1800222d0`

## string_xrefs

- `0x18001320a`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CGeneralPage::_InitLogSettingsFromRegistry(CGeneralPage *this)
{
  unsigned int *v2; // rdi
  unsigned int *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  HKEY v10; // rdx
  const unsigned __int16 *v11; // r8
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int16 *v14[4]; // [rsp+30h] [rbp-38h] BYREF

  v12 = 0;
  phkResult = 0;
  v2 = (unsigned int *)((char *)this + 68);
  *((_DWORD *)this + 17) = 0x4000;
  *((_DWORD *)this + 18) = 122;
  v3 = (unsigned int *)((char *)this + 76);
  *((_DWORD *)this + 19) = 7;
  std::wstring::wstring(v14);
  std::wstring::assign(v14, L"SYSTEM\\CurrentControlSet\\Services\\EventLog");
  v4 = std::char_traits<unsigned short>::length(L"\\");
  std::wstring::append(v14, v5, v4);
  v6 = std::char_traits<unsigned short>::length(*((_QWORD *)this + 7) + 554LL);
  std::wstring::append(v14, v7, v6);
  v8 = *((_QWORD *)this + 7) + 32LL;
  if ( (-(__int64)(*(_WORD *)v8 != 0) & v8) != 0 )
  {
    if ( (int)CSafeReg::Connect(&phkResult, (LPCWSTR)(v8 & -(__int64)(*(_WORD *)v8 != 0)), (HCURSOR)v8) < 0 )
      goto LABEL_19;
    v10 = phkResult;
  }
  else
  {
    v10 = HKEY_LOCAL_MACHINE;
  }
  v11 = (const unsigned __int16 *)v14;
  if ( v14[3] >= (unsigned __int16 *)8 )
    v11 = v14[0];
  if ( (int)CSafeReg::Open((CSafeReg *)&v12, v10, v11, 1u) >= 0 )
  {
    if ( (int)CSafeReg::QueryDword((CSafeReg *)&v12, L"MaxSize", v2) < 0 )
      *v2 = 0x80000;
    *v2 >>= 10;
    if ( (int)CSafeReg::QueryDword((CSafeReg *)&v12, L"Retention", v3) < 0 )
      *v3 = 604800;
    if ( *v3 == -1 )
    {
      *((_DWORD *)this + 18) = 124;
LABEL_16:
      *v3 = 7;
      goto LABEL_19;
    }
    if ( !*v3 )
    {
      *((_DWORD *)this + 18) = 122;
      goto LABEL_16;
    }
    *((_DWORD *)this + 18) = 123;
    v9 = *v3 / 0x15180;
    *v3 = v9;
    if ( (unsigned int)v9 > 0x16D )
      *v3 = 365;
  }
LABEL_19:
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v14, v9, 0);
  CSafeReg::Close((CSafeReg *)&phkResult);
  CSafeReg::Close((CSafeReg *)&v12);
}

```

## disassembly

```asm
0x1800131b8  push    rbp
0x1800131ba  push    rbx
0x1800131bb  push    rsi
0x1800131bc  push    rdi
0x1800131bd  mov     rbp, rsp
0x1800131c0  sub     rsp, 68h
0x1800131c4  mov     rax, cs:__security_cookie
0x1800131cb  xor     rax, rsp
0x1800131ce  mov     [rbp+var_18], rax
0x1800131d2  mov     rsi, rcx
0x1800131d5  mov     [rbp+var_48], 0
0x1800131dd  mov     [rbp+phkResult], 0
0x1800131e5  lea     rdi, [rcx+44h]
0x1800131e9  mov     dword ptr [rdi], 4000h
0x1800131ef  mov     dword ptr [rcx+48h], 7Ah ; 'z'
0x1800131f6  lea     rbx, [rcx+4Ch]
0x1800131fa  mov     dword ptr [rbx], 7
0x180013200  lea     rcx, [rbp+var_38]
0x180013204  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013209  nop
0x18001320a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180013211  lea     rcx, [rbp+var_38]
0x180013215  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001321a  lea     rcx, SubBlock; "\\"
0x180013221  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180013226  mov     r8, rax
0x180013229  mov     rdx, rcx
0x18001322c  lea     rcx, [rbp+var_38]
0x180013230  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180013235  mov     rcx, [rsi+38h]
0x180013239  add     rcx, 22Ah
0x180013240  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180013245  mov     r8, rax
0x180013248  mov     rdx, rcx
0x18001324b  lea     rcx, [rbp+var_38]
0x18001324f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180013254  mov     r8, [rsi+38h]
0x180013258  add     r8, 20h ; ' '; HKEY
0x18001325c  movzx   edx, word ptr [r8]
0x180013260  movzx   eax, dx
0x180013263  neg     ax
0x180013266  sbb     rcx, rcx
0x180013269  test    r8, rcx
0x18001326c  jz      short loc_18001328E
0x18001326e  neg     dx
0x180013271  sbb     rdx, rdx
0x180013274  and     rdx, r8; lpMachineName
0x180013277  lea     rcx, [rbp+phkResult]; phkResult
0x18001327b  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180013280  test    eax, eax
0x180013282  js      loc_180013333
0x180013288  mov     rdx, [rbp+phkResult]
0x18001328c  jmp     short loc_180013295
0x18001328e  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180013295  lea     r8, [rbp+var_38]
0x180013299  cmp     [rbp+var_20], 8
0x18001329e  cmovnb  r8, [rbp+var_38]; unsigned __int16 *
0x1800132a3  mov     r9d, 1; unsigned int
0x1800132a9  lea     rcx, [rbp+var_48]; this
0x1800132ad  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800132b2  test    eax, eax
0x1800132b4  js      short loc_180013333
0x1800132b6  mov     r8, rdi; unsigned int *
0x1800132b9  lea     rdx, aMaxsize; "MaxSize"
0x1800132c0  lea     rcx, [rbp+var_48]; this
0x1800132c4  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x1800132c9  test    eax, eax
0x1800132cb  jns     short loc_1800132D3
0x1800132cd  mov     dword ptr [rdi], 80000h
0x1800132d3  shr     dword ptr [rdi], 0Ah
0x1800132d6  mov     r8, rbx; unsigned int *
0x1800132d9  lea     rdx, aRetention; "Retention"
0x1800132e0  lea     rcx, [rbp+var_48]; this
0x1800132e4  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x1800132e9  test    eax, eax
0x1800132eb  jns     short loc_1800132F3
0x1800132ed  mov     dword ptr [rbx], 93A80h
0x1800132f3  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800132f6  jnz     short loc_180013301
0x1800132f8  mov     dword ptr [rsi+48h], 7Ch ; '|'
0x1800132ff  jmp     short loc_18001330D
0x180013301  cmp     dword ptr [rbx], 0
0x180013304  jnz     short loc_180013315
0x180013306  mov     dword ptr [rsi+48h], 7Ah ; 'z'
0x18001330d  mov     dword ptr [rbx], 7
0x180013313  jmp     short loc_180013333
0x180013315  mov     dword ptr [rsi+48h], 7Bh ; '{'
0x18001331c  mov     eax, 0C22E4507h
0x180013321  mul     dword ptr [rbx]
0x180013323  shr     edx, 10h
0x180013326  mov     [rbx], edx
0x180013328  mov     eax, 16Dh
0x18001332d  cmp     edx, eax
0x18001332f  jbe     short loc_180013333
0x180013331  mov     [rbx], eax
0x180013333  xor     r8d, r8d
0x180013336  mov     dl, 1
0x180013338  lea     rcx, [rbp+var_38]
0x18001333c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013341  nop
0x180013342  lea     rcx, [rbp+phkResult]; this
0x180013346  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001334b  nop
0x18001334c  lea     rcx, [rbp+var_48]; this
0x180013350  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180013355  mov     rcx, [rbp+var_18]
0x180013359  xor     rcx, rsp; StackCookie
0x18001335c  call    __security_check_cookie
0x180013361  add     rsp, 68h
0x180013365  pop     rdi
0x180013366  pop     rsi
0x180013367  pop     rbx
0x180013368  pop     rbp
0x180013369  retn
```
