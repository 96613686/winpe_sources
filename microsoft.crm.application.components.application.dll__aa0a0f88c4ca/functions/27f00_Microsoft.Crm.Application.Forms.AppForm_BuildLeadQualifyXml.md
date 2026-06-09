# Microsoft.Crm.Application.Forms.AppForm::BuildLeadQualifyXml

- ea: `0x27f00`
- end: `0x27fb8`
- name: `Microsoft.Crm.Application.Forms.AppForm::BuildLeadQualifyXml`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x27fc0`

## callees

- `0x27f00`

## string_xrefs

- `0x27f11`: `qlCreateAccount`
- `0x27f19`: `qlCreateContact`
- `0x27f21`: `qlCreateOpportunity`

## pseudocode

```c

```

## disassembly

```asm
0x27f00  ldc.i4.s 0xC
0x27f02  newarr   [mscorlib]System.String
0x27f07  dup
0x27f08  ldc.i4.0
0x27f09  ldstr    aQlshownew// "qlShowNew"
0x27f0e  stelem.ref
0x27f0f  dup
0x27f10  ldc.i4.1
0x27f11  ldstr    aQlcreateaccoun// "qlCreateAccount"
0x27f16  stelem.ref
0x27f17  dup
0x27f18  ldc.i4.2
0x27f19  ldstr    aQlcreatecontac// "qlCreateContact"
0x27f1e  stelem.ref
0x27f1f  dup
0x27f20  ldc.i4.3
0x27f21  ldstr    aQlcreateopport// "qlCreateOpportunity"
0x27f26  stelem.ref
0x27f27  dup
0x27f28  ldc.i4.4
0x27f29  ldstr    aUlnewstatus// "ulNewStatus"
0x27f2e  stelem.ref
0x27f2f  dup
0x27f30  ldc.i4.5
0x27f31  ldstr    aQlsuppressdupl// "qlSuppressDuplicateDetection"
0x27f36  stelem.ref
0x27f37  dup
0x27f38  ldc.i4.6
0x27f39  ldstr    aQloppcurrencyi// "qlOppCurrencyId"
0x27f3e  stelem.ref
0x27f3f  dup
0x27f40  ldc.i4.7
0x27f41  ldstr    aQlopportunityp// "qlOpportunityParentId"
0x27f46  stelem.ref
0x27f47  dup
0x27f48  ldc.i4.8
0x27f49  ldstr    aQlopportunityp_0// "qlOpportunityParentType"
0x27f4e  stelem.ref
0x27f4f  dup
0x27f50  ldc.i4.s 9
0x27f52  ldstr    aQlleadid// "qlLeadId"
0x27f57  stelem.ref
0x27f58  dup
0x27f59  ldc.i4.s 0xA
0x27f5b  ldstr    aQlcampaignid// "qlCampaignId"
0x27f60  stelem.ref
0x27f61  dup
0x27f62  ldc.i4.s 0xB
0x27f64  ldstr    aQlcampaigntype// "qlCampaignType"
0x27f69  stelem.ref
0x27f6a  ldstr    aQualifylead// "<QualifyLead>"
0x27f6f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x27f74  stloc.0
0x27f75  stloc.1
0x27f76  ldc.i4.0
0x27f77  stloc.2
0x27f78  br.s     loc_27F9F
0x27f7a  ldloc.1
0x27f7b  ldloc.2
0x27f7c  ldelem.ref
0x27f7d  stloc.3
0x27f7e  ldarg.1
0x27f7f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x27f84  ldloc.3
0x27f85  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x27f8a  stloc.s  4
0x27f8c  ldloc.0
0x27f8d  ldstr    a010// "<{0}>{1}</{0}>"
0x27f92  ldloc.3
0x27f93  ldloc.s  4
0x27f95  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x27f9a  pop
0x27f9b  ldloc.2
0x27f9c  ldc.i4.1
0x27f9d  add
0x27f9e  stloc.2
0x27f9f  ldloc.2
0x27fa0  ldloc.1
0x27fa1  ldlen
0x27fa2  conv.i4
0x27fa3  blt.s    loc_27F7A
0x27fa5  ldloc.0
0x27fa6  ldstr    aQualifylead_0// "</QualifyLead>"
0x27fab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27fb0  pop
0x27fb1  ldloc.0
0x27fb2  callvirt instance string [mscorlib]System.Object::ToString()
0x27fb7  ret
```
