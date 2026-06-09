# CNetDiagHelperImpl::GetKeyAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x18000a8f0`
- end: `0x18000aa18`
- name: `?GetKeyAttributes@CNetDiagHelperImpl@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006160`
- `0x180006628`
- `0x18000a8f0`
- `0x18000edb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a9fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a97c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a97c`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetKeyAttributes(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  __int64 v6; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rsi
  struct tagHELPER_ATTRIBUTE *v9; // rax
  struct tagHELPER_ATTRIBUTE *v10; // rdi
  __int64 i; // rsi
  int v13; // [rsp+20h] [rbp-48h] BYREF
  struct tagHELPER_ATTRIBUTE *v14; // [rsp+28h] [rbp-40h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = *((unsigned int *)this + 6);
  v13 = 0;
  v14 = 0;
  if ( (unsigned int)v6 > 0x1C71C71 )
  {
    v7 = -2147024362;
LABEL_13:
    _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
    CoTaskMemFree(0);
    return v7;
  }
  _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
  CoTaskMemFree(0);
  v8 = 144 * v6;
  v9 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v6);
  v14 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_13;
  }
  for ( ; v8; --v8 )
  {
    LOBYTE(v9->pwszName) = 0;
    v9 = (struct tagHELPER_ATTRIBUTE *)((char *)v9 + 1);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
    _attribute_t::Copy(&v10[i], (const struct tagHELPER_ATTRIBUTE *)(144 * i + *((_QWORD *)this + 4)));
  *a2 = v6;
  *a3 = v10;
  v14 = 0;
  _attributes_array_t::FreeElements((_attributes_array_t *)&v13);
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x18000a8f0  push    rbx
0x18000a8f2  push    rbp
0x18000a8f3  push    rsi
0x18000a8f4  push    rdi
0x18000a8f5  push    r14
0x18000a8f7  push    r15
0x18000a8f9  sub     rsp, 38h
0x18000a8fd  mov     r14, r8
0x18000a900  mov     r15, rdx
0x18000a903  mov     rbx, rcx
0x18000a906  test    rdx, rdx
0x18000a909  jnz     short loc_18000A910
0x18000a90b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a910  test    r14, r14
0x18000a913  jnz     short loc_18000A91A
0x18000a915  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a91a  cmp     dword ptr [rbx+10h], 1
0x18000a91e  jz      short loc_18000A925
0x18000a920  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a925  test    r15, r15
0x18000a928  jz      loc_18000AA04
0x18000a92e  test    r14, r14
0x18000a931  jz      loc_18000AA04
0x18000a937  mov     ebp, [rbx+18h]
0x18000a93a  xor     edi, edi
0x18000a93c  mov     [rsp+68h+var_48], 0
0x18000a944  mov     [rsp+68h+var_40], rdi
0x18000a949  cmp     ebp, 1C71C71h
0x18000a94f  jbe     short loc_18000A958
0x18000a951  mov     ebx, 80070216h
0x18000a956  jmp     short loc_18000A994
0x18000a958  lea     rcx, [rsp+68h+var_48]; this
0x18000a95d  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000a962  xor     ecx, ecx; pv
0x18000a964  call    cs:__imp_CoTaskMemFree
0x18000a96a  lea     rsi, ds:0[rbp*8]
0x18000a972  add     rsi, rbp
0x18000a975  shl     rsi, 4
0x18000a979  mov     rcx, rsi; cb
0x18000a97c  call    cs:__imp_CoTaskMemAlloc
0x18000a982  mov     [rsp+68h+var_40], rax
0x18000a987  mov     rdi, rax
0x18000a98a  test    rax, rax
0x18000a98d  jnz     short loc_18000A9A9
0x18000a98f  mov     ebx, 8007000Eh
0x18000a994  lea     rcx, [rsp+68h+var_48]; this
0x18000a999  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000a99e  mov     rcx, rdi; pv
0x18000a9a1  call    cs:__imp_CoTaskMemFree
0x18000a9a7  jmp     short loc_18000AA09
0x18000a9a9  test    rsi, rsi
0x18000a9ac  jz      short loc_18000A9BA
0x18000a9ae  mov     byte ptr [rax], 0
0x18000a9b1  inc     rax
0x18000a9b4  sub     rsi, 1
0x18000a9b8  jnz     short loc_18000A9AE
0x18000a9ba  xor     esi, esi
0x18000a9bc  cmp     [rbx+18h], esi
0x18000a9bf  jbe     short loc_18000A9DF
0x18000a9c1  mov     rdx, [rbx+20h]
0x18000a9c5  lea     rcx, [rsi+rsi*8]
0x18000a9c9  shl     rcx, 4
0x18000a9cd  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x18000a9d0  add     rcx, rdi; this
0x18000a9d3  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000a9d8  inc     esi
0x18000a9da  cmp     esi, [rbx+18h]
0x18000a9dd  jb      short loc_18000A9C1
0x18000a9df  mov     [r15], ebp
0x18000a9e2  lea     rcx, [rsp+68h+var_48]; this
0x18000a9e7  mov     [r14], rdi
0x18000a9ea  mov     [rsp+68h+var_40], 0
0x18000a9f3  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000a9f8  xor     ecx, ecx; pv
0x18000a9fa  call    cs:__imp_CoTaskMemFree
0x18000aa00  xor     ebx, ebx
0x18000aa02  jmp     short loc_18000AA09
0x18000aa04  mov     ebx, 80070057h
0x18000aa09  mov     eax, ebx
0x18000aa0b  add     rsp, 38h
0x18000aa0f  pop     r15
0x18000aa11  pop     r14
0x18000aa13  pop     rdi
0x18000aa14  pop     rsi
0x18000aa15  pop     rbp
0x18000aa16  pop     rbx
0x18000aa17  retn
```
