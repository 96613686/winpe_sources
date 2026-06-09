# ReadUserData

- ea: `0x180002954`
- end: `0x180002ec2`
- name: `ReadUserData`
- size: `1390`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180002040`
- `0x180003200`
- `0x180016ee0`

## callees

- `0x180002954`
- `0x180003bd0`
- `0x180006a20`
- `0x18000e120`
- `0x1800124d0`
- `0x180016630`
- `0x180023d74`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002cbd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ccb`

## pseudocode

```c
__int64 __fastcall ReadUserData(char *Src, size_t Size, _QWORD *a3)
{
  void *v3; // r13
  SIZE_T v4; // rsi
  char *v5; // rbp
  _OWORD *v7; // r12
  _DWORD *v9; // rax
  _OWORD *v10; // rdi
  DWORD LastError; // eax
  DWORD v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r14
  _OWORD *v17; // rax
  _OWORD *v18; // rcx
  __int64 v19; // rdx
  __int128 v20; // xmm1
  unsigned int v21; // edx
  char *v22; // rax
  unsigned int v23; // eax
  HLOCAL v24; // rax
  size_t v25; // r15
  _OWORD *v26; // rax
  __int128 v27; // xmm1
  _OWORD *v28; // rax
  __int128 v29; // xmm1
  char *v30; // rdx
  void *v31; // rcx
  size_t v32; // r8
  __int128 v33; // xmm1

  v3 = 0;
  v4 = (unsigned int)Size;
  v5 = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  *a3 = 0;
  if ( (unsigned int)v4 >= 0x220 )
  {
    v16 = 4;
    if ( (_DWORD)v4 == 544 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, 544);
      v17 = LocalAlloc(0x40u, 0x220u);
      v7 = v17;
      if ( !v17 )
      {
        LastError = GetLastError();
        v12 = LastError;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_66;
        v14 = 19;
        goto LABEL_9;
      }
      v18 = Src;
      v19 = 4;
      do
      {
        *v17 = *v18;
        v17[1] = v18[1];
        v17[2] = v18[2];
        v17[3] = v18[3];
        v17[4] = v18[4];
        v17[5] = v18[5];
        v17[6] = v18[6];
        v20 = v18[7];
        v18 += 8;
        v17[7] = v20;
        v17 += 8;
        --v19;
      }
      while ( v19 );
      *v17 = *v18;
      v17[1] = v18[1];
      if ( !(unsigned int)IsMschapV2UserDataV1Valid(v7, 544, 128) )
      {
        v15 = 13;
        v12 = 13;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_66;
        v14 = 20;
        goto LABEL_10;
      }
      v21 = 788;
    }
    else
    {
      if ( *(_DWORD *)Src == 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids,
            (unsigned int)v4);
        v22 = (char *)LocalAlloc(0x40u, v4);
        v5 = v22;
        if ( !v22 )
        {
          v12 = GetLastError();
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_66;
          v14 = 22;
          goto LABEL_30;
        }
        memcpy_0(v22, Src, v4);
        if ( !(unsigned int)IsMschapV2UserDataV2Valid(v5, (unsigned int)v4) )
        {
          v15 = 13;
          v12 = 13;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_66;
          v14 = 23;
          goto LABEL_10;
        }
        v23 = *((_DWORD *)Src + 136);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids,
            (unsigned int)v4);
        v24 = LocalAlloc(0x40u, v4);
        v3 = v24;
        if ( !v24 )
        {
          v12 = GetLastError();
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_66;
          v14 = 25;
          goto LABEL_30;
        }
        memcpy_0(v24, Src, v4);
        if ( !(unsigned int)IsMschapV2UserDataValid(v3, (unsigned int)v4) )
        {
          v15 = 13;
          v12 = 13;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_66;
          v14 = 26;
          goto LABEL_10;
        }
        v23 = *((_DWORD *)Src + 196);
      }
      v21 = -1;
      if ( v23 + 788 >= v23 )
        v21 = v23 + 788;
    }
    v25 = v21;
    v10 = LocalAlloc(0x40u, v21);
    if ( !v10 )
    {
      v12 = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_66;
      v14 = 27;
LABEL_30:
      v15 = v12;
      goto LABEL_10;
    }
    if ( (unsigned int)Feature_Eaphost_TVS_Fixes__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (_DWORD)v4 == 544 )
      {
        v26 = v10;
        do
        {
          *v26 = *(_OWORD *)Src;
          v26[1] = *((_OWORD *)Src + 1);
          v26[2] = *((_OWORD *)Src + 2);
          v26[3] = *((_OWORD *)Src + 3);
          v26[4] = *((_OWORD *)Src + 4);
          v26[5] = *((_OWORD *)Src + 5);
          v26[6] = *((_OWORD *)Src + 6);
          v27 = *((_OWORD *)Src + 7);
          Src += 128;
          v26[7] = v27;
          v26 += 8;
          --v16;
        }
        while ( v16 );
        *(_OWORD *)((char *)v26 - 2) = *(_OWORD *)(Src - 2);
        *(_OWORD *)((char *)v10 + 526) = *(_OWORD *)((char *)v7 + 526);
        goto LABEL_64;
      }
      if ( *(_DWORD *)Src == 2 )
      {
        v28 = v10;
        do
        {
          *v28 = *(_OWORD *)Src;
          v28[1] = *((_OWORD *)Src + 1);
          v28[2] = *((_OWORD *)Src + 2);
          v28[3] = *((_OWORD *)Src + 3);
          v28[4] = *((_OWORD *)Src + 4);
          v28[5] = *((_OWORD *)Src + 5);
          v28[6] = *((_OWORD *)Src + 6);
          v29 = *((_OWORD *)Src + 7);
          Src += 128;
          v28[7] = v29;
          v28 += 8;
          --v16;
        }
        while ( v16 );
LABEL_57:
        v30 = v5 + 548;
        v31 = (char *)v10 + 788;
        *(_OWORD *)((char *)v28 - 2) = *(_OWORD *)(Src - 2);
        *(_OWORD *)((char *)v10 + 526) = *(_OWORD *)(v5 + 526);
        *((_DWORD *)v10 + 196) = *((_DWORD *)v5 + 136);
        v32 = *((unsigned int *)v5 + 136);
LABEL_63:
        memcpy_0(v31, v30, v32);
LABEL_64:
        *(_DWORD *)v10 = 3;
        goto LABEL_65;
      }
    }
    else if ( *(_DWORD *)Src == 2 )
    {
      v28 = v10;
      do
      {
        *v28 = *(_OWORD *)Src;
        v28[1] = *((_OWORD *)Src + 1);
        v28[2] = *((_OWORD *)Src + 2);
        v28[3] = *((_OWORD *)Src + 3);
        v28[4] = *((_OWORD *)Src + 4);
        v28[5] = *((_OWORD *)Src + 5);
        v28[6] = *((_OWORD *)Src + 6);
        v33 = *((_OWORD *)Src + 7);
        Src += 128;
        v28[7] = v33;
        v28 += 8;
        --v16;
      }
      while ( v16 );
      goto LABEL_57;
    }
    v32 = v25;
    v30 = Src;
    v31 = v10;
    goto LABEL_63;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids,
      (unsigned int)v4);
  v9 = LocalAlloc(0x40u, 0x314u);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 3;
    v9[1] |= 4u;
    v9[2] = 2;
LABEL_65:
    v12 = 0;
    *a3 = v10;
    goto LABEL_66;
  }
  LastError = GetLastError();
  v12 = LastError;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v14 = 17;
LABEL_9:
    v15 = LastError;
LABEL_10:
    WPP_SF_d(v13[2], v14, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, v15);
  }
LABEL_66:
  LocalFree(0);
  LocalFree(v3);
  LocalFree(v7);
  LocalFree(v5);
  return v12;
}

```

## disassembly

```asm
0x180002954  mov     [rsp+arg_10], r8
0x180002959  push    rbx
0x18000295a  push    rbp
0x18000295b  push    rsi
0x18000295c  push    rdi
0x18000295d  push    r12
0x18000295f  push    r13
0x180002961  push    r14
0x180002963  push    r15
0x180002965  sub     rsp, 28h
0x180002969  xor     r13d, r13d
0x18000296c  mov     esi, edx
0x18000296e  xor     ebp, ebp
0x180002970  mov     rdi, r8
0x180002973  xor     r12d, r12d
0x180002976  mov     rbx, rcx
0x180002979  mov     rcx, cs:WPP_GLOBAL_Control
0x180002980  lea     r15, WPP_GLOBAL_Control
0x180002987  lea     rax, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x18000298e  cmp     rcx, r15
0x180002991  jz      short loc_1800029A9
0x180002993  mov     rcx, [rcx+10h]
0x180002997  lea     edx, [rbp+0Fh]
0x18000299a  mov     r8, rax
0x18000299d  call    WPP_SF_
0x1800029a2  lea     rax, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800029a9  mov     [rdi], rbp
0x1800029ac  cmp     esi, 220h
0x1800029b2  jnb     loc_180002A3F
0x1800029b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029bf  cmp     rcx, r15
0x1800029c2  jz      short loc_1800029D8
0x1800029c4  mov     rcx, [rcx+10h]
0x1800029c8  mov     edx, 10h
0x1800029cd  mov     r9d, esi
0x1800029d0  mov     r8, rax
0x1800029d3  call    WPP_SF_d
0x1800029d8  mov     edx, 314h; uBytes
0x1800029dd  mov     ecx, 40h ; '@'; uFlags
0x1800029e2  call    cs:__imp_LocalAlloc
0x1800029e8  mov     rdi, rax
0x1800029eb  test    rax, rax
0x1800029ee  jnz     short loc_180002A23
0x1800029f0  call    cs:__imp_GetLastError
0x1800029f6  mov     ebx, eax
0x1800029f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ff  cmp     rcx, r15
0x180002a02  jz      loc_180002E8B
0x180002a08  lea     edx, [rdi+11h]
0x180002a0b  mov     r9d, eax
0x180002a0e  mov     rcx, [rcx+10h]
0x180002a12  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180002a19  call    WPP_SF_d
0x180002a1e  jmp     loc_180002E8B
0x180002a23  mov     r14d, 4
0x180002a29  mov     dword ptr [rax], 3
0x180002a2f  or      [rax+4], r14d
0x180002a33  mov     dword ptr [rax+8], 2
0x180002a3a  jmp     loc_180002E7C
0x180002a3f  xor     edi, edi
0x180002a41  lea     r14d, [rdi+4]
0x180002a45  cmp     esi, 220h
0x180002a4b  jnz     loc_180002B47
0x180002a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a58  cmp     rcx, r15
0x180002a5b  jz      short loc_180002A6F
0x180002a5d  mov     rcx, [rcx+10h]
0x180002a61  lea     edx, [rdi+12h]
0x180002a64  mov     r9d, esi
0x180002a67  mov     r8, rax
0x180002a6a  call    WPP_SF_d
0x180002a6f  mov     edx, 220h; uBytes
0x180002a74  mov     ecx, 40h ; '@'; uFlags
0x180002a79  call    cs:__imp_LocalAlloc
0x180002a7f  mov     r12, rax
0x180002a82  test    rax, rax
0x180002a85  jnz     short loc_180002AA9
0x180002a87  call    cs:__imp_GetLastError
0x180002a8d  mov     ebx, eax
0x180002a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a96  cmp     rcx, r15
0x180002a99  jz      loc_180002E8B
0x180002a9f  lea     edx, [r12+13h]
0x180002aa4  jmp     loc_180002A0B
0x180002aa9  mov     rcx, rbx
0x180002aac  mov     rdx, r14
0x180002aaf  mov     r8d, 80h
0x180002ab5  movups  xmm0, xmmword ptr [rcx]
0x180002ab8  movups  xmmword ptr [rax], xmm0
0x180002abb  movups  xmm1, xmmword ptr [rcx+10h]
0x180002abf  movups  xmmword ptr [rax+10h], xmm1
0x180002ac3  movups  xmm0, xmmword ptr [rcx+20h]
0x180002ac7  movups  xmmword ptr [rax+20h], xmm0
0x180002acb  movups  xmm1, xmmword ptr [rcx+30h]
0x180002acf  movups  xmmword ptr [rax+30h], xmm1
0x180002ad3  movups  xmm0, xmmword ptr [rcx+40h]
0x180002ad7  movups  xmmword ptr [rax+40h], xmm0
0x180002adb  movups  xmm1, xmmword ptr [rcx+50h]
0x180002adf  movups  xmmword ptr [rax+50h], xmm1
0x180002ae3  movups  xmm0, xmmword ptr [rcx+60h]
0x180002ae7  movups  xmmword ptr [rax+60h], xmm0
0x180002aeb  movups  xmm1, xmmword ptr [rcx+70h]
0x180002aef  add     rcx, r8
0x180002af2  movups  xmmword ptr [rax+70h], xmm1
0x180002af6  add     rax, r8
0x180002af9  sub     rdx, 1
0x180002afd  jnz     short loc_180002AB5
0x180002aff  movups  xmm0, xmmword ptr [rcx]
0x180002b02  mov     edx, 220h
0x180002b07  movups  xmmword ptr [rax], xmm0
0x180002b0a  movups  xmm1, xmmword ptr [rcx+10h]
0x180002b0e  mov     rcx, r12
0x180002b11  movups  xmmword ptr [rax+10h], xmm1
0x180002b15  call    IsMschapV2UserDataV1Valid
0x180002b1a  test    eax, eax
0x180002b1c  jnz     short loc_180002B3D
0x180002b1e  lea     r9d, [rax+0Dh]
0x180002b22  mov     ebx, r9d
0x180002b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b2c  cmp     rcx, r15
0x180002b2f  jz      loc_180002E8B
0x180002b35  lea     edx, [rax+14h]
0x180002b38  jmp     loc_180002A0E
0x180002b3d  mov     edx, 314h
0x180002b42  jmp     loc_180002CB3
0x180002b47  cmp     dword ptr [rbx], 2
0x180002b4a  jnz     loc_180002BFE
0x180002b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b57  cmp     rcx, r15
0x180002b5a  jz      short loc_180002B70
0x180002b5c  mov     rcx, [rcx+10h]
0x180002b60  mov     edx, 15h
0x180002b65  mov     r9d, esi
0x180002b68  mov     r8, rax
0x180002b6b  call    WPP_SF_d
0x180002b70  mov     rdx, rsi; uBytes
0x180002b73  mov     ecx, 40h ; '@'; uFlags
0x180002b78  call    cs:__imp_LocalAlloc
0x180002b7e  mov     rbp, rax
0x180002b81  test    rax, rax
0x180002b84  jnz     short loc_180002BB0
0x180002b86  call    cs:__imp_GetLastError
0x180002b8c  mov     ebx, eax
0x180002b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b95  lea     rax, WPP_GLOBAL_Control
0x180002b9c  cmp     rcx, rax
0x180002b9f  jz      loc_180002E8B
0x180002ba5  lea     edx, [rbp+16h]
0x180002ba8  mov     r9d, ebx
0x180002bab  jmp     loc_180002A0E
0x180002bb0  mov     r8, rsi; Size
0x180002bb3  mov     rdx, rbx; Src
0x180002bb6  mov     rcx, rbp; void *
0x180002bb9  call    memcpy_0
0x180002bbe  mov     edx, esi
0x180002bc0  mov     rcx, rbp
0x180002bc3  call    IsMschapV2UserDataV2Valid
0x180002bc8  test    eax, eax
0x180002bca  jnz     short loc_180002BF3
0x180002bcc  lea     r9d, [rax+0Dh]
0x180002bd0  mov     ebx, r9d
0x180002bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bda  lea     rax, WPP_GLOBAL_Control
0x180002be1  cmp     rcx, rax
0x180002be4  jz      loc_180002E8B
0x180002bea  lea     edx, [r9+0Ah]
0x180002bee  jmp     loc_180002A0E
0x180002bf3  mov     eax, [rbx+220h]
0x180002bf9  jmp     loc_180002CA5
0x180002bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c05  cmp     rcx, r15
0x180002c08  jz      short loc_180002C1E
0x180002c0a  mov     rcx, [rcx+10h]
0x180002c0e  mov     edx, 18h
0x180002c13  mov     r9d, esi
0x180002c16  mov     r8, rax
0x180002c19  call    WPP_SF_d
0x180002c1e  mov     rdx, rsi; uBytes
0x180002c21  mov     ecx, 40h ; '@'; uFlags
0x180002c26  call    cs:__imp_LocalAlloc
0x180002c2c  mov     r13, rax
0x180002c2f  test    rax, rax
0x180002c32  jnz     short loc_180002C5C
0x180002c34  call    cs:__imp_GetLastError
0x180002c3a  mov     ebx, eax
0x180002c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c43  lea     rax, WPP_GLOBAL_Control
0x180002c4a  cmp     rcx, rax
0x180002c4d  jz      loc_180002E8B
0x180002c53  lea     edx, [r13+19h]
0x180002c57  jmp     loc_180002BA8
0x180002c5c  mov     r8, rsi; Size
0x180002c5f  mov     rdx, rbx; Src
0x180002c62  mov     rcx, r13; void *
0x180002c65  call    memcpy_0
0x180002c6a  mov     edx, esi
0x180002c6c  mov     rcx, r13
0x180002c6f  call    IsMschapV2UserDataValid
0x180002c74  test    eax, eax
0x180002c76  jnz     short loc_180002C9F
0x180002c78  lea     r9d, [rax+0Dh]
0x180002c7c  mov     ebx, r9d
0x180002c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c86  lea     rax, WPP_GLOBAL_Control
0x180002c8d  cmp     rcx, rax
0x180002c90  jz      loc_180002E8B
0x180002c96  lea     edx, [r9+0Dh]
0x180002c9a  jmp     loc_180002A0E
0x180002c9f  mov     eax, [rbx+310h]
0x180002ca5  or      edx, 0FFFFFFFFh
0x180002ca8  lea     ecx, [rax+314h]
0x180002cae  cmp     ecx, eax
0x180002cb0  cmovnb  edx, ecx
0x180002cb3  mov     r15d, edx
0x180002cb6  mov     ecx, 40h ; '@'; uFlags
0x180002cbb  mov     edx, edx; uBytes
0x180002cbd  call    cs:__imp_LocalAlloc
0x180002cc3  mov     rdi, rax
0x180002cc6  test    rax, rax
0x180002cc9  jnz     short loc_180002CF2
0x180002ccb  call    cs:__imp_GetLastError
0x180002cd1  mov     ebx, eax
0x180002cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cda  lea     rax, WPP_GLOBAL_Control
0x180002ce1  cmp     rcx, rax
0x180002ce4  jz      loc_180002E8B
0x180002cea  lea     edx, [rdi+1Bh]
0x180002ced  jmp     loc_180002BA8
0x180002cf2  call    Feature_Eaphost_TVS_Fixes__private_IsEnabledDeviceUsageNoInline
0x180002cf7  test    eax, eax
0x180002cf9  jz      loc_180002E0C
0x180002cff  cmp     esi, 220h
0x180002d05  jnz     short loc_180002D77
0x180002d07  mov     rax, rdi
0x180002d0a  mov     ecx, 80h
0x180002d0f  movups  xmm0, xmmword ptr [rbx]
0x180002d12  movups  xmmword ptr [rax], xmm0
0x180002d15  movups  xmm1, xmmword ptr [rbx+10h]
0x180002d19  movups  xmmword ptr [rax+10h], xmm1
0x180002d1d  movups  xmm0, xmmword ptr [rbx+20h]
0x180002d21  movups  xmmword ptr [rax+20h], xmm0
0x180002d25  movups  xmm1, xmmword ptr [rbx+30h]
0x180002d29  movups  xmmword ptr [rax+30h], xmm1
0x180002d2d  movups  xmm0, xmmword ptr [rbx+40h]
0x180002d31  movups  xmmword ptr [rax+40h], xmm0
0x180002d35  movups  xmm1, xmmword ptr [rbx+50h]
0x180002d39  movups  xmmword ptr [rax+50h], xmm1
0x180002d3d  movups  xmm0, xmmword ptr [rbx+60h]
0x180002d41  movups  xmmword ptr [rax+60h], xmm0
0x180002d45  movups  xmm1, xmmword ptr [rbx+70h]
0x180002d49  add     rbx, rcx
0x180002d4c  movups  xmmword ptr [rax+70h], xmm1
0x180002d50  add     rax, rcx
0x180002d53  sub     r14, 1
0x180002d57  jnz     short loc_180002D0F
0x180002d59  movups  xmm0, xmmword ptr [rbx-2]
0x180002d5d  movups  xmmword ptr [rax-2], xmm0
0x180002d61  movups  xmm1, xmmword ptr [r12+20Eh]
0x180002d6a  movdqu  xmmword ptr [rdi+20Eh], xmm1
0x180002d72  jmp     loc_180002E76
0x180002d77  cmp     dword ptr [rbx], 2
0x180002d7a  jnz     loc_180002E68
0x180002d80  mov     rax, rdi
0x180002d83  mov     ecx, 80h
0x180002d88  movups  xmm0, xmmword ptr [rbx]
0x180002d8b  movups  xmmword ptr [rax], xmm0
0x180002d8e  movups  xmm1, xmmword ptr [rbx+10h]
0x180002d92  movups  xmmword ptr [rax+10h], xmm1
0x180002d96  movups  xmm0, xmmword ptr [rbx+20h]
0x180002d9a  movups  xmmword ptr [rax+20h], xmm0
0x180002d9e  movups  xmm1, xmmword ptr [rbx+30h]
0x180002da2  movups  xmmword ptr [rax+30h], xmm1
0x180002da6  movups  xmm0, xmmword ptr [rbx+40h]
0x180002daa  movups  xmmword ptr [rax+40h], xmm0
0x180002dae  movups  xmm1, xmmword ptr [rbx+50h]
0x180002db2  movups  xmmword ptr [rax+50h], xmm1
0x180002db6  movups  xmm0, xmmword ptr [rbx+60h]
0x180002dba  movups  xmmword ptr [rax+60h], xmm0
0x180002dbe  movups  xmm1, xmmword ptr [rbx+70h]
0x180002dc2  add     rbx, rcx
0x180002dc5  movups  xmmword ptr [rax+70h], xmm1
0x180002dc9  add     rax, rcx
0x180002dcc  sub     r14, 1
0x180002dd0  jnz     short loc_180002D88
0x180002dd2  movups  xmm0, xmmword ptr [rbx-2]
0x180002dd6  lea     rdx, [rbp+224h]
0x180002ddd  lea     rcx, [rdi+314h]
0x180002de4  movups  xmmword ptr [rax-2], xmm0
0x180002de8  movups  xmm1, xmmword ptr [rbp+20Eh]
0x180002def  movdqu  xmmword ptr [rdi+20Eh], xmm1
0x180002df7  mov     eax, [rbp+220h]
0x180002dfd  mov     [rdi+310h], eax
0x180002e03  mov     r8d, [rbp+220h]
0x180002e0a  jmp     short loc_180002E71
0x180002e0c  cmp     dword ptr [rbx], 2
0x180002e0f  jnz     short loc_180002E68
0x180002e11  mov     rax, rdi
0x180002e14  mov     ecx, 80h
0x180002e19  movups  xmm0, xmmword ptr [rbx]
0x180002e1c  movups  xmmword ptr [rax], xmm0
  ... truncated ...
```
