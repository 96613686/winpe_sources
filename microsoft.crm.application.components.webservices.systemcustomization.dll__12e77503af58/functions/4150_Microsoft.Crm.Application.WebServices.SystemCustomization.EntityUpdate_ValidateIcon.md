# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon

- ea: `0x4150`
- end: `0x422c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::ValidateIcon`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4020`

## callees

- `0x4150`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldarg.0
0x4151  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4156  brfalse.s loc_4159
0x4158  ret
0x4159  ldarg.0
0x415a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x415f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetWebResources(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4164  stloc.0
0x4165  ldloc.0
0x4166  brfalse.s loc_4170
0x4168  ldloc.0
0x4169  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x416e  brtrue.s loc_4186
0x4170  ldstr    aCouldNotFindAW// "Could not find a web resource with name"...
0x4175  ldarg.0
0x4176  ldstr    asc_D5BA// "."
0x417b  call     string [mscorlib]System.String::Concat(string, string, string)
0x4180  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4185  throw
0x4186  ldloc.0
0x4187  ldc.i4.0
0x4188  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x418d  stloc.1
0x418e  ldloc.1
0x418f  ldstr    aContent// "content"
0x4194  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4199  castclass [mscorlib]System.String
0x419e  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x41a3  stloc.2
0x41a4  ldloc.2
0x41a5  ldlen
0x41a6  conv.i4
0x41a7  ldc.i4   0x2800
0x41ac  ble.s    loc_41BB
0x41ae  ldarg.1
0x41af  ldc.i4.0
0x41b0  newarr   [mscorlib]System.Object
0x41b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x41ba  throw
0x41bb  ldloc.1
0x41bc  ldstr    aWebresourcetyp// "webresourcetype"
0x41c1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x41c6  unbox.any [mscorlib]System.Int32
0x41cb  ldc.i4.s 0xB
0x41cd  bne.un.s loc_41D0
0x41cf  ret
0x41d0  ldloc.2
0x41d1  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x41d6  stloc.3
0x41d7  ldloc.3
0x41d8  call     class [System.Drawing]System.Drawing.Image [System.Drawing]System.Drawing.Image::FromStream(class [mscorlib]System.IO.Stream)
0x41dd  stloc.s  4
0x41df  ldloc.s  4
0x41e1  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Image::get_Size()
0x41e6  stloc.s  5
0x41e8  ldloca.s 5
0x41ea  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x41ef  ldarg.s  4
0x41f1  bne.un.s loc_4206
0x41f3  ldloc.s  4
0x41f5  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Image::get_Size()
0x41fa  stloc.s  5
0x41fc  ldloca.s 5
0x41fe  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x4203  ldarg.3
0x4204  beq.s    loc_4213
0x4206  ldarg.2
0x4207  ldc.i4.0
0x4208  newarr   [mscorlib]System.Object
0x420d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4212  throw
0x4213  leave.s  loc_422B
0x4215  ldloc.s  4
0x4217  brfalse.s loc_4220
0x4219  ldloc.s  4
0x421b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4220  endfinally
0x4221  ldloc.3
0x4222  brfalse.s loc_422A
0x4224  ldloc.3
0x4225  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x422a  endfinally
0x422b  ret
```
