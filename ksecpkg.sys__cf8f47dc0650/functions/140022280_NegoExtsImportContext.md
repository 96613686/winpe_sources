# NegoExtsImportContext

- ea: `0x140022280`
- end: `0x14002239c`
- name: `NegoExtsImportContext`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140007008`
- `0x14000e344`
- `0x140010240`
- `0x140022280`
- `0x14002c664`

## string_xrefs

- `0x1400222ea`: `Failed to create kernel mode context: %#x\n`
- `0x140022344`: `the package failed to create kernel mode context: %#x\n`

## pseudocode

```c
__int64 __fastcall NegoExtsImportContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbp
  int v7; // eax
  unsigned int v8; // edi
  PVOID v9; // rbx
  int v10; // eax
  __int128 v12; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v12 = 0;
  P = 0;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsImportContext called\n");
  v7 = NegoExtsCreateKernelModeContext(0, a1, &P);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = P;
    LODWORD(v12) = *(_DWORD *)(v3 + 16);
    *((_QWORD *)&v12 + 1) = v3 + *(unsigned int *)(v3 + 12);
    v10 = (*(__int64 (__fastcall **)(__int128 *, __int64, char *))(*((_QWORD *)P + 3) + 96LL))(&v12, a2, (char *)P + 32);
    v8 = v10;
    if ( v10 >= 0 )
    {
      *a3 = v9;
      v9 = 0;
    }
    else if ( KsecInfoLevel )
    {
      KsecDebugOut(1, "the package failed to create kernel mode context: %#x\n", v10);
    }
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to create kernel mode context: %#x\n", v7);
    v9 = P;
  }
  if ( v9 )
    NegoExtsFreeContext(v9);
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsImportContext returned %#x\n", v8);
  return v8;
}

```

## disassembly

```asm
0x140022280  mov     rax, rsp
0x140022283  mov     [rax+10h], rbx
0x140022287  mov     [rax+18h], rbp
0x14002228b  push    rsi
0x14002228c  push    rdi
0x14002228d  push    r14
0x14002228f  sub     rsp, 30h
0x140022293  cmp     cs:KsecInfoLevel, 0
0x14002229a  xorps   xmm0, xmm0
0x14002229d  mov     rbp, [rcx+8]
0x1400222a1  mov     rsi, r8
0x1400222a4  movups  xmmword ptr [rax-28h], xmm0
0x1400222a8  mov     r14, rdx
0x1400222ab  mov     qword ptr [rax+8], 0
0x1400222b3  mov     rbx, rcx
0x1400222b6  jz      short loc_1400222C9
0x1400222b8  lea     rdx, aNegoextsimport_0; "NegoExtsImportContext called\n"
0x1400222bf  mov     ecx, 4
0x1400222c4  call    KsecDebugOut
0x1400222c9  lea     r8, [rsp+48h+P]
0x1400222ce  mov     rdx, rbx
0x1400222d1  xor     ecx, ecx
0x1400222d3  call    NegoExtsCreateKernelModeContext
0x1400222d8  mov     edi, eax
0x1400222da  test    eax, eax
0x1400222dc  jns     short loc_140022302
0x1400222de  cmp     cs:KsecInfoLevel, 0
0x1400222e5  jz      short loc_1400222FB
0x1400222e7  mov     r8d, eax
0x1400222ea  lea     rdx, aFailedToCreate; "Failed to create kernel mode context: %"...
0x1400222f1  mov     ecx, 1
0x1400222f6  call    KsecDebugOut
0x1400222fb  mov     rbx, [rsp+48h+P]
0x140022300  jmp     short loc_14002235C
0x140022302  mov     eax, [rbp+10h]
0x140022305  lea     rcx, [rsp+48h+var_28]
0x14002230a  mov     rbx, [rsp+48h+P]
0x14002230f  mov     rdx, r14
0x140022312  mov     [rsp+48h+var_28], eax
0x140022316  mov     eax, [rbp+0Ch]
0x140022319  add     rax, rbp
0x14002231c  mov     [rsp+48h+var_20], rax
0x140022321  lea     r8, [rbx+20h]
0x140022325  mov     rax, [rbx+18h]
0x140022329  mov     rax, [rax+60h]
0x14002232d  call    _guard_dispatch_icall
0x140022332  mov     edi, eax
0x140022334  test    eax, eax
0x140022336  jns     short loc_140022357
0x140022338  cmp     cs:KsecInfoLevel, 0
0x14002233f  jz      short loc_14002235C
0x140022341  mov     r8d, eax
0x140022344  lea     rdx, aThePackageFail; "the package failed to create kernel mod"...
0x14002234b  mov     ecx, 1
0x140022350  call    KsecDebugOut
0x140022355  jmp     short loc_14002235C
0x140022357  mov     [rsi], rbx
0x14002235a  xor     ebx, ebx
0x14002235c  test    rbx, rbx
0x14002235f  jz      short loc_140022369
0x140022361  mov     rcx, rbx; P
0x140022364  call    NegoExtsFreeContext
0x140022369  cmp     cs:KsecInfoLevel, 0
0x140022370  jz      short loc_140022386
0x140022372  mov     r8d, edi
0x140022375  lea     rdx, aNegoextsimport; "NegoExtsImportContext returned %#x\n"
0x14002237c  mov     ecx, 4
0x140022381  call    KsecDebugOut
0x140022386  mov     rbx, [rsp+48h+arg_8]
0x14002238b  mov     eax, edi
0x14002238d  mov     rbp, [rsp+48h+arg_10]
0x140022392  add     rsp, 30h
0x140022396  pop     r14
0x140022398  pop     rdi
0x140022399  pop     rsi
0x14002239a  retn
```
