# NdisWanCreateConnectionTable

- ea: `0x14000c6e0`
- end: `0x14000c929`
- name: `NdisWanCreateConnectionTable`
- size: `585`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b2cc`
- `0x14000b3fc`
- `0x140039008`

## callees

- `0x14000a2c0`
- `0x14000a5f4`
- `0x14000c6e0`
- `0x140016400`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c88b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c88b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c736`
- `ntoskrnl!ExAllocatePool2` at `0x14000c736`

## pseudocode

```c
__int64 __fastcall NdisWanCreateConnectionTable(unsigned int a1)
{
  __int64 v1; // rax
  __int64 v3; // rbp
  unsigned int v4; // ebx
  unsigned int v5; // ecx
  unsigned int *Pool2; // rax
  unsigned int *v7; // rdi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned int *v11; // rbx
  unsigned int *v12; // rsi
  unsigned int *v13; // rax
  unsigned int *v14; // rbp
  _QWORD *v15; // rcx
  unsigned int *v16; // rax
  __int64 v17; // rdx
  unsigned int **v18; // rcx
  _QWORD *v19; // rcx
  unsigned int *v20; // rax
  __int64 v21; // rdx
  unsigned int **v22; // rcx

  v1 = a1 + 1;
  if ( (unsigned int)v1 < a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, a1);
    }
    return 3221225626LL;
  }
  v3 = 2 * v1;
  v4 = -1;
  if ( (unsigned __int64)(8 * v1) > 0xFFFFFFFF || (v5 = 16 * v1, 16 * (int)v1 < (unsigned int)(8 * v1)) || v5 + 72 < v5 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225626LL;
    }
    v9 = 36;
    goto LABEL_30;
  }
  v4 = v5 + 72;
  Pool2 = (unsigned int *)ExAllocatePool2(64, v5 + 72, 1332633943);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225626LL;
    }
    v9 = 37;
LABEL_30:
    WPP_SF_dd(v8->AttachedDevice, v9, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, v4, a1);
    return 3221225626LL;
  }
  *Pool2 = v4;
  v10 = Pool2 + 18;
  Pool2[1] = a1;
  v11 = Pool2 + 10;
  v12 = Pool2 + 6;
  Pool2[5] = 1;
  Pool2[3] = 1;
  v13 = &Pool2[v3 + 18];
  v14 = (unsigned int *)ConnectionTable;
  *((_QWORD *)v7 + 4) = v7 + 6;
  *((_QWORD *)v7 + 3) = v7 + 6;
  *((_QWORD *)v7 + 6) = v7 + 10;
  *((_QWORD *)v7 + 5) = v7 + 10;
  *((_QWORD *)v7 + 7) = v7 + 18;
  *((_QWORD *)v7 + 8) = v13;
  if ( v14 )
  {
    v7[2] = v14[2];
    v7[4] = v14[4];
    v7[3] = v14[3];
    v7[5] = v14[5];
    memmove(v10, *((const void **)v14 + 7), 8LL * v14[1]);
    memmove(*((void **)v7 + 8), *((const void **)v14 + 8), 8LL * v14[1]);
    while ( 1 )
    {
      v15 = v14 + 6;
      v16 = (unsigned int *)*((_QWORD *)v14 + 3);
      if ( v16 == v14 + 6 )
        break;
      if ( *((_QWORD **)v16 + 1) != v15
        || (v17 = *(_QWORD *)v16, *(unsigned int **)(*(_QWORD *)v16 + 8LL) != v16)
        || (*v15 = v17, *(_QWORD *)(v17 + 8) = v15, v18 = (unsigned int **)*((_QWORD *)v7 + 4), *v18 != v12) )
      {
LABEL_22:
        __fastfail(3u);
      }
      *(_QWORD *)v16 = v12;
      *((_QWORD *)v16 + 1) = v18;
      *v18 = v16;
      *((_QWORD *)v7 + 4) = v16;
    }
    while ( 1 )
    {
      v19 = v14 + 10;
      v20 = (unsigned int *)*((_QWORD *)v14 + 5);
      if ( v20 == v14 + 10 )
        break;
      if ( *((_QWORD **)v20 + 1) != v19 )
        goto LABEL_22;
      v21 = *(_QWORD *)v20;
      if ( *(unsigned int **)(*(_QWORD *)v20 + 8LL) != v20 )
        goto LABEL_22;
      *v19 = v21;
      *(_QWORD *)(v21 + 8) = v19;
      v22 = (unsigned int **)*((_QWORD *)v7 + 6);
      if ( *v22 != v11 )
        goto LABEL_22;
      *(_QWORD *)v20 = v11;
      *((_QWORD *)v20 + 1) = v22;
      *v22 = v20;
      *((_QWORD *)v7 + 6) = v20;
    }
    ConnectionTable = v7;
    ExFreePoolWithTag(v14, 0);
  }
  else
  {
    ConnectionTable = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x14000c6e0  push    rbx
0x14000c6e2  push    rbp
0x14000c6e3  push    rsi
0x14000c6e4  push    rdi
0x14000c6e5  sub     rsp, 38h
0x14000c6e9  lea     eax, [rcx+1]
0x14000c6ec  mov     esi, ecx
0x14000c6ee  cmp     eax, ecx
0x14000c6f0  jb      loc_14000C8E2
0x14000c6f6  lea     rbp, ds:0[rax*8]
0x14000c6fe  mov     ebx, 0FFFFFFFFh
0x14000c703  cmp     rbp, rbx
0x14000c706  ja      loc_14000C8A4
0x14000c70c  lea     ecx, ds:0[rbp*2]
0x14000c713  cmp     ecx, ebp
0x14000c715  jb      loc_14000C8A4
0x14000c71b  lea     eax, [rcx+48h]
0x14000c71e  cmp     eax, ecx
0x14000c720  cmovnb  ebx, eax
0x14000c723  jb      loc_14000C8A4
0x14000c729  mov     edx, ebx
0x14000c72b  mov     ecx, 40h ; '@'
0x14000c730  mov     r8d, 4F6E6157h
0x14000c736  call    cs:__imp_ExAllocatePool2
0x14000c73d  nop     dword ptr [rax+rax+00h]
0x14000c742  mov     rdi, rax
0x14000c745  test    rax, rax
0x14000c748  jnz     short loc_14000C77E
0x14000c74a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c751  lea     rax, WPP_GLOBAL_Control
0x14000c758  cmp     rcx, rax
0x14000c75b  jz      loc_14000C91A
0x14000c761  mov     eax, [rcx+2Ch]
0x14000c764  test    al, 40h
0x14000c766  jz      loc_14000C91A
0x14000c76c  cmp     byte ptr [rcx+29h], 2
0x14000c770  jb      loc_14000C91A
0x14000c776  lea     edx, [rdi+25h]
0x14000c779  jmp     loc_14000C8C9
0x14000c77e  mov     [rax], ebx
0x14000c780  lea     rcx, [rdi+48h]; void *
0x14000c784  mov     [rax+4], esi
0x14000c787  lea     rbx, [rdi+28h]
0x14000c78b  mov     eax, 1
0x14000c790  lea     rsi, [rdi+18h]
0x14000c794  mov     [rdi+14h], eax
0x14000c797  mov     [rdi+0Ch], eax
0x14000c79a  lea     rax, [rcx+rbp]
0x14000c79e  mov     rbp, cs:ConnectionTable
0x14000c7a5  mov     [rsi+8], rsi
0x14000c7a9  mov     [rsi], rsi
0x14000c7ac  mov     [rbx+8], rbx
0x14000c7b0  mov     [rbx], rbx
0x14000c7b3  mov     [rdi+38h], rcx
0x14000c7b7  mov     [rdi+40h], rax
0x14000c7bb  test    rbp, rbp
0x14000c7be  jz      loc_14000C899
0x14000c7c4  mov     eax, [rbp+8]
0x14000c7c7  mov     [rdi+8], eax
0x14000c7ca  mov     eax, [rbp+10h]
0x14000c7cd  mov     [rdi+10h], eax
0x14000c7d0  mov     eax, [rbp+0Ch]
0x14000c7d3  mov     [rdi+0Ch], eax
0x14000c7d6  mov     eax, [rbp+14h]
0x14000c7d9  mov     [rdi+14h], eax
0x14000c7dc  mov     r8d, [rbp+4]
0x14000c7e0  mov     rdx, [rbp+38h]; Src
0x14000c7e4  shl     r8, 3; Size
0x14000c7e8  call    memmove
0x14000c7ed  mov     r8d, [rbp+4]
0x14000c7f1  mov     rdx, [rbp+40h]; Src
0x14000c7f5  mov     rcx, [rdi+40h]; void *
0x14000c7f9  shl     r8, 3; Size
0x14000c7fd  call    memmove
0x14000c802  lea     rcx, [rbp+18h]
0x14000c806  mov     rax, [rcx]
0x14000c809  cmp     rax, rcx
0x14000c80c  jz      short loc_14000C83D
0x14000c80e  cmp     [rax+8], rcx
0x14000c812  jnz     short loc_14000C878
0x14000c814  mov     rdx, [rax]
0x14000c817  cmp     [rdx+8], rax
0x14000c81b  jnz     short loc_14000C878
0x14000c81d  mov     [rcx], rdx
0x14000c820  mov     [rdx+8], rcx
0x14000c824  mov     rcx, [rsi+8]
0x14000c828  cmp     [rcx], rsi
0x14000c82b  jnz     short loc_14000C878
0x14000c82d  mov     [rax], rsi
0x14000c830  mov     [rax+8], rcx
0x14000c834  mov     [rcx], rax
0x14000c837  mov     [rsi+8], rax
0x14000c83b  jmp     short loc_14000C802
0x14000c83d  lea     rcx, [rbp+28h]
0x14000c841  mov     rax, [rcx]
0x14000c844  cmp     rax, rcx
0x14000c847  jz      short loc_14000C87F
0x14000c849  cmp     [rax+8], rcx
0x14000c84d  jnz     short loc_14000C878
0x14000c84f  mov     rdx, [rax]
0x14000c852  cmp     [rdx+8], rax
0x14000c856  jnz     short loc_14000C878
0x14000c858  mov     [rcx], rdx
0x14000c85b  mov     [rdx+8], rcx
0x14000c85f  mov     rcx, [rbx+8]
0x14000c863  cmp     [rcx], rbx
0x14000c866  jnz     short loc_14000C878
0x14000c868  mov     [rax], rbx
0x14000c86b  mov     [rax+8], rcx
0x14000c86f  mov     [rcx], rax
0x14000c872  mov     [rbx+8], rax
0x14000c876  jmp     short loc_14000C83D
0x14000c878  mov     ecx, 3
0x14000c87d  int     29h; Win8: RtlFailFast(ecx)
0x14000c87f  xor     edx, edx; Tag
0x14000c881  mov     cs:ConnectionTable, rdi
0x14000c888  mov     rcx, rbp; P
0x14000c88b  call    cs:__imp_ExFreePoolWithTag
0x14000c892  nop     dword ptr [rax+rax+00h]
0x14000c897  jmp     short loc_14000C8A0
0x14000c899  mov     cs:ConnectionTable, rdi
0x14000c8a0  xor     eax, eax
0x14000c8a2  jmp     short loc_14000C91F
0x14000c8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8ab  lea     rax, WPP_GLOBAL_Control
0x14000c8b2  cmp     rcx, rax
0x14000c8b5  jz      short loc_14000C91A
0x14000c8b7  mov     eax, [rcx+2Ch]
0x14000c8ba  test    al, 40h
0x14000c8bc  jz      short loc_14000C91A
0x14000c8be  cmp     byte ptr [rcx+29h], 2
0x14000c8c2  jb      short loc_14000C91A
0x14000c8c4  mov     edx, 24h ; '$'
0x14000c8c9  mov     rcx, [rcx+18h]
0x14000c8cd  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c8d4  mov     r9d, ebx
0x14000c8d7  mov     [rsp+58h+var_38], esi
0x14000c8db  call    WPP_SF_dd
0x14000c8e0  jmp     short loc_14000C91A
0x14000c8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8e9  lea     rax, WPP_GLOBAL_Control
0x14000c8f0  cmp     rcx, rax
0x14000c8f3  jz      short loc_14000C91A
0x14000c8f5  mov     eax, [rcx+2Ch]
0x14000c8f8  test    al, 40h
0x14000c8fa  jz      short loc_14000C91A
0x14000c8fc  cmp     byte ptr [rcx+29h], 2
0x14000c900  jb      short loc_14000C91A
0x14000c902  mov     rcx, [rcx+18h]
0x14000c906  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c90d  mov     edx, 23h ; '#'
0x14000c912  mov     r9d, esi
0x14000c915  call    WPP_SF_d
0x14000c91a  mov     eax, 0C000009Ah
0x14000c91f  add     rsp, 38h
0x14000c923  pop     rdi
0x14000c924  pop     rsi
0x14000c925  pop     rbp
0x14000c926  pop     rbx
0x14000c927  retn
```
