# CContainer::GetDescriptor(_DMUS_OBJECTDESC *)

- ea: `0x18000e360`
- end: `0x18000e4c4`
- name: `?GetDescriptor@CContainer@@UEAAJPEAU_DMUS_OBJECTDESC@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CContainer *__hidden this, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001ef0`
- `0x18000e360`

## pseudocode

```c
__int64 __fastcall CContainer::GetDescriptor(CContainer *this, struct _DMUS_OBJECTDESC *a2)
{
  _WORD *v5; // r10
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  _WORD *v10; // rax
  bool v11; // zf
  _WORD *v12; // rcx
  _WORD *v13; // rdx
  _WORD *v14; // rax
  __int64 v15; // rcx
  _WORD *v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  _WORD *v20; // rcx

  if ( !a2 )
    return 2147500035LL;
  if ( *((_BYTE *)this + 864) )
    return 142086678;
  memset_0((char *)a2 + 4, 0, 0x354u);
  *(_DWORD *)a2 = 856;
  v5 = (_WORD *)((char *)this + 88);
  v6 = 2147483646;
  v7 = 64;
  v8 = 2147483646;
  v9 = 64;
  *(GUID *)((char *)a2 + 24) = CLSID_DirectMusicContainer;
  *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)((char *)this + 56);
  *((_QWORD *)a2 + 5) = *((_QWORD *)this + 9);
  *((_QWORD *)a2 + 6) = *((_QWORD *)this + 10);
  v10 = (_WORD *)((char *)a2 + 56);
  do
  {
    if ( !v8 )
      break;
    if ( !*v5 )
      break;
    *v10++ = *v5++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0;
  v12 = v10 - 1;
  v13 = (_WORD *)((char *)this + 216);
  if ( !v11 )
    v12 = v10;
  v14 = (_WORD *)((char *)a2 + 184);
  *v12 = 0;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*v13 )
      break;
    *v14++ = *v13++;
    --v15;
    --v7;
  }
  while ( v7 );
  v16 = v14 - 1;
  v17 = 260;
  if ( v7 )
    v16 = v14;
  v18 = (_WORD *)((char *)a2 + 312);
  *v16 = 0;
  v19 = (_WORD *)((char *)this + 344);
  do
  {
    if ( !v6 )
      break;
    if ( !*v19 )
      break;
    *v18++ = *v19++;
    --v6;
    --v17;
  }
  while ( v17 );
  v20 = v18 - 1;
  if ( v17 )
    v20 = v18;
  *v20 = 0;
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 13) | 2;
  return 0;
}

```

## disassembly

```asm
0x18000e360  mov     [rsp+arg_0], rbx
0x18000e365  mov     [rsp+arg_8], rsi
0x18000e36a  push    rdi
0x18000e36b  sub     rsp, 20h
0x18000e36f  xor     esi, esi
0x18000e371  mov     rbx, rdx
0x18000e374  mov     rdi, rcx
0x18000e377  test    rdx, rdx
0x18000e37a  jnz     short loc_18000E386
0x18000e37c  mov     eax, 80004003h
0x18000e381  jmp     loc_18000E4B4
0x18000e386  cmp     [rcx+360h], sil
0x18000e38d  jz      short loc_18000E399
0x18000e38f  mov     eax, 8781216h
0x18000e394  jmp     loc_18000E4B4
0x18000e399  lea     rcx, [rdx+4]; void *
0x18000e39d  mov     r8d, 354h; Size
0x18000e3a3  xor     edx, edx; Val
0x18000e3a5  call    memset_0
0x18000e3aa  mov     dword ptr [rbx], 358h
0x18000e3b0  lea     r10, [rdi+58h]
0x18000e3b4  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicContainer.Data1
0x18000e3bb  mov     r9d, 7FFFFFFEh
0x18000e3c1  mov     r8d, 40h ; '@'
0x18000e3c7  mov     ecx, r9d
0x18000e3ca  mov     edx, r8d
0x18000e3cd  movdqu  xmmword ptr [rbx+18h], xmm0
0x18000e3d2  movups  xmm0, xmmword ptr [rdi+38h]
0x18000e3d6  movdqu  xmmword ptr [rbx+8], xmm0
0x18000e3db  mov     rax, [rdi+48h]
0x18000e3df  mov     [rbx+28h], rax
0x18000e3e3  mov     rax, [rdi+50h]
0x18000e3e7  mov     [rbx+30h], rax
0x18000e3eb  lea     rax, [rbx+38h]
0x18000e3ef  test    rcx, rcx
0x18000e3f2  jz      short loc_18000E413
0x18000e3f4  movzx   r11d, word ptr [r10]
0x18000e3f8  test    r11w, r11w
0x18000e3fc  jz      short loc_18000E413
0x18000e3fe  mov     [rax], r11w
0x18000e402  add     r10, 2
0x18000e406  add     rax, 2
0x18000e40a  dec     rcx
0x18000e40d  sub     rdx, 1
0x18000e411  jnz     short loc_18000E3EF
0x18000e413  test    rdx, rdx
0x18000e416  lea     rcx, [rax-2]
0x18000e41a  lea     rdx, [rdi+0D8h]
0x18000e421  cmovnz  rcx, rax
0x18000e425  lea     rax, [rbx+0B8h]
0x18000e42c  mov     [rcx], si
0x18000e42f  mov     rcx, r9
0x18000e432  test    rcx, rcx
0x18000e435  jz      short loc_18000E456
0x18000e437  movzx   r10d, word ptr [rdx]
0x18000e43b  test    r10w, r10w
0x18000e43f  jz      short loc_18000E456
0x18000e441  mov     [rax], r10w
0x18000e445  add     rdx, 2
0x18000e449  add     rax, 2
0x18000e44d  dec     rcx
0x18000e450  sub     r8, 1
0x18000e454  jnz     short loc_18000E432
0x18000e456  lea     rcx, [rax-2]
0x18000e45a  test    r8, r8
0x18000e45d  mov     edx, 104h
0x18000e462  cmovnz  rcx, rax
0x18000e466  lea     rax, [rbx+138h]
0x18000e46d  mov     [rcx], si
0x18000e470  lea     rcx, [rdi+158h]
0x18000e477  test    r9, r9
0x18000e47a  jz      short loc_18000E49B
0x18000e47c  movzx   r8d, word ptr [rcx]
0x18000e480  test    r8w, r8w
0x18000e484  jz      short loc_18000E49B
0x18000e486  mov     [rax], r8w
0x18000e48a  add     rcx, 2
0x18000e48e  add     rax, 2
0x18000e492  dec     r9
0x18000e495  sub     rdx, 1
0x18000e499  jnz     short loc_18000E477
0x18000e49b  lea     rcx, [rax-2]
0x18000e49f  test    rdx, rdx
0x18000e4a2  cmovnz  rcx, rax
0x18000e4a6  mov     [rcx], si
0x18000e4a9  mov     eax, [rdi+34h]
0x18000e4ac  or      eax, 2
0x18000e4af  mov     [rbx+4], eax
0x18000e4b2  xor     eax, eax
0x18000e4b4  mov     rbx, [rsp+28h+arg_0]
0x18000e4b9  mov     rsi, [rsp+28h+arg_8]
0x18000e4be  add     rsp, 20h
0x18000e4c2  pop     rdi
0x18000e4c3  retn
```
