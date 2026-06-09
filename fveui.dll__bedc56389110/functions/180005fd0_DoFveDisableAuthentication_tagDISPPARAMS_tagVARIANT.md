# DoFveDisableAuthentication(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005fd0`
- end: `0x180006240`
- name: `?DoFveDisableAuthentication@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x180005fd0`
- `0x18000ccb0`

## import_xrefs

- `FVEAPI!FveCloseVolume` at `0x180006207`
- `FVEAPI!FveCloseVolume` at `0x180006207`
- `FVEAPI!FveCommitChanges` at `0x1800061c3`
- `FVEAPI!FveCommitChanges` at `0x1800061c3`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180006188`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180006188`
- `FVEAPI!FveOpenVolumeW` at `0x180006136`
- `FVEAPI!FveOpenVolumeW` at `0x180006136`
- `FVEAPI!FveSetFipsAllowDisabled` at `0x1800060ee`
- `FVEAPI!FveSetFipsAllowDisabled` at `0x1800060ee`

## pseudocode

```c
__int64 __fastcall DoFveDisableAuthentication(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  unsigned int v5; // eax
  LONG v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 result; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+40h] [rbp-C0h]
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+60h] [rbp-A0h]
  __int128 v18; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  char v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+94h] [rbp-6Ch]

  v12 = -1;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  memset_0(v19, 0, 0x248u);
  rgvarg = a1->rgvarg;
  v13 = 0;
  v5 = _ConfirmSuspend((HWND)rgvarg->llVal);
  v6 = v5;
  if ( !v5 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v5);
  if ( v6 >= 0 )
  {
LABEL_6:
    v19[0] = 584;
    v13 = v19;
    v19[1] = 1;
    *(_QWORD *)&v15 = &v13;
    v19[3] = 9;
    v19[2] = 1;
    v20 = 1;
    v21 = 25;
    *(_QWORD *)&v14 = 0x100000038LL;
    *((_QWORD *)&v14 + 1) = 0x100010000LL;
    v7 = FveSetFipsAllowDisabled(1);
    v6 = v7;
    if ( !v7 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v7);
    if ( v6 >= 0 )
    {
LABEL_11:
      v8 = FveOpenVolumeW(a1->rgvarg[1].llVal, 1, &v12);
      v6 = v8;
      if ( !v8 )
        goto LABEL_16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v8);
      if ( v6 >= 0 )
      {
LABEL_16:
        v9 = FveAddAuthMethodInformation(v12, &v14, &v18);
        v6 = v9;
        if ( !v9 )
          goto LABEL_21;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v9);
        if ( v6 >= 0 )
        {
LABEL_21:
          v10 = FveCommitChanges(v12);
          v6 = v10;
          if ( v10 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v10);
        }
      }
    }
  }
  if ( v12 != -1 )
    FveCloseVolume();
  a2->vt = 19;
  result = 0;
  a2->lVal = v6;
  return result;
}

```

## disassembly

```asm
0x180005fd0  mov     [rsp-8+arg_10], rbx
0x180005fd5  mov     [rsp-8+arg_18], rsi
0x180005fda  push    rbp
0x180005fdb  push    rdi
0x180005fdc  push    r13
0x180005fde  push    r14
0x180005fe0  push    r15
0x180005fe2  lea     rbp, [rsp-1E0h]
0x180005fea  sub     rsp, 2E0h
0x180005ff1  mov     rax, cs:__security_cookie
0x180005ff8  xor     rax, rsp
0x180005ffb  mov     [rbp+200h+var_30], rax
0x180006002  xorps   xmm0, xmm0
0x180006005  mov     [rsp+300h+var_2E0], 0FFFFFFFFFFFFFFFFh
0x18000600e  mov     rdi, rdx
0x180006011  mov     rsi, rcx
0x180006014  xor     eax, eax
0x180006016  lea     rcx, [rbp+200h+var_280]; void *
0x18000601a  mov     r14d, 248h
0x180006020  mov     [rsp+300h+var_2A0], rax
0x180006025  mov     r8d, r14d; Size
0x180006028  xor     edx, edx; Val
0x18000602a  movups  [rsp+300h+var_2D0], xmm0
0x18000602f  movups  [rsp+300h+var_2C0], xmm0
0x180006034  movups  [rsp+300h+var_2B0], xmm0
0x180006039  movups  [rsp+300h+var_298], xmm0
0x18000603e  call    memset_0
0x180006043  mov     rcx, [rsi]
0x180006046  mov     [rsp+300h+var_2D8], 0
0x18000604f  mov     rcx, [rcx+8]; HWND
0x180006053  call    ?_ConfirmSuspend@@YAJPEAUHWND__@@@Z; _ConfirmSuspend(HWND__ *)
0x180006058  lea     r15, WPP_GLOBAL_Control
0x18000605f  mov     ebx, eax
0x180006061  lea     r13, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180006068  test    eax, eax
0x18000606a  jz      short loc_18000609A
0x18000606c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006073  cmp     rcx, r15
0x180006076  jz      short loc_180006092
0x180006078  test    byte ptr [rcx+1Ch], 40h
0x18000607c  jz      short loc_180006092
0x18000607e  mov     rcx, [rcx+10h]
0x180006082  mov     edx, 11h
0x180006087  mov     r9d, eax
0x18000608a  mov     r8, r13
0x18000608d  call    WPP_SF_d
0x180006092  test    ebx, ebx
0x180006094  js      loc_1800061F7
0x18000609a  lea     rax, [rbp+200h+var_280]
0x18000609e  mov     [rbp+200h+var_280], r14d
0x1800060a2  mov     r14d, 1
0x1800060a8  mov     [rsp+300h+var_2D8], rax
0x1800060ad  lea     rax, [rsp+300h+var_2D8]
0x1800060b2  mov     [rbp+200h+var_27C], r14d
0x1800060b6  mov     ecx, r14d
0x1800060b9  mov     qword ptr [rsp+300h+var_2C0], rax
0x1800060be  mov     [rbp+200h+var_274], 9
0x1800060c5  mov     [rbp+200h+var_278], r14d
0x1800060c9  mov     [rbp+200h+var_270], r14b
0x1800060cd  mov     [rbp+200h+var_26C], 19h
0x1800060d4  mov     dword ptr [rsp+300h+var_2D0], 38h ; '8'
0x1800060dc  mov     dword ptr [rsp+300h+var_2D0+4], r14d
0x1800060e1  mov     dword ptr [rsp+300h+var_2D0+8], 10000h
0x1800060e9  mov     dword ptr [rsp+300h+var_2D0+0Ch], r14d
0x1800060ee  call    cs:__imp_FveSetFipsAllowDisabled
0x1800060f4  mov     ebx, eax
0x1800060f6  test    eax, eax
0x1800060f8  jz      short loc_180006127
0x1800060fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006101  cmp     rcx, r15
0x180006104  jz      short loc_18000611F
0x180006106  test    byte ptr [rcx+1Ch], 40h
0x18000610a  jz      short loc_18000611F
0x18000610c  mov     rcx, [rcx+10h]
0x180006110  lea     edx, [r14+11h]
0x180006114  mov     r9d, eax
0x180006117  mov     r8, r13
0x18000611a  call    WPP_SF_d
0x18000611f  test    ebx, ebx
0x180006121  js      loc_1800061F7
0x180006127  mov     rcx, [rsi]
0x18000612a  lea     r8, [rsp+300h+var_2E0]
0x18000612f  mov     edx, r14d
0x180006132  mov     rcx, [rcx+20h]
0x180006136  call    cs:__imp_FveOpenVolumeW
0x18000613c  mov     ebx, eax
0x18000613e  test    eax, eax
0x180006140  jz      short loc_180006174
0x180006142  mov     rcx, cs:WPP_GLOBAL_Control
0x180006149  mov     esi, 13h
0x18000614e  cmp     rcx, r15
0x180006151  jz      short loc_18000616A
0x180006153  test    byte ptr [rcx+1Ch], 40h
0x180006157  jz      short loc_18000616A
0x180006159  mov     rcx, [rcx+10h]
0x18000615d  mov     edx, esi
0x18000615f  mov     r9d, eax
0x180006162  mov     r8, r13
0x180006165  call    WPP_SF_d
0x18000616a  test    ebx, ebx
0x18000616c  js      loc_1800061FC
0x180006172  jmp     short loc_180006179
0x180006174  mov     esi, 13h
0x180006179  mov     rcx, [rsp+300h+var_2E0]
0x18000617e  lea     r8, [rsp+300h+var_298]
0x180006183  lea     rdx, [rsp+300h+var_2D0]
0x180006188  call    cs:__imp_FveAddAuthMethodInformation
0x18000618e  mov     ebx, eax
0x180006190  test    eax, eax
0x180006192  jz      short loc_1800061BE
0x180006194  mov     rcx, cs:WPP_GLOBAL_Control
0x18000619b  cmp     rcx, r15
0x18000619e  jz      short loc_1800061BA
0x1800061a0  test    byte ptr [rcx+1Ch], 40h
0x1800061a4  jz      short loc_1800061BA
0x1800061a6  mov     rcx, [rcx+10h]
0x1800061aa  mov     edx, 14h
0x1800061af  mov     r9d, eax
0x1800061b2  mov     r8, r13
0x1800061b5  call    WPP_SF_d
0x1800061ba  test    ebx, ebx
0x1800061bc  js      short loc_1800061FC
0x1800061be  mov     rcx, [rsp+300h+var_2E0]
0x1800061c3  call    cs:__imp_FveCommitChanges
0x1800061c9  mov     ebx, eax
0x1800061cb  test    eax, eax
0x1800061cd  jz      short loc_1800061FC
0x1800061cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061d6  cmp     rcx, r15
0x1800061d9  jz      short loc_1800061FC
0x1800061db  test    byte ptr [rcx+1Ch], 40h
0x1800061df  jz      short loc_1800061FC
0x1800061e1  mov     rcx, [rcx+10h]
0x1800061e5  mov     edx, 15h
0x1800061ea  mov     r9d, eax
0x1800061ed  mov     r8, r13
0x1800061f0  call    WPP_SF_d
0x1800061f5  jmp     short loc_1800061FC
0x1800061f7  mov     esi, 13h
0x1800061fc  mov     rcx, [rsp+300h+var_2E0]
0x180006201  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006205  jz      short loc_18000620D
0x180006207  call    cs:__imp_FveCloseVolume
0x18000620d  mov     [rdi], si
0x180006210  xor     eax, eax
0x180006212  mov     [rdi+8], ebx
0x180006215  mov     rcx, [rbp+200h+var_30]
0x18000621c  xor     rcx, rsp; StackCookie
0x18000621f  call    __security_check_cookie
0x180006224  lea     r11, [rsp+300h+var_20]
0x18000622c  mov     rbx, [r11+40h]
0x180006230  mov     rsi, [r11+48h]
0x180006234  mov     rsp, r11
0x180006237  pop     r15
0x180006239  pop     r14
0x18000623b  pop     r13
0x18000623d  pop     rdi
0x18000623e  pop     rbp
0x18000623f  retn
```
