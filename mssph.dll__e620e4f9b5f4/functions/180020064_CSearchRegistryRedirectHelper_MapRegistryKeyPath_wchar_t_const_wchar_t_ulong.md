# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x180020064`
- end: `0x1800201be`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `346`
- prototype: `int(CSearchRegistryRedirectHelper *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006300`
- `0x18000a100`
- `0x18000cbac`

## callees

- `0x1800090b0`
- `0x18000e9f4`
- `0x18001469c`
- `0x180014c70`
- `0x180020064`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800200c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002017c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800200c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002017c`

## string_xrefs

- `0x1800200e7`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x18002011d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        const wchar_t *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v5; // r8
  __int64 v7; // rbx
  __int64 v8; // rbp
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  const WCHAR *v17; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  LPCWCH lpString2[9]; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = 69LL * *(_QWORD *)this;
  v7 = -1;
  v8 = LODWORD(off_180035360[v5 + 2]);
  do
    ++v7;
  while ( a2[v7] );
  if ( (unsigned int)v7 >= (unsigned int)v8 && CompareStringOrdinal(a2, v8, off_180035360[v5 + 1], -1, 1) == 2 )
  {
    v9 = StringCchCopyW(a3, 0x104u, this + 4);
    v11 = v9;
    if ( v9 >= 0 )
    {
      if ( (unsigned int)v7 <= (unsigned int)v8 )
        return 0;
      v13 = StringCchCatW(a3, v10, &a2[v8]);
      v14 = v13;
      if ( v13 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
      return v11;
    }
  }
  else
  {
    v15 = 0;
    lpString2[0] = L"Software";
    lpString2[1] = L"System";
    while ( v15 < 2 )
    {
      v16 = -1;
      v17 = lpString2[v15];
      do
        ++v16;
      while ( v17[v16] );
      if ( CompareStringOrdinal(a2, v16, v17, -1, 1) == 2 )
      {
        if ( (byte_180036342 & 0x20) != 0 )
          McTemplateU0z_EventWriteTransfer(&Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging, a2);
        return 2147500037LL;
      }
      ++v15;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180020064  push    rbx
0x180020066  push    rbp
0x180020067  push    rsi
0x180020068  push    rdi
0x180020069  push    r13
0x18002006b  push    r14
0x18002006d  push    r15
0x18002006f  sub     rsp, 40h
0x180020073  or      r13, 0FFFFFFFFFFFFFFFFh
0x180020077  lea     rax, off_180035360; "WSearch"
0x18002007e  mov     r14, r8
0x180020081  mov     rsi, rdx
0x180020084  imul    r8, [rcx], 228h
0x18002008b  mov     rdi, rcx
0x18002008e  mov     rbx, r13
0x180020091  xor     r15d, r15d
0x180020094  mov     ebp, [r8+rax+10h]
0x180020099  inc     rbx
0x18002009c  cmp     [rdx+rbx*2], r15w
0x1800200a1  jnz     short loc_180020099
0x1800200a3  cmp     ebx, ebp
0x1800200a5  jb      loc_180020139
0x1800200ab  mov     r8, [r8+rax+8]; lpString2
0x1800200b0  mov     r9d, r13d; cchCount2
0x1800200b3  mov     edx, ebp; cchCount1
0x1800200b5  mov     [rsp+78h+bIgnoreCase], 1; int
0x1800200bd  mov     rcx, rsi; lpString1
0x1800200c0  call    cs:__imp_CompareStringOrdinal
0x1800200c6  cmp     eax, 2
0x1800200c9  jnz     short loc_180020139
0x1800200cb  lea     r8, [rdi+8]; wchar_t *
0x1800200cf  mov     edx, 104h; unsigned __int64
0x1800200d4  mov     rcx, r14; wchar_t *
0x1800200d7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800200dc  mov     edi, eax
0x1800200de  test    eax, eax
0x1800200e0  jns     short loc_180020102
0x1800200e2  mov     rcx, [rsp+78h]; this
0x1800200e7  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800200ee  mov     r9d, eax; char *
0x1800200f1  mov     edx, 46h ; 'F'; void *
0x1800200f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200fb  mov     eax, edi
0x1800200fd  jmp     loc_1800201AF
0x180020102  cmp     ebx, ebp
0x180020104  jbe     short loc_180020135
0x180020106  lea     r8, [rsi+rbp*2]; wchar_t *
0x18002010a  mov     rcx, r14; wchar_t *
0x18002010d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180020112  mov     ebx, eax
0x180020114  test    eax, eax
0x180020116  jns     short loc_180020135
0x180020118  mov     rcx, [rsp+78h]; this
0x18002011d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\com"...
0x180020124  mov     r9d, eax; char *
0x180020127  mov     edx, 49h ; 'I'; void *
0x18002012c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020131  mov     eax, ebx
0x180020133  jmp     short loc_1800201AF
0x180020135  xor     eax, eax
0x180020137  jmp     short loc_1800201AF
0x180020139  lea     rax, aSoftware; "Software"
0x180020140  mov     ebx, r15d
0x180020143  mov     [rsp+78h+lpString2], rax
0x180020148  lea     rax, aSystem_0; "System"
0x18002014f  mov     [rsp+78h+var_40], rax
0x180020154  cmp     ebx, 2
0x180020157  jnb     short loc_1800201AA
0x180020159  movsxd  rax, ebx
0x18002015c  mov     rdx, r13
0x18002015f  mov     r8, [rsp+rax*8+78h+lpString2]; lpString2
0x180020164  inc     rdx; cchCount1
0x180020167  cmp     [r8+rdx*2], r15w
0x18002016c  jnz     short loc_180020164
0x18002016e  mov     r9d, r13d; cchCount2
0x180020171  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180020179  mov     rcx, rsi; lpString1
0x18002017c  call    cs:__imp_CompareStringOrdinal
0x180020182  cmp     eax, 2
0x180020185  jz      short loc_18002018B
0x180020187  inc     ebx
0x180020189  jmp     short loc_180020154
0x18002018b  test    cs:byte_180036342, 20h
0x180020192  jz      short loc_1800201AA
0x180020194  mov     r8, rsi
0x180020197  lea     rdx, MSSearchTraceId_ETWLogging
0x18002019e  lea     rcx, Microsoft_Windows_Search_Core_Context
0x1800201a5  call    McTemplateU0z_EventWriteTransfer
0x1800201aa  mov     eax, 80004005h
0x1800201af  add     rsp, 40h
0x1800201b3  pop     r15
0x1800201b5  pop     r14
0x1800201b7  pop     r13
0x1800201b9  pop     rdi
0x1800201ba  pop     rsi
0x1800201bb  pop     rbp
0x1800201bc  pop     rbx
0x1800201bd  retn
```
