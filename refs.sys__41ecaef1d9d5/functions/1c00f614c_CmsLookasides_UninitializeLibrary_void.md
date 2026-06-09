# CmsLookasides::UninitializeLibrary(void)

- ea: `0x1c00f614c`
- end: `0x1c00f626a`
- name: `?UninitializeLibrary@CmsLookasides@@SAXXZ`
- size: `286`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1c00b43b8`

## callees

- `0x1c00f614c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f61ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f6224`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f61ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f6224`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f61ff`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f61ff`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1c00f61c3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1c00f61c3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1c00f61d1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1c00f61d1`

## pseudocode

```c
void CmsLookasides::UninitializeLibrary(void)
{
  unsigned int v0; // ebx
  PVOID *v1; // rsi
  unsigned int v2; // r15d
  __int64 v3; // r14
  __int64 v4; // rdi
  _BYTE *v5; // rbp
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  PSLIST_ENTRY v7; // rax

  if ( LookasideListsInitialized )
  {
    v0 = 0;
    v1 = (PVOID *)&LookasideLists;
    do
    {
      if ( v0 == 11 || (v2 = NumProcessors, v0 - 17 <= 1) )
        v2 = 1;
      v3 = 0;
      if ( v2 )
      {
        v4 = 0;
        do
        {
          v5 = *v1;
          if ( *((_BYTE *)*v1 + v4 + 8) )
          {
            v6 = (struct _NPAGED_LOOKASIDE_LIST *)&v5[192 * v3 + 64];
            if ( v5[v4 + 9] )
              ExDeleteNPagedLookasideList(v6);
            else
              ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)v6);
          }
          else
          {
            while ( 1 )
            {
              v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)&v5[v4 + 64]);
              if ( !v7 )
                break;
              ExFreePoolWithTag(v7, 0);
              --*(_DWORD *)&v5[v4 + 80];
            }
          }
          v3 = (unsigned int)(v3 + 1);
          v4 += 192;
        }
        while ( (unsigned int)v3 < v2 );
      }
      ExFreePoolWithTag(*v1, 0);
      *v1 = 0;
      ++v0;
      ++v1;
    }
    while ( v0 < 0x19 );
    LookasideListsInitialized = 0;
  }
}

```

## disassembly

```asm
0x1c00f614c  mov     rax, rsp
0x1c00f614f  mov     [rax+8], rbx
0x1c00f6153  mov     [rax+10h], rbp
0x1c00f6157  mov     [rax+18h], rsi
0x1c00f615b  mov     [rax+20h], rdi
0x1c00f615f  push    r12
0x1c00f6161  push    r14
0x1c00f6163  push    r15
0x1c00f6165  sub     rsp, 20h
0x1c00f6169  cmp     cs:?LookasideListsInitialized@@3EA, 0; uchar LookasideListsInitialized
0x1c00f6170  jz      loc_1C00F624A
0x1c00f6176  xor     ebx, ebx
0x1c00f6178  lea     rsi, ?LookasideLists@@3PAPEAU_SmsLookaside@@A; _SmsLookaside * near * LookasideLists
0x1c00f617f  cmp     ebx, 0Bh
0x1c00f6182  jz      short loc_1C00F6193
0x1c00f6184  mov     r15d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c00f618b  lea     eax, [rbx-11h]
0x1c00f618e  cmp     eax, 1
0x1c00f6191  ja      short loc_1C00F6199
0x1c00f6193  mov     r15d, 1
0x1c00f6199  xor     r14d, r14d
0x1c00f619c  test    r15d, r15d
0x1c00f619f  jz      short loc_1C00F621F
0x1c00f61a1  xor     edi, edi
0x1c00f61a3  mov     rbp, [rsi]
0x1c00f61a6  cmp     byte ptr [rdi+rbp+8], 0
0x1c00f61ab  jz      short loc_1C00F61DF
0x1c00f61ad  lea     rcx, [r14+r14*2]
0x1c00f61b1  shl     rcx, 6
0x1c00f61b5  add     rcx, 40h ; '@'
0x1c00f61b9  add     rcx, rbp; Lookaside
0x1c00f61bc  cmp     byte ptr [rdi+rbp+9], 0
0x1c00f61c1  jz      short loc_1C00F61D1
0x1c00f61c3  call    cs:__imp_ExDeleteNPagedLookasideList
0x1c00f61ca  nop     dword ptr [rax+rax+00h]
0x1c00f61cf  jmp     short loc_1C00F6210
0x1c00f61d1  call    cs:__imp_ExDeletePagedLookasideList
0x1c00f61d8  nop     dword ptr [rax+rax+00h]
0x1c00f61dd  jmp     short loc_1C00F6210
0x1c00f61df  lea     r12, [rdi+rbp]
0x1c00f61e3  jmp     short loc_1C00F61FA
0x1c00f61e5  xor     edx, edx; Tag
0x1c00f61e7  mov     rcx, rax; P
0x1c00f61ea  call    cs:__imp_ExFreePoolWithTag
0x1c00f61f1  nop     dword ptr [rax+rax+00h]
0x1c00f61f6  dec     dword ptr [rdi+rbp+50h]
0x1c00f61fa  lea     rcx, [r12+40h]; ListHead
0x1c00f61ff  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00f6206  nop     dword ptr [rax+rax+00h]
0x1c00f620b  test    rax, rax
0x1c00f620e  jnz     short loc_1C00F61E5
0x1c00f6210  inc     r14d
0x1c00f6213  add     rdi, 0C0h
0x1c00f621a  cmp     r14d, r15d
0x1c00f621d  jb      short loc_1C00F61A3
0x1c00f621f  mov     rcx, [rsi]; P
0x1c00f6222  xor     edx, edx; Tag
0x1c00f6224  call    cs:__imp_ExFreePoolWithTag
0x1c00f622b  nop     dword ptr [rax+rax+00h]
0x1c00f6230  and     qword ptr [rsi], 0
0x1c00f6234  inc     ebx
0x1c00f6236  add     rsi, 8
0x1c00f623a  cmp     ebx, 19h
0x1c00f623d  jb      loc_1C00F617F
0x1c00f6243  mov     cs:?LookasideListsInitialized@@3EA, 0; uchar LookasideListsInitialized
0x1c00f624a  mov     rbx, [rsp+38h+arg_0]
0x1c00f624f  mov     rbp, [rsp+38h+arg_8]
0x1c00f6254  mov     rsi, [rsp+38h+arg_10]
0x1c00f6259  mov     rdi, [rsp+38h+arg_18]
0x1c00f625e  add     rsp, 20h
0x1c00f6262  pop     r15
0x1c00f6264  pop     r14
0x1c00f6266  pop     r12
0x1c00f6268  retn
```
