# CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)

- ea: `0x1800036f0`
- end: `0x180003af6`
- name: `?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z`
- size: `1030`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, void *const, const union _CDB *, unsigned int, struct _SENSE_DATA *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned __int8)`
- caller_count: `9`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001f50`
- `0x180002750`
- `0x1800028d0`
- `0x1800030f0`
- `0x180029fd0`
- `0x18002a6a0`
- `0x18002b300`
- `0x18002b470`

## callees

- `0x1800036f0`
- `0x180005100`
- `0x180012700`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x18002ce50`
- `0x18002d004`
- `0x180049832`
- `0x18004984a`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180003764`
- `KERNEL32!LocalAlloc` at `0x180003764`
- `KERNEL32!LocalFree` at `0x180003894`
- `KERNEL32!LocalFree` at `0x180003894`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SendCommandHelper(
        CMsftDiscRecorder2 *this,
        void *const a2,
        const union _CDB *a3,
        unsigned int a4,
        struct _SENSE_DATA *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int Size,
        unsigned int *a9,
        unsigned __int8 a10)
{
  size_t v10; // r13
  char *v11; // rax
  char *v12; // rbx
  CMsftDiscRecorder2 *v13; // rcx
  _BYTE *v14; // r12
  int v15; // r8d
  int v16; // edi
  unsigned int v17; // eax
  __int64 v19; // rax
  __int128 v20; // xmm0
  int v21; // r9d
  __int64 v22; // r10
  int v23; // edx
  int v24; // r8d
  __int128 v25; // xmm0
  __int64 v26; // rcx
  unsigned int v27[4]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v28; // [rsp+50h] [rbp-30h] BYREF
  __int128 v29; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v30[16]; // [rsp+70h] [rbp-10h] BYREF

  v10 = a4;
  *(_OWORD *)a5 = 0;
  *(_WORD *)&a5->SenseKeySpecific[1] = 0;
  if ( a9 )
    *a9 = 0;
  if ( a10 && Size )
    memset_0(a7, 0, Size);
  v11 = (char *)LocalAlloc(0x40u, 0x60u);
  v12 = v11;
  if ( v11 )
  {
    *(_WORD *)v11 = 56;
    v11[6] = v10;
    *(_QWORD *)&v28 = v10;
    memcpy_0(v11 + 36, a3, v10);
    v12[7] = 18;
    if ( Size )
      v12[8] = a10 != 0;
    else
      v12[8] = 2;
    *((_QWORD *)v12 + 3) = a7;
    v14 = v12 + 36;
    *((_DWORD *)v12 + 3) = Size;
    *((_DWORD *)v12 + 4) = a6;
    *((_DWORD *)v12 + 8) = 64;
    if ( *((_DWORD *)this + 59) )
    {
      if ( (LOBYTE(v13) = *v14, (unsigned __int8)(*v14 + 95) <= 0x1Eu)
        && (v15 = 1073742337, _bittest(&v15, (_DWORD)v13 + 95))
        || (_BYTE)v13 == 4
        || (LOBYTE(v13) = (_BYTE)v13 - 42, (unsigned __int8)v13 <= 0x31u)
        && (v19 = 0x2420000000011LL, _bittest64(&v19, (unsigned __int64)v13)) )
      {
        *((_BYTE *)this + 169) = 1;
      }
    }
    v27[0] = 0;
    v16 = CMsftDiscRecorder2::SaferDeviceIoControl(v13, a2, 0x4D014u, v12, 0x60u, v12, 0x60u, v27);
    if ( a9 )
      *a9 = *((_DWORD *)v12 + 3);
    if ( v16 == -1062600179 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        v20 = *(_OWORD *)LOG_BLOB(v30, v28, v12 + 36);
        *(_DWORD *)((char *)&v28 + 2) = v21;
        WORD3(v28) = v21;
        LOWORD(v28) = v21 + 18;
        *((_QWORD *)&v28 + 1) = v22;
        v29 = v20;
        WPP_SF_dD_HEX__HEX_(*((_QWORD *)WPP_GLOBAL_Control + 22), v23, v24, a6, a6, (__int64)&v29, (__int64)&v28);
      }
    }
    else if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          25,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
          (unsigned int)v16);
      }
    }
    else if ( (v12[2] & 0xFD) != 0 )
    {
      v16 = -1062599937;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          26,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
          (unsigned __int8)v12[2],
          -1062599937);
      }
    }
    else
    {
      v17 = (unsigned __int8)v12[71] + 8;
      if ( v17 > 0x12 )
        v17 = 18;
      memcpy_0(a5, v12 + 64, v17);
      if ( (*((_BYTE *)a5 + 2) & 0xF) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
        {
          LOWORD(v29) = 18;
          *(_DWORD *)((char *)&v29 + 2) = 0;
          WORD3(v29) = 0;
          *((_QWORD *)&v29 + 1) = v12 + 64;
          v25 = *(_OWORD *)LOG_BLOB(v30, v28, v12 + 36);
          v26 = *((_QWORD *)WPP_GLOBAL_Control + 22);
          v28 = v25;
          WPP_SF__HEX__HEX_(
            v26,
            27,
            (unsigned int)&WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)&v28,
            (__int64)&v29);
        }
        v16 = 11141632;
      }
      else
      {
        v16 = 0;
      }
    }
    LocalFree(v12);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 23, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800036f0  mov     rax, rsp
0x1800036f3  mov     [rax+20h], rbx
0x1800036f7  mov     [rax+18h], r8
0x1800036fb  mov     [rax+10h], rdx
0x1800036ff  mov     [rax+8], rcx
0x180003703  push    rbp
0x180003704  push    rsi
0x180003705  push    rdi
0x180003706  push    r12
0x180003708  push    r13
0x18000370a  push    r14
0x18000370c  push    r15
0x18000370e  mov     rbp, rsp
0x180003711  sub     rsp, 80h
0x180003718  mov     r15, [rbp+arg_20]
0x18000371c  xor     eax, eax
0x18000371e  mov     r14, [rbp+arg_40]
0x180003725  xorps   xmm0, xmm0
0x180003728  mov     r13d, r9d
0x18000372b  movups  xmmword ptr [r15], xmm0
0x18000372f  mov     [r15+10h], ax
0x180003734  test    r14, r14
0x180003737  jz      short loc_18000373C
0x180003739  mov     [r14], eax
0x18000373c  mov     edi, dword ptr [rbp+Size]
0x18000373f  mov     r12, [rbp+arg_30]
0x180003743  cmp     [rbp+arg_48], al
0x180003749  jz      short loc_18000375C
0x18000374b  test    edi, edi
0x18000374d  jz      short loc_18000375C
0x18000374f  mov     r8d, edi; Size
0x180003752  xor     edx, edx; Val
0x180003754  mov     rcx, r12; void *
0x180003757  call    memset_0
0x18000375c  mov     edx, 60h ; '`'; uBytes
0x180003761  lea     ecx, [rdx-20h]; uFlags
0x180003764  call    cs:__imp_LocalAlloc
0x18000376a  mov     rbx, rax
0x18000376d  test    rax, rax
0x180003770  jz      loc_180003935
0x180003776  mov     rdx, [rbp+Src]; Src
0x18000377a  lea     rcx, [rax+24h]; void *
0x18000377e  mov     r8, r13; Size
0x180003781  mov     word ptr [rax], 38h ; '8'
0x180003786  mov     [rax+6], r13b
0x18000378a  mov     qword ptr [rbp+var_30], r13
0x18000378e  call    memcpy_0
0x180003793  mov     byte ptr [rbx+7], 12h
0x180003797  test    edi, edi
0x180003799  jz      loc_18000397F
0x18000379f  cmp     [rbp+arg_48], 0
0x1800037a6  setnz   al
0x1800037a9  mov     [rbx+8], al
0x1800037ac  mov     rdx, [rbp+arg_0]
0x1800037b0  mov     sil, 4
0x1800037b3  mov     r13d, [rbp+arg_28]
0x1800037b7  mov     [rbx+18h], r12
0x1800037bb  lea     r12, [rbx+24h]
0x1800037bf  mov     [rbx+0Ch], edi
0x1800037c2  mov     [rbx+10h], r13d
0x1800037c6  mov     dword ptr [rbx+20h], 40h ; '@'
0x1800037cd  cmp     dword ptr [rdx+0ECh], 0
0x1800037d4  jbe     short loc_1800037FC
0x1800037d6  mov     cl, [r12]; this
0x1800037da  lea     eax, [rcx+5Fh]
0x1800037dd  cmp     al, 1Eh
0x1800037df  ja      loc_1800038B7
0x1800037e5  mov     r8d, 40000201h
0x1800037eb  bt      r8d, eax
0x1800037ef  jnb     loc_1800038B7
0x1800037f5  mov     byte ptr [rdx+0A9h], 1
0x1800037fc  mov     rdx, [rbp+arg_8]; void *
0x180003800  lea     rax, [rbp+var_40]
0x180003804  mov     [rsp+80h+var_48], rax; unsigned int *
0x180003809  mov     r9, rbx; void *
0x18000380c  mov     [rsp+80h+var_50], 60h ; '`'; unsigned int
0x180003814  mov     r8d, 4D014h; unsigned int
0x18000381a  mov     [rsp+80h+var_58], rbx; void *
0x18000381f  mov     [rsp+80h+var_60], 60h ; '`'; unsigned int
0x180003827  mov     [rbp+var_40], 0
0x18000382e  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180003833  mov     edi, eax
0x180003835  test    r14, r14
0x180003838  jz      short loc_180003840
0x18000383a  mov     ecx, [rbx+0Ch]
0x18000383d  mov     [r14], ecx
0x180003840  cmp     edi, 0C0AA020Dh
0x180003846  jz      loc_180003988
0x18000384c  test    edi, edi
0x18000384e  js      loc_180003A20
0x180003854  test    byte ptr [rbx+2], 0FDh
0x180003858  jnz     loc_1800038E5
0x18000385e  lea     rdi, [rbx+40h]
0x180003862  mov     r14d, 12h
0x180003868  movzx   eax, byte ptr [rdi+7]
0x18000386c  mov     rdx, rdi; Src
0x18000386f  add     eax, 8
0x180003872  mov     rcx, r15; void *
0x180003875  cmp     eax, r14d
0x180003878  cmova   eax, r14d
0x18000387c  mov     r8d, eax; Size
0x18000387f  call    memcpy_0
0x180003884  test    byte ptr [r15+2], 0Fh
0x180003889  jnz     loc_180003A71
0x18000388f  xor     edi, edi
0x180003891  mov     rcx, rbx; hMem
0x180003894  call    cs:__imp_LocalFree
0x18000389a  mov     rbx, [rsp+80h+arg_18]
0x1800038a2  mov     eax, edi
0x1800038a4  add     rsp, 80h
0x1800038ab  pop     r15
0x1800038ad  pop     r14
0x1800038af  pop     r13
0x1800038b1  pop     r12
0x1800038b3  pop     rdi
0x1800038b4  pop     rsi
0x1800038b5  pop     rbp
0x1800038b6  retn
0x1800038b7  cmp     cl, sil
0x1800038ba  jz      loc_1800037F5
0x1800038c0  sub     cl, 2Ah ; '*'
0x1800038c3  cmp     cl, 31h ; '1'
0x1800038c6  ja      loc_1800037FC
0x1800038cc  mov     rax, 2420000000011h
0x1800038d6  bt      rax, rcx
0x1800038da  jnb     loc_1800037FC
0x1800038e0  jmp     loc_1800037F5
0x1800038e5  mov     edi, 0C0AA02FFh
0x1800038ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f1  lea     rax, WPP_GLOBAL_Control
0x1800038f8  cmp     rcx, rax
0x1800038fb  jz      short loc_180003891
0x1800038fd  test    [rcx+0BCh], sil
0x180003904  jz      short loc_180003891
0x180003906  cmp     byte ptr [rcx+0B9h], 1
0x18000390d  jb      short loc_180003891
0x18000390f  movzx   r9d, byte ptr [rbx+2]
0x180003914  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000391b  mov     rcx, [rcx+0B0h]
0x180003922  mov     edx, 1Ah
0x180003927  mov     [rsp+80h+var_60], edi
0x18000392b  call    WPP_SF_Dd
0x180003930  jmp     loc_180003891
0x180003935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000393c  lea     rax, WPP_GLOBAL_Control
0x180003943  cmp     rcx, rax
0x180003946  jz      short loc_180003975
0x180003948  mov     sil, 4
0x18000394b  test    [rcx+0BCh], sil
0x180003952  jz      short loc_180003975
0x180003954  cmp     byte ptr [rcx+0B9h], 3
0x18000395b  jb      short loc_180003975
0x18000395d  mov     rcx, [rcx+0B0h]
0x180003964  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000396b  mov     edx, 17h
0x180003970  call    WPP_SF_
0x180003975  mov     edi, 8007000Eh
0x18000397a  jmp     loc_18000389A
0x18000397f  mov     byte ptr [rbx+8], 2
0x180003983  jmp     loc_1800037AC
0x180003988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000398f  lea     rax, WPP_GLOBAL_Control
0x180003996  cmp     rcx, rax
0x180003999  jz      loc_180003891
0x18000399f  test    [rcx+0BCh], sil
0x1800039a6  jz      loc_180003891
0x1800039ac  cmp     byte ptr [rcx+0B9h], 3
0x1800039b3  jb      loc_180003891
0x1800039b9  mov     rdx, qword ptr [rbp+var_30]
0x1800039bd  lea     rcx, [rbp+var_10]
0x1800039c1  mov     r8, r12
0x1800039c4  lea     r10, [rbx+40h]
0x1800039c8  xor     r9d, r9d
0x1800039cb  call    ?LOG_BLOB@@YA?AU_IMAPI_BLOB@@_KPEBX@Z; LOG_BLOB(unsigned __int64,void const *)
0x1800039d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039d7  lea     r14d, [r9+12h]
0x1800039db  movups  xmm0, xmmword ptr [rax]
0x1800039de  mov     dword ptr [rbp+var_30+2], r9d
0x1800039e2  lea     rax, [rbp+var_30]
0x1800039e6  mov     qword ptr [rsp+80h+var_50], rax
0x1800039eb  lea     rax, [rbp+var_20]
0x1800039ef  mov     word ptr [rbp+var_30+6], r9w
0x1800039f4  mov     r9d, r13d
0x1800039f7  mov     word ptr [rbp+var_30], r14w
0x1800039fc  mov     qword ptr [rbp+var_30+8], r10
0x180003a00  movdqu  [rbp+var_20], xmm0
0x180003a05  mov     rcx, [rcx+0B0h]
0x180003a0c  mov     [rsp+80h+var_58], rax
0x180003a11  mov     [rsp+80h+var_60], r13d
0x180003a16  call    WPP_SF_dD_HEX__HEX_
0x180003a1b  jmp     loc_180003891
0x180003a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a27  lea     rax, WPP_GLOBAL_Control
0x180003a2e  cmp     rcx, rax
0x180003a31  jz      loc_180003891
0x180003a37  test    [rcx+0BCh], sil
0x180003a3e  jz      loc_180003891
0x180003a44  cmp     byte ptr [rcx+0B9h], 3
0x180003a4b  jb      loc_180003891
0x180003a51  mov     rcx, [rcx+0B0h]
0x180003a58  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003a5f  mov     edx, 19h
0x180003a64  mov     r9d, edi
0x180003a67  call    WPP_SF_d
0x180003a6c  jmp     loc_180003891
0x180003a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a78  lea     rax, WPP_GLOBAL_Control
0x180003a7f  cmp     rcx, rax
0x180003a82  jz      short loc_180003AEC
0x180003a84  test    [rcx+0BCh], sil
0x180003a8b  jz      short loc_180003AEC
0x180003a8d  cmp     [rcx+0B9h], sil
0x180003a94  jb      short loc_180003AEC
0x180003a96  mov     rdx, qword ptr [rbp+var_30]
0x180003a9a  lea     rcx, [rbp+var_10]
0x180003a9e  xor     eax, eax
0x180003aa0  mov     word ptr [rbp+var_20], r14w
0x180003aa5  mov     r8, r12
0x180003aa8  mov     dword ptr [rbp+var_20+2], eax
0x180003aab  mov     word ptr [rbp+var_20+6], ax
0x180003aaf  mov     qword ptr [rbp+var_20+8], rdi
0x180003ab3  call    ?LOG_BLOB@@YA?AU_IMAPI_BLOB@@_KPEBX@Z; LOG_BLOB(unsigned __int64,void const *)
0x180003ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003abf  lea     r9, [rbp+var_30]
0x180003ac3  mov     edx, 1Bh
0x180003ac8  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003acf  movups  xmm0, xmmword ptr [rax]
0x180003ad2  mov     rcx, [rcx+0B0h]
0x180003ad9  lea     rax, [rbp+var_20]
0x180003add  mov     qword ptr [rsp+80h+var_60], rax
0x180003ae2  movdqu  [rbp+var_30], xmm0
0x180003ae7  call    WPP_SF__HEX__HEX_
0x180003aec  mov     edi, 0AA0200h
0x180003af1  jmp     loc_180003891
```
