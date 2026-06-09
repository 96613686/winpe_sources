# IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)

- ea: `0x1800611e8`
- end: `0x180061299`
- name: `?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z`
- size: `177`
- prototype: `__int64 __fastcall(void *, enum _TOKEN_INFORMATION_CLASS, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036954`

## callees

- `0x180049df0`
- `0x18005d7c4`
- `0x1800611e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006123c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006123c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180061232`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180061232`

## pseudocode

```c
__int64 __fastcall IsTokenBoolPresent(void *a1, enum _TOKEN_INFORMATION_CLASS a2, int *a3)
{
  signed int LastError; // eax
  int v5; // edx
  int v6; // ecx
  int v7; // r9d
  unsigned int v8; // ebx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  DWORD v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+44h] [rbp+Ch]
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF

  v12 = HIDWORD(a1);
  TokenInformation = 0;
  v11 = 0;
  *a3 = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppContainer, &TokenInformation, 4u, &v11) )
  {
    v8 = 0;
    *a3 = TokenInformation != 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( dword_180071078 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      ComTraceMessageT<long>(v6, v5, 58, v7, ReturnLength, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800611e8  mov     rax, rsp
0x1800611eb  mov     [rax+18h], rbx
0x1800611ef  mov     [rax+10h], edx
0x1800611f2  mov     [rax+8], rcx
0x1800611f6  push    rdi
0x1800611f7  sub     rsp, 30h
0x1800611fb  mov     r9d, 4; TokenInformationLength
0x180061201  mov     dword ptr [rax+10h], 0
0x180061208  mov     dword ptr [rax+8], 0
0x18006120f  lea     rax, [rax+8]
0x180061213  mov     rdi, r8
0x180061216  mov     dword ptr [r8], 0
0x18006121d  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180061222  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180061227  lea     edx, [r9+19h]; TokenInformationClass
0x18006122b  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180061232  call    cs:__imp_GetTokenInformation
0x180061238  test    eax, eax
0x18006123a  jnz     short loc_18006127F
0x18006123c  call    cs:__imp_GetLastError
0x180061242  mov     ebx, eax
0x180061244  test    eax, eax
0x180061246  jle     short loc_180061251
0x180061248  movzx   ebx, ax
0x18006124b  or      ebx, 80070000h
0x180061251  mov     eax, cs:dword_180071078
0x180061257  test    eax, eax
0x180061259  jnz     short loc_18006126E
0x18006125b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061261  jz      short loc_18006128C
0x180061263  xor     ecx, ecx
0x180061265  call    IsWppLevelEnabled
0x18006126a  test    al, al
0x18006126c  jz      short loc_18006128C
0x18006126e  mov     r8d, 3Ah ; ':'
0x180061274  mov     [rsp+38h+var_10], ebx
0x180061278  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18006127d  jmp     short loc_18006128C
0x18006127f  xor     ecx, ecx
0x180061281  xor     ebx, ebx
0x180061283  cmp     [rsp+38h+TokenInformation], ecx
0x180061287  setnz   cl
0x18006128a  mov     [rdi], ecx
0x18006128c  mov     eax, ebx
0x18006128e  mov     rbx, [rsp+38h+arg_10]
0x180061293  add     rsp, 30h
0x180061297  pop     rdi
0x180061298  retn
```
