# WriteDialinInterfaceIndexIntoRegistry(int,ulong)

- ea: `0x18004e9b8`
- end: `0x18004eb8c`
- name: `?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z`
- size: `468`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18004ddd0`
- `0x18004fcec`
- `0x180051368`
- `0x180056f10`

## callees

- `0x18004e9b8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18004eb1c`
- `ADVAPI32!RegCloseKey` at `0x18004eb1c`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ea84`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ea84`
- `ADVAPI32!RegSetValueExA` at `0x18004eac6`
- `ADVAPI32!RegSetValueExA` at `0x18004eac6`

## string_xrefs

- `0x18004ea5c`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18004ea53`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x18004eadf`: `Failed to write InterfaceIndex into registry. Error: %d`
- `0x18004eb30`: `Failed to open the registry key %hs. Error: %d.`

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
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"bIPv4 = %d. dwAdapterIndex: %d", a1, a2);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v9);
  }
  v4 = "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip";
  if ( !a1 )
    v4 = "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6";
  v5 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, v4, 0, 0x20007u, &hKey);
  if ( v5 )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"Failed to open the registry key %hs. Error: %d.", v4, v5);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
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
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"Failed to write InterfaceIndex into registry. Error: %d", *(unsigned int *)Data, 0);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v9);
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18004e9b8  mov     [rsp-8+arg_10], rbx
0x18004e9bd  mov     [rsp-8+arg_18], rdi
0x18004e9c2  push    rbp
0x18004e9c3  lea     rbp, [rsp-750h]
0x18004e9cb  sub     rsp, 850h
0x18004e9d2  mov     rax, cs:__security_cookie
0x18004e9d9  xor     rax, rsp
0x18004e9dc  mov     [rbp+750h+var_10], rax
0x18004e9e3  mov     ebx, edx
0x18004e9e5  mov     dword ptr [rsp+850h+Data], edx
0x18004e9e9  mov     edi, ecx
0x18004e9eb  mov     [rsp+850h+hKey], 0
0x18004e9f4  xor     eax, eax
0x18004e9f6  lea     rcx, [rsp+850h+var_80C]; void *
0x18004e9fb  xor     edx, edx; Val
0x18004e9fd  mov     [rsp+850h+var_810], eax
0x18004ea01  mov     r8d, 7FCh; Size
0x18004ea07  call    memset_0
0x18004ea0c  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18004ea14  jz      short loc_18004EA53
0x18004ea16  xor     eax, eax
0x18004ea18  lea     rdx, aBipv4DDwadapte; "bIPv4 = %d. dwAdapterIndex: %d"
0x18004ea1f  mov     r9d, ebx
0x18004ea22  mov     word ptr [rsp+850h+var_810], ax
0x18004ea27  mov     r8d, edi
0x18004ea2a  lea     rcx, [rsp+850h+var_810]
0x18004ea2f  call    FormatRRASErrorString
0x18004ea34  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004ea3b  lea     r8, [rsp+850h+var_810]
0x18004ea40  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004ea47  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004ea4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea53  lea     rax, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x18004ea5a  test    edi, edi
0x18004ea5c  lea     rbx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18004ea63  mov     r9d, 20007h; samDesired
0x18004ea69  cmovz   rbx, rax
0x18004ea6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ea74  lea     rax, [rsp+850h+hKey]
0x18004ea79  mov     rdx, rbx; lpSubKey
0x18004ea7c  xor     r8d, r8d; ulOptions
0x18004ea7f  mov     [rsp+850h+phkResult], rax; phkResult
0x18004ea84  call    cs:__imp_RegOpenKeyExA
0x18004ea8a  mov     r9d, eax
0x18004ea8d  test    eax, eax
0x18004ea8f  jnz     loc_18004EB24
0x18004ea95  mov     rcx, [rsp+850h+hKey]; hKey
0x18004ea9a  lea     rax, aServerifindexv_0; "ServerIfIndexV6"
0x18004eaa1  mov     r9d, 4; dwType
0x18004eaa7  lea     rdx, aServerifindexv; "ServerIfIndexV4"
0x18004eaae  mov     [rsp+850h+cbData], r9d; cbData
0x18004eab3  test    edi, edi
0x18004eab5  cmovz   rdx, rax; lpValueName
0x18004eab9  lea     rax, [rsp+850h+Data]
0x18004eabe  xor     r8d, r8d; Reserved
0x18004eac1  mov     [rsp+850h+phkResult], rax; lpData
0x18004eac6  call    cs:__imp_RegSetValueExA
0x18004eacc  test    eax, eax
0x18004eace  jnz     short loc_18004EB17
0x18004ead0  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18004ead8  jz      short loc_18004EB17
0x18004eada  mov     r8d, dword ptr [rsp+850h+Data]
0x18004eadf  lea     rdx, aFailedToWriteI; "Failed to write InterfaceIndex into reg"...
0x18004eae6  xor     r9d, r9d
0x18004eae9  mov     word ptr [rsp+850h+var_810], ax
0x18004eaee  lea     rcx, [rsp+850h+var_810]
0x18004eaf3  call    FormatRRASErrorString
0x18004eaf8  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004eaff  lea     r8, [rsp+850h+var_810]
0x18004eb04  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004eb0b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004eb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb17  mov     rcx, [rsp+850h+hKey]; hKey
0x18004eb1c  call    cs:__imp_RegCloseKey
0x18004eb22  jmp     short loc_18004EB68
0x18004eb24  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18004eb2c  jz      short loc_18004EB68
0x18004eb2e  xor     eax, eax
0x18004eb30  lea     rdx, aFailedToOpenTh; "Failed to open the registry key %hs. Er"...
0x18004eb37  mov     r8, rbx
0x18004eb3a  mov     word ptr [rsp+850h+var_810], ax
0x18004eb3f  lea     rcx, [rsp+850h+var_810]
0x18004eb44  call    FormatRRASErrorString
0x18004eb49  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004eb50  lea     r8, [rsp+850h+var_810]
0x18004eb55  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004eb5c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004eb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb68  mov     rcx, [rbp+750h+var_10]
0x18004eb6f  xor     rcx, rsp; StackCookie
0x18004eb72  call    __security_check_cookie
0x18004eb77  lea     r11, [rsp+850h+var_s0]
0x18004eb7f  mov     rbx, [r11+20h]
0x18004eb83  mov     rdi, [r11+28h]
0x18004eb87  mov     rsp, r11
0x18004eb8a  pop     rbp
0x18004eb8b  retn
```
