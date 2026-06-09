# CreatePassword(uint,ushort * *)

- ea: `0x1400269f0`
- end: `0x140026c42`
- name: `?CreatePassword@@YAJIPEAPEAG@Z`
- size: `594`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012794`
- `0x140013f4c`
- `0x1400146cc`
- `0x140027f24`
- `0x140032274`

## callees

- `0x1400020f4`
- `0x140002463`
- `0x1400269f0`
- `0x140034ce4`
- `0x140040390`
- `0x140041640`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140026c04`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140026c18`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140026c04`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140026c18`
- `OLEAUT32!__imp_SysAllocString` at `0x140026bbb`
- `OLEAUT32!__imp_SysAllocString` at `0x140026bbb`

## string_xrefs

- `0x140026a88`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026aff`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026be9`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026a6e`: `CreatePassword`
- `0x140026ae5`: `CreatePassword`
- `0x140026be2`: `CreatePassword`

## pseudocode

```c
__int64 __fastcall CreatePassword(CEventLogger *a1, unsigned __int16 **a2)
{
  unsigned __int64 v2; // r14
  unsigned int v4; // ebx
  unsigned __int64 v5; // rax
  void *v6; // rsi
  unsigned __int8 *v7; // rax
  CEventLogger *v8; // rcx
  unsigned __int8 *v9; // rdi
  signed int RandomBytes; // eax
  CEventLogger *v11; // rcx
  unsigned int i; // r8d
  __int64 v13; // rdx
  unsigned __int16 *v14; // rax
  CEventLogger *v15; // rcx
  _QWORD v17[6]; // [rsp+30h] [rbp-49h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-19h]
  _OWORD v19[5]; // [rsp+80h] [rbp+7h]

  v2 = (unsigned int)a1;
  memset(v17, 0, sizeof(v17));
  v18[0] = *(_OWORD *)L"BCDFGHJKLMNPQRSTVWXYZ23456789";
  v18[1] = *(_OWORD *)L"LMNPQRSTVWXYZ23456789";
  v19[0] = *(_OWORD *)L"VWXYZ23456789";
  *(_OWORD *)((char *)v19 + 12) = *(_OWORD *)L"3456789";
  if ( a2 )
  {
    v5 = 2LL * (unsigned int)((_DWORD)a1 + 1);
    if ( !is_mul_ok((unsigned int)((_DWORD)a1 + 1), 2u) )
      v5 = -1;
    v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
    v7 = (unsigned __int8 *)operator new[](v2, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v7;
    if ( v6 )
    {
      if ( v7 )
      {
        memset_0(v6, 0, 2LL * (unsigned int)(v2 + 1));
        memset_0(v9, 0, v2);
        RandomBytes = CRAEncryption::GenerateRandomBytes((CRAEncryption *)v17, v9, v2);
        v4 = RandomBytes;
        if ( RandomBytes >= 0 )
        {
          for ( i = 0;
                i < (unsigned int)v2;
                *((_WORD *)v6 + v13) = *((_WORD *)v18 + (unsigned int)(int)(float)((double)v9[v13] * 0.00390625 * 29.0)) )
          {
            v13 = (int)i++;
          }
          v14 = SysAllocString((const OLECHAR *)v6);
          *a2 = v14;
          if ( !v14 )
          {
            v4 = -2147467261;
            CEventLogger::LogError(
              v15,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
              0x124Eu,
              L"CreatePassword",
              0x80004003);
          }
        }
        else
        {
          CEventLogger::LogError(
            v11,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
            0x1233u,
            L"CreatePassword",
            RandomBytes);
        }
      }
      else
      {
        v4 = -2147024882;
        CEventLogger::LogError(
          v8,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x122Eu,
          L"CreatePassword",
          0x8007000E);
      }
      operator delete[](v6);
    }
    else
    {
      v4 = -2147024882;
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x122Du,
        L"CreatePassword",
        0x8007000E);
    }
    if ( v9 )
      operator delete[](v9);
  }
  else
  {
    v4 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1220u,
      L"CreatePassword",
      0x80004003);
  }
  CRAEncryption::~CRAEncryption((CRAEncryption *)v17);
  return v4;
}

```

## disassembly

```asm
0x1400269f0  push    rbp
0x1400269f2  push    rbx
0x1400269f3  push    rsi
0x1400269f4  push    rdi
0x1400269f5  push    r12
0x1400269f7  push    r14
0x1400269f9  push    r15
0x1400269fb  lea     rbp, [rsp-27h]
0x140026a00  sub     rsp, 0A0h
0x140026a07  mov     r14d, ecx
0x140026a0a  mov     r15, rdx
0x140026a0d  mov     [rbp+57h+var_A0], 0
0x140026a15  mov     [rbp+57h+var_98], 0
0x140026a1d  mov     [rbp+57h+var_90], 0
0x140026a25  mov     [rbp+57h+var_88], 0
0x140026a2d  mov     [rbp+57h+var_80], 0
0x140026a35  mov     [rbp+57h+var_78], 0
0x140026a3d  movups  xmm0, xmmword ptr cs:aBcdfghjklmnpqr; "BCDFGHJKLMNPQRSTVWXYZ23456789"
0x140026a44  movups  xmm1, xmmword ptr cs:aBcdfghjklmnpqr+10h; "LMNPQRSTVWXYZ23456789"
0x140026a4b  movups  [rbp+57h+var_70], xmm0
0x140026a4f  movups  xmm0, xmmword ptr cs:aBcdfghjklmnpqr+20h; "VWXYZ23456789"
0x140026a56  movups  [rbp+57h+var_60], xmm1
0x140026a5a  movups  xmm1, xmmword ptr cs:aBcdfghjklmnpqr+2Ch; "3456789"
0x140026a61  movups  [rbp+57h+var_50], xmm0
0x140026a65  movups  [rbp+57h+var_50+0Ch], xmm1
0x140026a69  test    rdx, rdx
0x140026a6c  jnz     short loc_140026AA5
0x140026a6e  lea     rax, aCreatepassword; "CreatePassword"
0x140026a75  mov     [rsp+0D0h+var_A8], 80004003h; unsigned int
0x140026a7d  mov     r9d, 1220h; unsigned int
0x140026a83  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x140026a88  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026a8f  mov     ebx, 80004003h
0x140026a94  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026a9b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026aa0  jmp     loc_140026C24
0x140026aa5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140026aac  lea     ebx, [r14+1]
0x140026ab0  mov     eax, 2
0x140026ab5  mul     rbx
0x140026ab8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140026abf  cmovb   rax, rcx
0x140026ac3  mov     rcx, rax; unsigned __int64
0x140026ac6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140026acb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140026ad2  mov     rcx, r14; unsigned __int64
0x140026ad5  mov     rsi, rax
0x140026ad8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140026add  mov     rdi, rax
0x140026ae0  test    rsi, rsi
0x140026ae3  jnz     short loc_140026B1C
0x140026ae5  lea     rax, aCreatepassword; "CreatePassword"
0x140026aec  mov     [rsp+0D0h+var_A8], 8007000Eh; unsigned int
0x140026af4  mov     r9d, 122Dh; unsigned int
0x140026afa  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x140026aff  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026b06  mov     ebx, 8007000Eh
0x140026b0b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026b12  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026b17  jmp     loc_140026C10
0x140026b1c  test    rdi, rdi
0x140026b1f  jnz     short loc_140026B39
0x140026b21  mov     ebx, 8007000Eh
0x140026b26  mov     [rsp+0D0h+var_A8], 8007000Eh
0x140026b2e  mov     r9d, 122Eh
0x140026b34  jmp     loc_140026BE2
0x140026b39  lea     r8, [rbx+rbx]; Size
0x140026b3d  xor     edx, edx; Val
0x140026b3f  mov     rcx, rsi; void *
0x140026b42  call    memset_0
0x140026b47  mov     r8, r14; Size
0x140026b4a  xor     edx, edx; Val
0x140026b4c  mov     rcx, rdi; void *
0x140026b4f  call    memset_0
0x140026b54  mov     r8d, r14d; unsigned int
0x140026b57  lea     rcx, [rbp+57h+var_A0]; this
0x140026b5b  mov     rdx, rdi; unsigned __int8 *
0x140026b5e  call    ?GenerateRandomBytes@CRAEncryption@@QEAAJPEAEI@Z; CRAEncryption::GenerateRandomBytes(uchar *,uint)
0x140026b63  mov     ebx, eax
0x140026b65  test    eax, eax
0x140026b67  jns     short loc_140026B75
0x140026b69  mov     [rsp+0D0h+var_A8], eax
0x140026b6d  mov     r9d, 1233h
0x140026b73  jmp     short loc_140026BE2
0x140026b75  xor     r8d, r8d
0x140026b78  test    r14d, r14d
0x140026b7b  jz      short loc_140026BB8
0x140026b7d  movsxd  rdx, r8d
0x140026b80  inc     r8d
0x140026b83  movzx   eax, byte ptr [rdx+rdi]
0x140026b87  movd    xmm0, eax
0x140026b8b  cvtdq2pd xmm0, xmm0
0x140026b8f  mulsd   xmm0, cs:__real@3f70000000000000
0x140026b97  mulsd   xmm0, cs:__real@403d000000000000
0x140026b9f  cvtpd2ps xmm0, xmm0
0x140026ba3  cvttss2si rcx, xmm0
0x140026ba8  mov     ecx, ecx
0x140026baa  movzx   eax, word ptr [rbp+rcx*2+57h+var_70]
0x140026baf  mov     [rsi+rdx*2], ax
0x140026bb3  cmp     r8d, r14d
0x140026bb6  jb      short loc_140026B7D
0x140026bb8  mov     rcx, rsi; psz
0x140026bbb  call    cs:__imp_SysAllocString
0x140026bc2  nop     dword ptr [rax+rax+00h]
0x140026bc7  mov     [r15], rax
0x140026bca  test    rax, rax
0x140026bcd  jnz     short loc_140026C01
0x140026bcf  mov     ebx, 80004003h
0x140026bd4  mov     [rsp+0D0h+var_A8], 80004003h; unsigned int
0x140026bdc  mov     r9d, 124Eh; unsigned int
0x140026be2  lea     rax, aCreatepassword; "CreatePassword"
0x140026be9  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026bf0  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x140026bf5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026bfc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026c01  mov     rcx, rsi
0x140026c04  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140026c0b  nop     dword ptr [rax+rax+00h]
0x140026c10  test    rdi, rdi
0x140026c13  jz      short loc_140026C24
0x140026c15  mov     rcx, rdi
0x140026c18  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140026c1f  nop     dword ptr [rax+rax+00h]
0x140026c24  lea     rcx, [rbp+57h+var_A0]; this
0x140026c28  call    ??1CRAEncryption@@QEAA@XZ; CRAEncryption::~CRAEncryption(void)
0x140026c2d  mov     eax, ebx
0x140026c2f  add     rsp, 0A0h
0x140026c36  pop     r15
0x140026c38  pop     r14
0x140026c3a  pop     r12
0x140026c3c  pop     rdi
0x140026c3d  pop     rsi
0x140026c3e  pop     rbx
0x140026c3f  pop     rbp
0x140026c40  retn
```
