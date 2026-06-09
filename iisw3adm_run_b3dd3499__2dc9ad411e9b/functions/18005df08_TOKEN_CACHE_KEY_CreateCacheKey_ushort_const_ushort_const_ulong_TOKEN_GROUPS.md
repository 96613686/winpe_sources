# TOKEN_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ulong,_TOKEN_GROUPS *)

- ea: `0x18005df08`
- end: `0x18005e0cf`
- name: `?CreateCacheKey@TOKEN_CACHE_KEY@@QEAAJPEBG0KPEAU_TOKEN_GROUPS@@@Z`
- size: `455`
- prototype: `int(TOKEN_CACHE_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005e468`

## callees

- `0x18005df08`
- `0x180061060`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18005df89`
- `msvcrt!_wcsupr` at `0x18005df89`
- `msvcrt!_ultow` at `0x18005df9c`
- `msvcrt!_ultow` at `0x18005e056`
- `msvcrt!_ultow` at `0x18005df9c`
- `msvcrt!_ultow` at `0x18005e056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e08e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e08e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005df4b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005df4b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005df63`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005df77`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005dfaa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005dfc2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e012`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e03c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e064`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e078`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005df63`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005df77`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005dfaa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005dfc2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e012`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e03c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e064`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005e078`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005dffc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005dffc`

## pseudocode

```c
int __fastcall TOKEN_CACHE_KEY::CreateCacheKey(
        wchar_t **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct _TOKEN_GROUPS *a5)
{
  int result; // eax
  int v9; // edi
  int v10; // ebp
  LPWSTR StringSid; // [rsp+20h] [rbp-98h] BYREF
  wchar_t Buffer[40]; // [rsp+30h] [rbp-88h] BYREF

  if ( !a2 || !a3 )
    return -2147024809;
  result = STRU::Copy((STRU *)this, a2);
  if ( result >= 0 )
  {
    result = STRU::Append((STRU *)this, L"\\");
    if ( result >= 0 )
    {
      result = STRU::Append((STRU *)this, a3);
      if ( result >= 0 )
      {
        _wcsupr(this[4]);
        _ultow(a4, Buffer, 10);
        result = STRU::Append((STRU *)this, Buffer);
        if ( result >= 0 )
        {
          result = STRU::Append((STRU *)this, L"\\");
          if ( result >= 0 )
          {
            if ( a5 )
            {
              v9 = 0;
              if ( a5->GroupCount )
              {
                while ( 1 )
                {
                  StringSid = 0;
                  if ( !ConvertSidToStringSidW(a5->Groups[v9].Sid, &StringSid) )
                    break;
                  v10 = STRU::Append((STRU *)this, StringSid);
                  if ( v10 < 0 )
                  {
                    LocalFree(StringSid);
                    return v10;
                  }
                  LocalFree(StringSid);
                  StringSid = 0;
                  result = STRU::Append((STRU *)this, L"\\");
                  if ( result >= 0 )
                  {
                    _ultow(a5->Groups[v9].Attributes, Buffer, 10);
                    result = STRU::Append((STRU *)this, Buffer);
                    if ( result >= 0 )
                    {
                      result = STRU::Append((STRU *)this, L"\\");
                      if ( result >= 0 && ++v9 < a5->GroupCount )
                        continue;
                    }
                  }
                  return result;
                }
                result = GetLastError();
                if ( result > 0 )
                  return (unsigned __int16)result | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005df08  push    rbx
0x18005df0a  push    rbp
0x18005df0b  push    rsi
0x18005df0c  push    rdi
0x18005df0d  push    r14
0x18005df0f  sub     rsp, 90h
0x18005df16  mov     rax, cs:__security_cookie
0x18005df1d  xor     rax, rsp
0x18005df20  mov     [rsp+0B8h+var_38], rax
0x18005df28  mov     rsi, [rsp+0B8h+arg_20]
0x18005df30  mov     ebp, r9d
0x18005df33  mov     rdi, r8
0x18005df36  mov     rbx, rcx
0x18005df39  test    rdx, rdx
0x18005df3c  jz      loc_18005E0AC
0x18005df42  test    r8, r8
0x18005df45  jz      loc_18005E0AC
0x18005df4b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005df51  test    eax, eax
0x18005df53  js      loc_18005E0B1
0x18005df59  lea     rdx, asc_180065770; "\\"
0x18005df60  mov     rcx, rbx
0x18005df63  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005df69  test    eax, eax
0x18005df6b  js      loc_18005E0B1
0x18005df71  mov     rdx, rdi
0x18005df74  mov     rcx, rbx
0x18005df77  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005df7d  test    eax, eax
0x18005df7f  js      loc_18005E0B1
0x18005df85  mov     rcx, [rbx+20h]; String
0x18005df89  call    cs:__imp__wcsupr
0x18005df8f  mov     r8d, 0Ah; Radix
0x18005df95  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18005df9a  mov     ecx, ebp; Value
0x18005df9c  call    cs:__imp__ultow
0x18005dfa2  lea     rdx, [rsp+0B8h+Buffer]
0x18005dfa7  mov     rcx, rbx
0x18005dfaa  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005dfb0  test    eax, eax
0x18005dfb2  js      loc_18005E0B1
0x18005dfb8  lea     rdx, asc_180065770; "\\"
0x18005dfbf  mov     rcx, rbx
0x18005dfc2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005dfc8  test    eax, eax
0x18005dfca  js      loc_18005E0B1
0x18005dfd0  test    rsi, rsi
0x18005dfd3  jz      loc_18005E0B1
0x18005dfd9  xor     edi, edi
0x18005dfdb  cmp     [rsi], edi
0x18005dfdd  jbe     loc_18005E0B1
0x18005dfe3  mov     r14d, edi
0x18005dfe6  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x18005dfeb  add     r14, r14
0x18005dfee  mov     [rsp+0B8h+StringSid], 0
0x18005dff7  mov     rcx, [rsi+r14*8+8]; Sid
0x18005dffc  call    cs:__imp_ConvertSidToStringSidW
0x18005e002  test    eax, eax
0x18005e004  jz      loc_18005E098
0x18005e00a  mov     rdx, [rsp+0B8h+StringSid]
0x18005e00f  mov     rcx, rbx
0x18005e012  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005e018  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x18005e01d  mov     ebp, eax
0x18005e01f  test    eax, eax
0x18005e021  js      short loc_18005E08E
0x18005e023  call    cs:__imp_LocalFree
0x18005e029  lea     rdx, asc_180065770; "\\"
0x18005e030  mov     [rsp+0B8h+StringSid], 0
0x18005e039  mov     rcx, rbx
0x18005e03c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005e042  test    eax, eax
0x18005e044  js      short loc_18005E0B1
0x18005e046  mov     ecx, [rsi+r14*8+10h]; Value
0x18005e04b  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18005e050  mov     r8d, 0Ah; Radix
0x18005e056  call    cs:__imp__ultow
0x18005e05c  lea     rdx, [rsp+0B8h+Buffer]
0x18005e061  mov     rcx, rbx
0x18005e064  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005e06a  test    eax, eax
0x18005e06c  js      short loc_18005E0B1
0x18005e06e  lea     rdx, asc_180065770; "\\"
0x18005e075  mov     rcx, rbx
0x18005e078  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005e07e  test    eax, eax
0x18005e080  js      short loc_18005E0B1
0x18005e082  inc     edi
0x18005e084  cmp     edi, [rsi]
0x18005e086  jb      loc_18005DFE3
0x18005e08c  jmp     short loc_18005E0B1
0x18005e08e  call    cs:__imp_LocalFree
0x18005e094  mov     eax, ebp
0x18005e096  jmp     short loc_18005E0B1
0x18005e098  call    cs:__imp_GetLastError
0x18005e09e  test    eax, eax
0x18005e0a0  jle     short loc_18005E0B1
0x18005e0a2  movzx   eax, ax
0x18005e0a5  or      eax, 80070000h
0x18005e0aa  jmp     short loc_18005E0B1
0x18005e0ac  mov     eax, 80070057h
0x18005e0b1  mov     rcx, [rsp+0B8h+var_38]
0x18005e0b9  xor     rcx, rsp; StackCookie
0x18005e0bc  call    __security_check_cookie
0x18005e0c1  add     rsp, 90h
0x18005e0c8  pop     r14
0x18005e0ca  pop     rdi
0x18005e0cb  pop     rsi
0x18005e0cc  pop     rbp
0x18005e0cd  pop     rbx
0x18005e0ce  retn
```
