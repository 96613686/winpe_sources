# FREB_XML_SERIALIZER::AddStringXmlEscaped(ushort const *,ulong)

- ea: `0x1800095dc`
- end: `0x180009689`
- name: `?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z`
- size: `173`
- prototype: `void __fastcall(FREB_XML_SERIALIZER *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004ae4`
- `0x180009948`

## callees

- `0x180009360`
- `0x1800095dc`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `iisutil!ConvertToXmlEscapedStringQuickly` at `0x18000963c`
- `iisutil!ConvertToXmlEscapedStringQuickly` at `0x18000963c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009662`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009662`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009623`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009623`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddStringXmlEscaped(FREB_XML_SERIALIZER *this, const unsigned __int16 *a2)
{
  int v4; // eax
  _BYTE v5[32]; // [rsp+20h] [rbp-158h] BYREF
  unsigned __int16 *v6; // [rsp+40h] [rbp-138h]
  unsigned int v7; // [rsp+50h] [rbp-128h]
  unsigned __int16 v8[128]; // [rsp+60h] [rbp-118h] BYREF

  memset_0(v8, 0, sizeof(v8));
  STRU::STRU((STRU *)v5, v8, 0x80u);
  if ( !*((_DWORD *)this + 7) && a2 )
  {
    v4 = ConvertToXmlEscapedStringQuickly(a2, (struct STRU *)v5);
    if ( v4 >= 0 )
      FREB_XML_SERIALIZER::AddString(this, v6, v7);
    else
      *((_DWORD *)this + 7) = v4;
  }
  STRU::~STRU((STRU *)v5);
}

```

## disassembly

```asm
0x1800095dc  mov     [rsp+arg_10], rbx
0x1800095e1  push    rdi
0x1800095e2  sub     rsp, 170h
0x1800095e9  mov     rax, cs:__security_cookie
0x1800095f0  xor     rax, rsp
0x1800095f3  mov     [rsp+178h+var_18], rax
0x1800095fb  mov     rdi, rdx
0x1800095fe  mov     rbx, rcx
0x180009601  xor     edx, edx; Val
0x180009603  lea     rcx, [rsp+178h+var_118]; void *
0x180009608  mov     r8d, 100h; Size
0x18000960e  call    memset_0
0x180009613  mov     r8d, 80h
0x180009619  lea     rdx, [rsp+178h+var_118]
0x18000961e  lea     rcx, [rsp+178h+var_158]
0x180009623  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009629  cmp     dword ptr [rbx+1Ch], 0
0x18000962d  jnz     short loc_18000965D
0x18000962f  test    rdi, rdi
0x180009632  jz      short loc_18000965D
0x180009634  lea     rdx, [rsp+178h+var_158]
0x180009639  mov     rcx, rdi
0x18000963c  call    cs:__imp_?ConvertToXmlEscapedStringQuickly@@YAJPEBGPEAVSTRU@@@Z; ConvertToXmlEscapedStringQuickly(ushort const *,STRU *)
0x180009642  test    eax, eax
0x180009644  jns     short loc_18000964B
0x180009646  mov     [rbx+1Ch], eax
0x180009649  jmp     short loc_18000965D
0x18000964b  mov     r8d, [rsp+178h+var_128]; unsigned int
0x180009650  mov     rcx, rbx; this
0x180009653  mov     rdx, [rsp+178h+var_138]; unsigned __int16 *
0x180009658  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z; FREB_XML_SERIALIZER::AddString(ushort const *,ulong)
0x18000965d  lea     rcx, [rsp+178h+var_158]
0x180009662  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009668  mov     rcx, [rsp+178h+var_18]
0x180009670  xor     rcx, rsp; StackCookie
0x180009673  call    __security_check_cookie
0x180009678  mov     rbx, [rsp+178h+arg_10]
0x180009680  add     rsp, 170h
0x180009687  pop     rdi
0x180009688  retn
```
