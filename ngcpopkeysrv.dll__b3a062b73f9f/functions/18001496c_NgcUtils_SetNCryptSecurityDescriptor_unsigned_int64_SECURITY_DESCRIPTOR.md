# NgcUtils::SetNCryptSecurityDescriptor(unsigned __int64,_SECURITY_DESCRIPTOR *)

- ea: `0x18001496c`
- end: `0x180014aaa`
- name: `?SetNCryptSecurityDescriptor@NgcUtils@@YAJ_KPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, PSECURITY_DESCRIPTOR AbsoluteSD, struct _SECURITY_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017f60`
- `0x1800187a0`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x18001368c`
- `0x18001496c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a92`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001499b`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180014a12`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001499b`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180014a12`
- `ncrypt!NCryptSetProperty` at `0x180014a63`
- `ncrypt!NCryptSetProperty` at `0x180014a63`

## string_xrefs

- `0x1800149b1`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800149e7`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014a21`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014a74`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014a4e`: `Security Descr`

## pseudocode

```c
int __fastcall NgcUtils::SetNCryptSecurityDescriptor(
        NCRYPT_HANDLE hObject,
        PSECURITY_DESCRIPTOR AbsoluteSD,
        struct _SECURITY_DESCRIPTOR *a3)
{
  NTSTATUS v5; // eax
  BYTE *v7; // rbx
  NTSTATUS v8; // eax
  int v9; // edi
  SECURITY_STATUS v10; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ULONG BufferLength; // [rsp+48h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSD; // [rsp+50h] [rbp+18h] BYREF

  if ( !AbsoluteSD )
    return 0;
  BufferLength = 0;
  v5 = RtlMakeSelfRelativeSD(AbsoluteSD, 0, &BufferLength);
  if ( v5 != -1073741789 && v5 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x129,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v5,
             dwFlags);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&SelfRelativeSD, BufferLength);
  v7 = (BYTE *)SelfRelativeSD;
  if ( !SelfRelativeSD )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    return -2147024882;
  }
  v8 = RtlMakeSelfRelativeSD(AbsoluteSD, SelfRelativeSD, &BufferLength);
  if ( v8 >= 0 )
  {
    v10 = NCryptSetProperty(hObject, L"Security Descr", v7, BufferLength, 4u);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v10,
        dwFlagsa);
      goto LABEL_9;
    }
    if ( v7 )
      LocalFree(v7);
    return 0;
  }
  v9 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x134,
         (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
         (const char *)(unsigned int)v8,
         dwFlags);
LABEL_9:
  if ( v7 )
    LocalFree(v7);
  return v9;
}

```

## disassembly

```asm
0x18001496c  mov     rax, rsp
0x18001496f  mov     [rax+8], rbx
0x180014973  mov     [rax+20h], rsi
0x180014977  push    rdi
0x180014978  sub     rsp, 30h
0x18001497c  mov     rdi, rdx
0x18001497f  mov     rsi, rcx
0x180014982  test    rdx, rdx
0x180014985  jz      loc_180014A98
0x18001498b  lea     r8, [rax+10h]; BufferLength
0x18001498f  mov     dword ptr [rax+10h], 0
0x180014996  xor     edx, edx; SelfRelativeSD
0x180014998  mov     rcx, rdi; AbsoluteSD
0x18001499b  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800149a1  cmp     eax, 0C0000023h
0x1800149a6  jz      short loc_1800149CA
0x1800149a8  test    eax, eax
0x1800149aa  jns     short loc_1800149CA
0x1800149ac  mov     rcx, [rsp+38h]; this
0x1800149b1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800149b8  mov     r9d, eax; char *
0x1800149bb  mov     edx, 129h; void *
0x1800149c0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800149c5  jmp     loc_180014A9A
0x1800149ca  mov     edx, [rsp+38h+BufferLength]
0x1800149ce  lea     rcx, [rsp+38h+SelfRelativeSD]
0x1800149d3  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800149d8  mov     rbx, [rsp+38h+SelfRelativeSD]
0x1800149dd  test    rbx, rbx
0x1800149e0  jnz     short loc_180014A07
0x1800149e2  mov     rcx, [rsp+38h]; this
0x1800149e7  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800149ee  mov     ebx, 8007000Eh
0x1800149f3  mov     edx, 12Dh; void *
0x1800149f8  mov     r9d, ebx; char *
0x1800149fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a00  mov     eax, ebx
0x180014a02  jmp     loc_180014A9A
0x180014a07  lea     r8, [rsp+38h+BufferLength]; BufferLength
0x180014a0c  mov     rdx, rbx; SelfRelativeSD
0x180014a0f  mov     rcx, rdi; AbsoluteSD
0x180014a12  call    cs:__imp_RtlMakeSelfRelativeSD
0x180014a18  test    eax, eax
0x180014a1a  jns     short loc_180014A49
0x180014a1c  mov     rcx, [rsp+38h]; this
0x180014a21  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014a28  mov     r9d, eax; char *
0x180014a2b  mov     edx, 134h; void *
0x180014a30  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180014a35  mov     edi, eax
0x180014a37  test    rbx, rbx
0x180014a3a  jz      short loc_180014A45
0x180014a3c  mov     rcx, rbx; hMem
0x180014a3f  call    cs:__imp_LocalFree
0x180014a45  mov     eax, edi
0x180014a47  jmp     short loc_180014A9A
0x180014a49  mov     r9d, [rsp+38h+BufferLength]; cbInput
0x180014a4e  lea     rdx, aSecurityDescr; "Security Descr"
0x180014a55  mov     r8, rbx; pbInput
0x180014a58  mov     [rsp+38h+dwFlags], 4; int
0x180014a60  mov     rcx, rsi; hObject
0x180014a63  call    cs:__imp_NCryptSetProperty
0x180014a69  mov     edi, eax
0x180014a6b  test    eax, eax
0x180014a6d  jns     short loc_180014A8A
0x180014a6f  mov     rcx, [rsp+38h]; this
0x180014a74  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014a7b  mov     r9d, eax; char *
0x180014a7e  mov     edx, 13Bh; void *
0x180014a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a88  jmp     short loc_180014A37
0x180014a8a  test    rbx, rbx
0x180014a8d  jz      short loc_180014A98
0x180014a8f  mov     rcx, rbx; hMem
0x180014a92  call    cs:__imp_LocalFree
0x180014a98  xor     eax, eax
0x180014a9a  mov     rbx, [rsp+38h+arg_0]
0x180014a9f  mov     rsi, [rsp+38h+arg_18]
0x180014aa4  add     rsp, 30h
0x180014aa8  pop     rdi
0x180014aa9  retn
```
