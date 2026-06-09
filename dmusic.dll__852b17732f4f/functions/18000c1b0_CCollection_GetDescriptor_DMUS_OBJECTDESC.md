# CCollection::GetDescriptor(_DMUS_OBJECTDESC *)

- ea: `0x18000c1b0`
- end: `0x18000c31b`
- name: `?GetDescriptor@CCollection@@UEAAJPEAU_DMUS_OBJECTDESC@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(CCollection *__hidden this, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c1b0`

## pseudocode

```c
__int64 __fastcall CCollection::GetDescriptor(CCollection *this, struct _DMUS_OBJECTDESC *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r9
  _WORD *v10; // r10
  _WORD *v11; // rax
  _WORD *v12; // rcx
  int v13; // eax
  _WORD *v14; // rcx
  _WORD *v15; // rax
  _WORD *v16; // rcx
  int v17; // eax

  if ( !a2 )
    return 2147500035LL;
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 < 0x358u )
      return 2147942487LL;
  }
  else
  {
    *(_DWORD *)a2 = 856;
  }
  if ( *((_DWORD *)this + 50) )
  {
    v4 = (_DWORD *)((char *)this + 204);
    goto LABEL_11;
  }
  v4 = (_DWORD *)((char *)this + 204);
  if ( *v4 )
  {
LABEL_11:
    *((_DWORD *)a2 + 1) |= 0x80u;
    *((_DWORD *)a2 + 12) = *((_DWORD *)this + 50);
    *((_DWORD *)a2 + 13) = *v4;
  }
  v5 = *((_QWORD *)this + 8);
  v6 = 2147483646;
  v7 = 64;
  if ( v5 && (*(_BYTE *)v5 & 2) != 0 && *(_QWORD *)(v5 + 8) )
  {
    *((_DWORD *)a2 + 1) |= 4u;
    v8 = 2147483646;
    v9 = 64;
    v10 = *(_WORD **)(*((_QWORD *)this + 8) + 8LL);
    v11 = (_WORD *)((char *)a2 + 56);
    do
    {
      if ( !v8 )
        break;
      if ( !*v10 )
        break;
      *v11++ = *v10++;
      --v8;
      --v9;
    }
    while ( v9 );
    v12 = v11 - 1;
    if ( v9 )
      v12 = v11;
    *v12 = 0;
  }
  if ( *((_QWORD *)this + 26) != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
    || *((_QWORD *)this + 27) != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    *((_DWORD *)a2 + 1) |= 1u;
    *(_OWORD *)((char *)a2 + 8) = *((_OWORD *)this + 13);
  }
  v13 = *((_DWORD *)a2 + 1);
  v14 = (_WORD *)((char *)this + 72);
  if ( *((_WORD *)this + 36) )
  {
    v15 = (_WORD *)((char *)a2 + 56);
    do
    {
      if ( !v6 )
        break;
      if ( !*v14 )
        break;
      *v15++ = *v14++;
      --v6;
      --v7;
    }
    while ( v7 );
    v16 = v15 - 1;
    if ( v7 )
      v16 = v15;
    *v16 = 0;
    *((_DWORD *)a2 + 1) |= 4u;
    v13 = *((_DWORD *)a2 + 1);
  }
  v17 = v13 | 2;
  *((_DWORD *)a2 + 1) = v17;
  *(GUID *)((char *)a2 + 24) = CLSID_DirectMusicCollection;
  if ( *((_BYTE *)this + 224) )
    *((_DWORD *)a2 + 1) = v17 | 0x200;
  return 0;
}

```

## disassembly

```asm
0x18000c1b0  push    rbx
0x18000c1b2  push    rsi
0x18000c1b3  push    rdi
0x18000c1b4  xor     esi, esi
0x18000c1b6  mov     r8, rcx
0x18000c1b9  test    rdx, rdx
0x18000c1bc  jnz     short loc_18000C1C8
0x18000c1be  mov     eax, 80004003h
0x18000c1c3  jmp     loc_18000C317
0x18000c1c8  cmp     [rdx], esi
0x18000c1ca  jz      short loc_18000C1DE
0x18000c1cc  cmp     dword ptr [rdx], 358h
0x18000c1d2  jnb     short loc_18000C1E4
0x18000c1d4  mov     eax, 80070057h
0x18000c1d9  jmp     loc_18000C317
0x18000c1de  mov     dword ptr [rdx], 358h
0x18000c1e4  cmp     [rcx+0C8h], esi
0x18000c1ea  jnz     short loc_18000C1F9
0x18000c1ec  add     rcx, 0CCh
0x18000c1f3  cmp     [rcx], esi
0x18000c1f5  jnz     short loc_18000C200
0x18000c1f7  jmp     short loc_18000C214
0x18000c1f9  add     rcx, 0CCh
0x18000c200  bts     dword ptr [rdx+4], 7
0x18000c205  mov     eax, [r8+0C8h]
0x18000c20c  mov     [rdx+30h], eax
0x18000c20f  mov     eax, [rcx]
0x18000c211  mov     [rdx+34h], eax
0x18000c214  mov     rax, [r8+40h]
0x18000c218  mov     edi, 7FFFFFFEh
0x18000c21d  mov     ebx, 40h ; '@'
0x18000c222  test    rax, rax
0x18000c225  jz      short loc_18000C279
0x18000c227  test    byte ptr [rax], 2
0x18000c22a  jz      short loc_18000C279
0x18000c22c  cmp     [rax+8], rsi
0x18000c230  jz      short loc_18000C279
0x18000c232  or      dword ptr [rdx+4], 4
0x18000c236  mov     ecx, edi
0x18000c238  mov     rax, [r8+40h]
0x18000c23c  mov     r9d, ebx
0x18000c23f  mov     r10, [rax+8]
0x18000c243  lea     rax, [rdx+38h]
0x18000c247  test    rcx, rcx
0x18000c24a  jz      short loc_18000C26B
0x18000c24c  movzx   r11d, word ptr [r10]
0x18000c250  test    r11w, r11w
0x18000c254  jz      short loc_18000C26B
0x18000c256  mov     [rax], r11w
0x18000c25a  add     r10, 2
0x18000c25e  add     rax, 2
0x18000c262  dec     rcx
0x18000c265  sub     r9, 1
0x18000c269  jnz     short loc_18000C247
0x18000c26b  test    r9, r9
0x18000c26e  lea     rcx, [rax-2]
0x18000c272  cmovnz  rcx, rax
0x18000c276  mov     [rcx], si
0x18000c279  mov     rax, [r8+0D0h]
0x18000c280  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000c287  jnz     short loc_18000C299
0x18000c289  mov     rax, [r8+0D8h]
0x18000c290  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18000c297  jz      short loc_18000C2AA
0x18000c299  or      dword ptr [rdx+4], 1
0x18000c29d  movups  xmm0, xmmword ptr [r8+0D0h]
0x18000c2a5  movdqu  xmmword ptr [rdx+8], xmm0
0x18000c2aa  mov     eax, [rdx+4]
0x18000c2ad  lea     rcx, [r8+48h]
0x18000c2b1  cmp     [rcx], si
0x18000c2b4  jz      short loc_18000C2F3
0x18000c2b6  lea     rax, [rdx+38h]
0x18000c2ba  test    rdi, rdi
0x18000c2bd  jz      short loc_18000C2DE
0x18000c2bf  movzx   r9d, word ptr [rcx]
0x18000c2c3  test    r9w, r9w
0x18000c2c7  jz      short loc_18000C2DE
0x18000c2c9  mov     [rax], r9w
0x18000c2cd  add     rcx, 2
0x18000c2d1  add     rax, 2
0x18000c2d5  dec     rdi
0x18000c2d8  sub     rbx, 1
0x18000c2dc  jnz     short loc_18000C2BA
0x18000c2de  test    rbx, rbx
0x18000c2e1  lea     rcx, [rax-2]
0x18000c2e5  cmovnz  rcx, rax
0x18000c2e9  mov     [rcx], si
0x18000c2ec  or      dword ptr [rdx+4], 4
0x18000c2f0  mov     eax, [rdx+4]
0x18000c2f3  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicCollection.Data1
0x18000c2fa  or      eax, 2
0x18000c2fd  mov     [rdx+4], eax
0x18000c300  movdqu  xmmword ptr [rdx+18h], xmm0
0x18000c305  cmp     [r8+0E0h], sil
0x18000c30c  jz      short loc_18000C315
0x18000c30e  bts     eax, 9
0x18000c312  mov     [rdx+4], eax
0x18000c315  xor     eax, eax
0x18000c317  pop     rdi
0x18000c318  pop     rsi
0x18000c319  pop     rbx
0x18000c31a  retn
```
