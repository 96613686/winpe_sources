# GetValueInfo

- ea: `0x1800403f0`
- end: `0x180040545`
- name: `GetValueInfo`
- size: `341`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003f858`
- `0x1800424cc`
- `0x18004257c`
- `0x180042f6c`

## callees

- `0x1800403f0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1800404fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800404fc`

## pseudocode

```c
void __fastcall GetValueInfo(__int64 a1, _QWORD *a2, _DWORD *a3, _DWORD *a4)
{
  int v4; // r10d
  __int64 v8; // rsi
  int v9; // r10d
  int v10; // r10d
  int v11; // r10d
  __int64 v12; // rax
  int v13; // r10d
  int v14; // r10d
  int v15; // r10d
  int v16; // r10d
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  PUCHAR v20; // rax
  unsigned int v21; // eax

  v4 = *(_DWORD *)a1;
  *a4 = 0;
  v8 = a1;
  if ( v4 > 255 )
    goto LABEL_33;
  if ( v4 > 11 )
  {
    v13 = v4 - 12;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
        v20 = RtlSubAuthorityCountSid(*(PSID *)(a1 + 8));
        *a4 = 1;
        v21 = *v20;
        if ( v21 > 8 )
          v21 = 8;
        *a3 = 4 * v21;
        *a2 = *(_QWORD *)(v8 + 8) + 8LL;
        return;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        v19 = *(_QWORD *)(a1 + 8);
        *a2 = *(_QWORD *)(v19 + 8);
        *a3 = *(_DWORD *)v19;
        return;
      }
      v16 = v15 - 3;
      if ( !v16 )
      {
        v17 = *(_QWORD *)(a1 + 8);
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        *a3 = v18;
        *a2 = v17;
        goto LABEL_24;
      }
      if ( v16 != 1 )
        goto LABEL_33;
      *a3 = 6;
    }
    else
    {
      a1 = *(_QWORD *)(a1 + 8);
      *a3 = *(_DWORD *)a1;
    }
LABEL_23:
    *a2 = *(_QWORD *)(a1 + 8);
LABEL_24:
    *a4 = 1;
    return;
  }
  if ( v4 == 11 )
  {
    *a3 = 16;
    goto LABEL_23;
  }
  if ( v4 )
  {
    v9 = v4 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 )
          {
            v12 = *(_QWORD *)(a1 + 8);
            *a3 = 8;
LABEL_14:
            *a2 = v12;
            return;
          }
LABEL_33:
          __fastfail(5u);
        }
        *a3 = 4;
      }
      else
      {
        *a3 = 2;
      }
    }
    else
    {
      *a3 = 1;
    }
    v12 = a1 + 8;
    goto LABEL_14;
  }
  *a2 = 0;
  *a3 = 0;
}

```

## disassembly

```asm
0x1800403f0  push    rbx
0x1800403f2  push    rsi
0x1800403f3  push    rdi
0x1800403f4  push    r14
0x1800403f6  sub     rsp, 28h
0x1800403fa  mov     r10d, [rcx]
0x1800403fd  mov     rdi, rdx
0x180040400  xor     edx, edx
0x180040402  mov     r14, r9
0x180040405  mov     [r9], edx
0x180040408  mov     rbx, r8
0x18004040b  mov     rsi, rcx
0x18004040e  cmp     r10d, 0FFh
0x180040415  jg      loc_18004053E
0x18004041b  cmp     r10d, 0Bh
0x18004041f  jg      short loc_18004048D
0x180040421  jz      short loc_180040484
0x180040423  test    r10d, r10d
0x180040426  jz      short loc_18004047C
0x180040428  sub     r10d, 1
0x18004042c  jz      short loc_180040463
0x18004042e  sub     r10d, 1
0x180040432  jz      short loc_18004045A
0x180040434  sub     r10d, 1
0x180040438  jz      short loc_180040451
0x18004043a  cmp     r10d, 1
0x18004043e  jnz     loc_18004053E
0x180040444  mov     rax, [rcx+8]
0x180040448  mov     dword ptr [r8], 8
0x18004044f  jmp     short loc_18004046E
0x180040451  mov     dword ptr [r8], 4
0x180040458  jmp     short loc_18004046A
0x18004045a  mov     dword ptr [r8], 2
0x180040461  jmp     short loc_18004046A
0x180040463  mov     dword ptr [r8], 1
0x18004046a  lea     rax, [rcx+8]
0x18004046e  mov     [rdi], rax
0x180040471  add     rsp, 28h
0x180040475  pop     r14
0x180040477  pop     rdi
0x180040478  pop     rsi
0x180040479  pop     rbx
0x18004047a  retn
0x18004047c  mov     [rdi], rdx
0x18004047f  mov     [r8], edx
0x180040482  jmp     short loc_180040471
0x180040484  mov     dword ptr [r8], 10h
0x18004048b  jmp     short loc_1800404BA
0x18004048d  sub     r10d, 0Ch
0x180040491  jz      loc_180040530
0x180040497  sub     r10d, 1
0x18004049b  jz      short loc_1800404F8
0x18004049d  sub     r10d, 1
0x1800404a1  jz      short loc_1800404E3
0x1800404a3  sub     r10d, 3
0x1800404a7  jz      short loc_1800404CA
0x1800404a9  cmp     r10d, 1
0x1800404ad  jnz     loc_18004053E
0x1800404b3  mov     dword ptr [r8], 6
0x1800404ba  mov     rax, [rcx+8]
0x1800404be  mov     [rdi], rax
0x1800404c1  mov     dword ptr [r9], 1
0x1800404c8  jmp     short loc_180040471
0x1800404ca  mov     rcx, [rcx+8]
0x1800404ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800404d2  inc     rax
0x1800404d5  cmp     [rcx+rax*2], dx
0x1800404d9  jnz     short loc_1800404D2
0x1800404db  mov     [r8], eax
0x1800404de  mov     [rdi], rcx
0x1800404e1  jmp     short loc_1800404C1
0x1800404e3  mov     rcx, [rcx+8]
0x1800404e7  mov     rax, [rcx+8]
0x1800404eb  mov     [rdi], rax
0x1800404ee  mov     eax, [rcx]
0x1800404f0  mov     [r8], eax
0x1800404f3  jmp     loc_180040471
0x1800404f8  mov     rcx, [rcx+8]; Sid
0x1800404fc  call    cs:__imp_RtlSubAuthorityCountSid
0x180040503  nop     dword ptr [rax+rax+00h]
0x180040508  mov     ecx, 8
0x18004050d  mov     dword ptr [r14], 1
0x180040514  movzx   eax, byte ptr [rax]
0x180040517  cmp     eax, ecx
0x180040519  cmova   eax, ecx
0x18004051c  shl     eax, 2
0x18004051f  mov     [rbx], eax
0x180040521  mov     rax, [rsi+8]
0x180040525  add     rax, rcx
0x180040528  mov     [rdi], rax
0x18004052b  jmp     loc_180040471
0x180040530  mov     rcx, [rcx+8]
0x180040534  mov     eax, [rcx]
0x180040536  mov     [r8], eax
0x180040539  jmp     loc_1800404BA
0x18004053e  mov     ecx, 5
0x180040543  int     29h; Win8: RtlFailFast(ecx)
```
