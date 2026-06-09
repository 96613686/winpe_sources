# WriteUnloadedModuleList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000f180`
- end: `0x18000f2b0`
- name: `?WriteUnloadedModuleList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x18000bcbc`
- `0x18000e798`
- `0x18000f180`
- `0x18001951c`

## pseudocode

```c
__int64 __fastcall WriteUnloadedModuleList(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  _QWORD **v3; // rdi
  unsigned int v6; // edx
  int v7; // eax
  __int64 result; // rax
  _QWORD *v9; // rsi
  unsigned __int16 *v10; // r15
  unsigned int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // [rsp+20h] [rbp-40h] BYREF
  _DWORD v14[4]; // [rsp+28h] [rbp-38h] BYREF
  __int128 v15; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]

  v3 = (_QWORD **)((char *)a3 + 136);
  v16 = 0;
  v15 = 0;
  v13 = 0;
  if ( *v3 != v3 )
  {
    v6 = *((_DWORD *)a2 + 23);
    v7 = *((_DWORD *)a3 + 24);
    v14[0] = 12;
    v14[1] = 24;
    v14[2] = v7;
    result = WriteAtOffset(a1, v6, v14, 0xCu);
    if ( (_DWORD)result )
      return result;
    *((_DWORD *)a2 + 23) += 12;
    v9 = *v3;
    while ( v9 != v3 )
    {
      if ( (unsigned int)GenCheckCancel(a1) )
        return 2147943623LL;
      v10 = (unsigned __int16 *)(v9 - 93);
      v9 = (_QWORD *)*v9;
      result = WriteStringToPool(a1, a2, v10 + 10, &v13);
      if ( (_DWORD)result )
        return result;
      v11 = *((_DWORD *)a2 + 23);
      v12 = *((_DWORD *)a2 + 21) + *((_DWORD *)a2 + 22);
      v15 = *(_OWORD *)v10;
      LODWORD(v16) = *((_DWORD *)v10 + 4);
      HIDWORD(v16) = v13;
      if ( v11 + 24 > v12 )
        return 2147942487LL;
      result = WriteAtOffset(a1, v11, &v15, 0x18u);
      if ( (_DWORD)result )
        return result;
      *((_DWORD *)a2 + 23) += 24;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f180  mov     [rsp-28h+arg_18], rbx
0x18000f185  push    rbp
0x18000f186  push    rsi
0x18000f187  push    rdi
0x18000f188  push    r14
0x18000f18a  push    r15
0x18000f18c  mov     rbp, rsp
0x18000f18f  sub     rsp, 60h
0x18000f193  mov     rax, cs:__security_cookie
0x18000f19a  xor     rax, rsp
0x18000f19d  mov     [rbp+var_10], rax
0x18000f1a1  xor     eax, eax
0x18000f1a3  lea     rdi, [r8+88h]
0x18000f1aa  xorps   xmm0, xmm0
0x18000f1ad  mov     rbx, rdx
0x18000f1b0  mov     r14, rcx
0x18000f1b3  mov     [rbp+var_18], rax
0x18000f1b7  movups  [rbp+var_28], xmm0
0x18000f1bb  mov     [rbp+var_40], eax
0x18000f1be  cmp     [rdi], rdi
0x18000f1c1  jz      loc_18000F280
0x18000f1c7  mov     edx, [rdx+5Ch]; unsigned int
0x18000f1ca  lea     esi, [rax+0Ch]
0x18000f1cd  mov     eax, [r8+60h]
0x18000f1d1  mov     r9d, esi; unsigned int
0x18000f1d4  lea     r8, [rbp+var_38]; void *
0x18000f1d8  mov     [rbp+var_38], esi
0x18000f1db  mov     [rbp+var_34], 18h
0x18000f1e2  mov     [rbp+var_30], eax
0x18000f1e5  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000f1ea  test    eax, eax
0x18000f1ec  jnz     loc_18000F282
0x18000f1f2  add     [rbx+5Ch], esi
0x18000f1f5  mov     rsi, [rdi]
0x18000f1f8  jmp     short loc_18000F277
0x18000f1fa  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000f1fd  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000f202  test    eax, eax
0x18000f204  jnz     loc_18000F2A9
0x18000f20a  lea     r15, [rsi-2E8h]
0x18000f211  mov     rdx, rbx; struct _MINIDUMP_STREAM_INFO *
0x18000f214  mov     rsi, [rsi]
0x18000f217  lea     r8, [r15+14h]; unsigned __int16 *
0x18000f21b  lea     r9, [rbp+var_40]; unsigned int *
0x18000f21f  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000f222  call    ?WriteStringToPool@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAGPEAK@Z; WriteStringToPool(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ushort *,ulong *)
0x18000f227  test    eax, eax
0x18000f229  jnz     short loc_18000F282
0x18000f22b  mov     rax, [r15]
0x18000f22e  mov     edx, [rbx+5Ch]; unsigned int
0x18000f231  mov     ecx, [rbx+58h]
0x18000f234  add     ecx, [rbx+54h]
0x18000f237  mov     qword ptr [rbp+var_28], rax
0x18000f23b  mov     eax, [r15+8]
0x18000f23f  mov     dword ptr [rbp+var_28+8], eax
0x18000f242  mov     eax, [r15+0Ch]
0x18000f246  mov     dword ptr [rbp+var_28+0Ch], eax
0x18000f249  mov     eax, [r15+10h]
0x18000f24d  mov     dword ptr [rbp+var_18], eax
0x18000f250  mov     eax, [rbp+var_40]
0x18000f253  mov     dword ptr [rbp+var_18+4], eax
0x18000f256  lea     eax, [rdx+18h]
0x18000f259  cmp     eax, ecx
0x18000f25b  ja      short loc_18000F2A2
0x18000f25d  mov     r9d, 18h; unsigned int
0x18000f263  lea     r8, [rbp+var_28]; void *
0x18000f267  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18000f26a  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000f26f  test    eax, eax
0x18000f271  jnz     short loc_18000F282
0x18000f273  add     dword ptr [rbx+5Ch], 18h
0x18000f277  cmp     rsi, rdi
0x18000f27a  jnz     loc_18000F1FA
0x18000f280  xor     eax, eax
0x18000f282  mov     rcx, [rbp+var_10]
0x18000f286  xor     rcx, rsp; StackCookie
0x18000f289  call    __security_check_cookie
0x18000f28e  mov     rbx, [rsp+60h+arg_18]
0x18000f296  add     rsp, 60h
0x18000f29a  pop     r15
0x18000f29c  pop     r14
0x18000f29e  pop     rdi
0x18000f29f  pop     rsi
0x18000f2a0  pop     rbp
0x18000f2a1  retn
0x18000f2a2  mov     eax, 80070057h
0x18000f2a7  jmp     short loc_18000F282
0x18000f2a9  mov     eax, 800704C7h
0x18000f2ae  jmp     short loc_18000F282
```
