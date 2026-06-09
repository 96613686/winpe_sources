# CEXTLOG::BuildCustomLogHeader(ulong,LOG_PROPERTY_INFO * *,char const *,char const *,STR &)

- ea: `0x180003b68`
- end: `0x180003cd0`
- name: `?BuildCustomLogHeader@CEXTLOG@@AEAAXKPEAPEAULOG_PROPERTY_INFO@@PEBD1AEAVSTR@@@Z`
- size: `360`
- prototype: `void __fastcall(CEXTLOG *__hidden this, unsigned int, struct LOG_PROPERTY_INFO **, const char *, const char *Src, struct STR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006730`

## callees

- `0x180003b68`
- `0x18000ec56`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180003bde`
- `msvcrt!sprintf_s` at `0x180003bde`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180003c67`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180003c81`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180003c67`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180003c81`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180003cc9`
- `IisRTL!?Append@STR@@QEAAXD@Z` at `0x180003c93`
- `IisRTL!?Append@STR@@QEAAXD@Z` at `0x180003c93`
- `IisRTL!?Append@STR@@QEAAHAEBV1@@Z` at `0x180003ca4`
- `IisRTL!?Append@STR@@QEAAHAEBV1@@Z` at `0x180003ca4`

## string_xrefs

- `0x180003bc1`: `Internet Information Services`

## pseudocode

```c
void __fastcall CEXTLOG::BuildCustomLogHeader(
        CEXTLOG *this,
        unsigned int a2,
        struct LOG_PROPERTY_INFO **a3,
        const char *a4,
        const char *Src,
        struct STR *a6)
{
  __int64 v6; // rbp
  __int64 v10; // rax
  __int64 v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 i; // rdi

  v6 = -1;
  v10 = -1;
  v11 = *((_QWORD *)a6 + 4);
  do
    ++v10;
  while ( a4[v10] );
  v12 = sprintf_s(
          *((char *const *)a6 + 4),
          *((unsigned int *)a6 + 10),
          "#Software: Microsoft %s %d.%d\r\n#Version: %s\r\n#Date: %s %s\r\n",
          "Internet Information Services",
          10,
          0,
          "1.0",
          a4,
          &a4[v10 + 1]);
  v13 = v12;
  if ( Src && *Src )
  {
    if ( *Src != 35 )
    {
      *(_BYTE *)(v12 + v11) = 35;
      LODWORD(v13) = v12 + 1;
    }
    do
      ++v6;
    while ( Src[v6] );
    memcpy_0((void *)(v11 + (unsigned int)v13), Src, (unsigned int)v6);
    v14 = (unsigned int)(v13 + v6);
    *(_BYTE *)(v14 + v11) = 13;
    *(_BYTE *)((unsigned int)(v14 + 1) + v11) = 10;
    v13 = (unsigned int)(v14 + 2);
  }
  strcpy((char *)(v13 + v11), "#Fields:");
  v15 = (unsigned int)(v13 + 8);
  if ( (unsigned int)v15 < *((_DWORD *)a6 + 10) )
  {
    *(_BYTE *)(v15 + *((_QWORD *)a6 + 4)) = 0;
    *((_DWORD *)a6 + 12) = v15;
  }
  if ( (*((_BYTE *)this + 1576) & 1) != 0 )
    STR::Append(a6, " date");
  if ( (*((_BYTE *)this + 1576) & 2) != 0 )
    STR::Append(a6, " time");
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    STR::Append(a6, 32);
    STR::Append(a6, (struct LOG_PROPERTY_INFO *)((char *)a3[i] + 72));
  }
  STR::Append(a6, "\r\n");
}

```

## disassembly

```asm
0x180003b68  push    rbx
0x180003b6a  push    rbp
0x180003b6b  push    rsi
0x180003b6c  push    rdi
0x180003b6d  push    r12
0x180003b6f  push    r14
0x180003b71  push    r15
0x180003b73  sub     rsp, 50h
0x180003b77  mov     rbx, [rsp+88h+arg_28]
0x180003b7f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180003b83  mov     r15d, edx
0x180003b86  mov     r12, r8
0x180003b89  mov     r14, rcx
0x180003b8c  mov     rax, rbp
0x180003b8f  mov     rsi, [rbx+20h]
0x180003b93  mov     edx, [rbx+28h]; BufferCount
0x180003b96  inc     rax
0x180003b99  cmp     byte ptr [r9+rax], 0
0x180003b9e  jnz     short loc_180003B96
0x180003ba0  inc     rax
0x180003ba3  lea     r8, aSoftwareMicros_1; "#Software: Microsoft %s %d.%d\r\n#Versi"...
0x180003baa  add     rax, r9
0x180003bad  mov     rcx, rsi; Buffer
0x180003bb0  mov     [rsp+88h+var_48], rax
0x180003bb5  lea     rax, a10; "1.0"
0x180003bbc  mov     [rsp+88h+var_50], r9
0x180003bc1  lea     r9, aInternetInform; "Internet Information Services"
0x180003bc8  mov     [rsp+88h+var_58], rax
0x180003bcd  mov     [rsp+88h+var_60], 0
0x180003bd6  mov     [rsp+88h+var_68], 0Ah
0x180003bde  call    cs:__imp_sprintf_s
0x180003be4  mov     rdx, [rsp+88h+Src]; Src
0x180003bec  mov     edi, eax
0x180003bee  test    rdx, rdx
0x180003bf1  jz      short loc_180003C29
0x180003bf3  mov     al, [rdx]
0x180003bf5  test    al, al
0x180003bf7  jz      short loc_180003C29
0x180003bf9  cmp     al, 23h ; '#'
0x180003bfb  jz      short loc_180003C03
0x180003bfd  mov     byte ptr [rdi+rsi], 23h ; '#'
0x180003c01  inc     edi
0x180003c03  inc     rbp
0x180003c06  cmp     byte ptr [rdx+rbp], 0
0x180003c0a  jnz     short loc_180003C03
0x180003c0c  mov     ecx, edi
0x180003c0e  add     rcx, rsi; void *
0x180003c11  mov     r8d, ebp; Size
0x180003c14  call    memcpy_0
0x180003c19  lea     ecx, [rdi+rbp]
0x180003c1c  lea     edi, [rcx+1]
0x180003c1f  mov     byte ptr [rcx+rsi], 0Dh
0x180003c23  mov     byte ptr [rdi+rsi], 0Ah
0x180003c27  inc     edi
0x180003c29  movsd   xmm0, qword ptr cs:aFields; "#Fields:"
0x180003c31  movsd   qword ptr [rdi+rsi], xmm0
0x180003c36  mov     al, byte ptr cs:aFields+8; ""
0x180003c3c  mov     [rdi+rsi+8], al
0x180003c40  add     edi, 8
0x180003c43  cmp     edi, [rbx+28h]
0x180003c46  jnb     short loc_180003C53
0x180003c48  mov     rax, [rbx+20h]
0x180003c4c  mov     byte ptr [rdi+rax], 0
0x180003c50  mov     [rbx+30h], edi
0x180003c53  test    byte ptr [r14+628h], 1
0x180003c5b  jz      short loc_180003C6D
0x180003c5d  lea     rdx, aDate_1; " date"
0x180003c64  mov     rcx, rbx
0x180003c67  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180003c6d  test    byte ptr [r14+628h], 2
0x180003c75  jz      short loc_180003C87
0x180003c77  lea     rdx, aTime_0; " time"
0x180003c7e  mov     rcx, rbx
0x180003c81  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180003c87  xor     edi, edi
0x180003c89  test    r15d, r15d
0x180003c8c  jz      short loc_180003CB1
0x180003c8e  mov     dl, 20h ; ' '
0x180003c90  mov     rcx, rbx
0x180003c93  call    cs:__imp_?Append@STR@@QEAAXD@Z; STR::Append(char)
0x180003c99  mov     rdx, [r12+rdi*8]
0x180003c9d  mov     rcx, rbx
0x180003ca0  add     rdx, 48h ; 'H'
0x180003ca4  call    cs:__imp_?Append@STR@@QEAAHAEBV1@@Z; STR::Append(STR const &)
0x180003caa  inc     edi
0x180003cac  cmp     edi, r15d
0x180003caf  jb      short loc_180003C8E
0x180003cb1  lea     rdx, asc_1800135EC; "\r\n"
0x180003cb8  mov     rcx, rbx
0x180003cbb  add     rsp, 50h
0x180003cbf  pop     r15
0x180003cc1  pop     r14
0x180003cc3  pop     r12
0x180003cc5  pop     rdi
0x180003cc6  pop     rsi
0x180003cc7  pop     rbp
0x180003cc8  pop     rbx
0x180003cc9  jmp     cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
```
