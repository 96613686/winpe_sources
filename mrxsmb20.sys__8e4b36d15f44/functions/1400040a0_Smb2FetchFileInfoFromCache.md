# Smb2FetchFileInfoFromCache

- ea: `0x1400040a0`
- end: `0x140004639`
- name: `Smb2FetchFileInfoFromCache`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, int, int, int, void *, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140003840`
- `0x140003a80`
- `0x140019260`
- `0x14001deb0`
- `0x1400346c0`

## callees

- `0x1400040a0`
- `0x14000ad90`
- `0x140032c9c`
- `0x140037120`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400045ae`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400045ae`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400041a1`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400041ff`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400041a1`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400041ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400042c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000432d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400042c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000432d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004252`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004252`
- `rdbss!RxNameCacheCheckEntry` at `0x14000428a`
- `rdbss!RxNameCacheCheckEntry` at `0x14000428a`
- `rdbss!RxNameCacheExpireEntry` at `0x140004318`
- `rdbss!RxNameCacheExpireEntry` at `0x140004318`
- `rdbss!RxNameCacheActivateEntry` at `0x1400042b3`
- `rdbss!RxNameCacheActivateEntry` at `0x1400042b3`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000426c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000426c`
- `rdbss!RxCrackPathName` at `0x140004141`
- `rdbss!RxCrackPathName` at `0x140004141`

## pseudocode

```c
__int64 __fastcall Smb2FetchFileInfoFromCache(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        int a3,
        int a4,
        int a5,
        void *a6,
        unsigned int *a7)
{
  struct _NAME_CACHE_CONTROL_ *v7; // r12
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r15
  unsigned __int64 v13; // rcx
  ULONGLONG v14; // rcx
  ULONG v15; // ebx
  unsigned int v16; // edi
  unsigned int v17; // r14d
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v19; // rsi
  struct _LIST_ENTRY *Flink; // rbx
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rsi
  int v24; // ebx
  _OWORD *v26; // r15
  int v27; // r12d
  int v28; // esi
  int Blink_high; // eax
  unsigned int Blink; // eax
  int v31; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING String; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  int v35; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+80h] [rbp-80h]
  UNICODE_STRING Source; // [rsp+88h] [rbp-78h] BYREF
  void *v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  struct _NAME_CACHE_CONTROL_ *v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a2;
  v39 = a6;
  v8 = *(_QWORD *)(a1 + 72);
  v41 = a2;
  v9 = *(_QWORD *)(a1 + 56);
  v33 = a1;
  v10 = *(_QWORD *)(v8 + 40);
  v35 = a4;
  v11 = *(_QWORD *)(v9 + 136);
  v37 = a3;
  v12 = *(_QWORD *)(v10 + 40);
  Source = 0;
  v42 = v9;
  Destination = 0;
  LODWORD(v8) = *(_DWORD *)(v11 + 8);
  v40 = v12;
  if ( (v8 & 2) == 0 )
    return 3221225494LL;
  v34 = v9 + 360;
  RxCrackPathName(v9 + 360, 0, 0, &Source);
  *(_DWORD *)&Destination.Length = 0x1000000;
  Destination.Buffer = (PWSTR)&v43;
  String = Destination;
  if ( Source.Length )
  {
    if ( (unsigned __int64)Source.Length + 68 > 0x100 )
      return 3221225494LL;
  }
  RtlInt64ToUnicodeString(*(_QWORD *)(v11 + 32), 0x10u, &String);
  String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
  v13 = (unsigned __int16)(String.Length + 2);
  String.MaximumLength -= v13;
  Destination.Length = String.Length + 2;
  String.Buffer += v13 >> 1;
  v14 = *(_QWORD *)(v11 + 24);
  String.Length = 0;
  RtlInt64ToUnicodeString(v14, 0x10u, &String);
  String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
  Destination.Length += String.Length + 2;
  String.Length += 2;
  if ( Source.Length )
    RtlAppendUnicodeStringToString(&Destination, &Source);
  v15 = *(_DWORD *)(v12 + 264);
  v16 = -1073741802;
  v17 = 0;
  ExAcquirePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v7, &Destination, 0, 0);
  *(_QWORD *)&String.Length = Entry;
  v19 = Entry;
  if ( !Entry )
    goto LABEL_9;
  if ( RxNameCacheCheckEntry(Entry, v15) )
  {
    RxNameCacheExpireEntry(v7, v19);
    ExReleasePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
    goto LABEL_14;
  }
  Flink = v19->Link.Flink;
  if ( !Flink )
    goto LABEL_8;
  v26 = v39;
  v27 = v35;
  v28 = v37;
  while ( v16 == -1073741802 )
  {
    v17 = *a7;
    if ( v28 != 1 || WORD1(Flink->Blink) != 1 )
      goto LABEL_40;
    if ( HIDWORD(Flink->Blink) != 34 )
    {
      if ( HIDWORD(Flink->Blink) == 18 )
      {
        switch ( v27 )
        {
          case 4:
            if ( v17 >= 0x28 )
            {
              v16 = 0;
              v17 = 40;
              *v26 = *(_OWORD *)((char *)&Flink[1].Blink + 4);
              v26[1] = *(_OWORD *)((char *)&Flink[2].Blink + 4);
              *((_QWORD *)v26 + 4) = *(struct _LIST_ENTRY **)((char *)&Flink[3].Blink + 4);
            }
            else
            {
              v16 = -1073741789;
            }
            break;
          case 5:
            if ( v17 >= 0x18 )
            {
              v16 = 0;
              v17 = 24;
              *v26 = *(struct _LIST_ENTRY *)((char *)&Flink[4] + 4);
              *((_QWORD *)v26 + 2) = *(struct _LIST_ENTRY **)((char *)&Flink[5].Flink + 4);
            }
            else
            {
              v16 = -1073741789;
            }
            break;
          case 6:
            if ( v17 >= 8 )
            {
              v16 = 0;
              *(_QWORD *)v26 = *(struct _LIST_ENTRY **)((char *)&Flink[5].Blink + 4);
              v17 = 8;
            }
            else
            {
              v16 = -1073741789;
            }
            break;
          case 7:
            if ( v17 >= 4 )
            {
              v16 = 0;
              *(_DWORD *)v26 = HIDWORD(Flink[6].Flink);
              v17 = 4;
            }
            else
            {
              v16 = -1073741789;
            }
            break;
        }
        goto LABEL_31;
      }
LABEL_40:
      if ( WORD1(Flink->Blink) == (_WORD)v28 && HIDWORD(Flink->Blink) == v27 && LODWORD(Flink[1].Flink) == a5 )
      {
        Blink = (unsigned int)Flink[1].Blink;
        if ( v17 < Blink )
        {
          v16 = -1073741789;
        }
        else
        {
          memmove(v26, (char *)&Flink[1].Blink + 4, Blink);
          v16 = 0;
        }
        v17 = (unsigned int)Flink[1].Blink;
      }
      goto LABEL_31;
    }
    switch ( v27 )
    {
      case 34:
        if ( v17 < 0x38 )
        {
          v16 = -1073741789;
        }
        else
        {
          v16 = 0;
          v17 = 56;
          *v26 = *(_OWORD *)((char *)&Flink[1].Blink + 4);
          v26[1] = *(_OWORD *)((char *)&Flink[2].Blink + 4);
          v26[2] = *(_OWORD *)((char *)&Flink[3].Blink + 4);
          *((_QWORD *)v26 + 6) = *(struct _LIST_ENTRY **)((char *)&Flink[4].Blink + 4);
        }
        break;
      case 4:
        if ( v17 < 0x28 )
        {
          v16 = -1073741789;
        }
        else
        {
          v16 = 0;
          *((_QWORD *)v26 + 3) = *(struct _LIST_ENTRY **)((char *)&Flink[3].Flink + 4);
          v17 = 40;
          *(_QWORD *)v26 = *(struct _LIST_ENTRY **)((char *)&Flink[1].Blink + 4);
          *((_DWORD *)v26 + 8) = HIDWORD(Flink[4].Blink);
          *((_QWORD *)v26 + 1) = *(struct _LIST_ENTRY **)((char *)&Flink[2].Flink + 4);
          *((_QWORD *)v26 + 2) = *(struct _LIST_ENTRY **)((char *)&Flink[2].Blink + 4);
        }
        break;
      case 5:
        if ( v17 < 0x18 )
        {
          v16 = -1073741789;
        }
        else
        {
          v17 = 24;
          *(_QWORD *)v26 = *(struct _LIST_ENTRY **)((char *)&Flink[3].Blink + 4);
          *((_BYTE *)v26 + 20) = 0;
          *((_BYTE *)v26 + 21) = (HIDWORD(Flink[4].Blink) & 0x10) != 0;
          v16 = 0;
          *((_QWORD *)v26 + 1) = *(struct _LIST_ENTRY **)((char *)&Flink[4].Flink + 4);
          *((_DWORD *)v26 + 4) = 1;
        }
        break;
      case 35:
        if ( v17 < 8 )
        {
          v16 = -1073741789;
        }
        else
        {
          Blink_high = HIDWORD(Flink[4].Blink);
          v17 = 8;
          if ( (Blink_high & 0x400) == 0 )
          {
            *(_DWORD *)v26 = Blink_high;
            v16 = 0;
            *((_DWORD *)v26 + 1) = 0;
          }
        }
        break;
    }
LABEL_31:
    Flink = Flink->Flink;
    if ( !Flink )
      break;
  }
  v19 = *(struct _NAME_CACHE **)&String.Length;
  v12 = v40;
  v7 = v41;
LABEL_8:
  RxNameCacheActivateEntry(v7, v19, 0, 0);
LABEL_9:
  ExReleasePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
  if ( v16 == -1073741802 )
  {
LABEL_14:
    v23 = v34;
    v24 = v33;
    goto LABEL_15;
  }
  *a7 = v17;
  v23 = v34;
  v24 = v33;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DqDZZ(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v35, v33, v16, (__int64)&Destination, v34);
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v12 + 528));
LABEL_15:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
  {
    LOWORD(v31) = *(_WORD *)v23 >> 1;
    McTemplateK0pphzr2q_EtwWriteTransfer(
      (unsigned __int16)v31,
      (unsigned int)SmbFetchInfoCache,
      v24 + 412,
      v24,
      v42,
      v31,
      *(_QWORD *)(v23 + 8));
  }
  return v16;
}

```

## disassembly

```asm
0x1400040a0  push    rbp
0x1400040a2  push    rbx
0x1400040a3  push    r12
0x1400040a5  push    r13
0x1400040a7  push    r15
0x1400040a9  lea     rbp, [rsp-0E0h]
0x1400040b1  sub     rsp, 1E0h
0x1400040b8  mov     rax, cs:__security_cookie
0x1400040bf  xor     rax, rsp
0x1400040c2  mov     [rbp+100h+var_40], rax
0x1400040c9  mov     rax, [rbp+100h+arg_28]
0x1400040d0  mov     r12, rdx
0x1400040d3  mov     r13, [rbp+100h+arg_30]
0x1400040da  xorps   xmm0, xmm0
0x1400040dd  mov     [rbp+100h+var_168], rax
0x1400040e1  xorps   xmm1, xmm1
0x1400040e4  mov     rax, [rcx+48h]
0x1400040e8  mov     [rbp+100h+var_158], rdx
0x1400040ec  mov     rdx, [rcx+38h]
0x1400040f0  mov     [rsp+200h+var_1B0], rcx
0x1400040f5  mov     rcx, [rax+28h]
0x1400040f9  mov     [rsp+200h+var_1A0], r9d
0x1400040fe  mov     rbx, [rdx+88h]
0x140004105  mov     [rbp+100h+var_180], r8d
0x140004109  mov     r15, [rcx+28h]
0x14000410d  movups  xmmword ptr [rbp+100h+Source.Length], xmm0
0x140004111  mov     [rbp+100h+var_150], rdx
0x140004115  movups  xmmword ptr [rsp+200h+Destination.Length], xmm1
0x14000411a  mov     eax, [rbx+8]
0x14000411d  mov     [rbp+100h+var_160], r15
0x140004121  test    al, 2
0x140004123  jz      loc_14000438A
0x140004129  lea     rax, [rdx+168h]
0x140004130  xor     r8d, r8d
0x140004133  mov     rcx, rax
0x140004136  mov     [rsp+200h+var_1A8], rax
0x14000413b  lea     r9, [rbp+100h+Source]
0x14000413f  xor     edx, edx
0x140004141  call    cs:__imp_RxCrackPathName
0x140004148  nop     dword ptr [rax+rax+00h]
0x14000414d  lea     rax, [rbp+100h+var_140]
0x140004151  mov     dword ptr [rsp+200h+Destination.Length], 1000000h
0x140004159  mov     [rsp+200h+Destination.Buffer], rax
0x14000415e  mov     ecx, 100h
0x140004163  movzx   eax, [rbp+100h+Source.Length]
0x140004167  movaps  xmm0, xmmword ptr [rsp+200h+Destination.Length]
0x14000416c  movdqa  xmmword ptr [rsp+200h+String.Length], xmm0
0x140004172  test    ax, ax
0x140004175  jnz     loc_140004543
0x14000417b  mov     rcx, [rbx+20h]; Value
0x14000417f  lea     r8, [rsp+200h+String]; String
0x140004184  mov     [rsp+200h+arg_10], rsi
0x14000418c  mov     edx, 10h; Base
0x140004191  mov     [rsp+200h+var_28], rdi
0x140004199  mov     [rsp+200h+var_30], r14
0x1400041a1  call    cs:__imp_RtlInt64ToUnicodeString
0x1400041a8  nop     dword ptr [rax+rax+00h]
0x1400041ad  mov     rax, [rsp+200h+String.Buffer]
0x1400041b2  lea     r8, [rsp+200h+String]; String
0x1400041b7  movzx   ecx, [rsp+200h+String.Length]
0x1400041bc  mov     edi, 3Ah ; ':'
0x1400041c1  shr     rcx, 1
0x1400041c4  mov     edx, 10h; Base
0x1400041c9  mov     [rax+rcx*2], di
0x1400041cd  movzx   eax, [rsp+200h+String.Length]
0x1400041d2  add     ax, 2
0x1400041d6  movzx   ecx, ax
0x1400041d9  sub     [rsp+200h+String.MaximumLength], cx
0x1400041de  mov     rax, [rsp+200h+String.Buffer]
0x1400041e3  mov     [rsp+200h+Destination.Length], cx
0x1400041e8  shr     rcx, 1
0x1400041eb  lea     rcx, [rax+rcx*2]
0x1400041ef  xor     eax, eax
0x1400041f1  mov     [rsp+200h+String.Buffer], rcx
0x1400041f6  mov     rcx, [rbx+18h]; Value
0x1400041fa  mov     [rsp+200h+String.Length], ax
0x1400041ff  call    cs:__imp_RtlInt64ToUnicodeString
0x140004206  nop     dword ptr [rax+rax+00h]
0x14000420b  movzx   ecx, [rsp+200h+String.Length]
0x140004210  mov     rax, [rsp+200h+String.Buffer]
0x140004215  shr     rcx, 1
0x140004218  mov     [rax+rcx*2], di
0x14000421c  movzx   eax, [rsp+200h+String.Length]
0x140004221  add     ax, 2
0x140004225  add     [rsp+200h+Destination.Length], ax
0x14000422a  cmp     [rbp+100h+Source.Length], 0
0x14000422f  mov     [rsp+200h+String.Length], ax
0x140004234  jnz     loc_1400045A5
0x14000423a  mov     ebx, [r15+108h]
0x140004241  lea     rcx, Smb2FileInfoCacheLock
0x140004248  xor     edx, edx
0x14000424a  mov     edi, 0C0000016h
0x14000424f  xor     r14d, r14d
0x140004252  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140004259  nop     dword ptr [rax+rax+00h]
0x14000425e  xor     r9d, r9d
0x140004261  lea     rdx, [rsp+200h+Destination]
0x140004266  xor     r8d, r8d
0x140004269  mov     rcx, r12
0x14000426c  call    cs:__imp_RxNameCacheFetchEntryEx
0x140004273  nop     dword ptr [rax+rax+00h]
0x140004278  mov     qword ptr [rsp+200h+String.Length], rax
0x14000427d  mov     rsi, rax
0x140004280  test    rax, rax
0x140004283  jz      short loc_1400042BF
0x140004285  mov     edx, ebx; MRxContext
0x140004287  mov     rcx, rax; NameCache
0x14000428a  call    cs:__imp_RxNameCacheCheckEntry
0x140004291  nop     dword ptr [rax+rax+00h]
0x140004296  test    eax, eax
0x140004298  jnz     short loc_140004312
0x14000429a  mov     rbx, [rsi+28h]
0x14000429e  test    rbx, rbx
0x1400042a1  jnz     loc_140004391
0x1400042a7  xor     r9d, r9d; MRxContext
0x1400042aa  xor     r8d, r8d; LifeTime
0x1400042ad  mov     rdx, rsi; NameCache
0x1400042b0  mov     rcx, r12; NameCacheCtl
0x1400042b3  call    cs:__imp_RxNameCacheActivateEntry
0x1400042ba  nop     dword ptr [rax+rax+00h]
0x1400042bf  xor     edx, edx
0x1400042c1  lea     rcx, Smb2FileInfoCacheLock
0x1400042c8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400042cf  nop     dword ptr [rax+rax+00h]
0x1400042d4  cmp     edi, 0C0000016h
0x1400042da  jz      short loc_140004339
0x1400042dc  mov     [r13+0], r14d
0x1400042e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042e7  lea     rax, WPP_GLOBAL_Control
0x1400042ee  mov     rsi, [rsp+200h+var_1A8]
0x1400042f3  mov     rbx, [rsp+200h+var_1B0]
0x1400042f8  cmp     rcx, rax
0x1400042fb  jz      short loc_140004308
0x1400042fd  mov     eax, [rcx+2Ch]
0x140004300  test    al, al
0x140004302  js      loc_140004604
0x140004308  lock inc qword ptr [r15+210h]
0x140004310  jmp     short loc_140004343
0x140004312  mov     rdx, rsi; NameCache
0x140004315  mov     rcx, r12; NameCacheCtl
0x140004318  call    cs:__imp_RxNameCacheExpireEntry
0x14000431f  nop     dword ptr [rax+rax+00h]
0x140004324  xor     edx, edx
0x140004326  lea     rcx, Smb2FileInfoCacheLock
0x14000432d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140004334  nop     dword ptr [rax+rax+00h]
0x140004339  mov     rsi, [rsp+200h+var_1A8]
0x14000433e  mov     rbx, [rsp+200h+var_1B0]
0x140004343  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14000434a  mov     r14, [rsp+200h+var_30]
0x140004352  jnz     loc_140004569
0x140004358  mov     rsi, [rsp+200h+arg_10]
0x140004360  mov     eax, edi
0x140004362  mov     rdi, [rsp+200h+var_28]
0x14000436a  mov     rcx, [rbp+100h+var_40]
0x140004371  xor     rcx, rsp; StackCookie
0x140004374  call    __security_check_cookie
0x140004379  add     rsp, 1E0h
0x140004380  pop     r15
0x140004382  pop     r13
0x140004384  pop     r12
0x140004386  pop     rbx
0x140004387  pop     rbp
0x140004388  retn
0x14000438a  mov     eax, 0C0000016h
0x14000438f  jmp     short loc_14000436A
0x140004391  mov     r15, [rbp+100h+var_168]
0x140004395  mov     r12d, [rsp+200h+var_1A0]
0x14000439a  mov     esi, [rbp+100h+var_180]
0x14000439d  cmp     edi, 0C0000016h
0x1400043a3  jnz     loc_140004460
0x1400043a9  mov     r14d, [r13+0]
0x1400043ad  cmp     esi, 1
0x1400043b0  jnz     loc_1400044E6
0x1400043b6  cmp     [rbx+0Ah], si
0x1400043ba  jnz     loc_1400044E6
0x1400043c0  cmp     dword ptr [rbx+0Ch], 22h ; '"'
0x1400043c4  jnz     loc_1400044DC
0x1400043ca  cmp     r12d, 22h ; '"'
0x1400043ce  jz      short loc_14000441D
0x1400043d0  mov     eax, r12d
0x1400043d3  sub     eax, 4
0x1400043d6  jz      loc_140004472
0x1400043dc  sub     eax, esi
0x1400043de  jnz     loc_1400044AC
0x1400043e4  cmp     r14d, 18h
0x1400043e8  jb      loc_140004539
0x1400043ee  mov     rax, [rbx+3Ch]
0x1400043f2  mov     r14d, 18h
0x1400043f8  mov     [r15], rax
0x1400043fb  mov     byte ptr [r15+14h], 0
0x140004400  mov     eax, [rbx+4Ch]
0x140004403  shr     eax, 4
0x140004406  and     al, sil
0x140004409  mov     [r15+15h], al
0x14000440d  xor     edi, edi
0x14000440f  mov     rax, [rbx+44h]
0x140004413  mov     [r15+8], rax
0x140004417  mov     [r15+10h], esi
0x14000441b  jmp     short loc_140004454
0x14000441d  cmp     r14d, 38h ; '8'
0x140004421  jb      loc_140004555
0x140004427  movups  xmm0, xmmword ptr [rbx+1Ch]
0x14000442b  xor     edi, edi
0x14000442d  mov     r14d, 38h ; '8'
0x140004433  movups  xmmword ptr [r15], xmm0
0x140004437  movups  xmm1, xmmword ptr [rbx+2Ch]
0x14000443b  movups  xmmword ptr [r15+10h], xmm1
0x140004440  movups  xmm0, xmmword ptr [rbx+3Ch]
0x140004444  movups  xmmword ptr [r15+20h], xmm0
0x140004449  movsd   xmm1, qword ptr [rbx+4Ch]
0x14000444e  movsd   qword ptr [r15+30h], xmm1
0x140004454  mov     rbx, [rbx]
0x140004457  test    rbx, rbx
0x14000445a  jnz     loc_14000439D
0x140004460  mov     rsi, qword ptr [rsp+200h+String.Length]
0x140004465  mov     r15, [rbp+100h+var_160]
0x140004469  mov     r12, [rbp+100h+var_158]
0x14000446d  jmp     loc_1400042A7
0x140004472  cmp     r14d, 28h ; '('
0x140004476  jb      loc_14000452F
0x14000447c  mov     rax, [rbx+34h]
0x140004480  xor     edi, edi
0x140004482  mov     [r15+18h], rax
0x140004486  mov     r14d, 28h ; '('
0x14000448c  mov     rax, [rbx+1Ch]
0x140004490  mov     [r15], rax
0x140004493  mov     eax, [rbx+4Ch]
0x140004496  mov     [r15+20h], eax
0x14000449a  mov     rax, [rbx+24h]
0x14000449e  mov     [r15+8], rax
0x1400044a2  mov     rax, [rbx+2Ch]
0x1400044a6  mov     [r15+10h], rax
0x1400044aa  jmp     short loc_140004454
0x1400044ac  cmp     eax, 1Eh
0x1400044af  jnz     short loc_140004454
0x1400044b1  cmp     r14d, 8
0x1400044b5  jb      loc_14000455F
0x1400044bb  mov     eax, [rbx+4Ch]
0x1400044be  mov     r14d, 8
0x1400044c4  bt      eax, 0Ah
0x1400044c8  jb      short loc_140004454
0x1400044ca  mov     [r15], eax
0x1400044cd  xor     edi, edi
0x1400044cf  mov     dword ptr [r15+4], 0
0x1400044d7  jmp     loc_140004454
0x1400044dc  cmp     dword ptr [rbx+0Ch], 12h
0x1400044e0  jz      loc_1400045BF
0x1400044e6  cmp     [rbx+0Ah], si
0x1400044ea  jnz     loc_140004454
0x1400044f0  cmp     [rbx+0Ch], r12d
0x1400044f4  jnz     loc_140004454
0x1400044fa  mov     eax, [rbp+100h+arg_20]
0x140004500  cmp     [rbx+10h], eax
0x140004503  jnz     loc_140004454
0x140004509  mov     eax, [rbx+18h]
0x14000450c  cmp     r14d, eax
0x14000450f  jb      loc_1400045FA
0x140004515  mov     r8d, eax; Size
0x140004518  lea     rdx, [rbx+1Ch]; Src
0x14000451c  mov     rcx, r15; void *
0x14000451f  call    memmove
0x140004524  xor     edi, edi
0x140004526  mov     r14d, [rbx+18h]
0x14000452a  jmp     loc_140004454
0x14000452f  mov     edi, 0C0000023h
0x140004534  jmp     loc_140004454
0x140004539  mov     edi, 0C0000023h
0x14000453e  jmp     loc_140004454
0x140004543  add     rax, 44h ; 'D'
0x140004547  cmp     rax, rcx
0x14000454a  jbe     loc_14000417B
0x140004550  jmp     loc_14000438A
0x140004555  mov     edi, 0C0000023h
0x14000455a  jmp     loc_140004454
0x14000455f  mov     edi, 0C0000023h
0x140004564  jmp     loc_140004454
0x140004569  mov     rax, [rsi+8]
0x14000456d  lea     r8, [rbx+19Ch]
0x140004574  movzx   ecx, word ptr [rsi]
0x140004577  lea     rdx, SmbFetchInfoCache
0x14000457e  mov     dword ptr [rsp+200h+var_1C8], edi
0x140004582  mov     r9, rbx
0x140004585  mov     [rsp+200h+var_1D0], rax
0x14000458a  mov     rax, [rbp+100h+var_150]
0x14000458e  shr     cx, 1
0x140004591  mov     word ptr [rsp+200h+var_1D8], cx
0x140004596  mov     [rsp+200h+var_1E0], rax
0x14000459b  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x1400045a0  jmp     loc_140004358
0x1400045a5  lea     rdx, [rbp+100h+Source]; Source
0x1400045a9  lea     rcx, [rsp+200h+Destination]; Destination
0x1400045ae  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400045b5  nop     dword ptr [rax+rax+00h]
0x1400045ba  jmp     loc_14000423A
0x1400045bf  mov     eax, r12d
0x1400045c2  sub     eax, 4
0x1400045c5  jz      loc_1400383A9
0x1400045cb  sub     eax, 1
0x1400045ce  jz      loc_140038379
  ... truncated ...
```
