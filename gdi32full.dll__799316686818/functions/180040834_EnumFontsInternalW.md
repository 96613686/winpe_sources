# EnumFontsInternalW

- ea: `0x180040834`
- end: `0x180040a95`
- name: `EnumFontsInternalW`
- size: `609`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040650`
- `0x180040680`
- `0x1800406f8`
- `0x1800407e0`

## callees

- `0x180040834`
- `0x180040a9c`
- `0x180040c84`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a23`
- `GDI32!GdiSetLastError` at `0x180040a5b`
- `GDI32!GdiSetLastError` at `0x180040a5b`
- `ntdll!RtlFreeHeap` at `0x1800409c3`
- `ntdll!RtlFreeHeap` at `0x180040a3d`
- `ntdll!RtlFreeHeap` at `0x1800409c3`
- `ntdll!RtlFreeHeap` at `0x180040a3d`
- `ntdll!RtlAllocateHeap` at `0x1800408d0`
- `ntdll!RtlAllocateHeap` at `0x1800408d0`
- `USER32!GetAppCompatFlags` at `0x18004085f`
- `USER32!GetAppCompatFlags` at `0x18004085f`
- `win32u!NtGdiEnumFonts` at `0x1800408ab`
- `win32u!NtGdiEnumFonts` at `0x180040925`
- `win32u!NtGdiEnumFonts` at `0x1800408ab`
- `win32u!NtGdiEnumFonts` at `0x180040925`

## pseudocode

```c
__int64 __fastcall EnumFontsInternalW(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 (__fastcall *a4)(_QWORD, _QWORD, _QWORD, _QWORD),
        __int64 a5,
        unsigned int a6,
        char a7)
{
  __int64 v7; // rbx
  unsigned int AppCompatFlags; // r15d
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int *Heap; // rdi
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int *v17; // r14
  unsigned int *v18; // rbp
  char v19; // r13
  int v20; // r15d
  unsigned int v21; // eax
  unsigned int v22; // ebx
  int v24; // eax
  __int64 v25; // r9
  __int64 (__fastcall *v26)(_QWORD, _QWORD, _QWORD, _QWORD); // rdx
  DWORD LastError; // ebx
  bool v28; // zf
  __int64 v29; // rcx
  unsigned int v30; // eax
  SIZE_T Size; // [rsp+88h] [rbp+10h] BYREF
  __int64 (__fastcall *v33)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp+20h]

  v33 = a4;
  v7 = a1;
  LODWORD(Size) = 0;
  AppCompatFlags = GetAppCompatFlags(0);
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a2 + 2 * v11) );
    v12 = (unsigned int)(v11 + 1);
  }
  else
  {
    v12 = 0;
  }
  if ( (unsigned int)NtGdiEnumFonts(v7, a6, AppCompatFlags, v12, a2, a3, &Size, 0) )
  {
    while ( 1 )
    {
      Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      if ( !Heap )
      {
        v29 = 8;
        goto LABEL_29;
      }
      if ( a2 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(a2 + 2 * v14) );
        v15 = (unsigned int)(v14 + 1);
      }
      else
      {
        v15 = 0;
      }
      if ( (unsigned int)NtGdiEnumFonts(v7, a6, AppCompatFlags, v15, a2, a3, &Size, Heap) )
        break;
      LastError = GetLastError();
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v28 = LastError == 111;
      v7 = a1;
      if ( !v28 )
        return 0;
    }
    v17 = Heap;
    v18 = (unsigned int *)((char *)Heap + (unsigned int)Size);
    if ( Heap >= v18 )
    {
      v22 = 1;
    }
    else
    {
      v19 = a7;
      v20 = AppCompatFlags & 0x2000;
      while ( 1 )
      {
        if ( v20 )
        {
          v30 = Heap[2];
          if ( (v30 & 4) != 0 )
            Heap[2] = v30 & 0xFFFFFFFD;
        }
        if ( a2 && (v24 = Heap[2], v24 < 0) )
        {
          v25 = a5;
          v26 = v33;
          Heap[2] = v24 & 0x7FFFFFFF;
          v21 = iScaleEnum(v7, v26, Heap, v25);
        }
        else
        {
          v21 = (v19 & 1) != 0
              ? v33(Heap + 3, (char *)Heap + Heap[1] + 8, Heap[2], a5)
              : iAnsiCallback(Heap, v16, v33, a5);
        }
        v22 = v21;
        if ( !v21 )
          break;
        Heap = (unsigned int *)((char *)Heap + *Heap);
        if ( Heap >= v18 )
          break;
        v7 = a1;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    return v22;
  }
  else
  {
    v29 = 6;
LABEL_29:
    GdiSetLastError(v29);
    return 0;
  }
}

```

## disassembly

```asm
0x180040834  mov     rax, rsp
0x180040837  mov     [rax+20h], r9
0x18004083b  mov     [rax+8], rcx
0x18004083f  push    rbx
0x180040840  push    rbp
0x180040841  push    rsi
0x180040842  push    rdi
0x180040843  push    r13
0x180040845  push    r14
0x180040847  push    r15
0x180040849  sub     rsp, 40h
0x18004084d  mov     rbx, rcx
0x180040850  xor     r14d, r14d
0x180040853  xor     ecx, ecx
0x180040855  mov     [rax+10h], r14d
0x180040859  mov     ebp, r8d
0x18004085c  mov     rsi, rdx
0x18004085f  call    cs:__imp_GetAppCompatFlags
0x180040865  mov     r15d, eax
0x180040868  test    rsi, rsi
0x18004086b  jz      loc_180040A8D
0x180040871  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040875  inc     r8
0x180040878  cmp     [rsi+r8*2], r14w
0x18004087d  jnz     short loc_180040875
0x18004087f  lea     r9d, [r8+1]
0x180040883  mov     edx, [rsp+78h+arg_28]
0x18004088a  lea     rax, [rsp+78h+Size]
0x180040892  mov     [rsp+78h+var_40], r14
0x180040897  mov     r8d, r15d
0x18004089a  mov     [rsp+78h+var_48], rax
0x18004089f  mov     rcx, rbx
0x1800408a2  mov     [rsp+78h+var_50], ebp
0x1800408a6  mov     [rsp+78h+var_58], rsi
0x1800408ab  call    cs:__imp_NtGdiEnumFonts
0x1800408b1  test    eax, eax
0x1800408b3  jz      loc_180040A56
0x1800408b9  mov     rcx, gs:60h
0x1800408c2  xor     edx, edx; Flags
0x1800408c4  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x1800408cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800408d0  call    cs:__imp_RtlAllocateHeap
0x1800408d6  mov     rdi, rax
0x1800408d9  test    rax, rax
0x1800408dc  jz      loc_180040A86
0x1800408e2  test    rsi, rsi
0x1800408e5  jz      loc_180040A7E
0x1800408eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800408ef  inc     rax
0x1800408f2  cmp     [rsi+rax*2], r14w
0x1800408f7  jnz     short loc_1800408EF
0x1800408f9  lea     r9d, [rax+1]
0x1800408fd  mov     edx, [rsp+78h+arg_28]
0x180040904  lea     rax, [rsp+78h+Size]
0x18004090c  mov     [rsp+78h+var_40], rdi
0x180040911  mov     r8d, r15d
0x180040914  mov     [rsp+78h+var_48], rax
0x180040919  mov     rcx, rbx
0x18004091c  mov     [rsp+78h+var_50], ebp
0x180040920  mov     [rsp+78h+var_58], rsi
0x180040925  call    cs:__imp_NtGdiEnumFonts
0x18004092b  test    eax, eax
0x18004092d  jz      loc_180040A23
0x180040933  mov     ebp, dword ptr [rsp+78h+Size]
0x18004093a  mov     r14, rdi
0x18004093d  add     rbp, rdi
0x180040940  cmp     rdi, rbp
0x180040943  jnb     loc_180040A1C
0x180040949  mov     r13d, [rsp+78h+arg_30]
0x180040951  and     r15d, 2000h
0x180040958  jmp     short loc_180040962
0x18004095a  mov     rbx, [rsp+78h+arg_0]
0x180040962  test    r15d, r15d
0x180040965  jnz     loc_180040A68
0x18004096b  test    rsi, rsi
0x18004096e  jnz     short loc_1800409DA
0x180040970  mov     r9, [rsp+78h+arg_20]
0x180040978  test    r13b, 1
0x18004097c  jz      loc_180040A0A
0x180040982  mov     edx, [rdi+4]
0x180040985  lea     rcx, [rdi+0Ch]
0x180040989  mov     r8d, [rdi+8]
0x18004098d  add     rdx, 8
0x180040991  mov     rax, [rsp+78h+arg_18]
0x180040999  add     rdx, rdi
0x18004099c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409a1  mov     ebx, eax
0x1800409a3  test    eax, eax
0x1800409a5  jz      short loc_1800409B1
0x1800409a7  mov     eax, [rdi]
0x1800409a9  add     rdi, rax
0x1800409ac  cmp     rdi, rbp
0x1800409af  jb      short loc_18004095A
0x1800409b1  mov     rcx, gs:60h
0x1800409ba  mov     r8, r14; P
0x1800409bd  xor     edx, edx; Flags
0x1800409bf  mov     rcx, [rcx+30h]; HeapHandle
0x1800409c3  call    cs:__imp_RtlFreeHeap
0x1800409c9  mov     eax, ebx
0x1800409cb  add     rsp, 40h
0x1800409cf  pop     r15
0x1800409d1  pop     r14
0x1800409d3  pop     r13
0x1800409d5  pop     rdi
0x1800409d6  pop     rsi
0x1800409d7  pop     rbp
0x1800409d8  pop     rbx
0x1800409d9  retn
0x1800409da  mov     eax, [rdi+8]
0x1800409dd  test    eax, eax
0x1800409df  jns     short loc_180040970
0x1800409e1  mov     r9, [rsp+78h+arg_20]
0x1800409e9  btr     eax, 1Fh
0x1800409ed  mov     rdx, [rsp+78h+arg_18]
0x1800409f5  mov     r8, rdi
0x1800409f8  mov     rcx, rbx
0x1800409fb  mov     [rdi+8], eax
0x1800409fe  mov     [rsp+78h+var_50], r13d
0x180040a03  call    iScaleEnum
0x180040a08  jmp     short loc_1800409A1
0x180040a0a  mov     r8, [rsp+78h+arg_18]
0x180040a12  mov     rcx, rdi
0x180040a15  call    iAnsiCallback
0x180040a1a  jmp     short loc_1800409A1
0x180040a1c  mov     ebx, 1
0x180040a21  jmp     short loc_1800409B1
0x180040a23  call    cs:__imp_GetLastError
0x180040a29  mov     rcx, gs:60h
0x180040a32  mov     r8, rdi; P
0x180040a35  xor     edx, edx; Flags
0x180040a37  mov     ebx, eax
0x180040a39  mov     rcx, [rcx+30h]; HeapHandle
0x180040a3d  call    cs:__imp_RtlFreeHeap
0x180040a43  cmp     ebx, 6Fh ; 'o'
0x180040a46  mov     rbx, [rsp+78h+arg_0]
0x180040a4e  jz      loc_1800408B9
0x180040a54  jmp     short loc_180040A61
0x180040a56  mov     ecx, 6
0x180040a5b  call    cs:__imp_GdiSetLastError
0x180040a61  xor     eax, eax
0x180040a63  jmp     loc_1800409CB
0x180040a68  mov     eax, [rdi+8]
0x180040a6b  test    al, 4
0x180040a6d  jz      loc_18004096B
0x180040a73  and     eax, 0FFFFFFFDh
0x180040a76  mov     [rdi+8], eax
0x180040a79  jmp     loc_18004096B
0x180040a7e  mov     r9d, r14d
0x180040a81  jmp     loc_1800408FD
0x180040a86  mov     ecx, 8
0x180040a8b  jmp     short loc_180040A5B
0x180040a8d  mov     r9d, r14d
0x180040a90  jmp     loc_180040883
```
