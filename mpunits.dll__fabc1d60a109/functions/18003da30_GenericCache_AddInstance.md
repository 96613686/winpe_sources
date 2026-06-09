# GenericCache_AddInstance

- ea: `0x18003da30`
- end: `0x18003db83`
- name: `GenericCache_AddInstance`
- size: `339`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003e4f0`
- `0x18003e590`
- `0x18003e980`
- `0x18003eb90`
- `0x18003ece0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18003da30`
- `0x18003f270`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18003da50`
- `msvcrt!malloc` at `0x18003da50`
- `msvcrt!free` at `0x18003db68`
- `msvcrt!free` at `0x18003db68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dae7`

## string_xrefs

- `0x18003dad8`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall GenericCache_AddInstance(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        void (__fastcall *a5)(__int64))
{
  _QWORD *v9; // rax
  void *v10; // rdi
  __int64 v12; // r8
  unsigned __int16 v13; // dx
  unsigned __int16 *v14; // r9
  unsigned __int16 v15; // cx
  __int64 v16; // rbx
  HMODULE ModuleHandleA; // rax

  v9 = malloc(0x40u);
  v10 = v9;
  if ( !v9 )
    return 27;
  v9[4] = a2;
  v12 = 2166136261LL;
  v13 = *a2;
  if ( *a2 )
  {
    v14 = a2;
    do
    {
      v15 = v13 + 32;
      ++v14;
      if ( (unsigned __int16)(v13 - 65) > 0x19u )
        v15 = v13;
      v13 = *v14;
      v12 = 16777619 * (v12 ^ v15);
    }
    while ( *v14 );
  }
  v9[7] = a5;
  v9[3] = v12;
  v9[6] = a4;
  v9[5] = a3;
  if ( !(unsigned int)ThreadSafeHashMap_Insert(a1, (__int64)v9) )
    return 0;
  v16 = *(_QWORD *)(a1 + 128);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2133, v16);
  MI_ReportErrorDetails_ForCustomError(11, (int)L"MI", 0, 0);
  if ( a3 && *(_QWORD *)a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
  if ( a5 )
    a5(a4);
  free(v10);
  return 11;
}

```

## disassembly

```asm
0x18003da30  push    rbx
0x18003da32  push    rbp
0x18003da33  push    rsi
0x18003da34  push    rdi
0x18003da35  push    r12
0x18003da37  push    r14
0x18003da39  push    r15
0x18003da3b  sub     rsp, 40h
0x18003da3f  mov     rbx, rcx
0x18003da42  mov     r15, r9
0x18003da45  mov     ecx, 40h ; '@'; Size
0x18003da4a  mov     r14, r8
0x18003da4d  mov     rsi, rdx
0x18003da50  call    cs:__imp_malloc
0x18003da56  xor     r12d, r12d
0x18003da59  mov     rdi, rax
0x18003da5c  test    rax, rax
0x18003da5f  jnz     short loc_18003DA69
0x18003da61  lea     eax, [rdi+1Bh]
0x18003da64  jmp     loc_18003DB74
0x18003da69  mov     [rax+20h], rsi
0x18003da6d  mov     r8d, 811C9DC5h
0x18003da73  movzx   edx, word ptr [rsi]
0x18003da76  test    dx, dx
0x18003da79  jz      short loc_18003DAA6
0x18003da7b  mov     r9, rsi
0x18003da7e  lea     eax, [rdx-41h]
0x18003da81  cmp     ax, 19h
0x18003da85  lea     ecx, [rdx+20h]
0x18003da88  lea     r9, [r9+2]
0x18003da8c  cmova   cx, dx
0x18003da90  movzx   edx, word ptr [r9]
0x18003da94  movzx   eax, cx
0x18003da97  xor     rax, r8
0x18003da9a  imul    r8, rax, 1000193h
0x18003daa1  test    dx, dx
0x18003daa4  jnz     short loc_18003DA7E
0x18003daa6  mov     rbp, [rsp+78h+arg_20]
0x18003daae  mov     rdx, rdi
0x18003dab1  mov     rcx, rbx
0x18003dab4  mov     [rdi+38h], rbp
0x18003dab8  mov     [rdi+18h], r8
0x18003dabc  mov     [rdi+30h], r15
0x18003dac0  mov     [rdi+28h], r14
0x18003dac4  call    ThreadSafeHashMap_Insert
0x18003dac9  test    eax, eax
0x18003dacb  jz      loc_18003DB72
0x18003dad1  mov     rbx, [rbx+80h]
0x18003dad8  lea     rcx, ModuleName; "mpunits.dll"
0x18003dadf  xorps   xmm0, xmm0
0x18003dae2  movups  [rsp+78h+var_48], xmm0
0x18003dae7  call    cs:__imp_GetModuleHandleA
0x18003daed  mov     r9, rsi
0x18003daf0  mov     r8, rbx
0x18003daf3  mov     rcx, rax
0x18003daf6  mov     edx, 855h
0x18003dafb  call    _Intlstr_FormatString_FormatMessage
0x18003db00  mov     qword ptr [rsp+78h+var_48], rax
0x18003db05  lea     r9, [rsp+78h+var_48]
0x18003db0a  mov     byte ptr [rsp+78h+var_48+8], 1
0x18003db0f  lea     rdx, aMi; "MI"
0x18003db16  movaps  xmm0, [rsp+78h+var_48]
0x18003db1b  mov     r8d, 14h
0x18003db21  mov     [rsp+78h+var_50], r12; __int64
0x18003db26  movdqa  [rsp+78h+var_48], xmm0
0x18003db2c  mov     [rsp+78h+var_58], r12; __int64
0x18003db31  lea     ebx, [r8-9]
0x18003db35  mov     ecx, ebx; int
0x18003db37  call    MI_ReportErrorDetails_ForCustomError
0x18003db3c  test    r14, r14
0x18003db3f  jz      short loc_18003DB55
0x18003db41  mov     rax, [r14]
0x18003db44  test    rax, rax
0x18003db47  jz      short loc_18003DB55
0x18003db49  mov     rax, [rax+10h]
0x18003db4d  mov     rcx, r14
0x18003db50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db55  test    rbp, rbp
0x18003db58  jz      short loc_18003DB65
0x18003db5a  mov     rcx, r15
0x18003db5d  mov     rax, rbp
0x18003db60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db65  mov     rcx, rdi; Block
0x18003db68  call    cs:__imp_free
0x18003db6e  mov     eax, ebx
0x18003db70  jmp     short loc_18003DB74
0x18003db72  xor     eax, eax
0x18003db74  add     rsp, 40h
0x18003db78  pop     r15
0x18003db7a  pop     r14
0x18003db7c  pop     r12
0x18003db7e  pop     rdi
0x18003db7f  pop     rsi
0x18003db80  pop     rbp
0x18003db81  pop     rbx
0x18003db82  retn
```
