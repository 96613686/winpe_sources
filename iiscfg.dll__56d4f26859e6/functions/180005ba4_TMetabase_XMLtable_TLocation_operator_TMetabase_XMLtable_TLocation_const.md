# TMetabase_XMLtable::TLocation::operator=(TMetabase_XMLtable::TLocation const &)

- ea: `0x180005ba4`
- end: `0x180005c41`
- name: `??4TLocation@TMetabase_XMLtable@@QEAAAEAV01@AEBV01@@Z`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000654c`
- `0x18000bf74`

## callees

- `0x180005ba4`
- `0x18002df9b`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005bb7`
- `ole32!CoTaskMemFree` at `0x180005bb7`
- `ole32!CoTaskMemAlloc` at `0x180005bea`
- `ole32!CoTaskMemAlloc` at `0x180005bea`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::TLocation::operator=(__int64 a1, __int64 a2)
{
  int v4; // eax
  void *v5; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
  if ( *(_QWORD *)a2 )
  {
    v4 = *(_DWORD *)(a2 + 16);
    *(_DWORD *)(a1 + 16) = v4;
    v5 = CoTaskMemAlloc(saturated_mul((unsigned int)(v4 + 1), 2u));
    *(_QWORD *)a1 = v5;
    if ( !v5 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    memcpy_0(v5, *(const void **)a2, 2LL * (unsigned int)(*(_DWORD *)(a1 + 16) + 1));
  }
  *(_DWORD *)(a1 + 12) = *(_DWORD *)(a2 + 12);
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  return a1;
}

```

## disassembly

```asm
0x180005ba4  mov     [rsp+arg_8], rbx
0x180005ba9  push    rdi
0x180005baa  sub     rsp, 20h
0x180005bae  mov     rbx, rcx
0x180005bb1  mov     rdi, rdx
0x180005bb4  mov     rcx, [rcx]; pv
0x180005bb7  call    cs:__imp_CoTaskMemFree
0x180005bbd  mov     qword ptr [rbx], 0
0x180005bc4  cmp     qword ptr [rdi], 0
0x180005bc8  jz      short loc_180005C27
0x180005bca  mov     eax, [rdi+10h]
0x180005bcd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005bd4  mov     [rbx+10h], eax
0x180005bd7  lea     r8d, [rax+1]
0x180005bdb  mov     eax, 2
0x180005be0  mul     r8
0x180005be3  cmovb   rax, rcx
0x180005be7  mov     rcx, rax; cb
0x180005bea  call    cs:__imp_CoTaskMemAlloc
0x180005bf0  mov     [rbx], rax
0x180005bf3  mov     rcx, rax; void *
0x180005bf6  test    rax, rax
0x180005bf9  jnz     short loc_180005C15
0x180005bfb  lea     rdx, _TI1J; pThrowInfo
0x180005c02  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x180005c0a  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005c0f  call    _CxxThrowException_0
0x180005c15  mov     r8d, [rbx+10h]
0x180005c19  mov     rdx, [rdi]; Src
0x180005c1c  inc     r8d
0x180005c1f  add     r8, r8; Size
0x180005c22  call    memcpy_0
0x180005c27  mov     eax, [rdi+0Ch]
0x180005c2a  mov     [rbx+0Ch], eax
0x180005c2d  mov     eax, [rdi+8]
0x180005c30  mov     [rbx+8], eax
0x180005c33  mov     rax, rbx
0x180005c36  mov     rbx, [rsp+28h+arg_8]
0x180005c3b  add     rsp, 20h
0x180005c3f  pop     rdi
0x180005c40  retn
```
