# BuildRawCoreHeaders(_HTTP_RESPONSE_V2 *,STRA *)

- ea: `0x18000a794`
- end: `0x18000a9aa`
- name: `?BuildRawCoreHeaders@@YAJPEAU_HTTP_RESPONSE_V2@@PEAVSTRA@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct _HTTP_RESPONSE_V2 *, struct STRA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001d20`

## callees

- `0x18000a794`
- `0x18000c970`

## import_xrefs

- `msvcrt!_itoa_s` at `0x18000a7e4`
- `msvcrt!_itoa_s` at `0x18000a7e4`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a7f2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a825`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a885`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a7f2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a825`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000a885`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a810`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a846`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8a0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8bc`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8d7`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a91b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a932`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a94a`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a961`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a979`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a810`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a846`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8a0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8bc`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a8d7`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a91b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a932`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a94a`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a961`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000a979`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a7c3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000a7c3`

## pseudocode

```c
int __fastcall BuildRawCoreHeaders(struct _HTTP_RESPONSE_V2 *a1, struct STRA *a2)
{
  int result; // eax
  __int64 i; // rbp
  PCSTR pRawValue; // rax
  __int64 j; // rsi
  PHTTP_UNKNOWN_HEADER pUnknownHeaders; // r14
  char Buffer[32]; // [rsp+20h] [rbp-58h] BYREF

  result = STRA::Copy(a2, "HTTP/1.1 ");
  if ( result >= 0 )
  {
    _itoa_s(a1->StatusCode, Buffer, 0x20u, 10);
    result = STRA::Append(a2, Buffer);
    if ( result >= 0 )
    {
      result = STRA::Append(a2, " ", 1u);
      if ( result >= 0 )
      {
        result = STRA::Append(a2, a1->pReason);
        if ( result >= 0 )
        {
          result = STRA::Append(a2, "\r\n", 2u);
          if ( result >= 0 )
          {
            for ( i = 0; (unsigned int)i < 0x1E; i = (unsigned int)(i + 1) )
            {
              pRawValue = a1->Headers.KnownHeaders[(unsigned int)i].pRawValue;
              if ( pRawValue && *pRawValue )
              {
                result = STRA::Append(a2, (const char *)(&RESPONSE_HEADER_TABLE)[i]);
                if ( result < 0 )
                  return result;
                result = STRA::Append(a2, ": ", 2u);
                if ( result < 0 )
                  return result;
                result = STRA::Append(
                           a2,
                           a1->Headers.KnownHeaders[(unsigned int)i].pRawValue,
                           a1->Headers.KnownHeaders[(unsigned int)i].RawValueLength);
                if ( result < 0 )
                  return result;
                result = STRA::Append(a2, "\r\n", 2u);
                if ( result < 0 )
                  return result;
                a1->Headers.KnownHeaders[(unsigned int)i].pRawValue = 0;
                a1->Headers.KnownHeaders[(unsigned int)i].RawValueLength = 0;
              }
            }
            for ( j = 0; (unsigned int)j < a1->Headers.UnknownHeaderCount; j = (unsigned int)(j + 1) )
            {
              pUnknownHeaders = a1->Headers.pUnknownHeaders;
              result = STRA::Append(a2, pUnknownHeaders[j].pName, pUnknownHeaders[j].NameLength);
              if ( result < 0 )
                return result;
              result = STRA::Append(a2, ": ", 2u);
              if ( result < 0 )
                return result;
              result = STRA::Append(a2, pUnknownHeaders[j].pRawValue, pUnknownHeaders[j].RawValueLength);
              if ( result < 0 )
                return result;
              result = STRA::Append(a2, "\r\n", 2u);
              if ( result < 0 )
                return result;
            }
            result = STRA::Append(a2, "\r\n", 2u);
            if ( result >= 0 )
            {
              result = 0;
              a1->Headers.UnknownHeaderCount = 0;
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
0x18000a794  mov     [rsp+arg_10], rbx
0x18000a799  push    rbp
0x18000a79a  push    rsi
0x18000a79b  push    rdi
0x18000a79c  push    r14
0x18000a79e  push    r15
0x18000a7a0  sub     rsp, 50h
0x18000a7a4  mov     rax, cs:__security_cookie
0x18000a7ab  xor     rax, rsp
0x18000a7ae  mov     [rsp+78h+var_38], rax
0x18000a7b3  mov     rbx, rdx
0x18000a7b6  mov     rdi, rcx
0x18000a7b9  mov     rcx, rbx
0x18000a7bc  lea     rdx, Str2; "HTTP/1.1 "
0x18000a7c3  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000a7c9  test    eax, eax
0x18000a7cb  js      loc_18000A989
0x18000a7d1  movzx   ecx, word ptr [rdi+8]; Value
0x18000a7d5  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000a7da  mov     r9d, 0Ah; Radix
0x18000a7e0  lea     r8d, [r9+16h]; BufferCount
0x18000a7e4  call    cs:__imp__itoa_s
0x18000a7ea  lea     rdx, [rsp+78h+Buffer]
0x18000a7ef  mov     rcx, rbx
0x18000a7f2  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000a7f8  test    eax, eax
0x18000a7fa  js      loc_18000A989
0x18000a800  mov     r8d, 1
0x18000a806  lea     rdx, asc_18000EE88; " "
0x18000a80d  mov     rcx, rbx
0x18000a810  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a816  test    eax, eax
0x18000a818  js      loc_18000A989
0x18000a81e  mov     rdx, [rdi+10h]
0x18000a822  mov     rcx, rbx
0x18000a825  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000a82b  test    eax, eax
0x18000a82d  js      loc_18000A989
0x18000a833  mov     r15d, 2
0x18000a839  lea     rdx, SubStr; "\r\n"
0x18000a840  mov     r8d, r15d
0x18000a843  mov     rcx, rbx
0x18000a846  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a84c  test    eax, eax
0x18000a84e  js      loc_18000A989
0x18000a854  xor     ebp, ebp
0x18000a856  cmp     ebp, 1Eh
0x18000a859  jnb     loc_18000A8FC
0x18000a85f  mov     esi, ebp
0x18000a861  add     rsi, rsi
0x18000a864  mov     rax, [rdi+rsi*8+40h]
0x18000a869  test    rax, rax
0x18000a86c  jz      loc_18000A8F5
0x18000a872  cmp     byte ptr [rax], 0
0x18000a875  jz      short loc_18000A8F5
0x18000a877  lea     rax, ?RESPONSE_HEADER_TABLE@@3PAPEADA; char * near * RESPONSE_HEADER_TABLE
0x18000a87e  mov     rcx, rbx
0x18000a881  mov     rdx, [rax+rbp*8]
0x18000a885  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000a88b  test    eax, eax
0x18000a88d  js      loc_18000A989
0x18000a893  mov     r8d, r15d
0x18000a896  lea     rdx, asc_18000FB58; ": "
0x18000a89d  mov     rcx, rbx
0x18000a8a0  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a8a6  test    eax, eax
0x18000a8a8  js      loc_18000A989
0x18000a8ae  movzx   r8d, word ptr [rdi+rsi*8+38h]
0x18000a8b4  mov     rcx, rbx
0x18000a8b7  mov     rdx, [rdi+rsi*8+40h]
0x18000a8bc  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a8c2  test    eax, eax
0x18000a8c4  js      loc_18000A989
0x18000a8ca  mov     r8d, r15d
0x18000a8cd  lea     rdx, SubStr; "\r\n"
0x18000a8d4  mov     rcx, rbx
0x18000a8d7  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a8dd  test    eax, eax
0x18000a8df  js      loc_18000A989
0x18000a8e5  xor     eax, eax
0x18000a8e7  mov     qword ptr [rdi+rsi*8+40h], 0
0x18000a8f0  mov     [rdi+rsi*8+38h], ax
0x18000a8f5  inc     ebp
0x18000a8f7  jmp     loc_18000A856
0x18000a8fc  xor     esi, esi
0x18000a8fe  movzx   eax, word ptr [rdi+18h]
0x18000a902  mov     rcx, rbx
0x18000a905  cmp     esi, eax
0x18000a907  jnb     short loc_18000A96F
0x18000a909  mov     r14, [rdi+20h]
0x18000a90d  lea     rbp, [rsi+rsi*2]
0x18000a911  movzx   r8d, word ptr [r14+rbp*8]
0x18000a916  mov     rdx, [r14+rbp*8+8]
0x18000a91b  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a921  test    eax, eax
0x18000a923  js      short loc_18000A989
0x18000a925  mov     r8d, r15d
0x18000a928  lea     rdx, asc_18000FB58; ": "
0x18000a92f  mov     rcx, rbx
0x18000a932  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a938  test    eax, eax
0x18000a93a  js      short loc_18000A989
0x18000a93c  movzx   r8d, word ptr [r14+rbp*8+2]
0x18000a942  mov     rcx, rbx
0x18000a945  mov     rdx, [r14+rbp*8+10h]
0x18000a94a  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a950  test    eax, eax
0x18000a952  js      short loc_18000A989
0x18000a954  mov     r8d, r15d
0x18000a957  lea     rdx, SubStr; "\r\n"
0x18000a95e  mov     rcx, rbx
0x18000a961  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a967  test    eax, eax
0x18000a969  js      short loc_18000A989
0x18000a96b  inc     esi
0x18000a96d  jmp     short loc_18000A8FE
0x18000a96f  mov     r8d, r15d
0x18000a972  lea     rdx, SubStr; "\r\n"
0x18000a979  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000a97f  test    eax, eax
0x18000a981  js      short loc_18000A989
0x18000a983  xor     eax, eax
0x18000a985  mov     [rdi+18h], ax
0x18000a989  mov     rcx, [rsp+78h+var_38]
0x18000a98e  xor     rcx, rsp; StackCookie
0x18000a991  call    __security_check_cookie
0x18000a996  mov     rbx, [rsp+78h+arg_10]
0x18000a99e  add     rsp, 50h
0x18000a9a2  pop     r15
0x18000a9a4  pop     r14
0x18000a9a6  pop     rdi
0x18000a9a7  pop     rsi
0x18000a9a8  pop     rbp
0x18000a9a9  retn
```
