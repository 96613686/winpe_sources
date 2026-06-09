# WSTCreateUserModeContext(unsigned __int64,_SecBuffer *,_WST_USERMODE_CONTEXT * *)

- ea: `0x18002ee60`
- end: `0x18002f16c`
- name: `?WSTCreateUserModeContext@@YAJ_KPEAU_SecBuffer@@PEAPEAU_WST_USERMODE_CONTEXT@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(unsigned __int64, struct _SecBuffer *, struct _WST_USERMODE_CONTEXT **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024260`
- `0x18002f560`

## callees

- `0x180018870`
- `0x18001a5b0`
- `0x180023d9c`
- `0x18002b408`
- `0x18002ee60`
- `0x18002f384`
- `0x18002f698`
- `0x1800436dc`
- `0x180044f8c`

## pseudocode

```c
__int64 __fastcall WSTCreateUserModeContext(
        struct _WST_USERMODE_CONTEXT *a1,
        struct _SecBuffer *a2,
        struct _WST_USERMODE_CONTEXT **a3)
{
  bool v3; // cf
  char *pvBuffer; // rsi
  int v8; // eax
  struct _WST_USERMODE_CONTEXT *v9; // rdi
  int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  basessp::BaseSSP *v13; // rcx
  __int64 v14; // rbp
  void *v15; // rax
  __int16 v16; // bx
  void *v17; // rax
  __int16 v18; // cx
  void *v19; // rax
  __int16 v20; // ax
  unsigned int v21; // eax
  basessp::BaseSSP *v22; // rcx
  void *v23; // rax
  void *v24; // rdx
  basessp::BaseSSP *v25; // rcx
  char *v26; // rbx
  unsigned int v27; // esi
  void *v28; // rax
  struct _WST_USERMODE_CONTEXT *v29; // rax
  __int128 v30; // [rsp+30h] [rbp-68h]
  struct _WST_USERMODE_CONTEXT *v31; // [rsp+A8h] [rbp+10h] BYREF

  v3 = a2->cbBuffer < 0x48;
  v31 = 0;
  v30 = 0;
  if ( !v3 )
  {
    pvBuffer = (char *)a2->pvBuffer;
    v8 = WSTAllocateUserModeContext(&v31);
    v9 = v31;
    v10 = v8;
    if ( v8 < 0 )
      goto LABEL_30;
    *((_QWORD *)v31 + 11) = *((_QWORD *)pvBuffer + 7);
    v11 = *((_DWORD *)pvBuffer + 13);
    if ( v11 >= 0xFFFD )
    {
      v10 = -1073741637;
      goto LABEL_30;
    }
    v12 = 0;
    v13 = (basessp::BaseSSP *)(v11 >> 1);
    while ( 1 )
    {
      if ( v12 >= (unsigned int)v13 )
        goto LABEL_17;
      v14 = 2LL * v12;
      if ( *(_WORD *)&pvBuffer[v14 + *((unsigned int *)pvBuffer + 12)] == 92 )
        break;
      ++v12;
    }
    v15 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v14 + 2);
    *((_QWORD *)v9 + 15) = v15;
    if ( v15 )
    {
      v16 = 2 * v12;
      *((_WORD *)v9 + 56) = v16;
      *((_WORD *)v9 + 57) = v16 + 2;
      memcpy_0(*((void **)v9 + 15), &pvBuffer[*((unsigned int *)pvBuffer + 12)], *((unsigned __int16 *)v9 + 56));
      v17 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, *((unsigned int *)pvBuffer + 13) - v14);
      *((_QWORD *)v9 + 13) = v17;
      if ( v17 )
      {
        v18 = *((_WORD *)pvBuffer + 26) - v16;
        *((_WORD *)v9 + 48) = v18 - 2;
        *((_WORD *)v9 + 49) = v18;
        memcpy_0(
          *((void **)v9 + 13),
          &pvBuffer[v14 + 2 + *((unsigned int *)pvBuffer + 12)],
          *((unsigned __int16 *)v9 + 48));
LABEL_17:
        if ( !*((_WORD *)v9 + 49) )
        {
          v19 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, *((unsigned int *)pvBuffer + 13) + 2LL);
          *((_QWORD *)v9 + 13) = v19;
          if ( !v19 )
            goto LABEL_14;
          v20 = *((_WORD *)pvBuffer + 26);
          *((_WORD *)v9 + 48) = v20;
          *((_WORD *)v9 + 49) = v20 + 2;
          memcpy_0(*((void **)v9 + 13), &pvBuffer[*((unsigned int *)pvBuffer + 12)], *((unsigned __int16 *)v9 + 48));
        }
        if ( *((_DWORD *)pvBuffer + 16) )
        {
          v21 = *((_DWORD *)pvBuffer + 17);
          v22 = Pku2uGlobalBaseSSP;
          *((_DWORD *)v9 + 36) = v21;
          v23 = basessp::BaseSSP::WSTAllocate(v22, v21);
          *((_QWORD *)v9 + 17) = v23;
          if ( !v23 )
          {
            v10 = -1073741670;
LABEL_30:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                12,
                (unsigned int)WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids,
                v10,
                (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtmgr.cxx",
                210);
            if ( v9 )
              WSTFreeUserModeContext(v9);
            return (unsigned int)v10;
          }
          memcpy_0(v23, &pvBuffer[*((unsigned int *)pvBuffer + 16)], *((unsigned int *)v9 + 36));
        }
        *((_QWORD *)v9 + 4) = *((unsigned int *)pvBuffer + 2);
        *((_DWORD *)pvBuffer + 2) = 0;
        v24 = (void *)*((_QWORD *)v9 + 4);
        if ( v24 )
        {
          v10 = basessp::BaseSSP::WSTCreateTokenDacl(v13, v24);
          if ( v10 < 0 )
            goto LABEL_30;
        }
        v25 = Pku2uGlobalBaseSSP;
        *((_DWORD *)v9 + 20) = *((_DWORD *)pvBuffer + 10);
        *((_DWORD *)v9 + 21) = *((_DWORD *)pvBuffer + 11);
        LODWORD(v30) = *((_DWORD *)pvBuffer + 3);
        v26 = &pvBuffer[*((unsigned int *)pvBuffer + 4)];
        v27 = *((_DWORD *)pvBuffer + 5);
        DWORD2(v30) = v27;
        *(_OWORD *)((char *)v9 + 40) = v30;
        *((_QWORD *)v9 + 7) = v26;
        v28 = basessp::BaseSSP::WSTAllocate(v25, v27);
        *((_QWORD *)v9 + 7) = v28;
        if ( v28 )
        {
          memcpy_0(v28, v26, v27);
          *((_DWORD *)v9 + 4) = 1;
          *((_QWORD *)v9 + 1) = 0;
          v29 = v9;
          if ( a1 )
            v29 = a1;
          *(_QWORD *)v9 = 0;
          *((_QWORD *)v9 + 3) = v29;
          v10 = WSTInsertUserModeContext(v9);
          *a3 = v9;
          if ( v10 >= 0 )
            return (unsigned int)v10;
          goto LABEL_30;
        }
      }
    }
LABEL_14:
    v10 = -1073741801;
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids,
      a2->cbBuffer,
      72);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18002ee60  mov     rax, rsp
0x18002ee63  push    rbx
0x18002ee64  push    rbp
0x18002ee65  push    rsi
0x18002ee66  push    rdi
0x18002ee67  push    r12
0x18002ee69  push    r13
0x18002ee6b  push    r14
0x18002ee6d  push    r15
0x18002ee6f  sub     rsp, 58h
0x18002ee73  xor     r12d, r12d
0x18002ee76  xorps   xmm0, xmm0
0x18002ee79  cmp     dword ptr [rdx], 48h ; 'H'
0x18002ee7c  mov     r15, r8
0x18002ee7f  mov     rsi, rdx
0x18002ee82  mov     [rax+10h], r12
0x18002ee86  mov     r14, rcx
0x18002ee89  movups  xmmword ptr [rax-68h], xmm0
0x18002ee8d  jnb     short loc_18002EED2
0x18002ee8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee96  lea     rax, WPP_GLOBAL_Control
0x18002ee9d  cmp     rcx, rax
0x18002eea0  jz      short loc_18002EEC8
0x18002eea2  test    byte ptr [rcx+1Ch], 1
0x18002eea6  jz      short loc_18002EEC8
0x18002eea8  mov     r9d, [rsi]
0x18002eeab  lea     edx, [r12+0Bh]
0x18002eeb0  mov     rcx, [rcx+10h]
0x18002eeb4  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002eebb  mov     dword ptr [rsp+98h+var_78], 48h ; 'H'
0x18002eec3  call    WPP_SF_dd
0x18002eec8  mov     eax, 0C000000Dh
0x18002eecd  jmp     loc_18002F15B
0x18002eed2  mov     rsi, [rdx+8]
0x18002eed6  lea     rcx, [rsp+98h+arg_8]; struct _WST_USERMODE_CONTEXT **
0x18002eede  call    ?WSTAllocateUserModeContext@@YAJPEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTAllocateUserModeContext(_WST_USERMODE_CONTEXT * *)
0x18002eee3  mov     rdi, [rsp+98h+arg_8]
0x18002eeeb  mov     ebx, eax
0x18002eeed  test    eax, eax
0x18002eeef  js      loc_18002F107
0x18002eef5  mov     rax, [rsi+38h]
0x18002eef9  mov     [rdi+58h], rax
0x18002eefd  mov     ecx, [rsi+34h]
0x18002ef00  cmp     ecx, 0FFFDh
0x18002ef06  jb      short loc_18002EF12
0x18002ef08  mov     ebx, 0C00000BBh
0x18002ef0d  jmp     loc_18002F107
0x18002ef12  mov     ebx, r12d
0x18002ef15  shr     ecx, 1
0x18002ef17  mov     r13d, 2
0x18002ef1d  cmp     ebx, ecx
0x18002ef1f  jnb     loc_18002EFCD
0x18002ef25  mov     eax, ebx
0x18002ef27  lea     rbp, [rax+rax]
0x18002ef2b  mov     eax, [rsi+30h]
0x18002ef2e  add     rax, rbp
0x18002ef31  cmp     word ptr [rax+rsi], 5Ch ; '\'
0x18002ef36  jz      short loc_18002EF3C
0x18002ef38  inc     ebx
0x18002ef3a  jmp     short loc_18002EF17
0x18002ef3c  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002ef43  lea     rdx, [rbp+2]; unsigned __int64
0x18002ef47  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002ef4c  mov     [rdi+78h], rax
0x18002ef50  test    rax, rax
0x18002ef53  jnz     short loc_18002EF5F
0x18002ef55  mov     ebx, 0C0000017h
0x18002ef5a  jmp     loc_18002F107
0x18002ef5f  add     bx, bx
0x18002ef62  mov     [rdi+70h], bx
0x18002ef66  lea     eax, [rbx+r13]
0x18002ef6a  mov     [rdi+72h], ax
0x18002ef6e  mov     edx, [rsi+30h]
0x18002ef71  movzx   r8d, word ptr [rdi+70h]; Size
0x18002ef76  add     rdx, rsi; Src
0x18002ef79  mov     rcx, [rdi+78h]; void *
0x18002ef7d  call    memcpy_0
0x18002ef82  mov     edx, [rsi+34h]
0x18002ef85  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002ef8c  sub     rdx, rbp; unsigned __int64
0x18002ef8f  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002ef94  mov     [rdi+68h], rax
0x18002ef98  test    rax, rax
0x18002ef9b  jz      short loc_18002EF55
0x18002ef9d  movzx   ecx, word ptr [rsi+34h]
0x18002efa1  sub     cx, bx
0x18002efa4  movzx   eax, cx
0x18002efa7  sub     ax, r13w
0x18002efab  mov     [rdi+60h], ax
0x18002efaf  mov     [rdi+62h], cx
0x18002efb3  mov     edx, [rsi+30h]
0x18002efb6  movzx   r8d, word ptr [rdi+60h]; Size
0x18002efbb  add     rdx, r13
0x18002efbe  mov     rcx, [rdi+68h]; void *
0x18002efc2  add     rdx, rbp
0x18002efc5  add     rdx, rsi; Src
0x18002efc8  call    memcpy_0
0x18002efcd  cmp     [rdi+62h], r12w
0x18002efd2  jnz     short loc_18002F017
0x18002efd4  mov     edx, [rsi+34h]
0x18002efd7  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002efde  add     rdx, r13; unsigned __int64
0x18002efe1  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002efe6  mov     [rdi+68h], rax
0x18002efea  test    rax, rax
0x18002efed  jz      loc_18002EF55
0x18002eff3  movzx   eax, word ptr [rsi+34h]
0x18002eff7  mov     [rdi+60h], ax
0x18002effb  add     ax, r13w
0x18002efff  mov     [rdi+62h], ax
0x18002f003  mov     edx, [rsi+30h]
0x18002f006  movzx   r8d, word ptr [rdi+60h]; Size
0x18002f00b  add     rdx, rsi; Src
0x18002f00e  mov     rcx, [rdi+68h]; void *
0x18002f012  call    memcpy_0
0x18002f017  cmp     [rsi+40h], r12d
0x18002f01b  jz      short loc_18002F05F
0x18002f01d  mov     eax, [rsi+44h]
0x18002f020  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002f027  mov     edx, eax; unsigned __int64
0x18002f029  mov     [rdi+90h], eax
0x18002f02f  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002f034  mov     [rdi+88h], rax
0x18002f03b  test    rax, rax
0x18002f03e  jnz     short loc_18002F04A
0x18002f040  mov     ebx, 0C000009Ah
0x18002f045  jmp     loc_18002F107
0x18002f04a  mov     edx, [rsi+40h]
0x18002f04d  mov     rcx, rax; void *
0x18002f050  mov     r8d, [rdi+90h]; Size
0x18002f057  add     rdx, rsi; Src
0x18002f05a  call    memcpy_0
0x18002f05f  mov     eax, [rsi+8]
0x18002f062  mov     [rdi+20h], rax
0x18002f066  mov     [rsi+8], r12d
0x18002f06a  mov     rdx, [rdi+20h]; void *
0x18002f06e  test    rdx, rdx
0x18002f071  jz      short loc_18002F082
0x18002f073  call    ?WSTCreateTokenDacl@BaseSSP@basessp@@QEAAJPEAX@Z; basessp::BaseSSP::WSTCreateTokenDacl(void *)
0x18002f078  mov     ebx, eax
0x18002f07a  test    eax, eax
0x18002f07c  js      loc_18002F107
0x18002f082  mov     eax, [rsi+28h]
0x18002f085  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002f08c  mov     [rdi+50h], eax
0x18002f08f  mov     eax, [rsi+2Ch]
0x18002f092  mov     [rdi+54h], eax
0x18002f095  mov     eax, [rsi+0Ch]
0x18002f098  mov     ebx, [rsi+10h]
0x18002f09b  mov     dword ptr [rsp+98h+var_68], eax
0x18002f09f  add     rbx, rsi
0x18002f0a2  mov     eax, [rsi+14h]
0x18002f0a5  mov     dword ptr [rsp+98h+var_68+8], eax
0x18002f0a9  mov     edx, eax; unsigned __int64
0x18002f0ab  movups  xmm0, [rsp+98h+var_68]
0x18002f0b0  mov     esi, eax
0x18002f0b2  movups  xmmword ptr [rdi+28h], xmm0
0x18002f0b6  mov     [rdi+38h], rbx
0x18002f0ba  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002f0bf  mov     [rdi+38h], rax
0x18002f0c3  test    rax, rax
0x18002f0c6  jz      loc_18002EF55
0x18002f0cc  mov     r8d, esi; Size
0x18002f0cf  mov     rdx, rbx; Src
0x18002f0d2  mov     rcx, rax; void *
0x18002f0d5  call    memcpy_0
0x18002f0da  test    r14, r14
0x18002f0dd  mov     dword ptr [rdi+10h], 1
0x18002f0e4  mov     [rdi+8], r12
0x18002f0e8  mov     rax, rdi
0x18002f0eb  cmovnz  rax, r14
0x18002f0ef  mov     [rdi], r12
0x18002f0f2  mov     rcx, rdi; struct _WST_USERMODE_CONTEXT *
0x18002f0f5  mov     [rdi+18h], rax
0x18002f0f9  call    ?WSTInsertUserModeContext@@YAJPEAU_WST_USERMODE_CONTEXT@@@Z; WSTInsertUserModeContext(_WST_USERMODE_CONTEXT *)
0x18002f0fe  mov     ebx, eax
0x18002f100  mov     [r15], rdi
0x18002f103  test    eax, eax
0x18002f105  jns     short loc_18002F159
0x18002f107  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f10e  lea     rax, WPP_GLOBAL_Control
0x18002f115  cmp     rcx, rax
0x18002f118  jz      short loc_18002F14C
0x18002f11a  test    byte ptr [rcx+1Ch], 1
0x18002f11e  jz      short loc_18002F14C
0x18002f120  mov     rcx, [rcx+10h]
0x18002f124  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002f12b  mov     edx, 0Ch
0x18002f130  mov     [rsp+98h+var_70], 3D2h
0x18002f138  mov     r9d, ebx
0x18002f13b  mov     [rsp+98h+var_78], rax
0x18002f140  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002f147  call    WPP_SF_dsd
0x18002f14c  test    rdi, rdi
0x18002f14f  jz      short loc_18002F159
0x18002f151  mov     rcx, rdi; struct _WST_USERMODE_CONTEXT *
0x18002f154  call    ?WSTFreeUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTFreeUserModeContext(_WST_USERMODE_CONTEXT *)
0x18002f159  mov     eax, ebx
0x18002f15b  add     rsp, 58h
0x18002f15f  pop     r15
0x18002f161  pop     r14
0x18002f163  pop     r13
0x18002f165  pop     r12
0x18002f167  pop     rdi
0x18002f168  pop     rsi
0x18002f169  pop     rbp
0x18002f16a  pop     rbx
0x18002f16b  retn
```
