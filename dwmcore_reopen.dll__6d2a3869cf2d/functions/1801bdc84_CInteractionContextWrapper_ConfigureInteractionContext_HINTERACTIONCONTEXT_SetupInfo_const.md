# CInteractionContextWrapper::ConfigureInteractionContext(HINTERACTIONCONTEXT__ *,SetupInfo const &)

- ea: `0x1801bdc84`
- end: `0x1801be038`
- name: `?ConfigureInteractionContext@CInteractionContextWrapper@@AEAAJPEAUHINTERACTIONCONTEXT__@@AEBUSetupInfo@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(CInteractionContextWrapper *__hidden this, struct HINTERACTIONCONTEXT__ *, const struct SetupInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1801bdbd0`
- `0x1801bdc0c`

## callees

- `0x1801b8018`
- `0x1801bdc84`
- `0x1801f2b50`
- `0x1802284b0`

## import_xrefs

- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801bdfe7`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801bdfe7`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801bdf62`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801bdf62`
- `NInput!SetPropertyInteractionContext` at `0x1801bdde0`
- `NInput!SetPropertyInteractionContext` at `0x1801bddfa`
- `NInput!SetPropertyInteractionContext` at `0x1801bde14`
- `NInput!SetPropertyInteractionContext` at `0x1801bdde0`
- `NInput!SetPropertyInteractionContext` at `0x1801bddfa`
- `NInput!SetPropertyInteractionContext` at `0x1801bde14`
- `NInput!ResetInteractionContext` at `0x1801bddc6`
- `NInput!ResetInteractionContext` at `0x1801bddc6`

## pseudocode

```c
__int64 __fastcall CInteractionContextWrapper::ConfigureInteractionContext(
        CInteractionContextWrapper *this,
        struct HINTERACTIONCONTEXT__ *a2,
        const struct SetupInfo *a3)
{
  int v3; // eax
  _BYTE *v6; // rdx
  _BYTE *v8; // rcx
  char v9; // r13
  char v10; // r14
  char v11; // bl
  int v12; // esi
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // ebx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  char v23; // [rsp+50h] [rbp-19h]
  char v24; // [rsp+51h] [rbp-18h]
  int v25; // [rsp+54h] [rbp-15h] BYREF
  int v26; // [rsp+58h] [rbp-11h] BYREF
  int v27; // [rsp+5Ch] [rbp-Dh] BYREF
  unsigned int v28; // [rsp+60h] [rbp-9h] BYREF
  CInteractionContextWrapper *v29; // [rsp+68h] [rbp-1h] BYREF
  _DWORD v30[6]; // [rsp+70h] [rbp+7h] BYREF

  v3 = *(_DWORD *)a3;
  v6 = (char *)a3 + 4;
  if ( *(_DWORD *)a3 == 2 )
  {
    if ( (*v6 & 0x40) != 0 )
    {
LABEL_6:
      v23 = 1;
      goto LABEL_11;
    }
  }
  else if ( v3 == 3 )
  {
    if ( (*v6 & 0x40) != 0 )
      goto LABEL_6;
LABEL_4:
    if ( v3 != 6 )
      goto LABEL_10;
    goto LABEL_5;
  }
  if ( v3 != 4 )
    goto LABEL_4;
LABEL_5:
  if ( (*v6 & 0x40) != 0 )
    goto LABEL_6;
LABEL_10:
  v23 = 0;
LABEL_11:
  if ( v3 == 2 )
  {
    if ( (*v6 & 0x80) != 0 )
    {
      v3 = 2;
      goto LABEL_24;
    }
    v8 = (char *)a3 + 4;
  }
  else
  {
    v8 = (char *)a3 + 4;
    if ( v3 == 3 )
    {
      if ( (*v6 & 0x80) != 0 )
      {
        v3 = 3;
        goto LABEL_24;
      }
      goto LABEL_21;
    }
  }
  if ( v3 != 4 )
  {
LABEL_21:
    if ( v3 == 6 && (*v8 & 0x80) != 0 )
    {
      v3 = 6;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  if ( (*v6 & 0x80) != 0 )
  {
    v3 = 4;
LABEL_24:
    v9 = 1;
    goto LABEL_26;
  }
LABEL_25:
  v9 = 0;
LABEL_26:
  if ( v3 == 2 )
  {
    if ( (*((_BYTE *)a3 + 4) & 3) != 0 )
      goto LABEL_63;
LABEL_28:
    if ( v3 == 4 )
      goto LABEL_29;
    goto LABEL_64;
  }
  if ( v3 != 3 )
    goto LABEL_28;
  if ( (*((_BYTE *)a3 + 4) & 3) != 0 )
    goto LABEL_63;
LABEL_64:
  if ( v3 != 6 )
    goto LABEL_30;
LABEL_29:
  if ( (*((_BYTE *)a3 + 4) & 3) == 0 )
  {
LABEL_30:
    v24 = 0;
    goto LABEL_31;
  }
LABEL_63:
  v24 = 1;
LABEL_31:
  if ( v3 == 2 )
  {
    if ( (*((_BYTE *)a3 + 4) & 0xC) != 0 )
      goto LABEL_68;
LABEL_33:
    if ( v3 == 4 )
      goto LABEL_34;
    goto LABEL_69;
  }
  if ( v3 != 3 )
    goto LABEL_33;
  if ( (*((_BYTE *)a3 + 4) & 0xC) != 0 )
    goto LABEL_68;
LABEL_69:
  if ( v3 != 6 )
    goto LABEL_35;
LABEL_34:
  if ( (*((_BYTE *)a3 + 4) & 0xC) == 0 )
  {
LABEL_35:
    v10 = 0;
    goto LABEL_36;
  }
LABEL_68:
  v10 = 1;
LABEL_36:
  if ( v3 == 2 )
  {
    if ( (*((_BYTE *)a3 + 4) & 0x30) != 0 )
    {
LABEL_73:
      v11 = 1;
      goto LABEL_41;
    }
LABEL_38:
    if ( v3 == 4 )
      goto LABEL_39;
    goto LABEL_74;
  }
  if ( v3 != 3 )
    goto LABEL_38;
  if ( (*((_BYTE *)a3 + 4) & 0x30) != 0 )
    goto LABEL_73;
LABEL_74:
  if ( v3 != 6 )
    goto LABEL_40;
LABEL_39:
  if ( (*((_BYTE *)a3 + 4) & 0x30) != 0 )
    goto LABEL_73;
LABEL_40:
  v11 = 0;
LABEL_41:
  v12 = ResetInteractionContext(a2, v6, 3, 4);
  if ( v12 >= 0 )
  {
    v12 = SetPropertyInteractionContext(a2, 1);
    if ( v12 >= 0 )
    {
      v12 = SetPropertyInteractionContext(a2, 3);
      if ( v12 >= 0 )
      {
        v12 = SetPropertyInteractionContext(a2, 2);
        if ( v12 >= 0 )
        {
          v13 = ((~*((_BYTE *)a3 + 16) & 2) << 10) | 1;
          if ( *((float *)a3 + 2) != 0.0 )
            v13 = ((~*((_BYTE *)a3 + 16) & 2) << 10) | 0x101;
          if ( *((float *)a3 + 3) != 0.0 )
            v13 |= 0x200u;
          v14 = v13 | 2;
          if ( !v24 )
            v14 = v13;
          v15 = v14 | 4;
          if ( !v10 )
            v15 = v14;
          v16 = v15 | 0x10;
          if ( !v11 )
            v16 = v15;
          v17 = v16 | 0x10000000;
          if ( *(_DWORD *)a3 != 3 )
            v17 = v16;
          v18 = v17 | 0x40000000;
          if ( (*((_BYTE *)a3 + 16) & 1) == 0 )
            v18 = v17;
          if ( *((_DWORD *)a3 + 5) == 1 )
          {
            v18 = v18 & 0x7FFFFCFF | 0x80000100;
          }
          else if ( *((_DWORD *)a3 + 5) == 2 )
          {
            v18 = v18 & 0x7FFFFCFF | 0x80000200;
          }
          v30[0] = 1;
          v30[1] = v18;
          v30[2] = 2;
          v30[4] = 4;
          v30[3] = v23 != 0 ? 5 : 0;
          v30[5] = v9 != 0 ? 5 : 0;
          v12 = SetInteractionConfigurationInteractionContext(a2, 3, v30);
          if ( (unsigned int)dword_1803B9858 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803B9858, 2) )
          {
            v25 = v12;
            v26 = v9 != 0 ? 5 : 0;
            v27 = v23 != 0 ? 5 : 0;
            v28 = v18;
            v29 = this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v19,
              (unsigned int)&unk_18039697C,
              v20,
              v21,
              (__int64)&v29,
              (__int64)&v28,
              (__int64)&v27,
              (__int64)&v26,
              (__int64)&v25);
          }
          if ( v12 >= 0 )
          {
            v12 = RegisterOutputCallbackInteractionContext(
                    a2,
                    CInteractionContextWrapper::s_InteractionContextCallback,
                    this);
            if ( v12 >= 0 && (!v23 && *((_DWORD *)this + 6) == 2 || !v9 && *((_DWORD *)this + 6) == 4) )
              *((_QWORD *)this + 3) = 0;
          }
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801bdc84  mov     [rsp-8+arg_10], rbx
0x1801bdc89  push    rbp
0x1801bdc8a  push    rsi
0x1801bdc8b  push    rdi
0x1801bdc8c  push    r12
0x1801bdc8e  push    r13
0x1801bdc90  push    r14
0x1801bdc92  push    r15
0x1801bdc94  lea     rbp, [rsp-27h]
0x1801bdc99  sub     rsp, 90h
0x1801bdca0  mov     rax, cs:__security_cookie
0x1801bdca7  xor     rax, rsp
0x1801bdcaa  mov     [rbp+57h+var_38], rax
0x1801bdcae  mov     eax, [r8]
0x1801bdcb1  mov     r11d, 6
0x1801bdcb7  mov     r12, rdx
0x1801bdcba  mov     rdi, r8
0x1801bdcbd  lea     rdx, [r8+4]
0x1801bdcc1  mov     r15, rcx
0x1801bdcc4  mov     cl, 40h ; '@'
0x1801bdcc6  lea     r8d, [r11-3]
0x1801bdcca  lea     r9d, [r11-2]
0x1801bdcce  cmp     eax, 2
0x1801bdcd1  jnz     short loc_1801BDCEB
0x1801bdcd3  test    [rdx], cl
0x1801bdcd5  jnz     short loc_1801BDCE5
0x1801bdcd7  cmp     eax, r9d
0x1801bdcda  jz      short loc_1801BDCE1
0x1801bdcdc  cmp     eax, r11d
0x1801bdcdf  jnz     short loc_1801BDCF6
0x1801bdce1  test    [rdx], cl
0x1801bdce3  jz      short loc_1801BDCF6
0x1801bdce5  mov     [rbp+57h+var_70], 1
0x1801bdce9  jmp     short loc_1801BDCFA
0x1801bdceb  cmp     eax, r8d
0x1801bdcee  jnz     short loc_1801BDCD7
0x1801bdcf0  test    [rdx], cl
0x1801bdcf2  jz      short loc_1801BDCDC
0x1801bdcf4  jmp     short loc_1801BDCE5
0x1801bdcf6  mov     [rbp+57h+var_70], 0
0x1801bdcfa  mov     r10b, 80h
0x1801bdcfd  cmp     eax, 2
0x1801bdd00  jnz     short loc_1801BDD21
0x1801bdd02  test    [rdx], r10b
0x1801bdd05  jnz     short loc_1801BDD1A
0x1801bdd07  lea     rcx, [rdi+4]
0x1801bdd0b  cmp     eax, r9d
0x1801bdd0e  jnz     short loc_1801BDD33
0x1801bdd10  test    [rdx], r10b
0x1801bdd13  jz      short loc_1801BDD45
0x1801bdd15  mov     eax, r9d
0x1801bdd18  jmp     short loc_1801BDD40
0x1801bdd1a  mov     eax, 2
0x1801bdd1f  jmp     short loc_1801BDD40
0x1801bdd21  mov     rcx, rdx
0x1801bdd24  cmp     eax, r8d
0x1801bdd27  jnz     short loc_1801BDD0B
0x1801bdd29  test    [rdx], r10b
0x1801bdd2c  jz      short loc_1801BDD33
0x1801bdd2e  mov     eax, r8d
0x1801bdd31  jmp     short loc_1801BDD40
0x1801bdd33  cmp     eax, r11d
0x1801bdd36  jnz     short loc_1801BDD45
0x1801bdd38  test    [rcx], r10b
0x1801bdd3b  jz      short loc_1801BDD45
0x1801bdd3d  mov     eax, r11d
0x1801bdd40  mov     r13b, 1
0x1801bdd43  jmp     short loc_1801BDD48
0x1801bdd45  xor     r13b, r13b
0x1801bdd48  cmp     eax, 2
0x1801bdd4b  jnz     loc_1801BDEA7
0x1801bdd51  test    [rdi+4], r8b
0x1801bdd55  jnz     loc_1801BDEB6
0x1801bdd5b  cmp     eax, r9d
0x1801bdd5e  jnz     loc_1801BDEBF
0x1801bdd64  test    [rdi+4], r8b
0x1801bdd68  jnz     loc_1801BDEB6
0x1801bdd6e  mov     [rbp+57h+var_6F], 0
0x1801bdd72  mov     cl, 0Ch
0x1801bdd74  cmp     eax, 2
0x1801bdd77  jnz     loc_1801BDECD
0x1801bdd7d  test    [rdi+4], cl
0x1801bdd80  jnz     loc_1801BDEDB
0x1801bdd86  cmp     eax, r9d
0x1801bdd89  jnz     loc_1801BDEE3
0x1801bdd8f  test    [rdi+4], cl
0x1801bdd92  jnz     loc_1801BDEDB
0x1801bdd98  xor     r14b, r14b
0x1801bdd9b  mov     cl, 30h ; '0'
0x1801bdd9d  cmp     eax, 2
0x1801bdda0  jnz     loc_1801BDEF1
0x1801bdda6  test    [rdi+4], cl
0x1801bdda9  jnz     loc_1801BDEFF
0x1801bddaf  cmp     eax, r9d
0x1801bddb2  jnz     loc_1801BDF06
0x1801bddb8  test    [rdi+4], cl
0x1801bddbb  jnz     loc_1801BDEFF
0x1801bddc1  xor     bl, bl
0x1801bddc3  mov     rcx, r12
0x1801bddc6  call    cs:__imp_ResetInteractionContext
0x1801bddcc  mov     esi, eax
0x1801bddce  test    eax, eax
0x1801bddd0  js      loc_1801BE00F
0x1801bddd6  xor     r8d, r8d
0x1801bddd9  mov     rcx, r12
0x1801bdddc  lea     edx, [r8+1]
0x1801bdde0  call    cs:__imp_SetPropertyInteractionContext
0x1801bdde6  mov     esi, eax
0x1801bdde8  test    eax, eax
0x1801bddea  js      loc_1801BE00F
0x1801bddf0  xor     r8d, r8d
0x1801bddf3  mov     rcx, r12
0x1801bddf6  lea     edx, [r8+3]
0x1801bddfa  call    cs:__imp_SetPropertyInteractionContext
0x1801bde00  mov     esi, eax
0x1801bde02  test    eax, eax
0x1801bde04  js      loc_1801BE00F
0x1801bde0a  xor     r8d, r8d
0x1801bde0d  mov     rcx, r12
0x1801bde10  lea     edx, [r8+2]
0x1801bde14  call    cs:__imp_SetPropertyInteractionContext
0x1801bde1a  mov     esi, eax
0x1801bde1c  test    eax, eax
0x1801bde1e  js      loc_1801BE00F
0x1801bde24  mov     cl, [rdi+10h]
0x1801bde27  mov     r8d, 1
0x1801bde2d  movss   xmm0, dword ptr [rdi+8]
0x1801bde32  not     cl
0x1801bde34  and     ecx, 2
0x1801bde37  xorps   xmm1, xmm1
0x1801bde3a  shl     ecx, 0Ah
0x1801bde3d  or      ecx, r8d
0x1801bde40  ucomiss xmm0, xmm1
0x1801bde43  jp      short loc_1801BDE47
0x1801bde45  jz      short loc_1801BDE4B
0x1801bde47  bts     ecx, 8
0x1801bde4b  movss   xmm0, dword ptr [rdi+0Ch]
0x1801bde50  ucomiss xmm0, xmm1
0x1801bde53  jp      short loc_1801BDE57
0x1801bde55  jz      short loc_1801BDE5B
0x1801bde57  bts     ecx, 9
0x1801bde5b  mov     eax, ecx
0x1801bde5d  or      eax, 2
0x1801bde60  cmp     [rbp+57h+var_6F], 0
0x1801bde64  cmovz   eax, ecx
0x1801bde67  mov     ecx, eax
0x1801bde69  or      ecx, 4
0x1801bde6c  test    r14b, r14b
0x1801bde6f  cmovz   ecx, eax
0x1801bde72  mov     eax, ecx
0x1801bde74  or      eax, 10h
0x1801bde77  test    bl, bl
0x1801bde79  cmovz   eax, ecx
0x1801bde7c  mov     ecx, eax
0x1801bde7e  bts     ecx, 1Ch
0x1801bde82  cmp     dword ptr [rdi], 3
0x1801bde85  cmovnz  ecx, eax
0x1801bde88  mov     ebx, ecx
0x1801bde8a  bts     ebx, 1Eh
0x1801bde8e  test    [rdi+10h], r8b
0x1801bde92  cmovz   ebx, ecx
0x1801bde95  cmp     [rdi+14h], r8d
0x1801bde99  jnz     short loc_1801BDF14
0x1801bde9b  btr     ebx, 9
0x1801bde9f  or      ebx, 80000100h
0x1801bdea5  jmp     short loc_1801BDF24
0x1801bdea7  cmp     eax, r8d
0x1801bdeaa  jnz     loc_1801BDD5B
0x1801bdeb0  test    [rdi+4], r8b
0x1801bdeb4  jz      short loc_1801BDEBF
0x1801bdeb6  mov     [rbp+57h+var_6F], 1
0x1801bdeba  jmp     loc_1801BDD72
0x1801bdebf  cmp     eax, r11d
0x1801bdec2  jnz     loc_1801BDD6E
0x1801bdec8  jmp     loc_1801BDD64
0x1801bdecd  cmp     eax, r8d
0x1801bded0  jnz     loc_1801BDD86
0x1801bded6  test    [rdi+4], cl
0x1801bded9  jz      short loc_1801BDEE3
0x1801bdedb  mov     r14b, 1
0x1801bdede  jmp     loc_1801BDD9B
0x1801bdee3  cmp     eax, r11d
0x1801bdee6  jnz     loc_1801BDD98
0x1801bdeec  jmp     loc_1801BDD8F
0x1801bdef1  cmp     eax, r8d
0x1801bdef4  jnz     loc_1801BDDAF
0x1801bdefa  test    [rdi+4], cl
0x1801bdefd  jz      short loc_1801BDF06
0x1801bdeff  mov     bl, 1
0x1801bdf01  jmp     loc_1801BDDC3
0x1801bdf06  cmp     eax, r11d
0x1801bdf09  jnz     loc_1801BDDC1
0x1801bdf0f  jmp     loc_1801BDDB8
0x1801bdf14  cmp     dword ptr [rdi+14h], 2
0x1801bdf18  jnz     short loc_1801BDF24
0x1801bdf1a  btr     ebx, 8
0x1801bdf1e  or      ebx, 80000200h
0x1801bdf24  mov     al, [rbp+57h+var_70]
0x1801bdf27  mov     edx, 3
0x1801bdf2c  neg     al
0x1801bdf2e  mov     [rbp+57h+var_50], r8d
0x1801bdf32  mov     al, r13b
0x1801bdf35  mov     [rbp+57h+var_4C], ebx
0x1801bdf38  sbb     edi, edi
0x1801bdf3a  mov     [rbp+57h+var_48], 2
0x1801bdf41  and     edi, 5
0x1801bdf44  mov     [rbp+57h+var_40], 4
0x1801bdf4b  neg     al
0x1801bdf4d  mov     [rbp+57h+var_44], edi
0x1801bdf50  lea     r8, [rbp+57h+var_50]
0x1801bdf54  mov     rcx, r12
0x1801bdf57  sbb     r14d, r14d
0x1801bdf5a  and     r14d, 5
0x1801bdf5e  mov     [rbp+57h+var_3C], r14d
0x1801bdf62  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1801bdf68  mov     esi, eax
0x1801bdf6a  mov     eax, cs:dword_1803B9858
0x1801bdf70  cmp     eax, 4
0x1801bdf73  jbe     short loc_1801BDFD4
0x1801bdf75  mov     edx, 2
0x1801bdf7a  lea     rcx, dword_1803B9858
0x1801bdf81  call    _tlgKeywordOn
0x1801bdf86  test    al, al
0x1801bdf88  jz      short loc_1801BDFD4
0x1801bdf8a  lea     rax, [rbp+57h+var_6C]
0x1801bdf8e  mov     [rbp+57h+var_6C], esi
0x1801bdf91  mov     [rsp+0C0h+var_80], rax
0x1801bdf96  lea     rdx, unk_18039697C
0x1801bdf9d  lea     rax, [rbp+57h+var_68]
0x1801bdfa1  mov     [rbp+57h+var_68], r14d
0x1801bdfa5  mov     [rsp+0C0h+var_88], rax
0x1801bdfaa  lea     rax, [rbp+57h+var_64]
0x1801bdfae  mov     [rsp+0C0h+var_90], rax
0x1801bdfb3  lea     rax, [rbp+57h+var_60]
0x1801bdfb7  mov     [rsp+0C0h+var_98], rax
0x1801bdfbc  lea     rax, [rbp+57h+var_58]
0x1801bdfc0  mov     [rsp+0C0h+var_A0], rax
0x1801bdfc5  mov     [rbp+57h+var_64], edi
0x1801bdfc8  mov     [rbp+57h+var_60], ebx
0x1801bdfcb  mov     [rbp+57h+var_58], r15
0x1801bdfcf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801bdfd4  xor     ebx, ebx
0x1801bdfd6  test    esi, esi
0x1801bdfd8  js      short loc_1801BE00F
0x1801bdfda  mov     r8, r15
0x1801bdfdd  lea     rdx, ?s_InteractionContextCallback@CInteractionContextWrapper@@CAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CInteractionContextWrapper::s_InteractionContextCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1801bdfe4  mov     rcx, r12
0x1801bdfe7  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1801bdfed  mov     esi, eax
0x1801bdfef  test    eax, eax
0x1801bdff1  js      short loc_1801BE00F
0x1801bdff3  cmp     [rbp+57h+var_70], bl
0x1801bdff6  jnz     short loc_1801BDFFF
0x1801bdff8  cmp     dword ptr [r15+18h], 2
0x1801bdffd  jz      short loc_1801BE00B
0x1801bdfff  test    r13b, r13b
0x1801be002  jnz     short loc_1801BE00F
0x1801be004  cmp     dword ptr [r15+18h], 4
0x1801be009  jnz     short loc_1801BE00F
0x1801be00b  mov     [r15+18h], rbx
0x1801be00f  mov     eax, esi
0x1801be011  mov     rcx, [rbp+57h+var_38]
0x1801be015  xor     rcx, rsp; StackCookie
0x1801be018  call    __security_check_cookie
0x1801be01d  mov     rbx, [rsp+0C0h+arg_10]
0x1801be025  add     rsp, 90h
0x1801be02c  pop     r15
0x1801be02e  pop     r14
0x1801be030  pop     r13
0x1801be032  pop     r12
0x1801be034  pop     rdi
0x1801be035  pop     rsi
0x1801be036  pop     rbp
0x1801be037  retn
```
