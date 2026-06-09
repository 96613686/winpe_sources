# MetadataEnumerator::GetNextKey(ushort *,unsigned __int64)

- ea: `0x180017300`
- end: `0x1800173f3`
- name: `?GetNextKey@MetadataEnumerator@@EEAAJPEAG_K@Z`
- size: `243`
- prototype: `__int64 __fastcall(MetadataEnumerator *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1800020a8`
- `0x180005424`
- `0x180006014`
- `0x180017300`

## string_xrefs

- `0x18001739d`: `    Failed to copy key string`

## pseudocode

```c
__int64 __fastcall MetadataEnumerator::GetNextKey(MetadataEnumerator *this, unsigned __int16 *a2, unsigned __int64 a3)
{
  int v5; // eax
  const struct std::nothrow_t *v6; // rdx
  unsigned int v7; // edi
  _QWORD **v8; // rcx
  _QWORD *v9; // rdx
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  int v12; // [rsp+28h] [rbp-10h]

  if ( *((_QWORD *)this + 2) )
  {
    v5 = StringCchCopyW(a2, a3, *(const unsigned __int16 **)(**((_QWORD **)this + 1) + 16LL));
    v7 = v5;
    if ( v5 >= 0 )
    {
      operator delete(*(void **)(**((_QWORD **)this + 1) + 16LL), v6);
      v8 = (_QWORD **)**((_QWORD **)this + 1);
      v9 = *v8;
      --*((_QWORD *)this + 2);
      *v8[1] = v9;
      v9[1] = v8[1];
      operator delete(v8, (const struct std::nothrow_t *)0x18);
      return 0;
    }
    else
    {
      v12 = v5;
      v11 = 42;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "MetadataEnumerator::GetNextKey",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataenumerator.cpp",
        v11,
        v12);
      ProvPackageLog(3, L"    Failed to copy key string");
      return v7;
    }
  }
  else
  {
    v10 = 37;
    ProvPackageLog(
      0,
      L"%hs (%hs:%d): %s",
      "MetadataEnumerator::GetNextKey",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataenumerator.cpp",
      v10,
      L"No more keys to enumerate");
    return 2147942659LL;
  }
}

```

## disassembly

```asm
0x180017300  mov     [rsp+arg_0], rbx
0x180017305  push    rdi
0x180017306  sub     rsp, 30h
0x18001730a  cmp     qword ptr [rcx+10h], 0
0x18001730f  mov     r9, r8
0x180017312  mov     r10, rdx
0x180017315  mov     rbx, rcx
0x180017318  jnz     short loc_180017354
0x18001731a  lea     rax, aNoMoreKeysToEn; "No more keys to enumerate"
0x180017321  xor     ecx, ecx
0x180017323  mov     qword ptr [rsp+38h+var_10], rax
0x180017328  lea     r9, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001732f  lea     r8, aMetadataenumer; "MetadataEnumerator::GetNextKey"
0x180017336  mov     [rsp+38h+var_18], 25h ; '%'
0x18001733e  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x180017345  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001734a  mov     eax, 80070103h
0x18001734f  jmp     loc_1800173E8
0x180017354  mov     rax, [rcx+8]
0x180017358  mov     rdx, r9; unsigned __int64
0x18001735b  mov     rcx, r10; unsigned __int16 *
0x18001735e  mov     r8, [rax]
0x180017361  mov     r8, [r8+10h]; unsigned __int16 *
0x180017365  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001736a  mov     edi, eax
0x18001736c  test    eax, eax
0x18001736e  jns     short loc_1800173AF
0x180017370  mov     [rsp+38h+var_10], eax
0x180017374  lea     r9, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001737b  mov     ebx, 3
0x180017380  mov     [rsp+38h+var_18], 2Ah ; '*'
0x180017388  mov     ecx, ebx
0x18001738a  lea     r8, aMetadataenumer; "MetadataEnumerator::GetNextKey"
0x180017391  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017398  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001739d  lea     rdx, aFailedToCopyKe; "    Failed to copy key string"
0x1800173a4  mov     ecx, ebx
0x1800173a6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800173ab  mov     eax, edi
0x1800173ad  jmp     short loc_1800173E8
0x1800173af  mov     rax, [rbx+8]
0x1800173b3  mov     rcx, [rax]
0x1800173b6  mov     rcx, [rcx+10h]; void *
0x1800173ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800173bf  mov     rax, [rbx+8]
0x1800173c3  mov     rcx, [rax]; void *
0x1800173c6  mov     rdx, [rcx]
0x1800173c9  dec     qword ptr [rbx+10h]
0x1800173cd  mov     rax, [rcx+8]
0x1800173d1  mov     [rax], rdx
0x1800173d4  mov     rax, [rcx+8]
0x1800173d8  mov     [rdx+8], rax
0x1800173dc  mov     edx, 18h; struct std::nothrow_t *
0x1800173e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800173e6  xor     eax, eax
0x1800173e8  mov     rbx, [rsp+38h+arg_0]
0x1800173ed  add     rsp, 30h
0x1800173f1  pop     rdi
0x1800173f2  retn
```
