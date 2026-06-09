# IsRasmanProcessInternal

- ea: `0x18000f388`
- end: `0x18000f418`
- name: `IsRasmanProcessInternal`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f0bc`
- `0x18000f31c`

## callees

- `0x18000f388`
- `0x180063e9c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18000f394`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18000f394`
- `rtutils!TracePrintfExA` at `0x18000f3c0`
- `rtutils!TracePrintfExA` at `0x18000f405`
- `rtutils!TracePrintfExA` at `0x18000f3c0`
- `rtutils!TracePrintfExA` at `0x18000f405`

## pseudocode

```c
__int64 IsRasmanProcessInternal()
{
  unsigned int v0; // ebx
  LPSTR CommandLineA; // rax
  DWORD v2; // ecx
  const char *v3; // rdi
  const char *v4; // r9

  v0 = 0;
  CommandLineA = GetCommandLineA();
  v2 = g_dwTraceId;
  v3 = CommandLineA;
  if ( g_dwTraceId != -1 )
  {
    v4 = "NULL";
    if ( CommandLineA )
      v4 = CommandLineA;
    TracePrintfExA(g_dwTraceId, 0xCu, "IsRasmanProcess: CmdLine=%s\n", v4);
    v2 = g_dwTraceId;
  }
  if ( v3 )
  {
    if ( strstr_0(v3, "-k netsvcs") )
      v0 = 1;
    v2 = g_dwTraceId;
  }
  if ( v2 != -1 )
    TracePrintfExA(v2, 0xCu, "IsRasmanProcess: returning %d\n", v0);
  return v0;
}

```

## disassembly

```asm
0x18000f388  mov     [rsp+arg_0], rbx
0x18000f38d  push    rdi
0x18000f38e  sub     rsp, 20h
0x18000f392  xor     ebx, ebx
0x18000f394  call    cs:__imp_GetCommandLineA
0x18000f39a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000f3a0  mov     rdi, rax
0x18000f3a3  cmp     ecx, 0FFFFFFFFh
0x18000f3a6  jz      short loc_18000F3CC
0x18000f3a8  test    rax, rax
0x18000f3ab  lea     r9, aNull_0; "NULL"
0x18000f3b2  lea     r8, aIsrasmanproces; "IsRasmanProcess: CmdLine=%s\n"
0x18000f3b9  cmovnz  r9, rax
0x18000f3bd  lea     edx, [rbx+0Ch]; dwFlags
0x18000f3c0  call    cs:__imp_TracePrintfExA
0x18000f3c6  mov     ecx, cs:g_dwTraceId
0x18000f3cc  test    rdi, rdi
0x18000f3cf  jz      short loc_18000F3F1
0x18000f3d1  lea     rdx, aKNetsvcs; "-k netsvcs"
0x18000f3d8  mov     rcx, rdi; Str
0x18000f3db  call    strstr_0
0x18000f3e0  mov     ecx, 1
0x18000f3e5  test    rax, rax
0x18000f3e8  cmovnz  ebx, ecx
0x18000f3eb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000f3f1  cmp     ecx, 0FFFFFFFFh
0x18000f3f4  jz      short loc_18000F40B
0x18000f3f6  mov     r9d, ebx
0x18000f3f9  lea     r8, aIsrasmanproces_0; "IsRasmanProcess: returning %d\n"
0x18000f400  mov     edx, 0Ch; dwFlags
0x18000f405  call    cs:__imp_TracePrintfExA
0x18000f40b  mov     eax, ebx
0x18000f40d  mov     rbx, [rsp+28h+arg_0]
0x18000f412  add     rsp, 20h
0x18000f416  pop     rdi
0x18000f417  retn
```
