# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18000454c`
- end: `0x1800046d4`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800033d8`
- `0x1800038f4`
- `0x1800040fc`

## callees

- `0x18000454c`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)&FH4::s_negLengthTab + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x18000454c  xor     eax, eax
0x18000454e  lea     r11, cs:180000000h
0x180004555  mov     [rcx+18h], al
0x180004558  xorps   xmm0, xmm0
0x18000455b  mov     [rcx+1Ch], rax
0x18000455f  mov     r8, rcx
0x180004562  mov     [rcx+24h], rax
0x180004566  movups  xmmword ptr [rcx+30h], xmm0
0x18000456a  mov     rax, [rcx+8]
0x18000456e  mov     r10b, [rax]
0x180004571  lea     rdx, [rax+1]
0x180004575  mov     [rcx+18h], r10b
0x180004579  mov     [rcx+8], rdx
0x18000457d  test    r10b, 1
0x180004581  jz      short loc_1800045AA
0x180004583  movzx   ecx, byte ptr [rdx]
0x180004586  and     ecx, 0Fh
0x180004589  movsx   rax, byte ptr [rcx+r11+10238h]
0x180004592  mov     cl, [rcx+r11+10248h]
0x18000459a  sub     rdx, rax
0x18000459d  mov     eax, [rdx-4]
0x1800045a0  shr     eax, cl
0x1800045a2  mov     [r8+1Ch], eax
0x1800045a6  mov     [r8+8], rdx
0x1800045aa  test    r10b, 2
0x1800045ae  jz      short loc_1800045BE
0x1800045b0  mov     eax, [rdx]
0x1800045b2  add     rdx, 4
0x1800045b6  mov     [r8+8], rdx
0x1800045ba  mov     [r8+20h], eax
0x1800045be  test    r10b, 4
0x1800045c2  jz      short loc_1800045EB
0x1800045c4  movzx   ecx, byte ptr [rdx]
0x1800045c7  and     ecx, 0Fh
0x1800045ca  movsx   rax, byte ptr [rcx+r11+10238h]
0x1800045d3  mov     cl, [rcx+r11+10248h]
0x1800045db  sub     rdx, rax
0x1800045de  mov     eax, [rdx-4]
0x1800045e1  shr     eax, cl
0x1800045e3  mov     [r8+24h], eax
0x1800045e7  mov     [r8+8], rdx
0x1800045eb  mov     eax, [rdx]
0x1800045ed  lea     r9, [rdx+4]
0x1800045f1  mov     [r8+28h], eax
0x1800045f5  mov     al, r10b
0x1800045f8  and     al, 30h
0x1800045fa  mov     [r8+8], r9
0x1800045fe  test    r10b, 8
0x180004602  jz      short loc_18000463F
0x180004604  cmp     al, 10h
0x180004606  jnz     short loc_180004618
0x180004608  movsxd  rcx, dword ptr [r9]
0x18000460b  lea     rax, [r9+4]
0x18000460f  mov     [r8+8], rax
0x180004613  mov     [r8+30h], rcx
0x180004617  retn
0x180004618  cmp     al, 20h ; ' '
0x18000461a  jnz     locret_1800046D3
0x180004620  movsxd  rax, dword ptr [r9]
0x180004623  lea     rdx, [r9+4]
0x180004627  mov     [r8+8], rdx
0x18000462b  mov     [r8+30h], rax
0x18000462f  lea     rax, [rdx+4]
0x180004633  movsxd  rcx, dword ptr [rdx]
0x180004636  mov     [r8+8], rax
0x18000463a  jmp     loc_1800046CF
0x18000463f  cmp     al, 10h
0x180004641  jnz     short loc_180004673
0x180004643  movzx   ecx, byte ptr [r9]
0x180004647  and     ecx, 0Fh
0x18000464a  movsx   rax, byte ptr [rcx+r11+10238h]
0x180004653  mov     cl, [rcx+r11+10248h]
0x18000465b  sub     r9, rax
0x18000465e  mov     eax, [r8+48h]
0x180004662  mov     edx, [r9-4]
0x180004666  shr     edx, cl
0x180004668  add     eax, edx
0x18000466a  mov     [r8+8], r9
0x18000466e  mov     [r8+30h], rax
0x180004672  retn
0x180004673  cmp     al, 20h ; ' '
0x180004675  jnz     short locret_1800046D3
0x180004677  movzx   ecx, byte ptr [r9]
0x18000467b  mov     edx, [r8+48h]
0x18000467f  and     ecx, 0Fh
0x180004682  movsx   rax, byte ptr [rcx+r11+10238h]
0x18000468b  mov     cl, [rcx+r11+10248h]
0x180004693  sub     r9, rax
0x180004696  mov     eax, [r9-4]
0x18000469a  shr     eax, cl
0x18000469c  mov     [r8+8], r9
0x1800046a0  lea     ecx, [rdx+rax]
0x1800046a3  mov     [r8+30h], rcx
0x1800046a7  movzx   ecx, byte ptr [r9]
0x1800046ab  and     ecx, 0Fh
0x1800046ae  movsx   rax, byte ptr [rcx+r11+10238h]
0x1800046b7  mov     cl, [rcx+r11+10248h]
0x1800046bf  sub     r9, rax
0x1800046c2  mov     eax, [r9-4]
0x1800046c6  shr     eax, cl
0x1800046c8  mov     [r8+8], r9
0x1800046cc  lea     ecx, [rdx+rax]
0x1800046cf  mov     [r8+38h], rcx
0x1800046d3  retn
```
