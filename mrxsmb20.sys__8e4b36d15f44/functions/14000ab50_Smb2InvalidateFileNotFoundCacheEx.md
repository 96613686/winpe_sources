# Smb2InvalidateFileNotFoundCacheEx

- ea: `0x14000ab50`
- end: `0x14000ad84`
- name: `Smb2InvalidateFileNotFoundCacheEx`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140005820`
- `0x140013fa0`
- `0x1400236b0`
- `0x14002f280`
- `0x140034e78`

## callees

- `0x14000ab50`
- `0x14000ad90`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14000ac04`
- `ntoskrnl!RtlHashUnicodeString` at `0x14000ac04`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000acc2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000acc2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000abdb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000abdb`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14000acf9`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14000acf9`
- `rdbss!RxNameCacheExpireEntry` at `0x14000ad16`
- `rdbss!RxNameCacheExpireEntry` at `0x14000ad16`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000ac5c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000ad30`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000ac5c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14000ad30`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14000abc6`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14000abc6`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateFileNotFoundCacheEx(__int64 a1, struct _NAME_CACHE_CONTROL_ *a2, __int64 a3, char a4)
{
  __int64 v5; // rbx
  __int64 v8; // r8
  struct _NAME_CACHE *i; // rax
  __int64 v10; // rax
  _OWORD *v11; // rcx
  UNICODE_STRING String; // [rsp+40h] [rbp-59h] BYREF
  _OWORD v14[9]; // [rsp+50h] [rbp-49h] BYREF
  ULONG HashValue; // [rsp+118h] [rbp+7Fh] BYREF

  v5 = a3;
  String = 0;
  memset(v14, 0, 136);
  if ( !a3 )
    v5 = *(_QWORD *)(a1 + 56) + 360LL;
  MRxSmbIsStreamFile(v5, &String);
  ExAcquirePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
  if ( a4 )
  {
    LOBYTE(v8) = 1;
    RxNameCacheExpireEntriesWithPrefixEx(a2, &String, v8);
  }
  else
  {
    HashValue = 0;
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    memset(v14, 0, 0x88u);
    LODWORD(v14[0]) = 8973226;
    *((_QWORD *)&v14[6] + 1) = &v14[6];
    *(_QWORD *)&v14[6] = &v14[6];
    *((_QWORD *)&v14[4] + 1) = &v14[4];
    *(_QWORD *)&v14[4] = &v14[4];
    LODWORD(v14[7]) = HashValue;
    for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &String, 0, v14);
          i;
          i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &String, 0, v14) )
    {
      RxNameCacheExpireEntry(a2, i);
    }
    v10 = *(_QWORD *)&v14[6];
    v11 = &v14[6];
    if ( *(_OWORD **)&v14[6] != &v14[6] )
    {
      if ( *(_OWORD **)(*(_QWORD *)&v14[6] + 8LL) != &v14[6]
        || (v11 = (_OWORD *)*((_QWORD *)&v14[6] + 1), **((_OWORD ***)&v14[6] + 1) != &v14[6]) )
      {
        __fastfail(3u);
      }
      **((_QWORD **)&v14[6] + 1) = *(_QWORD *)&v14[6];
      *(_QWORD *)(v10 + 8) = v11;
      *((_QWORD *)&v14[6] + 1) = &v14[6];
      *(_QWORD *)&v14[6] = &v14[6];
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
      McTemplateK0pphzr2q_EtwWriteTransfer(
        (_DWORD)v11,
        (unsigned int)SmbInvalidateFNFCache,
        a1 + 412,
        a1,
        *(_QWORD *)(a1 + 56),
        *(_WORD *)v5 >> 1,
        *(_QWORD *)(v5 + 8));
  }
  return ExReleasePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
}

```

## disassembly

```asm
0x14000ab50  mov     [rsp-8+arg_8], rbx
0x14000ab55  mov     [rsp-8+arg_10], rsi
0x14000ab5a  push    rbp
0x14000ab5b  push    rdi
0x14000ab5c  push    r14
0x14000ab5e  lea     rbp, [rsp-47h]
0x14000ab63  sub     rsp, 0E0h
0x14000ab6a  xorps   xmm1, xmm1
0x14000ab6d  xor     eax, eax
0x14000ab6f  mov     [rbp+57h+var_20], rax
0x14000ab73  xorps   xmm0, xmm0
0x14000ab76  movzx   esi, r9b
0x14000ab7a  mov     rbx, r8
0x14000ab7d  mov     r14, rdx
0x14000ab80  mov     rdi, rcx
0x14000ab83  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x14000ab87  movups  [rbp+57h+var_A0], xmm1
0x14000ab8b  movups  [rbp+57h+var_90], xmm1
0x14000ab8f  movups  [rbp+57h+var_80], xmm1
0x14000ab93  movups  [rbp+57h+var_70], xmm1
0x14000ab97  movups  [rbp+57h+var_60], xmm1
0x14000ab9b  movups  [rbp+57h+var_50], xmm1
0x14000ab9f  movups  [rbp+57h+var_40], xmm1
0x14000aba3  movups  [rbp+57h+var_30], xmm1
0x14000aba7  test    r8, r8
0x14000abaa  jnz     short loc_14000ABB7
0x14000abac  mov     rbx, [rcx+38h]
0x14000abb0  add     rbx, 168h
0x14000abb7  lea     rdx, [rbp+57h+String]
0x14000abbb  mov     [rsp+0F0h+arg_0], r15
0x14000abc3  mov     rcx, rbx
0x14000abc6  call    cs:__imp_MRxSmbIsStreamFile
0x14000abcd  nop     dword ptr [rax+rax+00h]
0x14000abd2  xor     edx, edx
0x14000abd4  lea     rcx, Smb2FileNotFoundCacheLock
0x14000abdb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000abe2  nop     dword ptr [rax+rax+00h]
0x14000abe7  test    sil, sil
0x14000abea  jnz     loc_14000ACEF
0x14000abf0  xor     r15d, r15d
0x14000abf3  lea     r9, [rbp+57h+HashValue]; HashValue
0x14000abf7  xor     r8d, r8d; HashAlgorithm
0x14000abfa  mov     [rbp+57h+HashValue], r15d
0x14000abfe  mov     dl, 1; CaseInSensitive
0x14000ac00  lea     rcx, [rbp+57h+String]; String
0x14000ac04  call    cs:__imp_RtlHashUnicodeString
0x14000ac0b  nop     dword ptr [rax+rax+00h]
0x14000ac10  xor     edx, edx; Val
0x14000ac12  lea     rcx, [rbp+57h+var_A0]; void *
0x14000ac16  mov     r8d, 88h; Size
0x14000ac1c  call    memset
0x14000ac21  lea     rax, [rbp+57h+var_40]
0x14000ac25  mov     dword ptr [rbp+57h+var_A0], 88EBAAh
0x14000ac2c  mov     qword ptr [rbp+57h+var_40+8], rax
0x14000ac30  lea     r9, [rbp+57h+var_A0]
0x14000ac34  lea     rax, [rbp+57h+var_40]
0x14000ac38  xor     r8d, r8d
0x14000ac3b  mov     qword ptr [rbp+57h+var_40], rax
0x14000ac3f  lea     rdx, [rbp+57h+String]
0x14000ac43  lea     rax, [rbp+57h+var_60]
0x14000ac47  mov     rcx, r14
0x14000ac4a  mov     qword ptr [rbp+57h+var_60+8], rax
0x14000ac4e  lea     rax, [rbp+57h+var_60]
0x14000ac52  mov     qword ptr [rbp+57h+var_60], rax
0x14000ac56  mov     eax, [rbp+57h+HashValue]
0x14000ac59  mov     dword ptr [rbp+57h+var_30], eax
0x14000ac5c  call    cs:__imp_RxNameCacheFetchEntryEx
0x14000ac63  nop     dword ptr [rax+rax+00h]
0x14000ac68  test    rax, rax
0x14000ac6b  jnz     loc_14000AD10
0x14000ac71  mov     rax, qword ptr [rbp+57h+var_40]
0x14000ac75  lea     rcx, [rbp+57h+var_40]
0x14000ac79  cmp     rax, rcx
0x14000ac7c  jz      short loc_14000ACAC
0x14000ac7e  lea     rcx, [rbp+57h+var_40]
0x14000ac82  cmp     [rax+8], rcx
0x14000ac86  jnz     short loc_14000AD07
0x14000ac88  mov     rcx, qword ptr [rbp+57h+var_40+8]
0x14000ac8c  lea     rdx, [rbp+57h+var_40]
0x14000ac90  cmp     [rcx], rdx
0x14000ac93  jnz     short loc_14000AD07
0x14000ac95  mov     [rcx], rax
0x14000ac98  mov     [rax+8], rcx
0x14000ac9c  lea     rax, [rbp+57h+var_40]
0x14000aca0  mov     qword ptr [rbp+57h+var_40+8], rax
0x14000aca4  lea     rax, [rbp+57h+var_40]
0x14000aca8  mov     qword ptr [rbp+57h+var_40], rax
0x14000acac  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14000acb3  jnz     loc_14000AD47
0x14000acb9  xor     edx, edx
0x14000acbb  lea     rcx, Smb2FileNotFoundCacheLock
0x14000acc2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000acc9  nop     dword ptr [rax+rax+00h]
0x14000acce  mov     r15, [rsp+0F0h+arg_0]
0x14000acd6  lea     r11, [rsp+0F0h+var_10]
0x14000acde  mov     rbx, [r11+28h]
0x14000ace2  mov     rsi, [r11+30h]
0x14000ace6  mov     rsp, r11
0x14000ace9  pop     r14
0x14000aceb  pop     rdi
0x14000acec  pop     rbp
0x14000aced  retn
0x14000acef  mov     r8b, 1
0x14000acf2  lea     rdx, [rbp+57h+String]
0x14000acf6  mov     rcx, r14
0x14000acf9  call    cs:__imp_RxNameCacheExpireEntriesWithPrefixEx
0x14000ad00  nop     dword ptr [rax+rax+00h]
0x14000ad05  jmp     short loc_14000ACB9
0x14000ad07  mov     ecx, 3
0x14000ad0c  int     29h; Win8: RtlFailFast(ecx)
0x14000ad10  mov     rdx, rax; NameCache
0x14000ad13  mov     rcx, r14; NameCacheCtl
0x14000ad16  call    cs:__imp_RxNameCacheExpireEntry
0x14000ad1d  nop     dword ptr [rax+rax+00h]
0x14000ad22  lea     r9, [rbp+57h+var_A0]
0x14000ad26  xor     r8d, r8d
0x14000ad29  lea     rdx, [rbp+57h+String]
0x14000ad2d  mov     rcx, r14
0x14000ad30  call    cs:__imp_RxNameCacheFetchEntryEx
0x14000ad37  nop     dword ptr [rax+rax+00h]
0x14000ad3c  test    rax, rax
0x14000ad3f  jz      loc_14000AC71
0x14000ad45  jmp     short loc_14000AD10
0x14000ad47  movzx   edx, word ptr [rbx]
0x14000ad4a  lea     r8, [rdi+19Ch]
0x14000ad51  mov     rax, [rbx+8]
0x14000ad55  mov     r9, rdi
0x14000ad58  shr     dx, 1
0x14000ad5b  mov     [rsp+0F0h+var_B8], r15d
0x14000ad60  mov     [rsp+0F0h+var_C0], rax
0x14000ad65  mov     rax, [rdi+38h]
0x14000ad69  mov     [rsp+0F0h+var_C8], dx
0x14000ad6e  lea     rdx, SmbInvalidateFNFCache
0x14000ad75  mov     [rsp+0F0h+var_D0], rax
0x14000ad7a  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x14000ad7f  jmp     loc_14000ACB9
```
