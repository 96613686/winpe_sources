# CConfigGeneralPage::SetActiveDevice(void)

- ea: `0x1800124a4`
- end: `0x180012668`
- name: `?SetActiveDevice@CConfigGeneralPage@@AEAAKXZ`
- size: `452`
- prototype: `unsigned int __fastcall(CConfigGeneralPage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010970`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180006d30`
- `0x1800124a4`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::SetActiveDevice(CConfigGeneralPage *this)
{
  bool v2; // zf
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rsi
  int v6; // eax
  _QWORD *v7; // rcx
  unsigned int v8; // edi
  _QWORD v10[11]; // [rsp+20h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v2 = *((_DWORD *)this + 10) == 0;
  *((_DWORD *)this + 13) = 0;
  if ( v2 )
    return 0;
  v3 = *((_QWORD *)this + 4);
  v4 = 0;
  while ( !*(_DWORD *)(v3 + 72 * v4 + 40) && !*(_DWORD *)(v3 + 72 * v4 + 44) )
  {
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= *((_DWORD *)this + 10) )
    {
      v4 = 0;
      break;
    }
  }
  v5 = 9 * v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  *((_OWORD *)this + 3) = *(_OWORD *)(v3 + 8 * v5);
  *((_OWORD *)this + 4) = *(_OWORD *)(v3 + 8 * v5 + 16);
  *((_OWORD *)this + 5) = *(_OWORD *)(v3 + 8 * v5 + 32);
  *((_OWORD *)this + 6) = *(_OWORD *)(v3 + 8 * v5 + 48);
  *((_QWORD *)this + 14) = *(_QWORD *)(v3 + 8 * v5 + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v10[0] = *(_QWORD *)(v3 + 8 * v5 + 8);
  v10[1] = (char *)this + 56;
  v10[2] = *(_QWORD *)(v3 + 8 * v5 + 56);
  v10[3] = (char *)this + 104;
  v10[4] = *(_QWORD *)(v3 + 8 * v5 + 64);
  v10[5] = (char *)this + 112;
  v6 = MultiStringDup(v10);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_f5b496eade1b3798203481970613ce29_Traceguids,
        (unsigned int)(v6 - 1));
      v7 = WPP_GLOBAL_Control;
    }
    v8 = 8;
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_d(v7[2], 14, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, 8);
  }
  else
  {
    v8 = 0;
  }
  if ( (unsigned int)(*((_DWORD *)this + 25) - 1) > 0x62 )
    *((_DWORD *)this + 25) = 3;
  return v8;
}

```

## disassembly

```asm
0x1800124a4  push    rbx
0x1800124a6  push    rsi
0x1800124a7  push    rdi
0x1800124a8  push    r14
0x1800124aa  push    r15
0x1800124ac  sub     rsp, 50h
0x1800124b0  mov     rbx, rcx
0x1800124b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ba  lea     r15, WPP_GLOBAL_Control
0x1800124c1  mov     r14d, 100h
0x1800124c7  cmp     rcx, r15
0x1800124ca  jz      short loc_1800124ED
0x1800124cc  test    [rcx+1Ch], r14d
0x1800124d0  jz      short loc_1800124ED
0x1800124d2  cmp     byte ptr [rcx+19h], 5
0x1800124d6  jb      short loc_1800124ED
0x1800124d8  mov     rcx, [rcx+10h]
0x1800124dc  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800124e3  mov     edx, 0Dh
0x1800124e8  call    WPP_SF_
0x1800124ed  cmp     dword ptr [rbx+28h], 0
0x1800124f1  mov     dword ptr [rbx+34h], 0
0x1800124f8  jbe     loc_18001265A
0x1800124fe  mov     rdi, [rbx+20h]
0x180012502  xor     ecx, ecx
0x180012504  lea     rdx, [rcx+rcx*8]
0x180012508  cmp     dword ptr [rdi+rdx*8+28h], 0
0x18001250d  jnz     short loc_18001251F
0x18001250f  cmp     dword ptr [rdi+rdx*8+2Ch], 0
0x180012514  jnz     short loc_18001251F
0x180012516  inc     ecx
0x180012518  cmp     ecx, [rbx+28h]
0x18001251b  jb      short loc_180012504
0x18001251d  xor     ecx, ecx
0x18001251f  lea     rsi, [rcx+rcx*8]
0x180012523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001252a  cmp     rcx, r15
0x18001252d  jz      short loc_180012550
0x18001252f  test    [rcx+1Ch], r14d
0x180012533  jz      short loc_180012550
0x180012535  cmp     byte ptr [rcx+19h], 5
0x180012539  jb      short loc_180012550
0x18001253b  mov     rcx, [rcx+10h]
0x18001253f  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012546  mov     edx, 0Fh
0x18001254b  call    WPP_SF_
0x180012550  movups  xmm0, xmmword ptr [rdi+rsi*8]
0x180012554  lea     rcx, [rsp+78h+var_58]
0x180012559  movups  xmmword ptr [rbx+30h], xmm0
0x18001255d  movups  xmm1, xmmword ptr [rdi+rsi*8+10h]
0x180012562  movups  xmmword ptr [rbx+40h], xmm1
0x180012566  movups  xmm0, xmmword ptr [rdi+rsi*8+20h]
0x18001256b  movups  xmmword ptr [rbx+50h], xmm0
0x18001256f  movups  xmm1, xmmword ptr [rdi+rsi*8+30h]
0x180012574  movups  xmmword ptr [rbx+60h], xmm1
0x180012578  movsd   xmm0, qword ptr [rdi+rsi*8+40h]
0x18001257e  movsd   qword ptr [rbx+70h], xmm0
0x180012583  mov     qword ptr [rbx+40h], 0
0x18001258b  mov     qword ptr [rbx+48h], 0
0x180012593  mov     qword ptr [rbx+50h], 0
0x18001259b  mov     rax, [rdi+rsi*8+8]
0x1800125a0  mov     [rsp+78h+var_58], rax
0x1800125a5  lea     rax, [rbx+38h]
0x1800125a9  mov     [rsp+78h+var_50], rax
0x1800125ae  mov     rax, [rdi+rsi*8+38h]
0x1800125b3  mov     [rsp+78h+var_48], rax
0x1800125b8  lea     rax, [rbx+68h]
0x1800125bc  mov     [rsp+78h+var_40], rax
0x1800125c1  mov     rax, [rdi+rsi*8+40h]
0x1800125c6  mov     [rsp+78h+var_38], rax
0x1800125cb  lea     rax, [rbx+70h]
0x1800125cf  mov     [rsp+78h+var_30], rax
0x1800125d4  call    MultiStringDup
0x1800125d9  test    eax, eax
0x1800125db  jz      short loc_180012643
0x1800125dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125e4  cmp     rcx, r15
0x1800125e7  jz      short loc_180012615
0x1800125e9  test    [rcx+1Ch], r14d
0x1800125ed  jz      short loc_180012615
0x1800125ef  cmp     byte ptr [rcx+19h], 2
0x1800125f3  jb      short loc_180012615
0x1800125f5  mov     rcx, [rcx+10h]
0x1800125f9  lea     r9d, [rax-1]
0x1800125fd  mov     edx, 10h
0x180012602  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012609  call    WPP_SF_d
0x18001260e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012615  mov     edi, 8
0x18001261a  cmp     rcx, r15
0x18001261d  jz      short loc_180012645
0x18001261f  test    [rcx+1Ch], r14d
0x180012623  jz      short loc_180012645
0x180012625  cmp     byte ptr [rcx+19h], 2
0x180012629  jb      short loc_180012645
0x18001262b  mov     rcx, [rcx+10h]
0x18001262f  lea     edx, [rdi+6]
0x180012632  mov     r9d, edi
0x180012635  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x18001263c  call    WPP_SF_d
0x180012641  jmp     short loc_180012645
0x180012643  xor     edi, edi
0x180012645  mov     ecx, [rbx+64h]
0x180012648  dec     ecx
0x18001264a  cmp     ecx, 62h ; 'b'
0x18001264d  jbe     short loc_180012656
0x18001264f  mov     dword ptr [rbx+64h], 3
0x180012656  mov     eax, edi
0x180012658  jmp     short loc_18001265C
0x18001265a  xor     eax, eax
0x18001265c  add     rsp, 50h
0x180012660  pop     r15
0x180012662  pop     r14
0x180012664  pop     rdi
0x180012665  pop     rsi
0x180012666  pop     rbx
0x180012667  retn
```
