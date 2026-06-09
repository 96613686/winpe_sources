# FREB_XML_SERIALIZER::AddStringXmlEscaped(char const *,ulong)

- ea: `0x180009520`
- end: `0x1800095d5`
- name: `?AddStringXmlEscaped@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z`
- size: `181`
- prototype: `void __fastcall(FREB_XML_SERIALIZER *this, const char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009948`

## callees

- `0x1800092e0`
- `0x180009520`
- `0x18000ac90`

## import_xrefs

- `iisutil!ConvertToXmlEscapedStringQuicklyA` at `0x18000958e`
- `iisutil!ConvertToXmlEscapedStringQuicklyA` at `0x18000958e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009556`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180009556`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800095b4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800095b4`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddStringXmlEscaped(FREB_XML_SERIALIZER *this, const char *a2, int a3)
{
  __int64 v6; // rdx
  int v7; // eax
  _BYTE v8[32]; // [rsp+20h] [rbp-E8h] BYREF
  char *Src; // [rsp+40h] [rbp-C8h]
  unsigned int v10; // [rsp+50h] [rbp-B8h]
  char v11[128]; // [rsp+60h] [rbp-A8h] BYREF

  STRA::STRA((STRA *)v8, v11, 0x80u);
  if ( !*((_DWORD *)this + 7) && a2 )
  {
    if ( a3 )
    {
      if ( !a2[a3 - 1] )
        --a3;
      LODWORD(v6) = a3;
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
    }
    v7 = ConvertToXmlEscapedStringQuicklyA(a2, v6, (struct STRA *)v8);
    if ( v7 >= 0 )
      FREB_XML_SERIALIZER::AddString(this, Src, v10);
    else
      *((_DWORD *)this + 7) = v7;
  }
  STRA::~STRA((STRA *)v8);
}

```

## disassembly

```asm
0x180009520  push    rbx
0x180009522  push    rsi
0x180009523  push    rdi
0x180009524  sub     rsp, 0F0h
0x18000952b  mov     rax, cs:__security_cookie
0x180009532  xor     rax, rsp
0x180009535  mov     [rsp+108h+var_28], rax
0x18000953d  mov     ebx, r8d
0x180009540  mov     rdi, rdx
0x180009543  mov     rsi, rcx
0x180009546  lea     rdx, [rsp+108h+var_A8]
0x18000954b  mov     r8d, 80h
0x180009551  lea     rcx, [rsp+108h+var_E8]
0x180009556  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000955c  cmp     dword ptr [rsi+1Ch], 0
0x180009560  jnz     short loc_1800095AF
0x180009562  test    rdi, rdi
0x180009565  jz      short loc_1800095AF
0x180009567  test    ebx, ebx
0x180009569  jnz     short loc_18000957A
0x18000956b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000956f  inc     rdx
0x180009572  cmp     byte ptr [rdi+rdx], 0
0x180009576  jnz     short loc_18000956F
0x180009578  jmp     short loc_180009586
0x18000957a  lea     ecx, [rbx-1]
0x18000957d  cmp     byte ptr [rcx+rdi], 0
0x180009581  cmovz   ebx, ecx
0x180009584  mov     edx, ebx
0x180009586  lea     r8, [rsp+108h+var_E8]
0x18000958b  mov     rcx, rdi
0x18000958e  call    cs:__imp_?ConvertToXmlEscapedStringQuicklyA@@YAJPEBDKPEAVSTRA@@@Z; ConvertToXmlEscapedStringQuicklyA(char const *,ulong,STRA *)
0x180009594  test    eax, eax
0x180009596  jns     short loc_18000959D
0x180009598  mov     [rsi+1Ch], eax
0x18000959b  jmp     short loc_1800095AF
0x18000959d  mov     r8d, [rsp+108h+var_B8]; unsigned int
0x1800095a2  mov     rcx, rsi; this
0x1800095a5  mov     rdx, [rsp+108h+Src]; Src
0x1800095aa  call    ?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z; FREB_XML_SERIALIZER::AddString(char const *,ulong)
0x1800095af  lea     rcx, [rsp+108h+var_E8]
0x1800095b4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800095ba  mov     rcx, [rsp+108h+var_28]
0x1800095c2  xor     rcx, rsp; StackCookie
0x1800095c5  call    __security_check_cookie
0x1800095ca  add     rsp, 0F0h
0x1800095d1  pop     rdi
0x1800095d2  pop     rsi
0x1800095d3  pop     rbx
0x1800095d4  retn
```
