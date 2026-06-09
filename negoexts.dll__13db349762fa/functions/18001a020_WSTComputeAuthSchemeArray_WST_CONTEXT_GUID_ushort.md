# WSTComputeAuthSchemeArray(_WST_CONTEXT *,_GUID * *,ushort *)

- ea: `0x18001a020`
- end: `0x18001a38a`
- name: `?WSTComputeAuthSchemeArray@@YAJPEAU_WST_CONTEXT@@PEAPEAU_GUID@@PEAG@Z`
- size: `874`
- prototype: `__int64 __fastcall(struct _WST_CONTEXT *, struct _GUID **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x1800027e4`
- `0x18000285c`
- `0x1800028a0`
- `0x18000706c`
- `0x18000c528`
- `0x18000ec28`
- `0x1800157d8`
- `0x18001a020`
- `0x18001ece2`

## pseudocode

```c
__int64 __fastcall WSTComputeAuthSchemeArray(struct _WST_CONTEXT *a1, struct _GUID **a2, unsigned __int16 *a3)
{
  unsigned __int16 v3; // bx
  struct _GUID **v4; // r14
  struct _GUID *v7; // rax
  int v8; // r12d
  struct _GUID *v9; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  struct _WST_ACTIVE_ENGINE_CONTEXT *v12; // rax
  struct _WST_ACTIVE_ENGINE_CONTEXT *v13; // r14
  int v14; // r15d
  struct _WST_CONTEXT *i; // rbx
  unsigned __int8 *v16; // rdx
  int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  struct _WST_CONTEXT *v20; // r8
  struct _WST_CONTEXT *v21; // rax
  struct _WST_MESSAGE *v22; // rcx
  __int64 v23; // rbp
  __int64 v24; // r9
  int v25; // r8d
  struct _GUID *v26; // rax
  unsigned int v27; // r14d
  int j; // r15d
  unsigned int v29; // ebp
  unsigned int v30; // r10d
  int v31; // ecx
  unsigned int v32; // r9d
  unsigned int v33; // r10d
  unsigned int v34; // eax
  struct _GUID *v35; // rdx
  __int64 v36; // rax
  unsigned __int16 v38; // [rsp+70h] [rbp+8h] BYREF
  struct _GUID **v39; // [rsp+78h] [rbp+10h]

  v39 = a2;
  v4 = a2;
  v38 = *((_WORD *)a1 + 76);
  v3 = v38;
  v7 = (struct _GUID *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 16LL * v38);
  v8 = 0;
  v9 = v7;
  if ( v7 )
  {
    memcpy_0(v7, *((const void **)a1 + 18), 16LL * *((unsigned __int16 *)a1 + 76));
    if ( *((_DWORD *)a1 + 39) )
    {
      v11 = 0;
      if ( v3 )
      {
        do
        {
          v12 = WSTGetActiveContextByAuthScheme(a1, &v9[v11]);
          v13 = v12;
          if ( v12 && (!*((_QWORD *)v12 + 6) || *((_DWORD *)v12 + 34) || !*((_DWORD *)v12 + 35)) )
          {
            WSTRemoveAuthSchemeFromArray((__int64)v9, &v38, v11);
            v14 = 0;
            --v11;
            for ( i = (struct _WST_CONTEXT *)*((_QWORD *)a1 + 11);
                  i != (struct _WST_CONTEXT *)((char *)a1 + 88);
                  i = *(struct _WST_CONTEXT **)i )
            {
              v16 = (unsigned __int8 *)i + 24;
              if ( v14 )
              {
                v17 = v14++;
                *(_DWORD *)(*(_QWORD *)v16 + 12LL) = v17;
              }
              v18 = *(_QWORD *)v16;
              if ( *(_DWORD *)(*(_QWORD *)v16 + 8LL) == 2 )
              {
                v19 = *((_QWORD *)v13 + 3) - *(_QWORD *)(v18 + 40);
                if ( !v19 )
                  v19 = *((_QWORD *)v13 + 4) - *(_QWORD *)(v18 + 48);
                if ( !v19 )
                {
                  v20 = *(struct _WST_CONTEXT **)i;
                  if ( *(struct _WST_CONTEXT **)(*(_QWORD *)i + 8LL) != i
                    || (v21 = (struct _WST_CONTEXT *)*((_QWORD *)i + 1), *(struct _WST_CONTEXT **)v21 != i) )
                  {
                    __fastfail(3u);
                  }
                  *(_QWORD *)v21 = v20;
                  v22 = i;
                  *((_QWORD *)v20 + 1) = v21;
                  i = v21;
                  v14 = *(_DWORD *)(*(_QWORD *)v16 + 12LL);
                  WSTFreeWstMessage(v22, v16, (unsigned int)v20);
                }
              }
            }
            v3 = v38;
            v8 = 0;
          }
          ++v11;
        }
        while ( v11 < v3 );
        v4 = v39;
      }
      if ( !v3 )
      {
        v10 = -2146893042;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids);
        goto LABEL_57;
      }
      if ( *((struct _WST_CONTEXT **)a1 + 11) != (struct _WST_CONTEXT *)((char *)a1 + 88) )
      {
        v23 = *((_QWORD *)a1 + 12);
        v24 = *((unsigned int *)a1 + 35);
        v25 = *(_DWORD *)(*(_QWORD *)(v23 + 24) + 12LL) + 1;
        if ( (_DWORD)v24 != v25 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids,
              v24,
              v25);
          *((_DWORD *)a1 + 35) = *(_DWORD *)(*(_QWORD *)(v23 + 24) + 12LL) + 1;
        }
      }
      v26 = (struct _GUID *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 16LL * v3);
      *v4 = v26;
      if ( !v26 )
      {
        v10 = -1073741801;
        goto LABEL_57;
      }
      *a3 = v3;
      v27 = 0;
      for ( j = v3; v3 && v27 < *a3 && j; --j )
      {
        v29 = 0;
        v30 = 0;
        do
        {
          v31 = *((_DWORD *)WSTGetActiveContextByAuthScheme(a1, &v9[v30]) + 35);
          v34 = v33;
          if ( v8 >= v31 )
          {
            v34 = v29;
            v31 = v8;
          }
          v30 = v33 + 1;
          v29 = v34;
          v8 = v31;
        }
        while ( v30 < v32 );
        if ( !v31 || v34 >= v32 )
        {
          v10 = -1073741811;
          goto LABEL_57;
        }
        do
        {
          if ( v27 >= *a3 )
            break;
          if ( *((_DWORD *)WSTGetActiveContextByAuthScheme(a1, &v9[v29]) + 35) == v8 )
          {
            v36 = v27++;
            (*v39)[v36] = *v35;
            WSTRemoveAuthSchemeFromArray((__int64)v9, &v38, v29);
            v3 = v38;
            --v29;
          }
          ++v29;
        }
        while ( v29 < v3 );
        v8 = 0;
      }
    }
    else
    {
      *v4 = v9;
      v9 = 0;
      *a3 = v3;
    }
    v10 = 0;
    if ( !v9 )
      return v10;
LABEL_57:
    WSTFree(v9);
    return v10;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x18001a020  mov     [rsp+arg_10], rbx
0x18001a025  mov     [rsp+arg_8], rdx
0x18001a02a  push    rbp
0x18001a02b  push    rsi
0x18001a02c  push    rdi
0x18001a02d  push    r12
0x18001a02f  push    r13
0x18001a031  push    r14
0x18001a033  push    r15
0x18001a035  sub     rsp, 30h
0x18001a039  movzx   ebx, word ptr [rcx+98h]
0x18001a040  mov     r14, rdx
0x18001a043  mov     rsi, rcx
0x18001a046  mov     [rsp+68h+arg_0], bx
0x18001a04b  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18001a052  mov     edx, ebx
0x18001a054  shl     rdx, 4; unsigned __int64
0x18001a058  mov     r13, r8
0x18001a05b  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001a060  xor     r12d, r12d
0x18001a063  mov     rdi, rax
0x18001a066  test    rax, rax
0x18001a069  jnz     short loc_18001A075
0x18001a06b  mov     ebx, 0C0000017h
0x18001a070  jmp     loc_18001A370
0x18001a075  movzx   r8d, word ptr [rsi+98h]
0x18001a07d  mov     rcx, rdi; void *
0x18001a080  mov     rdx, [rsi+90h]; Src
0x18001a087  shl     r8, 4; Size
0x18001a08b  call    memcpy_0
0x18001a090  cmp     [rsi+9Ch], r12d
0x18001a097  jz      loc_18001A355
0x18001a09d  mov     ebp, r12d
0x18001a0a0  cmp     r12w, bx
0x18001a0a4  jnb     loc_18001A18C
0x18001a0aa  mov     edx, ebp
0x18001a0ac  mov     rcx, rsi; struct _WST_CONTEXT *
0x18001a0af  shl     rdx, 4
0x18001a0b3  add     rdx, rdi; struct _GUID *
0x18001a0b6  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18001a0bb  mov     r14, rax
0x18001a0be  test    rax, rax
0x18001a0c1  jz      loc_18001A17A
0x18001a0c7  cmp     [rax+30h], r12
0x18001a0cb  jz      short loc_18001A0E3
0x18001a0cd  cmp     [rax+88h], r12d
0x18001a0d4  jnz     short loc_18001A0E3
0x18001a0d6  cmp     [rax+8Ch], r12d
0x18001a0dd  jnz     loc_18001A17A
0x18001a0e3  mov     r8d, ebp; unsigned int
0x18001a0e6  lea     rdx, [rsp+68h+arg_0]; unsigned __int16 *
0x18001a0eb  mov     rcx, rdi; struct _GUID *
0x18001a0ee  call    ?WSTRemoveAuthSchemeFromArray@@YAXPEAU_GUID@@PEAGK@Z; WSTRemoveAuthSchemeFromArray(_GUID *,ushort *,ulong)
0x18001a0f3  mov     r15d, r12d
0x18001a0f6  dec     ebp
0x18001a0f8  lea     r12, [rsi+58h]
0x18001a0fc  mov     rbx, [r12]
0x18001a100  jmp     short loc_18001A16D
0x18001a102  lea     rdx, [rbx+18h]
0x18001a106  test    r15d, r15d
0x18001a109  jz      short loc_18001A117
0x18001a10b  mov     rax, [rdx]
0x18001a10e  mov     ecx, r15d
0x18001a111  inc     r15d
0x18001a114  mov     [rax+0Ch], ecx
0x18001a117  mov     rcx, [rdx]
0x18001a11a  cmp     dword ptr [rcx+8], 2
0x18001a11e  jnz     short loc_18001A16A
0x18001a120  mov     rax, [r14+18h]
0x18001a124  sub     rax, [rcx+28h]
0x18001a128  jnz     short loc_18001A132
0x18001a12a  mov     rax, [r14+20h]
0x18001a12e  sub     rax, [rcx+30h]
0x18001a132  test    rax, rax
0x18001a135  jnz     short loc_18001A16A
0x18001a137  mov     r8, [rbx]
0x18001a13a  cmp     [r8+8], rbx
0x18001a13e  jnz     loc_18001A1D1
0x18001a144  mov     rax, [rbx+8]
0x18001a148  cmp     [rax], rbx
0x18001a14b  jnz     loc_18001A1D1
0x18001a151  mov     [rax], r8
0x18001a154  mov     rcx, rbx; struct _WST_MESSAGE *
0x18001a157  mov     [r8+8], rax
0x18001a15b  mov     rbx, rax
0x18001a15e  mov     rax, [rdx]
0x18001a161  mov     r15d, [rax+0Ch]
0x18001a165  call    ?WSTFreeWstMessage@@YAXPEAU_WST_MESSAGE@@@Z; WSTFreeWstMessage(_WST_MESSAGE *)
0x18001a16a  mov     rbx, [rbx]
0x18001a16d  cmp     rbx, r12
0x18001a170  jnz     short loc_18001A102
0x18001a172  movzx   ebx, [rsp+68h+arg_0]
0x18001a177  xor     r12d, r12d
0x18001a17a  inc     ebp
0x18001a17c  movzx   eax, bx
0x18001a17f  cmp     ebp, eax
0x18001a181  jb      loc_18001A0AA
0x18001a187  mov     r14, [rsp+68h+arg_8]
0x18001a18c  test    bx, bx
0x18001a18f  jnz     short loc_18001A1D8
0x18001a191  mov     ebx, 8009030Eh
0x18001a196  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a19d  lea     rax, WPP_GLOBAL_Control
0x18001a1a4  cmp     rcx, rax
0x18001a1a7  jz      loc_18001A368
0x18001a1ad  test    byte ptr [rcx+1Ch], 2
0x18001a1b1  jz      loc_18001A368
0x18001a1b7  mov     rcx, [rcx+10h]
0x18001a1bb  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18001a1c2  mov     edx, 42h ; 'B'
0x18001a1c7  call    WPP_SF_
0x18001a1cc  jmp     loc_18001A368
0x18001a1d1  mov     ecx, 3
0x18001a1d6  int     29h; Win8: RtlFailFast(ecx)
0x18001a1d8  lea     rax, [rsi+58h]
0x18001a1dc  cmp     [rax], rax
0x18001a1df  jz      short loc_18001A23E
0x18001a1e1  mov     rbp, [rsi+60h]
0x18001a1e5  mov     r9d, [rsi+8Ch]
0x18001a1ec  mov     rax, [rbp+18h]
0x18001a1f0  mov     r8d, [rax+0Ch]
0x18001a1f4  inc     r8d
0x18001a1f7  cmp     r9d, r8d
0x18001a1fa  jz      short loc_18001A23E
0x18001a1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a203  lea     rax, WPP_GLOBAL_Control
0x18001a20a  cmp     rcx, rax
0x18001a20d  jz      short loc_18001A22F
0x18001a20f  test    byte ptr [rcx+1Ch], 2
0x18001a213  jz      short loc_18001A22F
0x18001a215  mov     rcx, [rcx+10h]
0x18001a219  mov     edx, 43h ; 'C'
0x18001a21e  mov     [rsp+68h+var_48], r8d
0x18001a223  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18001a22a  call    WPP_SF_Dd
0x18001a22f  mov     rax, [rbp+18h]
0x18001a233  mov     ecx, [rax+0Ch]
0x18001a236  inc     ecx
0x18001a238  mov     [rsi+8Ch], ecx
0x18001a23e  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18001a245  movzx   edx, bx
0x18001a248  shl     rdx, 4; unsigned __int64
0x18001a24c  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001a251  mov     [r14], rax
0x18001a254  test    rax, rax
0x18001a257  jnz     short loc_18001A263
0x18001a259  mov     ebx, 0C0000017h
0x18001a25e  jmp     loc_18001A368
0x18001a263  mov     [r13+0], bx
0x18001a268  mov     r14d, r12d
0x18001a26b  movzx   r15d, bx
0x18001a26f  jmp     short loc_18001A274
0x18001a271  xor     r12d, r12d
0x18001a274  test    bx, bx
0x18001a277  jz      loc_18001A360
0x18001a27d  movzx   eax, word ptr [r13+0]
0x18001a282  cmp     r14d, eax
0x18001a285  jnb     loc_18001A360
0x18001a28b  test    r15d, r15d
0x18001a28e  jz      loc_18001A360
0x18001a294  xor     r11d, r11d
0x18001a297  movzx   r9d, bx
0x18001a29b  mov     ebp, r11d
0x18001a29e  mov     r10d, r11d
0x18001a2a1  test    r9d, r9d
0x18001a2a4  jz      loc_18001A34E
0x18001a2aa  mov     edx, r10d
0x18001a2ad  mov     rcx, rsi; struct _WST_CONTEXT *
0x18001a2b0  shl     rdx, 4
0x18001a2b4  add     rdx, rdi; struct _GUID *
0x18001a2b7  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18001a2bc  mov     ecx, [rax+8Ch]
0x18001a2c2  cmp     r12d, ecx
0x18001a2c5  mov     eax, r10d
0x18001a2c8  cmovge  eax, ebp
0x18001a2cb  cmovge  ecx, r12d
0x18001a2cf  inc     r10d
0x18001a2d2  mov     ebp, eax
0x18001a2d4  mov     r12d, ecx
0x18001a2d7  cmp     r10d, r9d
0x18001a2da  jb      short loc_18001A2AA
0x18001a2dc  test    ecx, ecx
0x18001a2de  jz      short loc_18001A34E
0x18001a2e0  cmp     eax, r9d
0x18001a2e3  jnb     short loc_18001A34E
0x18001a2e5  dec     r15d
0x18001a2e8  movzx   eax, word ptr [r13+0]
0x18001a2ed  cmp     r14d, eax
0x18001a2f0  jnb     loc_18001A271
0x18001a2f6  mov     edx, ebp
0x18001a2f8  mov     rcx, rsi; struct _WST_CONTEXT *
0x18001a2fb  shl     rdx, 4
0x18001a2ff  add     rdx, rdi; struct _GUID *
0x18001a302  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18001a307  cmp     [rax+8Ch], r12d
0x18001a30e  jnz     short loc_18001A340
0x18001a310  movups  xmm0, xmmword ptr [rdx]
0x18001a313  mov     rcx, [rsp+68h+arg_8]
0x18001a318  lea     rdx, [rsp+68h+arg_0]; unsigned __int16 *
0x18001a31d  mov     eax, r14d
0x18001a320  mov     r8d, ebp; unsigned int
0x18001a323  shl     rax, 4
0x18001a327  inc     r14d
0x18001a32a  add     rax, [rcx]
0x18001a32d  mov     rcx, rdi; struct _GUID *
0x18001a330  movdqu  xmmword ptr [rax], xmm0
0x18001a334  call    ?WSTRemoveAuthSchemeFromArray@@YAXPEAU_GUID@@PEAGK@Z; WSTRemoveAuthSchemeFromArray(_GUID *,ushort *,ulong)
0x18001a339  movzx   ebx, [rsp+68h+arg_0]
0x18001a33e  dec     ebp
0x18001a340  inc     ebp
0x18001a342  movzx   eax, bx
0x18001a345  cmp     ebp, eax
0x18001a347  jb      short loc_18001A2E8
0x18001a349  jmp     loc_18001A271
0x18001a34e  mov     ebx, 0C000000Dh
0x18001a353  jmp     short loc_18001A368
0x18001a355  mov     [r14], rdi
0x18001a358  mov     rdi, r12
0x18001a35b  mov     [r13+0], bx
0x18001a360  mov     ebx, r12d
0x18001a363  test    rdi, rdi
0x18001a366  jz      short loc_18001A370
0x18001a368  mov     rcx, rdi; void *
0x18001a36b  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x18001a370  mov     eax, ebx
0x18001a372  mov     rbx, [rsp+68h+arg_10]
0x18001a37a  add     rsp, 30h
0x18001a37e  pop     r15
0x18001a380  pop     r14
0x18001a382  pop     r13
0x18001a384  pop     r12
0x18001a386  pop     rdi
0x18001a387  pop     rsi
0x18001a388  pop     rbp
0x18001a389  retn
```
