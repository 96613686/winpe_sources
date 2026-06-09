# WriteException(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_EXCEPTION_INFO * const)

- ea: `0x18000c54c`
- end: `0x18000c674`
- name: `?WriteException@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@QEAU_EXCEPTION_INFO@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _EXCEPTION_INFO *const)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000bcbc`
- `0x18000c54c`
- `0x18000e660`

## pseudocode

```c
__int64 __fastcall WriteException(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _EXCEPTION_INFO *const a3)
{
  __int64 result; // rax
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  void *v9; // r8
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  unsigned int v17; // r9d
  unsigned int v18[4]; // [rsp+30h] [rbp-89h] BYREF
  int v19; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v20[4]; // [rsp+44h] [rbp-75h] BYREF
  __int128 v21; // [rsp+48h] [rbp-71h]
  __int128 v22; // [rsp+58h] [rbp-61h]
  __int128 v23; // [rsp+68h] [rbp-51h]
  __int128 v24; // [rsp+78h] [rbp-41h]
  __int128 v25; // [rsp+88h] [rbp-31h]
  __int128 v26; // [rsp+98h] [rbp-21h]
  __int128 v27; // [rsp+A8h] [rbp-11h]
  __int128 v28; // [rsp+B8h] [rbp-1h]
  __int128 v29; // [rsp+C8h] [rbp+Fh]
  __int64 v30; // [rsp+D8h] [rbp+1Fh]
  __int64 v31; // [rsp+E0h] [rbp+27h]

  v18[0] = 0;
  if ( !a3 )
    return 0;
  memset_0(v20, 0, 0xA4u);
  v7 = *(_OWORD *)((char *)a3 + 4);
  v8 = *(_OWORD *)((char *)a3 + 20);
  v9 = (void *)*((_QWORD *)a3 + 20);
  v19 = *(_DWORD *)a3;
  v30 = *(_QWORD *)((char *)a3 + 148);
  v21 = v7;
  v10 = *(_OWORD *)((char *)a3 + 36);
  v22 = v8;
  v11 = *(_OWORD *)((char *)a3 + 52);
  v23 = v10;
  v12 = *(_OWORD *)((char *)a3 + 68);
  v24 = v11;
  v13 = *(_OWORD *)((char *)a3 + 84);
  v25 = v12;
  v14 = *(_OWORD *)((char *)a3 + 100);
  v26 = v13;
  v15 = *(_OWORD *)((char *)a3 + 116);
  v27 = v14;
  v16 = *(_OWORD *)((char *)a3 + 132);
  v28 = v15;
  v29 = v16;
  if ( v9 && (v17 = *((_DWORD *)a3 + 42)) != 0 )
  {
    result = WriteOther(a1, a2, v9, v17, v18);
    if ( (_DWORD)result )
      return result;
    LODWORD(v31) = *((_DWORD *)a3 + 42);
    HIDWORD(v31) = v18[0];
  }
  else
  {
    v31 = 0;
  }
  return WriteAtOffset(a1, *((_DWORD *)a2 + 9), &v19, *((_DWORD *)a2 + 10));
}

```

## disassembly

```asm
0x18000c54c  mov     [rsp-8+arg_18], rbx
0x18000c551  push    rbp
0x18000c552  push    rsi
0x18000c553  push    rdi
0x18000c554  lea     rbp, [rsp-47h]
0x18000c559  sub     rsp, 100h
0x18000c560  mov     rax, cs:__security_cookie
0x18000c567  xor     rax, rsp
0x18000c56a  mov     [rbp+57h+var_20], rax
0x18000c56e  mov     [rsp+110h+var_E0], 0
0x18000c576  mov     rbx, r8
0x18000c579  mov     rdi, rdx
0x18000c57c  mov     rsi, rcx
0x18000c57f  test    r8, r8
0x18000c582  jnz     short loc_18000C58B
0x18000c584  xor     eax, eax
0x18000c586  jmp     loc_18000C655
0x18000c58b  xor     edx, edx; Val
0x18000c58d  lea     rcx, [rbp+57h+var_CC]; void *
0x18000c591  mov     r8d, 0A4h; Size
0x18000c597  call    memset_0
0x18000c59c  movups  xmm0, xmmword ptr [rbx+4]
0x18000c5a0  mov     eax, [rbx]
0x18000c5a2  movups  xmm1, xmmword ptr [rbx+14h]
0x18000c5a6  mov     r8, [rbx+0A0h]; void *
0x18000c5ad  mov     [rbp+57h+var_D0], eax
0x18000c5b0  mov     rax, [rbx+94h]
0x18000c5b7  mov     [rbp+57h+var_38], rax
0x18000c5bb  movups  [rbp+57h+var_C8], xmm0
0x18000c5bf  movups  xmm0, xmmword ptr [rbx+24h]
0x18000c5c3  movups  [rbp+57h+var_B8], xmm1
0x18000c5c7  movups  xmm1, xmmword ptr [rbx+34h]
0x18000c5cb  movups  [rbp+57h+var_A8], xmm0
0x18000c5cf  movups  xmm0, xmmword ptr [rbx+44h]
0x18000c5d3  movups  [rbp+57h+var_98], xmm1
0x18000c5d7  movups  xmm1, xmmword ptr [rbx+54h]
0x18000c5db  movups  [rbp+57h+var_88], xmm0
0x18000c5df  movups  xmm0, xmmword ptr [rbx+64h]
0x18000c5e3  movups  [rbp+57h+var_78], xmm1
0x18000c5e7  movups  xmm1, xmmword ptr [rbx+74h]
0x18000c5eb  movups  [rbp+57h+var_68], xmm0
0x18000c5ef  movups  xmm0, xmmword ptr [rbx+84h]
0x18000c5f6  movups  [rbp+57h+var_58], xmm1
0x18000c5fa  movups  [rbp+57h+var_48], xmm0
0x18000c5fe  test    r8, r8
0x18000c601  jz      short loc_18000C63A
0x18000c603  mov     r9d, [rbx+0A8h]; unsigned int
0x18000c60a  test    r9d, r9d
0x18000c60d  jz      short loc_18000C63A
0x18000c60f  lea     rax, [rsp+110h+var_E0]
0x18000c614  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c617  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000c61a  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18000c61f  call    ?WriteOther@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAXKPEAK@Z; WriteOther(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,void *,ulong,ulong *)
0x18000c624  test    eax, eax
0x18000c626  jnz     short loc_18000C655
0x18000c628  mov     eax, [rbx+0A8h]
0x18000c62e  mov     dword ptr [rbp+57h+var_30], eax
0x18000c631  mov     eax, [rsp+110h+var_E0]
0x18000c635  mov     dword ptr [rbp+57h+var_30+4], eax
0x18000c638  jmp     short loc_18000C642
0x18000c63a  mov     [rbp+57h+var_30], 0
0x18000c642  mov     r9d, [rdi+28h]; unsigned int
0x18000c646  lea     r8, [rbp+57h+var_D0]; void *
0x18000c64a  mov     edx, [rdi+24h]; unsigned int
0x18000c64d  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000c650  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000c655  mov     rcx, [rbp+57h+var_20]
0x18000c659  xor     rcx, rsp; StackCookie
0x18000c65c  call    __security_check_cookie
0x18000c661  mov     rbx, [rsp+110h+arg_18]
0x18000c669  add     rsp, 100h
0x18000c670  pop     rdi
0x18000c671  pop     rsi
0x18000c672  pop     rbp
0x18000c673  retn
```
