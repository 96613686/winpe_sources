# CBTreeFile::GetPage(ulong,MemoryPage * *)

- ea: `0x18000fa20`
- end: `0x18000fb34`
- name: `?GetPage@CBTreeFile@@QEAAKKPEAPEAVMemoryPage@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(CBTreeFile *this, unsigned int, struct MemoryPage **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180037a98`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000e000`
- `0x18000fa20`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000fa9e`
- `wbemcomn!GetMemLogObject` at `0x18000faec`
- `wbemcomn!GetMemLogObject` at `0x18000fa9e`
- `wbemcomn!GetMemLogObject` at `0x18000faec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000faac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000faf7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000faac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000faf7`

## pseudocode

```c
__int64 __fastcall CBTreeFile::GetPage(CBTreeFile *this, unsigned int a2, struct MemoryPage **a3)
{
  CPageFile *v6; // rcx
  unsigned int Page; // edi
  CMemoryLog *v9; // rax
  CMemoryLog *MemLogObject; // rax
  struct MemoryPage *v11; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( a3 )
  {
    v6 = (CPageFile *)*((_QWORD *)this + 1);
    v11 = 0;
    Page = CPageFile::GetPage(v6, a2, (unsigned int)a3, &v11);
    if ( Page )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, Page);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, Page);
      }
      return Page;
    }
    else
    {
      *a3 = v11;
      return 0;
    }
  }
  else
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000fa20  push    rbx
0x18000fa22  push    rbp
0x18000fa23  push    rsi
0x18000fa24  push    rdi
0x18000fa25  sub     rsp, 28h
0x18000fa29  mov     rbx, r8
0x18000fa2c  mov     edi, edx
0x18000fa2e  mov     rsi, rcx
0x18000fa31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa38  lea     rbp, WPP_GLOBAL_Control
0x18000fa3f  cmp     rcx, rbp
0x18000fa42  jz      short loc_18000FA4A
0x18000fa44  test    byte ptr [rcx+1Ch], 1
0x18000fa48  jnz     short loc_18000FA81
0x18000fa4a  test    rbx, rbx
0x18000fa4d  jz      short loc_18000FA9E
0x18000fa4f  mov     rcx, [rsi+8]; this
0x18000fa53  lea     r9, [rsp+48h+arg_10]; struct MemoryPage **
0x18000fa58  mov     edx, edi; unsigned int
0x18000fa5a  mov     [rsp+48h+arg_10], 0
0x18000fa63  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x18000fa68  mov     edi, eax
0x18000fa6a  test    eax, eax
0x18000fa6c  jnz     short loc_18000FAEC
0x18000fa6e  mov     rax, [rsp+48h+arg_10]
0x18000fa73  mov     [rbx], rax
0x18000fa76  xor     eax, eax
0x18000fa78  add     rsp, 28h
0x18000fa7c  pop     rdi
0x18000fa7d  pop     rsi
0x18000fa7e  pop     rbp
0x18000fa7f  pop     rbx
0x18000fa80  retn
0x18000fa81  cmp     byte ptr [rcx+19h], 5
0x18000fa85  jb      short loc_18000FA4A
0x18000fa87  mov     rcx, [rcx+10h]
0x18000fa8b  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000fa92  mov     edx, 12h
0x18000fa97  call    WPP_SF_
0x18000fa9c  jmp     short loc_18000FA4A
0x18000fa9e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000faa4  mov     rcx, rax
0x18000faa7  mov     edx, 57h ; 'W'
0x18000faac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000fab2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fab9  cmp     rcx, rbp
0x18000fabc  jz      short loc_18000FAE5
0x18000fabe  test    byte ptr [rcx+1Ch], 1
0x18000fac2  jz      short loc_18000FAE5
0x18000fac4  cmp     byte ptr [rcx+19h], 2
0x18000fac8  jb      short loc_18000FAE5
0x18000faca  mov     rcx, [rcx+10h]
0x18000face  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000fad5  mov     edx, 13h
0x18000fada  mov     r9d, 57h ; 'W'
0x18000fae0  call    WPP_SF_d
0x18000fae5  mov     eax, 57h ; 'W'
0x18000faea  jmp     short loc_18000FA78
0x18000faec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000faf2  mov     rcx, rax
0x18000faf5  mov     edx, edi
0x18000faf7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000fafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb04  cmp     rcx, rbp
0x18000fb07  jz      short loc_18000FB2D
0x18000fb09  test    byte ptr [rcx+1Ch], 1
0x18000fb0d  jz      short loc_18000FB2D
0x18000fb0f  cmp     byte ptr [rcx+19h], 2
0x18000fb13  jb      short loc_18000FB2D
0x18000fb15  mov     rcx, [rcx+10h]
0x18000fb19  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000fb20  mov     edx, 14h
0x18000fb25  mov     r9d, edi
0x18000fb28  call    WPP_SF_d
0x18000fb2d  mov     eax, edi
0x18000fb2f  jmp     loc_18000FA78
```
