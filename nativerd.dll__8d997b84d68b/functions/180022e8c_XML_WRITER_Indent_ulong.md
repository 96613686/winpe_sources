# XML_WRITER::Indent(ulong)

- ea: `0x180022e8c`
- end: `0x180022f6e`
- name: `?Indent@XML_WRITER@@QEAAJK@Z`
- size: `226`
- prototype: `__int64 __fastcall(XML_WRITER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800228ec`

## callees

- `0x180022e8c`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180022ef5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022ef5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f49`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022f2e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022f2e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ed2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ed2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180022ee4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180022ee4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180022f11`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180022f11`

## pseudocode

```c
__int64 __fastcall XML_WRITER::Indent(XML_WRITER *this, unsigned int a2)
{
  int v4; // ebx
  unsigned int i; // ebx
  int v7; // edi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, unsigned __int16 *); // rbx
  unsigned __int16 *Str; // rax
  _BYTE v11[64]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v12[256]; // [rsp+60h] [rbp-238h] BYREF

  memset_0(v12, 0, sizeof(v12));
  STRU::STRU((STRU *)v11, v12, 0x100u);
  v4 = STRU::Copy((STRU *)v11, L"\n");
  if ( v4 >= 0 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v7 = STRU::Append((STRU *)v11, L"    ");
      if ( v7 < 0 )
        goto LABEL_8;
    }
    v8 = *(_QWORD *)this;
    v9 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *))(**(_QWORD **)this + 240LL);
    Str = STRU::QueryStr((STRU *)v11);
    v7 = v9(v8, Str);
LABEL_8:
    STRU::~STRU((STRU *)v11);
    return (unsigned int)v7;
  }
  else
  {
    STRU::~STRU((STRU *)v11);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180022e8c  push    rbx
0x180022e8e  push    rsi
0x180022e8f  push    rdi
0x180022e90  push    r14
0x180022e92  sub     rsp, 278h
0x180022e99  mov     rax, cs:__security_cookie
0x180022ea0  xor     rax, rsp
0x180022ea3  mov     [rsp+298h+var_38], rax
0x180022eab  mov     esi, edx
0x180022ead  mov     r14, rcx
0x180022eb0  xor     edx, edx; Val
0x180022eb2  lea     rcx, [rsp+298h+var_238]; void *
0x180022eb7  mov     r8d, 200h; Size
0x180022ebd  call    memset_0
0x180022ec2  mov     r8d, 100h
0x180022ec8  lea     rdx, [rsp+298h+var_238]
0x180022ecd  lea     rcx, [rsp+298h+var_278]
0x180022ed2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022ed8  lea     rdx, asc_180060844; "\n"
0x180022edf  lea     rcx, [rsp+298h+var_278]
0x180022ee4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180022eea  mov     ebx, eax
0x180022eec  test    eax, eax
0x180022eee  jns     short loc_180022EFF
0x180022ef0  lea     rcx, [rsp+298h+var_278]
0x180022ef5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022efb  mov     eax, ebx
0x180022efd  jmp     short loc_180022F51
0x180022eff  xor     ebx, ebx
0x180022f01  lea     rcx, [rsp+298h+var_278]
0x180022f06  cmp     ebx, esi
0x180022f08  jnb     short loc_180022F21
0x180022f0a  lea     rdx, asc_180060870; "    "
0x180022f11  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180022f17  mov     edi, eax
0x180022f19  test    eax, eax
0x180022f1b  js      short loc_180022F44
0x180022f1d  inc     ebx
0x180022f1f  jmp     short loc_180022F01
0x180022f21  mov     rdi, [r14]
0x180022f24  mov     rax, [rdi]
0x180022f27  mov     rbx, [rax+0F0h]
0x180022f2e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022f34  mov     rdx, rax
0x180022f37  mov     rcx, rdi
0x180022f3a  mov     rax, rbx
0x180022f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f42  mov     edi, eax
0x180022f44  lea     rcx, [rsp+298h+var_278]
0x180022f49  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022f4f  mov     eax, edi
0x180022f51  mov     rcx, [rsp+298h+var_38]
0x180022f59  xor     rcx, rsp; StackCookie
0x180022f5c  call    __security_check_cookie
0x180022f61  add     rsp, 278h
0x180022f68  pop     r14
0x180022f6a  pop     rdi
0x180022f6b  pop     rsi
0x180022f6c  pop     rbx
0x180022f6d  retn
```
