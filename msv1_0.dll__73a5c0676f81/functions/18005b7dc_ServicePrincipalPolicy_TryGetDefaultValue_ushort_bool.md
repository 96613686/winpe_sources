# ServicePrincipalPolicy::TryGetDefaultValue(ushort *,bool &)

- ea: `0x18005b7dc`
- end: `0x18005b868`
- name: `?TryGetDefaultValue@ServicePrincipalPolicy@@QEAA_NPEAGAEA_N@Z`
- size: `140`
- prototype: `bool(ServicePrincipalPolicy *__hidden this, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b870`

## callees

- `0x18005b7dc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005b841`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005b841`

## pseudocode

```c
bool __fastcall ServicePrincipalPolicy::TryGetDefaultValue(
        ServicePrincipalPolicy *this,
        unsigned __int16 *a2,
        bool *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  bool result; // al

  v3 = *((_QWORD *)this + 2);
  v5 = *((_QWORD *)this + 3);
  while ( v3 != v5 )
  {
    if ( a2
      && CompareStringEx(&Src, 1u, a2, -1, *(LPCWCH *)v3, (__int64)(*(_QWORD *)(v3 + 8) - *(_QWORD *)v3) >> 1, 0, 0, 0) == 2 )
    {
      result = 1;
      *a3 = *(_BYTE *)(v3 + 32);
      return result;
    }
    v3 += 40;
  }
  return 0;
}

```

## disassembly

```asm
0x18005b7dc  push    rbx
0x18005b7de  push    rsi
0x18005b7df  push    rdi
0x18005b7e0  push    r14
0x18005b7e2  sub     rsp, 58h
0x18005b7e6  mov     rbx, [rcx+10h]
0x18005b7ea  mov     r14, r8
0x18005b7ed  mov     rdi, [rcx+18h]
0x18005b7f1  mov     rsi, rdx
0x18005b7f4  cmp     rbx, rdi
0x18005b7f7  jz      short loc_18005B85C
0x18005b7f9  test    rsi, rsi
0x18005b7fc  jz      short loc_18005B84C
0x18005b7fe  mov     rcx, [rbx]
0x18005b801  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b805  mov     rax, [rbx+8]
0x18005b809  mov     r8, rsi; lpString1
0x18005b80c  mov     [rsp+78h+lParam], 0; lParam
0x18005b815  sub     rax, rcx
0x18005b818  mov     [rsp+78h+lpReserved], 0; lpReserved
0x18005b821  sar     rax, 1
0x18005b824  lea     edx, [r9+2]; dwCmpFlags
0x18005b828  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x18005b831  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18005b835  mov     [rsp+78h+lpString2], rcx; lpString2
0x18005b83a  lea     rcx, Src; lpLocaleName
0x18005b841  call    cs:__imp_CompareStringEx
0x18005b847  cmp     eax, 2
0x18005b84a  jz      short loc_18005B852
0x18005b84c  add     rbx, 28h ; '('
0x18005b850  jmp     short loc_18005B7F4
0x18005b852  mov     cl, [rbx+20h]
0x18005b855  mov     al, 1
0x18005b857  mov     [r14], cl
0x18005b85a  jmp     short loc_18005B85E
0x18005b85c  xor     al, al
0x18005b85e  add     rsp, 58h
0x18005b862  pop     r14
0x18005b864  pop     rdi
0x18005b865  pop     rsi
0x18005b866  pop     rbx
0x18005b867  retn
```
