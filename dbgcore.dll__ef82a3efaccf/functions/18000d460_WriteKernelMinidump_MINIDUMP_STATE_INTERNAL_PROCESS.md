# WriteKernelMinidump(_MINIDUMP_STATE *,_INTERNAL_PROCESS *)

- ea: `0x18000d460`
- end: `0x18000d600`
- name: `?WriteKernelMinidump@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `416`
- prototype: `void __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f8e8`

## callees

- `0x1800021f4`
- `0x18000d460`
- `0x180016b74`
- `0x18002c010`

## string_xrefs

- `0x18000d57d`: `Kernel minidump write failed, 0x%08x`

## pseudocode

```c
void __fastcall WriteKernelMinidump(struct _MINIDUMP_STATE *a1, struct _INTERNAL_PROCESS *a2)
{
  __int64 v4; // rcx
  unsigned int (__fastcall *v5)(__int64, _BYTE *, __int128 *); // rax
  unsigned int v6; // edx
  int v7; // edi
  _QWORD *v8; // rsi
  __int64 v9; // r9
  struct _INTERNAL_PROCESS *v10; // rdx
  struct _INTERNAL_PROCESS *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rcx
  void (__fastcall *v14)(__int64, _BYTE *, __int128 *); // rax
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+70h] [rbp-90h]
  _BYTE v19[12]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h]

  if ( *((_QWORD *)a1 + 8) )
  {
    memset_0(v19, 0, 0x520u);
    v4 = *((_QWORD *)a1 + 10);
    v20 = 7;
    v18 = 0;
    v5 = (unsigned int (__fastcall *)(__int64, _BYTE *, __int128 *))*((_QWORD *)a1 + 8);
    v15 = 0;
    v16 = 0;
    v17 = 0;
    if ( v5(v4, v19, &v15) )
    {
      if ( (_QWORD)v15 )
      {
        v6 = *((_DWORD *)a2 + 19);
        if ( v6 <= 0x1FFFFFFF )
        {
          v8 = AllocMemory(a1, 8 * v6);
          if ( v8 )
          {
            v9 = 0;
            v10 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 13);
            while ( v10 != (struct _INTERNAL_PROCESS *)((char *)a2 + 104) && (unsigned int)v9 < *((_DWORD *)a2 + 19) )
            {
              v11 = v10;
              v10 = *(struct _INTERNAL_PROCESS **)v10;
              if ( (*((_BYTE *)v11 - 8) & 1) != 0 )
              {
                v8[v9] = *((_QWORD *)v11 - 22);
                v9 = (unsigned int)(v9 + 1);
              }
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 2) + 440LL))(
                    *((_QWORD *)a1 + 2),
                    v15,
                    *((_QWORD *)a2 + 8));
            v7 = v12;
            if ( v12 )
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
                *((_QWORD *)a1 + 5),
                4,
                "Kernel minidump write failed, 0x%08x",
                v12);
            (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v8);
          }
          else
          {
            v7 = -2147024882;
          }
        }
        else
        {
          v7 = -2147024362;
        }
        memset_0(v19, 0, 0x520u);
        v13 = *((_QWORD *)a1 + 10);
        v20 = 8;
        v21 = v7;
        v18 = 0;
        v14 = (void (__fastcall *)(__int64, _BYTE *, __int128 *))*((_QWORD *)a1 + 8);
        v15 = 0;
        v16 = 0;
        v17 = 0;
        v14(v13, v19, &v15);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d460  push    rbp
0x18000d462  push    rbx
0x18000d463  push    rsi
0x18000d464  push    rdi
0x18000d465  lea     rbp, [rsp-4A8h]
0x18000d46d  sub     rsp, 5A8h
0x18000d474  cmp     qword ptr [rcx+40h], 0
0x18000d479  mov     rdi, rdx
0x18000d47c  mov     rbx, rcx
0x18000d47f  jz      loc_18000D5F4
0x18000d485  xor     edx, edx; Val
0x18000d487  lea     rcx, [rbp+4C0h+var_540]; void *
0x18000d48b  mov     r8d, 520h; Size
0x18000d491  call    memset_0
0x18000d496  mov     rcx, [rbx+50h]
0x18000d49a  lea     r8, [rsp+5C0h+var_580]
0x18000d49f  xorps   xmm0, xmm0
0x18000d4a2  mov     [rbp+4C0h+var_534], 7
0x18000d4a9  xor     eax, eax
0x18000d4ab  lea     rdx, [rbp+4C0h+var_540]
0x18000d4af  mov     [rsp+5C0h+var_550], eax
0x18000d4b3  mov     rax, [rbx+40h]
0x18000d4b7  movups  [rsp+5C0h+var_580], xmm0
0x18000d4bc  movups  [rsp+5C0h+var_570], xmm0
0x18000d4c1  movups  [rsp+5C0h+var_560], xmm0
0x18000d4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4cb  test    eax, eax
0x18000d4cd  jz      loc_18000D5F4
0x18000d4d3  cmp     qword ptr [rsp+5C0h+var_580], 0
0x18000d4d9  jz      loc_18000D5F4
0x18000d4df  mov     edx, [rdi+4Ch]
0x18000d4e2  cmp     edx, 1FFFFFFFh
0x18000d4e8  jbe     short loc_18000D4F4
0x18000d4ea  mov     edi, 80070216h
0x18000d4ef  jmp     loc_18000D5AB
0x18000d4f4  shl     edx, 3; unsigned int
0x18000d4f7  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000d4fa  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x18000d4ff  mov     rsi, rax
0x18000d502  test    rax, rax
0x18000d505  jnz     short loc_18000D511
0x18000d507  mov     edi, 8007000Eh
0x18000d50c  jmp     loc_18000D5AB
0x18000d511  lea     r8, [rdi+68h]
0x18000d515  xor     r9d, r9d
0x18000d518  mov     rdx, [r8]
0x18000d51b  jmp     short loc_18000D53D
0x18000d51d  cmp     r9d, [rdi+4Ch]
0x18000d521  jnb     short loc_18000D542
0x18000d523  mov     rax, rdx
0x18000d526  mov     rdx, [rdx]
0x18000d529  test    byte ptr [rax-8], 1
0x18000d52d  jz      short loc_18000D53D
0x18000d52f  mov     rax, [rax-0B0h]
0x18000d536  mov     [rsi+r9*8], rax
0x18000d53a  inc     r9d
0x18000d53d  cmp     rdx, r8
0x18000d540  jnz     short loc_18000D51D
0x18000d542  mov     rcx, [rbx+10h]
0x18000d546  mov     r8, [rdi+40h]
0x18000d54a  mov     rdx, qword ptr [rsp+5C0h+var_580]
0x18000d54f  mov     [rsp+5C0h+var_590], 0
0x18000d557  mov     rax, [rcx]
0x18000d55a  mov     [rsp+5C0h+var_598], 504D444Dh
0x18000d562  mov     [rsp+5C0h+var_5A0], rsi
0x18000d567  mov     rax, [rax+1B8h]
0x18000d56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d573  mov     edi, eax
0x18000d575  test    eax, eax
0x18000d577  jz      short loc_18000D598
0x18000d579  mov     rcx, [rbx+28h]
0x18000d57d  lea     r8, aKernelMinidump; "Kernel minidump write failed, 0x%08x"
0x18000d584  mov     r9d, edi
0x18000d587  mov     rdx, [rcx]
0x18000d58a  mov     rax, [rdx+8]
0x18000d58e  mov     edx, 4
0x18000d593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d598  mov     rcx, [rbx+20h]
0x18000d59c  mov     rdx, rsi
0x18000d59f  mov     rax, [rcx]
0x18000d5a2  mov     rax, [rax+18h]
0x18000d5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ab  xor     edx, edx; Val
0x18000d5ad  lea     rcx, [rbp+4C0h+var_540]; void *
0x18000d5b1  mov     r8d, 520h; Size
0x18000d5b7  call    memset_0
0x18000d5bc  mov     rcx, [rbx+50h]
0x18000d5c0  lea     r8, [rsp+5C0h+var_580]
0x18000d5c5  xorps   xmm0, xmm0
0x18000d5c8  mov     [rbp+4C0h+var_534], 8
0x18000d5cf  xor     eax, eax
0x18000d5d1  mov     [rbp+4C0h+var_530], edi
0x18000d5d4  mov     [rsp+5C0h+var_550], eax
0x18000d5d8  lea     rdx, [rbp+4C0h+var_540]
0x18000d5dc  mov     rax, [rbx+40h]
0x18000d5e0  movups  [rsp+5C0h+var_580], xmm0
0x18000d5e5  movups  [rsp+5C0h+var_570], xmm0
0x18000d5ea  movups  [rsp+5C0h+var_560], xmm0
0x18000d5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f4  add     rsp, 5A8h
0x18000d5fb  pop     rdi
0x18000d5fc  pop     rsi
0x18000d5fd  pop     rbx
0x18000d5fe  pop     rbp
0x18000d5ff  retn
```
