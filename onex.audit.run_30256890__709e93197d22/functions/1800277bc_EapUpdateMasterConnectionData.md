# EapUpdateMasterConnectionData

- ea: `0x1800277bc`
- end: `0x180027ade`
- name: `EapUpdateMasterConnectionData`
- size: `802`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800258c8`
- `0x180027598`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180014e20`
- `0x180018520`
- `0x18001b5ec`
- `0x1800214f0`
- `0x1800277bc`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x180027888`
- `MobileNetworking!AllocateMemory` at `0x180027888`
- `MobileNetworking!FreeMemory` at `0x180027a93`
- `MobileNetworking!FreeMemory` at `0x180027a93`

## string_xrefs

- `0x180027876`: `EapUpdateMasterConnectionData`
- `0x180027a84`: `EapUpdateMasterConnectionData`

## pseudocode

```c
__int64 __fastcall EapUpdateMasterConnectionData(__int64 *a1, unsigned int a2, const void *a3)
{
  __int64 v3; // r13
  size_t v5; // rbp
  unsigned int v6; // edi
  __int128 *EapType; // rax
  __int64 v8; // r15
  __int128 v9; // xmm6
  _QWORD *v10; // rcx
  unsigned int v11; // esi
  unsigned int v12; // r14d
  unsigned int v13; // eax
  unsigned int AlignedSize; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _OWORD *v17; // rcx
  char *v18; // rdx
  __int64 v19; // r9
  unsigned int *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r9
  unsigned int v23; // r8d
  unsigned int *v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v28; // [rsp+30h] [rbp-68h] BYREF
  _OWORD *v29; // [rsp+A0h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = a2;
  v29 = 0;
  v6 = *(_DWORD *)(v3 + 20);
  EapType = (__int128 *)EapGetEapType(&v28, a1);
  v8 = *(_QWORD *)(v3 + 2744);
  v9 = *EapType;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !v8 || !a3 || !(_DWORD)v5 )
  {
    AlignedSize = 87;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
      WPP_SF_d(v10[7], 58, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
    goto LABEL_34;
  }
  v11 = v5 + 20;
  if ( (unsigned int)v5 >= 0xFFFFFFEC || (v12 = v5 + 124, v11 >= 0xFFFFFF98) )
  {
    AlignedSize = 534;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
      WPP_SF_dd(v10[7], 61, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, 534);
    goto LABEL_34;
  }
  v13 = AllocateMemory(v12, &v29, "EapUpdateMasterConnectionData", 584);
  AlignedSize = v13;
  if ( v13 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = 59;
LABEL_13:
      WPP_SF_dd(v15[7], v16, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, v13);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v17 = v29;
  if ( !v29 )
  {
    AlignedSize = 234;
    goto LABEL_25;
  }
  v18 = (char *)v29 + 60;
  *v29 = *(_OWORD *)v8;
  v17[1] = *(_OWORD *)(v8 + 16);
  v17[2] = *(_OWORD *)(v8 + 32);
  v17[3] = *(_OWORD *)(v8 + 48);
  v17[4] = *(_OWORD *)(v8 + 64);
  v17[5] = *(_OWORD *)(v8 + 80);
  *((_QWORD *)v17 + 12) = *(_QWORD *)(v8 + 96);
  v19 = *((unsigned int *)v17 + 16);
  *((_DWORD *)v17 + 1) = v5 + 124;
  *(_OWORD *)((char *)v17 + v19 + 4) = v9;
  AlignedSize = GetAlignedSize(32, v18);
  if ( AlignedSize )
    goto LABEL_25;
  v23 = *v20 + v11;
  if ( v23 < *v20 )
  {
    *v20 = -1;
    AlignedSize = 534;
    goto LABEL_25;
  }
  *v20 = v23;
  *(_DWORD *)(v22 + 20) |= 1u;
  AlignedSize = GetAlignedSize(v21, v22 + 28);
  if ( AlignedSize )
  {
LABEL_25:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        60,
        WPP_7a334571dc123d156aa3af8aa642e608_Traceguids,
        v6,
        AlignedSize);
    goto LABEL_34;
  }
  v26 = *v24;
  *(_DWORD *)(v25 + 24) = v11;
  *(_DWORD *)(v26 + v25 + 16) = v5;
  *(_OWORD *)(v26 + v25) = v9;
  memcpy_0((void *)(v26 + v25 + 20), a3, v5);
  v13 = SupplicantSetConnProfile(v3 + 2384, v12, v29);
  AlignedSize = v13;
  if ( v13 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = 62;
      goto LABEL_13;
    }
  }
LABEL_34:
  FreeMemory(&v29, "EapUpdateMasterConnectionData", 602);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, AlignedSize);
  return AlignedSize;
}

```

## disassembly

```asm
0x1800277bc  mov     rax, rsp
0x1800277bf  push    rbx
0x1800277c0  push    rbp
0x1800277c1  push    rsi
0x1800277c2  push    rdi
0x1800277c3  push    r12
0x1800277c5  push    r13
0x1800277c7  push    r14
0x1800277c9  push    r15
0x1800277cb  sub     rsp, 58h
0x1800277cf  mov     r13, [rcx]
0x1800277d2  mov     r12, r8
0x1800277d5  mov     ebp, edx
0x1800277d7  mov     rdx, rcx
0x1800277da  mov     qword ptr [rax+8], 0
0x1800277e2  lea     rcx, [rax-68h]
0x1800277e6  movaps  xmmword ptr [rax-58h], xmm6
0x1800277ea  mov     edi, [r13+14h]
0x1800277ee  call    EapGetEapType
0x1800277f3  mov     r15, [r13+0AB8h]
0x1800277fa  movups  xmm6, xmmword ptr [rax]
0x1800277fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180027804  lea     rax, WPP_GLOBAL_Control
0x18002780b  cmp     rcx, rax
0x18002780e  jz      short loc_18002783C
0x180027810  test    dword ptr [rcx+44h], 800h
0x180027817  jz      short loc_18002783C
0x180027819  mov     rcx, [rcx+38h]
0x18002781d  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027824  mov     edx, 39h ; '9'
0x180027829  call    WPP_SF_
0x18002782e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027835  lea     rax, WPP_GLOBAL_Control
0x18002783c  test    r15, r15
0x18002783f  jz      loc_180027A51
0x180027845  test    r12, r12
0x180027848  jz      loc_180027A51
0x18002784e  test    ebp, ebp
0x180027850  jz      loc_180027A51
0x180027856  lea     esi, [rbp+14h]
0x180027859  cmp     esi, 14h
0x18002785c  jb      loc_180027A23
0x180027862  lea     r14d, [rsi+68h]
0x180027866  cmp     r14d, 68h ; 'h'
0x18002786a  jb      loc_180027A23
0x180027870  mov     r9d, 248h
0x180027876  lea     r8, aEapupdatemaste; "EapUpdateMasterConnectionData"
0x18002787d  lea     rdx, [rsp+98h+arg_0]
0x180027885  mov     ecx, r14d
0x180027888  call    cs:__imp_AllocateMemory
0x18002788e  mov     ebx, eax
0x180027890  test    eax, eax
0x180027892  jz      short loc_1800278D6
0x180027894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002789b  lea     rsi, WPP_GLOBAL_Control
0x1800278a2  cmp     rcx, rsi
0x1800278a5  jz      loc_180027A7E
0x1800278ab  test    byte ptr [rcx+44h], 1
0x1800278af  jz      loc_180027A7E
0x1800278b5  mov     edx, 3Bh ; ';'
0x1800278ba  mov     [rsp+98h+var_78], eax
0x1800278be  mov     rcx, [rcx+38h]
0x1800278c2  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800278c9  mov     r9d, edi
0x1800278cc  call    WPP_SF_dd
0x1800278d1  jmp     loc_180027A7E
0x1800278d6  mov     rcx, [rsp+98h+arg_0]
0x1800278de  test    rcx, rcx
0x1800278e1  jz      loc_1800279F7
0x1800278e7  movups  xmm0, xmmword ptr [r15]
0x1800278eb  lea     eax, [rsi+68h]
0x1800278ee  lea     rdx, [rcx+3Ch]
0x1800278f2  movups  xmmword ptr [rcx], xmm0
0x1800278f5  movups  xmm1, xmmword ptr [r15+10h]
0x1800278fa  movups  xmmword ptr [rcx+10h], xmm1
0x1800278fe  movups  xmm0, xmmword ptr [r15+20h]
0x180027903  movups  xmmword ptr [rcx+20h], xmm0
0x180027907  movups  xmm1, xmmword ptr [r15+30h]
0x18002790c  movups  xmmword ptr [rcx+30h], xmm1
0x180027910  movups  xmm0, xmmword ptr [r15+40h]
0x180027915  movups  xmmword ptr [rcx+40h], xmm0
0x180027919  movups  xmm1, xmmword ptr [r15+50h]
0x18002791e  movups  xmmword ptr [rcx+50h], xmm1
0x180027922  movsd   xmm0, qword ptr [r15+60h]
0x180027928  movsd   qword ptr [rcx+60h], xmm0
0x18002792d  mov     r9d, [rcx+40h]
0x180027931  mov     [rcx+4], eax
0x180027934  add     r9, rcx
0x180027937  mov     ecx, 20h ; ' '
0x18002793c  movdqu  xmmword ptr [r9+4], xmm6
0x180027942  call    GetAlignedSize
0x180027947  mov     ebx, eax
0x180027949  test    eax, eax
0x18002794b  jnz     loc_1800279FC
0x180027951  mov     eax, [rdx]
0x180027953  lea     r8d, [rax+rsi]
0x180027957  cmp     r8d, eax
0x18002795a  jb      loc_1800279EA
0x180027960  mov     [rdx], r8d
0x180027963  lea     rdx, [r9+1Ch]
0x180027967  or      dword ptr [r9+14h], 1
0x18002796c  call    GetAlignedSize
0x180027971  mov     ebx, eax
0x180027973  test    eax, eax
0x180027975  jnz     loc_1800279FC
0x18002797b  mov     eax, [rdx]
0x18002797d  lea     rcx, [r9+14h]
0x180027981  mov     [r9+18h], esi
0x180027985  mov     r8, rbp; Size
0x180027988  add     rcx, rax; void *
0x18002798b  mov     rdx, r12; Src
0x18002798e  mov     [rax+r9+10h], ebp
0x180027993  movdqu  xmmword ptr [rax+r9], xmm6
0x180027999  call    memcpy_0
0x18002799e  mov     r8, [rsp+98h+arg_0]
0x1800279a6  lea     rcx, [r13+950h]
0x1800279ad  mov     edx, r14d
0x1800279b0  call    SupplicantSetConnProfile
0x1800279b5  mov     ebx, eax
0x1800279b7  test    eax, eax
0x1800279b9  jz      loc_180027A77
0x1800279bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279c6  lea     rsi, WPP_GLOBAL_Control
0x1800279cd  cmp     rcx, rsi
0x1800279d0  jz      loc_180027A7E
0x1800279d6  test    byte ptr [rcx+44h], 1
0x1800279da  jz      loc_180027A7E
0x1800279e0  mov     edx, 3Eh ; '>'
0x1800279e5  jmp     loc_1800278BA
0x1800279ea  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800279f0  mov     ebx, 216h
0x1800279f5  jmp     short loc_1800279FC
0x1800279f7  mov     ebx, 0EAh
0x1800279fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a03  lea     rsi, WPP_GLOBAL_Control
0x180027a0a  cmp     rcx, rsi
0x180027a0d  jz      short loc_180027A7E
0x180027a0f  test    byte ptr [rcx+44h], 1
0x180027a13  jz      short loc_180027A7E
0x180027a15  mov     edx, 3Ch ; '<'
0x180027a1a  mov     [rsp+98h+var_78], ebx
0x180027a1e  jmp     loc_1800278BE
0x180027a23  mov     ebx, 216h
0x180027a28  cmp     rcx, rax
0x180027a2b  jz      short loc_180027A77
0x180027a2d  test    byte ptr [rcx+44h], 1
0x180027a31  jz      short loc_180027A77
0x180027a33  mov     rcx, [rcx+38h]
0x180027a37  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027a3e  mov     edx, 3Dh ; '='
0x180027a43  mov     [rsp+98h+var_78], ebx
0x180027a47  mov     r9d, edi
0x180027a4a  call    WPP_SF_dd
0x180027a4f  jmp     short loc_180027A77
0x180027a51  mov     ebx, 57h ; 'W'
0x180027a56  cmp     rcx, rax
0x180027a59  jz      short loc_180027A77
0x180027a5b  test    byte ptr [rcx+44h], 1
0x180027a5f  jz      short loc_180027A77
0x180027a61  mov     rcx, [rcx+38h]
0x180027a65  lea     edx, [rbx-1Dh]
0x180027a68  mov     r9d, edi
0x180027a6b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027a72  call    WPP_SF_d
0x180027a77  lea     rsi, WPP_GLOBAL_Control
0x180027a7e  mov     r8d, 25Ah
0x180027a84  lea     rdx, aEapupdatemaste; "EapUpdateMasterConnectionData"
0x180027a8b  lea     rcx, [rsp+98h+arg_0]
0x180027a93  call    cs:__imp_FreeMemory
0x180027a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180027aa0  cmp     rcx, rsi
0x180027aa3  jz      short loc_180027AC6
0x180027aa5  test    dword ptr [rcx+44h], 800h
0x180027aac  jz      short loc_180027AC6
0x180027aae  mov     rcx, [rcx+38h]
0x180027ab2  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180027ab9  mov     edx, 3Fh ; '?'
0x180027abe  mov     r9d, ebx
0x180027ac1  call    WPP_SF_D
0x180027ac6  movaps  xmm6, [rsp+98h+var_58]
0x180027acb  mov     eax, ebx
0x180027acd  add     rsp, 58h
0x180027ad1  pop     r15
0x180027ad3  pop     r14
0x180027ad5  pop     r13
0x180027ad7  pop     r12
0x180027ad9  pop     rdi
0x180027ada  pop     rsi
0x180027adb  pop     rbp
0x180027adc  pop     rbx
0x180027add  retn
```
