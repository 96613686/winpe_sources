# Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::.ctor

- ea: `0x109e0`
- end: `0x10a6c`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::.ctor`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10550`

## callees

- `0x109e0`
- `0x10a70`

## pseudocode

```c

```

## disassembly

```asm
0x109e0  ldarg.0
0x109e1  call     instance void [mscorlib]System.Object::.ctor()
0x109e6  ldarg.1
0x109e7  brtrue.s loc_109F4
0x109e9  ldstr    aMetadatabase// "metadataBase"
0x109ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x109f3  throw
0x109f4  ldarg.0
0x109f5  ldarg.1
0x109f6  stfld    class [System.IdentityModel]System.IdentityModel.Metadata.MetadataBase Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_metadataBase
0x109fb  ldarg.0
0x109fc  ldfld    class [System.IdentityModel]System.IdentityModel.Metadata.MetadataBase Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_metadataBase
0x10a01  isinst   [System.IdentityModel]System.IdentityModel.Metadata.EntitiesDescriptor
0x10a06  stloc.0
0x10a07  ldloc.0
0x10a08  brfalse.s loc_10A46
0x10a0a  ldloc.0
0x10a0b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor> [System.IdentityModel]System.IdentityModel.Metadata.EntitiesDescriptor::get_ChildEntities()
0x10a10  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor>::GetEnumerator()
0x10a15  stloc.1
0x10a16  br.s     loc_10A32
0x10a18  ldloc.1
0x10a19  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor>::get_Current()
0x10a1e  stloc.2
0x10a1f  ldarg.0
0x10a20  ldloc.2
0x10a21  stfld    class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_entityDescriptor
0x10a26  ldarg.0
0x10a27  ldarg.0
0x10a28  ldfld    class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_entityDescriptor
0x10a2d  call     instance void Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::ParseEntityDescriptor(class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor entityDescriptor)
0x10a32  ldloc.1
0x10a33  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10a38  brtrue.s loc_10A18
0x10a3a  leave.s  loc_10A46
0x10a3c  ldloc.1
0x10a3d  brfalse.s loc_10A45
0x10a3f  ldloc.1
0x10a40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a45  endfinally
0x10a46  ldarg.0
0x10a47  ldarg.0
0x10a48  ldfld    class [System.IdentityModel]System.IdentityModel.Metadata.MetadataBase Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_metadataBase
0x10a4d  isinst   [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor
0x10a52  stfld    class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_entityDescriptor
0x10a57  ldarg.0
0x10a58  ldfld    class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_entityDescriptor
0x10a5d  brfalse.s loc_10A6B
0x10a5f  ldarg.0
0x10a60  ldarg.0
0x10a61  ldfld    class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::_entityDescriptor
0x10a66  call     instance void Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::ParseEntityDescriptor(class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor entityDescriptor)
0x10a6b  ret
```
