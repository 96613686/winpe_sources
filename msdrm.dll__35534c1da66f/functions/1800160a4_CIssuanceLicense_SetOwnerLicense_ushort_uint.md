# CIssuanceLicense::SetOwnerLicense(ushort *,uint)

- ea: `0x1800160a4`
- end: `0x1800162b4`
- name: `?SetOwnerLicense@CIssuanceLicense@@QEAAJPEAGI@Z`
- size: `528`
- prototype: `int(CIssuanceLicense *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180016bb0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180015438`
- `0x1800160a4`
- `0x180017358`
- `0x18001f020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001627a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001627a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800160d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800160d3`

## string_xrefs

- `0x180016223`: `<?xml version="1.0"?>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::SetOwnerLicense(CIssuanceLicense *this, unsigned __int8 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r15
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  unsigned __int16 *v7; // rdi
  int v8; // ebx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+50h] [rbp-48h]
  __int64 v21; // [rsp+58h] [rbp-40h]
  char *v22; // [rsp+60h] [rbp-38h]
  __int64 v23; // [rsp+68h] [rbp-30h] BYREF
  void *Block; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+18h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+20h]

  v21 = -2;
  v3 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v22 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v7 = 0;
  v26 = 0;
  Block = 0;
  v25 = 0;
  v8 = CDRMCBase::Base64EncodeData(2 * (int)v3, a2, &v25, (unsigned __int16 **)&Block);
  if ( v8 >= 0 )
  {
    v9 = v3 + 21;
    if ( v3 + 21 < v3 || v9 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
    v10 = (unsigned int)v9;
    v11 = (unsigned int)v9 + 18LL;
    if ( v11 < v10 || v11 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
    v12 = (unsigned int)v11;
    v13 = (unsigned int)v11 + 13LL;
    if ( v13 < v12 || v13 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
    v14 = (unsigned int)v13 + v25;
    if ( (unsigned int)v14 < (unsigned int)v13 )
    {
      try
      {
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
      }
      catch ( SafeIntException v23 )
      {
        v25 = -2147467259;
        v8 = -2147467259;
        v7 = v26;
        v6 = v20;
        goto LABEL_17;
      }
    }
    v15 = (unsigned int)v14;
    v16 = v14 + 14;
    if ( v16 < v15 || v16 > 0xFFFFFFFF )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
    v17 = v16 + *(_DWORD *)(*((_QWORD *)this + 118) + 280LL);
    if ( v17 < (unsigned int)v16 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
    if ( v17 == -1 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
    v18 = v17 + 1;
    v7 = (unsigned __int16 *)operator new[](saturated_mul(v18, 2u));
    if ( v7 )
    {
      v8 = StringCchPrintfW(
             v7,
             v18,
             L"%s%s%s%s%s%s",
             L"<?xml version=\"1.0\"?>",
             L"<CERTIFICATECHAIN>",
             L"<CERTIFICATE>",
             Block,
             L"</CERTIFICATE>",
             *(_QWORD *)(*((_QWORD *)this + 118) + 272LL));
      if ( v8 >= 0 )
      {
        *((_QWORD *)this + 116) = v7;
        v7 = 0;
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
LABEL_17:
  operator delete(v7);
  operator delete(Block);
  LeaveCriticalSection(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800160a4  push    rbx
0x1800160a6  push    rsi
0x1800160a7  push    rdi
0x1800160a8  push    r14
0x1800160aa  push    r15
0x1800160ac  sub     rsp, 70h
0x1800160b0  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800160b9  mov     r15d, r8d
0x1800160bc  mov     rbx, rdx
0x1800160bf  mov     r14, rcx
0x1800160c2  lea     rsi, [rcx+58h]
0x1800160c6  mov     [rsp+98h+var_48], rsi
0x1800160cb  mov     [rsp+98h+var_38], rsi
0x1800160d0  mov     rcx, rsi; lpCriticalSection
0x1800160d3  call    cs:__imp_EnterCriticalSection
0x1800160d9  nop
0x1800160da  xor     edi, edi
0x1800160dc  mov     [rsp+98h+arg_18], rdi
0x1800160e4  mov     [rsp+98h+Block], rdi
0x1800160ec  mov     [rsp+98h+arg_10], edi
0x1800160f3  lea     ecx, [r15+r15]; unsigned int
0x1800160f7  lea     r9, [rsp+98h+Block]; unsigned __int16 **
0x1800160ff  lea     r8, [rsp+98h+arg_10]; unsigned int *
0x180016107  mov     rdx, rbx; unsigned __int8 *
0x18001610a  call    ?Base64EncodeData@CDRMCBase@@SAJIPEAEPEAIPEAPEAG@Z; CDRMCBase::Base64EncodeData(uint,uchar *,uint *,ushort * *)
0x18001610f  mov     ebx, eax
0x180016111  test    eax, eax
0x180016113  js      loc_180016261
0x180016119  lea     rcx, [r15+15h]
0x18001611d  cmp     rcx, r15
0x180016120  jb      loc_1800162AD
0x180016126  mov     r8d, 0FFFFFFFFh
0x18001612c  cmp     rcx, r8
0x18001612f  ja      loc_1800162AD
0x180016135  mov     eax, ecx
0x180016137  lea     rcx, [rax+12h]
0x18001613b  cmp     rcx, rax
0x18001613e  jb      loc_1800162A8
0x180016144  cmp     rcx, r8
0x180016147  ja      loc_1800162A8
0x18001614d  mov     eax, ecx
0x18001614f  lea     rcx, [rax+0Dh]
0x180016153  cmp     rcx, rax
0x180016156  jb      loc_1800162A3
0x18001615c  cmp     rcx, r8
0x18001615f  ja      loc_1800162A3
0x180016165  mov     edx, [rsp+98h+arg_10]
0x18001616c  add     edx, ecx
0x18001616e  cmp     edx, ecx
0x180016170  jb      loc_18001628E
0x180016176  mov     eax, edx
0x180016178  add     rdx, 0Eh
0x18001617c  cmp     rdx, rax
0x18001617f  jb      loc_18001629E
0x180016185  cmp     rdx, r8
0x180016188  ja      loc_18001629E
0x18001618e  mov     rax, [r14+3B0h]
0x180016195  mov     eax, [rax+118h]
0x18001619b  add     eax, edx
0x18001619d  cmp     eax, edx
0x18001619f  jb      loc_180016294
0x1800161a5  cmp     eax, r8d
0x1800161a8  jz      loc_180016299
0x1800161ae  inc     eax
0x1800161b0  mov     ebx, eax
0x1800161b2  mov     eax, 2
0x1800161b7  mul     rbx
0x1800161ba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800161c1  cmovb   rax, rcx
0x1800161c5  mov     rcx, rax; unsigned __int64
0x1800161c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800161cd  mov     rdi, rax
0x1800161d0  test    rax, rax
0x1800161d3  jnz     short loc_1800161DF
0x1800161d5  mov     ebx, 8007000Eh
0x1800161da  jmp     loc_180016261
0x1800161df  mov     rax, [r14+3B0h]
0x1800161e6  mov     rcx, [rax+110h]
0x1800161ed  mov     [rsp+98h+var_58], rcx
0x1800161f2  lea     rax, ?g_wszCertificateCloseNode@@3QBGB; "</CERTIFICATE>"
0x1800161f9  mov     [rsp+98h+var_60], rax
0x1800161fe  mov     rax, [rsp+98h+Block]
0x180016206  mov     [rsp+98h+var_68], rax
0x18001620b  lea     rax, ?g_wszCertificateOpenNode@@3QBGB; "<CERTIFICATE>"
0x180016212  mov     [rsp+98h+var_70], rax
0x180016217  lea     rax, ?g_wszCertificateChainOpenNode@@3QBGB; "<CERTIFICATECHAIN>"
0x18001621e  mov     [rsp+98h+var_78], rax
0x180016223  lea     r9, aXmlVersion10; "<?xml version=\"1.0\"?>"
0x18001622a  lea     r8, aSSSSSS; "%s%s%s%s%s%s"
0x180016231  mov     rdx, rbx; unsigned __int64
0x180016234  mov     rcx, rdi; unsigned __int16 *
0x180016237  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001623c  mov     ebx, eax
0x18001623e  test    eax, eax
0x180016240  js      short loc_180016261
0x180016242  mov     [r14+3A0h], rdi
0x180016249  xor     edi, edi
0x18001624b  jmp     short loc_180016261
0x18001624d  mov     ebx, [rsp+98h+arg_10]
0x180016254  mov     rdi, [rsp+98h+arg_18]
0x18001625c  mov     rsi, [rsp+98h+var_48]
0x180016261  mov     rcx, rdi; Block
0x180016264  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016269  mov     rcx, [rsp+98h+Block]; Block
0x180016271  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016276  nop
0x180016277  mov     rcx, rsi; lpCriticalSection
0x18001627a  call    cs:__imp_LeaveCriticalSection
0x180016280  mov     eax, ebx
0x180016282  add     rsp, 70h
0x180016286  pop     r15
0x180016288  pop     r14
0x18001628a  pop     rdi
0x18001628b  pop     rsi
0x18001628c  pop     rbx
0x18001628d  retn
0x18001628e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180016294  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180016299  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001629e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800162a3  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800162a8  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800162ad  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
