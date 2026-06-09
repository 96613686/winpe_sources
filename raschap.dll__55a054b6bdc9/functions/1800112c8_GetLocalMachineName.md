# GetLocalMachineName

- ea: `0x1800112c8`
- end: `0x18001140c`
- name: `GetLocalMachineName`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000db00`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x1800112c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800113d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800113d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011371`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001132b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001137f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001132b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001137f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113af`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011321`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800113a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011321`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800113a5`

## pseudocode

```c
__int64 __fastcall GetLocalMachineName(WCHAR **a1)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  WCHAR *v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  WCHAR *v7; // rax
  DWORD nSize; // [rsp+40h] [rbp+8h] BYREF

  nSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  *a1 = 0;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 234 )
    {
      v4 = 0;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_15;
      v6 = 32;
      goto LABEL_7;
    }
  }
  v7 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize + 2);
  v4 = v7;
  if ( v7 )
  {
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v7, &nSize) )
    {
      *a1 = v4;
      v4 = 0;
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v6 = 34;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v6 = 33;
LABEL_7:
      WPP_SF_d(v5[2], v6, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
    }
  }
LABEL_15:
  LocalFree(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800112c8  mov     [rsp+arg_8], rbx
0x1800112cd  mov     [rsp+arg_10], rbp
0x1800112d2  push    rsi
0x1800112d3  push    rdi
0x1800112d4  push    r14
0x1800112d6  sub     rsp, 20h
0x1800112da  mov     rsi, rcx
0x1800112dd  mov     [rsp+38h+nSize], 0
0x1800112e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112ec  lea     rbp, WPP_GLOBAL_Control
0x1800112f3  lea     r14, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800112fa  cmp     rcx, rbp
0x1800112fd  jz      short loc_180011310
0x1800112ff  mov     rcx, [rcx+10h]
0x180011303  mov     edx, 1Fh
0x180011308  mov     r8, r14
0x18001130b  call    WPP_SF_
0x180011310  xor     edx, edx; lpBuffer
0x180011312  mov     qword ptr [rsi], 0
0x180011319  lea     r8, [rsp+38h+nSize]; nSize
0x18001131e  lea     ecx, [rdx+3]; NameType
0x180011321  call    cs:__imp_GetComputerNameExW
0x180011327  test    eax, eax
0x180011329  jnz     short loc_180011360
0x18001132b  call    cs:__imp_GetLastError
0x180011331  mov     ebx, eax
0x180011333  cmp     eax, 0EAh
0x180011338  jz      short loc_180011360
0x18001133a  xor     edi, edi
0x18001133c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011343  cmp     rcx, rbp
0x180011346  jz      loc_1800113D1
0x18001134c  lea     edx, [rdi+20h]
0x18001134f  mov     rcx, [rcx+10h]
0x180011353  mov     r9d, eax
0x180011356  mov     r8, r14
0x180011359  call    WPP_SF_d
0x18001135e  jmp     short loc_1800113D1
0x180011360  mov     edx, [rsp+38h+nSize]
0x180011364  mov     ecx, 40h ; '@'; uFlags
0x180011369  lea     rdx, ds:2[rdx*2]; uBytes
0x180011371  call    cs:__imp_LocalAlloc
0x180011377  mov     rdi, rax
0x18001137a  test    rax, rax
0x18001137d  jnz     short loc_180011398
0x18001137f  call    cs:__imp_GetLastError
0x180011385  mov     ebx, eax
0x180011387  mov     rcx, cs:WPP_GLOBAL_Control
0x18001138e  cmp     rcx, rbp
0x180011391  jz      short loc_1800113D1
0x180011393  lea     edx, [rdi+21h]
0x180011396  jmp     short loc_18001134F
0x180011398  lea     r8, [rsp+38h+nSize]; nSize
0x18001139d  mov     rdx, rdi; lpBuffer
0x1800113a0  mov     ecx, 3; NameType
0x1800113a5  call    cs:__imp_GetComputerNameExW
0x1800113ab  test    eax, eax
0x1800113ad  jnz     short loc_1800113CA
0x1800113af  call    cs:__imp_GetLastError
0x1800113b5  mov     ebx, eax
0x1800113b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113be  cmp     rcx, rbp
0x1800113c1  jz      short loc_1800113D1
0x1800113c3  mov     edx, 22h ; '"'
0x1800113c8  jmp     short loc_18001134F
0x1800113ca  mov     [rsi], rdi
0x1800113cd  xor     edi, edi
0x1800113cf  xor     ebx, ebx
0x1800113d1  mov     rcx, rdi; hMem
0x1800113d4  call    cs:__imp_LocalFree
0x1800113da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113e1  cmp     rcx, rbp
0x1800113e4  jz      short loc_1800113F7
0x1800113e6  mov     rcx, [rcx+10h]
0x1800113ea  mov     edx, 23h ; '#'
0x1800113ef  mov     r8, r14
0x1800113f2  call    WPP_SF_
0x1800113f7  mov     rbp, [rsp+38h+arg_10]
0x1800113fc  mov     eax, ebx
0x1800113fe  mov     rbx, [rsp+38h+arg_8]
0x180011403  add     rsp, 20h
0x180011407  pop     r14
0x180011409  pop     rdi
0x18001140a  pop     rsi
0x18001140b  retn
```
