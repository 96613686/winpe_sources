# Microsoft.Xrm.CrmLicenseData::AddCommonLicenses

- ea: `0x4220`
- end: `0x9525`
- name: `Microsoft.Xrm.CrmLicenseData::AddCommonLicenses`
- size: `21253`
- prototype: ``
- caller_count: `1`
- callee_count: `351`
- tags: `broker_com_uri`

## callers

- `0xc600`

## callees

- `0xc690`
- `0xdf10`
- `0xdf20`
- `0xdf30`
- `0xdf40`
- `0xdf50`
- `0xdf60`
- `0xdf70`
- `0xdf80`
- `0xdf90`
- `0xdfa0`
- `0xdfb0`
- `0xdfc0`
- `0xdfd0`
- `0xdfe0`
- `0xdff0`
- `0xe000`
- `0xe010`
- `0xe020`
- `0xe030`
- `0xe040`
- `0xe050`
- `0xe060`
- `0xe070`
- `0xe080`
- `0xe090`
- `0xe0a0`
- `0xe0b0`
- `0xe0c0`
- `0xe0d0`
- `0xe0e0`
- `0xe0f0`
- `0xe100`
- `0xe110`
- `0xe120`
- `0xe130`
- `0xe140`
- `0xe150`
- `0xe160`
- `0xe170`
- `0xe180`
- `0xe190`
- `0xe1a0`
- `0xe1b0`
- `0xe1c0`
- `0xe1d0`
- `0xe1e0`
- `0xe1f0`
- `0xe200`
- `0xe210`

## pseudocode

```c

```

## disassembly

```asm
0x4220  ldsfld   class Microsoft.Xrm.LicensesPrivileges Microsoft.Xrm.CrmLicenseData::licensesPrivileges
0x4225  ldstr    a0999196858354f// "{09991968-5835-4fb6-B552-D9FF0632AB3D}"
0x422a  ldc.i4   0xCD
0x422f  newarr   Microsoft.Xrm.PrivilegeDefinition
0x4234  dup
0x4235  ldc.i4.0
0x4236  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateACIViewMapper()
0x423b  stelem.ref
0x423c  dup
0x423d  ldc.i4.1
0x423e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadACIViewMapper()
0x4243  stelem.ref
0x4244  dup
0x4245  ldc.i4.2
0x4246  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteACIViewMapper()
0x424b  stelem.ref
0x424c  dup
0x424d  ldc.i4.3
0x424e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteACIViewMapper()
0x4253  stelem.ref
0x4254  dup
0x4255  ldc.i4.4
0x4256  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateActionCardUserSettings()
0x425b  stelem.ref
0x425c  dup
0x425d  ldc.i4.5
0x425e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadActionCardUserSettings()
0x4263  stelem.ref
0x4264  dup
0x4265  ldc.i4.6
0x4266  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteActionCardUserSettings()
0x426b  stelem.ref
0x426c  dup
0x426d  ldc.i4.7
0x426e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteActionCardUserSettings()
0x4273  stelem.ref
0x4274  dup
0x4275  ldc.i4.8
0x4276  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareActionCardUserSettings()
0x427b  stelem.ref
0x427c  dup
0x427d  ldc.i4.s 9
0x427f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateAsyncOperation()
0x4284  stelem.ref
0x4285  dup
0x4286  ldc.i4.s 0xA
0x4288  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadAsyncOperation()
0x428d  stelem.ref
0x428e  dup
0x428f  ldc.i4.s 0xB
0x4291  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteAsyncOperation()
0x4296  stelem.ref
0x4297  dup
0x4298  ldc.i4.s 0xC
0x429a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteAsyncOperation()
0x429f  stelem.ref
0x42a0  dup
0x42a1  ldc.i4.s 0xD
0x42a3  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareAsyncOperation()
0x42a8  stelem.ref
0x42a9  dup
0x42aa  ldc.i4.s 0xE
0x42ac  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignAsyncOperation()
0x42b1  stelem.ref
0x42b2  dup
0x42b3  ldc.i4.s 0xF
0x42b5  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendAsyncOperation()
0x42ba  stelem.ref
0x42bb  dup
0x42bc  ldc.i4.s 0x10
0x42be  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToAsyncOperation()
0x42c3  stelem.ref
0x42c4  dup
0x42c5  ldc.i4.s 0x11
0x42c7  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateAttributeMap()
0x42cc  stelem.ref
0x42cd  dup
0x42ce  ldc.i4.s 0x12
0x42d0  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadAttributeMap()
0x42d5  stelem.ref
0x42d6  dup
0x42d7  ldc.i4.s 0x13
0x42d9  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteAttributeMap()
0x42de  stelem.ref
0x42df  dup
0x42e0  ldc.i4.s 0x14
0x42e2  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteAttributeMap()
0x42e7  stelem.ref
0x42e8  dup
0x42e9  ldc.i4.s 0x15
0x42eb  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendAttributeMap()
0x42f0  stelem.ref
0x42f1  dup
0x42f2  ldc.i4.s 0x16
0x42f4  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToAttributeMap()
0x42f9  stelem.ref
0x42fa  dup
0x42fb  ldc.i4.s 0x17
0x42fd  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateAuthorizationServer()
0x4302  stelem.ref
0x4303  dup
0x4304  ldc.i4.s 0x18
0x4306  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteAuthorizationServer()
0x430b  stelem.ref
0x430c  dup
0x430d  ldc.i4.s 0x19
0x430f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadAuthorizationServer()
0x4314  stelem.ref
0x4315  dup
0x4316  ldc.i4.s 0x1A
0x4318  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendAuthorizationServer()
0x431d  stelem.ref
0x431e  dup
0x431f  ldc.i4.s 0x1B
0x4321  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToAuthorizationServer()
0x4326  stelem.ref
0x4327  dup
0x4328  ldc.i4.s 0x1C
0x432a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteAuthorizationServer()
0x432f  stelem.ref
0x4330  dup
0x4331  ldc.i4.s 0x1D
0x4333  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateAzureServiceConnection()
0x4338  stelem.ref
0x4339  dup
0x433a  ldc.i4.s 0x1E
0x433c  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadAzureServiceConnection()
0x4341  stelem.ref
0x4342  dup
0x4343  ldc.i4.s 0x1F
0x4345  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteAzureServiceConnection()
0x434a  stelem.ref
0x434b  dup
0x434c  ldc.i4.s 0x20
0x434e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteAzureServiceConnection()
0x4353  stelem.ref
0x4354  dup
0x4355  ldc.i4.s 0x21
0x4357  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendAzureServiceConnection()
0x435c  stelem.ref
0x435d  dup
0x435e  ldc.i4.s 0x22
0x4360  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToAzureServiceConnection()
0x4365  stelem.ref
0x4366  dup
0x4367  ldc.i4.s 0x23
0x4369  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateNewsArticle()
0x436e  stelem.ref
0x436f  dup
0x4370  ldc.i4.s 0x24
0x4372  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadNewsArticle()
0x4377  stelem.ref
0x4378  dup
0x4379  ldc.i4.s 0x25
0x437b  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteNewsArticle()
0x4380  stelem.ref
0x4381  dup
0x4382  ldc.i4.s 0x26
0x4384  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteNewsArticle()
0x4389  stelem.ref
0x438a  dup
0x438b  ldc.i4.s 0x27
0x438d  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToNewsArticle()
0x4392  stelem.ref
0x4393  dup
0x4394  ldc.i4.s 0x28
0x4396  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateChannelAccessProfile()
0x439b  stelem.ref
0x439c  dup
0x439d  ldc.i4.s 0x29
0x439f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadChannelAccessProfile()
0x43a4  stelem.ref
0x43a5  dup
0x43a6  ldc.i4.s 0x2A
0x43a8  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteChannelAccessProfile()
0x43ad  stelem.ref
0x43ae  dup
0x43af  ldc.i4.s 0x2B
0x43b1  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteChannelAccessProfile()
0x43b6  stelem.ref
0x43b7  dup
0x43b8  ldc.i4.s 0x2C
0x43ba  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignChannelAccessProfile()
0x43bf  stelem.ref
0x43c0  dup
0x43c1  ldc.i4.s 0x2D
0x43c3  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareChannelAccessProfile()
0x43c8  stelem.ref
0x43c9  dup
0x43ca  ldc.i4.s 0x2E
0x43cc  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendChannelAccessProfile()
0x43d1  stelem.ref
0x43d2  dup
0x43d3  ldc.i4.s 0x2F
0x43d5  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToChannelAccessProfile()
0x43da  stelem.ref
0x43db  dup
0x43dc  ldc.i4.s 0x30
0x43de  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateProfileRule()
0x43e3  stelem.ref
0x43e4  dup
0x43e5  ldc.i4.s 0x31
0x43e7  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadProfileRule()
0x43ec  stelem.ref
0x43ed  dup
0x43ee  ldc.i4.s 0x32
0x43f0  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteProfileRule()
0x43f5  stelem.ref
0x43f6  dup
0x43f7  ldc.i4.s 0x33
0x43f9  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendProfileRule()
0x43fe  stelem.ref
0x43ff  dup
0x4400  ldc.i4.s 0x34
0x4402  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToProfileRule()
0x4407  stelem.ref
0x4408  dup
0x4409  ldc.i4.s 0x35
0x440b  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteProfileRule()
0x4410  stelem.ref
0x4411  dup
0x4412  ldc.i4.s 0x36
0x4414  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareProfileRule()
0x4419  stelem.ref
0x441a  dup
0x441b  ldc.i4.s 0x37
0x441d  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignProfileRule()
0x4422  stelem.ref
0x4423  dup
0x4424  ldc.i4.s 0x38
0x4426  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateComplexControl()
0x442b  stelem.ref
0x442c  dup
0x442d  ldc.i4.s 0x39
0x442f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadComplexControl()
0x4434  stelem.ref
0x4435  dup
0x4436  ldc.i4.s 0x3A
0x4438  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteComplexControl()
0x443d  stelem.ref
0x443e  dup
0x443f  ldc.i4.s 0x3B
0x4441  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteComplexControl()
0x4446  stelem.ref
0x4447  dup
0x4448  ldc.i4.s 0x3C
0x444a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateDataPerformance()
0x444f  stelem.ref
0x4450  dup
0x4451  ldc.i4.s 0x3D
0x4453  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadDataPerformance()
0x4458  stelem.ref
0x4459  dup
0x445a  ldc.i4.s 0x3E
0x445c  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteDataPerformance()
0x4461  stelem.ref
0x4462  dup
0x4463  ldc.i4.s 0x3F
0x4465  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteDataPerformance()
0x446a  stelem.ref
0x446b  dup
0x446c  ldc.i4.s 0x40
0x446e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendDataPerformance()
0x4473  stelem.ref
0x4474  dup
0x4475  ldc.i4.s 0x41
0x4477  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToDataPerformance()
0x447c  stelem.ref
0x447d  dup
0x447e  ldc.i4.s 0x42
0x4480  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadDelveActionHub()
0x4485  stelem.ref
0x4486  dup
0x4487  ldc.i4.s 0x43
0x4489  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateDocumentTemplate()
0x448e  stelem.ref
0x448f  dup
0x4490  ldc.i4.s 0x44
0x4492  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadDocumentTemplate()
0x4497  stelem.ref
0x4498  dup
0x4499  ldc.i4.s 0x45
0x449b  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteDocumentTemplate()
0x44a0  stelem.ref
0x44a1  dup
0x44a2  ldc.i4.s 0x46
0x44a4  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteDocumentTemplate()
0x44a9  stelem.ref
0x44aa  dup
0x44ab  ldc.i4.s 0x47
0x44ad  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendDocumentTemplate()
0x44b2  stelem.ref
0x44b3  dup
0x44b4  ldc.i4.s 0x48
0x44b6  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToDocumentTemplate()
0x44bb  stelem.ref
0x44bc  dup
0x44bd  ldc.i4.s 0x49
0x44bf  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_PublishDuplicateRule()
0x44c4  stelem.ref
  ... truncated ...
```
