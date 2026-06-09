# CONFIG_PATH_MAPPER::SetPathMapping(PATH *,ushort const *,_ALLOW_DEFINITION_LEVEL)

- ea: `0x1800537b4`
- end: `0x1800538ba`
- name: `?SetPathMapping@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@PEBGW4_ALLOW_DEFINITION_LEVEL@@@Z`
- size: `262`
- prototype: `int __high(struct PATH *, const unsigned __int16 *, enum _ALLOW_DEFINITION_LEVEL)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003b880`
- `0x18004d910`

## callees

- `0x180015ee0`
- `0x18001bdf0`
- `0x1800537b4`
- `0x1800538c0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18005388b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005388b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053839`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180053839`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005380f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005380f`
- `iisutil!MakePathCanonicalizationProof` at `0x180053828`
- `iisutil!MakePathCanonicalizationProof` at `0x180053828`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::SetPathMapping(
        __int64 a1,
        PATH *a2,
        const unsigned __int16 *Str,
        unsigned int a4)
{
  int PathCanonicalizationProof; // ebx
  unsigned __int16 *v10; // [rsp+30h] [rbp-178h] BYREF
  _BYTE v11[56]; // [rsp+38h] [rbp-170h] BYREF
  unsigned __int16 v12[128]; // [rsp+70h] [rbp-138h] BYREF

  v10 = 0;
  memset_0(v12, 0, sizeof(v12));
  STRU::STRU((STRU *)v11, v12, 0x80u);
  if ( Str && *Str )
  {
    PathCanonicalizationProof = MakePathCanonicalizationProof(Str, (struct STRU *)v11);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_7;
    Str = STRU::QueryStr((STRU *)v11);
  }
  *(_DWORD *)(a1 + 188) = 1;
  PathCanonicalizationProof = PATH::GetPathString(a2, (const unsigned __int16 **)&v10);
  if ( PathCanonicalizationProof >= 0 )
    PathCanonicalizationProof = CONFIG_PATH_MAPPER::SetPathMapping(a1, v10, Str, a4, 0, 0);
LABEL_7:
  PATH::RevertString(a2);
  STRU::~STRU((STRU *)v11);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x1800537b4  mov     [rsp+arg_18], rbx
0x1800537b9  push    rbp
0x1800537ba  push    rsi
0x1800537bb  push    rdi
0x1800537bc  push    r14
0x1800537be  push    r15
0x1800537c0  sub     rsp, 180h
0x1800537c7  mov     rax, cs:__security_cookie
0x1800537ce  xor     rax, rsp
0x1800537d1  mov     [rsp+1A8h+var_38], rax
0x1800537d9  mov     rdi, r8
0x1800537dc  mov     rsi, rdx
0x1800537df  mov     rbp, rcx
0x1800537e2  xor     r15d, r15d
0x1800537e5  xor     edx, edx; Val
0x1800537e7  mov     [rsp+1A8h+var_178], r15
0x1800537ec  mov     r8d, 100h; Size
0x1800537f2  lea     rcx, [rsp+1A8h+var_138]; void *
0x1800537f7  mov     r14d, r9d
0x1800537fa  call    memset_0
0x1800537ff  mov     r8d, 80h
0x180053805  lea     rdx, [rsp+1A8h+var_138]
0x18005380a  lea     rcx, [rsp+1A8h+var_170]
0x18005380f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180053815  test    rdi, rdi
0x180053818  jz      short loc_180053842
0x18005381a  cmp     [rdi], r15w
0x18005381e  jz      short loc_180053842
0x180053820  lea     rdx, [rsp+1A8h+var_170]
0x180053825  mov     rcx, rdi
0x180053828  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18005382e  mov     ebx, eax
0x180053830  test    eax, eax
0x180053832  js      short loc_18005387E
0x180053834  lea     rcx, [rsp+1A8h+var_170]
0x180053839  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18005383f  mov     rdi, rax
0x180053842  lea     rdx, [rsp+1A8h+var_178]; unsigned __int16 **
0x180053847  mov     dword ptr [rbp+0BCh], 1
0x180053851  mov     rcx, rsi; this
0x180053854  call    ?GetPathString@PATH@@QEAAJPEAPEBG@Z; PATH::GetPathString(ushort const * *)
0x180053859  mov     ebx, eax
0x18005385b  test    eax, eax
0x18005385d  js      short loc_18005387E
0x18005385f  mov     rdx, [rsp+1A8h+var_178]
0x180053864  mov     r9d, r14d
0x180053867  mov     [rsp+1A8h+var_180], r15
0x18005386c  mov     r8, rdi
0x18005386f  mov     rcx, rbp
0x180053872  mov     [rsp+1A8h+var_188], r15d
0x180053877  call    ?SetPathMapping@CONFIG_PATH_MAPPER@@QEAAJPEBG0W4_ALLOW_DEFINITION_LEVEL@@HPEAH@Z; CONFIG_PATH_MAPPER::SetPathMapping(ushort const *,ushort const *,_ALLOW_DEFINITION_LEVEL,int,int *)
0x18005387c  mov     ebx, eax
0x18005387e  mov     rcx, rsi; this
0x180053881  call    ?RevertString@PATH@@QEAAXXZ; PATH::RevertString(void)
0x180053886  lea     rcx, [rsp+1A8h+var_170]
0x18005388b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180053891  mov     eax, ebx
0x180053893  mov     rcx, [rsp+1A8h+var_38]
0x18005389b  xor     rcx, rsp; StackCookie
0x18005389e  call    __security_check_cookie
0x1800538a3  mov     rbx, [rsp+1A8h+arg_18]
0x1800538ab  add     rsp, 180h
0x1800538b2  pop     r15
0x1800538b4  pop     r14
0x1800538b6  pop     rdi
0x1800538b7  pop     rsi
0x1800538b8  pop     rbp
0x1800538b9  retn
```
