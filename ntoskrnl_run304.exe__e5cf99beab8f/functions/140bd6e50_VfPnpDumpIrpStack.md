# VfPnpDumpIrpStack

- ea: `0x140bd6e50`
- end: `0x140bd7029`
- name: `VfPnpDumpIrpStack`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14020fe90`
- `0x140529430`
- `0x140bd6e50`

## string_xrefs

- `0x140bd6f55`: `(BusQueryCompatibleIDs)`
- `0x140bd6f22`: `, InPath=TRUE)`
- `0x140bd6f1b`: `, InPath=FALSE)`

## pseudocode

```c
ULONG __fastcall VfPnpDumpIrpStack(__int64 a1)
{
  __int64 v2; // rax
  const char *v3; // rbx
  ULONG result; // eax
  const char *v5; // rdx
  const char *v6; // rcx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  const char *v10; // rcx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  DbgPrintEx(0x5Du, 0, "IRP_MJ_PNP.");
  v2 = *(unsigned __int8 *)(a1 + 1);
  v3 = "(Bogus)";
  if ( (unsigned __int8)v2 > 0x18u )
  {
    v6 = "IRP_MN_BOGUS";
    if ( (_BYTE)v2 != 0xFF )
      v6 = "(Bogus)";
    result = VfUtilDbgPrint(v6);
  }
  else
  {
    result = VfUtilDbgPrint(PnPIrpNames[v2]);
  }
  if ( *(_BYTE *)(a1 + 1) != 7 )
  {
    switch ( *(_BYTE *)(a1 + 1) )
    {
      case 0xC:
        v14 = *(_DWORD *)(a1 + 8);
        if ( v14 )
        {
          if ( v14 == 1 )
            v3 = "(DeviceTextLocationInformation)";
        }
        else
        {
          v3 = "(DeviceTextDescription)";
        }
        break;
      case 0xF:
      case 0x10:
        return DbgPrintEx(
                 0x5Du,
                 0,
                 "(WhichSpace=%x, Buffer=%p, Offset=%x, Length=%x)",
                 *(_DWORD *)(a1 + 8),
                 *(const void **)(a1 + 16),
                 *(_DWORD *)(a1 + 24),
                 *(_DWORD *)(a1 + 32));
      case 0x12:
        v5 = "(False)";
        v10 = "(True)";
LABEL_23:
        if ( !*(_BYTE *)(a1 + 8) )
          v10 = v5;
        return VfUtilDbgPrint(v10, v5);
      case 0x13:
        v11 = *(_DWORD *)(a1 + 8);
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 == 1 )
                v3 = "(BusQueryInstanceID)";
            }
            else
            {
              v3 = "(BusQueryCompatibleIDs)";
            }
          }
          else
          {
            v3 = "(BusQueryHardwareIDs)";
          }
        }
        else
        {
          v3 = "(BusQueryDeviceID)";
        }
        break;
      case 0x16:
        v7 = *(_DWORD *)(a1 + 16);
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( !v8 )
          {
            VfUtilDbgPrint("(DeviceUsageTypePaging");
            goto LABEL_22;
          }
          v9 = v8 - 1;
          if ( !v9 )
          {
            VfUtilDbgPrint("(DeviceUsageTypeHibernation");
            goto LABEL_22;
          }
          if ( v9 == 1 )
          {
            VfUtilDbgPrint("(DeviceUsageTypeDumpFile");
LABEL_22:
            v5 = ", InPath=FALSE)";
            v10 = ", InPath=TRUE)";
            goto LABEL_23;
          }
        }
        else
        {
          v3 = "(DeviceUsageTypeUndefined";
        }
        VfUtilDbgPrint(v3);
        goto LABEL_22;
      default:
        return result;
    }
    return VfUtilDbgPrint(v3, v5);
  }
  v15 = *(_DWORD *)(a1 + 8);
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( !v16 )
      return VfUtilDbgPrint("(EjectionRelations)", v5);
    v17 = v16 - 1;
    if ( !v17 )
      return VfUtilDbgPrint("(PowerRelations)", v5);
    v18 = v17 - 1;
    if ( !v18 )
      return VfUtilDbgPrint("(RemovalRelations)", v5);
    if ( v18 == 1 )
      return VfUtilDbgPrint("(TargetDeviceRelation)", v5);
    return VfUtilDbgPrint(v3, v5);
  }
  v10 = "(BusRelations)";
  return VfUtilDbgPrint(v10, v5);
}

```

## disassembly

```asm
0x140bd6e50  mov     [rsp+arg_0], rbx
0x140bd6e55  push    rdi
0x140bd6e56  sub     rsp, 40h
0x140bd6e5a  xor     edx, edx; Level
0x140bd6e5c  lea     r8, aIrpMjPnp_0; "IRP_MJ_PNP."
0x140bd6e63  mov     rdi, rcx
0x140bd6e66  lea     ecx, [rdx+5Dh]; ComponentId
0x140bd6e69  call    DbgPrintEx
0x140bd6e6e  movzx   eax, byte ptr [rdi+1]
0x140bd6e72  lea     rbx, aBogus; "(Bogus)"
0x140bd6e79  cmp     al, 18h
0x140bd6e7b  ja      short loc_140BD6E8A
0x140bd6e7d  lea     rcx, PnPIrpNames
0x140bd6e84  mov     rcx, [rcx+rax*8]
0x140bd6e88  jmp     short loc_140BD6E97
0x140bd6e8a  cmp     al, 0FFh
0x140bd6e8c  lea     rcx, aIrpMnBogus; "IRP_MN_BOGUS"
0x140bd6e93  cmovnz  rcx, rbx
0x140bd6e97  call    VfUtilDbgPrint
0x140bd6e9c  movzx   ecx, byte ptr [rdi+1]
0x140bd6ea0  sub     ecx, 7
0x140bd6ea3  jz      loc_140BD6FD2
0x140bd6ea9  sub     ecx, 5
0x140bd6eac  jz      loc_140BD6FB4
0x140bd6eb2  sub     ecx, 3
0x140bd6eb5  jz      loc_140BD6F86
0x140bd6ebb  sub     ecx, 1
0x140bd6ebe  jz      loc_140BD6F86
0x140bd6ec4  sub     ecx, 2
0x140bd6ec7  jz      loc_140BD6F76
0x140bd6ecd  sub     ecx, 1
0x140bd6ed0  jz      short loc_140BD6F36
0x140bd6ed2  cmp     ecx, 3
0x140bd6ed5  jnz     loc_140BD701D
0x140bd6edb  mov     ecx, [rdi+10h]
0x140bd6ede  test    ecx, ecx
0x140bd6ee0  jz      short loc_140BD6F0C
0x140bd6ee2  sub     ecx, 1
0x140bd6ee5  jz      short loc_140BD6F03
0x140bd6ee7  sub     ecx, 1
0x140bd6eea  jz      short loc_140BD6EFA
0x140bd6eec  cmp     ecx, 1
0x140bd6eef  jnz     short loc_140BD6F13
0x140bd6ef1  lea     rbx, aDeviceusagetyp_0; "(DeviceUsageTypeDumpFile"
0x140bd6ef8  jmp     short loc_140BD6F13
0x140bd6efa  lea     rbx, aDeviceusagetyp_2; "(DeviceUsageTypeHibernation"
0x140bd6f01  jmp     short loc_140BD6F13
0x140bd6f03  lea     rbx, aDeviceusagetyp_1; "(DeviceUsageTypePaging"
0x140bd6f0a  jmp     short loc_140BD6F13
0x140bd6f0c  lea     rbx, aDeviceusagetyp; "(DeviceUsageTypeUndefined"
0x140bd6f13  mov     rcx, rbx
0x140bd6f16  call    VfUtilDbgPrint
0x140bd6f1b  lea     rdx, aInpathFalse; ", InPath=FALSE)"
0x140bd6f22  lea     rcx, aInpathTrue; ", InPath=TRUE)"
0x140bd6f29  cmp     byte ptr [rdi+8], 0
0x140bd6f2d  cmovz   rcx, rdx
0x140bd6f31  jmp     loc_140BD7018
0x140bd6f36  mov     ecx, [rdi+8]
0x140bd6f39  test    ecx, ecx
0x140bd6f3b  jz      short loc_140BD6F67
0x140bd6f3d  sub     ecx, 1
0x140bd6f40  jz      short loc_140BD6F5E
0x140bd6f42  sub     ecx, 1
0x140bd6f45  jz      short loc_140BD6F55
0x140bd6f47  cmp     ecx, 1
0x140bd6f4a  jnz     short loc_140BD6F6E
0x140bd6f4c  lea     rbx, aBusqueryinstan; "(BusQueryInstanceID)"
0x140bd6f53  jmp     short loc_140BD6F6E
0x140bd6f55  lea     rbx, aBusquerycompat; "(BusQueryCompatibleIDs)"
0x140bd6f5c  jmp     short loc_140BD6F6E
0x140bd6f5e  lea     rbx, aBusqueryhardwa; "(BusQueryHardwareIDs)"
0x140bd6f65  jmp     short loc_140BD6F6E
0x140bd6f67  lea     rbx, aBusquerydevice; "(BusQueryDeviceID)"
0x140bd6f6e  mov     rcx, rbx
0x140bd6f71  jmp     loc_140BD7018
0x140bd6f76  lea     rdx, aFalse; "(False)"
0x140bd6f7d  lea     rcx, aTrue_0; "(True)"
0x140bd6f84  jmp     short loc_140BD6F29
0x140bd6f86  mov     eax, [rdi+20h]
0x140bd6f89  lea     r8, aWhichspaceXBuf; "(WhichSpace=%x, Buffer=%p, Offset=%x, L"...
0x140bd6f90  mov     r9d, [rdi+8]
0x140bd6f94  xor     edx, edx; Level
0x140bd6f96  mov     [rsp+48h+var_18], eax
0x140bd6f9a  mov     eax, [rdi+18h]
0x140bd6f9d  mov     [rsp+48h+var_20], eax
0x140bd6fa1  mov     rax, [rdi+10h]
0x140bd6fa5  lea     ecx, [rdx+5Dh]; ComponentId
0x140bd6fa8  mov     [rsp+48h+var_28], rax
0x140bd6fad  call    DbgPrintEx
0x140bd6fb2  jmp     short loc_140BD701D
0x140bd6fb4  mov     ecx, [rdi+8]
0x140bd6fb7  test    ecx, ecx
0x140bd6fb9  jz      short loc_140BD6FC9
0x140bd6fbb  cmp     ecx, 1
0x140bd6fbe  jnz     short loc_140BD6F6E
0x140bd6fc0  lea     rbx, aDevicetextloca; "(DeviceTextLocationInformation)"
0x140bd6fc7  jmp     short loc_140BD6F6E
0x140bd6fc9  lea     rbx, aDevicetextdesc; "(DeviceTextDescription)"
0x140bd6fd0  jmp     short loc_140BD6F6E
0x140bd6fd2  mov     ecx, [rdi+8]
0x140bd6fd5  test    ecx, ecx
0x140bd6fd7  jz      short loc_140BD7011
0x140bd6fd9  sub     ecx, 1
0x140bd6fdc  jz      short loc_140BD7008
0x140bd6fde  sub     ecx, 1
0x140bd6fe1  jz      short loc_140BD6FFF
0x140bd6fe3  sub     ecx, 1
0x140bd6fe6  jz      short loc_140BD6FF6
0x140bd6fe8  cmp     ecx, 1
0x140bd6feb  jnz     short loc_140BD6F6E
0x140bd6fed  lea     rcx, aTargetdevicere; "(TargetDeviceRelation)"
0x140bd6ff4  jmp     short loc_140BD7018
0x140bd6ff6  lea     rcx, aRemovalrelatio; "(RemovalRelations)"
0x140bd6ffd  jmp     short loc_140BD7018
0x140bd6fff  lea     rcx, aPowerrelations_0; "(PowerRelations)"
0x140bd7006  jmp     short loc_140BD7018
0x140bd7008  lea     rcx, aEjectionrelati; "(EjectionRelations)"
0x140bd700f  jmp     short loc_140BD7018
0x140bd7011  lea     rcx, aBusrelations_0; "(BusRelations)"
0x140bd7018  call    VfUtilDbgPrint
0x140bd701d  mov     rbx, [rsp+48h+arg_0]
0x140bd7022  add     rsp, 40h
0x140bd7026  pop     rdi
0x140bd7027  retn
```
