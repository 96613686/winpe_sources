# CClfsMarshallingContext::AppendRecord(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,ulong,_CLFS_RECORD_HEADER * &,ulong &,ulong &,ulong &)

- ea: `0x18000e8e4`
- end: `0x18000ef99`
- name: `?AppendRecord@CClfsMarshallingContext@@AEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JKAEAPEAU_CLFS_RECORD_HEADER@@AEAK33@Z`
- size: `1717`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, struct _CLS_WRITE_ENTRY *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, __int64 *const, char, struct _CLFS_RECORD_HEADER **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180013178`
- `0x180014328`

## callees

- `0x1800026c6`
- `0x18000e8e4`
- `0x18000f3f8`
- `0x1800106f8`
- `0x1800135a4`
- `0x180014dce`

## pseudocode

```c
unsigned int __fastcall CClfsMarshallingContext::AppendRecord(
        CClfsMarshallingContext *this,
        struct _CLS_WRITE_ENTRY *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 *const a6,
        char a7,
        CLFS_LSN **a8,
        unsigned int *a9,
        unsigned int *a10,
        unsigned int *a11)
{
  unsigned __int64 v11; // r14
  __int64 v13; // r10
  int v14; // r13d
  int v15; // esi
  __int64 v16; // r15
  __int64 v17; // r11
  signed __int64 v18; // rdx
  unsigned int result; // eax
  int v20; // r11d
  unsigned int v21; // edi
  int v22; // r8d
  int v23; // ecx
  unsigned __int64 v24; // r12
  __int64 v25; // rdx
  int v26; // r11d
  unsigned int v27; // esi
  unsigned int v28; // r13d
  unsigned int v29; // edx
  ULONG ByteLength; // ecx
  int v31; // ecx
  unsigned int v32; // r8d
  unsigned int v33; // r9d
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // r8d
  unsigned int v37; // eax
  unsigned __int64 v38; // r12
  __int64 v39; // r14
  unsigned int v40; // esi
  __int64 v41; // rax
  unsigned __int64 v42; // r14
  CLFS_LSN *v43; // rax
  unsigned int v44; // edx
  __int64 v45; // rax
  PVOID Buffer; // rdx
  size_t v47; // rcx
  int v48; // esi
  unsigned __int64 v49; // r14
  __int64 v50; // r10
  unsigned int v51; // r9d
  __int64 v52; // r8
  __int64 v53; // rax
  unsigned int v54; // edx
  int v55; // r8d
  CLFS_LSN v56; // rax
  CLFS_LSN *v57; // r9
  CLFS_LSN *v58; // rcx
  CLFS_CONTAINER_ID *p_cidContainer; // rdx
  ULONGLONG *p_ullOffset; // r8
  unsigned int cidContainer; // eax
  __int64 i; // r11
  signed __int64 v63; // rdx
  __int64 v64; // r11
  unsigned __int64 v65; // rax
  unsigned int v66; // [rsp+20h] [rbp-30h]
  int v67; // [rsp+24h] [rbp-2Ch]
  unsigned __int64 v68; // [rsp+28h] [rbp-28h] BYREF
  __int64 v69; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v70; // [rsp+38h] [rbp-18h] BYREF
  struct _CLFS_RECORD_HEADER *v71; // [rsp+40h] [rbp-10h] BYREF
  int v74; // [rsp+A8h] [rbp+58h]

  v74 = a4;
  v11 = 0;
  v71 = 0;
  *a8 = 0;
  v70 = 0;
  v68 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  if ( a5 && !a6 )
    return 87;
  v13 = *((_QWORD *)this + 20);
  v69 = v13;
  v14 = *(_DWORD *)(v13 + 76);
  if ( ((v14 + 1) & 0xFFFFFE00) == 0 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v67 = 0;
    if ( a5 )
    {
      while ( 1 )
      {
        v18 = a6[v17];
        if ( !v18 )
          return 87;
        if ( v18 >= 0 )
        {
          result = CClfsMarshallingContext::CalculateReservationForRecord(this, v18, &v68);
          v66 = result;
          v21 = result;
          if ( result )
            return result;
          v16 += v68;
          ++v15;
        }
        else
        {
          result = CClfsMarshallingContext::CalculateReservationForRecord(this, -v18, &v68);
          v66 = result;
          v21 = result;
          if ( result )
            return result;
          v16 -= v68;
          --v15;
        }
        v17 = (unsigned int)(v20 + 1);
        v67 = v15;
        if ( (unsigned int)v17 >= a5 )
        {
          v13 = v69;
          a4 = v74;
          goto LABEL_13;
        }
      }
    }
    v21 = 0;
    v66 = 0;
LABEL_13:
    v22 = *((_DWORD *)this + 38);
    v23 = v22 + v15;
    if ( v22 + v15 < 0 )
      return 6625;
    v24 = *((_QWORD *)this + 22);
    v25 = v24 + v16;
    if ( (__int64)(v24 + v16) < 0 )
      return 6626;
    v26 = *((_DWORD *)this + 34);
    if ( v25 < (unsigned int)(v26 * v23) || v25 > 0 && !v23 )
      return 6615;
    v27 = 0;
    if ( a3 )
    {
      v28 = a3;
      v29 = 0;
      do
      {
        ByteLength = a2[v29].ByteLength;
        if ( ByteLength && !a2[v29].Buffer )
          return 1784;
        if ( a4 )
          v31 = -a4 & (a4 + ByteLength - 1);
        else
          v31 = 0;
        v27 += v31;
        ++v29;
      }
      while ( v29 < a3 );
      v66 = CClfsMarshallingContext::CalculateReservationForRecord(this, v27, &v70);
      v21 = v66;
      if ( v66 )
      {
        if ( v66 == 6615 )
          return 122;
        return v21;
      }
      v13 = v69;
      v27 = (v27 + 47) & 0xFFFFFFF8;
      v32 = v27 + *(_DWORD *)(v69 + 72);
      v33 = v32 / 0x1FE + 1;
      if ( v32 == 510 * (v32 / 0x1FE) )
        v33 = v32 / 0x1FE;
      if ( v26 )
        v34 = ~(v26 - 1) & (v26 - 1 + ((2 * v33 + 7) & 0xFFFFFFF8) + v32);
      else
        v34 = 0;
      v11 = v70;
      v22 = *((_DWORD *)this + 38);
    }
    else
    {
      if ( v14 )
      {
        v35 = *(_DWORD *)(v13 + 72) / 0x1FEu;
        v36 = v35 + 1;
        if ( *(_DWORD *)(v13 + 72) == 510 * v35 )
          v36 = *(_DWORD *)(v13 + 72) / 0x1FEu;
        if ( v26 )
          v34 = ~(v26 - 1) & (v26 - 1 + ((2 * v36 + 7) & 0xFFFFFFF8) + *(_DWORD *)(v13 + 72));
        else
          v34 = 0;
        v22 = *((_DWORD *)this + 38);
      }
      else
      {
        v34 = 0;
      }
      v28 = 0;
    }
    v37 = *((_DWORD *)this + 33);
    if ( v27 > v37 )
      return 122;
    if ( v34 <= v37 )
    {
      if ( (a7 & 4) == 0 )
      {
        v39 = v16 + *(_QWORD *)(v13 + 80) - *((_QWORD *)this + 24) + v34;
        v69 = v39;
        if ( v39 <= 0 )
          goto LABEL_66;
        if ( v26 )
          v40 = -v26 & (v26 + *((_DWORD *)this + 32) + 983);
        else
          v40 = 0;
        v70 = v39 + v40;
        v66 = CClfsMarshallingContext::ReserveLogSpace(this, (const __int64 *)&v70);
        v21 = v66;
        if ( v66 )
        {
          result = CClfsMarshallingContext::ReserveLogSpace(this, &v69);
          v66 = result;
          v21 = result;
          if ( result )
            return result;
          v40 = 0;
        }
        *((_QWORD *)this + 24) += v39 + v40;
        goto LABEL_66;
      }
      if ( v22 )
      {
        if ( v11 <= v24 )
        {
          v38 = v24 - v11;
          if ( v38 >= (unsigned int)((v22 - 1) * v26) && (!v38 || v22 != 1) )
          {
            *(_QWORD *)(v13 + 80) -= v11;
            *((_QWORD *)this + 22) -= v11;
            --*((_DWORD *)this + 38);
LABEL_66:
            *(_QWORD *)(*((_QWORD *)this + 20) + 80LL) += v16;
            *((_DWORD *)this + 38) += v67;
            *((_QWORD *)this + 22) += v16;
            if ( v28 )
            {
              v41 = *((_QWORD *)this + 20);
              v42 = *(_QWORD *)(v41 + 64);
              *a8 = (CLFS_LSN *)(v42 + *(unsigned int *)(v41 + 72));
              *a11 += 40;
              v43 = *a8;
              v44 = 0;
              v70 = v42;
              WORD1(v43[4].ullOffset) = 40;
              *a9 = 0;
              do
              {
                if ( *a11 + *(_DWORD *)(*((_QWORD *)this + 20) + 72LL) >= *((_DWORD *)this + 33) )
                  break;
                v45 = v44;
                Buffer = a2[v44].Buffer;
                v47 = a2[v45].ByteLength;
                *a10 = v47;
                v48 = v74 ? -v74 & (v47 + v74 - 1) : 0;
                memcpy_0(
                  (void *)(*a11
                         + *(_QWORD *)(*((_QWORD *)this + 20) + 64LL)
                         + *(unsigned int *)(*((_QWORD *)this + 20) + 72LL)),
                  Buffer,
                  v47);
                memset_0(
                  (void *)(*a11
                         + *a10
                         + *(_QWORD *)(*((_QWORD *)this + 20) + 64LL)
                         + *(unsigned int *)(*((_QWORD *)this + 20) + 72LL)),
                  0,
                  v48 - *a10);
                *a11 += v48;
                v44 = ++*a9;
              }
              while ( *a9 < a3 );
              (*a8)[3].offset.idxRecord = *a11;
              CLogIocb::GetLastRecord(*((CLogIocb **)this + 20), &v71);
              if ( v71 )
                *((_BYTE *)v71 + 36) &= ~0x20u;
              else
                BYTE4((*a8)[4].ullOffset) |= 4u;
              v21 = v66;
              v49 = v70;
              BYTE4((*a8)[4].ullOffset) |= 0x20u;
              v50 = *((_QWORD *)this + 20);
              v51 = *(_DWORD *)(v50 + 76);
              v52 = v51 / 0x1F;
              if ( v51 == 31 * (_DWORD)v52 && v51 < 0x1F0 )
                *(_DWORD *)(v49 + 4 * v52 + 40) = *(_DWORD *)(v50 + 72);
              v53 = *((_QWORD *)this + 20);
              if ( !*(_DWORD *)(v53 + 76) && (*((_DWORD *)this + 26) & 0x100) != 0 )
              {
                *(_QWORD *)(v49 + 24) = *((_QWORD *)this + 25);
                v53 = *((_QWORD *)this + 20);
              }
              if ( this == (CClfsMarshallingContext *)-200LL
                || (v54 = *((_DWORD *)this + 51), v54 == -1)
                || (v55 = *(_DWORD *)(v53 + 76), (v55 & 0xFFFFFE00) != 0) )
              {
                v56 = CLFS_LSN_INVALID;
              }
              else
              {
                v56.ullOffset = __PAIR64__(v54, v55 | *((_DWORD *)this + 50) & 0xFFFFFE00);
              }
              **a8 = v56;
              v57 = (CLFS_LSN *)*((_QWORD *)this + 20);
              v58 = *a8;
              if ( v57 == (CLFS_LSN *)-176LL || !v58 )
              {
                p_cidContainer = &v58->offset.cidContainer;
              }
              else
              {
                p_cidContainer = &v58->offset.cidContainer;
                if ( v57[22].ullOffset < v58->ullOffset )
                  v57[22] = *v58;
              }
              p_ullOffset = &v57[23].ullOffset;
              if ( v57 != (CLFS_LSN *)-184LL )
              {
                if ( v58 )
                {
                  cidContainer = v57[23].offset.cidContainer;
                  if ( cidContainer >= *p_cidContainer
                    && (cidContainer != *p_cidContainer || *(_DWORD *)p_ullOffset > v58->offset.idxRecord) )
                  {
                    *p_ullOffset = v58->ullOffset;
                  }
                }
              }
              *(_DWORD *)(*((_QWORD *)this + 20) + 72LL) = (*(_DWORD *)(*((_QWORD *)this + 20) + 72LL) + *a11 + 7)
                                                         & 0xFFFFFFF8;
              ++*(_DWORD *)(*((_QWORD *)this + 20) + 76LL);
            }
            for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(v64 + 1) )
            {
              v63 = a6[i];
              if ( v63 >= 0 )
              {
                v21 = CClfsMarshallingContext::CalculateReservationForRecord(this, v63, &v68);
                v65 = v68;
              }
              else
              {
                v21 = CClfsMarshallingContext::CalculateReservationForRecord(this, -v63, &v68);
                v65 = -(__int64)v68;
              }
              a6[v64] = v65;
            }
            return v21;
          }
          return 6615;
        }
        return 6626;
      }
      return 6625;
    }
  }
  return 234;
}

```

## disassembly

```asm
0x18000e8e4  mov     rax, rsp
0x18000e8e7  mov     [rax+8], rbx
0x18000e8eb  mov     [rax+20h], r9d
0x18000e8ef  mov     [rax+18h], r8d
0x18000e8f3  mov     [rax+10h], rdx
0x18000e8f7  push    rbp
0x18000e8f8  push    rsi
0x18000e8f9  push    rdi
0x18000e8fa  push    r12
0x18000e8fc  push    r13
0x18000e8fe  push    r14
0x18000e900  push    r15
0x18000e902  mov     rbp, rsp
0x18000e905  sub     rsp, 50h
0x18000e909  mov     rax, [rbp+arg_38]
0x18000e90d  xor     r14d, r14d
0x18000e910  mov     r12, [rbp+arg_28]
0x18000e914  mov     rbx, rcx
0x18000e917  mov     ecx, [rbp+arg_20]
0x18000e91a  mov     [rbp+var_10], 0
0x18000e922  mov     [rax], r14
0x18000e925  mov     rax, [rbp+arg_40]
0x18000e92c  mov     [rbp+var_18], r14
0x18000e930  mov     [rbp+var_28], r14
0x18000e934  mov     [rax], r14d
0x18000e937  mov     rax, [rbp+arg_48]
0x18000e93e  mov     [rax], r14d
0x18000e941  mov     rax, [rbp+arg_50]
0x18000e948  mov     [rax], r14d
0x18000e94b  test    ecx, ecx
0x18000e94d  jz      short loc_18000E958
0x18000e94f  test    r12, r12
0x18000e952  jz      loc_18000EA69
0x18000e958  mov     r10, [rbx+0A0h]
0x18000e95f  mov     [rbp+var_20], r10
0x18000e963  mov     r13d, [r10+4Ch]
0x18000e967  lea     eax, [r13+1]
0x18000e96b  test    eax, 0FFFFFE00h
0x18000e970  jnz     loc_18000EF7B
0x18000e976  xor     esi, esi
0x18000e978  xor     r15d, r15d
0x18000e97b  xor     r11d, r11d
0x18000e97e  mov     [rbp+var_2C], esi
0x18000e981  test    ecx, ecx
0x18000e983  jz      loc_18000EA73
0x18000e989  mov     rdx, [r12+r11*8]; unsigned __int64
0x18000e98d  test    rdx, rdx
0x18000e990  jz      loc_18000EA69
0x18000e996  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18000e99a  mov     rcx, rbx; this
0x18000e99d  jns     short loc_18000E9BC
0x18000e99f  neg     rdx; unsigned __int64
0x18000e9a2  call    ?CalculateReservationForRecord@CClfsMarshallingContext@@AEBAK_KAEA_K@Z; CClfsMarshallingContext::CalculateReservationForRecord(unsigned __int64,unsigned __int64 &)
0x18000e9a7  mov     [rbp+var_30], eax
0x18000e9aa  mov     edi, eax
0x18000e9ac  test    eax, eax
0x18000e9ae  jnz     loc_18000EF80
0x18000e9b4  sub     r15, [rbp+var_28]
0x18000e9b8  dec     esi
0x18000e9ba  jmp     short loc_18000E9D4
0x18000e9bc  call    ?CalculateReservationForRecord@CClfsMarshallingContext@@AEBAK_KAEA_K@Z; CClfsMarshallingContext::CalculateReservationForRecord(unsigned __int64,unsigned __int64 &)
0x18000e9c1  mov     [rbp+var_30], eax
0x18000e9c4  mov     edi, eax
0x18000e9c6  test    eax, eax
0x18000e9c8  jnz     loc_18000EF80
0x18000e9ce  add     r15, [rbp+var_28]
0x18000e9d2  inc     esi
0x18000e9d4  inc     r11d
0x18000e9d7  mov     [rbp+var_2C], esi
0x18000e9da  cmp     r11d, [rbp+arg_20]
0x18000e9de  jb      short loc_18000E989
0x18000e9e0  mov     r10, [rbp+var_20]
0x18000e9e4  mov     r9d, [rbp+arg_18]
0x18000e9e8  mov     r8d, [rbx+98h]
0x18000e9ef  lea     ecx, [r8+rsi]
0x18000e9f3  test    ecx, ecx
0x18000e9f5  js      loc_18000EF74
0x18000e9fb  mov     r12, [rbx+0B0h]
0x18000ea02  lea     rdx, [r12+r15]
0x18000ea06  test    rdx, rdx
0x18000ea09  js      loc_18000EF6D
0x18000ea0f  mov     r11d, [rbx+88h]
0x18000ea16  mov     eax, ecx
0x18000ea18  imul    eax, r11d
0x18000ea1c  cmp     rdx, rax
0x18000ea1f  jl      loc_18000EF66
0x18000ea25  test    rdx, rdx
0x18000ea28  jle     short loc_18000EA32
0x18000ea2a  test    ecx, ecx
0x18000ea2c  jz      loc_18000EF66
0x18000ea32  xor     esi, esi
0x18000ea34  cmp     [rbp+arg_10], esi
0x18000ea37  jz      loc_18000EB2F
0x18000ea3d  mov     r13d, [rbp+arg_10]
0x18000ea41  xor     edx, edx
0x18000ea43  test    r13d, r13d
0x18000ea46  jz      short loc_18000EA92
0x18000ea48  mov     r8, [rbp+arg_8]
0x18000ea4c  mov     eax, edx
0x18000ea4e  add     rax, rax
0x18000ea51  mov     ecx, [r8+rax*8+8]
0x18000ea56  test    ecx, ecx
0x18000ea58  jz      short loc_18000EA60
0x18000ea5a  cmp     [r8+rax*8], r14
0x18000ea5e  jz      short loc_18000EABE
0x18000ea60  test    r9d, r9d
0x18000ea63  jnz     short loc_18000EA7D
0x18000ea65  xor     ecx, ecx
0x18000ea67  jmp     short loc_18000EA89
0x18000ea69  mov     eax, 57h ; 'W'
0x18000ea6e  jmp     loc_18000EF80
0x18000ea73  xor     edi, edi
0x18000ea75  mov     [rbp+var_30], edi
0x18000ea78  jmp     loc_18000E9E8
0x18000ea7d  dec     ecx
0x18000ea7f  mov     eax, r9d
0x18000ea82  add     ecx, r9d
0x18000ea85  neg     eax
0x18000ea87  and     ecx, eax
0x18000ea89  add     esi, ecx
0x18000ea8b  inc     edx
0x18000ea8d  cmp     edx, r13d
0x18000ea90  jb      short loc_18000EA4C
0x18000ea92  mov     edx, esi; unsigned __int64
0x18000ea94  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18000ea98  mov     rcx, rbx; this
0x18000ea9b  call    ?CalculateReservationForRecord@CClfsMarshallingContext@@AEBAK_KAEA_K@Z; CClfsMarshallingContext::CalculateReservationForRecord(unsigned __int64,unsigned __int64 &)
0x18000eaa0  mov     [rbp+var_30], eax
0x18000eaa3  mov     edi, eax
0x18000eaa5  test    eax, eax
0x18000eaa7  jz      short loc_18000EAC8
0x18000eaa9  cmp     edi, 19D7h
0x18000eaaf  mov     eax, 7Ah ; 'z'
0x18000eab4  cmovz   edi, eax
0x18000eab7  mov     eax, edi
0x18000eab9  jmp     loc_18000EF80
0x18000eabe  mov     eax, 6F8h
0x18000eac3  jmp     loc_18000EF80
0x18000eac8  mov     r10, [rbp+var_20]
0x18000eacc  add     esi, 2Fh ; '/'
0x18000eacf  mov     r14d, 0FFFFFFF8h
0x18000ead5  mov     eax, 80808081h
0x18000eada  and     esi, r14d
0x18000eadd  mov     r8d, [r10+48h]
0x18000eae1  add     r8d, esi
0x18000eae4  mul     r8d
0x18000eae7  shr     edx, 8
0x18000eaea  imul    ecx, edx, 1FEh
0x18000eaf0  lea     r9d, [rdx+1]
0x18000eaf4  cmp     r8d, ecx
0x18000eaf7  cmovz   r9d, edx
0x18000eafb  test    r11d, r11d
0x18000eafe  jnz     short loc_18000EB04
0x18000eb00  xor     edx, edx
0x18000eb02  jmp     short loc_18000EB22
0x18000eb04  lea     ecx, [r11-1]
0x18000eb08  mov     edx, r8d
0x18000eb0b  lea     eax, ds:7[r9*2]
0x18000eb13  and     rax, r14
0x18000eb16  add     rax, rcx
0x18000eb19  not     rcx
0x18000eb1c  add     rdx, rax
0x18000eb1f  and     rdx, rcx
0x18000eb22  mov     r14, [rbp+var_18]
0x18000eb26  mov     r8d, [rbx+98h]
0x18000eb2d  jmp     short loc_18000EB8E
0x18000eb2f  test    r13d, r13d
0x18000eb32  jz      short loc_18000EB88
0x18000eb34  mov     eax, 80808081h
0x18000eb39  mul     dword ptr [r10+48h]
0x18000eb3d  shr     edx, 8
0x18000eb40  imul    ecx, edx, 1FEh
0x18000eb46  lea     r8d, [rdx+1]
0x18000eb4a  cmp     [r10+48h], ecx
0x18000eb4e  cmovz   r8d, edx
0x18000eb52  test    r11d, r11d
0x18000eb55  jnz     short loc_18000EB5B
0x18000eb57  xor     edx, edx
0x18000eb59  jmp     short loc_18000EB7F
0x18000eb5b  mov     edx, 0FFFFFFF8h
0x18000eb60  lea     ecx, [r11-1]
0x18000eb64  lea     eax, ds:7[r8*2]
0x18000eb6c  and     rax, rdx
0x18000eb6f  mov     edx, [r10+48h]
0x18000eb73  add     rax, rcx
0x18000eb76  not     rcx
0x18000eb79  add     rdx, rax
0x18000eb7c  and     rdx, rcx
0x18000eb7f  mov     r8d, [rbx+98h]
0x18000eb86  jmp     short loc_18000EB8A
0x18000eb88  xor     edx, edx
0x18000eb8a  mov     r13d, [rbp+arg_10]
0x18000eb8e  mov     eax, [rbx+84h]
0x18000eb94  cmp     esi, eax
0x18000eb96  jbe     short loc_18000EBA2
0x18000eb98  mov     eax, 7Ah ; 'z'
0x18000eb9d  jmp     loc_18000EF80
0x18000eba2  cmp     edx, eax
0x18000eba4  ja      loc_18000EF7B
0x18000ebaa  test    [rbp+arg_30], 4
0x18000ebae  jz      short loc_18000EBFC
0x18000ebb0  test    r8d, r8d
0x18000ebb3  jz      loc_18000EF74
0x18000ebb9  cmp     r14, r12
0x18000ebbc  ja      loc_18000EF6D
0x18000ebc2  lea     ecx, [r8-1]
0x18000ebc6  sub     r12, r14
0x18000ebc9  imul    r11d, ecx
0x18000ebcd  mov     eax, r11d
0x18000ebd0  cmp     r12, rax
0x18000ebd3  jb      loc_18000EF66
0x18000ebd9  test    r12, r12
0x18000ebdc  jz      short loc_18000EBE6
0x18000ebde  test    ecx, ecx
0x18000ebe0  jz      loc_18000EF66
0x18000ebe6  sub     [r10+50h], r14
0x18000ebea  sub     [rbx+0B0h], r14
0x18000ebf1  dec     dword ptr [rbx+98h]
0x18000ebf7  jmp     loc_18000EC7C
0x18000ebfc  mov     rax, [r10+50h]
0x18000ec00  sub     rax, [rbx+0C0h]
0x18000ec07  add     rax, r15
0x18000ec0a  mov     r14d, edx
0x18000ec0d  add     r14, rax
0x18000ec10  mov     [rbp+var_20], r14
0x18000ec14  test    r14, r14
0x18000ec17  jle     short loc_18000EC7C
0x18000ec19  test    r11d, r11d
0x18000ec1c  jnz     short loc_18000EC22
0x18000ec1e  xor     esi, esi
0x18000ec20  jmp     short loc_18000EC37
0x18000ec22  mov     esi, [rbx+80h]
0x18000ec28  add     esi, 3D7h
0x18000ec2e  add     esi, r11d
0x18000ec31  neg     r11d
0x18000ec34  and     esi, r11d
0x18000ec37  mov     eax, esi
0x18000ec39  lea     rdx, [rbp+var_18]; __int64 *
0x18000ec3d  add     rax, r14
0x18000ec40  mov     rcx, rbx; this
0x18000ec43  mov     [rbp+var_18], rax
0x18000ec47  call    ?ReserveLogSpace@CClfsMarshallingContext@@QEAAKAEB_J@Z; CClfsMarshallingContext::ReserveLogSpace(__int64 const &)
0x18000ec4c  mov     [rbp+var_30], eax
0x18000ec4f  mov     edi, eax
0x18000ec51  test    eax, eax
0x18000ec53  jz      short loc_18000EC70
0x18000ec55  lea     rdx, [rbp+var_20]; __int64 *
0x18000ec59  mov     rcx, rbx; this
0x18000ec5c  call    ?ReserveLogSpace@CClfsMarshallingContext@@QEAAKAEB_J@Z; CClfsMarshallingContext::ReserveLogSpace(__int64 const &)
0x18000ec61  mov     [rbp+var_30], eax
0x18000ec64  mov     edi, eax
0x18000ec66  test    eax, eax
0x18000ec68  jnz     loc_18000EF80
0x18000ec6e  xor     esi, esi
0x18000ec70  mov     eax, esi
0x18000ec72  add     rax, r14
0x18000ec75  add     [rbx+0C0h], rax
0x18000ec7c  mov     rax, [rbx+0A0h]
0x18000ec83  add     [rax+50h], r15
0x18000ec87  mov     eax, [rbp+var_2C]
0x18000ec8a  add     [rbx+98h], eax
0x18000ec90  add     [rbx+0B0h], r15
0x18000ec97  test    r13d, r13d
0x18000ec9a  jz      loc_18000EF13
0x18000eca0  mov     rax, [rbx+0A0h]
0x18000eca7  mov     ecx, 28h ; '('
0x18000ecac  mov     r15, [rbp+arg_38]
0x18000ecb0  mov     r13, [rbp+arg_50]
0x18000ecb7  mov     rdi, [rbp+arg_40]
0x18000ecbe  mov     r14, [rax+40h]
0x18000ecc2  mov     eax, [rax+48h]
0x18000ecc5  mov     r12d, [rbp+arg_18]
0x18000ecc9  add     rax, r14
0x18000eccc  mov     [r15], rax
0x18000eccf  add     [r13+0], ecx
0x18000ecd3  mov     rax, [r15]
0x18000ecd6  xor     edx, edx
0x18000ecd8  mov     r15d, [rbp+arg_10]
0x18000ecdc  mov     [rbp+var_18], r14
0x18000ece0  mov     r14, [rbp+arg_8]
0x18000ece4  mov     [rax+22h], cx
0x18000ece8  mov     dword ptr [rdi], 0
0x18000ecee  mov     rax, [rbx+0A0h]
0x18000ecf5  mov     ecx, [rax+48h]
0x18000ecf8  add     ecx, [r13+0]
0x18000ecfc  cmp     ecx, [rbx+84h]
0x18000ed02  jnb     loc_18000ED93
0x18000ed08  mov     eax, edx
0x18000ed0a  add     rax, rax
0x18000ed0d  mov     rdx, [r14+rax*8]; Src
0x18000ed11  mov     ecx, [r14+rax*8+8]
0x18000ed16  mov     rax, [rbp+arg_48]
0x18000ed1d  mov     [rax], ecx
0x18000ed1f  test    r12d, r12d
0x18000ed22  jnz     short loc_18000ED28
0x18000ed24  xor     esi, esi
0x18000ed26  jmp     short loc_18000ED36
0x18000ed28  lea     esi, [r12-1]
0x18000ed2d  mov     eax, r12d
0x18000ed30  add     esi, ecx
  ... truncated ...
```
