# NsiGetCompartmentIdForRoutingDomain

- ea: `0x18002dc44`
- end: `0x18002dcf5`
- name: `NsiGetCompartmentIdForRoutingDomain`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ea80`
- `0x1800211f4`

## callees

- `0x18002dc44`

## import_xrefs

- `NSI!NsiGetParameter` at `0x18002dcc7`
- `NSI!NsiGetParameter` at `0x18002dcc7`

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
0x18002dc44  push    rbx
0x18002dc46  sub     rsp, 50h
0x18002dc4a  mov     [rsp+58h+arg_0], 0
0x18002dc52  mov     rbx, rdx
0x18002dc55  test    rcx, rcx
0x18002dc58  jz      loc_18002DCE9
0x18002dc5e  test    rdx, rdx
0x18002dc61  jz      loc_18002DCE9
0x18002dc67  mov     rax, [rcx]
0x18002dc6a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002dc71  jnz     short loc_18002DC7E
0x18002dc73  mov     rax, [rcx+8]
0x18002dc77  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002dc7e  test    rax, rax
0x18002dc81  jz      short loc_18002DCDF
0x18002dc83  mov     [rsp+58h+var_18], 0
0x18002dc8b  lea     rax, [rsp+58h+arg_0]
0x18002dc90  mov     [rsp+58h+var_20], 4
0x18002dc98  mov     r8d, 0Bh
0x18002dc9e  mov     [rsp+58h+var_28], rax
0x18002dca3  mov     r9, rcx
0x18002dca6  mov     dword ptr [rdx], 0
0x18002dcac  lea     rdx, NPI_MS_NDIS_MODULEID
0x18002dcb3  mov     [rsp+58h+var_30], 2
0x18002dcbb  lea     ecx, [r8-0Ah]
0x18002dcbf  mov     [rsp+58h+var_38], 10h
0x18002dcc7  call    cs:__imp_NsiGetParameter
0x18002dcce  nop     dword ptr [rax+rax+00h]
0x18002dcd3  test    eax, eax
0x18002dcd5  jnz     short loc_18002DCEE
0x18002dcd7  mov     ecx, [rsp+58h+arg_0]
0x18002dcdb  mov     [rbx], ecx
0x18002dcdd  jmp     short loc_18002DCEE
0x18002dcdf  mov     dword ptr [rdx], 1
0x18002dce5  xor     eax, eax
0x18002dce7  jmp     short loc_18002DCEE
0x18002dce9  mov     eax, 57h ; 'W'
0x18002dcee  add     rsp, 50h
0x18002dcf2  pop     rbx
0x18002dcf3  retn
```
