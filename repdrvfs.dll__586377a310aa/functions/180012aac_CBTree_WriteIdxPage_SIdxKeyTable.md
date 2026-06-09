# CBTree::WriteIdxPage(SIdxKeyTable *)

- ea: `0x180012aac`
- end: `0x180012ccd`
- name: `?WriteIdxPage@CBTree@@AEAAKPEAVSIdxKeyTable@@@Z`
- size: `545`
- prototype: `unsigned int(CBTree *__hidden this, struct SIdxKeyTable *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010fe4`
- `0x180011904`
- `0x180027eb4`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000f8f0`
- `0x1800129a0`
- `0x180012aac`
- `0x180012cd4`
- `0x180012d24`
- `0x180012e84`
- `0x180038410`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180012b16`
- `wbemcomn!GetMemLogObject` at `0x180012b65`
- `wbemcomn!GetMemLogObject` at `0x180012bbf`
- `wbemcomn!GetMemLogObject` at `0x180012c0f`
- `wbemcomn!GetMemLogObject` at `0x180012c81`
- `wbemcomn!GetMemLogObject` at `0x180012b16`
- `wbemcomn!GetMemLogObject` at `0x180012b65`
- `wbemcomn!GetMemLogObject` at `0x180012bbf`
- `wbemcomn!GetMemLogObject` at `0x180012c0f`
- `wbemcomn!GetMemLogObject` at `0x180012c81`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b73`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012bca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b73`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012bca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c8c`

## pseudocode

```c
__int64 __fastcall CBTree::WriteIdxPage(CBTree *this, struct SIdxKeyTable *a2)
{
  unsigned int v4; // ecx
  CMemoryLog *v5; // rax
  unsigned int v6; // ebx
  CVarObjHeap *v7; // rcx
  __int64 v8; // rdx
  struct MemoryPage *Page; // rax
  MemoryPage *v10; // rbp
  CMemoryLog *v11; // rax
  unsigned int v12; // r8d
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  SIdxKeyTable *v15; // rcx
  unsigned int v16; // edx
  CMemoryLog *v17; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  v4 = *(_DWORD *)(*((_QWORD *)a2 + 8) + 36LL)
     + 2 * (**((_DWORD **)a2 + 8) + *((_DWORD *)a2 + 15) + 5 * (*((_DWORD *)a2 + 3) + 5));
  if ( v4 <= 0x2000 )
  {
    Page = MemoryPage::AllocatePage(v4);
    v10 = Page;
    if ( Page )
    {
      v6 = SIdxKeyTable::MapToPage(a2, *((void **)Page + 2));
      if ( v6 )
      {
        MemoryPage::Release(v10);
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v6);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 122;
          goto LABEL_34;
        }
      }
      else
      {
        v6 = CBTreeFile::PutPage(*(CBTreeFile **)this, v10, v12);
        if ( v6 )
        {
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, v6);
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 123;
            goto LABEL_34;
          }
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 14);
          v15 = (SIdxKeyTable *)*((_QWORD *)this + 1);
          if ( v15 != a2 && *((_DWORD *)v15 + 1) == *((_DWORD *)a2 + 1) )
          {
            SIdxKeyTable::Release(v15);
            *((_QWORD *)this + 1) = a2;
            _InterlockedIncrement((volatile signed __int32 *)a2);
            v16 = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL);
            if ( **(_DWORD **)this != v16 )
            {
              v6 = CBTreeFile::SetRootPage(*(CBTreeFile **)this, v16);
              if ( v6 )
              {
                v17 = GetMemLogObject();
                CMemoryLog::Write(v17, v6);
              }
            }
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 124;
            goto LABEL_34;
          }
        }
      }
    }
    else
    {
      v11 = GetMemLogObject();
      v6 = 8;
      CMemoryLog::Write(v11, 8);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 121;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v5 = GetMemLogObject();
    v6 = 87;
    CMemoryLog::Write(v5, 87);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 120;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180012aac  push    rbx
0x180012aae  push    rbp
0x180012aaf  push    rsi
0x180012ab0  push    rdi
0x180012ab1  push    r12
0x180012ab3  push    r15
0x180012ab5  sub     rsp, 28h
0x180012ab9  mov     rdi, rdx
0x180012abc  mov     rsi, rcx
0x180012abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ac6  lea     r12, WPP_GLOBAL_Control
0x180012acd  lea     r15, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180012ad4  cmp     rcx, r12
0x180012ad7  jz      short loc_180012AF6
0x180012ad9  test    byte ptr [rcx+1Ch], 1
0x180012add  jz      short loc_180012AF6
0x180012adf  cmp     byte ptr [rcx+19h], 5
0x180012ae3  jb      short loc_180012AF6
0x180012ae5  mov     rcx, [rcx+10h]
0x180012ae9  mov     edx, 77h ; 'w'
0x180012aee  mov     r8, r15
0x180012af1  call    WPP_SF_
0x180012af6  mov     rdx, [rdi+40h]
0x180012afa  mov     eax, [rdi+0Ch]
0x180012afd  add     eax, 5
0x180012b00  lea     ecx, [rax+rax*4]
0x180012b03  mov     eax, [rdx+24h]
0x180012b06  add     ecx, [rdi+3Ch]
0x180012b09  add     ecx, [rdx]
0x180012b0b  lea     ecx, [rax+rcx*2]; unsigned int
0x180012b0e  cmp     ecx, 2000h
0x180012b14  jbe     short loc_180012B58
0x180012b16  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012b1c  mov     ebx, 57h ; 'W'
0x180012b21  mov     rcx, rax
0x180012b24  mov     edx, ebx
0x180012b26  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b33  cmp     rcx, r12
0x180012b36  jz      loc_180012CBE
0x180012b3c  test    byte ptr [rcx+1Ch], 1
0x180012b40  jz      loc_180012CBE
0x180012b46  cmp     byte ptr [rcx+19h], 2
0x180012b4a  jb      loc_180012CBE
0x180012b50  lea     edx, [rbx+21h]
0x180012b53  jmp     loc_180012CAF
0x180012b58  call    ?AllocatePage@MemoryPage@@SAPEAV1@K@Z; MemoryPage::AllocatePage(ulong)
0x180012b5d  mov     rbp, rax
0x180012b60  test    rax, rax
0x180012b63  jnz     short loc_180012BA5
0x180012b65  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012b6b  lea     ebx, [rbp+8]
0x180012b6e  mov     rcx, rax
0x180012b71  mov     edx, ebx
0x180012b73  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b80  cmp     rcx, r12
0x180012b83  jz      loc_180012CBE
0x180012b89  test    byte ptr [rcx+1Ch], 1
0x180012b8d  jz      loc_180012CBE
0x180012b93  cmp     byte ptr [rcx+19h], 2
0x180012b97  jb      loc_180012CBE
0x180012b9d  lea     edx, [rbp+79h]
0x180012ba0  jmp     loc_180012CAF
0x180012ba5  mov     rdx, [rax+10h]; void *
0x180012ba9  mov     rcx, rdi; this
0x180012bac  call    ?MapToPage@SIdxKeyTable@@QEAAKPEAX@Z; SIdxKeyTable::MapToPage(void *)
0x180012bb1  mov     ebx, eax
0x180012bb3  test    eax, eax
0x180012bb5  jz      short loc_180012BFE
0x180012bb7  mov     rcx, rbp; this
0x180012bba  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180012bbf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012bc5  mov     rcx, rax
0x180012bc8  mov     edx, ebx
0x180012bca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bd7  cmp     rcx, r12
0x180012bda  jz      loc_180012CBE
0x180012be0  test    byte ptr [rcx+1Ch], 1
0x180012be4  jz      loc_180012CBE
0x180012bea  cmp     byte ptr [rcx+19h], 2
0x180012bee  jb      loc_180012CBE
0x180012bf4  mov     edx, 7Ah ; 'z'
0x180012bf9  jmp     loc_180012CAF
0x180012bfe  mov     rcx, [rsi]; this
0x180012c01  mov     rdx, rbp; struct MemoryPage *
0x180012c04  call    ?PutPage@CBTreeFile@@QEAAKPEAVMemoryPage@@K@Z; CBTreeFile::PutPage(MemoryPage *,ulong)
0x180012c09  mov     ebx, eax
0x180012c0b  test    eax, eax
0x180012c0d  jz      short loc_180012C47
0x180012c0f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012c15  mov     rcx, rax
0x180012c18  mov     edx, ebx
0x180012c1a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c27  cmp     rcx, r12
0x180012c2a  jz      loc_180012CBE
0x180012c30  test    byte ptr [rcx+1Ch], 1
0x180012c34  jz      loc_180012CBE
0x180012c3a  cmp     byte ptr [rcx+19h], 2
0x180012c3e  jb      short loc_180012CBE
0x180012c40  mov     edx, 7Bh ; '{'
0x180012c45  jmp     short loc_180012CAF
0x180012c47  lock inc dword ptr [rsi+38h]
0x180012c4b  mov     rcx, [rsi+8]; this
0x180012c4f  cmp     rcx, rdi
0x180012c52  jz      short loc_180012C92
0x180012c54  mov     eax, [rdi+4]
0x180012c57  cmp     [rcx+4], eax
0x180012c5a  jnz     short loc_180012C92
0x180012c5c  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180012c61  mov     [rsi+8], rdi
0x180012c65  lock inc dword ptr [rdi]
0x180012c68  mov     rax, [rsi+8]
0x180012c6c  mov     rcx, [rsi]; this
0x180012c6f  mov     edx, [rax+4]; unsigned int
0x180012c72  cmp     [rcx], edx
0x180012c74  jz      short loc_180012C92
0x180012c76  call    ?SetRootPage@CBTreeFile@@QEAAKK@Z; CBTreeFile::SetRootPage(ulong)
0x180012c7b  mov     ebx, eax
0x180012c7d  test    eax, eax
0x180012c7f  jz      short loc_180012C92
0x180012c81  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012c87  mov     rcx, rax
0x180012c8a  mov     edx, ebx
0x180012c8c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c99  cmp     rcx, r12
0x180012c9c  jz      short loc_180012CBE
0x180012c9e  test    byte ptr [rcx+1Ch], 1
0x180012ca2  jz      short loc_180012CBE
0x180012ca4  cmp     byte ptr [rcx+19h], 2
0x180012ca8  jb      short loc_180012CBE
0x180012caa  mov     edx, 7Ch ; '|'
0x180012caf  mov     rcx, [rcx+10h]
0x180012cb3  mov     r9d, ebx
0x180012cb6  mov     r8, r15
0x180012cb9  call    WPP_SF_d
0x180012cbe  mov     eax, ebx
0x180012cc0  add     rsp, 28h
0x180012cc4  pop     r15
0x180012cc6  pop     r12
0x180012cc8  pop     rdi
0x180012cc9  pop     rsi
0x180012cca  pop     rbp
0x180012ccb  pop     rbx
0x180012ccc  retn
```
