# Microsoft.Crm.EndUserNotification.SlugService::.cctor

- ea: `0x7fc0`
- end: `0x804b`
- name: `Microsoft.Crm.EndUserNotification.SlugService::.cctor`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8012`: `LEGAL_LINK`
- `0x801b`: `PRIVACY_LINK`
- `0x8024`: `CONTACTUS_LINK`
- `0x802d`: `LEARN_MORE_LINK`

## pseudocode

```c

```

## disassembly

```asm
0x7fc0  ldc.i4.s 0xF
0x7fc2  newarr   [mscorlib]System.String
0x7fc7  dup
0x7fc8  ldc.i4.0
0x7fc9  ldstr    aLiveProductNam// "LIVE_PRODUCT_NAME"
0x7fce  stelem.ref
0x7fcf  dup
0x7fd0  ldc.i4.1
0x7fd1  ldstr    aOutlookProduct// "OUTLOOK_PRODUCT_NAME"
0x7fd6  stelem.ref
0x7fd7  dup
0x7fd8  ldc.i4.2
0x7fd9  ldstr    aOrganizationNa// "ORGANIZATION_NAME"
0x7fde  stelem.ref
0x7fdf  dup
0x7fe0  ldc.i4.3
0x7fe1  ldstr    aOrganizationUr// "ORGANIZATION_URL"
0x7fe6  stelem.ref
0x7fe7  dup
0x7fe8  ldc.i4.4
0x7fe9  ldstr    aUserFirstName// "USER_FIRST_NAME"
0x7fee  stelem.ref
0x7fef  dup
0x7ff0  ldc.i4.5
0x7ff1  ldstr    aUserLastName// "USER_LAST_NAME"
0x7ff6  stelem.ref
0x7ff7  dup
0x7ff8  ldc.i4.6
0x7ff9  ldstr    aUserWlid// "USER_WLID"
0x7ffe  stelem.ref
0x7fff  dup
0x8000  ldc.i4.7
0x8001  ldstr    aLiveHomePage// "LIVE_HOME_PAGE"
0x8006  stelem.ref
0x8007  dup
0x8008  ldc.i4.8
0x8009  ldstr    aImageRoot// "IMAGE_ROOT"
0x800e  stelem.ref
0x800f  dup
0x8010  ldc.i4.s 9
0x8012  ldstr    aLegalLink// "LEGAL_LINK"
0x8017  stelem.ref
0x8018  dup
0x8019  ldc.i4.s 0xA
0x801b  ldstr    aPrivacyLink// "PRIVACY_LINK"
0x8020  stelem.ref
0x8021  dup
0x8022  ldc.i4.s 0xB
0x8024  ldstr    aContactusLink// "CONTACTUS_LINK"
0x8029  stelem.ref
0x802a  dup
0x802b  ldc.i4.s 0xC
0x802d  ldstr    aLearnMoreLink// "LEARN_MORE_LINK"
0x8032  stelem.ref
0x8033  dup
0x8034  ldc.i4.s 0xD
0x8036  ldstr    aNumHours// "NUM_HOURS"
0x803b  stelem.ref
0x803c  dup
0x803d  ldc.i4.s 0xE
0x803f  ldstr    aThresholdStati// "THRESHOLD_STATIC_PARAM"
0x8044  stelem.ref
0x8045  stsfld   string[] Microsoft.Crm.EndUserNotification.SlugService::SystemSlugs
0x804a  ret
```
