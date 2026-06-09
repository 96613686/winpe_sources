# FormatRuntimeErrorVa(ushort *,ulong,long,char *)

- ea: `0x180039890`
- end: `0x1800399aa`
- name: `?FormatRuntimeErrorVa@@YAJPEAGKJPEAD@Z`
- size: `282`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned int, int, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039a74`

## callees

- `0x18000df7c`
- `0x18000dfa8`
- `0x18002a7c8`
- `0x180039890`
- `0x1800399b0`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800398fe`
- `KERNEL32!FormatMessageW` at `0x1800398fe`
- `KERNEL32!lstrlenW` at `0x18003990b`
- `KERNEL32!lstrlenW` at `0x18003990b`

## string_xrefs

- `0x180039939`: `Common Language Runtime Internal error: 0x%08x`

## pseudocode

```c
__int64 __fastcall FormatRuntimeErrorVa(wchar_t *Buffer, __int64 a2, DWORD a3, va_list a4)
{
  int v7; // eax
  bool v8; // sf
  int ResourceString; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-458h]
  wchar_t Format[512]; // [rsp+40h] [rbp-438h] BYREF

  *Buffer = 0;
  if ( (a3 & 0x1FFF0000) == 0x130000 || !HIWORD(a3) )
  {
    ResourceString = UtilLoadResourceString(4, (unsigned __int16)a3, Format, 512);
    v8 = ResourceString < 0;
    if ( !ResourceString )
    {
      vsnwprintf_s(Buffer, 0x1000u, 0xFFFFFFFFFFFFFFFFuLL, Format, a4);
      return a3;
    }
  }
  else
  {
    if ( FormatMessageW(0x1000u, 0, a3, 0, Buffer, 0x1000u, 0) )
    {
      v7 = lstrlenW(Buffer);
      if ( v7 > 3 && Buffer[v7 - 2] == 13 && Buffer[v7 - 1] == 10 )
        Buffer[v7 - 2] = 0;
      return a3;
    }
    v8 = (int)HRESULT_FROM_GetLastError() < 0;
  }
  if ( v8 )
  {
    LODWORD(lpBuffer) = a3;
    snwprintf_s(Buffer, 0x1000u, 0xFFFFFFFFFFFFFFFFuLL, L"Common Language Runtime Internal error: 0x%08x", lpBuffer);
  }
  return a3;
}

```

## disassembly

```asm
0x180039890  push    rbx
0x180039892  push    rbp
0x180039893  push    rsi
0x180039894  push    rdi
0x180039895  push    r14
0x180039897  sub     rsp, 450h
0x18003989e  mov     rax, cs:__security_cookie
0x1800398a5  xor     rax, rsp
0x1800398a8  mov     [rsp+478h+var_38], rax
0x1800398b0  xor     ebp, ebp
0x1800398b2  mov     eax, r8d
0x1800398b5  and     eax, 1FFF0000h
0x1800398ba  mov     [rcx], bp
0x1800398bd  mov     rsi, r9
0x1800398c0  mov     edi, r8d
0x1800398c3  mov     rbx, rcx
0x1800398c6  mov     r14d, 1000h
0x1800398cc  cmp     eax, 130000h
0x1800398d1  jz      loc_180039973
0x1800398d7  mov     eax, r8d
0x1800398da  shr     rax, 10h
0x1800398de  test    ax, ax
0x1800398e1  jz      loc_180039973
0x1800398e7  mov     [rsp+478h+Arguments], rbp; Arguments
0x1800398ec  xor     r9d, r9d; dwLanguageId
0x1800398ef  mov     [rsp+478h+nSize], r14d; nSize
0x1800398f4  xor     edx, edx; lpSource
0x1800398f6  mov     [rsp+478h+lpBuffer], rcx; lpBuffer
0x1800398fb  mov     ecx, r14d; dwFlags
0x1800398fe  call    cs:__imp_FormatMessageW
0x180039904  test    eax, eax
0x180039906  jz      short loc_180039930
0x180039908  mov     rcx, rbx; lpString
0x18003990b  call    cs:__imp_lstrlenW
0x180039911  cmp     eax, 3
0x180039914  jle     short loc_180039953
0x180039916  movsxd  rcx, eax
0x180039919  cmp     word ptr [rbx+rcx*2-4], 0Dh
0x18003991f  jnz     short loc_180039953
0x180039921  cmp     word ptr [rbx+rcx*2-2], 0Ah
0x180039927  jnz     short loc_180039953
0x180039929  mov     [rbx+rcx*2-4], bp
0x18003992e  jmp     short loc_180039953
0x180039930  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x180039935  test    eax, eax
0x180039937  jns     short loc_180039953
0x180039939  lea     r9, aCommonLanguage; "Common Language Runtime Internal error:"...
0x180039940  mov     dword ptr [rsp+478h+lpBuffer], edi
0x180039944  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180039948  mov     rdx, r14; BufferCount
0x18003994b  mov     rcx, rbx; Buffer
0x18003994e  call    _snwprintf_s
0x180039953  mov     eax, edi
0x180039955  mov     rcx, [rsp+478h+var_38]
0x18003995d  xor     rcx, rsp; StackCookie
0x180039960  call    __security_check_cookie
0x180039965  add     rsp, 450h
0x18003996c  pop     r14
0x18003996e  pop     rdi
0x18003996f  pop     rsi
0x180039970  pop     rbp
0x180039971  pop     rbx
0x180039972  retn
0x180039973  movzx   edx, di
0x180039976  lea     r8, [rsp+478h+Format]
0x18003997b  mov     r9d, 200h
0x180039981  mov     ecx, 4
0x180039986  call    ?UtilLoadResourceString@@YAJW4ResourceCategory@CCompRC@@IPEAGH@Z; UtilLoadResourceString(CCompRC::ResourceCategory,uint,ushort *,int)
0x18003998b  test    eax, eax
0x18003998d  jnz     short loc_180039937
0x18003998f  lea     r9, [rsp+478h+Format]; Format
0x180039994  mov     [rsp+478h+lpBuffer], rsi; ArgList
0x180039999  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003999d  mov     rdx, r14; BufferCount
0x1800399a0  mov     rcx, rbx; Buffer
0x1800399a3  call    _vsnwprintf_s
0x1800399a8  jmp     short loc_180039953
```
