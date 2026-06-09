# IISCryptoCloneBlobFromRawData2

- ea: `0x180029d74`
- end: `0x180029e1b`
- name: `IISCryptoCloneBlobFromRawData2`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001f720`

## callees

- `0x180029d74`
- `0x18003098e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180029d9b`
- `ole32!CoTaskMemAlloc` at `0x180029d9b`
- `ole32!CoTaskMemFree` at `0x180029dff`
- `ole32!CoTaskMemFree` at `0x180029dff`

## pseudocode

```c
__int64 __fastcall IISCryptoCloneBlobFromRawData2(_QWORD *a1, _DWORD *a2, int a3)
{
  unsigned int v3; // eax
  unsigned int v6; // r9d
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  unsigned int v10; // ecx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // edx

  v3 = a2[1];
  v6 = v3 + 8;
  if ( v3 + 8 < v3 || v6 != a3 )
    return 2147942413LL;
  v7 = v3 + 8;
  v8 = CoTaskMemAlloc(v6);
  v9 = v8;
  if ( v8 )
  {
    memcpy_0(v8, a2, v7);
    if ( *v9 == 1649632073 )
    {
      v10 = v9[3];
      v11 = v9[2];
      v12 = v10 + 8;
      if ( v10 + 8 < v10 || (v14 = (v11 + 7) & 0xFFFFFFF8, v14 < v11) )
      {
        v13 = 0;
      }
      else
      {
        v13 = v14 + v12;
        if ( v14 + v12 < v14 )
          v13 = 0;
      }
      if ( v11 && v9[1] == v13 && v13 )
      {
        *a1 = v9;
        return 0;
      }
    }
    CoTaskMemFree(v9);
    return 2147942413LL;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180029d74  push    rbx
0x180029d76  push    rsi
0x180029d77  push    rdi
0x180029d78  push    r14
0x180029d7a  sub     rsp, 28h
0x180029d7e  mov     eax, [rdx+4]
0x180029d81  mov     rsi, rdx
0x180029d84  mov     r14, rcx
0x180029d87  lea     r9d, [rax+8]
0x180029d8b  cmp     r9d, eax
0x180029d8e  jb      short loc_180029E05
0x180029d90  cmp     r9d, r8d
0x180029d93  jnz     short loc_180029E05
0x180029d95  mov     ecx, r9d; cb
0x180029d98  mov     edi, r9d
0x180029d9b  call    cs:__imp_CoTaskMemAlloc
0x180029da1  mov     rbx, rax
0x180029da4  test    rax, rax
0x180029da7  jz      short loc_180029E14
0x180029da9  mov     r8d, edi; Size
0x180029dac  mov     rdx, rsi; Src
0x180029daf  mov     rcx, rax; void *
0x180029db2  call    memcpy_0
0x180029db7  cmp     dword ptr [rbx], 62536349h
0x180029dbd  jnz     short loc_180029DFC
0x180029dbf  mov     ecx, [rbx+0Ch]
0x180029dc2  mov     r8d, [rbx+8]
0x180029dc6  lea     eax, [rcx+8]
0x180029dc9  cmp     eax, ecx
0x180029dcb  jnb     short loc_180029DD1
0x180029dcd  xor     ecx, ecx
0x180029dcf  jmp     short loc_180029DE7
0x180029dd1  lea     edx, [r8+7]
0x180029dd5  and     edx, 0FFFFFFF8h
0x180029dd8  cmp     edx, r8d
0x180029ddb  jb      short loc_180029DCD
0x180029ddd  lea     ecx, [rdx+rax]
0x180029de0  xor     eax, eax
0x180029de2  cmp     ecx, edx
0x180029de4  cmovb   ecx, eax
0x180029de7  test    r8d, r8d
0x180029dea  jz      short loc_180029DFC
0x180029dec  cmp     [rbx+4], ecx
0x180029def  jnz     short loc_180029DFC
0x180029df1  test    ecx, ecx
0x180029df3  jz      short loc_180029DFC
0x180029df5  mov     [r14], rbx
0x180029df8  xor     eax, eax
0x180029dfa  jmp     short loc_180029E0A
0x180029dfc  mov     rcx, rbx; pv
0x180029dff  call    cs:__imp_CoTaskMemFree
0x180029e05  mov     eax, 8007000Dh
0x180029e0a  add     rsp, 28h
0x180029e0e  pop     r14
0x180029e10  pop     rdi
0x180029e11  pop     rsi
0x180029e12  pop     rbx
0x180029e13  retn
0x180029e14  mov     eax, 80070008h
0x180029e19  jmp     short loc_180029E0A
```
