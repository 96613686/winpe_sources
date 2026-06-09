# Smb2InvalidateFileInfoCacheEntry

- ea: `0x140014650`
- end: `0x1400149ee`
- name: `Smb2InvalidateFileInfoCacheEntry`
- size: `926`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x140013210`
- `0x140013dc0`
- `0x140013fa0`
- `0x1400144c0`
- `0x140014590`
- `0x140024b10`
- `0x140027880`
- `0x14002f210`
- `0x14002f280`
- `0x140034e78`
- `0x1400513a0`
- `0x140055bd0`

## callees

- `0x14000ad90`
- `0x140014650`
- `0x140032e7c`
- `0x140037120`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400149ae`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400149ae`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140014716`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140014776`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400148e1`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14001493b`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140014716`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140014776`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400148e1`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14001493b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001480f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001480f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400147bc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400147bc`
- `rdbss!RxNameCacheExpireEntry` at `0x140014854`
- `rdbss!RxNameCacheExpireEntry` at `0x14003b42e`
- `rdbss!RxNameCacheExpireEntry` at `0x140014854`
- `rdbss!RxNameCacheExpireEntry` at `0x14003b42e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400147d6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014975`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400147d6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014975`
- `rdbss!RxCrackPathName` at `0x1400146bc`
- `rdbss!RxCrackPathName` at `0x1400146bc`

## pseudocode

```c
unsigned __int64 __fastcall Smb2InvalidateFileInfoCacheEntry(__int64 a1, struct _NAME_CACHE_CONTROL_ *a2)
{
  __int64 v2; // rbx
  __int64 v5; // rdi
  unsigned __int64 result; // rax
  _WORD *v7; // r15
  unsigned __int64 v8; // rcx
  ULONGLONG v9; // rcx
  struct _NAME_CACHE *Entry; // rax
  int v11; // r8d
  ULONGLONG v12; // rcx
  unsigned __int64 v13; // rcx
  ULONGLONG v14; // rcx
  int Timer_high; // ecx
  struct _NAME_CACHE *v16; // rdi
  int v17; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING String; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+70h] [rbp-90h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v5 = *(_QWORD *)(v2 + 136);
  Source = 0;
  Destination = 0;
  result = *(unsigned int *)(v5 + 8);
  if ( (result & 2) != 0 )
  {
    v7 = (_WORD *)(v2 + 360);
    RxCrackPathName(v2 + 360, 0, 0, &Source);
    *(_DWORD *)&Destination.Length = 0x1000000;
    Destination.Buffer = (PWSTR)&v21;
    String = Destination;
    if ( !Source.Length || (result = Source.Length + 68LL, result <= 0x100) )
    {
      RtlInt64ToUnicodeString(*(_QWORD *)(v5 + 32), 0x10u, &String);
      String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
      v8 = (unsigned __int16)(String.Length + 2);
      String.MaximumLength -= v8;
      Destination.Length = String.Length + 2;
      String.Buffer += v8 >> 1;
      v9 = *(_QWORD *)(v5 + 24);
      String.Length = 0;
      RtlInt64ToUnicodeString(v9, 0x10u, &String);
      String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
      Destination.Length += String.Length + 2;
      String.Length += 2;
      if ( Source.Length )
        RtlAppendUnicodeStringToString(&Destination, &Source);
      ExAcquirePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, 0, 0);
      if ( Entry )
      {
        RxNameCacheExpireEntry(a2, Entry);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qZZ(WPP_GLOBAL_Control->AttachedDevice, 13, v11, a1, (__int64)&Destination, v2 + 360);
        }
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
        {
          LOWORD(v17) = *v7 >> 1;
          McTemplateK0pphzr2q_EtwWriteTransfer(
            (unsigned __int16)v17,
            (unsigned int)SmbInvalidateInfoCache,
            a1 + 412,
            a1,
            v2,
            v17,
            *(_QWORD *)(v2 + 368));
        }
      }
      if ( Source.Length )
      {
        Destination.Length = 0;
        v12 = *(_QWORD *)(v5 + 32);
        String = Destination;
        RtlInt64ToUnicodeString(v12, 0x10u, &String);
        String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
        v13 = (unsigned __int16)(String.Length + 2);
        String.MaximumLength -= v13;
        Destination.Length = String.Length + 2;
        String.Buffer += v13 >> 1;
        v14 = *(_QWORD *)(v5 + 24);
        String.Length = 0;
        RtlInt64ToUnicodeString(v14, 0x10u, &String);
        String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
        Destination.Length += String.Length + 2;
        v16 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, 0, 0);
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (Timer_high & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qZZ(
                WPP_GLOBAL_Control->AttachedDevice,
                14,
                (_DWORD)WPP_GLOBAL_Control,
                a1,
                (__int64)&Destination,
                *(_QWORD *)(a1 + 56) + 360LL);
          }
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
          {
            LOWORD(v17) = *v7 >> 1;
            McTemplateK0pphzr2q_EtwWriteTransfer(
              Timer_high,
              (unsigned int)SmbInvalidateInfoCache,
              a1 + 412,
              a1,
              v2,
              v17,
              *(_QWORD *)(v2 + 368));
          }
          RxNameCacheExpireEntry(a2, v16);
        }
      }
      *(_BYTE *)(*(_QWORD *)(v2 + 136) + 81LL) = 0;
      return ExReleasePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014650  push    rbp
0x140014652  push    rbx
0x140014653  push    rsi
0x140014654  push    rdi
0x140014655  push    r14
0x140014657  lea     rbp, [rsp-90h]
0x14001465f  sub     rsp, 190h
0x140014666  mov     rax, cs:__security_cookie
0x14001466d  xor     rax, rsp
0x140014670  mov     [rbp+0B0h+var_40], rax
0x140014674  mov     rbx, [rcx+38h]
0x140014678  xorps   xmm0, xmm0
0x14001467b  xorps   xmm1, xmm1
0x14001467e  mov     r14, rdx
0x140014681  mov     rsi, rcx
0x140014684  mov     rdi, [rbx+88h]
0x14001468b  movups  xmmword ptr [rsp+1B0h+Source.Length], xmm0
0x140014690  movups  xmmword ptr [rsp+1B0h+Destination.Length], xmm1
0x140014695  mov     eax, [rdi+8]
0x140014698  test    al, 2
0x14001469a  jz      loc_140014833
0x1400146a0  mov     [rsp+1B0h+var_30], r15
0x1400146a8  lea     r9, [rsp+1B0h+Source]
0x1400146ad  lea     r15, [rbx+168h]
0x1400146b4  xor     r8d, r8d
0x1400146b7  mov     rcx, r15
0x1400146ba  xor     edx, edx
0x1400146bc  call    cs:__imp_RxCrackPathName
0x1400146c3  nop     dword ptr [rax+rax+00h]
0x1400146c8  lea     rax, [rsp+1B0h+var_140]
0x1400146cd  mov     dword ptr [rsp+1B0h+Destination.Length], 1000000h
0x1400146d5  mov     [rsp+1B0h+Destination.Buffer], rax
0x1400146da  mov     ecx, 100h
0x1400146df  movzx   eax, [rsp+1B0h+Source.Length]
0x1400146e4  movaps  xmm0, xmmword ptr [rsp+1B0h+Destination.Length]
0x1400146e9  movdqa  xmmword ptr [rsp+1B0h+String.Length], xmm0
0x1400146ef  test    ax, ax
0x1400146f2  jnz     loc_140014992
0x1400146f8  mov     rcx, [rdi+20h]; Value
0x1400146fc  lea     r8, [rsp+1B0h+String]; String
0x140014701  mov     [rsp+1B0h+arg_10], r12
0x140014709  mov     edx, 10h; Base
0x14001470e  mov     [rsp+1B0h+var_28], r13
0x140014716  call    cs:__imp_RtlInt64ToUnicodeString
0x14001471d  nop     dword ptr [rax+rax+00h]
0x140014722  mov     rax, [rsp+1B0h+String.Buffer]
0x140014727  lea     r8, [rsp+1B0h+String]; String
0x14001472c  movzx   ecx, [rsp+1B0h+String.Length]
0x140014731  mov     r12d, 3Ah ; ':'
0x140014737  shr     rcx, 1
0x14001473a  mov     edx, 10h; Base
0x14001473f  mov     [rax+rcx*2], r12w
0x140014744  movzx   eax, [rsp+1B0h+String.Length]
0x140014749  add     ax, 2
0x14001474d  movzx   ecx, ax
0x140014750  sub     [rsp+1B0h+String.MaximumLength], cx
0x140014755  mov     rax, [rsp+1B0h+String.Buffer]
0x14001475a  mov     [rsp+1B0h+Destination.Length], cx
0x14001475f  shr     rcx, 1
0x140014762  lea     rcx, [rax+rcx*2]
0x140014766  xor     eax, eax
0x140014768  mov     [rsp+1B0h+String.Buffer], rcx
0x14001476d  mov     rcx, [rdi+18h]; Value
0x140014771  mov     [rsp+1B0h+String.Length], ax
0x140014776  call    cs:__imp_RtlInt64ToUnicodeString
0x14001477d  nop     dword ptr [rax+rax+00h]
0x140014782  movzx   ecx, [rsp+1B0h+String.Length]
0x140014787  mov     rax, [rsp+1B0h+String.Buffer]
0x14001478c  shr     rcx, 1
0x14001478f  mov     [rax+rcx*2], r12w
0x140014794  movzx   eax, [rsp+1B0h+String.Length]
0x140014799  add     ax, 2
0x14001479d  add     [rsp+1B0h+Destination.Length], ax
0x1400147a2  cmp     [rsp+1B0h+Source.Length], 0
0x1400147a8  mov     [rsp+1B0h+String.Length], ax
0x1400147ad  jnz     loc_1400149A4
0x1400147b3  xor     edx, edx
0x1400147b5  lea     rcx, Smb2FileInfoCacheLock
0x1400147bc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400147c3  nop     dword ptr [rax+rax+00h]
0x1400147c8  xor     r9d, r9d
0x1400147cb  lea     rdx, [rsp+1B0h+Destination]
0x1400147d0  xor     r8d, r8d
0x1400147d3  mov     rcx, r14
0x1400147d6  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400147dd  nop     dword ptr [rax+rax+00h]
0x1400147e2  lea     r13, WPP_GLOBAL_Control
0x1400147e9  test    rax, rax
0x1400147ec  jnz     short loc_14001484E
0x1400147ee  cmp     [rsp+1B0h+Source.Length], 0
0x1400147f4  jnz     loc_1400148C1
0x1400147fa  mov     rdx, [rbx+88h]
0x140014801  lea     rcx, Smb2FileInfoCacheLock
0x140014808  xor     eax, eax
0x14001480a  xchg    al, [rdx+51h]
0x14001480d  xor     edx, edx
0x14001480f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014816  nop     dword ptr [rax+rax+00h]
0x14001481b  mov     r13, [rsp+1B0h+var_28]
0x140014823  mov     r12, [rsp+1B0h+arg_10]
0x14001482b  mov     r15, [rsp+1B0h+var_30]
0x140014833  mov     rcx, [rbp+0B0h+var_40]
0x140014837  xor     rcx, rsp; StackCookie
0x14001483a  call    __security_check_cookie
0x14001483f  add     rsp, 190h
0x140014846  pop     r14
0x140014848  pop     rdi
0x140014849  pop     rsi
0x14001484a  pop     rbx
0x14001484b  pop     rbp
0x14001484c  retn
0x14001484e  mov     rdx, rax; NameCache
0x140014851  mov     rcx, r14; NameCacheCtl
0x140014854  call    cs:__imp_RxNameCacheExpireEntry
0x14001485b  nop     dword ptr [rax+rax+00h]
0x140014860  mov     rcx, cs:WPP_GLOBAL_Control
0x140014867  cmp     rcx, r13
0x14001486a  jz      short loc_140014877
0x14001486c  mov     eax, [rcx+2Ch]
0x14001486f  test    al, al
0x140014871  js      loc_1400149BF
0x140014877  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14001487e  jz      loc_1400147EE
0x140014884  movzx   ecx, word ptr [r15]
0x140014888  lea     r8, [rsi+19Ch]
0x14001488f  mov     rax, [r15+8]
0x140014893  lea     rdx, SmbInvalidateInfoCache
0x14001489a  mov     [rsp+1B0h+var_178], 0
0x1400148a2  mov     r9, rsi
0x1400148a5  mov     [rsp+1B0h+var_180], rax
0x1400148aa  shr     cx, 1
0x1400148ad  mov     word ptr [rsp+1B0h+var_188], cx
0x1400148b2  mov     [rsp+1B0h+var_190], rbx
0x1400148b7  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x1400148bc  jmp     loc_1400147EE
0x1400148c1  xor     eax, eax
0x1400148c3  lea     r8, [rsp+1B0h+String]; String
0x1400148c8  mov     [rsp+1B0h+Destination.Length], ax
0x1400148cd  mov     edx, 10h; Base
0x1400148d2  movaps  xmm0, xmmword ptr [rsp+1B0h+Destination.Length]
0x1400148d7  mov     rcx, [rdi+20h]; Value
0x1400148db  movdqa  xmmword ptr [rsp+1B0h+String.Length], xmm0
0x1400148e1  call    cs:__imp_RtlInt64ToUnicodeString
0x1400148e8  nop     dword ptr [rax+rax+00h]
0x1400148ed  mov     rax, [rsp+1B0h+String.Buffer]
0x1400148f2  lea     r8, [rsp+1B0h+String]; String
0x1400148f7  movzx   ecx, [rsp+1B0h+String.Length]
0x1400148fc  mov     edx, 10h; Base
0x140014901  shr     rcx, 1
0x140014904  mov     [rax+rcx*2], r12w
0x140014909  movzx   eax, [rsp+1B0h+String.Length]
0x14001490e  add     ax, 2
0x140014912  movzx   ecx, ax
0x140014915  sub     [rsp+1B0h+String.MaximumLength], cx
0x14001491a  mov     rax, [rsp+1B0h+String.Buffer]
0x14001491f  mov     [rsp+1B0h+Destination.Length], cx
0x140014924  shr     rcx, 1
0x140014927  lea     rcx, [rax+rcx*2]
0x14001492b  xor     eax, eax
0x14001492d  mov     [rsp+1B0h+String.Buffer], rcx
0x140014932  mov     rcx, [rdi+18h]; Value
0x140014936  mov     [rsp+1B0h+String.Length], ax
0x14001493b  call    cs:__imp_RtlInt64ToUnicodeString
0x140014942  nop     dword ptr [rax+rax+00h]
0x140014947  mov     rax, [rsp+1B0h+String.Buffer]
0x14001494c  lea     rdx, [rsp+1B0h+Destination]
0x140014951  movzx   ecx, [rsp+1B0h+String.Length]
0x140014956  xor     r9d, r9d
0x140014959  shr     rcx, 1
0x14001495c  xor     r8d, r8d
0x14001495f  mov     [rax+rcx*2], r12w
0x140014964  mov     rcx, r14
0x140014967  movzx   eax, [rsp+1B0h+String.Length]
0x14001496c  add     ax, 2
0x140014970  add     [rsp+1B0h+Destination.Length], ax
0x140014975  call    cs:__imp_RxNameCacheFetchEntryEx
0x14001497c  nop     dword ptr [rax+rax+00h]
0x140014981  mov     rdi, rax
0x140014984  test    rax, rax
0x140014987  jz      loc_1400147FA
0x14001498d  jmp     loc_14003B3A0
0x140014992  add     rax, 44h ; 'D'
0x140014996  cmp     rax, rcx
0x140014999  jbe     loc_1400146F8
0x14001499f  jmp     loc_14001482B
0x1400149a4  lea     rdx, [rsp+1B0h+Source]; Source
0x1400149a9  lea     rcx, [rsp+1B0h+Destination]; Destination
0x1400149ae  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400149b5  nop     dword ptr [rax+rax+00h]
0x1400149ba  jmp     loc_1400147B3
0x1400149bf  cmp     byte ptr [rcx+29h], 2
0x1400149c3  jb      loc_140014877
0x1400149c9  mov     rcx, [rcx+18h]
0x1400149cd  lea     rax, [rsp+1B0h+Destination]
0x1400149d2  mov     edx, 0Dh
0x1400149d7  mov     [rsp+1B0h+var_188], r15
0x1400149dc  mov     r9, rsi
0x1400149df  mov     [rsp+1B0h+var_190], rax
0x1400149e4  call    WPP_SF_qZZ
0x1400149e9  jmp     loc_140014877
0x14003b3a0  mov     r8, cs:WPP_GLOBAL_Control
0x14003b3a7  cmp     r8, r13
0x14003b3aa  jz      short loc_14003B3E5
0x14003b3ac  mov     ecx, [r8+2Ch]
0x14003b3b0  test    cl, cl
0x14003b3b2  jns     short loc_14003B3E5
0x14003b3b4  cmp     byte ptr [r8+29h], 2
0x14003b3b9  jb      short loc_14003B3E5
0x14003b3bb  mov     rax, [rsi+38h]
0x14003b3bf  mov     edx, 0Eh
0x14003b3c4  mov     rcx, [r8+18h]
0x14003b3c8  add     rax, 168h
0x14003b3ce  mov     [rsp+1B0h+var_188], rax
0x14003b3d3  mov     r9, rsi
0x14003b3d6  lea     rax, [rsp+1B0h+Destination]
0x14003b3db  mov     [rsp+1B0h+var_190], rax
0x14003b3e0  call    WPP_SF_qZZ
0x14003b3e5  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14003b3ec  jz      short loc_14003B428
0x14003b3ee  movzx   r10d, word ptr [r15]
0x14003b3f2  lea     r8, [rsi+19Ch]
0x14003b3f9  mov     rax, [r15+8]
0x14003b3fd  lea     rdx, SmbInvalidateInfoCache
0x14003b404  mov     [rsp+1B0h+var_178], 0
0x14003b40c  mov     r9, rsi
0x14003b40f  mov     [rsp+1B0h+var_180], rax
0x14003b414  shr     r10w, 1
0x14003b418  mov     word ptr [rsp+1B0h+var_188], r10w
0x14003b41e  mov     [rsp+1B0h+var_190], rbx
0x14003b423  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x14003b428  mov     rdx, rdi; NameCache
0x14003b42b  mov     rcx, r14; NameCacheCtl
0x14003b42e  call    cs:__imp_RxNameCacheExpireEntry
0x14003b435  nop     dword ptr [rax+rax+00h]
0x14003b43a  nop
0x14003b43b  jmp     loc_1400147FA
```
