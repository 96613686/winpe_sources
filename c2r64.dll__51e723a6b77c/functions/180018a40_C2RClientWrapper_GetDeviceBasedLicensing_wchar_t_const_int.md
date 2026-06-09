# C2RClientWrapper::GetDeviceBasedLicensing(wchar_t const *,int *)

- ea: `0x180018a40`
- end: `0x180018ca1`
- name: `?GetDeviceBasedLicensing@C2RClientWrapper@@UEAAJPEB_WPEAH@Z`
- size: `609`
- prototype: `__int64 __fastcall(C2RClientWrapper *__hidden this, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017950`

## callees

- `0x180008f14`
- `0x18000aa64`
- `0x18000c0a4`
- `0x180018a40`
- `0x180018ca4`
- `0x180019034`
- `0x18003e690`
- `0x1800409e0`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018c5e`
- `KERNEL32!GetLastError` at `0x180018c5e`
- `KERNEL32!CompareStringEx` at `0x180018bf9`
- `KERNEL32!CompareStringEx` at `0x180018c54`
- `KERNEL32!CompareStringEx` at `0x180018bf9`
- `KERNEL32!CompareStringEx` at `0x180018c54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall C2RClientWrapper::GetDeviceBasedLicensing(C2RClientWrapper *this, const wchar_t *a2, int *a3)
{
  _QWORD *v5; // rax
  __int64 *RpcClient; // rax
  int v7; // esi
  unsigned __int64 v9; // rdi
  int cchCount2; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  DWORD LastError; // eax
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v18; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v20; // [rsp+70h] [rbp-90h]
  _QWORD v21[5]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22[2]; // [rsp+A0h] [rbp-60h] BYREF
  int pExceptionObject; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v24; // [rsp+B4h] [rbp-4Ch]
  DWORD v25; // [rsp+2B4h] [rbp+1B4h]
  __int16 v26; // [rsp+2B8h] [rbp+1B8h]
  __int16 v27; // [rsp+3B8h] [rbp+2B8h]
  int v28; // [rsp+438h] [rbp+338h]
  _QWORD v29[3]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int64 v30; // [rsp+458h] [rbp+358h]
  WCHAR String1[264]; // [rsp+460h] [rbp+360h] BYREF

  v17 = a2;
  OString::Format<wchar_t const *,wchar_t [21]>(v29, a2, &v17);
  memset(String1, 0, 0x208u);
  v5 = v29;
  if ( v30 > 7 )
    v5 = (_QWORD *)v29[0];
  LODWORD(v17) = 260;
  v19 = String1;
  v18 = v5;
  v16 = 2;
  v21[0] = this;
  v21[1] = &v16;
  v21[2] = &v18;
  v21[3] = &v19;
  v21[4] = &v17;
  v20 = v22;
  RpcClient = C2RClientWrapper::get_RpcClient((__int64)this, v22);
  v7 = sub_180018CA4(RpcClient, v21);
  if ( v7 >= 0 )
  {
    v9 = -1;
    if ( String1[0] )
    {
      do
        ++v9;
      while ( String1[v9] );
      cchCount2 = OcfxInt32FromSize_t(1u);
      v11 = OcfxInt32FromSize_t(v9);
      v12 = CompareStringEx(&LocaleName, 1u, String1, v11, L"1", cchCount2, 0, 0, 0);
      if ( !v12 )
      {
        v13 = OcfxInt32FromSize_t(1u);
        v14 = OcfxInt32FromSize_t(v9);
        v12 = CompareStringEx(L"en-US", 1u, String1, v14, L"1", v13, 0, 0, 0);
        if ( !v12 )
        {
          LastError = GetLastError();
          pExceptionObject = 15;
          v25 = LastError;
          v28 = 808464432;
          v27 = 0;
          v26 = 0;
          v24 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      LODWORD(v9) = v12 - 2;
    }
    *a3 = v9 == 0;
  }
  std::wstring::_Tidy_deallocate(v29);
  v20 = v29;
  v29[0] = 19937;
  v29[2] = 0;
  v30 = 15;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018a40  mov     [rsp-8+arg_18], rbx
0x180018a45  push    rbp
0x180018a46  push    rsi
0x180018a47  push    rdi
0x180018a48  push    r12
0x180018a4a  push    r13
0x180018a4c  push    r14
0x180018a4e  push    r15
0x180018a50  lea     rbp, [rsp-580h]
0x180018a58  sub     rsp, 680h
0x180018a5f  mov     rax, cs:__security_cookie
0x180018a66  xor     rax, rsp
0x180018a69  mov     [rbp+5B0h+var_40], rax
0x180018a70  mov     r14, r8
0x180018a73  mov     rbx, rcx
0x180018a76  mov     [rsp+6B0h+var_658], rdx
0x180018a7b  lea     r8, [rsp+6B0h+var_658]
0x180018a80  lea     rcx, [rbp+5B0h+var_270]
0x180018a87  call    ??$Format@PEB_W$$BY0BF@_W@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBQEB_WAEAY0BF@$$CB_W@Z; OString::Format<wchar_t const *,wchar_t [21]>(wchar_t const *,wchar_t const * const &,wchar_t const (&)[21])
0x180018a8c  nop
0x180018a8d  xor     edx, edx; Val
0x180018a8f  mov     r8d, 208h; Size
0x180018a95  lea     rcx, [rbp+5B0h+String1]; void *
0x180018a9c  call    memset
0x180018aa1  lea     rax, [rbp+5B0h+var_270]
0x180018aa8  cmp     [rbp+5B0h+var_258], 7
0x180018ab0  cmova   rax, [rbp+5B0h+var_270]
0x180018ab8  mov     dword ptr [rsp+6B0h+var_658], 104h
0x180018ac0  lea     rcx, [rbp+5B0h+String1]
0x180018ac7  mov     [rsp+6B0h+var_648], rcx
0x180018acc  mov     [rsp+6B0h+var_650], rax
0x180018ad1  mov     [rsp+6B0h+var_660], 2
0x180018ad9  mov     [rsp+6B0h+var_638], rbx
0x180018ade  lea     rax, [rsp+6B0h+var_660]
0x180018ae3  mov     [rbp+5B0h+var_630], rax
0x180018ae7  lea     rax, [rsp+6B0h+var_650]
0x180018aec  mov     [rbp+5B0h+var_628], rax
0x180018af0  lea     rax, [rsp+6B0h+var_648]
0x180018af5  mov     [rbp+5B0h+var_620], rax
0x180018af9  lea     rax, [rsp+6B0h+var_658]
0x180018afe  mov     [rbp+5B0h+var_618], rax
0x180018b02  lea     rax, [rbp+5B0h+var_610]
0x180018b06  mov     [rsp+6B0h+var_640], rax
0x180018b0b  lea     rdx, [rbp+5B0h+var_610]
0x180018b0f  mov     rcx, rbx
0x180018b12  call    ?get_RpcClient@C2RClientWrapper@@AEAA?AV?$shared_ptr@VORpcClient@@@std@@XZ; C2RClientWrapper::get_RpcClient(void)
0x180018b17  lea     rdx, [rsp+6B0h+var_638]
0x180018b1c  mov     rcx, rax
0x180018b1f  call    sub_180018CA4
0x180018b24  mov     esi, eax
0x180018b26  xor     r15d, r15d
0x180018b29  test    eax, eax
0x180018b2b  jns     short loc_180018B8F
0x180018b2d  lea     rcx, [rbp+5B0h+var_270]
0x180018b34  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018b39  nop
0x180018b3a  lea     rax, [rbp+5B0h+var_270]
0x180018b41  mov     [rsp+6B0h+var_640], rax
0x180018b46  mov     [rbp+5B0h+var_270], 4DE1h
0x180018b51  mov     [rbp+5B0h+var_260], r15
0x180018b58  mov     [rbp+5B0h+var_258], 0Fh
0x180018b63  mov     eax, esi
0x180018b65  mov     rcx, [rbp+5B0h+var_40]
0x180018b6c  xor     rcx, rsp; StackCookie
0x180018b6f  call    __security_check_cookie
0x180018b74  mov     rbx, [rsp+6B0h+arg_18]
0x180018b7c  add     rsp, 680h
0x180018b83  pop     r15
0x180018b85  pop     r14
0x180018b87  pop     r13
0x180018b89  pop     r12
0x180018b8b  pop     rdi
0x180018b8c  pop     rsi
0x180018b8d  pop     rbp
0x180018b8e  retn
0x180018b8f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018b93  cmp     r15w, [rbp+5B0h+String1]
0x180018b9b  jz      short loc_180018C06
0x180018b9d  lea     rax, [rbp+5B0h+String1]
0x180018ba4  inc     rdi
0x180018ba7  cmp     [rax+rdi*2], r15w
0x180018bac  jnz     short loc_180018BA4
0x180018bae  mov     r12d, 1
0x180018bb4  mov     ecx, r12d; unsigned __int64
0x180018bb7  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180018bbc  mov     ebx, eax
0x180018bbe  mov     rcx, rdi; unsigned __int64
0x180018bc1  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180018bc6  mov     [rsp+6B0h+lParam], r15; lParam
0x180018bcb  mov     [rsp+6B0h+lpReserved], r15; lpReserved
0x180018bd0  mov     [rsp+6B0h+lpVersionInformation], r15; lpVersionInformation
0x180018bd5  mov     [rsp+6B0h+cchCount2], ebx; cchCount2
0x180018bd9  lea     r13, a1; "1"
0x180018be0  mov     [rsp+6B0h+lpString2], r13; lpString2
0x180018be5  mov     r9d, eax; cchCount1
0x180018be8  lea     r8, [rbp+5B0h+String1]; lpString1
0x180018bef  mov     edx, r12d; dwCmpFlags
0x180018bf2  lea     rcx, LocaleName; lpLocaleName
0x180018bf9  call    cs:__imp_CompareStringEx
0x180018bff  test    eax, eax
0x180018c01  jz      short loc_180018C16
0x180018c03  lea     edi, [rax-2]
0x180018c06  mov     eax, r15d
0x180018c09  test    edi, edi
0x180018c0b  setz    al
0x180018c0e  mov     [r14], eax
0x180018c11  jmp     loc_180018B2D
0x180018c16  mov     rcx, r12; unsigned __int64
0x180018c19  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180018c1e  mov     ebx, eax
0x180018c20  mov     rcx, rdi; unsigned __int64
0x180018c23  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180018c28  mov     [rsp+6B0h+lParam], r15; lParam
0x180018c2d  mov     [rsp+6B0h+lpReserved], r15; lpReserved
0x180018c32  mov     [rsp+6B0h+lpVersionInformation], r15; lpVersionInformation
0x180018c37  mov     [rsp+6B0h+cchCount2], ebx; cchCount2
0x180018c3b  mov     [rsp+6B0h+lpString2], r13; lpString2
0x180018c40  mov     r9d, eax; cchCount1
0x180018c43  lea     r8, [rbp+5B0h+String1]; lpString1
0x180018c4a  mov     edx, r12d; dwCmpFlags
0x180018c4d  lea     rcx, aEnUs; "en-US"
0x180018c54  call    cs:__imp_CompareStringEx
0x180018c5a  test    eax, eax
0x180018c5c  jnz     short loc_180018C03
0x180018c5e  call    cs:__imp_GetLastError
0x180018c64  mov     [rbp+5B0h+pExceptionObject], 0Fh
0x180018c6b  mov     [rbp+5B0h+var_3FC], eax
0x180018c71  mov     [rbp+5B0h+var_278], 30303030h
0x180018c7b  mov     [rbp+5B0h+var_2F8], r15w
0x180018c83  mov     [rbp+5B0h+var_3F8], r15w
0x180018c8b  mov     [rbp+5B0h+var_5FC], r15w
0x180018c90  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180018c97  lea     rcx, [rbp+5B0h+pExceptionObject]; pExceptionObject
0x180018c9b  call    _CxxThrowException
```
