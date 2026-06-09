# CNamespaceHandle::GetObjectByPath(ushort const *,ulong,_GUID const &,void * *)

- ea: `0x1800040c0`
- end: `0x180004302`
- name: `?GetObjectByPath@CNamespaceHandle@@QEAAJPEBGKAEBU_GUID@@PEAPEAX@Z`
- size: `578`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002af0`
- `0x180003bc0`

## callees

- `0x1800012b8`
- `0x1800013c8`
- `0x1800040c0`
- `0x180004310`
- `0x180004f30`
- `0x180006000`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180004137`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180004137`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800041cc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800041d6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004226`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004230`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800042f6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800041cc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800041d6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004226`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004230`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800042f6`
- `wbemcomn!GetMemLogObject` at `0x180004260`
- `wbemcomn!GetMemLogObject` at `0x1800042b1`
- `wbemcomn!GetMemLogObject` at `0x180004260`
- `wbemcomn!GetMemLogObject` at `0x1800042b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000426e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800042bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000426e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800042bc`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetObjectByPath(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        int a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rsi
  int ClassDirect; // ebx
  unsigned __int16 *v14; // rdi
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v18[4]; // [rsp+50h] [rbp-48h] BYREF
  int v19; // [rsp+B0h] [rbp+18h] BYREF

  v19 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a2);
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = v8 + 1;
  v10 = 2;
  if ( v9 > 2 )
    v10 = (unsigned int)v9;
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10, 2u));
  v12 = v11;
  if ( v11 )
  {
    v18[1] = v11;
    LOBYTE(v19) = 0;
    v18[0] = 0;
    ClassDirect = CNamespaceHandle::ComputeKeyFromPath(this, a2, v11, (unsigned int)v10, v18, (bool *)&v19, 0);
    if ( ClassDirect < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, ClassDirect);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)ClassDirect);
      }
      CWin32DefaultArena::WbemMemFree(v12);
    }
    else
    {
      v14 = v18[0];
      v18[2] = v18[0];
      if ( (_BYTE)v19 )
        ClassDirect = CNamespaceHandle::GetClassDirect(this, v18[0], a4, a5, 1, 0, 0, 0, 0);
      else
        ClassDirect = CNamespaceHandle::GetInstanceByKey(this, v18[0], v12, a4, a5);
      CWin32DefaultArena::WbemMemFree(v14);
      CWin32DefaultArena::WbemMemFree(v12);
    }
    return (unsigned int)ClassDirect;
  }
  else
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800040c0  mov     [rsp+arg_0], rbx
0x1800040c5  mov     [rsp+arg_8], rbp
0x1800040ca  mov     [rsp+arg_10], r8d
0x1800040cf  push    rsi
0x1800040d0  push    rdi
0x1800040d1  push    r12
0x1800040d3  push    r14
0x1800040d5  push    r15
0x1800040d7  sub     rsp, 70h
0x1800040db  mov     r14, r9
0x1800040de  mov     rbx, rdx
0x1800040e1  mov     rbp, rcx
0x1800040e4  lea     r12, WPP_GLOBAL_Control
0x1800040eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040f2  cmp     rcx, r12
0x1800040f5  jz      short loc_180004101
0x1800040f7  test    byte ptr [rcx+1Ch], 1
0x1800040fb  jnz     loc_180004239
0x180004101  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004108  mov     rax, r8
0x18000410b  nop     dword ptr [rax+rax+00h]
0x180004110  inc     rax
0x180004113  cmp     word ptr [rbx+rax*2], 0
0x180004118  jnz     short loc_180004110
0x18000411a  inc     rax
0x18000411d  mov     edi, 2
0x180004122  cmp     rax, rdi
0x180004125  cmova   edi, eax
0x180004128  mov     eax, 2
0x18000412d  mul     rdi
0x180004130  cmovb   rax, r8
0x180004134  mov     rcx, rax
0x180004137  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000413d  mov     rsi, rax
0x180004140  test    rax, rax
0x180004143  jz      loc_180004260
0x180004149  mov     [rsp+98h+var_40], rax
0x18000414e  mov     byte ptr [rsp+98h+arg_10], 0
0x180004156  xor     r15d, r15d
0x180004159  mov     [rsp+98h+var_48], r15
0x18000415e  mov     [rsp+98h+var_68], r15; unsigned __int16 **
0x180004163  lea     rax, [rsp+98h+arg_10]
0x18000416b  mov     [rsp+98h+var_70], rax; bool *
0x180004170  lea     rax, [rsp+98h+var_48]
0x180004175  mov     [rsp+98h+var_78], rax; unsigned __int16 **
0x18000417a  mov     r9d, edi; unsigned __int64
0x18000417d  mov     r8, rsi; unsigned __int16 *
0x180004180  mov     rdx, rbx; unsigned __int16 *
0x180004183  mov     rcx, rbp; this
0x180004186  call    ?ComputeKeyFromPath@CNamespaceHandle@@IEAAJPEBGPEAG_KPEAPEAGPEA_N3@Z; CNamespaceHandle::ComputeKeyFromPath(ushort const *,ushort *,unsigned __int64,ushort * *,bool *,ushort * *)
0x18000418b  mov     ebx, eax
0x18000418d  test    eax, eax
0x18000418f  js      loc_1800042B1
0x180004195  mov     rdi, [rsp+98h+var_48]
0x18000419a  mov     [rsp+98h+var_38], rdi
0x18000419f  mov     rdx, rdi; unsigned __int16 *
0x1800041a2  mov     rcx, rbp; this
0x1800041a5  cmp     byte ptr [rsp+98h+arg_10], r15b
0x1800041ad  jnz     short loc_1800041F8
0x1800041af  mov     rax, [rsp+98h+arg_20]
0x1800041b7  mov     [rsp+98h+var_78], rax; void **
0x1800041bc  mov     r9, r14; struct _GUID *
0x1800041bf  mov     r8, rsi; unsigned __int16 *
0x1800041c2  call    ?GetInstanceByKey@CNamespaceHandle@@IEAAJPEBG0AEBU_GUID@@PEAPEAX@Z; CNamespaceHandle::GetInstanceByKey(ushort const *,ushort const *,_GUID const &,void * *)
0x1800041c7  mov     ebx, eax
0x1800041c9  mov     rcx, rdi
0x1800041cc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800041d2  nop
0x1800041d3  mov     rcx, rsi
0x1800041d6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800041dc  nop
0x1800041dd  mov     eax, ebx
0x1800041df  lea     r11, [rsp+98h+var_28]
0x1800041e4  mov     rbx, [r11+30h]
0x1800041e8  mov     rbp, [r11+38h]
0x1800041ec  mov     rsp, r11
0x1800041ef  pop     r15
0x1800041f1  pop     r14
0x1800041f3  pop     r12
0x1800041f5  pop     rdi
0x1800041f6  pop     rsi
0x1800041f7  retn
0x1800041f8  mov     [rsp+98h+var_58], r15d; unsigned int
0x1800041fd  mov     [rsp+98h+var_60], r15; bool *
0x180004202  mov     [rsp+98h+var_68], r15; bool *
0x180004207  mov     [rsp+98h+var_70], r15; __int64 *
0x18000420c  mov     byte ptr [rsp+98h+var_78], 1; bool
0x180004211  mov     r9, [rsp+98h+arg_20]; void **
0x180004219  mov     r8, r14; struct _GUID *
0x18000421c  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x180004221  mov     ebx, eax
0x180004223  mov     rcx, rdi
0x180004226  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000422c  nop
0x18000422d  mov     rcx, rsi
0x180004230  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180004236  nop
0x180004237  jmp     short loc_1800041DD
0x180004239  cmp     byte ptr [rcx+19h], 5
0x18000423d  jb      loc_180004101
0x180004243  mov     edx, 84h
0x180004248  mov     r9, rbx
0x18000424b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180004252  mov     rcx, [rcx+10h]
0x180004256  call    WPP_SF_S
0x18000425b  jmp     loc_180004101
0x180004260  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004266  mov     edx, 80041006h
0x18000426b  mov     rcx, rax
0x18000426e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004274  mov     rcx, cs:WPP_GLOBAL_Control
0x18000427b  cmp     rcx, r12
0x18000427e  jz      short loc_1800042A7
0x180004280  test    byte ptr [rcx+1Ch], 1
0x180004284  jz      short loc_1800042A7
0x180004286  cmp     byte ptr [rcx+19h], 2
0x18000428a  jb      short loc_1800042A7
0x18000428c  mov     edx, 85h
0x180004291  mov     r9d, 80041006h
0x180004297  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000429e  mov     rcx, [rcx+10h]
0x1800042a2  call    WPP_SF_d
0x1800042a7  mov     eax, 80041006h
0x1800042ac  jmp     loc_1800041DF
0x1800042b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800042b7  mov     edx, ebx
0x1800042b9  mov     rcx, rax
0x1800042bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800042c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042c9  cmp     rcx, r12
0x1800042cc  jz      short loc_1800042F3
0x1800042ce  test    byte ptr [rcx+1Ch], 1
0x1800042d2  jz      short loc_1800042F3
0x1800042d4  cmp     byte ptr [rcx+19h], 2
0x1800042d8  jb      short loc_1800042F3
0x1800042da  mov     edx, 86h
0x1800042df  mov     r9d, ebx
0x1800042e2  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800042e9  mov     rcx, [rcx+10h]
0x1800042ed  call    WPP_SF_d
0x1800042f2  nop
0x1800042f3  mov     rcx, rsi
0x1800042f6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800042fc  nop
0x1800042fd  jmp     loc_1800041DD
```
