# CRepository::Backup(ushort const *,long)

- ea: `0x180038f00`
- end: `0x180039054`
- name: `?Backup@CRepository@@UEAAJPEBGJ@Z`
- size: `340`
- prototype: `__int64 __fastcall(CRepository *this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180038f00`
- `0x18003f940`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180038f6d`
- `wbemcomn!GetMemLogObject` at `0x180038fcf`
- `wbemcomn!GetMemLogObject` at `0x180038fff`
- `wbemcomn!GetMemLogObject` at `0x180038f6d`
- `wbemcomn!GetMemLogObject` at `0x180038fcf`
- `wbemcomn!GetMemLogObject` at `0x180038fff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038f78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038fda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003900f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038f78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038fda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003900f`

## pseudocode

```c
__int64 __fastcall CRepository::Backup(CRepository *this, const unsigned __int16 *a2, int a3)
{
  CRepositoryPackager *v6; // rcx
  int v7; // ebx
  CMemoryLog *v8; // rax
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  if ( !a2 || a3 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 76;
      v11 = 2147749896LL;
      goto LABEL_23;
    }
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(CRepository *))(*(_QWORD *)this + 104LL))(this);
    if ( v7 >= 0 )
    {
      v7 = CRepositoryPackager::PackageRepository(v6, a2, 0);
      (*(void (__fastcall **)(CRepository *))(*(_QWORD *)this + 112LL))(this);
      if ( v7 < 0 )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v7);
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 78;
        goto LABEL_12;
      }
    }
    else
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, v7);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 77;
LABEL_12:
        v11 = (unsigned int)v7;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, v11);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038f00  push    rbx
0x180038f02  push    rsi
0x180038f03  push    rdi
0x180038f04  push    r15
0x180038f06  sub     rsp, 28h
0x180038f0a  mov     ebx, r8d
0x180038f0d  mov     rsi, rdx
0x180038f10  mov     rdi, rcx
0x180038f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f1a  lea     r15, WPP_GLOBAL_Control
0x180038f21  cmp     rcx, r15
0x180038f24  jz      short loc_180038F47
0x180038f26  test    byte ptr [rcx+1Ch], 1
0x180038f2a  jz      short loc_180038F47
0x180038f2c  cmp     byte ptr [rcx+19h], 5
0x180038f30  jb      short loc_180038F47
0x180038f32  mov     rcx, [rcx+10h]
0x180038f36  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180038f3d  mov     edx, 4Bh ; 'K'
0x180038f42  call    WPP_SF_
0x180038f47  test    rsi, rsi
0x180038f4a  jz      loc_180038FFF
0x180038f50  test    ebx, ebx
0x180038f52  jnz     loc_180038FFF
0x180038f58  mov     rax, [rdi]
0x180038f5b  mov     rcx, rdi
0x180038f5e  mov     rax, [rax+68h]
0x180038f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f67  mov     ebx, eax
0x180038f69  test    eax, eax
0x180038f6b  jns     short loc_180038FAF
0x180038f6d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038f73  mov     rcx, rax
0x180038f76  mov     edx, ebx
0x180038f78  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f85  cmp     rcx, r15
0x180038f88  jz      loc_180039048
0x180038f8e  test    byte ptr [rcx+1Ch], 1
0x180038f92  jz      loc_180039048
0x180038f98  cmp     byte ptr [rcx+19h], 2
0x180038f9c  jb      loc_180039048
0x180038fa2  mov     edx, 4Dh ; 'M'
0x180038fa7  mov     r9d, ebx
0x180038faa  jmp     loc_180039038
0x180038faf  xor     r8d, r8d; unsigned __int16 *
0x180038fb2  mov     rdx, rsi; unsigned __int16 *
0x180038fb5  call    ?PackageRepository@CRepositoryPackager@@QEAAJPEBG0@Z; CRepositoryPackager::PackageRepository(ushort const *,ushort const *)
0x180038fba  mov     rcx, [rdi]
0x180038fbd  mov     ebx, eax
0x180038fbf  mov     rax, [rcx+70h]
0x180038fc3  mov     rcx, rdi
0x180038fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fcb  test    ebx, ebx
0x180038fcd  jns     short loc_180038FE0
0x180038fcf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038fd5  mov     rcx, rax
0x180038fd8  mov     edx, ebx
0x180038fda  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180038fe7  cmp     rcx, r15
0x180038fea  jz      short loc_180039048
0x180038fec  test    byte ptr [rcx+1Ch], 1
0x180038ff0  jz      short loc_180039048
0x180038ff2  cmp     byte ptr [rcx+19h], 2
0x180038ff6  jb      short loc_180039048
0x180038ff8  mov     edx, 4Eh ; 'N'
0x180038ffd  jmp     short loc_180038FA7
0x180038fff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180039005  mov     ebx, 80041008h
0x18003900a  mov     rcx, rax
0x18003900d  mov     edx, ebx
0x18003900f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039015  mov     rcx, cs:WPP_GLOBAL_Control
0x18003901c  cmp     rcx, r15
0x18003901f  jz      short loc_180039048
0x180039021  test    byte ptr [rcx+1Ch], 1
0x180039025  jz      short loc_180039048
0x180039027  cmp     byte ptr [rcx+19h], 2
0x18003902b  jb      short loc_180039048
0x18003902d  mov     edx, 4Ch ; 'L'
0x180039032  mov     r9d, 80041008h
0x180039038  mov     rcx, [rcx+10h]
0x18003903c  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039043  call    WPP_SF_d
0x180039048  mov     eax, ebx
0x18003904a  add     rsp, 28h
0x18003904e  pop     r15
0x180039050  pop     rdi
0x180039051  pop     rsi
0x180039052  pop     rbx
0x180039053  retn
```
