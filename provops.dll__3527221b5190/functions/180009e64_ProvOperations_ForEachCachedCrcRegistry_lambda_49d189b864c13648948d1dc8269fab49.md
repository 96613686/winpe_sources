# ProvOperations::ForEachCachedCrcRegistry__lambda_49d189b864c13648948d1dc8269fab49___

- ea: `0x180009e64`
- end: `0x18000a03c`
- name: `ProvOperations::ForEachCachedCrcRegistry__lambda_49d189b864c13648948d1dc8269fab49___`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011db0`

## callees

- `0x180002f44`
- `0x180003efc`
- `0x180003f6c`
- `0x180009e64`
- `0x18000a224`
- `0x18001b3a8`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180009fda`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180009fda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009faf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009edb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall ProvOperations::ForEachCachedCrcRegistry__lambda_49d189b864c13648948d1dc8269fab49___(__int64 a1)
{
  unsigned __int64 i; // rdi
  unsigned int v3; // eax
  HKEY v4; // rsi
  _QWORD *v5; // rax
  _BYTE *v6; // rdx
  int result; // eax
  _BYTE *v8; // rcx
  _BYTE *v9; // rdx
  _BYTE *v10; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v14; // [rsp+50h] [rbp-9h]
  _BYTE *v15; // [rsp+58h] [rbp-1h]
  _BYTE v16[24]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v17; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( dword_18004AF08 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
LABEL_17:
    Init_thread_header(&dword_18004AF08);
    if ( dword_18004AF08 == -1 )
    {
      qword_18004ADE0[0] = (__int64)gc_wszRegMultivariantStatus;
      qword_18004ADE8 = (__int64)gc_wszRegUicc;
      Init_thread_footer(&dword_18004AF08);
    }
  }
  for ( i = 0; i < 2; ++i )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_18004ADE0[i], 0, 0xF003Fu, &hKey);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x54D,
        (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
        (const char *)v3,
        phkResult);
    v4 = hKey;
    v17 = 0;
    v5 = operator new(0x20u);
    if ( !v5 )
    {
      std::_Xbad_alloc();
      goto LABEL_17;
    }
    *v5 = off_1800385B0;
    v5[1] = v16;
    v5[2] = a1;
    v17 = v5;
    v15 = v13;
    v14 = 0;
    if ( v5 == (_QWORD *)v16 )
      v6 = v13;
    else
      v6 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v5)(v5, v6);
    result = ForEachRegSubKey<std::function<bool (HKEY__ *,unsigned short const *)>>(v4, (__int64)v13);
    v8 = v17;
    if ( v17 )
    {
      v9 = v16;
      LOBYTE(v9) = v17 != v16;
      result = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v9);
      v8 = 0;
      v17 = 0;
    }
    if ( v8 )
    {
      v10 = v16;
      LOBYTE(v10) = v8 != v16;
      result = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v8 + 32LL))(v8, v10);
    }
    if ( hKey )
      result = RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180009e64  push    rbp
0x180009e66  push    rbx
0x180009e67  push    rsi
0x180009e68  push    rdi
0x180009e69  lea     rbp, [rsp-3Fh]
0x180009e6e  sub     rsp, 98h
0x180009e75  mov     rax, cs:__security_cookie
0x180009e7c  xor     rax, rsp
0x180009e7f  mov     [rbp+57h+var_30], rax
0x180009e83  mov     rbx, rcx
0x180009e86  mov     ecx, cs:_tls_index
0x180009e8c  mov     rax, gs:58h
0x180009e95  mov     edx, 4
0x180009e9a  mov     rax, [rax+rcx*8]
0x180009e9e  mov     eax, [rdx+rax]
0x180009ea1  cmp     cs:dword_18004AF08, eax
0x180009ea7  jg      loc_180009FE1
0x180009ead  xor     edi, edi
0x180009eaf  mov     [rbp+57h+hKey], 0
0x180009eb7  lea     rdx, qword_18004ADE0
0x180009ebe  lea     rax, [rbp+57h+hKey]
0x180009ec2  mov     qword ptr [rsp+0B0h+phkResult], rax; unsigned int
0x180009ec7  mov     r9d, 0F003Fh; samDesired
0x180009ecd  xor     r8d, r8d; ulOptions
0x180009ed0  mov     rdx, [rdx+rdi*8]; lpSubKey
0x180009ed4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009edb  call    cs:__imp_RegOpenKeyExW
0x180009ee1  mov     rcx, [rbp+5Fh]; this
0x180009ee5  test    eax, eax
0x180009ee7  jnz     loc_18000A027
0x180009eed  mov     rsi, [rbp+57h+hKey]
0x180009ef1  mov     [rbp+57h+var_38], 0
0x180009ef9  lea     ecx, [rax+20h]; Size
0x180009efc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f01  mov     rcx, rax
0x180009f04  test    rax, rax
0x180009f07  jz      loc_180009FDA
0x180009f0d  lea     rax, off_1800385B0
0x180009f14  mov     [rcx], rax
0x180009f17  lea     rax, [rbp+57h+var_50]
0x180009f1b  mov     [rcx+8], rax
0x180009f1f  mov     [rcx+10h], rbx
0x180009f23  mov     [rbp+57h+var_38], rcx
0x180009f27  lea     rax, [rbp+57h+var_78]
0x180009f2b  mov     [rbp+57h+var_58], rax
0x180009f2f  mov     [rbp+57h+var_60], 0
0x180009f37  lea     rax, [rbp+57h+var_50]
0x180009f3b  cmp     rcx, rax
0x180009f3e  mov     rax, [rcx]
0x180009f41  mov     rax, [rax]
0x180009f44  jnz     short loc_180009F4C
0x180009f46  lea     rdx, [rbp+57h+var_78]
0x180009f4a  jmp     short loc_180009F4E
0x180009f4c  xor     edx, edx
0x180009f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f53  nop
0x180009f54  mov     [rbp+57h+var_60], rax
0x180009f58  lea     rdx, [rbp+57h+var_78]
0x180009f5c  mov     rcx, rsi; hKey
0x180009f5f  call    ??$ForEachRegSubKey@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@@YAKQEAUHKEY__@@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@Z; ForEachRegSubKey<std::function<bool (HKEY__ *,ushort const *)>>(HKEY__ * const,std::function<bool (HKEY__ *,ushort const *)>)
0x180009f64  nop
0x180009f65  mov     rcx, [rbp+57h+var_38]
0x180009f69  test    rcx, rcx
0x180009f6c  jz      short loc_180009F8A
0x180009f6e  mov     rax, [rcx]
0x180009f71  lea     rdx, [rbp+57h+var_50]
0x180009f75  cmp     rcx, rdx
0x180009f78  setnz   dl
0x180009f7b  mov     rax, [rax+20h]
0x180009f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f84  xor     ecx, ecx
0x180009f86  mov     [rbp+57h+var_38], rcx
0x180009f8a  test    rcx, rcx
0x180009f8d  jz      short loc_180009FA6
0x180009f8f  mov     rax, [rcx]
0x180009f92  lea     rdx, [rbp+57h+var_50]
0x180009f96  cmp     rcx, rdx
0x180009f99  setnz   dl
0x180009f9c  mov     rax, [rax+20h]
0x180009fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa5  nop
0x180009fa6  mov     rcx, [rbp+57h+hKey]; hKey
0x180009faa  test    rcx, rcx
0x180009fad  jz      short loc_180009FB5
0x180009faf  call    cs:__imp_RegCloseKey
0x180009fb5  inc     rdi
0x180009fb8  cmp     rdi, 2
0x180009fbc  jb      loc_180009EAF
0x180009fc2  mov     rcx, [rbp+57h+var_30]
0x180009fc6  xor     rcx, rsp; StackCookie
0x180009fc9  call    __security_check_cookie
0x180009fce  add     rsp, 98h
0x180009fd5  pop     rdi
0x180009fd6  pop     rsi
0x180009fd7  pop     rbx
0x180009fd8  pop     rbp
0x180009fd9  retn
0x180009fda  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009fe0  nop
0x180009fe1  lea     rcx, dword_18004AF08
0x180009fe8  call    _Init_thread_header
0x180009fed  cmp     cs:dword_18004AF08, 0FFFFFFFFh
0x180009ff4  jnz     loc_180009EAD
0x180009ffa  mov     rax, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; ushort const * const gc_wszRegMultivariantStatus
0x18000a001  mov     cs:qword_18004ADE0, rax
0x18000a008  mov     rax, cs:?gc_wszRegUicc@@3PEBGEB; ushort const * const gc_wszRegUicc
0x18000a00f  mov     cs:qword_18004ADE8, rax
0x18000a016  lea     rcx, dword_18004AF08
0x18000a01d  call    _Init_thread_footer
0x18000a022  jmp     loc_180009EAD
0x18000a027  mov     r9d, eax; char *
0x18000a02a  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18000a031  mov     edx, 54Dh; void *
0x18000a036  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
