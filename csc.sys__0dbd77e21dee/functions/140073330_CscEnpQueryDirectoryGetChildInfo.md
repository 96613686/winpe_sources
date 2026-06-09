# CscEnpQueryDirectoryGetChildInfo

- ea: `0x140073330`
- end: `0x140073a8b`
- name: `CscEnpQueryDirectoryGetChildInfo`
- size: `1883`
- prototype: `__int64 __fastcall(unsigned __int64, __int16 *, __int64, unsigned __int16, __int64 (__fastcall *)(__int64), __int64, struct _UNICODE_STRING *, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x14005e5c4`
- `0x140072bc0`

## callees

- `0x140005328`
- `0x140005390`
- `0x14000b0e0`
- `0x14000ecb0`
- `0x14000fc60`
- `0x14000fcd0`
- `0x140011a30`
- `0x14001256c`
- `0x140012720`
- `0x140012d20`
- `0x1400190ec`
- `0x14001ac1c`
- `0x14002b518`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`
- `0x140073330`
- `0x140073aa0`
- `0x140073c50`

## import_xrefs

- `ntoskrnl!RtlAssert` at `0x14007373a`
- `ntoskrnl!RtlAssert` at `0x14007373a`

## pseudocode

```c
__int64 __fastcall CscEnpQueryDirectoryGetChildInfo(
        unsigned __int64 a1,
        __int16 *a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 (__fastcall *a5)(__int64),
        __int64 a6,
        struct _UNICODE_STRING *a7,
        __int64 a8,
        _BYTE *a9)
{
  unsigned int v11; // r15d
  __int16 v12; // dx
  unsigned __int8 VisibiliyInPqInfo; // r13
  int v14; // edi
  int v15; // esi
  int UserInfo; // edi
  struct _UNICODE_STRING *v17; // rdx
  _WORD *v19; // rax
  __int64 v20; // rax
  struct _UNICODE_STRING *v21; // r12
  struct _UNICODE_STRING *v22; // rdx
  struct _UNICODE_STRING *v23; // rax
  int Entry; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  bool v27; // zf
  _QWORD *v28; // rcx
  struct _UNICODE_STRING v29; // xmm0
  struct _UNICODE_STRING v30; // xmm1
  struct _UNICODE_STRING v31; // xmm0
  struct _UNICODE_STRING v32; // xmm1
  struct _UNICODE_STRING v33; // xmm0
  struct _UNICODE_STRING *v34; // rcx
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING *v36; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE *v37; // [rsp+68h] [rbp-A0h]
  __int64 v38; // [rsp+70h] [rbp-98h]
  __int64 (__fastcall *v39)(__int64); // [rsp+78h] [rbp-90h]
  __int64 v40; // [rsp+80h] [rbp-88h]
  _OWORD v41[2]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v42[11]; // [rsp+A8h] [rbp-60h] BYREF

  v39 = a5;
  v40 = a6;
  v38 = a3;
  v37 = a9;
  v11 = a4;
  v36 = 0;
  memset(v42, 0, 0xA8u);
  v12 = *a2;
  VisibiliyInPqInfo = 0;
  LOBYTE(v35) = 0;
  if ( v12 == 2 && **((_WORD **)a2 + 1) == 46 )
  {
    *(_OWORD *)a8 = *(_OWORD *)(a1 + 288);
    *(_OWORD *)(a8 + 16) = *(_OWORD *)(a1 + 304);
    *(_OWORD *)(a8 + 32) = *(_OWORD *)(a1 + 320);
    *(_QWORD *)(a8 + 48) = *(_QWORD *)(a1 + 336);
    memset(a7, 0, 0x50u);
    UserInfo = 0;
    v15 = 614;
    goto LABEL_10;
  }
  if ( v12 != 4 || (v19 = (_WORD *)*((_QWORD *)a2 + 1), *v19 != 46) || v19[1] != 46 )
  {
    v14 = *(_DWORD *)(a1 + 16);
    if ( !v14 )
    {
      *(_OWORD *)a8 = 0;
      *(_OWORD *)(a8 + 16) = 0;
      *(_OWORD *)(a8 + 32) = 0;
      *(_QWORD *)(a8 + 48) = 0;
      memset(a7, 0, 0x50u);
      *(_DWORD *)(a8 + 48) = 16;
      v15 = 681;
      *(_DWORD *)&a7->Length |= 0x40u;
      UserInfo = 0;
      goto LABEL_9;
    }
    if ( v14 != 1 && (unsigned int)(v14 - 2) >= 2 )
      RtlAssert("0", "base\\fs\\remotefs\\rdr\\csc\\newdb\\entry_i.h", 0x47Du, 0);
    v23 = (struct _UNICODE_STRING *)CscEnpLookupChildInMemory(a1, a2, 0);
    v36 = v23;
    if ( v23 )
    {
      if ( (_WORD)v11 )
      {
        CscEnpFieldUpdateAcquireExclusive((__int64)v23);
        UserInfo = CscEnpUserQueryUserInfoEx(
                     (_DWORD)v36,
                     (unsigned __int16)v11,
                     (unsigned int)&v35,
                     0,
                     0,
                     0,
                     (__int64)v37);
      }
      else
      {
        UserInfo = 0;
        CscEnpFieldUpdateAcquireShared((__int64)v23);
      }
      v34 = v36;
      *(struct _UNICODE_STRING *)a8 = v36[18];
      *(struct _UNICODE_STRING *)(a8 + 16) = v34[19];
      *(struct _UNICODE_STRING *)(a8 + 32) = v34[20];
      *(_QWORD *)(a8 + 48) = *(_QWORD *)&v34[21].Length;
      *a7 = v34[12];
      a7[1] = v34[13];
      a7[2] = v34[14];
      a7[3] = v34[15];
      a7[4] = v34[16];
      if ( v34[25].Length )
        *(_DWORD *)&a7->Length |= 0x80u;
      if ( LOBYTE(v34[27].Buffer) || (*(_DWORD *)(&v34[1].MaximumLength + 1) & 8) != 0 )
        *(_DWORD *)&a7->Length |= 0x200000u;
      CscEnpFieldUpdateRelease((__int64)v34);
      v15 = 736;
      goto LABEL_9;
    }
    if ( !v39 )
    {
      Entry = CscPqQueryEntry(
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                *(unsigned int *)(v38 + 8),
                *(_QWORD *)(v38 + 96),
                v42);
      UserInfo = Entry;
      if ( Entry < 0 )
      {
        if ( Entry != -1073741802 )
        {
          v15 = 753;
          goto LABEL_9;
        }
      }
      else
      {
        v25 = *(_QWORD *)(a1 + 8);
        v26 = *(_QWORD *)((char *)&v42[7] + 4) - *(_QWORD *)(v25 + 264);
        if ( *(_QWORD *)((char *)&v42[7] + 4) == *(_QWORD *)(v25 + 264) )
          v26 = *(_QWORD *)((char *)&v42[7] + 12) - *(_QWORD *)(v25 + 272);
        if ( !v26 )
        {
          if ( (_WORD)v11 )
            VisibiliyInPqInfo = CscEnpUserFindVisibiliyInPqInfo(v42, (unsigned __int16)v11, v37);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              11,
              WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids,
              v11,
              VisibiliyInPqInfo);
          }
          if ( !(_WORD)v11 || VisibiliyInPqInfo )
          {
            v27 = WORD1(v42[6]) == 0;
            v28 = (_QWORD *)v38;
            v29 = (struct _UNICODE_STRING)v42[0];
            v30 = (struct _UNICODE_STRING)v42[1];
            *(_QWORD *)a8 = *(_QWORD *)(v38 + 8);
            *(_QWORD *)(a8 + 8) = v28[2];
            *(_QWORD *)(a8 + 16) = v28[3];
            *(_QWORD *)(a8 + 24) = v28[4];
            *(_QWORD *)(a8 + 32) = v28[6];
            *(_QWORD *)(a8 + 40) = v28[5];
            *(_DWORD *)(a8 + 48) = DWORD2(v42[5]);
            *(_QWORD *)a8 = *(_QWORD *)&v42[5];
            *a7 = v29;
            v31 = (struct _UNICODE_STRING)v42[2];
            a7[1] = v30;
            v32 = (struct _UNICODE_STRING)v42[3];
            a7[2] = v31;
            v33 = (struct _UNICODE_STRING)v42[4];
            a7[3] = v32;
            a7[4] = v33;
            if ( !v27 )
              *(_DWORD *)&a7->Length |= 0x80u;
            v15 = 799;
            UserInfo = 0;
            goto LABEL_9;
          }
        }
      }
    }
    UserInfo = CscEnpLookupChildInFileSystem(a1, (struct _LIST_ENTRY *)a2, 0, &v36);
    if ( UserInfo >= 0 )
    {
      v15 = 0;
      if ( (_WORD)v11 )
      {
        v21 = v36;
        memset(v41, 0, sizeof(v41));
        LOBYTE(v35) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_0614c5833ce33c8bd689fd5b76b78206_Traceguids, v36, v11);
        }
        CscEnpFieldUpdateAcquireExclusive((__int64)v21);
        UserInfo = CscEnpUserQuerySetUserInfo((_DWORD)v21, 0, (unsigned __int16)v11, (unsigned int)&v35, (__int64)v41);
        CscEnpFieldUpdateRelease((__int64)v21);
        if ( v37 )
          *v37 = BYTE9(v41[0]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_cDDDcDD(WPP_GLOBAL_Control->AttachedDevice, 23);
        }
      }
      v22 = v36;
      *(struct _UNICODE_STRING *)a8 = v36[18];
      *(struct _UNICODE_STRING *)(a8 + 16) = v22[19];
      *(struct _UNICODE_STRING *)(a8 + 32) = v22[20];
      *(_QWORD *)(a8 + 48) = *(_QWORD *)&v22[21].Length;
      *a7 = v22[12];
      a7[1] = v22[13];
      a7[2] = v22[14];
      a7[3] = v22[15];
      a7[4] = v22[16];
      if ( v22[25].Length )
        *(_DWORD *)&a7->Length |= 0x80u;
    }
    else
    {
      v15 = 840;
    }
    goto LABEL_9;
  }
  if ( *(_DWORD *)(a1 + 16) == 2 )
  {
    *(_OWORD *)a8 = *(_OWORD *)(a1 + 288);
    *(_OWORD *)(a8 + 16) = *(_OWORD *)(a1 + 304);
    *(_OWORD *)(a8 + 32) = *(_OWORD *)(a1 + 320);
    *(_QWORD *)(a8 + 48) = *(_QWORD *)(a1 + 336);
  }
  else
  {
    CscEnpMainAcquireShared(*(_QWORD *)(a1 + 24));
    v20 = *(_QWORD *)(a1 + 24);
    *(_OWORD *)a8 = *(_OWORD *)(v20 + 288);
    *(_OWORD *)(a8 + 16) = *(_OWORD *)(v20 + 304);
    *(_OWORD *)(a8 + 32) = *(_OWORD *)(v20 + 320);
    *(_QWORD *)(a8 + 48) = *(_QWORD *)(v20 + 336);
    CscEnpMainRelease(*(_QWORD *)(a1 + 24));
  }
  memset(a7, 0, 0x50u);
  UserInfo = 0;
  v15 = 661;
LABEL_9:
  v17 = v36;
  if ( v36 )
  {
    if ( v39 )
    {
      if ( UserInfo >= 0 )
      {
        UserInfo = v39(v40);
        if ( UserInfo < 0 )
          v15 = 882;
      }
    }
    LOBYTE(v17) = 1;
    CscEnpDereferenceEntryEx((__int64)&v36, (__int64)v17);
  }
LABEL_10:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids,
      (unsigned int)UserInfo,
      v15);
  return (unsigned int)UserInfo;
}

```

## disassembly

```asm
0x140073330  mov     r11, rsp
0x140073333  push    rbp
0x140073334  push    rsi
0x140073335  push    rdi
0x140073336  lea     rbp, [r11-0A8h]
0x14007333d  sub     rsp, 190h
0x140073344  mov     rax, cs:__security_cookie
0x14007334b  xor     rax, rsp
0x14007334e  mov     [rbp+0A0h+var_50], rax
0x140073352  mov     rax, [rbp+0A0h+arg_20]
0x140073359  mov     rsi, rcx
0x14007335c  mov     [r11-20h], rbx
0x140073360  lea     rcx, [rbp+0A0h+var_100]; void *
0x140073364  mov     rbx, [rbp+0A0h+arg_38]
0x14007336b  mov     [r11-28h], r12
0x14007336f  mov     r12, rdx
0x140073372  mov     [rsp+1A0h+var_130], rax
0x140073377  xor     edx, edx; Val
0x140073379  mov     rax, [rbp+0A0h+arg_28]
0x140073380  mov     [r11-30h], r13
0x140073384  mov     [r11-38h], r14
0x140073388  mov     r14, [rbp+0A0h+arg_30]
0x14007338f  mov     [rsp+1A0h+var_128], rax
0x140073394  mov     rax, [rbp+0A0h+arg_40]
0x14007339b  mov     [rsp+1A0h+var_138], r8
0x1400733a0  mov     r8d, 0A8h; Size
0x1400733a6  mov     [r11-40h], r15
0x1400733aa  mov     [rsp+1A0h+var_140], rax
0x1400733af  movzx   r15d, r9w
0x1400733b3  mov     [rsp+1A0h+var_148], 0
0x1400733bc  call    memset
0x1400733c1  movzx   edx, word ptr [r12]
0x1400733c6  xor     r13b, r13b
0x1400733c9  mov     eax, 2
0x1400733ce  mov     byte ptr [rsp+1A0h+var_150], r13b
0x1400733d3  mov     r8d, 2Eh ; '.'
0x1400733d9  cmp     ax, dx
0x1400733dc  jz      short loc_14007342F
0x1400733de  mov     eax, 4
0x1400733e3  cmp     ax, dx
0x1400733e6  jz      loc_140073512
0x1400733ec  mov     edi, [rsi+10h]
0x1400733ef  test    edi, edi
0x1400733f1  jnz     loc_140073712
0x1400733f7  xorps   xmm0, xmm0
0x1400733fa  xor     eax, eax
0x1400733fc  movups  xmmword ptr [rbx], xmm0
0x1400733ff  xor     edx, edx; Val
0x140073401  mov     r8d, 50h ; 'P'; Size
0x140073407  movups  xmmword ptr [rbx+10h], xmm0
0x14007340b  mov     rcx, r14; void *
0x14007340e  movups  xmmword ptr [rbx+20h], xmm0
0x140073412  mov     [rbx+30h], rax
0x140073416  call    memset
0x14007341b  mov     dword ptr [rbx+30h], 10h
0x140073422  mov     esi, 2A9h
0x140073427  or      dword ptr [r14], 40h
0x14007342b  xor     edi, edi
0x14007342d  jmp     short loc_1400734A2
0x14007342f  mov     rax, [r12+8]
0x140073434  cmp     r8w, [rax]
0x140073438  jnz     short loc_1400733DE
0x14007343a  movups  xmm0, xmmword ptr [rsi+120h]
0x140073441  xor     edx, edx; Val
0x140073443  mov     r8d, 50h ; 'P'; Size
0x140073449  mov     rcx, r14; void *
0x14007344c  movups  xmmword ptr [rbx], xmm0
0x14007344f  movups  xmm1, xmmword ptr [rsi+130h]
0x140073456  movups  xmmword ptr [rbx+10h], xmm1
0x14007345a  movups  xmm0, xmmword ptr [rsi+140h]
0x140073461  movups  xmmword ptr [rbx+20h], xmm0
0x140073465  movsd   xmm1, qword ptr [rsi+150h]
0x14007346d  movsd   qword ptr [rbx+30h], xmm1
0x140073472  call    memset
0x140073477  xor     edi, edi
0x140073479  mov     esi, 266h
0x14007347e  jmp     short loc_1400734B0
0x140073480  lea     r9, [rsp+1A0h+var_148]
0x140073485  xor     r8d, r8d
0x140073488  mov     rdx, r12
0x14007348b  mov     rcx, rsi
0x14007348e  call    CscEnpLookupChildInFileSystem
0x140073493  mov     edi, eax
0x140073495  test    eax, eax
0x140073497  jns     loc_1400735B4
0x14007349d  mov     esi, 348h
0x1400734a2  mov     rdx, [rsp+1A0h+var_148]
0x1400734a7  test    rdx, rdx
0x1400734aa  jnz     loc_140073595
0x1400734b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400734b7  lea     rax, WPP_GLOBAL_Control
0x1400734be  mov     r15, [rsp+1A0h+var_38]
0x1400734c6  mov     r14, [rsp+1A0h+var_30]
0x1400734ce  mov     r13, [rsp+1A0h+var_28]
0x1400734d6  mov     r12, [rsp+1A0h+var_20]
0x1400734de  mov     rbx, [rsp+188h]
0x1400734e6  cmp     rcx, rax
0x1400734e9  jz      short loc_1400734F8
0x1400734eb  test    dword ptr [rcx+2Ch], 20000h
0x1400734f2  jnz     loc_140073A6A
0x1400734f8  mov     eax, edi
0x1400734fa  mov     rcx, [rbp+0A0h+var_50]
0x1400734fe  xor     rcx, rsp; StackCookie
0x140073501  call    __security_check_cookie
0x140073506  add     rsp, 190h
0x14007350d  pop     rdi
0x14007350e  pop     rsi
0x14007350f  pop     rbp
0x140073510  retn
0x140073512  mov     rax, [r12+8]
0x140073517  cmp     r8w, [rax]
0x14007351b  jnz     loc_1400733EC
0x140073521  cmp     r8w, [rax+2]
0x140073526  jnz     loc_1400733EC
0x14007352c  cmp     dword ptr [rsi+10h], 2
0x140073530  jz      loc_1400736E0
0x140073536  mov     rcx, [rsi+18h]
0x14007353a  call    CscEnpMainAcquireShared
0x14007353f  mov     rax, [rsi+18h]
0x140073543  movups  xmm0, xmmword ptr [rax+120h]
0x14007354a  movups  xmmword ptr [rbx], xmm0
0x14007354d  movups  xmm1, xmmword ptr [rax+130h]
0x140073554  movups  xmmword ptr [rbx+10h], xmm1
0x140073558  movups  xmm0, xmmword ptr [rax+140h]
0x14007355f  movups  xmmword ptr [rbx+20h], xmm0
0x140073563  movsd   xmm1, qword ptr [rax+150h]
0x14007356b  movsd   qword ptr [rbx+30h], xmm1
0x140073570  mov     rcx, [rsi+18h]
0x140073574  call    CscEnpMainRelease
0x140073579  xor     edx, edx; Val
0x14007357b  mov     r8d, 50h ; 'P'; Size
0x140073581  mov     rcx, r14; void *
0x140073584  call    memset
0x140073589  xor     edi, edi
0x14007358b  mov     esi, 295h
0x140073590  jmp     loc_1400734A2
0x140073595  mov     rax, [rsp+1A0h+var_130]
0x14007359a  test    rax, rax
0x14007359d  jnz     loc_140073A47
0x1400735a3  mov     dl, 1
0x1400735a5  lea     rcx, [rsp+1A0h+var_148]
0x1400735aa  call    CscEnpDereferenceEntryEx
0x1400735af  jmp     loc_1400734B0
0x1400735b4  xor     esi, esi
0x1400735b6  test    r15w, r15w
0x1400735ba  jz      loc_14007365A
0x1400735c0  mov     r12, [rsp+1A0h+var_148]
0x1400735c5  xorps   xmm0, xmm0
0x1400735c8  movups  [rbp+0A0h+var_120], xmm0
0x1400735cc  mov     byte ptr [rsp+1A0h+var_150], sil
0x1400735d1  movups  [rbp+0A0h+var_110], xmm0
0x1400735d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400735dc  lea     r13, WPP_GLOBAL_Control
0x1400735e3  cmp     rcx, r13
0x1400735e6  jz      short loc_1400735F5
0x1400735e8  test    dword ptr [rcx+2Ch], 40000h
0x1400735ef  jnz     loc_1400739D1
0x1400735f5  mov     rcx, r12
0x1400735f8  call    CscEnpFieldUpdateAcquireExclusive
0x1400735fd  lea     rax, [rbp+0A0h+var_120]
0x140073601  movzx   r8d, r15w
0x140073605  lea     r9, [rsp+1A0h+var_150]
0x14007360a  mov     [rsp+1A0h+var_180], rax
0x14007360f  xor     edx, edx
0x140073611  mov     rcx, r12
0x140073614  call    CscEnpUserQuerySetUserInfo
0x140073619  mov     rcx, r12
0x14007361c  mov     edi, eax
0x14007361e  call    CscEnpFieldUpdateRelease
0x140073623  xor     r10d, r10d
0x140073626  mov     eax, 7C0h
0x14007362b  test    edi, edi
0x14007362d  cmovs   r10d, eax
0x140073631  mov     rax, [rsp+1A0h+var_140]
0x140073636  movzx   edx, byte ptr [rbp+0A0h+var_120+9]
0x14007363a  test    rax, rax
0x14007363d  jz      short loc_140073641
0x14007363f  mov     [rax], dl
0x140073641  mov     rcx, cs:WPP_GLOBAL_Control
0x140073648  cmp     rcx, r13
0x14007364b  jz      short loc_14007365A
0x14007364d  test    dword ptr [rcx+2Ch], 40000h
0x140073654  jnz     loc_1400739F3
0x14007365a  mov     rdx, [rsp+1A0h+var_148]
0x14007365f  movups  xmm0, xmmword ptr [rdx+120h]
0x140073666  movups  xmmword ptr [rbx], xmm0
0x140073669  movups  xmm1, xmmword ptr [rdx+130h]
0x140073670  movups  xmmword ptr [rbx+10h], xmm1
0x140073674  movups  xmm0, xmmword ptr [rdx+140h]
0x14007367b  movups  xmmword ptr [rbx+20h], xmm0
0x14007367f  movsd   xmm1, qword ptr [rdx+150h]
0x140073687  movsd   qword ptr [rbx+30h], xmm1
0x14007368c  movups  xmm0, xmmword ptr [rdx+0C0h]
0x140073693  movups  xmmword ptr [r14], xmm0
0x140073697  movups  xmm1, xmmword ptr [rdx+0D0h]
0x14007369e  movups  xmmword ptr [r14+10h], xmm1
0x1400736a3  movups  xmm0, xmmword ptr [rdx+0E0h]
0x1400736aa  movups  xmmword ptr [r14+20h], xmm0
0x1400736af  movups  xmm1, xmmword ptr [rdx+0F0h]
0x1400736b6  movups  xmmword ptr [r14+30h], xmm1
0x1400736bb  movups  xmm0, xmmword ptr [rdx+100h]
0x1400736c2  movups  xmmword ptr [r14+40h], xmm0
0x1400736c7  cmp     [rdx+190h], si
0x1400736ce  jz      loc_1400734A2
0x1400736d4  or      dword ptr [r14], 80h
0x1400736db  jmp     loc_1400734A2
0x1400736e0  movups  xmm0, xmmword ptr [rsi+120h]
0x1400736e7  movups  xmmword ptr [rbx], xmm0
0x1400736ea  movups  xmm1, xmmword ptr [rsi+130h]
0x1400736f1  movups  xmmword ptr [rbx+10h], xmm1
0x1400736f5  movups  xmm0, xmmword ptr [rsi+140h]
0x1400736fc  movups  xmmword ptr [rbx+20h], xmm0
0x140073700  movsd   xmm1, qword ptr [rsi+150h]
0x140073708  movsd   qword ptr [rbx+30h], xmm1
0x14007370d  jmp     loc_140073579
0x140073712  mov     ecx, edi
0x140073714  sub     ecx, 1
0x140073717  jz      short loc_14007374F
0x140073719  sub     ecx, 1
0x14007371c  jz      short loc_14007374F
0x14007371e  cmp     ecx, 1
0x140073721  jz      short loc_14007374F
0x140073723  xor     r9d, r9d; MutableMessage
0x140073726  lea     rdx, aBaseFsRemotefs_1; "base\\fs\\remotefs\\rdr\\csc\\newdb\\en"...
0x14007372d  mov     r8d, 47Dh; LineNumber
0x140073733  lea     rcx, a0; "0"
0x14007373a  call    cs:__imp_RtlAssert
0x140073741  nop     dword ptr [rax+rax+00h]
0x140073746  cmp     edi, 1
0x140073749  jz      loc_1400733F7
0x14007374f  xor     r8d, r8d
0x140073752  mov     rdx, r12
0x140073755  mov     rcx, rsi
0x140073758  call    CscEnpLookupChildInMemory
0x14007375d  mov     [rsp+1A0h+var_148], rax
0x140073762  test    rax, rax
0x140073765  jnz     loc_1400738A6
0x14007376b  cmp     [rsp+1A0h+var_130], rax
0x140073770  jnz     loc_140073480
0x140073776  mov     rdx, [rsp+1A0h+var_138]
0x14007377b  lea     r9, [rbp+0A0h+var_100]
0x14007377f  mov     rcx, [rsi+8]
0x140073783  mov     r8, [rdx+60h]
0x140073787  mov     edx, [rdx+8]
0x14007378a  mov     rcx, [rcx+30h]
0x14007378e  call    CscPqQueryEntry
0x140073793  mov     edi, eax
0x140073795  test    eax, eax
0x140073797  js      loc_140073891
0x14007379d  mov     rdx, [rsi+8]
0x1400737a1  mov     rcx, [rbp+0A0h+var_8C]
0x1400737a5  sub     rcx, [rdx+108h]
0x1400737ac  jnz     short loc_1400737B9
0x1400737ae  mov     rcx, [rbp+0A0h+var_84]
0x1400737b2  sub     rcx, [rdx+110h]
0x1400737b9  test    rcx, rcx
0x1400737bc  jnz     loc_140073480
0x1400737c2  test    r15w, r15w
0x1400737c6  jz      short loc_1400737DE
0x1400737c8  mov     r8, [rsp+1A0h+var_140]
0x1400737cd  lea     rcx, [rbp+0A0h+var_100]
0x1400737d1  movzx   edx, r15w
0x1400737d5  call    CscEnpUserFindVisibiliyInPqInfo
0x1400737da  movzx   r13d, al
0x1400737de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400737e5  lea     rax, WPP_GLOBAL_Control
0x1400737ec  cmp     rcx, rax
0x1400737ef  jz      short loc_1400737FE
0x1400737f1  test    dword ptr [rcx+2Ch], 40000h
0x1400737f8  jnz     loc_1400739A0
0x1400737fe  test    r15w, r15w
0x140073802  jz      short loc_14007380D
0x140073804  test    r13b, r13b
0x140073807  jz      loc_140073480
0x14007380d  cmp     [rbp+0A0h+var_9E], 0
0x140073812  mov     rcx, [rsp+1A0h+var_138]
0x140073817  movaps  xmm0, [rbp+0A0h+var_100]
0x14007381b  movaps  xmm1, [rbp+0A0h+var_F0]
0x14007381f  mov     rax, [rcx+8]
0x140073823  mov     [rbx], rax
0x140073826  mov     rax, [rcx+10h]
0x14007382a  mov     [rbx+8], rax
0x14007382e  mov     rax, [rcx+18h]
0x140073832  mov     [rbx+10h], rax
0x140073836  mov     rax, [rcx+20h]
0x14007383a  mov     [rbx+18h], rax
0x14007383e  mov     rax, [rcx+30h]
0x140073842  mov     [rbx+20h], rax
0x140073846  mov     rax, [rcx+28h]
0x14007384a  mov     [rbx+28h], rax
0x14007384e  mov     eax, [rbp+0A0h+var_A8]
0x140073851  mov     [rbx+30h], eax
0x140073854  mov     rax, [rbp+0A0h+var_B0]
0x140073858  mov     [rbx], rax
0x14007385b  movups  xmmword ptr [r14], xmm0
0x14007385f  movaps  xmm0, [rbp+0A0h+var_E0]
0x140073863  movups  xmmword ptr [r14+10h], xmm1
0x140073868  movaps  xmm1, [rbp+0A0h+var_D0]
0x14007386c  movups  xmmword ptr [r14+20h], xmm0
0x140073871  movaps  xmm0, [rbp+0A0h+var_C0]
  ... truncated ...
```
