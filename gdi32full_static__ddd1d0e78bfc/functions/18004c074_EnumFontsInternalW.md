# EnumFontsInternalW

- ea: `0x18004c074`
- end: `0x18004c309`
- name: `EnumFontsInternalW`
- size: `661`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004be60`
- `0x18004be90`
- `0x18004bf1c`
- `0x18004c020`

## callees

- `0x18004c074`
- `0x18004c310`
- `0x18004c52c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c285`
- `GDI32!GdiSetLastError` at `0x18004c2c9`
- `GDI32!GdiSetLastError` at `0x18004c2c9`
- `ntdll!RtlFreeHeap` at `0x18004c21b`
- `ntdll!RtlFreeHeap` at `0x18004c2a5`
- `ntdll!RtlFreeHeap` at `0x18004c21b`
- `ntdll!RtlFreeHeap` at `0x18004c2a5`
- `ntdll!RtlAllocateHeap` at `0x18004c11c`
- `ntdll!RtlAllocateHeap` at `0x18004c11c`
- `USER32!GetAppCompatFlags` at `0x18004c09f`
- `USER32!GetAppCompatFlags` at `0x18004c09f`
- `win32u!NtGdiEnumFonts` at `0x18004c0f1`
- `win32u!NtGdiEnumFonts` at `0x18004c177`
- `win32u!NtGdiEnumFonts` at `0x18004c0f1`
- `win32u!NtGdiEnumFonts` at `0x18004c177`

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
0x18004c074  mov     rax, rsp
0x18004c077  mov     [rax+20h], r9
0x18004c07b  mov     [rax+8], rcx
0x18004c07f  push    rbx
0x18004c080  push    rbp
0x18004c081  push    rsi
0x18004c082  push    rdi
0x18004c083  push    r13
0x18004c085  push    r14
0x18004c087  push    r15
0x18004c089  sub     rsp, 40h
0x18004c08d  mov     rbx, rcx
0x18004c090  xor     r14d, r14d
0x18004c093  xor     ecx, ecx
0x18004c095  mov     [rax+10h], r14d
0x18004c099  mov     ebp, r8d
0x18004c09c  mov     rsi, rdx
0x18004c09f  call    cs:__imp_GetAppCompatFlags
0x18004c0a6  nop     dword ptr [rax+rax+00h]
0x18004c0ab  mov     r15d, eax
0x18004c0ae  test    rsi, rsi
0x18004c0b1  jz      loc_18004C301
0x18004c0b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c0bb  inc     r8
0x18004c0be  cmp     [rsi+r8*2], r14w
0x18004c0c3  jnz     short loc_18004C0BB
0x18004c0c5  lea     r9d, [r8+1]
0x18004c0c9  mov     edx, [rsp+78h+arg_28]
0x18004c0d0  lea     rax, [rsp+78h+Size]
0x18004c0d8  mov     [rsp+78h+var_40], r14
0x18004c0dd  mov     r8d, r15d
0x18004c0e0  mov     [rsp+78h+var_48], rax
0x18004c0e5  mov     rcx, rbx
0x18004c0e8  mov     [rsp+78h+var_50], ebp
0x18004c0ec  mov     [rsp+78h+var_58], rsi
0x18004c0f1  call    cs:__imp_NtGdiEnumFonts
0x18004c0f8  nop     dword ptr [rax+rax+00h]
0x18004c0fd  test    eax, eax
0x18004c0ff  jz      loc_18004C2C4
0x18004c105  mov     rcx, gs:60h
0x18004c10e  xor     edx, edx; Flags
0x18004c110  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18004c118  mov     rcx, [rcx+30h]; HeapHandle
0x18004c11c  call    cs:__imp_RtlAllocateHeap
0x18004c123  nop     dword ptr [rax+rax+00h]
0x18004c128  mov     rdi, rax
0x18004c12b  test    rax, rax
0x18004c12e  jz      loc_18004C2FA
0x18004c134  test    rsi, rsi
0x18004c137  jz      loc_18004C2F2
0x18004c13d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c141  inc     rax
0x18004c144  cmp     [rsi+rax*2], r14w
0x18004c149  jnz     short loc_18004C141
0x18004c14b  lea     r9d, [rax+1]
0x18004c14f  mov     edx, [rsp+78h+arg_28]
0x18004c156  lea     rax, [rsp+78h+Size]
0x18004c15e  mov     [rsp+78h+var_40], rdi
0x18004c163  mov     r8d, r15d
0x18004c166  mov     [rsp+78h+var_48], rax
0x18004c16b  mov     rcx, rbx
0x18004c16e  mov     [rsp+78h+var_50], ebp
0x18004c172  mov     [rsp+78h+var_58], rsi
0x18004c177  call    cs:__imp_NtGdiEnumFonts
0x18004c17e  nop     dword ptr [rax+rax+00h]
0x18004c183  test    eax, eax
0x18004c185  jz      loc_18004C285
0x18004c18b  mov     ebp, dword ptr [rsp+78h+Size]
0x18004c192  mov     r14, rdi
0x18004c195  add     rbp, rdi
0x18004c198  cmp     rdi, rbp
0x18004c19b  jnb     loc_18004C27E
0x18004c1a1  mov     r13d, [rsp+78h+arg_30]
0x18004c1a9  and     r15d, 2000h
0x18004c1b0  jmp     short loc_18004C1BA
0x18004c1b2  mov     rbx, [rsp+78h+arg_0]
0x18004c1ba  test    r15d, r15d
0x18004c1bd  jnz     loc_18004C2DC
0x18004c1c3  test    rsi, rsi
0x18004c1c6  jnz     short loc_18004C239
0x18004c1c8  mov     r9, [rsp+78h+arg_20]
0x18004c1d0  test    r13b, 1
0x18004c1d4  jz      loc_18004C269
0x18004c1da  mov     edx, [rdi+4]
0x18004c1dd  lea     rcx, [rdi+0Ch]
0x18004c1e1  mov     r8d, [rdi+8]
0x18004c1e5  add     rdx, 8
0x18004c1e9  mov     rax, [rsp+78h+arg_18]
0x18004c1f1  add     rdx, rdi
0x18004c1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1f9  mov     ebx, eax
0x18004c1fb  test    eax, eax
0x18004c1fd  jz      short loc_18004C209
0x18004c1ff  mov     eax, [rdi]
0x18004c201  add     rdi, rax
0x18004c204  cmp     rdi, rbp
0x18004c207  jb      short loc_18004C1B2
0x18004c209  mov     rcx, gs:60h
0x18004c212  mov     r8, r14; P
0x18004c215  xor     edx, edx; Flags
0x18004c217  mov     rcx, [rcx+30h]; HeapHandle
0x18004c21b  call    cs:__imp_RtlFreeHeap
0x18004c222  nop     dword ptr [rax+rax+00h]
0x18004c227  mov     eax, ebx
0x18004c229  add     rsp, 40h
0x18004c22d  pop     r15
0x18004c22f  pop     r14
0x18004c231  pop     r13
0x18004c233  pop     rdi
0x18004c234  pop     rsi
0x18004c235  pop     rbp
0x18004c236  pop     rbx
0x18004c237  retn
0x18004c239  mov     eax, [rdi+8]
0x18004c23c  test    eax, eax
0x18004c23e  jns     short loc_18004C1C8
0x18004c240  mov     r9, [rsp+78h+arg_20]
0x18004c248  btr     eax, 1Fh
0x18004c24c  mov     rdx, [rsp+78h+arg_18]
0x18004c254  mov     r8, rdi
0x18004c257  mov     rcx, rbx
0x18004c25a  mov     [rdi+8], eax
0x18004c25d  mov     [rsp+78h+var_50], r13d
0x18004c262  call    iScaleEnum
0x18004c267  jmp     short loc_18004C1F9
0x18004c269  mov     r8, [rsp+78h+arg_18]
0x18004c271  mov     rcx, rdi
0x18004c274  call    iAnsiCallback
0x18004c279  jmp     loc_18004C1F9
0x18004c27e  mov     ebx, 1
0x18004c283  jmp     short loc_18004C209
0x18004c285  call    cs:__imp_GetLastError
0x18004c28c  nop     dword ptr [rax+rax+00h]
0x18004c291  mov     rcx, gs:60h
0x18004c29a  mov     r8, rdi; P
0x18004c29d  xor     edx, edx; Flags
0x18004c29f  mov     ebx, eax
0x18004c2a1  mov     rcx, [rcx+30h]; HeapHandle
0x18004c2a5  call    cs:__imp_RtlFreeHeap
0x18004c2ac  nop     dword ptr [rax+rax+00h]
0x18004c2b1  cmp     ebx, 6Fh ; 'o'
0x18004c2b4  mov     rbx, [rsp+78h+arg_0]
0x18004c2bc  jz      loc_18004C105
0x18004c2c2  jmp     short loc_18004C2D5
0x18004c2c4  mov     ecx, 6
0x18004c2c9  call    cs:__imp_GdiSetLastError
0x18004c2d0  nop     dword ptr [rax+rax+00h]
0x18004c2d5  xor     eax, eax
0x18004c2d7  jmp     loc_18004C229
0x18004c2dc  mov     eax, [rdi+8]
0x18004c2df  test    al, 4
0x18004c2e1  jz      loc_18004C1C3
0x18004c2e7  and     eax, 0FFFFFFFDh
0x18004c2ea  mov     [rdi+8], eax
0x18004c2ed  jmp     loc_18004C1C3
0x18004c2f2  mov     r9d, r14d
0x18004c2f5  jmp     loc_18004C14F
0x18004c2fa  mov     ecx, 8
0x18004c2ff  jmp     short loc_18004C2C9
0x18004c301  mov     r9d, r14d
0x18004c304  jmp     loc_18004C0C9
```
