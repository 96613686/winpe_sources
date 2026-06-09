# SECTION_GROUP_TABLE::GetFullyQualifiedName(STRU *)

- ea: `0x18000af60`
- end: `0x18000b07e`
- name: `?GetFullyQualifiedName@SECTION_GROUP_TABLE@@AEAAJPEAVSTRU@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(SECTION_GROUP_TABLE *__hidden this, struct STRU *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002c078`
- `0x18002c840`

## callees

- `0x18000af60`
- `0x18000b8cc`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b051`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b051`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000afac`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000afac`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000afe8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000afe8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b00d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b00d`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000aff7`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000aff7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000b035`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000b035`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000afb5`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000afb5`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000b021`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000b021`

## pseudocode

```c
__int64 __fastcall SECTION_GROUP_TABLE::GetFullyQualifiedName(SECTION_GROUP_TABLE *this, struct STRU *a2)
{
  const unsigned __int16 **v4; // r8
  const unsigned __int16 *v5; // rdx
  int v6; // edi
  _BYTE v8[64]; // [rsp+20h] [rbp-D8h] BYREF
  unsigned __int16 v9[64]; // [rsp+60h] [rbp-98h] BYREF

  memset_0(v9, 0, sizeof(v9));
  STRU::STRU((STRU *)v8, v9, 0x40u);
  STRU::Reset(a2);
  while ( this && !SMALL_STRU::IsEmpty((SECTION_GROUP_TABLE *)((char *)this + 40)) )
  {
    v5 = &szDomain;
    if ( *v4 )
      v5 = *v4;
    v6 = STRU::Copy((STRU *)v8, v5);
    if ( v6 < 0 )
      goto LABEL_13;
    if ( !STRU::IsEmpty(a2) )
    {
      v6 = STRU::Append((STRU *)v8, L"/");
      if ( v6 < 0 )
        goto LABEL_13;
      v6 = STRU::Append((STRU *)v8, a2);
      if ( v6 < 0 )
        goto LABEL_13;
    }
    v6 = STRU::Copy(a2, (const struct STRU *)v8);
    if ( v6 < 0 )
      goto LABEL_13;
    this = (SECTION_GROUP_TABLE *)*((_QWORD *)this + 7);
  }
  v6 = 0;
LABEL_13:
  STRU::~STRU((STRU *)v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000af60  mov     [rsp+arg_10], rbx
0x18000af65  mov     [rsp+arg_18], rsi
0x18000af6a  push    rdi
0x18000af6b  sub     rsp, 0F0h
0x18000af72  mov     rax, cs:__security_cookie
0x18000af79  xor     rax, rsp
0x18000af7c  mov     [rsp+0F8h+var_18], rax
0x18000af84  mov     rsi, rdx
0x18000af87  mov     rbx, rcx
0x18000af8a  xor     edx, edx; Val
0x18000af8c  lea     rcx, [rsp+0F8h+var_98]; void *
0x18000af91  mov     r8d, 80h; Size
0x18000af97  call    memset_0
0x18000af9c  mov     r8d, 40h ; '@'
0x18000afa2  lea     rdx, [rsp+0F8h+var_98]
0x18000afa7  lea     rcx, [rsp+0F8h+var_D8]
0x18000afac  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000afb2  mov     rcx, rsi
0x18000afb5  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000afbb  test    rbx, rbx
0x18000afbe  jz      loc_18000B04A
0x18000afc4  lea     r8, [rbx+28h]
0x18000afc8  mov     rcx, r8; this
0x18000afcb  call    ?IsEmpty@SMALL_STRU@@QEBA_NXZ; SMALL_STRU::IsEmpty(void)
0x18000afd0  test    al, al
0x18000afd2  jnz     short loc_18000B04A
0x18000afd4  cmp     qword ptr [r8], 0
0x18000afd8  lea     rdx, szDomain
0x18000afdf  lea     rcx, [rsp+0F8h+var_D8]
0x18000afe4  cmovnz  rdx, [r8]
0x18000afe8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000afee  mov     edi, eax
0x18000aff0  test    eax, eax
0x18000aff2  js      short loc_18000B04C
0x18000aff4  mov     rcx, rsi
0x18000aff7  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000affd  test    al, al
0x18000afff  jnz     short loc_18000B02D
0x18000b001  lea     rdx, asc_18005F044; "/"
0x18000b008  lea     rcx, [rsp+0F8h+var_D8]
0x18000b00d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000b013  lea     rcx, [rsp+0F8h+var_D8]
0x18000b018  mov     edi, eax
0x18000b01a  test    eax, eax
0x18000b01c  js      short loc_18000B051
0x18000b01e  mov     rdx, rsi
0x18000b021  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000b027  mov     edi, eax
0x18000b029  test    eax, eax
0x18000b02b  js      short loc_18000B04C
0x18000b02d  lea     rdx, [rsp+0F8h+var_D8]
0x18000b032  mov     rcx, rsi
0x18000b035  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000b03b  mov     edi, eax
0x18000b03d  test    eax, eax
0x18000b03f  js      short loc_18000B04C
0x18000b041  mov     rbx, [rbx+38h]
0x18000b045  jmp     loc_18000AFBB
0x18000b04a  xor     edi, edi
0x18000b04c  lea     rcx, [rsp+0F8h+var_D8]
0x18000b051  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b057  mov     eax, edi
0x18000b059  mov     rcx, [rsp+0F8h+var_18]
0x18000b061  xor     rcx, rsp; StackCookie
0x18000b064  call    __security_check_cookie
0x18000b069  lea     r11, [rsp+0F8h+var_8]
0x18000b071  mov     rbx, [r11+20h]
0x18000b075  mov     rsi, [r11+28h]
0x18000b079  mov     rsp, r11
0x18000b07c  pop     rdi
0x18000b07d  retn
```
