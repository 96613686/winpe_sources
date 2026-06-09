# ILCompareRelIDs

- ea: `0x18001230c`
- end: `0x180012453`
- name: `ILCompareRelIDs`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000da24`

## callees

- `0x18001230c`
- `0x180013010`

## import_xrefs

- `SHELL32!__imp_ILCloneFirst` at `0x180012359`
- `SHELL32!__imp_ILCloneFirst` at `0x180012359`
- `SHELL32!__imp_ILFree` at `0x18001240e`
- `SHELL32!__imp_ILFree` at `0x18001240e`

## pseudocode

```c
__int64 __fastcall ILCompareRelIDs(__int64 *a1, const ITEMIDLIST *a2, unsigned __int16 *a3, __int64 a4)
{
  _WORD *v4; // rdi
  _WORD *v7; // rbp
  LPITEMIDLIST v8; // rax
  ITEMIDLIST *v9; // rsi
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // ebx
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF

  v4 = (unsigned __int16 *)((char *)a3 + *a3);
  v7 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
  if ( v7 && *v7 )
  {
    if ( v4 && *v4 )
    {
      v8 = ILCloneFirst(a2);
      v9 = v8;
      if ( v8 )
      {
        v10 = *a1;
        v14 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64 *, LPITEMIDLIST, _QWORD, GUID *, __int64 *))(v10 + 40))(
                a1,
                v8,
                0,
                &GUID_000214e6_0000_0000_c000_000000000046,
                &v14);
        if ( v11 >= 0 )
        {
          v15 = 0;
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
                 v14,
                 &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                 &v15) < 0 )
            a4 = 0;
          else
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)v14 + 56LL))(
                  v14,
                  a4 & 0xFFFFFFFFFFFF0000uLL,
                  v7,
                  v4);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        ILFree(v9);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    if ( !v4 || (v12 = 0, !*v4) )
      v12 = 1;
    return (unsigned __int16)-(v12 == 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001230c  mov     [rsp+arg_0], rbx
0x180012311  push    rbp
0x180012312  push    rsi
0x180012313  push    rdi
0x180012314  push    r14
0x180012316  push    r15
0x180012318  sub     rsp, 30h
0x18001231c  movzx   edi, word ptr [r8]
0x180012320  xor     r15d, r15d
0x180012323  movzx   ebp, word ptr [rdx]
0x180012326  add     rdi, r8
0x180012329  mov     r14, r9
0x18001232c  mov     rbx, rcx
0x18001232f  add     rbp, rdx
0x180012332  jz      loc_180012424
0x180012338  cmp     [rbp+0], r15w
0x18001233d  jz      loc_180012424
0x180012343  test    rdi, rdi
0x180012346  jz      loc_18001241D
0x18001234c  cmp     [rdi], r15w
0x180012350  jz      loc_18001241D
0x180012356  mov     rcx, rdx; pidl
0x180012359  call    cs:__imp_ILCloneFirst
0x18001235f  mov     rsi, rax
0x180012362  test    rax, rax
0x180012365  jz      loc_180012416
0x18001236b  mov     rcx, [rbx]
0x18001236e  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180012375  xor     r8d, r8d
0x180012378  mov     [rsp+58h+arg_8], r15
0x18001237d  mov     rdx, rsi
0x180012380  mov     rax, [rcx+28h]
0x180012384  lea     rcx, [rsp+58h+arg_8]
0x180012389  mov     [rsp+58h+var_38], rcx
0x18001238e  mov     rcx, rbx
0x180012391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012396  mov     ebx, eax
0x180012398  test    eax, eax
0x18001239a  js      short loc_18001240B
0x18001239c  mov     rcx, [rsp+58h+arg_8]
0x1800123a1  lea     r8, [rsp+58h+arg_10]
0x1800123a6  mov     [rsp+58h+arg_10], r15
0x1800123ab  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800123b2  mov     rax, [rcx]
0x1800123b5  mov     rax, [rax]
0x1800123b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123bd  test    eax, eax
0x1800123bf  js      short loc_1800123D4
0x1800123c1  mov     rcx, [rsp+58h+arg_10]
0x1800123c6  mov     rax, [rcx]
0x1800123c9  mov     rax, [rax+10h]
0x1800123cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d2  jmp     short loc_1800123D7
0x1800123d4  mov     r14, r15
0x1800123d7  mov     rcx, [rsp+58h+arg_8]
0x1800123dc  and     r14, 0FFFFFFFFFFFF0000h
0x1800123e3  mov     r9, rdi
0x1800123e6  mov     r8, rbp
0x1800123e9  mov     rdx, r14
0x1800123ec  mov     rax, [rcx]
0x1800123ef  mov     rax, [rax+38h]
0x1800123f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f8  mov     rcx, [rsp+58h+arg_8]
0x1800123fd  mov     ebx, eax
0x1800123ff  mov     rax, [rcx]
0x180012402  mov     rax, [rax+10h]
0x180012406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240b  mov     rcx, rsi; pidl
0x18001240e  call    cs:__imp_ILFree
0x180012414  jmp     short loc_180012440
0x180012416  mov     ebx, 8007000Eh
0x18001241b  jmp     short loc_180012440
0x18001241d  mov     ebx, 1
0x180012422  jmp     short loc_180012440
0x180012424  test    rdi, rdi
0x180012427  jz      short loc_180012432
0x180012429  mov     ebx, r15d
0x18001242c  cmp     [rdi], r15w
0x180012430  jnz     short loc_180012437
0x180012432  mov     ebx, 1
0x180012437  neg     ebx
0x180012439  sbb     ebx, ebx
0x18001243b  not     ebx
0x18001243d  movzx   ebx, bx
0x180012440  mov     eax, ebx
0x180012442  mov     rbx, [rsp+58h+arg_0]
0x180012447  add     rsp, 30h
0x18001244b  pop     r15
0x18001244d  pop     r14
0x18001244f  pop     rdi
0x180012450  pop     rsi
0x180012451  pop     rbp
0x180012452  retn
```
