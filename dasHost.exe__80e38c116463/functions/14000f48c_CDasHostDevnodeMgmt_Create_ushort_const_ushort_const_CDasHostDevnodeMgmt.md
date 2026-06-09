# CDasHostDevnodeMgmt::Create(ushort const *,ushort const *,CDasHostDevnodeMgmt * *)

- ea: `0x14000f48c`
- end: `0x14000f6b7`
- name: `?Create@CDasHostDevnodeMgmt@@SAJPEBG0PEAPEAV1@@Z`
- size: `555`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000dbe0`

## callees

- `0x14000190c`
- `0x1400077d8`
- `0x14000f48c`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000f61d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000f627`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000f61d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000f627`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f4f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f583`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f4f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f66b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f684`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f66b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f4e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f676`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f4e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f676`

## pseudocode

```c
__int64 __fastcall CDasHostDevnodeMgmt::Create(unsigned __int16 *a1, unsigned __int16 *a2, RTL_SRWLOCK **a3)
{
  __int64 v4; // r9
  const unsigned __int16 *v5; // rax
  int v6; // edi
  __int64 v7; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r12
  unsigned __int16 *v11; // r14
  RTL_SRWLOCK *v12; // r15
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdi
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  RTL_SRWLOCK *v18; // rsi
  HANDLE v19; // rax
  HANDLE v20; // rax
  RTL_SRWLOCK *v22; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v23; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v26; // [rsp+88h] [rbp+20h]

  if ( !a1 )
    return (unsigned int)-2147024809;
  v4 = 768;
  v5 = a1;
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
    {
      v6 = -2147024809;
      v7 = 0;
      goto LABEL_7;
    }
  }
  v6 = 0;
  v7 = 768 - v4;
LABEL_7:
  if ( v6 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v7 + 2);
    v10 = v9;
    v23 = v9;
    if ( !v9 )
      return (unsigned int)-2147024882;
    v11 = 0;
    v26 = 0;
    v12 = 0;
    v6 = StringCchCopyW(v9, v7 + 1, a1);
    if ( v6 < 0 )
      goto LABEL_19;
    if ( a2 )
    {
      v13 = 184;
      v14 = a2;
      while ( *v14 )
      {
        ++v14;
        if ( !--v13 )
        {
          v6 = -2147024809;
          goto LABEL_19;
        }
      }
      v15 = 184 - v13;
      v16 = GetProcessHeap();
      v17 = (unsigned __int16 *)HeapAlloc(v16, 0, 2 * v15 + 2);
      v11 = v17;
      v26 = v17;
      if ( !v17 )
      {
        v6 = -2147024882;
LABEL_19:
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v10);
        if ( v11 )
        {
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v11);
        }
        if ( v12 )
          (*((void (__fastcall **)(RTL_SRWLOCK *))v12->Ptr + 2))(v12);
        return (unsigned int)v6;
      }
      v6 = StringCchCopyW(v17, v15 + 1, a2);
      if ( v6 < 0 )
        goto LABEL_19;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v18 = (RTL_SRWLOCK *)operator new(0x88u);
      v18->Ptr = &CDasHostDevnodeMgmt::`vftable';
      v18[1].Ptr = 0;
      v18[2].Ptr = 0;
      v18[3].Ptr = 0;
      LODWORD(v18[4].Ptr) = 1;
      v18[5].Ptr = 0;
      v18[6].Ptr = 0;
      v18[7].Ptr = 0;
      LODWORD(v18[13].Ptr) = 0;
      v18[14].Ptr = 0;
      LODWORD(v18[16].Ptr) = 1;
      v18[9].Ptr = &v18[8];
      v18[8].Ptr = &v18[8];
      v18[11].Ptr = &v18[10];
      v18[10].Ptr = &v18[10];
      InitializeSRWLock(v18 + 12);
      InitializeSRWLock(v18 + 15);
      v22 = v18;
      v18[1].Ptr = v10;
      v18[2].Ptr = v11;
      *a3 = v18;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v6 = -2147024882;
        v10 = v23;
        v11 = v26;
        v12 = v22;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000F647);
        goto LABEL_19;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000f48c  mov     [rsp+arg_10], r8
0x14000f491  mov     [rsp+arg_8], rdx
0x14000f496  push    rbx
0x14000f497  push    rsi
0x14000f498  push    rdi
0x14000f499  push    r12
0x14000f49b  push    r13
0x14000f49d  push    r14
0x14000f49f  push    r15
0x14000f4a1  sub     rsp, 30h
0x14000f4a5  mov     r13, rcx
0x14000f4a8  xor     ebx, ebx
0x14000f4aa  test    rcx, rcx
0x14000f4ad  jz      loc_14000F6A0
0x14000f4b3  mov     esi, 300h
0x14000f4b8  mov     r9d, esi
0x14000f4bb  mov     rax, rcx
0x14000f4be  cmp     [rax], bx
0x14000f4c1  jz      short loc_14000F4D7
0x14000f4c3  add     rax, 2
0x14000f4c7  sub     r9, 1
0x14000f4cb  jnz     short loc_14000F4BE
0x14000f4cd  mov     edi, 80070057h
0x14000f4d2  mov     rsi, rbx
0x14000f4d5  jmp     short loc_14000F4DC
0x14000f4d7  mov     edi, ebx
0x14000f4d9  sub     rsi, r9
0x14000f4dc  test    edi, edi
0x14000f4de  js      loc_14000F6A5
0x14000f4e4  call    cs:__imp_GetProcessHeap
0x14000f4ea  lea     r8, ds:2[rsi*2]; dwBytes
0x14000f4f2  xor     edx, edx; dwFlags
0x14000f4f4  mov     rcx, rax; hHeap
0x14000f4f7  call    cs:__imp_HeapAlloc
0x14000f4fd  mov     r12, rax
0x14000f500  mov     [rsp+68h+var_40], rax
0x14000f505  test    rax, rax
0x14000f508  jnz     short loc_14000F514
0x14000f50a  mov     edi, 8007000Eh
0x14000f50f  jmp     loc_14000F6A5
0x14000f514  mov     r14, rbx
0x14000f517  mov     [rsp+68h+arg_18], rbx
0x14000f51f  mov     r15, rbx
0x14000f522  mov     [rsp+68h+var_48], rbx
0x14000f527  lea     rdx, [rsi+1]; unsigned __int64
0x14000f52b  mov     r8, r13; unsigned __int16 *
0x14000f52e  mov     rcx, r12; unsigned __int16 *
0x14000f531  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000f536  mov     edi, eax
0x14000f538  test    eax, eax
0x14000f53a  js      loc_14000F65D
0x14000f540  mov     rsi, [rsp+68h+arg_8]
0x14000f545  test    rsi, rsi
0x14000f548  jz      short loc_14000F5BC
0x14000f54a  mov     edi, 0B8h
0x14000f54f  mov     ecx, edi
0x14000f551  mov     rax, rsi
0x14000f554  cmp     [rax], bx
0x14000f557  jz      short loc_14000F56D
0x14000f559  add     rax, 2
0x14000f55d  sub     rcx, 1
0x14000f561  jnz     short loc_14000F554
0x14000f563  mov     edi, 80070057h
0x14000f568  jmp     loc_14000F65D
0x14000f56d  sub     rdi, rcx
0x14000f570  call    cs:__imp_GetProcessHeap
0x14000f576  lea     r8, ds:2[rdi*2]; dwBytes
0x14000f57e  xor     edx, edx; dwFlags
0x14000f580  mov     rcx, rax; hHeap
0x14000f583  call    cs:__imp_HeapAlloc
0x14000f589  mov     r14, rax
0x14000f58c  mov     [rsp+68h+arg_18], rax
0x14000f594  test    rax, rax
0x14000f597  jnz     short loc_14000F5A3
0x14000f599  mov     edi, 8007000Eh
0x14000f59e  jmp     loc_14000F65D
0x14000f5a3  lea     rdx, [rdi+1]; unsigned __int64
0x14000f5a7  mov     r8, rsi; unsigned __int16 *
0x14000f5aa  mov     rcx, rax; unsigned __int16 *
0x14000f5ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000f5b2  mov     edi, eax
0x14000f5b4  test    eax, eax
0x14000f5b6  js      loc_14000F65D
0x14000f5bc  mov     ecx, 88h; Size
0x14000f5c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f5c6  mov     rsi, rax
0x14000f5c9  lea     rax, ??_7CDasHostDevnodeMgmt@@6B@; const CDasHostDevnodeMgmt::`vftable'
0x14000f5d0  mov     [rsi], rax
0x14000f5d3  mov     [rsi+8], rbx
0x14000f5d7  mov     [rsi+10h], rbx
0x14000f5db  mov     [rsi+18h], rbx
0x14000f5df  mov     dword ptr [rsi+20h], 1
0x14000f5e6  mov     [rsi+28h], rbx
0x14000f5ea  mov     [rsi+30h], rbx
0x14000f5ee  mov     [rsi+38h], rbx
0x14000f5f2  mov     [rsi+68h], ebx
0x14000f5f5  mov     [rsi+70h], rbx
0x14000f5f9  mov     dword ptr [rsi+80h], 1
0x14000f603  lea     rax, [rsi+40h]
0x14000f607  mov     [rax+8], rax
0x14000f60b  mov     [rax], rax
0x14000f60e  lea     rax, [rsi+50h]
0x14000f612  mov     [rax+8], rax
0x14000f616  mov     [rax], rax
0x14000f619  lea     rcx, [rsi+60h]; SRWLock
0x14000f61d  call    cs:__imp_InitializeSRWLock
0x14000f623  lea     rcx, [rsi+78h]; SRWLock
0x14000f627  call    cs:__imp_InitializeSRWLock
0x14000f62d  mov     [rsp+68h+var_48], rsi
0x14000f632  mov     [rsi+8], r12
0x14000f636  mov     [rsi+10h], r14
0x14000f63a  mov     rax, [rsp+68h+arg_10]
0x14000f642  mov     [rax], rsi
0x14000f645  jmp     short loc_14000F6A5
0x14000f647  mov     edi, [rsp+68h+arg_0]
0x14000f64b  mov     r12, [rsp+68h+var_40]
0x14000f650  mov     r14, [rsp+68h+arg_18]
0x14000f658  mov     r15, [rsp+68h+var_48]
0x14000f65d  call    cs:__imp_GetProcessHeap
0x14000f663  mov     rcx, rax; hHeap
0x14000f666  mov     r8, r12; lpMem
0x14000f669  xor     edx, edx; dwFlags
0x14000f66b  call    cs:__imp_HeapFree
0x14000f671  test    r14, r14
0x14000f674  jz      short loc_14000F68A
0x14000f676  call    cs:__imp_GetProcessHeap
0x14000f67c  mov     rcx, rax; hHeap
0x14000f67f  mov     r8, r14; lpMem
0x14000f682  xor     edx, edx; dwFlags
0x14000f684  call    cs:__imp_HeapFree
0x14000f68a  test    r15, r15
0x14000f68d  jz      short loc_14000F6A5
0x14000f68f  mov     rax, [r15]
0x14000f692  mov     rcx, r15
0x14000f695  mov     rax, [rax+10h]
0x14000f699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f69e  jmp     short loc_14000F6A5
0x14000f6a0  mov     edi, 80070057h
0x14000f6a5  mov     eax, edi
0x14000f6a7  add     rsp, 30h
0x14000f6ab  pop     r15
0x14000f6ad  pop     r14
0x14000f6af  pop     r13
0x14000f6b1  pop     r12
0x14000f6b3  pop     rdi
0x14000f6b4  pop     rsi
0x14000f6b5  pop     rbx
0x14000f6b6  retn
```
