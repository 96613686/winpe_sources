# CArray<CompInfo *,CompInfo * const &>::SetSize(int,int)

- ea: `0x18003e498`
- end: `0x18003e5dc`
- name: `?SetSize@?$CArray@PEAUCompInfo@@AEBQEAU1@@@QEAAXHH@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fb94`
- `0x18003c380`

## callees

- `0x18003a3e8`
- `0x18003e498`
- `0x18005550e`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e4c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e4c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e587`

## pseudocode

```c
void __fastcall CArray<CompInfo *,CompInfo * const &>::SetSize(__int64 a1, int a2)
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
            DestructElements<CompInfo *>(v4 + 8 * v2, v7 - v2);
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
      DestructElements<CompInfo *>(v4, *(_DWORD *)(a1 + 16));
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
0x18003e498  push    rbx
0x18003e49a  push    rbp
0x18003e49b  push    rsi
0x18003e49c  push    rdi
0x18003e49d  sub     rsp, 28h
0x18003e4a1  movsxd  rsi, edx
0x18003e4a4  mov     rbp, rcx
0x18003e4a7  mov     rcx, [rcx+8]
0x18003e4ab  test    edx, edx
0x18003e4ad  jnz     short loc_18003E4DC
0x18003e4af  test    rcx, rcx
0x18003e4b2  jz      short loc_18003E4CE
0x18003e4b4  mov     edx, [rbp+10h]
0x18003e4b7  call    ??$DestructElements@PEAUCompInfo@@@@YAXPEAPEAUCompInfo@@H@Z; DestructElements<CompInfo *>(CompInfo * *,int)
0x18003e4bc  mov     rcx, [rbp+8]; pv
0x18003e4c0  call    cs:__imp_CoTaskMemFree
0x18003e4c6  mov     qword ptr [rbp+8], 0
0x18003e4ce  mov     dword ptr [rbp+14h], 0
0x18003e4d5  xor     esi, esi
0x18003e4d7  jmp     loc_18003E5D0
0x18003e4dc  test    rcx, rcx
0x18003e4df  jnz     short loc_18003E50A
0x18003e4e1  mov     rbx, rsi
0x18003e4e4  shl     rbx, 3
0x18003e4e8  mov     rcx, rbx; cb
0x18003e4eb  call    cs:__imp_CoTaskMemAlloc
0x18003e4f1  mov     r8, rbx; Size
0x18003e4f4  xor     edx, edx; Val
0x18003e4f6  mov     rcx, rax; void *
0x18003e4f9  mov     [rbp+8], rax
0x18003e4fd  call    memset_0
0x18003e502  mov     [rbp+14h], esi
0x18003e505  jmp     loc_18003E5D0
0x18003e50a  mov     r8d, [rbp+14h]
0x18003e50e  cmp     esi, r8d
0x18003e511  jg      short loc_18003E54C
0x18003e513  movsxd  rdx, dword ptr [rbp+10h]
0x18003e517  cmp     esi, edx
0x18003e519  jle     short loc_18003E536
0x18003e51b  mov     eax, esi
0x18003e51d  lea     rcx, [rcx+rdx*8]; void *
0x18003e521  sub     eax, edx
0x18003e523  xor     edx, edx; Val
0x18003e525  movsxd  r8, eax
0x18003e528  shl     r8, 3; Size
0x18003e52c  call    memset_0
0x18003e531  jmp     loc_18003E5D0
0x18003e536  jge     loc_18003E5D0
0x18003e53c  sub     edx, esi
0x18003e53e  lea     rcx, [rcx+rsi*8]
0x18003e542  call    ??$DestructElements@PEAUCompInfo@@@@YAXPEAPEAUCompInfo@@H@Z; DestructElements<CompInfo *>(CompInfo * *,int)
0x18003e547  jmp     loc_18003E5D0
0x18003e54c  mov     eax, [rbp+18h]
0x18003e54f  test    eax, eax
0x18003e551  jnz     short loc_18003E576
0x18003e553  mov     eax, [rbp+10h]
0x18003e556  mov     ecx, 8
0x18003e55b  cdq
0x18003e55c  idiv    ecx
0x18003e55e  mov     ecx, eax
0x18003e560  mov     eax, 4
0x18003e565  cmp     ecx, eax
0x18003e567  jl      short loc_18003E576
0x18003e569  mov     edx, 400h
0x18003e56e  mov     eax, ecx
0x18003e570  cmp     ecx, edx
0x18003e572  jle     short loc_18003E576
0x18003e574  mov     eax, edx
0x18003e576  add     eax, r8d
0x18003e579  mov     edi, esi
0x18003e57b  cmp     esi, eax
0x18003e57d  cmovl   edi, eax
0x18003e580  movsxd  rcx, edi
0x18003e583  shl     rcx, 3; cb
0x18003e587  call    cs:__imp_CoTaskMemAlloc
0x18003e58d  movsxd  r8, dword ptr [rbp+10h]
0x18003e591  mov     rcx, rax; void *
0x18003e594  mov     rdx, [rbp+8]; Src
0x18003e598  mov     rbx, rax
0x18003e59b  shl     r8, 3; Size
0x18003e59f  call    memcpy_0
0x18003e5a4  mov     ecx, esi
0x18003e5a6  xor     edx, edx; Val
0x18003e5a8  sub     ecx, [rbp+10h]
0x18003e5ab  movsxd  r8, ecx
0x18003e5ae  movsxd  rcx, dword ptr [rbp+10h]
0x18003e5b2  shl     r8, 3; Size
0x18003e5b6  lea     rcx, [rbx+rcx*8]; void *
0x18003e5ba  call    memset_0
0x18003e5bf  mov     rcx, [rbp+8]; pv
0x18003e5c3  call    cs:__imp_CoTaskMemFree
0x18003e5c9  mov     [rbp+8], rbx
0x18003e5cd  mov     [rbp+14h], edi
0x18003e5d0  mov     [rbp+10h], esi
0x18003e5d3  add     rsp, 28h
0x18003e5d7  pop     rdi
0x18003e5d8  pop     rsi
0x18003e5d9  pop     rbp
0x18003e5da  pop     rbx
0x18003e5db  retn
```
