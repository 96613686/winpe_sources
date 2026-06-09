# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Peek(uint *,uint *,uint *)

- ea: `0x180011634`
- end: `0x180011746`
- name: `?Peek@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXPEAI00@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011048`

## callees

- `0x1800036f0`
- `0x18000d590`
- `0x1800107bc`
- `0x180011634`
- `0x180012144`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Peek(
        void **a1,
        _DWORD *a2,
        _DWORD *a3)
{
  void *v5; // rcx
  unsigned int v6; // eax
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-60h]
  int v9; // [rsp+20h] [rbp-60h]
  const char *v10; // [rsp+28h] [rbp-58h]
  __int64 v11; // [rsp+40h] [rbp-40h] BYREF
  __int64 v12; // [rsp+48h] [rbp-38h] BYREF
  int v13; // [rsp+50h] [rbp-30h]
  __int128 v14; // [rsp+58h] [rbp-28h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
      (const char *)0x80004003LL,
      v8);
  if ( !a3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
      (const char *)0x80004003LL,
      v8);
  v5 = *a1;
  v13 = 13;
  v15 = 0;
  LODWORD(v11) = 0;
  v12 = 12;
  v14 = 0;
  v6 = Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(
         v5,
         (__int64)a2,
         &v12,
         0xCu,
         &v14,
         0x18u,
         &v11);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x179,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
    (const char *)v6,
    (int)"Failed to peek channel",
    v10);
  if ( (unsigned int)v11 < 0x18 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
      (const char *)0x800705B6LL,
      v9);
  *a2 = DWORD2(v14);
  result = DWORD1(v14);
  *a3 = DWORD1(v14);
  return result;
}

```

## disassembly

```asm
0x180011634  push    rbp
0x180011636  push    rbx
0x180011637  push    rdi
0x180011638  mov     rbp, rsp
0x18001163b  sub     rsp, 80h
0x180011642  mov     rax, cs:__security_cookie
0x180011649  xor     rax, rsp
0x18001164c  mov     [rbp+var_10], rax
0x180011650  mov     rbx, r8
0x180011653  mov     rdi, rdx
0x180011656  test    rdx, rdx
0x180011659  jnz     short loc_180011677
0x18001165b  mov     rcx, [rbp+18h]; this
0x18001165f  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011666  mov     r9d, 80004003h; char *
0x18001166c  mov     edx, 167h; void *
0x180011671  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011677  test    rbx, rbx
0x18001167a  jnz     short loc_180011698
0x18001167c  mov     rcx, [rbp+18h]; this
0x180011680  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011687  mov     r9d, 80004003h; char *
0x18001168d  mov     edx, 168h; void *
0x180011692  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011698  mov     rcx, [rcx]; FileHandle
0x18001169b  lea     r8, [rbp+var_38]
0x18001169f  xor     eax, eax
0x1800116a1  mov     [rbp+var_30], 0Dh
0x1800116a8  mov     [rbp+var_18], rax
0x1800116ac  mov     r9d, 0Ch
0x1800116b2  mov     dword ptr [rbp+var_40], eax
0x1800116b5  xorps   xmm0, xmm0
0x1800116b8  lea     rax, [rbp+var_40]
0x1800116bc  mov     [rbp+var_38], r9
0x1800116c0  mov     [rsp+80h+var_50], rax; __int64
0x1800116c5  lea     rax, [rbp+var_28]
0x1800116c9  mov     dword ptr [rsp+80h+var_58], 18h; char *
0x1800116d1  mov     [rsp+80h+var_60], rax; PVOID
0x1800116d6  movups  [rbp+var_28], xmm0
0x1800116da  call    ?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x1800116df  mov     rcx, [rbp+18h]; this
0x1800116e3  lea     rdx, aFailedToPeekCh; "Failed to peek channel"
0x1800116ea  mov     [rsp+80h+var_60], rdx; int
0x1800116ef  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800116f6  mov     edx, 179h; void *
0x1800116fb  mov     r9d, eax; char *
0x1800116fe  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180011703  cmp     dword ptr [rbp+var_40], 18h
0x180011707  jnb     short loc_180011725
0x180011709  mov     rcx, [rbp+18h]; this
0x18001170d  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011714  mov     r9d, 800705B6h; char *
0x18001171a  mov     edx, 17Ah; void *
0x18001171f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011725  mov     eax, dword ptr [rbp+var_28+8]
0x180011728  mov     [rdi], eax
0x18001172a  mov     eax, dword ptr [rbp+var_28+4]
0x18001172d  mov     [rbx], eax
0x18001172f  mov     rcx, [rbp+var_10]
0x180011733  xor     rcx, rsp; StackCookie
0x180011736  call    __security_check_cookie
0x18001173b  add     rsp, 80h
0x180011742  pop     rdi
0x180011743  pop     rbx
0x180011744  pop     rbp
0x180011745  retn
```
