# Hashtable::_remove(Object *)

- ea: `0x18001e400`
- end: `0x18001e8e3`
- name: `?_remove@Hashtable@@IEAAPEAUIUnknown@@PEAVObject@@@Z`
- size: `1251`
- prototype: `struct IUnknown *__fastcall(Hashtable *__hidden this, struct Object *)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18001fa80`
- `0x18003b600`
- `0x180043db0`
- `0x18006e160`
- `0x1800ab5ac`
- `0x1800c34d0`
- `0x1800fc228`
- `0x1800fcf00`
- `0x1800fd16c`

## callees

- `0x18001e400`
- `0x18001ecd0`
- `0x18001fec0`
- `0x18003d92c`
- `0x18005e9e8`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18001e78e`
- `msvcrt!_resetstkoflw` at `0x18001e85a`
- `msvcrt!_resetstkoflw` at `0x18001e78e`
- `msvcrt!_resetstkoflw` at `0x18001e85a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e7e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e8ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e7e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e8ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e77c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e848`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e77c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e848`

## pseudocode

```c
struct IUnknown *__fastcall Hashtable::_remove(Hashtable *this, struct Object *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned int v8; // r15d
  unsigned int v9; // r12d
  int v10; // r14d
  _QWORD *v11; // rsi
  unsigned int v12; // r13d
  __int64 v13; // rcx
  __int64 v14; // rcx
  struct Object *v15; // r14
  struct IUnknown *v16; // r15
  _QWORD *v17; // r12
  struct IUnknown *v18; // rsi
  struct Object *v19; // r13
  struct IUnknown **v20; // r13
  struct IUnknown *v21; // rsi
  struct IUnknown *v22; // r13
  int v23; // esi
  __int64 v24; // r12
  struct IUnknown *v26; // [rsp+38h] [rbp-70h] BYREF
  struct IUnknown *v27; // [rsp+40h] [rbp-68h] BYREF
  int v28; // [rsp+48h] [rbp-60h]
  int v29; // [rsp+4Ch] [rbp-5Ch]
  __int64 v30; // [rsp+50h] [rbp-58h]
  __int64 v31; // [rsp+58h] [rbp-50h]
  __int64 v32; // [rsp+60h] [rbp-48h]
  unsigned int v33; // [rsp+C8h] [rbp+20h]
  unsigned int v34; // [rsp+C8h] [rbp+20h]

  v4 = *((_QWORD *)this + 7);
  v32 = v4;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  }
  v5 = (*(__int64 (__fastcall **)(struct Object *))(*(_QWORD *)a2 + 64LL))(a2);
  v6 = v5;
  v33 = v5;
  v7 = (v5 & 0x7FFFFFFF) % *((_DWORD *)this + 8);
  v8 = v7;
  v29 = v7;
  v9 = -1;
  v28 = -1;
  v10 = 0;
  v11 = 0;
  while ( !v10 )
  {
    v11 = (_QWORD *)(*((_QWORD *)this + 5) + 24LL * v8);
    if ( *((_DWORD *)v11 + 5) )
    {
      if ( *((_DWORD *)v11 + 4) == (_DWORD)v6
        && (*(unsigned __int8 (__fastcall **)(_QWORD, struct Object *))(*(_QWORD *)*v11 + 72LL))(*v11, a2) )
      {
        v10 = 1;
      }
      else if ( *((_DWORD *)v11 + 5) == -1 )
      {
        v10 = 3;
      }
      else
      {
        v9 = v8;
        v28 = v8;
        v8 = *((_DWORD *)v11 + 5);
        v29 = v8;
      }
    }
    else
    {
      v10 = 2;
    }
    v6 = v33;
  }
  if ( v10 == 1 )
  {
    v12 = *((_DWORD *)v11 + 5);
    v34 = v12;
    v30 = v11[1];
    v31 = v30;
    if ( *((_BYTE *)this + 17) )
    {
      v13 = *v11;
      if ( *v11 )
      {
        *v11 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 16LL))(v13, v7, v6);
      }
    }
    else
    {
      *v11 = 0;
    }
    if ( *((_BYTE *)this + 16) )
    {
      v14 = v11[1];
      if ( v14 )
      {
        v11[1] = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(v14, v7, v6);
      }
    }
    else
    {
      v11[1] = 0;
    }
    *((_DWORD *)v11 + 5) = 0;
    --*((_DWORD *)this + 5);
    v7 = 0xFFFFFFFFLL;
    if ( v9 != -1 )
      *(_DWORD *)(*((_QWORD *)this + 5) + 24LL * v9 + 20) = -1;
    if ( *((_DWORD *)this + 9) <= v8 )
      *((_DWORD *)this + 9) = v8 + 1;
    v15 = 0;
    v26 = 0;
    v16 = 0;
    v27 = 0;
    while ( v12 != -1 )
    {
      v17 = (_QWORD *)(*((_QWORD *)this + 5) + 24LL * v12);
      v18 = (struct IUnknown *)*v17;
      if ( *((_BYTE *)this + 17) )
      {
        v19 = v15;
        if ( v18 )
          ((void (__fastcall *)(_QWORD, __int64, __int64))v18->lpVtbl->AddRef)(*v17, 0xFFFFFFFFLL, v6);
        v15 = (struct Object *)v18;
        v26 = v18;
        if ( v19 )
          (*(void (__fastcall **)(struct Object *, __int64, __int64))(*(_QWORD *)v19 + 16LL))(v19, v7, v6);
      }
      else
      {
        v15 = (struct Object *)*v17;
        v26 = (struct IUnknown *)*v17;
      }
      v20 = (struct IUnknown **)(v17 + 1);
      v21 = (struct IUnknown *)v17[1];
      if ( *((_BYTE *)this + 16) )
      {
        v22 = v16;
        if ( v21 )
          ((void (__fastcall *)(_QWORD, __int64, __int64))v21->lpVtbl->AddRef)(v17[1], v7, v6);
        v16 = v21;
        v27 = v21;
        if ( v22 )
          ((void (__fastcall *)(struct IUnknown *, __int64, __int64))v22->lpVtbl->Release)(v22, v7, v6);
        v20 = (struct IUnknown **)(v17 + 1);
      }
      else
      {
        v16 = (struct IUnknown *)v17[1];
        v27 = v16;
      }
      v23 = *((_DWORD *)v17 + 4);
      if ( *((_DWORD *)this + 9) <= v34 )
        *((_DWORD *)this + 9) = v34 + 1;
      v34 = *((_DWORD *)v17 + 5);
      if ( *((_BYTE *)this + 17) )
        release((struct IUnknown **)v17);
      else
        *v17 = 0;
      if ( *((_BYTE *)this + 16) )
        release(v20);
      else
        *v20 = 0;
      *((_DWORD *)v17 + 5) = 0;
      --*((_DWORD *)this + 5);
      Hashtable::__set(this, v15, v16, v23, 0);
      v12 = v34;
      v7 = 0xFFFFFFFFLL;
    }
    if ( *((_BYTE *)this + 17) )
      release(&v26);
    if ( *((_BYTE *)this + 16) )
      release(&v27);
    v24 = v30;
  }
  else
  {
    v24 = 0;
    v31 = 0;
  }
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, v7, v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return (struct IUnknown *)v24;
}

```

## disassembly

```asm
0x18001e400  mov     [rsp+arg_0], rcx
0x18001e405  push    rbx
0x18001e406  push    rsi
0x18001e407  push    rdi
0x18001e408  push    r12
0x18001e40a  push    r13
0x18001e40c  push    r14
0x18001e40e  push    r15
0x18001e410  sub     rsp, 70h
0x18001e414  mov     r13, rdx
0x18001e417  mov     rdi, rcx
0x18001e41a  mov     rbx, [rcx+38h]
0x18001e41e  mov     [rsp+0A8h+var_48], rbx
0x18001e423  test    rbx, rbx
0x18001e426  jz      short loc_18001E447
0x18001e428  mov     rax, [rbx]
0x18001e42b  mov     rcx, rbx
0x18001e42e  mov     rax, [rax+8]
0x18001e432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e437  mov     rax, [rbx]
0x18001e43a  mov     rcx, rbx
0x18001e43d  mov     rax, [rax+18h]
0x18001e441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e446  nop
0x18001e447  mov     [rsp+0A8h+var_74], 0
0x18001e44f  mov     [rsp+0A8h+arg_10], 0
0x18001e45a  mov     rax, [r13+0]
0x18001e45e  mov     rcx, r13
0x18001e461  mov     rax, [rax+40h]
0x18001e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46a  mov     r8d, eax
0x18001e46d  mov     [rsp+0A8h+arg_18], eax
0x18001e474  btr     eax, 1Fh
0x18001e478  xor     edx, edx
0x18001e47a  div     dword ptr [rdi+20h]
0x18001e47d  mov     r15d, edx
0x18001e480  mov     [rsp+0A8h+var_5C], edx
0x18001e484  or      r12d, 0FFFFFFFFh
0x18001e488  mov     [rsp+0A8h+var_60], r12d
0x18001e48d  xor     r14d, r14d
0x18001e490  mov     [rsp+0A8h+var_78], r14d
0x18001e495  xor     esi, esi
0x18001e497  test    r14d, r14d
0x18001e49a  jnz     short loc_18001E50B
0x18001e49c  mov     eax, r15d
0x18001e49f  lea     rcx, [rax+rax*2]
0x18001e4a3  mov     rax, [rdi+28h]
0x18001e4a7  lea     rsi, [rax+rcx*8]
0x18001e4ab  cmp     [rsi+14h], r14d
0x18001e4af  jnz     short loc_18001E4B9
0x18001e4b1  mov     r14d, 2
0x18001e4b7  jmp     short loc_18001E4E9
0x18001e4b9  cmp     [rsi+10h], r8d
0x18001e4bd  jnz     short loc_18001E4DD
0x18001e4bf  mov     rcx, [rsi]
0x18001e4c2  mov     rax, [rcx]
0x18001e4c5  mov     rdx, r13
0x18001e4c8  mov     rax, [rax+48h]
0x18001e4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d1  test    al, al
0x18001e4d3  jz      short loc_18001E4DD
0x18001e4d5  mov     r14d, 1
0x18001e4db  jmp     short loc_18001E4E9
0x18001e4dd  cmp     dword ptr [rsi+14h], 0FFFFFFFFh
0x18001e4e1  jnz     short loc_18001E4F0
0x18001e4e3  mov     r14d, 3
0x18001e4e9  mov     [rsp+0A8h+var_78], r14d
0x18001e4ee  jmp     short loc_18001E501
0x18001e4f0  mov     r12d, r15d
0x18001e4f3  mov     [rsp+0A8h+var_60], r15d
0x18001e4f8  mov     r15d, [rsi+14h]
0x18001e4fc  mov     [rsp+0A8h+var_5C], r15d
0x18001e501  mov     r8d, [rsp+0A8h+arg_18]
0x18001e509  jmp     short loc_18001E497
0x18001e50b  lea     rax, [rsp+0A8h+var_74]
0x18001e510  mov     [rax], r15d
0x18001e513  lea     rax, [rsp+0A8h+arg_10]
0x18001e51b  mov     [rax], r12d
0x18001e51e  cmp     r14d, 1
0x18001e522  jnz     loc_18001E835
0x18001e528  mov     r13d, [rsi+14h]
0x18001e52c  mov     [rsp+0A8h+arg_18], r13d
0x18001e534  mov     r12, [rsi+8]
0x18001e538  mov     [rsp+0A8h+var_58], r12
0x18001e53d  mov     [rsp+0A8h+var_50], r12
0x18001e542  cmp     byte ptr [rdi+11h], 0
0x18001e546  jz      short loc_18001E565
0x18001e548  mov     rcx, [rsi]
0x18001e54b  test    rcx, rcx
0x18001e54e  jz      short loc_18001E56C
0x18001e550  mov     qword ptr [rsi], 0
0x18001e557  mov     rax, [rcx]
0x18001e55a  mov     rax, [rax+10h]
0x18001e55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e563  jmp     short loc_18001E56C
0x18001e565  mov     qword ptr [rsi], 0
0x18001e56c  cmp     byte ptr [rdi+10h], 0
0x18001e570  jz      short loc_18001E591
0x18001e572  mov     rcx, [rsi+8]
0x18001e576  test    rcx, rcx
0x18001e579  jz      short loc_18001E599
0x18001e57b  mov     qword ptr [rsi+8], 0
0x18001e583  mov     rax, [rcx]
0x18001e586  mov     rax, [rax+10h]
0x18001e58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e58f  jmp     short loc_18001E599
0x18001e591  mov     qword ptr [rsi+8], 0
0x18001e599  mov     dword ptr [rsi+14h], 0
0x18001e5a0  mov     eax, [rdi+14h]
0x18001e5a3  dec     eax
0x18001e5a5  mov     [rdi+14h], eax
0x18001e5a8  or      edx, 0FFFFFFFFh
0x18001e5ab  cmp     [rsp+0A8h+arg_10], edx
0x18001e5b2  jz      short loc_18001E5C7
0x18001e5b4  mov     eax, [rsp+0A8h+arg_10]
0x18001e5bb  lea     rcx, [rax+rax*2]
0x18001e5bf  mov     rax, [rdi+28h]
0x18001e5c3  mov     [rax+rcx*8+14h], edx
0x18001e5c7  mov     eax, [rsp+0A8h+var_74]
0x18001e5cb  cmp     [rdi+24h], eax
0x18001e5ce  ja      short loc_18001E5D5
0x18001e5d0  inc     eax
0x18001e5d2  mov     [rdi+24h], eax
0x18001e5d5  xor     r14d, r14d
0x18001e5d8  mov     [rsp+0A8h+var_70], r14
0x18001e5dd  xor     r15d, r15d
0x18001e5e0  mov     [rsp+0A8h+var_68], r15
0x18001e5e5  cmp     r13d, edx
0x18001e5e8  jz      loc_18001E71B
0x18001e5ee  mov     eax, r13d
0x18001e5f1  lea     rcx, [rax+rax*2]
0x18001e5f5  mov     rax, [rdi+28h]
0x18001e5f9  lea     r12, [rax+rcx*8]
0x18001e5fd  mov     rsi, [r12]
0x18001e601  cmp     byte ptr [rdi+11h], 0
0x18001e605  jz      short loc_18001E63D
0x18001e607  mov     r13, r14
0x18001e60a  test    rsi, rsi
0x18001e60d  jz      short loc_18001E61E
0x18001e60f  mov     rax, [rsi]
0x18001e612  mov     rcx, rsi
0x18001e615  mov     rax, [rax+8]
0x18001e619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e61e  mov     r14, rsi
0x18001e621  mov     [rsp+0A8h+var_70], rsi
0x18001e626  test    r13, r13
0x18001e629  jz      short loc_18001E645
0x18001e62b  mov     rax, [r13+0]
0x18001e62f  mov     rcx, r13
0x18001e632  mov     rax, [rax+10h]
0x18001e636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e63b  jmp     short loc_18001E645
0x18001e63d  mov     r14, rsi
0x18001e640  mov     [rsp+0A8h+var_70], rsi
0x18001e645  lea     r13, [r12+8]
0x18001e64a  mov     rsi, [r13+0]
0x18001e64e  cmp     byte ptr [rdi+10h], 0
0x18001e652  jz      short loc_18001E6BF
0x18001e654  mov     r13, r15
0x18001e657  test    rsi, rsi
0x18001e65a  jz      short loc_18001E66B
0x18001e65c  mov     rax, [rsi]
0x18001e65f  mov     rcx, rsi
0x18001e662  mov     rax, [rax+8]
0x18001e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e66b  mov     r15, rsi
0x18001e66e  mov     [rsp+0A8h+var_68], rsi
0x18001e673  test    r13, r13
0x18001e676  jz      short loc_18001E688
0x18001e678  mov     rax, [r13+0]
0x18001e67c  mov     rcx, r13
0x18001e67f  mov     rax, [rax+10h]
0x18001e683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e688  lea     r13, [r12+8]
0x18001e68d  mov     esi, [r12+10h]
0x18001e692  mov     eax, [rsp+0A8h+arg_18]
0x18001e699  cmp     [rdi+24h], eax
0x18001e69c  ja      short loc_18001E6A3
0x18001e69e  inc     eax
0x18001e6a0  mov     [rdi+24h], eax
0x18001e6a3  mov     eax, [r12+14h]
0x18001e6a8  mov     [rsp+0A8h+arg_18], eax
0x18001e6af  cmp     byte ptr [rdi+11h], 0
0x18001e6b3  jz      short loc_18001E6C9
0x18001e6b5  mov     rcx, r12; struct IUnknown **
0x18001e6b8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e6bd  jmp     short loc_18001E6D1
0x18001e6bf  mov     r15, rsi
0x18001e6c2  mov     [rsp+0A8h+var_68], rsi
0x18001e6c7  jmp     short loc_18001E68D
0x18001e6c9  mov     qword ptr [r12], 0
0x18001e6d1  cmp     byte ptr [rdi+10h], 0
0x18001e6d5  jz      short loc_18001E6E1
0x18001e6d7  mov     rcx, r13; struct IUnknown **
0x18001e6da  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e6df  jmp     short loc_18001E6E9
0x18001e6e1  mov     qword ptr [r13+0], 0
0x18001e6e9  mov     dword ptr [r12+14h], 0
0x18001e6f2  dec     dword ptr [rdi+14h]
0x18001e6f5  mov     [rsp+0A8h+var_88], 0; bool
0x18001e6fa  mov     r9d, esi; int
0x18001e6fd  mov     r8, r15; struct IUnknown *
0x18001e700  mov     rdx, r14; struct Object *
0x18001e703  mov     rcx, rdi; this
0x18001e706  call    ?__set@Hashtable@@IEAAPEAUIUnknown@@PEAVObject@@PEAU2@H_N@Z; Hashtable::__set(Object *,IUnknown *,int,bool)
0x18001e70b  mov     r13d, [rsp+0A8h+arg_18]
0x18001e713  or      edx, 0FFFFFFFFh
0x18001e716  jmp     loc_18001E5E5
0x18001e71b  cmp     byte ptr [rdi+11h], 0
0x18001e71f  jz      short loc_18001E72B
0x18001e721  lea     rcx, [rsp+0A8h+var_70]; struct IUnknown **
0x18001e726  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e72b  cmp     byte ptr [rdi+10h], 0
0x18001e72f  jz      short loc_18001E73B
0x18001e731  lea     rcx, [rsp+0A8h+var_68]; struct IUnknown **
0x18001e736  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e73b  mov     r12, [rsp+0A8h+var_58]
0x18001e740  test    rbx, rbx
0x18001e743  jz      short loc_18001E763
0x18001e745  mov     rcx, [rbx]
0x18001e748  mov     rax, [rcx+20h]
0x18001e74c  mov     rcx, rbx
0x18001e74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e754  mov     rcx, [rbx]
0x18001e757  mov     rax, [rcx+10h]
0x18001e75b  mov     rcx, rbx
0x18001e75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e763  mov     rax, r12
0x18001e766  add     rsp, 70h
0x18001e76a  pop     r15
0x18001e76c  pop     r14
0x18001e76e  pop     r13
0x18001e770  pop     r12
0x18001e772  pop     rdi
0x18001e773  pop     rsi
0x18001e774  pop     rbx
0x18001e775  retn
0x18001e776  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001e77c  call    cs:__imp_TlsGetValue
0x18001e782  mov     rbx, rax
0x18001e785  cmp     dword ptr [rax+54h], 0C00000FDh
0x18001e78c  jnz     short loc_18001E807
0x18001e78e  call    cs:__imp__resetstkoflw
0x18001e794  test    eax, eax
0x18001e796  jnz     short loc_18001E7E9
0x18001e798  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18001e79f  test    rcx, rcx
0x18001e7a2  jz      short loc_18001E7B6
0x18001e7a4  cmp     [rcx+50h], rbx
0x18001e7a8  jnz     short loc_18001E7B6
0x18001e7aa  mov     rax, [rcx]
0x18001e7ad  mov     rax, [rax+20h]
0x18001e7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7b6  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18001e7bd  test    rcx, rcx
0x18001e7c0  jz      short loc_18001E7D4
0x18001e7c2  cmp     [rcx+50h], rbx
0x18001e7c6  jnz     short loc_18001E7D4
0x18001e7c8  mov     rax, [rcx]
0x18001e7cb  mov     rax, [rax+20h]
0x18001e7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7d4  xor     r9d, r9d; lpArguments
0x18001e7d7  xor     r8d, r8d; nNumberOfArguments
0x18001e7da  xor     edx, edx; dwExceptionFlags
0x18001e7dc  mov     ecx, 0C00000FDh; dwExceptionCode
0x18001e7e1  call    cs:__imp_RaiseException
0x18001e7e7  jmp     short loc_18001E807
0x18001e7e9  mov     rax, [rbx+60h]
0x18001e7ed  mov     [rbx+68h], rax
0x18001e7f1  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18001e7f8  mov     [rbx+60h], rax
0x18001e7fc  mov     dword ptr [rbx+54h], 800703E9h
0x18001e803  mov     byte ptr [rbx+78h], 0
0x18001e807  mov     rbx, [rsp+0A8h+arg_0]
0x18001e80f  cmp     byte ptr [rbx+11h], 0
0x18001e813  jz      short loc_18001E81F
0x18001e815  lea     rcx, [rsp+0A8h+var_70]; struct IUnknown **
0x18001e81a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e81f  cmp     byte ptr [rbx+10h], 0
0x18001e823  jz      short loc_18001E82F
0x18001e825  lea     rcx, [rsp+0A8h+var_68]; struct IUnknown **
0x18001e82a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18001e82f  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x18001e835  xor     r12d, r12d
0x18001e838  mov     [rsp+0A8h+var_50], r12
0x18001e83d  jmp     loc_18001E740
0x18001e842  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001e848  call    cs:__imp_TlsGetValue
0x18001e84e  mov     rbx, rax
0x18001e851  cmp     dword ptr [rax+54h], 0C00000FDh
0x18001e858  jnz     short loc_18001E8D3
0x18001e85a  call    cs:__imp__resetstkoflw
0x18001e860  test    eax, eax
0x18001e862  jnz     short loc_18001E8B5
0x18001e864  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18001e86b  test    rcx, rcx
0x18001e86e  jz      short loc_18001E882
0x18001e870  cmp     [rcx+50h], rbx
0x18001e874  jnz     short loc_18001E882
0x18001e876  mov     rax, [rcx]
  ... truncated ...
```
