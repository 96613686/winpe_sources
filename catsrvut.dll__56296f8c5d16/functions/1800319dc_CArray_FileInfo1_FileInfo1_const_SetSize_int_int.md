# CArray<FileInfo1 *,FileInfo1 * const &>::SetSize(int,int)

- ea: `0x1800319dc`
- end: `0x180031b24`
- name: `?SetSize@?$CArray@PEAUFileInfo1@@AEBQEAU1@@@QEAAXHH@Z`
- size: `328`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d3a0`
- `0x180030710`

## callees

- `0x18002ccd0`
- `0x1800319dc`
- `0x18005582e`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031acd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031acd`

## pseudocode

```c
void __fastcall CArray<FileInfo1 *,FileInfo1 * const &>::SetSize(__int64 a1, int a2)
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
            DestructElements<FileInfo1 *>(v4 + 8 * v2, v7 - v2);
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
      DestructElements<FileInfo1 *>(v4, *(_DWORD *)(a1 + 16));
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
0x1800319dc  push    rbx
0x1800319de  push    rbp
0x1800319df  push    rsi
0x1800319e0  push    rdi
0x1800319e1  sub     rsp, 28h
0x1800319e5  movsxd  rsi, edx
0x1800319e8  mov     rbp, rcx
0x1800319eb  mov     rcx, [rcx+8]
0x1800319ef  test    edx, edx
0x1800319f1  jnz     short loc_180031A22
0x1800319f3  test    rcx, rcx
0x1800319f6  jz      short loc_180031A14
0x1800319f8  mov     edx, [rbp+10h]
0x1800319fb  call    ??$DestructElements@PEAUFileInfo1@@@@YAXPEAPEAUFileInfo1@@H@Z; DestructElements<FileInfo1 *>(FileInfo1 * *,int)
0x180031a00  nop
0x180031a01  mov     rcx, [rbp+8]; pv
0x180031a05  call    cs:__imp_CoTaskMemFree
0x180031a0b  nop
0x180031a0c  mov     qword ptr [rbp+8], 0
0x180031a14  mov     dword ptr [rbp+14h], 0
0x180031a1b  xor     esi, esi
0x180031a1d  jmp     loc_180031B18
0x180031a22  test    rcx, rcx
0x180031a25  jnz     short loc_180031A50
0x180031a27  mov     rbx, rsi
0x180031a2a  shl     rbx, 3
0x180031a2e  mov     rcx, rbx; cb
0x180031a31  call    cs:__imp_CoTaskMemAlloc
0x180031a37  mov     [rbp+8], rax
0x180031a3b  mov     r8, rbx; Size
0x180031a3e  xor     edx, edx; Val
0x180031a40  mov     rcx, rax; void *
0x180031a43  call    memset_0
0x180031a48  mov     [rbp+14h], esi
0x180031a4b  jmp     loc_180031B18
0x180031a50  mov     r8d, [rbp+14h]
0x180031a54  cmp     esi, r8d
0x180031a57  jg      short loc_180031A92
0x180031a59  movsxd  rdx, dword ptr [rbp+10h]
0x180031a5d  cmp     esi, edx
0x180031a5f  jle     short loc_180031A7C
0x180031a61  mov     eax, esi
0x180031a63  sub     eax, edx
0x180031a65  movsxd  r8, eax
0x180031a68  shl     r8, 3; Size
0x180031a6c  lea     rcx, [rcx+rdx*8]; void *
0x180031a70  xor     edx, edx; Val
0x180031a72  call    memset_0
0x180031a77  jmp     loc_180031B18
0x180031a7c  jge     loc_180031B18
0x180031a82  sub     edx, esi
0x180031a84  lea     rcx, [rcx+rsi*8]
0x180031a88  call    ??$DestructElements@PEAUFileInfo1@@@@YAXPEAPEAUFileInfo1@@H@Z; DestructElements<FileInfo1 *>(FileInfo1 * *,int)
0x180031a8d  jmp     loc_180031B18
0x180031a92  mov     eax, [rbp+18h]
0x180031a95  test    eax, eax
0x180031a97  jnz     short loc_180031ABC
0x180031a99  mov     eax, [rbp+10h]
0x180031a9c  cdq
0x180031a9d  mov     ecx, 8
0x180031aa2  idiv    ecx
0x180031aa4  mov     ecx, eax
0x180031aa6  mov     eax, 4
0x180031aab  cmp     ecx, eax
0x180031aad  jl      short loc_180031ABC
0x180031aaf  mov     eax, ecx
0x180031ab1  mov     edx, 400h
0x180031ab6  cmp     ecx, edx
0x180031ab8  jle     short loc_180031ABC
0x180031aba  mov     eax, edx
0x180031abc  add     eax, r8d
0x180031abf  mov     edi, esi
0x180031ac1  cmp     esi, eax
0x180031ac3  cmovl   edi, eax
0x180031ac6  movsxd  rcx, edi
0x180031ac9  shl     rcx, 3; cb
0x180031acd  call    cs:__imp_CoTaskMemAlloc
0x180031ad3  mov     rbx, rax
0x180031ad6  movsxd  r8, dword ptr [rbp+10h]
0x180031ada  shl     r8, 3; Size
0x180031ade  mov     rdx, [rbp+8]; Src
0x180031ae2  mov     rcx, rax; void *
0x180031ae5  call    memcpy_0
0x180031aea  mov     ecx, esi
0x180031aec  sub     ecx, [rbp+10h]
0x180031aef  movsxd  r8, ecx
0x180031af2  shl     r8, 3; Size
0x180031af6  movsxd  rcx, dword ptr [rbp+10h]
0x180031afa  lea     rcx, [rbx+rcx*8]; void *
0x180031afe  xor     edx, edx; Val
0x180031b00  call    memset_0
0x180031b05  nop
0x180031b06  mov     rcx, [rbp+8]; pv
0x180031b0a  call    cs:__imp_CoTaskMemFree
0x180031b10  nop
0x180031b11  mov     [rbp+8], rbx
0x180031b15  mov     [rbp+14h], edi
0x180031b18  mov     [rbp+10h], esi
0x180031b1b  add     rsp, 28h
0x180031b1f  pop     rdi
0x180031b20  pop     rsi
0x180031b21  pop     rbp
0x180031b22  pop     rbx
0x180031b23  retn
```
