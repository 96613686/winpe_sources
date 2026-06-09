# util_CheckPackageSignature(IServiceProvider *,PlainBase const &,unsigned __int64,_GUID const &,ulong,ushort *,unsigned __int64)

- ea: `0x140038d60`
- end: `0x140038f5f`
- name: `?util_CheckPackageSignature@@YA?AW4CheckPackageSignatureResult@@PEAUIServiceProvider@@AEBVPlainBase@@_KAEBU_GUID@@KPEAG2@Z`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400404ec`

## callees

- `0x140001020`
- `0x140001040`
- `0x14000b5f0`
- `0x140038d60`
- `0x140038f60`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140038dab`
- `KERNEL32!LoadLibraryExW` at `0x140038dab`
- `KERNEL32!FreeLibrary` at `0x140038dd9`
- `KERNEL32!FreeLibrary` at `0x140038dd9`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x140038ea8`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x140038ea8`
- `OLEAUT32!__imp_SysFreeString` at `0x140038dfe`
- `OLEAUT32!__imp_SysFreeString` at `0x140038f34`
- `OLEAUT32!__imp_SysFreeString` at `0x140038dfe`
- `OLEAUT32!__imp_SysFreeString` at `0x140038f34`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall util_CheckPackageSignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int Value,
        const WCHAR *lpLibFileName,
        __int64 a7)
{
  HMODULE Library; // rax
  HMODULE v12; // rdi
  __int64 v14; // rcx
  unsigned int v15; // ebx
  BSTR bstrString; // [rsp+30h] [rbp-71h] BYREF
  __int64 v17; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-61h] BYREF
  __int64 v19; // [rsp+48h] [rbp-59h] BYREF
  wchar_t Buffer[40]; // [rsp+50h] [rbp-51h] BYREF

  if ( a3 && lpLibFileName )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 2u);
    v12 = Library;
    if ( !Library )
      return 2;
    bstrString = 0;
    ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, Library, Value);
    FreeLibrary(v12);
    if ( (unsigned int)util_VerifyPackageSignature(a2, a3, bstrString, a7) )
    {
      SysFreeString(bstrString);
      bstrString = 0;
      v14 = 0;
      v17 = 0;
      if ( !a1 )
      {
        v15 = 3;
        goto LABEL_22;
      }
      if ( (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)a1 + 24LL))(
             a1,
             &IID_SVsResourceManager,
             &GUID_f0d7a6f0_c722_4ab6_a5d9_c7ff13027410,
             &v17) >= 0
        && v17 )
      {
        _mm_lfence();
        memset_0(Buffer, 0, 0x42u);
        v18 = 0;
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)a1 + 24LL))(
               a1,
               &IID_IUIHostLocale,
               &GUID_2c2ea031_02be_11d1_8c85_00c04fc2aa89,
               &v19) >= 0
          && v19 )
        {
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v18);
        }
        _ultow_s(Value, Buffer, 0x21u, 10);
        if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, wchar_t *, BSTR *))(*(_QWORD *)v17 + 24LL))(
               v17,
               a4,
               v18,
               Buffer,
               &bstrString) < 0 )
        {
          if ( v19 )
            (*(void (**)(void))(*(_QWORD *)v19 + 16LL))();
          v15 = 4;
          goto LABEL_21;
        }
        if ( v19 )
          (*(void (**)(void))(*(_QWORD *)v19 + 16LL))();
      }
      if ( (unsigned int)util_VerifyPackageSignature(a2, a3, bstrString, a7) )
      {
        v15 = 5;
LABEL_21:
        v14 = v17;
LABEL_22:
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        goto LABEL_27;
      }
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v15 = 0;
LABEL_27:
    SysFreeString(bstrString);
    return v15;
  }
  return 1;
}

```

## disassembly

```asm
0x140038d60  push    rbp
0x140038d62  push    rbx
0x140038d63  push    rsi
0x140038d64  push    rdi
0x140038d65  push    r14
0x140038d67  push    r15
0x140038d69  lea     rbp, [rsp-17h]
0x140038d6e  sub     rsp, 0B8h
0x140038d75  mov     rax, cs:__security_cookie
0x140038d7c  xor     rax, rsp
0x140038d7f  mov     [rbp+3Fh+var_40], rax
0x140038d83  mov     r15, r9
0x140038d86  mov     rsi, r8
0x140038d89  mov     r14, rdx
0x140038d8c  mov     rbx, rcx
0x140038d8f  mov     rcx, [rbp+3Fh+lpLibFileName]; lpLibFileName
0x140038d93  test    r8, r8
0x140038d96  jz      loc_140038F3E
0x140038d9c  test    rcx, rcx
0x140038d9f  jz      loc_140038F3E
0x140038da5  xor     edx, edx; hFile
0x140038da7  lea     r8d, [rdx+2]; dwFlags
0x140038dab  call    cs:__imp_LoadLibraryExW
0x140038db1  mov     rdi, rax
0x140038db4  test    rax, rax
0x140038db7  jnz     short loc_140038DC1
0x140038db9  lea     eax, [rdi+2]
0x140038dbc  jmp     loc_140038F43
0x140038dc1  and     [rbp+3Fh+bstrString], 0
0x140038dc6  mov     r8d, [rbp+3Fh+Value]; unsigned int
0x140038dca  mov     rdx, rdi; HINSTANCE
0x140038dcd  lea     rcx, [rbp+3Fh+bstrString]; this
0x140038dd1  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x140038dd6  mov     rcx, rdi; hLibModule
0x140038dd9  call    cs:__imp_FreeLibrary
0x140038ddf  mov     r9, [rbp+3Fh+arg_30]
0x140038de3  mov     r8, [rbp+3Fh+bstrString]
0x140038de7  mov     rdx, rsi
0x140038dea  mov     rcx, r14
0x140038ded  call    ?util_VerifyPackageSignature@@YA?AW4VerifyPackageSignatureResult@@AEBVPlainBase@@_KPEBG1@Z; util_VerifyPackageSignature(PlainBase const &,unsigned __int64,ushort const *,unsigned __int64)
0x140038df2  test    eax, eax
0x140038df4  jz      loc_140038F2E
0x140038dfa  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x140038dfe  call    cs:__imp_SysFreeString
0x140038e04  and     [rbp+3Fh+bstrString], 0
0x140038e09  xor     ecx, ecx
0x140038e0b  mov     [rbp+3Fh+var_A8], rcx
0x140038e0f  test    rbx, rbx
0x140038e12  jnz     short loc_140038E1C
0x140038e14  lea     ebx, [rcx+3]
0x140038e17  jmp     loc_140038F12
0x140038e1c  mov     rax, [rbx]
0x140038e1f  lea     r9, [rbp+3Fh+var_A8]
0x140038e23  lea     r8, _GUID_f0d7a6f0_c722_4ab6_a5d9_c7ff13027410
0x140038e2a  lea     rdx, IID_SVsResourceManager
0x140038e31  mov     rcx, rbx
0x140038e34  call    qword ptr [rax+18h]
0x140038e37  test    eax, eax
0x140038e39  js      loc_140038EF2
0x140038e3f  cmp     [rbp+3Fh+var_A8], 0
0x140038e44  jz      loc_140038EF2
0x140038e4a  lfence
0x140038e4d  xor     edx, edx; Val
0x140038e4f  lea     r8d, [rdx+42h]; Size
0x140038e53  lea     rcx, [rbp+3Fh+Buffer]; void *
0x140038e57  call    memset_0
0x140038e5c  and     [rbp+3Fh+var_A0], 0
0x140038e60  and     [rbp+3Fh+var_98], 0
0x140038e65  mov     rax, [rbx]
0x140038e68  lea     r9, [rbp+3Fh+var_98]
0x140038e6c  lea     r8, _GUID_2c2ea031_02be_11d1_8c85_00c04fc2aa89
0x140038e73  lea     rdx, IID_IUIHostLocale
0x140038e7a  mov     rcx, rbx
0x140038e7d  call    qword ptr [rax+18h]
0x140038e80  test    eax, eax
0x140038e82  js      short loc_140038E97
0x140038e84  mov     rcx, [rbp+3Fh+var_98]
0x140038e88  test    rcx, rcx
0x140038e8b  jz      short loc_140038E97
0x140038e8d  mov     rax, [rcx]
0x140038e90  lea     rdx, [rbp+3Fh+var_A0]
0x140038e94  call    qword ptr [rax+18h]
0x140038e97  mov     r9d, 0Ah; Radix
0x140038e9d  lea     r8d, [r9+17h]; BufferCount
0x140038ea1  lea     rdx, [rbp+3Fh+Buffer]; Buffer
0x140038ea5  mov     ecx, [rbp+3Fh+Value]; Value
0x140038ea8  call    cs:__imp__ultow_s
0x140038eae  mov     rcx, [rbp+3Fh+var_A8]
0x140038eb2  mov     rax, [rcx]
0x140038eb5  lea     rdx, [rbp+3Fh+bstrString]
0x140038eb9  mov     [rsp+0E0h+var_C0], rdx
0x140038ebe  lea     r9, [rbp+3Fh+Buffer]
0x140038ec2  mov     r8d, [rbp+3Fh+var_A0]
0x140038ec6  mov     rdx, r15
0x140038ec9  call    qword ptr [rax+18h]
0x140038ecc  nop
0x140038ecd  mov     rcx, [rbp+3Fh+var_98]
0x140038ed1  test    eax, eax
0x140038ed3  jns     short loc_140038EE7
0x140038ed5  test    rcx, rcx
0x140038ed8  jz      short loc_140038EE0
0x140038eda  mov     rax, [rcx]
0x140038edd  call    qword ptr [rax+10h]
0x140038ee0  mov     ebx, 4
0x140038ee5  jmp     short loc_140038F0E
0x140038ee7  test    rcx, rcx
0x140038eea  jz      short loc_140038EF2
0x140038eec  mov     rax, [rcx]
0x140038eef  call    qword ptr [rax+10h]
0x140038ef2  mov     r9, [rbp+3Fh+arg_30]
0x140038ef6  mov     r8, [rbp+3Fh+bstrString]
0x140038efa  mov     rdx, rsi
0x140038efd  mov     rcx, r14
0x140038f00  call    ?util_VerifyPackageSignature@@YA?AW4VerifyPackageSignatureResult@@AEBVPlainBase@@_KPEBG1@Z; util_VerifyPackageSignature(PlainBase const &,unsigned __int64,ushort const *,unsigned __int64)
0x140038f05  test    eax, eax
0x140038f07  jz      short loc_140038F1F
0x140038f09  mov     ebx, 5
0x140038f0e  mov     rcx, [rbp+3Fh+var_A8]
0x140038f12  test    rcx, rcx
0x140038f15  jz      short loc_140038F30
0x140038f17  mov     rax, [rcx]
0x140038f1a  call    qword ptr [rax+10h]
0x140038f1d  jmp     short loc_140038F30
0x140038f1f  mov     rcx, [rbp+3Fh+var_A8]
0x140038f23  test    rcx, rcx
0x140038f26  jz      short loc_140038F2E
0x140038f28  mov     rax, [rcx]
0x140038f2b  call    qword ptr [rax+10h]
0x140038f2e  xor     ebx, ebx
0x140038f30  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x140038f34  call    cs:__imp_SysFreeString
0x140038f3a  mov     eax, ebx
0x140038f3c  jmp     short loc_140038F43
0x140038f3e  mov     eax, 1
0x140038f43  mov     rcx, [rbp+3Fh+var_40]
0x140038f47  xor     rcx, rsp; StackCookie
0x140038f4a  call    __security_check_cookie
0x140038f4f  add     rsp, 0B8h
0x140038f56  pop     r15
0x140038f58  pop     r14
0x140038f5a  pop     rdi
0x140038f5b  pop     rsi
0x140038f5c  pop     rbx
0x140038f5d  pop     rbp
0x140038f5e  retn
```
