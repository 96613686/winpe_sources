# GmsapGetPassword(_tagCredFetchInt,ushort const *,ushort const *,_tagGMsaListEntry * *,int *)

- ea: `0x180003e84`
- end: `0x18000430f`
- name: `?GmsapGetPassword@@YAJW4_tagCredFetchInt@@PEBG1PEAPEAU_tagGMsaListEntry@@PEAH@Z`
- size: `1163`
- prototype: `int __high(enum _tagCredFetchInt, const unsigned __int16 *, const unsigned __int16 *, struct _tagGMsaListEntry **, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1800036c0`

## callees

- `0x180002380`
- `0x180002a64`
- `0x180002b18`
- `0x180003200`
- `0x180003e84`
- `0x180004318`
- `0x180005018`
- `0x180006280`
- `0x1800062b0`
- `0x1800063cc`
- `0x180007a34`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042be`
- `ntdll!RtlReleaseResource` at `0x18000405c`
- `ntdll!RtlReleaseResource` at `0x18000405c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004071`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004071`

## pseudocode

```c
__int64 __fastcall GmsapGetPassword(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _tagGMsaListEntry **a4,
        BOOL *a5)
{
  struct _tagGMsaListEntry *v8; // rdi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r13
  unsigned __int16 *v11; // r14
  struct _tagGMsaListEntry *v12; // rsi
  const unsigned __int16 *v13; // r8
  int v14; // eax
  int PasswordDataWithRetry; // ebx
  void *v16; // rcx
  __int64 v17; // rcx
  int updated; // eax
  _QWORD *v19; // rcx
  int v20; // edx
  int v21; // esi
  BOOL v22; // ecx
  BOOL IsSameFileTime; // eax
  _QWORD *v24; // rax
  int v25; // eax
  HLOCAL v26; // r8
  __int64 v27; // rax
  _BYTE *v28; // rdx
  HLOCAL hMem; // [rsp+30h] [rbp-40h] BYREF
  int v31; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v32; // [rsp+3Ch] [rbp-34h] BYREF
  struct _tagGMsaListEntry *v33; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL v34; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v35; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL v36; // [rsp+58h] [rbp-18h]
  unsigned __int8 *v37; // [rsp+60h] [rbp-10h] BYREF
  FILETIME FileTime1; // [rsp+68h] [rbp-8h] BYREF

  FileTime1 = 0;
  v8 = 0;
  v31 = 0;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  v33 = 0;
  v11 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  hMem = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v9 = 0;
  }
  v12 = *a4;
  *a5 = 0;
  if ( v12 )
  {
    v13 = (const unsigned __int16 *)*((_QWORD *)v12 + 4);
    v8 = v12;
    v33 = v12;
    goto LABEL_12;
  }
  v14 = GmsapCrackDomainName(0, 1, a3, &v35, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v34);
  PasswordDataWithRetry = v14;
  if ( v14 >= 0 )
  {
    v11 = (unsigned __int16 *)v34;
    v12 = 0;
    v9 = v35;
    v13 = (const unsigned __int16 *)v34;
    v10 = (unsigned __int16 *)hMem;
    v36 = v35;
LABEL_12:
    PasswordDataWithRetry = GmsapFetchPasswordDataWithRetry(a2, v9, v13, &v32, &v37);
    hMem = v37;
    if ( PasswordDataWithRetry < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
          (_DWORD)a3,
          (__int64)a2,
          PasswordDataWithRetry);
      if ( ((a1 - 1) & 0xFFFFFFFD) != 0 && v8 )
      {
        v17 = 0;
        while ( *((_DWORD *)&g_StatusFatal + v17) != PasswordDataWithRetry )
        {
          v17 = (unsigned int)(v17 + 1);
          if ( (unsigned int)v17 >= 4 )
            goto LABEL_49;
        }
      }
      goto LABEL_50;
    }
    if ( a1 != 3 )
    {
      _InterlockedIncrement(&dword_18000B670);
      RtlReleaseResource(&Resource);
      RtlAcquireResourceExclusive(&Resource, 1u);
      _InterlockedDecrement(&dword_18000B670);
      if ( !v12 )
      {
        GmsapCheckGMSAInList(a2, 0, a3, &v33);
        v8 = v33;
      }
      if ( v8 )
      {
        FileTime1 = (FILETIME)*((_QWORD *)v8 + 5);
        updated = GmsapUpdateGMSAEntry((FILETIME *)v8, (struct _tagPasswordData *)hMem, &v31);
        PasswordDataWithRetry = updated;
        if ( updated < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_41;
          v20 = 76;
          goto LABEL_40;
        }
        IsSameFileTime = GmsapIsSameFileTime(&FileTime1, (FILETIME *)v8 + 5);
        v21 = v31;
        v22 = !IsSameFileTime;
      }
      else
      {
        updated = GmsapAddNewGMSAEntryToList(1, a2, v10, v11, (struct _tagPasswordData *)hMem, &v33);
        PasswordDataWithRetry = updated;
        if ( updated < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_41;
          v20 = 75;
LABEL_40:
          WPP_SF_SSD(
            v19[2],
            v20,
            (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
            (_DWORD)a3,
            (__int64)a2,
            updated);
LABEL_41:
          SCLockConvertExclusiveToShared();
LABEL_50:
          v26 = hMem;
          if ( hMem )
          {
            v27 = v32;
            v28 = hMem;
            if ( v32 )
            {
              do
              {
                *v28++ = 0;
                --v27;
              }
              while ( v27 );
            }
            LocalFree(v26);
          }
          v16 = v36;
          goto LABEL_55;
        }
        v8 = v33;
        v21 = 1;
        v22 = 1;
      }
      *a5 = v22;
      v24 = hMem;
      *((_DWORD *)v8 + 24) = 0;
      updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))&xmmword_18000B5B0 + 1))(
                  0,
                  *((_QWORD *)v8 + 2),
                  *((_QWORD *)v8 + 3),
                  *((unsigned int *)v24 + 16),
                  v24[7]);
      PasswordDataWithRetry = updated;
      if ( updated < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_41;
        v20 = 77;
        goto LABEL_40;
      }
      SCLockConvertExclusiveToShared();
      if ( v21 )
      {
        v25 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD))&xmmword_18000B5B0 + 1))(
                1,
                *((_QWORD *)v8 + 2),
                *((_QWORD *)v8 + 3));
        PasswordDataWithRetry = v25;
        if ( v25 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              78,
              (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
              (_DWORD)a3,
              (__int64)a2,
              v25);
          goto LABEL_50;
        }
      }
      if ( !*a4 )
        *a4 = v8;
    }
LABEL_49:
    PasswordDataWithRetry = 0;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      &WPP_70b8577d707437755865c965214ce19a_Traceguids,
      (unsigned int)v14);
  v16 = v35;
  v10 = (unsigned __int16 *)hMem;
  v11 = (unsigned __int16 *)v34;
LABEL_55:
  if ( v16 )
    LocalFree(v16);
  if ( v10 )
    LocalFree(v10);
  if ( v11 )
    LocalFree(v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      &WPP_70b8577d707437755865c965214ce19a_Traceguids,
      (unsigned int)PasswordDataWithRetry);
  return (unsigned int)PasswordDataWithRetry;
}

```

## disassembly

```asm
0x180003e84  mov     [rsp-38h+arg_8], rbx
0x180003e89  mov     [rsp-38h+arg_18], r9
0x180003e8e  mov     [rsp-38h+arg_0], ecx
0x180003e92  push    rbp
0x180003e93  push    rsi
0x180003e94  push    rdi
0x180003e95  push    r12
0x180003e97  push    r13
0x180003e99  push    r14
0x180003e9b  push    r15
0x180003e9d  mov     rbp, rsp
0x180003ea0  sub     rsp, 70h
0x180003ea4  mov     r15, rdx
0x180003ea7  mov     rbx, r9
0x180003eaa  xor     edx, edx
0x180003eac  mov     r12, r8
0x180003eaf  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdx
0x180003eb3  mov     edi, edx
0x180003eb5  mov     [rbp+var_38], edx
0x180003eb8  mov     eax, edx
0x180003eba  mov     [rbp+var_34], edx
0x180003ebd  mov     r13d, edx
0x180003ec0  mov     [rbp+var_30], rdx
0x180003ec4  mov     r14d, edx
0x180003ec7  mov     [rbp+var_10], rdx
0x180003ecb  mov     [rbp+var_18], rdx
0x180003ecf  mov     [rbp+var_20], rdx
0x180003ed3  mov     [rbp+hMem], rdx
0x180003ed7  mov     [rbp+var_28], rdx
0x180003edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ee2  lea     r8, WPP_GLOBAL_Control
0x180003ee9  cmp     rcx, r8
0x180003eec  jz      short loc_180003F0D
0x180003eee  test    byte ptr [rcx+1Ch], 8
0x180003ef2  jz      short loc_180003F0D
0x180003ef4  mov     rcx, [rcx+10h]
0x180003ef8  lea     edx, [r14+48h]
0x180003efc  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003f03  call    WPP_SF_
0x180003f08  mov     eax, r14d
0x180003f0b  xor     edx, edx
0x180003f0d  mov     rcx, [rbp+arg_20]
0x180003f11  mov     rsi, [rbx]
0x180003f14  mov     [rcx], edx
0x180003f16  test    rsi, rsi
0x180003f19  jz      short loc_180003F2B
0x180003f1b  mov     r8, [rsi+20h]
0x180003f1f  mov     rdi, rsi
0x180003f22  mov     [rbp+var_30], rsi
0x180003f26  jmp     loc_180003FAD
0x180003f2b  lea     rax, [rbp+var_28]
0x180003f2f  mov     r8, r12; unsigned __int16 *
0x180003f32  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x180003f37  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180003f3b  lea     rax, [rbp+hMem]
0x180003f3f  mov     edx, 1; int
0x180003f44  xor     ecx, ecx; int
0x180003f46  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x180003f4b  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x180003f50  mov     ebx, eax
0x180003f52  test    eax, eax
0x180003f54  jns     short loc_180003F98
0x180003f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f5d  lea     rsi, WPP_GLOBAL_Control
0x180003f64  cmp     rcx, rsi
0x180003f67  jz      short loc_180003F87
0x180003f69  test    byte ptr [rcx+1Ch], 4
0x180003f6d  jz      short loc_180003F87
0x180003f6f  mov     rcx, [rcx+10h]
0x180003f73  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003f7a  mov     edx, 49h ; 'I'
0x180003f7f  mov     r9d, eax
0x180003f82  call    WPP_SF_D
0x180003f87  mov     rcx, [rbp+var_20]
0x180003f8b  mov     r13, [rbp+hMem]
0x180003f8f  mov     r14, [rbp+var_28]
0x180003f93  jmp     loc_180004291
0x180003f98  mov     r14, [rbp+var_28]
0x180003f9c  xor     esi, esi
0x180003f9e  mov     rax, [rbp+var_20]
0x180003fa2  mov     r8, r14; unsigned __int16 *
0x180003fa5  mov     r13, [rbp+hMem]
0x180003fa9  mov     [rbp+var_18], rax
0x180003fad  lea     rcx, [rbp+var_10]
0x180003fb1  mov     rdx, rax; unsigned __int16 *
0x180003fb4  mov     [rsp+70h+var_50], rcx; unsigned __int8 **
0x180003fb9  lea     r9, [rbp+var_34]; unsigned int *
0x180003fbd  mov     rcx, r15; unsigned __int16 *
0x180003fc0  call    ?GmsapFetchPasswordDataWithRetry@@YAJPEBG00PEAKPEAPEAE@Z; GmsapFetchPasswordDataWithRetry(ushort const *,ushort const *,ushort const *,ulong *,uchar * *)
0x180003fc5  mov     ebx, eax
0x180003fc7  mov     rax, [rbp+var_10]
0x180003fcb  mov     [rbp+hMem], rax
0x180003fcf  test    ebx, ebx
0x180003fd1  jns     short loc_180004044
0x180003fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fda  lea     rsi, WPP_GLOBAL_Control
0x180003fe1  cmp     rcx, rsi
0x180003fe4  jz      short loc_18000400D
0x180003fe6  test    byte ptr [rcx+1Ch], 4
0x180003fea  jz      short loc_18000400D
0x180003fec  mov     rcx, [rcx+10h]
0x180003ff0  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003ff7  mov     edx, 4Ah ; 'J'
0x180003ffc  mov     dword ptr [rsp+70h+var_48], ebx
0x180004000  mov     r9, r12
0x180004003  mov     [rsp+70h+var_50], r15
0x180004008  call    WPP_SF_SSD
0x18000400d  mov     eax, [rbp+arg_0]
0x180004010  dec     eax
0x180004012  test    eax, 0FFFFFFFDh
0x180004017  jz      loc_18000425E
0x18000401d  test    rdi, rdi
0x180004020  jz      loc_18000425E
0x180004026  xor     ecx, ecx
0x180004028  lea     rdx, ?g_StatusFatal@@3PAJA; long near * g_StatusFatal
0x18000402f  cmp     [rdx+rcx*4], ebx
0x180004032  jz      loc_18000425E
0x180004038  inc     ecx
0x18000403a  cmp     ecx, 4
0x18000403d  jb      short loc_180004028
0x18000403f  jmp     loc_18000425C
0x180004044  cmp     [rbp+arg_0], 3
0x180004048  jz      loc_180004255
0x18000404e  lock inc cs:dword_18000B670
0x180004055  lea     rcx, Resource; Resource
0x18000405c  call    cs:__imp_RtlReleaseResource
0x180004063  nop     dword ptr [rax+rax+00h]
0x180004068  mov     dl, 1; Wait
0x18000406a  lea     rcx, Resource; Resource
0x180004071  call    cs:__imp_RtlAcquireResourceExclusive
0x180004078  nop     dword ptr [rax+rax+00h]
0x18000407d  lock dec cs:dword_18000B670
0x180004084  test    rsi, rsi
0x180004087  jnz     short loc_18000409E
0x180004089  lea     r9, [rbp+var_30]; struct _tagGMsaListEntry **
0x18000408d  mov     r8, r12; unsigned __int16 *
0x180004090  xor     edx, edx; unsigned __int16 *
0x180004092  mov     rcx, r15; unsigned __int16 *
0x180004095  call    ?GmsapCheckGMSAInList@@YAXPEBG00PEAPEAU_tagGMsaListEntry@@@Z; GmsapCheckGMSAInList(ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)
0x18000409a  mov     rdi, [rbp+var_30]
0x18000409e  mov     rdx, [rbp+hMem]; struct _tagPasswordData *
0x1800040a2  test    rdi, rdi
0x1800040a5  jnz     short loc_180004102
0x1800040a7  lea     rax, [rbp+var_30]
0x1800040ab  mov     r9, r14; unsigned __int16 *
0x1800040ae  mov     [rsp+70h+var_48], rax; struct _tagGMsaListEntry **
0x1800040b3  lea     ecx, [rdi+1]; int
0x1800040b6  mov     [rsp+70h+var_50], rdx; struct _tagPasswordData *
0x1800040bb  mov     r8, r13; unsigned __int16 *
0x1800040be  mov     rdx, r15; unsigned __int16 *
0x1800040c1  call    ?GmsapAddNewGMSAEntryToList@@YAJHPEBG00PEAU_tagPasswordData@@PEAPEAU_tagGMsaListEntry@@@Z; GmsapAddNewGMSAEntryToList(int,ushort const *,ushort const *,ushort const *,_tagPasswordData *,_tagGMsaListEntry * *)
0x1800040c6  mov     ebx, eax
0x1800040c8  test    eax, eax
0x1800040ca  jns     short loc_1800040F5
0x1800040cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040d3  lea     rsi, WPP_GLOBAL_Control
0x1800040da  cmp     rcx, rsi
0x1800040dd  jz      loc_1800041CF
0x1800040e3  test    byte ptr [rcx+1Ch], 4
0x1800040e7  jz      loc_1800041CF
0x1800040ed  lea     edx, [rdi+4Bh]
0x1800040f0  jmp     loc_1800041B3
0x1800040f5  mov     rdi, [rbp+var_30]
0x1800040f9  mov     esi, 1
0x1800040fe  mov     ecx, esi
0x180004100  jmp     short loc_18000415B
0x180004102  mov     rax, [rdi+28h]
0x180004106  lea     r8, [rbp+var_38]; int *
0x18000410a  mov     rcx, rdi; struct _tagGMsaListEntry *
0x18000410d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180004111  call    ?GmsapUpdateGMSAEntry@@YAJPEAU_tagGMsaListEntry@@PEAU_tagPasswordData@@PEAH@Z; GmsapUpdateGMSAEntry(_tagGMsaListEntry *,_tagPasswordData *,int *)
0x180004116  mov     ebx, eax
0x180004118  test    eax, eax
0x18000411a  jns     short loc_180004144
0x18000411c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004123  lea     rsi, WPP_GLOBAL_Control
0x18000412a  cmp     rcx, rsi
0x18000412d  jz      loc_1800041CF
0x180004133  test    byte ptr [rcx+1Ch], 4
0x180004137  jz      loc_1800041CF
0x18000413d  mov     edx, 4Ch ; 'L'
0x180004142  jmp     short loc_1800041B3
0x180004144  lea     rdx, [rdi+28h]; lpFileTime2
0x180004148  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18000414c  call    ?GmsapIsSameFileTime@@YAHPEBU_FILETIME@@0@Z; GmsapIsSameFileTime(_FILETIME const *,_FILETIME const *)
0x180004151  mov     esi, [rbp+var_38]
0x180004154  xor     ecx, ecx
0x180004156  test    eax, eax
0x180004158  setz    cl
0x18000415b  mov     rax, [rbp+arg_20]
0x18000415f  mov     [rax], ecx
0x180004161  mov     rax, [rbp+hMem]
0x180004165  mov     dword ptr [rdi+60h], 0
0x18000416c  mov     r8, [rdi+18h]
0x180004170  mov     rdx, [rdi+10h]
0x180004174  mov     rcx, [rax+38h]
0x180004178  mov     r9d, [rax+40h]
0x18000417c  mov     rax, qword ptr cs:xmmword_18000B5B0+8
0x180004183  mov     [rsp+70h+var_50], rcx
0x180004188  xor     ecx, ecx
0x18000418a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418f  mov     ebx, eax
0x180004191  test    eax, eax
0x180004193  jns     short loc_1800041D9
0x180004195  mov     rcx, cs:WPP_GLOBAL_Control
0x18000419c  lea     rsi, WPP_GLOBAL_Control
0x1800041a3  cmp     rcx, rsi
0x1800041a6  jz      short loc_1800041CF
0x1800041a8  test    byte ptr [rcx+1Ch], 4
0x1800041ac  jz      short loc_1800041CF
0x1800041ae  mov     edx, 4Dh ; 'M'
0x1800041b3  mov     rcx, [rcx+10h]
0x1800041b7  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800041be  mov     dword ptr [rsp+70h+var_48], eax
0x1800041c2  mov     r9, r12
0x1800041c5  mov     [rsp+70h+var_50], r15
0x1800041ca  call    WPP_SF_SSD
0x1800041cf  call    SCLockConvertExclusiveToShared
0x1800041d4  jmp     loc_18000425E
0x1800041d9  call    SCLockConvertExclusiveToShared
0x1800041de  test    esi, esi
0x1800041e0  jz      short loc_180004248
0x1800041e2  mov     r8, [rdi+18h]
0x1800041e6  xor     r9d, r9d
0x1800041e9  mov     rdx, [rdi+10h]
0x1800041ed  mov     rax, qword ptr cs:xmmword_18000B5B0+8
0x1800041f4  mov     [rsp+70h+var_50], 0
0x1800041fd  lea     ecx, [r9+1]
0x180004201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004206  mov     ebx, eax
0x180004208  test    eax, eax
0x18000420a  jns     short loc_180004248
0x18000420c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004213  lea     rsi, WPP_GLOBAL_Control
0x18000421a  cmp     rcx, rsi
0x18000421d  jz      short loc_18000425E
0x18000421f  test    byte ptr [rcx+1Ch], 4
0x180004223  jz      short loc_18000425E
0x180004225  mov     rcx, [rcx+10h]
0x180004229  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180004230  mov     dword ptr [rsp+70h+var_48], eax
0x180004234  mov     edx, 4Eh ; 'N'
0x180004239  mov     r9, r12
0x18000423c  mov     [rsp+70h+var_50], r15
0x180004241  call    WPP_SF_SSD
0x180004246  jmp     short loc_18000425E
0x180004248  mov     rax, [rbp+arg_18]
0x18000424c  cmp     qword ptr [rax], 0
0x180004250  jnz     short loc_180004255
0x180004252  mov     [rax], rdi
0x180004255  lea     rsi, WPP_GLOBAL_Control
0x18000425c  xor     ebx, ebx
0x18000425e  mov     r8, [rbp+hMem]
0x180004262  test    r8, r8
0x180004265  jz      short loc_18000428D
0x180004267  mov     eax, [rbp+var_34]
0x18000426a  mov     rdx, r8
0x18000426d  test    rax, rax
0x180004270  jz      short loc_18000427E
0x180004272  mov     byte ptr [rdx], 0
0x180004275  inc     rdx
0x180004278  sub     rax, 1
0x18000427c  jnz     short loc_180004272
0x18000427e  mov     rcx, r8; hMem
0x180004281  call    cs:__imp_LocalFree
0x180004288  nop     dword ptr [rax+rax+00h]
0x18000428d  mov     rcx, [rbp+var_18]; hMem
0x180004291  test    rcx, rcx
0x180004294  jz      short loc_1800042A2
0x180004296  call    cs:__imp_LocalFree
0x18000429d  nop     dword ptr [rax+rax+00h]
0x1800042a2  test    r13, r13
0x1800042a5  jz      short loc_1800042B6
0x1800042a7  mov     rcx, r13; hMem
0x1800042aa  call    cs:__imp_LocalFree
0x1800042b1  nop     dword ptr [rax+rax+00h]
0x1800042b6  test    r14, r14
0x1800042b9  jz      short loc_1800042CA
0x1800042bb  mov     rcx, r14; hMem
0x1800042be  call    cs:__imp_LocalFree
0x1800042c5  nop     dword ptr [rax+rax+00h]
0x1800042ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042d1  cmp     rcx, rsi
0x1800042d4  jz      short loc_1800042F4
0x1800042d6  test    byte ptr [rcx+1Ch], 8
0x1800042da  jz      short loc_1800042F4
0x1800042dc  mov     rcx, [rcx+10h]
0x1800042e0  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800042e7  mov     edx, 4Fh ; 'O'
0x1800042ec  mov     r9d, ebx
0x1800042ef  call    WPP_SF_D
0x1800042f4  mov     eax, ebx
0x1800042f6  mov     rbx, [rsp+70h+arg_8]
0x1800042fe  add     rsp, 70h
0x180004302  pop     r15
0x180004304  pop     r14
0x180004306  pop     r13
0x180004308  pop     r12
0x18000430a  pop     rdi
0x18000430b  pop     rsi
  ... truncated ...
```
