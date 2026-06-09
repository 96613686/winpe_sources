# CdGenerate8dot3Name

- ea: `0x14001617c`
- end: `0x1400163ea`
- name: `CdGenerate8dot3Name`
- size: `622`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140010f68`
- `0x140011744`
- `0x140012198`
- `0x14001233c`
- `0x1400135d0`

## callees

- `0x140001114`
- `0x140002df0`
- `0x140003000`
- `0x14001617c`

## import_xrefs

- `ntoskrnl!RtlGenerate8dot3Name` at `0x140016201`
- `ntoskrnl!RtlGenerate8dot3Name` at `0x140016201`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140016218`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140016218`
- `ntoskrnl!NlsMbOemCodePageTag` at `0x1400162d8`
- `ntoskrnl!NlsOemLeadByteInfo` at `0x1400162e4`
- `ntoskrnl!RtlFreeOemString` at `0x140016351`
- `ntoskrnl!RtlFreeOemString` at `0x140016351`

## pseudocode

```c
_WORD *__fastcall CdGenerate8dot3Name(__int64 a1, const UNICODE_STRING *a2, unsigned int a3, WCHAR *a4, _WORD *a5)
{
  int v8; // eax
  __int16 v9; // r15
  char v10; // r10
  unsigned int v11; // ebx
  unsigned __int16 v12; // r9
  __int64 *v13; // r8
  char v14; // r11
  __int16 v15; // dx
  __int16 v16; // ax
  __int16 v17; // ax
  unsigned int Length; // r13d
  _WORD *v19; // r12
  size_t v20; // rbx
  unsigned int v21; // edi
  PWSTR Buffer; // r12
  WCHAR v23; // r8
  size_t v24; // rsi
  __int16 v25; // bx
  _WORD *result; // rax
  struct _UNICODE_STRING Name8dot3; // [rsp+30h] [rbp-71h] BYREF
  _WORD *v28; // [rsp+40h] [rbp-61h]
  _WORD *v29; // [rsp+48h] [rbp-59h]
  struct _STRING DestinationString; // [rsp+50h] [rbp-51h] BYREF
  _GENERATE_NAME_CONTEXT Context; // [rsp+60h] [rbp-41h] BYREF
  __int128 v32; // [rsp+88h] [rbp-19h] BYREF
  __int64 v33; // [rsp+98h] [rbp-9h]
  __int64 v34; // [rsp+B8h] [rbp+17h] BYREF

  v29 = a5;
  v33 = 0;
  *(_QWORD *)&Name8dot3.Length = 1572864;
  Name8dot3.Buffer = (PWSTR)&v32;
  v32 = 0;
  DestinationString = 0;
  memset(&Context, 0, sizeof(Context));
  RtlGenerate8dot3Name(a2, 1u, &Context, &Name8dot3);
  v8 = RtlUnicodeStringToOemString(&DestinationString, &Name8dot3, 1u);
  v9 = 0;
  if ( v8 < 0 )
    CdRaiseStatusEx(a1, v8, 0, 1179648, 680);
  v10 = 0;
  v11 = a3 >> 5;
  v12 = 0;
  v13 = &v34;
  v14 = 0;
  v15 = 0;
  do
  {
    v13 = (__int64 *)((char *)v13 - 2);
    v16 = 48;
    if ( (v11 & 0xF) > 9 )
      v16 = 55;
    v15 += 2;
    v17 = (v11 & 0xF) + v16;
    v11 >>= 4;
    *(_WORD *)v13 = v17;
  }
  while ( v11 );
  Length = Name8dot3.Length;
  v19 = (_WORD *)v13 - 1;
  v28 = v19;
  v20 = (unsigned __int16)(v15 + 2);
  *v19 = 126;
  v21 = 0;
  if ( Length )
  {
    Buffer = Name8dot3.Buffer;
    do
    {
      v23 = Buffer[(unsigned __int64)v21 >> 1];
      if ( v23 == 46 )
        break;
      if ( v23 == 126 )
        v10 = 1;
      if ( DestinationString.Buffer[v12] >= 0x80u
        && (_BYTE)NlsMbOemCodePageTag
        && *((_WORD *)NlsOemLeadByteInfo + (unsigned __int8)DestinationString.Buffer[v12]) )
      {
        v12 += 2;
        if ( v12 + (v20 >> 1) > 8 )
          v14 = 1;
      }
      else
      {
        ++v12;
      }
      if ( !v10 && !v14 && v21 < 16 - (int)v20 )
      {
        v9 += 2;
        *a4++ = v23;
      }
      v21 += 2;
    }
    while ( v21 < Length );
    v19 = v28;
  }
  RtlFreeOemString(&DestinationString);
  v24 = v20;
  memmove(a4, v19, v20);
  v25 = v9 + v20;
  if ( v21 != Name8dot3.Length )
  {
    memmove(&a4[v24 >> 1], &Name8dot3.Buffer[(unsigned __int64)v21 >> 1], Name8dot3.Length - v21);
    v25 = Name8dot3.Length + v25 - v21;
  }
  result = v29;
  *v29 = v25;
  return result;
}

```

## disassembly

```asm
0x14001617c  mov     [rsp-8+arg_10], rbx
0x140016181  push    rbp
0x140016182  push    rsi
0x140016183  push    rdi
0x140016184  push    r12
0x140016186  push    r13
0x140016188  push    r14
0x14001618a  push    r15
0x14001618c  lea     rbp, [rsp-1Fh]
0x140016191  sub     rsp, 0C0h
0x140016198  mov     rax, cs:__security_cookie
0x14001619f  xor     rax, rsp
0x1400161a2  mov     [rbp+4Fh+var_38], rax
0x1400161a6  mov     rdi, rcx
0x1400161a9  xorps   xmm0, xmm0
0x1400161ac  mov     rcx, [rbp+4Fh+arg_20]
0x1400161b0  mov     rax, rdx
0x1400161b3  mov     [rbp+4Fh+var_A8], rcx
0x1400161b7  mov     r14, r9
0x1400161ba  xor     ecx, ecx
0x1400161bc  lea     r9, [rbp+4Fh+Name8dot3]; Name8dot3
0x1400161c0  mov     [rbp+4Fh+var_58], rcx
0x1400161c4  mov     ebx, r8d
0x1400161c7  lea     rcx, [rbp+4Fh+var_68]
0x1400161cb  xorps   xmm1, xmm1
0x1400161ce  movups  xmmword ptr [rbp+4Fh+Name8dot3.Length], xmm0
0x1400161d2  mov     [rbp+4Fh+Name8dot3.Buffer], rcx
0x1400161d6  lea     r8, [rbp+4Fh+Context]; Context
0x1400161da  mov     ecx, 18h
0x1400161df  mov     [rbp+4Fh+Name8dot3.MaximumLength], cx
0x1400161e3  xor     ecx, ecx
0x1400161e5  mov     [rbp+4Fh+Context.LastIndexValue], ecx
0x1400161e8  movups  [rbp+4Fh+var_68], xmm1
0x1400161ec  lea     esi, [rcx+1]
0x1400161ef  mov     rcx, rax; Name
0x1400161f2  mov     dl, sil; AllowExtendedCharacters
0x1400161f5  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400161f9  movups  xmmword ptr [rbp+4Fh+Context.Checksum], xmm0
0x1400161fd  movups  xmmword ptr [rbp+4Fh+Context.NameBuffer+0Ch], xmm0
0x140016201  call    cs:__imp_RtlGenerate8dot3Name
0x140016208  nop     dword ptr [rax+rax+00h]
0x14001620d  mov     r8b, sil; AllocateDestinationString
0x140016210  lea     rdx, [rbp+4Fh+Name8dot3]; SourceString
0x140016214  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x140016218  call    cs:__imp_RtlUnicodeStringToOemString
0x14001621f  nop     dword ptr [rax+rax+00h]
0x140016224  xor     r15d, r15d
0x140016227  test    eax, eax
0x140016229  js      loc_1400163CE
0x14001622f  mov     r10b, r15b
0x140016232  shr     ebx, 5
0x140016235  mov     r9d, r15d
0x140016238  lea     r8, [rbp+4Fh+var_38]
0x14001623c  mov     r11b, r15b
0x14001623f  lea     esi, [r15+2]
0x140016243  mov     edx, r15d
0x140016246  sub     r8, rsi
0x140016249  movzx   ecx, bx
0x14001624c  and     cx, 0Fh
0x140016250  mov     eax, 30h ; '0'
0x140016255  cmp     cx, 9
0x140016259  lea     edi, [rax+7]
0x14001625c  cmova   ax, di
0x140016260  add     dx, si
0x140016263  add     ax, cx
0x140016266  shr     ebx, 4
0x140016269  mov     [r8], ax
0x14001626d  test    ebx, ebx
0x14001626f  jnz     short loc_140016246
0x140016271  movzx   r13d, [rbp+4Fh+Name8dot3.Length]
0x140016276  lea     r12, [r8-2]
0x14001627a  add     dx, si
0x14001627d  mov     [rbp+4Fh+var_B0], r12
0x140016281  lea     esi, [rdi-27h]
0x140016284  movzx   ebx, dx
0x140016287  lea     ecx, [rdi+47h]
0x14001628a  sub     esi, ebx
0x14001628c  mov     [r12], cx
0x140016291  mov     edi, r15d
0x140016294  test    r13d, r13d
0x140016297  jz      loc_14001634D
0x14001629d  mov     r12, [rbp+4Fh+Name8dot3.Buffer]
0x1400162a1  mov     eax, edi
0x1400162a3  shr     rax, 1
0x1400162a6  movzx   r8d, word ptr [r12+rax*2]
0x1400162ab  cmp     r8w, 2Eh ; '.'
0x1400162b0  jz      loc_140016349
0x1400162b6  cmp     r8w, cx
0x1400162ba  movzx   r10d, r10b
0x1400162be  mov     rcx, [rbp+4Fh+DestinationString.Buffer]
0x1400162c2  mov     eax, 1
0x1400162c7  cmovz   r10d, eax
0x1400162cb  movzx   eax, r9w
0x1400162cf  movzx   ecx, byte ptr [rax+rcx]
0x1400162d3  cmp     cl, 80h
0x1400162d6  jb      short loc_140016317
0x1400162d8  mov     rax, cs:NlsMbOemCodePageTag
0x1400162df  cmp     byte ptr [rax], 0
0x1400162e2  jz      short loc_140016317
0x1400162e4  mov     rax, cs:__imp_NlsOemLeadByteInfo
0x1400162eb  mov     edx, ecx
0x1400162ed  mov     rcx, [rax]
0x1400162f0  xor     eax, eax
0x1400162f2  cmp     [rcx+rdx*2], ax
0x1400162f6  jz      short loc_140016317
0x1400162f8  lea     edx, [rax+2]
0x1400162fb  mov     rcx, rbx
0x1400162fe  add     r9w, dx
0x140016302  shr     rcx, 1
0x140016305  movzx   eax, r9w
0x140016309  add     rcx, rax
0x14001630c  cmp     rcx, 8
0x140016310  jbe     short loc_140016320
0x140016312  mov     r11b, 1
0x140016315  jmp     short loc_140016320
0x140016317  inc     r9w
0x14001631b  mov     edx, 2
0x140016320  test    r10b, r10b
0x140016323  jnz     short loc_140016339
0x140016325  test    r11b, r11b
0x140016328  jnz     short loc_140016339
0x14001632a  cmp     edi, esi
0x14001632c  jnb     short loc_140016339
0x14001632e  add     r15w, dx
0x140016332  mov     [r14], r8w
0x140016336  add     r14, rdx
0x140016339  add     edi, edx
0x14001633b  mov     ecx, 7Eh ; '~'
0x140016340  cmp     edi, r13d
0x140016343  jb      loc_1400162A1
0x140016349  mov     r12, [rbp+4Fh+var_B0]
0x14001634d  lea     rcx, [rbp+4Fh+DestinationString]; OemString
0x140016351  call    cs:__imp_RtlFreeOemString
0x140016358  nop     dword ptr [rax+rax+00h]
0x14001635d  mov     r8, rbx; Size
0x140016360  mov     rdx, r12; Src
0x140016363  mov     rcx, r14; void *
0x140016366  mov     rsi, rbx
0x140016369  call    memmove
0x14001636e  movzx   eax, [rbp+4Fh+Name8dot3.Length]
0x140016372  add     bx, r15w
0x140016376  cmp     edi, eax
0x140016378  jz      short loc_14001639F
0x14001637a  sub     eax, edi
0x14001637c  mov     ecx, edi
0x14001637e  shr     rcx, 1
0x140016381  mov     r8d, eax; Size
0x140016384  mov     rax, [rbp+4Fh+Name8dot3.Buffer]
0x140016388  shr     rsi, 1
0x14001638b  lea     rdx, [rax+rcx*2]; Src
0x14001638f  lea     rcx, [r14+rsi*2]; void *
0x140016393  call    memmove
0x140016398  sub     bx, di
0x14001639b  add     bx, [rbp+4Fh+Name8dot3.Length]
0x14001639f  mov     rax, [rbp+4Fh+var_A8]
0x1400163a3  mov     [rax], bx
0x1400163a6  mov     rcx, [rbp+4Fh+var_38]
0x1400163aa  xor     rcx, rsp; StackCookie
0x1400163ad  call    __security_check_cookie
0x1400163b2  mov     rbx, [rsp+0F0h+arg_10]
0x1400163ba  add     rsp, 0C0h
0x1400163c1  pop     r15
0x1400163c3  pop     r14
0x1400163c5  pop     r13
0x1400163c7  pop     r12
0x1400163c9  pop     rdi
0x1400163ca  pop     rsi
0x1400163cb  pop     rbp
0x1400163cc  retn
0x1400163ce  mov     r9d, 120000h
0x1400163d4  mov     [rsp+0F0h+var_D0], 2A8h
0x1400163dc  xor     r8d, r8d
0x1400163df  mov     edx, eax
0x1400163e1  mov     rcx, rdi
0x1400163e4  call    CdRaiseStatusEx
```
