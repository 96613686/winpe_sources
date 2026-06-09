# Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::EventTypeToCrmLevel

- ea: `0x9b0`
- end: `0xa29`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::EventTypeToCrmLevel`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x950`

## callees

- `0x9b0`

## pseudocode

```c

```

## disassembly

```asm
0x9b0  ldarg.0
0x9b1  ldc.i4   0x100
0x9b6  bgt.s    loc_9E9
0x9b8  ldarg.0
0x9b9  ldc.i4.8
0x9ba  bgt.s    loc_9DA
0x9bc  ldarg.0
0x9bd  ldc.i4.1
0x9be  sub
0x9bf  switch   loc_A15, loc_A15, loc_A25, loc_A19
0x9d4  ldarg.0
0x9d5  ldc.i4.8
0x9d6  beq.s    loc_A1D
0x9d8  br.s     loc_A25
0x9da  ldarg.0
0x9db  ldc.i4.s 0x10
0x9dd  beq.s    loc_A21
0x9df  ldarg.0
0x9e0  ldc.i4   0x100
0x9e5  beq.s    loc_A21
0x9e7  br.s     loc_A25
0x9e9  ldarg.0
0x9ea  ldc.i4   0x400
0x9ef  bgt.s    loc_A03
0x9f1  ldarg.0
0x9f2  ldc.i4   0x200
0x9f7  beq.s    loc_A21
0x9f9  ldarg.0
0x9fa  ldc.i4   0x400
0x9ff  beq.s    loc_A21
0xa01  br.s     loc_A25
0xa03  ldarg.0
0xa04  ldc.i4   0x800
0xa09  beq.s    loc_A21
0xa0b  ldarg.0
0xa0c  ldc.i4   0x1000
0xa11  beq.s    loc_A21
0xa13  br.s     loc_A25
0xa15  ldc.i4.1
0xa16  stloc.0
0xa17  br.s     loc_A27
0xa19  ldc.i4.2
0xa1a  stloc.0
0xa1b  br.s     loc_A27
0xa1d  ldc.i4.3
0xa1e  stloc.0
0xa1f  br.s     loc_A27
0xa21  ldc.i4.4
0xa22  stloc.0
0xa23  br.s     loc_A27
0xa25  ldc.i4.4
0xa26  stloc.0
0xa27  ldloc.0
0xa28  ret
```
