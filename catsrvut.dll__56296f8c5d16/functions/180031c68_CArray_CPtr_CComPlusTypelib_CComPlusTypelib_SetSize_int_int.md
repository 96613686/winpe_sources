# CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::SetSize(int,int)

- ea: `0x180031c68`
- end: `0x180031dac`
- name: `?SetSize@?$CArray@V?$CPtr@VCComPlusTypelib@@@@PEAVCComPlusTypelib@@@@QEAAXHH@Z`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b640`

## callees

- `0x18002cc40`
- `0x18002cd18`
- `0x180031c68`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031d5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::SetSize(__int64 a1, int a2)
{
  int v2; // esi
  __int64 v4; // r8
  _QWORD *v5; // rax
  int v6; // r9d
  __int64 v7; // rax
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // edi
  void *v12; // rbx

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
            v8 = v9;
            if ( v9 > 1024 )
              v8 = 1024;
          }
        }
        v10 = v6 + v8;
        v11 = a2;
        if ( a2 < v10 )
          v11 = v10;
        v12 = CoTaskMemAlloc(16LL * v11);
        memcpy_0(v12, *(const void **)(a1 + 8), 16LL * *(int *)(a1 + 16));
        ConstructElements<CPtr<CComPlusTypelib>>((_QWORD *)v12 + 2 * *(int *)(a1 + 16), v2 - *(_DWORD *)(a1 + 16));
        CoTaskMemFree(*(LPVOID *)(a1 + 8));
        *(_QWORD *)(a1 + 8) = v12;
        *(_DWORD *)(a1 + 20) = v11;
      }
      else
      {
        v7 = *(int *)(a1 + 16);
        if ( a2 <= (int)v7 )
        {
          if ( a2 < (int)v7 )
            DestructElements<CPtr<CComPlusTypelib>>(v4 + 16LL * a2, v7 - a2);
        }
        else
        {
          ConstructElements<CPtr<CComPlusTypelib>>((_QWORD *)(v4 + 16 * v7), a2 - v7);
        }
      }
    }
    else
    {
      v5 = CoTaskMemAlloc(16LL * a2);
      *(_QWORD *)(a1 + 8) = v5;
      ConstructElements<CPtr<CComPlusTypelib>>(v5, v2);
      *(_DWORD *)(a1 + 20) = v2;
    }
  }
  else
  {
    if ( v4 )
    {
      DestructElements<CPtr<CComPlusTypelib>>(*(_QWORD *)(a1 + 8), *(_DWORD *)(a1 + 16));
      CoTaskMemFree(*(LPVOID *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = 0;
    }
    *(_DWORD *)(a1 + 20) = 0;
    v2 = 0;
  }
  *(_DWORD *)(a1 + 16) = v2;
}

```

## disassembly

```asm
0x180031c68  push    rbx
0x180031c6a  push    rbp
0x180031c6b  push    rsi
0x180031c6c  push    rdi
0x180031c6d  sub     rsp, 28h
0x180031c71  movsxd  rsi, edx
0x180031c74  mov     rbp, rcx
0x180031c77  mov     r8, [rcx+8]
0x180031c7b  test    edx, edx
0x180031c7d  jnz     short loc_180031CB1
0x180031c7f  test    r8, r8
0x180031c82  jz      short loc_180031CA3
0x180031c84  mov     edx, [rcx+10h]
0x180031c87  mov     rcx, r8
0x180031c8a  call    ??$DestructElements@V?$CPtr@VCComPlusTypelib@@@@@@YAXPEAV?$CPtr@VCComPlusTypelib@@@@H@Z; DestructElements<CPtr<CComPlusTypelib>>(CPtr<CComPlusTypelib> *,int)
0x180031c8f  nop
0x180031c90  mov     rcx, [rbp+8]; pv
0x180031c94  call    cs:__imp_CoTaskMemFree
0x180031c9a  nop
0x180031c9b  mov     qword ptr [rbp+8], 0
0x180031ca3  mov     dword ptr [rbp+14h], 0
0x180031caa  xor     esi, esi
0x180031cac  jmp     loc_180031DA0
0x180031cb1  test    r8, r8
0x180031cb4  jnz     short loc_180031CD9
0x180031cb6  mov     rcx, rsi
0x180031cb9  shl     rcx, 4; cb
0x180031cbd  call    cs:__imp_CoTaskMemAlloc
0x180031cc3  mov     [rbp+8], rax
0x180031cc7  mov     edx, esi
0x180031cc9  mov     rcx, rax
0x180031ccc  call    ??$ConstructElements@V?$CPtr@VCComPlusTypelib@@@@@@YAXPEAV?$CPtr@VCComPlusTypelib@@@@H@Z; ConstructElements<CPtr<CComPlusTypelib>>(CPtr<CComPlusTypelib> *,int)
0x180031cd1  mov     [rbp+14h], esi
0x180031cd4  jmp     loc_180031DA0
0x180031cd9  mov     r9d, [rcx+14h]
0x180031cdd  cmp     esi, r9d
0x180031ce0  jg      short loc_180031D20
0x180031ce2  movsxd  rax, dword ptr [rcx+10h]
0x180031ce6  cmp     esi, eax
0x180031ce8  jle     short loc_180031D02
0x180031cea  mov     edx, esi
0x180031cec  sub     edx, eax
0x180031cee  mov     rcx, rax
0x180031cf1  shl     rcx, 4
0x180031cf5  add     rcx, r8
0x180031cf8  call    ??$ConstructElements@V?$CPtr@VCComPlusTypelib@@@@@@YAXPEAV?$CPtr@VCComPlusTypelib@@@@H@Z; ConstructElements<CPtr<CComPlusTypelib>>(CPtr<CComPlusTypelib> *,int)
0x180031cfd  jmp     loc_180031DA0
0x180031d02  jge     loc_180031DA0
0x180031d08  sub     eax, esi
0x180031d0a  mov     rcx, rsi
0x180031d0d  shl     rcx, 4
0x180031d11  add     rcx, r8
0x180031d14  mov     edx, eax
0x180031d16  call    ??$DestructElements@V?$CPtr@VCComPlusTypelib@@@@@@YAXPEAV?$CPtr@VCComPlusTypelib@@@@H@Z; DestructElements<CPtr<CComPlusTypelib>>(CPtr<CComPlusTypelib> *,int)
0x180031d1b  jmp     loc_180031DA0
0x180031d20  mov     eax, [rcx+18h]
0x180031d23  test    eax, eax
0x180031d25  jnz     short loc_180031D4A
0x180031d27  mov     eax, [rcx+10h]
0x180031d2a  cdq
0x180031d2b  mov     ecx, 8
0x180031d30  idiv    ecx
0x180031d32  mov     ecx, eax
0x180031d34  mov     eax, 4
0x180031d39  cmp     ecx, eax
0x180031d3b  jl      short loc_180031D4A
0x180031d3d  mov     eax, ecx
0x180031d3f  mov     edx, 400h
0x180031d44  cmp     ecx, edx
0x180031d46  jle     short loc_180031D4A
0x180031d48  mov     eax, edx
0x180031d4a  add     eax, r9d
0x180031d4d  mov     edi, esi
0x180031d4f  cmp     esi, eax
0x180031d51  cmovl   edi, eax
0x180031d54  movsxd  rcx, edi
0x180031d57  shl     rcx, 4; cb
0x180031d5b  call    cs:__imp_CoTaskMemAlloc
0x180031d61  mov     rbx, rax
0x180031d64  movsxd  r8, dword ptr [rbp+10h]
0x180031d68  shl     r8, 4; Size
0x180031d6c  mov     rdx, [rbp+8]; Src
0x180031d70  mov     rcx, rax; void *
0x180031d73  call    memcpy_0
0x180031d78  mov     edx, esi
0x180031d7a  sub     edx, [rbp+10h]
0x180031d7d  movsxd  rcx, dword ptr [rbp+10h]
0x180031d81  shl     rcx, 4
0x180031d85  add     rcx, rbx
0x180031d88  call    ??$ConstructElements@V?$CPtr@VCComPlusTypelib@@@@@@YAXPEAV?$CPtr@VCComPlusTypelib@@@@H@Z; ConstructElements<CPtr<CComPlusTypelib>>(CPtr<CComPlusTypelib> *,int)
0x180031d8d  nop
0x180031d8e  mov     rcx, [rbp+8]; pv
0x180031d92  call    cs:__imp_CoTaskMemFree
0x180031d98  nop
0x180031d99  mov     [rbp+8], rbx
0x180031d9d  mov     [rbp+14h], edi
0x180031da0  mov     [rbp+10h], esi
0x180031da3  add     rsp, 28h
0x180031da7  pop     rdi
0x180031da8  pop     rsi
0x180031da9  pop     rbp
0x180031daa  pop     rbx
0x180031dab  retn
```
