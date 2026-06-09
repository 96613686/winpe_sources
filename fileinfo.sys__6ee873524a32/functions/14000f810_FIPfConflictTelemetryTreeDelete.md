# FIPfConflictTelemetryTreeDelete

- ea: `0x14000f810`
- end: `0x14000f9b2`
- name: `FIPfConflictTelemetryTreeDelete`
- size: `418`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e370`
- `0x14000f510`

## callees

- `0x14000f01c`
- `0x14000f810`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f8ad`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f967`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f8ad`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f967`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f8f3`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000f8f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f99c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f99c`

## pseudocode

```c
void __fastcall FIPfConflictTelemetryTreeDelete(unsigned __int16 *P, __int64 a2)
{
  unsigned __int16 *v3; // rbx
  __int64 v4; // r8
  unsigned int v5; // eax
  unsigned __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbp
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rax

  v3 = P;
  if ( !a2 )
  {
    if ( !P )
      return;
    goto LABEL_48;
  }
  FIPfConflictTelemetryAdd(a2 + 40, P);
  v5 = *(_DWORD *)(a2 + 32);
  v6 = a2 + 16;
  if ( v5 < 0xF )
  {
    *(_DWORD *)(a2 + 32) = v5 + 1;
    v7 = *(_QWORD *)v6;
    if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
    {
      if ( v7 )
        v7 ^= v6;
    }
    LOBYTE(v4) = 0;
    if ( v7 )
    {
      v4 = v3[16];
      while ( 1 )
      {
        if ( (unsigned __int16)v4 < *(_WORD *)(v7 + 32) )
        {
          v8 = *(_QWORD *)v7;
          if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
          {
            if ( !v8 )
              goto LABEL_19;
            v8 ^= v7;
          }
          if ( !v8 )
          {
LABEL_19:
            LOBYTE(v4) = 0;
            break;
          }
        }
        else
        {
          v8 = *(_QWORD *)(v7 + 8);
          if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
          {
            if ( !v8 )
              goto LABEL_13;
            v8 ^= v7;
          }
          if ( !v8 )
          {
LABEL_13:
            LOBYTE(v4) = 1;
            break;
          }
        }
        v7 = v8;
      }
    }
    RtlRbInsertNodeEx(a2 + 16, v7, v4, v3);
    return;
  }
  v9 = *(_QWORD *)(a2 + 24);
  if ( (v9 & 1) != 0 )
  {
    if ( v9 == 1 )
      v10 = 0;
    else
      v10 = v9 ^ (v6 | 1);
  }
  else
  {
    v10 = *(_QWORD *)(a2 + 24);
  }
  if ( *(_WORD *)(v10 + 32) < v3[16] )
  {
    RtlRbRemoveNode(a2 + 16, v10);
    v12 = *(_QWORD *)v6;
    if ( (*(_BYTE *)(a2 + 24) & 1) != 0 && v12 )
      v12 ^= v6;
    LOBYTE(v11) = 0;
    if ( v12 )
    {
      v11 = v3[16];
      while ( 1 )
      {
        if ( (unsigned __int16)v11 < *(_WORD *)(v12 + 32) )
        {
          v13 = *(_QWORD *)v12;
          if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
          {
            if ( !v13 )
              goto LABEL_43;
            v13 ^= v12;
          }
          if ( !v13 )
          {
LABEL_43:
            LOBYTE(v11) = 0;
            break;
          }
        }
        else
        {
          v13 = *(_QWORD *)(v12 + 8);
          if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
          {
            if ( !v13 )
              goto LABEL_37;
            v13 ^= v12;
          }
          if ( !v13 )
          {
LABEL_37:
            LOBYTE(v11) = 1;
            break;
          }
        }
        v12 = v13;
      }
    }
    RtlRbInsertNodeEx(a2 + 16, v12, v11, v3);
    v3 = (unsigned __int16 *)v10;
  }
  if ( v3 )
  {
    ++*(_DWORD *)(a2 + 456);
    FIPfConflictTelemetryAdd(a2 + 248, v3);
LABEL_48:
    ExFreePoolWithTag(v3, 0);
  }
}

```

## disassembly

```asm
0x14000f810  push    rbx
0x14000f812  push    rbp
0x14000f813  push    rsi
0x14000f814  push    rdi
0x14000f815  sub     rsp, 28h
0x14000f819  mov     rsi, rdx
0x14000f81c  mov     rbx, rcx
0x14000f81f  test    rdx, rdx
0x14000f822  jz      loc_14000F992
0x14000f828  lea     rcx, [rdx+28h]
0x14000f82c  mov     rdx, rbx
0x14000f82f  call    FIPfConflictTelemetryAdd
0x14000f834  mov     eax, [rsi+20h]
0x14000f837  lea     rdi, [rsi+10h]
0x14000f83b  cmp     eax, 0Fh
0x14000f83e  jnb     short loc_14000F8BE
0x14000f840  inc     eax
0x14000f842  mov     [rsi+20h], eax
0x14000f845  test    byte ptr [rdi+8], 1
0x14000f849  mov     rdx, [rdi]
0x14000f84c  jz      short loc_14000F856
0x14000f84e  test    rdx, rdx
0x14000f851  jz      short loc_14000F856
0x14000f853  xor     rdx, rdi
0x14000f856  xor     r8b, r8b
0x14000f859  test    rdx, rdx
0x14000f85c  jz      short loc_14000F8A7
0x14000f85e  movzx   ecx, byte ptr [rdi+8]
0x14000f862  movzx   r8d, word ptr [rbx+20h]
0x14000f867  and     ecx, 1
0x14000f86a  cmp     r8w, [rdx+20h]
0x14000f86f  jb      short loc_14000F88B
0x14000f871  mov     rax, [rdx+8]
0x14000f875  test    ecx, ecx
0x14000f877  jz      short loc_14000F881
0x14000f879  test    rax, rax
0x14000f87c  jz      short loc_14000F886
0x14000f87e  xor     rax, rdx
0x14000f881  test    rax, rax
0x14000f884  jnz     short loc_14000F89F
0x14000f886  mov     r8b, 1
0x14000f889  jmp     short loc_14000F8A7
0x14000f88b  mov     rax, [rdx]
0x14000f88e  test    ecx, ecx
0x14000f890  jz      short loc_14000F89A
0x14000f892  test    rax, rax
0x14000f895  jz      short loc_14000F8A4
0x14000f897  xor     rax, rdx
0x14000f89a  test    rax, rax
0x14000f89d  jz      short loc_14000F8A4
0x14000f89f  mov     rdx, rax
0x14000f8a2  jmp     short loc_14000F86A
0x14000f8a4  xor     r8b, r8b
0x14000f8a7  mov     r9, rbx
0x14000f8aa  mov     rcx, rdi
0x14000f8ad  call    cs:__imp_RtlRbInsertNodeEx
0x14000f8b4  nop     dword ptr [rax+rax+00h]
0x14000f8b9  jmp     loc_14000F9A8
0x14000f8be  mov     rax, [rdi+8]
0x14000f8c2  test    al, 1
0x14000f8c4  jz      short loc_14000F8DC
0x14000f8c6  cmp     rax, 1
0x14000f8ca  jnz     short loc_14000F8D0
0x14000f8cc  xor     ebp, ebp
0x14000f8ce  jmp     short loc_14000F8DF
0x14000f8d0  mov     rbp, rdi
0x14000f8d3  or      rbp, 1
0x14000f8d7  xor     rbp, rax
0x14000f8da  jmp     short loc_14000F8DF
0x14000f8dc  mov     rbp, rax
0x14000f8df  movzx   eax, word ptr [rbx+20h]
0x14000f8e3  cmp     [rbp+20h], ax
0x14000f8e7  jnb     loc_14000F976
0x14000f8ed  mov     rdx, rbp
0x14000f8f0  mov     rcx, rdi
0x14000f8f3  call    cs:__imp_RtlRbRemoveNode
0x14000f8fa  nop     dword ptr [rax+rax+00h]
0x14000f8ff  test    byte ptr [rdi+8], 1
0x14000f903  mov     rdx, [rdi]
0x14000f906  jz      short loc_14000F910
0x14000f908  test    rdx, rdx
0x14000f90b  jz      short loc_14000F910
0x14000f90d  xor     rdx, rdi
0x14000f910  xor     r8b, r8b
0x14000f913  test    rdx, rdx
0x14000f916  jz      short loc_14000F961
0x14000f918  movzx   ecx, byte ptr [rdi+8]
0x14000f91c  movzx   r8d, word ptr [rbx+20h]
0x14000f921  and     ecx, 1
0x14000f924  cmp     r8w, [rdx+20h]
0x14000f929  jb      short loc_14000F945
0x14000f92b  mov     rax, [rdx+8]
0x14000f92f  test    ecx, ecx
0x14000f931  jz      short loc_14000F93B
0x14000f933  test    rax, rax
0x14000f936  jz      short loc_14000F940
0x14000f938  xor     rax, rdx
0x14000f93b  test    rax, rax
0x14000f93e  jnz     short loc_14000F959
0x14000f940  mov     r8b, 1
0x14000f943  jmp     short loc_14000F961
0x14000f945  mov     rax, [rdx]
0x14000f948  test    ecx, ecx
0x14000f94a  jz      short loc_14000F954
0x14000f94c  test    rax, rax
0x14000f94f  jz      short loc_14000F95E
0x14000f951  xor     rax, rdx
0x14000f954  test    rax, rax
0x14000f957  jz      short loc_14000F95E
0x14000f959  mov     rdx, rax
0x14000f95c  jmp     short loc_14000F924
0x14000f95e  xor     r8b, r8b
0x14000f961  mov     r9, rbx
0x14000f964  mov     rcx, rdi
0x14000f967  call    cs:__imp_RtlRbInsertNodeEx
0x14000f96e  nop     dword ptr [rax+rax+00h]
0x14000f973  mov     rbx, rbp
0x14000f976  test    rbx, rbx
0x14000f979  jz      short loc_14000F9A8
0x14000f97b  inc     dword ptr [rsi+1C8h]
0x14000f981  lea     rcx, [rsi+0F8h]
0x14000f988  mov     rdx, rbx
0x14000f98b  call    FIPfConflictTelemetryAdd
0x14000f990  jmp     short loc_14000F997
0x14000f992  test    rbx, rbx
0x14000f995  jz      short loc_14000F9A8
0x14000f997  xor     edx, edx; Tag
0x14000f999  mov     rcx, rbx; P
0x14000f99c  call    cs:__imp_ExFreePoolWithTag
0x14000f9a3  nop     dword ptr [rax+rax+00h]
0x14000f9a8  add     rsp, 28h
0x14000f9ac  pop     rdi
0x14000f9ad  pop     rsi
0x14000f9ae  pop     rbp
0x14000f9af  pop     rbx
0x14000f9b0  retn
```
