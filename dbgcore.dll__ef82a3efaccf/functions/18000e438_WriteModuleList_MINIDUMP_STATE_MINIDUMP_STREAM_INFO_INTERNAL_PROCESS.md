# WriteModuleList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000e438`
- end: `0x18000e658`
- name: `?WriteModuleList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000bcbc`
- `0x18000e438`
- `0x18000e660`
- `0x18000e798`
- `0x18001951c`

## pseudocode

```c
__int64 __fastcall WriteModuleList(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  unsigned int v6; // edx
  __int64 result; // rax
  _QWORD *v8; // r12
  _QWORD *v9; // rbx
  _QWORD *v10; // r13
  void *v11; // r8
  unsigned int v12; // r9d
  unsigned int v13; // r15d
  void *v14; // r8
  int *v15; // r14
  unsigned int v16; // r9d
  unsigned int v17; // ecx
  unsigned int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-61h] BYREF
  int v23; // [rsp+3Ch] [rbp-5Dh] BYREF
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  int v25; // [rsp+48h] [rbp-51h]
  int v26; // [rsp+4Ch] [rbp-4Dh]
  int v27; // [rsp+50h] [rbp-49h]
  unsigned int v28; // [rsp+54h] [rbp-45h]
  __int128 v29; // [rsp+58h] [rbp-41h]
  __int128 v30; // [rsp+68h] [rbp-31h]
  __int128 v31; // [rsp+78h] [rbp-21h]
  int v32; // [rsp+88h] [rbp-11h]
  int v33; // [rsp+8Ch] [rbp-Dh]
  unsigned int v34; // [rsp+90h] [rbp-9h]
  int v35; // [rsp+94h] [rbp-5h]
  unsigned int v36; // [rsp+98h] [rbp-1h]
  __int64 v37; // [rsp+9Ch] [rbp+3h]
  __int64 v38; // [rsp+A4h] [rbp+Bh]

  memset_0(&v24, 0, 0x6Cu);
  v6 = *((_DWORD *)a2 + 20);
  v23 = *((_DWORD *)a3 + 22);
  v22 = 0;
  v20 = 0;
  v21 = 0;
  result = WriteAtOffset(a1, v6, &v23, 4u);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)a2 + 20) += 4;
    v8 = (_QWORD *)((char *)a3 + 120);
    v9 = (_QWORD *)*v8;
    if ( (_QWORD *)*v8 == v8 )
    {
      return 0;
    }
    else
    {
      while ( !(unsigned int)GenCheckCancel(a1) )
      {
        v10 = (_QWORD *)*v9;
        if ( (*(_BYTE *)(v9 - 1) & 1) != 0 )
        {
          result = WriteStringToPool(a1, a2, (unsigned __int16 *)*(v9 - 2), &v22);
          if ( (_DWORD)result )
            return result;
          if ( (*(_BYTE *)(v9 - 1) & 8) != 0 && (v11 = (void *)*(v9 - 8)) != 0 && (v12 = *((_DWORD *)v9 - 14)) != 0 )
          {
            result = WriteOther(a1, a2, v11, v12, &v20);
            if ( (_DWORD)result )
              return result;
            v13 = v20;
          }
          else
          {
            v13 = 0;
            v20 = 0;
          }
          if ( (*(_BYTE *)(v9 - 1) & 4) != 0
            && (v14 = (void *)*(v9 - 6)) != 0
            && (v15 = (int *)(v9 - 5), (v16 = *((_DWORD *)v9 - 10)) != 0) )
          {
            result = WriteOther(a1, a2, v14, v16, &v21);
            if ( (_DWORD)result )
              return result;
            v17 = v21;
          }
          else
          {
            v17 = 0;
            v15 = (int *)(v9 - 5);
            v21 = 0;
          }
          v18 = *((_DWORD *)a2 + 20);
          v24 = *(v9 - 17);
          v25 = *((_DWORD *)v9 - 32);
          v26 = *((_DWORD *)v9 - 31);
          v27 = *((_DWORD *)v9 - 30);
          v29 = *(_OWORD *)((char *)v9 - 116);
          v30 = *(_OWORD *)((char *)v9 - 100);
          v31 = *(_OWORD *)((char *)v9 - 84);
          v32 = *((_DWORD *)v9 - 17);
          v34 = v13;
          v33 = *((_DWORD *)v9 - 14);
          v36 = v17;
          v19 = *((_DWORD *)a2 + 18) + *((_DWORD *)a2 + 19);
          v35 = *v15;
          v28 = v22;
          v37 = *((unsigned __int16 *)v9 + 8);
          v38 = 0;
          if ( v18 + 108 > v19 )
            return 2147942487LL;
          result = WriteAtOffset(a1, v18, &v24, 0x6Cu);
          if ( (_DWORD)result )
            return result;
          *((_DWORD *)a2 + 20) += 108;
        }
        v9 = v10;
        if ( v10 == v8 )
          return 0;
      }
      return 2147943623LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e438  mov     [rsp-8+arg_18], rbx
0x18000e43d  push    rbp
0x18000e43e  push    rsi
0x18000e43f  push    rdi
0x18000e440  push    r12
0x18000e442  push    r13
0x18000e444  push    r14
0x18000e446  push    r15
0x18000e448  lea     rbp, [rsp-27h]
0x18000e44d  sub     rsp, 0C0h
0x18000e454  mov     rax, cs:__security_cookie
0x18000e45b  xor     rax, rsp
0x18000e45e  mov     [rbp+57h+var_40], rax
0x18000e462  mov     rdi, rdx
0x18000e465  mov     r12, r8
0x18000e468  xor     edx, edx; Val
0x18000e46a  mov     rsi, rcx
0x18000e46d  lea     rcx, [rbp+57h+var_B0]; void *
0x18000e471  lea     r8d, [rdx+6Ch]; Size
0x18000e475  call    memset_0
0x18000e47a  mov     eax, [r12+58h]
0x18000e47f  lea     r8, [rbp+57h+var_B4]; void *
0x18000e483  mov     edx, [rdi+50h]; unsigned int
0x18000e486  mov     r9d, 4; unsigned int
0x18000e48c  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e48f  mov     [rbp+57h+var_B4], eax
0x18000e492  mov     [rbp+57h+var_B8], 0
0x18000e499  mov     [rbp+57h+var_C0], 0
0x18000e4a0  mov     [rbp+57h+var_BC], 0
0x18000e4a7  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000e4ac  test    eax, eax
0x18000e4ae  jnz     loc_18000E623
0x18000e4b4  add     dword ptr [rdi+50h], 4
0x18000e4b8  add     r12, 78h ; 'x'
0x18000e4bc  mov     rbx, [r12]
0x18000e4c0  cmp     rbx, r12
0x18000e4c3  jz      loc_18000E621
0x18000e4c9  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e4cc  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000e4d1  test    eax, eax
0x18000e4d3  jnz     loc_18000E651
0x18000e4d9  test    byte ptr [rbx-8], 1
0x18000e4dd  mov     r13, [rbx]
0x18000e4e0  jz      loc_18000E615
0x18000e4e6  mov     r8, [rbx-10h]; unsigned __int16 *
0x18000e4ea  lea     r9, [rbp+57h+var_B8]; unsigned int *
0x18000e4ee  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000e4f1  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e4f4  call    ?WriteStringToPool@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAGPEAK@Z; WriteStringToPool(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ushort *,ulong *)
0x18000e4f9  test    eax, eax
0x18000e4fb  jnz     loc_18000E623
0x18000e501  test    byte ptr [rbx-8], 8
0x18000e505  jz      short loc_18000E53B
0x18000e507  mov     r8, [rbx-40h]; void *
0x18000e50b  test    r8, r8
0x18000e50e  jz      short loc_18000E53B
0x18000e510  mov     r9d, [rbx-38h]; unsigned int
0x18000e514  test    r9d, r9d
0x18000e517  jz      short loc_18000E53B
0x18000e519  lea     rax, [rbp+57h+var_C0]
0x18000e51d  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000e520  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e523  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18000e528  call    ?WriteOther@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAXKPEAK@Z; WriteOther(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,void *,ulong,ulong *)
0x18000e52d  test    eax, eax
0x18000e52f  jnz     loc_18000E623
0x18000e535  mov     r15d, [rbp+57h+var_C0]
0x18000e539  jmp     short loc_18000E542
0x18000e53b  xor     r15d, r15d
0x18000e53e  mov     [rbp+57h+var_C0], r15d
0x18000e542  test    byte ptr [rbx-8], 4
0x18000e546  jz      short loc_18000E57E
0x18000e548  mov     r8, [rbx-30h]; void *
0x18000e54c  test    r8, r8
0x18000e54f  jz      short loc_18000E57E
0x18000e551  lea     r14, [rbx-28h]
0x18000e555  mov     r9d, [r14]; unsigned int
0x18000e558  test    r9d, r9d
0x18000e55b  jz      short loc_18000E57E
0x18000e55d  lea     rax, [rbp+57h+var_BC]
0x18000e561  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000e564  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e567  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18000e56c  call    ?WriteOther@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAXKPEAK@Z; WriteOther(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,void *,ulong,ulong *)
0x18000e571  test    eax, eax
0x18000e573  jnz     loc_18000E623
0x18000e579  mov     ecx, [rbp+57h+var_BC]
0x18000e57c  jmp     short loc_18000E587
0x18000e57e  xor     ecx, ecx
0x18000e580  lea     r14, [rbx-28h]
0x18000e584  mov     [rbp+57h+var_BC], ecx
0x18000e587  mov     rax, [rbx-88h]
0x18000e58e  mov     edx, [rdi+50h]; unsigned int
0x18000e591  mov     [rbp+57h+var_B0], rax
0x18000e595  mov     eax, [rbx-80h]
0x18000e598  mov     [rbp+57h+var_A8], eax
0x18000e59b  mov     eax, [rbx-7Ch]
0x18000e59e  mov     [rbp+57h+var_A4], eax
0x18000e5a1  mov     eax, [rbx-78h]
0x18000e5a4  mov     [rbp+57h+var_A0], eax
0x18000e5a7  movups  xmm0, xmmword ptr [rbx-74h]
0x18000e5ab  movups  [rbp+57h+var_98], xmm0
0x18000e5af  movups  xmm1, xmmword ptr [rbx-64h]
0x18000e5b3  movups  [rbp+57h+var_88], xmm1
0x18000e5b7  movups  xmm0, xmmword ptr [rbx-54h]
0x18000e5bb  movups  [rbp+57h+var_78], xmm0
0x18000e5bf  mov     eax, [rbx-44h]
0x18000e5c2  mov     [rbp+57h+var_68], eax
0x18000e5c5  mov     [rbp+57h+var_60], r15d
0x18000e5c9  mov     eax, [rbx-38h]
0x18000e5cc  mov     [rbp+57h+var_64], eax
0x18000e5cf  mov     [rbp+57h+var_58], ecx
0x18000e5d2  mov     eax, [r14]
0x18000e5d5  mov     ecx, [rdi+4Ch]
0x18000e5d8  add     ecx, [rdi+48h]
0x18000e5db  mov     [rbp+57h+var_5C], eax
0x18000e5de  mov     eax, [rbp+57h+var_B8]
0x18000e5e1  mov     [rbp+57h+var_9C], eax
0x18000e5e4  movzx   eax, word ptr [rbx+10h]
0x18000e5e8  mov     [rbp+57h+var_54], rax
0x18000e5ec  lea     eax, [rdx+6Ch]
0x18000e5ef  mov     [rbp+57h+var_4C], 0
0x18000e5f7  cmp     eax, ecx
0x18000e5f9  ja      short loc_18000E64A
0x18000e5fb  mov     r9d, 6Ch ; 'l'; unsigned int
0x18000e601  lea     r8, [rbp+57h+var_B0]; void *
0x18000e605  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000e608  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000e60d  test    eax, eax
0x18000e60f  jnz     short loc_18000E623
0x18000e611  add     dword ptr [rdi+50h], 6Ch ; 'l'
0x18000e615  mov     rbx, r13
0x18000e618  cmp     r13, r12
0x18000e61b  jnz     loc_18000E4C9
0x18000e621  xor     eax, eax
0x18000e623  mov     rcx, [rbp+57h+var_40]
0x18000e627  xor     rcx, rsp; StackCookie
0x18000e62a  call    __security_check_cookie
0x18000e62f  mov     rbx, [rsp+0F0h+arg_18]
0x18000e637  add     rsp, 0C0h
0x18000e63e  pop     r15
0x18000e640  pop     r14
0x18000e642  pop     r13
0x18000e644  pop     r12
0x18000e646  pop     rdi
0x18000e647  pop     rsi
0x18000e648  pop     rbp
0x18000e649  retn
0x18000e64a  mov     eax, 80070057h
0x18000e64f  jmp     short loc_18000E623
0x18000e651  mov     eax, 800704C7h
0x18000e656  jmp     short loc_18000E623
```
