# CObjectHeap::DeleteNode(ushort const *)

- ea: `0x180030a90`
- end: `0x180030d57`
- name: `?DeleteNode@CObjectHeap@@QEAAJPEBG@Z`
- size: `711`
- prototype: `__int64 __fastcall(CPageFile **this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800253d4`
- `0x180027814`

## callees

- `0x1800012b8`
- `0x180009920`
- `0x18000bef0`
- `0x1800117f0`
- `0x180013370`
- `0x1800136b8`
- `0x180013880`
- `0x180023528`
- `0x180023bf0`
- `0x180030a90`

## import_xrefs

- `msvcrt!wcschr` at `0x180030c84`
- `msvcrt!wcschr` at `0x180030c95`
- `msvcrt!wcschr` at `0x180030c84`
- `msvcrt!wcschr` at `0x180030c95`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b12`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b7d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b88`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030bfb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030c06`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030d30`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030d3b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b12`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b7d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030b88`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030bfb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030c06`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030d30`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180030d3b`
- `wbemcomn!GetMemLogObject` at `0x180030ac4`
- `wbemcomn!GetMemLogObject` at `0x180030b31`
- `wbemcomn!GetMemLogObject` at `0x180030baf`
- `wbemcomn!GetMemLogObject` at `0x180030ce4`
- `wbemcomn!GetMemLogObject` at `0x180030ac4`
- `wbemcomn!GetMemLogObject` at `0x180030b31`
- `wbemcomn!GetMemLogObject` at `0x180030baf`
- `wbemcomn!GetMemLogObject` at `0x180030ce4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030ad4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030b3f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030bba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030cef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030ad4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030b3f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030bba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030cef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CObjectHeap::DeleteNode(CPageFile **this, const unsigned __int16 *a2)
{
  CMemoryLog *v4; // rax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rdi
  CMemoryLog *v7; // rax
  unsigned int v8; // eax
  CMemoryLog *MemLogObject; // rax
  unsigned int v10; // esi
  CObjectHeap *v11; // rcx
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  CMemoryLog *v14; // rax
  unsigned int v16; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-18h] BYREF
  void *v18; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+38h] BYREF

  v18 = 0;
  CFileName::CFileName((CFileName *)&v17);
  if ( v17 )
  {
    CFileName::CFileName((CFileName *)&v19);
    v6 = v19;
    if ( v19 )
    {
      v8 = CObjectHeap::IndexEnumerationBegin((CObjectHeap *)this, a2, &v18);
      v5 = 0;
      if ( v8 != 18 )
        v5 = v8;
      if ( v5 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v5);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, v5);
        }
        CWin32DefaultArena::WbemMemFree(v6);
        CWin32DefaultArena::WbemMemFree(v17);
      }
      else
      {
        while ( 1 )
        {
          v10 = CObjectHeap::IndexEnumerationNext((CObjectHeap *)this, v18, (struct CFileName *)&v17, 1);
          if ( v10 )
            break;
          StringCchCopyW(v6, 0x173u, v17);
          v10 = CBtrIndex::Delete((CBtrIndex *)(this + 4), v6);
          if ( v10 )
            break;
          v21 = 0;
          v20 = 0;
          v16 = 0;
          if ( CObjectHeap::ParseInfoFromIndexFile(v11, v6, &v21, &v20, &v16) != 87 )
          {
            v12 = wcschr(v6 + 1, 0x5Cu);
            if ( !v12 || (v13 = wcschr(v12 + 1, 0x5Cu)) == 0 || v13[1] != 73 || v13[2] != 95 )
            {
              v10 = CVarObjHeap::DeleteBuffer(this + 2, v21, v20);
              if ( v10 )
                break;
            }
          }
        }
        CObjectHeap::IndexEnumerationEnd((CObjectHeap *)this, v18);
        v5 = 0;
        if ( v10 != 18 )
          v5 = v10;
        if ( v5 )
        {
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, v5);
        }
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, v5);
        }
        CWin32DefaultArena::WbemMemFree(v6);
        CWin32DefaultArena::WbemMemFree(v17);
      }
    }
    else
    {
      v7 = GetMemLogObject();
      v5 = 14;
      CMemoryLog::Write(v7, 14);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
      }
      CWin32DefaultArena::WbemMemFree(0);
      CWin32DefaultArena::WbemMemFree(v17);
    }
  }
  else
  {
    v4 = GetMemLogObject();
    v5 = 14;
    CMemoryLog::Write(v4, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  return v5;
}

```

## disassembly

```asm
0x180030a90  mov     [rsp-18h+arg_0], rbx
0x180030a95  mov     [rsp-18h+arg_8], rsi
0x180030a9a  push    rbp
0x180030a9b  push    rdi
0x180030a9c  push    r15
0x180030a9e  mov     rbp, rsp
0x180030aa1  sub     rsp, 50h
0x180030aa5  mov     rbx, rdx
0x180030aa8  mov     r15, rcx
0x180030aab  mov     [rbp+var_10], 0
0x180030ab3  lea     rcx, [rbp+var_18]; this
0x180030ab7  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180030abc  nop
0x180030abd  cmp     [rbp+var_18], 0
0x180030ac2  jnz     short loc_180030B1E
0x180030ac4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030aca  mov     ebx, 0Eh
0x180030acf  mov     edx, ebx
0x180030ad1  mov     rcx, rax
0x180030ad4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030ada  lea     rax, WPP_GLOBAL_Control
0x180030ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ae8  cmp     rcx, rax
0x180030aeb  jz      short loc_180030B10
0x180030aed  test    byte ptr [rcx+1Ch], 1
0x180030af1  jz      short loc_180030B10
0x180030af3  cmp     byte ptr [rcx+19h], 2
0x180030af7  jb      short loc_180030B10
0x180030af9  lea     edx, [rbx+2Ah]
0x180030afc  mov     r9d, ebx
0x180030aff  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030b06  mov     rcx, [rcx+10h]
0x180030b0a  call    WPP_SF_d
0x180030b0f  nop
0x180030b10  xor     ecx, ecx
0x180030b12  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030b18  nop
0x180030b19  jmp     loc_180030D42
0x180030b1e  lea     rcx, [rbp+var_8]; this
0x180030b22  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180030b27  nop
0x180030b28  mov     rdi, [rbp+var_8]
0x180030b2c  test    rdi, rdi
0x180030b2f  jnz     short loc_180030B94
0x180030b31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030b37  lea     ebx, [rdi+0Eh]
0x180030b3a  mov     edx, ebx
0x180030b3c  mov     rcx, rax
0x180030b3f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030b45  lea     rax, WPP_GLOBAL_Control
0x180030b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b53  cmp     rcx, rax
0x180030b56  jz      short loc_180030B7B
0x180030b58  test    byte ptr [rcx+1Ch], 1
0x180030b5c  jz      short loc_180030B7B
0x180030b5e  cmp     byte ptr [rcx+19h], 2
0x180030b62  jb      short loc_180030B7B
0x180030b64  lea     edx, [rdi+39h]
0x180030b67  mov     r9d, ebx
0x180030b6a  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030b71  mov     rcx, [rcx+10h]
0x180030b75  call    WPP_SF_d
0x180030b7a  nop
0x180030b7b  xor     ecx, ecx
0x180030b7d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030b83  nop
0x180030b84  mov     rcx, [rbp+var_18]
0x180030b88  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030b8e  nop
0x180030b8f  jmp     loc_180030D42
0x180030b94  lea     r8, [rbp+var_10]; void **
0x180030b98  mov     rdx, rbx; unsigned __int16 *
0x180030b9b  mov     rcx, r15; this
0x180030b9e  call    ?IndexEnumerationBegin@CObjectHeap@@QEAAJPEBGPEAPEAX@Z; CObjectHeap::IndexEnumerationBegin(ushort const *,void * *)
0x180030ba3  xor     ebx, ebx
0x180030ba5  cmp     eax, 12h
0x180030ba8  cmovnz  ebx, eax
0x180030bab  test    ebx, ebx
0x180030bad  jz      short loc_180030C12
0x180030baf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030bb5  mov     edx, ebx
0x180030bb7  mov     rcx, rax
0x180030bba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030bc0  lea     rax, WPP_GLOBAL_Control
0x180030bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bce  cmp     rcx, rax
0x180030bd1  jz      short loc_180030BF8
0x180030bd3  test    byte ptr [rcx+1Ch], 1
0x180030bd7  jz      short loc_180030BF8
0x180030bd9  cmp     byte ptr [rcx+19h], 2
0x180030bdd  jb      short loc_180030BF8
0x180030bdf  mov     edx, 3Ah ; ':'
0x180030be4  mov     r9d, ebx
0x180030be7  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030bee  mov     rcx, [rcx+10h]
0x180030bf2  call    WPP_SF_d
0x180030bf7  nop
0x180030bf8  mov     rcx, rdi
0x180030bfb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030c01  nop
0x180030c02  mov     rcx, [rbp+var_18]
0x180030c06  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030c0c  nop
0x180030c0d  jmp     loc_180030D42
0x180030c12  mov     ebx, 5Ch ; '\'
0x180030c17  mov     r9b, 1; bool
0x180030c1a  lea     r8, [rbp+var_18]; struct CFileName *
0x180030c1e  mov     rdx, [rbp+var_10]; void *
0x180030c22  mov     rcx, r15; this
0x180030c25  call    ?IndexEnumerationNext@CObjectHeap@@QEAAJPEAXAEAVCFileName@@_N@Z; CObjectHeap::IndexEnumerationNext(void *,CFileName &,bool)
0x180030c2a  mov     esi, eax
0x180030c2c  test    eax, eax
0x180030c2e  jnz     loc_180030CCC
0x180030c34  mov     r8, [rbp+var_18]; unsigned __int16 *
0x180030c38  mov     edx, 173h; unsigned __int64
0x180030c3d  mov     rcx, rdi; unsigned __int16 *
0x180030c40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030c45  lea     rcx, [r15+20h]; this
0x180030c49  mov     rdx, rdi; unsigned __int16 *
0x180030c4c  call    ?Delete@CBtrIndex@@QEAAJPEBG@Z; CBtrIndex::Delete(ushort const *)
0x180030c51  mov     esi, eax
0x180030c53  test    eax, eax
0x180030c55  jnz     short loc_180030CCC
0x180030c57  mov     [rbp+arg_18], eax
0x180030c5a  mov     [rbp+arg_10], eax
0x180030c5d  mov     [rbp+var_20], eax
0x180030c60  lea     rax, [rbp+var_20]
0x180030c64  mov     [rsp+50h+var_30], rax; unsigned int *
0x180030c69  lea     r9, [rbp+arg_10]; unsigned int *
0x180030c6d  lea     r8, [rbp+arg_18]; unsigned int *
0x180030c71  mov     rdx, rdi; unsigned __int16 *
0x180030c74  call    ?ParseInfoFromIndexFile@CObjectHeap@@IEAAJPEBGPEAK11@Z; CObjectHeap::ParseInfoFromIndexFile(ushort const *,ulong *,ulong *,ulong *)
0x180030c79  cmp     eax, 57h ; 'W'
0x180030c7c  jz      short loc_180030C17
0x180030c7e  mov     edx, ebx; Ch
0x180030c80  lea     rcx, [rdi+2]; Str
0x180030c84  call    cs:__imp_wcschr
0x180030c8a  test    rax, rax
0x180030c8d  jz      short loc_180030CB2
0x180030c8f  mov     edx, ebx; Ch
0x180030c91  lea     rcx, [rax+2]; Str
0x180030c95  call    cs:__imp_wcschr
0x180030c9b  test    rax, rax
0x180030c9e  jz      short loc_180030CB2
0x180030ca0  cmp     word ptr [rax+2], 49h ; 'I'
0x180030ca5  jnz     short loc_180030CB2
0x180030ca7  cmp     word ptr [rax+4], 5Fh ; '_'
0x180030cac  jz      loc_180030C17
0x180030cb2  lea     rcx, [r15+10h]; this
0x180030cb6  mov     r8d, [rbp+arg_10]; unsigned int
0x180030cba  mov     edx, [rbp+arg_18]; unsigned int
0x180030cbd  call    ?DeleteBuffer@CVarObjHeap@@QEAAKKK@Z; CVarObjHeap::DeleteBuffer(ulong,ulong)
0x180030cc2  mov     esi, eax
0x180030cc4  test    eax, eax
0x180030cc6  jz      loc_180030C17
0x180030ccc  mov     rdx, [rbp+var_10]; void *
0x180030cd0  mov     rcx, r15; this
0x180030cd3  call    ?IndexEnumerationEnd@CObjectHeap@@QEAAJPEAX@Z; CObjectHeap::IndexEnumerationEnd(void *)
0x180030cd8  xor     ebx, ebx
0x180030cda  cmp     esi, 12h
0x180030cdd  cmovnz  ebx, esi
0x180030ce0  test    ebx, ebx
0x180030ce2  jz      short loc_180030CF5
0x180030ce4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030cea  mov     edx, ebx
0x180030cec  mov     rcx, rax
0x180030cef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030cf5  lea     rax, WPP_GLOBAL_Control
0x180030cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d03  cmp     rcx, rax
0x180030d06  jz      short loc_180030D2D
0x180030d08  test    byte ptr [rcx+1Ch], 1
0x180030d0c  jz      short loc_180030D2D
0x180030d0e  cmp     byte ptr [rcx+19h], 2
0x180030d12  jb      short loc_180030D2D
0x180030d14  mov     edx, 3Bh ; ';'
0x180030d19  mov     r9d, ebx
0x180030d1c  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030d23  mov     rcx, [rcx+10h]
0x180030d27  call    WPP_SF_d
0x180030d2c  nop
0x180030d2d  mov     rcx, rdi
0x180030d30  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030d36  nop
0x180030d37  mov     rcx, [rbp+var_18]
0x180030d3b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180030d41  nop
0x180030d42  mov     eax, ebx
0x180030d44  mov     rbx, [rsp+50h+arg_0]
0x180030d49  mov     rsi, [rsp+50h+arg_8]
0x180030d4e  add     rsp, 50h
0x180030d52  pop     r15
0x180030d54  pop     rdi
0x180030d55  pop     rbp
0x180030d56  retn
```
