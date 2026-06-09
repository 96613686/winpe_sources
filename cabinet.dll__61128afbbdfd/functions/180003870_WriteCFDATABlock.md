# WriteCFDATABlock

- ea: `0x180003870`
- end: `0x1800039b2`
- name: `WriteCFDATABlock`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800019d0`
- `0x180003340`

## callees

- `0x180003730`
- `0x180003870`
- `0x180004640`
- `0x18001562a`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall WriteCFDATABlock(
        __int64 a1,
        unsigned int (__fastcall *a2)(_QWORD, _QWORD, _QWORD, __int64),
        __int64 a3)
{
  void *v6; // rax
  __int64 v7; // rdi
  unsigned __int16 *v8; // rbp
  __int64 v9; // r8
  int v10; // r9d
  void (__fastcall *v11)(__int64); // rax
  __int64 v13; // rax
  __int64 v14; // rax

  if ( !*(_DWORD *)(a1 + 668) )
    return 1;
  v6 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(unsigned int *)(a1 + 656));
  v7 = (__int64)v6;
  if ( v6 )
  {
    memset_0(v6, 0, *(unsigned int *)(a1 + 656));
    v8 = (unsigned __int16 *)(v7 + 4);
    if ( (unsigned int)MCICompressGlobal(a1, (_WORD *)(v7 + 4), v9, v10) )
    {
      *(_WORD *)(v7 + 6) = *(_WORD *)(a1 + 668);
      if ( (unsigned int)WriteCount(
                           a1 + 96,
                           v7,
                           *(_DWORD *)(a1 + 656),
                           *(unsigned int (__fastcall **)(__int64, __int64, _QWORD, int *, __int64))(a1 + 48),
                           *(_QWORD **)(a1 + 88),
                           a3) )
      {
        if ( (unsigned int)WriteCount(
                             a1 + 96,
                             *(_QWORD *)(a1 + 688),
                             *v8,
                             *(unsigned int (__fastcall **)(__int64, __int64, _QWORD, int *, __int64))(a1 + 48),
                             *(_QWORD **)(a1 + 88),
                             a3) )
        {
          if ( a2(0, *v8, *(unsigned int *)(a1 + 668), a3) != -1 )
          {
            v11 = *(void (__fastcall **)(__int64))(a1 + 24);
            *(_DWORD *)(a1 + 668) = 0;
            v11(v7);
            return 1;
          }
          v14 = *(_QWORD *)(a1 + 88);
          *(_QWORD *)v14 = 7;
          *(_DWORD *)(v14 + 8) = 1;
        }
      }
    }
    (*(void (__fastcall **)(__int64))(a1 + 24))(v7);
  }
  else
  {
    v13 = *(_QWORD *)(a1 + 88);
    *(_QWORD *)v13 = 3;
    *(_DWORD *)(v13 + 8) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180003870  push    rbx
0x180003872  push    rbp
0x180003873  push    rsi
0x180003874  push    rdi
0x180003875  push    r14
0x180003877  push    r15
0x180003879  sub     rsp, 38h
0x18000387d  cmp     dword ptr [rcx+29Ch], 0
0x180003884  mov     rsi, r8
0x180003887  mov     r15, rdx
0x18000388a  mov     rbx, rcx
0x18000388d  jz      loc_180003968
0x180003893  mov     ecx, [rcx+290h]
0x180003899  mov     rax, [rbx+10h]
0x18000389d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a2  mov     rdi, rax
0x1800038a5  test    rax, rax
0x1800038a8  jz      loc_18000398A
0x1800038ae  mov     r8d, [rbx+290h]; Size
0x1800038b5  xor     edx, edx; Val
0x1800038b7  mov     rcx, rax; void *
0x1800038ba  call    memset_0
0x1800038bf  lea     rbp, [rdi+4]
0x1800038c3  mov     rcx, rbx
0x1800038c6  mov     rdx, rbp
0x1800038c9  call    MCICompressGlobal
0x1800038ce  test    eax, eax
0x1800038d0  jz      loc_18000397A
0x1800038d6  movzx   eax, word ptr [rbx+29Ch]
0x1800038dd  lea     rcx, [rbx+60h]
0x1800038e1  mov     [rdi+6], ax
0x1800038e5  mov     rdx, rdi
0x1800038e8  mov     rax, [rbx+58h]
0x1800038ec  mov     r9, [rbx+30h]
0x1800038f0  mov     r8d, [rbx+290h]
0x1800038f7  mov     [rsp+68h+var_40], rsi
0x1800038fc  mov     [rsp+68h+var_48], rax
0x180003901  call    WriteCount
0x180003906  test    eax, eax
0x180003908  jz      short loc_18000397A
0x18000390a  mov     rax, [rbx+58h]
0x18000390e  lea     rcx, [rbx+60h]
0x180003912  movzx   r8d, word ptr [rbp+0]
0x180003917  mov     r9, [rbx+30h]
0x18000391b  mov     rdx, [rbx+2B0h]
0x180003922  mov     [rsp+68h+var_40], rsi
0x180003927  mov     [rsp+68h+var_48], rax
0x18000392c  call    WriteCount
0x180003931  test    eax, eax
0x180003933  jz      short loc_18000397A
0x180003935  movzx   edx, word ptr [rbp+0]
0x180003939  mov     r9, rsi
0x18000393c  mov     r8d, [rbx+29Ch]
0x180003943  xor     ecx, ecx
0x180003945  mov     rax, r15
0x180003948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000394d  cmp     eax, 0FFFFFFFFh
0x180003950  jz      short loc_18000399E
0x180003952  mov     rax, [rbx+18h]
0x180003956  mov     rcx, rdi
0x180003959  mov     dword ptr [rbx+29Ch], 0
0x180003963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003968  mov     eax, 1
0x18000396d  add     rsp, 38h
0x180003971  pop     r15
0x180003973  pop     r14
0x180003975  pop     rdi
0x180003976  pop     rsi
0x180003977  pop     rbp
0x180003978  pop     rbx
0x180003979  retn
0x18000397a  mov     rax, [rbx+18h]
0x18000397e  mov     rcx, rdi
0x180003981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003986  xor     eax, eax
0x180003988  jmp     short loc_18000396D
0x18000398a  mov     rax, [rbx+58h]
0x18000398e  mov     qword ptr [rax], 3
0x180003995  mov     dword ptr [rax+8], 1
0x18000399c  jmp     short loc_180003986
0x18000399e  mov     rax, [rbx+58h]
0x1800039a2  mov     qword ptr [rax], 7
0x1800039a9  mov     dword ptr [rax+8], 1
0x1800039b0  jmp     short loc_18000397A
```
