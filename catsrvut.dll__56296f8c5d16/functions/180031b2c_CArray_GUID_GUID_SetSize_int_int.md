# CArray<_GUID,_GUID &>::SetSize(int,int)

- ea: `0x180031b2c`
- end: `0x180031c60`
- name: `?SetSize@?$CArray@U_GUID@@AEAU1@@@QEAAXHH@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b640`

## callees

- `0x180031b2c`
- `0x18005582e`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031b77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031b77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031c06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CArray<_GUID,_GUID &>::SetSize(__int64 a1, int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdx
  void *v5; // rax
  int v6; // r8d
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // edi
  char *v11; // rbx

  v2 = a2;
  v4 = *(_QWORD *)(a1 + 8);
  if ( (_DWORD)v2 )
  {
    if ( v4 )
    {
      v6 = *(_DWORD *)(a1 + 20);
      if ( (int)v2 > v6 )
      {
        v7 = *(_DWORD *)(a1 + 24);
        if ( !v7 )
        {
          v8 = *(_DWORD *)(a1 + 16) / 8;
          v7 = 4;
          if ( v8 >= 4 )
          {
            v7 = v8;
            if ( v8 > 1024 )
              v7 = 1024;
          }
        }
        v9 = v6 + v7;
        v10 = v2;
        if ( (int)v2 < v9 )
          v10 = v9;
        v11 = (char *)CoTaskMemAlloc(16LL * v10);
        memcpy_0(v11, *(const void **)(a1 + 8), 16LL * *(int *)(a1 + 16));
        memset_0(&v11[16 * *(int *)(a1 + 16)], 0, 16LL * ((int)v2 - *(_DWORD *)(a1 + 16)));
        CoTaskMemFree(*(LPVOID *)(a1 + 8));
        *(_QWORD *)(a1 + 8) = v11;
        *(_DWORD *)(a1 + 20) = v10;
      }
      else if ( (int)v2 > *(_DWORD *)(a1 + 16) )
      {
        memset_0((void *)(v4 + 16LL * *(int *)(a1 + 16)), 0, 16LL * ((int)v2 - *(_DWORD *)(a1 + 16)));
      }
    }
    else
    {
      v5 = CoTaskMemAlloc(16 * v2);
      *(_QWORD *)(a1 + 8) = v5;
      memset_0(v5, 0, 16 * v2);
      *(_DWORD *)(a1 + 20) = v2;
    }
  }
  else
  {
    if ( v4 )
    {
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
0x180031b2c  push    rbx
0x180031b2e  push    rbp
0x180031b2f  push    rsi
0x180031b30  push    rdi
0x180031b31  sub     rsp, 28h
0x180031b35  movsxd  rsi, edx
0x180031b38  mov     rbp, rcx
0x180031b3b  mov     rdx, [rcx+8]
0x180031b3f  test    esi, esi
0x180031b41  jnz     short loc_180031B68
0x180031b43  test    rdx, rdx
0x180031b46  jz      short loc_180031B5A
0x180031b48  mov     rcx, rdx; pv
0x180031b4b  call    cs:__imp_CoTaskMemFree
0x180031b51  nop
0x180031b52  mov     qword ptr [rbp+8], 0
0x180031b5a  mov     dword ptr [rbp+14h], 0
0x180031b61  xor     esi, esi
0x180031b63  jmp     loc_180031C54
0x180031b68  test    rdx, rdx
0x180031b6b  jnz     short loc_180031B96
0x180031b6d  mov     rbx, rsi
0x180031b70  shl     rbx, 4
0x180031b74  mov     rcx, rbx; cb
0x180031b77  call    cs:__imp_CoTaskMemAlloc
0x180031b7d  mov     [rbp+8], rax
0x180031b81  mov     r8, rbx; Size
0x180031b84  xor     edx, edx; Val
0x180031b86  mov     rcx, rax; void *
0x180031b89  call    memset_0
0x180031b8e  mov     [rbp+14h], esi
0x180031b91  jmp     loc_180031C54
0x180031b96  mov     r8d, [rcx+14h]
0x180031b9a  cmp     esi, r8d
0x180031b9d  jg      short loc_180031BCB
0x180031b9f  cmp     esi, [rcx+10h]
0x180031ba2  jle     loc_180031C54
0x180031ba8  mov     eax, esi
0x180031baa  sub     eax, [rcx+10h]
0x180031bad  movsxd  r8, eax
0x180031bb0  shl     r8, 4; Size
0x180031bb4  movsxd  rcx, dword ptr [rcx+10h]
0x180031bb8  shl     rcx, 4
0x180031bbc  add     rcx, rdx; void *
0x180031bbf  xor     edx, edx; Val
0x180031bc1  call    memset_0
0x180031bc6  jmp     loc_180031C54
0x180031bcb  mov     eax, [rcx+18h]
0x180031bce  test    eax, eax
0x180031bd0  jnz     short loc_180031BF5
0x180031bd2  mov     eax, [rcx+10h]
0x180031bd5  cdq
0x180031bd6  mov     ecx, 8
0x180031bdb  idiv    ecx
0x180031bdd  mov     ecx, eax
0x180031bdf  mov     eax, 4
0x180031be4  cmp     ecx, eax
0x180031be6  jl      short loc_180031BF5
0x180031be8  mov     eax, ecx
0x180031bea  mov     edx, 400h
0x180031bef  cmp     ecx, edx
0x180031bf1  jle     short loc_180031BF5
0x180031bf3  mov     eax, edx
0x180031bf5  add     eax, r8d
0x180031bf8  mov     edi, esi
0x180031bfa  cmp     esi, eax
0x180031bfc  cmovl   edi, eax
0x180031bff  movsxd  rcx, edi
0x180031c02  shl     rcx, 4; cb
0x180031c06  call    cs:__imp_CoTaskMemAlloc
0x180031c0c  mov     rbx, rax
0x180031c0f  movsxd  r8, dword ptr [rbp+10h]
0x180031c13  shl     r8, 4; Size
0x180031c17  mov     rdx, [rbp+8]; Src
0x180031c1b  mov     rcx, rax; void *
0x180031c1e  call    memcpy_0
0x180031c23  mov     ecx, esi
0x180031c25  sub     ecx, [rbp+10h]
0x180031c28  movsxd  r8, ecx
0x180031c2b  shl     r8, 4; Size
0x180031c2f  movsxd  rcx, dword ptr [rbp+10h]
0x180031c33  shl     rcx, 4
0x180031c37  add     rcx, rbx; void *
0x180031c3a  xor     edx, edx; Val
0x180031c3c  call    memset_0
0x180031c41  nop
0x180031c42  mov     rcx, [rbp+8]; pv
0x180031c46  call    cs:__imp_CoTaskMemFree
0x180031c4c  nop
0x180031c4d  mov     [rbp+8], rbx
0x180031c51  mov     [rbp+14h], edi
0x180031c54  mov     [rbp+10h], esi
0x180031c57  add     rsp, 28h
0x180031c5b  pop     rdi
0x180031c5c  pop     rsi
0x180031c5d  pop     rbp
0x180031c5e  pop     rbx
0x180031c5f  retn
```
