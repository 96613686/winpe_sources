# CURL::Init(wchar_t const *,ulong)

- ea: `0x180009680`
- end: `0x1800097ed`
- name: `?Init@CURL@@QEAAJPEB_WK@Z`
- size: `365`
- prototype: `__int64 __fastcall(CURL *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003970`
- `0x180022cc8`

## callees

- `0x180006430`
- `0x180009680`
- `0x18000e4c8`
- `0x18000fcd0`
- `0x18001e194`
- `0x180020bac`
- `0x18002324c`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800096eb`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180009742`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800096eb`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180009742`

## string_xrefs

- `0x18000970e`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CURL::Init(CURL *this, const wchar_t *a2)
{
  char *v3; // rbx
  __int64 v4; // rsi
  int v5; // edi
  char *v6; // r14
  int v7; // edx
  int v8; // eax
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // esi
  __int64 result; // rax
  int v13; // [rsp+30h] [rbp-1D8h] BYREF
  int v14; // [rsp+34h] [rbp-1D4h]
  char *v15; // [rsp+38h] [rbp-1D0h]
  _BYTE v16[8]; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-1C0h]

  v3 = (char *)this + 24;
  (*(void (__fastcall **)(char *, const wchar_t *, _QWORD, __int64))(*((_QWORD *)this + 3) + 32LL))(
    (char *)this + 24,
    a2,
    0,
    0xFFFFFFFFLL);
  v4 = 0;
  v5 = *((_DWORD *)v3 + 5);
  v6 = v3;
  v15 = v3;
  while ( 1 )
  {
    v14 = v5;
    v13 = v4;
    if ( !v5 )
    {
      v11 = 0;
      goto LABEL_13;
    }
    if ( !(unsigned int)_o_iswspace(*(unsigned __int16 *)(*((_QWORD *)v3 + 1) + 2 * v4)) )
      break;
    v4 = (unsigned int)(v4 + 1);
    --v5;
  }
  v7 = v5;
  v8 = v5;
  v9 = v5;
  while ( 1 )
  {
    if ( v5 )
    {
      v10 = *(unsigned __int16 *)(*((_QWORD *)v6 + 1) + 2LL * (unsigned int)(v4 + v9 - 1));
    }
    else
    {
      v10 = 0;
      v7 = v8;
    }
    v11 = v7;
    if ( !(unsigned int)_o_iswspace(v10) )
      break;
    CLMSubStr::Truncate((CLMSubStr *)&v13, v5 - 1);
    v5 = v14;
    v7 = v14;
    v8 = v14;
    v11 = v14;
    v9 = v14;
    if ( !v14 )
      break;
    v6 = v15;
    LODWORD(v4) = v13;
  }
LABEL_13:
  if ( v11 != *((_DWORD *)this + 11) )
  {
    TLMString<192,64,32767>::TLMString<192,64,32767>(v16, &v13);
    CLMString::operator=(v3, v17);
    TLMString<192,64,32767>::~TLMString<192,64,32767>(v16);
  }
  *(_QWORD *)((char *)this + 460) = 6225920;
  result = 0;
  *(_QWORD *)((char *)this + 442) = 0;
  *(_QWORD *)((char *)this + 450) = 0;
  *((_WORD *)this + 229) = 0;
  return result;
}

```

## disassembly

```asm
0x180009680  mov     [rsp+arg_10], rbx
0x180009685  mov     [rsp+arg_18], rbp
0x18000968a  push    rsi
0x18000968b  push    rdi
0x18000968c  push    r14
0x18000968e  sub     rsp, 1F0h
0x180009695  mov     rax, cs:__security_cookie
0x18000969c  xor     rax, rsp
0x18000969f  mov     [rsp+208h+var_28], rax
0x1800096a7  mov     rbp, rcx
0x1800096aa  lea     rbx, [rcx+18h]
0x1800096ae  mov     rax, [rbx]
0x1800096b1  mov     r9d, 0FFFFFFFFh
0x1800096b7  xor     r8d, r8d
0x1800096ba  mov     rcx, rbx
0x1800096bd  mov     rax, [rax+20h]
0x1800096c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c6  xor     esi, esi
0x1800096c8  mov     edi, [rbx+14h]
0x1800096cb  mov     r14, rbx
0x1800096ce  mov     [rsp+208h+var_1D0], rbx
0x1800096d3  mov     [rsp+208h+var_1D4], edi
0x1800096d7  mov     [rsp+208h+var_1D8], esi
0x1800096db  test    edi, edi
0x1800096dd  jz      loc_180009774
0x1800096e3  mov     rcx, [rbx+8]
0x1800096e7  movzx   ecx, word ptr [rcx+rsi*2]
0x1800096eb  call    cs:__imp__o_iswspace
0x1800096f1  test    eax, eax
0x1800096f3  jz      short loc_180009720
0x1800096f5  cmp     edi, 1
0x1800096f8  jb      short loc_180009700
0x1800096fa  inc     esi
0x1800096fc  dec     edi
0x1800096fe  jmp     short loc_1800096D3
0x180009700  mov     rcx, [rsp+208h]; this
0x180009708  mov     r9d, 0CEh; char *
0x18000970e  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180009715  mov     edx, 39Ah; void *
0x18000971a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009720  test    edi, edi
0x180009722  jz      short loc_180009774
0x180009724  mov     edx, edi
0x180009726  mov     eax, edi
0x180009728  mov     ecx, edi
0x18000972a  test    edi, edi
0x18000972c  jz      short loc_18000973C
0x18000972e  dec     ecx
0x180009730  add     ecx, esi
0x180009732  mov     rax, [r14+8]
0x180009736  movzx   ecx, word ptr [rax+rcx*2]
0x18000973a  jmp     short loc_180009740
0x18000973c  xor     ecx, ecx
0x18000973e  mov     edx, eax
0x180009740  mov     esi, edx
0x180009742  call    cs:__imp__o_iswspace
0x180009748  test    eax, eax
0x18000974a  jz      short loc_180009776
0x18000974c  lea     edx, [rdi-1]; unsigned int
0x18000974f  lea     rcx, [rsp+208h+var_1D8]; this
0x180009754  call    ?Truncate@CLMSubStr@@QEAAXI@Z; CLMSubStr::Truncate(uint)
0x180009759  mov     edi, [rsp+208h+var_1D4]
0x18000975d  mov     edx, edi
0x18000975f  mov     eax, edi
0x180009761  mov     esi, edi
0x180009763  mov     ecx, edi
0x180009765  test    edi, edi
0x180009767  jz      short loc_180009776
0x180009769  mov     r14, [rsp+208h+var_1D0]
0x18000976e  mov     esi, [rsp+208h+var_1D8]
0x180009772  jmp     short loc_18000972A
0x180009774  xor     esi, esi
0x180009776  cmp     esi, [rbp+2Ch]
0x180009779  jz      short loc_1800097A3
0x18000977b  lea     rdx, [rsp+208h+var_1D8]
0x180009780  lea     rcx, [rsp+208h+var_1C8]
0x180009785  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@AEBVCLMSubStr@@@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(CLMSubStr const &)
0x18000978a  nop
0x18000978b  mov     rdx, [rsp+208h+var_1C0]
0x180009790  mov     rcx, rbx
0x180009793  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180009798  nop
0x180009799  lea     rcx, [rsp+208h+var_1C8]
0x18000979e  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x1800097a3  mov     qword ptr [rbp+1CCh], 5F0000h
0x1800097ae  xor     eax, eax
0x1800097b0  mov     [rbp+1BAh], rax
0x1800097b7  mov     [rbp+1C2h], rax
0x1800097be  mov     [rbp+1CAh], ax
0x1800097c5  mov     rcx, [rsp+208h+var_28]
0x1800097cd  xor     rcx, rsp; StackCookie
0x1800097d0  call    __security_check_cookie
0x1800097d5  lea     r11, [rsp+208h+var_18]
0x1800097dd  mov     rbx, [r11+30h]
0x1800097e1  mov     rbp, [r11+38h]
0x1800097e5  mov     rsp, r11
0x1800097e8  pop     r14
0x1800097ea  pop     rdi
0x1800097eb  pop     rsi
0x1800097ec  retn
```
