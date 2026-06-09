# CIVIAudioCodec::DecodeMPEG(uchar *,long,int,eSTM_TYPE,uchar *,uchar)

- ea: `0x18001bb60`
- end: `0x18001c2e4`
- name: `?DecodeMPEG@CIVIAudioCodec@@IEAAJPEAEJHW4eSTM_TYPE@@0E@Z`
- size: `1924`
- prototype: `__int64 __fastcall(__int64, char *, int, __int64, int, unsigned int *, char)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001ab80`

## callees

- `0x180001360`
- `0x1800017b0`
- `0x180019030`
- `0x1800196c0`
- `0x18001bb60`
- `0x18001c8f0`
- `0x18001d200`
- `0x18002b6d0`
- `0x18002be50`
- `0x18002c550`
- `0x1800886fc`
- `0x180088708`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c24a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c24a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c213`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c213`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001c23a`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001c23a`

## pseudocode

```c
__int64 __fastcall CIVIAudioCodec::DecodeMPEG(
        __int64 a1,
        char *a2,
        int a3,
        __int64 a4,
        int a5,
        unsigned int *a6,
        char a7)
{
  unsigned int *v9; // rbx
  Mpegtoraw *v10; // rax
  int *v11; // rdx
  bool v12; // al
  unsigned int v13; // edx
  Mpegtoraw *v14; // rcx
  __int64 result; // rax
  __int64 v16; // rcx
  int v17; // r10d
  char v18; // r11
  int v19; // r13d
  _QWORD *v20; // rcx
  _QWORD *v21; // rbp
  __m128 si128; // xmm6
  unsigned int v23; // r9d
  const void **v24; // r15
  const void *v25; // rdx
  unsigned __int64 v26; // rcx
  int v27; // edi
  __int64 v28; // rsi
  char *v29; // rax
  unsigned int v30; // r8d
  __int64 v31; // rax
  int v32; // edx
  char *v33; // r15
  const void *v34; // rdx
  unsigned __int64 v35; // rcx
  int v36; // edi
  __int64 v37; // rsi
  __int64 v38; // rax
  int v39; // r15d
  int v40; // r15d
  const void *v41; // rdx
  unsigned __int64 v42; // rcx
  int v43; // edi
  __int64 v44; // rsi
  __int64 v45; // rax
  unsigned __int8 *v46; // rdx
  int mpeg_header; // eax
  _DWORD *v48; // rcx
  int *v49; // rsi
  int v50; // edi
  unsigned __int8 *v51; // rdx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  int v54; // ecx
  int v55; // eax
  unsigned __int8 *v56; // rdx
  Mpegtoraw *v57; // rcx
  int v58; // ecx
  int v59; // eax
  _QWORD *v60; // rcx
  int v61; // edx
  bool v62; // zf
  unsigned int v63; // edx
  __m128 *v64; // rax
  unsigned int v65; // ecx
  unsigned int v66; // [rsp+30h] [rbp-A8h]
  int v67; // [rsp+34h] [rbp-A4h]
  int v68; // [rsp+38h] [rbp-A0h]
  unsigned int v69; // [rsp+40h] [rbp-98h]
  int v70; // [rsp+44h] [rbp-94h]
  char *Src; // [rsp+48h] [rbp-90h]
  char v72; // [rsp+50h] [rbp-88h]
  unsigned int *v73; // [rsp+58h] [rbp-80h]
  unsigned __int8 *v74; // [rsp+60h] [rbp-78h] BYREF
  Mpegtoraw *v75; // [rsp+68h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-68h] BYREF

  v67 = a3;
  Src = a2;
  HIWORD(v68) = HIWORD(a3);
  v9 = a6;
  v73 = a6;
  v74 = 0;
  if ( !*(_QWORD *)(a1 + 6240) )
  {
    v10 = (Mpegtoraw *)operator new(0x259E0u);
    v75 = v10;
    if ( v10 )
      v10 = Mpegtoraw::Mpegtoraw(v10, v11);
    *(_QWORD *)(a1 + 6240) = v10;
    if ( !v10 )
      return 2147500037LL;
    v12 = Mpegtoraw::initialize(v10);
    v14 = *(Mpegtoraw **)(a1 + 6240);
    if ( !v12 )
    {
      if ( v14 )
        Mpegtoraw::`scalar deleting destructor'(v14, v13);
      *(_QWORD *)(a1 + 6240) = 0;
      return 2147500037LL;
    }
    *((_DWORD *)v14 + 33907) = 2;
    a3 = v67;
  }
  v16 = a2 - (char *)a6;
  if ( (unsigned __int64)(a2 - (char *)a6) > 0x7FFFFFFF || v16 + a3 < v16 )
    return 2147549183LL;
  v66 = 0;
  v17 = v16 + a3;
  v70 = v16 + a3;
  v18 = -8;
  if ( !*(_BYTE *)(a1 + 5720) )
    v18 = -32;
  v72 = v18;
  v19 = a3;
  v20 = (_QWORD *)(a1 + 104);
  v21 = (_QWORD *)(a1 + 104);
  si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v23) = a7;
  LOBYTE(v69) = a7;
  while ( 1 )
  {
    v24 = (const void **)(a1 + 96);
    if ( a5 )
    {
      v40 = 0;
      if ( v19 >= 0 )
        v40 = v19;
      v41 = *(const void **)(a1 + 96);
      v21 = (_QWORD *)(a1 + 104);
      v42 = *(_QWORD *)(a1 + 104) - (_QWORD)v41;
      if ( v42 > 0x7FFFFFFF )
      {
        v41 = (const void *)(a1 + 6864);
        *v21 = a1 + 6864;
        *(_QWORD *)(a1 + 96) = a1 + 6864;
        *(_QWORD *)(a1 + 88) = a1 + 6864;
        LODWORD(v42) = 0;
      }
      v43 = v40;
      if ( 8256 - (int)v42 < v40 )
        v43 = 8256 - v42;
      v44 = (int)v42;
      memmove_0(*(void **)(a1 + 88), v41, (int)v42);
      memcpy_0((void *)(v44 + *(_QWORD *)(a1 + 88)), Src, v43);
      v39 = v40 - v43;
      v19 = v39;
      Src += v43;
      v45 = *(_QWORD *)(a1 + 88);
      *(_QWORD *)(a1 + 96) = v45;
      *v21 = v44 + v43 + v45;
LABEL_47:
      v67 = v39;
    }
    else
    {
      if ( ((unsigned __int8)v23 & (unsigned __int8)v18) == -64 )
      {
        if ( v19 < 0 )
        {
          v19 = 0;
          v24 = (const void **)(a1 + 96);
          v21 = v20;
        }
        v25 = *v24;
        v26 = *v21 - (_QWORD)*v24;
        if ( v26 > 0x7FFFFFFF )
        {
          v25 = (const void *)(a1 + 6864);
          *v21 = a1 + 6864;
          *v24 = (const void *)(a1 + 6864);
          *(_QWORD *)(a1 + 88) = a1 + 6864;
          LODWORD(v26) = 0;
        }
        v27 = v19;
        if ( 8256 - (int)v26 < v19 )
          v27 = 8256 - v26;
        v28 = (int)v26;
        memmove_0(*(void **)(a1 + 88), v25, (int)v26);
        memcpy_0((void *)(v28 + *(_QWORD *)(a1 + 88)), Src, v27);
        v19 -= v27;
        Src += v27;
        v29 = *(char **)(a1 + 88);
        *v24 = v29;
        *v21 = &v29[v27 + v28];
        v9 = v73;
        a3 = v67;
        LOBYTE(v23) = v69;
        v17 = v70;
        v18 = v72;
      }
      v21 = (_QWORD *)(a1 + 104);
      while ( !v19 || ((unsigned __int8)v23 & (unsigned __int8)v18) != -64 )
      {
        v67 = a3 - v17;
        if ( a3 - v17 <= 16 )
        {
          v39 = 0;
          goto LABEL_47;
        }
        v9 = (unsigned int *)((char *)v9 + v17);
        v73 = v9;
        v30 = *v9;
        if ( (*v9 & 0xFFFFFF) != 0x10000 )
          break;
        LOBYTE(v68) = *((_BYTE *)v9 + 5);
        BYTE1(v68) = *((_BYTE *)v9 + 4);
        v31 = *((unsigned __int8 *)v9 + 8);
        v32 = v68 - v31 - 3;
        HIWORD(v68) = HIWORD(v32);
        v33 = (char *)v9 + v31 + 9;
        Src = v33;
        v17 = v31 + 9 + v32;
        v70 = v17;
        v23 = HIBYTE(v30);
        v69 = HIBYTE(v30);
        v19 = 0;
        if ( (HIBYTE(v30) & (unsigned __int8)v18) == -64 )
        {
          if ( v32 >= 0 )
            v19 = v32;
          v34 = *(const void **)(a1 + 96);
          v35 = *v21 - (_QWORD)v34;
          if ( v35 > 0x7FFFFFFF )
          {
            v34 = (const void *)(a1 + 6864);
            *v21 = a1 + 6864;
            *(_QWORD *)(a1 + 96) = a1 + 6864;
            *(_QWORD *)(a1 + 88) = a1 + 6864;
            LODWORD(v35) = 0;
          }
          v36 = v19;
          if ( 8256 - (int)v35 < v19 )
            v36 = 8256 - v35;
          v37 = (int)v35;
          memmove_0(*(void **)(a1 + 88), v34, (int)v35);
          memcpy_0((void *)(v37 + *(_QWORD *)(a1 + 88)), v33, v36);
          v19 -= v36;
          Src = &v33[v36];
          v38 = *(_QWORD *)(a1 + 88);
          *(_QWORD *)(a1 + 96) = v38;
          *v21 = v37 + v36 + v38;
          a3 = v67;
          LOBYTE(v23) = v69;
          v17 = v70;
          v18 = v72;
        }
        else
        {
          a3 = v67;
        }
      }
    }
    if ( !(unsigned int)CIVIAudioCodec::LookForSyncWord((CIVIAudioCodec *)a1) )
      return v66;
    v46 = *(unsigned __int8 **)(a1 + 96);
    if ( (unsigned __int64)(v46 + 3) > *v21 )
      return v66;
    mpeg_header = CIVIAudioCodec::get_mpeg_header((CIVIAudioCodec *)a1, v46);
    v48 = (_DWORD *)(a1 + 376);
    if ( mpeg_header == 2 )
    {
      *(_DWORD *)(a1 + 8) = 1;
    }
    else if ( !mpeg_header )
    {
      *(_QWORD *)(a1 + 96) = *v21;
      *v48 = 0;
      return 2147500037LL;
    }
    v49 = (int *)(a1 + 376);
    if ( *(_DWORD *)v21 - *(_DWORD *)(a1 + 96) < *v48 )
      return v66;
    result = CIVIAudioCodec::CheckModeChange((CIVIAudioCodec *)a1);
    if ( (int)result < 0 )
      return result;
    v50 = v66;
    if ( (unsigned int)CIVIAudioCodec::LookForSyncWord((CIVIAudioCodec *)a1) )
      break;
LABEL_89:
    a3 = v67;
    if ( v67 <= 0 )
      return (unsigned int)v50;
    v20 = (_QWORD *)(a1 + 104);
    v9 = v73;
    LOBYTE(v23) = v69;
    v17 = v70;
    v18 = v72;
  }
  while ( !*(_DWORD *)(a1 + 6344) )
  {
    v51 = *(unsigned __int8 **)(a1 + 96);
    if ( (unsigned __int64)(v51 + 4) > *v21 )
      goto LABEL_89;
    if ( *(_DWORD *)(a1 + 6220) == 4 )
    {
      v53 = *(_DWORD *)v51;
      v54 = *(_DWORD *)v51 & 0x600;
      if ( ((v54 - 512) & 0xFFFFFDFF) != 0 )
      {
        if ( v54 == 1536 )
          v52 = (v53 >> 15) & 4;
        else
          v52 = 0;
      }
      else
      {
        v52 = (v53 >> 17) & 1;
      }
    }
    else
    {
      v52 = 0;
    }
    v55 = CIVIAudioCodec::get_mpeg_header((CIVIAudioCodec *)a1, v51);
    if ( v55 == 2 )
    {
      *(_DWORD *)(a1 + 8) = 1;
    }
    else if ( !v55 )
    {
      v50 = -2147467259;
      v66 = -2147467259;
      goto LABEL_89;
    }
    if ( *(_QWORD *)(a1 + 96) + (unsigned __int64)v52 + *v49 > *v21 )
      goto LABEL_89;
    v50 = CIVIAudioCodec::CheckModeChange((CIVIAudioCodec *)a1);
    v66 = v50;
    if ( v50 < 0 )
      goto LABEL_89;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 **))(*(_QWORD *)a1 + 32LL))(
               a1,
               *(unsigned int *)(a1 + 5900),
               &v74);
    if ( (int)result < 0 )
      return result;
    v56 = *(unsigned __int8 **)(a1 + 96);
    if ( !v56 || !v74 || (v57 = *(Mpegtoraw **)(a1 + 6240)) == 0 || (int)Mpegtoraw::run(v57, v56, v52 + *v49, v74) < 32 )
    {
      v60 = (_QWORD *)(a1 + 96);
LABEL_84:
      *v60 = *v21;
      *v49 = 0;
      v50 = -2147467259;
      v66 = -2147467259;
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, 7, -2147024809, 0);
      LODWORD(v75) = -2147467259;
      UserData.Ptr = (ULONGLONG)&v75;
      *(_QWORD *)&UserData.Size = 4;
      if ( a1 != -24 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
        if ( !*(_DWORD *)(a1 + 24) )
          EventWrite(*(_QWORD *)(a1 + 32), &MSMPEG2ADEC_AUDDECODE_FRAME_ERROR, 1u, &UserData);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
      }
      goto LABEL_89;
    }
    *(_DWORD *)(a1 + 6248) = (*(_DWORD *)(a1 + 5724) != 3) + 1;
    *(_DWORD *)(a1 + 6252) = 0;
    v58 = *(_DWORD *)(*(_QWORD *)(a1 + 6240) + 135624LL);
    *(_DWORD *)(a1 + 5728) = v58;
    if ( v58 != *(_DWORD *)(a1 + 5732) )
    {
      *(_DWORD *)(a1 + 8) = 1;
      *(_DWORD *)(a1 + 5732) = v58;
    }
    v59 = CIVIAudioCodec::CheckModeChange((CIVIAudioCodec *)a1);
    v60 = (_QWORD *)(a1 + 96);
    if ( v59 < 0 )
      goto LABEL_84;
    *(_QWORD *)(a1 + 96) += (int)(v52 + *v49);
    v61 = *(_DWORD *)(a1 + 5904);
    v62 = 2 * v61 == 0;
    v63 = 2 * v61;
    v64 = (__m128 *)v74;
    v65 = 0;
    if ( !v62 )
    {
      do
      {
        *v64 = _mm_mul_ps(si128, *v64);
        ++v64;
        v65 += 4;
      }
      while ( v65 < v63 );
    }
    v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 64LL))(
            a1,
            *(unsigned int *)(a1 + 5900),
            *(_QWORD *)(a1 + 112));
    v66 = v50;
    if ( v50 < 0 || !(unsigned int)CIVIAudioCodec::LookForSyncWord((CIVIAudioCodec *)a1) )
      goto LABEL_89;
  }
  return (unsigned int)v50;
}

```

## disassembly

```asm
0x18001bb60  mov     [rsp+arg_18], rbx
0x18001bb65  push    rbp
0x18001bb66  push    rsi
0x18001bb67  push    rdi
0x18001bb68  push    r12
0x18001bb6a  push    r13
0x18001bb6c  push    r14
0x18001bb6e  push    r15
0x18001bb70  sub     rsp, 0A0h
0x18001bb77  movaps  [rsp+0D8h+var_48], xmm6
0x18001bb7f  mov     rax, cs:__security_cookie
0x18001bb86  xor     rax, rsp
0x18001bb89  mov     [rsp+0D8h+var_58], rax
0x18001bb91  mov     [rsp+0D8h+var_A4], r8d
0x18001bb96  mov     rdi, rdx
0x18001bb99  mov     [rsp+0D8h+Src], rdx
0x18001bb9e  mov     r14, rcx
0x18001bba1  mov     [rsp+0D8h+var_A0], r8d
0x18001bba6  mov     rbx, [rsp+0D8h+arg_28]
0x18001bbae  mov     [rsp+0D8h+var_80], rbx
0x18001bbb3  mov     [rsp+0D8h+var_78], 0
0x18001bbbc  cmp     qword ptr [rcx+1860h], 0
0x18001bbc4  jnz     short loc_18001BC32
0x18001bbc6  mov     ecx, 259E0h; Size
0x18001bbcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bbd0  mov     [rsp+0D8h+var_70], rax
0x18001bbd5  test    rax, rax
0x18001bbd8  jz      short loc_18001BBE3
0x18001bbda  mov     rcx, rax; this
0x18001bbdd  call    ??0Mpegtoraw@@QEAA@PEAJ@Z; Mpegtoraw::Mpegtoraw(long *)
0x18001bbe2  nop
0x18001bbe3  mov     [r14+1860h], rax
0x18001bbea  test    rax, rax
0x18001bbed  jz      short loc_18001BC17
0x18001bbef  mov     rcx, rax; this
0x18001bbf2  call    ?initialize@Mpegtoraw@@QEAA_NXZ; Mpegtoraw::initialize(void)
0x18001bbf7  mov     rcx, [r14+1860h]; this
0x18001bbfe  test    al, al
0x18001bc00  jnz     short loc_18001BC23
0x18001bc02  test    rcx, rcx
0x18001bc05  jz      short loc_18001BC0C
0x18001bc07  call    ??_GMpegtoraw@@QEAAPEAXI@Z; Mpegtoraw::`scalar deleting destructor'(uint)
0x18001bc0c  mov     qword ptr [r14+1860h], 0
0x18001bc17  mov     edi, 80004005h
0x18001bc1c  mov     eax, edi
0x18001bc1e  jmp     loc_18001C2B0
0x18001bc23  mov     dword ptr [rcx+211CCh], 2
0x18001bc2d  mov     r8d, [rsp+0D8h+var_A4]
0x18001bc32  mov     rcx, rdi
0x18001bc35  sub     rcx, rbx
0x18001bc38  cmp     rcx, 7FFFFFFFh
0x18001bc3f  ja      loc_18001C2AB
0x18001bc45  movsxd  rax, r8d
0x18001bc48  add     rax, rcx
0x18001bc4b  cmp     rax, rcx
0x18001bc4e  jl      loc_18001C2AB
0x18001bc54  mov     [rsp+0D8h+var_A8], 0
0x18001bc5c  lea     r10d, [rcx+r8]
0x18001bc60  mov     [rsp+0D8h+var_94], r10d
0x18001bc65  mov     eax, 0E0h
0x18001bc6a  mov     r11d, 0F8h
0x18001bc70  cmp     byte ptr [r14+1658h], 0
0x18001bc78  cmovz   r11d, eax
0x18001bc7c  mov     dword ptr [rsp+0D8h+var_88], r11d
0x18001bc81  mov     r13d, r8d
0x18001bc84  lea     rcx, [r14+68h]
0x18001bc88  mov     rbp, rcx
0x18001bc8b  movdqa  xmm6, cs:__xmm@38000000380000003800000038000000
0x18001bc93  movzx   r9d, [rsp+0D8h+arg_30]
0x18001bc9c  mov     [rsp+0D8h+var_98], r9d
0x18001bca1  lea     r15, [r14+60h]
0x18001bca5  cmp     [rsp+0D8h+arg_20], 0
0x18001bcad  jnz     loc_18001BEB9
0x18001bcb3  movzx   eax, r11b
0x18001bcb7  and     al, r9b
0x18001bcba  cmp     al, 0C0h
0x18001bcbc  jnz     loc_18001BD61
0x18001bcc2  test    r13d, r13d
0x18001bcc5  jns     short loc_18001BCD1
0x18001bcc7  xor     r13d, r13d
0x18001bcca  lea     r15, [r14+60h]
0x18001bcce  mov     rbp, rcx
0x18001bcd1  mov     rdx, [r15]
0x18001bcd4  mov     rcx, [rbp+0]
0x18001bcd8  sub     rcx, rdx
0x18001bcdb  cmp     rcx, 7FFFFFFFh
0x18001bce2  jbe     short loc_18001BCF8
0x18001bce4  lea     rdx, [r14+1AD0h]; Src
0x18001bceb  mov     [rbp+0], rdx
0x18001bcef  mov     [r15], rdx
0x18001bcf2  mov     [r14+58h], rdx
0x18001bcf6  xor     ecx, ecx
0x18001bcf8  mov     eax, 2040h
0x18001bcfd  sub     eax, ecx
0x18001bcff  mov     edi, r13d
0x18001bd02  cmp     eax, r13d
0x18001bd05  cmovl   edi, eax
0x18001bd08  movsxd  rsi, ecx
0x18001bd0b  mov     r8, rsi; Size
0x18001bd0e  mov     rcx, [r14+58h]; void *
0x18001bd12  call    memmove_0
0x18001bd17  movsxd  rbx, edi
0x18001bd1a  mov     rcx, [r14+58h]
0x18001bd1e  add     rcx, rsi; void *
0x18001bd21  mov     r8, rbx; Size
0x18001bd24  mov     rdx, [rsp+0D8h+Src]; Src
0x18001bd29  call    memcpy_0
0x18001bd2e  sub     r13d, edi
0x18001bd31  add     [rsp+0D8h+Src], rbx
0x18001bd36  mov     rax, [r14+58h]
0x18001bd3a  mov     [r15], rax
0x18001bd3d  lea     rcx, [rbx+rax]
0x18001bd41  add     rcx, rsi
0x18001bd44  mov     [rbp+0], rcx
0x18001bd48  mov     rbx, [rsp+0D8h+var_80]
0x18001bd4d  mov     r8d, [rsp+0D8h+var_A4]
0x18001bd52  mov     r9d, [rsp+0D8h+var_98]
0x18001bd57  mov     r10d, [rsp+0D8h+var_94]
0x18001bd5c  mov     r11d, dword ptr [rsp+0D8h+var_88]
0x18001bd61  lea     rbp, [r14+68h]
0x18001bd65  test    r13d, r13d
0x18001bd68  jz      short loc_18001BD79
0x18001bd6a  movzx   eax, r11b
0x18001bd6e  and     al, r9b
0x18001bd71  cmp     al, 0C0h
0x18001bd73  jz      loc_18001BF49
0x18001bd79  sub     r8d, r10d
0x18001bd7c  mov     [rsp+0D8h+var_A4], r8d
0x18001bd81  cmp     r8d, 10h
0x18001bd85  jle     loc_18001BEB1
0x18001bd8b  movsxd  rax, r10d
0x18001bd8e  add     rbx, rax
0x18001bd91  mov     [rsp+0D8h+var_80], rbx
0x18001bd96  mov     r8d, [rbx]
0x18001bd99  mov     eax, r8d
0x18001bd9c  and     eax, 0FFFFFFh
0x18001bda1  cmp     eax, 10000h
0x18001bda6  jnz     loc_18001BF49
0x18001bdac  movzx   eax, byte ptr [rbx+5]
0x18001bdb0  mov     byte ptr [rsp+0D8h+var_A0], al
0x18001bdb4  movzx   eax, byte ptr [rbx+4]
0x18001bdb8  mov     byte ptr [rsp+0D8h+var_A0+1], al
0x18001bdbc  movzx   eax, byte ptr [rbx+8]
0x18001bdc0  mov     ecx, [rsp+0D8h+var_A0]
0x18001bdc4  sub     ecx, eax
0x18001bdc6  lea     edx, [rcx-3]
0x18001bdc9  mov     [rsp+0D8h+var_A0], edx
0x18001bdcd  lea     r15, [rax+9]
0x18001bdd1  add     r15, rbx
0x18001bdd4  mov     [rsp+0D8h+Src], r15
0x18001bdd9  mov     eax, r15d
0x18001bddc  sub     eax, ebx
0x18001bdde  lea     r10d, [rcx-3]
0x18001bde2  add     r10d, eax
0x18001bde5  mov     [rsp+0D8h+var_94], r10d
0x18001bdea  mov     r9d, r8d
0x18001bded  shr     r9d, 18h
0x18001bdf1  mov     [rsp+0D8h+var_98], r9d
0x18001bdf6  movzx   eax, r11b
0x18001bdfa  and     al, r9b
0x18001bdfd  xor     r13d, r13d
0x18001be00  cmp     al, 0C0h
0x18001be02  jnz     loc_18001BEA7
0x18001be08  test    edx, edx
0x18001be0a  cmovns  r13d, edx
0x18001be0e  mov     rdx, [r14+60h]
0x18001be12  mov     rcx, [rbp+0]
0x18001be16  sub     rcx, rdx
0x18001be19  cmp     rcx, 7FFFFFFFh
0x18001be20  jbe     short loc_18001BE37
0x18001be22  lea     rdx, [r14+1AD0h]; Src
0x18001be29  mov     [rbp+0], rdx
0x18001be2d  mov     [r14+60h], rdx
0x18001be31  mov     [r14+58h], rdx
0x18001be35  xor     ecx, ecx
0x18001be37  mov     eax, 2040h
0x18001be3c  sub     eax, ecx
0x18001be3e  mov     edi, r13d
0x18001be41  cmp     eax, r13d
0x18001be44  cmovl   edi, eax
0x18001be47  movsxd  rsi, ecx
0x18001be4a  mov     r8, rsi; Size
0x18001be4d  mov     rcx, [r14+58h]; void *
0x18001be51  call    memmove_0
0x18001be56  movsxd  rbx, edi
0x18001be59  mov     rcx, [r14+58h]
0x18001be5d  add     rcx, rsi; void *
0x18001be60  mov     r8, rbx; Size
0x18001be63  mov     rdx, r15; Src
0x18001be66  call    memcpy_0
0x18001be6b  sub     r13d, edi
0x18001be6e  add     r15, rbx
0x18001be71  mov     [rsp+0D8h+Src], r15
0x18001be76  mov     rax, [r14+58h]
0x18001be7a  mov     [r14+60h], rax
0x18001be7e  lea     rcx, [rbx+rax]
0x18001be82  add     rcx, rsi
0x18001be85  mov     [rbp+0], rcx
0x18001be89  mov     rbx, [rsp+0D8h+var_80]
0x18001be8e  mov     r8d, [rsp+0D8h+var_A4]
0x18001be93  mov     r9d, [rsp+0D8h+var_98]
0x18001be98  mov     r10d, [rsp+0D8h+var_94]
0x18001be9d  mov     r11d, dword ptr [rsp+0D8h+var_88]
0x18001bea2  jmp     loc_18001BD65
0x18001bea7  mov     r8d, [rsp+0D8h+var_A4]
0x18001beac  jmp     loc_18001BD65
0x18001beb1  xor     r15d, r15d
0x18001beb4  jmp     loc_18001BF44
0x18001beb9  xor     r15d, r15d
0x18001bebc  test    r13d, r13d
0x18001bebf  cmovns  r15d, r13d
0x18001bec3  mov     rdx, [r14+60h]
0x18001bec7  lea     rbp, [r14+68h]
0x18001becb  mov     rcx, [rbp+0]
0x18001becf  sub     rcx, rdx
0x18001bed2  cmp     rcx, 7FFFFFFFh
0x18001bed9  jbe     short loc_18001BEF0
0x18001bedb  lea     rdx, [r14+1AD0h]; Src
0x18001bee2  mov     [rbp+0], rdx
0x18001bee6  mov     [r14+60h], rdx
0x18001beea  mov     [r14+58h], rdx
0x18001beee  xor     ecx, ecx
0x18001bef0  mov     eax, 2040h
0x18001bef5  sub     eax, ecx
0x18001bef7  mov     edi, r15d
0x18001befa  cmp     eax, r15d
0x18001befd  cmovl   edi, eax
0x18001bf00  movsxd  rsi, ecx
0x18001bf03  mov     r8, rsi; Size
0x18001bf06  mov     rcx, [r14+58h]; void *
0x18001bf0a  call    memmove_0
0x18001bf0f  movsxd  rbx, edi
0x18001bf12  mov     rcx, [r14+58h]
0x18001bf16  add     rcx, rsi; void *
0x18001bf19  mov     r8, rbx; Size
0x18001bf1c  mov     rdx, [rsp+0D8h+Src]; Src
0x18001bf21  call    memcpy_0
0x18001bf26  sub     r15d, edi
0x18001bf29  mov     r13d, r15d
0x18001bf2c  add     [rsp+0D8h+Src], rbx
0x18001bf31  mov     rax, [r14+58h]
0x18001bf35  mov     [r14+60h], rax
0x18001bf39  lea     rcx, [rbx+rax]
0x18001bf3d  add     rcx, rsi
0x18001bf40  mov     [rbp+0], rcx
0x18001bf44  mov     [rsp+0D8h+var_A4], r15d
0x18001bf49  mov     rcx, r14; this
0x18001bf4c  call    ?LookForSyncWord@CIVIAudioCodec@@IEAAHXZ; CIVIAudioCodec::LookForSyncWord(void)
0x18001bf51  test    eax, eax
0x18001bf53  jz      loc_18001C2A3
0x18001bf59  mov     rdx, [r14+60h]; unsigned __int8 *
0x18001bf5d  lea     rax, [rdx+3]
0x18001bf61  cmp     rax, [rbp+0]
0x18001bf65  ja      loc_18001C2A3
0x18001bf6b  mov     rcx, r14; this
0x18001bf6e  call    ?get_mpeg_header@CIVIAudioCodec@@AEAAHPEAE@Z; CIVIAudioCodec::get_mpeg_header(uchar *)
0x18001bf73  lea     rcx, [r14+178h]
0x18001bf7a  cmp     eax, 2
0x18001bf7d  jnz     short loc_18001BF89
0x18001bf7f  mov     dword ptr [r14+8], 1
0x18001bf87  jmp     short loc_18001BF91
0x18001bf89  test    eax, eax
0x18001bf8b  jz      loc_18001C28C
0x18001bf91  mov     rsi, rcx
0x18001bf94  mov     eax, [rbp+0]
0x18001bf97  sub     eax, [r14+60h]
0x18001bf9b  cmp     eax, [rcx]
0x18001bf9d  jl      loc_18001C2A3
0x18001bfa3  mov     rcx, r14; this
0x18001bfa6  call    ?CheckModeChange@CIVIAudioCodec@@IEAAJXZ; CIVIAudioCodec::CheckModeChange(void)
0x18001bfab  test    eax, eax
0x18001bfad  js      loc_18001C288
0x18001bfb3  mov     rcx, r14; this
0x18001bfb6  call    ?LookForSyncWord@CIVIAudioCodec@@IEAAHXZ; CIVIAudioCodec::LookForSyncWord(void)
0x18001bfbb  mov     edi, [rsp+0D8h+var_A8]
0x18001bfbf  test    eax, eax
0x18001bfc1  jz      loc_18001C261
0x18001bfc7  xor     r15d, r15d
0x18001bfca  nop     word ptr [rax+rax+00h]
0x18001bfd0  cmp     [r14+18C8h], r15d
0x18001bfd7  jnz     loc_18001C2A7
0x18001bfdd  mov     rdx, [r14+60h]; unsigned __int8 *
0x18001bfe1  lea     rax, [rdx+4]
0x18001bfe5  cmp     rax, [rbp+0]
0x18001bfe9  ja      loc_18001C261
0x18001bfef  cmp     dword ptr [r14+184Ch], 4
0x18001bff7  jz      short loc_18001BFFE
0x18001bff9  mov     ebx, r15d
0x18001bffc  jmp     short loc_18001C030
0x18001bffe  mov     ebx, [rdx]
0x18001c000  mov     ecx, ebx
0x18001c002  and     ecx, 600h
0x18001c008  lea     eax, [rcx-200h]
0x18001c00e  test    eax, 0FFFFFDFFh
0x18001c013  jz      short loc_18001C02A
0x18001c015  cmp     ecx, 600h
0x18001c01b  jz      short loc_18001C022
0x18001c01d  mov     ebx, r15d
0x18001c020  jmp     short loc_18001C030
0x18001c022  shr     ebx, 0Fh
  ... truncated ...
```
