# CFileListener::InitChangeNotificationData(void)

- ea: `0x18000c244`
- end: `0x18000c36c`
- name: `?InitChangeNotificationData@CFileListener@@AEAAJXZ`
- size: `296`
- prototype: `__int64 __fastcall(CFileListener *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ba98`

## callees

- `0x18000c244`
- `0x180020940`

## import_xrefs

- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c2a3`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c2f2`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c327`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c2a3`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c2f2`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c327`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c27f`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c2da`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c30f`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c27f`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c2da`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000c30f`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c268`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c2c3`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c268`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c2c3`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c336`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c336`

## pseudocode

```c
__int64 __fastcall CFileListener::InitChangeNotificationData(CFileListener *this)
{
  STRU *v1; // rsi
  int PathFrom; // edx
  struct STRU *v4; // rdi
  int v5; // eax
  const unsigned __int16 *Str; // rax

  v1 = (CFileListener *)((char *)this + 376);
  PathFrom = STRU::Copy(
               (CFileListener *)((char *)this + 376),
               *((const unsigned __int16 **)this + 7),
               *((_DWORD *)this + 16));
  if ( PathFrom >= 0 )
  {
    if ( STRU::IsEmpty((STRU *)g_struChangeNotificationDirectory) || dword_180048760 )
    {
      v4 = (CFileListener *)((char *)this + 320);
      v5 = STRU::Copy(
             (CFileListener *)((char *)this + 320),
             *((const unsigned __int16 **)this + 23),
             *((_DWORD *)this + 48));
    }
    else
    {
      v4 = (CFileListener *)((char *)this + 320);
      v5 = STRU::Copy((CFileListener *)((char *)this + 320), (const struct STRU *)g_struChangeNotificationDirectory);
    }
    PathFrom = v5;
    if ( v5 >= 0 )
    {
      if ( !STRU::IsEmpty((STRU *)g_struUNCUserName) )
      {
        PathFrom = STRU::Copy((CFileListener *)((char *)this + 432), (const struct STRU *)g_struUNCUserName);
        if ( PathFrom < 0 )
          return (unsigned int)PathFrom;
        *((_DWORD *)this + 137) = 1;
      }
      if ( STRU::IsEmpty((STRU *)g_struUNCPassword)
        || (PathFrom = STRU::Copy((CFileListener *)((char *)this + 488), (const struct STRU *)g_struUNCPassword),
            PathFrom >= 0) )
      {
        Str = STRU::QueryStr(v1);
        PathFrom = MakePathFrom((CFileListener *)((char *)this + 264), v4, Str, 0);
        if ( PathFrom >= 0 )
          return 0;
      }
    }
  }
  return (unsigned int)PathFrom;
}

```

## disassembly

```asm
0x18000c244  mov     [rsp+arg_0], rbx
0x18000c249  mov     [rsp+arg_8], rsi
0x18000c24e  push    rdi
0x18000c24f  sub     rsp, 20h
0x18000c253  mov     r8d, [rcx+40h]
0x18000c257  lea     rsi, [rcx+178h]
0x18000c25e  mov     rdx, [rcx+38h]
0x18000c262  mov     rbx, rcx
0x18000c265  mov     rcx, rsi
0x18000c268  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000c26e  mov     edx, eax
0x18000c270  test    eax, eax
0x18000c272  js      loc_18000C35A
0x18000c278  lea     rcx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x18000c27f  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000c285  test    al, al
0x18000c287  jnz     short loc_18000C2AB
0x18000c289  cmp     cs:dword_180048760, 0
0x18000c290  jnz     short loc_18000C2AB
0x18000c292  lea     rdi, [rbx+140h]
0x18000c299  mov     rcx, rdi
0x18000c29c  lea     rdx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x18000c2a3  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000c2a9  jmp     short loc_18000C2C9
0x18000c2ab  mov     r8d, [rbx+0C0h]
0x18000c2b2  lea     rdi, [rbx+140h]
0x18000c2b9  mov     rdx, [rbx+0B8h]
0x18000c2c0  mov     rcx, rdi
0x18000c2c3  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000c2c9  mov     edx, eax
0x18000c2cb  test    eax, eax
0x18000c2cd  js      loc_18000C35A
0x18000c2d3  lea     rcx, ?g_struUNCUserName@@3VSTRU@@A; STRU g_struUNCUserName
0x18000c2da  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000c2e0  test    al, al
0x18000c2e2  jnz     short loc_18000C308
0x18000c2e4  lea     rcx, [rbx+1B0h]
0x18000c2eb  lea     rdx, ?g_struUNCUserName@@3VSTRU@@A; STRU g_struUNCUserName
0x18000c2f2  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000c2f8  mov     edx, eax
0x18000c2fa  test    eax, eax
0x18000c2fc  js      short loc_18000C35A
0x18000c2fe  mov     dword ptr [rbx+224h], 1
0x18000c308  lea     rcx, ?g_struUNCPassword@@3VSTRU@@A; STRU g_struUNCPassword
0x18000c30f  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000c315  test    al, al
0x18000c317  jnz     short loc_18000C333
0x18000c319  lea     rcx, [rbx+1E8h]
0x18000c320  lea     rdx, ?g_struUNCPassword@@3VSTRU@@A; STRU g_struUNCPassword
0x18000c327  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000c32d  mov     edx, eax
0x18000c32f  test    eax, eax
0x18000c331  js      short loc_18000C35A
0x18000c333  mov     rcx, rsi
0x18000c336  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c33c  lea     rcx, [rbx+108h]; struct STRU *
0x18000c343  xor     r9d, r9d; unsigned __int16 *
0x18000c346  mov     r8, rax; unsigned __int16 *
0x18000c349  mov     rdx, rdi; struct STRU *
0x18000c34c  call    ?MakePathFrom@@YAJPEAVSTRU@@0PEBG1@Z; MakePathFrom(STRU *,STRU *,ushort const *,ushort const *)
0x18000c351  mov     edx, eax
0x18000c353  xor     eax, eax
0x18000c355  test    edx, edx
0x18000c357  cmovns  edx, eax
0x18000c35a  mov     rbx, [rsp+28h+arg_0]
0x18000c35f  mov     eax, edx
0x18000c361  mov     rsi, [rsp+28h+arg_8]
0x18000c366  add     rsp, 20h
0x18000c36a  pop     rdi
0x18000c36b  retn
```
