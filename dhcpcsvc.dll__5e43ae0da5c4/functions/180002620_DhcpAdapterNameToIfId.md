# DhcpAdapterNameToIfId

- ea: `0x180002620`
- end: `0x18000268f`
- name: `DhcpAdapterNameToIfId`
- size: `111`
- prototype: ``
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180001240`
- `0x180001490`
- `0x180001bd0`
- `0x180005be0`
- `0x180005d30`
- `0x180006790`
- `0x1800068b0`
- `0x180006c90`
- `0x180006e10`
- `0x180007010`
- `0x180007480`
- `0x180007950`
- `0x180007c00`
- `0x180008210`
- `0x18000847c`
- `0x180008dd4`
- `0x18000a180`
- `0x18000a950`
- `0x18000ac50`
- `0x18000b180`
- `0x18000b360`
- `0x18000b590`
- `0x18000b7c0`
- `0x18000b9d0`
- `0x18000bd64`
- `0x18000bf80`
- `0x18000c110`
- `0x18000d660`
- `0x18000dbe0`

## callees

- `0x180002620`
- `0x1800026a0`
- `0x180012a40`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002638`
- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002638`

## pseudocode

```c
NTSTATUS __fastcall DhcpAdapterNameToIfId(const WCHAR *a1, NET_LUID *a2)
{
  NTSTATUS result; // eax
  int v4; // edi

  if ( !a1 )
  {
    v4 = 87;
LABEL_8:
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_DS(1025, 13, (unsigned int)WPP_1c950673330936d81a3de42a8ac0149e_Traceguids, v4, (__int64)a1);
    return v4;
  }
  if ( *a1 == 123 )
    result = ConvertIfGuidToInterfaceLuidW(a1, a2);
  else
    result = ConvertInterfaceNameToLuidW(a1, a2);
  v4 = result;
  if ( result )
    goto LABEL_8;
  return result;
}

```

## disassembly

```asm
0x180002620  mov     [rsp+arg_0], rbx
0x180002625  push    rdi
0x180002626  sub     rsp, 30h
0x18000262a  mov     rbx, rcx
0x18000262d  test    rcx, rcx
0x180002630  jz      short loc_180002656
0x180002632  cmp     word ptr [rcx], 7Bh ; '{'
0x180002636  jz      short loc_18000264F
0x180002638  call    cs:__imp_ConvertInterfaceNameToLuidW
0x18000263e  mov     edi, eax
0x180002640  test    eax, eax
0x180002642  jnz     short loc_18000265B
0x180002644  mov     rbx, [rsp+38h+arg_0]
0x180002649  add     rsp, 30h
0x18000264d  pop     rdi
0x18000264e  retn
0x18000264f  call    ConvertIfGuidToInterfaceLuidW
0x180002654  jmp     short loc_18000263E
0x180002656  mov     edi, 57h ; 'W'
0x18000265b  test    byte ptr cs:xmmword_18001E1E0, 2
0x180002662  jz      short loc_180002682
0x180002664  mov     edx, 0Dh
0x180002669  mov     [rsp+38h+var_18], rbx
0x18000266e  mov     ecx, 401h
0x180002673  lea     r8, WPP_1c950673330936d81a3de42a8ac0149e_Traceguids
0x18000267a  mov     r9d, edi
0x18000267d  call    WPP_SF_DS
0x180002682  mov     rbx, [rsp+38h+arg_0]
0x180002687  mov     eax, edi
0x180002689  add     rsp, 30h
0x18000268d  pop     rdi
0x18000268e  retn
```
