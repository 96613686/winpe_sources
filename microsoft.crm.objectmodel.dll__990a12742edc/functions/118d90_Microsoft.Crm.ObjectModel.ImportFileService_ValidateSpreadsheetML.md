# Microsoft.Crm.ObjectModel.ImportFileService::ValidateSpreadsheetML

- ea: `0x118d90`
- end: `0x119241`
- name: `Microsoft.Crm.ObjectModel.ImportFileService::ValidateSpreadsheetML`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x118ba0`

## callees

- `0x118d90`
- `0x11bf90`

## string_xrefs

- `0x118d9f`: `xmlss_c.xsd`
- `0x118dc6`: `xmlss_c.xsd`
- `0x118de3`: `xmlss_dt.xsd`
- `0x118e00`: `xmlss_excel.xsd`
- `0x118e1d`: `xmlss_excel2003xml.xsd`
- `0x118e3a`: `xmlss_excelss.xsd`
- `0x118e57`: `xmlss_office.xsd`
- `0x118e74`: `xmlss_rowsetschema.xsd`
- `0x118e91`: `xmlss_rowsset.xsd`
- `0x118eae`: `xmlss_schema.xsd`
- `0x118ecb`: `xmlss_udc.xsd`
- `0x118ee8`: `xmlss_udcsoap.xsd`
- `0x118f05`: `xmlss_udcxmlfile.xsd`
- `0x118f22`: `xmlss_vml.xsd`
- `0x118f65`: `/_resources/xmlss_c.xsd`
- `0x118f86`: `/_resources/xmlss_dt.xsd`
- `0x118fa7`: `/_resources/xmlss_excel.xsd`
- `0x118fc8`: `/_resources/xmlss_excel2003xml.xsd`
- `0x118fe9`: `/_resources/xmlss_excelss.xsd`
- `0x11900a`: `/_resources/xmlss_office.xsd`
- `0x11902b`: `/_resources/xmlss_rowsetschema.xsd`
- `0x11904c`: `/_resources/xmlss_rowsset.xsd`
- `0x11906d`: `/_resources/xmlss_schema.xsd`
- `0x11908e`: `/_resources/xmlss_udc.xsd`
- `0x1190af`: `/_resources/xmlss_udcsoap.xsd`
- `0x1190d0`: `/_resources/xmlss_udcxmlfile.xsd`
- `0x1190f1`: `/_resources/xmlss_vml.xsd`
- `0x11914c`: `urn:schemas-microsoft-com:office:spreadsheet`
- `0x1191a0`: `ValidateSpreadsheetML hit exception. Message: {0} Details: {1} {2}`
- `0x119207`: `ValidateSpreadsheetML hit exception. Message: {0} Details: {1} {2}`

## pseudocode

```c

```

## disassembly

```asm
0x118d90  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x118d95  stloc.0
0x118d96  ldarg.0
0x118d97  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118d9c  brtrue.s loc_118DAE
0x118d9e  ldarg.0
0x118d9f  ldstr    aXmlssCXsd// "xmlss_c.xsd"
0x118da4  call     string Microsoft.Crm.ObjectModel.ImportServicesHelper::GetPathToXsdIfExistsInTheSameFolderAsAssembly(string xsdFileName)
0x118da9  stfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118dae  ldarg.0
0x118daf  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118db4  brfalse  loc_118F54
0x118db9  ldloc.0
0x118dba  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118dbf  ldnull
0x118dc0  ldarg.0
0x118dc1  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118dc6  ldstr    aXmlssCXsd// "xmlss_c.xsd"
0x118dcb  call     string [mscorlib]System.String::Concat(string, string)
0x118dd0  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118dd5  pop
0x118dd6  ldloc.0
0x118dd7  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118ddc  ldnull
0x118ddd  ldarg.0
0x118dde  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118de3  ldstr    aXmlssDtXsd// "xmlss_dt.xsd"
0x118de8  call     string [mscorlib]System.String::Concat(string, string)
0x118ded  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118df2  pop
0x118df3  ldloc.0
0x118df4  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118df9  ldnull
0x118dfa  ldarg.0
0x118dfb  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e00  ldstr    aXmlssExcelXsd// "xmlss_excel.xsd"
0x118e05  call     string [mscorlib]System.String::Concat(string, string)
0x118e0a  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118e0f  pop
0x118e10  ldloc.0
0x118e11  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118e16  ldnull
0x118e17  ldarg.0
0x118e18  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e1d  ldstr    aXmlssExcel2003// "xmlss_excel2003xml.xsd"
0x118e22  call     string [mscorlib]System.String::Concat(string, string)
0x118e27  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118e2c  pop
0x118e2d  ldloc.0
0x118e2e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118e33  ldnull
0x118e34  ldarg.0
0x118e35  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e3a  ldstr    aXmlssExcelssXs// "xmlss_excelss.xsd"
0x118e3f  call     string [mscorlib]System.String::Concat(string, string)
0x118e44  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118e49  pop
0x118e4a  ldloc.0
0x118e4b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118e50  ldnull
0x118e51  ldarg.0
0x118e52  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e57  ldstr    aXmlssOfficeXsd// "xmlss_office.xsd"
0x118e5c  call     string [mscorlib]System.String::Concat(string, string)
0x118e61  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118e66  pop
0x118e67  ldloc.0
0x118e68  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118e6d  ldnull
0x118e6e  ldarg.0
0x118e6f  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e74  ldstr    aXmlssRowsetsch// "xmlss_rowsetschema.xsd"
0x118e79  call     string [mscorlib]System.String::Concat(string, string)
0x118e7e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118e83  pop
0x118e84  ldloc.0
0x118e85  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118e8a  ldnull
0x118e8b  ldarg.0
0x118e8c  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118e91  ldstr    aXmlssRowssetXs// "xmlss_rowsset.xsd"
0x118e96  call     string [mscorlib]System.String::Concat(string, string)
0x118e9b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118ea0  pop
0x118ea1  ldloc.0
0x118ea2  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118ea7  ldnull
0x118ea8  ldarg.0
0x118ea9  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118eae  ldstr    aXmlssSchemaXsd// "xmlss_schema.xsd"
0x118eb3  call     string [mscorlib]System.String::Concat(string, string)
0x118eb8  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118ebd  pop
0x118ebe  ldloc.0
0x118ebf  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118ec4  ldnull
0x118ec5  ldarg.0
0x118ec6  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118ecb  ldstr    aXmlssUdcXsd// "xmlss_udc.xsd"
0x118ed0  call     string [mscorlib]System.String::Concat(string, string)
0x118ed5  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118eda  pop
0x118edb  ldloc.0
0x118edc  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118ee1  ldnull
0x118ee2  ldarg.0
0x118ee3  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118ee8  ldstr    aXmlssUdcsoapXs// "xmlss_udcsoap.xsd"
0x118eed  call     string [mscorlib]System.String::Concat(string, string)
0x118ef2  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118ef7  pop
0x118ef8  ldloc.0
0x118ef9  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118efe  ldnull
0x118eff  ldarg.0
0x118f00  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118f05  ldstr    aXmlssUdcxmlfil// "xmlss_udcxmlfile.xsd"
0x118f0a  call     string [mscorlib]System.String::Concat(string, string)
0x118f0f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118f14  pop
0x118f15  ldloc.0
0x118f16  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118f1b  ldnull
0x118f1c  ldarg.0
0x118f1d  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118f22  ldstr    aXmlssVmlXsd// "xmlss_vml.xsd"
0x118f27  call     string [mscorlib]System.String::Concat(string, string)
0x118f2c  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118f31  pop
0x118f32  ldloc.0
0x118f33  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118f38  ldnull
0x118f39  ldarg.0
0x118f3a  ldfld    string Microsoft.Crm.ObjectModel.ImportFileService::pathToXsd
0x118f3f  ldstr    aSoapenvolopeXs// "soapenvolope.xsd"
0x118f44  call     string [mscorlib]System.String::Concat(string, string)
0x118f49  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118f4e  pop
0x118f4f  br       loc_119122
0x118f54  ldloc.0
0x118f55  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118f5a  ldnull
0x118f5b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x118f60  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x118f65  ldstr    aResourcesXmlss// "/_resources/xmlss_c.xsd"
0x118f6a  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x118f6f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118f74  pop
0x118f75  ldloc.0
0x118f76  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118f7b  ldnull
0x118f7c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x118f81  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x118f86  ldstr    aResourcesXmlss_0// "/_resources/xmlss_dt.xsd"
0x118f8b  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x118f90  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118f95  pop
0x118f96  ldloc.0
0x118f97  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118f9c  ldnull
0x118f9d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x118fa2  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x118fa7  ldstr    aResourcesXmlss_1// "/_resources/xmlss_excel.xsd"
0x118fac  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x118fb1  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118fb6  pop
0x118fb7  ldloc.0
0x118fb8  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118fbd  ldnull
0x118fbe  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x118fc3  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x118fc8  ldstr    aResourcesXmlss_2// "/_resources/xmlss_excel2003xml.xsd"
0x118fcd  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x118fd2  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118fd7  pop
0x118fd8  ldloc.0
0x118fd9  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118fde  ldnull
0x118fdf  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x118fe4  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x118fe9  ldstr    aResourcesXmlss_3// "/_resources/xmlss_excelss.xsd"
0x118fee  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x118ff3  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x118ff8  pop
0x118ff9  ldloc.0
0x118ffa  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x118fff  ldnull
0x119000  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119005  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x11900a  ldstr    aResourcesXmlss_4// "/_resources/xmlss_office.xsd"
0x11900f  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x119014  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x119019  pop
0x11901a  ldloc.0
0x11901b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x119020  ldnull
0x119021  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119026  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x11902b  ldstr    aResourcesXmlss_5// "/_resources/xmlss_rowsetschema.xsd"
0x119030  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x119035  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x11903a  pop
0x11903b  ldloc.0
0x11903c  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x119041  ldnull
0x119042  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119047  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x11904c  ldstr    aResourcesXmlss_6// "/_resources/xmlss_rowsset.xsd"
0x119051  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x119056  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x11905b  pop
0x11905c  ldloc.0
0x11905d  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x119062  ldnull
0x119063  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119068  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x11906d  ldstr    aResourcesXmlss_7// "/_resources/xmlss_schema.xsd"
0x119072  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x119077  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x11907c  pop
0x11907d  ldloc.0
0x11907e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x119083  ldnull
0x119084  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x119089  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x11908e  ldstr    aResourcesXmlss_8// "/_resources/xmlss_udc.xsd"
0x119093  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x119098  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x11909d  pop
0x11909e  ldloc.0
0x11909f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x1190a4  ldnull
0x1190a5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1190aa  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1190af  ldstr    aResourcesXmlss_9// "/_resources/xmlss_udcsoap.xsd"
0x1190b4  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1190b9  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x1190be  pop
0x1190bf  ldloc.0
0x1190c0  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x1190c5  ldnull
0x1190c6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1190cb  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1190d0  ldstr    aResourcesXmlss_10// "/_resources/xmlss_udcxmlfile.xsd"
0x1190d5  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1190da  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x1190df  pop
0x1190e0  ldloc.0
0x1190e1  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x1190e6  ldnull
0x1190e7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1190ec  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1190f1  ldstr    aResourcesXmlss_11// "/_resources/xmlss_vml.xsd"
0x1190f6  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1190fb  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x119100  pop
0x119101  ldloc.0
0x119102  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x119107  ldnull
0x119108  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x11910d  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x119112  ldstr    aResourcesSoape// "/_resources/soapenvolope.xsd"
0x119117  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x11911c  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x119121  pop
0x119122  ldloc.0
0x119123  ldc.i4.4
0x119124  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0x119129  ldloc.0
0x11912a  ldnull
0x11912b  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x119130  ldloc.0
0x119131  ldc.i4.1
0x119132  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0x119137  ldarg.1
0x119138  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x11913d  ldloc.0
0x11913e  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x119143  stloc.1
0x119144  ldc.i4.1
0x119145  stloc.2
0x119146  ldloc.1
0x119147  ldstr    aWorkbook// "Workbook"
0x11914c  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:spread"...
0x119151  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement(string, string)
0x119156  ldloc.1
0x119157  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x11915c  brtrue.s loc_119156
0x11915e  leave    loc_11922F
0x119163  stloc.3
0x119164  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x119169  ldstr    a01_18// "{0}|{1}|"
0x11916e  ldc.i4.2
0x11916f  newarr   [mscorlib]System.Object
0x119174  dup
0x119175  ldc.i4.0
0x119176  ldloc.3
0x119177  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaException::get_LineNumber()
0x11917c  box      [mscorlib]System.Int32
0x119181  stelem.ref
  ... truncated ...
```
