# Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::.cctor

- ea: `0x184e0`
- end: `0x188f1`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::.cctor`
- size: `1041`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x184f4`: `A record with matching key values already exists.`

## pseudocode

```c

```

## disassembly

```asm
0x184e0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x184e5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorMessageMap
0x184ea  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorMessageMap
0x184ef  ldc.i4   0x80040237
0x184f4  ldstr    aARecordWithMat// "A record with matching key values alrea"...
0x184f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x184fe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::.ctor()
0x18503  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18508  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1850d  ldc.i4   0x80048405
0x18512  ldc.i4   0x193
0x18517  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1851c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18521  ldc.i4   0x8004F504
0x18526  ldc.i4   0x193
0x1852b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18530  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18535  ldc.i4   0x8004F507
0x1853a  ldc.i4   0x193
0x1853f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18544  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18549  ldc.i4   0x8004F502
0x1854e  ldc.i4   0x193
0x18553  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18558  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1855d  ldc.i4   0x8004A110
0x18562  ldc.i4   0x193
0x18567  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1856c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18571  ldc.i4   0x8004ED43
0x18576  ldc.i4   0x193
0x1857b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18580  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18585  ldc.i4   0x80040256
0x1858a  ldc.i4   0x193
0x1858f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18594  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18599  ldc.i4   0x8004020D
0x1859e  ldc.i4   0x193
0x185a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x185a8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x185ad  ldc.i4   0x80040231
0x185b2  ldc.i4   0x193
0x185b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x185bc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x185c1  ldc.i4   0x80040276
0x185c6  ldc.i4   0x193
0x185cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x185d0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x185d5  ldc.i4   0x80040220
0x185da  ldc.i4   0x193
0x185df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x185e4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x185e9  ldc.i4   0x8004049E
0x185ee  ldc.i4   0x193
0x185f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x185f8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x185fd  ldc.i4   0x800404BB
0x18602  ldc.i4   0x193
0x18607  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1860c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18611  ldc.i4   0x80048306
0x18616  ldc.i4   0x193
0x1861b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18620  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18625  ldc.i4   0x80042F09
0x1862a  ldc.i4   0x193
0x1862f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18634  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18639  ldc.i4   0x8004A102
0x1863e  ldc.i4   0x191
0x18643  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18648  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1864d  ldc.i4   0x8004A101
0x18652  ldc.i4   0x191
0x18657  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1865c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18661  ldc.i4   0x8004A103
0x18666  ldc.i4   0x191
0x1866b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18670  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18675  ldc.i4   0x8004A100
0x1867a  ldc.i4   0x191
0x1867f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18684  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18689  ldc.i4   0x80040204
0x1868e  ldc.i4   0x191
0x18693  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18698  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1869d  ldc.i4   0x80044300
0x186a2  ldc.i4   0x191
0x186a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x186ac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x186b1  ldc.i4   0x80044308
0x186b6  ldc.i4   0x191
0x186bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x186c0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x186c5  ldc.i4   0x80044302
0x186ca  ldc.i4   0x191
0x186cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x186d4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x186d9  ldc.i4   0x8004A105
0x186de  ldc.i4   0x191
0x186e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x186e8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x186ed  ldc.i4   0x80040277
0x186f2  ldc.i4   0x191
0x186f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x186fc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18701  ldc.i4   0x800404D2
0x18706  ldc.i4   0x191
0x1870b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18710  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18715  ldc.i4   0x80040227
0x1871a  ldc.i4   0x195
0x1871f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18724  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18729  ldc.i4   0x8004023B
0x1872e  ldc.i4   0x195
0x18733  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18738  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1873d  ldc.i4   0x80040315
0x18742  ldc.i4   0x195
0x18747  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1874c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18751  ldc.i4   0x80040217
0x18756  ldc.i4   0x194
0x1875b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18760  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18765  ldc.i4   0x80060891
0x1876a  ldc.i4   0x194
0x1876f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18774  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18779  ldc.i4   0x8004418A
0x1877e  ldc.i4   0x19D
0x18783  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18788  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1878d  ldc.i4   0x80060882
0x18792  ldc.i4   0x19C
0x18797  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1879c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x187a1  ldc.i4   0x80040237
0x187a6  ldc.i4   0x19C
0x187ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x187b0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x187b5  ldc.i4   0x80060892
0x187ba  ldc.i4   0x19C
0x187bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x187c4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x187c9  ldc.i4   0x80040333
0x187ce  ldc.i4   0x19C
0x187d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x187d8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x187dd  ldc.i4   0x80040203
0x187e2  ldc.i4   0x190
0x187e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x187ec  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x187f1  ldc.i4   0x80060890
0x187f6  ldc.i4   0x190
0x187fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18800  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18805  ldc.i4   0x8004F01F
0x1880a  ldc.i4   0x190
0x1880f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18814  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18819  ldc.i4   0x80044410
0x1881e  ldc.i4   0x190
0x18823  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18828  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1882d  ldc.i4   0x80044330
0x18832  ldc.i4   0x190
0x18837  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1883c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18841  ldc.i4   0x8004431A
0x18846  ldc.i4   0x190
0x1884b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18850  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18855  ldc.i4   0x8004432F
0x1885a  ldc.i4   0x190
0x1885f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18864  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18869  ldc.i4   0x80044331
0x1886e  ldc.i4   0x190
0x18873  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x18878  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x1887d  ldc.i4   0x8004700C
0x18882  ldc.i4   0x190
0x18887  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x1888c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x18891  ldc.i4   0x80041D33
0x18896  ldc.i4   0x190
0x1889b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x188a0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x188a5  ldc.i4   0x80041D67
0x188aa  ldc.i4   0x190
0x188af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x188b4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x188b9  ldc.i4   0x80040800
0x188be  ldc.i4   0x190
0x188c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x188c8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x188cd  ldc.i4   0x80072321
0x188d2  ldc.i4   0x1AD
0x188d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x188dc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Extensibility.OData.CrmODataExceptionHandler::_crmErrorStatusCodeMap
0x188e1  ldc.i4   0x80072322
0x188e6  ldc.i4   0x1AD
0x188eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System]System.Net.HttpStatusCode>::Add(var<u1>, !!T0)
0x188f0  ret
```
