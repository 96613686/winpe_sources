# Microsoft.Crm.Asynchronous.YammerPostOperation::PopulateYammerConfigurationSettings

- ea: `0x9060`
- end: `0x9196`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::PopulateYammerConfigurationSettings`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8ea0`

## callees

- `0x9060`

## string_xrefs

- `0x90af`: `YammerMinWaitTimeForAsyncJobToRecurInSec`

## pseudocode

```c

```

## disassembly

```asm
0x9060  ldarg.0
0x9061  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x9066  ldstr    aYammermaxposts// "YammerMaxPostsInBatch"
0x906b  ldc.i4   0xC8
0x9070  callvirt T0x2B00001C
0x9075  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x907a  ldarg.0
0x907b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x9080  ldstr    aYammermaxposts_0// "YammerMaxPostsToProcessByAsyncJob"
0x9085  ldc.i4   0xC8
0x908a  callvirt T0x2B00001C
0x908f  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x9094  ldarg.0
0x9095  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x909a  ldstr    aYammermaxposts_1// "YammerMaxPostsRetryCount"
0x909f  ldc.i4.5
0x90a0  callvirt T0x2B00001C
0x90a5  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x90aa  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x90af  ldstr    aYammerminwaitt// "YammerMinWaitTimeForAsyncJobToRecurInSe"...
0x90b4  ldc.i4.s 0x3C
0x90b6  callvirt T0x2B00001C
0x90bb  stloc.0
0x90bc  ldarg.0
0x90bd  ldc.i4.0
0x90be  ldc.i4.0
0x90bf  ldloc.0
0x90c0  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x90c5  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.YammerPostOperation::YammerMinWaitTimeForAsyncJobToRecurInSec
0x90ca  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x90cf  ldstr    aYammerminwaitt_0// "YammerMinWaitTimeForPostsInSec"
0x90d4  ldc.i4   0x258
0x90d9  callvirt T0x2B00001C
0x90de  stloc.0
0x90df  ldarg.0
0x90e0  ldc.i4.0
0x90e1  ldc.i4.0
0x90e2  ldloc.0
0x90e3  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x90e8  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.YammerPostOperation::YammerMinWaitTimeForPostsInSec
0x90ed  ldarg.0
0x90ee  ldarg.0
0x90ef  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x90f4  ldc.i4   0xC8
0x90f9  bgt.s    loc_9103
0x90fb  ldarg.0
0x90fc  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x9101  br.s     loc_9108
0x9103  ldc.i4   0xC8
0x9108  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x910d  ldarg.0
0x910e  ldarg.0
0x910f  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x9114  ldc.i4   0xC8
0x9119  bgt.s    loc_9123
0x911b  ldarg.0
0x911c  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x9121  br.s     loc_9128
0x9123  ldc.i4   0xC8
0x9128  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x912d  ldarg.0
0x912e  ldarg.0
0x912f  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x9134  ldc.i4.5
0x9135  bgt.s    loc_913F
0x9137  ldarg.0
0x9138  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x913d  br.s     loc_9140
0x913f  ldc.i4.5
0x9140  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x9145  ldarg.0
0x9146  ldarg.0
0x9147  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x914c  ldc.i4.0
0x914d  bge.s    loc_9156
0x914f  ldc.i4   0xC8
0x9154  br.s     loc_915C
0x9156  ldarg.0
0x9157  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x915c  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x9161  ldarg.0
0x9162  ldarg.0
0x9163  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x9168  ldc.i4.0
0x9169  bge.s    loc_9172
0x916b  ldc.i4   0xC8
0x9170  br.s     loc_9178
0x9172  ldarg.0
0x9173  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x9178  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x917d  ldarg.0
0x917e  ldarg.0
0x917f  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x9184  ldc.i4.0
0x9185  bge.s    loc_918A
0x9187  ldc.i4.5
0x9188  br.s     loc_9190
0x918a  ldarg.0
0x918b  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x9190  stfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0x9195  ret
```
