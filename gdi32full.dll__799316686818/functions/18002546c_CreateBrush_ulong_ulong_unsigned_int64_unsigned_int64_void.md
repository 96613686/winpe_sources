# CreateBrush(ulong,ulong,unsigned __int64,unsigned __int64,void *)

- ea: `0x18002546c`
- end: `0x180025591`
- name: `?CreateBrush@@YAPEAUHBRUSH__@@KK_K0PEAX@Z`
- size: `293`
- prototype: `HBRUSH __fastcall(unsigned int, unsigned int, unsigned __int64, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800253b0`
- `0x18003bd30`
- `0x180085880`

## callees

- `0x18001d4fc`
- `0x18002546c`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x180025577`
- `GDI32!hGetPEBHandle` at `0x180025480`
- `GDI32!hGetPEBHandle` at `0x180025480`
- `ntdll!RtlFreeHeap` at `0x18002554a`
- `ntdll!RtlFreeHeap` at `0x18002554a`
- `win32u!NtGdiCreateSolidBrush` at `0x180025493`
- `win32u!NtGdiCreateSolidBrush` at `0x180025493`
- `win32u!NtGdiCreatePatternBrushInternal` at `0x180025561`
- `win32u!NtGdiCreatePatternBrushInternal` at `0x180025561`
- `win32u!NtGdiCreateHatchBrushInternal` at `0x18002556f`
- `win32u!NtGdiCreateHatchBrushInternal` at `0x18002556f`
- `win32u!NtGdiCreateDIBBrush` at `0x18002552a`
- `win32u!NtGdiCreateDIBBrush` at `0x18002552a`

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
0x18002546c  push    rbx
0x18002546e  push    rbp
0x18002546f  push    rsi
0x180025470  push    rdi
0x180025471  sub     rsp, 38h
0x180025475  mov     r9, r8
0x180025478  mov     ebx, edx
0x18002547a  mov     esi, ecx
0x18002547c  test    ecx, ecx
0x18002547e  jnz     short loc_18002549E
0x180025480  call    cs:__imp_hGetPEBHandle
0x180025486  test    rax, rax
0x180025489  jnz     loc_180025588
0x18002548f  xor     edx, edx
0x180025491  mov     ecx, ebx
0x180025493  call    cs:__imp_NtGdiCreateSolidBrush
0x180025499  jmp     loc_180025588
0x18002549e  mov     eax, esi
0x1800254a0  sub     eax, 1
0x1800254a3  jz      loc_180025577
0x1800254a9  sub     eax, 1
0x1800254ac  jz      loc_180025569
0x1800254b2  sub     eax, 1
0x1800254b5  jz      loc_180025559
0x1800254bb  sub     eax, 2
0x1800254be  jz      short loc_1800254DE
0x1800254c0  sub     eax, 1
0x1800254c3  jz      short loc_1800254DE
0x1800254c5  sub     eax, 1
0x1800254c8  jz      short loc_1800254D6
0x1800254ca  cmp     eax, 1
0x1800254cd  jz      short loc_1800254DE
0x1800254cf  xor     eax, eax
0x1800254d1  jmp     loc_180025588
0x1800254d6  mov     r8d, 1
0x1800254dc  jmp     short loc_18002555C
0x1800254de  mov     rbp, [rsp+58h+arg_20]
0x1800254e6  lea     r8, [rsp+58h+arg_0]
0x1800254eb  mov     rcx, rbp
0x1800254ee  mov     [rsp+58h+arg_0], 0
0x1800254f6  mov     r9d, 1
0x1800254fc  call    pbmiConvertInfo
0x180025501  mov     rdi, rax
0x180025504  test    rax, rax
0x180025507  jz      short loc_180025552
0x180025509  mov     r8d, [rsp+58h+arg_0]
0x18002550e  xor     r9d, r9d
0x180025511  cmp     esi, 8
0x180025514  mov     [rsp+58h+var_30], rbp
0x180025519  mov     edx, ebx
0x18002551b  mov     [rsp+58h+var_38], 0
0x180025523  setz    r9b
0x180025527  mov     rcx, rax
0x18002552a  call    cs:__imp_NtGdiCreateDIBBrush
0x180025530  mov     rbx, rax
0x180025533  cmp     rdi, rbp
0x180025536  jz      short loc_180025554
0x180025538  mov     rcx, gs:60h
0x180025541  mov     r8, rdi; P
0x180025544  xor     edx, edx; Flags
0x180025546  mov     rcx, [rcx+30h]; HeapHandle
0x18002554a  call    cs:__imp_RtlFreeHeap
0x180025550  jmp     short loc_180025554
0x180025552  xor     ebx, ebx
0x180025554  mov     rax, rbx
0x180025557  jmp     short loc_180025588
0x180025559  xor     r8d, r8d
0x18002555c  xor     edx, edx
0x18002555e  mov     rcx, r9
0x180025561  call    cs:__imp_NtGdiCreatePatternBrushInternal
0x180025567  jmp     short loc_180025588
0x180025569  mov     ecx, r9d
0x18002556c  xor     r8d, r8d
0x18002556f  call    cs:__imp_NtGdiCreateHatchBrushInternal
0x180025575  jmp     short loc_180025588
0x180025577  mov     rax, cs:__imp_pGdiSharedMemory
0x18002557e  mov     rax, [rax]
0x180025581  mov     rax, [rax+1800D8h]
0x180025588  add     rsp, 38h
0x18002558c  pop     rdi
0x18002558d  pop     rsi
0x18002558e  pop     rbp
0x18002558f  pop     rbx
0x180025590  retn
```
