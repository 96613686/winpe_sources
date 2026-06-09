# DpspAddDirectoryToTable

- ea: `0x180007e90`
- end: `0x180007f79`
- name: `DpspAddDirectoryToTable`
- size: `233`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _OWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015b84`

## callees

- `0x1800013a0`
- `0x180007e90`
- `0x180009090`

## string_xrefs

- `0x180007ec4`: `DpspAddDirectoryToTable`

## pseudocode

```c
__int64 __fastcall DpspAddDirectoryToTable(__int64 a1, _OWORD *a2, _OWORD *a3, unsigned int a4, __int64 a5)
{
  unsigned int v5; // ebx
  int v9; // r8d
  unsigned int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // r8
  _QWORD *v15; // rax

  v5 = a4;
  if ( !a1 )
  {
    v9 = 1119;
LABEL_3:
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspAddDirectoryToTable",
      v9,
      (int)L"Error = %d",
      87);
    return v10;
  }
  if ( !a2 )
  {
    v9 = 1120;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = 1121;
    goto LABEL_3;
  }
  v11 = *(_DWORD *)(a1 + 8);
  if ( a4 >= v11 )
    v5 = v11 - 1;
  v12 = WdipAlloc(56);
  v13 = (_QWORD *)v12;
  if ( v12 )
  {
    v14 = *(_QWORD *)a1 + 16LL * v5;
    *(_OWORD *)(v12 + 16) = *a2;
    *(_OWORD *)(v12 + 32) = *a3;
    *(_QWORD *)(v12 + 48) = a5;
    v15 = *(_QWORD **)(v14 + 8);
    if ( *v15 != v14 )
      __fastfail(3u);
    *v13 = v14;
    v10 = 0;
    v13[1] = v15;
    *v15 = v13;
    *(_QWORD *)(v14 + 8) = v13;
  }
  else
  {
    v10 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspAddDirectoryToTable",
      1134,
      (int)L"Error = %d",
      14);
  }
  return v10;
}

```

## disassembly

```asm
0x180007e90  push    rbx
0x180007e92  push    rbp
0x180007e93  push    rsi
0x180007e94  push    rdi
0x180007e95  sub     rsp, 38h
0x180007e99  mov     ebx, r9d
0x180007e9c  mov     rsi, r8
0x180007e9f  mov     rbp, rdx
0x180007ea2  mov     rdi, rcx
0x180007ea5  test    rcx, rcx
0x180007ea8  jnz     short loc_180007EDC
0x180007eaa  mov     r8d, 45Fh; int
0x180007eb0  mov     ebx, 80070057h
0x180007eb5  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180007ebd  lea     r9, aErrorD; "Error = %d"
0x180007ec4  lea     rdx, aDpspadddirecto; "DpspAddDirectoryToTable"
0x180007ecb  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007ed2  call    WdipTraceError
0x180007ed7  jmp     loc_180007F6E
0x180007edc  test    rbp, rbp
0x180007edf  jnz     short loc_180007EE9
0x180007ee1  mov     r8d, 460h
0x180007ee7  jmp     short loc_180007EB0
0x180007ee9  test    rsi, rsi
0x180007eec  jnz     short loc_180007EF6
0x180007eee  mov     r8d, 461h
0x180007ef4  jmp     short loc_180007EB0
0x180007ef6  mov     eax, [rcx+8]
0x180007ef9  cmp     ebx, eax
0x180007efb  jb      short loc_180007F00
0x180007efd  lea     ebx, [rax-1]
0x180007f00  mov     ecx, 38h ; '8'
0x180007f05  call    WdipAlloc
0x180007f0a  mov     rdx, rax
0x180007f0d  test    rax, rax
0x180007f10  jnz     short loc_180007F27
0x180007f12  mov     ebx, 8007000Eh
0x180007f17  mov     dword ptr [rsp+58h+Args], 0Eh
0x180007f1f  mov     r8d, 46Eh
0x180007f25  jmp     short loc_180007EBD
0x180007f27  movups  xmm0, xmmword ptr [rbp+0]
0x180007f2b  mov     r8d, ebx
0x180007f2e  shl     r8, 4
0x180007f32  add     r8, [rdi]
0x180007f35  movdqu  xmmword ptr [rax+10h], xmm0
0x180007f3a  movups  xmm1, xmmword ptr [rsi]
0x180007f3d  movdqu  xmmword ptr [rax+20h], xmm1
0x180007f42  mov     rax, [rsp+58h+arg_20]
0x180007f4a  mov     [rdx+30h], rax
0x180007f4e  mov     rax, [r8+8]
0x180007f52  cmp     [rax], r8
0x180007f55  jz      short loc_180007F5E
0x180007f57  mov     ecx, 3
0x180007f5c  int     29h; Win8: RtlFailFast(ecx)
0x180007f5e  mov     [rdx], r8
0x180007f61  xor     ebx, ebx
0x180007f63  mov     [rdx+8], rax
0x180007f67  mov     [rax], rdx
0x180007f6a  mov     [r8+8], rdx
0x180007f6e  mov     eax, ebx
0x180007f70  add     rsp, 38h
0x180007f74  pop     rdi
0x180007f75  pop     rsi
0x180007f76  pop     rbp
0x180007f77  pop     rbx
0x180007f78  retn
```
