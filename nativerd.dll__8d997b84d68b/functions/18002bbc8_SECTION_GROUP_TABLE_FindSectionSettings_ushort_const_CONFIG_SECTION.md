# SECTION_GROUP_TABLE::FindSectionSettings(ushort const *,CONFIG_SECTION * *)

- ea: `0x18002bbc8`
- end: `0x18002bd5e`
- name: `?FindSectionSettings@SECTION_GROUP_TABLE@@QEAAJPEBGPEAPEAVCONFIG_SECTION@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(SECTION_GROUP_TABLE *__hidden this, const unsigned __int16 *, struct CONFIG_SECTION **)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180024130`
- `0x180024780`
- `0x18002bbc8`
- `0x18003ada4`

## callees

- `0x180018edc`
- `0x180025f44`
- `0x18002baf0`
- `0x18002bb54`
- `0x18002bbc8`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002bc45`
- `msvcrt!wcsstr` at `0x18002bc45`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002bd33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002bd33`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bc8f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bcca`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bc8f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002bcca`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002bc23`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002bc23`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bc5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002bc5b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002bc76`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002bc76`

## pseudocode

```c
__int64 __fastcall SECTION_GROUP_TABLE::FindSectionSettings(
        SECTION_GROUP_TABLE *this,
        const unsigned __int16 *a2,
        struct CONFIG_SECTION **a3)
{
  SECTION_GROUP_TABLE *v6; // rsi
  volatile signed __int32 *v7; // rdi
  wchar_t *v8; // rax
  const unsigned __int16 *v9; // rdi
  int SectionSettings; // ebx
  unsigned __int16 *Str; // rax
  CONFIG_SECTION_TABLE *v12; // rbx
  const unsigned __int16 *v13; // rax
  SECTION_GROUP_TABLE *v15; // [rsp+20h] [rbp-A9h] BYREF
  CONFIG_SECTION *v16; // [rsp+28h] [rbp-A1h] BYREF
  _BYTE v17[64]; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int16 v18[64]; // [rsp+70h] [rbp-59h] BYREF

  v6 = 0;
  v7 = 0;
  v15 = 0;
  v16 = 0;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v17, v18, 0x40u);
  if ( !a2 || !a3 )
  {
    SectionSettings = -2147024809;
    goto LABEL_15;
  }
  v8 = wcsstr(a2, L"/");
  v9 = v8;
  if ( v8 )
  {
    SectionSettings = STRU::Copy((STRU *)v17, a2, v8 - a2);
    if ( SectionSettings < 0 )
      goto LABEL_19;
    ++v9;
  }
  else
  {
    SectionSettings = STRU::Copy((STRU *)v17, a2);
    if ( SectionSettings < 0 )
      goto LABEL_19;
  }
  Str = STRU::QueryStr((STRU *)v17);
  if ( (int)CONFIG_HASH<SECTION_GROUP_TABLE>::Find((char *)this + 96, Str, &v15) < 0 )
  {
    v12 = (CONFIG_SECTION_TABLE *)*((_QWORD *)this + 4);
    v13 = STRU::QueryStr((STRU *)v17);
    if ( (int)CONFIG_SECTION_TABLE::FindSection(v12, v13, &v16) < 0 || v9 )
    {
      v6 = v15;
      SectionSettings = -2147023728;
      v7 = (volatile signed __int32 *)v16;
    }
    else
    {
      v7 = (volatile signed __int32 *)v16;
      *a3 = v16;
      _InterlockedIncrement(v7 + 6);
      v6 = v15;
      SectionSettings = 0;
    }
LABEL_15:
    if ( v7 )
      CONFIG_SECTION::DereferenceConfigSection((CONFIG_SECTION *)v7);
    goto LABEL_17;
  }
  v6 = v15;
  SectionSettings = SECTION_GROUP_TABLE::FindSectionSettings(v15, v9, a3);
LABEL_17:
  if ( v6 )
    SECTION_GROUP_TABLE::DereferenceSectionGroupTable(v6);
LABEL_19:
  STRU::~STRU((STRU *)v17);
  return (unsigned int)SectionSettings;
}

```

## disassembly

```asm
0x18002bbc8  mov     [rsp-8+arg_18], rbx
0x18002bbcd  push    rbp
0x18002bbce  push    rsi
0x18002bbcf  push    rdi
0x18002bbd0  push    r14
0x18002bbd2  push    r15
0x18002bbd4  lea     rbp, [rsp-37h]
0x18002bbd9  sub     rsp, 100h
0x18002bbe0  mov     rax, cs:__security_cookie
0x18002bbe7  xor     rax, rsp
0x18002bbea  mov     [rbp+57h+var_30], rax
0x18002bbee  mov     r14, r8
0x18002bbf1  mov     rbx, rdx
0x18002bbf4  mov     r15, rcx
0x18002bbf7  xor     esi, esi
0x18002bbf9  xor     edi, edi
0x18002bbfb  mov     [rsp+120h+var_100], rsi
0x18002bc00  xor     edx, edx; Val
0x18002bc02  mov     [rsp+120h+var_F8], rdi
0x18002bc07  mov     r8d, 80h; Size
0x18002bc0d  lea     rcx, [rbp+57h+var_B0]; void *
0x18002bc11  call    memset_0
0x18002bc16  lea     r8d, [rsi+40h]
0x18002bc1a  lea     rdx, [rbp+57h+var_B0]
0x18002bc1e  lea     rcx, [rsp+120h+var_F0]
0x18002bc23  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002bc29  test    rbx, rbx
0x18002bc2c  jz      loc_18002BD0F
0x18002bc32  test    r14, r14
0x18002bc35  jz      loc_18002BD0F
0x18002bc3b  lea     rdx, asc_18005F044; "/"
0x18002bc42  mov     rcx, rbx; Str
0x18002bc45  call    cs:__imp_wcsstr
0x18002bc4b  mov     rdx, rbx
0x18002bc4e  lea     rcx, [rsp+120h+var_F0]
0x18002bc53  mov     rdi, rax
0x18002bc56  test    rax, rax
0x18002bc59  jnz     short loc_18002BC6D
0x18002bc5b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002bc61  mov     ebx, eax
0x18002bc63  test    eax, eax
0x18002bc65  js      loc_18002BD2E
0x18002bc6b  jmp     short loc_18002BC8A
0x18002bc6d  mov     r8, rdi
0x18002bc70  sub     r8, rbx
0x18002bc73  sar     r8, 1
0x18002bc76  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002bc7c  mov     ebx, eax
0x18002bc7e  test    eax, eax
0x18002bc80  js      loc_18002BD2E
0x18002bc86  add     rdi, 2
0x18002bc8a  lea     rcx, [rsp+120h+var_F0]
0x18002bc8f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002bc95  mov     rdx, rax
0x18002bc98  lea     rcx, [r15+60h]
0x18002bc9c  lea     r8, [rsp+120h+var_100]
0x18002bca1  call    ?Find@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEBGPEAPEAVSECTION_GROUP_TABLE@@H@Z; CONFIG_HASH<SECTION_GROUP_TABLE>::Find(ushort const *,SECTION_GROUP_TABLE * *,int)
0x18002bca6  test    eax, eax
0x18002bca8  js      short loc_18002BCC1
0x18002bcaa  mov     rsi, [rsp+120h+var_100]
0x18002bcaf  mov     r8, r14; struct CONFIG_SECTION **
0x18002bcb2  mov     rcx, rsi; this
0x18002bcb5  mov     rdx, rdi; unsigned __int16 *
0x18002bcb8  call    ?FindSectionSettings@SECTION_GROUP_TABLE@@QEAAJPEBGPEAPEAVCONFIG_SECTION@@@Z; SECTION_GROUP_TABLE::FindSectionSettings(ushort const *,CONFIG_SECTION * *)
0x18002bcbd  mov     ebx, eax
0x18002bcbf  jmp     short loc_18002BD21
0x18002bcc1  mov     rbx, [r15+20h]
0x18002bcc5  lea     rcx, [rsp+120h+var_F0]
0x18002bcca  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002bcd0  lea     r8, [rsp+120h+var_F8]; struct CONFIG_SECTION **
0x18002bcd5  mov     rcx, rbx; this
0x18002bcd8  mov     rdx, rax; unsigned __int16 *
0x18002bcdb  call    ?FindSection@CONFIG_SECTION_TABLE@@QEAAJPEBGPEAPEAVCONFIG_SECTION@@@Z; CONFIG_SECTION_TABLE::FindSection(ushort const *,CONFIG_SECTION * *)
0x18002bce0  test    eax, eax
0x18002bce2  js      short loc_18002BCFE
0x18002bce4  test    rdi, rdi
0x18002bce7  jnz     short loc_18002BCFE
0x18002bce9  mov     rdi, [rsp+120h+var_F8]
0x18002bcee  mov     [r14], rdi
0x18002bcf1  lock inc dword ptr [rdi+18h]
0x18002bcf5  mov     rsi, [rsp+120h+var_100]
0x18002bcfa  xor     ebx, ebx
0x18002bcfc  jmp     short loc_18002BD14
0x18002bcfe  mov     rsi, [rsp+120h+var_100]
0x18002bd03  mov     ebx, 80070490h
0x18002bd08  mov     rdi, [rsp+120h+var_F8]
0x18002bd0d  jmp     short loc_18002BD14
0x18002bd0f  mov     ebx, 80070057h
0x18002bd14  test    rdi, rdi
0x18002bd17  jz      short loc_18002BD21
0x18002bd19  mov     rcx, rdi; this
0x18002bd1c  call    ?DereferenceConfigSection@CONFIG_SECTION@@QEAAXXZ; CONFIG_SECTION::DereferenceConfigSection(void)
0x18002bd21  test    rsi, rsi
0x18002bd24  jz      short loc_18002BD2E
0x18002bd26  mov     rcx, rsi; this
0x18002bd29  call    ?DereferenceSectionGroupTable@SECTION_GROUP_TABLE@@QEAAXXZ; SECTION_GROUP_TABLE::DereferenceSectionGroupTable(void)
0x18002bd2e  lea     rcx, [rsp+120h+var_F0]
0x18002bd33  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002bd39  mov     eax, ebx
0x18002bd3b  mov     rcx, [rbp+57h+var_30]
0x18002bd3f  xor     rcx, rsp; StackCookie
0x18002bd42  call    __security_check_cookie
0x18002bd47  mov     rbx, [rsp+120h+arg_18]
0x18002bd4f  add     rsp, 100h
0x18002bd56  pop     r15
0x18002bd58  pop     r14
0x18002bd5a  pop     rdi
0x18002bd5b  pop     rsi
0x18002bd5c  pop     rbp
0x18002bd5d  retn
```
