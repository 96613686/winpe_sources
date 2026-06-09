# CRTFRead::HandleEndGroup(void)

- ea: `0x1800480e0`
- end: `0x1800483b4`
- name: `?HandleEndGroup@CRTFRead@@AEAAHXZ`
- size: `724`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800026c0`

## callees

- `0x180027f70`
- `0x18002a424`
- `0x180031cbc`
- `0x180032db0`
- `0x180037760`
- `0x18003b9a4`
- `0x1800480e0`
- `0x180076900`
- `0x18007a09c`
- `0x180091140`

## import_xrefs

- `KERNEL32!GetSystemDefaultLangID` at `0x1800482a8`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800482a8`

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
  int v11; // edx
  __int16 *v12; // r14
  signed int v13; // ecx
  WCHAR *v14; // rbx
  __int64 v15; // rdx
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
0x1800480e0  push    rbx
0x1800480e2  push    rbp
0x1800480e3  push    rsi
0x1800480e4  push    rdi
0x1800480e5  push    r12
0x1800480e7  push    r13
0x1800480e9  push    r14
0x1800480eb  push    r15
0x1800480ed  sub     rsp, 88h
0x1800480f4  mov     rax, cs:__security_cookie
0x1800480fb  xor     rax, rsp
0x1800480fe  mov     [rsp+0C8h+var_50], rax
0x180048103  mov     rbx, [rcx+0D8h]
0x18004810a  xor     r15d, r15d
0x18004810d  mov     rdi, rcx
0x180048110  test    rbx, rbx
0x180048113  jnz     short loc_180048121
0x180048115  mov     dword ptr [rcx+30h], 0Dh
0x18004811c  jmp     loc_180048390
0x180048121  mov     rsi, [rbx+28h]
0x180048125  lea     r14, [rcx+12Ch]
0x18004812c  or      r12d, 0FFFFFFFFh
0x180048130  mov     [rcx+0D8h], rsi
0x180048137  test    rsi, rsi
0x18004813a  jnz     short loc_180048187
0x18004813c  mov     rax, [rbx+30h]
0x180048140  movups  xmm0, xmmword ptr [rax]
0x180048143  movups  xmmword ptr [rcx+0F4h], xmm0
0x18004814a  movups  xmm1, xmmword ptr [rax+10h]
0x18004814e  movups  xmmword ptr [rcx+104h], xmm1
0x180048155  movups  xmm0, xmmword ptr [rax+20h]
0x180048159  movups  xmmword ptr [rcx+114h], xmm0
0x180048160  movsd   xmm1, qword ptr [rax+30h]
0x180048165  movsd   qword ptr [rcx+124h], xmm1
0x18004816d  mov     eax, [rbx+38h]
0x180048170  mov     [r14], eax
0x180048173  mov     eax, 0BFFFh
0x180048178  and     [rcx+0F6h], ax
0x18004817f  mov     [rcx+106h], r12w
0x180048187  movzx   eax, word ptr [rbx+0Ah]
0x18004818b  mov     r13d, 1
0x180048191  sub     ax, 0Ch
0x180048195  cmp     ax, r13w
0x180048199  jbe     short loc_1800481B1
0x18004819b  mov     rcx, rbx; this
0x18004819e  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x1800481a3  test    rsi, rsi
0x1800481a6  jz      loc_180048390
0x1800481ac  mov     [r14], r15d
0x1800481af  jmp     short loc_1800481E7
0x1800481b1  test    rsi, rsi
0x1800481b4  jz      short loc_1800481D6
0x1800481b6  mov     rax, [rsi+30h]
0x1800481ba  cmp     [rbx+30h], rax
0x1800481be  jz      short loc_1800481D6
0x1800481c0  mov     rcx, rsi; this
0x1800481c3  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x1800481c8  mov     rax, [rbx+30h]
0x1800481cc  mov     [rsi+30h], rax
0x1800481d0  mov     [rbx+30h], r15
0x1800481d4  jmp     short loc_1800481E7
0x1800481d6  mov     rcx, rbx; this
0x1800481d9  call    ?DeletePF@STATE@@QEAAXXZ; STATE::DeletePF(void)
0x1800481de  test    rsi, rsi
0x1800481e1  jz      loc_180048390
0x1800481e7  mov     ecx, 2
0x1800481ec  mov     [rdi+0ECh], r15
0x1800481f3  cmp     [rbx+0Ah], cx
0x1800481f7  jz      short loc_18004824D
0x1800481f9  cmp     word ptr [rbx+0Ah], 4
0x1800481fe  jz      short loc_180048223
0x180048200  cmp     word ptr [rbx+0Ah], 0Ch
0x180048205  jnz     loc_180048377
0x18004820b  movzx   eax, word ptr [rbx+8]
0x18004820f  mov     [rsi+8], ax
0x180048213  mov     eax, [rsi+4]
0x180048216  xor     eax, [rbx+4]
0x180048219  and     eax, ecx
0x18004821b  xor     [rsi+4], eax
0x18004821e  jmp     loc_180048377
0x180048223  movzx   eax, word ptr [rdi+1D8h]
0x18004822a  test    al, 4
0x18004822c  jz      loc_180048377
0x180048232  mov     ecx, 0FFF9h
0x180048237  mov     [rdi+1D0h], r15
0x18004823e  and     ax, cx
0x180048241  mov     [rdi+1D8h], ax
0x180048248  jmp     loc_180048377
0x18004824d  cmp     [rsi+0Ah], cx
0x180048251  jz      loc_180048377
0x180048257  mov     eax, 80h
0x18004825c  mov     rdx, rbx; struct STATE *
0x18004825f  or      [rdi+1D8h], ax
0x180048266  mov     rcx, rdi; this
0x180048269  call    ?SetPlain@CRTFRead@@AEAAXPEAUSTATE@@@Z; CRTFRead::SetPlain(STATE *)
0x18004826e  cmp     [rdi+24Ch], r12d
0x180048275  jnz     short loc_1800482C5
0x180048277  movzx   eax, word ptr [rdi+1E2h]
0x18004827e  cmp     ax, r12w
0x180048282  jnz     short loc_1800482AE
0x180048284  movzx   eax, word ptr [rdi+1E0h]
0x18004828b  cmp     ax, r12w
0x18004828f  jz      short loc_18004829B
0x180048291  mov     ecx, 409h
0x180048296  cmp     ax, cx
0x180048299  jnz     short loc_1800482AE
0x18004829b  test    dword ptr [rdi+50h], 8000h
0x1800482a2  jz      loc_180048377
0x1800482a8  call    cs:__imp_GetSystemDefaultLangID
0x1800482ae  movzx   ecx, ax; unsigned __int16
0x1800482b1  call    ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
0x1800482b6  mov     [rdi+24Ch], eax
0x1800482bc  cmp     eax, r12d
0x1800482bf  jz      loc_180048377
0x1800482c5  mov     ebp, r15d
0x1800482c8  cmp     [rdi+8], r15d
0x1800482cc  jle     loc_180048377
0x1800482d2  mov     edx, ebp; int
0x1800482d4  mov     rcx, rdi; this
0x1800482d7  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x1800482dc  mov     r14, rax
0x1800482df  cmp     [rax+48h], r12w
0x1800482e4  jz      short loc_1800482ED
0x1800482e6  cmp     word ptr [rax+48h], 2Ah ; '*'
0x1800482eb  jnz     short loc_18004836B
0x1800482ed  cmp     [rax+4Ah], r15b
0x1800482f1  jz      short loc_18004836B
0x1800482f3  movsx   ecx, word ptr [rax+48h]; CodePage
0x1800482f7  lea     rbx, [rax+6]
0x1800482fb  mov     [rsp+0C8h+var_80], r15d; int
0x180048300  lea     rax, [rsp+0C8h+var_78]
0x180048305  mov     [rsp+0C8h+var_88], rax; int *
0x18004830a  mov     r9d, r12d; int
0x18004830d  mov     [rsp+0C8h+var_90], r15; int *
0x180048312  lea     rax, [rsp+0C8h+var_70]
0x180048317  mov     qword ptr [rsp+0C8h+UsedDefaultChar], r15; UsedDefaultChar
0x18004831c  mov     r8, rbx; unsigned __int16 *
0x18004831f  mov     [rsp+0C8h+var_A0], 20h ; ' '; int
0x180048327  mov     [rsp+0C8h+var_A8], rax; LPSTR
0x18004832c  mov     [rsp+0C8h+var_78], r15d
0x180048331  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x180048336  mov     ecx, [rdi+24Ch]; int
0x18004833c  lea     rax, [rsp+0C8h+var_78]
0x180048341  mov     qword ptr [rsp+0C8h+UsedDefaultChar], rax; int *
0x180048346  lea     r8, [rsp+0C8h+var_70]; char *
0x18004834b  mov     [rsp+0C8h+var_A0], 21h ; '!'; int
0x180048353  mov     r9d, r12d; int
0x180048356  mov     [rsp+0C8h+var_A8], rbx; LPWSTR
0x18004835b  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x180048360  cmp     [rsp+0C8h+var_78], r15d
0x180048365  jnz     short loc_18004836B
0x180048367  mov     [r14+4Ah], r15b
0x18004836b  add     ebp, r13d
0x18004836e  cmp     ebp, [rdi+8]
0x180048371  jl      loc_1800482D2
0x180048377  movsx   edx, word ptr [rsi+2]; int
0x18004837b  mov     rcx, [rdi+40h]; this
0x18004837f  call    ?Set_iCF@CTxtRange@@QEAAHJ@Z; CTxtRange::Set_iCF(long)
0x180048384  movsx   ecx, word ptr [rsi+2]; int
0x180048388  mov     edx, r12d; int
0x18004838b  call    ?ReleaseFormats@@YAXJJ@Z; ReleaseFormats(long,long)
0x180048390  mov     eax, [rdi+30h]
0x180048393  mov     rcx, [rsp+0C8h+var_50]
0x180048398  xor     rcx, rsp; StackCookie
0x18004839b  call    __security_check_cookie
0x1800483a0  add     rsp, 88h
0x1800483a7  pop     r15
0x1800483a9  pop     r14
0x1800483ab  pop     r13
0x1800483ad  pop     r12
0x1800483af  pop     rdi
0x1800483b0  pop     rsi
0x1800483b1  pop     rbp
0x1800483b2  pop     rbx
0x1800483b3  retn
```
