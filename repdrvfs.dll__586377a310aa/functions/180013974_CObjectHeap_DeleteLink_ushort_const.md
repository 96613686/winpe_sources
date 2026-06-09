# CObjectHeap::DeleteLink(ushort const *)

- ea: `0x180013974`
- end: `0x180013bbb`
- name: `?DeleteLink@CObjectHeap@@QEAAJPEBG@Z`
- size: `583`
- prototype: `__int64 __fastcall(CObjectHeap *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013bc4`
- `0x180027780`

## callees

- `0x1800012b8`
- `0x18000ca40`
- `0x1800117f0`
- `0x180013880`
- `0x180013974`
- `0x180013f90`

## import_xrefs

- `msvcrt!wcschr` at `0x180013b6d`
- `msvcrt!wcschr` at `0x180013b6d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800139e8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013ace`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800139e8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013ace`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013a50`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013abd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b45`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b96`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013ba2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013a50`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013abd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b45`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b96`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013ba2`
- `wbemcomn!GetMemLogObject` at `0x18001398f`
- `wbemcomn!GetMemLogObject` at `0x180013a02`
- `wbemcomn!GetMemLogObject` at `0x180013a6f`
- `wbemcomn!GetMemLogObject` at `0x180013aeb`
- `wbemcomn!GetMemLogObject` at `0x18001398f`
- `wbemcomn!GetMemLogObject` at `0x180013a02`
- `wbemcomn!GetMemLogObject` at `0x180013a6f`
- `wbemcomn!GetMemLogObject` at `0x180013aeb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001399f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013a12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013a7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013afb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001399f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013a12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013a7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013afb`

## pseudocode

```c
__int64 __fastcall CObjectHeap::DeleteLink(CObjectHeap *this, const unsigned __int16 *a2)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int IndexFileName; // ebx
  wchar_t *v7; // rax
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  unsigned __int16 *v10; // rbx
  CMemoryLog *v11; // rax
  wchar_t *v12; // rax
  unsigned int v13; // edi
  wchar_t *Str; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp+18h]

  if ( !*((_DWORD *)this + 2) )
  {
    MemLogObject = GetMemLogObject();
    IndexFileName = 4317;
    CMemoryLog::Write(MemLogObject, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
    }
    return IndexFileName;
  }
  v7 = (wchar_t *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  Str = v7;
  if ( !v7 )
  {
    v8 = GetMemLogObject();
    IndexFileName = 14;
    CMemoryLog::Write(v8, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return IndexFileName;
  }
  *v7 = 0;
  IndexFileName = CObjectHeap::GetIndexFileName(this, a2, (struct CFileName *)&Str);
  if ( IndexFileName )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, IndexFileName);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, IndexFileName);
    }
    CWin32DefaultArena::WbemMemFree(Str);
    return IndexFileName;
  }
  v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  v15 = v10;
  if ( !v10 )
  {
    v11 = GetMemLogObject();
    IndexFileName = 14;
    CMemoryLog::Write(v11, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    CWin32DefaultArena::WbemMemFree(Str);
    return IndexFileName;
  }
  *v10 = 0;
  StringCchCopyW(v10, 0x173u, a2);
  v12 = wcschr(Str, 0x2Eu);
  if ( v12 )
    StringCchCatW(v10, 0x173u, v12);
  v13 = CBtrIndex::Delete((CObjectHeap *)((char *)this + 32), v10);
  CWin32DefaultArena::WbemMemFree(v10);
  CWin32DefaultArena::WbemMemFree(Str);
  return v13;
}

```

## disassembly

```asm
0x180013974  mov     [rsp+arg_8], rbx
0x180013979  mov     [rsp+arg_18], rsi
0x18001397e  push    rdi
0x18001397f  sub     rsp, 20h
0x180013983  mov     rsi, rdx
0x180013986  mov     rdi, rcx
0x180013989  cmp     dword ptr [rcx+8], 0
0x18001398d  jnz     short loc_1800139E3
0x18001398f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013995  mov     ebx, 10DDh
0x18001399a  mov     edx, ebx
0x18001399c  mov     rcx, rax
0x18001399f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800139a5  lea     rax, WPP_GLOBAL_Control
0x1800139ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139b3  cmp     rcx, rax
0x1800139b6  jz      short loc_1800139DC
0x1800139b8  test    byte ptr [rcx+1Ch], 1
0x1800139bc  jz      short loc_1800139DC
0x1800139be  cmp     byte ptr [rcx+19h], 2
0x1800139c2  jb      short loc_1800139DC
0x1800139c4  mov     edx, 2Dh ; '-'
0x1800139c9  mov     r9d, ebx
0x1800139cc  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800139d3  mov     rcx, [rcx+10h]
0x1800139d7  call    WPP_SF_d
0x1800139dc  mov     eax, ebx
0x1800139de  jmp     loc_180013BAB
0x1800139e3  mov     ecx, 2E6h
0x1800139e8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800139ee  mov     [rsp+28h+Str], rax
0x1800139f3  test    rax, rax
0x1800139f6  jz      short loc_1800139FD
0x1800139f8  xor     ecx, ecx
0x1800139fa  mov     [rax], cx
0x1800139fd  test    rax, rax
0x180013a00  jnz     short loc_180013A59
0x180013a02  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013a08  mov     ebx, 0Eh
0x180013a0d  mov     edx, ebx
0x180013a0f  mov     rcx, rax
0x180013a12  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013a18  lea     rax, WPP_GLOBAL_Control
0x180013a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a26  cmp     rcx, rax
0x180013a29  jz      short loc_180013A4E
0x180013a2b  test    byte ptr [rcx+1Ch], 1
0x180013a2f  jz      short loc_180013A4E
0x180013a31  cmp     byte ptr [rcx+19h], 2
0x180013a35  jb      short loc_180013A4E
0x180013a37  lea     edx, [rbx+20h]
0x180013a3a  mov     r9d, ebx
0x180013a3d  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013a44  mov     rcx, [rcx+10h]
0x180013a48  call    WPP_SF_d
0x180013a4d  nop
0x180013a4e  xor     ecx, ecx
0x180013a50  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013a56  nop
0x180013a57  jmp     short loc_1800139DC
0x180013a59  lea     r8, [rsp+28h+Str]; struct CFileName *
0x180013a5e  mov     rdx, rsi; unsigned __int16 *
0x180013a61  mov     rcx, rdi; this
0x180013a64  call    ?GetIndexFileName@CObjectHeap@@IEAAJPEBGAEAVCFileName@@@Z; CObjectHeap::GetIndexFileName(ushort const *,CFileName &)
0x180013a69  mov     ebx, eax
0x180013a6b  test    eax, eax
0x180013a6d  jz      short loc_180013AC9
0x180013a6f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013a75  mov     edx, ebx
0x180013a77  mov     rcx, rax
0x180013a7a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013a80  lea     rax, WPP_GLOBAL_Control
0x180013a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a8e  cmp     rcx, rax
0x180013a91  jz      short loc_180013AB8
0x180013a93  test    byte ptr [rcx+1Ch], 1
0x180013a97  jz      short loc_180013AB8
0x180013a99  cmp     byte ptr [rcx+19h], 2
0x180013a9d  jb      short loc_180013AB8
0x180013a9f  mov     edx, 2Fh ; '/'
0x180013aa4  mov     r9d, ebx
0x180013aa7  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013aae  mov     rcx, [rcx+10h]
0x180013ab2  call    WPP_SF_d
0x180013ab7  nop
0x180013ab8  mov     rcx, [rsp+28h+Str]
0x180013abd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013ac3  nop
0x180013ac4  jmp     loc_1800139DC
0x180013ac9  mov     ecx, 2E6h
0x180013ace  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013ad4  mov     rbx, rax
0x180013ad7  mov     [rsp+28h+arg_10], rax
0x180013adc  test    rax, rax
0x180013adf  jz      short loc_180013AE6
0x180013ae1  xor     eax, eax
0x180013ae3  mov     [rbx], ax
0x180013ae6  test    rbx, rbx
0x180013ae9  jnz     short loc_180013B51
0x180013aeb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013af1  mov     ebx, 0Eh
0x180013af6  mov     edx, ebx
0x180013af8  mov     rcx, rax
0x180013afb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013b01  lea     rax, WPP_GLOBAL_Control
0x180013b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b0f  cmp     rcx, rax
0x180013b12  jz      short loc_180013B37
0x180013b14  test    byte ptr [rcx+1Ch], 1
0x180013b18  jz      short loc_180013B37
0x180013b1a  cmp     byte ptr [rcx+19h], 2
0x180013b1e  jb      short loc_180013B37
0x180013b20  lea     edx, [rbx+22h]
0x180013b23  mov     r9d, ebx
0x180013b26  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013b2d  mov     rcx, [rcx+10h]
0x180013b31  call    WPP_SF_d
0x180013b36  nop
0x180013b37  xor     ecx, ecx
0x180013b39  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013b3f  nop
0x180013b40  mov     rcx, [rsp+28h+Str]
0x180013b45  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013b4b  nop
0x180013b4c  jmp     loc_1800139DC
0x180013b51  mov     r8, rsi; unsigned __int16 *
0x180013b54  mov     esi, 173h
0x180013b59  mov     edx, esi; unsigned __int64
0x180013b5b  mov     rcx, rbx; unsigned __int16 *
0x180013b5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013b63  mov     edx, 2Eh ; '.'; Ch
0x180013b68  mov     rcx, [rsp+28h+Str]; Str
0x180013b6d  call    cs:__imp_wcschr
0x180013b73  test    rax, rax
0x180013b76  jz      short loc_180013B85
0x180013b78  mov     r8, rax; unsigned __int16 *
0x180013b7b  mov     edx, esi; unsigned __int64
0x180013b7d  mov     rcx, rbx; unsigned __int16 *
0x180013b80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013b85  lea     rcx, [rdi+20h]; this
0x180013b89  mov     rdx, rbx; unsigned __int16 *
0x180013b8c  call    ?Delete@CBtrIndex@@QEAAJPEBG@Z; CBtrIndex::Delete(ushort const *)
0x180013b91  mov     edi, eax
0x180013b93  mov     rcx, rbx
0x180013b96  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013b9c  nop
0x180013b9d  mov     rcx, [rsp+28h+Str]
0x180013ba2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013ba8  nop
0x180013ba9  mov     eax, edi
0x180013bab  mov     rbx, [rsp+28h+arg_8]
0x180013bb0  mov     rsi, [rsp+28h+arg_18]
0x180013bb5  add     rsp, 20h
0x180013bb9  pop     rdi
0x180013bba  retn
```
