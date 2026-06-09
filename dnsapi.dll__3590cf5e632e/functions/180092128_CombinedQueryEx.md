# CombinedQueryEx

- ea: `0x180092128`
- end: `0x180092308`
- name: `CombinedQueryEx`
- size: `480`
- prototype: `__int64 __fastcall(PVOID Parameter, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180096640`
- `0x1800966b0`
- `0x180096720`

## callees

- `0x1800112d0`
- `0x180029d80`
- `0x18002b050`
- `0x18008b5f0`
- `0x180092128`
- `0x180093bc0`
- `0x1800ce9f8`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800922ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800922ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180092270`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180092270`

## pseudocode

```c
ULONG __fastcall CombinedQueryEx(_QWORD *Parameter, int a2, int a3)
{
  void *v6; // rbp
  __int64 *v7; // r9
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rax
  void *v11; // rax
  int v12; // ebx
  HANDLE v13; // rax
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+44h] [rbp-24h] BYREF

  ThreadId = 0;
  if ( g_fVelocityDisableInternalExports )
    return 120;
  v6 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    if ( a2 == 1 )
    {
      v7 = (__int64 *)Parameter[1];
      v8 = &qword_1800F6058;
    }
    else
    {
      v8 = (const unsigned __int16 *)Parameter[1];
      v7 = &qword_1800F61A0;
    }
    WPP_SF_SsdDq(
      *((unsigned __int16 *)Parameter + 8),
      (_DWORD)v8,
      a3,
      (_DWORD)v7,
      (__int64)v8,
      *((_WORD *)Parameter + 8),
      *((_DWORD *)Parameter + 5),
      Parameter[8]);
  }
  *((_DWORD *)Parameter + 7) = a2;
  if ( a2 == 1 )
  {
    Parameter[13] = 0;
  }
  else if ( (unsigned int)(a2 - 2) <= 1 )
  {
    v9 = Parameter[1];
    if ( !v9 )
      return 87;
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(v9 + v10) );
    v11 = (void *)Dns_Allocate(2 * (unsigned int)(unsigned __int16)v10 + 2);
    v6 = v11;
    if ( !v11 )
      return 14;
    if ( !(unsigned int)Dns_StringCopy(v11, a2, 1) )
    {
      v12 = 123;
LABEL_26:
      DnsApiFree(v6);
      return v12;
    }
    Parameter[1] = v6;
    Parameter[13] = v9;
  }
  if ( !Parameter[8] )
    return ShimDnsQueryEx(Parameter);
  v13 = CreateThread(0, 0, ShimDnsQueryEx, Parameter, 0, &ThreadId);
  if ( !v13 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( SBYTE3(xmmword_1801119E0) < 0 )
      WPP_SF_d(1055, 116, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, LastError);
    if ( !v12 )
      v12 = 14;
    goto LABEL_26;
  }
  CloseHandle(v13);
  return 997;
}

```

## disassembly

```asm
0x180092128  mov     [rsp+arg_8], rbx
0x18009212d  mov     [rsp+arg_10], rbp
0x180092132  push    rsi
0x180092133  push    rdi
0x180092134  push    r14
0x180092136  sub     rsp, 50h
0x18009213a  mov     rax, cs:__security_cookie
0x180092141  xor     rax, rsp
0x180092144  mov     [rsp+68h+var_20], rax
0x180092149  cmp     cs:g_fVelocityDisableInternalExports, 0
0x180092150  mov     edi, edx
0x180092152  mov     rbx, rcx
0x180092155  mov     [rsp+68h+ThreadId], 0
0x18009215d  jz      short loc_180092169
0x18009215f  mov     eax, 78h ; 'x'
0x180092164  jmp     loc_1800922E5
0x180092169  xor     ebp, ebp
0x18009216b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180092172  jz      short loc_1800921B3
0x180092174  cmp     edi, 1
0x180092177  jnz     short loc_180092186
0x180092179  mov     r9, [rcx+8]
0x18009217d  lea     rdx, qword_1800F6058
0x180092184  jmp     short loc_180092191
0x180092186  mov     rdx, [rcx+8]
0x18009218a  lea     r9, qword_1800F61A0
0x180092191  mov     rax, [rbx+40h]
0x180092195  movzx   ecx, word ptr [rcx+10h]
0x180092199  mov     [rsp+68h+var_30], rax
0x18009219e  mov     eax, [rbx+14h]
0x1800921a1  mov     [rsp+68h+var_38], eax
0x1800921a5  mov     dword ptr [rsp+68h+lpThreadId], ecx
0x1800921a9  mov     qword ptr [rsp+68h+dwCreationFlags], rdx
0x1800921ae  call    WPP_SF_SsdDq
0x1800921b3  mov     [rbx+1Ch], edi
0x1800921b6  cmp     edi, 1
0x1800921b9  jnz     short loc_1800921C4
0x1800921bb  mov     [rbx+68h], rbp
0x1800921bf  jmp     loc_180092245
0x1800921c4  lea     eax, [rdi-2]
0x1800921c7  cmp     eax, 1
0x1800921ca  ja      short loc_180092245
0x1800921cc  mov     rsi, [rbx+8]
0x1800921d0  mov     [rsp+68h+var_28], ebp
0x1800921d4  test    rsi, rsi
0x1800921d7  jnz     short loc_1800921E1
0x1800921d9  lea     eax, [rsi+57h]
0x1800921dc  jmp     loc_1800922E5
0x1800921e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800921e5  inc     rax
0x1800921e8  cmp     [rsi+rax], bpl
0x1800921ec  jnz     short loc_1800921E5
0x1800921ee  movzx   r14d, ax
0x1800921f2  lea     eax, ds:2[r14*2]
0x1800921fa  mov     ecx, eax
0x1800921fc  mov     [rsp+68h+var_28], eax
0x180092200  call    Dns_Allocate
0x180092205  mov     rbp, rax
0x180092208  test    rax, rax
0x18009220b  jnz     short loc_180092215
0x18009220d  lea     eax, [rbp+0Eh]
0x180092210  jmp     loc_1800922E5
0x180092215  mov     dword ptr [rsp+68h+lpThreadId], 1; int
0x18009221d  lea     rdx, [rsp+68h+var_28]
0x180092222  mov     r9d, r14d
0x180092225  mov     [rsp+68h+dwCreationFlags], edi; int
0x180092229  mov     r8, rsi
0x18009222c  mov     rcx, rbp; void *
0x18009222f  call    Dns_StringCopy
0x180092234  test    eax, eax
0x180092236  jnz     short loc_18009223D
0x180092238  lea     ebx, [rax+7Bh]
0x18009223b  jmp     short loc_1800922BB
0x18009223d  mov     [rbx+8], rbp
0x180092241  mov     [rbx+68h], rsi
0x180092245  cmp     qword ptr [rbx+40h], 0
0x18009224a  jz      loc_1800922DD
0x180092250  lea     rax, [rsp+68h+ThreadId]
0x180092255  mov     r9, rbx; lpParameter
0x180092258  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18009225d  lea     r8, ShimDnsQueryEx; lpStartAddress
0x180092264  xor     edx, edx; dwStackSize
0x180092266  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18009226e  xor     ecx, ecx; lpThreadAttributes
0x180092270  call    cs:__imp_CreateThread
0x180092277  nop     dword ptr [rax+rax+00h]
0x18009227c  test    rax, rax
0x18009227f  jnz     short loc_1800922C7
0x180092281  call    cs:__imp_GetLastError
0x180092288  nop     dword ptr [rax+rax+00h]
0x18009228d  mov     ebx, eax
0x18009228f  cmp     byte ptr cs:xmmword_1801119E0+3, 0
0x180092296  jge     short loc_1800922B1
0x180092298  mov     edx, 74h ; 't'
0x18009229d  lea     r8, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids
0x1800922a4  mov     ecx, 41Fh
0x1800922a9  mov     r9d, eax
0x1800922ac  call    WPP_SF_d
0x1800922b1  test    ebx, ebx
0x1800922b3  mov     eax, 0Eh
0x1800922b8  cmovz   ebx, eax
0x1800922bb  mov     rcx, rbp; lpMem
0x1800922be  call    DnsApiFree
0x1800922c3  mov     eax, ebx
0x1800922c5  jmp     short loc_1800922E5
0x1800922c7  mov     rcx, rax; hObject
0x1800922ca  call    cs:__imp_CloseHandle
0x1800922d1  nop     dword ptr [rax+rax+00h]
0x1800922d6  mov     eax, 3E5h
0x1800922db  jmp     short loc_1800922E5
0x1800922dd  mov     rcx, rbx; Parameter
0x1800922e0  call    ShimDnsQueryEx
0x1800922e5  mov     rcx, [rsp+68h+var_20]
0x1800922ea  xor     rcx, rsp; StackCookie
0x1800922ed  call    __security_check_cookie
0x1800922f2  lea     r11, [rsp+68h+var_18]
0x1800922f7  mov     rbx, [r11+28h]
0x1800922fb  mov     rbp, [r11+30h]
0x1800922ff  mov     rsp, r11
0x180092302  pop     r14
0x180092304  pop     rdi
0x180092305  pop     rsi
0x180092306  retn
```
