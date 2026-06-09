# CPageFile::Init(void *,ulong,ulong,ulong)

- ea: `0x18002d888`
- end: `0x18002d978`
- name: `?Init@CPageFile@@QEAAKPEAXKKK@Z`
- size: `240`
- prototype: `unsigned int(CPageFile *__hidden this, void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800012b8`
- `0x18002d7f4`
- `0x18002d888`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002d8e7`
- `wbemcomn!GetMemLogObject` at `0x18002d93e`
- `wbemcomn!GetMemLogObject` at `0x18002d8e7`
- `wbemcomn!GetMemLogObject` at `0x18002d93e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d8f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d94e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d8f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d94e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002d8a9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002d8a9`

## pseudocode

```c
__int64 __fastcall CPageFile::Init(CPageFile *this, void *a2, unsigned int a3, unsigned int a4, unsigned int a5)
{
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v11; // rcx
  __int64 v12; // rdx
  CMemoryLog *v14; // rax
  unsigned int v15; // [rsp+20h] [rbp-38h]
  unsigned int v16; // [rsp+28h] [rbp-30h]

  if ( *((_BYTE *)this + 56) )
  {
LABEL_4:
    *((_DWORD *)this + 3) = a5;
    *((_DWORD *)this + 54) = 0;
    v9 = CPageCache::Init((CPageFile *)((char *)this + 64), a2, a3, a4, v15, v16);
    if ( v9 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 97;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0) )
  {
    *((_BYTE *)this + 56) = 1;
    goto LABEL_4;
  }
  *((_BYTE *)this + 56) = 0;
  v14 = GetMemLogObject();
  v9 = 14;
  CMemoryLog::Write(v14, 14);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 96;
    goto LABEL_10;
  }
  return v9;
}

```

## disassembly

```asm
0x18002d888  push    rbx
0x18002d88a  push    rbp
0x18002d88b  push    rsi
0x18002d88c  push    rdi
0x18002d88d  sub     rsp, 38h
0x18002d891  cmp     byte ptr [rcx+38h], 0
0x18002d895  mov     edi, r9d
0x18002d898  mov     esi, r8d
0x18002d89b  mov     rbp, rdx
0x18002d89e  mov     rbx, rcx
0x18002d8a1  jnz     short loc_18002D8BB
0x18002d8a3  add     rcx, 10h; lpCriticalSection
0x18002d8a7  xor     edx, edx; dwSpinCount
0x18002d8a9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002d8af  test    eax, eax
0x18002d8b1  jz      loc_18002D93A
0x18002d8b7  mov     byte ptr [rbx+38h], 1
0x18002d8bb  mov     eax, [rsp+58h+arg_20]
0x18002d8c2  lea     rcx, [rbx+40h]; this
0x18002d8c6  mov     r9d, edi; unsigned int
0x18002d8c9  mov     [rbx+0Ch], eax
0x18002d8cc  mov     r8d, esi; unsigned int
0x18002d8cf  mov     dword ptr [rbx+0D8h], 0
0x18002d8d9  mov     rdx, rbp; void *
0x18002d8dc  call    ?Init@CPageCache@@QEAAKPEAXKKKK@Z; CPageCache::Init(void *,ulong,ulong,ulong,ulong)
0x18002d8e1  mov     ebx, eax
0x18002d8e3  test    eax, eax
0x18002d8e5  jz      short loc_18002D8F8
0x18002d8e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d8ed  mov     rcx, rax
0x18002d8f0  mov     edx, ebx
0x18002d8f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d8f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8ff  lea     rax, WPP_GLOBAL_Control
0x18002d906  cmp     rcx, rax
0x18002d909  jz      short loc_18002D92F
0x18002d90b  test    byte ptr [rcx+1Ch], 1
0x18002d90f  jz      short loc_18002D92F
0x18002d911  cmp     byte ptr [rcx+19h], 2
0x18002d915  jb      short loc_18002D92F
0x18002d917  mov     edx, 61h ; 'a'
0x18002d91c  mov     rcx, [rcx+10h]
0x18002d920  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002d927  mov     r9d, ebx
0x18002d92a  call    WPP_SF_d
0x18002d92f  mov     eax, ebx
0x18002d931  add     rsp, 38h
0x18002d935  pop     rdi
0x18002d936  pop     rsi
0x18002d937  pop     rbp
0x18002d938  pop     rbx
0x18002d939  retn
0x18002d93a  mov     byte ptr [rbx+38h], 0
0x18002d93e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d944  mov     ebx, 0Eh
0x18002d949  mov     rcx, rax
0x18002d94c  mov     edx, ebx
0x18002d94e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d954  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d95b  lea     rax, WPP_GLOBAL_Control
0x18002d962  cmp     rcx, rax
0x18002d965  jz      short loc_18002D92F
0x18002d967  test    byte ptr [rcx+1Ch], 1
0x18002d96b  jz      short loc_18002D92F
0x18002d96d  cmp     byte ptr [rcx+19h], 2
0x18002d971  jb      short loc_18002D92F
0x18002d973  lea     edx, [rbx+52h]
0x18002d976  jmp     short loc_18002D91C
```
