# GmsapParsePasswordData(ulong,uchar *,ulong *,uchar * *)

- ea: `0x180004bbc`
- end: `0x180005012`
- name: `?GmsapParsePasswordData@@YAJKPEAEPEAKPEAPEAE@Z`
- size: `1110`
- prototype: `__int64 __fastcall(size_t Size, unsigned __int8 *Src, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800043f0`
- `0x180006084`

## callees

- `0x180004bbc`
- `0x180006280`
- `0x1800062b0`
- `0x180007bcd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c7d`
- `bcrypt!BCryptGenRandom` at `0x180004eb4`
- `bcrypt!BCryptGenRandom` at `0x180004eb4`

## pseudocode

```c
__int64 __fastcall GmsapParsePasswordData(size_t Size, unsigned __int8 *Src, unsigned int *a3, unsigned __int8 **a4)
{
  size_t v4; // rsi
  _UNKNOWN **v8; // rcx
  unsigned int v9; // r15d
  __int64 v10; // r14
  char *v11; // rax
  char *v12; // rdi
  unsigned int v13; // ebx
  char *v14; // rbx
  unsigned int v15; // r10d
  _BYTE *v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // ecx
  __int64 v19; // r9
  bool v20; // zf
  _WORD *v21; // r9
  unsigned __int64 i; // r8
  int v23; // ecx
  __int64 v24; // r8
  _WORD *v25; // r8
  unsigned __int64 v26; // rcx
  unsigned int j; // edx
  int v28; // edx
  int v29; // edx
  _QWORD *v30; // rcx
  USHORT v31; // dx
  int v32; // r9d
  NTSTATUS v33; // eax
  UCHAR v34; // kr00_1
  UCHAR pbBuffer; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+18h] BYREF

  v4 = (unsigned int)Size;
  pbBuffer = 0;
  SystemTimeAsFileTime = 0;
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x22u, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  v9 = v4 + 72;
  *a4 = 0;
  *a3 = 0;
  if ( (unsigned int)v4 < 0xFFFFFFB8 )
  {
    v10 = v9;
    v11 = (char *)LocalAlloc(0x40u, v9);
    v12 = v11;
    if ( !v11 )
    {
      v13 = -1073741801;
LABEL_65:
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      goto LABEL_66;
    }
    v14 = v11 + 72;
    memcpy_0(v11 + 72, Src, v4);
    *((_DWORD *)v12 + 16) = v4;
    *((_QWORD *)v12 + 7) = v14;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v15 = *((_DWORD *)v12 + 16);
    if ( v15 < 0x10 )
    {
      v13 = -1073741285;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0x24u,
          &WPP_70b8577d707437755865c965214ce19a_Traceguids,
          -1073741285);
      goto LABEL_11;
    }
    v17 = *((_QWORD *)v12 + 7);
    if ( !v17
      || !*(_WORD *)v17
      || (v18 = *(_DWORD *)(v17 + 4), v15 != v18)
      || !*(_WORD *)(v17 + 8)
      || !*(_WORD *)(v17 + 14)
      || !*(_WORD *)(v17 + 12)
      || *(unsigned __int16 *)(v17 + 8) > v18
      || *(unsigned __int16 *)(v17 + 10) > v18
      || *(unsigned __int16 *)(v17 + 14) > v18
      || *(unsigned __int16 *)(v17 + 12) > v18 )
    {
      v13 = -1073741285;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_11;
      v31 = 37;
      v32 = -1073741285;
      goto LABEL_47;
    }
    *(_QWORD *)(v12 + 28) = *(_QWORD *)&SystemTimeAsFileTime + *(_QWORD *)(*(unsigned __int16 *)(v17 + 14) + v17);
    *(_QWORD *)(v12 + 36) = *(_QWORD *)&SystemTimeAsFileTime + *(_QWORD *)(*(unsigned __int16 *)(v17 + 12) + v17);
    v19 = *(unsigned __int16 *)(v17 + 8);
    v20 = v17 + v19 == 0;
    v21 = (_WORD *)(v17 + v19);
    *(_QWORD *)v12 = v21;
    if ( v20 )
    {
      v13 = -1073741811;
    }
    else
    {
      for ( i = (unsigned __int64)(v15 - *(unsigned __int16 *)(v17 + 8)) >> 1; i; --i )
      {
        if ( !*v21 )
          break;
        ++v21;
      }
      v13 = i == 0 ? 0xC000000D : 0;
      if ( i )
        v23 = ((v15 - *(unsigned __int16 *)(v17 + 8)) >> 1) - i;
      else
        v23 = 0;
      if ( i )
      {
        *((_DWORD *)v12 + 2) = 2 * v23;
        if ( !*(_WORD *)(v17 + 10) )
        {
          *((_QWORD *)v12 + 2) = 0;
          v29 = 0;
          goto LABEL_49;
        }
        v24 = *(unsigned __int16 *)(v17 + 10);
        v20 = v17 + v24 == 0;
        v25 = (_WORD *)(v17 + v24);
        *((_QWORD *)v12 + 2) = v25;
        if ( v20 )
        {
          v13 = -1073741811;
        }
        else
        {
          v26 = (unsigned __int64)(v15 - *(unsigned __int16 *)(v17 + 10)) >> 1;
          for ( j = (v15 - *(unsigned __int16 *)(v17 + 10)) >> 1; v26; --v26 )
          {
            if ( !*v25 )
              break;
            ++v25;
          }
          v13 = v26 == 0 ? 0xC000000D : 0;
          if ( v26 )
            v28 = j - v26;
          else
            v28 = 0;
          if ( v26 )
          {
            v29 = 2 * v28;
LABEL_49:
            *((_DWORD *)v12 + 6) = v29;
            v33 = BCryptGenRandom(0, &pbBuffer, 1u, 2u);
            v13 = v33;
            if ( v33 >= 0 )
            {
              v34 = pbBuffer;
              *a3 = v9;
              v13 = 0;
              *a4 = (unsigned __int8 *)v12;
              pbBuffer = v34 % 0x3Bu + 1;
              *(_QWORD *)(v12 + 44) = *(_QWORD *)(v12 + 36) + 150000000LL * pbBuffer;
              goto LABEL_65;
            }
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_11:
              v16 = v12;
              do
              {
                *v16++ = 0;
                --v10;
              }
              while ( v10 );
              LocalFree(v12);
              goto LABEL_65;
            }
            v31 = 40;
            v32 = v33;
LABEL_47:
            WPP_SF_D(v30[2], v31, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v32);
            goto LABEL_11;
          }
        }
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_11;
        v31 = 39;
LABEL_46:
        v32 = v13;
        goto LABEL_47;
      }
    }
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_11;
    v31 = 38;
    goto LABEL_46;
  }
  v13 = -1073741675;
  if ( v8 == &WPP_GLOBAL_Control )
    return v13;
  if ( (*((_BYTE *)v8 + 28) & 4) != 0 )
  {
    WPP_SF_D((TRACEHANDLE)v8[2], 0x23u, &WPP_70b8577d707437755865c965214ce19a_Traceguids, -1073741675);
    goto LABEL_65;
  }
LABEL_66:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_D((TRACEHANDLE)v8[2], 0x29u, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180004bbc  mov     [rsp+arg_8], rbx
0x180004bc1  push    rbp
0x180004bc2  push    rsi
0x180004bc3  push    rdi
0x180004bc4  push    r12
0x180004bc6  push    r13
0x180004bc8  push    r14
0x180004bca  push    r15
0x180004bcc  sub     rsp, 20h
0x180004bd0  xor     ebx, ebx
0x180004bd2  mov     esi, ecx
0x180004bd4  mov     [rsp+58h+pbBuffer], bl
0x180004bd8  mov     r12, r9
0x180004bdb  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180004be0  mov     r13, r8
0x180004be3  mov     rbp, rdx
0x180004be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bed  lea     r15, WPP_GLOBAL_Control
0x180004bf4  cmp     rcx, r15
0x180004bf7  jz      short loc_180004C19
0x180004bf9  test    byte ptr [rcx+1Ch], 8
0x180004bfd  jz      short loc_180004C19
0x180004bff  mov     rcx, [rcx+10h]
0x180004c03  lea     edx, [rbx+22h]
0x180004c06  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004c0d  call    WPP_SF_
0x180004c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c19  lea     r15d, [rsi+48h]
0x180004c1d  mov     [r12], rbx
0x180004c21  mov     [r13+0], ebx
0x180004c25  cmp     r15d, 48h ; 'H'
0x180004c29  jb      loc_180004F9E
0x180004c2f  mov     edx, r15d; uBytes
0x180004c32  mov     ecx, 40h ; '@'; uFlags
0x180004c37  mov     r14d, r15d
0x180004c3a  call    cs:__imp_LocalAlloc
0x180004c41  nop     dword ptr [rax+rax+00h]
0x180004c46  mov     rdi, rax
0x180004c49  test    rax, rax
0x180004c4c  jnz     short loc_180004C5F
0x180004c4e  mov     ebx, 0C0000017h
0x180004c53  lea     rbp, WPP_GLOBAL_Control
0x180004c5a  jmp     loc_180004FD0
0x180004c5f  lea     rbx, [rax+48h]
0x180004c63  mov     r8, rsi; Size
0x180004c66  mov     rcx, rbx; void *
0x180004c69  mov     rdx, rbp; Src
0x180004c6c  call    memcpy_0
0x180004c71  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004c76  mov     [rdi+40h], esi
0x180004c79  mov     [rdi+38h], rbx
0x180004c7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004c84  nop     dword ptr [rax+rax+00h]
0x180004c89  mov     r10d, [rdi+40h]
0x180004c8d  mov     r11d, 1
0x180004c93  cmp     r10d, 10h
0x180004c97  jnb     short loc_180004D08
0x180004c99  mov     ebx, 0C000021Bh
0x180004c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ca5  lea     rbp, WPP_GLOBAL_Control
0x180004cac  cmp     rcx, rbp
0x180004caf  jz      loc_180004F97
0x180004cb5  test    byte ptr [rcx+1Ch], 4
0x180004cb9  jz      loc_180004F97
0x180004cbf  mov     rcx, [rcx+10h]
0x180004cc3  lea     edx, [r11+23h]
0x180004cc7  mov     r9d, 0C000021Bh
0x180004ccd  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004cd4  call    WPP_SF_D
0x180004cd9  xor     esi, esi
0x180004cdb  mov     r11d, 1
0x180004ce1  test    r15d, r15d
0x180004ce4  jz      short loc_180004CF4
0x180004ce6  mov     rax, rdi
0x180004ce9  mov     [rax], sil
0x180004cec  add     rax, r11
0x180004cef  sub     r14, r11
0x180004cf2  jnz     short loc_180004CE9
0x180004cf4  mov     rcx, rdi; hMem
0x180004cf7  call    cs:__imp_LocalFree
0x180004cfe  nop     dword ptr [rax+rax+00h]
0x180004d03  jmp     loc_180004FD0
0x180004d08  mov     rdx, [rdi+38h]
0x180004d0c  xor     esi, esi
0x180004d0e  test    rdx, rdx
0x180004d11  jz      loc_180004F61
0x180004d17  cmp     r11w, [rdx]
0x180004d1b  ja      loc_180004F61
0x180004d21  mov     ecx, [rdx+4]
0x180004d24  cmp     r10d, ecx
0x180004d27  jnz     loc_180004F61
0x180004d2d  cmp     si, [rdx+8]
0x180004d31  jz      loc_180004F61
0x180004d37  cmp     si, [rdx+0Eh]
0x180004d3b  jz      loc_180004F61
0x180004d41  cmp     si, [rdx+0Ch]
0x180004d45  jz      loc_180004F61
0x180004d4b  movzx   eax, word ptr [rdx+8]
0x180004d4f  cmp     eax, ecx
0x180004d51  ja      loc_180004F61
0x180004d57  movzx   eax, word ptr [rdx+0Ah]
0x180004d5b  cmp     eax, ecx
0x180004d5d  ja      loc_180004F61
0x180004d63  movzx   eax, word ptr [rdx+0Eh]
0x180004d67  cmp     eax, ecx
0x180004d69  ja      loc_180004F61
0x180004d6f  movzx   eax, word ptr [rdx+0Ch]
0x180004d73  cmp     eax, ecx
0x180004d75  ja      loc_180004F61
0x180004d7b  movzx   eax, word ptr [rdx+0Eh]
0x180004d7f  mov     rcx, [rax+rdx]
0x180004d83  add     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x180004d88  mov     [rdi+1Ch], rcx
0x180004d8c  movzx   eax, word ptr [rdx+0Ch]
0x180004d90  mov     rcx, [rax+rdx]
0x180004d94  add     rcx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x180004d99  mov     [rdi+24h], rcx
0x180004d9d  movzx   r9d, word ptr [rdx+8]
0x180004da2  add     r9, rdx
0x180004da5  mov     [rdi], r9
0x180004da8  jz      loc_180004F31
0x180004dae  movzx   eax, word ptr [rdx+8]
0x180004db2  mov     r8d, r10d
0x180004db5  sub     r8d, eax
0x180004db8  shr     r8, 1
0x180004dbb  mov     rcx, r8
0x180004dbe  jz      short loc_180004DCF
0x180004dc0  cmp     [r9], si
0x180004dc4  jz      short loc_180004DCF
0x180004dc6  add     r9, 2
0x180004dca  sub     r8, r11
0x180004dcd  jnz     short loc_180004DC0
0x180004dcf  mov     rax, r8
0x180004dd2  mov     r9d, 0C000000Dh
0x180004dd8  neg     rax
0x180004ddb  sbb     ebx, ebx
0x180004ddd  not     ebx
0x180004ddf  and     ebx, r9d
0x180004de2  test    r8, r8
0x180004de5  jz      short loc_180004DEC
0x180004de7  sub     rcx, r8
0x180004dea  jmp     short loc_180004DEF
0x180004dec  mov     rcx, rsi
0x180004def  test    r8, r8
0x180004df2  jz      loc_180004F36
0x180004df8  lea     eax, [rcx+rcx]
0x180004dfb  mov     [rdi+8], eax
0x180004dfe  cmp     si, [rdx+0Ah]
0x180004e02  jz      loc_180004E9B
0x180004e08  movzx   r8d, word ptr [rdx+0Ah]
0x180004e0d  add     r8, rdx
0x180004e10  mov     [rdi+10h], r8
0x180004e14  jz      short loc_180004E5A
0x180004e16  movzx   eax, word ptr [rdx+0Ah]
0x180004e1a  sub     r10d, eax
0x180004e1d  mov     ecx, r10d
0x180004e20  shr     rcx, 1
0x180004e23  mov     rdx, rcx
0x180004e26  jz      short loc_180004E37
0x180004e28  cmp     [r8], si
0x180004e2c  jz      short loc_180004E37
0x180004e2e  add     r8, 2
0x180004e32  sub     rcx, r11
0x180004e35  jnz     short loc_180004E28
0x180004e37  mov     rax, rcx
0x180004e3a  neg     rax
0x180004e3d  sbb     ebx, ebx
0x180004e3f  not     ebx
0x180004e41  and     ebx, r9d
0x180004e44  test    rcx, rcx
0x180004e47  jz      short loc_180004E4E
0x180004e49  sub     rdx, rcx
0x180004e4c  jmp     short loc_180004E51
0x180004e4e  mov     rdx, rsi
0x180004e51  test    rcx, rcx
0x180004e54  jz      short loc_180004E5D
0x180004e56  add     edx, edx
0x180004e58  jmp     short loc_180004EA1
0x180004e5a  mov     ebx, r9d
0x180004e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e64  lea     rbp, WPP_GLOBAL_Control
0x180004e6b  cmp     rcx, rbp
0x180004e6e  jz      loc_180004CE1
0x180004e74  test    byte ptr [rcx+1Ch], 4
0x180004e78  jz      loc_180004CE1
0x180004e7e  mov     edx, 27h ; '''
0x180004e83  mov     r9d, ebx
0x180004e86  mov     rcx, [rcx+10h]
0x180004e8a  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004e91  call    WPP_SF_D
0x180004e96  jmp     loc_180004CDB
0x180004e9b  mov     [rdi+10h], rsi
0x180004e9f  mov     edx, esi
0x180004ea1  mov     [rdi+18h], edx
0x180004ea4  mov     r9d, 2; dwFlags
0x180004eaa  lea     rdx, [rsp+58h+pbBuffer]; pbBuffer
0x180004eaf  mov     r8d, r11d; cbBuffer
0x180004eb2  xor     ecx, ecx; hAlgorithm
0x180004eb4  call    cs:__imp_BCryptGenRandom
0x180004ebb  nop     dword ptr [rax+rax+00h]
0x180004ec0  mov     ebx, eax
0x180004ec2  test    eax, eax
0x180004ec4  jns     short loc_180004EF6
0x180004ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ecd  lea     rbp, WPP_GLOBAL_Control
0x180004ed4  cmp     rcx, rbp
0x180004ed7  jz      loc_180004CDB
0x180004edd  mov     r11d, 1
0x180004ee3  test    [rcx+1Ch], r11b
0x180004ee7  jz      loc_180004CE1
0x180004eed  lea     edx, [r11+27h]
0x180004ef1  mov     r9d, eax
0x180004ef4  jmp     short loc_180004E86
0x180004ef6  movzx   ecx, [rsp+58h+pbBuffer]
0x180004efb  mov     eax, 22B63CBFh
0x180004f00  mul     ecx
0x180004f02  mov     [r13+0], r15d
0x180004f06  mov     ebx, esi
0x180004f08  shr     edx, 3
0x180004f0b  imul    eax, edx, 3Bh ; ';'
0x180004f0e  mov     [r12], rdi
0x180004f12  sub     ecx, eax
0x180004f14  inc     cl
0x180004f16  movzx   eax, cl
0x180004f19  mov     [rsp+58h+pbBuffer], al
0x180004f1d  imul    rax, 8F0D180h
0x180004f24  add     rax, [rdi+24h]
0x180004f28  mov     [rdi+2Ch], rax
0x180004f2c  jmp     loc_180004C53
0x180004f31  mov     ebx, 0C000000Dh
0x180004f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f3d  lea     rbp, WPP_GLOBAL_Control
0x180004f44  cmp     rcx, rbp
0x180004f47  jz      loc_180004CE1
0x180004f4d  test    byte ptr [rcx+1Ch], 4
0x180004f51  jz      loc_180004CE1
0x180004f57  mov     edx, 26h ; '&'
0x180004f5c  jmp     loc_180004E83
0x180004f61  mov     ebx, 0C000021Bh
0x180004f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f6d  lea     rbp, WPP_GLOBAL_Control
0x180004f74  cmp     rcx, rbp
0x180004f77  jz      loc_180004CE1
0x180004f7d  test    byte ptr [rcx+1Ch], 4
0x180004f81  jz      loc_180004CE1
0x180004f87  mov     edx, 25h ; '%'
0x180004f8c  mov     r9d, 0C000021Bh
0x180004f92  jmp     loc_180004E86
0x180004f97  xor     esi, esi
0x180004f99  jmp     loc_180004CE1
0x180004f9e  mov     ebx, 0C0000095h
0x180004fa3  lea     rbp, WPP_GLOBAL_Control
0x180004faa  cmp     rcx, rbp
0x180004fad  jz      short loc_180004FFA
0x180004faf  test    byte ptr [rcx+1Ch], 4
0x180004fb3  jz      short loc_180004FD7
0x180004fb5  mov     rcx, [rcx+10h]
0x180004fb9  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004fc0  mov     edx, 23h ; '#'
0x180004fc5  mov     r9d, 0C0000095h
0x180004fcb  call    WPP_SF_D
0x180004fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fd7  cmp     rcx, rbp
0x180004fda  jz      short loc_180004FFA
0x180004fdc  test    byte ptr [rcx+1Ch], 8
0x180004fe0  jz      short loc_180004FFA
0x180004fe2  mov     rcx, [rcx+10h]
0x180004fe6  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004fed  mov     edx, 29h ; ')'
0x180004ff2  mov     r9d, ebx
0x180004ff5  call    WPP_SF_D
0x180004ffa  mov     eax, ebx
0x180004ffc  mov     rbx, [rsp+58h+arg_8]
0x180005001  add     rsp, 20h
0x180005005  pop     r15
0x180005007  pop     r14
0x180005009  pop     r13
0x18000500b  pop     r12
0x18000500d  pop     rdi
0x18000500e  pop     rsi
0x18000500f  pop     rbp
0x180005010  retn
```
