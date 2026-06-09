# Microsoft.Crm.Security.User::GetPrivilegeTypeFromAccessRights

- ea: `0xecb0`
- end: `0xed32`
- name: `Microsoft.Crm.Security.User::GetPrivilegeTypeFromAccessRights`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xec90`

## callees

- `0xecb0`

## string_xrefs

- `0xed15`: `Invalid access rights: `
- `0xed25`: `accessRights`

## pseudocode

```c

```

## disassembly

```asm
0xecb0  ldc.i4.m1
0xecb1  stloc.0
0xecb2  ldarg.0
0xecb3  ldc.i4.s 0x20
0xecb5  bgt.s    loc_ECDB
0xecb7  ldarg.0
0xecb8  ldc.i4.1
0xecb9  sub
0xecba  switch   loc_ED09, loc_ED11, loc_ED15, loc_ECF5
0xeccf  ldarg.0
0xecd0  ldc.i4.s 0x10
0xecd2  beq.s    loc_ECF9
0xecd4  ldarg.0
0xecd5  ldc.i4.s 0x20
0xecd7  beq.s    loc_ED01
0xecd9  br.s     loc_ED15
0xecdb  ldarg.0
0xecdc  ldc.i4   0x10000
0xece1  beq.s    loc_ED05
0xece3  ldarg.0
0xece4  ldc.i4   0x40000
0xece9  beq.s    loc_ED0D
0xeceb  ldarg.0
0xecec  ldc.i4   0x80000
0xecf1  beq.s    loc_ECFD
0xecf3  br.s     loc_ED15
0xecf5  ldc.i4.6
0xecf6  stloc.0
0xecf7  br.s     loc_ED30
0xecf9  ldc.i4.7
0xecfa  stloc.0
0xecfb  br.s     loc_ED30
0xecfd  ldc.i4.4
0xecfe  stloc.0
0xecff  br.s     loc_ED30
0xed01  ldc.i4.0
0xed02  stloc.0
0xed03  br.s     loc_ED30
0xed05  ldc.i4.3
0xed06  stloc.0
0xed07  br.s     loc_ED30
0xed09  ldc.i4.1
0xed0a  stloc.0
0xed0b  br.s     loc_ED30
0xed0d  ldc.i4.5
0xed0e  stloc.0
0xed0f  br.s     loc_ED30
0xed11  ldc.i4.2
0xed12  stloc.0
0xed13  br.s     loc_ED30
0xed15  ldstr    aInvalidAccessR// "Invalid access rights: "
0xed1a  ldarg.0
0xed1b  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0xed20  call     string [mscorlib]System.String::Concat(object, object)
0xed25  ldstr    aAccessrights// "accessRights"
0xed2a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xed2f  throw
0xed30  ldloc.0
0xed31  ret
```
