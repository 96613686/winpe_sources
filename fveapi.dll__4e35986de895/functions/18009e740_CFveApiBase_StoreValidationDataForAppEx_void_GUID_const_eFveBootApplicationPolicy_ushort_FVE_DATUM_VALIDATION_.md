# CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)

- ea: `0x18009e740`
- end: `0x18009eca2`
- name: `?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z`
- size: `1378`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180098fc8`
- `0x180099a58`
- `0x18009c910`
- `0x18009d1d0`
- `0x18009d858`
- `0x1800c7ff8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x18000ba30`
- `0x180018b10`
- `0x18003e7a8`
- `0x180044da4`
- `0x180049638`
- `0x18004a354`
- `0x1800500dc`
- `0x180098f48`
- `0x18009e740`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18009ec46`
- `msvcrt!??3@YAXPEAX@Z` at `0x180124a38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009ec46`
- `msvcrt!??3@YAXPEAX@Z` at `0x180124a38`
- `bcd!BcdQueryObject` at `0x18009e9ab`
- `bcd!BcdQueryObject` at `0x18009e9ab`
- `bcd!BcdCloseObject` at `0x18009ec21`
- `bcd!BcdCloseObject` at `0x180124a13`
- `bcd!BcdCloseObject` at `0x18009ec21`
- `bcd!BcdCloseObject` at `0x180124a13`
- `bcd!BcdOpenObject` at `0x18009e82c`
- `bcd!BcdOpenObject` at `0x18009e82c`

## pseudocode

```c
__int64 __fastcall CFveApiBase::StoreValidationDataForAppEx(
        CFveApiBase *a1,
        void *a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct _FVE_DATUM_VALIDATION_ENTRY *a6,
        unsigned __int16 *a7,
        char a8,
        unsigned __int8 a9)
{
  int Policy; // ebx
  int v13; // eax
  unsigned __int16 i; // r14
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  CFveApiBase *v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 j; // r11
  unsigned int v22; // r13d
  struct _FVE_DATUM_VALIDATION_ENTRY *v23; // rcx
  int v24; // r11d
  __int64 v25; // r8
  __int64 v26; // rcx
  int BcdElementsList; // eax
  unsigned int k; // esi
  __int64 v29; // rcx
  unsigned int v30; // ebx
  __int64 v31; // r11
  unsigned int v32; // edx
  unsigned int v33; // r13d
  struct _FVE_DATUM_VALIDATION_ENTRY *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r11
  int v37; // eax
  unsigned __int16 v39; // [rsp+48h] [rbp-B0h]
  unsigned int v40; // [rsp+50h] [rbp-A8h] BYREF
  void *lpMem; // [rsp+58h] [rbp-A0h] BYREF
  _DWORD *v42; // [rsp+60h] [rbp-98h]
  unsigned int v43; // [rsp+68h] [rbp-90h]
  struct CFvePolicy *v44; // [rsp+70h] [rbp-88h] BYREF
  unsigned __int64 v45; // [rsp+78h] [rbp-80h]
  __int64 v46; // [rsp+80h] [rbp-78h]
  void *v47; // [rsp+88h] [rbp-70h]
  __int64 v48; // [rsp+90h] [rbp-68h]
  void *v49; // [rsp+98h] [rbp-60h] BYREF
  struct _GUID v50; // [rsp+A0h] [rbp-58h] BYREF

  v43 = a4;
  v47 = a2;
  v40 = 0;
  lpMem = 0;
  v49 = 0;
  v44 = 0;
  v42 = 0;
  v45 = 0;
  v46 = 0;
  v50 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  Policy = CFveApiBase::GetPolicy(a1, &v44);
  if ( Policy >= 0 )
  {
    if ( !a3 || (v13 = BcdOpenObject(a2, a3, &v49), Policy = FromNtStatus(v13), Policy >= 0) )
    {
      if ( v49 )
      {
        for ( i = 0; i < *a7 && *((_WORD *)a6 + 20 * i) == 2; ++i )
          ;
        if ( a8 )
        {
          if ( *a7 >= a5 )
          {
LABEL_14:
            Policy = -2147024883;
            goto LABEL_54;
          }
          v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 )
            v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4;
          if ( !v15 )
            goto LABEL_25;
          v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1 )
            v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_DEFAULT_BOOT_ENTRY.Data4;
          if ( v16 )
          {
            v50 = *a3;
          }
          else
          {
LABEL_25:
            v19 = BcdQueryObject(v49, 0, 0, &v50);
            v20 = FromNtStatus(v19);
            Policy = v20;
            if ( v20 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  &WPP_1559182127783aab3882fe828952d989_Traceguids,
                  (unsigned int)v20);
              goto LABEL_54;
            }
          }
          v17 = FveDatumValidationInfoDataEntry(0, &v50, 16, (char *)a6 + 40 * *a7);
          Policy = FromNtStatus(v17);
          if ( Policy < 0 )
            goto LABEL_54;
          *((_WORD *)a6 + 20 * *a7) = 4;
          v18 = (CFveApiBase *)(5LL * *a7);
          *((_WORD *)a6 + 4 * (_QWORD)v18 + 1) = 2 * a9;
          ++*a7;
          Policy = CFveApiBase::AddAppHashEntry(v18, v49, a5, a6, a7);
          if ( Policy < 0 )
          {
            --*a7;
            goto LABEL_54;
          }
        }
        v39 = *a7;
      }
      else
      {
        *a7 = 0;
        i = 0;
        v39 = 0;
      }
      Policy = CFveBcdSettings::GetIgnoredBcdSettings(*((_QWORD *)v44 + 1) + 56LL, v43);
      if ( Policy >= 0 )
      {
        for ( j = 0; (unsigned int)j < v45; j = (unsigned int)(v24 + 1) )
        {
          v22 = v42[j];
          if ( !HasDupEntry(a6, 0, i, v22) && !HasDupEntry(v23, v39, *a7, v22) )
          {
            if ( (unsigned __int16)v25 >= a5 )
              goto LABEL_14;
            v26 = 5 * v25;
            *(_OWORD *)((char *)a6 + 8 * v26) = 0;
            *(_OWORD *)((char *)a6 + 8 * v26 + 16) = 0;
            *((_QWORD *)a6 + v26 + 4) = 0;
            *((_WORD *)a6 + 20 * *a7) = 2;
            *((_WORD *)a6 + 20 * *a7 + 1) = 1;
            *((_DWORD *)a6 + 10 * (*a7)++ + 1) = v22;
          }
        }
        if ( v49 )
        {
          BcdElementsList = GetBcdElementsList(v47, a3, (struct _BCD_ELEMENT **)&lpMem, &v40);
          Policy = FromNtStatus(BcdElementsList);
          if ( Policy >= 0 )
          {
            for ( k = 0; k < v40; ++k )
            {
              v29 = *((_QWORD *)lpMem + 2 * k);
              v30 = *(_DWORD *)(v29 + 4);
              v31 = *((_QWORD *)lpMem + 2 * k + 1);
              v48 = v31;
              v32 = *(_DWORD *)(v29 + 8);
              if ( (v30 & 0xF000000) == 0x1000000 )
                v48 = v31 + 4;
              v33 = v32 - 4;
              if ( (v30 & 0xF000000) != 0x1000000 )
                v33 = v32;
              if ( !HasDupEntry(a6, 0, i, v30) && !HasDupEntry(v34, v39, *a7, v30) )
              {
                if ( (unsigned __int16)v35 >= a5 )
                  goto LABEL_14;
                v37 = FveDatumValidationInfoDataEntry(v30, v36, v33, (char *)a6 + 40 * v35);
                Policy = FromNtStatus(v37);
                if ( Policy < 0 )
                  goto LABEL_54;
                ++*a7;
              }
            }
            Policy = 0;
          }
        }
      }
    }
  }
LABEL_54:
  if ( v49 )
    BcdCloseObject(v49);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v42 )
    operator delete(v42);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_1559182127783aab3882fe828952d989_Traceguids,
      (unsigned int)Policy);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x18009e740  mov     r11, rsp
0x18009e743  push    rbx
0x18009e744  push    rsi
0x18009e745  push    rdi
0x18009e746  push    r12
0x18009e748  push    r13
0x18009e74a  push    r14
0x18009e74c  push    r15
0x18009e74e  sub     rsp, 0C0h
0x18009e755  mov     rax, cs:__security_cookie
0x18009e75c  xor     rax, rsp
0x18009e75f  mov     [rsp+0F8h+var_48], rax
0x18009e767  mov     [rsp+0F8h+var_90], r9d
0x18009e76c  mov     rsi, r8
0x18009e76f  mov     r14, rdx
0x18009e772  mov     [rsp+0F8h+var_70], rdx
0x18009e77a  mov     rbx, rcx
0x18009e77d  mov     r12, [rsp+0F8h+arg_28]
0x18009e785  mov     rdi, [rsp+0F8h+arg_30]
0x18009e78d  mov     [rsp+0F8h+var_A8], 0
0x18009e795  mov     [rsp+0F8h+lpMem], 0
0x18009e79e  mov     qword ptr [r11-60h], 0
0x18009e7a6  mov     [rsp+0F8h+var_88], 0
0x18009e7af  mov     [rsp+0F8h+var_98], 0
0x18009e7b8  mov     qword ptr [r11-80h], 0
0x18009e7c0  xor     r13d, r13d
0x18009e7c3  mov     [r11-78h], r13
0x18009e7c7  xorps   xmm0, xmm0
0x18009e7ca  movdqa  xmmword ptr [r11-58h], xmm0
0x18009e7d0  lea     r15, WPP_GLOBAL_Control
0x18009e7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e7de  cmp     rcx, r15
0x18009e7e1  jz      short loc_18009E7FE
0x18009e7e3  test    byte ptr [rcx+1Ch], 20h
0x18009e7e7  jz      short loc_18009E7FE
0x18009e7e9  lea     edx, [r13+11h]
0x18009e7ed  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009e7f4  mov     rcx, [rcx+10h]
0x18009e7f8  call    WPP_SF_
0x18009e7fd  nop
0x18009e7fe  lea     rdx, [rsp+0F8h+var_88]; struct CFvePolicy **
0x18009e803  mov     rcx, rbx; this
0x18009e806  call    ?GetPolicy@CFveApiBase@@IEAAJPEAPEAVCFvePolicy@@@Z; CFveApiBase::GetPolicy(CFvePolicy * *)
0x18009e80b  mov     ebx, eax
0x18009e80d  mov     [rsp+0F8h+var_B8], eax
0x18009e811  test    eax, eax
0x18009e813  js      loc_18009EC14
0x18009e819  test    rsi, rsi
0x18009e81c  jz      short loc_18009E84D
0x18009e81e  lea     r8, [rsp+0F8h+var_60]
0x18009e826  mov     rdx, rsi
0x18009e829  mov     rcx, r14
0x18009e82c  call    cs:__imp_BcdOpenObject
0x18009e833  nop     dword ptr [rax+rax+00h]
0x18009e838  mov     ecx, eax; int
0x18009e83a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e83f  mov     ebx, eax
0x18009e841  mov     [rsp+0F8h+var_B8], eax
0x18009e845  test    eax, eax
0x18009e847  js      loc_18009EC14
0x18009e84d  mov     r15d, 1
0x18009e853  cmp     [rsp+0F8h+var_60], 0
0x18009e85c  jz      loc_18009EA15
0x18009e862  xor     r14d, r14d
0x18009e865  lea     r13d, [r15+1]
0x18009e869  mov     [rsp+0F8h+var_B4], r14w
0x18009e86f  movzx   edx, word ptr [rdi]
0x18009e872  cmp     r14w, dx
0x18009e876  jnb     short loc_18009E88D
0x18009e878  movzx   eax, r14w
0x18009e87c  lea     rcx, [rax+rax*4]
0x18009e880  cmp     [r12+rcx*8], r13w
0x18009e885  jnz     short loc_18009E88D
0x18009e887  add     r14w, r15w
0x18009e88b  jmp     short loc_18009E869
0x18009e88d  cmp     [rsp+0F8h+arg_38], 0
0x18009e895  jz      loc_18009EA0A
0x18009e89b  cmp     dx, [rsp+0F8h+arg_20]
0x18009e8a3  jb      short loc_18009E8AF
0x18009e8a5  mov     ebx, 8007000Dh
0x18009e8aa  jmp     loc_18009EC09
0x18009e8af  mov     rax, [rsi]
0x18009e8b2  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x18009e8b9  jnz     short loc_18009E8C6
0x18009e8bb  mov     rax, [rsi+8]
0x18009e8bf  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x18009e8c6  test    rax, rax
0x18009e8c9  jz      loc_18009E996
0x18009e8cf  mov     rax, [rsi]
0x18009e8d2  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data1
0x18009e8d9  jnz     short loc_18009E8E6
0x18009e8db  mov     rax, [rsi+8]
0x18009e8df  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data4
0x18009e8e6  test    rax, rax
0x18009e8e9  jz      loc_18009E996
0x18009e8ef  movups  xmm0, xmmword ptr [rsi]
0x18009e8f2  movdqu  [rsp+0F8h+var_58], xmm0
0x18009e8fb  movzx   eax, word ptr [rdi]
0x18009e8fe  lea     rcx, [rax+rax*4]
0x18009e902  lea     r9, [r12+rcx*8]
0x18009e906  mov     r8d, 10h
0x18009e90c  lea     rdx, [rsp+0F8h+var_58]
0x18009e914  xor     ecx, ecx
0x18009e916  call    FveDatumValidationInfoDataEntry
0x18009e91b  mov     ecx, eax; int
0x18009e91d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e922  mov     ebx, eax
0x18009e924  mov     [rsp+0F8h+var_B8], eax
0x18009e928  test    eax, eax
0x18009e92a  js      loc_18009EC0D
0x18009e930  movzx   eax, word ptr [rdi]
0x18009e933  lea     rcx, [rax+rax*4]
0x18009e937  mov     eax, 4
0x18009e93c  mov     [r12+rcx*8], ax
0x18009e941  movzx   edx, [rsp+0F8h+arg_40]
0x18009e949  add     dx, dx
0x18009e94c  movzx   eax, word ptr [rdi]
0x18009e94f  lea     rcx, [rax+rax*4]; this
0x18009e953  mov     [r12+rcx*8+2], dx
0x18009e959  add     [rdi], r15w
0x18009e95d  mov     [rsp+0F8h+var_D8], rdi; unsigned __int16 *
0x18009e962  mov     r9, r12; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009e965  movzx   r8d, [rsp+0F8h+arg_20]; unsigned __int16
0x18009e96e  mov     rdx, [rsp+0F8h+var_60]; void *
0x18009e976  call    ?AddAppHashEntry@CFveApiBase@@AEAAJPEAXGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z; CFveApiBase::AddAppHashEntry(void *,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)
0x18009e97b  mov     ebx, eax
0x18009e97d  mov     [rsp+0F8h+var_B8], eax
0x18009e981  test    eax, eax
0x18009e983  jns     loc_18009EA0A
0x18009e989  mov     eax, 0FFFFh
0x18009e98e  add     [rdi], ax
0x18009e991  jmp     loc_18009EC0D
0x18009e996  lea     r9, [rsp+0F8h+var_58]
0x18009e99e  xor     r8d, r8d
0x18009e9a1  xor     edx, edx
0x18009e9a3  mov     rcx, [rsp+0F8h+var_60]
0x18009e9ab  call    cs:__imp_BcdQueryObject
0x18009e9b2  nop     dword ptr [rax+rax+00h]
0x18009e9b7  mov     ecx, eax; int
0x18009e9b9  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009e9be  mov     ebx, eax
0x18009e9c0  mov     [rsp+0F8h+var_B8], eax
0x18009e9c4  test    eax, eax
0x18009e9c6  jns     loc_18009E8FB
0x18009e9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e9d3  lea     r15, WPP_GLOBAL_Control
0x18009e9da  cmp     rcx, r15
0x18009e9dd  jz      loc_18009EC14
0x18009e9e3  test    [rcx+1Ch], r13b
0x18009e9e7  jz      loc_18009EC14
0x18009e9ed  mov     edx, 12h
0x18009e9f2  mov     r9d, eax
0x18009e9f5  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009e9fc  mov     rcx, [rcx+10h]
0x18009ea00  call    WPP_SF_d
0x18009ea05  jmp     loc_18009EC14
0x18009ea0a  movzx   r13d, word ptr [rdi]
0x18009ea0e  mov     [rsp+0F8h+var_B0], r13d
0x18009ea13  jmp     short loc_18009EA27
0x18009ea15  xor     eax, eax
0x18009ea17  mov     [rdi], ax
0x18009ea1a  movzx   r14d, ax
0x18009ea1e  mov     [rsp+0F8h+var_B4], ax
0x18009ea23  mov     [rsp+0F8h+var_B0], eax
0x18009ea27  mov     rax, [rsp+0F8h+var_88]
0x18009ea2c  mov     rcx, [rax+8]
0x18009ea30  add     rcx, 38h ; '8'
0x18009ea34  lea     rax, [rsp+0F8h+var_80]
0x18009ea39  mov     [rsp+0F8h+var_D0], rax
0x18009ea3e  lea     rax, [rsp+0F8h+var_98]
0x18009ea43  mov     [rsp+0F8h+var_D8], rax
0x18009ea48  mov     edx, [rsp+0F8h+var_90]
0x18009ea4c  call    ?GetIgnoredBcdSettings@CFveBcdSettings@@QEBAJW4eFveBootApplicationPolicy@@PEBU_ELEMENT_ENTRY@@_KPEAPEAKPEA_KPEAH@Z; CFveBcdSettings::GetIgnoredBcdSettings(eFveBootApplicationPolicy,_ELEMENT_ENTRY const *,unsigned __int64,ulong * *,unsigned __int64 *,int *)
0x18009ea51  mov     ebx, eax
0x18009ea53  mov     [rsp+0F8h+var_B8], eax
0x18009ea57  test    eax, eax
0x18009ea59  js      loc_18009EC0D
0x18009ea5f  xor     r11d, r11d
0x18009ea62  mov     [rsp+0F8h+var_AC], r11d
0x18009ea67  mov     ecx, r11d
0x18009ea6a  cmp     rcx, [rsp+0F8h+var_80]
0x18009ea6f  jnb     loc_18009EB06
0x18009ea75  mov     rax, [rsp+0F8h+var_98]
0x18009ea7a  mov     r13d, [rax+r11*4]
0x18009ea7e  xor     edx, edx; unsigned __int16
0x18009ea80  mov     r9d, r13d; unsigned int
0x18009ea83  movzx   r8d, r14w; unsigned __int16
0x18009ea87  mov     rcx, r12; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009ea8a  call    ?HasDupEntry@@YA_NPEAU_FVE_DATUM_VALIDATION_ENTRY@@GGK@Z; HasDupEntry(_FVE_DATUM_VALIDATION_ENTRY *,ushort,ushort,ulong)
0x18009ea8f  test    al, al
0x18009ea91  jnz     short loc_18009EAFE
0x18009ea93  movzx   r8d, word ptr [rdi]; unsigned __int16
0x18009ea97  mov     r9d, r13d; unsigned int
0x18009ea9a  movzx   edx, word ptr [rsp+0F8h+var_B0]; unsigned __int16
0x18009ea9f  call    ?HasDupEntry@@YA_NPEAU_FVE_DATUM_VALIDATION_ENTRY@@GGK@Z; HasDupEntry(_FVE_DATUM_VALIDATION_ENTRY *,ushort,ushort,ulong)
0x18009eaa4  test    al, al
0x18009eaa6  jnz     short loc_18009EAFE
0x18009eaa8  cmp     r8w, [rsp+0F8h+arg_20]
0x18009eab1  jnb     loc_18009E8A5
0x18009eab7  lea     rcx, [r8+r8*4]
0x18009eabb  xorps   xmm0, xmm0
0x18009eabe  xor     eax, eax
0x18009eac0  movups  xmmword ptr [r12+rcx*8], xmm0
0x18009eac5  movups  xmmword ptr [r12+rcx*8+10h], xmm0
0x18009eacb  mov     [r12+rcx*8+20h], rax
0x18009ead0  movzx   eax, word ptr [rdi]
0x18009ead3  lea     rcx, [rax+rax*4]
0x18009ead7  mov     eax, 2
0x18009eadc  mov     [r12+rcx*8], ax
0x18009eae1  movzx   eax, word ptr [rdi]
0x18009eae4  lea     rcx, [rax+rax*4]
0x18009eae8  mov     [r12+rcx*8+2], r15w
0x18009eaee  movzx   eax, word ptr [rdi]
0x18009eaf1  lea     rcx, [rax+rax*4]
0x18009eaf5  mov     [r12+rcx*8+4], r13d
0x18009eafa  add     [rdi], r15w
0x18009eafe  add     r11d, r15d
0x18009eb01  jmp     loc_18009EA62
0x18009eb06  cmp     [rsp+0F8h+var_60], 0
0x18009eb0f  jz      loc_18009EC0D
0x18009eb15  lea     r9, [rsp+0F8h+var_A8]; unsigned int *
0x18009eb1a  lea     r8, [rsp+0F8h+lpMem]; struct _BCD_ELEMENT **
0x18009eb1f  mov     rdx, rsi; struct _GUID *
0x18009eb22  mov     rcx, [rsp+0F8h+var_70]; void *
0x18009eb2a  call    ?GetBcdElementsList@@YAJPEAXPEBU_GUID@@PEAPEAU_BCD_ELEMENT@@PEAK@Z; GetBcdElementsList(void *,_GUID const *,_BCD_ELEMENT * *,ulong *)
0x18009eb2f  mov     ecx, eax; int
0x18009eb31  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009eb36  mov     ebx, eax
0x18009eb38  mov     [rsp+0F8h+var_B8], eax
0x18009eb3c  test    eax, eax
0x18009eb3e  js      loc_18009EC0D
0x18009eb44  xor     esi, esi
0x18009eb46  mov     [rsp+0F8h+var_AC], esi
0x18009eb4a  cmp     esi, [rsp+0F8h+var_A8]
0x18009eb4e  jnb     loc_18009EC07
0x18009eb54  mov     edx, esi
0x18009eb56  add     rdx, rdx
0x18009eb59  mov     rax, [rsp+0F8h+lpMem]
0x18009eb5e  mov     rcx, [rax+rdx*8]
0x18009eb62  mov     ebx, [rcx+4]
0x18009eb65  mov     r11, [rax+rdx*8+8]
0x18009eb6a  mov     [rsp+0F8h+var_68], r11
0x18009eb72  mov     edx, [rcx+8]
0x18009eb75  mov     eax, ebx
0x18009eb77  and     eax, 0F000000h
0x18009eb7c  cmp     eax, 1000000h
0x18009eb81  jnz     short loc_18009EB8F
0x18009eb83  add     r11, 4
0x18009eb87  mov     [rsp+0F8h+var_68], r11
0x18009eb8f  lea     r13d, [rdx-4]
0x18009eb93  cmp     eax, 1000000h
0x18009eb98  cmovnz  r13d, edx
0x18009eb9c  xor     edx, edx; unsigned __int16
0x18009eb9e  mov     r9d, ebx; unsigned int
0x18009eba1  movzx   r8d, r14w; unsigned __int16
0x18009eba5  mov     rcx, r12; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009eba8  call    ?HasDupEntry@@YA_NPEAU_FVE_DATUM_VALIDATION_ENTRY@@GGK@Z; HasDupEntry(_FVE_DATUM_VALIDATION_ENTRY *,ushort,ushort,ulong)
0x18009ebad  test    al, al
0x18009ebaf  jnz     short loc_18009EBFF
0x18009ebb1  movzx   r8d, word ptr [rdi]; unsigned __int16
0x18009ebb5  mov     r9d, ebx; unsigned int
0x18009ebb8  movzx   edx, word ptr [rsp+0F8h+var_B0]; unsigned __int16
0x18009ebbd  call    ?HasDupEntry@@YA_NPEAU_FVE_DATUM_VALIDATION_ENTRY@@GGK@Z; HasDupEntry(_FVE_DATUM_VALIDATION_ENTRY *,ushort,ushort,ulong)
0x18009ebc2  test    al, al
0x18009ebc4  jnz     short loc_18009EBFF
0x18009ebc6  cmp     r8w, [rsp+0F8h+arg_20]
0x18009ebcf  jnb     loc_18009E8A5
0x18009ebd5  lea     r8, [r8+r8*4]
0x18009ebd9  lea     r9, [r12+r8*8]
0x18009ebdd  mov     r8d, r13d
0x18009ebe0  mov     rdx, r11
0x18009ebe3  mov     ecx, ebx
0x18009ebe5  call    FveDatumValidationInfoDataEntry
0x18009ebea  mov     ecx, eax; int
0x18009ebec  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009ebf1  mov     ebx, eax
0x18009ebf3  mov     [rsp+0F8h+var_B8], eax
0x18009ebf7  test    eax, eax
0x18009ebf9  js      short loc_18009EC0D
0x18009ebfb  add     [rdi], r15w
0x18009ebff  add     esi, r15d
0x18009ec02  jmp     loc_18009EB46
0x18009ec07  xor     ebx, ebx
0x18009ec09  mov     [rsp+0F8h+var_B8], ebx
0x18009ec0d  lea     r15, WPP_GLOBAL_Control
0x18009ec14  mov     rcx, [rsp+0F8h+var_60]
0x18009ec1c  test    rcx, rcx
0x18009ec1f  jz      short loc_18009EC2D
0x18009ec21  call    cs:__imp_BcdCloseObject
0x18009ec28  nop     dword ptr [rax+rax+00h]
0x18009ec2d  mov     rcx, [rsp+0F8h+lpMem]; lpMem
0x18009ec32  test    rcx, rcx
0x18009ec35  jz      short loc_18009EC3C
0x18009ec37  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18009ec3c  mov     rcx, [rsp+0F8h+var_98]
0x18009ec41  test    rcx, rcx
0x18009ec44  jz      short loc_18009EC52
0x18009ec46  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18009ec4d  nop     dword ptr [rax+rax+00h]
0x18009ec52  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
