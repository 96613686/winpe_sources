# Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator::.ctor

- ea: `0x1a81f0`
- end: `0x1a8766`
- name: `Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator::.ctor`
- size: `1398`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16aa10`
- `0x1a97a0`

## callees

- `0x19d1a0`

## string_xrefs

- `0x1a83f7`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8411`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a842b`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8445`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a845f`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8479`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8493`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a84ad`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a84c7`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a84e1`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a84fb`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8515`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a852f`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8549`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8563`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a857d`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8597`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a85b1`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a85cb`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a85e5`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a85ff`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8619`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8633`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a864d`: `/_static/_common/scripts/commandbaractions.js`
- `0x1a8667`: `commandbaractions.js`
- `0x1a8681`: `commandbaractions.js`
- `0x1a869b`: `commandbaractions.js`
- `0x1a86b5`: `commandbaractions.js`
- `0x1a86cf`: `commandbaractions.js`

## pseudocode

```c

```

## disassembly

```asm
0x1a81f0  ldarg.0
0x1a81f1  ldarg.1
0x1a81f2  ldarg.2
0x1a81f3  call     instance void Microsoft.Crm.ObjectModel.DependencyCalculatorBase::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.IDependencyHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a81f8  ldarg.0
0x1a81f9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::.ctor()
0x1a81fe  dup
0x1a81ff  ldstr    aC49667d92ff44a// "C49667D9-2FF4-4A81-A6A1-562E25292E05"
0x1a8204  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8209  ldstr    aWebresourceEma// "$webresource:email_main_system_library."...
0x1a820e  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8213  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8218  dup
0x1a8219  ldstr    a33dc7981733a4e// "33DC7981-733A-4E09-B65F-E020559578E9"
0x1a821e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8223  ldstr    aWebresourceEma// "$webresource:email_main_system_library."...
0x1a8228  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a822d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8232  dup
0x1a8233  ldstr    a3b1f5aafAc0c4e// "3B1F5AAF-AC0C-4E0B-8827-9562524E4137"
0x1a8238  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a823d  ldstr    aWebresourceEma// "$webresource:email_main_system_library."...
0x1a8242  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8247  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a824c  dup
0x1a824d  ldstr    a97cb800dAa2d47// "97CB800D-AA2D-47F2-A142-A7F03B4AB72B"
0x1a8252  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8257  ldstr    aWebresourceInc// "$webresource:incident_main_system_libra"...
0x1a825c  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8261  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8266  dup
0x1a8267  ldstr    a5327e6cdF0714d// "5327E6CD-F071-4DA9-8221-BA34EBD93479"
0x1a826c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8271  ldstr    aWebresourceInc// "$webresource:incident_main_system_libra"...
0x1a8276  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a827b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8280  dup
0x1a8281  ldstr    a09f923e7Ebba44// "09F923E7-EBBA-4490-BF64-3186CEEF8AA9"
0x1a8286  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a828b  ldstr    aWebresourceInc// "$webresource:incident_main_system_libra"...
0x1a8290  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8295  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a829a  dup
0x1a829b  ldstr    a624265f0Cb144e// "624265F0-CB14-4EFF-8E41-EBC61C432E70"
0x1a82a0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a82a5  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a82aa  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a82af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a82b4  dup
0x1a82b5  ldstr    a4ed6c17705074f// "4ED6C177-0507-4FA3-A1E1-491FCD831069"
0x1a82ba  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a82bf  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a82c4  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a82c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a82ce  dup
0x1a82cf  ldstr    a5fe8e9b081714d// "5FE8E9B0-8171-4D56-A5D7-1783F231D475"
0x1a82d4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a82d9  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a82de  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a82e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a82e8  dup
0x1a82e9  ldstr    aCddb0610D12243// "CDDB0610-D122-43F4-800B-3FA564B5A7CA"
0x1a82ee  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a82f3  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a82f8  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a82fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8302  dup
0x1a8303  ldstr    a8fbbdb1dCcc548// "8FBBDB1D-CCC5-48B6-B595-5ACD4A878C70"
0x1a8308  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a830d  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a8312  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8317  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a831c  dup
0x1a831d  ldstr    a7f774485Dd064f// "7F774485-DD06-4FF1-8E92-7ED757F87532"
0x1a8322  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8327  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a832c  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8331  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8336  dup
0x1a8337  ldstr    aC495f6cd743043// "C495F6CD-7430-43C4-A1DF-3D8423FE23BA"
0x1a833c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8341  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a8346  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a834b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8350  dup
0x1a8351  ldstr    aF6642784Aee44b// "F6642784-AEE4-4B7F-9BE8-D1A76DBA926C"
0x1a8356  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a835b  ldstr    aWebresourceKno// "$webresource:knowledgearticle_main_syst"...
0x1a8360  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8365  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a836a  dup
0x1a836b  ldstr    a6551f23b82474f// "6551F23B-8247-4F1A-8B6E-3CCFB09075D2"
0x1a8370  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8375  ldstr    aWebresourceLea// "$webresource:lead_main_system_library.j"...
0x1a837a  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a837f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8384  dup
0x1a8385  ldstr    aC7bf0b82Ccf74b// "C7BF0B82-CCF7-4B32-88F5-1750D3B7C8BA"
0x1a838a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a838f  ldstr    aWebresourceOpp// "$webresource:opportunity_main_system_li"...
0x1a8394  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8399  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a839e  dup
0x1a839f  ldstr    aBa31bfafA7c348// "BA31BFAF-A7C3-4841-9CEA-2AB7C74ED6B9"
0x1a83a4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a83a9  ldstr    aWebresourceQue// "$webresource:queueitem_main_system_libr"...
0x1a83ae  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a83b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a83b8  dup
0x1a83b9  ldstr    a5551d483470743// "5551D483-4707-438F-9BBF-722F2AF9A670"
0x1a83be  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a83c3  ldstr    aWebresourceQue// "$webresource:queueitem_main_system_libr"...
0x1a83c8  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a83cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a83d2  dup
0x1a83d3  ldstr    aA3617c2cE07042// "A3617C2C-E070-427D-A080-56BEE66BC637"
0x1a83d8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a83dd  ldstr    aWebresourceSla// "$webresource:sla_main_system_library.js"
0x1a83e2  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a83e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a83ec  dup
0x1a83ed  ldstr    a32ef8c69C6934f// "32EF8C69-C693-4F80-B6AB-1D0780611260"
0x1a83f2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a83f7  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a83fc  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8401  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8406  dup
0x1a8407  ldstr    aF126402359764c// "F1264023-5976-4CE0-8A1C-3D485A4E468B"
0x1a840c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8411  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8416  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a841b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8420  dup
0x1a8421  ldstr    a467542c4663245// "467542C4-6632-4564-A2E7-B9ADD9FDF5E4"
0x1a8426  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a842b  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8430  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8435  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a843a  dup
0x1a843b  ldstr    aE2da280859124b// "E2DA2808-5912-4B2B-A68B-5F4552C0FF74"
0x1a8440  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8445  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a844a  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a844f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8454  dup
0x1a8455  ldstr    a2178dda76d844f// "2178DDA7-6D84-4F10-A245-61F724BF6110"
0x1a845a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a845f  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8464  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8469  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a846e  dup
0x1a846f  ldstr    a96a67849153a46// "96A67849-153A-461D-AECA-B95862B92887"
0x1a8474  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8479  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a847e  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8483  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8488  dup
0x1a8489  ldstr    aC3b052cd782541// "C3B052CD-7825-41DA-AB54-599245836D13"
0x1a848e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8493  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8498  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a849d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a84a2  dup
0x1a84a3  ldstr    aA5570bab2a1d4f// "A5570BAB-2A1D-4FDE-B7B0-762745833460"
0x1a84a8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a84ad  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a84b2  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a84b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a84bc  dup
0x1a84bd  ldstr    a5bf63d8b330c44// "5BF63D8B-330C-44FE-9FC0-BE5FF814EE96"
0x1a84c2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a84c7  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a84cc  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a84d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a84d6  dup
0x1a84d7  ldstr    a41ff0509900041// "41FF0509-9000-41D5-9777-A117D300119F"
0x1a84dc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a84e1  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a84e6  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a84eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a84f0  dup
0x1a84f1  ldstr    a2ae0a98c0d0d4e// "2AE0A98C-0D0D-4E0F-B565-16B03A15BE99"
0x1a84f6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a84fb  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8500  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8505  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a850a  dup
0x1a850b  ldstr    a6e0607e544c84f// "6E0607E5-44C8-4FCD-9C89-F5EFF1E07C32"
0x1a8510  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8515  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a851a  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a851f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8524  dup
0x1a8525  ldstr    a2178dda74f106d// "2178DDA7-4F10-6D84-A245-61F724BF6110"
0x1a852a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a852f  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8534  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8539  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a853e  dup
0x1a853f  ldstr    a8591b3da7f6545// "8591B3DA-7F65-451F-A059-68216C8D03D2"
0x1a8544  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8549  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a854e  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8553  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8558  dup
0x1a8559  ldstr    aB82a7bd4087640// "B82A7BD4-0876-4022-AEF2-74EE352139A7"
0x1a855e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8563  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8568  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a856d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8572  dup
0x1a8573  ldstr    aAba40418Ece211// "ABA40418-ECE2-11E5-9CE9-5E5517507C66"
0x1a8578  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a857d  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8582  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8587  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a858c  dup
0x1a858d  ldstr    a69e0c11eEcde11// "69E0C11E-ECDE-11E5-9CE9-5E5517507C66"
0x1a8592  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8597  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a859c  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a85a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a85a6  dup
0x1a85a7  ldstr    a63c30e33036b44// "63C30E33-036B-44F3-BC06-372378A68A9F"
0x1a85ac  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a85b1  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a85b6  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a85bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a85c0  dup
0x1a85c1  ldstr    a602fcc01Dd6248// "602FCC01-DD62-4886-8F07-042ED67AE299"
0x1a85c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a85cb  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a85d0  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a85d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a85da  dup
0x1a85db  ldstr    aB7c5f6a8514c48// "B7C5F6A8-514C-4810-B93E-E78EC3A2C6BD"
0x1a85e0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a85e5  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a85ea  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a85ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a85f4  dup
0x1a85f5  ldstr    a33dc7981733a4e// "33DC7981-733A-4E09-B65F-E020559578E9"
0x1a85fa  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a85ff  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8604  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8609  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a860e  dup
0x1a860f  ldstr    a3b1f5aafAc0c4e// "3B1F5AAF-AC0C-4E0B-8827-9562524E4137"
0x1a8614  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8619  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a861e  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8623  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8628  dup
0x1a8629  ldstr    aA3617c2cE07042// "A3617C2C-E070-427D-A080-56BEE66BC637"
0x1a862e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8633  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8638  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a863d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8642  dup
0x1a8643  ldstr    a34c15bd2087640// "34C15BD2-0876-4022-AEF2-74EE352139A7"
0x1a8648  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a864d  ldstr    aStaticCommonSc// "/_static/_common/scripts/commandbaracti"...
0x1a8652  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8657  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a865c  dup
0x1a865d  ldstr    a264b9b29F68642// "264B9B29-F686-42DF-984E-CFC008416B89"
0x1a8662  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8667  ldstr    aCommandbaracti// "commandbaractions.js"
0x1a866c  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a8671  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8676  dup
0x1a8677  ldstr    a0a66deff4b464e// "0A66DEFF-4B46-4EA6-8909-FF19CD389DC8"
0x1a867c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a8681  ldstr    aCommandbaracti// "commandbaractions.js"
0x1a8686  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a868b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a8690  dup
0x1a8691  ldstr    aFdf28843D6c744// "FDF28843-D6C7-44B0-8B88-3858257D6355"
0x1a8696  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a869b  ldstr    aCommandbaracti// "commandbaractions.js"
0x1a86a0  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a86a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a86aa  dup
0x1a86ab  ldstr    aBe79fdb6E66647// "BE79FDB6-E666-4731-8DB4-F58276EBBBFC"
0x1a86b0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a86b5  ldstr    aCommandbaracti// "commandbaractions.js"
0x1a86ba  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a86bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a86c4  dup
0x1a86c5  ldstr    a8900f84c652d4d// "8900F84C-652D-4D2E-9ECB-8F9769DC5F3E"
0x1a86ca  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a86cf  ldstr    aCommandbaracti// "commandbaractions.js"
0x1a86d4  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a86d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x1a86de  dup
0x1a86df  ldstr    a2701de608f2a48_0// "2701DE60-8F2A-48A4-8262-4A35CA7441FA"
0x1a86e4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a86e9  ldstr    aMsdynPersonalw// "msdyn_/personalwall.htm"
0x1a86ee  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::.ctor(var<u1>, !!T0)
0x1a86f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
  ... truncated ...
```
