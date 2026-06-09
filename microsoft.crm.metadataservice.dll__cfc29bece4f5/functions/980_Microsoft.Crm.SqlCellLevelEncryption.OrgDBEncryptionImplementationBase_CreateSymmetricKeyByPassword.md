# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateSymmetricKeyByPassword

- ea: `0x980`
- end: `0xa4f`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateSymmetricKeyByPassword`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8d0`

## callees

- `0x650`
- `0x690`
- `0x980`
- `0xa50`

## string_xrefs

- `0x9c0`: `Symmetric key password '{0}' was randomly generated, but cannot be used to create symmetric key into the database (attempt {1} of (2)). Exception: {3}`
- `0xa0c`: `We try maximum {0} times to create symmetric key encrypted by password using randomly gnerated passwords. Actual number of attempts is {1}. `

## pseudocode

```c

```

## disassembly

```asm
0x980  ldarg.0
0x981  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.BasicEncryptionOperations Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::get_Encryption()
0x986  ldstr    aCrmsymmetricke// "CrmSymmetricKey1"
0x98b  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.BasicEncryptionOperations::ExistsSymmetricKey(string)
0x990  brtrue   loc_A31
0x995  ldc.i4.1
0x996  stloc.0
0x997  ldarg.0
0x998  call     instance string Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::GenerateRandomSymmetricKeyPassword()
0x99d  stloc.1
0x99e  br.s     loc_9FF
0x9a0  nop
0x9a1  ldarg.0
0x9a2  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.BasicEncryptionOperations Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::get_Encryption()
0x9a7  ldstr    aCrmsymmetricke// "CrmSymmetricKey1"
0x9ac  ldarg.1
0x9ad  ldloc.1
0x9ae  ldnull
0x9af  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.BasicEncryptionOperations::CreateSymmetricKeyByPassword(string, string, string, string)
0x9b4  leave.s  loc_A04
0x9b6  stloc.2
0x9b7  ldloc.2
0x9b8  ldarg.0
0x9b9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::get_OrganizationId()
0x9be  ldc.i4.s 0x1D
0x9c0  ldstr    aSymmetricKeyPa// "Symmetric key password '{0}' was random"...
0x9c5  ldc.i4.4
0x9c6  newarr   [mscorlib]System.Object
0x9cb  dup
0x9cc  ldc.i4.0
0x9cd  ldloc.1
0x9ce  stelem.ref
0x9cf  dup
0x9d0  ldc.i4.1
0x9d1  ldloc.0
0x9d2  box      [mscorlib]System.Int32
0x9d7  stelem.ref
0x9d8  dup
0x9d9  ldc.i4.2
0x9da  ldc.i4.s 0xA
0x9dc  box      [mscorlib]System.Int32
0x9e1  stelem.ref
0x9e2  dup
0x9e3  ldc.i4.3
0x9e4  ldloc.2
0x9e5  stelem.ref
0x9e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9eb  ldloc.0
0x9ec  ldc.i4.s 0xA
0x9ee  bne.un.s loc_9F2
0x9f0  rethrow
0x9f2  leave.s  loc_9F4
0x9f4  ldloc.0
0x9f5  ldc.i4.1
0x9f6  add
0x9f7  stloc.0
0x9f8  ldarg.0
0x9f9  call     instance string Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::GenerateRandomSymmetricKeyPassword()
0x9fe  stloc.1
0x9ff  ldloc.0
0xa00  ldc.i4.s 0xA
0xa02  ble.s    loc_9A0
0xa04  ldloc.0
0xa05  ldc.i4.s 0xA
0xa07  cgt
0xa09  ldc.i4.0
0xa0a  ceq
0xa0c  ldstr    aWeTryMaximum0T// "We try maximum {0} times to create symm"...
0xa11  ldc.i4.2
0xa12  newarr   [mscorlib]System.Object
0xa17  dup
0xa18  ldc.i4.0
0xa19  ldc.i4.s 0xA
0xa1b  box      [mscorlib]System.Int32
0xa20  stelem.ref
0xa21  dup
0xa22  ldc.i4.1
0xa23  ldloc.0
0xa24  box      [mscorlib]System.Int32
0xa29  stelem.ref
0xa2a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0xa2f  ldloc.1
0xa30  ret
0xa31  ldarg.2
0xa32  brfalse.s loc_A4D
0xa34  ldc.i4   0x80048521
0xa39  ldc.i4.1
0xa3a  newarr   [mscorlib]System.Object
0xa3f  dup
0xa40  ldc.i4.0
0xa41  ldstr    aCrmsymmetricke// "CrmSymmetricKey1"
0xa46  stelem.ref
0xa47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa4c  throw
0xa4d  ldnull
0xa4e  ret
```
