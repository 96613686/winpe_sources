# _UnlockWithStringBasedProtector

- ea: `0x18000d4c0`
- end: `0x18000d666`
- name: `_UnlockWithStringBasedProtector`
- size: `422`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007da0`
- `0x180007de0`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000d4c0`

## import_xrefs

- `FVEAPI!FveAuthElementFromRecoveryPasswordW` at `0x18000d566`
- `FVEAPI!FveAuthElementFromRecoveryPasswordW` at `0x18000d566`
- `FVEAPI!FveAuthElementFromPassPhraseW` at `0x18000d58a`
- `FVEAPI!FveAuthElementFromPassPhraseW` at `0x18000d58a`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x18000d604`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x18000d604`
- `FVEAPI!FveCloseVolume` at `0x18000d625`
- `FVEAPI!FveCloseVolume` at `0x18000d625`
- `FVEAPI!FveOpenVolumeW` at `0x18000d5eb`
- `FVEAPI!FveOpenVolumeW` at `0x18000d5eb`

## pseudocode

```c
__int64 __fastcall UnlockWithStringBasedProtector(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v7; // rsi
  __int64 v9; // rcx
  int v10; // eax
  int v11; // ebx
  _BYTE *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v15; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  _DWORD v20[148]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v7 = 584;
  memset_0(v20, 0, 0x248u);
  v9 = -1;
  v19 = 0;
  v14 = -1;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( a1 && a2 )
  {
    v20[1] = 1;
    if ( a4 == 0x80000 )
    {
      v20[0] = 32;
      v10 = FveAuthElementFromRecoveryPasswordW(a2, v20);
    }
    else
    {
      if ( a4 != 0x800000 )
      {
        v11 = -2147024809;
        goto LABEL_15;
      }
      v20[0] = 578;
      v10 = FveAuthElementFromPassPhraseW(a2, v20);
    }
    v11 = v10;
    if ( v10 >= 0 )
    {
      v19 = 0;
      v15 = v20;
      *(_QWORD *)&v16 = 0x100000038LL;
      v17 = (unsigned __int64)&v15;
      *((_QWORD *)&v16 + 1) = a4 | 0x100000000LL;
      v18 = 0;
      v11 = FveOpenVolumeW(a1, 0, &v14);
      if ( v11 >= 0 )
        v11 = FveUnlockVolumeWithAccessMode(v14, &v16, a3);
    }
    v9 = v14;
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v9 != -1 )
  {
    FveCloseVolume();
    v14 = -1;
  }
LABEL_15:
  v12 = v20;
  do
  {
    *v12++ = 0;
    --v7;
  }
  while ( v7 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d4c0  push    rbp
0x18000d4c2  push    rbx
0x18000d4c3  push    rsi
0x18000d4c4  push    rdi
0x18000d4c5  push    r14
0x18000d4c7  push    r15
0x18000d4c9  lea     rbp, [rsp-1D8h]
0x18000d4d1  sub     rsp, 2D8h
0x18000d4d8  mov     rax, cs:__security_cookie
0x18000d4df  xor     rax, rsp
0x18000d4e2  mov     [rbp+200h+var_40], rax
0x18000d4e9  mov     r15, r8
0x18000d4ec  mov     [rsp+300h+var_2D8], 0
0x18000d4f5  mov     rbx, rdx
0x18000d4f8  mov     r14, rcx
0x18000d4fb  mov     esi, 248h
0x18000d500  lea     rcx, [rsp+300h+var_290]; void *
0x18000d505  mov     r8d, esi; Size
0x18000d508  xor     edx, edx; Val
0x18000d50a  mov     edi, r9d
0x18000d50d  call    memset_0
0x18000d512  xorps   xmm0, xmm0
0x18000d515  xor     eax, eax
0x18000d517  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d51b  mov     [rsp+300h+var_2A0], rax
0x18000d520  mov     [rsp+300h+var_2E0], rcx
0x18000d525  movups  [rsp+300h+var_2D0], xmm0
0x18000d52a  movups  [rsp+300h+var_2C0], xmm0
0x18000d52f  movups  [rsp+300h+var_2B0], xmm0
0x18000d534  test    r14, r14
0x18000d537  jz      loc_18000D61A
0x18000d53d  test    rbx, rbx
0x18000d540  jz      loc_18000D61A
0x18000d546  mov     [rsp+300h+var_28C], 1
0x18000d54e  cmp     edi, 80000h
0x18000d554  jnz     short loc_18000D56E
0x18000d556  lea     rdx, [rsp+300h+var_290]
0x18000d55b  mov     [rsp+300h+var_290], 20h ; ' '
0x18000d563  mov     rcx, rbx
0x18000d566  call    cs:__imp_FveAuthElementFromRecoveryPasswordW
0x18000d56c  jmp     short loc_18000D590
0x18000d56e  cmp     edi, 800000h
0x18000d574  jnz     loc_18000D613
0x18000d57a  lea     rdx, [rsp+300h+var_290]
0x18000d57f  mov     [rsp+300h+var_290], 242h
0x18000d587  mov     rcx, rbx
0x18000d58a  call    cs:__imp_FveAuthElementFromPassPhraseW
0x18000d590  mov     ebx, eax
0x18000d592  test    eax, eax
0x18000d594  js      short loc_18000D60C
0x18000d596  lea     rax, [rsp+300h+var_290]
0x18000d59b  mov     [rsp+300h+var_2A0], 0
0x18000d5a4  mov     [rsp+300h+var_2D8], rax
0x18000d5a9  lea     r8, [rsp+300h+var_2E0]
0x18000d5ae  lea     rax, [rsp+300h+var_2D8]
0x18000d5b3  mov     dword ptr [rsp+300h+var_2D0], 38h ; '8'
0x18000d5bb  xorps   xmm0, xmm0
0x18000d5be  mov     qword ptr [rsp+300h+var_2C0], rax
0x18000d5c3  xor     edx, edx
0x18000d5c5  mov     dword ptr [rsp+300h+var_2D0+4], 1
0x18000d5cd  mov     rcx, r14
0x18000d5d0  mov     dword ptr [rsp+300h+var_2D0+8], edi
0x18000d5d4  movdqu  [rsp+300h+var_2B0], xmm0
0x18000d5da  mov     dword ptr [rsp+300h+var_2D0+0Ch], 1
0x18000d5e2  mov     qword ptr [rsp+300h+var_2C0+8], 0
0x18000d5eb  call    cs:__imp_FveOpenVolumeW
0x18000d5f1  mov     ebx, eax
0x18000d5f3  test    eax, eax
0x18000d5f5  js      short loc_18000D60C
0x18000d5f7  mov     rcx, [rsp+300h+var_2E0]
0x18000d5fc  lea     rdx, [rsp+300h+var_2D0]
0x18000d601  mov     r8, r15
0x18000d604  call    cs:__imp_FveUnlockVolumeWithAccessMode
0x18000d60a  mov     ebx, eax
0x18000d60c  mov     rcx, [rsp+300h+var_2E0]
0x18000d611  jmp     short loc_18000D61F
0x18000d613  mov     ebx, 80070057h
0x18000d618  jmp     short loc_18000D634
0x18000d61a  mov     ebx, 80004003h
0x18000d61f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d623  jz      short loc_18000D634
0x18000d625  call    cs:__imp_FveCloseVolume
0x18000d62b  mov     [rsp+300h+var_2E0], 0FFFFFFFFFFFFFFFFh
0x18000d634  lea     rax, [rsp+300h+var_290]
0x18000d639  mov     byte ptr [rax], 0
0x18000d63c  inc     rax
0x18000d63f  sub     rsi, 1
0x18000d643  jnz     short loc_18000D639
0x18000d645  mov     eax, ebx
0x18000d647  mov     rcx, [rbp+200h+var_40]
0x18000d64e  xor     rcx, rsp; StackCookie
0x18000d651  call    __security_check_cookie
0x18000d656  add     rsp, 2D8h
0x18000d65d  pop     r15
0x18000d65f  pop     r14
0x18000d661  pop     rdi
0x18000d662  pop     rsi
0x18000d663  pop     rbx
0x18000d664  pop     rbp
0x18000d665  retn
```
