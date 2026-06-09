# CNetDiagClient::ExtractSimpleDataType(void *,void *,ulong)

- ea: `0x18000c8fc`
- end: `0x18000c9a7`
- name: `?ExtractSimpleDataType@CNetDiagClient@@IEAAJPEAX0K@Z`
- size: `171`
- prototype: `__int64 __fastcall(CNetDiagClient *this, void *, void *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000cd4c`
- `0x18000e2d4`
- `0x180016f30`

## callees

- `0x1800026a6`
- `0x18000c8fc`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c942`
- `ole32!CoTaskMemAlloc` at `0x18000c942`
- `ole32!CoTaskMemFree` at `0x18000c98c`
- `ole32!CoTaskMemFree` at `0x18000c98c`
- `wdi!WdiGetParameterDataLength` at `0x18000c92c`
- `wdi!WdiGetParameterDataLength` at `0x18000c92c`
- `wdi!WdiGetParameterData` at `0x18000c962`
- `wdi!WdiGetParameterData` at `0x18000c962`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ExtractSimpleDataType(CNetDiagClient *this, void *a2, void *a3, unsigned int a4)
{
  size_t v5; // rsi
  void *v7; // rdi
  int ParameterDataLength; // ebx
  LPVOID v9; // rax
  unsigned int cb; // [rsp+40h] [rbp+8h] BYREF
  int cb_4; // [rsp+44h] [rbp+Ch]

  cb_4 = HIDWORD(this);
  v5 = a4;
  cb = 0;
  v7 = 0;
  ParameterDataLength = WdiGetParameterDataLength(a2, &cb);
  if ( ParameterDataLength >= 0 && cb )
  {
    v9 = CoTaskMemAlloc(cb);
    v7 = v9;
    if ( v9 )
    {
      ParameterDataLength = WdiGetParameterData(a2, v9, cb);
      if ( ParameterDataLength >= 0 )
      {
        if ( cb <= (unsigned int)v5 )
          memcpy_0(a3, v7, v5);
        else
          ParameterDataLength = -2147024774;
      }
    }
    else
    {
      ParameterDataLength = -2147024882;
    }
  }
  CoTaskMemFree(v7);
  return (unsigned int)ParameterDataLength;
}

```

## disassembly

```asm
0x18000c8fc  mov     rax, rsp
0x18000c8ff  mov     [rax+10h], rbx
0x18000c903  mov     [rax+18h], rbp
0x18000c907  mov     [rax+8], rcx
0x18000c90b  push    rsi
0x18000c90c  push    rdi
0x18000c90d  push    r14
0x18000c90f  sub     rsp, 20h
0x18000c913  mov     rbp, rdx
0x18000c916  mov     esi, r9d
0x18000c919  mov     rcx, rbp
0x18000c91c  mov     dword ptr [rax+8], 0
0x18000c923  lea     rdx, [rax+8]
0x18000c927  mov     r14, r8
0x18000c92a  xor     edi, edi
0x18000c92c  call    cs:__imp_WdiGetParameterDataLength
0x18000c932  mov     ebx, eax
0x18000c934  test    eax, eax
0x18000c936  js      short loc_18000C989
0x18000c938  mov     eax, dword ptr [rsp+38h+cb]
0x18000c93c  test    eax, eax
0x18000c93e  jz      short loc_18000C989
0x18000c940  mov     ecx, eax; cb
0x18000c942  call    cs:__imp_CoTaskMemAlloc
0x18000c948  mov     rdi, rax
0x18000c94b  test    rax, rax
0x18000c94e  jnz     short loc_18000C957
0x18000c950  mov     ebx, 8007000Eh
0x18000c955  jmp     short loc_18000C989
0x18000c957  mov     r8d, dword ptr [rsp+38h+cb]
0x18000c95c  mov     rdx, rdi
0x18000c95f  mov     rcx, rbp
0x18000c962  call    cs:__imp_WdiGetParameterData
0x18000c968  mov     ebx, eax
0x18000c96a  test    eax, eax
0x18000c96c  js      short loc_18000C989
0x18000c96e  cmp     dword ptr [rsp+38h+cb], esi
0x18000c972  jbe     short loc_18000C97B
0x18000c974  mov     ebx, 8007007Ah
0x18000c979  jmp     short loc_18000C989
0x18000c97b  mov     r8, rsi; Size
0x18000c97e  mov     rdx, rdi; Src
0x18000c981  mov     rcx, r14; void *
0x18000c984  call    memcpy_0
0x18000c989  mov     rcx, rdi; pv
0x18000c98c  call    cs:__imp_CoTaskMemFree
0x18000c992  mov     rbp, [rsp+38h+arg_10]
0x18000c997  mov     eax, ebx
0x18000c999  mov     rbx, [rsp+38h+arg_8]
0x18000c99e  add     rsp, 20h
0x18000c9a2  pop     r14
0x18000c9a4  pop     rdi
0x18000c9a5  pop     rsi
0x18000c9a6  retn
```
