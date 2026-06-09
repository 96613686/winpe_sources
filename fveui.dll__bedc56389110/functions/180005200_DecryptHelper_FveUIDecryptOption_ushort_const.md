# DecryptHelper(FveUIDecryptOption,ushort const *)

- ea: `0x180005200`
- end: `0x1800057e1`
- name: `?DecryptHelper@@YAJW4FveUIDecryptOption@@PEBG@Z`
- size: `1505`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180005cc0`
- `0x180007210`

## callees

- `0x18000116c`
- `0x180001248`
- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x180005200`
- `0x18000b1b0`
- `0x18000e354`
- `0x18000e37c`

## import_xrefs

- `FVEAPI!FveFindFirstVolume` at `0x180005423`
- `FVEAPI!FveFindFirstVolume` at `0x180005423`
- `FVEAPI!FveFindNextVolume` at `0x180005549`
- `FVEAPI!FveFindNextVolume` at `0x180005549`
- `FVEAPI!FveCloseVolume` at `0x180005438`
- `FVEAPI!FveCloseVolume` at `0x180005672`
- `FVEAPI!FveCloseVolume` at `0x180005711`
- `FVEAPI!FveCloseVolume` at `0x18000572f`
- `FVEAPI!FveCloseVolume` at `0x180005438`
- `FVEAPI!FveCloseVolume` at `0x180005672`
- `FVEAPI!FveCloseVolume` at `0x180005711`
- `FVEAPI!FveCloseVolume` at `0x18000572f`
- `FVEAPI!FveSetFipsAllowDisabled` at `0x1800052f7`
- `FVEAPI!FveSetFipsAllowDisabled` at `0x1800052f7`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18000545e`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18000545e`
- `FVEAPI!FveOpenVolumeExW` at `0x180005359`
- `FVEAPI!FveOpenVolumeExW` at `0x180005359`
- `FVEAPI!FveGetStatus` at `0x1800053b8`
- `FVEAPI!FveGetStatus` at `0x180005498`
- `FVEAPI!FveGetStatus` at `0x1800053b8`
- `FVEAPI!FveGetStatus` at `0x180005498`
- `FVEAPI!FveIsBoundDataVolumeToOSVolume` at `0x1800055cf`
- `FVEAPI!FveIsBoundDataVolumeToOSVolume` at `0x1800055cf`
- `FVEAPI!FveUnbindAllDataVolumeFromOSVolume` at `0x180005682`
- `FVEAPI!FveUnbindAllDataVolumeFromOSVolume` at `0x180005682`
- `FVEAPI!FveRevertVolume` at `0x1800056c8`
- `FVEAPI!FveRevertVolume` at `0x1800056c8`
- `FVEAPI!FveCloseHandle` at `0x18000574d`
- `FVEAPI!FveCloseHandle` at `0x18000574d`

## pseudocode

```c
__int64 __fastcall DecryptHelper(int a1, __int64 a2)
{
  int v4; // edx
  int v5; // r8d
  int v6; // esi
  PVOID *v7; // rcx
  unsigned int v8; // eax
  int v9; // ebx
  PVOID *v10; // rcx
  unsigned int v11; // esi
  unsigned int v12; // eax
  unsigned int Status; // eax
  int i; // eax
  int IsBoundDataVolumeToOSVolume; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // r9
  PVOID *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  void *v31; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+74h] [rbp-8Ch]
  _BYTE v39[4]; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+7Ch] [rbp-84h]
  char v41; // [rsp+A8h] [rbp-58h]

  v35 = 0;
  v34 = -1;
  memset_0(&v37, 0, 0x90u);
  v30 = 0;
  v36 = 0;
  v6 = 0;
  v33 = -1;
  v31 = (void *)-1LL;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    {
      WPP_SF_LS((unsigned int)v7[2], v4, v5, a1, a2);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( a1 == 1 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(v7[2], 68, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
    v6 = 4;
  }
  v8 = FveSetFipsAllowDisabled(1);
  v9 = v8;
  if ( v8 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v8);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
      goto LABEL_79;
  }
  v11 = v6 | 8;
  v12 = FveOpenVolumeExW(a2, 0, 1, 0xFFFFFFFFLL, v11, &v33, v30);
  v9 = v12;
  if ( v12 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v12);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
      goto LABEL_79;
  }
  v37 = 144;
  v38 = 10;
  Status = FveGetStatus(v33, &v37);
  v9 = Status;
  if ( Status )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, Status);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
      goto LABEL_79;
  }
  if ( (v40 & 0x4000) == 0 )
  {
LABEL_73:
    v25 = FveRevertVolume(v33);
    v9 = v25;
    if ( v25 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_79;
      v21 = 79;
      v22 = v25;
LABEL_77:
      WPP_SF_d(v10[2], v21, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v22);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_79;
  }
  v35 = 0xFFFFFFFF00000001uLL;
  for ( i = FveFindFirstVolume(&v34, &v35); ; i = FveFindNextVolume(v34, &v35) )
  {
    v9 = i;
    if ( i < 0 )
      break;
    if ( v31 != (void *)-1LL )
    {
      ((void (*)(void))FveCloseVolume)();
      v31 = (void *)-1LL;
    }
    if ( (int)FveOpenVolumeByHandle(v34, 0, 0, 0xFFFFFFFFLL, v11, &v31) < 0 )
      continue;
    memset_0(v39, 0, 0x88u);
    v37 = 144;
    v38 = 10;
    if ( (int)FveGetStatus(v31, &v37) < 0 || (v40 & 0x4000) != 0 || (v40 & 1) == 0 )
      continue;
    v30 = 0;
    if ( a1 == 1 && (v41 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
      v30 = 1;
LABEL_41:
      IsBoundDataVolumeToOSVolume = RevertVolumeHelper(v31, v11);
      if ( IsBoundDataVolumeToOSVolume < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v17 = 76;
LABEL_45:
          WPP_SF_d(
            v16[2],
            v17,
            &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
            (unsigned int)IsBoundDataVolumeToOSVolume);
          continue;
        }
      }
      continue;
    }
    IsBoundDataVolumeToOSVolume = FveIsBoundDataVolumeToOSVolume(v31, &v30, &v36);
    if ( IsBoundDataVolumeToOSVolume >= 0 )
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v30);
        v23 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v30 )
      {
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
          WPP_SF_(v23[2], 75, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
        continue;
      }
      goto LABEL_41;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 73;
      goto LABEL_45;
    }
  }
  if ( i == -2147024878 )
  {
    if ( v31 != (void *)-1LL )
    {
      ((void (*)(void))FveCloseVolume)();
      v31 = (void *)-1LL;
    }
    v24 = FveUnbindAllDataVolumeFromOSVolume(v33);
    v9 = v24;
    if ( v24 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v24);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 < 0 )
        goto LABEL_79;
    }
    goto LABEL_73;
  }
  if ( (unsigned int)dword_18003D518 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003D518) )
  {
    v32 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&byte_18003723F,
      v19,
      v20,
      (__int64)&v32);
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v21 = 77;
    v22 = (unsigned int)v9;
    goto LABEL_77;
  }
LABEL_79:
  if ( v33 != -1 )
  {
    FveCloseVolume(v33);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v33 = -1;
  }
  if ( v31 != (void *)-1LL )
  {
    FveCloseVolume(v31);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v31 = (void *)-1LL;
  }
  if ( v34 != -1 )
  {
    FveCloseHandle(v34);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v34 = -1;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 80, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, (unsigned int)v9);
  if ( (unsigned int)dword_18003D518 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003D518) )
  {
    v32 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v26,
      (unsigned int)byte_1800371F1,
      v27,
      v28,
      (__int64)&v32);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005200  mov     [rsp-8+arg_10], rbx
0x180005205  mov     [rsp-8+arg_18], rsi
0x18000520a  push    rbp
0x18000520b  push    rdi
0x18000520c  push    r12
0x18000520e  push    r13
0x180005210  push    r14
0x180005212  lea     rbp, [rsp-10h]
0x180005217  sub     rsp, 110h
0x18000521e  mov     rax, cs:__security_cookie
0x180005225  xor     rax, rsp
0x180005228  mov     [rbp+30h+var_30], rax
0x18000522c  mov     rdi, rdx
0x18000522f  mov     [rsp+130h+var_D8], 0
0x180005238  mov     r14d, ecx
0x18000523b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000523f  xor     edx, edx; Val
0x180005241  mov     [rsp+130h+var_E0], r12
0x180005246  lea     rcx, [rsp+130h+var_C0]; void *
0x18000524b  mov     r8d, 90h; Size
0x180005251  call    memset_0
0x180005256  xorps   xmm0, xmm0
0x180005259  mov     [rsp+130h+var_100], 0
0x180005261  movups  [rsp+130h+var_D0], xmm0
0x180005266  xor     esi, esi
0x180005268  mov     [rsp+130h+var_E8], r12
0x18000526d  mov     [rsp+130h+var_F8], r12
0x180005272  mov     rcx, cs:WPP_GLOBAL_Control
0x180005279  lea     r13, WPP_GLOBAL_Control
0x180005280  cmp     rcx, r13
0x180005283  jz      short loc_1800052C8
0x180005285  test    byte ptr [rcx+1Ch], 20h
0x180005289  jz      short loc_1800052A5
0x18000528b  mov     rcx, [rcx+10h]
0x18000528f  lea     edx, [rsi+42h]
0x180005292  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180005299  call    WPP_SF_
0x18000529e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052a5  cmp     rcx, r13
0x1800052a8  jz      short loc_1800052C8
0x1800052aa  test    byte ptr [rcx+1Ch], 20h
0x1800052ae  jz      short loc_1800052C8
0x1800052b0  mov     rcx, [rcx+10h]
0x1800052b4  mov     r9d, r14d
0x1800052b7  mov     [rsp+130h+var_110], rdi
0x1800052bc  call    WPP_SF_LS
0x1800052c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052c8  cmp     r14d, 1
0x1800052cc  jnz     short loc_1800052F2
0x1800052ce  cmp     rcx, r13
0x1800052d1  jz      short loc_1800052ED
0x1800052d3  test    byte ptr [rcx+1Ch], 8
0x1800052d7  jz      short loc_1800052ED
0x1800052d9  mov     rcx, [rcx+10h]
0x1800052dd  lea     edx, [r14+43h]
0x1800052e1  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800052e8  call    WPP_SF_
0x1800052ed  mov     esi, 4
0x1800052f2  mov     ecx, 1
0x1800052f7  call    cs:__imp_FveSetFipsAllowDisabled
0x1800052fd  mov     ebx, eax
0x1800052ff  test    eax, eax
0x180005301  jz      short loc_18000533C
0x180005303  mov     rcx, cs:WPP_GLOBAL_Control
0x18000530a  cmp     rcx, r13
0x18000530d  jz      short loc_180005334
0x18000530f  test    byte ptr [rcx+1Ch], 40h
0x180005313  jz      short loc_180005334
0x180005315  mov     rcx, [rcx+10h]
0x180005319  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180005320  mov     edx, 45h ; 'E'
0x180005325  mov     r9d, eax
0x180005328  call    WPP_SF_d
0x18000532d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005334  test    ebx, ebx
0x180005336  js      loc_180005705
0x18000533c  xor     edx, edx
0x18000533e  lea     rax, [rsp+130h+var_E8]
0x180005343  mov     [rsp+130h+var_108], rax
0x180005348  or      esi, 8
0x18000534b  mov     r9d, r12d
0x18000534e  mov     dword ptr [rsp+130h+var_110], esi
0x180005352  mov     rcx, rdi
0x180005355  lea     r8d, [rdx+1]
0x180005359  call    cs:__imp_FveOpenVolumeExW
0x18000535f  mov     ebx, eax
0x180005361  test    eax, eax
0x180005363  jz      short loc_18000539E
0x180005365  mov     rcx, cs:WPP_GLOBAL_Control
0x18000536c  cmp     rcx, r13
0x18000536f  jz      short loc_180005396
0x180005371  test    byte ptr [rcx+1Ch], 40h
0x180005375  jz      short loc_180005396
0x180005377  mov     rcx, [rcx+10h]
0x18000537b  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180005382  mov     edx, 46h ; 'F'
0x180005387  mov     r9d, eax
0x18000538a  call    WPP_SF_d
0x18000538f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005396  test    ebx, ebx
0x180005398  js      loc_180005705
0x18000539e  mov     rcx, [rsp+130h+var_E8]
0x1800053a3  lea     rdx, [rsp+130h+var_C0]
0x1800053a8  mov     [rsp+130h+var_C0], 90h
0x1800053b0  mov     [rsp+130h+var_BC], 0Ah
0x1800053b8  call    cs:__imp_FveGetStatus
0x1800053be  mov     ebx, eax
0x1800053c0  test    eax, eax
0x1800053c2  jz      short loc_1800053FD
0x1800053c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053cb  cmp     rcx, r13
0x1800053ce  jz      short loc_1800053F5
0x1800053d0  test    byte ptr [rcx+1Ch], 40h
0x1800053d4  jz      short loc_1800053F5
0x1800053d6  mov     rcx, [rcx+10h]
0x1800053da  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800053e1  mov     edx, 47h ; 'G'
0x1800053e6  mov     r9d, eax
0x1800053e9  call    WPP_SF_d
0x1800053ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053f5  test    ebx, ebx
0x1800053f7  js      loc_180005705
0x1800053fd  test    [rsp+130h+var_B4], 4000h
0x180005405  jz      loc_1800056C3
0x18000540b  mov     edi, 1
0x180005410  mov     dword ptr [rsp+130h+var_D8+4], r12d
0x180005415  lea     rdx, [rsp+130h+var_D8]
0x18000541a  mov     dword ptr [rsp+130h+var_D8], edi
0x18000541e  lea     rcx, [rsp+130h+var_E0]
0x180005423  call    cs:__imp_FveFindFirstVolume
0x180005429  jmp     loc_18000554F
0x18000542e  mov     rcx, [rsp+130h+var_F8]
0x180005433  cmp     rcx, r12
0x180005436  jz      short loc_180005443
0x180005438  call    cs:__imp_FveCloseVolume
0x18000543e  mov     [rsp+130h+var_F8], r12
0x180005443  mov     rcx, [rsp+130h+var_E0]
0x180005448  lea     rax, [rsp+130h+var_F8]
0x18000544d  mov     [rsp+130h+var_108], rax
0x180005452  mov     r9d, r12d
0x180005455  xor     r8d, r8d
0x180005458  mov     dword ptr [rsp+130h+var_110], esi
0x18000545c  xor     edx, edx
0x18000545e  call    cs:__imp_FveOpenVolumeByHandle
0x180005464  test    eax, eax
0x180005466  js      loc_18000553F
0x18000546c  xor     edx, edx; Val
0x18000546e  lea     rcx, [rsp+130h+var_B8]; void *
0x180005473  mov     r8d, 88h; Size
0x180005479  call    memset_0
0x18000547e  mov     rcx, [rsp+130h+var_F8]
0x180005483  lea     rdx, [rsp+130h+var_C0]
0x180005488  mov     [rsp+130h+var_C0], 90h
0x180005490  mov     [rsp+130h+var_BC], 0Ah
0x180005498  call    cs:__imp_FveGetStatus
0x18000549e  test    eax, eax
0x1800054a0  js      loc_18000553F
0x1800054a6  test    [rsp+130h+var_B4], 4000h
0x1800054ae  jnz     loc_18000553F
0x1800054b4  test    byte ptr [rsp+130h+var_B4], dil
0x1800054b9  jz      loc_18000553F
0x1800054bf  mov     [rsp+130h+var_100], 0
0x1800054c7  cmp     r14d, edi
0x1800054ca  jnz     loc_1800055C0
0x1800054d0  test    [rbp+30h+var_88], 8
0x1800054d4  jz      loc_1800055C0
0x1800054da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054e1  cmp     rcx, r13
0x1800054e4  jz      short loc_180005501
0x1800054e6  test    byte ptr [rcx+1Ch], 8
0x1800054ea  jz      short loc_180005501
0x1800054ec  mov     rcx, [rcx+10h]
0x1800054f0  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800054f7  mov     edx, 48h ; 'H'
0x1800054fc  call    WPP_SF_
0x180005501  mov     [rsp+130h+var_100], edi
0x180005505  mov     rcx, [rsp+130h+var_F8]; void *
0x18000550a  mov     edx, esi; unsigned int
0x18000550c  call    ?RevertVolumeHelper@@YAJPEAXK@Z; RevertVolumeHelper(void *,ulong)
0x180005511  test    eax, eax
0x180005513  jns     short loc_18000553F
0x180005515  mov     rcx, cs:WPP_GLOBAL_Control
0x18000551c  cmp     rcx, r13
0x18000551f  jz      short loc_18000553F
0x180005521  test    byte ptr [rcx+1Ch], 2
0x180005525  jz      short loc_18000553F
0x180005527  mov     edx, 4Ch ; 'L'
0x18000552c  mov     rcx, [rcx+10h]
0x180005530  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180005537  mov     r9d, eax
0x18000553a  call    WPP_SF_d
0x18000553f  mov     rcx, [rsp+130h+var_E0]
0x180005544  lea     rdx, [rsp+130h+var_D8]
0x180005549  call    cs:__imp_FveFindNextVolume
0x18000554f  mov     ebx, eax
0x180005551  test    eax, eax
0x180005553  jns     loc_18000542E
0x180005559  cmp     eax, 80070012h
0x18000555e  jz      loc_180005668
0x180005564  mov     eax, cs:dword_18003D518
0x18000556a  cmp     eax, 4
0x18000556d  jbe     short loc_180005599
0x18000556f  lea     rcx, dword_18003D518
0x180005576  call    _tlgKeywordOn
0x18000557b  test    al, al
0x18000557d  jz      short loc_180005599
0x18000557f  lea     rax, [rsp+130h+var_F0]
0x180005584  mov     [rsp+130h+var_F0], ebx
0x180005588  lea     rdx, byte_18003723F
0x18000558f  mov     [rsp+130h+var_110], rax
0x180005594  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180005599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055a0  cmp     rcx, r13
0x1800055a3  jz      loc_180005705
0x1800055a9  test    byte ptr [rcx+1Ch], 40h
0x1800055ad  jz      loc_180005705
0x1800055b3  mov     edx, 4Dh ; 'M'
0x1800055b8  mov     r9d, ebx
0x1800055bb  jmp     loc_1800056EE
0x1800055c0  mov     rcx, [rsp+130h+var_F8]
0x1800055c5  lea     r8, [rsp+130h+var_D0]
0x1800055ca  lea     rdx, [rsp+130h+var_100]
0x1800055cf  call    cs:__imp_FveIsBoundDataVolumeToOSVolume
0x1800055d5  test    eax, eax
0x1800055d7  jns     short loc_1800055FD
0x1800055d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e0  cmp     rcx, r13
0x1800055e3  jz      loc_18000553F
0x1800055e9  test    byte ptr [rcx+1Ch], 2
0x1800055ed  jz      loc_18000553F
0x1800055f3  mov     edx, 49h ; 'I'
0x1800055f8  jmp     loc_18000552C
0x1800055fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005604  cmp     rcx, r13
0x180005607  jz      short loc_180005630
0x180005609  test    byte ptr [rcx+1Ch], 8
0x18000560d  jz      short loc_180005630
0x18000560f  mov     r9d, [rsp+130h+var_100]
0x180005614  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x18000561b  mov     rcx, [rcx+10h]
0x18000561f  mov     edx, 4Ah ; 'J'
0x180005624  call    WPP_SF_d
0x180005629  mov     rcx, cs:WPP_GLOBAL_Control
0x180005630  cmp     [rsp+130h+var_100], 0
0x180005635  jnz     loc_180005505
0x18000563b  cmp     rcx, r13
0x18000563e  jz      loc_18000553F
0x180005644  test    byte ptr [rcx+1Ch], 8
0x180005648  jz      loc_18000553F
0x18000564e  mov     rcx, [rcx+10h]
0x180005652  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180005659  mov     edx, 4Bh ; 'K'
0x18000565e  call    WPP_SF_
0x180005663  jmp     loc_18000553F
0x180005668  mov     rcx, [rsp+130h+var_F8]
0x18000566d  cmp     rcx, r12
0x180005670  jz      short loc_18000567D
0x180005672  call    cs:__imp_FveCloseVolume
0x180005678  mov     [rsp+130h+var_F8], r12
0x18000567d  mov     rcx, [rsp+130h+var_E8]
0x180005682  call    cs:__imp_FveUnbindAllDataVolumeFromOSVolume
0x180005688  mov     ebx, eax
0x18000568a  test    eax, eax
0x18000568c  jz      short loc_1800056C3
0x18000568e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005695  cmp     rcx, r13
0x180005698  jz      short loc_1800056BF
0x18000569a  test    byte ptr [rcx+1Ch], 40h
0x18000569e  jz      short loc_1800056BF
0x1800056a0  mov     rcx, [rcx+10h]
0x1800056a4  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800056ab  mov     edx, 4Eh ; 'N'
0x1800056b0  mov     r9d, eax
0x1800056b3  call    WPP_SF_d
0x1800056b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056bf  test    ebx, ebx
0x1800056c1  js      short loc_180005705
0x1800056c3  mov     rcx, [rsp+130h+var_E8]
0x1800056c8  call    cs:__imp_FveRevertVolume
0x1800056ce  mov     ebx, eax
0x1800056d0  test    eax, eax
0x1800056d2  jz      short loc_1800056FE
0x1800056d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056db  cmp     rcx, r13
0x1800056de  jz      short loc_180005705
0x1800056e0  test    byte ptr [rcx+1Ch], 40h
0x1800056e4  jz      short loc_180005705
0x1800056e6  mov     edx, 4Fh ; 'O'
0x1800056eb  mov     r9d, eax
0x1800056ee  mov     rcx, [rcx+10h]
0x1800056f2  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x1800056f9  call    WPP_SF_d
0x1800056fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005705  cmp     [rsp+130h+var_E8], r12
0x18000570a  jz      short loc_180005723
0x18000570c  mov     rcx, [rsp+130h+var_E8]
0x180005711  call    cs:__imp_FveCloseVolume
0x180005717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000571e  mov     [rsp+130h+var_E8], r12
0x180005723  cmp     [rsp+130h+var_F8], r12
  ... truncated ...
```
