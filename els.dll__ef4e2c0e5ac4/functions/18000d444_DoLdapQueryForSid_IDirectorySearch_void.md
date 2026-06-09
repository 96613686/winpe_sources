# DoLdapQueryForSid(IDirectorySearch *,void *)

- ea: `0x18000d444`
- end: `0x18000d688`
- name: `?DoLdapQueryForSid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIDirectorySearch@@PEAX@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000e208`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x18000d444`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18000d50f`
- `ADVAPI32!GetLengthSid` at `0x18000d50f`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000d65f`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000d65f`
- `ACTIVEDS!__imp_ADsEncodeBinaryData` at `0x18000d51f`
- `ACTIVEDS!__imp_ADsEncodeBinaryData` at `0x18000d51f`

## string_xrefs

- `0x18000d52d`: `(objectSid=`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DoLdapQueryForSid(__int64 a1, __int64 a2, void *a3)
{
  DWORD LengthSid; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h]
  LPWSTR ppszDestData; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  _QWORD v23[4]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v24[32]; // [rsp+A0h] [rbp-60h] BYREF

  v22 = a1;
  ppszDestData = 0;
  v15 = 0;
  std::wstring::wstring(a1);
  v16 = 1;
  memset_0(v24, 0, 0x78u);
  v24[0] = 1;
  v24[2] = 7;
  v24[4] = 3;
  v24[10] = 5;
  v24[12] = 7;
  v24[14] = 2;
  v24[20] = 13;
  v24[22] = 6;
  v24[24] = 1;
  if ( (*(int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a2 + 24LL))(a2, v24) >= 0 )
  {
    std::wstring::wstring(v23);
    LengthSid = GetLengthSid(a3);
    if ( ADsEncodeBinaryData((PBYTE)a3, LengthSid, &ppszDestData) >= 0 )
    {
      std::wstring::assign(v23, L"(objectSid=");
      v8 = std::char_traits<unsigned short>::length(ppszDestData);
      std::wstring::append(v23, v9, v8);
      v10 = std::char_traits<unsigned short>::length(L")");
      std::wstring::append(v23, v11, v10);
      v18 = L"name";
      v12 = v23;
      if ( v23[3] >= 8u )
        v12 = (_QWORD *)v23[0];
      if ( (*(int (__fastcall **)(__int64, _QWORD *, const wchar_t **, __int64, __int64 *))(*(_QWORD *)a2 + 32LL))(
             a2,
             v12,
             &v18,
             1,
             &v15) >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 48LL))(a2, v15);
        if ( v13 >= 0 && v13 != 20498 )
        {
          v19 = 0;
          v20 = 0;
          v21 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, const wchar_t *, __int128 *))(*(_QWORD *)a2 + 80LL))(
                 a2,
                 v15,
                 v18,
                 &v19) >= 0 )
          {
            std::wstring::assign(a1, *(_QWORD *)(v20 + 8));
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 88LL))(a2, &v19);
          }
        }
      }
    }
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v23, v7, 0);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 96LL))(a2);
  if ( ppszDestData )
    FreeADsMem(ppszDestData);
  return a1;
}

```

## disassembly

```asm
0x18000d444  mov     [rsp-8+arg_18], rbx
0x18000d449  push    rbp
0x18000d44a  push    rsi
0x18000d44b  push    rdi
0x18000d44c  lea     rbp, [rsp-30h]
0x18000d451  sub     rsp, 130h
0x18000d458  mov     rax, cs:__security_cookie
0x18000d45f  xor     rax, rsp
0x18000d462  mov     [rbp+40h+var_20], rax
0x18000d466  mov     rsi, r8
0x18000d469  mov     rbx, rdx
0x18000d46c  mov     rdi, rcx
0x18000d46f  mov     [rsp+140h+var_C8], rcx
0x18000d474  mov     [rsp+140h+var_108], 0
0x18000d47c  mov     [rsp+140h+ppszDestData], 0
0x18000d485  mov     [rsp+140h+var_110], 0
0x18000d48e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d493  mov     [rsp+140h+var_108], 1
0x18000d49b  xor     edx, edx; Val
0x18000d49d  lea     r8d, [rdx+78h]; Size
0x18000d4a1  lea     rcx, [rbp+40h+var_A0]; void *
0x18000d4a5  call    memset_0
0x18000d4aa  mov     [rbp+40h+var_A0], 1
0x18000d4b1  mov     eax, 7
0x18000d4b6  mov     [rbp+40h+var_98], eax
0x18000d4b9  lea     r8d, [rax-4]
0x18000d4bd  mov     [rbp+40h+var_90], r8d
0x18000d4c1  mov     [rbp+40h+var_78], 5
0x18000d4c8  mov     [rbp+40h+var_70], eax
0x18000d4cb  mov     [rbp+40h+var_68], 2
0x18000d4d2  mov     [rbp+40h+var_50], 0Dh
0x18000d4d9  mov     [rbp+40h+var_48], 6
0x18000d4e0  mov     [rbp+40h+var_40], 1
0x18000d4e7  mov     rax, [rbx]
0x18000d4ea  lea     rdx, [rbp+40h+var_A0]
0x18000d4ee  mov     rcx, rbx
0x18000d4f1  mov     rax, [rax+18h]
0x18000d4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4fa  test    eax, eax
0x18000d4fc  js      loc_18000D63C
0x18000d502  lea     rcx, [rbp+40h+var_C0]
0x18000d506  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d50b  nop
0x18000d50c  mov     rcx, rsi; pSid
0x18000d50f  call    cs:__imp_GetLengthSid
0x18000d515  mov     edx, eax; dwSrcLen
0x18000d517  lea     r8, [rsp+140h+ppszDestData]; ppszDestData
0x18000d51c  mov     rcx, rsi; pbSrcData
0x18000d51f  call    cs:__imp_ADsEncodeBinaryData
0x18000d525  test    eax, eax
0x18000d527  js      loc_18000D62E
0x18000d52d  lea     rdx, aObjectsid; "(objectSid="
0x18000d534  lea     rcx, [rbp+40h+var_C0]
0x18000d538  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d53d  mov     rcx, [rsp+140h+ppszDestData]
0x18000d542  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000d547  mov     r8, rax
0x18000d54a  mov     rdx, rcx
0x18000d54d  lea     rcx, [rbp+40h+var_C0]
0x18000d551  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d556  lea     rcx, asc_180028EB0; ")"
0x18000d55d  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18000d562  mov     r8, rax
0x18000d565  mov     rdx, rcx
0x18000d568  lea     rcx, [rbp+40h+var_C0]
0x18000d56c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000d571  lea     rax, aName; "name"
0x18000d578  mov     [rsp+140h+var_F8], rax
0x18000d57d  mov     rax, [rbx]
0x18000d580  lea     rdx, [rbp+40h+var_C0]
0x18000d584  cmp     [rbp+40h+var_A8], 8
0x18000d589  cmovnb  rdx, [rbp+40h+var_C0]
0x18000d58e  lea     rcx, [rsp+140h+var_110]
0x18000d593  mov     [rsp+140h+var_120], rcx
0x18000d598  mov     r9d, 1
0x18000d59e  lea     r8, [rsp+140h+var_F8]
0x18000d5a3  mov     rcx, rbx
0x18000d5a6  mov     rax, [rax+20h]
0x18000d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5af  test    eax, eax
0x18000d5b1  js      short loc_18000D62E
0x18000d5b3  mov     rax, [rbx]
0x18000d5b6  mov     rdx, [rsp+140h+var_110]
0x18000d5bb  mov     rcx, rbx
0x18000d5be  mov     rax, [rax+30h]
0x18000d5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c7  test    eax, eax
0x18000d5c9  js      short loc_18000D62E
0x18000d5cb  cmp     eax, 5012h
0x18000d5d0  jz      short loc_18000D62E
0x18000d5d2  xorps   xmm0, xmm0
0x18000d5d5  xor     eax, eax
0x18000d5d7  movups  [rsp+140h+var_F0], xmm0
0x18000d5dc  movups  [rsp+140h+var_E0], xmm0
0x18000d5e1  mov     [rsp+140h+var_D0], rax
0x18000d5e6  mov     rax, [rbx]
0x18000d5e9  lea     r9, [rsp+140h+var_F0]
0x18000d5ee  mov     r8, [rsp+140h+var_F8]
0x18000d5f3  mov     rdx, [rsp+140h+var_110]
0x18000d5f8  mov     rcx, rbx
0x18000d5fb  mov     rax, [rax+50h]
0x18000d5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d604  test    eax, eax
0x18000d606  js      short loc_18000D62E
0x18000d608  mov     rdx, qword ptr [rsp+140h+var_E0]
0x18000d60d  mov     rdx, [rdx+8]
0x18000d611  mov     rcx, rdi
0x18000d614  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000d619  mov     rax, [rbx]
0x18000d61c  lea     rdx, [rsp+140h+var_F0]
0x18000d621  mov     rcx, rbx
0x18000d624  mov     rax, [rax+58h]
0x18000d628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d62d  nop
0x18000d62e  xor     r8d, r8d
0x18000d631  mov     dl, 1
0x18000d633  lea     rcx, [rbp+40h+var_C0]
0x18000d637  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d63c  mov     rdx, [rsp+140h+var_110]
0x18000d641  test    rdx, rdx
0x18000d644  jz      short loc_18000D655
0x18000d646  mov     rax, [rbx]
0x18000d649  mov     rcx, rbx
0x18000d64c  mov     rax, [rax+60h]
0x18000d650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d655  mov     rcx, [rsp+140h+ppszDestData]; pMem
0x18000d65a  test    rcx, rcx
0x18000d65d  jz      short loc_18000D665
0x18000d65f  call    cs:__imp_FreeADsMem
0x18000d665  mov     rax, rdi
0x18000d668  mov     rcx, [rbp+40h+var_20]
0x18000d66c  xor     rcx, rsp; StackCookie
0x18000d66f  call    __security_check_cookie
0x18000d674  mov     rbx, [rsp+140h+arg_18]
0x18000d67c  add     rsp, 130h
0x18000d683  pop     rdi
0x18000d684  pop     rsi
0x18000d685  pop     rbp
0x18000d686  retn
```
