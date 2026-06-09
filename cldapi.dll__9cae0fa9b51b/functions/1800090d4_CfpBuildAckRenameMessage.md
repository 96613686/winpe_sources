# CfpBuildAckRenameMessage

- ea: `0x1800090d4`
- end: `0x1800092f0`
- name: `CfpBuildAckRenameMessage`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ac50`

## callees

- `0x1800090d4`
- `0x1800092f8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800091a4`
- `ntdll!RtlNtStatusToDosError` at `0x180009226`
- `ntdll!RtlNtStatusToDosError` at `0x1800092ab`
- `ntdll!RtlNtStatusToDosError` at `0x1800091a4`
- `ntdll!RtlNtStatusToDosError` at `0x180009226`
- `ntdll!RtlNtStatusToDosError` at `0x1800092ab`

## pseudocode

```c
__int64 __fastcall CfpBuildAckRenameMessage(__int64 a1, unsigned int a2, __int64 a3, int a4, int a5)
{
  unsigned __int64 v6; // rsi
  int v8; // r10d
  _WORD *v9; // rbp
  NTSTATUS v10; // edi
  NTSTATUS v11; // ecx
  __int64 v12; // rdx
  unsigned int v13; // eax
  signed int v14; // eax
  NTSTATUS v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rax
  signed int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  signed int v21; // eax

  v6 = a2;
  v8 = a2 < 0xC8 ? 0x57 : 0;
  if ( a2 < 0xC8 )
    v8 = (a2 < 0xC8 ? 0x57 : 0) | 0x80070000;
  if ( v8 < 0 )
    return (unsigned int)v8;
  v8 = CfpBuildMessageHeader(a1, a2, a3, 513);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v9 = (_WORD *)(a1 + 14);
  v10 = -1073741789;
  if ( (unsigned int)v6 < 0x18 )
    goto LABEL_9;
  if ( *v9 <= 0xAu )
  {
    v11 = -1073741811;
    goto LABEL_14;
  }
  if ( (unsigned int)v6 < 0x68 || (v12 = *(unsigned int *)(a1 + 8), ((v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v6) )
  {
LABEL_9:
    v11 = -1073741789;
  }
  else
  {
    v13 = (v12 + 3) & 0xFFFFFFFC;
    *(_DWORD *)(a1 + 8) = v13;
    if ( *(_WORD *)(a1 + 96) )
      *(_WORD *)(a1 + 12) |= 1u;
    *(_DWORD *)(a1 + 100) = v13;
    *(_DWORD *)(a1 + 96) = 262154;
    *(_DWORD *)(v13 + a1) = a5;
    v11 = 0;
    *(_DWORD *)(a1 + 8) += 4;
  }
LABEL_14:
  v14 = RtlNtStatusToDosError(v11);
  v8 = v14;
  if ( v14 > 0 )
    v8 = (unsigned __int16)v14 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( (unsigned int)v6 >= 0x18 )
    {
      if ( *v9 <= 5u )
      {
        v15 = -1073741811;
        goto LABEL_26;
      }
      if ( (unsigned int)v6 >= 0x40 )
      {
        v16 = *(unsigned int *)(a1 + 8);
        if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v6 )
        {
          v17 = ((_DWORD)v16 + 3) & 0xFFFFFFFC;
          *(_DWORD *)(a1 + 8) = v17;
          if ( *(_WORD *)(a1 + 56) )
            *(_WORD *)(a1 + 12) |= 1u;
          *(_DWORD *)(a1 + 56) = 262154;
          v15 = 0;
          *(_DWORD *)(a1 + 60) = v17;
          *(_DWORD *)(v17 + a1) = a4;
          *(_DWORD *)(a1 + 8) += 4;
          goto LABEL_26;
        }
      }
    }
    v15 = -1073741789;
LABEL_26:
    v18 = RtlNtStatusToDosError(v15);
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    if ( v8 >= 0 )
    {
      if ( (unsigned int)v6 >= 0x18 )
      {
        if ( *v9 > 0xDu )
        {
          if ( (unsigned int)v6 >= 0x80 )
          {
            v19 = *(unsigned int *)(a1 + 8);
            if ( ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v6 )
            {
              v20 = ((_DWORD)v19 + 3) & 0xFFFFFFFC;
              *(_DWORD *)(a1 + 8) = v20;
              if ( *(_WORD *)(a1 + 120) )
                *(_WORD *)(a1 + 12) |= 1u;
              *(_DWORD *)(a1 + 120) = 262154;
              v10 = 0;
              *(_DWORD *)(a1 + 124) = v20;
              *(_DWORD *)(v20 + a1) = 5;
              *(_DWORD *)(a1 + 8) += 4;
            }
          }
        }
        else
        {
          v10 = -1073741811;
        }
      }
      v21 = RtlNtStatusToDosError(v10);
      v8 = v21;
      if ( v21 > 0 )
        v8 = (unsigned __int16)v21 | 0x80070000;
      if ( v8 >= 0 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        *(_WORD *)(a1 + 12) &= ~2u;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800090d4  push    rbx
0x1800090d6  push    rbp
0x1800090d7  push    rsi
0x1800090d8  push    rdi
0x1800090d9  push    r12
0x1800090db  push    r13
0x1800090dd  push    r14
0x1800090df  push    r15
0x1800090e1  sub     rsp, 28h
0x1800090e5  mov     rbx, rcx
0x1800090e8  mov     esi, edx
0x1800090ea  mov     ecx, 0C8h
0x1800090ef  mov     r13d, 80070000h
0x1800090f5  cmp     edx, ecx
0x1800090f7  mov     r14d, r9d
0x1800090fa  sbb     r10d, r10d
0x1800090fd  and     r10d, 57h
0x180009101  mov     eax, r10d
0x180009104  or      eax, r13d
0x180009107  cmp     edx, ecx
0x180009109  cmovb   r10d, eax
0x18000910d  xor     r15d, r15d
0x180009110  test    r10d, r10d
0x180009113  js      loc_1800092DB
0x180009119  mov     r9d, 201h
0x18000911f  mov     edx, esi
0x180009121  mov     rcx, rbx
0x180009124  call    CfpBuildMessageHeader
0x180009129  mov     r10d, eax
0x18000912c  test    eax, eax
0x18000912e  js      loc_1800092DB
0x180009134  lea     rbp, [rbx+0Eh]
0x180009138  mov     edi, 0C0000023h
0x18000913d  lea     r8d, [r15+0Ah]
0x180009141  lea     r12d, [r15+4]
0x180009145  cmp     esi, 18h
0x180009148  jb      short loc_18000915B
0x18000914a  cmp     r8w, [rbp+0]
0x18000914f  jb      short loc_180009156
0x180009151  lea     ecx, [rdi-16h]
0x180009154  jmp     short loc_1800091A4
0x180009156  cmp     esi, 68h ; 'h'
0x180009159  jnb     short loc_18000915F
0x18000915b  mov     ecx, edi
0x18000915d  jmp     short loc_1800091A4
0x18000915f  mov     edx, [rbx+8]
0x180009162  lea     rcx, [rdx+3]
0x180009166  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000916a  add     rcx, r12
0x18000916d  cmp     rcx, rsi
0x180009170  ja      short loc_18000915B
0x180009172  lea     eax, [rdx+3]
0x180009175  and     eax, 0FFFFFFFCh
0x180009178  mov     [rbx+8], eax
0x18000917b  cmp     [rbx+60h], r15w
0x180009180  jz      short loc_180009187
0x180009182  or      word ptr [rbx+0Ch], 1
0x180009187  mov     ecx, eax
0x180009189  mov     [rbx+64h], eax
0x18000918c  mov     eax, [rsp+68h+arg_20]
0x180009193  mov     dword ptr [rbx+60h], 4000Ah
0x18000919a  mov     [rcx+rbx], eax
0x18000919d  mov     ecx, r15d; Status
0x1800091a0  add     [rbx+8], r12d
0x1800091a4  call    cs:__imp_RtlNtStatusToDosError
0x1800091ab  nop     dword ptr [rax+rax+00h]
0x1800091b0  mov     r10d, eax
0x1800091b3  test    eax, eax
0x1800091b5  jle     short loc_1800091BE
0x1800091b7  movzx   r10d, ax
0x1800091bb  or      r10d, r13d
0x1800091be  test    r10d, r10d
0x1800091c1  js      loc_1800092DB
0x1800091c7  mov     r13d, 5
0x1800091cd  cmp     esi, 18h
0x1800091d0  jnb     short loc_1800091D6
0x1800091d2  mov     ecx, edi
0x1800091d4  jmp     short loc_180009226
0x1800091d6  cmp     r13w, [rbp+0]
0x1800091db  jb      short loc_1800091E4
0x1800091dd  mov     ecx, 0C000000Dh
0x1800091e2  jmp     short loc_180009226
0x1800091e4  cmp     esi, 40h ; '@'
0x1800091e7  jb      short loc_1800091D2
0x1800091e9  mov     edx, [rbx+8]
0x1800091ec  lea     rcx, [rdx+3]
0x1800091f0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800091f4  add     rcx, r12
0x1800091f7  cmp     rcx, rsi
0x1800091fa  ja      short loc_1800091D2
0x1800091fc  lea     eax, [rdx+3]
0x1800091ff  and     eax, 0FFFFFFFCh
0x180009202  mov     [rbx+8], eax
0x180009205  cmp     [rbx+38h], r15w
0x18000920a  jz      short loc_180009211
0x18000920c  or      word ptr [rbx+0Ch], 1
0x180009211  mov     dword ptr [rbx+38h], 4000Ah
0x180009218  mov     ecx, r15d; Status
0x18000921b  mov     [rbx+3Ch], eax
0x18000921e  mov     [rax+rbx], r14d
0x180009222  add     [rbx+8], r12d
0x180009226  call    cs:__imp_RtlNtStatusToDosError
0x18000922d  nop     dword ptr [rax+rax+00h]
0x180009232  mov     r10d, eax
0x180009235  test    eax, eax
0x180009237  jle     short loc_180009244
0x180009239  movzx   r10d, ax
0x18000923d  or      r10d, 80070000h
0x180009244  test    r10d, r10d
0x180009247  js      loc_1800092DB
0x18000924d  cmp     esi, 18h
0x180009250  jb      short loc_1800092A9
0x180009252  mov     eax, 0Dh
0x180009257  cmp     ax, [rbp+0]
0x18000925b  jb      short loc_180009264
0x18000925d  mov     edi, 0C000000Dh
0x180009262  jmp     short loc_1800092A9
0x180009264  cmp     esi, 80h
0x18000926a  jb      short loc_1800092A9
0x18000926c  mov     edx, [rbx+8]
0x18000926f  lea     rcx, [rdx+3]
0x180009273  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180009277  add     rcx, r12
0x18000927a  cmp     rcx, rsi
0x18000927d  ja      short loc_1800092A9
0x18000927f  lea     eax, [rdx+3]
0x180009282  and     eax, 0FFFFFFFCh
0x180009285  mov     [rbx+8], eax
0x180009288  cmp     [rbx+78h], r15w
0x18000928d  jz      short loc_180009294
0x18000928f  or      word ptr [rbx+0Ch], 1
0x180009294  mov     dword ptr [rbx+78h], 4000Ah
0x18000929b  mov     edi, r15d
0x18000929e  mov     [rbx+7Ch], eax
0x1800092a1  mov     [rax+rbx], r13d
0x1800092a5  add     [rbx+8], r12d
0x1800092a9  mov     ecx, edi; Status
0x1800092ab  call    cs:__imp_RtlNtStatusToDosError
0x1800092b2  nop     dword ptr [rax+rax+00h]
0x1800092b7  mov     r10d, eax
0x1800092ba  test    eax, eax
0x1800092bc  jle     short loc_1800092C9
0x1800092be  movzx   r10d, ax
0x1800092c2  or      r10d, 80070000h
0x1800092c9  test    r10d, r10d
0x1800092cc  js      short loc_1800092DB
0x1800092ce  mov     eax, 0FFFDh
0x1800092d3  mov     [rbx+4], r15d
0x1800092d7  and     [rbx+0Ch], ax
0x1800092db  mov     eax, r10d
0x1800092de  add     rsp, 28h
0x1800092e2  pop     r15
0x1800092e4  pop     r14
0x1800092e6  pop     r13
0x1800092e8  pop     r12
0x1800092ea  pop     rdi
0x1800092eb  pop     rsi
0x1800092ec  pop     rbp
0x1800092ed  pop     rbx
0x1800092ee  retn
```
