# FatRescanDirectory

- ea: `0x140032ff0`
- end: `0x140033269`
- name: `FatRescanDirectory`
- size: `633`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003062c`

## callees

- `0x140024584`
- `0x140032ff0`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x140033149`
- `ntoskrnl!RtlClearBits` at `0x1400331f4`
- `ntoskrnl!RtlClearBits` at `0x14003321c`
- `ntoskrnl!RtlClearBits` at `0x140033149`
- `ntoskrnl!RtlClearBits` at `0x1400331f4`
- `ntoskrnl!RtlClearBits` at `0x14003321c`
- `ntoskrnl!RtlSetBits` at `0x140033187`
- `ntoskrnl!RtlSetBits` at `0x1400331e6`
- `ntoskrnl!RtlSetBits` at `0x140033187`
- `ntoskrnl!RtlSetBits` at `0x1400331e6`
- `ntoskrnl!CcUnpinData` at `0x140033044`
- `ntoskrnl!CcUnpinData` at `0x140033071`
- `ntoskrnl!CcUnpinData` at `0x140033236`
- `ntoskrnl!CcUnpinData` at `0x14005d2e0`
- `ntoskrnl!CcUnpinData` at `0x140033044`
- `ntoskrnl!CcUnpinData` at `0x140033071`
- `ntoskrnl!CcUnpinData` at `0x140033236`
- `ntoskrnl!CcUnpinData` at `0x14005d2e0`

## pseudocode

```c
void __fastcall FatRescanDirectory(__int64 a1, __int64 a2)
{
  __int64 v3; // r13
  PVOID v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // r15d
  unsigned int v8; // edi
  ULONG v9; // r12d
  ULONG i; // esi
  unsigned __int8 v11; // r13
  ULONG v12; // r8d
  struct _RTL_BITMAP *v13; // rcx
  unsigned int v14; // r8d
  PVOID v15; // [rsp+50h] [rbp-48h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+18h] BYREF
  PVOID Bcb; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a1;
  v4 = 0;
  Bcb = 0;
  v15 = 0;
  v5 = 0;
  LODWORD(v17) = 0;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  v9 = 0;
  for ( i = 0; ; ++i )
  {
    if ( v6 < *(_DWORD *)(a2 + 24) )
    {
      if ( (v6 & 0xFFF) == 0 || !v4 )
      {
        if ( v4 )
        {
          CcUnpinData(v4);
          Bcb = 0;
        }
        FatReadDirectoryFile(v3, a2, v6 & 0xFFFFF000, 0x1000u, 0, &Bcb, &v15, &v17);
        v15 = (char *)v15 + (v6 & 0xFFF);
        v4 = Bcb;
        goto LABEL_10;
      }
    }
    else
    {
      v5 = -1073741807;
      LODWORD(v17) = -1073741807;
      if ( v4 )
      {
        CcUnpinData(v4);
        v4 = 0;
        Bcb = 0;
LABEL_10:
        v5 = v17;
      }
    }
    if ( v5 == -1073741807 || !*(_BYTE *)v15 )
      break;
    if ( *(_BYTE *)v15 == 0xE5 )
    {
      v11 = 1;
      if ( v7 == -1 )
        v7 = v6;
    }
    else
    {
      v11 = 0;
    }
    if ( v8 )
    {
      if ( v8 == 1 && !v11 )
      {
        RtlClearBits((PRTL_BITMAP)(a2 + 400), v9, i - v9);
        v8 = 2;
        v9 = i;
        v4 = Bcb;
      }
      if ( v8 == 2 )
      {
        if ( v11 )
        {
          RtlSetBits((PRTL_BITMAP)(a2 + 400), v9, i - v9);
          v8 = 1;
          v9 = i;
          v4 = Bcb;
        }
      }
    }
    else
    {
      v8 = (v11 ^ 1) + 1;
    }
    v6 += 32;
    v15 = (char *)v15 + 32;
    v5 = v17;
    v3 = a1;
  }
  v12 = i - v9;
  v13 = (struct _RTL_BITMAP *)(a2 + 400);
  if ( v8 <= 1 )
    RtlClearBits(v13, v9, v12);
  else
    RtlSetBits(v13, v9, v12);
  v14 = *(_DWORD *)(a2 + 24);
  if ( v6 < v14 )
    RtlClearBits((PRTL_BITMAP)(a2 + 400), v6 >> 5, (v14 - v6) >> 5);
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v7 == -1 )
    v7 = v6;
  *(_DWORD *)(a2 + 376) = v6;
  *(_DWORD *)(a2 + 380) = v7;
}

```

## disassembly

```asm
0x140032ff0  mov     r11, rsp
0x140032ff3  mov     [r11+8], rcx
0x140032ff7  push    rbx
0x140032ff8  push    rsi
0x140032ff9  push    rdi
0x140032ffa  push    r12
0x140032ffc  push    r13
0x140032ffe  push    r14
0x140033000  push    r15
0x140033002  sub     rsp, 60h
0x140033006  mov     r14, rdx
0x140033009  mov     r13, rcx
0x14003300c  xor     ecx, ecx; Bcb
0x14003300e  mov     [r11+20h], rcx
0x140033012  mov     [r11-48h], rcx
0x140033016  xor     eax, eax
0x140033018  mov     [r11+18h], eax
0x14003301c  xor     ebx, ebx
0x14003301e  or      r15d, 0FFFFFFFFh
0x140033022  xor     edi, edi
0x140033024  xor     r12d, r12d
0x140033027  xor     esi, esi
0x140033029  cmp     ebx, [r14+18h]
0x14003302d  jb      short loc_14003305F
0x14003302f  mov     eax, 0C0000011h
0x140033034  mov     dword ptr [rsp+98h+arg_10], eax
0x14003303b  test    rcx, rcx
0x14003303e  jz      loc_1400330E8
0x140033044  call    cs:__imp_CcUnpinData
0x14003304b  nop     dword ptr [rax+rax+00h]
0x140033050  xor     ecx, ecx
0x140033052  mov     [rsp+98h+Bcb], rcx
0x14003305a  jmp     loc_1400330E1
0x14003305f  test    ebx, 0FFFh
0x140033065  jz      short loc_14003306C
0x140033067  test    rcx, rcx
0x14003306a  jnz     short loc_1400330E8
0x14003306c  test    rcx, rcx
0x14003306f  jz      short loc_140033089
0x140033071  call    cs:__imp_CcUnpinData
0x140033078  nop     dword ptr [rax+rax+00h]
0x14003307d  mov     [rsp+98h+Bcb], 0
0x140033089  mov     r8d, ebx
0x14003308c  and     r8d, 0FFFFF000h; int
0x140033093  lea     rax, [rsp+98h+arg_10]
0x14003309b  mov     [rsp+98h+var_60], rax; __int64
0x1400330a0  lea     rax, [rsp+98h+var_48]
0x1400330a5  mov     [rsp+98h+var_68], rax; PVOID *
0x1400330aa  lea     rax, [rsp+98h+Bcb]
0x1400330b2  mov     [rsp+98h+var_70], rax; PVOID *
0x1400330b7  mov     [rsp+98h+var_78], 0; char
0x1400330bc  mov     r9d, 1000h; int
0x1400330c2  mov     rdx, r14; int
0x1400330c5  mov     rcx, r13; int
0x1400330c8  call    FatReadDirectoryFile
0x1400330cd  mov     eax, ebx
0x1400330cf  and     eax, 0FFFh
0x1400330d4  add     [rsp+98h+var_48], rax
0x1400330d9  mov     rcx, [rsp+98h+Bcb]
0x1400330e1  mov     eax, dword ptr [rsp+98h+arg_10]
0x1400330e8  cmp     eax, 0C0000011h
0x1400330ed  jz      loc_1400331CE
0x1400330f3  mov     rax, [rsp+98h+var_48]
0x1400330f8  mov     dl, [rax]
0x1400330fa  test    dl, dl
0x1400330fc  jz      loc_1400331CE
0x140033102  cmp     dl, 0E5h
0x140033105  jnz     short loc_140033119
0x140033107  mov     r13b, 1
0x14003310a  cmp     r15d, 0FFFFFFFFh
0x14003310e  jnz     short loc_14003311C
0x140033110  mov     r15d, ebx
0x140033113  mov     [rsp+98h+var_50], ebx
0x140033117  jmp     short loc_14003311C
0x140033119  xor     r13b, r13b
0x14003311c  test    edi, edi
0x14003311e  jnz     short loc_14003312F
0x140033120  movzx   edi, r13b
0x140033124  xor     edi, 1
0x140033127  inc     edi
0x140033129  mov     [rsp+98h+var_58], edi
0x14003312d  jmp     short loc_1400331AB
0x14003312f  cmp     edi, 1
0x140033132  jnz     short loc_14003316D
0x140033134  test    r13b, r13b
0x140033137  jnz     short loc_14003316D
0x140033139  lea     rcx, [r14+190h]; BitMapHeader
0x140033140  mov     r8d, esi
0x140033143  sub     r8d, r12d; NumberToClear
0x140033146  mov     edx, r12d; StartingIndex
0x140033149  call    cs:__imp_RtlClearBits
0x140033150  nop     dword ptr [rax+rax+00h]
0x140033155  mov     edi, 2
0x14003315a  mov     [rsp+98h+var_58], edi
0x14003315e  mov     r12d, esi
0x140033161  mov     [rsp+98h+var_54], esi
0x140033165  mov     rcx, [rsp+98h+Bcb]
0x14003316d  cmp     edi, 2
0x140033170  jnz     short loc_1400331AB
0x140033172  test    r13b, r13b
0x140033175  jz      short loc_1400331AB
0x140033177  lea     rcx, [r14+190h]; BitMapHeader
0x14003317e  mov     r8d, esi
0x140033181  sub     r8d, r12d; NumberToSet
0x140033184  mov     edx, r12d; StartingIndex
0x140033187  call    cs:__imp_RtlSetBits
0x14003318e  nop     dword ptr [rax+rax+00h]
0x140033193  mov     edi, 1
0x140033198  mov     [rsp+98h+var_58], edi
0x14003319c  mov     r12d, esi
0x14003319f  mov     [rsp+98h+var_54], esi
0x1400331a3  mov     rcx, [rsp+98h+Bcb]
0x1400331ab  add     ebx, 20h ; ' '
0x1400331ae  add     [rsp+98h+var_48], 20h ; ' '
0x1400331b4  inc     esi
0x1400331b6  mov     [rsp+98h+var_4C], esi
0x1400331ba  mov     eax, dword ptr [rsp+98h+arg_10]
0x1400331c1  mov     r13, [rsp+98h+arg_0]
0x1400331c9  jmp     loc_140033029
0x1400331ce  sub     esi, r12d
0x1400331d1  mov     r8d, esi; NumberToClear
0x1400331d4  mov     edx, r12d; StartingIndex
0x1400331d7  cmp     edi, 1
0x1400331da  lea     rdi, [r14+190h]
0x1400331e1  mov     rcx, rdi; BitMapHeader
0x1400331e4  jbe     short loc_1400331F4
0x1400331e6  call    cs:__imp_RtlSetBits
0x1400331ed  nop     dword ptr [rax+rax+00h]
0x1400331f2  jmp     short loc_140033200
0x1400331f4  call    cs:__imp_RtlClearBits
0x1400331fb  nop     dword ptr [rax+rax+00h]
0x140033200  mov     r8d, [r14+18h]
0x140033204  cmp     ebx, r8d
0x140033207  jnb     short loc_140033229
0x140033209  mov     edx, ebx
0x14003320b  shr     edx, 5; StartingIndex
0x14003320e  mov     [rsp+98h+var_54], edx
0x140033212  sub     r8d, ebx
0x140033215  shr     r8d, 5; NumberToClear
0x140033219  mov     rcx, rdi; BitMapHeader
0x14003321c  call    cs:__imp_RtlClearBits
0x140033223  nop     dword ptr [rax+rax+00h]
0x140033228  nop
0x140033229  mov     rcx, [rsp+98h+Bcb]; Bcb
0x140033231  test    rcx, rcx
0x140033234  jz      short loc_140033242
0x140033236  call    cs:__imp_CcUnpinData
0x14003323d  nop     dword ptr [rax+rax+00h]
0x140033242  cmp     r15d, 0FFFFFFFFh
0x140033246  cmovz   r15d, ebx
0x14003324a  mov     [r14+178h], ebx
0x140033251  mov     [r14+17Ch], r15d
0x140033258  add     rsp, 60h
0x14003325c  pop     r15
0x14003325e  pop     r14
0x140033260  pop     r13
0x140033262  pop     r12
0x140033264  pop     rdi
0x140033265  pop     rsi
0x140033266  pop     rbx
0x140033267  retn
0x14005d2cb  push    rbp
0x14005d2cd  sub     rsp, 40h
0x14005d2d1  mov     rbp, rdx
0x14005d2d4  mov     rcx, [rbp+0B8h]; Bcb
0x14005d2db  test    rcx, rcx
0x14005d2de  jz      short loc_14005D2ED
0x14005d2e0  call    cs:__imp_CcUnpinData
0x14005d2e7  nop     dword ptr [rax+rax+00h]
0x14005d2ec  nop
0x14005d2ed  add     rsp, 40h
0x14005d2f1  pop     rbp
0x14005d2f2  retn
```
