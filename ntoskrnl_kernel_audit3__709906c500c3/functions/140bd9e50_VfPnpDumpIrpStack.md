# VfPnpDumpIrpStack

- ea: `0x140bd9e50`
- end: `0x140bda029`
- name: `VfPnpDumpIrpStack`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1402a2f90`
- `0x140530500`
- `0x140bd9e50`

## string_xrefs

- `0x140bd9f22`: `, InPath=TRUE)`
- `0x140bd9f1b`: `, InPath=FALSE)`
- `0x140bd9f55`: `(BusQueryCompatibleIDs)`

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
0x140bd9e50  mov     [rsp+arg_0], rbx
0x140bd9e55  push    rdi
0x140bd9e56  sub     rsp, 40h
0x140bd9e5a  xor     edx, edx; Level
0x140bd9e5c  lea     r8, aIrpMjPnp_0; "IRP_MJ_PNP."
0x140bd9e63  mov     rdi, rcx
0x140bd9e66  lea     ecx, [rdx+5Dh]; ComponentId
0x140bd9e69  call    DbgPrintEx
0x140bd9e6e  movzx   eax, byte ptr [rdi+1]
0x140bd9e72  lea     rbx, aBogus; "(Bogus)"
0x140bd9e79  cmp     al, 18h
0x140bd9e7b  ja      short loc_140BD9E8A
0x140bd9e7d  lea     rcx, PnPIrpNames
0x140bd9e84  mov     rcx, [rcx+rax*8]
0x140bd9e88  jmp     short loc_140BD9E97
0x140bd9e8a  cmp     al, 0FFh
0x140bd9e8c  lea     rcx, aIrpMnBogus; "IRP_MN_BOGUS"
0x140bd9e93  cmovnz  rcx, rbx
0x140bd9e97  call    VfUtilDbgPrint
0x140bd9e9c  movzx   ecx, byte ptr [rdi+1]
0x140bd9ea0  sub     ecx, 7
0x140bd9ea3  jz      loc_140BD9FD2
0x140bd9ea9  sub     ecx, 5
0x140bd9eac  jz      loc_140BD9FB4
0x140bd9eb2  sub     ecx, 3
0x140bd9eb5  jz      loc_140BD9F86
0x140bd9ebb  sub     ecx, 1
0x140bd9ebe  jz      loc_140BD9F86
0x140bd9ec4  sub     ecx, 2
0x140bd9ec7  jz      loc_140BD9F76
0x140bd9ecd  sub     ecx, 1
0x140bd9ed0  jz      short loc_140BD9F36
0x140bd9ed2  cmp     ecx, 3
0x140bd9ed5  jnz     loc_140BDA01D
0x140bd9edb  mov     ecx, [rdi+10h]
0x140bd9ede  test    ecx, ecx
0x140bd9ee0  jz      short loc_140BD9F0C
0x140bd9ee2  sub     ecx, 1
0x140bd9ee5  jz      short loc_140BD9F03
0x140bd9ee7  sub     ecx, 1
0x140bd9eea  jz      short loc_140BD9EFA
0x140bd9eec  cmp     ecx, 1
0x140bd9eef  jnz     short loc_140BD9F13
0x140bd9ef1  lea     rbx, aDeviceusagetyp_0; "(DeviceUsageTypeDumpFile"
0x140bd9ef8  jmp     short loc_140BD9F13
0x140bd9efa  lea     rbx, aDeviceusagetyp_2; "(DeviceUsageTypeHibernation"
0x140bd9f01  jmp     short loc_140BD9F13
0x140bd9f03  lea     rbx, aDeviceusagetyp_1; "(DeviceUsageTypePaging"
0x140bd9f0a  jmp     short loc_140BD9F13
0x140bd9f0c  lea     rbx, aDeviceusagetyp; "(DeviceUsageTypeUndefined"
0x140bd9f13  mov     rcx, rbx
0x140bd9f16  call    VfUtilDbgPrint
0x140bd9f1b  lea     rdx, aInpathFalse; ", InPath=FALSE)"
0x140bd9f22  lea     rcx, aInpathTrue; ", InPath=TRUE)"
0x140bd9f29  cmp     byte ptr [rdi+8], 0
0x140bd9f2d  cmovz   rcx, rdx
0x140bd9f31  jmp     loc_140BDA018
0x140bd9f36  mov     ecx, [rdi+8]
0x140bd9f39  test    ecx, ecx
0x140bd9f3b  jz      short loc_140BD9F67
0x140bd9f3d  sub     ecx, 1
0x140bd9f40  jz      short loc_140BD9F5E
0x140bd9f42  sub     ecx, 1
0x140bd9f45  jz      short loc_140BD9F55
0x140bd9f47  cmp     ecx, 1
0x140bd9f4a  jnz     short loc_140BD9F6E
0x140bd9f4c  lea     rbx, aBusqueryinstan; "(BusQueryInstanceID)"
0x140bd9f53  jmp     short loc_140BD9F6E
0x140bd9f55  lea     rbx, aBusquerycompat; "(BusQueryCompatibleIDs)"
0x140bd9f5c  jmp     short loc_140BD9F6E
0x140bd9f5e  lea     rbx, aBusqueryhardwa; "(BusQueryHardwareIDs)"
0x140bd9f65  jmp     short loc_140BD9F6E
0x140bd9f67  lea     rbx, aBusquerydevice; "(BusQueryDeviceID)"
0x140bd9f6e  mov     rcx, rbx
0x140bd9f71  jmp     loc_140BDA018
0x140bd9f76  lea     rdx, aFalse; "(False)"
0x140bd9f7d  lea     rcx, aTrue_0; "(True)"
0x140bd9f84  jmp     short loc_140BD9F29
0x140bd9f86  mov     eax, [rdi+20h]
0x140bd9f89  lea     r8, aWhichspaceXBuf; "(WhichSpace=%x, Buffer=%p, Offset=%x, L"...
0x140bd9f90  mov     r9d, [rdi+8]
0x140bd9f94  xor     edx, edx; Level
0x140bd9f96  mov     [rsp+48h+var_18], eax
0x140bd9f9a  mov     eax, [rdi+18h]
0x140bd9f9d  mov     [rsp+48h+var_20], eax
0x140bd9fa1  mov     rax, [rdi+10h]
0x140bd9fa5  lea     ecx, [rdx+5Dh]; ComponentId
0x140bd9fa8  mov     [rsp+48h+var_28], rax
0x140bd9fad  call    DbgPrintEx
0x140bd9fb2  jmp     short loc_140BDA01D
0x140bd9fb4  mov     ecx, [rdi+8]
0x140bd9fb7  test    ecx, ecx
0x140bd9fb9  jz      short loc_140BD9FC9
0x140bd9fbb  cmp     ecx, 1
0x140bd9fbe  jnz     short loc_140BD9F6E
0x140bd9fc0  lea     rbx, aDevicetextloca; "(DeviceTextLocationInformation)"
0x140bd9fc7  jmp     short loc_140BD9F6E
0x140bd9fc9  lea     rbx, aDevicetextdesc; "(DeviceTextDescription)"
0x140bd9fd0  jmp     short loc_140BD9F6E
0x140bd9fd2  mov     ecx, [rdi+8]
0x140bd9fd5  test    ecx, ecx
0x140bd9fd7  jz      short loc_140BDA011
0x140bd9fd9  sub     ecx, 1
0x140bd9fdc  jz      short loc_140BDA008
0x140bd9fde  sub     ecx, 1
0x140bd9fe1  jz      short loc_140BD9FFF
0x140bd9fe3  sub     ecx, 1
0x140bd9fe6  jz      short loc_140BD9FF6
0x140bd9fe8  cmp     ecx, 1
0x140bd9feb  jnz     short loc_140BD9F6E
0x140bd9fed  lea     rcx, aTargetdevicere; "(TargetDeviceRelation)"
0x140bd9ff4  jmp     short loc_140BDA018
0x140bd9ff6  lea     rcx, aRemovalrelatio; "(RemovalRelations)"
0x140bd9ffd  jmp     short loc_140BDA018
0x140bd9fff  lea     rcx, aPowerrelations_0; "(PowerRelations)"
0x140bda006  jmp     short loc_140BDA018
0x140bda008  lea     rcx, aEjectionrelati; "(EjectionRelations)"
0x140bda00f  jmp     short loc_140BDA018
0x140bda011  lea     rcx, aBusrelations_0; "(BusRelations)"
0x140bda018  call    VfUtilDbgPrint
0x140bda01d  mov     rbx, [rsp+48h+arg_0]
0x140bda022  add     rsp, 40h
0x140bda026  pop     rdi
0x140bda027  retn
```
