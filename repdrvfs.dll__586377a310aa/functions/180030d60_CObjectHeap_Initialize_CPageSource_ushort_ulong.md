# CObjectHeap::Initialize(CPageSource *,ushort *,ulong)

- ea: `0x180030d60`
- end: `0x180030ea9`
- name: `?Initialize@CObjectHeap@@QEAAJPEAVCPageSource@@PEAGK@Z`
- size: `329`
- prototype: `int(CObjectHeap *__hidden this, struct CPageSource *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003dbf8`

## callees

- `0x1800012b8`
- `0x18002bedc`
- `0x180030d60`
- `0x18003e3f0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180030dc1`
- `wbemcomn!GetMemLogObject` at `0x180030e27`
- `wbemcomn!GetMemLogObject` at `0x180030dc1`
- `wbemcomn!GetMemLogObject` at `0x180030e27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030dcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030e32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030dcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180030e32`

## pseudocode

```c
__int64 __fastcall CObjectHeap::Initialize(
        CObjectHeap *this,
        struct CPageSource *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v12; // rcx
  __int64 v13; // rdx
  CMemoryLog *v15; // rax

  if ( !*((_DWORD *)this + 2) )
  {
    v10 = CVarObjHeap::Initialize((CObjectHeap *)((char *)this + 16), a2);
    if ( v10 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v10);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v10;
      }
      v13 = 11;
    }
    else
    {
      v10 = CBtrIndex::Initialize((CObjectHeap *)((char *)this + 32), a4, a3, a2);
      if ( !v10 )
      {
        *((_DWORD *)this + 2) = 1;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 0;
        }
        v9 = 13;
        goto LABEL_22;
      }
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, v10);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v10;
      }
      v13 = 12;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, v10);
    return v10;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 0;
  }
  v9 = 10;
LABEL_22:
  WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180030d60  push    rbx
0x180030d62  push    rbp
0x180030d63  push    rsi
0x180030d64  push    rdi
0x180030d65  push    r14
0x180030d67  sub     rsp, 20h
0x180030d6b  cmp     dword ptr [rcx+8], 0
0x180030d6f  mov     ebp, r9d
0x180030d72  mov     r14, r8
0x180030d75  mov     rsi, rdx
0x180030d78  mov     rdi, rcx
0x180030d7b  jz      short loc_180030DB2
0x180030d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d84  lea     rax, WPP_GLOBAL_Control
0x180030d8b  cmp     rcx, rax
0x180030d8e  jz      loc_180030E9C
0x180030d94  test    byte ptr [rcx+1Ch], 1
0x180030d98  jz      loc_180030E9C
0x180030d9e  cmp     byte ptr [rcx+19h], 2
0x180030da2  jb      loc_180030E9C
0x180030da8  mov     edx, 0Ah; struct CPageSource *
0x180030dad  jmp     loc_180030E89
0x180030db2  add     rcx, 10h; this
0x180030db6  call    ?Initialize@CVarObjHeap@@QEAAKPEAVCPageSource@@@Z; CVarObjHeap::Initialize(CPageSource *)
0x180030dbb  mov     ebx, eax
0x180030dbd  test    eax, eax
0x180030dbf  jz      short loc_180030E10
0x180030dc1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030dc7  mov     rcx, rax
0x180030dca  mov     edx, ebx
0x180030dcc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dd9  lea     rax, WPP_GLOBAL_Control
0x180030de0  cmp     rcx, rax
0x180030de3  jz      short loc_180030E09
0x180030de5  test    byte ptr [rcx+1Ch], 1
0x180030de9  jz      short loc_180030E09
0x180030deb  cmp     byte ptr [rcx+19h], 2
0x180030def  jb      short loc_180030E09
0x180030df1  mov     edx, 0Bh
0x180030df6  mov     rcx, [rcx+10h]
0x180030dfa  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030e01  mov     r9d, ebx
0x180030e04  call    WPP_SF_d
0x180030e09  mov     eax, ebx
0x180030e0b  jmp     loc_180030E9E
0x180030e10  lea     rcx, [rdi+20h]; this
0x180030e14  mov     r9, rsi; struct CPageSource *
0x180030e17  mov     r8, r14; unsigned __int16 *
0x180030e1a  mov     edx, ebp; unsigned int
0x180030e1c  call    ?Initialize@CBtrIndex@@QEAAJKPEBGPEAVCPageSource@@@Z; CBtrIndex::Initialize(ulong,ushort const *,CPageSource *)
0x180030e21  mov     ebx, eax
0x180030e23  test    eax, eax
0x180030e25  jz      short loc_180030E5E
0x180030e27  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180030e2d  mov     rcx, rax
0x180030e30  mov     edx, ebx
0x180030e32  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180030e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e3f  lea     rax, WPP_GLOBAL_Control
0x180030e46  cmp     rcx, rax
0x180030e49  jz      short loc_180030E09
0x180030e4b  test    byte ptr [rcx+1Ch], 1
0x180030e4f  jz      short loc_180030E09
0x180030e51  cmp     byte ptr [rcx+19h], 2
0x180030e55  jb      short loc_180030E09
0x180030e57  mov     edx, 0Ch
0x180030e5c  jmp     short loc_180030DF6
0x180030e5e  mov     dword ptr [rdi+8], 1
0x180030e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e6c  lea     rax, WPP_GLOBAL_Control
0x180030e73  cmp     rcx, rax
0x180030e76  jz      short loc_180030E9C
0x180030e78  test    byte ptr [rcx+1Ch], 1
0x180030e7c  jz      short loc_180030E9C
0x180030e7e  cmp     byte ptr [rcx+19h], 2
0x180030e82  jb      short loc_180030E9C
0x180030e84  mov     edx, 0Dh
0x180030e89  mov     rcx, [rcx+10h]
0x180030e8d  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180030e94  xor     r9d, r9d
0x180030e97  call    WPP_SF_d
0x180030e9c  xor     eax, eax
0x180030e9e  add     rsp, 20h
0x180030ea2  pop     r14
0x180030ea4  pop     rdi
0x180030ea5  pop     rsi
0x180030ea6  pop     rbp
0x180030ea7  pop     rbx
0x180030ea8  retn
```
