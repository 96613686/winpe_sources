# CMyUpdateList::UpdateAll(void)

- ea: `0x180010aac`
- end: `0x180010d3a`
- name: `?UpdateAll@CMyUpdateList@@QEAAXXZ`
- size: `654`
- prototype: `void __fastcall(CMyUpdateList *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004a40`
- `0x180004d50`
- `0x18000a0c0`
- `0x18000a220`
- `0x18000a430`
- `0x18000cad0`
- `0x18000cb00`
- `0x18000cc10`
- `0x18000d830`
- `0x1800168f8`

## callees

- `0x180010aac`
- `0x180019010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180010b94`
- `KERNEL32!SetEvent` at `0x180010b94`

## pseudocode

```c
void __fastcall CMyUpdateList::UpdateAll(CMyUpdateList *this)
{
  HANDLE *v1; // rsi
  CMyUpdateList *v2; // rbp
  _BYTE *v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // r14
  int v6; // edi
  unsigned int v7; // r15d
  unsigned int v8; // r13d
  unsigned int v9; // r12d
  unsigned int v10; // ebp
  __int64 v11; // rbx
  _BYTE *v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-68h]
  unsigned int v14; // [rsp+24h] [rbp-64h]
  unsigned int v15; // [rsp+28h] [rbp-60h]
  unsigned int v16; // [rsp+2Ch] [rbp-5Ch]
  unsigned int v17; // [rsp+30h] [rbp-58h]
  int v19; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+18h]
  unsigned int v21; // [rsp+A8h] [rbp+20h]

  v1 = (HANDLE *)((char *)this + 16);
  v19 = 0;
  v2 = this;
  if ( this != (CMyUpdateList *)-16LL && *((_QWORD *)this + 4) )
  {
    v3 = (_BYTE *)*((_QWORD *)this + 19);
    if ( v3 )
      *v3 = 1;
    v4 = *((_QWORD *)this + 7);
    v5 = (_QWORD *)*((_QWORD *)this + 4);
    v6 = *(_DWORD *)(v4 + 4);
    v7 = *(_DWORD *)(v4 + 12);
    v8 = *(_DWORD *)(v4 + 28);
    v9 = *(_DWORD *)(v4 + 36);
    v13 = *(_DWORD *)(v4 + 8);
    v15 = *(_DWORD *)(v4 + 16);
    v21 = *(_DWORD *)(v4 + 20);
    v20 = *(_DWORD *)(v4 + 24);
    v14 = *(_DWORD *)(v4 + 32);
    v16 = *(_DWORD *)(v4 + 40);
    v17 = *(_DWORD *)(v4 + 44);
    *(_OWORD *)v4 = 0;
    *(_OWORD *)(v4 + 16) = 0;
    *(_OWORD *)(v4 + 32) = 0;
    if ( v5 )
    {
      v10 = v20;
      do
      {
        v11 = v5[1];
        v19 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 24LL))(v11, &v19);
        if ( v19 )
          SetEvent(v1[4]);
        if ( (v6 & 0x20000) != 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
        if ( (v6 & 1) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, 0, v8);
        if ( (v6 & 2) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v10, v8);
        if ( (v6 & 4) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v10, v8);
        if ( (v6 & 0x1000) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 64LL))(v11, v21);
        if ( (v6 & 0x10) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 56LL))(v11, 0, v9);
        if ( (v6 & 0x100) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(v11, 0, v7);
        if ( (v6 & 0x200) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(v11, v13, v7);
        if ( (v6 & 0x400) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(v11, v7, v7);
        if ( (v6 & 0x20) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 56LL))(v11, v14, v9);
        if ( (v6 & 0x40) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 56LL))(v11, v9, v9);
        if ( (v6 & 0x2000) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, v15);
        if ( (v6 & 0x4000) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 80LL))(v11, v16);
        if ( (v6 & 0x10000) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 88LL))(v11, v17);
        v5 = (_QWORD *)*v5;
      }
      while ( v5 );
      v2 = this;
    }
  }
  v12 = (_BYTE *)*((_QWORD *)v2 + 19);
  if ( v12 )
    *v12 = 0;
}

```

## disassembly

```asm
0x180010aac  mov     rax, rsp
0x180010aaf  mov     [rax+8], rcx
0x180010ab3  push    rbx
0x180010ab4  push    rbp
0x180010ab5  push    rsi
0x180010ab6  push    rdi
0x180010ab7  push    r12
0x180010ab9  push    r13
0x180010abb  push    r14
0x180010abd  push    r15
0x180010abf  sub     rsp, 48h
0x180010ac3  lea     rsi, [rcx+10h]
0x180010ac7  mov     dword ptr [rax+10h], 0
0x180010ace  mov     rbp, rcx
0x180010ad1  test    rsi, rsi
0x180010ad4  jz      loc_180010D1A
0x180010ada  cmp     qword ptr [rsi+10h], 0
0x180010adf  jz      loc_180010D1A
0x180010ae5  mov     rax, [rcx+98h]
0x180010aec  test    rax, rax
0x180010aef  jz      short loc_180010AF4
0x180010af1  mov     byte ptr [rax], 1
0x180010af4  mov     rax, [rsi+28h]
0x180010af8  xorps   xmm0, xmm0
0x180010afb  mov     r14, [rsi+10h]
0x180010aff  mov     ecx, [rax+8]
0x180010b02  mov     edi, [rax+4]
0x180010b05  mov     r15d, [rax+0Ch]
0x180010b09  mov     r13d, [rax+1Ch]
0x180010b0d  mov     r12d, [rax+24h]
0x180010b11  mov     [rsp+88h+var_68], ecx
0x180010b15  mov     ecx, [rax+10h]
0x180010b18  mov     [rsp+88h+var_60], ecx
0x180010b1c  mov     ecx, [rax+14h]
0x180010b1f  mov     [rsp+88h+arg_18], ecx
0x180010b26  mov     ecx, [rax+18h]
0x180010b29  mov     [rsp+88h+arg_10], ecx
0x180010b30  mov     ecx, [rax+20h]
0x180010b33  mov     [rsp+88h+var_64], ecx
0x180010b37  mov     ecx, [rax+28h]
0x180010b3a  mov     [rsp+88h+var_5C], ecx
0x180010b3e  mov     ecx, [rax+2Ch]
0x180010b41  mov     [rsp+88h+var_58], ecx
0x180010b45  movups  xmmword ptr [rax], xmm0
0x180010b48  movups  xmmword ptr [rax+10h], xmm0
0x180010b4c  movups  xmmword ptr [rax+20h], xmm0
0x180010b50  test    r14, r14
0x180010b53  jz      loc_180010D1A
0x180010b59  mov     ebp, [rsp+88h+arg_10]
0x180010b60  mov     rbx, [r14+8]
0x180010b64  lea     rdx, [rsp+88h+arg_8]
0x180010b6c  mov     [rsp+88h+arg_8], 0
0x180010b77  mov     rcx, rbx
0x180010b7a  mov     rax, [rbx]
0x180010b7d  mov     rax, [rax+18h]
0x180010b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b86  cmp     [rsp+88h+arg_8], 0
0x180010b8e  jz      short loc_180010B9A
0x180010b90  mov     rcx, [rsi+20h]; hEvent
0x180010b94  call    cs:__imp_SetEvent
0x180010b9a  bt      edi, 11h
0x180010b9e  jnb     short loc_180010BAF
0x180010ba0  mov     rax, [rbx]
0x180010ba3  mov     rcx, rbx
0x180010ba6  mov     rax, [rax+20h]
0x180010baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010baf  test    dil, 1
0x180010bb3  jz      short loc_180010BC9
0x180010bb5  mov     rax, [rbx]
0x180010bb8  mov     r8d, r13d
0x180010bbb  xor     edx, edx
0x180010bbd  mov     rcx, rbx
0x180010bc0  mov     rax, [rax+28h]
0x180010bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bc9  test    dil, 2
0x180010bcd  jz      short loc_180010BE3
0x180010bcf  mov     rax, [rbx]
0x180010bd2  mov     r8d, r13d
0x180010bd5  mov     edx, ebp
0x180010bd7  mov     rcx, rbx
0x180010bda  mov     rax, [rax+28h]
0x180010bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be3  test    dil, 4
0x180010be7  jz      short loc_180010BFD
0x180010be9  mov     rax, [rbx]
0x180010bec  mov     r8d, r13d
0x180010bef  mov     edx, ebp
0x180010bf1  mov     rcx, rbx
0x180010bf4  mov     rax, [rax+28h]
0x180010bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bfd  bt      edi, 0Ch
0x180010c01  jnb     short loc_180010C19
0x180010c03  mov     rax, [rbx]
0x180010c06  mov     rcx, rbx
0x180010c09  mov     edx, [rsp+88h+arg_18]
0x180010c10  mov     rax, [rax+40h]
0x180010c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c19  test    dil, 10h
0x180010c1d  jz      short loc_180010C33
0x180010c1f  mov     rax, [rbx]
0x180010c22  mov     r8d, r12d
0x180010c25  xor     edx, edx
0x180010c27  mov     rcx, rbx
0x180010c2a  mov     rax, [rax+38h]
0x180010c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c33  bt      edi, 8
0x180010c37  jnb     short loc_180010C4D
0x180010c39  mov     rax, [rbx]
0x180010c3c  mov     r8d, r15d
0x180010c3f  xor     edx, edx
0x180010c41  mov     rcx, rbx
0x180010c44  mov     rax, [rax+30h]
0x180010c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c4d  bt      edi, 9
0x180010c51  jnb     short loc_180010C69
0x180010c53  mov     rax, [rbx]
0x180010c56  mov     r8d, r15d
0x180010c59  mov     edx, [rsp+88h+var_68]
0x180010c5d  mov     rcx, rbx
0x180010c60  mov     rax, [rax+30h]
0x180010c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c69  bt      edi, 0Ah
0x180010c6d  jnb     short loc_180010C84
0x180010c6f  mov     rax, [rbx]
0x180010c72  mov     r8d, r15d
0x180010c75  mov     edx, r15d
0x180010c78  mov     rcx, rbx
0x180010c7b  mov     rax, [rax+30h]
0x180010c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c84  test    dil, 20h
0x180010c88  jz      short loc_180010CA0
0x180010c8a  mov     rax, [rbx]
0x180010c8d  mov     r8d, r12d
0x180010c90  mov     edx, [rsp+88h+var_64]
0x180010c94  mov     rcx, rbx
0x180010c97  mov     rax, [rax+38h]
0x180010c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ca0  test    dil, 40h
0x180010ca4  jz      short loc_180010CBB
0x180010ca6  mov     rax, [rbx]
0x180010ca9  mov     r8d, r12d
0x180010cac  mov     edx, r12d
0x180010caf  mov     rcx, rbx
0x180010cb2  mov     rax, [rax+38h]
0x180010cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cbb  bt      edi, 0Dh
0x180010cbf  jnb     short loc_180010CD4
0x180010cc1  mov     rax, [rbx]
0x180010cc4  mov     rcx, rbx
0x180010cc7  mov     edx, [rsp+88h+var_60]
0x180010ccb  mov     rax, [rax+48h]
0x180010ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd4  bt      edi, 0Eh
0x180010cd8  jnb     short loc_180010CED
0x180010cda  mov     rax, [rbx]
0x180010cdd  mov     rcx, rbx
0x180010ce0  mov     edx, [rsp+88h+var_5C]
0x180010ce4  mov     rax, [rax+50h]
0x180010ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ced  bt      edi, 10h
0x180010cf1  jnb     short loc_180010D06
0x180010cf3  mov     rax, [rbx]
0x180010cf6  mov     rcx, rbx
0x180010cf9  mov     edx, [rsp+88h+var_58]
0x180010cfd  mov     rax, [rax+58h]
0x180010d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d06  mov     r14, [r14]
0x180010d09  test    r14, r14
0x180010d0c  jnz     loc_180010B60
0x180010d12  mov     rbp, [rsp+88h+arg_0]
0x180010d1a  mov     rax, [rbp+98h]
0x180010d21  test    rax, rax
0x180010d24  jz      short loc_180010D29
0x180010d26  mov     byte ptr [rax], 0
0x180010d29  add     rsp, 48h
0x180010d2d  pop     r15
0x180010d2f  pop     r14
0x180010d31  pop     r13
0x180010d33  pop     r12
0x180010d35  pop     rdi
0x180010d36  pop     rsi
0x180010d37  pop     rbp
0x180010d38  pop     rbx
0x180010d39  retn
```
