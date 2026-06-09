# DiscpCreatePortalName

- ea: `0x180016de8`
- end: `0x180016f02`
- name: `DiscpCreatePortalName`
- size: `282`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int, char, wchar_t **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001df4`
- `0x180002cbc`
- `0x180002da4`
- `0x180004ee8`
- `0x18000a748`
- `0x18000b720`

## callees

- `0x18000bdb0`
- `0x180016de8`
- `0x1800186f4`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180016e0a`
- `ISCSIUM!DiscpAllocMemory` at `0x180016e80`
- `ISCSIUM!DiscpAllocMemory` at `0x180016e0a`
- `ISCSIUM!DiscpAllocMemory` at `0x180016e80`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ee2`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ee2`

## pseudocode

```c
__int64 __fastcall DiscpCreatePortalName(__int64 a1, int *a2, unsigned int a3, char a4, wchar_t **a5)
{
  __int64 v9; // rax
  __int64 v10; // rdi
  unsigned int v11; // ebx
  int *v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // esi
  wchar_t *v17; // rbx
  const wchar_t *v18; // r8
  __int64 v20; // [rsp+30h] [rbp-58h]

  v9 = DiscpAllocMemory(256);
  v10 = v9;
  if ( v9 )
  {
    v11 = DiscpInitiatorPortToIPAddress(a2, a3, v9);
    if ( !v11 )
    {
      v12 = &dword_1800211CC;
      if ( a2 )
        v12 = a2;
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v12 + v14) );
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v10 + 2 * v15) );
      do
        ++v13;
      while ( *(_WORD *)(a1 + 512 + 2 * v13) );
      v16 = v14 + 24 + v15 + v13;
      v17 = (wchar_t *)DiscpAllocMemory(2 * v16);
      if ( v17 )
      {
        if ( a4 )
        {
          LODWORD(v20) = a3;
          v18 = L"%ws %07d %ws %08x";
        }
        else
        {
          v20 = v10;
          v18 = L"*%ws %07d %ws %ws";
        }
        StringCchPrintfW(v17, v16, v18, a1 + 512, *(unsigned __int16 *)(a1 + 1024), v12, v20);
        *a5 = v17;
        v11 = 0;
      }
      else
      {
        v11 = 8;
      }
    }
    DiscpFreeMemory(v10);
  }
  else
  {
    return 8;
  }
  return v11;
}

```

## disassembly

```asm
0x180016de8  push    rbx
0x180016dea  push    rbp
0x180016deb  push    rsi
0x180016dec  push    rdi
0x180016ded  push    r12
0x180016def  push    r13
0x180016df1  push    r14
0x180016df3  push    r15
0x180016df5  sub     rsp, 48h
0x180016df9  mov     r13, rcx
0x180016dfc  mov     r12b, r9b
0x180016dff  mov     ecx, 100h
0x180016e04  mov     r15d, r8d
0x180016e07  mov     rsi, rdx
0x180016e0a  call    cs:__imp_DiscpAllocMemory
0x180016e10  mov     rdi, rax
0x180016e13  test    rax, rax
0x180016e16  jz      loc_180016EEA
0x180016e1c  mov     r8, rax
0x180016e1f  mov     edx, r15d
0x180016e22  mov     rcx, rsi
0x180016e25  call    DiscpInitiatorPortToIPAddress
0x180016e2a  xor     r8d, r8d
0x180016e2d  mov     ebx, eax
0x180016e2f  test    eax, eax
0x180016e31  jnz     loc_180016EDF
0x180016e37  test    rsi, rsi
0x180016e3a  lea     rbp, dword_1800211CC
0x180016e41  lea     r14, [r13+200h]
0x180016e48  cmovnz  rbp, rsi
0x180016e4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016e50  mov     rdx, rax
0x180016e53  inc     rdx
0x180016e56  cmp     [rbp+rdx*2+0], r8w
0x180016e5c  jnz     short loc_180016E53
0x180016e5e  mov     rcx, rax
0x180016e61  inc     rcx
0x180016e64  cmp     [rdi+rcx*2], r8w
0x180016e69  jnz     short loc_180016E61
0x180016e6b  inc     rax
0x180016e6e  cmp     [r14+rax*2], r8w
0x180016e73  jnz     short loc_180016E6B
0x180016e75  lea     esi, [rcx+rax]
0x180016e78  add     edx, 18h
0x180016e7b  add     esi, edx
0x180016e7d  lea     ecx, [rsi+rsi]
0x180016e80  call    cs:__imp_DiscpAllocMemory
0x180016e86  mov     rbx, rax
0x180016e89  test    rax, rax
0x180016e8c  jz      short loc_180016EDA
0x180016e8e  movzx   eax, word ptr [r13+400h]
0x180016e96  mov     r9, r14
0x180016e99  mov     edx, esi; cchDest
0x180016e9b  mov     rcx, rbx; pszDest
0x180016e9e  test    r12b, r12b
0x180016ea1  jz      short loc_180016EB1
0x180016ea3  mov     dword ptr [rsp+88h+var_58], r15d
0x180016ea8  lea     r8, aWs07dWs08x; "%ws %07d %ws %08x"
0x180016eaf  jmp     short loc_180016EBD
0x180016eb1  mov     [rsp+88h+var_58], rdi
0x180016eb6  lea     r8, aWs07dWsWs; "*%ws %07d %ws %ws"
0x180016ebd  mov     [rsp+88h+var_60], rbp
0x180016ec2  mov     [rsp+88h+var_68], eax
0x180016ec6  call    StringCchPrintfW
0x180016ecb  mov     rax, [rsp+88h+arg_20]
0x180016ed3  mov     [rax], rbx
0x180016ed6  xor     ebx, ebx
0x180016ed8  jmp     short loc_180016EDF
0x180016eda  mov     ebx, 8
0x180016edf  mov     rcx, rdi
0x180016ee2  call    cs:__imp_DiscpFreeMemory
0x180016ee8  jmp     short loc_180016EEF
0x180016eea  mov     ebx, 8
0x180016eef  mov     eax, ebx
0x180016ef1  add     rsp, 48h
0x180016ef5  pop     r15
0x180016ef7  pop     r14
0x180016ef9  pop     r13
0x180016efb  pop     r12
0x180016efd  pop     rdi
0x180016efe  pop     rsi
0x180016eff  pop     rbp
0x180016f00  pop     rbx
0x180016f01  retn
```
