# Microsoft.Crm.CrmTraceSettings::LoadSiteWideSettings

- ea: `0x21190`
- end: `0x21309`
- name: `Microsoft.Crm.CrmTraceSettings::LoadSiteWideSettings`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21000`

## callees

- `0x1840`
- `0x4640`
- `0x1be80`
- `0x20ba0`
- `0x20bb0`
- `0x20bd0`
- `0x20c10`
- `0x20c30`
- `0x20c50`
- `0x20ce0`
- `0x20cf0`
- `0x20dc0`
- `0x21190`
- `0x221b0`
- `0x340b0`

## string_xrefs

- `0x211eb`: `TraceDirectory`
- `0x2119d`: `LocatorService.Instance`

## pseudocode

```c

```

## disassembly

```asm
0x21190  call     bool Microsoft.Crm.RegControl::IsInSandboxServerContext()
0x21195  brfalse.s loc_21198
0x21197  ret
0x21198  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x2119d  ldstr    aLocatorservice_2// "LocatorService.Instance"
0x211a2  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x211a7  newobj   instance void Microsoft.Crm.CrmTraceSettings::.ctor()
0x211ac  stloc.0
0x211ad  ldloc.0
0x211ae  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x211b3  ldstr    aTraceenabled// "TraceEnabled"
0x211b8  ldc.i4.0
0x211b9  callvirt T0x2B00005D
0x211be  brfalse.s loc_211C3
0x211c0  ldc.i4.2
0x211c1  br.s     loc_211C4
0x211c3  ldc.i4.1
0x211c4  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_IsTracingOff(valuetype TraceBool value)
0x211c9  ldloc.0
0x211ca  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x211cf  ldstr    aTracecallstack// "TraceCallStack"
0x211d4  ldc.i4.0
0x211d5  callvirt T0x2B00005D
0x211da  brtrue.s loc_211DF
0x211dc  ldc.i4.2
0x211dd  br.s     loc_211E0
0x211df  ldc.i4.1
0x211e0  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TracingCallStack(valuetype TraceBool value)
0x211e5  ldloc.0
0x211e6  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x211eb  ldstr    aTracedirectory// "TraceDirectory"
0x211f0  ldc.i4.0
0x211f1  callvirt T0x2B000034
0x211f6  callvirt instance string [mscorlib]System.String::Trim()
0x211fb  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceDirectory(string value)
0x21200  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x21205  ldstr    aTracebypassorg// "TraceBypassOrganizations"
0x2120a  ldc.i4.0
0x2120b  callvirt T0x2B000034
0x21210  stloc.2
0x21211  ldloc.2
0x21212  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21217  brtrue.s loc_21257
0x21219  ldloc.2
0x2121a  ldc.i4.1
0x2121b  newarr   [mscorlib]System.Char
0x21220  dup
0x21221  ldc.i4.0
0x21222  ldc.i4.s 0x2C
0x21224  stelem.i2
0x21225  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2122a  stloc.3
0x2122b  ldc.i4.0
0x2122c  stloc.s  4
0x2122e  br.s     loc_21250
0x21230  ldloc.3
0x21231  ldloc.s  4
0x21233  ldelem.ref
0x21234  ldloca.s 5
0x21236  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2123b  brfalse.s loc_2124A
0x2123d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.CrmTrace::TraceBypassOrganizations
0x21242  ldloc.s  5
0x21244  ldc.i4.1
0x21245  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::set_Item(var<u1>, !!T0)
0x2124a  ldloc.s  4
0x2124c  ldc.i4.1
0x2124d  add
0x2124e  stloc.s  4
0x21250  ldloc.s  4
0x21252  ldloc.3
0x21253  ldlen
0x21254  conv.i4
0x21255  blt.s    loc_21230
0x21257  leave.s  loc_2125C
0x21259  pop
0x2125a  leave.s  loc_2125C
0x2125c  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x21261  ldstr    aTracecategorie// "TraceCategories"
0x21266  ldc.i4.0
0x21267  callvirt T0x2B000034
0x2126c  callvirt instance string [mscorlib]System.String::Trim()
0x21271  stloc.1
0x21272  ldloc.1
0x21273  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21278  brfalse.s loc_21283
0x2127a  ldloc.0
0x2127b  ldnull
0x2127c  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x21281  br.s     loc_212A7
0x21283  ldloc.0
0x21284  ldloc.1
0x21285  call     class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::GenerateTraceCategories(string traceCategoriesUnsplit)
0x2128a  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x2128f  ldloc.0
0x21290  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::get_TraceCategoryLevels()
0x21295  brtrue.s loc_212A7
0x21297  ldloc.0
0x21298  ldstr    aError_0// "*:Error"
0x2129d  call     class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::GenerateTraceCategories(string traceCategoriesUnsplit)
0x212a2  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x212a7  ldloc.0
0x212a8  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x212ad  ldstr    aTracefilesize// "TraceFileSize"
0x212b2  ldc.i4.0
0x212b3  callvirt T0x2B000038
0x212b8  ldc.i4   0x100000
0x212bd  mul
0x212be  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceFileSize(int32 value)
0x212c3  ldloc.0
0x212c4  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x212c9  ldstr    aTracerefresh// "TraceRefresh"
0x212ce  ldc.i4.0
0x212cf  callvirt T0x2B000038
0x212d4  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_RefreshTraceInt(int32 value)
0x212d9  ldloc.0
0x212da  brfalse.s loc_212FC
0x212dc  ldsfld   class Microsoft.Crm.CrmTraceSettings Microsoft.Crm.CrmTraceSettings::_siteWideSettings
0x212e1  brfalse.s loc_212FC
0x212e3  ldsfld   class Microsoft.Crm.CrmTraceSettings Microsoft.Crm.CrmTraceSettings::_siteWideSettings
0x212e8  callvirt instance int32 Microsoft.Crm.CrmTraceSettings::get_RefreshTraceInt()
0x212ed  ldloc.0
0x212ee  callvirt instance int32 Microsoft.Crm.CrmTraceSettings::get_RefreshTraceInt()
0x212f3  bne.un.s loc_212FC
0x212f5  ldloc.0
0x212f6  ldc.i4.m1
0x212f7  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_RefreshTraceInt(int32 value)
0x212fc  ldsflda  class Microsoft.Crm.CrmTraceSettings Microsoft.Crm.CrmTraceSettings::_siteWideSettings
0x21301  ldloc.0
0x21302  call     T0x2B00005E
0x21307  pop
0x21308  ret
```
