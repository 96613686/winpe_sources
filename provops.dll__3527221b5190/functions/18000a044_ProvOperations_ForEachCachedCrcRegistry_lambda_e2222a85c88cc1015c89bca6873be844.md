# ProvOperations::ForEachCachedCrcRegistry__lambda_e2222a85c88cc1015c89bca6873be844___

- ea: `0x18000a044`
- end: `0x18000a21c`
- name: `ProvOperations::ForEachCachedCrcRegistry__lambda_e2222a85c88cc1015c89bca6873be844___`
- size: `472`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016d64`

## callees

- `0x180002f44`
- `0x180003efc`
- `0x180003f6c`
- `0x18000a044`
- `0x18000a224`
- `0x18001b3a8`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a1ba`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a1ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a18f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a18f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0bb`

## pseudocode

```c
int __fastcall ProvOperations::ForEachCachedCrcRegistry__lambda_e2222a85c88cc1015c89bca6873be844___(__int64 a1)
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

  if ( dword_18004AEF8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
LABEL_17:
    Init_thread_header(&dword_18004AEF8);
    if ( dword_18004AEF8 == -1 )
    {
      qword_18004AE10[0] = (__int64)gc_wszRegMultivariantStatus;
      qword_18004AE18 = (__int64)gc_wszRegUicc;
      Init_thread_footer(&dword_18004AEF8);
    }
  }
  for ( i = 0; i < 2; ++i )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_18004AE10[i], 0, 0xF003Fu, &hKey);
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
    *v5 = off_1800384D8;
    v5[1] = a1;
    v5[2] = v16;
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
0x18000a044  push    rbp
0x18000a046  push    rbx
0x18000a047  push    rsi
0x18000a048  push    rdi
0x18000a049  lea     rbp, [rsp-3Fh]
0x18000a04e  sub     rsp, 98h
0x18000a055  mov     rax, cs:__security_cookie
0x18000a05c  xor     rax, rsp
0x18000a05f  mov     [rbp+57h+var_30], rax
0x18000a063  mov     rbx, rcx
0x18000a066  mov     ecx, cs:_tls_index
0x18000a06c  mov     rax, gs:58h
0x18000a075  mov     edx, 4
0x18000a07a  mov     rax, [rax+rcx*8]
0x18000a07e  mov     eax, [rdx+rax]
0x18000a081  cmp     cs:dword_18004AEF8, eax
0x18000a087  jg      loc_18000A1C1
0x18000a08d  xor     edi, edi
0x18000a08f  mov     [rbp+57h+hKey], 0
0x18000a097  lea     rdx, qword_18004AE10
0x18000a09e  lea     rax, [rbp+57h+hKey]
0x18000a0a2  mov     qword ptr [rsp+0B0h+phkResult], rax; unsigned int
0x18000a0a7  mov     r9d, 0F003Fh; samDesired
0x18000a0ad  xor     r8d, r8d; ulOptions
0x18000a0b0  mov     rdx, [rdx+rdi*8]; lpSubKey
0x18000a0b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a0bb  call    cs:__imp_RegOpenKeyExW
0x18000a0c1  mov     rcx, [rbp+5Fh]; this
0x18000a0c5  test    eax, eax
0x18000a0c7  jnz     loc_18000A207
0x18000a0cd  mov     rsi, [rbp+57h+hKey]
0x18000a0d1  mov     [rbp+57h+var_38], 0
0x18000a0d9  lea     ecx, [rax+20h]; Size
0x18000a0dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0e1  mov     rcx, rax
0x18000a0e4  test    rax, rax
0x18000a0e7  jz      loc_18000A1BA
0x18000a0ed  lea     rax, off_1800384D8
0x18000a0f4  mov     [rcx], rax
0x18000a0f7  mov     [rcx+8], rbx
0x18000a0fb  lea     rax, [rbp+57h+var_50]
0x18000a0ff  mov     [rcx+10h], rax
0x18000a103  mov     [rbp+57h+var_38], rcx
0x18000a107  lea     rax, [rbp+57h+var_78]
0x18000a10b  mov     [rbp+57h+var_58], rax
0x18000a10f  mov     [rbp+57h+var_60], 0
0x18000a117  lea     rax, [rbp+57h+var_50]
0x18000a11b  cmp     rcx, rax
0x18000a11e  mov     rax, [rcx]
0x18000a121  mov     rax, [rax]
0x18000a124  jnz     short loc_18000A12C
0x18000a126  lea     rdx, [rbp+57h+var_78]
0x18000a12a  jmp     short loc_18000A12E
0x18000a12c  xor     edx, edx
0x18000a12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a133  nop
0x18000a134  mov     [rbp+57h+var_60], rax
0x18000a138  lea     rdx, [rbp+57h+var_78]
0x18000a13c  mov     rcx, rsi; hKey
0x18000a13f  call    ??$ForEachRegSubKey@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@@YAKQEAUHKEY__@@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@Z; ForEachRegSubKey<std::function<bool (HKEY__ *,ushort const *)>>(HKEY__ * const,std::function<bool (HKEY__ *,ushort const *)>)
0x18000a144  nop
0x18000a145  mov     rcx, [rbp+57h+var_38]
0x18000a149  test    rcx, rcx
0x18000a14c  jz      short loc_18000A16A
0x18000a14e  mov     rax, [rcx]
0x18000a151  lea     rdx, [rbp+57h+var_50]
0x18000a155  cmp     rcx, rdx
0x18000a158  setnz   dl
0x18000a15b  mov     rax, [rax+20h]
0x18000a15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a164  xor     ecx, ecx
0x18000a166  mov     [rbp+57h+var_38], rcx
0x18000a16a  test    rcx, rcx
0x18000a16d  jz      short loc_18000A186
0x18000a16f  mov     rax, [rcx]
0x18000a172  lea     rdx, [rbp+57h+var_50]
0x18000a176  cmp     rcx, rdx
0x18000a179  setnz   dl
0x18000a17c  mov     rax, [rax+20h]
0x18000a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a185  nop
0x18000a186  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a18a  test    rcx, rcx
0x18000a18d  jz      short loc_18000A195
0x18000a18f  call    cs:__imp_RegCloseKey
0x18000a195  inc     rdi
0x18000a198  cmp     rdi, 2
0x18000a19c  jb      loc_18000A08F
0x18000a1a2  mov     rcx, [rbp+57h+var_30]
0x18000a1a6  xor     rcx, rsp; StackCookie
0x18000a1a9  call    __security_check_cookie
0x18000a1ae  add     rsp, 98h
0x18000a1b5  pop     rdi
0x18000a1b6  pop     rsi
0x18000a1b7  pop     rbx
0x18000a1b8  pop     rbp
0x18000a1b9  retn
0x18000a1ba  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a1c0  nop
0x18000a1c1  lea     rcx, dword_18004AEF8
0x18000a1c8  call    _Init_thread_header
0x18000a1cd  cmp     cs:dword_18004AEF8, 0FFFFFFFFh
0x18000a1d4  jnz     loc_18000A08D
0x18000a1da  mov     rax, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; ushort const * const gc_wszRegMultivariantStatus
0x18000a1e1  mov     cs:qword_18004AE10, rax
0x18000a1e8  mov     rax, cs:?gc_wszRegUicc@@3PEBGEB; ushort const * const gc_wszRegUicc
0x18000a1ef  mov     cs:qword_18004AE18, rax
0x18000a1f6  lea     rcx, dword_18004AEF8
0x18000a1fd  call    _Init_thread_footer
0x18000a202  jmp     loc_18000A08D
0x18000a207  mov     r9d, eax; char *
0x18000a20a  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x18000a211  mov     edx, 54Dh; void *
0x18000a216  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
