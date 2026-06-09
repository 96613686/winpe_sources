# PnpApiWrapper::Details::GetDeviceStringProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,HSTRING__ * &)

- ea: `0x18002e4cc`
- end: `0x18002e7b0`
- name: `?GetDeviceStringProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAPEAUHSTRING__@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(PnpApiWrapper::Details *__hidden this, unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *), void *, const struct _DEVPROPKEY *, HSTRING *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e300`
- `0x18002e38c`
- `0x180124ddc`

## callees

- `0x18002e4cc`
- `0x18002e7b8`
- `0x18008ead4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002e780`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002e780`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e5c9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e5c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002e796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002e551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002e749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002e551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002e749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002e613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002e613`

## pseudocode

```c
__int64 __fastcall PnpApiWrapper::Details::GetDeviceStringProperty(
        PnpApiWrapper::Details *this,
        unsigned int (*a2)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *),
        void *a3,
        HSTRING *a4)
{
  unsigned int v4; // eax
  unsigned int v5; // edx
  int v7; // eax
  unsigned int v8; // edi
  int v9; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v11; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING *string; // [rsp+B8h] [rbp+58h]

  string = a4;
  *a4 = 0;
  v11 = 0;
  v9 = 0;
  v4 = ((__int64 (__fastcall *)(unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *), void *, int *, _QWORD))this)(
         a2,
         a3,
         &v11,
         0);
  if ( !v4 || v4 == 26 )
    return 0;
  if ( v4 == 37 )
    return 1;
  v7 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)v4, v5);
  v8 = v7;
  if ( v7 == -2147023728 )
    return 2147943568LL;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AC,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpapiwrapper.cpp",
    (const char *)(unsigned int)v7,
    (int)&v9);
  return v8;
}

```

## disassembly

```asm
0x18002e4cc  mov     [rsp-38h+arg_8], rbx
0x18002e4d1  mov     [rsp-38h+string], r9
0x18002e4d6  push    rbp
0x18002e4d7  push    rsi
0x18002e4d8  push    rdi
0x18002e4d9  push    r12
0x18002e4db  push    r13
0x18002e4dd  push    r14
0x18002e4df  push    r15
0x18002e4e1  mov     rbp, rsp
0x18002e4e4  sub     rsp, 60h
0x18002e4e8  mov     r15, r8
0x18002e4eb  mov     r12, rdx
0x18002e4ee  mov     r13, rcx
0x18002e4f1  xor     esi, esi
0x18002e4f3  mov     [r9], rsi
0x18002e4f6  mov     [rbp+arg_0], esi
0x18002e4f9  mov     [rbp+var_30], esi
0x18002e4fc  lea     rax, [rbp+var_30]
0x18002e500  mov     qword ptr [rsp+60h+var_40], rax; int
0x18002e505  xor     r9d, r9d
0x18002e508  lea     r8, [rbp+arg_0]
0x18002e50c  mov     rdx, r15
0x18002e50f  mov     rcx, r12
0x18002e512  mov     rax, r13
0x18002e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51a  mov     ebx, 80070490h
0x18002e51f  test    eax, eax
0x18002e521  jz      short loc_18002E52C
0x18002e523  cmp     eax, 1Ah
0x18002e526  jnz     loc_18002E6B1
0x18002e52c  mov     edi, [rbp+var_30]
0x18002e52f  cmp     edi, 2
0x18002e532  jbe     loc_18002E61F
0x18002e538  shr     edi, 1
0x18002e53a  lea     r14d, [rdi-1]
0x18002e53e  mov     [rbp+charBuffer], rsi
0x18002e542  mov     [rbp+bufferHandle], rsi
0x18002e546  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18002e54a  lea     rdx, [rbp+charBuffer]; charBuffer
0x18002e54e  mov     ecx, r14d; length
0x18002e551  call    cs:__imp_WindowsPreallocateStringBuffer
0x18002e557  mov     esi, eax
0x18002e559  test    eax, eax
0x18002e55b  js      loc_18002E6C0
0x18002e561  lea     rax, [rbp+var_30]
0x18002e565  mov     qword ptr [rsp+60h+var_40], rax; int
0x18002e56a  mov     r9, [rbp+charBuffer]
0x18002e56e  lea     r8, [rbp+arg_0]
0x18002e572  mov     rdx, r15
0x18002e575  mov     rcx, r12
0x18002e578  mov     rax, r13
0x18002e57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e580  xor     esi, esi
0x18002e582  test    eax, eax
0x18002e584  jz      short loc_18002E5B3
0x18002e586  cmp     eax, 37h ; '7'
0x18002e589  jnz     loc_18002E656
0x18002e58f  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002e593  call    cs:__imp_WindowsDeleteStringBuffer
0x18002e599  mov     eax, ebx
0x18002e59b  mov     rbx, [rsp+60h+arg_8]
0x18002e5a3  add     rsp, 60h
0x18002e5a7  pop     r15
0x18002e5a9  pop     r14
0x18002e5ab  pop     r13
0x18002e5ad  pop     r12
0x18002e5af  pop     rdi
0x18002e5b0  pop     rsi
0x18002e5b1  pop     rbp
0x18002e5b2  retn
0x18002e5b3  test    rdi, rdi
0x18002e5b6  jz      loc_18002E68D
0x18002e5bc  mov     rcx, [rbp+charBuffer]; Source
0x18002e5c0  cmp     [rbp+arg_0], 12h
0x18002e5c4  jnz     short loc_18002E626
0x18002e5c6  mov     rdx, rdi; MaxCount
0x18002e5c9  call    cs:__imp_wcsnlen
0x18002e5cf  mov     rbx, rax
0x18002e5d2  cmp     rbx, rdi
0x18002e5d5  jb      short loc_18002E5F6
0x18002e5d7  mov     ebx, 8000FFFFh
0x18002e5dc  mov     r9d, ebx; char *
0x18002e5df  mov     edx, 1D5h; void *
0x18002e5e4  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e5eb  mov     rcx, [rbp+38h]; this
0x18002e5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e5f4  jmp     short loc_18002E58F
0x18002e5f6  test    rbx, rbx
0x18002e5f9  jz      loc_18002E6A2
0x18002e5ff  mov     eax, r14d
0x18002e602  cmp     rbx, rax
0x18002e605  jnz     loc_18002E737
0x18002e60b  mov     rdx, [rbp+string]; string
0x18002e60f  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002e613  call    cs:__imp_WindowsPromoteStringBuffer
0x18002e619  mov     ebx, eax
0x18002e61b  test    eax, eax
0x18002e61d  js      short loc_18002E695
0x18002e61f  xor     eax, eax
0x18002e621  jmp     loc_18002E59B
0x18002e626  cmp     [rbp+arg_0], 2012h
0x18002e62d  jnz     short loc_18002E68D
0x18002e62f  cmp     [rcx], si
0x18002e632  jz      short loc_18002E68D
0x18002e634  mov     ebx, 1
0x18002e639  cmp     rbx, rdi
0x18002e63c  jnb     short loc_18002E5D7
0x18002e63e  movzx   eax, word ptr [rcx]
0x18002e641  add     rcx, 2
0x18002e645  test    ax, ax
0x18002e648  jz      short loc_18002E64F
0x18002e64a  inc     rbx
0x18002e64d  jmp     short loc_18002E639
0x18002e64f  cmp     [rcx], si
0x18002e652  jnz     short loc_18002E64A
0x18002e654  jmp     short loc_18002E5F6
0x18002e656  cmp     eax, 25h ; '%'
0x18002e659  jz      loc_18002E58F
0x18002e65f  cmp     eax, 2
0x18002e662  jz      loc_18002E725
0x18002e668  cmp     eax, 0Dh
0x18002e66b  jz      loc_18002E58F
0x18002e671  cmp     eax, 13h
0x18002e674  jz      loc_18002E71E
0x18002e67a  cmp     eax, 33h ; '3'
0x18002e67d  jz      loc_18002E717
0x18002e683  mov     ebx, 8000FFFFh
0x18002e688  jmp     loc_18002E72A
0x18002e68d  mov     rbx, rsi
0x18002e690  jmp     loc_18002E5D2
0x18002e695  mov     edx, 1EEh
0x18002e69a  mov     r9d, eax
0x18002e69d  jmp     loc_18002E5E4
0x18002e6a2  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002e6a6  call    cs:__imp_WindowsDeleteStringBuffer
0x18002e6ac  jmp     loc_18002E61F
0x18002e6b1  cmp     eax, 25h ; '%'
0x18002e6b4  jnz     short loc_18002E6DF
0x18002e6b6  mov     eax, 1
0x18002e6bb  jmp     loc_18002E59B
0x18002e6c0  mov     rcx, [rbp+38h]; this
0x18002e6c4  mov     r9d, esi; char *
0x18002e6c7  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e6ce  mov     edx, 1C5h; void *
0x18002e6d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6d8  mov     eax, esi
0x18002e6da  jmp     loc_18002E59B
0x18002e6df  mov     ecx, eax; this
0x18002e6e1  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x18002e6e6  mov     edi, eax
0x18002e6e8  cmp     eax, ebx
0x18002e6ea  jz      loc_18002E599
0x18002e6f0  test    eax, eax
0x18002e6f2  jns     loc_18002E52C
0x18002e6f8  mov     rcx, [rbp+38h]; this
0x18002e6fc  mov     r9d, eax; char *
0x18002e6ff  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e706  mov     edx, 1ACh; void *
0x18002e70b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e710  mov     eax, edi
0x18002e712  jmp     loc_18002E59B
0x18002e717  mov     ebx, 80070005h
0x18002e71c  jmp     short loc_18002E72A
0x18002e71e  mov     ebx, 80004005h
0x18002e723  jmp     short loc_18002E72A
0x18002e725  mov     ebx, 8007000Eh
0x18002e72a  mov     r9d, ebx
0x18002e72d  mov     edx, 1D1h
0x18002e732  jmp     loc_18002E5E4
0x18002e737  mov     [rbp+var_10], rsi
0x18002e73b  mov     [rbp+var_18], rsi
0x18002e73f  mov     ecx, ebx; length
0x18002e741  lea     r8, [rbp+var_18]; bufferHandle
0x18002e745  lea     rdx, [rbp+var_10]; charBuffer
0x18002e749  call    cs:__imp_WindowsPreallocateStringBuffer
0x18002e74f  mov     edi, eax
0x18002e751  test    eax, eax
0x18002e753  jns     short loc_18002E774
0x18002e755  mov     rcx, [rbp+38h]; this
0x18002e759  mov     r9d, eax; char *
0x18002e75c  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e763  mov     edx, 1E5h; void *
0x18002e768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e76d  mov     ebx, edi
0x18002e76f  jmp     loc_18002E58F
0x18002e774  lea     rdx, [rbx+1]
0x18002e778  mov     r8, [rbp+charBuffer]
0x18002e77c  mov     rcx, [rbp+var_10]
0x18002e780  call    cs:__imp__o_wcscpy_s
0x18002e786  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002e78a  mov     rax, [rbp+var_18]
0x18002e78e  mov     [rbp+bufferHandle], rax
0x18002e792  mov     [rbp+var_18], rcx
0x18002e796  call    cs:__imp_WindowsDeleteStringBuffer
0x18002e79c  mov     ebx, eax
0x18002e79e  test    eax, eax
0x18002e7a0  jns     loc_18002E60B
0x18002e7a6  mov     edx, 1EAh
0x18002e7ab  jmp     loc_18002E69A
```
