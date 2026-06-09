# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetModifiedTextXmlWithEmptyPrimitive

- ea: `0x4040`
- end: `0x40a4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetModifiedTextXmlWithEmptyPrimitive`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3fd0`
- `0x41d0`

## callees

- `0x4040`

## pseudocode

```c

```

## disassembly

```asm
0x4040  ldarg.1
0x4041  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4046  brfalse.s loc_404A
0x4048  ldarg.1
0x4049  ret
0x404a  ldstr    aLtSlugbodyGt// "&lt;slugbody&gt;"
0x404f  stloc.0
0x4050  ldstr    aLtSlugelementT// "&lt;slugelement type=\"operator\" value"...
0x4055  stloc.1
0x4056  ldstr    aLtSlugelementT_0// "&lt;slugelement type=\"primitive\" valu"...
0x405b  stloc.2
0x405c  ldstr    aLtSlugelementT_1// "&lt;slugelement type=\"primitive\" valu"...
0x4061  stloc.3
0x4062  ldstr    aLtSlugelementT_2// "&lt;slugelement type=\"slug\"&gt;"
0x4067  stloc.s  4
0x4069  ldarg.1
0x406a  ldloc.0
0x406b  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4070  brfalse.s loc_40A2
0x4072  ldarg.1
0x4073  ldloc.s  4
0x4075  callvirt instance bool [mscorlib]System.String::Contains(string)
0x407a  brfalse.s loc_40A2
0x407c  ldarg.1
0x407d  ldloc.2
0x407e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4083  brtrue.s loc_40A2
0x4085  ldarg.1
0x4086  ldloc.1
0x4087  ldc.i4.0
0x4088  ldc.i4.4
0x4089  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0x408e  stloc.s  5
0x4090  ldarg.1
0x4091  ldloc.s  5
0x4093  ldloc.1
0x4094  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4099  add
0x409a  ldloc.3
0x409b  callvirt instance string [mscorlib]System.String::Insert(int32, string)
0x40a0  starg.s  1
0x40a2  ldarg.1
0x40a3  ret
```
