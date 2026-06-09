# NsiGetCompartmentIdForRoutingDomain

- ea: `0x18002cb08`
- end: `0x18002cbae`
- name: `NsiGetCompartmentIdForRoutingDomain`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001df60`
- `0x1800205d4`

## callees

- `0x18002cb08`

## import_xrefs

- `NSI!NsiGetParameter` at `0x18002cb87`
- `NSI!NsiGetParameter` at `0x18002cb87`

## pseudocode

```c
__int64 __fastcall NsiGetCompartmentIdForRoutingDomain(_QWORD *a1, _DWORD *a2)
{
  __int64 v3; // rax
  __int64 result; // rax
  int v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = 0;
  if ( !a1 || !a2 )
    return 87;
  v3 = *a1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *a1 == *(_QWORD *)&GUID_NULL.Data1 )
    v3 = a1[1] - *(_QWORD *)GUID_NULL.Data4;
  if ( v3 )
  {
    *a2 = 0;
    result = NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 11, a1, 16, 2, &v5, 4, 0);
    if ( !(_DWORD)result )
      *a2 = v5;
  }
  else
  {
    *a2 = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002cb08  push    rbx
0x18002cb0a  sub     rsp, 50h
0x18002cb0e  mov     [rsp+58h+arg_0], 0
0x18002cb16  mov     rbx, rdx
0x18002cb19  test    rcx, rcx
0x18002cb1c  jz      loc_18002CBA3
0x18002cb22  test    rdx, rdx
0x18002cb25  jz      short loc_18002CBA3
0x18002cb27  mov     rax, [rcx]
0x18002cb2a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002cb31  jnz     short loc_18002CB3E
0x18002cb33  mov     rax, [rcx+8]
0x18002cb37  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002cb3e  test    rax, rax
0x18002cb41  jz      short loc_18002CB99
0x18002cb43  mov     [rsp+58h+var_18], 0
0x18002cb4b  lea     rax, [rsp+58h+arg_0]
0x18002cb50  mov     [rsp+58h+var_20], 4
0x18002cb58  mov     r8d, 0Bh
0x18002cb5e  mov     [rsp+58h+var_28], rax
0x18002cb63  mov     r9, rcx
0x18002cb66  mov     dword ptr [rdx], 0
0x18002cb6c  lea     rdx, NPI_MS_NDIS_MODULEID
0x18002cb73  mov     [rsp+58h+var_30], 2
0x18002cb7b  lea     ecx, [r8-0Ah]
0x18002cb7f  mov     [rsp+58h+var_38], 10h
0x18002cb87  call    cs:__imp_NsiGetParameter
0x18002cb8d  test    eax, eax
0x18002cb8f  jnz     short loc_18002CBA8
0x18002cb91  mov     ecx, [rsp+58h+arg_0]
0x18002cb95  mov     [rbx], ecx
0x18002cb97  jmp     short loc_18002CBA8
0x18002cb99  mov     dword ptr [rdx], 1
0x18002cb9f  xor     eax, eax
0x18002cba1  jmp     short loc_18002CBA8
0x18002cba3  mov     eax, 57h ; 'W'
0x18002cba8  add     rsp, 50h
0x18002cbac  pop     rbx
0x18002cbad  retn
```
