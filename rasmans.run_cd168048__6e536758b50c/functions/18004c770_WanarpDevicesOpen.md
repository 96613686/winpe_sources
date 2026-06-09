# WanarpDevicesOpen

- ea: `0x18004c770`
- end: `0x18004c99c`
- name: `WanarpDevicesOpen`
- size: `556`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002e050`
- `0x18004c5f0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18004c770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c909`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004c84e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004c8f0`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004c84e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004c8f0`

## pseudocode

```c
__int64 __fastcall WanarpDevicesOpen(_QWORD *a1, _QWORD *a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  bool v8; // zf
  DWORD LastError; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 631, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a1 )
  {
    v8 = (char *)g_hWanarp + 1 == 0;
    *a1 = -1;
    if ( v8 )
    {
      g_hWanarp = CreateFileA("\\\\.\\WANARP", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( g_hWanarp == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v5;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_34;
          v6 = 633;
LABEL_19:
          v7 = LastError;
          goto LABEL_11;
        }
      }
    }
    if ( !a2 )
      goto LABEL_28;
    goto LABEL_21;
  }
  if ( a2 )
  {
LABEL_21:
    v8 = (char *)g_hWanarpv6 + 1 == 0;
    *a2 = -1;
    if ( v8 )
    {
      g_hWanarpv6 = CreateFileA("\\\\.\\WANARPV6", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( g_hWanarpv6 == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v5;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_34;
          v6 = 634;
          goto LABEL_19;
        }
LABEL_29:
        if ( a1 )
          *a1 = g_hWanarp;
        if ( a2 )
          *a2 = g_hWanarpv6;
        goto LABEL_33;
      }
    }
LABEL_28:
    if ( v5 )
      goto LABEL_33;
    goto LABEL_29;
  }
  v5 = 87;
  if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v5;
  if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 2u )
  {
    v6 = 632;
    v7 = 87;
LABEL_11:
    WPP_SF_d(v4[1].Flink, v6, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v7);
LABEL_33:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 635, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18004c770  push    rbx
0x18004c772  push    rsi
0x18004c773  push    rdi
0x18004c774  push    r12
0x18004c776  push    r14
0x18004c778  push    r15
0x18004c77a  sub     rsp, 48h
0x18004c77e  mov     rdi, rdx
0x18004c781  mov     rsi, rcx
0x18004c784  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c78b  lea     r15, WPP_GLOBAL_Control
0x18004c792  lea     r12, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004c799  mov     r14d, 2000h
0x18004c79f  cmp     rcx, r15
0x18004c7a2  jz      short loc_18004C7C8
0x18004c7a4  test    [rcx+1Ch], r14d
0x18004c7a8  jz      short loc_18004C7C8
0x18004c7aa  cmp     byte ptr [rcx+19h], 6
0x18004c7ae  jb      short loc_18004C7C8
0x18004c7b0  mov     rcx, [rcx+10h]
0x18004c7b4  mov     edx, 277h
0x18004c7b9  mov     r8, r12
0x18004c7bc  call    WPP_SF_
0x18004c7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7c8  xor     ebx, ebx
0x18004c7ca  test    rsi, rsi
0x18004c7cd  jnz     short loc_18004C811
0x18004c7cf  test    rdi, rdi
0x18004c7d2  jnz     loc_18004C8B3
0x18004c7d8  lea     ebx, [rsi+57h]
0x18004c7db  cmp     rcx, r15
0x18004c7de  jz      loc_18004C98B
0x18004c7e4  test    [rcx+1Ch], r14d
0x18004c7e8  jz      loc_18004C966
0x18004c7ee  cmp     byte ptr [rcx+19h], 2
0x18004c7f2  jb      loc_18004C966
0x18004c7f8  mov     edx, 278h
0x18004c7fd  mov     r9d, ebx
0x18004c800  mov     rcx, [rcx+10h]
0x18004c804  mov     r8, r12
0x18004c807  call    WPP_SF_d
0x18004c80c  jmp     loc_18004C95F
0x18004c811  cmp     cs:g_hWanarp, 0FFFFFFFFFFFFFFFFh
0x18004c819  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004c820  jnz     loc_18004C8AA
0x18004c826  xor     r9d, r9d; lpSecurityAttributes
0x18004c829  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18004c82e  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004c836  lea     rcx, aWanarp; "\\\\.\\WANARP"
0x18004c83d  mov     edx, 0C0000000h; dwDesiredAccess
0x18004c842  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004c84a  lea     r8d, [r9+3]; dwShareMode
0x18004c84e  call    cs:__imp_CreateFileA
0x18004c855  nop     dword ptr [rax+rax+00h]
0x18004c85a  mov     cs:g_hWanarp, rax
0x18004c861  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c865  jnz     short loc_18004C8AA
0x18004c867  call    cs:__imp_GetLastError
0x18004c86e  nop     dword ptr [rax+rax+00h]
0x18004c873  mov     ebx, eax
0x18004c875  test    eax, eax
0x18004c877  jz      short loc_18004C8AA
0x18004c879  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c880  cmp     rcx, r15
0x18004c883  jz      loc_18004C98B
0x18004c889  test    [rcx+1Ch], r14d
0x18004c88d  jz      loc_18004C966
0x18004c893  cmp     byte ptr [rcx+19h], 2
0x18004c897  jb      loc_18004C966
0x18004c89d  mov     edx, 279h
0x18004c8a2  mov     r9d, eax
0x18004c8a5  jmp     loc_18004C800
0x18004c8aa  test    rdi, rdi
0x18004c8ad  jz      loc_18004C93D
0x18004c8b3  cmp     cs:g_hWanarpv6, 0FFFFFFFFFFFFFFFFh
0x18004c8bb  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18004c8c2  jnz     short loc_18004C93D
0x18004c8c4  xor     r9d, r9d; lpSecurityAttributes
0x18004c8c7  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18004c8d0  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004c8d8  lea     rcx, aWanarpv6; "\\\\.\\WANARPV6"
0x18004c8df  mov     edx, 0C0000000h; dwDesiredAccess
0x18004c8e4  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004c8ec  lea     r8d, [r9+3]; dwShareMode
0x18004c8f0  call    cs:__imp_CreateFileA
0x18004c8f7  nop     dword ptr [rax+rax+00h]
0x18004c8fc  mov     cs:g_hWanarpv6, rax
0x18004c903  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c907  jnz     short loc_18004C93D
0x18004c909  call    cs:__imp_GetLastError
0x18004c910  nop     dword ptr [rax+rax+00h]
0x18004c915  mov     ebx, eax
0x18004c917  test    eax, eax
0x18004c919  jz      short loc_18004C941
0x18004c91b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c922  cmp     rcx, r15
0x18004c925  jz      short loc_18004C98B
0x18004c927  test    [rcx+1Ch], r14d
0x18004c92b  jz      short loc_18004C966
0x18004c92d  cmp     byte ptr [rcx+19h], 2
0x18004c931  jb      short loc_18004C966
0x18004c933  mov     edx, 27Ah
0x18004c938  jmp     loc_18004C8A2
0x18004c93d  test    ebx, ebx
0x18004c93f  jnz     short loc_18004C95F
0x18004c941  test    rsi, rsi
0x18004c944  jz      short loc_18004C950
0x18004c946  mov     rax, cs:g_hWanarp
0x18004c94d  mov     [rsi], rax
0x18004c950  test    rdi, rdi
0x18004c953  jz      short loc_18004C95F
0x18004c955  mov     rax, cs:g_hWanarpv6
0x18004c95c  mov     [rdi], rax
0x18004c95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c966  cmp     rcx, r15
0x18004c969  jz      short loc_18004C98B
0x18004c96b  test    [rcx+1Ch], r14d
0x18004c96f  jz      short loc_18004C98B
0x18004c971  cmp     byte ptr [rcx+19h], 6
0x18004c975  jb      short loc_18004C98B
0x18004c977  mov     rcx, [rcx+10h]
0x18004c97b  mov     edx, 27Bh
0x18004c980  mov     r9d, ebx
0x18004c983  mov     r8, r12
0x18004c986  call    WPP_SF_d
0x18004c98b  mov     eax, ebx
0x18004c98d  add     rsp, 48h
0x18004c991  pop     r15
0x18004c993  pop     r14
0x18004c995  pop     r12
0x18004c997  pop     rdi
0x18004c998  pop     rsi
0x18004c999  pop     rbx
0x18004c99a  retn
```
