# Microsoft::Resources::Runtime::MrtMap<ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<ushort const *>>::Insert(ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *)

- ea: `0x180038190`
- end: `0x18003824b`
- name: `?Insert@?$MrtMap@PEBGPEAVCSchemaPriIndexInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@U?$Equal@PEBG@345@@Runtime@Resources@Microsoft@@QEAAJPEBGPEAVCSchemaPriIndexInfo@CResourceManagerInternal@234@@Z`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003760c`
- `0x180037a7c`

## callees

- `0x180038190`
- `0x180038478`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038221`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038221`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800381ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800381ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800381cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800381cc`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::MrtMap<unsigned short const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::Insert(
        RTL_SRWLOCK *a1,
        const WCHAR *a2,
        __int64 a3)
{
  void *i; // rdi
  int v7; // edi

  for ( i = 0; i < a1[3].Ptr; i = (char *)i + 1 )
  {
    if ( CompareStringOrdinal(*((LPCWCH *)a1->Ptr + 2 * (_QWORD)i), -1, a2, -1, 1) == 2 )
      break;
  }
  if ( i < a1[3].Ptr )
  {
    return (unsigned int)-2147024713;
  }
  else
  {
    v7 = 0;
    AcquireSRWLockExclusive(a1 + 4);
    if ( a1[3].Ptr != a1[2].Ptr
      || (v7 = Microsoft::Resources::Runtime::MrtMap<unsigned short const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::_Expand(a1),
          v7 >= 0) )
    {
      *((_QWORD *)a1->Ptr + 2 * (__int64)a1[3].Ptr) = a2;
      *((_QWORD *)a1->Ptr + 2 * (__int64)a1[3].Ptr++ + 1) = a3;
    }
    ReleaseSRWLockExclusive(a1 + 4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038190  push    rbx
0x180038192  push    rbp
0x180038193  push    rsi
0x180038194  push    rdi
0x180038195  push    r14
0x180038197  sub     rsp, 30h
0x18003819b  xor     edi, edi
0x18003819d  mov     r14, r8
0x1800381a0  mov     rbp, rdx
0x1800381a3  mov     rbx, rcx
0x1800381a6  cmp     [rcx+18h], rdi
0x1800381aa  jbe     short loc_1800381E0
0x1800381ac  or      esi, 0FFFFFFFFh
0x1800381af  mov     rcx, [rbx]
0x1800381b2  mov     rax, rdi
0x1800381b5  add     rax, rax
0x1800381b8  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800381c0  mov     r9d, esi; cchCount2
0x1800381c3  mov     r8, rbp; lpString2
0x1800381c6  mov     edx, esi; cchCount1
0x1800381c8  mov     rcx, [rcx+rax*8]; lpString1
0x1800381cc  call    cs:__imp_CompareStringOrdinal
0x1800381d2  cmp     eax, 2
0x1800381d5  jz      short loc_1800381E0
0x1800381d7  inc     rdi
0x1800381da  cmp     rdi, [rbx+18h]
0x1800381de  jb      short loc_1800381AF
0x1800381e0  cmp     rdi, [rbx+18h]
0x1800381e4  jb      short loc_180038234
0x1800381e6  lea     rcx, [rbx+20h]; SRWLock
0x1800381ea  xor     edi, edi
0x1800381ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800381f2  mov     rax, [rbx+10h]
0x1800381f6  cmp     [rbx+18h], rax
0x1800381fa  jz      short loc_18003823B
0x1800381fc  mov     r8, [rbx+18h]
0x180038200  mov     rdx, [rbx]
0x180038203  add     r8, r8
0x180038206  mov     [rdx+r8*8], rbp
0x18003820a  mov     r8, [rbx+18h]
0x18003820e  mov     rdx, [rbx]
0x180038211  add     r8, r8
0x180038214  mov     [rdx+r8*8+8], r14
0x180038219  inc     qword ptr [rbx+18h]
0x18003821d  lea     rcx, [rbx+20h]; SRWLock
0x180038221  call    cs:__imp_ReleaseSRWLockExclusive
0x180038227  mov     eax, edi
0x180038229  add     rsp, 30h
0x18003822d  pop     r14
0x18003822f  pop     rdi
0x180038230  pop     rsi
0x180038231  pop     rbp
0x180038232  pop     rbx
0x180038233  retn
0x180038234  mov     edi, 800700B7h
0x180038239  jmp     short loc_180038227
0x18003823b  mov     rcx, rbx
0x18003823e  call    ?_Expand@?$MrtMap@PEBGPEAVCSchemaPriIndexInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@U?$Equal@PEBG@345@@Runtime@Resources@Microsoft@@AEAAJXZ; Microsoft::Resources::Runtime::MrtMap<ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *,Microsoft::Resources::Runtime::Equal<ushort const *>>::_Expand(void)
0x180038243  mov     edi, eax
0x180038245  test    eax, eax
0x180038247  jns     short loc_1800381FC
0x180038249  jmp     short loc_18003821D
```
