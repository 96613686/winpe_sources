# Windows::Foundation::UriFactory::EscapeComponent(HSTRING__ *,HSTRING__ * *)

- ea: `0x180041dc0`
- end: `0x180041f95`
- name: `?EscapeComponent@UriFactory@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `469`
- prototype: `__int64 __fastcall(Windows::Foundation::UriFactory *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180041dc0`
- `0x180041f9c`
- `0x180083c10`
- `0x180083cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041f65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180041e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180041e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180041e58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180041e58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041f20`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180041f80`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180041f80`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::UriFactory::EscapeComponent(
        Windows::Foundation::UriFactory *this,
        HSTRING a2,
        HSTRING *a3)
{
  UINT32 StringLen; // eax
  unsigned __int64 v6; // rcx
  unsigned int v7; // eax
  HRESULT HasEmbeddedNull; // edi
  unsigned __int64 v9; // rbp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v12; // r9d
  HSTRING v13; // rbx
  HANDLE v15; // rax
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  BOOL hasEmbedNull; // [rsp+20h] [rbp-10A8h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-10A4h] BYREF
  HSTRING string; // [rsp+28h] [rbp-10A0h] BYREF
  WCHAR sourceString[2088]; // [rsp+30h] [rbp-1098h] BYREF

  *a3 = 0;
  v19 = 0;
  StringLen = WindowsGetStringLen(a2);
  v6 = 9LL * (StringLen + 1);
  v7 = 9 * (StringLen + 1);
  if ( v6 > 0xFFFFFFFF )
    v7 = -1;
  v19 = v7;
  HasEmbeddedNull = v6 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( v6 <= 0xFFFFFFFF )
  {
    v9 = -1;
    if ( v7 > 0x824 )
    {
      v16 = 2LL * v7;
      if ( !is_mul_ok(v7, 2u) )
        v16 = -1;
      ProcessHeap = GetProcessHeap();
      v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v16);
      if ( !v10 )
      {
        HasEmbeddedNull = -2147024882;
        RoOriginateError(2147942414LL, 0);
        return (unsigned int)HasEmbeddedNull;
      }
    }
    else
    {
      v10 = sourceString;
    }
    hasEmbedNull = 0;
    HasEmbeddedNull = WindowsStringHasEmbeddedNull(a2, &hasEmbedNull);
    if ( HasEmbeddedNull >= 0 )
    {
      if ( hasEmbedNull )
      {
        HasEmbeddedNull = -2147024809;
      }
      else
      {
        StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
        HasEmbeddedNull = IE_UrlEscapeW(StringRawBuffer, v10, &v19, v12);
        if ( HasEmbeddedNull >= 0 )
        {
          if ( !v10 )
          {
            HasEmbeddedNull = -2147467261;
            goto LABEL_23;
          }
          v13 = 0;
          string = 0;
          do
            ++v9;
          while ( v10[v9] );
          if ( v9 > 0xFFFFFFFF )
          {
            HasEmbeddedNull = -2147024362;
          }
          else
          {
            HasEmbeddedNull = WindowsCreateString(v10, v9, &string);
            if ( HasEmbeddedNull >= 0 )
            {
              v13 = string;
              WindowsDeleteString(0);
            }
          }
          if ( HasEmbeddedNull < 0 )
          {
            if ( v13 )
              WindowsDeleteString(v13);
          }
          else
          {
            *a3 = v13;
          }
        }
      }
    }
    if ( v10 == sourceString )
      return (unsigned int)HasEmbeddedNull;
LABEL_23:
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v10);
  }
  return (unsigned int)HasEmbeddedNull;
}

```

## disassembly

```asm
0x180041dc0  mov     [rsp+arg_0], rbx
0x180041dc5  push    rbp
0x180041dc6  push    rsi
0x180041dc7  push    rdi
0x180041dc8  push    r12
0x180041dca  push    r13
0x180041dcc  push    r14
0x180041dce  push    r15
0x180041dd0  mov     eax, 1090h
0x180041dd5  call    _alloca_probe
0x180041dda  sub     rsp, rax
0x180041ddd  mov     rax, cs:__security_cookie
0x180041de4  xor     rax, rsp
0x180041de7  mov     [rsp+10C8h+var_48], rax
0x180041def  xor     r12d, r12d
0x180041df2  mov     rcx, rdx; string
0x180041df5  mov     [r8], r12
0x180041df8  mov     r15, r8
0x180041dfb  mov     [rsp+10C8h+var_10A4], r12d
0x180041e00  mov     r14, rdx
0x180041e03  call    cs:__imp_WindowsGetStringLen
0x180041e09  inc     eax
0x180041e0b  mov     r13d, 0FFFFFFFFh
0x180041e11  lea     rcx, [rax+rax*8]
0x180041e15  mov     eax, ecx
0x180041e17  cmp     rcx, r13
0x180041e1a  jbe     short loc_180041E1F
0x180041e1c  mov     eax, r13d
0x180041e1f  cmp     r13, rcx
0x180041e22  mov     [rsp+10C8h+var_10A4], eax
0x180041e26  sbb     edi, edi
0x180041e28  and     edi, 80070216h
0x180041e2e  cmp     rcx, r13
0x180041e31  ja      loc_180041EE4
0x180041e37  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180041e3b  cmp     eax, 824h
0x180041e40  ja      loc_180041F43
0x180041e46  lea     rsi, [rsp+10C8h+sourceString]
0x180041e4b  lea     rdx, [rsp+10C8h+hasEmbedNull]; hasEmbedNull
0x180041e50  mov     [rsp+10C8h+hasEmbedNull], r12d
0x180041e55  mov     rcx, r14; string
0x180041e58  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180041e5e  mov     edi, eax
0x180041e60  test    eax, eax
0x180041e62  js      short loc_180041EDA
0x180041e64  cmp     [rsp+10C8h+hasEmbedNull], r12d
0x180041e69  jnz     loc_180041F8B
0x180041e6f  xor     edx, edx; length
0x180041e71  mov     rcx, r14; string
0x180041e74  call    cs:__imp_WindowsGetStringRawBuffer
0x180041e7a  lea     r8, [rsp+10C8h+var_10A4]; unsigned int *
0x180041e7f  mov     rdx, rsi; unsigned __int16 *
0x180041e82  mov     rcx, rax; unsigned __int16 *
0x180041e85  call    ?IE_UrlEscapeW@@YAJPEBGPEAGPEAKK@Z; IE_UrlEscapeW(ushort const *,ushort *,ulong *,ulong)
0x180041e8a  mov     edi, eax
0x180041e8c  test    eax, eax
0x180041e8e  js      short loc_180041EDA
0x180041e90  test    rsi, rsi
0x180041e93  jz      loc_180041F28
0x180041e99  mov     rbx, r12
0x180041e9c  mov     [rsp+10C8h+string], r12
0x180041ea1  inc     rbp
0x180041ea4  cmp     [rsi+rbp*2], r12w
0x180041ea9  jnz     short loc_180041EA1
0x180041eab  cmp     rbp, r13
0x180041eae  ja      short loc_180041F11
0x180041eb0  mov     edx, ebp; length
0x180041eb2  lea     r8, [rsp+10C8h+string]; string
0x180041eb7  mov     rcx, rsi; sourceString
0x180041eba  call    cs:__imp_WindowsCreateString
0x180041ec0  mov     edi, eax
0x180041ec2  test    eax, eax
0x180041ec4  js      short loc_180041ED3
0x180041ec6  mov     rbx, [rsp+10C8h+string]
0x180041ecb  xor     ecx, ecx; string
0x180041ecd  call    cs:__imp_WindowsDeleteString
0x180041ed3  test    edi, edi
0x180041ed5  js      short loc_180041F18
0x180041ed7  mov     [r15], rbx
0x180041eda  lea     rax, [rsp+10C8h+sourceString]
0x180041edf  cmp     rsi, rax
0x180041ee2  jnz     short loc_180041F2D
0x180041ee4  mov     eax, edi
0x180041ee6  mov     rcx, [rsp+10C8h+var_48]
0x180041eee  xor     rcx, rsp; StackCookie
0x180041ef1  call    __security_check_cookie
0x180041ef6  mov     rbx, [rsp+10C8h+arg_0]
0x180041efe  add     rsp, 1090h
0x180041f05  pop     r15
0x180041f07  pop     r14
0x180041f09  pop     r13
0x180041f0b  pop     r12
0x180041f0d  pop     rdi
0x180041f0e  pop     rsi
0x180041f0f  pop     rbp
0x180041f10  retn
0x180041f11  mov     edi, 80070216h
0x180041f16  jmp     short loc_180041ED3
0x180041f18  test    rbx, rbx
0x180041f1b  jz      short loc_180041EDA
0x180041f1d  mov     rcx, rbx; string
0x180041f20  call    cs:__imp_WindowsDeleteString
0x180041f26  jmp     short loc_180041EDA
0x180041f28  mov     edi, 80004003h
0x180041f2d  call    cs:__imp_GetProcessHeap
0x180041f33  mov     r8, rsi; lpMem
0x180041f36  xor     edx, edx; dwFlags
0x180041f38  mov     rcx, rax; hHeap
0x180041f3b  call    cs:__imp_HeapFree
0x180041f41  jmp     short loc_180041EE4
0x180041f43  mov     ecx, eax
0x180041f45  mov     eax, 2
0x180041f4a  mul     rcx
0x180041f4d  mov     rbx, rax
0x180041f50  cmovb   rbx, rbp
0x180041f54  call    cs:__imp_GetProcessHeap
0x180041f5a  mov     r8, rbx; dwBytes
0x180041f5d  mov     edx, 8; dwFlags
0x180041f62  mov     rcx, rax; hHeap
0x180041f65  call    cs:__imp_HeapAlloc
0x180041f6b  mov     rsi, rax
0x180041f6e  test    rax, rax
0x180041f71  jnz     loc_180041E4B
0x180041f77  mov     edi, 8007000Eh
0x180041f7c  xor     edx, edx
0x180041f7e  mov     ecx, edi
0x180041f80  call    cs:__imp_RoOriginateError
0x180041f86  jmp     loc_180041EE4
0x180041f8b  mov     edi, 80070057h
0x180041f90  jmp     loc_180041EDA
```
