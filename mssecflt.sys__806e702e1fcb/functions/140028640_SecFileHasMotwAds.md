# SecFileHasMotwAds

- ea: `0x140028640`
- end: `0x140028834`
- name: `SecFileHasMotwAds`
- size: `500`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14002cddc`
- `0x14003205c`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x140028640`
- `0x14002975c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140028795`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140028795`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400287fe`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400287fe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002868f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002868f`
- `ntoskrnl!ExQueryDepthSList` at `0x1400287d2`
- `ntoskrnl!ExQueryDepthSList` at `0x1400287d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002871d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002871d`

## pseudocode

```c
char __fastcall SecFileHasMotwAds(PFILE_OBJECT FileObject)
{
  char *v1; // rbx
  unsigned int *v3; // rdi
  union _SLIST_HEADER *v4; // rcx
  char v5; // r14
  PSLIST_ENTRY v6; // rsi
  int InformationFile; // eax
  unsigned int *PoolWithTag; // rax
  unsigned int *v9; // rbx
  __int64 v10; // rax
  char *v11; // rdi
  USHORT v12; // bx
  SIZE_T NumberOfBytes; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-18h] BYREF

  v1 = (char *)SecData + 512;
  String1 = 0;
  v3 = 0;
  v4 = (union _SLIST_HEADER *)((char *)SecData + 512);
  LODWORD(NumberOfBytes) = 0;
  v5 = 0;
  ++*((_DWORD *)SecData + 133);
  v6 = ExpInterlockedPopEntrySList(v4);
  if ( !v6 )
  {
    ++*((_DWORD *)v1 + 6);
    v6 = (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v1 + 6))(
                         *((unsigned int *)v1 + 9),
                         *((unsigned int *)v1 + 11),
                         *((unsigned int *)v1 + 10));
  }
  if ( v6 )
  {
    InformationFile = SecQueryInformationFile(FileObject, v6, 0x10000u, FileStreamInformation, (PULONG)&NumberOfBytes);
    if ( InformationFile == -2147483643 || InformationFile == -1073741789 )
    {
      if ( qword_140020008 )
        PoolWithTag = (unsigned int *)qword_140020008(256, (unsigned int)NumberOfBytes, 1902535507);
      else
        PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x71666353u);
      v3 = PoolWithTag;
      if ( !PoolWithTag )
      {
LABEL_22:
        v11 = (char *)SecData + 512;
        ++*((_DWORD *)SecData + 135);
        v12 = *((_WORD *)v11 + 8);
        if ( ExQueryDepthSList((PSLIST_HEADER)v11) < v12 )
        {
          _mm_lfence();
          ExpInterlockedPushEntrySList((PSLIST_HEADER)v11, v6);
        }
        else
        {
          ++*((_DWORD *)v11 + 8);
          (*((void (__fastcall **)(PSLIST_ENTRY))v11 + 7))(v6);
        }
        return v5;
      }
      InformationFile = SecQueryInformationFile(
                          FileObject,
                          PoolWithTag,
                          NumberOfBytes,
                          FileStreamInformation,
                          (PULONG)&NumberOfBytes);
    }
    if ( InformationFile >= 0 && (unsigned int)NumberOfBytes >= 0x20 )
    {
      v9 = (unsigned int *)v6;
      if ( v3 )
        v9 = v3;
      while ( 1 )
      {
        String1.Length = *((_WORD *)v9 + 2);
        String1.MaximumLength = *((_WORD *)v9 + 2);
        String1.Buffer = (PWSTR)(v9 + 6);
        if ( RtlEqualUnicodeString(&String1, &SecMotwAdsName, 1u) )
          break;
        v10 = *v9;
        if ( !(_DWORD)v10 )
          goto LABEL_20;
        v9 = (unsigned int *)((char *)v9 + v10);
      }
      v5 = 1;
    }
LABEL_20:
    if ( v3 )
      SecFreePool(v3, 0x71666353u);
    goto LABEL_22;
  }
  return v5;
}

```

## disassembly

```asm
0x140028640  mov     [rsp-18h+arg_8], rbx
0x140028645  mov     [rsp-18h+arg_10], rsi
0x14002864a  mov     [rsp-18h+arg_18], rdi
0x14002864f  push    rbp
0x140028650  push    r14
0x140028652  push    r15
0x140028654  mov     rbp, rsp
0x140028657  sub     rsp, 50h
0x14002865b  mov     rax, cs:__security_cookie
0x140028662  xor     rax, rsp
0x140028665  mov     [rbp+var_8], rax
0x140028669  mov     rbx, cs:SecData
0x140028670  xorps   xmm0, xmm0
0x140028673  add     rbx, 200h
0x14002867a  mov     r15, rcx
0x14002867d  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140028681  xor     edi, edi
0x140028683  mov     rcx, rbx; ListHead
0x140028686  mov     dword ptr [rbp+NumberOfBytes], edi
0x140028689  xor     r14b, r14b
0x14002868c  inc     dword ptr [rbx+14h]
0x14002868f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140028696  nop     dword ptr [rax+rax+00h]
0x14002869b  mov     rsi, rax
0x14002869e  test    rax, rax
0x1400286a1  jnz     short loc_1400286BD
0x1400286a3  inc     dword ptr [rbx+18h]
0x1400286a6  mov     edx, [rbx+2Ch]
0x1400286a9  mov     rax, [rbx+30h]
0x1400286ad  mov     r8d, [rbx+28h]
0x1400286b1  mov     ecx, [rbx+24h]
0x1400286b4  call    cs:__guard_dispatch_icall_fptr
0x1400286ba  mov     rsi, rax
0x1400286bd  test    rsi, rsi
0x1400286c0  jz      loc_14002880A
0x1400286c6  lea     rax, [rbp+NumberOfBytes]
0x1400286ca  mov     ebx, 16h
0x1400286cf  mov     r9d, ebx; FileInformationClass
0x1400286d2  mov     [rsp+50h+var_30], rax; PULONG
0x1400286d7  mov     r8d, 10000h; Length
0x1400286dd  mov     rdx, rsi; FileInformation
0x1400286e0  mov     rcx, r15; FileObject
0x1400286e3  call    SecQueryInformationFile
0x1400286e8  cmp     eax, 80000005h
0x1400286ed  jz      short loc_1400286F6
0x1400286ef  cmp     eax, 0C0000023h
0x1400286f4  jnz     short loc_140028750
0x1400286f6  mov     rax, cs:qword_140020008
0x1400286fd  mov     r8d, 71666353h; Tag
0x140028703  mov     edx, dword ptr [rbp+NumberOfBytes]; NumberOfBytes
0x140028706  test    rax, rax
0x140028709  jz      short loc_140028718
0x14002870b  mov     ecx, 100h
0x140028710  call    cs:__guard_dispatch_icall_fptr
0x140028716  jmp     short loc_140028729
0x140028718  mov     ecx, 1; PoolType
0x14002871d  call    cs:__imp_ExAllocatePoolWithTag
0x140028724  nop     dword ptr [rax+rax+00h]
0x140028729  mov     rdi, rax
0x14002872c  test    rax, rax
0x14002872f  jz      loc_1400287BA
0x140028735  mov     r8d, dword ptr [rbp+NumberOfBytes]; Length
0x140028739  lea     rax, [rbp+NumberOfBytes]
0x14002873d  mov     r9d, ebx; FileInformationClass
0x140028740  mov     [rsp+50h+var_30], rax; PULONG
0x140028745  mov     rdx, rdi; FileInformation
0x140028748  mov     rcx, r15; FileObject
0x14002874b  call    SecQueryInformationFile
0x140028750  test    eax, eax
0x140028752  js      short loc_1400287A8
0x140028754  cmp     dword ptr [rbp+NumberOfBytes], 20h ; ' '
0x140028758  jb      short loc_1400287A8
0x14002875a  test    rdi, rdi
0x14002875d  mov     rbx, rsi
0x140028760  cmovnz  rbx, rdi
0x140028764  jmp     short loc_14002876F
0x140028766  mov     eax, [rbx]
0x140028768  test    eax, eax
0x14002876a  jz      short loc_1400287A8
0x14002876c  add     rbx, rax
0x14002876f  movzx   eax, word ptr [rbx+4]
0x140028773  lea     rdx, SecMotwAdsName; String2
0x14002877a  mov     [rbp+String1.Length], ax
0x14002877e  lea     rcx, [rbp+String1]; String1
0x140028782  movzx   eax, word ptr [rbx+4]
0x140028786  mov     r8b, 1; CaseInSensitive
0x140028789  mov     [rbp+String1.MaximumLength], ax
0x14002878d  lea     rax, [rbx+18h]
0x140028791  mov     [rbp+String1.Buffer], rax
0x140028795  call    cs:__imp_RtlEqualUnicodeString
0x14002879c  nop     dword ptr [rax+rax+00h]
0x1400287a1  test    al, al
0x1400287a3  jz      short loc_140028766
0x1400287a5  mov     r14b, 1
0x1400287a8  test    rdi, rdi
0x1400287ab  jz      short loc_1400287BA
0x1400287ad  mov     edx, 71666353h; Tag
0x1400287b2  mov     rcx, rdi; P
0x1400287b5  call    SecFreePool
0x1400287ba  mov     rdi, cs:SecData
0x1400287c1  add     rdi, 200h
0x1400287c8  mov     rcx, rdi; SListHead
0x1400287cb  inc     dword ptr [rdi+1Ch]
0x1400287ce  movzx   ebx, word ptr [rdi+10h]
0x1400287d2  call    cs:__imp_ExQueryDepthSList
0x1400287d9  nop     dword ptr [rax+rax+00h]
0x1400287de  cmp     ax, bx
0x1400287e1  jb      short loc_1400287F5
0x1400287e3  inc     dword ptr [rdi+20h]
0x1400287e6  mov     rcx, rsi
0x1400287e9  mov     rax, [rdi+38h]
0x1400287ed  call    cs:__guard_dispatch_icall_fptr
0x1400287f3  jmp     short loc_14002880A
0x1400287f5  lfence
0x1400287f8  mov     rdx, rsi; ListEntry
0x1400287fb  mov     rcx, rdi; ListHead
0x1400287fe  call    cs:__imp_ExpInterlockedPushEntrySList
0x140028805  nop     dword ptr [rax+rax+00h]
0x14002880a  mov     al, r14b
0x14002880d  mov     rcx, [rbp+var_8]
0x140028811  xor     rcx, rsp; StackCookie
0x140028814  call    __security_check_cookie
0x140028819  lea     r11, [rsp+50h+var_s0]
0x14002881e  mov     rbx, [r11+28h]
0x140028822  mov     rsi, [r11+30h]
0x140028826  mov     rdi, [r11+38h]
0x14002882a  mov     rsp, r11
0x14002882d  pop     r15
0x14002882f  pop     r14
0x140028831  pop     rbp
0x140028832  retn
```
