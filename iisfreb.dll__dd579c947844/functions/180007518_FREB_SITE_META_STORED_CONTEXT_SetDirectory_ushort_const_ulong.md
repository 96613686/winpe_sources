# FREB_SITE_META_STORED_CONTEXT::SetDirectory(ushort const *,ulong)

- ea: `0x180007518`
- end: `0x1800075cd`
- name: `?SetDirectory@FREB_SITE_META_STORED_CONTEXT@@QEAAJPEBGK@Z`
- size: `181`
- prototype: `int __fastcall(FREB_SITE_META_STORED_CONTEXT *this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ce0`

## callees

- `0x180007518`
- `0x18000ac90`

## import_xrefs

- `msvcrt!_ultow` at `0x180007590`
- `msvcrt!_ultow` at `0x180007590`
- `iisutil!MakePathCanonicalizationProof` at `0x180007542`
- `iisutil!MakePathCanonicalizationProof` at `0x180007542`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007565`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007579`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000759e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800075b2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007565`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007579`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000759e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800075b2`

## pseudocode

```c
int __fastcall FREB_SITE_META_STORED_CONTEXT::SetDirectory(
        FREB_SITE_META_STORED_CONTEXT *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  STRU *v3; // rbx
  int result; // eax
  wchar_t Buffer[32]; // [rsp+20h] [rbp-68h] BYREF

  v3 = (FREB_SITE_META_STORED_CONTEXT *)((char *)this + 16);
  result = MakePathCanonicalizationProof(a2, (FREB_SITE_META_STORED_CONTEXT *)((char *)this + 16));
  if ( result >= 0 )
  {
    if ( *(_WORD *)(*((_QWORD *)this + 6) + 2LL * *((unsigned int *)this + 16) - 2) == 92
      || (result = STRU::Append(v3, L"\\"), result >= 0) )
    {
      result = STRU::Append(v3, L"W3SVC");
      if ( result >= 0 )
      {
        _ultow(a3, Buffer, 10);
        result = STRU::Append(v3, Buffer);
        if ( result >= 0 )
          return STRU::Append(v3, L"\\");
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007518  push    rbx
0x18000751a  push    rsi
0x18000751b  push    rdi
0x18000751c  sub     rsp, 70h
0x180007520  mov     rax, cs:__security_cookie
0x180007527  xor     rax, rsp
0x18000752a  mov     [rsp+88h+var_28], rax
0x18000752f  mov     rax, rdx
0x180007532  lea     rbx, [rcx+10h]
0x180007536  mov     rdi, rcx
0x180007539  mov     rdx, rbx
0x18000753c  mov     rcx, rax
0x18000753f  mov     esi, r8d
0x180007542  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180007548  test    eax, eax
0x18000754a  js      short loc_1800075B8
0x18000754c  mov     ecx, [rdi+40h]
0x18000754f  mov     rax, [rdi+30h]
0x180007553  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180007559  jz      short loc_18000756F
0x18000755b  lea     rdx, asc_18000CACC; "\\"
0x180007562  mov     rcx, rbx
0x180007565  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000756b  test    eax, eax
0x18000756d  js      short loc_1800075B8
0x18000756f  lea     rdx, aW3svc; "W3SVC"
0x180007576  mov     rcx, rbx
0x180007579  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000757f  test    eax, eax
0x180007581  js      short loc_1800075B8
0x180007583  mov     r8d, 0Ah; Radix
0x180007589  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18000758e  mov     ecx, esi; Value
0x180007590  call    cs:__imp__ultow
0x180007596  lea     rdx, [rsp+88h+Buffer]
0x18000759b  mov     rcx, rbx
0x18000759e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800075a4  test    eax, eax
0x1800075a6  js      short loc_1800075B8
0x1800075a8  lea     rdx, asc_18000CACC; "\\"
0x1800075af  mov     rcx, rbx
0x1800075b2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800075b8  mov     rcx, [rsp+88h+var_28]
0x1800075bd  xor     rcx, rsp; StackCookie
0x1800075c0  call    __security_check_cookie
0x1800075c5  add     rsp, 70h
0x1800075c9  pop     rdi
0x1800075ca  pop     rsi
0x1800075cb  pop     rbx
0x1800075cc  retn
```
