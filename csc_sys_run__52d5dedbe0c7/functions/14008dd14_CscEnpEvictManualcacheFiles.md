# CscEnpEvictManualcacheFiles

- ea: `0x14008dd14`
- end: `0x14008df6a`
- name: `CscEnpEvictManualcacheFiles`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14008eae0`

## callees

- `0x140012cf8`
- `0x140013eec`
- `0x140016e44`
- `0x1400180dc`
- `0x140018974`
- `0x1400190ec`
- `0x14001b568`
- `0x1400247bc`
- `0x140024a0c`
- `0x140048fb8`
- `0x14005837c`
- `0x14008dd14`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dd41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008dd41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008df08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008df08`

## pseudocode

```c
__int64 __fastcall CscEnpEvictManualcacheFiles(__int64 a1, char a2, _QWORD *a3)
{
  int v3; // esi
  __int64 v4; // r14
  __int64 v8; // rcx
  int v9; // ebx
  char IsRecovering; // al
  _QWORD *v11; // r10
  unsigned __int64 *v12; // r8
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  char *v15; // r9
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdx
  char v18; // al
  unsigned __int64 v19; // r10
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  int EnumContext; // eax
  __int64 v23; // r8
  __int64 v25; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+38h] [rbp-20h] BYREF
  __int64 v27; // [rsp+40h] [rbp-18h] BYREF
  __int64 v28; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int64 v29; // [rsp+A8h] [rbp+50h] BYREF

  v3 = 0;
  v4 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v28 = 0;
  KeEnterCriticalRegion();
  if ( a2 )
  {
    CscEnpDbInfoAcquireShared(a1);
    v8 = *(unsigned int *)(*(_QWORD *)(a1 + 8) + 280LL);
    if ( (_DWORD)v8 )
      *a3 = -10000000 * v8;
    v9 = 0;
    goto LABEL_24;
  }
  CscEnpDbInfoAcquireExclusive(a1);
  IsRecovering = CscEnpQuotaIsRecovering(a1);
  v12 = v11 + 21;
  v13 = IsRecovering != 0 ? 216LL : 192LL;
  v14 = *(_QWORD *)((char *)v11 + v13);
  v15 = (char *)v11 + v13;
  if ( v14 > v11[31] )
  {
    v17 = v14 - v11[32];
    v29 = v17;
    v19 = v17;
    goto LABEL_10;
  }
  v16 = *v12;
  v17 = 0;
  v29 = 0;
  if ( *((_QWORD *)v15 + 2) > v16 )
  {
    v19 = 0;
LABEL_10:
    v20 = *((_QWORD *)v15 + 2);
    if ( v20 > *v12 )
    {
      v21 = v20 - *v12;
      if ( v19 <= v21 )
        v17 = v21;
      v29 = v17;
    }
    v18 = 1;
    goto LABEL_15;
  }
  v18 = 0;
LABEL_15:
  LOBYTE(v12) = 1;
  EnumContext = CscEnEvictAllocateEnumContext((unsigned int)&v27, 0, (_DWORD)v12, 0, v18);
  v4 = v27;
  v9 = EnumContext;
  if ( EnumContext >= 0 )
  {
    LOBYTE(v23) = 1;
    v9 = CscEnpEvictpChangeDbStatus(a1, 256, v23);
    if ( v9 >= 0 )
    {
      CscEnpDbInfoRelease(a1);
      CscEnpNotifyQuota(a1, 4, 0, 0, 0);
      CscEnEvict(a1, v4, (unsigned int)&v29, 0, (__int64)&v26, (__int64)&v25);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids, v26, v25);
      }
      CscEnpNotifyQuota(a1, 8, (unsigned int)&v26, (unsigned int)&v28, (__int64)&v25);
      CscEnpDbInfoAcquireExclusive(a1);
      v9 = CscEnpEvictpChangeDbStatus(a1, 256, 0);
      if ( v9 < 0 )
        v3 = 2013;
    }
    else
    {
      v3 = 1969;
    }
  }
  else
  {
    v3 = 1964;
  }
LABEL_24:
  CscEnpDbInfoRelease(a1);
  KeLeaveCriticalRegion();
  if ( v4 )
    CscEnEvictFreeEnumContext(&v27);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids,
      (unsigned int)v9,
      v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14008dd14  push    rbp
0x14008dd16  push    rbx
0x14008dd17  push    rsi
0x14008dd18  push    rdi
0x14008dd19  push    r14
0x14008dd1b  push    r15
0x14008dd1d  mov     rbp, rsp
0x14008dd20  sub     rsp, 58h
0x14008dd24  xor     esi, esi
0x14008dd26  xor     r14d, r14d
0x14008dd29  mov     [rbp+var_18], r14
0x14008dd2d  mov     r15, r8
0x14008dd30  mov     [rbp+var_20], rsi
0x14008dd34  mov     bl, dl
0x14008dd36  mov     [rbp+var_28], rsi
0x14008dd3a  mov     rdi, rcx
0x14008dd3d  mov     [rbp+var_10], rsi
0x14008dd41  call    cs:__imp_KeEnterCriticalRegion
0x14008dd48  nop     dword ptr [rax+rax+00h]
0x14008dd4d  mov     rcx, rdi
0x14008dd50  test    bl, bl
0x14008dd52  jz      short loc_14008DD78
0x14008dd54  call    CscEnpDbInfoAcquireShared
0x14008dd59  mov     rax, [rdi+8]
0x14008dd5d  mov     ecx, [rax+118h]
0x14008dd63  test    ecx, ecx
0x14008dd65  jz      short loc_14008DD71
0x14008dd67  imul    rcx, 0FFFFFFFFFF676980h
0x14008dd6e  mov     [r15], rcx
0x14008dd71  xor     ebx, ebx
0x14008dd73  jmp     loc_14008DF00
0x14008dd78  call    CscEnpDbInfoAcquireExclusive
0x14008dd7d  mov     r10, [rdi+8]
0x14008dd81  mov     rcx, rdi
0x14008dd84  call    CscEnpQuotaIsRecovering
0x14008dd89  neg     al
0x14008dd8b  lea     r8, [r10+0A8h]
0x14008dd92  sbb     rcx, rcx
0x14008dd95  and     ecx, 18h
0x14008dd98  add     rcx, 0C0h
0x14008dd9f  mov     rdx, [rcx+r10]
0x14008dda3  lea     r9, [rcx+r10]
0x14008dda7  cmp     rdx, [r10+0F8h]
0x14008ddae  ja      short loc_14008DDC8
0x14008ddb0  mov     rax, [r8]
0x14008ddb3  xor     edx, edx
0x14008ddb5  mov     [rbp+arg_18], rdx
0x14008ddb9  cmp     [r9+10h], rax
0x14008ddbd  ja      short loc_14008DDC3
0x14008ddbf  xor     al, al
0x14008ddc1  jmp     short loc_14008DDF2
0x14008ddc3  xor     r10d, r10d
0x14008ddc6  jmp     short loc_14008DDD6
0x14008ddc8  sub     rdx, [r10+100h]
0x14008ddcf  mov     [rbp+arg_18], rdx
0x14008ddd3  mov     r10, rdx
0x14008ddd6  mov     rcx, [r8]
0x14008ddd9  mov     rax, [r9+10h]
0x14008dddd  cmp     rax, rcx
0x14008dde0  jbe     short loc_14008DDF0
0x14008dde2  sub     rax, rcx
0x14008dde5  cmp     r10, rax
0x14008dde8  cmovbe  rdx, rax
0x14008ddec  mov     [rbp+arg_18], rdx
0x14008ddf0  mov     al, 1
0x14008ddf2  xor     r9d, r9d
0x14008ddf5  mov     byte ptr [rsp+58h+var_38], al
0x14008ddf9  mov     r8b, 1
0x14008ddfc  lea     rcx, [rbp+var_18]
0x14008de00  xor     edx, edx
0x14008de02  call    CscEnEvictAllocateEnumContext
0x14008de07  mov     r14, [rbp+var_18]
0x14008de0b  mov     ebx, eax
0x14008de0d  test    eax, eax
0x14008de0f  jns     short loc_14008DE1B
0x14008de11  mov     esi, 7ACh
0x14008de16  jmp     loc_14008DF00
0x14008de1b  mov     r15d, 100h
0x14008de21  mov     r8b, 1
0x14008de24  mov     edx, r15d
0x14008de27  mov     rcx, rdi
0x14008de2a  call    CscEnpEvictpChangeDbStatus
0x14008de2f  mov     ebx, eax
0x14008de31  test    eax, eax
0x14008de33  jns     short loc_14008DE3F
0x14008de35  mov     esi, 7B1h
0x14008de3a  jmp     loc_14008DF00
0x14008de3f  mov     rcx, rdi
0x14008de42  call    CscEnpDbInfoRelease
0x14008de47  xor     r9d, r9d
0x14008de4a  mov     [rsp+58h+var_38], rsi
0x14008de4f  xor     r8d, r8d
0x14008de52  mov     rcx, rdi
0x14008de55  lea     edx, [r9+4]
0x14008de59  call    CscEnpNotifyQuota
0x14008de5e  lea     rax, [rbp+var_28]
0x14008de62  xor     r9d, r9d
0x14008de65  mov     [rsp+58h+var_30], rax
0x14008de6a  lea     r8, [rbp+arg_18]
0x14008de6e  lea     rax, [rbp+var_20]
0x14008de72  mov     rdx, r14
0x14008de75  mov     rcx, rdi
0x14008de78  mov     [rsp+58h+var_38], rax
0x14008de7d  call    CscEnEvict
0x14008de82  mov     rcx, cs:WPP_GLOBAL_Control
0x14008de89  lea     rax, WPP_GLOBAL_Control
0x14008de90  cmp     rcx, rax
0x14008de93  jz      short loc_14008DEC0
0x14008de95  test    dword ptr [rcx+2Ch], 20000h
0x14008de9c  jz      short loc_14008DEC0
0x14008de9e  mov     rax, [rbp+var_28]
0x14008dea2  lea     r8, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids
0x14008dea9  mov     r9, [rbp+var_20]
0x14008dead  mov     edx, 20h ; ' '
0x14008deb2  mov     rcx, [rcx+18h]
0x14008deb6  mov     [rsp+58h+var_38], rax
0x14008debb  call    WPP_SF_qq
0x14008dec0  lea     rax, [rbp+var_28]
0x14008dec4  mov     edx, 8
0x14008dec9  lea     r9, [rbp+var_10]
0x14008decd  mov     [rsp+58h+var_38], rax
0x14008ded2  lea     r8, [rbp+var_20]
0x14008ded6  mov     rcx, rdi
0x14008ded9  call    CscEnpNotifyQuota
0x14008dede  mov     rcx, rdi
0x14008dee1  call    CscEnpDbInfoAcquireExclusive
0x14008dee6  xor     r8d, r8d
0x14008dee9  mov     edx, r15d
0x14008deec  mov     rcx, rdi
0x14008deef  call    CscEnpEvictpChangeDbStatus
0x14008def4  mov     ebx, eax
0x14008def6  mov     eax, 7DDh
0x14008defb  test    ebx, ebx
0x14008defd  cmovs   esi, eax
0x14008df00  mov     rcx, rdi
0x14008df03  call    CscEnpDbInfoRelease
0x14008df08  call    cs:__imp_KeLeaveCriticalRegion
0x14008df0f  nop     dword ptr [rax+rax+00h]
0x14008df14  test    r14, r14
0x14008df17  jz      short loc_14008DF22
0x14008df19  lea     rcx, [rbp+var_18]
0x14008df1d  call    CscEnEvictFreeEnumContext
0x14008df22  mov     rcx, cs:WPP_GLOBAL_Control
0x14008df29  lea     rax, WPP_GLOBAL_Control
0x14008df30  cmp     rcx, rax
0x14008df33  jz      short loc_14008DF5A
0x14008df35  test    dword ptr [rcx+2Ch], 20000h
0x14008df3c  jz      short loc_14008DF5A
0x14008df3e  mov     rcx, [rcx+18h]
0x14008df42  lea     r8, WPP_2dc78ab1835d3a2b6a689c5f087f77ec_Traceguids
0x14008df49  mov     edx, 21h ; '!'
0x14008df4e  mov     dword ptr [rsp+58h+var_38], esi
0x14008df52  mov     r9d, ebx
0x14008df55  call    WPP_SF_Dd
0x14008df5a  mov     eax, ebx
0x14008df5c  add     rsp, 58h
0x14008df60  pop     r15
0x14008df62  pop     r14
0x14008df64  pop     rdi
0x14008df65  pop     rsi
0x14008df66  pop     rbx
0x14008df67  pop     rbp
0x14008df68  retn
```
