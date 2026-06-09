# CRTFRead::HandleEndGroup(void)

- ea: `0x180049b60`
- end: `0x180049e3b`
- name: `?HandleEndGroup@CRTFRead@@AEAAHXZ`
- size: `731`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002740`

## callees

- `0x18001e3e0`
- `0x18002c900`
- `0x18002da30`
- `0x180038730`
- `0x18003c554`
- `0x18004223c`
- `0x180049b60`
- `0x180078a64`
- `0x18007c4d0`
- `0x180093c00`

## import_xrefs

- `KERNEL32!GetSystemDefaultLangID` at `0x180049d28`
- `KERNEL32!GetSystemDefaultLangID` at `0x180049d28`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleEndGroup(CRTFRead *this)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  _DWORD *v4; // r14
  __int64 v5; // rax
  __int16 v6; // ax
  LANGID SystemDefaultLangID; // ax
  unsigned int v8; // eax
  int i; // ebp
  __int16 *v10; // rax
  unsigned int v11; // edx
  __int16 *v12; // r14
  UINT v13; // ecx
  WCHAR *v14; // rbx
  unsigned int v15; // edx
  int v17; // [rsp+50h] [rbp-78h] BYREF
  CHAR v18[32]; // [rsp+58h] [rbp-70h] BYREF

  v1 = *((_QWORD *)this + 27);
  if ( v1 )
  {
    v3 = *(_QWORD *)(v1 + 40);
    v4 = (_DWORD *)((char *)this + 300);
    *((_QWORD *)this + 27) = v3;
    if ( !v3 )
    {
      v5 = *(_QWORD *)(v1 + 48);
      *(_OWORD *)((char *)this + 244) = *(_OWORD *)v5;
      *(_OWORD *)((char *)this + 260) = *(_OWORD *)(v5 + 16);
      *(_OWORD *)((char *)this + 276) = *(_OWORD *)(v5 + 32);
      *(_QWORD *)((char *)this + 292) = *(_QWORD *)(v5 + 48);
      *v4 = *(_DWORD *)(v1 + 56);
      *((_WORD *)this + 123) &= ~0x4000u;
      *((_WORD *)this + 131) = -1;
    }
    if ( (unsigned __int16)(*(_WORD *)(v1 + 10) - 12) <= 1u )
    {
      if ( !v3 || *(_QWORD *)(v1 + 48) == *(_QWORD *)(v3 + 48) )
      {
        STATE::DeletePF((STATE *)v1);
        if ( !v3 )
          return *((unsigned int *)this + 12);
      }
      else
      {
        STATE::DeletePF((STATE *)v3);
        *(_QWORD *)(v3 + 48) = *(_QWORD *)(v1 + 48);
        *(_QWORD *)(v1 + 48) = 0;
      }
    }
    else
    {
      STATE::DeletePF((STATE *)v1);
      if ( !v3 )
        return *((unsigned int *)this + 12);
      *v4 = 0;
    }
    *(_QWORD *)((char *)this + 236) = 0;
    if ( *(_WORD *)(v1 + 10) != 2 )
    {
      if ( *(_WORD *)(v1 + 10) == 4 )
      {
        v6 = *((_WORD *)this + 236);
        if ( (v6 & 4) != 0 )
        {
          *((_QWORD *)this + 58) = 0;
          *((_WORD *)this + 236) = v6 & 0xFFF9;
        }
      }
      else if ( *(_WORD *)(v1 + 10) == 12 )
      {
        *(_WORD *)(v3 + 8) = *(_WORD *)(v1 + 8);
        *(_DWORD *)(v3 + 4) ^= (*(_DWORD *)(v1 + 4) ^ *(_DWORD *)(v3 + 4)) & 2;
      }
      goto LABEL_33;
    }
    if ( *(_WORD *)(v3 + 10) != 2 )
    {
      *((_WORD *)this + 236) |= 0x80u;
      CRTFRead::SetPlain(this, (struct STATE *)v1);
      if ( *((_DWORD *)this + 147) != -1 )
        goto LABEL_26;
      SystemDefaultLangID = *((_WORD *)this + 241);
      if ( SystemDefaultLangID == 0xFFFF )
      {
        SystemDefaultLangID = *((_WORD *)this + 240);
        if ( SystemDefaultLangID == 0xFFFF || SystemDefaultLangID == 1033 )
        {
          if ( (*((_DWORD *)this + 20) & 0x8000) == 0 )
            goto LABEL_33;
          SystemDefaultLangID = GetSystemDefaultLangID();
        }
      }
      v8 = CW32System::ConvertLanguageIDtoCodePage(SystemDefaultLangID);
      *((_DWORD *)this + 147) = v8;
      if ( v8 != -1 )
      {
LABEL_26:
        for ( i = 0; i < *((_DWORD *)this + 2); ++i )
        {
          v10 = (__int16 *)CArrayBase::Elem(this, i);
          v12 = v10;
          if ( v10[36] == -1 || v10[36] == 42 )
          {
            if ( *((_BYTE *)v10 + 74) )
            {
              v13 = v10[36];
              v14 = (WCHAR *)(v10 + 3);
              v17 = 0;
              CW32System::WCTMB(v13, v11, (const unsigned __int16 *)v10 + 3, -1, v18, 32, 0, 0, &v17, 0);
              CW32System::MBTWC(*((_DWORD *)this + 147), v15, v18, -1, v14, 33, &v17);
              if ( !v17 )
                *((_BYTE *)v12 + 74) = 0;
            }
          }
        }
      }
    }
LABEL_33:
    CTxtRange::Set_iCF(*((CTxtRange **)this + 8), *(__int16 *)(v3 + 2));
    ReleaseFormats(*(__int16 *)(v3 + 2), -1);
    return *((unsigned int *)this + 12);
  }
  *((_DWORD *)this + 12) = 13;
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x180049b60  push    rbx
0x180049b62  push    rbp
0x180049b63  push    rsi
0x180049b64  push    rdi
0x180049b65  push    r12
0x180049b67  push    r13
0x180049b69  push    r14
0x180049b6b  push    r15
0x180049b6d  sub     rsp, 88h
0x180049b74  mov     rax, cs:__security_cookie
0x180049b7b  xor     rax, rsp
0x180049b7e  mov     [rsp+0C8h+var_50], rax
0x180049b83  mov     rbx, [rcx+0D8h]
0x180049b8a  xor     r15d, r15d
0x180049b8d  mov     rdi, rcx
0x180049b90  test    rbx, rbx
0x180049b93  jnz     short loc_180049BA1
0x180049b95  mov     dword ptr [rcx+30h], 0Dh
0x180049b9c  jmp     loc_180049E16
0x180049ba1  mov     rsi, [rbx+28h]
0x180049ba5  lea     r14, [rcx+12Ch]
0x180049bac  or      r12d, 0FFFFFFFFh
0x180049bb0  mov     [rcx+0D8h], rsi
0x180049bb7  test    rsi, rsi
0x180049bba  jnz     short loc_180049C07
0x180049bbc  mov     rax, [rbx+30h]
0x180049bc0  movups  xmm0, xmmword ptr [rax]
0x180049bc3  movups  xmmword ptr [rcx+0F4h], xmm0
0x180049bca  movups  xmm1, xmmword ptr [rax+10h]
0x180049bce  movups  xmmword ptr [rcx+104h], xmm1
0x180049bd5  movups  xmm0, xmmword ptr [rax+20h]
0x180049bd9  movups  xmmword ptr [rcx+114h], xmm0
0x180049be0  movsd   xmm1, qword ptr [rax+30h]
0x180049be5  movsd   qword ptr [rcx+124h], xmm1
0x180049bed  mov     eax, [rbx+38h]
0x180049bf0  mov     [r14], eax
0x180049bf3  mov     eax, 0BFFFh
0x180049bf8  and     [rcx+0F6h], ax
0x180049bff  mov     [rcx+106h], r12w
0x180049c07  movzx   eax, word ptr [rbx+0Ah]
0x180049c0b  mov     r13d, 1
0x180049c11  sub     ax, 0Ch
0x180049c15  cmp     ax, r13w
0x180049c19  jbe     short loc_180049C31
0x180049c1b  mov     rcx, rbx; this
0x180049c1e  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x180049c23  test    rsi, rsi
0x180049c26  jz      loc_180049E16
0x180049c2c  mov     [r14], r15d
0x180049c2f  jmp     short loc_180049C67
0x180049c31  test    rsi, rsi
0x180049c34  jz      short loc_180049C56
0x180049c36  mov     rax, [rsi+30h]
0x180049c3a  cmp     [rbx+30h], rax
0x180049c3e  jz      short loc_180049C56
0x180049c40  mov     rcx, rsi; this
0x180049c43  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x180049c48  mov     rax, [rbx+30h]
0x180049c4c  mov     [rsi+30h], rax
0x180049c50  mov     [rbx+30h], r15
0x180049c54  jmp     short loc_180049C67
0x180049c56  mov     rcx, rbx; this
0x180049c59  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x180049c5e  test    rsi, rsi
0x180049c61  jz      loc_180049E16
0x180049c67  mov     ecx, 2
0x180049c6c  mov     [rdi+0ECh], r15
0x180049c73  cmp     [rbx+0Ah], cx
0x180049c77  jz      short loc_180049CCD
0x180049c79  cmp     word ptr [rbx+0Ah], 4
0x180049c7e  jz      short loc_180049CA3
0x180049c80  cmp     word ptr [rbx+0Ah], 0Ch
0x180049c85  jnz     loc_180049DFD
0x180049c8b  movzx   eax, word ptr [rbx+8]
0x180049c8f  mov     [rsi+8], ax
0x180049c93  mov     eax, [rsi+4]
0x180049c96  xor     eax, [rbx+4]
0x180049c99  and     eax, ecx
0x180049c9b  xor     [rsi+4], eax
0x180049c9e  jmp     loc_180049DFD
0x180049ca3  movzx   eax, word ptr [rdi+1D8h]
0x180049caa  test    al, 4
0x180049cac  jz      loc_180049DFD
0x180049cb2  mov     ecx, 0FFF9h
0x180049cb7  mov     [rdi+1D0h], r15
0x180049cbe  and     ax, cx
0x180049cc1  mov     [rdi+1D8h], ax
0x180049cc8  jmp     loc_180049DFD
0x180049ccd  cmp     [rsi+0Ah], cx
0x180049cd1  jz      loc_180049DFD
0x180049cd7  mov     eax, 80h
0x180049cdc  mov     rdx, rbx; struct STATE *
0x180049cdf  or      [rdi+1D8h], ax
0x180049ce6  mov     rcx, rdi; this
0x180049ce9  call    ?SetPlain@CRTFRead@@AEAAXPEAUSTATE@@@Z; CRTFRead::SetPlain(STATE *)
0x180049cee  cmp     [rdi+24Ch], r12d
0x180049cf5  jnz     short loc_180049D4B
0x180049cf7  movzx   eax, word ptr [rdi+1E2h]
0x180049cfe  cmp     ax, r12w
0x180049d02  jnz     short loc_180049D34
0x180049d04  movzx   eax, word ptr [rdi+1E0h]
0x180049d0b  cmp     ax, r12w
0x180049d0f  jz      short loc_180049D1B
0x180049d11  mov     ecx, 409h
0x180049d16  cmp     ax, cx
0x180049d19  jnz     short loc_180049D34
0x180049d1b  test    dword ptr [rdi+50h], 8000h
0x180049d22  jz      loc_180049DFD
0x180049d28  call    cs:__imp_GetSystemDefaultLangID
0x180049d2f  nop     dword ptr [rax+rax+00h]
0x180049d34  movzx   ecx, ax; unsigned __int16
0x180049d37  call    ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
0x180049d3c  mov     [rdi+24Ch], eax
0x180049d42  cmp     eax, r12d
0x180049d45  jz      loc_180049DFD
0x180049d4b  mov     ebp, r15d
0x180049d4e  cmp     [rdi+8], r15d
0x180049d52  jle     loc_180049DFD
0x180049d58  mov     edx, ebp; int
0x180049d5a  mov     rcx, rdi; this
0x180049d5d  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x180049d62  mov     r14, rax
0x180049d65  cmp     [rax+48h], r12w
0x180049d6a  jz      short loc_180049D73
0x180049d6c  cmp     word ptr [rax+48h], 2Ah ; '*'
0x180049d71  jnz     short loc_180049DF1
0x180049d73  cmp     [rax+4Ah], r15b
0x180049d77  jz      short loc_180049DF1
0x180049d79  movsx   ecx, word ptr [rax+48h]; CodePage
0x180049d7d  lea     rbx, [rax+6]
0x180049d81  mov     [rsp+0C8h+var_80], r15d; int
0x180049d86  lea     rax, [rsp+0C8h+var_78]
0x180049d8b  mov     [rsp+0C8h+var_88], rax; int *
0x180049d90  mov     r9d, r12d; int
0x180049d93  mov     [rsp+0C8h+var_90], r15; int *
0x180049d98  lea     rax, [rsp+0C8h+var_70]
0x180049d9d  mov     qword ptr [rsp+0C8h+UsedDefaultChar], r15; UsedDefaultChar
0x180049da2  mov     r8, rbx; unsigned __int16 *
0x180049da5  mov     [rsp+0C8h+var_A0], 20h ; ' '; int
0x180049dad  mov     [rsp+0C8h+var_A8], rax; LPSTR
0x180049db2  mov     [rsp+0C8h+var_78], r15d
0x180049db7  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x180049dbc  mov     ecx, [rdi+24Ch]; int
0x180049dc2  lea     rax, [rsp+0C8h+var_78]
0x180049dc7  mov     qword ptr [rsp+0C8h+UsedDefaultChar], rax; int *
0x180049dcc  lea     r8, [rsp+0C8h+var_70]; char *
0x180049dd1  mov     [rsp+0C8h+var_A0], 21h ; '!'; int
0x180049dd9  mov     r9d, r12d; int
0x180049ddc  mov     [rsp+0C8h+var_A8], rbx; LPWSTR
0x180049de1  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x180049de6  cmp     [rsp+0C8h+var_78], r15d
0x180049deb  jnz     short loc_180049DF1
0x180049ded  mov     [r14+4Ah], r15b
0x180049df1  add     ebp, r13d
0x180049df4  cmp     ebp, [rdi+8]
0x180049df7  jl      loc_180049D58
0x180049dfd  movsx   edx, word ptr [rsi+2]; int
0x180049e01  mov     rcx, [rdi+40h]; this
0x180049e05  call    ?Set_iCF@CTxtRange@@QEAAHJ@Z; CTxtRange::Set_iCF(long)
0x180049e0a  movsx   ecx, word ptr [rsi+2]; int
0x180049e0e  mov     edx, r12d; int
0x180049e11  call    ?ReleaseFormats@@YAXJJ@Z; ReleaseFormats(long,long)
0x180049e16  mov     eax, [rdi+30h]
0x180049e19  mov     rcx, [rsp+0C8h+var_50]
0x180049e1e  xor     rcx, rsp; StackCookie
0x180049e21  call    __security_check_cookie
0x180049e26  add     rsp, 88h
0x180049e2d  pop     r15
0x180049e2f  pop     r14
0x180049e31  pop     r13
0x180049e33  pop     r12
0x180049e35  pop     rdi
0x180049e36  pop     rsi
0x180049e37  pop     rbp
0x180049e38  pop     rbx
0x180049e39  retn
```
