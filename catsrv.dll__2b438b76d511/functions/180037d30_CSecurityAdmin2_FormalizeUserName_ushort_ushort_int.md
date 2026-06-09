# CSecurityAdmin2::FormalizeUserName(ushort *,ushort * *,int)

- ea: `0x180037d30`
- end: `0x180037f6f`
- name: `?FormalizeUserName@CSecurityAdmin2@@UEAAJPEAGPEAPEAGH@Z`
- size: `575`
- prototype: `int(CSecurityAdmin2 *__hidden this, unsigned __int16 *, unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a01c`
- `0x18000b6a0`
- `0x18001a6c8`
- `0x180027418`
- `0x180037d30`
- `0x180038078`
- `0x18003821c`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180037e6b`
- `msvcrt!_wcsicmp` at `0x180037e84`
- `msvcrt!_wcsicmp` at `0x180037e6b`
- `msvcrt!_wcsicmp` at `0x180037e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037ee0`

## pseudocode

```c
int __fastcall CSecurityAdmin2::FormalizeUserName(CSecurityAdmin2 *this, unsigned __int16 *a2, LPVOID *a3, int a4)
{
  int result; // eax
  int v8; // eax
  CGetAccountDomain *v9; // rcx
  int v10; // r11d
  __int64 v11; // rdi
  unsigned __int16 v12; // si
  __int64 v13; // rax
  __int64 v14; // rcx
  SIZE_T v15; // rbx
  unsigned __int16 *v16; // rax
  int v17; // eax
  int v18; // ebx
  wchar_t *String2; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[280]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v21[280]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(String1, 0, 0x222u);
  memset_0(v21, 0, 0x222u);
  *a3 = 0;
  if ( (int)safe_lstrlenW(a2) >= 273 )
    return -2147024809;
  while ( 1 )
  {
    v8 = safe_lstrlenW(a2);
    if ( v10 >= v8 )
      break;
    v11 = v10;
    v12 = a2[v10];
    if ( v12 == 92 || v12 == 47 )
    {
      a2[v10] = 0;
      result = StringCchCopyW(String1, 0x111u, a2);
      if ( result < 0 )
        return result;
      a2[v11] = v12;
      result = StringCchCopyW(v21, 0x111u, &a2[v11 + 1]);
      if ( result < 0 )
        return result;
    }
  }
  if ( String1[0] || (result = StringCchCopyW(v21, 0x111u, a2), result >= 0) )
  {
    result = CGetAccountDomain::Init(v9);
    if ( result >= 0 )
    {
      String2 = 0;
      result = GetLocalizedBUILTIN(&String2);
      if ( result >= 0 )
      {
        if ( _wcsicmp(String1, L".") && (!a4 || _wcsicmp(String1, String2))
          || (result = StringCchCopyW(String1, 0x111u, qword_1800732E8), result >= 0) )
        {
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( String1[v14] );
          do
            ++v13;
          while ( v21[v13] );
          v15 = (unsigned int)(2 * (v14 + v13) + 4);
          v16 = (unsigned __int16 *)CoTaskMemAlloc(v15);
          *a3 = v16;
          if ( v16 )
          {
            if ( String1[0] )
              v17 = StringCbPrintfW(v16, v15, L"%s\\%s", String1, v21);
            else
              v17 = StringCbCopyW(v16, v15, v21);
            v18 = v17;
            if ( v17 < 0 )
            {
              CoTaskMemFree(*a3);
              *a3 = 0;
            }
            return v18;
          }
          else
          {
            return -2147024882;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037d30  mov     [rsp-8+arg_0], rbx
0x180037d35  push    rbp
0x180037d36  push    rsi
0x180037d37  push    rdi
0x180037d38  push    r12
0x180037d3a  push    r13
0x180037d3c  push    r14
0x180037d3e  push    r15
0x180037d40  lea     rbp, [rsp-3B0h]
0x180037d48  sub     rsp, 4B0h
0x180037d4f  mov     rax, cs:__security_cookie
0x180037d56  xor     rax, rsp
0x180037d59  mov     [rbp+3E0h+var_40], rax
0x180037d60  mov     r14, r8
0x180037d63  lea     rcx, [rsp+4E0h+String1]; void *
0x180037d68  mov     rbx, rdx
0x180037d6b  mov     edi, 222h
0x180037d70  mov     r8d, edi; Size
0x180037d73  xor     edx, edx; Val
0x180037d75  mov     r15d, r9d
0x180037d78  call    memset_0
0x180037d7d  mov     r8d, edi; Size
0x180037d80  lea     rcx, [rbp+3E0h+var_270]; void *
0x180037d87  xor     edx, edx; Val
0x180037d89  call    memset_0
0x180037d8e  xor     r12d, r12d
0x180037d91  mov     rcx, rbx; unsigned __int16 *
0x180037d94  mov     [r14], r12
0x180037d97  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180037d9c  mov     r13d, 111h
0x180037da2  cmp     eax, r13d
0x180037da5  jl      short loc_180037DB1
0x180037da7  mov     eax, 80070057h
0x180037dac  jmp     loc_180037F45
0x180037db1  mov     r11d, r12d
0x180037db4  mov     rcx, rbx; unsigned __int16 *
0x180037db7  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180037dbc  cmp     r11d, eax
0x180037dbf  jge     short loc_180037E19
0x180037dc1  movsxd  rdi, r11d
0x180037dc4  movzx   esi, word ptr [rbx+rdi*2]
0x180037dc8  cmp     si, 5Ch ; '\'
0x180037dcc  jz      short loc_180037DD4
0x180037dce  cmp     si, 2Fh ; '/'
0x180037dd2  jnz     short loc_180037E14
0x180037dd4  mov     r8, rbx; unsigned __int16 *
0x180037dd7  mov     [rbx+rdi*2], r12w
0x180037ddc  mov     rdx, r13; unsigned __int64
0x180037ddf  lea     rcx, [rsp+4E0h+String1]; unsigned __int16 *
0x180037de4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037de9  test    eax, eax
0x180037deb  js      loc_180037F45
0x180037df1  lea     r8, [rbx+2]
0x180037df5  mov     [rbx+rdi*2], si
0x180037df9  lea     r8, [r8+rdi*2]; unsigned __int16 *
0x180037dfd  mov     rdx, r13; unsigned __int64
0x180037e00  lea     rcx, [rbp+3E0h+var_270]; unsigned __int16 *
0x180037e07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037e0c  test    eax, eax
0x180037e0e  js      loc_180037F45
0x180037e14  inc     r11d
0x180037e17  jmp     short loc_180037DB4
0x180037e19  cmp     [rsp+4E0h+String1], r12w
0x180037e1f  jnz     short loc_180037E3B
0x180037e21  mov     r8, rbx; unsigned __int16 *
0x180037e24  lea     rcx, [rbp+3E0h+var_270]; unsigned __int16 *
0x180037e2b  mov     rdx, r13; unsigned __int64
0x180037e2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037e33  test    eax, eax
0x180037e35  js      loc_180037F45
0x180037e3b  call    ?Init@CGetAccountDomain@@QEAAJXZ; CGetAccountDomain::Init(void)
0x180037e40  test    eax, eax
0x180037e42  js      loc_180037F45
0x180037e48  lea     rcx, [rsp+4E0h+String2]; unsigned __int16 **
0x180037e4d  mov     [rsp+4E0h+String2], r12
0x180037e52  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x180037e57  test    eax, eax
0x180037e59  js      loc_180037F45
0x180037e5f  lea     rdx, asc_18005EA94; "."
0x180037e66  lea     rcx, [rsp+4E0h+String1]; String1
0x180037e6b  call    cs:__imp__wcsicmp
0x180037e71  test    eax, eax
0x180037e73  jz      short loc_180037E8E
0x180037e75  test    r15d, r15d
0x180037e78  jz      short loc_180037EAA
0x180037e7a  mov     rdx, [rsp+4E0h+String2]; String2
0x180037e7f  lea     rcx, [rsp+4E0h+String1]; String1
0x180037e84  call    cs:__imp__wcsicmp
0x180037e8a  test    eax, eax
0x180037e8c  jnz     short loc_180037EAA
0x180037e8e  mov     r8, cs:qword_1800732E8; unsigned __int16 *
0x180037e95  lea     rcx, [rsp+4E0h+String1]; unsigned __int16 *
0x180037e9a  mov     rdx, r13; unsigned __int64
0x180037e9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037ea2  test    eax, eax
0x180037ea4  js      loc_180037F45
0x180037eaa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037eae  lea     rdx, [rsp+4E0h+String1]
0x180037eb3  mov     rcx, rax
0x180037eb6  inc     rcx
0x180037eb9  cmp     [rdx+rcx*2], r12w
0x180037ebe  jnz     short loc_180037EB6
0x180037ec0  lea     rdx, [rbp+3E0h+var_270]
0x180037ec7  inc     rax
0x180037eca  cmp     [rdx+rax*2], r12w
0x180037ecf  jnz     short loc_180037EC7
0x180037ed1  add     rax, rcx
0x180037ed4  lea     rax, ds:4[rax*2]
0x180037edc  mov     ecx, eax; cb
0x180037ede  mov     ebx, eax
0x180037ee0  call    cs:__imp_CoTaskMemAlloc
0x180037ee6  mov     [r14], rax
0x180037ee9  test    rax, rax
0x180037eec  jnz     short loc_180037EF5
0x180037eee  mov     eax, 8007000Eh
0x180037ef3  jmp     short loc_180037F45
0x180037ef5  mov     rdx, rbx; unsigned __int64
0x180037ef8  cmp     [rsp+4E0h+String1], r12w
0x180037efe  jz      short loc_180037F22
0x180037f00  lea     rcx, [rbp+3E0h+var_270]
0x180037f07  mov     [rsp+4E0h+var_4C0], rcx
0x180037f0c  lea     r9, [rsp+4E0h+String1]
0x180037f11  mov     rcx, rax; unsigned __int16 *
0x180037f14  lea     r8, aSS; "%s\\%s"
0x180037f1b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037f20  jmp     short loc_180037F31
0x180037f22  lea     r8, [rbp+3E0h+var_270]; unsigned __int16 *
0x180037f29  mov     rcx, rax; unsigned __int16 *
0x180037f2c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180037f31  mov     ebx, eax
0x180037f33  test    eax, eax
0x180037f35  jns     short loc_180037F43
0x180037f37  mov     rcx, [r14]; pv
0x180037f3a  call    cs:__imp_CoTaskMemFree
0x180037f40  mov     [r14], r12
0x180037f43  mov     eax, ebx
0x180037f45  mov     rcx, [rbp+3E0h+var_40]
0x180037f4c  xor     rcx, rsp; StackCookie
0x180037f4f  call    __security_check_cookie
0x180037f54  mov     rbx, [rsp+4E0h+arg_0]
0x180037f5c  add     rsp, 4B0h
0x180037f63  pop     r15
0x180037f65  pop     r14
0x180037f67  pop     r13
0x180037f69  pop     r12
0x180037f6b  pop     rdi
0x180037f6c  pop     rsi
0x180037f6d  pop     rbp
0x180037f6e  retn
```
