# CMsftStreamSubcode::Read(void *,ulong,ulong *)

- ea: `0x18000e6a0`
- end: `0x18000e83e`
- name: `?Read@CMsftStreamSubcode@@UEAAJPEAXKPEAK@Z`
- size: `414`
- prototype: `__int64 __fastcall(CMsftStreamSubcode *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d980`
- `0x18000e6a0`
- `0x180016778`
- `0x180049832`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000e815`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000e815`

## pseudocode

```c
__int64 __fastcall CMsftStreamSubcode::Read(CMsftStreamSubcode *this, char *a2, unsigned int a3, unsigned int *a4)
{
  int v4; // edi
  __int64 v5; // rbp
  char *v7; // r15
  PVOID *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  int v12; // ebx
  unsigned __int64 v13; // rdx
  unsigned int v14; // edi
  unsigned int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // r12
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax

  v4 = 0;
  v5 = a3;
  v7 = a2;
  if ( a2 )
    goto LABEL_6;
  v4 = -2147467261;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 10, WPP_27c29486cd193c47cac89267182ad072_Traceguids);
LABEL_6:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = *((_QWORD *)this + 18);
  v11 = *((_QWORD *)this + 17);
  if ( v11 < v10 )
  {
    if ( v11 + v5 >= v11 )
    {
      if ( v11 + v5 <= v10 )
        v12 = v5;
      else
        v12 = *((_DWORD *)this + 36) - *((_DWORD *)this + 34);
    }
    else
    {
      v13 = v10 - v11;
      v12 = -1;
      if ( v13 <= 0xFFFFFFFF )
        v12 = v13;
    }
  }
  else
  {
    v12 = 0;
  }
  if ( a4 )
  {
    *a4 = 0;
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 )
  {
    v14 = v12;
    if ( v12 )
    {
      do
      {
        v15 = *((_QWORD *)this + 17) % (unsigned __int64)*((unsigned int *)this + 17);
        v16 = v14;
        if ( v14 >= *((_DWORD *)this + 17) - v15 )
          v16 = *((_DWORD *)this + 17) - v15;
        v17 = v16;
        memcpy_0(v7, (const void *)(*((_QWORD *)this + 22) + v15), v16);
        v18 = *((unsigned int *)this + 17);
        v19 = v17 + *((_QWORD *)this + 17);
        *((_QWORD *)this + 17) = v19;
        v14 -= v17;
        if ( !(v19 % v18) )
          CMsftStreamSubcode::InitializeSectorData(this);
        v7 += v17;
      }
      while ( v14 );
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 != (_DWORD)v5
      && !v12
      && v9 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v9 + 708) & 0x10) != 0
      && *((_BYTE *)v9 + 705) >= 3u )
    {
      WPP_SF_(v9[87], 11, WPP_27c29486cd193c47cac89267182ad072_Traceguids);
    }
    GetSystemTimeAsFileTime((LPFILETIME)this + 21);
    v4 = v12 != v5;
    if ( a4 )
      *a4 = v12;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e6a0  push    rbx
0x18000e6a2  push    rbp
0x18000e6a3  push    rsi
0x18000e6a4  push    rdi
0x18000e6a5  push    r12
0x18000e6a7  push    r13
0x18000e6a9  push    r14
0x18000e6ab  push    r15
0x18000e6ad  sub     rsp, 28h
0x18000e6b1  xor     edi, edi
0x18000e6b3  mov     ebp, r8d
0x18000e6b6  lea     r13, WPP_GLOBAL_Control
0x18000e6bd  mov     r14, r9
0x18000e6c0  mov     r15, rdx
0x18000e6c3  mov     rsi, rcx
0x18000e6c6  test    rdx, rdx
0x18000e6c9  jnz     short loc_18000E705
0x18000e6cb  mov     edi, 80004003h
0x18000e6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d7  cmp     rcx, r13
0x18000e6da  jz      short loc_18000E70C
0x18000e6dc  test    byte ptr [rcx+2C4h], 10h
0x18000e6e3  jz      short loc_18000E70C
0x18000e6e5  cmp     byte ptr [rcx+2C1h], 3
0x18000e6ec  jb      short loc_18000E70C
0x18000e6ee  mov     rcx, [rcx+2B8h]
0x18000e6f5  lea     edx, [r15+0Ah]
0x18000e6f9  lea     r8, WPP_27c29486cd193c47cac89267182ad072_Traceguids
0x18000e700  call    WPP_SF_
0x18000e705  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e70c  mov     rdx, [rsi+90h]
0x18000e713  mov     r8, [rsi+88h]
0x18000e71a  cmp     r8, rdx
0x18000e71d  jb      short loc_18000E723
0x18000e71f  xor     ebx, ebx
0x18000e721  jmp     short loc_18000E752
0x18000e723  lea     r9, [r8+rbp]
0x18000e727  cmp     r9, r8
0x18000e72a  jnb     short loc_18000E73D
0x18000e72c  sub     rdx, r8
0x18000e72f  mov     ebx, 0FFFFFFFFh
0x18000e734  cmp     rdx, rbx
0x18000e737  ja      short loc_18000E752
0x18000e739  mov     ebx, edx
0x18000e73b  jmp     short loc_18000E752
0x18000e73d  cmp     r9, rdx
0x18000e740  jbe     short loc_18000E750
0x18000e742  mov     ebx, [rsi+90h]
0x18000e748  sub     ebx, [rsi+88h]
0x18000e74e  jmp     short loc_18000E752
0x18000e750  mov     ebx, ebp
0x18000e752  test    r14, r14
0x18000e755  jz      short loc_18000E765
0x18000e757  mov     dword ptr [r14], 0
0x18000e75e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e765  test    edi, edi
0x18000e767  js      loc_18000E82B
0x18000e76d  mov     edi, ebx
0x18000e76f  test    ebx, ebx
0x18000e771  jz      short loc_18000E7D9
0x18000e773  mov     ecx, [rsi+44h]
0x18000e776  xor     edx, edx
0x18000e778  mov     rax, [rsi+88h]
0x18000e77f  div     rcx
0x18000e782  mov     eax, edi
0x18000e784  sub     ecx, edx
0x18000e786  mov     edx, edx
0x18000e788  cmp     edi, ecx
0x18000e78a  cmovnb  eax, ecx
0x18000e78d  add     rdx, [rsi+0B0h]; Src
0x18000e794  mov     r8d, eax; Size
0x18000e797  mov     rcx, r15; void *
0x18000e79a  mov     r12d, eax
0x18000e79d  call    memcpy_0
0x18000e7a2  mov     rax, [rsi+88h]
0x18000e7a9  xor     edx, edx
0x18000e7ab  mov     ecx, [rsi+44h]
0x18000e7ae  add     rax, r12
0x18000e7b1  mov     [rsi+88h], rax
0x18000e7b8  sub     edi, r12d
0x18000e7bb  div     rcx
0x18000e7be  test    rdx, rdx
0x18000e7c1  jnz     short loc_18000E7CB
0x18000e7c3  mov     rcx, rsi; this
0x18000e7c6  call    ?InitializeSectorData@CMsftStreamSubcode@@QEAAXXZ; CMsftStreamSubcode::InitializeSectorData(void)
0x18000e7cb  add     r15, r12
0x18000e7ce  test    edi, edi
0x18000e7d0  jnz     short loc_18000E773
0x18000e7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d9  cmp     ebx, ebp
0x18000e7db  jz      short loc_18000E80E
0x18000e7dd  test    ebx, ebx
0x18000e7df  jnz     short loc_18000E80E
0x18000e7e1  cmp     rcx, r13
0x18000e7e4  jz      short loc_18000E80E
0x18000e7e6  test    byte ptr [rcx+2C4h], 10h
0x18000e7ed  jz      short loc_18000E80E
0x18000e7ef  cmp     byte ptr [rcx+2C1h], 3
0x18000e7f6  jb      short loc_18000E80E
0x18000e7f8  mov     rcx, [rcx+2B8h]
0x18000e7ff  lea     edx, [rbx+0Bh]
0x18000e802  lea     r8, WPP_27c29486cd193c47cac89267182ad072_Traceguids
0x18000e809  call    WPP_SF_
0x18000e80e  lea     rcx, [rsi+0A8h]; lpSystemTimeAsFileTime
0x18000e815  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e81b  xor     edi, edi
0x18000e81d  cmp     ebx, ebp
0x18000e81f  setnz   dil
0x18000e823  test    r14, r14
0x18000e826  jz      short loc_18000E82B
0x18000e828  mov     [r14], ebx
0x18000e82b  mov     eax, edi
0x18000e82d  add     rsp, 28h
0x18000e831  pop     r15
0x18000e833  pop     r14
0x18000e835  pop     r13
0x18000e837  pop     r12
0x18000e839  pop     rdi
0x18000e83a  pop     rsi
0x18000e83b  pop     rbp
0x18000e83c  pop     rbx
0x18000e83d  retn
```
