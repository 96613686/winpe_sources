# TMBSchemaCompilation::RenameBinFileVersion(long,long)

- ea: `0x1800176b8`
- end: `0x1800177ed`
- name: `?RenameBinFileVersion@TMBSchemaCompilation@@AEAAJJJ@Z`
- size: `309`
- prototype: `__int64 __fastcall(TMBSchemaCompilation *this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017b70`

## callees

- `0x180005870`
- `0x1800176b8`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180017732`
- `msvcrt!swprintf_s` at `0x180017785`
- `msvcrt!swprintf_s` at `0x180017732`
- `msvcrt!swprintf_s` at `0x180017785`
- `KERNEL32!MoveFileExW` at `0x180017797`
- `KERNEL32!MoveFileExW` at `0x180017797`
- `ole32!CoTaskMemAlloc` at `0x1800176e9`
- `ole32!CoTaskMemAlloc` at `0x18001774b`
- `ole32!CoTaskMemAlloc` at `0x1800176e9`
- `ole32!CoTaskMemAlloc` at `0x18001774b`

## pseudocode

```c
__int64 __fastcall TMBSchemaCompilation::RenameBinFileVersion(TMBSchemaCompilation *this, int a2)
{
  wchar_t *v4; // rax
  const WCHAR *v5; // rbx
  wchar_t *v7; // rax
  const WCHAR *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // [rsp+20h] [rbp-48h]
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  wchar_t *v12; // [rsp+88h] [rbp+20h] BYREF

  if ( a2 < 0 )
    return 2147942487LL;
  v4 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v5 = v4;
  v12 = v4;
  if ( !v4 )
  {
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v12);
    return 2147942414LL;
  }
  swprintf_s(v4, *((_QWORD *)this + 320), L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), a2);
  v7 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v8 = v7;
  v11[0] = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
LABEL_8:
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(v11);
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v12);
    return v9;
  }
  LODWORD(v10) = 0;
  swprintf_s(v7, *((_QWORD *)this + 320), L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), v10);
  if ( !MoveFileExW(v5, v8, 3u) )
  {
    v9 = -2147467259;
    goto LABEL_8;
  }
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(v11);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v12);
  return 0;
}

```

## disassembly

```asm
0x1800176b8  push    rbx
0x1800176ba  push    rsi
0x1800176bb  push    rdi
0x1800176bc  push    r14
0x1800176be  sub     rsp, 48h
0x1800176c2  mov     edi, edx
0x1800176c4  mov     rsi, rcx
0x1800176c7  test    edx, edx
0x1800176c9  js      loc_1800177DE
0x1800176cf  mov     eax, 2
0x1800176d4  mul     qword ptr [rcx+0A00h]
0x1800176db  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800176e2  cmovb   rax, r14
0x1800176e6  mov     rcx, rax; cb
0x1800176e9  call    cs:__imp_CoTaskMemAlloc
0x1800176ef  mov     rbx, rax
0x1800176f2  mov     [rsp+68h+arg_18], rax
0x1800176fa  test    rax, rax
0x1800176fd  jnz     short loc_180017716
0x1800176ff  lea     rcx, [rsp+68h+arg_18]; void *
0x180017707  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x18001770c  mov     eax, 8007000Eh
0x180017711  jmp     loc_1800177E3
0x180017716  mov     [rsp+68h+var_48], edi
0x18001771a  mov     r9, [rsi+0A08h]
0x180017721  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x180017728  mov     rdx, [rsi+0A00h]; BufferCount
0x18001772f  mov     rcx, rbx; Buffer
0x180017732  call    cs:__imp_swprintf_s
0x180017738  mov     eax, 2
0x18001773d  mul     qword ptr [rsi+0A00h]
0x180017744  cmovb   rax, r14
0x180017748  mov     rcx, rax; cb
0x18001774b  call    cs:__imp_CoTaskMemAlloc
0x180017751  mov     rdi, rax
0x180017754  mov     [rsp+68h+var_38], rax
0x180017759  test    rax, rax
0x18001775c  jnz     short loc_180017765
0x18001775e  mov     ebx, 8007000Eh
0x180017763  jmp     short loc_1800177A6
0x180017765  mov     [rsp+68h+var_48], 0
0x18001776d  mov     r9, [rsi+0A08h]
0x180017774  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x18001777b  mov     rdx, [rsi+0A00h]; BufferCount
0x180017782  mov     rcx, rdi; Buffer
0x180017785  call    cs:__imp_swprintf_s
0x18001778b  mov     r8d, 3; dwFlags
0x180017791  mov     rdx, rdi; lpNewFileName
0x180017794  mov     rcx, rbx; lpExistingFileName
0x180017797  call    cs:__imp_MoveFileExW
0x18001779d  test    eax, eax
0x18001779f  jnz     short loc_1800177C2
0x1800177a1  mov     ebx, 80004005h
0x1800177a6  lea     rcx, [rsp+68h+var_38]; void *
0x1800177ab  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800177b0  nop
0x1800177b1  lea     rcx, [rsp+68h+arg_18]; void *
0x1800177b9  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800177be  mov     eax, ebx
0x1800177c0  jmp     short loc_1800177E3
0x1800177c2  lea     rcx, [rsp+68h+var_38]; void *
0x1800177c7  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800177cc  nop
0x1800177cd  lea     rcx, [rsp+68h+arg_18]; void *
0x1800177d5  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800177da  xor     eax, eax
0x1800177dc  jmp     short loc_1800177E3
0x1800177de  mov     eax, 80070057h
0x1800177e3  add     rsp, 48h
0x1800177e7  pop     r14
0x1800177e9  pop     rdi
0x1800177ea  pop     rsi
0x1800177eb  pop     rbx
0x1800177ec  retn
```
