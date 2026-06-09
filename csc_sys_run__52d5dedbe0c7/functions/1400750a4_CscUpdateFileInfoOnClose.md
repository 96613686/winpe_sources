# CscUpdateFileInfoOnClose

- ea: `0x1400750a4`
- end: `0x14007533f`
- name: `CscUpdateFileInfoOnClose`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140074330`

## callees

- `0x1400017c0`
- `0x140014da4`
- `0x1400180f4`
- `0x1400190ec`
- `0x14001b568`
- `0x14002f010`
- `0x14002f440`
- `0x1400750a4`

## import_xrefs

- `rdbss!RxFinishFcbInitialization` at `0x1400752c6`
- `rdbss!RxFinishFcbInitialization` at `0x1400752c6`
- `rdbss!RxInitNetInfoFromFcb` at `0x140075170`
- `rdbss!RxInitNetInfoFromFcb` at `0x140075170`

## pseudocode

```c
__int64 __fastcall CscUpdateFileInfoOnClose(__int64 a1, __int64 a2)
{
  struct _MRX_FCB_ *v2; // r14
  bool v5; // zf
  _OWORD *v6; // rdi
  int NetInfoUsingEnum; // ebx
  int v8; // esi
  __int64 v9; // rcx
  __int128 v10; // xmm1
  int v11; // eax
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE InitPacket[80]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v16; // [rsp+B0h] [rbp-50h]
  __int64 v17; // [rsp+C0h] [rbp-40h]
  _OWORD v18[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v19; // [rsp+E8h] [rbp-18h]
  __int64 v20; // [rsp+F8h] [rbp-8h]
  _OWORD v21[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v22; // [rsp+120h] [rbp+20h]
  __int64 v23; // [rsp+130h] [rbp+30h]

  v2 = *(struct _MRX_FCB_ **)(a1 + 56);
  v20 = 0;
  v23 = 0;
  v17 = 0;
  memset(v18, 0, sizeof(v18));
  v19 = 0;
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  v15 = 0;
  v16 = 0;
  memset(InitPacket, 0, 0x4Cu);
  v5 = (*(_BYTE *)(a1 + 504) & 2) == 0;
  v13 = 1;
  if ( v5 )
  {
    NetInfoUsingEnum = CscQueryNetInfoUsingEnum(a1, (__int64)&v2[2].Header.Resource, (RXVBO)v18);
    if ( NetInfoUsingEnum < 0 )
    {
      v8 = 11176;
      goto LABEL_16;
    }
    RxInitNetInfoFromFcb(v2, v21);
    if ( *(_QWORD *)&v21[0] != *(_QWORD *)&v18[0]
      || *((_QWORD *)&v22 + 1) != *((_QWORD *)&v19 + 1)
      || (((unsigned __int8)((unsigned int)v23 >> 14) ^ (unsigned __int8)((unsigned int)v20 >> 14)) & 1) != 0
      || (v6 = v18, (((unsigned __int8)((unsigned int)v23 >> 4) ^ (unsigned __int8)((unsigned int)v20 >> 4)) & 1) != 0) )
    {
      NetInfoUsingEnum = -1073741788;
      v8 = 11200;
      goto LABEL_16;
    }
  }
  else
  {
    v6 = (_OWORD *)(a1 + 448);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      211,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      *((_QWORD *)v6 + 2),
      *((_QWORD *)v6 + 3));
  v9 = *(_QWORD *)(a2 + 8);
  v10 = v6[1];
  v11 = *((_DWORD *)v6 + 12);
  v15 = *v6;
  HIDWORD(v17) = HIDWORD(*((_QWORD *)v6 + 4));
  LODWORD(v17) = v11;
  v16 = v10;
  NetInfoUsingEnum = CscStoreUpdateLocalBasicInformationEntry(*(_QWORD *)(v9 + 56), 0, &v15, 0);
  if ( NetInfoUsingEnum >= 0 )
  {
    v8 = 0;
    NetInfoUsingEnum = CscStoreSetInformationEntry(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 56LL), 0, 0, 0, (__int64)v6, 0, 0);
    *(_DWORD *)InitPacket = 0;
    *(_QWORD *)&InitPacket[8] = v6 + 3;
    *(_QWORD *)&InitPacket[16] = &v13;
    *(_QWORD *)&InitPacket[24] = v6;
    *(_QWORD *)&InitPacket[32] = (char *)v6 + 8;
    memset(&InitPacket[56], 0, 24);
    *(_QWORD *)&InitPacket[40] = v6 + 1;
    *(_QWORD *)&InitPacket[48] = (char *)v6 + 24;
    HIDWORD(v2->SrvOpenList.Flink) &= ~0x40000u;
    RxFinishFcbInitialization(v2, (RX_FILE_TYPE)(unsigned __int16)v2->Header.NodeTypeCode, (PFCB_INIT_PACKET)InitPacket);
  }
  else
  {
    v8 = 11222;
  }
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      212,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)NetInfoUsingEnum,
      v8);
  return (unsigned int)NetInfoUsingEnum;
}

```

## disassembly

```asm
0x1400750a4  mov     [rsp-8+arg_10], rbx
0x1400750a9  mov     [rsp-8+arg_18], rsi
0x1400750ae  push    rbp
0x1400750af  push    rdi
0x1400750b0  push    r13
0x1400750b2  push    r14
0x1400750b4  push    r15
0x1400750b6  lea     rbp, [rsp-40h]
0x1400750bb  sub     rsp, 140h
0x1400750c2  mov     rax, cs:__security_cookie
0x1400750c9  xor     rax, rsp
0x1400750cc  mov     [rbp+60h+var_28], rax
0x1400750d0  mov     r14, [rcx+38h]
0x1400750d4  xor     eax, eax
0x1400750d6  xorps   xmm0, xmm0
0x1400750d9  mov     [rbp+60h+var_68], rax
0x1400750dd  xorps   xmm1, xmm1
0x1400750e0  mov     [rbp+60h+var_30], rax
0x1400750e4  mov     r13, rdx
0x1400750e7  mov     [rbp+60h+var_A0], rax
0x1400750eb  mov     rbx, rcx
0x1400750ee  mov     dword ptr [rsp+160h+InitPacket+4], eax
0x1400750f2  lea     r8d, [rax+4Ch]; Size
0x1400750f6  xor     edx, edx; Val
0x1400750f8  lea     rcx, [rsp+160h+InitPacket]; void *
0x1400750fd  movups  [rbp+60h+var_98], xmm0
0x140075101  movups  [rbp+60h+var_88], xmm0
0x140075105  movups  [rbp+60h+var_78], xmm0
0x140075109  movups  [rbp+60h+var_60], xmm1
0x14007510d  movups  [rbp+60h+var_50], xmm1
0x140075111  movups  [rbp+60h+var_40], xmm1
0x140075115  movups  [rbp+60h+var_C0], xmm0
0x140075119  movups  [rbp+60h+var_B0], xmm0
0x14007511d  call    memset
0x140075122  test    byte ptr [rbx+1F8h], 2
0x140075129  lea     rsi, WPP_GLOBAL_Control
0x140075130  mov     [rsp+160h+var_120], 1
0x140075138  jz      short loc_140075146
0x14007513a  lea     rdi, [rbx+1C0h]
0x140075141  jmp     loc_1400751CD
0x140075146  lea     rdx, [r14+168h]
0x14007514d  mov     rcx, rbx
0x140075150  lea     r8, [rbp+60h+var_98]
0x140075154  call    CscQueryNetInfoUsingEnum
0x140075159  mov     ebx, eax
0x14007515b  test    eax, eax
0x14007515d  jns     short loc_140075169
0x14007515f  mov     esi, 2BA8h
0x140075164  jmp     loc_1400752DE
0x140075169  lea     rdx, [rbp+60h+var_60]
0x14007516d  mov     rcx, r14
0x140075170  call    cs:__imp_RxInitNetInfoFromFcb
0x140075177  nop     dword ptr [rax+rax+00h]
0x14007517c  mov     rax, qword ptr [rbp+60h+var_98]
0x140075180  cmp     qword ptr [rbp+60h+var_60], rax
0x140075184  jnz     loc_1400752D4
0x14007518a  mov     rax, qword ptr [rbp+60h+var_78+8]
0x14007518e  cmp     qword ptr [rbp+60h+var_40+8], rax
0x140075192  jnz     loc_1400752D4
0x140075198  mov     rdx, [rbp+60h+var_68]
0x14007519c  mov     r8, [rbp+60h+var_30]
0x1400751a0  mov     ecx, edx
0x1400751a2  shr     ecx, 0Eh
0x1400751a5  mov     eax, r8d
0x1400751a8  shr     eax, 0Eh
0x1400751ab  xor     cl, al
0x1400751ad  test    cl, 1
0x1400751b0  jnz     loc_1400752D4
0x1400751b6  shr     edx, 4
0x1400751b9  lea     rdi, [rbp+60h+var_98]
0x1400751bd  shr     r8d, 4
0x1400751c1  xor     dl, r8b
0x1400751c4  test    dl, 1
0x1400751c7  jnz     loc_1400752D4
0x1400751cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400751d4  cmp     rcx, rsi
0x1400751d7  jz      short loc_140075202
0x1400751d9  mov     eax, [rcx+2Ch]
0x1400751dc  test    al, 40h
0x1400751de  jz      short loc_140075202
0x1400751e0  mov     rax, [rdi+18h]
0x1400751e4  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400751eb  mov     r9, [rdi+10h]
0x1400751ef  mov     edx, 0D3h
0x1400751f4  mov     rcx, [rcx+18h]
0x1400751f8  mov     [rsp+160h+var_140], rax
0x1400751fd  call    WPP_SF_qq
0x140075202  movups  xmm0, xmmword ptr [rdi]
0x140075205  mov     rcx, [r13+8]
0x140075209  lea     r15, [rdi+30h]
0x14007520d  movups  xmm1, xmmword ptr [rdi+10h]
0x140075211  mov     eax, [r15]
0x140075214  lea     r8, [rbp+60h+var_C0]
0x140075218  movups  [rbp+60h+var_C0], xmm0
0x14007521c  xor     r9d, r9d
0x14007521f  xor     edx, edx
0x140075221  movsd   xmm0, qword ptr [rdi+20h]
0x140075226  movsd   [rbp+60h+var_A0], xmm0
0x14007522b  mov     dword ptr [rbp+60h+var_A0], eax
0x14007522e  movups  [rbp+60h+var_B0], xmm1
0x140075232  mov     rcx, [rcx+38h]
0x140075236  call    CscStoreUpdateLocalBasicInformationEntry
0x14007523b  mov     ebx, eax
0x14007523d  test    eax, eax
0x14007523f  jns     short loc_14007524B
0x140075241  mov     esi, 2BD6h
0x140075246  jmp     loc_1400752DE
0x14007524b  mov     rcx, [r13+8]
0x14007524f  xor     esi, esi
0x140075251  mov     [rsp+160h+var_130], rsi
0x140075256  xor     r9d, r9d
0x140075259  mov     [rsp+160h+var_138], rsi
0x14007525e  xor     r8d, r8d
0x140075261  xor     edx, edx
0x140075263  mov     [rsp+160h+var_140], rdi
0x140075268  mov     rcx, [rcx+38h]
0x14007526c  call    CscStoreSetInformationEntry
0x140075271  mov     ebx, eax
0x140075273  mov     dword ptr [rsp+160h+InitPacket], esi
0x140075277  mov     qword ptr [rsp+160h+InitPacket+8], r15
0x14007527c  lea     rax, [rsp+160h+var_120]
0x140075281  mov     qword ptr [rsp+160h+InitPacket+10h], rax
0x140075286  lea     r8, [rsp+160h+InitPacket]; InitPacket
0x14007528b  mov     qword ptr [rsp+160h+InitPacket+18h], rdi
0x140075290  lea     rax, [rdi+8]
0x140075294  mov     qword ptr [rsp+160h+InitPacket+20h], rax
0x140075299  xorps   xmm0, xmm0
0x14007529c  mov     qword ptr [rbp+60h+InitPacket+38h], rsi
0x1400752a0  lea     rax, [rdi+10h]
0x1400752a4  mov     qword ptr [rsp+160h+InitPacket+28h], rax
0x1400752a9  mov     rcx, r14; Fcb
0x1400752ac  movdqa  xmmword ptr [rbp+60h+InitPacket+40h], xmm0
0x1400752b1  lea     rax, [rdi+18h]
0x1400752b5  mov     qword ptr [rbp+60h+InitPacket+30h], rax
0x1400752b9  btr     dword ptr [r14+9Ch], 12h
0x1400752c2  movzx   edx, word ptr [r14]; FileType
0x1400752c6  call    cs:__imp_RxFinishFcbInitialization
0x1400752cd  nop     dword ptr [rax+rax+00h]
0x1400752d2  jmp     short loc_1400752DE
0x1400752d4  mov     ebx, 0C0000024h
0x1400752d9  mov     esi, 2BC0h
0x1400752de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400752e5  lea     rax, WPP_GLOBAL_Control
0x1400752ec  cmp     rcx, rax
0x1400752ef  jz      short loc_140075314
0x1400752f1  mov     eax, [rcx+2Ch]
0x1400752f4  test    al, 20h
0x1400752f6  jz      short loc_140075314
0x1400752f8  mov     rcx, [rcx+18h]
0x1400752fc  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140075303  mov     edx, 0D4h
0x140075308  mov     dword ptr [rsp+160h+var_140], esi
0x14007530c  mov     r9d, ebx
0x14007530f  call    WPP_SF_Dd
0x140075314  mov     eax, ebx
0x140075316  mov     rcx, [rbp+60h+var_28]
0x14007531a  xor     rcx, rsp; StackCookie
0x14007531d  call    __security_check_cookie
0x140075322  lea     r11, [rsp+160h+var_20]
0x14007532a  mov     rbx, [r11+40h]
0x14007532e  mov     rsi, [r11+48h]
0x140075332  mov     rsp, r11
0x140075335  pop     r15
0x140075337  pop     r14
0x140075339  pop     r13
0x14007533b  pop     rdi
0x14007533c  pop     rbp
0x14007533d  retn
```
