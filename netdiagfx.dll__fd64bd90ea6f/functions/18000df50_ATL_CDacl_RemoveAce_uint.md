# ATL::CDacl::RemoveAce(uint)

- ea: `0x18000df50`
- end: `0x18000dfc8`
- name: `?RemoveAce@CDacl@ATL@@UEAAXI@Z`
- size: `120`
- prototype: `void __fastcall(ATL::CDacl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180005bcc`
- `0x180005c18`
- `0x180009a30`
- `0x18000df50`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000dfa3`
- `msvcrt!memmove_s` at `0x18000dfa3`

## pseudocode

```c
void __fastcall ATL::CDacl::RemoveAce(ATL::CDacl *this, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rbp
  errno_t v7; // eax

  v2 = a2;
  v4 = a2 + 1LL;
  if ( v4 < a2 || a2 == -1 || (v5 = *((_QWORD *)this + 4), v4 > v5) )
    ATL::AtlThrowImpl(-2147024809);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
    *((_QWORD *)this + 3) + 8LL * a2,
    1u);
  v6 = v5 - v4;
  if ( v6 )
  {
    v7 = memmove_s(
           (void *const)(*((_QWORD *)this + 3) + 8 * v2),
           8 * v6,
           (const void *const)(*((_QWORD *)this + 3) + 8 * v4),
           8 * v6);
    ATL::AtlCrtErrorCheck(v7);
  }
  --*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x18000df50  push    rbx
0x18000df52  push    rbp
0x18000df53  push    rsi
0x18000df54  push    rdi
0x18000df55  sub     rsp, 28h
0x18000df59  mov     esi, edx
0x18000df5b  mov     rbx, rcx
0x18000df5e  lea     rdi, [rsi+1]
0x18000df62  cmp     rdi, rsi
0x18000df65  jb      short loc_18000DFBD
0x18000df67  mov     edx, 1
0x18000df6c  cmp     rdi, rdx
0x18000df6f  jb      short loc_18000DFBD
0x18000df71  mov     rbp, [rcx+20h]
0x18000df75  cmp     rdi, rbp
0x18000df78  ja      short loc_18000DFBD
0x18000df7a  mov     rax, [rcx+18h]
0x18000df7e  lea     rcx, [rax+rsi*8]
0x18000df82  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x18000df87  sub     rbp, rdi
0x18000df8a  jz      short loc_18000DFB0
0x18000df8c  mov     rax, [rbx+18h]
0x18000df90  lea     rdx, ds:0[rbp*8]; DestinationSize
0x18000df98  mov     r9, rdx; SourceSize
0x18000df9b  lea     r8, [rax+rdi*8]; Source
0x18000df9f  lea     rcx, [rax+rsi*8]; Destination
0x18000dfa3  call    cs:__imp_memmove_s
0x18000dfa9  mov     ecx, eax; int
0x18000dfab  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000dfb0  dec     qword ptr [rbx+20h]
0x18000dfb4  add     rsp, 28h
0x18000dfb8  pop     rdi
0x18000dfb9  pop     rsi
0x18000dfba  pop     rbp
0x18000dfbb  pop     rbx
0x18000dfbc  retn
0x18000dfbd  mov     ecx, 80070057h; int
0x18000dfc2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
