# CVarObjHeap::ReadBuffer(ulong,ulong,uchar * *,ulong *,MemoryPage * *)

- ea: `0x18000bc10`
- end: `0x18000bee7`
- name: `?ReadBuffer@CVarObjHeap@@QEAAKKKPEAPEAEPEAKPEAPEAVMemoryPage@@@Z`
- size: `727`
- prototype: `unsigned int __fastcall(CVarObjHeap *__hidden this, unsigned int, unsigned int, unsigned __int8 **, unsigned int *, struct MemoryPage **)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b6c0`
- `0x18000bf70`
- `0x180028a74`
- `0x18002bf30`

## callees

- `0x1800012b8`
- `0x18000bc10`
- `0x18000e000`
- `0x18000f8f0`
- `0x18002b7b6`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bebb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000bebb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bcc9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bcc9`
- `wbemcomn!GetMemLogObject` at `0x18000bcd8`
- `wbemcomn!GetMemLogObject` at `0x18000be45`
- `wbemcomn!GetMemLogObject` at `0x18000bea2`
- `wbemcomn!GetMemLogObject` at `0x18000bcd8`
- `wbemcomn!GetMemLogObject` at `0x18000be45`
- `wbemcomn!GetMemLogObject` at `0x18000bea2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bce3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000be53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bead`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bce3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000be53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bead`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVarObjHeap::ReadBuffer(
        CPageFile **this,
        unsigned int a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        struct MemoryPage **a6)
{
  int v6; // edi
  int v7; // r13d
  unsigned int Page; // esi
  __int64 v9; // r8
  MemoryPage *v10; // rbx
  unsigned __int8 *v11; // r14
  unsigned int v12; // r15d
  unsigned int i; // edx
  int v14; // eax
  unsigned __int8 *v15; // rbp
  CMemoryLog *v16; // rax
  unsigned int v17; // edi
  unsigned __int8 *v19; // rcx
  MemoryPage *v20; // r14
  const void *v21; // rdx
  CMemoryLog *v22; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int8 *v24; // rax
  MemoryPage *v25; // [rsp+20h] [rbp-58h] BYREF
  size_t v26; // [rsp+28h] [rbp-50h]
  MemoryPage *v27; // [rsp+30h] [rbp-48h]

  v6 = a3;
  if ( (_DWORD)a3 )
  {
    v7 = 0;
    *a6 = 0;
    v25 = 0;
    Page = CPageFile::GetPage(*this, a2, a3, &v25);
    v10 = v25;
    v27 = v25;
    v11 = 0;
    v12 = 0;
    if ( !Page )
    {
      v9 = *((_QWORD *)v25 + 2);
      for ( i = 0; ; ++i )
      {
        v14 = *(_DWORD *)(v9 + 16LL * i);
        if ( !v14 )
          break;
        if ( v14 == v6 )
        {
          Page = 0;
          v12 = *(_DWORD *)(v9 + 16LL * i + 8);
          v11 = (unsigned __int8 *)(v9 + *(unsigned int *)(v9 + 16LL * i + 4));
          goto LABEL_8;
        }
      }
      Page = 2;
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 2);
LABEL_8:
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, Page);
      }
    }
    if ( Page )
    {
      v15 = 0;
    }
    else
    {
      v17 = v12;
      if ( v12 >= *((_DWORD *)v10 + 4) - (int)v11 + 0x2000 )
        v17 = *((_DWORD *)v10 + 4) - (_DWORD)v11 + 0x2000;
      if ( v17 >= v12 )
      {
        *a6 = v10;
        v15 = v11;
        goto LABEL_21;
      }
      v24 = (unsigned __int8 *)CWin32DefaultArena::WbemMemAlloc(v12);
      v15 = v24;
      if ( v24 )
      {
        memcpy_0(v24, v11, v17);
LABEL_21:
        while ( v17 < v12 )
        {
          ++v7;
          v25 = 0;
          Page = CPageFile::GetPage(*this, v7 + a2, v9, &v25);
          if ( Page )
            goto LABEL_11;
          v19 = &v15[v17];
          v20 = v25;
          v21 = (const void *)*((_QWORD *)v25 + 2);
          if ( v17 + 0x2000 <= v12 )
          {
            memcpy_0(v19, v21, 0x2000u);
            LODWORD(v26) = 0x2000;
          }
          else
          {
            v26 = v12 - v17;
            memcpy_0(v19, v21, v26);
          }
          MemoryPage::Release(v20);
          v17 += v26;
        }
        *a4 = v15;
        *a5 = v12;
        if ( *a6 )
          v10 = 0;
        goto LABEL_24;
      }
      Page = 14;
    }
LABEL_11:
    if ( !*a6 )
      CWin32DefaultArena::WbemMemFree(v15);
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, Page);
LABEL_24:
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, Page);
    }
    if ( v10 )
      MemoryPage::Release(v10);
    return Page;
  }
  v22 = GetMemLogObject();
  CMemoryLog::Write(v22, 87);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, 87);
  }
  return 87;
}

```

## disassembly

```asm
0x18000bc10  mov     [rsp+arg_10], rbx
0x18000bc15  mov     [rsp+arg_18], r9
0x18000bc1a  mov     [rsp+arg_8], edx
0x18000bc1e  mov     [rsp+arg_0], rcx
0x18000bc23  push    rbp
0x18000bc24  push    rsi
0x18000bc25  push    rdi
0x18000bc26  push    r12
0x18000bc28  push    r13
0x18000bc2a  push    r14
0x18000bc2c  push    r15
0x18000bc2e  sub     rsp, 40h
0x18000bc32  mov     edi, r8d
0x18000bc35  test    r8d, r8d
0x18000bc38  jz      loc_18000BE45
0x18000bc3e  xor     r13d, r13d
0x18000bc41  mov     r12, [rsp+78h+arg_28]
0x18000bc49  mov     [r12], r13
0x18000bc4d  mov     [rsp+78h+var_58], r13
0x18000bc52  lea     r9, [rsp+78h+var_58]; struct MemoryPage **
0x18000bc57  mov     rcx, [rcx]; this
0x18000bc5a  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x18000bc5f  mov     esi, eax
0x18000bc61  mov     rbx, [rsp+78h+var_58]
0x18000bc66  mov     [rsp+78h+var_48], rbx
0x18000bc6b  mov     r14d, r13d
0x18000bc6e  mov     r15d, r13d
0x18000bc71  lea     rbp, WPP_GLOBAL_Control
0x18000bc78  test    eax, eax
0x18000bc7a  jnz     short loc_18000BCB8
0x18000bc7c  mov     r8, [rbx+10h]; unsigned int
0x18000bc80  mov     edx, r13d
0x18000bc83  mov     ecx, edx
0x18000bc85  add     rcx, rcx
0x18000bc88  mov     eax, [r8+rcx*8]
0x18000bc8c  test    eax, eax
0x18000bc8e  jz      loc_18000BE9D
0x18000bc94  cmp     eax, edi
0x18000bc96  jz      short loc_18000BC9C
0x18000bc98  inc     edx
0x18000bc9a  jmp     short loc_18000BC83
0x18000bc9c  mov     esi, r13d
0x18000bc9f  mov     r15d, [r8+rcx*8+8]
0x18000bca4  mov     r14d, [r8+rcx*8+4]
0x18000bca9  add     r14, r8
0x18000bcac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcb3  cmp     rcx, rbp
0x18000bcb6  jnz     short loc_18000BCEB
0x18000bcb8  test    esi, esi
0x18000bcba  jz      short loc_18000BD11
0x18000bcbc  mov     rbp, r13
0x18000bcbf  cmp     qword ptr [r12], 0
0x18000bcc4  jnz     short loc_18000BCD8
0x18000bcc6  mov     rcx, rbp
0x18000bcc9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000bccf  nop
0x18000bcd0  test    esi, esi
0x18000bcd2  jz      loc_18000BD5D
0x18000bcd8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000bcde  mov     edx, esi
0x18000bce0  mov     rcx, rax
0x18000bce3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000bce9  jmp     short loc_18000BD5D
0x18000bceb  test    byte ptr [rcx+1Ch], 1
0x18000bcef  jz      short loc_18000BCB8
0x18000bcf1  cmp     byte ptr [rcx+19h], 2
0x18000bcf5  jb      short loc_18000BCB8
0x18000bcf7  mov     edx, 15h
0x18000bcfc  mov     r9d, esi
0x18000bcff  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18000bd06  mov     rcx, [rcx+10h]
0x18000bd0a  call    WPP_SF_d
0x18000bd0f  jmp     short loc_18000BCB8
0x18000bd11  mov     eax, [rbx+10h]
0x18000bd14  sub     eax, r14d
0x18000bd17  add     eax, 2000h
0x18000bd1c  mov     edi, r15d
0x18000bd1f  cmp     r15d, eax
0x18000bd22  cmovnb  edi, eax
0x18000bd25  cmp     edi, r15d
0x18000bd28  jb      loc_18000BEB8
0x18000bd2e  mov     [r12], rbx
0x18000bd32  mov     rbp, r14
0x18000bd35  cmp     edi, r15d
0x18000bd38  jb      loc_18000BDBF
0x18000bd3e  mov     rax, [rsp+78h+arg_18]
0x18000bd46  mov     [rax], rbp
0x18000bd49  mov     rax, [rsp+78h+arg_20]
0x18000bd51  mov     [rax], r15d
0x18000bd54  cmp     qword ptr [r12], 0
0x18000bd59  jz      short loc_18000BD5D
0x18000bd5b  xor     ebx, ebx
0x18000bd5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd64  lea     rax, WPP_GLOBAL_Control
0x18000bd6b  cmp     rcx, rax
0x18000bd6e  jz      short loc_18000BD76
0x18000bd70  test    byte ptr [rcx+1Ch], 1
0x18000bd74  jnz     short loc_18000BD9F
0x18000bd76  test    rbx, rbx
0x18000bd79  jnz     short loc_18000BD95
0x18000bd7b  mov     eax, esi
0x18000bd7d  mov     rbx, [rsp+78h+arg_10]
0x18000bd85  add     rsp, 40h
0x18000bd89  pop     r15
0x18000bd8b  pop     r14
0x18000bd8d  pop     r13
0x18000bd8f  pop     r12
0x18000bd91  pop     rdi
0x18000bd92  pop     rsi
0x18000bd93  pop     rbp
0x18000bd94  retn
0x18000bd95  mov     rcx, rbx; this
0x18000bd98  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000bd9d  jmp     short loc_18000BD7B
0x18000bd9f  cmp     byte ptr [rcx+19h], 2
0x18000bda3  jb      short loc_18000BD76
0x18000bda5  mov     edx, 0Ch
0x18000bdaa  mov     r9d, esi
0x18000bdad  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18000bdb4  mov     rcx, [rcx+10h]
0x18000bdb8  call    WPP_SF_d
0x18000bdbd  jmp     short loc_18000BD76
0x18000bdbf  inc     r13d
0x18000bdc2  mov     [rsp+78h+var_58], 0
0x18000bdcb  mov     edx, [rsp+78h+arg_8]
0x18000bdd2  add     edx, r13d; unsigned int
0x18000bdd5  lea     r9, [rsp+78h+var_58]; struct MemoryPage **
0x18000bdda  mov     rax, [rsp+78h+arg_0]
0x18000bde2  mov     rcx, [rax]; this
0x18000bde5  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x18000bdea  mov     esi, eax
0x18000bdec  test    eax, eax
0x18000bdee  jnz     loc_18000BCBF
0x18000bdf4  mov     ecx, edi
0x18000bdf6  add     rcx, rbp; void *
0x18000bdf9  lea     eax, [rdi+2000h]
0x18000bdff  mov     r14, [rsp+78h+var_58]
0x18000be04  mov     rdx, [r14+10h]; Src
0x18000be08  cmp     eax, r15d
0x18000be0b  jbe     short loc_18000BE30
0x18000be0d  mov     eax, r15d
0x18000be10  sub     eax, edi
0x18000be12  mov     [rsp+78h+var_50], rax
0x18000be17  mov     r8d, eax; Size
0x18000be1a  call    memcpy_0
0x18000be1f  mov     rcx, r14; this
0x18000be22  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000be27  add     edi, dword ptr [rsp+78h+var_50]
0x18000be2b  jmp     loc_18000BD35
0x18000be30  mov     r8d, 2000h; Size
0x18000be36  call    memcpy_0
0x18000be3b  mov     dword ptr [rsp+78h+var_50], 2000h
0x18000be43  jmp     short loc_18000BE1F
0x18000be45  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000be4b  mov     edx, 57h ; 'W'
0x18000be50  mov     rcx, rax
0x18000be53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000be59  lea     rax, WPP_GLOBAL_Control
0x18000be60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be67  cmp     rcx, rax
0x18000be6a  jz      short loc_18000BE93
0x18000be6c  test    byte ptr [rcx+1Ch], 1
0x18000be70  jz      short loc_18000BE93
0x18000be72  cmp     byte ptr [rcx+19h], 2
0x18000be76  jb      short loc_18000BE93
0x18000be78  mov     edx, 0Bh
0x18000be7d  mov     r9d, 57h ; 'W'
0x18000be83  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18000be8a  mov     rcx, [rcx+10h]
0x18000be8e  call    WPP_SF_d
0x18000be93  mov     eax, 57h ; 'W'
0x18000be98  jmp     loc_18000BD7D
0x18000be9d  mov     esi, 2
0x18000bea2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000bea8  mov     edx, esi
0x18000beaa  mov     rcx, rax
0x18000bead  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000beb3  jmp     loc_18000BCAC
0x18000beb8  mov     ecx, r15d
0x18000bebb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000bec1  mov     rbp, rax
0x18000bec4  test    rax, rax
0x18000bec7  jnz     short loc_18000BED3
0x18000bec9  mov     esi, 0Eh
0x18000bece  jmp     loc_18000BCBF
0x18000bed3  mov     r8d, edi; Size
0x18000bed6  mov     rdx, r14; Src
0x18000bed9  mov     rcx, rax; void *
0x18000bedc  call    memcpy_0
0x18000bee1  jmp     loc_18000BD35
```
