# MRxSmb2QueryFsInformationFromVolumeCache

- ea: `0x1400166f0`
- end: `0x140016acb`
- name: `MRxSmb2QueryFsInformationFromVolumeCache`
- size: `987`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140016510`

## callees

- `0x1400166f0`
- `0x140016ae0`
- `0x140037120`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140016776`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140016973`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140016776`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140016973`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140016859`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140016931`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140016859`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140016931`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001678b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016988`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001678b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016988`
- `rdbss!RxNameCacheCheckEntry` at `0x1400167c2`
- `rdbss!RxNameCacheCheckEntry` at `0x1400169bf`
- `rdbss!RxNameCacheCheckEntry` at `0x1400167c2`
- `rdbss!RxNameCacheCheckEntry` at `0x1400169bf`
- `rdbss!RxNameCacheExpireEntry` at `0x14001691c`
- `rdbss!RxNameCacheExpireEntry` at `0x140016a61`
- `rdbss!RxNameCacheExpireEntry` at `0x14001691c`
- `rdbss!RxNameCacheExpireEntry` at `0x140016a61`
- `rdbss!RxNameCacheActivateEntry` at `0x140016844`
- `rdbss!RxNameCacheActivateEntry` at `0x140016844`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400167a5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400169a2`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400167a5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400169a2`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryFsInformationFromVolumeCache(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rax
  ULONGLONG v5; // rcx
  unsigned int v6; // ebp
  void *v7; // r12
  struct _NAME_CACHE_CONTROL_ *v8; // r13
  int v9; // r14d
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v11; // r15
  struct _LIST_ENTRY *Flink; // rdx
  int v13; // r14d
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // r14d
  bool v17; // cf
  signed int v18; // esi
  unsigned int v20; // eax
  unsigned int v21; // esi
  ULONGLONG v22; // rcx
  void *v23; // r12
  struct _NAME_CACHE *v24; // rax
  struct _LIST_ENTRY *v25; // rdx
  int v26; // r14d
  unsigned int v27; // eax
  unsigned int v28; // edi
  bool v29; // cf
  unsigned int v30; // eax
  unsigned int v31; // esi
  struct _UNICODE_STRING String; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v33[40]; // [rsp+30h] [rbp-58h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(v2 + 136);
  if ( (*(_DWORD *)(v3 + 8) & 2) != 0 )
  {
    v4 = *(_QWORD *)(v2 + 120);
    v5 = *(_QWORD *)(v3 + 32);
    v6 = *(_DWORD *)(a1 + 472);
    v7 = *(void **)(a1 + 456);
    v8 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 744LL);
    v9 = *(_DWORD *)(a1 + 448);
    String.Buffer = (PWSTR)v33;
    *(_QWORD *)&String.Length = 2228224;
    RtlInt64ToUnicodeString(v5, 0x10u, &String);
    ExAcquirePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v8, &String, 0, 0);
    v11 = Entry;
    if ( Entry )
    {
      if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
      {
        if ( !v7 )
        {
          v18 = 0;
          goto LABEL_13;
        }
        Flink = v11->Link.Flink;
        v13 = v9 - 1;
        if ( v13 )
        {
          if ( v13 != 4 )
          {
            v18 = -1073741637;
            goto LABEL_13;
          }
          if ( v6 < 0xC )
          {
            v18 = -1073741789;
            goto LABEL_13;
          }
          v14 = v6;
          v15 = LODWORD(Flink->Blink) + 12;
          if ( v6 >= v15 )
            v14 = LODWORD(Flink->Blink) + 12;
          v16 = v14;
          memmove(v7, Flink, v14);
          v17 = v6 < v15;
        }
        else
        {
          if ( v6 < 0x12 )
          {
            v18 = -1073741789;
            goto LABEL_13;
          }
          v20 = v6;
          v21 = HIDWORD(Flink[5].Blink) + 18;
          if ( v6 >= v21 )
            v20 = HIDWORD(Flink[5].Blink) + 18;
          v16 = v20;
          memmove(v7, &Flink[5], v20);
          v17 = v6 < v21;
        }
        v18 = v17 ? 0x80000005 : 0;
        if ( (int)(v18 + 0x80000000) < 0 )
        {
LABEL_12:
          v6 = v16;
LABEL_13:
          RxNameCacheActivateEntry(v8, v11, 0, 0);
          goto LABEL_14;
        }
LABEL_22:
        if ( v18 != -2147483643 )
          goto LABEL_13;
        goto LABEL_12;
      }
      RxNameCacheExpireEntry(v8, v11);
    }
    ExReleasePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
    v18 = Smb2PopulateVolumeInformationCache(a1);
    if ( v18 < 0 )
    {
LABEL_24:
      if ( v18 != -2147483643 )
      {
        if ( v18 != -1073741789 )
          return (unsigned int)-1073741802;
        return (unsigned int)v18;
      }
LABEL_15:
      *(_DWORD *)(a1 + 472) -= v6;
      return (unsigned int)v18;
    }
    v22 = *(_QWORD *)(v3 + 32);
    v23 = *(void **)(a1 + 456);
    String.Buffer = (PWSTR)v33;
    *(_QWORD *)&String.Length = 2228224;
    RtlInt64ToUnicodeString(v22, 0x10u, &String);
    ExAcquirePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
    v24 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v8, &String, 0, 0);
    v11 = v24;
    if ( v24 )
    {
      if ( RxNameCacheCheckEntry(v24, 0) == RX_NC_SUCCESS )
      {
        if ( !v23 )
        {
          v18 = 0;
          goto LABEL_13;
        }
        v25 = v11->Link.Flink;
        v26 = v9 - 1;
        if ( v26 )
        {
          if ( v26 != 4 )
          {
            v18 = -1073741637;
            goto LABEL_13;
          }
          if ( v6 < 0xC )
          {
            v18 = -1073741789;
            goto LABEL_13;
          }
          v27 = v6;
          v28 = LODWORD(v25->Blink) + 12;
          if ( v6 >= v28 )
            v27 = LODWORD(v25->Blink) + 12;
          v16 = v27;
          memmove(v23, v25, v27);
          v29 = v6 < v28;
        }
        else
        {
          if ( v6 < 0x12 )
          {
            v18 = -1073741789;
            goto LABEL_13;
          }
          v30 = v6;
          v31 = HIDWORD(v25[5].Blink) + 18;
          if ( v6 >= v31 )
            v30 = HIDWORD(v25[5].Blink) + 18;
          v16 = v30;
          memmove(v23, &v25[5], v30);
          v29 = v6 < v31;
        }
        v18 = v29 ? 0x80000005 : 0;
        if ( (int)(v18 + 0x80000000) < 0 )
          goto LABEL_12;
        goto LABEL_22;
      }
      RxNameCacheExpireEntry(v8, v11);
      v18 = -1073741275;
    }
    else
    {
      v18 = -1073741275;
    }
LABEL_14:
    ExReleasePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
    if ( v18 >= 0 )
      goto LABEL_15;
    goto LABEL_24;
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400166f0  mov     r11, rsp
0x1400166f3  push    rbx
0x1400166f4  push    rsi
0x1400166f5  push    rdi
0x1400166f6  sub     rsp, 70h
0x1400166fa  mov     rax, cs:__security_cookie
0x140016701  xor     rax, rsp
0x140016704  mov     [rsp+88h+var_30], rax
0x140016709  mov     rbx, rcx
0x14001670c  mov     rcx, [rcx+38h]
0x140016710  mov     rdi, [rcx+88h]
0x140016717  mov     eax, [rdi+8]
0x14001671a  test    al, 2
0x14001671c  jz      loc_1400168AD
0x140016722  mov     rax, [rcx+78h]
0x140016726  lea     r8, [r11-68h]; String
0x14001672a  mov     rcx, [rdi+20h]; Value
0x14001672e  mov     edx, 10h; Base
0x140016733  mov     [r11+10h], rbp
0x140016737  mov     ebp, [rbx+1D8h]
0x14001673d  mov     [r11+18h], r12
0x140016741  mov     r12, [rbx+1C8h]
0x140016748  mov     [r11+20h], r13
0x14001674c  mov     r13, [rax+28h]
0x140016750  lea     rax, [r11-58h]
0x140016754  mov     [r11-20h], r14
0x140016758  add     r13, 2E8h
0x14001675f  mov     r14d, [rbx+1C0h]
0x140016766  mov     [r11-60h], rax
0x14001676a  mov     [r11-28h], r15
0x14001676e  mov     qword ptr [r11-68h], 220000h
0x140016776  call    cs:__imp_RtlInt64ToUnicodeString
0x14001677d  nop     dword ptr [rax+rax+00h]
0x140016782  xor     edx, edx
0x140016784  lea     rcx, Smb2VolumeInfoCacheLock
0x14001678b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140016792  nop     dword ptr [rax+rax+00h]
0x140016797  xor     r9d, r9d
0x14001679a  lea     rdx, [rsp+88h+String]
0x14001679f  xor     r8d, r8d
0x1400167a2  mov     rcx, r13
0x1400167a5  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400167ac  nop     dword ptr [rax+rax+00h]
0x1400167b1  xor     edx, edx; MRxContext
0x1400167b3  mov     r15, rax
0x1400167b6  test    rax, rax
0x1400167b9  jz      loc_14001692A
0x1400167bf  mov     rcx, rax; NameCache
0x1400167c2  call    cs:__imp_RxNameCacheCheckEntry
0x1400167c9  nop     dword ptr [rax+rax+00h]
0x1400167ce  test    eax, eax
0x1400167d0  jnz     loc_140016916
0x1400167d6  test    r12, r12
0x1400167d9  jz      loc_140016AB0
0x1400167df  mov     rdx, [r15+28h]; Src
0x1400167e3  sub     r14d, 1
0x1400167e7  jz      loc_1400168B4
0x1400167ed  cmp     r14d, 4
0x1400167f1  jnz     loc_140016AB7
0x1400167f7  cmp     ebp, 0Ch
0x1400167fa  jb      loc_140016A77
0x140016800  mov     edi, [rdx+8]
0x140016803  mov     eax, ebp
0x140016805  add     edi, 0Ch
0x140016808  mov     rcx, r12; void *
0x14001680b  cmp     ebp, edi
0x14001680d  cmovnb  eax, edi
0x140016810  mov     r8d, eax; Size
0x140016813  mov     r14d, eax
0x140016816  call    memmove
0x14001681b  cmp     ebp, edi
0x14001681d  sbb     esi, esi
0x14001681f  mov     ecx, 80000000h
0x140016824  and     esi, 80000005h
0x14001682a  lea     eax, [rsi+rcx]
0x14001682d  test    ecx, eax
0x14001682f  jz      loc_1400168E3
0x140016835  mov     ebp, r14d
0x140016838  xor     r9d, r9d; MRxContext
0x14001683b  xor     r8d, r8d; LifeTime
0x14001683e  mov     rdx, r15; NameCache
0x140016841  mov     rcx, r13; NameCacheCtl
0x140016844  call    cs:__imp_RxNameCacheActivateEntry
0x14001684b  nop     dword ptr [rax+rax+00h]
0x140016850  xor     edx, edx
0x140016852  lea     rcx, Smb2VolumeInfoCacheLock
0x140016859  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140016860  nop     dword ptr [rax+rax+00h]
0x140016865  test    esi, esi
0x140016867  js      loc_1400168F4
0x14001686d  sub     [rbx+1D8h], ebp
0x140016873  mov     r15, [rsp+88h+var_28]
0x140016878  mov     eax, esi
0x14001687a  mov     r14, [rsp+88h+var_20]
0x14001687f  mov     r13, [rsp+88h+arg_18]
0x140016887  mov     r12, [rsp+88h+arg_10]
0x14001688f  mov     rbp, [rsp+88h+arg_8]
0x140016897  mov     rcx, [rsp+88h+var_30]
0x14001689c  xor     rcx, rsp; StackCookie
0x14001689f  call    __security_check_cookie
0x1400168a4  add     rsp, 70h
0x1400168a8  pop     rdi
0x1400168a9  pop     rsi
0x1400168aa  pop     rbx
0x1400168ab  retn
0x1400168ad  mov     eax, 0C0000016h
0x1400168b2  jmp     short loc_140016897
0x1400168b4  cmp     ebp, 12h
0x1400168b7  jb      loc_140016AC1
0x1400168bd  mov     esi, [rdx+5Ch]
0x1400168c0  mov     eax, ebp
0x1400168c2  add     esi, 12h
0x1400168c5  mov     rcx, r12; void *
0x1400168c8  cmp     ebp, esi
0x1400168ca  cmovnb  eax, esi
0x1400168cd  add     rdx, 50h ; 'P'; Src
0x1400168d1  mov     r8d, eax; Size
0x1400168d4  mov     r14d, eax
0x1400168d7  call    memmove
0x1400168dc  cmp     ebp, esi
0x1400168de  jmp     loc_14001681D
0x1400168e3  cmp     esi, 80000005h
0x1400168e9  jz      loc_140016835
0x1400168ef  jmp     loc_140016838
0x1400168f4  cmp     esi, 80000005h
0x1400168fa  jz      loc_14001686D
0x140016900  cmp     esi, 0C0000023h
0x140016906  jz      loc_140016873
0x14001690c  mov     esi, 0C0000016h
0x140016911  jmp     loc_140016873
0x140016916  mov     rdx, r15; NameCache
0x140016919  mov     rcx, r13; NameCacheCtl
0x14001691c  call    cs:__imp_RxNameCacheExpireEntry
0x140016923  nop     dword ptr [rax+rax+00h]
0x140016928  xor     edx, edx
0x14001692a  lea     rcx, Smb2VolumeInfoCacheLock
0x140016931  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140016938  nop     dword ptr [rax+rax+00h]
0x14001693d  mov     rcx, rbx
0x140016940  call    Smb2PopulateVolumeInformationCache
0x140016945  mov     esi, eax
0x140016947  test    eax, eax
0x140016949  js      short loc_1400168F4
0x14001694b  mov     rcx, [rdi+20h]; Value
0x14001694f  lea     rax, [rsp+88h+var_58]
0x140016954  mov     r12, [rbx+1C8h]
0x14001695b  lea     r8, [rsp+88h+String]; String
0x140016960  mov     edx, 10h; Base
0x140016965  mov     [rsp+88h+String.Buffer], rax
0x14001696a  mov     qword ptr [rsp+88h+String.Length], 220000h
0x140016973  call    cs:__imp_RtlInt64ToUnicodeString
0x14001697a  nop     dword ptr [rax+rax+00h]
0x14001697f  xor     edx, edx
0x140016981  lea     rcx, Smb2VolumeInfoCacheLock
0x140016988  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001698f  nop     dword ptr [rax+rax+00h]
0x140016994  xor     r9d, r9d
0x140016997  lea     rdx, [rsp+88h+String]
0x14001699c  xor     r8d, r8d
0x14001699f  mov     rcx, r13
0x1400169a2  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400169a9  nop     dword ptr [rax+rax+00h]
0x1400169ae  mov     r15, rax
0x1400169b1  test    rax, rax
0x1400169b4  jz      loc_140016A8B
0x1400169ba  xor     edx, edx; MRxContext
0x1400169bc  mov     rcx, rax; NameCache
0x1400169bf  call    cs:__imp_RxNameCacheCheckEntry
0x1400169c6  nop     dword ptr [rax+rax+00h]
0x1400169cb  test    eax, eax
0x1400169cd  jnz     loc_140016A5B
0x1400169d3  test    r12, r12
0x1400169d6  jz      loc_140016A95
0x1400169dc  mov     rdx, [r15+28h]; Src
0x1400169e0  sub     r14d, 1
0x1400169e4  jz      short loc_140016A33
0x1400169e6  cmp     r14d, 4
0x1400169ea  jnz     loc_140016A9C
0x1400169f0  cmp     ebp, 0Ch
0x1400169f3  jb      loc_140016A81
0x1400169f9  mov     edi, [rdx+8]
0x1400169fc  mov     eax, ebp
0x1400169fe  add     edi, 0Ch
0x140016a01  mov     rcx, r12; void *
0x140016a04  cmp     ebp, edi
0x140016a06  cmovnb  eax, edi
0x140016a09  mov     r8d, eax; Size
0x140016a0c  mov     r14d, eax
0x140016a0f  call    memmove
0x140016a14  cmp     ebp, edi
0x140016a16  sbb     esi, esi
0x140016a18  mov     ecx, 80000000h
0x140016a1d  and     esi, 80000005h
0x140016a23  lea     eax, [rsi+rcx]
0x140016a26  test    ecx, eax
0x140016a28  jnz     loc_140016835
0x140016a2e  jmp     loc_1400168E3
0x140016a33  cmp     ebp, 12h
0x140016a36  jb      short loc_140016AA6
0x140016a38  mov     esi, [rdx+5Ch]
0x140016a3b  mov     eax, ebp
0x140016a3d  add     esi, 12h
0x140016a40  mov     rcx, r12; void *
0x140016a43  cmp     ebp, esi
0x140016a45  cmovnb  eax, esi
0x140016a48  add     rdx, 50h ; 'P'; Src
0x140016a4c  mov     r8d, eax; Size
0x140016a4f  mov     r14d, eax
0x140016a52  call    memmove
0x140016a57  cmp     ebp, esi
0x140016a59  jmp     short loc_140016A16
0x140016a5b  mov     rdx, r15; NameCache
0x140016a5e  mov     rcx, r13; NameCacheCtl
0x140016a61  call    cs:__imp_RxNameCacheExpireEntry
0x140016a68  nop     dword ptr [rax+rax+00h]
0x140016a6d  mov     esi, 0C0000225h
0x140016a72  jmp     loc_140016850
0x140016a77  mov     esi, 0C0000023h
0x140016a7c  jmp     loc_140016838
0x140016a81  mov     esi, 0C0000023h
0x140016a86  jmp     loc_140016838
0x140016a8b  mov     esi, 0C0000225h
0x140016a90  jmp     loc_140016850
0x140016a95  xor     esi, esi
0x140016a97  jmp     loc_140016838
0x140016a9c  mov     esi, 0C00000BBh
0x140016aa1  jmp     loc_140016838
0x140016aa6  mov     esi, 0C0000023h
0x140016aab  jmp     loc_140016838
0x140016ab0  xor     esi, esi
0x140016ab2  jmp     loc_140016838
0x140016ab7  mov     esi, 0C00000BBh
0x140016abc  jmp     loc_140016838
0x140016ac1  mov     esi, 0C0000023h
0x140016ac6  jmp     loc_140016838
```
