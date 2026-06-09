# CreateBrush(ulong,ulong,unsigned __int64,unsigned __int64,void *)

- ea: `0x18002e39c`
- end: `0x18002e4e9`
- name: `?CreateBrush@@YAPEAUHBRUSH__@@KK_K0PEAX@Z`
- size: `333`
- prototype: `HBRUSH __fastcall(unsigned int, unsigned int, unsigned __int64, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e2d0`
- `0x1800479b0`
- `0x18008aab0`

## callees

- `0x18002e39c`
- `0x180036734`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x18002e4ce`
- `GDI32!hGetPEBHandle` at `0x18002e3b0`
- `GDI32!hGetPEBHandle` at `0x18002e3b0`
- `ntdll!RtlFreeHeap` at `0x18002e48f`
- `ntdll!RtlFreeHeap` at `0x18002e48f`
- `win32u!NtGdiCreateSolidBrush` at `0x18002e3c9`
- `win32u!NtGdiCreateSolidBrush` at `0x18002e3c9`
- `win32u!NtGdiCreatePatternBrushInternal` at `0x18002e4ac`
- `win32u!NtGdiCreatePatternBrushInternal` at `0x18002e4ac`
- `win32u!NtGdiCreateHatchBrushInternal` at `0x18002e4c0`
- `win32u!NtGdiCreateHatchBrushInternal` at `0x18002e4c0`
- `win32u!NtGdiCreateDIBBrush` at `0x18002e469`
- `win32u!NtGdiCreateDIBBrush` at `0x18002e469`

## pseudocode

```c
HBRUSH __fastcall CreateBrush(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void *a5)
{
  unsigned int v6; // ebx
  int v7; // esi
  HBRUSH result; // rax
  __int64 v9; // r8
  void *v10; // rbp
  __int64 v11; // rax
  void *v12; // rdi
  __int64 DIBBrush; // rbx
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v6 = a2;
  v7 = a1;
  switch ( (_DWORD)a1 )
  {
    case 0:
      result = (HBRUSH)hGetPEBHandle(a1, a2, a3, a3);
      if ( !result )
        return (HBRUSH)NtGdiCreateSolidBrush(v6, 0);
      return result;
    case 1:
      return *(HBRUSH *)(pGdiSharedMemory + 1573080LL);
    case 2:
      return (HBRUSH)NtGdiCreateHatchBrushInternal((unsigned int)a3, a2, 0);
    case 3:
      v9 = 0;
      return (HBRUSH)NtGdiCreatePatternBrushInternal(a3, 0, v9);
  }
  if ( (_DWORD)a1 != 5 && (_DWORD)a1 != 6 )
  {
    if ( (_DWORD)a1 != 7 )
    {
      if ( (_DWORD)a1 != 8 )
        return 0;
      goto LABEL_13;
    }
    v9 = 1;
    return (HBRUSH)NtGdiCreatePatternBrushInternal(a3, 0, v9);
  }
LABEL_13:
  v10 = a5;
  v14 = 0;
  v11 = pbmiConvertInfo(a5, a2, &v14, 1);
  v12 = (void *)v11;
  if ( !v11 )
    return 0;
  DIBBrush = NtGdiCreateDIBBrush(v11, v6, v14, v7 == 8, 0, v10);
  if ( v12 != v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  return (HBRUSH)DIBBrush;
}

```

## disassembly

```asm
0x18002e39c  push    rbx
0x18002e39e  push    rbp
0x18002e39f  push    rsi
0x18002e3a0  push    rdi
0x18002e3a1  sub     rsp, 38h
0x18002e3a5  mov     r9, r8
0x18002e3a8  mov     ebx, edx
0x18002e3aa  mov     esi, ecx
0x18002e3ac  test    ecx, ecx
0x18002e3ae  jnz     short loc_18002E3DA
0x18002e3b0  call    cs:__imp_hGetPEBHandle
0x18002e3b7  nop     dword ptr [rax+rax+00h]
0x18002e3bc  test    rax, rax
0x18002e3bf  jnz     loc_18002E4DF
0x18002e3c5  xor     edx, edx
0x18002e3c7  mov     ecx, ebx
0x18002e3c9  call    cs:__imp_NtGdiCreateSolidBrush
0x18002e3d0  nop     dword ptr [rax+rax+00h]
0x18002e3d5  jmp     loc_18002E4DF
0x18002e3da  mov     eax, esi
0x18002e3dc  sub     eax, 1
0x18002e3df  jz      loc_18002E4CE
0x18002e3e5  sub     eax, 1
0x18002e3e8  jz      loc_18002E4BA
0x18002e3ee  sub     eax, 1
0x18002e3f1  jz      loc_18002E4A4
0x18002e3f7  sub     eax, 2
0x18002e3fa  jz      short loc_18002E41D
0x18002e3fc  sub     eax, 1
0x18002e3ff  jz      short loc_18002E41D
0x18002e401  sub     eax, 1
0x18002e404  jz      short loc_18002E412
0x18002e406  cmp     eax, 1
0x18002e409  jz      short loc_18002E41D
0x18002e40b  xor     eax, eax
0x18002e40d  jmp     loc_18002E4DF
0x18002e412  mov     r8d, 1
0x18002e418  jmp     loc_18002E4A7
0x18002e41d  mov     rbp, [rsp+58h+arg_20]
0x18002e425  lea     r8, [rsp+58h+arg_0]
0x18002e42a  mov     rcx, rbp
0x18002e42d  mov     [rsp+58h+arg_0], 0
0x18002e435  mov     r9d, 1
0x18002e43b  call    pbmiConvertInfo
0x18002e440  mov     rdi, rax
0x18002e443  test    rax, rax
0x18002e446  jz      short loc_18002E49D
0x18002e448  mov     r8d, [rsp+58h+arg_0]
0x18002e44d  xor     r9d, r9d
0x18002e450  cmp     esi, 8
0x18002e453  mov     [rsp+58h+var_30], rbp
0x18002e458  mov     edx, ebx
0x18002e45a  mov     [rsp+58h+var_38], 0
0x18002e462  setz    r9b
0x18002e466  mov     rcx, rax
0x18002e469  call    cs:__imp_NtGdiCreateDIBBrush
0x18002e470  nop     dword ptr [rax+rax+00h]
0x18002e475  mov     rbx, rax
0x18002e478  cmp     rdi, rbp
0x18002e47b  jz      short loc_18002E49F
0x18002e47d  mov     rcx, gs:60h
0x18002e486  mov     r8, rdi; P
0x18002e489  xor     edx, edx; Flags
0x18002e48b  mov     rcx, [rcx+30h]; HeapHandle
0x18002e48f  call    cs:__imp_RtlFreeHeap
0x18002e496  nop     dword ptr [rax+rax+00h]
0x18002e49b  jmp     short loc_18002E49F
0x18002e49d  xor     ebx, ebx
0x18002e49f  mov     rax, rbx
0x18002e4a2  jmp     short loc_18002E4DF
0x18002e4a4  xor     r8d, r8d
0x18002e4a7  xor     edx, edx
0x18002e4a9  mov     rcx, r9
0x18002e4ac  call    cs:__imp_NtGdiCreatePatternBrushInternal
0x18002e4b3  nop     dword ptr [rax+rax+00h]
0x18002e4b8  jmp     short loc_18002E4DF
0x18002e4ba  mov     ecx, r9d
0x18002e4bd  xor     r8d, r8d
0x18002e4c0  call    cs:__imp_NtGdiCreateHatchBrushInternal
0x18002e4c7  nop     dword ptr [rax+rax+00h]
0x18002e4cc  jmp     short loc_18002E4DF
0x18002e4ce  mov     rax, cs:__imp_pGdiSharedMemory
0x18002e4d5  mov     rax, [rax]
0x18002e4d8  mov     rax, [rax+1800D8h]
0x18002e4df  add     rsp, 38h
0x18002e4e3  pop     rdi
0x18002e4e4  pop     rsi
0x18002e4e5  pop     rbp
0x18002e4e6  pop     rbx
0x18002e4e7  retn
```
