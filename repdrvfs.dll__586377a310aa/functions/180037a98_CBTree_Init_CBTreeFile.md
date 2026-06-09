# CBTree::Init(CBTreeFile *)

- ea: `0x180037a98`
- end: `0x180037ca9`
- name: `?Init@CBTree@@QEAAKPEAVCBTreeFile@@@Z`
- size: `529`
- prototype: `unsigned int(CBTree *__hidden this, struct CBTreeFile *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028a74`
- `0x18003e3f0`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000f130`
- `0x18000f8f0`
- `0x18000fa20`
- `0x1800129a0`
- `0x180037a98`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180037ae7`
- `wbemcomn!GetMemLogObject` at `0x180037b74`
- `wbemcomn!GetMemLogObject` at `0x180037bc9`
- `wbemcomn!GetMemLogObject` at `0x180037c2a`
- `wbemcomn!GetMemLogObject` at `0x180037ae7`
- `wbemcomn!GetMemLogObject` at `0x180037b74`
- `wbemcomn!GetMemLogObject` at `0x180037bc9`
- `wbemcomn!GetMemLogObject` at `0x180037c2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037af7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037b7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037bd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037c3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037af7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037b7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037bd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b3e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180037b34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180037b34`

## pseudocode

```c
DWORD __fastcall CBTree::Init(CBTree *this, struct CBTreeFile *a2)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int Page; // ebx
  CVarObjHeap *v6; // rcx
  __int64 v7; // rdx
  unsigned int v9; // ebp
  unsigned int v10; // edx
  CMemoryLog *v11; // rax
  MemoryPage *v12; // rbx
  unsigned int v13; // edi
  CMemoryLog *v14; // rax
  SIdxKeyTable *v15; // rcx
  CMemoryLog *v16; // rax
  MemoryPage *v17; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    Page = 87;
    CMemoryLog::Write(MemLogObject, 87);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return Page;
    }
    v7 = 96;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, Page);
    return Page;
  }
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0) )
    return GetLastError();
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  v9 = *(_DWORD *)a2;
  v10 = *(_DWORD *)a2;
  v17 = 0;
  Page = CBTreeFile::GetPage(a2, v10, &v17);
  if ( Page )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, Page);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return Page;
    }
    v7 = 97;
    goto LABEL_10;
  }
  v12 = v17;
  v13 = SIdxKeyTable::Create(*((void **)v17 + 2), 0, (struct SIdxKeyTable **)this + 1);
  MemoryPage::Release(v12);
  if ( v13 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v13);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v13);
    }
    return v13;
  }
  else
  {
    v15 = (SIdxKeyTable *)*((_QWORD *)this + 1);
    if ( v9 != *((_DWORD *)v15 + 1) )
    {
      SIdxKeyTable::Release(v15);
      CRepositoryCorruption::SetRepositoryCorrupted(129, 0, 0);
      v16 = GetMemLogObject();
      Page = 1358;
      CMemoryLog::Write(v16, 1358);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return Page;
      }
      v7 = 99;
      goto LABEL_10;
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180037a98  push    rbx
0x180037a9a  push    rbp
0x180037a9b  push    rsi
0x180037a9c  push    rdi
0x180037a9d  push    r12
0x180037a9f  push    r15
0x180037aa1  sub     rsp, 28h
0x180037aa5  mov     rbx, rdx
0x180037aa8  mov     rsi, rcx
0x180037aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ab2  lea     r12, WPP_GLOBAL_Control
0x180037ab9  lea     r15, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180037ac0  cmp     rcx, r12
0x180037ac3  jz      short loc_180037AE2
0x180037ac5  test    byte ptr [rcx+1Ch], 1
0x180037ac9  jz      short loc_180037AE2
0x180037acb  cmp     byte ptr [rcx+19h], 5
0x180037acf  jb      short loc_180037AE2
0x180037ad1  mov     rcx, [rcx+10h]
0x180037ad5  mov     edx, 5Fh ; '_'
0x180037ada  mov     r8, r15
0x180037add  call    WPP_SF_
0x180037ae2  test    rbx, rbx
0x180037ae5  jnz     short loc_180037B2E
0x180037ae7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037aed  mov     ebx, 57h ; 'W'
0x180037af2  mov     rcx, rax
0x180037af5  mov     edx, ebx
0x180037af7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b04  cmp     rcx, r12
0x180037b07  jz      short loc_180037B27
0x180037b09  test    byte ptr [rcx+1Ch], 1
0x180037b0d  jz      short loc_180037B27
0x180037b0f  cmp     byte ptr [rcx+19h], 2
0x180037b13  jb      short loc_180037B27
0x180037b15  lea     edx, [rbx+9]
0x180037b18  mov     rcx, [rcx+10h]
0x180037b1c  mov     r9d, ebx
0x180037b1f  mov     r8, r15
0x180037b22  call    WPP_SF_d
0x180037b27  mov     eax, ebx
0x180037b29  jmp     loc_180037C9C
0x180037b2e  lea     rcx, [rsi+10h]; lpCriticalSection
0x180037b32  xor     edx, edx; dwSpinCount
0x180037b34  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180037b3a  test    eax, eax
0x180037b3c  jnz     short loc_180037B49
0x180037b3e  call    cs:__imp_GetLastError
0x180037b44  jmp     loc_180037C9C
0x180037b49  mov     [rsi], rbx
0x180037b4c  lea     r8, [rsp+58h+arg_8]; struct MemoryPage **
0x180037b51  mov     qword ptr [rsi+8], 0
0x180037b59  mov     rcx, rbx; this
0x180037b5c  mov     ebp, [rbx]
0x180037b5e  mov     edx, ebp; unsigned int
0x180037b60  mov     [rsp+58h+arg_8], 0
0x180037b69  call    ?GetPage@CBTreeFile@@QEAAKKPEAPEAVMemoryPage@@@Z; CBTreeFile::GetPage(ulong,MemoryPage * *)
0x180037b6e  mov     ebx, eax
0x180037b70  test    eax, eax
0x180037b72  jz      short loc_180037BA7
0x180037b74  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037b7a  mov     rcx, rax
0x180037b7d  mov     edx, ebx
0x180037b7f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b8c  cmp     rcx, r12
0x180037b8f  jz      short loc_180037B27
0x180037b91  test    byte ptr [rcx+1Ch], 1
0x180037b95  jz      short loc_180037B27
0x180037b97  cmp     byte ptr [rcx+19h], 2
0x180037b9b  jb      short loc_180037B27
0x180037b9d  mov     edx, 61h ; 'a'
0x180037ba2  jmp     loc_180037B18
0x180037ba7  mov     rbx, [rsp+58h+arg_8]
0x180037bac  lea     r8, [rsi+8]; struct SIdxKeyTable **
0x180037bb0  xor     edx, edx; struct MemoryPage *
0x180037bb2  mov     rcx, [rbx+10h]; void *
0x180037bb6  call    ?Create@SIdxKeyTable@@SAKPEAXPEAVMemoryPage@@PEAPEAV1@@Z; SIdxKeyTable::Create(void *,MemoryPage *,SIdxKeyTable * *)
0x180037bbb  mov     rcx, rbx; this
0x180037bbe  mov     edi, eax
0x180037bc0  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180037bc5  test    edi, edi
0x180037bc7  jz      short loc_180037C0D
0x180037bc9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037bcf  mov     rcx, rax
0x180037bd2  mov     edx, edi
0x180037bd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180037be1  cmp     rcx, r12
0x180037be4  jz      short loc_180037C06
0x180037be6  test    byte ptr [rcx+1Ch], 1
0x180037bea  jz      short loc_180037C06
0x180037bec  cmp     byte ptr [rcx+19h], 2
0x180037bf0  jb      short loc_180037C06
0x180037bf2  mov     rcx, [rcx+10h]
0x180037bf6  mov     edx, 62h ; 'b'
0x180037bfb  mov     r9d, edi
0x180037bfe  mov     r8, r15
0x180037c01  call    WPP_SF_d
0x180037c06  mov     eax, edi
0x180037c08  jmp     loc_180037C9C
0x180037c0d  mov     rcx, [rsi+8]; this
0x180037c11  cmp     ebp, [rcx+4]
0x180037c14  jz      short loc_180037C6E
0x180037c16  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180037c1b  xor     r8d, r8d; unsigned int
0x180037c1e  xor     edx, edx; bool
0x180037c20  mov     ecx, 81h; int
0x180037c25  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180037c2a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037c30  mov     ebx, 54Eh
0x180037c35  mov     rcx, rax
0x180037c38  mov     edx, ebx
0x180037c3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c47  cmp     rcx, r12
0x180037c4a  jz      loc_180037B27
0x180037c50  test    byte ptr [rcx+1Ch], 1
0x180037c54  jz      loc_180037B27
0x180037c5a  cmp     byte ptr [rcx+19h], 2
0x180037c5e  jb      loc_180037B27
0x180037c64  mov     edx, 63h ; 'c'
0x180037c69  jmp     loc_180037B18
0x180037c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c75  cmp     rcx, r12
0x180037c78  jz      short loc_180037C9A
0x180037c7a  test    byte ptr [rcx+1Ch], 1
0x180037c7e  jz      short loc_180037C9A
0x180037c80  cmp     byte ptr [rcx+19h], 2
0x180037c84  jb      short loc_180037C9A
0x180037c86  mov     rcx, [rcx+10h]
0x180037c8a  mov     edx, 64h ; 'd'
0x180037c8f  xor     r9d, r9d
0x180037c92  mov     r8, r15
0x180037c95  call    WPP_SF_d
0x180037c9a  xor     eax, eax
0x180037c9c  add     rsp, 28h
0x180037ca0  pop     r15
0x180037ca2  pop     r12
0x180037ca4  pop     rdi
0x180037ca5  pop     rsi
0x180037ca6  pop     rbp
0x180037ca7  pop     rbx
0x180037ca8  retn
```
