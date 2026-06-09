# CNetDiagClient::ExtractString(void *,ushort * *)

- ea: `0x18000c9b0`
- end: `0x18000ca45`
- name: `?ExtractString@CNetDiagClient@@IEAAJPEAXPEAPEAG@Z`
- size: `149`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e0c4`
- `0x18000e2d4`

## callees

- `0x18000c9b0`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c9ed`
- `ole32!CoTaskMemAlloc` at `0x18000c9ed`
- `ole32!CoTaskMemFree` at `0x18000ca03`
- `ole32!CoTaskMemFree` at `0x18000ca03`
- `wdi!WdiGetParameterDataLength` at `0x18000c9d5`
- `wdi!WdiGetParameterDataLength` at `0x18000c9d5`
- `wdi!WdiGetParameterData` at `0x18000ca32`
- `wdi!WdiGetParameterData` at `0x18000ca32`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ExtractString(CNetDiagClient *this, void *a2, unsigned __int16 **a3)
{
  void *v5; // rbx
  int ParameterDataLength; // edi
  void *v7; // rax
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]

  v10 = HIDWORD(this);
  v9 = 0;
  v5 = 0;
  ParameterDataLength = WdiGetParameterDataLength(a2, &v9);
  if ( ParameterDataLength < 0 )
    goto LABEL_5;
  if ( v9 )
  {
    v7 = CoTaskMemAlloc(v9 + 2LL);
    v5 = v7;
    if ( !v7 )
    {
      ParameterDataLength = -2147024882;
LABEL_5:
      CoTaskMemFree(v5);
      return (unsigned int)ParameterDataLength;
    }
    memset_0(v7, 0, v9 + 2LL);
    ParameterDataLength = WdiGetParameterData(a2, v5, v9);
    if ( ParameterDataLength < 0 )
      goto LABEL_5;
    *a3 = (unsigned __int16 *)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c9b0  mov     [rsp+arg_0], rcx
0x18000c9b5  push    rbx
0x18000c9b6  push    rbp
0x18000c9b7  push    rsi
0x18000c9b8  push    rdi
0x18000c9b9  sub     rsp, 28h
0x18000c9bd  mov     rbp, rdx
0x18000c9c0  mov     dword ptr [rsp+48h+arg_0], 0
0x18000c9c8  mov     rcx, rbp
0x18000c9cb  lea     rdx, [rsp+48h+arg_0]
0x18000c9d0  mov     rsi, r8
0x18000c9d3  xor     ebx, ebx
0x18000c9d5  call    cs:__imp_WdiGetParameterDataLength
0x18000c9db  mov     edi, eax
0x18000c9dd  test    eax, eax
0x18000c9df  js      short loc_18000CA00
0x18000c9e1  mov     eax, dword ptr [rsp+48h+arg_0]
0x18000c9e5  test    eax, eax
0x18000c9e7  jz      short loc_18000CA41
0x18000c9e9  lea     rcx, [rax+2]; cb
0x18000c9ed  call    cs:__imp_CoTaskMemAlloc
0x18000c9f3  mov     rbx, rax
0x18000c9f6  test    rax, rax
0x18000c9f9  jnz     short loc_18000CA14
0x18000c9fb  mov     edi, 8007000Eh
0x18000ca00  mov     rcx, rbx; pv
0x18000ca03  call    cs:__imp_CoTaskMemFree
0x18000ca09  mov     eax, edi
0x18000ca0b  add     rsp, 28h
0x18000ca0f  pop     rdi
0x18000ca10  pop     rsi
0x18000ca11  pop     rbp
0x18000ca12  pop     rbx
0x18000ca13  retn
0x18000ca14  mov     r8d, dword ptr [rsp+48h+arg_0]
0x18000ca19  xor     edx, edx; Val
0x18000ca1b  add     r8, 2; Size
0x18000ca1f  mov     rcx, rbx; void *
0x18000ca22  call    memset_0
0x18000ca27  mov     r8d, dword ptr [rsp+48h+arg_0]
0x18000ca2c  mov     rdx, rbx
0x18000ca2f  mov     rcx, rbp
0x18000ca32  call    cs:__imp_WdiGetParameterData
0x18000ca38  mov     edi, eax
0x18000ca3a  test    eax, eax
0x18000ca3c  js      short loc_18000CA00
0x18000ca3e  mov     [rsi], rbx
0x18000ca41  xor     eax, eax
0x18000ca43  jmp     short loc_18000CA0B
```
