# CArray<CompInfo1 *,CompInfo1 * const &>::SetSize(int,int)

- ea: `0x18003188c`
- end: `0x1800319d4`
- name: `?SetSize@?$CArray@PEAUCompInfo1@@AEBQEAU1@@@QEAAXHH@Z`
- size: `328`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d1a0`
- `0x180030710`

## callees

- `0x18002cc8c`
- `0x18003188c`
- `0x18005582e`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800318b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800318b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800319ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003197d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003197d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CArray<CompInfo1 *,CompInfo1 * const &>::SetSize(__int64 a1, int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rcx
  void *v5; // rax
  int v6; // r8d
  __int64 v7; // rdx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // edi
  char *v12; // rbx

  v2 = a2;
  v4 = *(_QWORD *)(a1 + 8);
  if ( a2 )
  {
    if ( v4 )
    {
      v6 = *(_DWORD *)(a1 + 20);
      if ( a2 > v6 )
      {
        v8 = *(_DWORD *)(a1 + 24);
        if ( !v8 )
        {
          v9 = *(_DWORD *)(a1 + 16) / 8;
          v8 = 4;
          if ( v9 >= 4 )
          {
            v8 = *(_DWORD *)(a1 + 16) / 8;
            if ( v9 > 1024 )
              v8 = 1024;
          }
        }
        v10 = v6 + v8;
        v11 = a2;
        if ( a2 < v10 )
          v11 = v10;
        v12 = (char *)CoTaskMemAlloc(8LL * v11);
        memcpy_0(v12, *(const void **)(a1 + 8), 8LL * *(int *)(a1 + 16));
        memset_0(&v12[8 * *(int *)(a1 + 16)], 0, 8LL * ((int)v2 - *(_DWORD *)(a1 + 16)));
        CoTaskMemFree(*(LPVOID *)(a1 + 8));
        *(_QWORD *)(a1 + 8) = v12;
        *(_DWORD *)(a1 + 20) = v11;
      }
      else
      {
        v7 = *(int *)(a1 + 16);
        if ( (int)v2 <= (int)v7 )
        {
          if ( (int)v2 < (int)v7 )
            DestructElements<CompInfo1 *>(v4 + 8 * v2, v7 - v2);
        }
        else
        {
          memset_0((void *)(v4 + 8 * v7), 0, 8LL * ((int)v2 - (int)v7));
        }
      }
    }
    else
    {
      v5 = CoTaskMemAlloc(8LL * a2);
      *(_QWORD *)(a1 + 8) = v5;
      memset_0(v5, 0, 8 * v2);
      *(_DWORD *)(a1 + 20) = v2;
    }
  }
  else
  {
    if ( v4 )
    {
      DestructElements<CompInfo1 *>(v4, *(_DWORD *)(a1 + 16));
      CoTaskMemFree(*(LPVOID *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = 0;
    }
    *(_DWORD *)(a1 + 20) = 0;
    LODWORD(v2) = 0;
  }
  *(_DWORD *)(a1 + 16) = v2;
}

```

## disassembly

```asm
0x18003188c  push    rbx
0x18003188e  push    rbp
0x18003188f  push    rsi
0x180031890  push    rdi
0x180031891  sub     rsp, 28h
0x180031895  movsxd  rsi, edx
0x180031898  mov     rbp, rcx
0x18003189b  mov     rcx, [rcx+8]
0x18003189f  test    edx, edx
0x1800318a1  jnz     short loc_1800318D2
0x1800318a3  test    rcx, rcx
0x1800318a6  jz      short loc_1800318C4
0x1800318a8  mov     edx, [rbp+10h]
0x1800318ab  call    ??$DestructElements@PEAUCompInfo1@@@@YAXPEAPEAUCompInfo1@@H@Z; DestructElements<CompInfo1 *>(CompInfo1 * *,int)
0x1800318b0  nop
0x1800318b1  mov     rcx, [rbp+8]; pv
0x1800318b5  call    cs:__imp_CoTaskMemFree
0x1800318bb  nop
0x1800318bc  mov     qword ptr [rbp+8], 0
0x1800318c4  mov     dword ptr [rbp+14h], 0
0x1800318cb  xor     esi, esi
0x1800318cd  jmp     loc_1800319C8
0x1800318d2  test    rcx, rcx
0x1800318d5  jnz     short loc_180031900
0x1800318d7  mov     rbx, rsi
0x1800318da  shl     rbx, 3
0x1800318de  mov     rcx, rbx; cb
0x1800318e1  call    cs:__imp_CoTaskMemAlloc
0x1800318e7  mov     [rbp+8], rax
0x1800318eb  mov     r8, rbx; Size
0x1800318ee  xor     edx, edx; Val
0x1800318f0  mov     rcx, rax; void *
0x1800318f3  call    memset_0
0x1800318f8  mov     [rbp+14h], esi
0x1800318fb  jmp     loc_1800319C8
0x180031900  mov     r8d, [rbp+14h]
0x180031904  cmp     esi, r8d
0x180031907  jg      short loc_180031942
0x180031909  movsxd  rdx, dword ptr [rbp+10h]
0x18003190d  cmp     esi, edx
0x18003190f  jle     short loc_18003192C
0x180031911  mov     eax, esi
0x180031913  sub     eax, edx
0x180031915  movsxd  r8, eax
0x180031918  shl     r8, 3; Size
0x18003191c  lea     rcx, [rcx+rdx*8]; void *
0x180031920  xor     edx, edx; Val
0x180031922  call    memset_0
0x180031927  jmp     loc_1800319C8
0x18003192c  jge     loc_1800319C8
0x180031932  sub     edx, esi
0x180031934  lea     rcx, [rcx+rsi*8]
0x180031938  call    ??$DestructElements@PEAUCompInfo1@@@@YAXPEAPEAUCompInfo1@@H@Z; DestructElements<CompInfo1 *>(CompInfo1 * *,int)
0x18003193d  jmp     loc_1800319C8
0x180031942  mov     eax, [rbp+18h]
0x180031945  test    eax, eax
0x180031947  jnz     short loc_18003196C
0x180031949  mov     eax, [rbp+10h]
0x18003194c  cdq
0x18003194d  mov     ecx, 8
0x180031952  idiv    ecx
0x180031954  mov     ecx, eax
0x180031956  mov     eax, 4
0x18003195b  cmp     ecx, eax
0x18003195d  jl      short loc_18003196C
0x18003195f  mov     eax, ecx
0x180031961  mov     edx, 400h
0x180031966  cmp     ecx, edx
0x180031968  jle     short loc_18003196C
0x18003196a  mov     eax, edx
0x18003196c  add     eax, r8d
0x18003196f  mov     edi, esi
0x180031971  cmp     esi, eax
0x180031973  cmovl   edi, eax
0x180031976  movsxd  rcx, edi
0x180031979  shl     rcx, 3; cb
0x18003197d  call    cs:__imp_CoTaskMemAlloc
0x180031983  mov     rbx, rax
0x180031986  movsxd  r8, dword ptr [rbp+10h]
0x18003198a  shl     r8, 3; Size
0x18003198e  mov     rdx, [rbp+8]; Src
0x180031992  mov     rcx, rax; void *
0x180031995  call    memcpy_0
0x18003199a  mov     ecx, esi
0x18003199c  sub     ecx, [rbp+10h]
0x18003199f  movsxd  r8, ecx
0x1800319a2  shl     r8, 3; Size
0x1800319a6  movsxd  rcx, dword ptr [rbp+10h]
0x1800319aa  lea     rcx, [rbx+rcx*8]; void *
0x1800319ae  xor     edx, edx; Val
0x1800319b0  call    memset_0
0x1800319b5  nop
0x1800319b6  mov     rcx, [rbp+8]; pv
0x1800319ba  call    cs:__imp_CoTaskMemFree
0x1800319c0  nop
0x1800319c1  mov     [rbp+8], rbx
0x1800319c5  mov     [rbp+14h], edi
0x1800319c8  mov     [rbp+10h], esi
0x1800319cb  add     rsp, 28h
0x1800319cf  pop     rdi
0x1800319d0  pop     rsi
0x1800319d1  pop     rbp
0x1800319d2  pop     rbx
0x1800319d3  retn
```
