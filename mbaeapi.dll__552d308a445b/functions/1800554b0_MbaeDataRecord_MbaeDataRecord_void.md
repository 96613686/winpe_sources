# MbaeDataRecord::MbaeDataRecord(void)

- ea: `0x1800554b0`
- end: `0x180055845`
- name: `??0MbaeDataRecord@@IEAA@XZ`
- size: `917`
- prototype: `MbaeDataRecord *__fastcall(MbaeDataRecord *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055154`

## callees

- `0x180055448`
- `0x1800554b0`

## string_xrefs

- `0x1800556b1`: `CompanionAppId`
- `0x1800556bc`: `CompanionAppPackageFamilyName`
- `0x180055670`: `ServiceProviderGuid`
- `0x180055697`: `ServiceProviderIconPath`
- `0x180055685`: `ServiceProviderFriendlyName`
- `0x1800556dc`: `CompletedTasks`
- `0x1800556f2`: `V:MbnPurchaseProfileTemplatePath`
- `0x1800557e6`: `ServiceProviderType`
- `0x18005570f`: `V:MbnInternetProfileTemplatePath`

## pseudocode

```c
MbaeDataRecord *__fastcall MbaeDataRecord::MbaeDataRecord(MbaeDataRecord *this)
{
  MbaeDataRecord *v1; // r13
  char *v2; // rax
  char *v3; // rdx
  char *v4; // r8
  char *v5; // r9
  char *v6; // r10
  char *v7; // r12
  char *v8; // r11
  char *v9; // rcx
  _QWORD *v10; // rdi
  _QWORD *v11; // rsi
  _QWORD *v12; // r15
  _QWORD *v13; // rbp

  v1 = this;
  *(_QWORD *)this = 0;
  v2 = (char *)this + 152;
  *((_QWORD *)this + 1) = 0;
  v3 = (char *)this + 192;
  *((_QWORD *)this + 2) = (char *)this + 152;
  v4 = (char *)this + 232;
  *((_QWORD *)this + 3) = (char *)this + 192;
  v5 = (char *)this + 272;
  *((_QWORD *)this + 4) = (char *)this + 232;
  v6 = (char *)this + 312;
  *((_QWORD *)this + 5) = (char *)this + 272;
  v7 = (char *)this + 704;
  *((_QWORD *)this + 6) = (char *)this + 312;
  *((_QWORD *)this + 15) = (char *)this + 704;
  v8 = (char *)this + 400;
  v9 = (char *)this + 352;
  *((_QWORD *)v1 + 8) = v8;
  *((_QWORD *)v1 + 7) = v9;
  v10 = (_QWORD *)((char *)v1 + 480);
  *((_QWORD *)v1 + 9) = (char *)v1 + 440;
  v11 = (_QWORD *)((char *)v1 + 520);
  *((_QWORD *)v1 + 10) = (char *)v1 + 480;
  *((_QWORD *)v1 + 11) = (char *)v1 + 520;
  v12 = (_QWORD *)((char *)v1 + 640);
  *((_QWORD *)v1 + 12) = (char *)v1 + 560;
  v13 = (_QWORD *)((char *)v1 + 672);
  *((_QWORD *)v1 + 13) = (char *)v1 + 640;
  *((_QWORD *)v1 + 14) = (char *)v1 + 672;
  *((_QWORD *)this + 16) = (char *)v1 + 744;
  *((_QWORD *)this + 17) = (char *)this + 784;
  *((_QWORD *)this + 18) = 0;
  *((_WORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 4) = L"EncryptedSubscriberId";
  *(_QWORD *)v2 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedStringProperty>::`vftable';
  v2[10] = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v3 + 4) = L"EncryptedSimIccId";
  *((_QWORD *)v4 + 4) = L"EncryptedCurrentMobileEquipmentId";
  *((_QWORD *)v5 + 4) = L"CurrentNetworkDeviceId";
  *((_WORD *)v3 + 4) = 0;
  v3[10] = 0;
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 3) = 0;
  *(_QWORD *)v3 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedStringProperty>::`vftable';
  *((_QWORD *)v6 + 4) = L"MetadataPackageId";
  *((_WORD *)v4 + 4) = 0;
  v4[10] = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *(_QWORD *)v4 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedStringProperty>::`vftable';
  *((_WORD *)v5 + 4) = 0;
  v5[10] = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *(_QWORD *)v5 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable';
  *((_WORD *)v6 + 4) = 0;
  v6[10] = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *(_QWORD *)v6 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable';
  *((_WORD *)v9 + 4) = 0;
  v9[10] = 0;
  *(_QWORD *)(v9 + 28) = 0;
  *((_QWORD *)v9 + 5) = L"ServiceProviderGuid";
  *(_QWORD *)v9 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::ValueTypeProperty<_GUID>>::`vftable';
  *((_QWORD *)v8 + 4) = L"ServiceProviderFriendlyName";
  *((_WORD *)v1 + 224) = 0;
  *((_QWORD *)v1 + 59) = L"ServiceProviderIconPath";
  *((_QWORD *)v1 + 55) = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::MetadataCachePathProperty>::`vftable';
  *((_QWORD *)v1 + 64) = L"CompanionAppId";
  *((_QWORD *)v1 + 69) = L"CompanionAppPackageFamilyName";
  *((_QWORD *)v1 + 75) = L"AppsAccountIsVisibleTo";
  *((_QWORD *)v1 + 70) = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringCollectionProperty>::`vftable';
  *((_QWORD *)v1 + 83) = L"CompletedTasks";
  *((_QWORD *)v1 + 87) = L"AllowStandardUserPinUnlock";
  *((_BYTE *)v1 + 450) = 0;
  *((_QWORD *)v1 + 57) = 0;
  *((_QWORD *)v1 + 58) = 0;
  *((_QWORD *)v7 + 4) = L"V:MbnPurchaseProfileTemplatePath";
  *((_WORD *)v8 + 4) = 0;
  v8[10] = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *((_WORD *)v1 + 244) = 0;
  *((_BYTE *)v1 + 490) = 0;
  *((_QWORD *)v1 + 62) = 0;
  *((_QWORD *)v1 + 63) = 0;
  *((_WORD *)v1 + 264) = 0;
  *((_BYTE *)v1 + 530) = 0;
  *((_QWORD *)v1 + 67) = 0;
  *((_QWORD *)v1 + 68) = 0;
  *((_WORD *)v1 + 284) = 0;
  *((_BYTE *)v1 + 570) = 0;
  *((_QWORD *)v1 + 72) = 0;
  *((_QWORD *)v1 + 73) = 0;
  *((_QWORD *)v1 + 74) = 0;
  *((_QWORD *)v1 + 76) = 0;
  *((_QWORD *)v1 + 77) = 0;
  *((_QWORD *)v1 + 78) = 0;
  *((_DWORD *)v1 + 158) = 0;
  *((_WORD *)v1 + 324) = 0;
  *((_BYTE *)v1 + 650) = 0;
  *((_QWORD *)v1 + 82) = 0;
  *((_WORD *)v1 + 340) = 0;
  *((_BYTE *)v1 + 682) = 0;
  *((_QWORD *)v1 + 86) = 0;
  *((_WORD *)v7 + 4) = 0;
  v7[10] = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  v1 = (MbaeDataRecord *)((char *)v1 + 744);
  *(_QWORD *)v8 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable';
  *v10 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable';
  *v11 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable';
  *((_QWORD *)v1 + 4) = L"V:MbnInternetProfileTemplatePath";
  *v12 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::ValueTypeProperty<unsigned long>>::`vftable';
  *v13 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::ValueTypeProperty<unsigned long>>::`vftable';
  *((_WORD *)this + 396) = 0;
  *((_BYTE *)this + 794) = 0;
  *(_QWORD *)v7 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::VolatileStringProperty>::`vftable';
  *((_WORD *)v1 + 4) = 0;
  *((_BYTE *)v1 + 10) = 0;
  *((_QWORD *)v1 + 2) = 0;
  *((_QWORD *)v1 + 3) = 0;
  *(_QWORD *)v1 = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::VolatileStringProperty>::`vftable';
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = L"ServiceProviderType";
  *((_QWORD *)this + 98) = &PersistablePropertyBag<HKEY__ *,unsigned short const *>::AdminView<RegistryPropertyBag::EncryptedDwordProperty>::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids);
  return this;
}

```

## disassembly

```asm
0x1800554b0  mov     [rsp+arg_18], rbx
0x1800554b5  mov     [rsp+arg_0], rcx
0x1800554ba  push    rbp
0x1800554bb  push    rsi
0x1800554bc  push    rdi
0x1800554bd  push    r12
0x1800554bf  push    r13
0x1800554c1  push    r14
0x1800554c3  push    r15
0x1800554c5  sub     rsp, 20h
0x1800554c9  mov     r13, rcx
0x1800554cc  mov     qword ptr [rcx], 0
0x1800554d3  lea     rax, [rcx+98h]
0x1800554da  mov     qword ptr [rcx+8], 0
0x1800554e2  lea     rdx, [rcx+0C0h]
0x1800554e9  mov     [rcx+10h], rax
0x1800554ed  lea     r8, [rcx+0E8h]
0x1800554f4  mov     [rcx+18h], rdx
0x1800554f8  lea     r9, [rcx+110h]
0x1800554ff  mov     [rcx+20h], r8
0x180055503  lea     r10, [rcx+138h]
0x18005550a  mov     [rcx+28h], r9
0x18005550e  lea     r12, [r13+2C0h]
0x180055515  mov     [rcx+30h], r10
0x180055519  mov     [r13+78h], r12
0x18005551d  lea     r11, [r13+190h]
0x180055524  add     rcx, 160h
0x18005552b  mov     [r13+40h], r11
0x18005552f  lea     rbx, [r13+1B8h]
0x180055536  mov     [r13+38h], rcx
0x18005553a  lea     rdi, [r13+1E0h]
0x180055541  mov     [r13+48h], rbx
0x180055545  lea     rsi, [r13+208h]
0x18005554c  mov     [r13+50h], rdi
0x180055550  lea     r14, [r13+230h]
0x180055557  mov     [r13+58h], rsi
0x18005555b  lea     r15, [r13+280h]
0x180055562  mov     [r13+60h], r14
0x180055566  lea     rbp, [r13+2A0h]
0x18005556d  mov     [r13+68h], r15
0x180055571  mov     [r13+70h], rbp
0x180055575  add     r13, 2E8h
0x18005557c  mov     [rsp+58h+arg_8], r12
0x180055581  mov     r12, [rsp+58h+arg_0]
0x180055586  mov     [rsp+58h+arg_10], r13
0x18005558b  mov     [r12+80h], r13
0x180055593  lea     r13, [r12+310h]
0x18005559b  mov     [r12+88h], r13
0x1800555a3  mov     r13, r12
0x1800555a6  xor     r13d, r13d
0x1800555a9  mov     qword ptr [r12+90h], 0
0x1800555b5  mov     [rax+8], r13w
0x1800555ba  lea     r12, aEncryptedsubsc; "EncryptedSubscriberId"
0x1800555c1  mov     [rax+20h], r12
0x1800555c5  lea     r12, ??_7?$AdminView@VEncryptedStringProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::EncryptedStringProperty>::`vftable'
0x1800555cc  mov     [rax], r12
0x1800555cf  mov     [rax+0Ah], r13b
0x1800555d3  mov     [rax+10h], r13
0x1800555d7  mov     [rax+18h], r13
0x1800555db  lea     rax, aEncryptedsimic; "EncryptedSimIccId"
0x1800555e2  mov     [rdx+20h], rax
0x1800555e6  lea     rax, aEncryptedcurre; "EncryptedCurrentMobileEquipmentId"
0x1800555ed  mov     [r8+20h], rax
0x1800555f1  lea     rax, aCurrentnetwork; "CurrentNetworkDeviceId"
0x1800555f8  mov     [r9+20h], rax
0x1800555fc  lea     rax, aMetadatapackag; "MetadataPackageId"
0x180055603  mov     [rdx+8], r13w
0x180055608  mov     [rdx+0Ah], r13b
0x18005560c  mov     [rdx+10h], r13
0x180055610  mov     [rdx+18h], r13
0x180055614  mov     [rdx], r12
0x180055617  lea     rdx, ??_7?$AdminView@VStringProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::StringProperty>::`vftable'
0x18005561e  mov     [r10+20h], rax
0x180055622  mov     [r8+8], r13w
0x180055627  mov     [r8+0Ah], r13b
0x18005562b  mov     [r8+10h], r13
0x18005562f  mov     [r8+18h], r13
0x180055633  mov     [r8], r12
0x180055636  mov     [r9+8], r13w
0x18005563b  mov     [r9+0Ah], r13b
0x18005563f  mov     [r9+10h], r13
0x180055643  mov     [r9+18h], r13
0x180055647  mov     [r9], rdx
0x18005564a  mov     [r10+8], r13w
0x18005564f  mov     [r10+0Ah], r13b
0x180055653  mov     [r10+10h], r13
0x180055657  mov     [r10+18h], r13
0x18005565b  mov     [r10], rdx
0x18005565e  mov     [rcx+8], r13w
0x180055663  mov     [rcx+0Ah], r13b
0x180055667  mov     [rcx+1Ch], r13
0x18005566b  mov     r12, [rsp+58h+arg_8]
0x180055670  lea     rax, aServiceprovide_2; "ServiceProviderGuid"
0x180055677  mov     [rcx+28h], rax
0x18005567b  lea     rax, ??_7?$AdminView@V?$ValueTypeProperty@U_GUID@@@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::ValueTypeProperty<_GUID>>::`vftable'
0x180055682  mov     [rcx], rax
0x180055685  lea     rax, aServiceprovide_0; "ServiceProviderFriendlyName"
0x18005568c  mov     [r11+20h], rax
0x180055690  lea     rcx, ??_7?$AdminView@V?$ValueTypeProperty@K@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::ValueTypeProperty<ulong>>::`vftable'
0x180055697  lea     rax, aServiceprovide_1; "ServiceProviderIconPath"
0x18005569e  mov     [rbx+8], r13w
0x1800556a3  mov     [rbx+20h], rax
0x1800556a7  lea     rax, ??_7?$AdminView@VMetadataCachePathProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::MetadataCachePathProperty>::`vftable'
0x1800556ae  mov     [rbx], rax
0x1800556b1  lea     rax, aCompanionappid; "CompanionAppId"
0x1800556b8  mov     [rdi+20h], rax
0x1800556bc  lea     rax, aCompanionapppa; "CompanionAppPackageFamilyName"
0x1800556c3  mov     [rsi+20h], rax
0x1800556c7  lea     rax, aAppsaccountisv; "AppsAccountIsVisibleTo"
0x1800556ce  mov     [r14+28h], rax
0x1800556d2  lea     rax, ??_7?$AdminView@VStringCollectionProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::StringCollectionProperty>::`vftable'
0x1800556d9  mov     [r14], rax
0x1800556dc  lea     rax, aCompletedtasks; "CompletedTasks"
0x1800556e3  mov     [r15+18h], rax
0x1800556e7  lea     rax, aAllowstandardu; "AllowStandardUserPinUnlock"
0x1800556ee  mov     [rbp+18h], rax
0x1800556f2  lea     rax, aVMbnpurchasepr; "V:MbnPurchaseProfileTemplatePath"
0x1800556f9  mov     [rbx+0Ah], r13b
0x1800556fd  mov     [rbx+10h], r13
0x180055701  mov     [rbx+18h], r13
0x180055705  mov     rbx, [rsp+58h+arg_0]
0x18005570a  mov     [r12+20h], rax
0x18005570f  lea     rax, aVMbninternetpr; "V:MbnInternetProfileTemplatePath"
0x180055716  mov     [r11+8], r13w
0x18005571b  mov     [r11+0Ah], r13b
0x18005571f  mov     [r11+10h], r13
0x180055723  mov     [r11+18h], r13
0x180055727  mov     [rdi+8], r13w
0x18005572c  mov     [rdi+0Ah], r13b
0x180055730  mov     [rdi+10h], r13
0x180055734  mov     [rdi+18h], r13
0x180055738  mov     [rsi+8], r13w
0x18005573d  mov     [rsi+0Ah], r13b
0x180055741  mov     [rsi+10h], r13
0x180055745  mov     [rsi+18h], r13
0x180055749  mov     [r14+8], r13w
0x18005574e  mov     [r14+0Ah], r13b
0x180055752  mov     [r14+10h], r13
0x180055756  mov     [r14+18h], r13
0x18005575a  mov     [r14+20h], r13
0x18005575e  mov     [r14+30h], r13
0x180055762  mov     [r14+38h], r13
0x180055766  mov     [r14+40h], r13
0x18005576a  mov     [r14+48h], r13d
0x18005576e  mov     [r15+8], r13w
0x180055773  mov     [r15+0Ah], r13b
0x180055777  mov     [r15+10h], r13
0x18005577b  mov     [rbp+8], r13w
0x180055780  mov     [rbp+0Ah], r13b
0x180055784  mov     [rbp+10h], r13
0x180055788  mov     [r12+8], r13w
0x18005578e  mov     [r12+0Ah], r13b
0x180055793  mov     [r12+10h], r13
0x180055798  mov     [r12+18h], r13
0x18005579d  mov     r13, [rsp+58h+arg_10]
0x1800557a2  mov     [r11], rdx
0x1800557a5  mov     [rdi], rdx
0x1800557a8  mov     [rsi], rdx
0x1800557ab  xor     edx, edx
0x1800557ad  mov     [r13+20h], rax
0x1800557b1  lea     rax, [rbx+310h]
0x1800557b8  mov     [r15], rcx
0x1800557bb  mov     [rbp+0], rcx
0x1800557bf  lea     rcx, ??_7?$AdminView@VVolatileStringProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::VolatileStringProperty>::`vftable'
0x1800557c6  mov     [rax+8], dx
0x1800557ca  mov     [rax+0Ah], dl
0x1800557cd  mov     [r12], rcx
0x1800557d1  mov     [r13+8], dx
0x1800557d6  mov     [r13+0Ah], dl
0x1800557da  mov     [r13+10h], rdx
0x1800557de  mov     [r13+18h], rdx
0x1800557e2  mov     [r13+0], rcx
0x1800557e6  lea     rcx, aServiceprovide; "ServiceProviderType"
0x1800557ed  mov     [rax+10h], rdx
0x1800557f1  mov     [rax+18h], rcx
0x1800557f5  lea     rcx, ??_7?$AdminView@VEncryptedDwordProperty@RegistryPropertyBag@@@?$PersistablePropertyBag@PEAUHKEY__@@PEBG@@6B@; const PersistablePropertyBag<HKEY__ *,ushort const *>::AdminView<RegistryPropertyBag::EncryptedDwordProperty>::`vftable'
0x1800557fc  mov     [rax], rcx
0x1800557ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180055806  lea     rax, WPP_GLOBAL_Control
0x18005580d  cmp     rcx, rax
0x180055810  jz      short loc_18005582D
0x180055812  test    byte ptr [rcx+1Ch], 10h
0x180055816  jz      short loc_18005582D
0x180055818  mov     rcx, [rcx+10h]
0x18005581c  lea     r8, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids
0x180055823  mov     edx, 0Ch
0x180055828  call    WPP_SF_
0x18005582d  mov     rax, rbx
0x180055830  mov     rbx, [rsp+58h+arg_18]
0x180055835  add     rsp, 20h
0x180055839  pop     r15
0x18005583b  pop     r14
0x18005583d  pop     r13
0x18005583f  pop     r12
0x180055841  pop     rdi
0x180055842  pop     rsi
0x180055843  pop     rbp
0x180055844  retn
```
