# CONFIG_MAPPING_EXTENSION::GetSiteNameFromSiteId(ulong,ushort *,ulong *,INativeSectionException * *)

- ea: `0x180040960`
- end: `0x180040a3e`
- name: `?GetSiteNameFromSiteId@CONFIG_MAPPING_EXTENSION@@UEAAJKPEAGPEAKPEAPEAVINativeSectionException@@@Z`
- size: `222`
- prototype: `__int64 __usercall@<rax>(CONFIG_MAPPING_EXTENSION *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int *@<r9>, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18001e678`
- `0x180040878`
- `0x180040960`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x1800409e9`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x1800409e9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180040a18`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180040a18`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800409be`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800409be`

## pseudocode

```c
__int64 __fastcall CONFIG_MAPPING_EXTENSION::GetSiteNameFromSiteId(
        CONFIG_MAPPING_EXTENSION *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct INativeSectionException **a5)
{
  int SiteNameFromSiteId; // ebx
  CONFIG_EXCEPTION *v10; // rcx
  struct CONFIG_EXCEPTION *v12; // [rsp+20h] [rbp-278h] BYREF
  _BYTE v13[56]; // [rsp+28h] [rbp-270h] BYREF
  unsigned __int16 v14[256]; // [rsp+60h] [rbp-238h] BYREF

  v12 = 0;
  memset_0(v14, 0, sizeof(v14));
  STRU::STRU((STRU *)v13, v14, 0x100u);
  SiteNameFromSiteId = CONFIG_MAPPING_EXTENSION::GetSiteNameFromSiteId(this, a2, (struct STRU *)v13, &v12);
  if ( SiteNameFromSiteId >= 0 )
    SiteNameFromSiteId = STRU::CopyToBuffer((STRU *)v13, a3, a4);
  v10 = v12;
  if ( v12 )
  {
    if ( a5 )
    {
      v10 = 0;
      *a5 = (struct CONFIG_EXCEPTION *)((char *)v12 + 24);
    }
    if ( v10 )
      CONFIG_EXCEPTION::DereferenceSectionException(v10);
  }
  STRU::~STRU((STRU *)v13);
  return (unsigned int)SiteNameFromSiteId;
}

```

## disassembly

```asm
0x180040960  push    rbx
0x180040962  push    rbp
0x180040963  push    rsi
0x180040964  push    rdi
0x180040965  push    r14
0x180040967  sub     rsp, 270h
0x18004096e  mov     rax, cs:__security_cookie
0x180040975  xor     rax, rsp
0x180040978  mov     [rsp+298h+var_38], rax
0x180040980  mov     rsi, [rsp+298h+arg_20]
0x180040988  mov     rbp, r8
0x18004098b  mov     edi, edx
0x18004098d  mov     [rsp+298h+var_278], 0
0x180040996  mov     rbx, rcx
0x180040999  xor     edx, edx; Val
0x18004099b  mov     r8d, 200h; Size
0x1800409a1  lea     rcx, [rsp+298h+var_238]; void *
0x1800409a6  mov     r14, r9
0x1800409a9  call    memset_0
0x1800409ae  mov     r8d, 100h
0x1800409b4  lea     rdx, [rsp+298h+var_238]
0x1800409b9  lea     rcx, [rsp+298h+var_270]
0x1800409be  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800409c4  lea     r9, [rsp+298h+var_278]; struct CONFIG_EXCEPTION **
0x1800409c9  mov     edx, edi; unsigned int
0x1800409cb  lea     r8, [rsp+298h+var_270]; struct STRU *
0x1800409d0  mov     rcx, rbx; this
0x1800409d3  call    ?GetSiteNameFromSiteId@CONFIG_MAPPING_EXTENSION@@AEAAJKPEAVSTRU@@PEAPEAVCONFIG_EXCEPTION@@@Z; CONFIG_MAPPING_EXTENSION::GetSiteNameFromSiteId(ulong,STRU *,CONFIG_EXCEPTION * *)
0x1800409d8  mov     ebx, eax
0x1800409da  test    eax, eax
0x1800409dc  js      short loc_1800409F1
0x1800409de  mov     r8, r14
0x1800409e1  lea     rcx, [rsp+298h+var_270]
0x1800409e6  mov     rdx, rbp
0x1800409e9  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x1800409ef  mov     ebx, eax
0x1800409f1  mov     rcx, [rsp+298h+var_278]
0x1800409f6  test    rcx, rcx
0x1800409f9  jz      short loc_180040A13
0x1800409fb  test    rsi, rsi
0x1800409fe  jz      short loc_180040A09
0x180040a00  lea     rax, [rcx+18h]
0x180040a04  xor     ecx, ecx; this
0x180040a06  mov     [rsi], rax
0x180040a09  test    rcx, rcx
0x180040a0c  jz      short loc_180040A13
0x180040a0e  call    ?DereferenceSectionException@CONFIG_EXCEPTION@@QEAAXXZ; CONFIG_EXCEPTION::DereferenceSectionException(void)
0x180040a13  lea     rcx, [rsp+298h+var_270]
0x180040a18  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180040a1e  mov     eax, ebx
0x180040a20  mov     rcx, [rsp+298h+var_38]
0x180040a28  xor     rcx, rsp; StackCookie
0x180040a2b  call    __security_check_cookie
0x180040a30  add     rsp, 270h
0x180040a37  pop     r14
0x180040a39  pop     rdi
0x180040a3a  pop     rsi
0x180040a3b  pop     rbp
0x180040a3c  pop     rbx
0x180040a3d  retn
```
