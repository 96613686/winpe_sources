# SIdxKeyTable::GetKeyAt(ushort,char * *)

- ea: `0x18000eee0`
- end: `0x18000f11d`
- name: `?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z`
- size: `573`
- prototype: `__int64 __fastcall(SIdxKeyTable *this, unsigned __int16, char **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dc00`
- `0x180019868`
- `0x180027eb4`
- `0x180037fb0`
- `0x180038570`

## callees

- `0x1800012b8`
- `0x18000eee0`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f011`
- `msvcrt!memcpy_s` at `0x18000f011`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000efb7`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000efb7`
- `wbemcomn!GetMemLogObject` at `0x18000f06d`
- `wbemcomn!GetMemLogObject` at `0x18000f0c5`
- `wbemcomn!GetMemLogObject` at `0x18000f06d`
- `wbemcomn!GetMemLogObject` at `0x18000f0c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f07b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f0d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f07b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f0d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SIdxKeyTable::GetKeyAt(SIdxKeyTable *this, unsigned __int16 a2, char **a3)
{
  __int64 v5; // rsi
  __int64 v6; // rdi
  unsigned int v7; // r15d
  int v8; // r10d
  __int64 v9; // r9
  __int64 v10; // rax
  void *v11; // rcx
  __int64 v12; // rbp
  void *ArenaHeap; // rax
  char *v14; // rax
  char *v15; // r14
  __int64 v16; // rsi
  char *i; // rdi
  rsize_t v18; // rbx
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v21; // rax
  unsigned int SourceSize[32]; // [rsp+20h] [rbp-1C8h]
  void *Source[32]; // [rsp+A0h] [rbp-148h] BYREF

  if ( (unsigned int)a2 < *((_DWORD *)this + 3) && a3 )
  {
    v5 = *((_QWORD *)this + 6);
    v6 = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 2LL * a2);
    memset_0(Source, 0, sizeof(Source));
    v7 = *(unsigned __int16 *)(v5 + 2 * v6);
    v8 = 0;
    if ( *(_WORD *)(v5 + 2 * v6) )
    {
      v9 = 0;
      do
      {
        if ( (unsigned int)v9 >= 0x20 )
          break;
        v10 = -1;
        v11 = (void *)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL)
                     + *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 8) + 8LL)
                                           + 2LL * *(unsigned __int16 *)(v5 + 2LL * (unsigned int)(v9 + v6 + 1))));
        Source[v9] = v11;
        do
          ++v10;
        while ( *((_BYTE *)v11 + v10) );
        SourceSize[v9] = v10;
        v8 += v10;
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 < v7 );
    }
    v12 = v8 + v7 + 1;
    _InterlockedIncrement(&g_lAllocs);
    ArenaHeap = (void *)CWin32DefaultArena::GetArenaHeap();
    v14 = (char *)HeapAlloc(ArenaHeap, 8u, (unsigned int)v12);
    v15 = v14;
    if ( v14 )
    {
      v16 = 0;
      *v14 = 0;
      for ( i = v14; (unsigned int)v16 < v7; v16 = (unsigned int)(v16 + 1) )
      {
        if ( (unsigned int)v16 >= 0x20 )
          break;
        if ( (_DWORD)v16 )
          *i++ = 92;
        v18 = SourceSize[v16];
        memcpy_s(i, v12 + v15 - i, Source[v16], v18);
        i += v18;
      }
      *i = 0;
      result = 0;
      *a3 = v15;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 8);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
      }
      return 8;
    }
  }
  else
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x18000eee0  mov     r11, rsp
0x18000eee3  push    rbx
0x18000eee4  push    r12
0x18000eee6  sub     rsp, 1D8h
0x18000eeed  mov     rax, cs:__security_cookie
0x18000eef4  xor     rax, rsp
0x18000eef7  mov     [rsp+1E8h+var_48], rax
0x18000eeff  movzx   eax, dx
0x18000ef02  mov     r12, r8
0x18000ef05  mov     rbx, rcx
0x18000ef08  cmp     eax, [rcx+0Ch]
0x18000ef0b  jnb     loc_18000F0C5
0x18000ef11  test    r8, r8
0x18000ef14  jz      loc_18000F0C5
0x18000ef1a  mov     rax, [rbx+10h]
0x18000ef1e  mov     r8d, 100h; Size
0x18000ef24  mov     [r11-18h], rbp
0x18000ef28  mov     [r11-20h], rsi
0x18000ef2c  mov     rsi, [rbx+30h]
0x18000ef30  movzx   ecx, dx
0x18000ef33  xor     edx, edx; Val
0x18000ef35  mov     [r11-28h], rdi
0x18000ef39  mov     [r11-30h], r14
0x18000ef3d  mov     [r11-38h], r15
0x18000ef41  movzx   edi, word ptr [rax+rcx*2]
0x18000ef45  lea     rcx, [r11-148h]; void *
0x18000ef4c  call    memset_0
0x18000ef51  movzx   r15d, word ptr [rsi+rdi*2]
0x18000ef56  xor     r10d, r10d
0x18000ef59  test    r15d, r15d
0x18000ef5c  jz      short loc_18000EFA9
0x18000ef5e  xor     r9d, r9d
0x18000ef61  cmp     r9d, 20h ; ' '
0x18000ef65  jnb     short loc_18000EFA9
0x18000ef67  mov     r8, [rbx+40h]
0x18000ef6b  lea     ecx, [rdi+1]
0x18000ef6e  add     ecx, r9d
0x18000ef71  mov     rax, [r8+8]
0x18000ef75  movzx   ecx, word ptr [rsi+rcx*2]
0x18000ef79  movzx   ecx, word ptr [rax+rcx*2]
0x18000ef7d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ef84  add     rcx, [r8+18h]
0x18000ef88  mov     [rsp+r9*8+1E8h+Source], rcx
0x18000ef90  inc     rax
0x18000ef93  cmp     byte ptr [rcx+rax], 0
0x18000ef97  jnz     short loc_18000EF90
0x18000ef99  mov     [rsp+r9*4+1E8h+SourceSize], eax
0x18000ef9e  add     r10d, eax
0x18000efa1  inc     r9d
0x18000efa4  cmp     r9d, r15d
0x18000efa7  jb      short loc_18000EF61
0x18000efa9  lea     ebp, [r15+1]
0x18000efad  add     ebp, r10d
0x18000efb0  lock inc cs:?g_lAllocs@@3JA; long g_lAllocs
0x18000efb7  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x18000efbd  mov     r8d, ebp; dwBytes
0x18000efc0  mov     edx, 8; dwFlags
0x18000efc5  mov     rcx, rax; hHeap
0x18000efc8  call    cs:__imp_HeapAlloc
0x18000efce  mov     r14, rax
0x18000efd1  test    rax, rax
0x18000efd4  jz      loc_18000F06D
0x18000efda  xor     esi, esi
0x18000efdc  mov     byte ptr [rax], 0
0x18000efdf  mov     rdi, rax
0x18000efe2  test    r15d, r15d
0x18000efe5  jz      short loc_18000F021
0x18000efe7  cmp     esi, 20h ; ' '
0x18000efea  jnb     short loc_18000F021
0x18000efec  test    esi, esi
0x18000efee  jz      short loc_18000EFF6
0x18000eff0  mov     byte ptr [rdi], 5Ch ; '\'
0x18000eff3  inc     rdi
0x18000eff6  mov     ebx, [rsp+rsi*4+1E8h+SourceSize]
0x18000effa  mov     rdx, r14
0x18000effd  mov     r8, [rsp+rsi*8+1E8h+Source]; Source
0x18000f005  sub     rdx, rdi
0x18000f008  add     rdx, rbp; DestinationSize
0x18000f00b  mov     r9d, ebx; SourceSize
0x18000f00e  mov     rcx, rdi; Destination
0x18000f011  call    cs:__imp_memcpy_s
0x18000f017  add     rdi, rbx
0x18000f01a  inc     esi
0x18000f01c  cmp     esi, r15d
0x18000f01f  jb      short loc_18000EFE7
0x18000f021  mov     byte ptr [rdi], 0
0x18000f024  xor     eax, eax
0x18000f026  mov     [r12], r14
0x18000f02a  mov     r14, [rsp+1E8h+var_30]
0x18000f032  mov     rdi, [rsp+1E8h+var_28]
0x18000f03a  mov     rsi, [rsp+1E8h+var_20]
0x18000f042  mov     rbp, [rsp+1E8h+var_18]
0x18000f04a  mov     r15, [rsp+1E8h+var_38]
0x18000f052  mov     rcx, [rsp+1E8h+var_48]
0x18000f05a  xor     rcx, rsp; StackCookie
0x18000f05d  call    __security_check_cookie
0x18000f062  add     rsp, 1D8h
0x18000f069  pop     r12
0x18000f06b  pop     rbx
0x18000f06c  retn
0x18000f06d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f073  mov     rcx, rax
0x18000f076  mov     edx, 8
0x18000f07b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f081  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f088  lea     rax, WPP_GLOBAL_Control
0x18000f08f  cmp     rcx, rax
0x18000f092  jz      short loc_18000F0BB
0x18000f094  test    byte ptr [rcx+1Ch], 1
0x18000f098  jz      short loc_18000F0BB
0x18000f09a  cmp     byte ptr [rcx+19h], 2
0x18000f09e  jb      short loc_18000F0BB
0x18000f0a0  mov     rcx, [rcx+10h]
0x18000f0a4  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000f0ab  mov     edx, 46h ; 'F'
0x18000f0b0  mov     r9d, 8
0x18000f0b6  call    WPP_SF_d
0x18000f0bb  mov     eax, 8
0x18000f0c0  jmp     loc_18000F02A
0x18000f0c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f0cb  mov     rcx, rax
0x18000f0ce  mov     edx, 57h ; 'W'
0x18000f0d3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0e0  lea     rax, WPP_GLOBAL_Control
0x18000f0e7  cmp     rcx, rax
0x18000f0ea  jz      short loc_18000F113
0x18000f0ec  test    byte ptr [rcx+1Ch], 1
0x18000f0f0  jz      short loc_18000F113
0x18000f0f2  cmp     byte ptr [rcx+19h], 2
0x18000f0f6  jb      short loc_18000F113
0x18000f0f8  mov     rcx, [rcx+10h]
0x18000f0fc  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000f103  mov     edx, 45h ; 'E'
0x18000f108  mov     r9d, 57h ; 'W'
0x18000f10e  call    WPP_SF_d
0x18000f113  mov     eax, 57h ; 'W'
0x18000f118  jmp     loc_18000F052
```
