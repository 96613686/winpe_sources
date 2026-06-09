# CMFCDynamicLayoutData::ReadResource(void *,uint)

- ea: `0x180018da0`
- end: `0x180018ebd`
- name: `?ReadResource@CMFCDynamicLayoutData@@QEAAHPEAXI@Z`
- size: `285`
- prototype: `_BOOL8 __fastcall(CMFCDynamicLayoutData *this, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180018b94`
- `0x180018da0`
- `0x180018ec4`

## pseudocode

```c
_BOOL8 __fastcall CMFCDynamicLayoutData::ReadResource(CMFCDynamicLayoutData *this, char *a2, unsigned int a3)
{
  __int64 v3; // rbx
  char *v6; // rbp
  __int16 *v7; // rbx
  int v8; // r12d
  int v9; // r15d
  int v10; // r14d
  int v11; // eax
  int v12; // edi
  _DWORD *v13; // rax
  _QWORD *v14; // rcx

  v3 = a3;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 0;
  CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::RemoveAll();
  if ( *(_WORD *)a2 )
    return 0;
  v6 = &a2[v3];
  v7 = (__int16 *)(a2 + 2);
  if ( a2 + 10 <= v6 )
  {
    do
    {
      if ( *v7 >= 0 )
      {
        v8 = 100;
        if ( *v7 <= 100 )
          v8 = *v7;
      }
      else
      {
        v8 = 0;
      }
      if ( v7[1] >= 0 )
      {
        v9 = 100;
        if ( v7[1] <= 100 )
          v9 = v7[1];
      }
      else
      {
        v9 = 0;
      }
      if ( v7[2] >= 0 )
      {
        v10 = 100;
        if ( v7[2] <= 100 )
          v10 = v7[2];
      }
      else
      {
        v10 = 0;
      }
      v11 = v7[3];
      v7 += 4;
      if ( (v11 & 0x8000u) == 0 )
      {
        v12 = 100;
        if ( (__int16)v11 <= 100 )
          v12 = v11;
      }
      else
      {
        v12 = 0;
      }
      v13 = (_DWORD *)CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::NewNode(
                        this,
                        *((_QWORD *)this + 1));
      v13[4] = v8;
      v13[5] = v9;
      v13[6] = v10;
      v13[7] = v12;
      v14 = (_QWORD *)*((_QWORD *)this + 1);
      if ( v14 )
        *v14 = v13;
      else
        *(_QWORD *)this = v13;
      *((_QWORD *)this + 1) = v13;
    }
    while ( v7 + 4 <= (__int16 *)v6 );
  }
  return *((_DWORD *)this + 4) > 0;
}

```

## disassembly

```asm
0x180018da0  push    rbx
0x180018da2  push    rbp
0x180018da3  push    rsi
0x180018da4  push    rdi
0x180018da5  push    r12
0x180018da7  push    r13
0x180018da9  push    r14
0x180018dab  push    r15
0x180018dad  sub     rsp, 28h
0x180018db1  xor     r13d, r13d
0x180018db4  mov     ebx, r8d
0x180018db7  mov     rdi, rdx
0x180018dba  mov     rsi, rcx
0x180018dbd  test    rdx, rdx
0x180018dc0  jz      loc_180018EAA
0x180018dc6  test    r8d, r8d
0x180018dc9  jz      loc_180018EAA
0x180018dcf  call    ?RemoveAll@?$CList@PEAUAFX_DYNAMIC_LAYOUT_ITEM@@PEAU1@@@QEAAXXZ; CList<AFX_DYNAMIC_LAYOUT_ITEM *,AFX_DYNAMIC_LAYOUT_ITEM *>::RemoveAll(void)
0x180018dd4  cmp     [rdi], r13w
0x180018dd8  jnz     loc_180018EAA
0x180018dde  lea     rbp, [rdi+rbx]
0x180018de2  lea     rax, [rdi+0Ah]
0x180018de6  lea     rbx, [rdi+2]
0x180018dea  cmp     rax, rbp
0x180018ded  ja      loc_180018E9E
0x180018df3  lea     ecx, [r13+64h]
0x180018df7  movsx   eax, word ptr [rbx]
0x180018dfa  test    ax, ax
0x180018dfd  jns     short loc_180018E04
0x180018dff  mov     r12d, r13d
0x180018e02  jmp     short loc_180018E0F
0x180018e04  mov     r12d, ecx
0x180018e07  cmp     ax, cx
0x180018e0a  jg      short loc_180018E0F
0x180018e0c  mov     r12d, eax
0x180018e0f  movsx   eax, word ptr [rbx+2]
0x180018e13  test    ax, ax
0x180018e16  jns     short loc_180018E1D
0x180018e18  mov     r15d, r13d
0x180018e1b  jmp     short loc_180018E28
0x180018e1d  mov     r15d, ecx
0x180018e20  cmp     ax, cx
0x180018e23  jg      short loc_180018E28
0x180018e25  mov     r15d, eax
0x180018e28  movsx   eax, word ptr [rbx+4]
0x180018e2c  test    ax, ax
0x180018e2f  jns     short loc_180018E36
0x180018e31  mov     r14d, r13d
0x180018e34  jmp     short loc_180018E41
0x180018e36  mov     r14d, ecx
0x180018e39  cmp     ax, cx
0x180018e3c  jg      short loc_180018E41
0x180018e3e  mov     r14d, eax
0x180018e41  movsx   eax, word ptr [rbx+6]
0x180018e45  add     rbx, 8
0x180018e49  test    ax, ax
0x180018e4c  jns     short loc_180018E53
0x180018e4e  mov     edi, r13d
0x180018e51  jmp     short loc_180018E5C
0x180018e53  mov     edi, ecx
0x180018e55  cmp     ax, cx
0x180018e58  jg      short loc_180018E5C
0x180018e5a  mov     edi, eax
0x180018e5c  mov     rdx, [rsi+8]
0x180018e60  mov     rcx, rsi
0x180018e63  call    ?NewNode@?$CList@UItem@CMFCDynamicLayoutData@@AEAU12@@@IEAAPEAUCNode@1@PEAU21@0@Z; CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::NewNode(CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::CNode *,CList<CMFCDynamicLayoutData::Item,CMFCDynamicLayoutData::Item &>::CNode *)
0x180018e68  mov     [rax+10h], r12d
0x180018e6c  mov     [rax+14h], r15d
0x180018e70  mov     [rax+18h], r14d
0x180018e74  mov     [rax+1Ch], edi
0x180018e77  mov     rcx, [rsi+8]
0x180018e7b  test    rcx, rcx
0x180018e7e  jz      short loc_180018E85
0x180018e80  mov     [rcx], rax
0x180018e83  jmp     short loc_180018E88
0x180018e85  mov     [rsi], rax
0x180018e88  mov     [rsi+8], rax
0x180018e8c  mov     ecx, 64h ; 'd'
0x180018e91  lea     rax, [rbx+8]
0x180018e95  cmp     rax, rbp
0x180018e98  jbe     loc_180018DF7
0x180018e9e  cmp     [rsi+10h], r13d
0x180018ea2  mov     eax, r13d
0x180018ea5  setnle  al
0x180018ea8  jmp     short loc_180018EAC
0x180018eaa  xor     eax, eax
0x180018eac  add     rsp, 28h
0x180018eb0  pop     r15
0x180018eb2  pop     r14
0x180018eb4  pop     r13
0x180018eb6  pop     r12
0x180018eb8  pop     rdi
0x180018eb9  pop     rsi
0x180018eba  pop     rbp
0x180018ebb  pop     rbx
0x180018ebc  retn
```
