# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::CreateAggregateTokenResolver

- ea: `0xa740`
- end: `0xa845`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::CreateAggregateTokenResolver`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0x7670`
- `0xa740`

## string_xrefs

- `0xa740`: `CreateAggregateTokenResolver - Loading encryption certificates:\n`

## pseudocode

```c

```

## disassembly

```asm
0xa740  ldstr    aCreateaggregat// "CreateAggregateTokenResolver - Loading "...
0xa745  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xa74a  stloc.0
0xa74b  ldloc.0
0xa74c  ldstr    aHost0// "Host: {0}\n"
0xa751  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa756  call     string [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::CurrentHost(class [System.Web]System.Web.HttpContext)
0xa75b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa760  pop
0xa761  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>::.ctor()
0xa766  stloc.1
0xa767  ldarg.0
0xa768  brfalse  loc_A822
0xa76d  ldarg.0
0xa76e  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xa773  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken>::.ctor(int32)
0xa778  stloc.2
0xa779  ldarg.0
0xa77a  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Enumerator [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::GetEnumerator()
0xa77f  stloc.3
0xa780  br.s     loc_A7F5
0xa782  ldloc.3
0xa783  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System]System.Security.Cryptography.X509Certificates.X509Certificate2Enumerator::get_Current()
0xa788  stloc.s  4
0xa78a  ldloc.2
0xa78b  ldloc.s  4
0xa78d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xa792  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken>::Add(var<u1>)
0xa797  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0xa79c  stloc.s  5
0xa79e  ldloc.0
0xa79f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7a4  ldstr    aSubject0Thumbp// "Subject: {0}, Thumbprint: {1}, Valid On"...
0xa7a9  ldc.i4.4
0xa7aa  newarr   [mscorlib]System.Object
0xa7af  dup
0xa7b0  ldc.i4.0
0xa7b1  ldloc.s  4
0xa7b3  callvirt instance string [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Subject()
0xa7b8  stelem.ref
0xa7b9  dup
0xa7ba  ldc.i4.1
0xa7bb  ldloc.s  4
0xa7bd  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0xa7c2  stelem.ref
0xa7c3  dup
0xa7c4  ldc.i4.2
0xa7c5  ldloc.s  4
0xa7c7  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotBefore()
0xa7cc  box      [mscorlib]System.DateTime
0xa7d1  stelem.ref
0xa7d2  dup
0xa7d3  ldc.i4.3
0xa7d4  ldloc.s  4
0xa7d6  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0xa7db  box      [mscorlib]System.DateTime
0xa7e0  stelem.ref
0xa7e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xa7e6  pop
0xa7e7  leave.s  loc_A7F5
0xa7e9  ldloc.s  5
0xa7eb  brfalse.s loc_A7F4
0xa7ed  ldloc.s  5
0xa7ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7f4  endfinally
0xa7f5  ldloc.3
0xa7f6  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Certificate2Enumerator::MoveNext()
0xa7fb  brtrue.s loc_A782
0xa7fd  ldc.i4.8
0xa7fe  ldc.i4   0x4000433A
0xa803  conv.i8
0xa804  ldloc.0
0xa805  callvirt instance string [mscorlib]System.Object::ToString()
0xa80a  ldnull
0xa80b  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xa810  ldloc.1
0xa811  ldloc.2
0xa812  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken>::AsReadOnly()
0xa817  ldc.i4.0
0xa818  call     class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver::CreateDefaultSecurityTokenResolver(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken>, bool)
0xa81d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>::Add(var<u1>)
0xa822  ldloc.1
0xa823  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>::get_Count()
0xa828  ldc.i4.1
0xa829  bne.un.s loc_A833
0xa82b  ldloc.1
0xa82c  ldc.i4.0
0xa82d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>::get_Item(!!T0)
0xa832  ret
0xa833  ldloc.1
0xa834  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>::get_Count()
0xa839  ldc.i4.1
0xa83a  ble.s    loc_A843
0xa83c  ldloc.1
0xa83d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.AggregateTokenResolver::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>)
0xa842  ret
0xa843  ldnull
0xa844  ret
```
