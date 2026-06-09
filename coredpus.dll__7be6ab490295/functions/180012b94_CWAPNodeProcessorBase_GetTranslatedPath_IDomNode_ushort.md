# CWAPNodeProcessorBase::GetTranslatedPath(IDomNode *,ushort * *)

- ea: `0x180012b94`
- end: `0x180012d41`
- name: `?GetTranslatedPath@CWAPNodeProcessorBase@@IEAAJPEAUIDomNode@@PEAPEAG@Z`
- size: `429`
- prototype: `__int64 __fastcall(CWAPNodeProcessorBase *__hidden this, struct IDomNode *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180022ee0`
- `0x1800233b0`

## callees

- `0x180012b94`
- `0x180016428`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012c8f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012ce2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012c8f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012ce2`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c54`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c66`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c54`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d2d`

## string_xrefs

- `0x180012bff`: `V2CSPNodePath`
- `0x180012d1a`: `V2CSPNodePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWAPNodeProcessorBase::GetTranslatedPath(
        CWAPNodeProcessorBase *this,
        struct IDomNode *a2,
        unsigned __int16 **a3)
{
  BSTR pvData; // rdi
  signed int v5; // ebx
  __int64 v6; // rsi
  LSTATUS ValueW; // eax
  bool v8; // sf
  UINT v10; // esi
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+10h] BYREF

  v12 = HIDWORD(this);
  pvData = 0;
  pcbData = 0;
  lpSubKey = 0;
  v5 = (*(__int64 (__fastcall **)(struct IDomNode *, LPCWSTR *))(*(_QWORD *)a2 + 64LL))(a2, &lpSubKey);
  if ( v5 < 0 )
    goto LABEL_13;
  v6 = -1;
  do
    ++v6;
  while ( lpSubKey[v6] );
  ValueW = RegGetValueW(HKEY_CLASSES_ROOT, lpSubKey, L"V2CSPNodePath", 2u, 0, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW == 234 || !ValueW )
  {
    pvData = SysAllocStringLen(0, pcbData >> 1);
    if ( pvData )
    {
      ValueW = RegGetValueW(HKEY_CLASSES_ROOT, lpSubKey, L"V2CSPNodePath", 2u, 0, pvData, &pcbData);
      v5 = ValueW;
LABEL_8:
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
      v8 = v5 < 0;
      goto LABEL_11;
    }
LABEL_17:
    v5 = -2147024882;
    goto LABEL_13;
  }
  if ( ValueW != 1168 && ValueW != 2 )
    goto LABEL_8;
  v10 = v6 + 15;
  pvData = SysAllocStringLen(0, v10);
  if ( !pvData )
    goto LABEL_17;
  v5 = StringCchPrintfW(pvData, v10, L"%s%s%s", L"./Vendor/MSFT", L"/", lpSubKey);
  v8 = v5 < 0;
LABEL_11:
  if ( !v8 )
  {
    *a3 = pvData;
    pvData = 0;
  }
LABEL_13:
  SysFreeString(pvData);
  SysFreeString((BSTR)lpSubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012b94  mov     rax, rsp
0x180012b97  mov     [rax+18h], rbx
0x180012b9b  mov     [rax+20h], rbp
0x180012b9f  mov     [rax+8], rcx
0x180012ba3  push    rsi
0x180012ba4  push    rdi
0x180012ba5  push    r14
0x180012ba7  sub     rsp, 40h
0x180012bab  mov     r14, r8
0x180012bae  mov     rcx, rdx
0x180012bb1  xor     ebp, ebp
0x180012bb3  mov     edi, ebp
0x180012bb5  mov     [rax+8], ebp
0x180012bb8  mov     [rax+10h], rbp
0x180012bbc  mov     rax, [rdx]
0x180012bbf  lea     rdx, [rsp+58h+lpSubKey]
0x180012bc4  mov     rax, [rax+40h]
0x180012bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bcd  mov     ebx, eax
0x180012bcf  test    eax, eax
0x180012bd1  js      short loc_180012C51
0x180012bd3  mov     rdx, [rsp+58h+lpSubKey]; lpSubKey
0x180012bd8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012bdc  inc     rsi
0x180012bdf  cmp     [rdx+rsi*2], bp
0x180012be3  jnz     short loc_180012BDC
0x180012be5  lea     rax, [rsp+58h+arg_0]
0x180012bea  mov     [rsp+58h+pcbData], rax; pcbData
0x180012bef  mov     [rsp+58h+pvData], rbp; pvData
0x180012bf4  mov     [rsp+58h+pdwType], rbp; pdwType
0x180012bf9  mov     r9d, 2; dwFlags
0x180012bff  lea     r8, Value; "V2CSPNodePath"
0x180012c06  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180012c0d  call    cs:__imp_RegGetValueW
0x180012c14  nop     dword ptr [rax+rax+00h]
0x180012c19  mov     ebx, eax
0x180012c1b  cmp     eax, 0EAh
0x180012c20  jz      loc_180012CDA
0x180012c26  test    eax, eax
0x180012c28  jz      loc_180012CDA
0x180012c2e  cmp     eax, 490h
0x180012c33  jz      short loc_180012C88
0x180012c35  cmp     eax, 2
0x180012c38  jz      short loc_180012C88
0x180012c3a  test    eax, eax
0x180012c3c  jle     short loc_180012C47
0x180012c3e  movzx   ebx, ax
0x180012c41  or      ebx, 80070000h
0x180012c47  test    ebx, ebx
0x180012c49  js      short loc_180012C51
0x180012c4b  mov     [r14], rdi
0x180012c4e  mov     rdi, rbp
0x180012c51  mov     rcx, rdi; bstrString
0x180012c54  call    cs:__imp_SysFreeString
0x180012c5b  nop     dword ptr [rax+rax+00h]
0x180012c60  nop
0x180012c61  mov     rcx, [rsp+58h+lpSubKey]; bstrString
0x180012c66  call    cs:__imp_SysFreeString
0x180012c6d  nop     dword ptr [rax+rax+00h]
0x180012c72  mov     eax, ebx
0x180012c74  mov     rbx, [rsp+58h+arg_10]
0x180012c79  mov     rbp, [rsp+58h+arg_18]
0x180012c7e  add     rsp, 40h
0x180012c82  pop     r14
0x180012c84  pop     rdi
0x180012c85  pop     rsi
0x180012c86  retn
0x180012c88  add     esi, 0Fh
0x180012c8b  mov     edx, esi; ui
0x180012c8d  xor     ecx, ecx; strIn
0x180012c8f  call    cs:__imp_SysAllocStringLen
0x180012c96  nop     dword ptr [rax+rax+00h]
0x180012c9b  mov     rdi, rax
0x180012c9e  test    rax, rax
0x180012ca1  jz      short loc_180012CF6
0x180012ca3  mov     rax, [rsp+58h+lpSubKey]
0x180012ca8  mov     edx, esi; unsigned __int64
0x180012caa  mov     [rsp+58h+pvData], rax
0x180012caf  lea     rax, asc_180032DA8; "/"
0x180012cb6  mov     [rsp+58h+pdwType], rax
0x180012cbb  lea     r9, aVendorMsft; "./Vendor/MSFT"
0x180012cc2  lea     r8, aSSS; "%s%s%s"
0x180012cc9  mov     rcx, rdi; unsigned __int16 *
0x180012ccc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012cd1  mov     ebx, eax
0x180012cd3  test    eax, eax
0x180012cd5  jmp     loc_180012C49
0x180012cda  mov     edx, [rsp+58h+arg_0]
0x180012cde  shr     edx, 1; ui
0x180012ce0  xor     ecx, ecx; strIn
0x180012ce2  call    cs:__imp_SysAllocStringLen
0x180012ce9  nop     dword ptr [rax+rax+00h]
0x180012cee  mov     rdi, rax
0x180012cf1  test    rax, rax
0x180012cf4  jnz     short loc_180012D00
0x180012cf6  mov     ebx, 8007000Eh
0x180012cfb  jmp     loc_180012C51
0x180012d00  lea     rax, [rsp+58h+arg_0]
0x180012d05  mov     [rsp+58h+pcbData], rax; pcbData
0x180012d0a  mov     [rsp+58h+pvData], rdi; pvData
0x180012d0f  mov     [rsp+58h+pdwType], rbp; pdwType
0x180012d14  mov     r9d, 2; dwFlags
0x180012d1a  lea     r8, Value; "V2CSPNodePath"
0x180012d21  mov     rdx, [rsp+58h+lpSubKey]; lpSubKey
0x180012d26  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180012d2d  call    cs:__imp_RegGetValueW
0x180012d34  nop     dword ptr [rax+rax+00h]
0x180012d39  mov     ebx, eax
0x180012d3b  jmp     loc_180012C3A
```
