# BookKeepingXml::AddXml(bool,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000bfcc`
- end: `0x18000c2d0`
- name: `?AddXml@BookKeepingXml@@AEAAJ_NPEBG11111@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(BookKeepingXml *__hidden this@<rcx>, bool@<dl>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000c2d8`

## callees

- `0x180008630`
- `0x18000bfcc`
- `0x18000c378`
- `0x18000c3e8`
- `0x18000c844`
- `0x18000c88c`
- `0x18000cd38`
- `0x18001b522`
- `0x18001b550`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::AddXml(
        BookKeepingXml *this,
        char a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8)
{
  __int64 v12; // r14
  int v13; // ebx
  unsigned __int64 AttributeXmlLength; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // r10
  unsigned __int64 v17; // rsi
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v22; // rdx
  char v24; // [rsp+40h] [rbp-468h]
  int v25; // [rsp+48h] [rbp-460h]
  unsigned __int16 *v26; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-450h] BYREF
  unsigned __int16 v28[512]; // [rsp+60h] [rbp-448h] BYREF

  v27 = a6;
  v26 = a8;
  memset_0(v28, 0, sizeof(v28));
  v12 = -1;
  if ( *((_QWORD *)this + 2) == -1 )
    return (unsigned int)-2147221497;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( !a5 && a7 )
    return (unsigned int)-2147467261;
  if ( a2 == 1 && a4 )
    return (unsigned int)-2147024809;
  v13 = 0;
  v24 = 0;
  do
    ++v12;
  while ( a3[v12] );
  GetAttributeXmlLength(a5, (const unsigned __int16 **)&v27);
  AttributeXmlLength = GetAttributeXmlLength(a7, (const unsigned __int16 **)&v26);
  v17 = AttributeXmlLength + v16 + v12;
  if ( !a2 )
  {
    if ( a4 )
    {
      v24 = 1;
      v17 += v12 + _EscapeXML(a4, v28, v15) + 3;
    }
    else
    {
      ++v17;
    }
  }
  if ( v17 )
  {
    if ( a2 )
      v18 = 1;
    else
      v18 = a4 != 0 ? 4 : 7;
    v19 = v18 + 1;
    if ( !a5 )
      v19 = v18;
    v20 = v19 + 1;
    if ( !a7 )
      v20 = v19;
    v25 = v20;
    v13 = BookKeepingXml::CheckBufferSize(this, v17);
    if ( v13 >= 0 )
    {
      v13 = BookKeepingXml::Indent(this);
      if ( v13 >= 0 )
      {
        v13 = BookKeepingXml::Append(this, (&off_18001EE80)[v25], a3, a5, v27, a7, v26);
        if ( v13 >= 0 )
        {
          if ( a4 && (v13 = BookKeepingXml::Append(this, L"%s", v28), v13 < 0) )
          {
            v21 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v22 = 20;
              goto LABEL_28;
            }
          }
          else if ( v24 && (v13 = BookKeepingXml::Append(this, L"</%s>\r\n", a3), v13 < 0) )
          {
            v21 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v22 = 21;
              goto LABEL_28;
            }
          }
          else if ( a2 )
          {
            ++*((_QWORD *)this + 1030);
          }
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v22 = 19;
            goto LABEL_28;
          }
        }
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v22 = 18;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v22 = 17;
LABEL_28:
        WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids, (unsigned int)v13);
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000bfcc  mov     [rsp+arg_8], rbx
0x18000bfd1  push    rbp
0x18000bfd2  push    rsi
0x18000bfd3  push    rdi
0x18000bfd4  push    r12
0x18000bfd6  push    r13
0x18000bfd8  push    r14
0x18000bfda  push    r15
0x18000bfdc  sub     rsp, 470h
0x18000bfe3  mov     rax, cs:__security_cookie
0x18000bfea  xor     rax, rsp
0x18000bfed  mov     [rsp+4A8h+var_48], rax
0x18000bff5  mov     rax, [rsp+4A8h+arg_28]
0x18000bffd  mov     r12, r8
0x18000c000  mov     rsi, [rsp+4A8h+arg_30]
0x18000c008  mov     r15b, dl
0x18000c00b  mov     r13, [rsp+4A8h+arg_20]
0x18000c013  mov     rdi, rcx
0x18000c016  mov     [rsp+4A8h+var_450], rax
0x18000c01b  lea     rcx, [rsp+4A8h+var_448]; void *
0x18000c020  mov     rax, [rsp+4A8h+arg_38]
0x18000c028  xor     edx, edx; Val
0x18000c02a  mov     r8d, 400h; Size
0x18000c030  mov     [rsp+4A8h+var_458], rax
0x18000c035  mov     rbp, r9
0x18000c038  mov     [rsp+4A8h+var_460], rsi
0x18000c03d  call    memset_0
0x18000c042  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c046  cmp     [rdi+10h], r14
0x18000c04a  jnz     short loc_18000C056
0x18000c04c  mov     ebx, 80040007h
0x18000c051  jmp     loc_18000C2A3
0x18000c056  xor     r11d, r11d
0x18000c059  test    r12, r12
0x18000c05c  jz      short loc_18000C07D
0x18000c05e  test    r13, r13
0x18000c061  jnz     short loc_18000C072
0x18000c063  test    rsi, rsi
0x18000c066  jz      short loc_18000C072
0x18000c068  mov     ebx, 80004003h
0x18000c06d  jmp     loc_18000C2A3
0x18000c072  cmp     r15b, 1
0x18000c076  jnz     short loc_18000C087
0x18000c078  test    rbp, rbp
0x18000c07b  jz      short loc_18000C087
0x18000c07d  mov     ebx, 80070057h
0x18000c082  jmp     loc_18000C2A3
0x18000c087  mov     ebx, r11d
0x18000c08a  mov     [rsp+4A8h+var_468], r11b
0x18000c08f  inc     r14
0x18000c092  cmp     [r12+r14*2], r11w
0x18000c097  jnz     short loc_18000C08F
0x18000c099  lea     rdx, [rsp+4A8h+var_450]; unsigned __int16 **
0x18000c09e  mov     rcx, r13; unsigned __int16 *
0x18000c0a1  call    ?GetAttributeXmlLength@@YA_KPEBGAEAPEBG@Z; GetAttributeXmlLength(ushort const *,ushort const * &)
0x18000c0a6  lea     rdx, [rsp+4A8h+var_458]; unsigned __int16 **
0x18000c0ab  mov     rcx, rsi; unsigned __int16 *
0x18000c0ae  lea     r10, [rax+4]
0x18000c0b2  call    ?GetAttributeXmlLength@@YA_KPEBGAEAPEBG@Z; GetAttributeXmlLength(ushort const *,ushort const * &)
0x18000c0b7  lea     rsi, [r10+r14]
0x18000c0bb  add     rsi, rax
0x18000c0be  test    r15b, r15b
0x18000c0c1  jnz     short loc_18000C0E9
0x18000c0c3  test    rbp, rbp
0x18000c0c6  jz      short loc_18000C0E6
0x18000c0c8  lea     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x18000c0cd  mov     rcx, rbp; unsigned __int16 *
0x18000c0d0  call    ?_EscapeXML@@YA_KPEBGPEAG_K@Z; _EscapeXML(ushort const *,ushort *,unsigned __int64)
0x18000c0d5  add     rsi, 3
0x18000c0d9  mov     [rsp+4A8h+var_468], 1
0x18000c0de  add     rsi, rax
0x18000c0e1  add     rsi, r14
0x18000c0e4  jmp     short loc_18000C0E9
0x18000c0e6  inc     rsi
0x18000c0e9  test    rsi, rsi
0x18000c0ec  jz      loc_18000C2A3
0x18000c0f2  test    r15b, r15b
0x18000c0f5  jz      short loc_18000C0FE
0x18000c0f7  mov     ecx, 1
0x18000c0fc  jmp     short loc_18000C10C
0x18000c0fe  mov     rax, rbp
0x18000c101  neg     rax
0x18000c104  sbb     ecx, ecx
0x18000c106  and     ecx, 0FFFFFFFDh
0x18000c109  add     ecx, 7
0x18000c10c  mov     r14, [rsp+4A8h+var_460]
0x18000c111  lea     eax, [rcx+1]
0x18000c114  test    r13, r13
0x18000c117  mov     rdx, rsi; unsigned __int64
0x18000c11a  cmovz   eax, ecx
0x18000c11d  test    r14, r14
0x18000c120  lea     ecx, [rax+1]
0x18000c123  cmovz   ecx, eax
0x18000c126  mov     dword ptr [rsp+4A8h+var_460], ecx
0x18000c12a  mov     rcx, rdi; this
0x18000c12d  call    ?CheckBufferSize@BookKeepingXml@@AEAAJ_K@Z; BookKeepingXml::CheckBufferSize(unsigned __int64)
0x18000c132  mov     ebx, eax
0x18000c134  test    eax, eax
0x18000c136  jns     short loc_18000C176
0x18000c138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c13f  lea     rax, WPP_GLOBAL_Control
0x18000c146  cmp     rcx, rax
0x18000c149  jz      loc_18000C2A3
0x18000c14f  cmp     byte ptr [rcx+19h], 2
0x18000c153  jb      loc_18000C2A3
0x18000c159  mov     edx, 11h
0x18000c15e  mov     rcx, [rcx+10h]
0x18000c162  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000c169  mov     r9d, ebx
0x18000c16c  call    WPP_SF_d
0x18000c171  jmp     loc_18000C2A3
0x18000c176  mov     rcx, rdi; this
0x18000c179  call    ?Indent@BookKeepingXml@@AEAAJXZ; BookKeepingXml::Indent(void)
0x18000c17e  mov     ebx, eax
0x18000c180  test    eax, eax
0x18000c182  jns     short loc_18000C1AC
0x18000c184  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c18b  lea     rax, WPP_GLOBAL_Control
0x18000c192  cmp     rcx, rax
0x18000c195  jz      loc_18000C2A3
0x18000c19b  cmp     byte ptr [rcx+19h], 2
0x18000c19f  jb      loc_18000C2A3
0x18000c1a5  mov     edx, 12h
0x18000c1aa  jmp     short loc_18000C15E
0x18000c1ac  mov     rax, [rsp+4A8h+var_458]
0x18000c1b1  lea     rcx, off_18001EE80; "</%s>\r\n"
0x18000c1b8  mov     edx, dword ptr [rsp+4A8h+var_460]
0x18000c1bc  mov     r9, r13
0x18000c1bf  mov     [rsp+4A8h+var_478], rax
0x18000c1c4  mov     r8, r12
0x18000c1c7  mov     rax, [rsp+4A8h+var_450]
0x18000c1cc  mov     [rsp+4A8h+var_480], r14
0x18000c1d1  mov     rdx, [rcx+rdx*8]; unsigned __int16 *
0x18000c1d5  mov     rcx, rdi; this
0x18000c1d8  mov     [rsp+4A8h+var_488], rax
0x18000c1dd  call    ?Append@BookKeepingXml@@AEAAJPEBGZZ; BookKeepingXml::Append(ushort const *,...)
0x18000c1e2  mov     ebx, eax
0x18000c1e4  test    eax, eax
0x18000c1e6  jns     short loc_18000C213
0x18000c1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1ef  lea     rax, WPP_GLOBAL_Control
0x18000c1f6  cmp     rcx, rax
0x18000c1f9  jz      loc_18000C2A3
0x18000c1ff  cmp     byte ptr [rcx+19h], 2
0x18000c203  jb      loc_18000C2A3
0x18000c209  mov     edx, 13h
0x18000c20e  jmp     loc_18000C15E
0x18000c213  test    rbp, rbp
0x18000c216  jz      short loc_18000C255
0x18000c218  lea     r8, [rsp+4A8h+var_448]
0x18000c21d  mov     rcx, rdi; this
0x18000c220  lea     rdx, aS_3; "%s"
0x18000c227  call    ?Append@BookKeepingXml@@AEAAJPEBGZZ; BookKeepingXml::Append(ushort const *,...)
0x18000c22c  mov     ebx, eax
0x18000c22e  test    eax, eax
0x18000c230  jns     short loc_18000C255
0x18000c232  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c239  lea     rax, WPP_GLOBAL_Control
0x18000c240  cmp     rcx, rax
0x18000c243  jz      short loc_18000C2A3
0x18000c245  cmp     byte ptr [rcx+19h], 2
0x18000c249  jb      short loc_18000C2A3
0x18000c24b  mov     edx, 14h
0x18000c250  jmp     loc_18000C15E
0x18000c255  cmp     [rsp+4A8h+var_468], 0
0x18000c25a  jz      short loc_18000C297
0x18000c25c  mov     rdx, cs:off_18001EE80; unsigned __int16 *
0x18000c263  mov     r8, r12
0x18000c266  mov     rcx, rdi; this
0x18000c269  call    ?Append@BookKeepingXml@@AEAAJPEBGZZ; BookKeepingXml::Append(ushort const *,...)
0x18000c26e  mov     ebx, eax
0x18000c270  test    eax, eax
0x18000c272  jns     short loc_18000C297
0x18000c274  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c27b  lea     rax, WPP_GLOBAL_Control
0x18000c282  cmp     rcx, rax
0x18000c285  jz      short loc_18000C2A3
0x18000c287  cmp     byte ptr [rcx+19h], 2
0x18000c28b  jb      short loc_18000C2A3
0x18000c28d  mov     edx, 15h
0x18000c292  jmp     loc_18000C15E
0x18000c297  test    r15b, r15b
0x18000c29a  jz      short loc_18000C2A3
0x18000c29c  inc     qword ptr [rdi+2030h]
0x18000c2a3  mov     eax, ebx
0x18000c2a5  mov     rcx, [rsp+4A8h+var_48]
0x18000c2ad  xor     rcx, rsp; StackCookie
0x18000c2b0  call    __security_check_cookie
0x18000c2b5  mov     rbx, [rsp+4A8h+arg_8]
0x18000c2bd  add     rsp, 470h
0x18000c2c4  pop     r15
0x18000c2c6  pop     r14
0x18000c2c8  pop     r13
0x18000c2ca  pop     r12
0x18000c2cc  pop     rdi
0x18000c2cd  pop     rsi
0x18000c2ce  pop     rbp
0x18000c2cf  retn
```
