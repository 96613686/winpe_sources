# PrintAsnObjectIdentifier

- ea: `0x180001d10`
- end: `0x180001dcb`
- name: `PrintAsnObjectIdentifier`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001dd4`

## callees

- `0x180001d10`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180001d64`
- `iisutil!PuDbgPrint` at `0x180001daf`
- `iisutil!PuDbgPrint` at `0x180001d64`
- `iisutil!PuDbgPrint` at `0x180001daf`

## string_xrefs

- `0x180001d46`: `servercommon\inetsrv\iis\iisrearc\core\snmp\dll\mib.cxx`
- `0x180001d8a`: `servercommon\inetsrv\iis\iisrearc\core\snmp\dll\mib.cxx`

## pseudocode

```c
_UNKNOWN **__fastcall PrintAsnObjectIdentifier(const char *a1, _DWORD *a2)
{
  _UNKNOWN **result; // rax
  unsigned int v4; // esi
  __int64 i; // rbx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF

  result = &retaddr;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v4 = *a2;
    result = (_UNKNOWN **)PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\snmp\\dll\\mib.cxx",
                            74,
                            "PrintAsnObjectIdentifier",
                            "Printing Oid %s = %08x. Length = %u.\n",
                            a1,
                            (_DWORD)a2,
                            *a2);
    for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        result = (_UNKNOWN **)PuDbgPrint(
                                g_pDebug,
                                "servercommon\\inetsrv\\iis\\iisrearc\\core\\snmp\\dll\\mib.cxx",
                                80,
                                "PrintAsnObjectIdentifier",
                                "AsnOid[ %u] = %u\n",
                                i,
                                *(_DWORD *)(*(_QWORD *)(a2 + 1) + 4 * i));
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001d10  mov     rax, rsp
0x180001d13  mov     [rax+8], rbx
0x180001d17  mov     [rax+10h], rsi
0x180001d1b  push    rdi
0x180001d1c  sub     rsp, 40h
0x180001d20  test    byte ptr cs:g_dwDebugFlags, 3
0x180001d27  mov     rdi, rdx
0x180001d2a  jz      loc_180001DBB
0x180001d30  mov     esi, [rdx]
0x180001d32  lea     r9, aPrintasnobject; "PrintAsnObjectIdentifier"
0x180001d39  mov     [rax-10h], esi
0x180001d3c  mov     r8d, 4Ah ; 'J'
0x180001d42  mov     [rax-18h], rdx
0x180001d46  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001d4d  mov     [rax-20h], rcx
0x180001d51  lea     rax, aPrintingOidS08; "Printing Oid %s = %08x. Length = %u.\n"
0x180001d58  mov     rcx, cs:g_pDebug
0x180001d5f  mov     [rsp+48h+var_28], rax
0x180001d64  call    cs:__imp_PuDbgPrint
0x180001d6a  xor     ebx, ebx
0x180001d6c  test    esi, esi
0x180001d6e  jz      short loc_180001DBB
0x180001d70  test    byte ptr cs:g_dwDebugFlags, 3
0x180001d77  jz      short loc_180001DB5
0x180001d79  mov     rax, [rdi+4]
0x180001d7d  lea     r9, aPrintasnobject; "PrintAsnObjectIdentifier"
0x180001d84  mov     r8d, 50h ; 'P'
0x180001d8a  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001d91  mov     ecx, [rax+rbx*4]
0x180001d94  lea     rax, aAsnoidUU; "AsnOid[ %u] = %u\n"
0x180001d9b  mov     [rsp+48h+var_18], ecx
0x180001d9f  mov     rcx, cs:g_pDebug
0x180001da6  mov     [rsp+48h+var_20], ebx
0x180001daa  mov     [rsp+48h+var_28], rax
0x180001daf  call    cs:__imp_PuDbgPrint
0x180001db5  inc     ebx
0x180001db7  cmp     ebx, esi
0x180001db9  jb      short loc_180001D70
0x180001dbb  mov     rbx, [rsp+48h+arg_0]
0x180001dc0  mov     rsi, [rsp+48h+arg_8]
0x180001dc5  add     rsp, 40h
0x180001dc9  pop     rdi
0x180001dca  retn
```
