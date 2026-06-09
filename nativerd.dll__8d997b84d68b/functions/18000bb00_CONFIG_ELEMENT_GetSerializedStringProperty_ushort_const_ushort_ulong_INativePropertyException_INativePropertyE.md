# CONFIG_ELEMENT::GetSerializedStringProperty(ushort const *,ushort *,ulong *,INativePropertyException * *,INativePropertyExtendedInfo * *)

- ea: `0x18000bb00`
- end: `0x18000bc82`
- name: `?GetSerializedStringProperty@CONFIG_ELEMENT@@UEAAJPEBGPEAGPEAKPEAPEAVINativePropertyException@@PEAPEAVINativePropertyExtendedInfo@@@Z`
- size: `386`
- prototype: `int(CONFIG_ELEMENT *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *, struct INativePropertyException **, struct INativePropertyExtendedInfo **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000bb00`
- `0x18000c3f0`
- `0x18001c250`
- `0x18001d504`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18000bbfd`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x18000bbfd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bc58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bc58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bb6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bb6b`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000bbab`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000bbab`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::GetSerializedStringProperty(
        CONFIG_ELEMENT *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct INativePropertyException **a5,
        struct INativePropertyExtendedInfo **a6)
{
  int AttributeEntry; // eax
  struct ATTRIBUTE_ENTRY *v11; // rsi
  unsigned int v12; // ebx
  ATTRIBUTE_VALUE *v13; // rcx
  struct VALIDATION_EXCEPTION *Exception; // rax
  struct INativePropertyException *v15; // rcx
  struct INativePropertyExtendedInfo *v16; // rax
  int v17; // ecx
  struct ATTRIBUTE_ENTRY *v19; // [rsp+20h] [rbp-288h] BYREF
  _BYTE v20[56]; // [rsp+28h] [rbp-280h] BYREF
  unsigned __int16 v21[256]; // [rsp+60h] [rbp-248h] BYREF

  v19 = 0;
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v20, v21, 0x100u);
  AttributeEntry = CONFIG_ELEMENT::GetAttributeEntry(
                     (CONFIG_ELEMENT *)((char *)this - 16),
                     a2,
                     &v19,
                     (struct STRU *)v20);
  v11 = v19;
  v12 = AttributeEntry;
  if ( AttributeEntry >= 0 )
  {
    if ( *(_QWORD *)v19 )
    {
      if ( a5 && ATTRIBUTE_VALUE::QueryException(*(ATTRIBUTE_VALUE **)v19) )
      {
        Exception = ATTRIBUTE_VALUE::QueryException(v13);
        v15 = (struct INativePropertyException *)(((unsigned __int64)Exception + 16) & -(__int64)(Exception != 0));
        *a5 = v15;
        (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v15 + 8LL))(v15);
      }
      goto LABEL_10;
    }
    v12 = -2147024809;
  }
  else if ( AttributeEntry == -2147023483 && (*(_BYTE *)(*((_QWORD *)this + 8) + 128LL) & 1) != 0 )
  {
    STRU::Reset((STRU *)v20);
LABEL_10:
    v12 = STRU::CopyToBuffer((STRU *)v20, a3, a4);
  }
  if ( v11 && a6 )
  {
    while ( 1 )
    {
      v16 = (struct INativePropertyExtendedInfo *)operator new(0x18u);
      if ( v16 )
        break;
      *a6 = 0;
      v12 = -2147024888;
    }
    v17 = *((_DWORD *)v11 + 2);
    *(_QWORD *)v16 = &NATIVE_PROPERTY_EXTENDED_INFO::`vftable';
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = -__CFSHR__(v17, 2);
    *((_DWORD *)v16 + 4) = -(v17 & 1);
    *a6 = v16;
  }
  STRU::~STRU((STRU *)v20);
  return v12;
}

```

## disassembly

```asm
0x18000bb00  push    rbx
0x18000bb02  push    rbp
0x18000bb03  push    rsi
0x18000bb04  push    rdi
0x18000bb05  push    r12
0x18000bb07  push    r14
0x18000bb09  push    r15
0x18000bb0b  sub     rsp, 270h
0x18000bb12  mov     rax, cs:__security_cookie
0x18000bb19  xor     rax, rsp
0x18000bb1c  mov     [rsp+2A8h+var_48], rax
0x18000bb24  mov     r14, [rsp+2A8h+arg_20]
0x18000bb2c  mov     r15, r8
0x18000bb2f  mov     rdi, [rsp+2A8h+arg_28]
0x18000bb37  mov     rbx, rdx
0x18000bb3a  mov     rbp, rcx
0x18000bb3d  mov     [rsp+2A8h+var_288], 0
0x18000bb46  xor     edx, edx; Val
0x18000bb48  lea     rcx, [rsp+2A8h+var_248]; void *
0x18000bb4d  mov     r8d, 200h; Size
0x18000bb53  mov     r12, r9
0x18000bb56  call    memset_0
0x18000bb5b  mov     r8d, 100h
0x18000bb61  lea     rdx, [rsp+2A8h+var_248]
0x18000bb66  lea     rcx, [rsp+2A8h+var_280]
0x18000bb6b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bb71  lea     rcx, [rbp-10h]; this
0x18000bb75  mov     rdx, rbx; unsigned __int16 *
0x18000bb78  lea     r9, [rsp+2A8h+var_280]; struct STRU *
0x18000bb7d  lea     r8, [rsp+2A8h+var_288]; struct ATTRIBUTE_ENTRY **
0x18000bb82  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x18000bb87  mov     rsi, [rsp+2A8h+var_288]
0x18000bb8c  mov     ebx, eax
0x18000bb8e  test    eax, eax
0x18000bb90  jns     short loc_18000BBB3
0x18000bb92  cmp     eax, 80070585h
0x18000bb97  jnz     short loc_18000BC05
0x18000bb99  mov     rcx, [rbp+40h]
0x18000bb9d  test    byte ptr [rcx+80h], 1
0x18000bba4  jz      short loc_18000BC05
0x18000bba6  lea     rcx, [rsp+2A8h+var_280]
0x18000bbab  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000bbb1  jmp     short loc_18000BBF2
0x18000bbb3  mov     rcx, [rsi]; this
0x18000bbb6  test    rcx, rcx
0x18000bbb9  jnz     short loc_18000BBC2
0x18000bbbb  mov     ebx, 80070057h
0x18000bbc0  jmp     short loc_18000BC05
0x18000bbc2  test    r14, r14
0x18000bbc5  jz      short loc_18000BBF2
0x18000bbc7  call    ?QueryException@ATTRIBUTE_VALUE@@QEBAPEAVVALIDATION_EXCEPTION@@XZ; ATTRIBUTE_VALUE::QueryException(void)
0x18000bbcc  test    rax, rax
0x18000bbcf  jz      short loc_18000BBF2
0x18000bbd1  call    ?QueryException@ATTRIBUTE_VALUE@@QEBAPEAVVALIDATION_EXCEPTION@@XZ; ATTRIBUTE_VALUE::QueryException(void)
0x18000bbd6  lea     r9, [rax+10h]
0x18000bbda  neg     rax
0x18000bbdd  sbb     rcx, rcx
0x18000bbe0  and     rcx, r9
0x18000bbe3  mov     [r14], rcx
0x18000bbe6  mov     rax, [rcx]
0x18000bbe9  mov     rax, [rax+8]
0x18000bbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf2  mov     r8, r12
0x18000bbf5  lea     rcx, [rsp+2A8h+var_280]
0x18000bbfa  mov     rdx, r15
0x18000bbfd  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18000bc03  mov     ebx, eax
0x18000bc05  test    rsi, rsi
0x18000bc08  jz      short loc_18000BC53
0x18000bc0a  test    rdi, rdi
0x18000bc0d  jz      short loc_18000BC53
0x18000bc0f  mov     ecx, 18h; Size
0x18000bc14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc19  mov     rdx, rax
0x18000bc1c  test    rax, rax
0x18000bc1f  jnz     short loc_18000BC2B
0x18000bc21  mov     [rdi], rax
0x18000bc24  mov     ebx, 80070008h
0x18000bc29  jmp     short loc_18000BC0F
0x18000bc2b  mov     ecx, [rsi+8]
0x18000bc2e  lea     rax, ??_7NATIVE_PROPERTY_EXTENDED_INFO@@6B@; const NATIVE_PROPERTY_EXTENDED_INFO::`vftable'
0x18000bc35  mov     [rdx], rax
0x18000bc38  mov     eax, ecx
0x18000bc3a  shr     eax, 2
0x18000bc3d  mov     dword ptr [rdx+8], 1
0x18000bc44  sbb     eax, eax
0x18000bc46  shr     ecx, 1
0x18000bc48  mov     [rdx+0Ch], eax
0x18000bc4b  sbb     ecx, ecx
0x18000bc4d  mov     [rdx+10h], ecx
0x18000bc50  mov     [rdi], rdx
0x18000bc53  lea     rcx, [rsp+2A8h+var_280]
0x18000bc58  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bc5e  mov     eax, ebx
0x18000bc60  mov     rcx, [rsp+2A8h+var_48]
0x18000bc68  xor     rcx, rsp; StackCookie
0x18000bc6b  call    __security_check_cookie
0x18000bc70  add     rsp, 270h
0x18000bc77  pop     r15
0x18000bc79  pop     r14
0x18000bc7b  pop     r12
0x18000bc7d  pop     rdi
0x18000bc7e  pop     rsi
0x18000bc7f  pop     rbp
0x18000bc80  pop     rbx
0x18000bc81  retn
```
