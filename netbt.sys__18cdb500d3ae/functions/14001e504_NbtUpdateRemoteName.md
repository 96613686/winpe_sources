# NbtUpdateRemoteName

- ea: `0x14001e504`
- end: `0x14001e771`
- name: `NbtUpdateRemoteName`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140008160`

## callees

- `0x14001e504`
- `0x140031140`
- `0x140031440`
- `0x140040294`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e740`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e75c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e740`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e75c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e545`
- `ntoskrnl!ExAllocatePool2` at `0x14001e545`

## pseudocode

```c
__int64 __fastcall NbtUpdateRemoteName(__int64 a1, __int64 a2, __int64 a3, __int16 a4)
{
  void *Pool2; // rax
  void *v9; // rdi
  __int16 v10; // dx
  __int64 v11; // r12
  __int64 v12; // rsi
  int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // rdi
  __int64 v16; // rax
  void *v17; // rcx
  const void *v19; // rdx
  __int16 v20; // ax
  void *v21; // rcx

  if ( *(_WORD *)(a2 + 128) < (unsigned __int16)word_1400395D0 )
  {
    Pool2 = (void *)ExAllocatePool2(64, 16LL * (unsigned __int16)word_1400395D0, 842031694);
    v9 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 16LL * (unsigned __int16)word_1400395D0);
      v19 = *(const void **)(a2 + 24);
      if ( v19 )
      {
        memmove(v9, v19, 16LL * *(unsigned __int16 *)(a2 + 128));
        ExFreePoolWithTag(*(PVOID *)(a2 + 24), 0);
      }
      *(_QWORD *)(a2 + 24) = v9;
      *(_WORD *)(a2 + 128) = word_1400395D0;
    }
    else if ( (BYTE1(xmmword_140038420) & 8) != 0 )
    {
      WPP_SF_(1035, 14, WPP_ea3294f46db239813d82e8111ee47aa3_Traceguids);
    }
  }
  v10 = *(_WORD *)(a2 + 130);
  if ( ((v10 & 2) == 0 || (a4 & 2) != 0) && (unsigned __int8)(v10 & 4) <= (unsigned __int8)(a4 & 0xC) )
  {
    if ( a3 )
    {
      v11 = *(_QWORD *)(a3 + 40);
      v13 = *(_DWORD *)(a3 + 32);
      *(_QWORD *)(a3 + 40) = 0;
      *(_DWORD *)(a2 + 56) = dword_1400395F8;
      v12 = *(_QWORD *)(a3 + 48);
    }
    else
    {
      v11 = *(_QWORD *)(a2 + 40);
      v12 = 0;
      v13 = *(_DWORD *)(a2 + 32);
      *(_QWORD *)(a2 + 40) = 0;
    }
    if ( (a4 & 0xB) != 0 )
    {
      if ( *(_WORD *)(a2 + 128) )
      {
        **(_DWORD **)(a2 + 24) = v13;
        v20 = *(_WORD *)(a2 + 130);
        if ( (v20 & 4) != 0 && (a4 & 8) != 0 )
        {
          *(_WORD *)(a2 + 130) = a4 | v20;
          return 0;
        }
      }
    }
    if ( a1 )
    {
      if ( *(_DWORD *)(a1 + 340) != 1 )
      {
        v14 = *(_DWORD *)(a1 + 696);
        if ( v14 < *(unsigned __int16 *)(a2 + 128) )
        {
          *(_QWORD *)(a2 + 80) |= *(_QWORD *)(a1 + 560);
          v15 = 16LL * v14;
          if ( v13 )
          {
            v16 = *(_QWORD *)(a2 + 24);
            *(_DWORD *)(a2 + 32) = v13;
            *(_DWORD *)(v15 + v16) = v13;
          }
          if ( v12 )
          {
            *(_QWORD *)(a3 + 48) = 0;
            goto LABEL_18;
          }
          v12 = *(_QWORD *)(a2 + 48);
          if ( v12 )
          {
            *(_QWORD *)(a2 + 48) = 0;
LABEL_18:
            v17 = *(void **)(*(_QWORD *)(a2 + 24) + v15 + 8);
            if ( v17 )
              ExFreePoolWithTag(v17, 0);
            *(_QWORD *)(*(_QWORD *)(a2 + 24) + v15 + 8) = v12;
          }
        }
      }
    }
    if ( v11 )
    {
      v21 = *(void **)(a2 + 40);
      if ( v21 )
        ExFreePoolWithTag(v21, 0);
      *(_QWORD *)(a2 + 40) = v11;
    }
    *(_WORD *)(a2 + 130) |= a4;
    return 0;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001e504  push    rbx
0x14001e506  push    rbp
0x14001e507  push    rsi
0x14001e508  push    rdi
0x14001e509  push    r12
0x14001e50b  push    r13
0x14001e50d  push    r14
0x14001e50f  push    r15
0x14001e511  sub     rsp, 28h
0x14001e515  movzx   eax, cs:word_1400395D0
0x14001e51c  xor     r13d, r13d
0x14001e51f  movzx   ebp, r9w
0x14001e523  mov     r14, r8
0x14001e526  mov     rbx, rdx
0x14001e529  mov     r15, rcx
0x14001e52c  cmp     [rdx+80h], ax
0x14001e533  jnb     short loc_14001E56A
0x14001e535  mov     edx, eax
0x14001e537  lea     ecx, [r13+40h]
0x14001e53b  shl     rdx, 4
0x14001e53f  mov     r8d, 3230624Eh
0x14001e545  call    cs:__imp_ExAllocatePool2
0x14001e54c  nop     dword ptr [rax+rax+00h]
0x14001e551  mov     rdi, rax
0x14001e554  test    rax, rax
0x14001e557  jnz     loc_14001E654
0x14001e55d  test    byte ptr cs:xmmword_140038420+1, 8
0x14001e564  jnz     loc_14001E723
0x14001e56a  movzx   edx, word ptr [rbx+82h]
0x14001e571  mov     r8d, 1
0x14001e577  bt      dx, r8w
0x14001e57c  setb    cl
0x14001e57f  bt      bp, r8w
0x14001e584  setnb   al
0x14001e587  test    al, cl
0x14001e589  jnz     loc_14001E68E
0x14001e58f  mov     al, bpl
0x14001e592  and     dl, 4
0x14001e595  and     al, 0Ch
0x14001e597  cmp     dl, al
0x14001e599  ja      loc_14001E68E
0x14001e59f  test    r14, r14
0x14001e5a2  jnz     loc_14001E6D1
0x14001e5a8  mov     r12, [rbx+28h]
0x14001e5ac  mov     rsi, r13
0x14001e5af  mov     edx, [rbx+20h]
0x14001e5b2  mov     [rbx+28h], r13
0x14001e5b6  test    bpl, 0Bh
0x14001e5ba  jnz     loc_14001E695
0x14001e5c0  test    r15, r15
0x14001e5c3  jz      short loc_14001E630
0x14001e5c5  cmp     [r15+154h], r8d
0x14001e5cc  jz      short loc_14001E630
0x14001e5ce  mov     ecx, [r15+2B8h]
0x14001e5d5  movzx   eax, word ptr [rbx+80h]
0x14001e5dc  cmp     ecx, eax
0x14001e5de  jnb     short loc_14001E630
0x14001e5e0  mov     rax, [r15+230h]
0x14001e5e7  mov     edi, ecx
0x14001e5e9  or      [rbx+50h], rax
0x14001e5ed  shl     rdi, 4
0x14001e5f1  test    edx, edx
0x14001e5f3  jz      short loc_14001E5FF
0x14001e5f5  mov     rax, [rbx+18h]
0x14001e5f9  mov     [rbx+20h], edx
0x14001e5fc  mov     [rdi+rax], edx
0x14001e5ff  test    rsi, rsi
0x14001e602  jnz     loc_14001E6EF
0x14001e608  mov     rsi, [rbx+30h]
0x14001e60c  test    rsi, rsi
0x14001e60f  jz      short loc_14001E630
0x14001e611  mov     [rbx+30h], r13
0x14001e615  mov     rax, [rbx+18h]
0x14001e619  mov     rcx, [rax+rdi+8]; P
0x14001e61e  test    rcx, rcx
0x14001e621  jnz     loc_14001E73E
0x14001e627  mov     rax, [rbx+18h]
0x14001e62b  mov     [rax+rdi+8], rsi
0x14001e630  test    r12, r12
0x14001e633  jnz     loc_14001E751
0x14001e639  or      [rbx+82h], bp
0x14001e640  xor     eax, eax
0x14001e642  add     rsp, 28h
0x14001e646  pop     r15
0x14001e648  pop     r14
0x14001e64a  pop     r13
0x14001e64c  pop     r12
0x14001e64e  pop     rdi
0x14001e64f  pop     rsi
0x14001e650  pop     rbp
0x14001e651  pop     rbx
0x14001e652  retn
0x14001e654  movzx   r8d, cs:word_1400395D0
0x14001e65c  xor     edx, edx; Val
0x14001e65e  shl     r8, 4; Size
0x14001e662  mov     rcx, rdi; void *
0x14001e665  call    memset
0x14001e66a  mov     rdx, [rbx+18h]; Src
0x14001e66e  test    rdx, rdx
0x14001e671  jnz     loc_14001E6F8
0x14001e677  mov     [rbx+18h], rdi
0x14001e67b  movzx   eax, cs:word_1400395D0
0x14001e682  mov     [rbx+80h], ax
0x14001e689  jmp     loc_14001E56A
0x14001e68e  mov     eax, 0C0000001h
0x14001e693  jmp     short loc_14001E642
0x14001e695  cmp     [rbx+80h], r13w
0x14001e69d  jz      loc_14001E5C0
0x14001e6a3  mov     rax, [rbx+18h]
0x14001e6a7  mov     [rax], edx
0x14001e6a9  movzx   eax, word ptr [rbx+82h]
0x14001e6b0  test    al, 4
0x14001e6b2  jz      loc_14001E5C0
0x14001e6b8  test    bpl, 8
0x14001e6bc  jz      loc_14001E5C0
0x14001e6c2  or      ax, bp
0x14001e6c5  mov     [rbx+82h], ax
0x14001e6cc  jmp     loc_14001E640
0x14001e6d1  mov     r12, [r14+28h]
0x14001e6d5  mov     edx, [r14+20h]
0x14001e6d9  mov     [r14+28h], r13
0x14001e6dd  mov     eax, cs:dword_1400395F8
0x14001e6e3  mov     [rbx+38h], eax
0x14001e6e6  mov     rsi, [r14+30h]
0x14001e6ea  jmp     loc_14001E5B6
0x14001e6ef  mov     [r14+30h], r13
0x14001e6f3  jmp     loc_14001E615
0x14001e6f8  movzx   r8d, word ptr [rbx+80h]
0x14001e700  mov     rcx, rdi; void *
0x14001e703  shl     r8, 4; Size
0x14001e707  call    memmove
0x14001e70c  mov     rcx, [rbx+18h]; P
0x14001e710  xor     edx, edx; Tag
0x14001e712  call    cs:__imp_ExFreePoolWithTag
0x14001e719  nop     dword ptr [rax+rax+00h]
0x14001e71e  jmp     loc_14001E677
0x14001e723  mov     edx, 0Eh
0x14001e728  lea     r8, WPP_ea3294f46db239813d82e8111ee47aa3_Traceguids
0x14001e72f  mov     ecx, 40Bh
0x14001e734  call    WPP_SF_
0x14001e739  jmp     loc_14001E56A
0x14001e73e  xor     edx, edx; Tag
0x14001e740  call    cs:__imp_ExFreePoolWithTag
0x14001e747  nop     dword ptr [rax+rax+00h]
0x14001e74c  jmp     loc_14001E627
0x14001e751  mov     rcx, [rbx+28h]; P
0x14001e755  test    rcx, rcx
0x14001e758  jz      short loc_14001E768
0x14001e75a  xor     edx, edx; Tag
0x14001e75c  call    cs:__imp_ExFreePoolWithTag
0x14001e763  nop     dword ptr [rax+rax+00h]
0x14001e768  mov     [rbx+28h], r12
0x14001e76c  jmp     loc_14001E639
```
