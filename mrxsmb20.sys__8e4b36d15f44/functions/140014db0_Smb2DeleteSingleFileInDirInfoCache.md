# Smb2DeleteSingleFileInDirInfoCache

- ea: `0x140014db0`
- end: `0x1400150f9`
- name: `Smb2DeleteSingleFileInDirInfoCache`
- size: `841`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140013210`
- `0x1400236b0`
- `0x14002f280`

## callees

- `0x140004b30`
- `0x140004d30`
- `0x140014db0`
- `0x140015100`
- `0x1400151a0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x140014ee1`
- `ntoskrnl!RtlHashUnicodeString` at `0x140014ee1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014f92`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014fed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014f92`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014fed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014f59`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014f59`
- `rdbss!RxNameCacheCheckEntry` at `0x140014fa3`
- `rdbss!RxNameCacheCheckEntry` at `0x140014fa3`
- `rdbss!RxNameCacheExpireEntry` at `0x14001504b`
- `rdbss!RxNameCacheExpireEntry` at `0x14001504b`
- `rdbss!RxNameCacheActivateEntry` at `0x140014fd8`
- `rdbss!RxNameCacheActivateEntry` at `0x140014fd8`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014f75`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014f75`
- `rdbss!RxCrackPathName` at `0x140014e0c`
- `rdbss!RxCrackPathName` at `0x140014f44`
- `rdbss!RxCrackPathName` at `0x140014e0c`
- `rdbss!RxCrackPathName` at `0x140014f44`

## pseudocode

```c
__int64 __fastcall Smb2DeleteSingleFileInDirInfoCache(_QWORD *a1, struct _NAME_CACHE_CONTROL_ *a2, char a3)
{
  __int64 result; // rax
  void *v7; // rbx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v9; // rbx
  struct _LIST_ENTRY *Flink; // rsi
  __int64 v11; // rcx
  UNICODE_STRING String; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[18]; // [rsp+70h] [rbp-90h] BYREF
  ULONG HashValue; // [rsp+130h] [rbp+30h] BYREF

  String = 0;
  String1 = 0;
  v14 = 0;
  memset(v16, 0, 0x88u);
  result = RxCrackPathName(a1[7] + 360LL, &String, &String1, &v14);
  if ( String1.Length )
  {
    if ( !(_WORD)v14 )
    {
      result = a1[7];
      if ( (*(_BYTE *)(result + 355) & 0x3C) != 0xC )
      {
        if ( a3 )
        {
          HashValue = 0;
          RtlHashUnicodeString(&String, 1u, 0, &HashValue);
          memset(v16, 0, 0x88u);
          LODWORD(v16[0]) = 8973226;
          v16[13] = &v16[12];
          v16[12] = &v16[12];
          v16[9] = &v16[8];
          v16[8] = &v16[8];
          LODWORD(v16[14]) = HashValue;
          while ( 1 )
          {
            v15 = 0;
            RxCrackPathName(&String, 0, &v15, 0);
            ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
            while ( 1 )
            {
              Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v15, 0, v16);
              v9 = Entry;
              if ( !Entry )
              {
                ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
                goto LABEL_16;
              }
              if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
                break;
              RxNameCacheExpireEntry(a2, v9);
            }
            Flink = v9->Link.Flink;
            if ( Flink )
              Smb2ReferenceDirCacheObject(v9->Link.Flink);
            RxNameCacheActivateEntry(a2, v9, 0, 0);
            ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
            if ( !Flink )
              break;
            Smb2DeleteSingleFileInDirCacheObject(Flink, &String1);
            Smb2DereferenceDirCacheObject(Flink);
          }
LABEL_16:
          result = v16[12];
          if ( (_QWORD *)v16[12] != &v16[12] )
          {
            if ( *(_QWORD **)(v16[12] + 8LL) != &v16[12] || (v11 = v16[13], *(_QWORD **)v16[13] != &v16[12]) )
              __fastfail(3u);
            *(_QWORD *)v16[13] = v16[12];
            *(_QWORD *)(result + 8) = v11;
          }
        }
        else
        {
          result = Smb2FindOrCreateDirCacheObject(a1, a2, (__int64)&String, 0, 0, 0);
          v7 = (void *)result;
          if ( result )
          {
            Smb2DeleteSingleFileInDirCacheObject((void *)result, &String1);
            return Smb2DereferenceDirCacheObject(v7);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014db0  push    rbp
0x140014db2  push    rbx
0x140014db3  push    rsi
0x140014db4  push    rdi
0x140014db5  lea     rbp, [rsp-8]
0x140014dba  sub     rsp, 108h
0x140014dc1  xorps   xmm0, xmm0
0x140014dc4  movzx   esi, r8b
0x140014dc8  mov     rdi, rdx
0x140014dcb  mov     rbx, rcx
0x140014dce  xorps   xmm1, xmm1
0x140014dd1  lea     rcx, [rsp+120h+var_B0]; void *
0x140014dd6  xor     edx, edx; Val
0x140014dd8  mov     r8d, 88h; Size
0x140014dde  movups  xmmword ptr [rsp+120h+String.Length], xmm0
0x140014de3  movups  xmmword ptr [rsp+120h+String1.Length], xmm1
0x140014de8  movups  [rsp+120h+var_D0], xmm0
0x140014ded  call    memset
0x140014df2  mov     rcx, [rbx+38h]
0x140014df6  lea     r9, [rsp+120h+var_D0]
0x140014dfb  add     rcx, 168h
0x140014e02  lea     r8, [rsp+120h+String1]
0x140014e07  lea     rdx, [rsp+120h+String]
0x140014e0c  call    cs:__imp_RxCrackPathName
0x140014e13  nop     dword ptr [rax+rax+00h]
0x140014e18  cmp     [rsp+120h+String1.Length], 0
0x140014e1e  jz      loc_140014EB7
0x140014e24  cmp     word ptr [rsp+120h+var_D0], 0
0x140014e2a  jnz     loc_140014EB7
0x140014e30  mov     rax, [rbx+38h]
0x140014e34  movzx   ecx, byte ptr [rax+163h]
0x140014e3b  and     cl, 3Ch
0x140014e3e  cmp     cl, 0Ch
0x140014e41  jz      short loc_140014EB7
0x140014e43  mov     rax, [rbx+40h]
0x140014e47  mov     [rsp+120h+arg_10], r13
0x140014e4f  xor     r13d, r13d
0x140014e52  mov     [rsp+120h+arg_18], r14
0x140014e5a  mov     r14d, r13d
0x140014e5d  mov     [rsp+120h+var_20], r15
0x140014e65  mov     r15d, r13d
0x140014e68  test    rax, rax
0x140014e6b  jnz     loc_14001505C
0x140014e71  test    sil, sil
0x140014e74  jnz     short loc_140014EC4
0x140014e76  mov     [rsp+120h+var_F8], r13
0x140014e7b  lea     r8, [rsp+120h+String]
0x140014e80  xor     r9d, r9d
0x140014e83  mov     [rsp+120h+var_100], r13
0x140014e88  mov     rdx, rdi
0x140014e8b  mov     rcx, rbx
0x140014e8e  call    Smb2FindOrCreateDirCacheObject
0x140014e93  mov     rbx, rax
0x140014e96  test    rax, rax
0x140014e99  jnz     loc_1400150A2
0x140014e9f  mov     r14, [rsp+120h+arg_18]
0x140014ea7  mov     r13, [rsp+120h+arg_10]
0x140014eaf  mov     r15, [rsp+120h+var_20]
0x140014eb7  add     rsp, 108h
0x140014ebe  pop     rdi
0x140014ebf  pop     rsi
0x140014ec0  pop     rbx
0x140014ec1  pop     rbp
0x140014ec2  retn
0x140014ec4  mov     [rsp+120h+arg_8], r12
0x140014ecc  lea     r9, [rbp+20h+HashValue]; HashValue
0x140014ed0  xor     r8d, r8d; HashAlgorithm
0x140014ed3  mov     [rbp+20h+HashValue], r13d
0x140014ed7  mov     dl, 1; CaseInSensitive
0x140014ed9  lea     rcx, [rsp+120h+String]; String
0x140014ede  mov     r12, r13
0x140014ee1  call    cs:__imp_RtlHashUnicodeString
0x140014ee8  nop     dword ptr [rax+rax+00h]
0x140014eed  xor     edx, edx; Val
0x140014eef  lea     rcx, [rsp+120h+var_B0]; void *
0x140014ef4  mov     r8d, 88h; Size
0x140014efa  call    memset
0x140014eff  lea     rax, [rbp+20h+var_50]
0x140014f03  mov     [rsp+120h+var_B0], 88EBAAh
0x140014f0b  mov     [rbp+20h+var_48], rax
0x140014f0f  lea     rax, [rbp+20h+var_50]
0x140014f13  mov     [rbp+20h+var_50], rax
0x140014f17  lea     rax, [rbp+20h+var_70]
0x140014f1b  mov     [rbp+20h+var_68], rax
0x140014f1f  lea     rax, [rbp+20h+var_70]
0x140014f23  mov     [rbp+20h+var_70], rax
0x140014f27  mov     eax, [rbp+20h+HashValue]
0x140014f2a  mov     [rbp+20h+var_40], eax
0x140014f2d  xorps   xmm0, xmm0
0x140014f30  lea     r8, [rsp+120h+var_C0]
0x140014f35  xor     r9d, r9d
0x140014f38  lea     rcx, [rsp+120h+String]
0x140014f3d  xor     edx, edx
0x140014f3f  movups  [rsp+120h+var_C0], xmm0
0x140014f44  call    cs:__imp_RxCrackPathName
0x140014f4b  nop     dword ptr [rax+rax+00h]
0x140014f50  xor     edx, edx
0x140014f52  lea     rcx, Smb2DirCacheLock
0x140014f59  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140014f60  nop     dword ptr [rax+rax+00h]
0x140014f65  lea     r9, [rsp+120h+var_B0]
0x140014f6a  xor     r8d, r8d
0x140014f6d  lea     rdx, [rsp+120h+var_C0]
0x140014f72  mov     rcx, rdi
0x140014f75  call    cs:__imp_RxNameCacheFetchEntryEx
0x140014f7c  nop     dword ptr [rax+rax+00h]
0x140014f81  xor     edx, edx; MRxContext
0x140014f83  mov     rbx, rax
0x140014f86  test    rax, rax
0x140014f89  jnz     short loc_140014FA0
0x140014f8b  lea     rcx, Smb2DirCacheLock
0x140014f92  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014f99  nop     dword ptr [rax+rax+00h]
0x140014f9e  jmp     short loc_140015002
0x140014fa0  mov     rcx, rbx; NameCache
0x140014fa3  call    cs:__imp_RxNameCacheCheckEntry
0x140014faa  nop     dword ptr [rax+rax+00h]
0x140014faf  test    eax, eax
0x140014fb1  jnz     loc_140015045
0x140014fb7  mov     rsi, [rbx+28h]
0x140014fbb  test    rsi, rsi
0x140014fbe  jz      short loc_140014FCC
0x140014fc0  mov     rcx, rsi
0x140014fc3  call    Smb2ReferenceDirCacheObject
0x140014fc8  mov     r12, [rbx+78h]
0x140014fcc  xor     r9d, r9d; MRxContext
0x140014fcf  xor     r8d, r8d; LifeTime
0x140014fd2  mov     rdx, rbx; NameCache
0x140014fd5  mov     rcx, rdi; NameCacheCtl
0x140014fd8  call    cs:__imp_RxNameCacheActivateEntry
0x140014fdf  nop     dword ptr [rax+rax+00h]
0x140014fe4  xor     edx, edx
0x140014fe6  lea     rcx, Smb2DirCacheLock
0x140014fed  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014ff4  nop     dword ptr [rax+rax+00h]
0x140014ff9  test    rsi, rsi
0x140014ffc  jnz     loc_1400150C4
0x140015002  mov     rax, [rbp+20h+var_50]
0x140015006  lea     rcx, [rbp+20h+var_50]
0x14001500a  mov     r12, [rsp+120h+arg_8]
0x140015012  cmp     rax, rcx
0x140015015  jz      loc_140014E9F
0x14001501b  lea     rcx, [rbp+20h+var_50]
0x14001501f  cmp     [rax+8], rcx
0x140015023  jnz     short loc_14001503E
0x140015025  mov     rcx, [rbp+20h+var_48]
0x140015029  lea     rdx, [rbp+20h+var_50]
0x14001502d  cmp     [rcx], rdx
0x140015030  jnz     short loc_14001503E
0x140015032  mov     [rcx], rax
0x140015035  mov     [rax+8], rcx
0x140015039  jmp     loc_140014E9F
0x14001503e  mov     ecx, 3
0x140015043  int     29h; Win8: RtlFailFast(ecx)
0x140015045  mov     rdx, rbx; NameCache
0x140015048  mov     rcx, rdi; NameCacheCtl
0x14001504b  call    cs:__imp_RxNameCacheExpireEntry
0x140015052  nop     dword ptr [rax+rax+00h]
0x140015057  jmp     loc_140014F65
0x14001505c  mov     rcx, [rax+38h]
0x140015060  test    rcx, rcx
0x140015063  jz      loc_140014E71
0x140015069  mov     rax, [rbx+48h]
0x14001506d  lea     r15, [rcx+8]
0x140015071  mov     rcx, [rax+28h]
0x140015075  mov     r14, [rcx+28h]
0x140015079  mov     rax, [r14+1A8h]
0x140015080  test    dword ptr [rax+0B8h], 800h
0x14001508a  jnz     short loc_140015099
0x14001508c  mov     rax, [r14+18h]
0x140015090  test    byte ptr [rax+522h], 4
0x140015097  jnz     short loc_1400150ED
0x140015099  mov     r14, [r14+60h]
0x14001509d  jmp     loc_140014E71
0x1400150a2  mov     r9, r15
0x1400150a5  lea     r8, [rsp+120h+String]
0x1400150aa  lea     rdx, [rsp+120h+String1]; String1
0x1400150af  mov     rcx, rbx; Context
0x1400150b2  call    Smb2DeleteSingleFileInDirCacheObject
0x1400150b7  mov     rcx, rbx; P
0x1400150ba  call    Smb2DereferenceDirCacheObject
0x1400150bf  jmp     loc_140014E9F
0x1400150c4  cmp     r14, r12
0x1400150c7  lea     r8, [rsp+120h+String]
0x1400150cc  mov     r9, r15
0x1400150cf  lea     rdx, [rsp+120h+String1]; String1
0x1400150d4  cmovnz  r9, r13
0x1400150d8  mov     rcx, rsi; Context
0x1400150db  call    Smb2DeleteSingleFileInDirCacheObject
0x1400150e0  mov     rcx, rsi; P
0x1400150e3  call    Smb2DereferenceDirCacheObject
0x1400150e8  jmp     loc_140014F2D
0x1400150ed  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1400150f4  jmp     loc_140014E71
```
