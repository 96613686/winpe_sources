# CRevertToken::~CRevertToken(void)

- ea: `0x18006ed20`
- end: `0x18006ed6c`
- name: `??1CRevertToken@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CRevertToken *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18003db80`
- `0x1800465e0`
- `0x1800b0b22`
- `0x1800b1bbe`

## callees

- `0x18006ed20`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006ed2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006ed2f`

## string_xrefs

- `0x18006ed43`: `Failed to restore the previous impersonation token. status = %d`
- `0x18006ed55`: `CRevertToken::~CRevertToken`

## pseudocode

```c
void __fastcall CRevertToken::~CRevertToken(HANDLE *this)
{
  DWORD LastError; // [rsp+28h] [rbp-10h]

  if ( *((_BYTE *)this + 8) )
  {
    if ( !SetThreadToken(0, *this) )
    {
      LastError = GetLastError();
      TraceMsg(
        2,
        0,
        L"CRevertToken::~CRevertToken",
        112,
        L"Failed to restore the previous impersonation token. status = %d",
        LastError);
    }
  }
}

```

## disassembly

```asm
0x18006ed20  sub     rsp, 38h
0x18006ed24  cmp     byte ptr [rcx+8], 0
0x18006ed28  jz      short loc_18006ED67
0x18006ed2a  mov     rdx, [rcx]; Token
0x18006ed2d  xor     ecx, ecx; Thread
0x18006ed2f  call    cs:__imp_SetThreadToken
0x18006ed35  test    eax, eax
0x18006ed37  jnz     short loc_18006ED67
0x18006ed39  call    cs:__imp_GetLastError
0x18006ed3f  mov     [rsp+38h+var_10], eax
0x18006ed43  lea     rax, aFailedToRestor; "Failed to restore the previous imperson"...
0x18006ed4a  mov     [rsp+38h+var_18], rax
0x18006ed4f  mov     r9d, 70h ; 'p'
0x18006ed55  lea     r8, aCreverttokenCr; "CRevertToken::~CRevertToken"
0x18006ed5c  xor     edx, edx
0x18006ed5e  lea     ecx, [rdx+2]
0x18006ed61  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18006ed66  nop
0x18006ed67  add     rsp, 38h
0x18006ed6b  retn
```
