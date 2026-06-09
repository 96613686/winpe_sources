# CIsoBurn::_GetDiscRecorderForVolume(ushort const *,IDiscRecorder2 * *)

- ea: `0x140009a48`
- end: `0x140009c40`
- name: `?_GetDiscRecorderForVolume@CIsoBurn@@CAJPEBGPEAPEAUIDiscRecorder2@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct IDiscRecorder2 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004ca0`
- `0x140009e64`

## callees

- `0x140009a48`
- `0x140010010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140009b87`
- `KERNEL32!CompareStringOrdinal` at `0x140009b87`
- `OLEAUT32!__imp_SysFreeString` at `0x140009b98`
- `OLEAUT32!__imp_SysFreeString` at `0x140009b98`
- `OLEAUT32!__imp_VariantInit` at `0x140009ac6`
- `OLEAUT32!__imp_VariantInit` at `0x140009ac6`
- `OLEAUT32!__imp_VariantClear` at `0x140009bbb`
- `OLEAUT32!__imp_VariantClear` at `0x140009bfa`
- `OLEAUT32!__imp_VariantClear` at `0x140009bbb`
- `OLEAUT32!__imp_VariantClear` at `0x140009bfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009a8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009b24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009a8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009b24`

## pseudocode

```c
__int64 __fastcall CIsoBurn::_GetDiscRecorderForVolume(LPCWCH lpString1, LPVOID *a2)
{
  HRESULT v4; // ebx
  int v5; // edi
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v10; // [rsp+A0h] [rbp+40h] BYREF
  LPCWCH lpString2; // [rsp+A8h] [rbp+48h] BYREF

  ppv = 0;
  v7 = 0;
  v4 = CoCreateInstance(&CLSID_MsftDiscMaster2, 0, 0x17u, &GUID_27354130_7f64_5b0f_8f00_5d77afbe261e, &ppv);
  if ( v4 >= 0 )
  {
    v5 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, &v7);
    if ( v4 >= 0 )
    {
      while ( 1 )
      {
        VariantInit(&pvarg);
        v10 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v7 + 24LL))(
               v7,
               1,
               &pvarg,
               0) )
        {
          break;
        }
        if ( pvarg.vt == 8 )
        {
          v4 = CoCreateInstance(&CLSID_MsftDiscRecorder2, 0, 0x17u, &GUID_27354133_7f64_5b0f_8f00_5d77afbe261e, &v10);
          if ( v4 >= 0 )
          {
            if ( (*(int (__fastcall **)(LPVOID, LONGLONG))(*(_QWORD *)v10 + 104LL))(v10, pvarg.llVal) >= 0 )
            {
              lpString2 = 0;
              v4 = (*(__int64 (__fastcall **)(LPVOID, LPCWCH *))(*(_QWORD *)v10 + 144LL))(v10, &lpString2);
              if ( v4 >= 0 )
              {
                if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) == 2 )
                  v5 = 1;
                SysFreeString((BSTR)lpString2);
              }
            }
            else
            {
              v4 = -1062539262;
            }
          }
          if ( v5 )
          {
            *a2 = v10;
            v10 = 0;
            goto LABEL_21;
          }
        }
        else
        {
          v4 = -2147418113;
        }
        if ( v10 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
        VariantClear(&pvarg);
        if ( v4 < 0 )
          goto LABEL_22;
      }
      v4 = -1062539263;
      if ( v10 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_21:
      VariantClear(&pvarg);
    }
  }
LABEL_22:
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009a48  mov     [rsp-28h+arg_0], rbx
0x140009a4d  push    rbp
0x140009a4e  push    rsi
0x140009a4f  push    rdi
0x140009a50  push    r12
0x140009a52  push    r14
0x140009a54  mov     rbp, rsp
0x140009a57  sub     rsp, 60h
0x140009a5b  mov     rsi, rdx
0x140009a5e  mov     [rbp+var_28], 0
0x140009a66  xor     edx, edx; pUnkOuter
0x140009a68  mov     [rbp+var_30], 0
0x140009a70  mov     r14, rcx
0x140009a73  lea     rax, [rbp+var_28]
0x140009a77  lea     r9, _GUID_27354130_7f64_5b0f_8f00_5d77afbe261e; riid
0x140009a7e  mov     [rsp+60h+ppv], rax; ppv
0x140009a83  lea     rcx, CLSID_MsftDiscMaster2; rclsid
0x140009a8a  lea     r8d, [rdx+17h]; dwClsContext
0x140009a8e  call    cs:__imp_CoCreateInstance
0x140009a94  mov     ebx, eax
0x140009a96  test    eax, eax
0x140009a98  js      loc_140009C00
0x140009a9e  mov     rcx, [rbp+var_28]
0x140009aa2  lea     rdx, [rbp+var_30]
0x140009aa6  xor     edi, edi
0x140009aa8  mov     rax, [rcx]
0x140009aab  mov     rax, [rax+38h]
0x140009aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ab4  mov     ebx, eax
0x140009ab6  test    eax, eax
0x140009ab8  js      loc_140009C00
0x140009abe  lea     r12d, [rdi+1]
0x140009ac2  lea     rcx, [rbp+pvarg]; pvarg
0x140009ac6  call    cs:__imp_VariantInit
0x140009acc  mov     rcx, [rbp+var_30]
0x140009ad0  lea     r8, [rbp+pvarg]
0x140009ad4  mov     [rbp+arg_10], 0
0x140009adc  xor     r9d, r9d
0x140009adf  mov     edx, r12d
0x140009ae2  mov     rax, [rcx]
0x140009ae5  mov     rax, [rax+18h]
0x140009ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009aee  test    eax, eax
0x140009af0  jnz     loc_140009BDC
0x140009af6  cmp     word ptr [rbp+pvarg], 8
0x140009afb  jz      short loc_140009B07
0x140009afd  mov     ebx, 8000FFFFh
0x140009b02  jmp     loc_140009BA2
0x140009b07  xor     edx, edx; pUnkOuter
0x140009b09  lea     rax, [rbp+arg_10]
0x140009b0d  lea     r9, _GUID_27354133_7f64_5b0f_8f00_5d77afbe261e; riid
0x140009b14  mov     [rsp+60h+ppv], rax; ppv
0x140009b19  lea     rcx, CLSID_MsftDiscRecorder2; rclsid
0x140009b20  lea     r8d, [rdx+17h]; dwClsContext
0x140009b24  call    cs:__imp_CoCreateInstance
0x140009b2a  mov     ebx, eax
0x140009b2c  test    eax, eax
0x140009b2e  js      short loc_140009B9E
0x140009b30  mov     rcx, [rbp+arg_10]
0x140009b34  mov     rdx, qword ptr [rbp+pvarg+8]
0x140009b38  mov     rax, [rcx]
0x140009b3b  mov     rax, [rax+68h]
0x140009b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b44  test    eax, eax
0x140009b46  jns     short loc_140009B4F
0x140009b48  mov     ebx, 0C0AAF002h
0x140009b4d  jmp     short loc_140009B9E
0x140009b4f  mov     rcx, [rbp+arg_10]
0x140009b53  lea     rdx, [rbp+lpString2]
0x140009b57  mov     [rbp+lpString2], 0
0x140009b5f  mov     rax, [rcx]
0x140009b62  mov     rax, [rax+90h]
0x140009b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b6e  mov     ebx, eax
0x140009b70  test    eax, eax
0x140009b72  js      short loc_140009B9E
0x140009b74  mov     r8, [rbp+lpString2]; lpString2
0x140009b78  or      r9d, 0FFFFFFFFh; cchCount2
0x140009b7c  or      edx, r9d; cchCount1
0x140009b7f  mov     dword ptr [rsp+60h+ppv], r12d; bIgnoreCase
0x140009b84  mov     rcx, r14; lpString1
0x140009b87  call    cs:__imp_CompareStringOrdinal
0x140009b8d  mov     rcx, [rbp+lpString2]; bstrString
0x140009b91  cmp     eax, 2
0x140009b94  cmovz   edi, r12d
0x140009b98  call    cs:__imp_SysFreeString
0x140009b9e  test    edi, edi
0x140009ba0  jnz     short loc_140009BCB
0x140009ba2  mov     rcx, [rbp+arg_10]
0x140009ba6  test    rcx, rcx
0x140009ba9  jz      short loc_140009BB7
0x140009bab  mov     rax, [rcx]
0x140009bae  mov     rax, [rax+10h]
0x140009bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bb7  lea     rcx, [rbp+pvarg]; pvarg
0x140009bbb  call    cs:__imp_VariantClear
0x140009bc1  test    ebx, ebx
0x140009bc3  jns     loc_140009AC2
0x140009bc9  jmp     short loc_140009C00
0x140009bcb  mov     rax, [rbp+arg_10]
0x140009bcf  mov     [rsi], rax
0x140009bd2  mov     [rbp+arg_10], 0
0x140009bda  jmp     short loc_140009BF6
0x140009bdc  mov     rcx, [rbp+arg_10]
0x140009be0  mov     ebx, 0C0AAF001h
0x140009be5  test    rcx, rcx
0x140009be8  jz      short loc_140009BF6
0x140009bea  mov     rax, [rcx]
0x140009bed  mov     rax, [rax+10h]
0x140009bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bf6  lea     rcx, [rbp+pvarg]; pvarg
0x140009bfa  call    cs:__imp_VariantClear
0x140009c00  mov     rcx, [rbp+var_30]
0x140009c04  test    rcx, rcx
0x140009c07  jz      short loc_140009C15
0x140009c09  mov     rax, [rcx]
0x140009c0c  mov     rax, [rax+10h]
0x140009c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c15  mov     rcx, [rbp+var_28]
0x140009c19  test    rcx, rcx
0x140009c1c  jz      short loc_140009C2A
0x140009c1e  mov     rax, [rcx]
0x140009c21  mov     rax, [rax+10h]
0x140009c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c2a  mov     eax, ebx
0x140009c2c  mov     rbx, [rsp+60h+arg_0]
0x140009c34  add     rsp, 60h
0x140009c38  pop     r14
0x140009c3a  pop     r12
0x140009c3c  pop     rdi
0x140009c3d  pop     rsi
0x140009c3e  pop     rbp
0x140009c3f  retn
```
