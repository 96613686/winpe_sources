# GetFormatNameFromPathName(wchar_t const *,wchar_t * *)

- ea: `0x1800220b4`
- end: `0x180022194`
- name: `?GetFormatNameFromPathName@@YAJPEB_WPEAPEA_W@Z`
- size: `224`
- prototype: `__int64 __fastcall(LPCWSTR lpwcsPathName, wchar_t **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e10c`
- `0x180022820`

## callees

- `0x180013590`
- `0x180013970`
- `0x1800149b0`
- `0x1800149e0`
- `0x1800220b4`
- `0x1800273b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022152`
- `OLEAUT32!__imp_SysAllocString` at `0x180022152`
- `mqrt!MQPathNameToFormatName` at `0x18002211c`
- `mqrt!MQPathNameToFormatName` at `0x18002211c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFormatNameFromPathName(LPCWSTR lpwcsPathName, wchar_t **a2)
{
  WCHAR *Buffer; // rax
  int v5; // ebx
  const OLECHAR *v6; // rax
  wchar_t *v7; // rax
  DWORD dwFormatNameLength[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh]

  v10[1] = 0;
  v11 = 0;
  v10[0] = &CStaticBufferGrowing<wchar_t,128>::`vftable';
  dwFormatNameLength[0] = CBaseStaticBufferGrowing<unsigned char>::GetBufferMaxSize(v10);
  while ( 1 )
  {
    Buffer = (WCHAR *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v10);
    v5 = MQPathNameToFormatName(lpwcsPathName, Buffer, dwFormatNameLength);
    if ( v5 != -1072824289 )
      break;
    v5 = CBaseStaticBufferGrowing<wchar_t>::AllocateBuffer((__int64)v10, dwFormatNameLength[0]);
    if ( v5 < 0 )
      goto LABEL_9;
  }
  if ( v5 >= 0 )
  {
    v6 = (const OLECHAR *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v10);
    v7 = SysAllocString(v6);
    if ( v7 )
    {
      *a2 = v7;
      v5 = 0;
    }
    else
    {
      v5 = -2147024882;
    }
  }
LABEL_9:
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800220b4  mov     [rsp-8+arg_10], rbx
0x1800220b9  push    rbp
0x1800220ba  push    rsi
0x1800220bb  push    rdi
0x1800220bc  lea     rbp, [rsp-60h]
0x1800220c1  sub     rsp, 160h
0x1800220c8  mov     rax, cs:__security_cookie
0x1800220cf  xor     rax, rsp
0x1800220d2  mov     [rbp+70h+var_20], rax
0x1800220d6  mov     rsi, rdx
0x1800220d9  mov     rdi, rcx
0x1800220dc  mov     [rsp+170h+var_138], 0
0x1800220e5  mov     [rsp+170h+var_12C], 0
0x1800220ed  lea     rax, ??_7?$CStaticBufferGrowing@_W$0IA@@@6B@; const CStaticBufferGrowing<wchar_t,128>::`vftable'
0x1800220f4  mov     [rsp+170h+var_140], rax
0x1800220f9  lea     rcx, [rsp+170h+var_140]
0x1800220fe  call    ?GetBufferMaxSize@?$CBaseStaticBufferGrowing@E@@UEAAKXZ; CBaseStaticBufferGrowing<uchar>::GetBufferMaxSize(void)
0x180022103  mov     [rsp+170h+dwFormatNameLength], eax
0x180022107  lea     rcx, [rsp+170h+var_140]
0x18002210c  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x180022111  lea     r8, [rsp+170h+dwFormatNameLength]; lpdwFormatNameLength
0x180022116  mov     rdx, rax; lpwcsFormatName
0x180022119  mov     rcx, rdi; lpwcsPathName
0x18002211c  call    cs:__imp_MQPathNameToFormatName
0x180022122  mov     ebx, eax
0x180022124  cmp     eax, 0C00E001Fh
0x180022129  jnz     short loc_180022141
0x18002212b  mov     edx, [rsp+170h+dwFormatNameLength]
0x18002212f  lea     rcx, [rsp+170h+var_140]
0x180022134  call    ?AllocateBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAJK@Z; CBaseStaticBufferGrowing<wchar_t>::AllocateBuffer(ulong)
0x180022139  mov     ebx, eax
0x18002213b  test    eax, eax
0x18002213d  js      short loc_180022169
0x18002213f  jmp     short loc_180022107
0x180022141  test    ebx, ebx
0x180022143  js      short loc_180022169
0x180022145  lea     rcx, [rsp+170h+var_140]
0x18002214a  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x18002214f  mov     rcx, rax; psz
0x180022152  call    cs:__imp_SysAllocString
0x180022158  test    rax, rax
0x18002215b  jnz     short loc_180022164
0x18002215d  mov     ebx, 8007000Eh
0x180022162  jmp     short loc_180022169
0x180022164  mov     [rsi], rax
0x180022167  xor     ebx, ebx
0x180022169  lea     rcx, [rsp+170h+var_140]
0x18002216e  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x180022173  mov     eax, ebx
0x180022175  mov     rcx, [rbp+70h+var_20]
0x180022179  xor     rcx, rsp; StackCookie
0x18002217c  call    __security_check_cookie
0x180022181  mov     rbx, [rsp+170h+arg_10]
0x180022189  add     rsp, 160h
0x180022190  pop     rdi
0x180022191  pop     rsi
0x180022192  pop     rbp
0x180022193  retn
```
