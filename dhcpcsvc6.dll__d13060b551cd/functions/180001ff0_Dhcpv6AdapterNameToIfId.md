# Dhcpv6AdapterNameToIfId

- ea: `0x180001ff0`
- end: `0x18000205f`
- name: `Dhcpv6AdapterNameToIfId`
- size: `111`
- prototype: `NTSTATUS __fastcall(const WCHAR *, NET_LUID *)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x1800016f0`
- `0x180003240`
- `0x180004870`
- `0x180004ad0`
- `0x180004e10`
- `0x180005040`
- `0x180005270`
- `0x180005640`
- `0x180005b30`
- `0x180005ec0`
- `0x1800062f0`
- `0x180006820`
- `0x180006cb0`

## callees

- `0x180001ff0`
- `0x180002070`
- `0x180008220`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002008`
- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002008`

## pseudocode

```c
NTSTATUS __fastcall Dhcpv6AdapterNameToIfId(const WCHAR *a1, NET_LUID *a2)
{
  NTSTATUS result; // eax
  int v4; // edi

  if ( !a1 )
  {
    v4 = 87;
LABEL_8:
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_DS(1025, 11, (unsigned int)WPP_49ae112189e6338ccd255122bd844a6f_Traceguids, v4, (__int64)a1);
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
0x180001ff0  mov     [rsp+arg_0], rbx
0x180001ff5  push    rdi
0x180001ff6  sub     rsp, 30h
0x180001ffa  mov     rbx, rcx
0x180001ffd  test    rcx, rcx
0x180002000  jz      short loc_180002026
0x180002002  cmp     word ptr [rcx], 7Bh ; '{'
0x180002006  jz      short loc_18000201F
0x180002008  call    cs:__imp_ConvertInterfaceNameToLuidW
0x18000200e  mov     edi, eax
0x180002010  test    eax, eax
0x180002012  jnz     short loc_18000202B
0x180002014  mov     rbx, [rsp+38h+arg_0]
0x180002019  add     rsp, 30h
0x18000201d  pop     rdi
0x18000201e  retn
0x18000201f  call    ConvertIfGuidToInterfaceLuidW
0x180002024  jmp     short loc_18000200E
0x180002026  mov     edi, 57h ; 'W'
0x18000202b  test    byte ptr cs:xmmword_18000F160, 2
0x180002032  jz      short loc_180002052
0x180002034  mov     edx, 0Bh
0x180002039  mov     [rsp+38h+var_18], rbx
0x18000203e  mov     ecx, 401h
0x180002043  lea     r8, WPP_49ae112189e6338ccd255122bd844a6f_Traceguids
0x18000204a  mov     r9d, edi
0x18000204d  call    WPP_SF_DS
0x180002052  mov     rbx, [rsp+38h+arg_0]
0x180002057  mov     eax, edi
0x180002059  add     rsp, 30h
0x18000205d  pop     rdi
0x18000205e  retn
```
