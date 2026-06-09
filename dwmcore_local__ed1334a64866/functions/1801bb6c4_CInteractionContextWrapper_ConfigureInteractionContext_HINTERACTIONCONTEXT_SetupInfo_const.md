# CInteractionContextWrapper::ConfigureInteractionContext(HINTERACTIONCONTEXT__ *,SetupInfo const &)

- ea: `0x1801bb6c4`
- end: `0x1801bba78`
- name: `?ConfigureInteractionContext@CInteractionContextWrapper@@AEAAJPEAUHINTERACTIONCONTEXT__@@AEBUSetupInfo@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(CInteractionContextWrapper *__hidden this, struct HINTERACTIONCONTEXT__ *, const struct SetupInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1801bb610`
- `0x1801bb64c`

## callees

- `0x1801b70a8`
- `0x1801bb6c4`
- `0x1801f2ce0`
- `0x180228490`

## import_xrefs

- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801bba27`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801bba27`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801bb9a2`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801bb9a2`
- `NInput!SetPropertyInteractionContext` at `0x1801bb820`
- `NInput!SetPropertyInteractionContext` at `0x1801bb83a`
- `NInput!SetPropertyInteractionContext` at `0x1801bb854`
- `NInput!SetPropertyInteractionContext` at `0x1801bb820`
- `NInput!SetPropertyInteractionContext` at `0x1801bb83a`
- `NInput!SetPropertyInteractionContext` at `0x1801bb854`
- `NInput!ResetInteractionContext` at `0x1801bb806`
- `NInput!ResetInteractionContext` at `0x1801bb806`

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
              (unsigned int)&dword_1803969FC,
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
0x1801bb6c4  mov     [rsp-8+arg_10], rbx
0x1801bb6c9  push    rbp
0x1801bb6ca  push    rsi
0x1801bb6cb  push    rdi
0x1801bb6cc  push    r12
0x1801bb6ce  push    r13
0x1801bb6d0  push    r14
0x1801bb6d2  push    r15
0x1801bb6d4  lea     rbp, [rsp-27h]
0x1801bb6d9  sub     rsp, 90h
0x1801bb6e0  mov     rax, cs:__security_cookie
0x1801bb6e7  xor     rax, rsp
0x1801bb6ea  mov     [rbp+57h+var_38], rax
0x1801bb6ee  mov     eax, [r8]
0x1801bb6f1  mov     r11d, 6
0x1801bb6f7  mov     r12, rdx
0x1801bb6fa  mov     rdi, r8
0x1801bb6fd  lea     rdx, [r8+4]
0x1801bb701  mov     r15, rcx
0x1801bb704  mov     cl, 40h ; '@'
0x1801bb706  lea     r8d, [r11-3]
0x1801bb70a  lea     r9d, [r11-2]
0x1801bb70e  cmp     eax, 2
0x1801bb711  jnz     short loc_1801BB72B
0x1801bb713  test    [rdx], cl
0x1801bb715  jnz     short loc_1801BB725
0x1801bb717  cmp     eax, r9d
0x1801bb71a  jz      short loc_1801BB721
0x1801bb71c  cmp     eax, r11d
0x1801bb71f  jnz     short loc_1801BB736
0x1801bb721  test    [rdx], cl
0x1801bb723  jz      short loc_1801BB736
0x1801bb725  mov     [rbp+57h+var_70], 1
0x1801bb729  jmp     short loc_1801BB73A
0x1801bb72b  cmp     eax, r8d
0x1801bb72e  jnz     short loc_1801BB717
0x1801bb730  test    [rdx], cl
0x1801bb732  jz      short loc_1801BB71C
0x1801bb734  jmp     short loc_1801BB725
0x1801bb736  mov     [rbp+57h+var_70], 0
0x1801bb73a  mov     r10b, 80h
0x1801bb73d  cmp     eax, 2
0x1801bb740  jnz     short loc_1801BB761
0x1801bb742  test    [rdx], r10b
0x1801bb745  jnz     short loc_1801BB75A
0x1801bb747  lea     rcx, [rdi+4]
0x1801bb74b  cmp     eax, r9d
0x1801bb74e  jnz     short loc_1801BB773
0x1801bb750  test    [rdx], r10b
0x1801bb753  jz      short loc_1801BB785
0x1801bb755  mov     eax, r9d
0x1801bb758  jmp     short loc_1801BB780
0x1801bb75a  mov     eax, 2
0x1801bb75f  jmp     short loc_1801BB780
0x1801bb761  mov     rcx, rdx
0x1801bb764  cmp     eax, r8d
0x1801bb767  jnz     short loc_1801BB74B
0x1801bb769  test    [rdx], r10b
0x1801bb76c  jz      short loc_1801BB773
0x1801bb76e  mov     eax, r8d
0x1801bb771  jmp     short loc_1801BB780
0x1801bb773  cmp     eax, r11d
0x1801bb776  jnz     short loc_1801BB785
0x1801bb778  test    [rcx], r10b
0x1801bb77b  jz      short loc_1801BB785
0x1801bb77d  mov     eax, r11d
0x1801bb780  mov     r13b, 1
0x1801bb783  jmp     short loc_1801BB788
0x1801bb785  xor     r13b, r13b
0x1801bb788  cmp     eax, 2
0x1801bb78b  jnz     loc_1801BB8E7
0x1801bb791  test    [rdi+4], r8b
0x1801bb795  jnz     loc_1801BB8F6
0x1801bb79b  cmp     eax, r9d
0x1801bb79e  jnz     loc_1801BB8FF
0x1801bb7a4  test    [rdi+4], r8b
0x1801bb7a8  jnz     loc_1801BB8F6
0x1801bb7ae  mov     [rbp+57h+var_6F], 0
0x1801bb7b2  mov     cl, 0Ch
0x1801bb7b4  cmp     eax, 2
0x1801bb7b7  jnz     loc_1801BB90D
0x1801bb7bd  test    [rdi+4], cl
0x1801bb7c0  jnz     loc_1801BB91B
0x1801bb7c6  cmp     eax, r9d
0x1801bb7c9  jnz     loc_1801BB923
0x1801bb7cf  test    [rdi+4], cl
0x1801bb7d2  jnz     loc_1801BB91B
0x1801bb7d8  xor     r14b, r14b
0x1801bb7db  mov     cl, 30h ; '0'
0x1801bb7dd  cmp     eax, 2
0x1801bb7e0  jnz     loc_1801BB931
0x1801bb7e6  test    [rdi+4], cl
0x1801bb7e9  jnz     loc_1801BB93F
0x1801bb7ef  cmp     eax, r9d
0x1801bb7f2  jnz     loc_1801BB946
0x1801bb7f8  test    [rdi+4], cl
0x1801bb7fb  jnz     loc_1801BB93F
0x1801bb801  xor     bl, bl
0x1801bb803  mov     rcx, r12
0x1801bb806  call    cs:__imp_ResetInteractionContext
0x1801bb80c  mov     esi, eax
0x1801bb80e  test    eax, eax
0x1801bb810  js      loc_1801BBA4F
0x1801bb816  xor     r8d, r8d
0x1801bb819  mov     rcx, r12
0x1801bb81c  lea     edx, [r8+1]
0x1801bb820  call    cs:__imp_SetPropertyInteractionContext
0x1801bb826  mov     esi, eax
0x1801bb828  test    eax, eax
0x1801bb82a  js      loc_1801BBA4F
0x1801bb830  xor     r8d, r8d
0x1801bb833  mov     rcx, r12
0x1801bb836  lea     edx, [r8+3]
0x1801bb83a  call    cs:__imp_SetPropertyInteractionContext
0x1801bb840  mov     esi, eax
0x1801bb842  test    eax, eax
0x1801bb844  js      loc_1801BBA4F
0x1801bb84a  xor     r8d, r8d
0x1801bb84d  mov     rcx, r12
0x1801bb850  lea     edx, [r8+2]
0x1801bb854  call    cs:__imp_SetPropertyInteractionContext
0x1801bb85a  mov     esi, eax
0x1801bb85c  test    eax, eax
0x1801bb85e  js      loc_1801BBA4F
0x1801bb864  mov     cl, [rdi+10h]
0x1801bb867  mov     r8d, 1
0x1801bb86d  movss   xmm0, dword ptr [rdi+8]
0x1801bb872  not     cl
0x1801bb874  and     ecx, 2
0x1801bb877  xorps   xmm1, xmm1
0x1801bb87a  shl     ecx, 0Ah
0x1801bb87d  or      ecx, r8d
0x1801bb880  ucomiss xmm0, xmm1
0x1801bb883  jp      short loc_1801BB887
0x1801bb885  jz      short loc_1801BB88B
0x1801bb887  bts     ecx, 8
0x1801bb88b  movss   xmm0, dword ptr [rdi+0Ch]
0x1801bb890  ucomiss xmm0, xmm1
0x1801bb893  jp      short loc_1801BB897
0x1801bb895  jz      short loc_1801BB89B
0x1801bb897  bts     ecx, 9
0x1801bb89b  mov     eax, ecx
0x1801bb89d  or      eax, 2
0x1801bb8a0  cmp     [rbp+57h+var_6F], 0
0x1801bb8a4  cmovz   eax, ecx
0x1801bb8a7  mov     ecx, eax
0x1801bb8a9  or      ecx, 4
0x1801bb8ac  test    r14b, r14b
0x1801bb8af  cmovz   ecx, eax
0x1801bb8b2  mov     eax, ecx
0x1801bb8b4  or      eax, 10h
0x1801bb8b7  test    bl, bl
0x1801bb8b9  cmovz   eax, ecx
0x1801bb8bc  mov     ecx, eax
0x1801bb8be  bts     ecx, 1Ch
0x1801bb8c2  cmp     dword ptr [rdi], 3
0x1801bb8c5  cmovnz  ecx, eax
0x1801bb8c8  mov     ebx, ecx
0x1801bb8ca  bts     ebx, 1Eh
0x1801bb8ce  test    [rdi+10h], r8b
0x1801bb8d2  cmovz   ebx, ecx
0x1801bb8d5  cmp     [rdi+14h], r8d
0x1801bb8d9  jnz     short loc_1801BB954
0x1801bb8db  btr     ebx, 9
0x1801bb8df  or      ebx, 80000100h
0x1801bb8e5  jmp     short loc_1801BB964
0x1801bb8e7  cmp     eax, r8d
0x1801bb8ea  jnz     loc_1801BB79B
0x1801bb8f0  test    [rdi+4], r8b
0x1801bb8f4  jz      short loc_1801BB8FF
0x1801bb8f6  mov     [rbp+57h+var_6F], 1
0x1801bb8fa  jmp     loc_1801BB7B2
0x1801bb8ff  cmp     eax, r11d
0x1801bb902  jnz     loc_1801BB7AE
0x1801bb908  jmp     loc_1801BB7A4
0x1801bb90d  cmp     eax, r8d
0x1801bb910  jnz     loc_1801BB7C6
0x1801bb916  test    [rdi+4], cl
0x1801bb919  jz      short loc_1801BB923
0x1801bb91b  mov     r14b, 1
0x1801bb91e  jmp     loc_1801BB7DB
0x1801bb923  cmp     eax, r11d
0x1801bb926  jnz     loc_1801BB7D8
0x1801bb92c  jmp     loc_1801BB7CF
0x1801bb931  cmp     eax, r8d
0x1801bb934  jnz     loc_1801BB7EF
0x1801bb93a  test    [rdi+4], cl
0x1801bb93d  jz      short loc_1801BB946
0x1801bb93f  mov     bl, 1
0x1801bb941  jmp     loc_1801BB803
0x1801bb946  cmp     eax, r11d
0x1801bb949  jnz     loc_1801BB801
0x1801bb94f  jmp     loc_1801BB7F8
0x1801bb954  cmp     dword ptr [rdi+14h], 2
0x1801bb958  jnz     short loc_1801BB964
0x1801bb95a  btr     ebx, 8
0x1801bb95e  or      ebx, 80000200h
0x1801bb964  mov     al, [rbp+57h+var_70]
0x1801bb967  mov     edx, 3
0x1801bb96c  neg     al
0x1801bb96e  mov     [rbp+57h+var_50], r8d
0x1801bb972  mov     al, r13b
0x1801bb975  mov     [rbp+57h+var_4C], ebx
0x1801bb978  sbb     edi, edi
0x1801bb97a  mov     [rbp+57h+var_48], 2
0x1801bb981  and     edi, 5
0x1801bb984  mov     [rbp+57h+var_40], 4
0x1801bb98b  neg     al
0x1801bb98d  mov     [rbp+57h+var_44], edi
0x1801bb990  lea     r8, [rbp+57h+var_50]
0x1801bb994  mov     rcx, r12
0x1801bb997  sbb     r14d, r14d
0x1801bb99a  and     r14d, 5
0x1801bb99e  mov     [rbp+57h+var_3C], r14d
0x1801bb9a2  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1801bb9a8  mov     esi, eax
0x1801bb9aa  mov     eax, cs:dword_1803B9858
0x1801bb9b0  cmp     eax, 4
0x1801bb9b3  jbe     short loc_1801BBA14
0x1801bb9b5  mov     edx, 2
0x1801bb9ba  lea     rcx, dword_1803B9858
0x1801bb9c1  call    _tlgKeywordOn
0x1801bb9c6  test    al, al
0x1801bb9c8  jz      short loc_1801BBA14
0x1801bb9ca  lea     rax, [rbp+57h+var_6C]
0x1801bb9ce  mov     [rbp+57h+var_6C], esi
0x1801bb9d1  mov     [rsp+0C0h+var_80], rax
0x1801bb9d6  lea     rdx, dword_1803969FC
0x1801bb9dd  lea     rax, [rbp+57h+var_68]
0x1801bb9e1  mov     [rbp+57h+var_68], r14d
0x1801bb9e5  mov     [rsp+0C0h+var_88], rax
0x1801bb9ea  lea     rax, [rbp+57h+var_64]
0x1801bb9ee  mov     [rsp+0C0h+var_90], rax
0x1801bb9f3  lea     rax, [rbp+57h+var_60]
0x1801bb9f7  mov     [rsp+0C0h+var_98], rax
0x1801bb9fc  lea     rax, [rbp+57h+var_58]
0x1801bba00  mov     [rsp+0C0h+var_A0], rax
0x1801bba05  mov     [rbp+57h+var_64], edi
0x1801bba08  mov     [rbp+57h+var_60], ebx
0x1801bba0b  mov     [rbp+57h+var_58], r15
0x1801bba0f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801bba14  xor     ebx, ebx
0x1801bba16  test    esi, esi
0x1801bba18  js      short loc_1801BBA4F
0x1801bba1a  mov     r8, r15
0x1801bba1d  lea     rdx, ?s_InteractionContextCallback@CInteractionContextWrapper@@CAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CInteractionContextWrapper::s_InteractionContextCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1801bba24  mov     rcx, r12
0x1801bba27  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1801bba2d  mov     esi, eax
0x1801bba2f  test    eax, eax
0x1801bba31  js      short loc_1801BBA4F
0x1801bba33  cmp     [rbp+57h+var_70], bl
0x1801bba36  jnz     short loc_1801BBA3F
0x1801bba38  cmp     dword ptr [r15+18h], 2
0x1801bba3d  jz      short loc_1801BBA4B
0x1801bba3f  test    r13b, r13b
0x1801bba42  jnz     short loc_1801BBA4F
0x1801bba44  cmp     dword ptr [r15+18h], 4
0x1801bba49  jnz     short loc_1801BBA4F
0x1801bba4b  mov     [r15+18h], rbx
0x1801bba4f  mov     eax, esi
0x1801bba51  mov     rcx, [rbp+57h+var_38]
0x1801bba55  xor     rcx, rsp; StackCookie
0x1801bba58  call    __security_check_cookie
0x1801bba5d  mov     rbx, [rsp+0C0h+arg_10]
0x1801bba65  add     rsp, 90h
0x1801bba6c  pop     r15
0x1801bba6e  pop     r14
0x1801bba70  pop     r13
0x1801bba72  pop     r12
0x1801bba74  pop     rdi
0x1801bba75  pop     rsi
0x1801bba76  pop     rbp
0x1801bba77  retn
```
