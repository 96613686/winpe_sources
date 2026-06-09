# PerflibciLocalEnumerateCounterSetInstances

- ea: `0x180002810`
- end: `0x180002dbe`
- name: `PerflibciLocalEnumerateCounterSetInstances`
- size: `1454`
- prototype: `DWORD __fastcall(unsigned __int16 *, __int128 *Buf1, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005c60`

## callees

- `0x180002810`
- `0x180002dd0`
- `0x180004e70`
- `0x180005da0`
- `0x180006bc0`
- `0x180008042`
- `0x180008050`
- `0x18000805c`
- `0x18000fea0`
- `0x1800158e8`
- `0x180016260`
- `0x18001e431`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180002c5c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180002c5c`
- `ntdll!RtlNtStatusToDosError` at `0x18000295f`
- `ntdll!RtlNtStatusToDosError` at `0x18000295f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180002abe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180002abe`
- `api-ms-win-core-pcw-l1-1-0!PcwEnumerateInstances` at `0x180002925`
- `api-ms-win-core-pcw-l1-1-0!PcwEnumerateInstances` at `0x180002925`

## pseudocode

```c
DWORD __fastcall PerflibciLocalEnumerateCounterSetInstances(
        unsigned __int16 *a1,
        __int128 *Buf1,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  DWORD result; // eax
  ULONG v10; // edi
  char *CounterSet; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  unsigned int *v13; // r14
  int v14; // ecx
  void *v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // edi
  void *v19; // rax
  NTSTATUS v20; // r12d
  unsigned __int16 *v21; // rbp
  unsigned int v22; // edx
  LONG LockCount; // eax
  unsigned int v24; // ebx
  unsigned __int16 *v25; // rcx
  __int64 v26; // r12
  __int64 v27; // rax
  DWORD v28; // eax
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r11
  int v31; // edx
  unsigned int *v33; // rcx
  __int64 v34; // r12
  unsigned int v35; // ebp
  unsigned int v36; // r9d
  unsigned int i; // r10d
  unsigned int *v38; // rdx
  __int64 v39; // r11
  unsigned int v40; // eax
  unsigned int v41; // r11d
  int v42; // r11d
  __int64 v43; // rcx
  unsigned int v44; // r8d
  __int64 v45; // r14
  __int64 v46; // rax
  _DWORD *v47; // rbx
  unsigned int v48; // ecx
  unsigned int v49; // eax
  LONG v50; // eax
  int v51; // eax
  unsigned int Size; // [rsp+40h] [rbp-78h] BYREF
  int Size_4; // [rsp+44h] [rbp-74h]
  DWORD nSize; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v55; // [rsp+4Ch] [rbp-6Ch] BYREF
  unsigned int v56; // [rsp+50h] [rbp-68h]
  void *Block; // [rsp+58h] [rbp-60h] BYREF
  int v58; // [rsp+60h] [rbp-58h]
  unsigned __int16 *v59; // [rsp+68h] [rbp-50h]
  unsigned __int16 *v60[2]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int *v61; // [rsp+80h] [rbp-38h]

  Block = 0;
  nSize = 0;
  v55 = 0;
  result = PerflibciEnsureCounterSetList();
  v10 = result;
  if ( !result )
  {
    CounterSet = PerflibciCreateOrFindCounterSet(Buf1, 0, 0, 0, 0, 0, 0);
    v12 = (struct _RTL_CRITICAL_SECTION *)CounterSet;
    if ( !CounterSet )
      return 4200;
    v13 = a5;
    v14 = *(_DWORD *)(*((_QWORD *)CounterSet + 2) + 32LL);
    *a5 = 0;
    if ( v14 == 1 )
    {
      v60[0] = (unsigned __int16 *)262146;
      v60[1] = L"*";
      v15 = 0;
      v16 = 0x2000;
      v17 = 0;
      for ( Size = 0x2000; ; v16 = Size )
      {
        if ( v16 > v17 )
        {
          operator delete(v15);
          v18 = Size;
          v19 = operator new(Size, (const struct std::nothrow_t *)&std::nothrow);
          v15 = v19;
          if ( !v19 )
            return 14;
          memset_0(v19, 0, v18);
          v17 = Size;
        }
        v20 = PcwEnumerateInstances(0, &v12[2].LockSemaphore, v60, v15, v17, &Size);
        if ( v20 != -2147483643 )
          break;
      }
      if ( v20 >= 0 )
      {
        v22 = Size;
        v21 = (unsigned __int16 *)v15;
        Size_4 = Size;
      }
      else
      {
        Size_4 = 0;
        v21 = 0;
        operator delete(v15);
        v10 = RtlNtStatusToDosError(v20);
        if ( v10 )
          return v10;
        v22 = 0;
      }
      if ( !*(_DWORD *)v21 )
      {
        v10 = 4201;
LABEL_33:
        v25 = v21;
LABEL_101:
        operator delete(v25);
        return v10;
      }
      LockCount = v12[2].LockCount;
      v10 = 0;
      if ( LockCount )
      {
        if ( LockCount != 2 )
        {
          if ( LockCount == 4 )
            goto LABEL_31;
          if ( LockCount != 6 )
          {
            if ( LockCount != 12 )
            {
LABEL_23:
              v10 = 4211;
              goto LABEL_33;
            }
LABEL_31:
            if ( *a5 > a4 )
              v10 = 8;
            goto LABEL_33;
          }
          v10 = PerfpAddInstanceToBuffer(a3, a4, a5, 0, L"_Total");
          if ( v10 )
            goto LABEL_33;
          v22 = Size_4;
        }
        v24 = *((_DWORD *)v21 + 1);
        while ( v24 < v22 )
        {
          v10 = PerfpAddInstanceToBuffer(
                  a3,
                  a4,
                  a5,
                  *(_DWORD *)((char *)v21 + v24 + 4),
                  (unsigned __int16 *)((char *)v21 + v24 + 8));
          if ( v10 )
            goto LABEL_33;
          v24 += *(_DWORD *)((char *)v21 + v24);
          v22 = Size_4;
        }
        goto LABEL_31;
      }
      if ( *(_DWORD *)v21 > 1u )
        goto LABEL_23;
      goto LABEL_31;
    }
    if ( a4 )
    {
      if ( a3 )
      {
        *a3 = 0;
        a3[a4 - 1] = 0;
      }
      else
      {
        v10 = 87;
      }
    }
    v26 = -1;
    if ( a1 )
    {
      v27 = -1;
      do
        ++v27;
      while ( a1[v27] );
      v28 = v27 + 1;
    }
    else
    {
      v28 = 261;
    }
    nSize = v28;
    v29 = (unsigned __int16 *)operator new(saturated_mul(v28, 2u));
    v59 = v29;
    v30 = v29;
    if ( !v29 )
    {
      v10 = 14;
LABEL_100:
      v25 = v30;
      goto LABEL_101;
    }
    if ( a1 && *a1 )
    {
      StringCchCopyW(v29, nSize, a1);
    }
    else
    {
      GetComputerNameW(v29, &nSize);
      v30 = v59;
    }
    while ( v30[++v26] != 0 )
      ;
    if ( v10 )
      goto LABEL_100;
    v55 = 0x2000;
    v10 = PerfpSendStateLessNotification(
            (_DWORD)Buf1,
            v31,
            (_DWORD)v30,
            2 * (int)v26 + 2,
            (__int64)&Block,
            (__int64)&v55);
    if ( v10 )
    {
LABEL_99:
      v30 = v59;
      goto LABEL_100;
    }
    v33 = (unsigned int *)Block;
    v34 = 0;
    Size = 8;
    v35 = 0;
    v36 = 8;
    for ( i = 0; ; ++i )
    {
      v56 = i;
      if ( i >= *v33 || v36 >= v55 )
        break;
      v38 = (unsigned int *)((char *)v33 + v36);
      v61 = v38;
      v39 = *v38;
      v58 = v39;
      if ( (unsigned int)v39 >= 0x20 && !v38[3] )
      {
        v40 = v38[6];
        if ( (v12[2].LockCount & 2) != 0 )
        {
          if ( v40 == -1 )
          {
LABEL_61:
            v10 = 4211;
            break;
          }
          if ( v40 )
          {
            LODWORD(v43) = v39;
            if ( (unsigned __int64)(v39 - 8) > 0x20 )
            {
              v44 = 32;
              Size_4 = 32;
              v45 = 32;
              do
              {
                v46 = *(unsigned int *)((char *)v38 + v45);
                if ( (unsigned int)v46 > (unsigned int)v43 - v44 )
                  break;
                if ( (unsigned int)v46 < 0x10 )
                  break;
                v60[0] = (unsigned __int16 *)((char *)v38 + v45 + 8);
                if ( (unsigned int)((unsigned __int64)(v46 - 8) >> 1) == wcsnlen(
                                                                           v60[0],
                                                                           (unsigned int)((unsigned __int64)(v46 - 8) >> 1)) )
                  break;
                v47 = (unsigned int *)((char *)v61 + v45);
                if ( PerflibciFindInstance(v12, v60[0], *(unsigned int *)((char *)v61 + v45 + 4), v61[7]) )
                {
                  ++v35;
                  if ( (v12[2].LockCount & 2) != 0 )
                  {
                    if ( a3 && (v48 = *v47, v49 = *v47 + v34, (unsigned int)v34 <= v49) && v48 <= v49 && v49 <= a4 )
                      memcpy_0(&a3[(unsigned int)v34], v47, v48);
                    else
                      v10 = 8;
                    v34 = (unsigned int)(*v47 + v34);
                  }
                }
                v44 = *v47 + Size_4;
                v38 = v61;
                v45 = v44;
                Size_4 = v44;
                v43 = *v61;
              }
              while ( v44 < (unsigned __int64)(v43 - 8) );
              v13 = a5;
              v36 = Size;
              i = v56;
              LODWORD(v39) = v58;
            }
            v33 = (unsigned int *)Block;
          }
        }
        else if ( v40 == -1 )
        {
          ++v35;
        }
        else if ( v40 )
        {
          goto LABEL_61;
        }
      }
      v36 += v39;
      Size = v36;
    }
    if ( v12[2].LockCount == 6 && v35 )
    {
      ++v35;
      if ( a3 && (v41 = v34 + 24, (unsigned int)v34 < (int)v34 + 24) && v41 >= 0x18 && v41 <= a4 )
      {
        *(_QWORD *)&a3[v34] = 24;
        StringCchCopyW((unsigned __int16 *)&a3[(unsigned int)v34 + 8], 7u, L"_Total");
        v33 = (unsigned int *)Block;
        LODWORD(v34) = v42;
      }
      else
      {
        v10 = 8;
        LODWORD(v34) = v34 + 24;
      }
    }
    if ( (v10 & 0xFFFFFFF7) != 0 )
    {
LABEL_98:
      operator delete(v33);
      goto LABEL_99;
    }
    v50 = v12[2].LockCount;
    if ( v50 )
    {
      switch ( v50 )
      {
        case 2:
          goto LABEL_104;
        case 4:
          goto LABEL_96;
        case 6:
LABEL_104:
          v51 = v10;
          *v13 = v34;
          if ( !v35 )
            v51 = 4201;
          v10 = v51;
          goto LABEL_98;
        case 12:
LABEL_96:
          if ( v35 )
          {
LABEL_97:
            *v13 = 0;
            goto LABEL_98;
          }
LABEL_110:
          v10 = 4201;
          goto LABEL_98;
      }
    }
    else if ( v35 <= 1 )
    {
      if ( v35 )
        goto LABEL_97;
      goto LABEL_110;
    }
    v10 = 4211;
    goto LABEL_98;
  }
  return result;
}

```

## disassembly

```asm
0x180002810  mov     [rsp+arg_10], rbx
0x180002815  push    rbp
0x180002816  push    rdi
0x180002817  push    r12
0x180002819  push    r13
0x18000281b  push    r15
0x18000281d  sub     rsp, 90h
0x180002824  xor     r12d, r12d
0x180002827  mov     r13d, r9d
0x18000282a  mov     [rsp+0B8h+Block], r12
0x18000282f  mov     r15, r8
0x180002832  mov     [rsp+0B8h+nSize], r12d
0x180002837  mov     rbx, rdx
0x18000283a  mov     [rsp+0B8h+var_6C], r12d
0x18000283f  mov     rbp, rcx
0x180002842  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180002847  mov     edi, eax
0x180002849  test    eax, eax
0x18000284b  jnz     loc_180002D7C
0x180002851  mov     [rsp+0B8h+var_88], r12d; int
0x180002856  xor     r9d, r9d
0x180002859  mov     [rsp+0B8h+var_90], r12w; __int16
0x18000285f  xor     r8d, r8d
0x180002862  xor     edx, edx
0x180002864  mov     [rsp+0B8h+Src], r12; void *
0x180002869  mov     rcx, rbx; Buf1
0x18000286c  mov     [rsp+0B8h+arg_0], rsi
0x180002874  call    PerflibciCreateOrFindCounterSet
0x180002879  mov     rsi, rax
0x18000287c  test    rax, rax
0x18000287f  jnz     short loc_18000288B
0x180002881  mov     eax, 1068h
0x180002886  jmp     loc_180002D74
0x18000288b  mov     rax, [rax+10h]
0x18000288f  mov     [rsp+0B8h+arg_8], r14
0x180002897  mov     r14, [rsp+0B8h+arg_20]
0x18000289f  mov     ecx, [rax+20h]
0x1800028a2  mov     [r14], r12d
0x1800028a5  cmp     ecx, 1
0x1800028a8  jnz     loc_180002A29
0x1800028ae  lea     rax, SourceString; "*"
0x1800028b5  mov     [rsp+0B8h+var_48], 40002h
0x1800028be  mov     [rsp+0B8h+var_40], rax
0x1800028c3  mov     rbx, r12
0x1800028c6  mov     eax, 2000h
0x1800028cb  mov     edi, r12d
0x1800028ce  mov     dword ptr [rsp+0B8h+Size], eax
0x1800028d2  cmp     eax, edi
0x1800028d4  jbe     short loc_180002909
0x1800028d6  mov     rcx, rbx; Block
0x1800028d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028de  mov     edi, dword ptr [rsp+0B8h+Size]
0x1800028e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800028e9  mov     ecx, edi; unsigned __int64
0x1800028eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800028f0  mov     rbx, rax
0x1800028f3  test    rax, rax
0x1800028f6  jz      short loc_18000293B
0x1800028f8  mov     r8d, edi; Size
0x1800028fb  xor     edx, edx; Val
0x1800028fd  mov     rcx, rax; void *
0x180002900  call    memset_0
0x180002905  mov     edi, dword ptr [rsp+0B8h+Size]
0x180002909  lea     rax, [rsp+0B8h+Size]
0x18000290e  mov     r9, rbx
0x180002911  mov     qword ptr [rsp+0B8h+var_90], rax
0x180002916  lea     rdx, [rsi+68h]
0x18000291a  lea     r8, [rsp+0B8h+var_48]
0x18000291f  mov     dword ptr [rsp+0B8h+Src], edi
0x180002923  xor     ecx, ecx
0x180002925  call    cs:__imp_PcwEnumerateInstances
0x18000292b  mov     r12d, eax
0x18000292e  cmp     eax, 80000005h
0x180002933  jnz     short loc_180002945
0x180002935  mov     eax, dword ptr [rsp+0B8h+Size]
0x180002939  jmp     short loc_1800028D2
0x18000293b  mov     edi, 0Eh
0x180002940  jmp     loc_180002D6A
0x180002945  test    r12d, r12d
0x180002948  jns     short loc_180002982
0x18000294a  mov     rcx, rbx; Block
0x18000294d  mov     dword ptr [rsp+0B8h+Size+4], 0
0x180002955  xor     ebp, ebp
0x180002957  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000295c  mov     ecx, r12d; Status
0x18000295f  call    cs:__imp_RtlNtStatusToDosError
0x180002965  mov     edi, eax
0x180002967  test    eax, eax
0x180002969  jnz     loc_180002D6A
0x18000296f  mov     edx, ebp
0x180002971  mov     ecx, [rbp+0]
0x180002974  test    ecx, ecx
0x180002976  jnz     short loc_18000298F
0x180002978  mov     edi, 1069h
0x18000297d  jmp     loc_180002A21
0x180002982  mov     edx, dword ptr [rsp+0B8h+Size]
0x180002986  mov     rbp, rbx
0x180002989  mov     dword ptr [rsp+0B8h+Size+4], edx
0x18000298d  jmp     short loc_180002971
0x18000298f  mov     eax, [rsi+58h]
0x180002992  xor     edi, edi
0x180002994  test    eax, eax
0x180002996  jz      short loc_180002A11
0x180002998  cmp     eax, 2
0x18000299b  jz      short loc_1800029DA
0x18000299d  cmp     eax, 4
0x1800029a0  jz      short loc_180002A16
0x1800029a2  cmp     eax, 6
0x1800029a5  jz      short loc_1800029B3
0x1800029a7  cmp     eax, 0Ch
0x1800029aa  jz      short loc_180002A16
0x1800029ac  mov     edi, 1073h
0x1800029b1  jmp     short loc_180002A21
0x1800029b3  lea     r8, Src; "_Total"
0x1800029ba  xor     r9d, r9d; unsigned int
0x1800029bd  mov     [rsp+0B8h+Src], r8; Src
0x1800029c2  mov     edx, r13d; unsigned int
0x1800029c5  mov     r8, r14; unsigned int *
0x1800029c8  mov     rcx, r15; unsigned __int8 *
0x1800029cb  call    ?PerfpAddInstanceToBuffer@@YAKPEAEKPEAKKPEBG@Z; PerfpAddInstanceToBuffer(uchar *,ulong,ulong *,ulong,ushort const *)
0x1800029d0  mov     edi, eax
0x1800029d2  test    eax, eax
0x1800029d4  jnz     short loc_180002A21
0x1800029d6  mov     edx, dword ptr [rsp+0B8h+Size+4]
0x1800029da  mov     ebx, [rbp+4]
0x1800029dd  cmp     ebx, edx
0x1800029df  jnb     short loc_180002A16
0x1800029e1  mov     esi, ebx
0x1800029e3  mov     r8, r14; unsigned int *
0x1800029e6  mov     edx, r13d; unsigned int
0x1800029e9  mov     rcx, r15; unsigned __int8 *
0x1800029ec  mov     r9d, [rsi+rbp+4]; unsigned int
0x1800029f1  lea     rax, [rsi+8]
0x1800029f5  add     rax, rbp
0x1800029f8  mov     [rsp+0B8h+Src], rax; Src
0x1800029fd  call    ?PerfpAddInstanceToBuffer@@YAKPEAEKPEAKKPEBG@Z; PerfpAddInstanceToBuffer(uchar *,ulong,ulong *,ulong,ushort const *)
0x180002a02  mov     edi, eax
0x180002a04  test    eax, eax
0x180002a06  jnz     short loc_180002A21
0x180002a08  add     ebx, [rsi+rbp]
0x180002a0b  mov     edx, dword ptr [rsp+0B8h+Size+4]
0x180002a0f  jmp     short loc_1800029DD
0x180002a11  cmp     ecx, 1
0x180002a14  ja      short loc_1800029AC
0x180002a16  cmp     [r14], r13d
0x180002a19  mov     eax, 8
0x180002a1e  cmova   edi, eax
0x180002a21  mov     rcx, rbp
0x180002a24  jmp     loc_180002D65
0x180002a29  test    r13d, r13d
0x180002a2c  jz      short loc_180002A45
0x180002a2e  test    r15, r15
0x180002a31  jz      short loc_180002A40
0x180002a33  lea     eax, [r13-1]
0x180002a37  mov     [r15], r12b
0x180002a3a  mov     [rax+r15], r12b
0x180002a3e  jmp     short loc_180002A45
0x180002a40  mov     edi, 57h ; 'W'
0x180002a45  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180002a4c  test    rbp, rbp
0x180002a4f  jz      short loc_180002A63
0x180002a51  mov     rax, r12
0x180002a54  inc     rax
0x180002a57  cmp     word ptr [rbp+rax*2+0], 0
0x180002a5d  jnz     short loc_180002A54
0x180002a5f  inc     eax
0x180002a61  jmp     short loc_180002A68
0x180002a63  mov     eax, 105h
0x180002a68  mov     ecx, eax
0x180002a6a  mov     [rsp+0B8h+nSize], eax
0x180002a6e  mov     eax, 2
0x180002a73  mul     rcx
0x180002a76  cmovb   rax, r12
0x180002a7a  mov     rcx, rax
0x180002a7d  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180002a82  mov     [rsp+0B8h+var_50], rax
0x180002a87  mov     r11, rax
0x180002a8a  test    rax, rax
0x180002a8d  jnz     short loc_180002A99
0x180002a8f  mov     edi, 0Eh
0x180002a94  jmp     loc_180002D62
0x180002a99  test    rbp, rbp
0x180002a9c  jz      short loc_180002AB6
0x180002a9e  cmp     word ptr [rbp+0], 0
0x180002aa3  jz      short loc_180002AB6
0x180002aa5  mov     edx, [rsp+0B8h+nSize]; unsigned __int64
0x180002aa9  mov     r8, rbp; unsigned __int16 *
0x180002aac  mov     rcx, rax; unsigned __int16 *
0x180002aaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002ab4  jmp     short loc_180002AC9
0x180002ab6  lea     rdx, [rsp+0B8h+nSize]; nSize
0x180002abb  mov     rcx, rax; lpBuffer
0x180002abe  call    cs:__imp_GetComputerNameW
0x180002ac4  mov     r11, [rsp+0B8h+var_50]
0x180002ac9  cmp     word ptr [r11+r12*2+2], 0
0x180002ad0  lea     r12, [r12+1]
0x180002ad5  jnz     short loc_180002AC9
0x180002ad7  test    edi, edi
0x180002ad9  jnz     loc_180002D62
0x180002adf  mov     eax, 2000h
0x180002ae4  lea     r9d, ds:2[r12*2]
0x180002aec  mov     [rsp+0B8h+var_6C], eax
0x180002af0  mov     r8, r11
0x180002af3  lea     rax, [rsp+0B8h+var_6C]
0x180002af8  mov     rcx, rbx
0x180002afb  mov     qword ptr [rsp+0B8h+var_90], rax
0x180002b00  lea     rax, [rsp+0B8h+Block]
0x180002b05  mov     [rsp+0B8h+Src], rax; int
0x180002b0a  call    PerfpSendStateLessNotification
0x180002b0f  mov     edi, eax
0x180002b11  test    eax, eax
0x180002b13  jnz     loc_180002D5D
0x180002b19  mov     rcx, [rsp+0B8h+Block]; Block
0x180002b1e  mov     eax, 8
0x180002b23  xor     r12d, r12d
0x180002b26  mov     dword ptr [rsp+0B8h+Size], eax
0x180002b2a  xor     ebp, ebp
0x180002b2c  mov     r9d, eax
0x180002b2f  xor     r10d, r10d
0x180002b32  mov     [rsp+0B8h+var_68], r10d
0x180002b37  cmp     r10d, [rcx]
0x180002b3a  jnb     short loc_180002B93
0x180002b3c  cmp     r9d, [rsp+0B8h+var_6C]
0x180002b41  jnb     short loc_180002B93
0x180002b43  mov     edx, r9d
0x180002b46  add     rdx, rcx
0x180002b49  mov     [rsp+0B8h+var_38], rdx
0x180002b51  mov     r11d, [rdx]
0x180002b54  mov     [rsp+0B8h+var_58], r11d
0x180002b59  cmp     r11d, 20h ; ' '
0x180002b5d  jb      loc_180002D11
0x180002b63  cmp     dword ptr [rdx+0Ch], 0
0x180002b67  jnz     loc_180002D11
0x180002b6d  test    byte ptr [rsi+58h], 2
0x180002b71  mov     eax, [rdx+18h]
0x180002b74  jnz     loc_180002C01
0x180002b7a  cmp     eax, 0FFFFFFFFh
0x180002b7d  jnz     short loc_180002B86
0x180002b7f  inc     ebp
0x180002b81  jmp     loc_180002D11
0x180002b86  test    eax, eax
0x180002b88  jz      loc_180002D11
0x180002b8e  mov     edi, 1073h
0x180002b93  cmp     dword ptr [rsi+58h], 6
0x180002b97  jnz     loc_180002D2A
0x180002b9d  test    ebp, ebp
0x180002b9f  jz      loc_180002D2A
0x180002ba5  inc     ebp
0x180002ba7  test    r15, r15
0x180002baa  jz      loc_180002D21
0x180002bb0  lea     r11d, [r12+18h]
0x180002bb5  cmp     r12d, r11d
0x180002bb8  jnb     loc_180002D21
0x180002bbe  cmp     r11d, 18h
0x180002bc2  jb      loc_180002D21
0x180002bc8  cmp     r11d, r13d
0x180002bcb  ja      loc_180002D21
0x180002bd1  mov     eax, r12d
0x180002bd4  lea     rcx, [r15+8]
0x180002bd8  add     rcx, rax; unsigned __int16 *
0x180002bdb  mov     qword ptr [r12+r15], 18h
0x180002be3  lea     r8, Src; "_Total"
0x180002bea  mov     edx, 7; unsigned __int64
0x180002bef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002bf4  mov     rcx, [rsp+0B8h+Block]
0x180002bf9  mov     r12d, r11d
0x180002bfc  jmp     loc_180002D2A
0x180002c01  cmp     eax, 0FFFFFFFFh
0x180002c04  jz      short loc_180002B8E
0x180002c06  test    eax, eax
0x180002c08  jz      loc_180002D11
0x180002c0e  lea     rax, [r11-8]
0x180002c12  mov     rcx, r11
0x180002c15  cmp     rax, 20h ; ' '
0x180002c19  jbe     loc_180002D0C
0x180002c1f  mov     r8d, 20h ; ' '
0x180002c25  mov     dword ptr [rsp+0B8h+Size+4], r8d
0x180002c2a  mov     r14d, r8d
0x180002c2d  mov     eax, [r14+rdx]
0x180002c31  sub     ecx, r8d
0x180002c34  cmp     eax, ecx
0x180002c36  ja      loc_180002CF5
0x180002c3c  cmp     eax, 10h
0x180002c3f  jb      loc_180002CF5
0x180002c45  lea     rcx, [rdx+8]
0x180002c49  sub     rax, 8
0x180002c4d  shr     rax, 1
0x180002c50  add     rcx, r14; Source
0x180002c53  mov     edx, eax; MaxCount
0x180002c55  mov     [rsp+0B8h+var_48], rcx
0x180002c5a  mov     ebx, eax
0x180002c5c  call    cs:__imp_wcsnlen
0x180002c62  cmp     rbx, rax
0x180002c65  jz      loc_180002CF5
0x180002c6b  mov     r8, [rsp+0B8h+var_38]
0x180002c73  mov     rcx, rsi; struct PERFLIBCI_COUNTERSET_NODE *
0x180002c76  mov     rdx, [rsp+0B8h+var_48]; unsigned __int16 *
0x180002c7b  mov     r9d, [r8+1Ch]; unsigned int
0x180002c7f  lea     rbx, [r14+r8]
0x180002c83  mov     r8d, [r14+r8+4]; unsigned int
  ... truncated ...
```
