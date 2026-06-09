# CNamespaceHandle::ConstructReferenceDirFromFilePath(ushort const *,CFileName &)

- ea: `0x180032874`
- end: `0x1800329ee`
- name: `?ConstructReferenceDirFromFilePath@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033b84`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x180032874`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18003290a`
- `msvcrt!wcsrchr` at `0x18003290a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800328f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003296e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800329d5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800328f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003296e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800329d5`
- `wbemcomn!GetMemLogObject` at `0x1800328a0`
- `wbemcomn!GetMemLogObject` at `0x180032918`
- `wbemcomn!GetMemLogObject` at `0x1800328a0`
- `wbemcomn!GetMemLogObject` at `0x180032918`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800328ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032928`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800328ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032928`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ConstructReferenceDirFromFilePath(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  CMemoryLog *v5; // rax
  wchar_t *v7; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v9; // r10
  unsigned __int16 *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = (unsigned __int16 *)this;
  CFileName::CFileName((CFileName *)&v10);
  if ( v10 )
  {
    v7 = wcsrchr(a2, 0x5Cu);
    if ( v7 )
    {
      StringCchCopyW(v10, 0x173u, v7 + 3);
      StringCchCopyW(*a3, 0x173u, a2);
      (*a3)[(v9 - (__int64)a2 + 2) >> 1] = 0;
      StringCchCatW(*a3, 0x173u, L"IR_");
      StringCchCatW(*a3, 0x173u, v10);
      CWin32DefaultArena::WbemMemFree(v10);
      return 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217407);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          329,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749889LL);
      }
      CWin32DefaultArena::WbemMemFree(v10);
      return 2147749889LL;
    }
  }
  else
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180032874  mov     rax, rsp
0x180032877  mov     [rax+10h], rbp
0x18003287b  mov     [rax+18h], rsi
0x18003287f  mov     [rax+8], rcx
0x180032883  push    rdi
0x180032884  sub     rsp, 20h
0x180032888  mov     rsi, r8
0x18003288b  mov     rdi, rdx
0x18003288e  lea     rcx, [rax+8]; this
0x180032892  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180032897  nop
0x180032898  cmp     [rsp+28h+arg_0], 0
0x18003289e  jnz     short loc_180032902
0x1800328a0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800328a6  mov     edx, 80041006h
0x1800328ab  mov     rcx, rax
0x1800328ae  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800328b4  lea     rax, WPP_GLOBAL_Control
0x1800328bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328c2  cmp     rcx, rax
0x1800328c5  jz      short loc_1800328EF
0x1800328c7  test    byte ptr [rcx+1Ch], 1
0x1800328cb  jz      short loc_1800328EF
0x1800328cd  cmp     byte ptr [rcx+19h], 2
0x1800328d1  jb      short loc_1800328EF
0x1800328d3  mov     edx, 148h
0x1800328d8  mov     r9d, 80041006h
0x1800328de  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800328e5  mov     rcx, [rcx+10h]
0x1800328e9  call    WPP_SF_d
0x1800328ee  nop
0x1800328ef  xor     ecx, ecx
0x1800328f1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800328f7  nop
0x1800328f8  mov     eax, 80041006h
0x1800328fd  jmp     loc_1800329DE
0x180032902  mov     edx, 5Ch ; '\'; Ch
0x180032907  mov     rcx, rdi; Str
0x18003290a  call    cs:__imp_wcsrchr
0x180032910  mov     r10, rax
0x180032913  test    rax, rax
0x180032916  jnz     short loc_180032979
0x180032918  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003291e  mov     edi, 80041001h
0x180032923  mov     edx, edi
0x180032925  mov     rcx, rax
0x180032928  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003292e  lea     rax, WPP_GLOBAL_Control
0x180032935  mov     rcx, cs:WPP_GLOBAL_Control
0x18003293c  cmp     rcx, rax
0x18003293f  jz      short loc_180032969
0x180032941  test    byte ptr [rcx+1Ch], 1
0x180032945  jz      short loc_180032969
0x180032947  cmp     byte ptr [rcx+19h], 2
0x18003294b  jb      short loc_180032969
0x18003294d  mov     edx, 149h
0x180032952  mov     r9d, 80041001h
0x180032958  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003295f  mov     rcx, [rcx+10h]
0x180032963  call    WPP_SF_d
0x180032968  nop
0x180032969  mov     rcx, [rsp+28h+arg_0]
0x18003296e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180032974  nop
0x180032975  mov     eax, edi
0x180032977  jmp     short loc_1800329DE
0x180032979  lea     r8, [rax+6]; unsigned __int16 *
0x18003297d  mov     ebp, 173h
0x180032982  mov     edx, ebp; unsigned __int64
0x180032984  mov     rcx, [rsp+28h+arg_0]; unsigned __int16 *
0x180032989  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003298e  mov     r8, rdi; unsigned __int16 *
0x180032991  mov     edx, ebp; unsigned __int64
0x180032993  mov     rcx, [rsi]; unsigned __int16 *
0x180032996  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003299b  sub     r10, rdi
0x18003299e  add     r10, 2
0x1800329a2  sar     r10, 1
0x1800329a5  mov     r8, [rsi]
0x1800329a8  xor     eax, eax
0x1800329aa  mov     [r8+r10*2], ax
0x1800329af  lea     r8, aIr; "IR_"
0x1800329b6  mov     edx, ebp; unsigned __int64
0x1800329b8  mov     rcx, [rsi]; unsigned __int16 *
0x1800329bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800329c0  mov     r8, [rsp+28h+arg_0]; unsigned __int16 *
0x1800329c5  mov     edx, ebp; unsigned __int64
0x1800329c7  mov     rcx, [rsi]; unsigned __int16 *
0x1800329ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800329cf  nop
0x1800329d0  mov     rcx, [rsp+28h+arg_0]
0x1800329d5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800329db  nop
0x1800329dc  xor     eax, eax
0x1800329de  mov     rbp, [rsp+28h+arg_8]
0x1800329e3  mov     rsi, [rsp+28h+arg_10]
0x1800329e8  add     rsp, 20h
0x1800329ec  pop     rdi
0x1800329ed  retn
```
