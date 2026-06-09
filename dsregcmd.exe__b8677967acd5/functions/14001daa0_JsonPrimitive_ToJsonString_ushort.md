# JsonPrimitive::ToJsonString(ushort * *)

- ea: `0x14001daa0`
- end: `0x14001dc09`
- name: `?ToJsonString@JsonPrimitive@@UEBAKPEAPEAG@Z`
- size: `361`
- prototype: `unsigned int(JsonPrimitive *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140001b60`
- `0x1400032ec`
- `0x14001c2d0`
- `0x14001ca24`
- `0x14001ced8`
- `0x14001d06c`
- `0x14001daa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001db38`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001db38`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001db56`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001db56`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001db1b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001db1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonPrimitive::ToJsonString(JsonPrimitive *this, unsigned __int16 **a2)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // ebx
  size_t v8; // rax
  size_t v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  const unsigned __int16 *v12; // rcx
  unsigned int JsonEncodedQuotedString; // eax
  __int64 v14; // rax
  const unsigned __int16 *v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-58h] BYREF
  __m128i si128; // [rsp+30h] [rbp-48h]
  char *v19[4]; // [rsp+40h] [rbp-38h] BYREF

  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17) = 0;
  *a2 = 0;
  v4 = *((_DWORD *)this + 2) - 3;
  if ( !v4 )
  {
    v15 = (const unsigned __int16 *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v15 = *(const unsigned __int16 **)v15;
    JsonEncodedQuotedString = JsonUtil::GetJsonEncodedQuotedString(v15, a2);
    goto LABEL_21;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v14 = StringUtility::ToString<__int64>(v19, (char *)this + 24);
    std::wstring::operator=(&v17, v14);
    std::wstring::~wstring(v19);
    v12 = (const unsigned __int16 *)&v17;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = (const unsigned __int16 *)v17;
    goto LABEL_14;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v12 = L"true";
    if ( !*((_BYTE *)this + 16) )
      v12 = L"false";
LABEL_14:
    JsonEncodedQuotedString = JsonPrimitive::AllocateAndCopyString(v12, a2);
LABEL_21:
    v7 = JsonEncodedQuotedString;
    goto LABEL_22;
  }
  if ( v6 == 1 )
  {
    v8 = wcsnlen(L"null", 0x7FFFFFFFu);
    if ( v8 == 0x7FFFFFFF )
    {
      v7 = -895090684;
    }
    else
    {
      v9 = v8 + 1;
      v10 = (unsigned __int16 *)malloc(2 * (v8 + 1));
      v11 = v10;
      if ( !v10 || (unsigned int)_o_wcsncpy_s(v10, v9, L"null", v9) )
      {
        v7 = -895090686;
      }
      else
      {
        v7 = 0;
        *a2 = v11;
      }
    }
  }
  else
  {
    v7 = -895090685;
  }
LABEL_22:
  std::wstring::~wstring((char **)&v17);
  return v7;
}

```

## disassembly

```asm
0x14001daa0  mov     [rsp+arg_10], rbx
0x14001daa5  mov     [rsp+arg_18], rsi
0x14001daaa  push    rdi
0x14001daab  sub     rsp, 70h
0x14001daaf  mov     rax, cs:__security_cookie
0x14001dab6  xor     rax, rsp
0x14001dab9  mov     [rsp+78h+var_18], rax
0x14001dabe  mov     rdi, rdx
0x14001dac1  mov     rdx, rcx
0x14001dac4  xorps   xmm0, xmm0
0x14001dac7  movups  [rsp+78h+var_58], xmm0
0x14001dacc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001dad4  movdqu  [rsp+78h+var_48], xmm1
0x14001dada  xor     eax, eax
0x14001dadc  mov     word ptr [rsp+78h+var_58], ax
0x14001dae1  mov     [rdi], rax
0x14001dae4  mov     ecx, [rcx+8]
0x14001dae7  sub     ecx, 3
0x14001daea  jz      loc_14001DBC6
0x14001daf0  sub     ecx, 1
0x14001daf3  jz      loc_14001DB8E
0x14001daf9  sub     ecx, 1
0x14001dafc  jz      short loc_14001DB6E
0x14001dafe  cmp     ecx, 1
0x14001db01  jz      short loc_14001DB0D
0x14001db03  mov     ebx, 0CAA60003h
0x14001db08  jmp     loc_14001DBDE
0x14001db0d  mov     ebx, 7FFFFFFFh
0x14001db12  mov     edx, ebx; MaxCount
0x14001db14  lea     rcx, aNull; "null"
0x14001db1b  call    cs:__imp_wcsnlen
0x14001db21  cmp     rax, rbx
0x14001db24  jnz     short loc_14001DB30
0x14001db26  mov     ebx, 0CAA60004h
0x14001db2b  jmp     loc_14001DBDE
0x14001db30  lea     rbx, [rax+1]
0x14001db34  lea     rcx, [rbx+rbx]; Size
0x14001db38  call    cs:__imp_malloc
0x14001db3e  mov     rsi, rax
0x14001db41  test    rax, rax
0x14001db44  jz      short loc_14001DB67
0x14001db46  mov     r9, rbx
0x14001db49  lea     r8, aNull; "null"
0x14001db50  mov     rdx, rbx
0x14001db53  mov     rcx, rax
0x14001db56  call    cs:__imp__o_wcsncpy_s
0x14001db5c  test    eax, eax
0x14001db5e  jnz     short loc_14001DB67
0x14001db60  xor     ebx, ebx
0x14001db62  mov     [rdi], rsi
0x14001db65  jmp     short loc_14001DBDE
0x14001db67  mov     ebx, 0CAA60002h
0x14001db6c  jmp     short loc_14001DBDE
0x14001db6e  lea     rax, aFalse; "false"
0x14001db75  lea     rcx, aTrue; "true"
0x14001db7c  cmp     byte ptr [rdx+10h], 0
0x14001db80  cmovz   rcx, rax; unsigned __int16 *
0x14001db84  mov     rdx, rdi; unsigned __int16 **
0x14001db87  call    ?AllocateAndCopyString@JsonPrimitive@@CAKPEBGPEAPEAG@Z; JsonPrimitive::AllocateAndCopyString(ushort const *,ushort * *)
0x14001db8c  jmp     short loc_14001DBDC
0x14001db8e  add     rdx, 18h
0x14001db92  lea     rcx, [rsp+78h+var_38]
0x14001db97  call    ??$ToString@_J@StringUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_J@Z; StringUtility::ToString<__int64>(__int64 const &)
0x14001db9c  mov     rdx, rax
0x14001db9f  lea     rcx, [rsp+78h+var_58]
0x14001dba4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001dba9  lea     rcx, [rsp+78h+var_38]
0x14001dbae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dbb3  lea     rcx, [rsp+78h+var_58]
0x14001dbb8  cmp     qword ptr [rsp+78h+var_48+8], 7
0x14001dbbe  cmova   rcx, qword ptr [rsp+78h+var_58]
0x14001dbc4  jmp     short loc_14001DB84
0x14001dbc6  lea     rcx, [rdx+20h]
0x14001dbca  cmp     qword ptr [rcx+18h], 7
0x14001dbcf  jbe     short loc_14001DBD4
0x14001dbd1  mov     rcx, [rcx]; unsigned __int16 *
0x14001dbd4  mov     rdx, rdi; unsigned __int16 **
0x14001dbd7  call    ?GetJsonEncodedQuotedString@JsonUtil@@SAKPEBGPEAPEAG@Z; JsonUtil::GetJsonEncodedQuotedString(ushort const *,ushort * *)
0x14001dbdc  mov     ebx, eax
0x14001dbde  lea     rcx, [rsp+78h+var_58]
0x14001dbe3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dbe8  mov     eax, ebx
0x14001dbea  mov     rcx, [rsp+78h+var_18]
0x14001dbef  xor     rcx, rsp; StackCookie
0x14001dbf2  call    __security_check_cookie
0x14001dbf7  lea     r11, [rsp+78h+var_8]
0x14001dbfc  mov     rbx, [r11+20h]
0x14001dc00  mov     rsi, [r11+28h]
0x14001dc04  mov     rsp, r11
0x14001dc07  pop     rdi
0x14001dc08  retn
```
