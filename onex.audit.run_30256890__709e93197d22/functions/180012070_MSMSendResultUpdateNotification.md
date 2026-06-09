# MSMSendResultUpdateNotification

- ea: `0x180012070`
- end: `0x18001246f`
- name: `MSMSendResultUpdateNotification`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000dd40`

## callees

- `0x180005440`
- `0x180007f60`
- `0x1800106c8`
- `0x180010ae0`
- `0x180012070`
- `0x1800127a0`
- `0x180019570`
- `0x180019f28`
- `0x1800214f0`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x1800121ba`
- `MobileNetworking!AllocateMemory` at `0x1800121ba`
- `MobileNetworking!FreeMemory` at `0x18001240a`
- `MobileNetworking!FreeMemory` at `0x18001240a`

## string_xrefs

- `0x1800121a9`: `MSMSendResultUpdateNotification`
- `0x1800123fb`: `MSMSendResultUpdateNotification`

## pseudocode

```c
__int64 __fastcall MSMSendResultUpdateNotification(_DWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r13d
  __int64 v6; // r8
  __int64 v7; // r10
  unsigned int v8; // edi
  unsigned int v9; // esi
  const void *v10; // r12
  unsigned int v11; // r15d
  unsigned int v12; // ecx
  unsigned int v13; // r14d
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  int v18; // edx
  _DWORD *v19; // rbp
  _DWORD *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // r15d
  int v23; // eax
  void *v25; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-40h]
  int v27; // [rsp+80h] [rbp+8h]
  unsigned int Size; // [rsp+88h] [rbp+10h]
  unsigned __int64 v29; // [rsp+98h] [rbp+20h] BYREF

  v5 = a1[5];
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
  if ( a1[679] == a1[680] && !(unsigned int)PortMgrHasResultChanged(a1) )
  {
    v8 = 0;
    if ( v7 != v6 && *(char *)(v7 + 68) < 0 )
      WPP_SF_d(*(_QWORD *)(v7 + 56), 33, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5);
    goto LABEL_43;
  }
  v9 = *(_DWORD *)(a3 + 28);
  if ( v9 )
  {
    v10 = (const void *)(a3 + *(unsigned int *)(a3 + 32));
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  Size = *(_DWORD *)(a3 + 20);
  v11 = Size + 7;
  if ( Size + 7 < Size
    || (v12 = (v11 & 0xFFFFFFF8) + 40, (v11 & 0xFFFFFFF8) >= 0xFFFFFFD8)
    || (v13 = v9 + 7, v9 + 7 < v9) )
  {
    v8 = 534;
    goto LABEL_43;
  }
  v14 = v12 + (v13 & 0xFFFFFFF8);
  v27 = v14;
  if ( v14 < v12 )
  {
    v8 = 534;
    goto LABEL_43;
  }
  v15 = AllocateMemory(v14, &v29, "MSMSendResultUpdateNotification", 279);
  v8 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5, v15);
    goto LABEL_43;
  }
  v16 = v29;
  *(_QWORD *)v29 = *(_QWORD *)a3;
  *(_DWORD *)(v16 + 8) = *(_DWORD *)(a3 + 8);
  *(_DWORD *)(v29 + 12) = a1[679];
  *(_DWORD *)(v29 + 16) = a1[674];
  if ( !v29 )
  {
    v18 = 87;
LABEL_42:
    v8 = v18;
    goto LABEL_43;
  }
  v17 = -1;
  v8 = 534;
  if ( v29 + 40 >= v29 )
    v17 = v29 + 40;
  v18 = v29 + 40 < v29 ? 0x216 : 0;
  v26 = (_DWORD *)v17;
  v25 = (void *)v17;
  if ( v29 + 40 < v29 )
    goto LABEL_42;
  if ( *(_DWORD *)(a3 + 20) )
  {
    *(_DWORD *)(v29 + 20) |= 1u;
    *(_DWORD *)(v29 + 24) = Size;
    *(_DWORD *)(v29 + 28) = 40;
    memcpy_0((void *)v17, (const void *)(a3 + *(unsigned int *)(a3 + 24)), Size);
    v19 = v26;
    v20 = v26;
    v26[5] &= ~2u;
    *((_QWORD *)v20 + 4) = 0;
    OneXScrubAuthParams(v20);
    v21 = AddAlignedSizeToPointer(Size, v19, &v25);
    if ( v21 )
    {
      v8 = v21;
      goto LABEL_43;
    }
    v17 = (__int64)v25;
    v22 = (v11 & 0xFFFFFFF8) + 40;
    v26 = v25;
  }
  else
  {
    *(_DWORD *)(v29 + 20) &= ~1u;
    v22 = 40;
  }
  if ( v9 )
  {
    *(_DWORD *)(v29 + 20) |= 2u;
    *(_DWORD *)(v29 + 32) = v9;
    *(_DWORD *)(v29 + 36) = v22;
    memcpy_0((void *)v17, v10, v9);
    if ( v22 + (v13 & 0xFFFFFFF8) < v22 )
      goto LABEL_43;
    v8 = AddAlignedSizeToPointer(v9, v26, &v25);
    if ( v8 )
      goto LABEL_43;
  }
  else
  {
    *(_DWORD *)(v29 + 20) &= ~2u;
  }
  v23 = MSMSendOneXEventNotification((__int64)a1, 1u, v27, v29);
  if ( v23 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v5, v23);
  v8 = 0;
  a1[680] = a1[679];
LABEL_43:
  FreeMemory(&v29, "MSMSendResultUpdateNotification", 348);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180012070  mov     rax, rsp
0x180012073  mov     [rax+10h], edx
0x180012076  sub     rsp, 78h
0x18001207a  mov     [rax+18h], rbx
0x18001207e  mov     rbx, rcx
0x180012081  mov     [rax-8], rbp
0x180012085  mov     rbp, r8
0x180012088  mov     [rax-10h], rsi
0x18001208c  mov     [rax-28h], r13
0x180012090  mov     r13d, [rcx+14h]
0x180012094  mov     qword ptr [rax+20h], 0
0x18001209c  mov     r10, cs:WPP_GLOBAL_Control
0x1800120a3  lea     r8, WPP_GLOBAL_Control
0x1800120aa  cmp     r10, r8
0x1800120ad  jz      short loc_1800120DC
0x1800120af  test    dword ptr [r10+44h], 800h
0x1800120b7  jz      short loc_1800120DC
0x1800120b9  mov     rcx, [r10+38h]
0x1800120bd  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800120c4  mov     edx, 1Eh
0x1800120c9  call    WPP_SF_
0x1800120ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800120d5  lea     r8, WPP_GLOBAL_Control
0x1800120dc  mov     eax, [rbx+0AA0h]
0x1800120e2  mov     [rsp+78h+var_18], rdi
0x1800120e7  mov     [rsp+78h+var_20], r12
0x1800120ec  mov     [rsp+78h+var_30], r14
0x1800120f1  mov     [rsp+78h+var_38], r15
0x1800120f6  cmp     [rbx+0A9Ch], eax
0x1800120fc  jnz     short loc_18001213D
0x1800120fe  mov     rcx, rbx
0x180012101  call    PortMgrHasResultChanged
0x180012106  test    eax, eax
0x180012108  jnz     short loc_18001213D
0x18001210a  xor     edi, edi
0x18001210c  cmp     r10, r8
0x18001210f  jz      loc_1800123EE
0x180012115  test    byte ptr [r10+44h], 80h
0x18001211a  jz      loc_1800123EE
0x180012120  mov     rcx, [r10+38h]
0x180012124  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001212b  mov     edx, 21h ; '!'
0x180012130  mov     r9d, r13d
0x180012133  call    WPP_SF_d
0x180012138  jmp     loc_1800123EE
0x18001213d  mov     esi, [rbp+1Ch]
0x180012140  test    esi, esi
0x180012142  jz      short loc_18001214D
0x180012144  mov     r12d, [rbp+20h]
0x180012148  add     r12, rbp
0x18001214b  jmp     short loc_180012152
0x18001214d  xor     esi, esi
0x18001214f  xor     r12d, r12d
0x180012152  mov     eax, [rbp+14h]
0x180012155  mov     dword ptr [rsp+78h+Size], eax
0x18001215c  lea     r15d, [rax+7]
0x180012160  cmp     r15d, eax
0x180012163  jb      short loc_180012173
0x180012165  mov     ecx, r15d
0x180012168  and     ecx, 0FFFFFFF8h
0x18001216b  add     ecx, 28h ; '('
0x18001216e  cmp     ecx, 28h ; '('
0x180012171  jnb     short loc_18001217D
0x180012173  mov     edi, 216h
0x180012178  jmp     loc_1800123EE
0x18001217d  lea     r14d, [rsi+7]
0x180012181  cmp     r14d, esi
0x180012184  jb      short loc_180012173
0x180012186  mov     eax, r14d
0x180012189  and     eax, 0FFFFFFF8h
0x18001218c  add     eax, ecx
0x18001218e  mov     [rsp+78h+arg_0], eax
0x180012195  cmp     eax, ecx
0x180012197  jnb     short loc_1800121A3
0x180012199  mov     edi, 216h
0x18001219e  jmp     loc_1800123EE
0x1800121a3  mov     r9d, 117h
0x1800121a9  lea     r8, aMsmsendresultu; "MSMSendResultUpdateNotification"
0x1800121b0  lea     rdx, [rsp+78h+arg_18]
0x1800121b8  mov     ecx, eax
0x1800121ba  call    cs:__imp_AllocateMemory
0x1800121c0  mov     edi, eax
0x1800121c2  test    eax, eax
0x1800121c4  jz      short loc_180012208
0x1800121c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121cd  lea     rsi, WPP_GLOBAL_Control
0x1800121d4  cmp     rcx, rsi
0x1800121d7  jz      loc_1800123F5
0x1800121dd  test    byte ptr [rcx+44h], 1
0x1800121e1  jz      loc_1800123F5
0x1800121e7  mov     rcx, [rcx+38h]
0x1800121eb  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800121f2  mov     edx, 1Fh
0x1800121f7  mov     [rsp+78h+var_58], eax
0x1800121fb  mov     r9d, r13d
0x1800121fe  call    WPP_SF_dd
0x180012203  jmp     loc_1800123F5
0x180012208  mov     rcx, [rsp+78h+arg_18]
0x180012210  movsd   xmm0, qword ptr [rbp+0]
0x180012215  movsd   qword ptr [rcx], xmm0
0x180012219  mov     eax, [rbp+8]
0x18001221c  mov     [rcx+8], eax
0x18001221f  mov     ecx, [rbx+0A9Ch]
0x180012225  mov     rax, [rsp+78h+arg_18]
0x18001222d  mov     [rax+0Ch], ecx
0x180012230  mov     ecx, [rbx+0A88h]
0x180012236  mov     rax, [rsp+78h+arg_18]
0x18001223e  mov     [rax+10h], ecx
0x180012241  mov     rcx, [rsp+78h+arg_18]
0x180012249  test    rcx, rcx
0x18001224c  jz      loc_1800123E7
0x180012252  lea     rax, [rcx+28h]
0x180012256  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18001225d  cmp     rax, rcx
0x180012260  mov     edi, 216h
0x180012265  cmovnb  r9, rax
0x180012269  sbb     edx, edx
0x18001226b  and     edx, edi
0x18001226d  mov     [rsp+78h+var_40], r9
0x180012272  mov     [rsp+78h+var_48], r9
0x180012277  cmp     rax, rcx
0x18001227a  jb      loc_1800123EC
0x180012280  cmp     dword ptr [rbp+14h], 0
0x180012284  jz      loc_18001230C
0x18001228a  or      dword ptr [rcx+14h], 1
0x18001228e  mov     rax, [rsp+78h+arg_18]
0x180012296  mov     ecx, dword ptr [rsp+78h+Size]
0x18001229d  mov     r8d, ecx; Size
0x1800122a0  mov     [rax+18h], ecx
0x1800122a3  mov     rcx, r9; void *
0x1800122a6  mov     rax, [rsp+78h+arg_18]
0x1800122ae  mov     dword ptr [rax+1Ch], 28h ; '('
0x1800122b5  mov     edx, [rbp+18h]
0x1800122b8  add     rdx, rbp; Src
0x1800122bb  call    memcpy_0
0x1800122c0  mov     rbp, [rsp+78h+var_40]
0x1800122c5  mov     rcx, rbp
0x1800122c8  and     dword ptr [rbp+14h], 0FFFFFFFDh
0x1800122cc  mov     qword ptr [rbp+20h], 0
0x1800122d4  call    OneXScrubAuthParams
0x1800122d9  mov     ecx, dword ptr [rsp+78h+Size]
0x1800122e0  lea     r8, [rsp+78h+var_48]
0x1800122e5  mov     rdx, rbp
0x1800122e8  call    AddAlignedSizeToPointer
0x1800122ed  test    eax, eax
0x1800122ef  jnz     short loc_180012305
0x1800122f1  mov     r9, [rsp+78h+var_48]
0x1800122f6  and     r15d, 0FFFFFFF8h
0x1800122fa  add     r15d, 28h ; '('
0x1800122fe  mov     [rsp+78h+var_40], r9
0x180012303  jmp     short loc_180012316
0x180012305  mov     edi, eax
0x180012307  jmp     loc_1800123EE
0x18001230c  and     dword ptr [rcx+14h], 0FFFFFFFEh
0x180012310  mov     r15d, 28h ; '('
0x180012316  mov     rax, [rsp+78h+arg_18]
0x18001231e  test    esi, esi
0x180012320  jz      short loc_180012374
0x180012322  or      dword ptr [rax+14h], 2
0x180012326  mov     rdx, r12; Src
0x180012329  mov     rax, [rsp+78h+arg_18]
0x180012331  mov     rcx, r9; void *
0x180012334  mov     r8d, esi; Size
0x180012337  mov     [rax+20h], esi
0x18001233a  mov     rax, [rsp+78h+arg_18]
0x180012342  mov     [rax+24h], r15d
0x180012346  call    memcpy_0
0x18001234b  and     r14d, 0FFFFFFF8h
0x18001234f  add     r14d, r15d
0x180012352  cmp     r14d, r15d
0x180012355  jb      loc_1800123EE
0x18001235b  mov     rdx, [rsp+78h+var_40]
0x180012360  lea     r8, [rsp+78h+var_48]
0x180012365  mov     ecx, esi
0x180012367  call    AddAlignedSizeToPointer
0x18001236c  mov     edi, eax
0x18001236e  test    eax, eax
0x180012370  jnz     short loc_1800123EE
0x180012372  jmp     short loc_180012378
0x180012374  and     dword ptr [rax+14h], 0FFFFFFFDh
0x180012378  mov     r9, [rsp+78h+arg_18]
0x180012380  mov     edx, 1
0x180012385  mov     r8d, [rsp+78h+arg_0]
0x18001238d  mov     rcx, rbx
0x180012390  call    MSMSendOneXEventNotification
0x180012395  test    eax, eax
0x180012397  jz      short loc_1800123D0
0x180012399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123a0  lea     rsi, WPP_GLOBAL_Control
0x1800123a7  cmp     rcx, rsi
0x1800123aa  jz      short loc_1800123D7
0x1800123ac  test    byte ptr [rcx+44h], 1
0x1800123b0  jz      short loc_1800123D7
0x1800123b2  mov     rcx, [rcx+38h]
0x1800123b6  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800123bd  mov     edx, 20h ; ' '
0x1800123c2  mov     [rsp+78h+var_58], eax
0x1800123c6  mov     r9d, r13d
0x1800123c9  call    WPP_SF_dd
0x1800123ce  jmp     short loc_1800123D7
0x1800123d0  lea     rsi, WPP_GLOBAL_Control
0x1800123d7  mov     eax, [rbx+0A9Ch]
0x1800123dd  xor     edi, edi
0x1800123df  mov     [rbx+0AA0h], eax
0x1800123e5  jmp     short loc_1800123F5
0x1800123e7  mov     edx, 57h ; 'W'
0x1800123ec  mov     edi, edx
0x1800123ee  lea     rsi, WPP_GLOBAL_Control
0x1800123f5  mov     r8d, 15Ch
0x1800123fb  lea     rdx, aMsmsendresultu; "MSMSendResultUpdateNotification"
0x180012402  lea     rcx, [rsp+78h+arg_18]
0x18001240a  call    cs:__imp_FreeMemory
0x180012410  mov     rcx, cs:WPP_GLOBAL_Control
0x180012417  mov     r15, [rsp+78h+var_38]
0x18001241c  cmp     rcx, rsi
0x18001241f  mov     rsi, [rsp+78h+var_10]
0x180012424  mov     r14, [rsp+78h+var_30]
0x180012429  mov     r13, [rsp+78h+var_28]
0x18001242e  mov     r12, [rsp+78h+var_20]
0x180012433  mov     rbp, [rsp+78h+var_8]
0x180012438  mov     rbx, [rsp+78h+arg_10]
0x180012440  jz      short loc_180012463
0x180012442  test    dword ptr [rcx+44h], 800h
0x180012449  jz      short loc_180012463
0x18001244b  mov     rcx, [rcx+38h]
0x18001244f  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180012456  mov     edx, 22h ; '"'
0x18001245b  mov     r9d, edi
0x18001245e  call    WPP_SF_D
0x180012463  mov     eax, edi
0x180012465  mov     rdi, [rsp+78h+var_18]
0x18001246a  add     rsp, 78h
0x18001246e  retn
```
