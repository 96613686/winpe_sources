# CBTreeFile::NewPage(void * *)

- ea: `0x180037da8`
- end: `0x180037f4e`
- name: `?NewPage@CBTreeFile@@QEAAKPEAPEAX@Z`
- size: `422`
- prototype: `unsigned int __fastcall(CBTreeFile *__hidden this, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010fe4`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000fcf0`
- `0x180010fa0`
- `0x1800259c0`
- `0x180037da8`
- `0x1800443df`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180037dfd`
- `wbemcomn!GetMemLogObject` at `0x180037e5b`
- `wbemcomn!GetMemLogObject` at `0x180037eb6`
- `wbemcomn!GetMemLogObject` at `0x180037dfd`
- `wbemcomn!GetMemLogObject` at `0x180037e5b`
- `wbemcomn!GetMemLogObject` at `0x180037eb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037e0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037e69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037ec1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037e0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037e69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037ec1`

## pseudocode

```c
__int64 __fastcall CBTreeFile::NewPage(CBTreeFile *this, void **a2)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v5; // ebx
  CVarObjHeap *v6; // rcx
  __int64 v7; // rdx
  unsigned int v9; // edx
  _DWORD *v10; // rdi
  CMemoryLog *v11; // rax
  CPageFile *v12; // rcx
  CMemoryLog *v13; // rax
  unsigned int v14; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    v5 = 87;
    CMemoryLog::Write(MemLogObject, 87);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 24;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v5);
    return v5;
  }
  *a2 = 0;
  v10 = _BtrMemAlloc(0x2000u);
  if ( !v10 )
  {
    v11 = GetMemLogObject();
    v5 = 8;
    CMemoryLog::Write(v11, 8);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 25;
    goto LABEL_10;
  }
  v12 = (CPageFile *)*((_QWORD *)this + 1);
  v14 = 0;
  v5 = CPageFile::NewPage(v12, v9, 1u, &v14);
  if ( v5 )
  {
    _BtrMemFree(v10);
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v5);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 26;
    goto LABEL_10;
  }
  memset_0(v10, 0, 0x2000u);
  v10[1] = v14;
  *a2 = v10;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180037da8  mov     [rsp+arg_0], rbx
0x180037dad  mov     [rsp+arg_10], rsi
0x180037db2  push    rdi
0x180037db3  push    r14
0x180037db5  push    r15
0x180037db7  sub     rsp, 20h
0x180037dbb  mov     rsi, rdx
0x180037dbe  mov     rbx, rcx
0x180037dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037dc8  lea     r15, WPP_GLOBAL_Control
0x180037dcf  lea     r14, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180037dd6  cmp     rcx, r15
0x180037dd9  jz      short loc_180037DF8
0x180037ddb  test    byte ptr [rcx+1Ch], 1
0x180037ddf  jz      short loc_180037DF8
0x180037de1  cmp     byte ptr [rcx+19h], 5
0x180037de5  jb      short loc_180037DF8
0x180037de7  mov     rcx, [rcx+10h]
0x180037deb  mov     edx, 17h
0x180037df0  mov     r8, r14
0x180037df3  call    WPP_SF_
0x180037df8  test    rsi, rsi
0x180037dfb  jnz     short loc_180037E42
0x180037dfd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037e03  lea     ebx, [rsi+57h]
0x180037e06  mov     rcx, rax
0x180037e09  mov     edx, ebx
0x180037e0b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e18  cmp     rcx, r15
0x180037e1b  jz      short loc_180037E3B
0x180037e1d  test    byte ptr [rcx+1Ch], 1
0x180037e21  jz      short loc_180037E3B
0x180037e23  cmp     byte ptr [rcx+19h], 2
0x180037e27  jb      short loc_180037E3B
0x180037e29  lea     edx, [rsi+18h]
0x180037e2c  mov     rcx, [rcx+10h]
0x180037e30  mov     r9d, ebx
0x180037e33  mov     r8, r14
0x180037e36  call    WPP_SF_d
0x180037e3b  mov     eax, ebx
0x180037e3d  jmp     loc_180037F3A
0x180037e42  mov     ecx, 2000h; unsigned __int64
0x180037e47  mov     qword ptr [rsi], 0
0x180037e4e  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180037e53  mov     rdi, rax
0x180037e56  test    rax, rax
0x180037e59  jnz     short loc_180037E8C
0x180037e5b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037e61  lea     ebx, [rdi+8]
0x180037e64  mov     rcx, rax
0x180037e67  mov     edx, ebx
0x180037e69  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e76  cmp     rcx, r15
0x180037e79  jz      short loc_180037E3B
0x180037e7b  test    byte ptr [rcx+1Ch], 1
0x180037e7f  jz      short loc_180037E3B
0x180037e81  cmp     byte ptr [rcx+19h], 2
0x180037e85  jb      short loc_180037E3B
0x180037e87  lea     edx, [rdi+19h]
0x180037e8a  jmp     short loc_180037E2C
0x180037e8c  mov     rcx, [rbx+8]; this
0x180037e90  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x180037e95  mov     r8d, 1; unsigned int
0x180037e9b  mov     [rsp+38h+arg_8], 0
0x180037ea3  call    ?NewPage@CPageFile@@QEAAKKKPEAK@Z; CPageFile::NewPage(ulong,ulong,ulong *)
0x180037ea8  mov     ebx, eax
0x180037eaa  mov     rcx, rdi; void *
0x180037ead  test    eax, eax
0x180037eaf  jz      short loc_180037EF5
0x180037eb1  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180037eb6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037ebc  mov     rcx, rax
0x180037ebf  mov     edx, ebx
0x180037ec1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ece  cmp     rcx, r15
0x180037ed1  jz      loc_180037E3B
0x180037ed7  test    byte ptr [rcx+1Ch], 1
0x180037edb  jz      loc_180037E3B
0x180037ee1  cmp     byte ptr [rcx+19h], 2
0x180037ee5  jb      loc_180037E3B
0x180037eeb  mov     edx, 1Ah
0x180037ef0  jmp     loc_180037E2C
0x180037ef5  xor     edx, edx; Val
0x180037ef7  mov     r8d, 2000h; Size
0x180037efd  call    memset_0
0x180037f02  mov     eax, [rsp+38h+arg_8]
0x180037f06  mov     [rdi+4], eax
0x180037f09  mov     [rsi], rdi
0x180037f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f13  cmp     rcx, r15
0x180037f16  jz      short loc_180037F38
0x180037f18  test    byte ptr [rcx+1Ch], 1
0x180037f1c  jz      short loc_180037F38
0x180037f1e  cmp     byte ptr [rcx+19h], 2
0x180037f22  jb      short loc_180037F38
0x180037f24  mov     rcx, [rcx+10h]
0x180037f28  mov     edx, 1Bh
0x180037f2d  xor     r9d, r9d
0x180037f30  mov     r8, r14
0x180037f33  call    WPP_SF_d
0x180037f38  xor     eax, eax
0x180037f3a  mov     rbx, [rsp+38h+arg_0]
0x180037f3f  mov     rsi, [rsp+38h+arg_10]
0x180037f44  add     rsp, 20h
0x180037f48  pop     r15
0x180037f4a  pop     r14
0x180037f4c  pop     rdi
0x180037f4d  retn
```
