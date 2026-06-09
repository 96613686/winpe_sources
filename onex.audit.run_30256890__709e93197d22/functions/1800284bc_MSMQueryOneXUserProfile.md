# MSMQueryOneXUserProfile

- ea: `0x1800284bc`
- end: `0x18002871d`
- name: `MSMQueryOneXUserProfile`
- size: `609`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180007fb0`
- `0x18000a318`
- `0x18001dab8`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x1800214f0`
- `0x1800281dc`
- `0x1800284bc`
- `0x18002b3c4`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800285a2`
- `MobileNetworking!ReleaseWriteLock` at `0x1800285a2`
- `MobileNetworking!AcquireWriteLock` at `0x1800286b4`
- `MobileNetworking!AcquireWriteLock` at `0x1800286b4`

## pseudocode

```c
__int64 __fastcall MSMQueryOneXUserProfile(__int64 a1, __int64 a2, _DWORD *a3, _QWORD *a4)
{
  unsigned int v4; // ebp
  __int64 v6; // rsi
  __int64 v8; // r12
  char *v11; // rcx
  bool v12; // zf
  unsigned int v13; // eax
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // esi
  int v19; // [rsp+60h] [rbp+8h] BYREF
  __int64 v20; // [rsp+70h] [rbp+18h] BYREF

  v4 = *(_DWORD *)(a1 + 20);
  v6 = *(_QWORD *)(a1 + 192);
  v8 = *(_QWORD *)(a1 + 2368);
  v20 = 0;
  v19 = 0;
  v11 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v11 = (char *)WPP_GLOBAL_Control;
    }
    if ( v11 != (char *)&WPP_GLOBAL_Control && v11[68] < 0 )
    {
      WPP_SF_d(*((_QWORD *)v11 + 7), 43, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4);
      v11 = (char *)WPP_GLOBAL_Control;
    }
  }
  v12 = *(_QWORD *)(a1 + 2320) == 0;
  *a4 = 0;
  *a3 = 0;
  if ( !v12 )
  {
    ReleaseWriteLock(a1, a1 + 2896, "MSMQueryOneXUserProfile", 444);
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *, __int64 *))(a1 + 2320))(v6, v8, a2, &v19, &v20);
    v14 = v13;
    if ( v13 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_24;
      v16 = 44;
      goto LABEL_12;
    }
    v17 = 1;
    if ( v20 )
    {
      if ( v19 )
      {
        v13 = ProfileMgrValidateUserProfile();
        v14 = v13;
        if ( v13 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_24;
          v16 = 45;
LABEL_12:
          WPP_SF_dd(v15[7], v16, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, v13);
LABEL_24:
          AcquireWriteLock(a1, a1 + 2896, "MSMQueryOneXUserProfile", 479);
          v11 = (char *)WPP_GLOBAL_Control;
          goto LABEL_25;
        }
      }
    }
    goto LABEL_22;
  }
  v14 = 0;
  v17 = 0;
  if ( v11 != (char *)&WPP_GLOBAL_Control && v11[68] < 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 7), 46, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4);
LABEL_22:
    v11 = (char *)WPP_GLOBAL_Control;
  }
  *a4 = v20;
  *a3 = v19;
  if ( v17 )
    goto LABEL_24;
LABEL_25:
  if ( v14 && v20 )
  {
    MSMFreeMemory(a1);
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( v11 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v11 + 7), 47, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x1800284bc  mov     rax, rsp
0x1800284bf  mov     [rax+10h], rbx
0x1800284c3  mov     [rax+20h], rbp
0x1800284c7  push    rsi
0x1800284c8  push    rdi
0x1800284c9  push    r12
0x1800284cb  push    r14
0x1800284cd  push    r15
0x1800284cf  sub     rsp, 30h
0x1800284d3  mov     ebp, [rcx+14h]
0x1800284d6  mov     r14, r9
0x1800284d9  mov     rsi, [rcx+0C0h]
0x1800284e0  mov     r15, r8
0x1800284e3  mov     r12, [rcx+940h]
0x1800284ea  mov     rbx, rdx
0x1800284ed  mov     rdi, rcx
0x1800284f0  mov     qword ptr [rax+18h], 0
0x1800284f8  mov     dword ptr [rax+8], 0
0x1800284ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180028506  lea     rax, WPP_GLOBAL_Control
0x18002850d  cmp     rcx, rax
0x180028510  jz      short loc_18002856F
0x180028512  test    dword ptr [rcx+44h], 800h
0x180028519  jz      short loc_18002853E
0x18002851b  mov     rcx, [rcx+38h]
0x18002851f  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028526  mov     edx, 2Ah ; '*'
0x18002852b  call    WPP_SF_
0x180028530  mov     rcx, cs:WPP_GLOBAL_Control
0x180028537  lea     rax, WPP_GLOBAL_Control
0x18002853e  cmp     rcx, rax
0x180028541  jz      short loc_18002856F
0x180028543  test    byte ptr [rcx+44h], 80h
0x180028547  jz      short loc_18002856F
0x180028549  mov     rcx, [rcx+38h]
0x18002854d  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028554  mov     edx, 2Bh ; '+'
0x180028559  mov     r9d, ebp
0x18002855c  call    WPP_SF_d
0x180028561  mov     rcx, cs:WPP_GLOBAL_Control
0x180028568  lea     rax, WPP_GLOBAL_Control
0x18002856f  cmp     qword ptr [rdi+910h], 0
0x180028577  mov     qword ptr [r14], 0
0x18002857e  mov     dword ptr [r15], 0
0x180028585  jz      loc_180028657
0x18002858b  lea     rdx, [rdi+0B50h]
0x180028592  mov     r9d, 1BCh
0x180028598  lea     r8, aMsmqueryonexus; "MSMQueryOneXUserProfile"
0x18002859f  mov     rcx, rdi
0x1800285a2  call    cs:__imp_ReleaseWriteLock
0x1800285a8  lea     rax, [rsp+58h+arg_10]
0x1800285ad  mov     r8, rbx
0x1800285b0  mov     [rsp+58h+var_38], rax
0x1800285b5  lea     r9, [rsp+58h+arg_0]
0x1800285ba  mov     rax, [rdi+910h]
0x1800285c1  mov     rdx, r12
0x1800285c4  mov     rcx, rsi
0x1800285c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285cc  mov     ebx, eax
0x1800285ce  test    eax, eax
0x1800285d0  jz      short loc_180028617
0x1800285d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285d9  lea     r14, WPP_GLOBAL_Control
0x1800285e0  cmp     rcx, r14
0x1800285e3  jz      loc_18002869D
0x1800285e9  mov     esi, 1
0x1800285ee  test    [rcx+44h], sil
0x1800285f2  jz      loc_18002869D
0x1800285f8  lea     edx, [rsi+2Bh]
0x1800285fb  mov     rcx, [rcx+38h]
0x1800285ff  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028606  mov     r9d, ebp
0x180028609  mov     dword ptr [rsp+58h+var_38], eax
0x18002860d  call    WPP_SF_dd
0x180028612  jmp     loc_18002869D
0x180028617  mov     rdx, [rsp+58h+arg_10]
0x18002861c  mov     esi, 1
0x180028621  test    rdx, rdx
0x180028624  jz      short loc_18002867C
0x180028626  mov     ecx, [rsp+58h+arg_0]
0x18002862a  test    ecx, ecx
0x18002862c  jz      short loc_18002867C
0x18002862e  call    ProfileMgrValidateUserProfile
0x180028633  mov     ebx, eax
0x180028635  test    eax, eax
0x180028637  jz      short loc_18002867C
0x180028639  mov     rcx, cs:WPP_GLOBAL_Control
0x180028640  lea     r14, WPP_GLOBAL_Control
0x180028647  cmp     rcx, r14
0x18002864a  jz      short loc_18002869D
0x18002864c  test    [rcx+44h], sil
0x180028650  jz      short loc_18002869D
0x180028652  lea     edx, [rsi+2Ch]
0x180028655  jmp     short loc_1800285FB
0x180028657  xor     ebx, ebx
0x180028659  xor     esi, esi
0x18002865b  cmp     rcx, rax
0x18002865e  jz      short loc_180028683
0x180028660  test    byte ptr [rcx+44h], 80h
0x180028664  jz      short loc_180028683
0x180028666  mov     rcx, [rcx+38h]
0x18002866a  lea     edx, [rbx+2Eh]
0x18002866d  mov     r9d, ebp
0x180028670  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028677  call    WPP_SF_d
0x18002867c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028683  mov     rax, [rsp+58h+arg_10]
0x180028688  mov     [r14], rax
0x18002868b  mov     eax, [rsp+58h+arg_0]
0x18002868f  mov     [r15], eax
0x180028692  lea     r14, WPP_GLOBAL_Control
0x180028699  test    esi, esi
0x18002869b  jz      short loc_1800286C1
0x18002869d  lea     rdx, [rdi+0B50h]
0x1800286a4  mov     r9d, 1DFh
0x1800286aa  lea     r8, aMsmqueryonexus; "MSMQueryOneXUserProfile"
0x1800286b1  mov     rcx, rdi
0x1800286b4  call    cs:__imp_AcquireWriteLock
0x1800286ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286c1  test    ebx, ebx
0x1800286c3  jz      short loc_1800286DE
0x1800286c5  mov     rdx, [rsp+58h+arg_10]
0x1800286ca  test    rdx, rdx
0x1800286cd  jz      short loc_1800286DE
0x1800286cf  mov     rcx, rdi
0x1800286d2  call    MSMFreeMemory
0x1800286d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286de  cmp     rcx, r14
0x1800286e1  jz      short loc_180028704
0x1800286e3  test    dword ptr [rcx+44h], 800h
0x1800286ea  jz      short loc_180028704
0x1800286ec  mov     rcx, [rcx+38h]
0x1800286f0  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800286f7  mov     edx, 2Fh ; '/'
0x1800286fc  mov     r9d, ebx
0x1800286ff  call    WPP_SF_D
0x180028704  mov     rbp, [rsp+58h+arg_18]
0x180028709  mov     eax, ebx
0x18002870b  mov     rbx, [rsp+58h+arg_8]
0x180028710  add     rsp, 30h
0x180028714  pop     r15
0x180028716  pop     r14
0x180028718  pop     r12
0x18002871a  pop     rdi
0x18002871b  pop     rsi
0x18002871c  retn
```
