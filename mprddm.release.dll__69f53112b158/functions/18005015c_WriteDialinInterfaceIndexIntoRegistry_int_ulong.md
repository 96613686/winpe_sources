# WriteDialinInterfaceIndexIntoRegistry(int,ulong)

- ea: `0x18005015c`
- end: `0x180050333`
- name: `?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z`
- size: `471`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18004f4cc`
- `0x1800515a4`
- `0x180052d5c`
- `0x180058dac`

## callees

- `0x18005015c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800502be`
- `ADVAPI32!RegCloseKey` at `0x1800502be`
- `ADVAPI32!RegOpenKeyExA` at `0x18005021e`
- `ADVAPI32!RegOpenKeyExA` at `0x18005021e`
- `ADVAPI32!RegSetValueExA` at `0x180050263`
- `ADVAPI32!RegSetValueExA` at `0x180050263`

## string_xrefs

- `0x1800501f6`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x1800501ed`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x180050281`: `Failed to write InterfaceIndex into registry. Error: %d`
- `0x1800502e0`: `Failed to open the registry key %hs. Error: %d.`

## pseudocode

```c
void __fastcall WriteDialinInterfaceIndexIntoRegistry(unsigned int a1, unsigned int a2)
{
  const CHAR *v4; // rbx
  unsigned int v5; // eax
  const CHAR *v6; // rdx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[2044]; // [rsp+44h] [rbp-BCh] BYREF

  *(_DWORD *)Data = a2;
  hKey = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"bIPv4 = %d. dwAdapterIndex: %d", a1, a2);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v9);
  }
  v4 = "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip";
  if ( !a1 )
    v4 = "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6";
  v5 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, v4, 0, 0x20007u, &hKey);
  if ( v5 )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"Failed to open the registry key %hs. Error: %d.", v4, v5);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v9);
    }
  }
  else
  {
    v6 = "ServerIfIndexV4";
    if ( !a1 )
      v6 = "ServerIfIndexV6";
    if ( !RegSetValueExA(hKey, v6, 0, 4u, Data, 4u) )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"Failed to write InterfaceIndex into registry. Error: %d", *(unsigned int *)Data, 0);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v9);
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18005015c  mov     [rsp-8+arg_10], rbx
0x180050161  push    rbp
0x180050162  push    rsi
0x180050163  push    rdi
0x180050164  lea     rbp, [rsp-750h]
0x18005016c  sub     rsp, 850h
0x180050173  mov     rax, cs:__security_cookie
0x18005017a  xor     rax, rsp
0x18005017d  mov     [rbp+760h+var_20], rax
0x180050184  mov     ebx, edx
0x180050186  mov     dword ptr [rsp+860h+Data], edx
0x18005018a  mov     edi, ecx
0x18005018c  xor     esi, esi
0x18005018e  xor     edx, edx; Val
0x180050190  mov     [rsp+860h+hKey], rsi
0x180050195  lea     rcx, [rsp+860h+var_81C]; void *
0x18005019a  mov     [rsp+860h+var_820], esi
0x18005019e  mov     r8d, 7FCh; Size
0x1800501a4  call    memset_0
0x1800501a9  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x1800501b0  jz      short loc_1800501ED
0x1800501b2  mov     r9d, ebx
0x1800501b5  mov     word ptr [rsp+860h+var_820], si
0x1800501ba  mov     r8d, edi
0x1800501bd  lea     rdx, aBipv4DDwadapte; "bIPv4 = %d. dwAdapterIndex: %d"
0x1800501c4  lea     rcx, [rsp+860h+var_820]
0x1800501c9  call    FormatRRASErrorString
0x1800501ce  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800501d5  lea     r8, [rsp+860h+var_820]
0x1800501da  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800501e1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800501e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501ed  lea     rax, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x1800501f4  test    edi, edi
0x1800501f6  lea     rbx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x1800501fd  mov     r9d, 20007h; samDesired
0x180050203  cmovz   rbx, rax
0x180050207  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005020e  lea     rax, [rsp+860h+hKey]
0x180050213  mov     rdx, rbx; lpSubKey
0x180050216  xor     r8d, r8d; ulOptions
0x180050219  mov     [rsp+860h+phkResult], rax; phkResult
0x18005021e  call    cs:__imp_RegOpenKeyExA
0x180050225  nop     dword ptr [rax+rax+00h]
0x18005022a  test    eax, eax
0x18005022c  jnz     loc_1800502CC
0x180050232  mov     rcx, [rsp+860h+hKey]; hKey
0x180050237  lea     rax, aServerifindexv_0; "ServerIfIndexV6"
0x18005023e  mov     r9d, 4; dwType
0x180050244  lea     rdx, aServerifindexv; "ServerIfIndexV4"
0x18005024b  mov     [rsp+860h+cbData], r9d; cbData
0x180050250  test    edi, edi
0x180050252  cmovz   rdx, rax; lpValueName
0x180050256  lea     rax, [rsp+860h+Data]
0x18005025b  xor     r8d, r8d; Reserved
0x18005025e  mov     [rsp+860h+phkResult], rax; lpData
0x180050263  call    cs:__imp_RegSetValueExA
0x18005026a  nop     dword ptr [rax+rax+00h]
0x18005026f  test    eax, eax
0x180050271  jnz     short loc_1800502B9
0x180050273  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18005027a  jz      short loc_1800502B9
0x18005027c  mov     r8d, dword ptr [rsp+860h+Data]
0x180050281  lea     rdx, aFailedToWriteI; "Failed to write InterfaceIndex into reg"...
0x180050288  xor     r9d, r9d
0x18005028b  mov     word ptr [rsp+860h+var_820], si
0x180050290  lea     rcx, [rsp+860h+var_820]
0x180050295  call    FormatRRASErrorString
0x18005029a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800502a1  lea     r8, [rsp+860h+var_820]
0x1800502a6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800502ad  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800502b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502b9  mov     rcx, [rsp+860h+hKey]; hKey
0x1800502be  call    cs:__imp_RegCloseKey
0x1800502c5  nop     dword ptr [rax+rax+00h]
0x1800502ca  jmp     short loc_180050310
0x1800502cc  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x1800502d3  jz      short loc_180050310
0x1800502d5  mov     r9d, eax
0x1800502d8  mov     word ptr [rsp+860h+var_820], si
0x1800502dd  mov     r8, rbx
0x1800502e0  lea     rdx, aFailedToOpenTh; "Failed to open the registry key %hs. Er"...
0x1800502e7  lea     rcx, [rsp+860h+var_820]
0x1800502ec  call    FormatRRASErrorString
0x1800502f1  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800502f8  lea     r8, [rsp+860h+var_820]
0x1800502fd  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050304  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005030b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050310  mov     rcx, [rbp+760h+var_20]
0x180050317  xor     rcx, rsp; StackCookie
0x18005031a  call    __security_check_cookie
0x18005031f  mov     rbx, [rsp+860h+arg_10]
0x180050327  add     rsp, 850h
0x18005032e  pop     rdi
0x18005032f  pop     rsi
0x180050330  pop     rbp
0x180050331  retn
```
