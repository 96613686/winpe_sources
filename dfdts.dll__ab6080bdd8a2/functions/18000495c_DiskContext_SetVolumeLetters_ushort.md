# DiskContext::SetVolumeLetters(ushort *)

- ea: `0x18000495c`
- end: `0x180004d62`
- name: `?SetVolumeLetters@DiskContext@@AEAAKPEAG@Z`
- size: `1030`
- prototype: `__int64 __fastcall(DiskContext *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003bac`

## callees

- `0x180003984`
- `0x18000495c`
- `0x1800050b4`
- `0x1800051c4`
- `0x180005268`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180004990`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180004a28`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180004990`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180004a28`
- `KERNEL32!HeapAlloc` at `0x180004a02`
- `KERNEL32!HeapAlloc` at `0x180004a02`
- `KERNEL32!GetProcessHeap` at `0x1800049f1`
- `KERNEL32!GetProcessHeap` at `0x180004c51`
- `KERNEL32!GetProcessHeap` at `0x1800049f1`
- `KERNEL32!GetProcessHeap` at `0x180004c51`
- `KERNEL32!HeapFree` at `0x180004c5f`
- `KERNEL32!HeapFree` at `0x180004c5f`
- `KERNEL32!GetLastError` at `0x18000499a`
- `KERNEL32!GetLastError` at `0x180004a32`
- `KERNEL32!GetLastError` at `0x18000499a`
- `KERNEL32!GetLastError` at `0x180004a32`

## pseudocode

```c
__int64 __fastcall DiskContext::SetVolumeLetters(DiskContext *this, unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  WCHAR *v8; // r14
  _QWORD *v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rcx
  int v12; // edx
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // rsi
  _WORD *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rcx
  _WORD *v19; // rcx
  unsigned int v20; // ecx
  _WORD *v21; // rax
  unsigned int v22; // ecx
  __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rcx
  int v26; // eax
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  HANDLE v34; // rax
  _QWORD *v36; // rcx
  int v37; // edx
  DWORD cchBufferLength; // [rsp+70h] [rbp+18h] BYREF
  DWORD cchReturnLength; // [rsp+78h] [rbp+20h] BYREF

  cchBufferLength = 0;
  cchReturnLength = 0;
  if ( !GetVolumePathNamesForVolumeNameW(a2, 0, 0, &cchBufferLength) )
  {
    LastError = GetLastError();
    if ( LastError != 234 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
          (_DWORD)a2,
          LastError);
      return LastError;
    }
  }
  v5 = 2LL * cchBufferLength;
  ProcessHeap = GetProcessHeap();
  v7 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v5);
  v8 = v7;
  if ( !v7 )
    return 14;
  if ( !GetVolumePathNamesForVolumeNameW(a2, v7, cchBufferLength, &cchReturnLength) )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 39;
      LODWORD(v13) = (_DWORD)a2;
LABEL_12:
      WPP_SF_Sd(v11[2], v12, (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, (_DWORD)v13, LastError);
    }
    goto LABEL_50;
  }
  v14 = v8;
  if ( !*v8 )
  {
LABEL_47:
    LastError = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v9, v10, (_DWORD)a2, *((_QWORD *)this + 76));
    goto LABEL_50;
  }
  while ( 1 )
  {
    v15 = (_WORD *)*((_QWORD *)this + 76);
    if ( *v15 )
      break;
    v16 = cchReturnLength;
    if ( !cchReturnLength )
    {
      LOWORD(v20) = 87;
      goto LABEL_62;
    }
    if ( cchReturnLength > 0x7FFFFFFFuLL )
    {
      LOWORD(v20) = 87;
      *v15 = 0;
LABEL_62:
      LastError = (unsigned __int16)v20;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v37 = 40;
        goto LABEL_65;
      }
      goto LABEL_50;
    }
    v17 = 2147483646;
    v18 = v14;
    do
    {
      if ( !v17 )
        break;
      LODWORD(v10) = *v18;
      if ( !(_WORD)v10 )
        break;
      *v15 = v10;
      ++v18;
      ++v15;
      --v17;
      --v16;
    }
    while ( v16 );
    v19 = v15 - 1;
    if ( v16 )
      v19 = v15;
    *v19 = 0;
    v20 = v16 == 0 ? 0x8007007A : 0;
    if ( !v16 )
      goto LABEL_62;
    v21 = (_WORD *)*((_QWORD *)this + 76);
    v9 = (_QWORD *)((char *)this + 616);
    if ( !v21 )
    {
      LOWORD(v22) = 87;
LABEL_54:
      if ( this != (DiskContext *)-616LL )
LABEL_55:
        *v9 = 0;
      LastError = (unsigned __int16)v22;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v37 = 41;
LABEL_65:
        WPP_SF_SSD(v36[2], v37, v10, (_DWORD)v14, (__int64)a2, LastError);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    v10 = 130;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v10;
    }
    while ( v10 );
    v22 = v10 == 0 ? 0x80070057 : 0;
    if ( this == (DiskContext *)-616LL )
    {
      if ( !v10 )
        goto LABEL_54;
    }
    else
    {
      if ( !v10 )
      {
        *v9 = 0;
        goto LABEL_55;
      }
      *v9 = 130 - v10;
    }
LABEL_44:
    v33 = -1;
    do
      ++v33;
    while ( v14[v33] );
    v14 += v33 + 1;
    if ( !*v14 )
      goto LABEL_47;
  }
  v23 = -1;
  do
    ++v23;
  while ( v15[v23] );
  v24 = v23 + 2;
  v25 = (unsigned __int16 *)*((_QWORD *)this + 76);
  *((_QWORD *)this + 77) = v24;
  v26 = StringCchCatW(v25, v24, L";");
  if ( v26 >= 0 )
  {
    v27 = (unsigned __int16 *)*((_QWORD *)this + 76);
    v28 = -1;
    do
      ++v28;
    while ( v14[v28] );
    v29 = -1;
    do
      ++v29;
    while ( v27[v29] );
    v30 = v29 + 1 + v28;
    *((_QWORD *)this + 77) = v30;
    v31 = StringCchCatW(v27, v30, v14);
    if ( v31 < 0 )
    {
      LastError = (unsigned __int16)v31;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v37 = 43;
        goto LABEL_65;
      }
      goto LABEL_50;
    }
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)(*((_QWORD *)this + 76) + 2 * v32) );
    *((_QWORD *)this + 77) = v32;
    goto LABEL_44;
  }
  LastError = (unsigned __int16)v26;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 42;
    v13 = L";";
    goto LABEL_12;
  }
LABEL_50:
  v34 = GetProcessHeap();
  HeapFree(v34, 0, v8);
  return LastError;
}

```

## disassembly

```asm
0x18000495c  mov     rax, rsp
0x18000495f  mov     [rax+8], rbx
0x180004963  mov     [rax+10h], rbp
0x180004967  push    rsi
0x180004968  push    rdi
0x180004969  push    r12
0x18000496b  push    r14
0x18000496d  push    r15
0x18000496f  sub     rsp, 30h
0x180004973  mov     rdi, rdx
0x180004976  lea     r9, [rax+18h]; lpcchReturnLength
0x18000497a  mov     rbp, rcx
0x18000497d  xor     r15d, r15d
0x180004980  mov     rcx, rdi; lpszVolumeName
0x180004983  mov     [rax+18h], r15d
0x180004987  xor     r8d, r8d; cchBufferLength
0x18000498a  mov     [rax+20h], r15d
0x18000498e  xor     edx, edx; lpszVolumePathNames
0x180004990  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180004996  test    eax, eax
0x180004998  jnz     short loc_1800049EA
0x18000499a  call    cs:__imp_GetLastError
0x1800049a0  mov     ebx, eax
0x1800049a2  cmp     eax, 0EAh
0x1800049a7  jz      short loc_1800049EA
0x1800049a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049b0  lea     rax, WPP_GLOBAL_Control
0x1800049b7  cmp     rcx, rax
0x1800049ba  jz      loc_180004C65
0x1800049c0  test    byte ptr [rcx+1Ch], 1
0x1800049c4  jz      loc_180004C65
0x1800049ca  mov     rcx, [rcx+10h]
0x1800049ce  lea     edx, [r15+26h]
0x1800049d2  mov     r9, rdi
0x1800049d5  mov     dword ptr [rsp+58h+var_38], ebx
0x1800049d9  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x1800049e0  call    WPP_SF_Sd
0x1800049e5  jmp     loc_180004C65
0x1800049ea  mov     ebx, [rsp+58h+cchBufferLength]
0x1800049ee  add     rbx, rbx
0x1800049f1  call    cs:__imp_GetProcessHeap
0x1800049f7  mov     r8, rbx; dwBytes
0x1800049fa  mov     edx, 8; dwFlags
0x1800049ff  mov     rcx, rax; hHeap
0x180004a02  call    cs:__imp_HeapAlloc
0x180004a08  mov     r14, rax
0x180004a0b  test    rax, rax
0x180004a0e  jnz     short loc_180004A18
0x180004a10  lea     ebx, [rax+0Eh]
0x180004a13  jmp     loc_180004C65
0x180004a18  mov     r8d, [rsp+58h+cchBufferLength]; cchBufferLength
0x180004a1d  lea     r9, [rsp+58h+cchReturnLength]; lpcchReturnLength
0x180004a22  mov     rdx, r14; lpszVolumePathNames
0x180004a25  mov     rcx, rdi; lpszVolumeName
0x180004a28  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180004a2e  test    eax, eax
0x180004a30  jnz     short loc_180004A7C
0x180004a32  call    cs:__imp_GetLastError
0x180004a38  mov     ebx, eax
0x180004a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a41  lea     rax, WPP_GLOBAL_Control
0x180004a48  cmp     rcx, rax
0x180004a4b  jz      loc_180004C51
0x180004a51  test    byte ptr [rcx+1Ch], 1
0x180004a55  jz      loc_180004C51
0x180004a5b  mov     edx, 27h ; '''
0x180004a60  mov     r9, rdi
0x180004a63  mov     rcx, [rcx+10h]
0x180004a67  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004a6e  mov     dword ptr [rsp+58h+var_38], ebx
0x180004a72  call    WPP_SF_Sd
0x180004a77  jmp     loc_180004C51
0x180004a7c  mov     rsi, r14
0x180004a7f  cmp     r15w, [r14]
0x180004a83  jz      loc_180004C1D
0x180004a89  mov     ebx, 80070057h
0x180004a8e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180004a92  mov     r9, [rbp+260h]
0x180004a99  cmp     [r9], r15w
0x180004a9d  jnz     loc_180004B76
0x180004aa3  mov     edx, [rsp+58h+cchReturnLength]
0x180004aa7  test    rdx, rdx
0x180004aaa  jz      loc_180004CB4
0x180004ab0  cmp     rdx, 7FFFFFFFh
0x180004ab7  ja      loc_180004CB0
0x180004abd  mov     eax, 7FFFFFFEh
0x180004ac2  mov     rcx, rsi
0x180004ac5  test    rax, rax
0x180004ac8  jz      short loc_180004AE9
0x180004aca  movzx   r8d, word ptr [rcx]
0x180004ace  test    r8w, r8w
0x180004ad2  jz      short loc_180004AE9
0x180004ad4  mov     [r9], r8w
0x180004ad8  add     rcx, 2
0x180004adc  add     r9, 2
0x180004ae0  dec     rax
0x180004ae3  sub     rdx, 1
0x180004ae7  jnz     short loc_180004AC5
0x180004ae9  test    rdx, rdx
0x180004aec  lea     rcx, [r9-2]
0x180004af0  mov     rax, rdx
0x180004af3  cmovnz  rcx, r9
0x180004af7  neg     rax
0x180004afa  mov     [rcx], r15w
0x180004afe  sbb     ecx, ecx
0x180004b00  not     ecx
0x180004b02  and     ecx, 8007007Ah
0x180004b08  test    rdx, rdx
0x180004b0b  jz      loc_180004CBF
0x180004b11  mov     rax, [rbp+260h]
0x180004b18  lea     rdx, [rbp+268h]
0x180004b1f  test    rax, rax
0x180004b22  jz      loc_180004C83
0x180004b28  mov     r8d, 82h
0x180004b2e  cmp     [rax], r15w
0x180004b32  jz      short loc_180004B3E
0x180004b34  add     rax, 2
0x180004b38  sub     r8, 1
0x180004b3c  jnz     short loc_180004B2E
0x180004b3e  mov     rax, r8
0x180004b41  neg     rax
0x180004b44  sbb     ecx, ecx
0x180004b46  not     ecx
0x180004b48  and     ecx, ebx
0x180004b4a  test    rdx, rdx
0x180004b4d  jz      short loc_180004B68
0x180004b4f  test    r8, r8
0x180004b52  jz      loc_180004C7E
0x180004b58  mov     eax, 82h
0x180004b5d  sub     rax, r8
0x180004b60  mov     [rdx], rax
0x180004b63  jmp     loc_180004BFE
0x180004b68  test    r8, r8
0x180004b6b  jz      loc_180004C85
0x180004b71  jmp     loc_180004BFE
0x180004b76  mov     rdx, r12
0x180004b79  inc     rdx
0x180004b7c  cmp     [r9+rdx*2], r15w
0x180004b81  jnz     short loc_180004B79
0x180004b83  add     rdx, 2; unsigned __int64
0x180004b87  lea     r8, asc_18000BDB0; ";"
0x180004b8e  mov     rcx, r9; unsigned __int16 *
0x180004b91  mov     [rbp+268h], rdx
0x180004b98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b9d  test    eax, eax
0x180004b9f  js      loc_180004D2D
0x180004ba5  mov     rcx, [rbp+260h]; unsigned __int16 *
0x180004bac  mov     rdx, r12
0x180004baf  inc     rdx
0x180004bb2  cmp     [rsi+rdx*2], r15w
0x180004bb7  jnz     short loc_180004BAF
0x180004bb9  mov     rax, r12
0x180004bbc  inc     rax
0x180004bbf  cmp     [rcx+rax*2], r15w
0x180004bc4  jnz     short loc_180004BBC
0x180004bc6  inc     rax
0x180004bc9  mov     r8, rsi; unsigned __int16 *
0x180004bcc  add     rdx, rax; unsigned __int64
0x180004bcf  mov     [rbp+268h], rdx
0x180004bd6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004bdb  test    eax, eax
0x180004bdd  js      loc_180004D02
0x180004be3  mov     rcx, [rbp+260h]
0x180004bea  mov     rax, r12
0x180004bed  inc     rax
0x180004bf0  cmp     [rcx+rax*2], r15w
0x180004bf5  jnz     short loc_180004BED
0x180004bf7  mov     [rbp+268h], rax
0x180004bfe  mov     rax, r12
0x180004c01  inc     rax
0x180004c04  cmp     [rsi+rax*2], r15w
0x180004c09  jnz     short loc_180004C01
0x180004c0b  lea     rsi, [rsi+rax*2]
0x180004c0f  add     rsi, 2
0x180004c13  cmp     r15w, [rsi]
0x180004c17  jnz     loc_180004A92
0x180004c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c24  lea     rax, WPP_GLOBAL_Control
0x180004c2b  mov     ebx, r15d
0x180004c2e  cmp     rcx, rax
0x180004c31  jz      short loc_180004C51
0x180004c33  test    byte ptr [rcx+1Ch], 4
0x180004c37  jz      short loc_180004C51
0x180004c39  mov     rax, [rbp+260h]
0x180004c40  mov     r9, rdi
0x180004c43  mov     rcx, [rcx+10h]
0x180004c47  mov     [rsp+58h+var_38], rax
0x180004c4c  call    WPP_SF_SS
0x180004c51  call    cs:__imp_GetProcessHeap
0x180004c57  mov     r8, r14; lpMem
0x180004c5a  xor     edx, edx; dwFlags
0x180004c5c  mov     rcx, rax; hHeap
0x180004c5f  call    cs:__imp_HeapFree
0x180004c65  mov     rbp, [rsp+58h+arg_8]
0x180004c6a  mov     eax, ebx
0x180004c6c  mov     rbx, [rsp+58h+arg_0]
0x180004c71  add     rsp, 30h
0x180004c75  pop     r15
0x180004c77  pop     r14
0x180004c79  pop     r12
0x180004c7b  pop     rdi
0x180004c7c  pop     rsi
0x180004c7d  retn
0x180004c7e  mov     [rdx], r15
0x180004c81  jmp     short loc_180004C8A
0x180004c83  mov     ecx, ebx
0x180004c85  test    rdx, rdx
0x180004c88  jz      short loc_180004C8D
0x180004c8a  mov     [rdx], r15
0x180004c8d  movzx   ebx, cx
0x180004c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c97  lea     rax, WPP_GLOBAL_Control
0x180004c9e  cmp     rcx, rax
0x180004ca1  jz      short loc_180004C51
0x180004ca3  test    byte ptr [rcx+1Ch], 1
0x180004ca7  jz      short loc_180004C51
0x180004ca9  mov     edx, 29h ; ')'
0x180004cae  jmp     short loc_180004CE8
0x180004cb0  mov     ecx, ebx
0x180004cb2  jmp     short loc_180004CBB
0x180004cb4  mov     ecx, ebx
0x180004cb6  test    rdx, rdx
0x180004cb9  jz      short loc_180004CBF
0x180004cbb  mov     [r9], r15w
0x180004cbf  movzx   ebx, cx
0x180004cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cc9  lea     rax, WPP_GLOBAL_Control
0x180004cd0  cmp     rcx, rax
0x180004cd3  jz      loc_180004C51
0x180004cd9  test    byte ptr [rcx+1Ch], 1
0x180004cdd  jz      loc_180004C51
0x180004ce3  mov     edx, 28h ; '('
0x180004ce8  mov     rcx, [rcx+10h]
0x180004cec  mov     r9, rsi
0x180004cef  mov     [rsp+58h+var_30], ebx
0x180004cf3  mov     [rsp+58h+var_38], rdi
0x180004cf8  call    WPP_SF_SSD
0x180004cfd  jmp     loc_180004C51
0x180004d02  movzx   ebx, ax
0x180004d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d0c  lea     rax, WPP_GLOBAL_Control
0x180004d13  cmp     rcx, rax
0x180004d16  jz      loc_180004C51
0x180004d1c  test    byte ptr [rcx+1Ch], 1
0x180004d20  jz      loc_180004C51
0x180004d26  mov     edx, 2Bh ; '+'
0x180004d2b  jmp     short loc_180004CE8
0x180004d2d  movzx   ebx, ax
0x180004d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d37  lea     rax, WPP_GLOBAL_Control
0x180004d3e  cmp     rcx, rax
0x180004d41  jz      loc_180004C51
0x180004d47  test    byte ptr [rcx+1Ch], 1
0x180004d4b  jz      loc_180004C51
0x180004d51  mov     edx, 2Ah ; '*'
0x180004d56  lea     r9, asc_18000BDB0; ";"
0x180004d5d  jmp     loc_180004A63
```
