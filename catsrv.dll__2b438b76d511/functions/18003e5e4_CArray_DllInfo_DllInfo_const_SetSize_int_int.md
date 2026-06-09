# CArray<DllInfo *,DllInfo * const &>::SetSize(int,int)

- ea: `0x18003e5e4`
- end: `0x18003e728`
- name: `?SetSize@?$CArray@PEAUDllInfo@@AEBQEAU1@@@QEAAXHH@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c04c`
- `0x180011aec`
- `0x18003ac0c`
- `0x18003c380`
- `0x1800474b0`
- `0x18004afcc`
- `0x18004e3fc`

## callees

- `0x18003a42c`
- `0x18003e5e4`
- `0x18005550e`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e70f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e70f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6d3`

## pseudocode

```c
void __fastcall CArray<DllInfo *,DllInfo * const &>::SetSize(__int64 a1, int a2)
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
            DestructElements<DllInfo *>(v4 + 8 * v2, v7 - v2);
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
      DestructElements<DllInfo *>(v4, *(_DWORD *)(a1 + 16));
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
0x18003e5e4  push    rbx
0x18003e5e6  push    rbp
0x18003e5e7  push    rsi
0x18003e5e8  push    rdi
0x18003e5e9  sub     rsp, 28h
0x18003e5ed  movsxd  rsi, edx
0x18003e5f0  mov     rbp, rcx
0x18003e5f3  mov     rcx, [rcx+8]
0x18003e5f7  test    edx, edx
0x18003e5f9  jnz     short loc_18003E628
0x18003e5fb  test    rcx, rcx
0x18003e5fe  jz      short loc_18003E61A
0x18003e600  mov     edx, [rbp+10h]
0x18003e603  call    ??$DestructElements@PEAUDllInfo@@@@YAXPEAPEAUDllInfo@@H@Z; DestructElements<DllInfo *>(DllInfo * *,int)
0x18003e608  mov     rcx, [rbp+8]; pv
0x18003e60c  call    cs:__imp_CoTaskMemFree
0x18003e612  mov     qword ptr [rbp+8], 0
0x18003e61a  mov     dword ptr [rbp+14h], 0
0x18003e621  xor     esi, esi
0x18003e623  jmp     loc_18003E71C
0x18003e628  test    rcx, rcx
0x18003e62b  jnz     short loc_18003E656
0x18003e62d  mov     rbx, rsi
0x18003e630  shl     rbx, 3
0x18003e634  mov     rcx, rbx; cb
0x18003e637  call    cs:__imp_CoTaskMemAlloc
0x18003e63d  mov     r8, rbx; Size
0x18003e640  xor     edx, edx; Val
0x18003e642  mov     rcx, rax; void *
0x18003e645  mov     [rbp+8], rax
0x18003e649  call    memset_0
0x18003e64e  mov     [rbp+14h], esi
0x18003e651  jmp     loc_18003E71C
0x18003e656  mov     r8d, [rbp+14h]
0x18003e65a  cmp     esi, r8d
0x18003e65d  jg      short loc_18003E698
0x18003e65f  movsxd  rdx, dword ptr [rbp+10h]
0x18003e663  cmp     esi, edx
0x18003e665  jle     short loc_18003E682
0x18003e667  mov     eax, esi
0x18003e669  lea     rcx, [rcx+rdx*8]; void *
0x18003e66d  sub     eax, edx
0x18003e66f  xor     edx, edx; Val
0x18003e671  movsxd  r8, eax
0x18003e674  shl     r8, 3; Size
0x18003e678  call    memset_0
0x18003e67d  jmp     loc_18003E71C
0x18003e682  jge     loc_18003E71C
0x18003e688  sub     edx, esi
0x18003e68a  lea     rcx, [rcx+rsi*8]
0x18003e68e  call    ??$DestructElements@PEAUDllInfo@@@@YAXPEAPEAUDllInfo@@H@Z; DestructElements<DllInfo *>(DllInfo * *,int)
0x18003e693  jmp     loc_18003E71C
0x18003e698  mov     eax, [rbp+18h]
0x18003e69b  test    eax, eax
0x18003e69d  jnz     short loc_18003E6C2
0x18003e69f  mov     eax, [rbp+10h]
0x18003e6a2  mov     ecx, 8
0x18003e6a7  cdq
0x18003e6a8  idiv    ecx
0x18003e6aa  mov     ecx, eax
0x18003e6ac  mov     eax, 4
0x18003e6b1  cmp     ecx, eax
0x18003e6b3  jl      short loc_18003E6C2
0x18003e6b5  mov     edx, 400h
0x18003e6ba  mov     eax, ecx
0x18003e6bc  cmp     ecx, edx
0x18003e6be  jle     short loc_18003E6C2
0x18003e6c0  mov     eax, edx
0x18003e6c2  add     eax, r8d
0x18003e6c5  mov     edi, esi
0x18003e6c7  cmp     esi, eax
0x18003e6c9  cmovl   edi, eax
0x18003e6cc  movsxd  rcx, edi
0x18003e6cf  shl     rcx, 3; cb
0x18003e6d3  call    cs:__imp_CoTaskMemAlloc
0x18003e6d9  movsxd  r8, dword ptr [rbp+10h]
0x18003e6dd  mov     rcx, rax; void *
0x18003e6e0  mov     rdx, [rbp+8]; Src
0x18003e6e4  mov     rbx, rax
0x18003e6e7  shl     r8, 3; Size
0x18003e6eb  call    memcpy_0
0x18003e6f0  mov     ecx, esi
0x18003e6f2  xor     edx, edx; Val
0x18003e6f4  sub     ecx, [rbp+10h]
0x18003e6f7  movsxd  r8, ecx
0x18003e6fa  movsxd  rcx, dword ptr [rbp+10h]
0x18003e6fe  shl     r8, 3; Size
0x18003e702  lea     rcx, [rbx+rcx*8]; void *
0x18003e706  call    memset_0
0x18003e70b  mov     rcx, [rbp+8]; pv
0x18003e70f  call    cs:__imp_CoTaskMemFree
0x18003e715  mov     [rbp+8], rbx
0x18003e719  mov     [rbp+14h], edi
0x18003e71c  mov     [rbp+10h], esi
0x18003e71f  add     rsp, 28h
0x18003e723  pop     rdi
0x18003e724  pop     rsi
0x18003e725  pop     rbp
0x18003e726  pop     rbx
0x18003e727  retn
```
