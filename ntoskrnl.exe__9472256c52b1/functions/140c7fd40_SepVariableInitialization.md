# SepVariableInitialization

- ea: `0x140c7fd40`
- end: `0x140c81772`
- name: `SepVariableInitialization`
- size: `6706`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140c81944`

## callees

- `0x14046c370`
- `0x140634644`
- `0x1406877f8`
- `0x1406f7380`
- `0x1407cbe48`
- `0x1409e3990`
- `0x140a04560`
- `0x140c7f280`
- `0x140c7fd40`

## string_xrefs

- `0x140c7fd75`: `lpacCom`
- `0x140c7fd88`: `lpacCryptoServices`
- `0x140c7fd93`: `lpacIdentityServices`
- `0x140c7fe4b`: `lpacDeviceAccess`
- `0x140c7fdcd`: `registryRead`
- `0x140c7fddb`: `lpacServicesManagement`
- `0x140c7fea1`: `isolatedWin32-promptForAccess`
- `0x140c7feaf`: `isolatedWin32-accessToPublisherDirectory`
- `0x140c7fe6f`: `sessionImpersonation`
- `0x140c7fe7a`: `constrainedImpersonation`

## pseudocode

```c

```

## disassembly

```asm
0x140c7fd40  push    rbp
0x140c7fd42  push    rbx
0x140c7fd43  push    rsi
0x140c7fd44  push    rdi
0x140c7fd45  push    r12
0x140c7fd47  push    r13
0x140c7fd49  push    r14
0x140c7fd4b  push    r15
0x140c7fd4d  lea     rbp, [rsp-198h]
0x140c7fd55  sub     rsp, 298h
0x140c7fd5c  lea     rax, aLpacappexperie; "lpacAppExperience"
0x140c7fd63  mov     qword ptr [rbp+1D0h+String2.Length], 240022h
0x140c7fd6b  mov     [rbp+1D0h+String2.Buffer], rax
0x140c7fd6f  mov     r8d, 40h ; '@'
0x140c7fd75  lea     rax, aLpaccom; "lpacCom"
0x140c7fd7c  mov     qword ptr [rbp+1D0h+var_1A8.Length], 10000Eh
0x140c7fd84  mov     [rbp+1D0h+var_1A8.Buffer], rax
0x140c7fd88  lea     rax, aLpaccryptoserv; "lpacCryptoServices"
0x140c7fd8f  mov     [rbp+1D0h+var_198.Buffer], rax
0x140c7fd93  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x140c7fd9a  mov     [rbp+1D0h+var_188.Buffer], rax
0x140c7fd9e  lea     rax, aLpacinstrument_0; "lpacInstrumentation"
0x140c7fda5  mov     [rbp+1D0h+var_178.Buffer], rax
0x140c7fda9  lea     rax, aLpacenterprise; "lpacEnterprisePolicyChangeNotifications"
0x140c7fdb0  mov     [rbp+1D0h+var_168.Buffer], rax
0x140c7fdb4  lea     rax, aLpacmedia; "lpacMedia"
0x140c7fdbb  mov     [rbp+1D0h+var_1B8.Buffer], rax
0x140c7fdbf  lea     rax, aLpacpnpnotific; "lpacPnpNotifications"
0x140c7fdc6  mov     [rbp+1D0h+var_158.Buffer], rax
0x140c7fdcd  lea     rax, aRegistryread_0; "registryRead"
0x140c7fdd4  mov     [rbp+1D0h+var_148.Buffer], rax
0x140c7fddb  lea     rax, aLpacservicesma; "lpacServicesManagement"
0x140c7fde2  mov     [rbp+1D0h+var_138.Buffer], rax
0x140c7fde9  lea     rax, aLpacsessionman; "lpacSessionManagement"
0x140c7fdf0  mov     [rbp+1D0h+var_128.Buffer], rax
0x140c7fdf7  lea     rax, aLpacprinting; "lpacPrinting"
0x140c7fdfe  mov     [rbp+1D0h+var_118.Buffer], rax
0x140c7fe05  lea     rax, aLpacwebplatfor; "lpacWebPlatform"
0x140c7fe0c  mov     [rbp+1D0h+var_108.Buffer], rax
0x140c7fe13  lea     rax, aLpacpayments; "lpacPayments"
0x140c7fe1a  mov     [rbp+1D0h+var_F8.Buffer], rax
0x140c7fe21  lea     rax, aLpacclipboard; "lpacClipboard"
0x140c7fe28  mov     [rbp+1D0h+var_E8.Buffer], rax
0x140c7fe2f  lea     rax, aLpacime; "lpacIME"
0x140c7fe36  mov     [rbp+1D0h+var_D8.Buffer], rax
0x140c7fe3d  lea     rax, aLpacpackageman; "lpacPackageManagerOperation"
0x140c7fe44  mov     [rbp+1D0h+var_C8.Buffer], rax
0x140c7fe4b  lea     rax, aLpacdeviceacce; "lpacDeviceAccess"
0x140c7fe52  mov     [rbp+1D0h+var_B8.Buffer], rax
0x140c7fe59  lea     rax, aLearningmodelo; "learningModeLogging"
0x140c7fe60  mov     [rbp+1D0h+var_1F8.Buffer], rax
0x140c7fe64  lea     rax, aPermissivelear; "permissiveLearningMode"
0x140c7fe6b  mov     [rbp+1D0h+var_1E8.Buffer], rax
0x140c7fe6f  lea     rax, aSessionimperso; "sessionImpersonation"
0x140c7fe76  mov     [rbp+1D0h+var_1C8.Buffer], rax
0x140c7fe7a  lea     rax, aConstrainedimp; "constrainedImpersonation"
0x140c7fe81  mov     [rbp+1D0h+var_1D8.Buffer], rax
0x140c7fe85  lea     rax, aIsolatedwin32V; "isolatedWin32-volumeRootMinimal"
0x140c7fe8c  mov     [rbp+1D0h+var_A8.Buffer], rax
0x140c7fe93  lea     rax, aIsolatedwin32P_0; "isolatedWin32-profilesRootMinimal"
0x140c7fe9a  mov     [rbp+1D0h+var_98.Buffer], rax
0x140c7fea1  lea     rax, aIsolatedwin32P; "isolatedWin32-promptForAccess"
0x140c7fea8  mov     [rbp+1D0h+var_88.Buffer], rax
0x140c7feaf  lea     rax, aIsolatedwin32A; "isolatedWin32-accessToPublisherDirector"...
0x140c7feb6  mov     [rbp+1D0h+var_208.Buffer], rax
0x140c7feba  mov     eax, cs:dword_141203188
0x140c7fec0  mov     dword ptr [rsp+2D0h+IdentifierAuthority.Value], eax
0x140c7fec4  mov     qword ptr [rbp+1D0h+var_198.Length], 260024h
0x140c7fecc  mov     qword ptr [rbp+1D0h+var_188.Length], 2A0028h
0x140c7fed4  mov     qword ptr [rbp+1D0h+var_178.Length], 280026h
0x140c7fedc  mov     qword ptr [rbp+1D0h+var_168.Length], 50004Eh
0x140c7fee4  mov     qword ptr [rbp+1D0h+var_1B8.Length], 140012h
0x140c7feec  mov     qword ptr [rbp+1D0h+var_158.Length], 2A0028h
0x140c7fef4  mov     qword ptr [rbp+1D0h+var_148.Length], 1A0018h
0x140c7feff  mov     qword ptr [rbp+1D0h+var_138.Length], 2E002Ch
0x140c7ff0a  mov     qword ptr [rbp+1D0h+var_128.Length], 2C002Ah
0x140c7ff15  mov     qword ptr [rbp+1D0h+var_118.Length], 1A0018h
0x140c7ff20  mov     qword ptr [rbp+1D0h+var_108.Length], 20001Eh
0x140c7ff2b  mov     qword ptr [rbp+1D0h+var_F8.Length], 1A0018h
0x140c7ff36  mov     qword ptr [rbp+1D0h+var_E8.Length], 1C001Ah
0x140c7ff41  mov     qword ptr [rbp+1D0h+var_D8.Length], 10000Eh
0x140c7ff4c  mov     qword ptr [rbp+1D0h+var_C8.Length], 380036h
0x140c7ff57  mov     qword ptr [rbp+1D0h+var_B8.Length], 220020h
0x140c7ff62  mov     qword ptr [rbp+1D0h+var_1F8.Length], 280026h
0x140c7ff6a  mov     qword ptr [rbp+1D0h+var_1E8.Length], 2E002Ch
0x140c7ff72  mov     qword ptr [rbp+1D0h+var_1C8.Length], 2A0028h
0x140c7ff7a  mov     qword ptr [rbp+1D0h+var_1D8.Length], 320030h
0x140c7ff82  mov     qword ptr [rbp+1D0h+var_A8.Length], 40003Eh
0x140c7ff8d  mov     qword ptr [rbp+1D0h+var_98.Length], 440042h
0x140c7ff98  mov     qword ptr [rbp+1D0h+var_88.Length], 3C003Ah
0x140c7ffa3  mov     qword ptr [rbp+1D0h+var_208.Length], 520050h
0x140c7ffab  movzx   eax, cs:word_14120318C
0x140c7ffb2  mov     word ptr [rsp+2D0h+IdentifierAuthority.Value+4], ax
0x140c7ffb7  mov     eax, cs:dword_141203190
0x140c7ffbd  mov     dword ptr [rsp+2D0h+var_278.Value], eax
0x140c7ffc1  movzx   eax, cs:word_141203194
0x140c7ffc8  mov     word ptr [rsp+2D0h+var_278.Value+4], ax
0x140c7ffcd  mov     eax, cs:dword_141203198
0x140c7ffd3  mov     dword ptr [rsp+2D0h+var_270.Value], eax
0x140c7ffd7  movzx   eax, cs:word_14120319C
0x140c7ffde  mov     word ptr [rsp+2D0h+var_270.Value+4], ax
0x140c7ffe3  mov     eax, cs:dword_1412031A0
0x140c7ffe9  mov     dword ptr [rsp+2D0h+var_298.Value], eax
0x140c7ffed  movzx   eax, cs:word_1412031A4
0x140c7fff4  mov     word ptr [rsp+2D0h+var_298.Value+4], ax
0x140c7fff9  mov     eax, cs:dword_1412031A8
0x140c7ffff  mov     dword ptr [rsp+2D0h+var_2A8.Value], eax
0x140c80003  movzx   eax, cs:word_1412031AC
0x140c8000a  mov     word ptr [rsp+2D0h+var_2A8.Value+4], ax
0x140c8000f  mov     eax, cs:dword_1412031B0
0x140c80015  mov     dword ptr [rsp+2D0h+var_290.Value], eax
0x140c80019  movzx   eax, cs:word_1412031B4
0x140c80020  mov     word ptr [rsp+2D0h+var_290.Value+4], ax
0x140c80025  mov     eax, cs:dword_1412031B8
0x140c8002b  mov     dword ptr [rsp+2D0h+var_288.Value], eax
0x140c8002f  movzx   eax, cs:word_1412031BC
0x140c80036  mov     word ptr [rsp+2D0h+var_288.Value+4], ax
0x140c8003b  mov     eax, cs:dword_1412031C0
0x140c80041  mov     dword ptr [rsp+2D0h+var_2A0.Value], eax
0x140c80045  movzx   eax, cs:word_1412031C4
0x140c8004c  mov     word ptr [rsp+2D0h+var_2A0.Value+4], ax
0x140c80051  mov     rax, cs:KeLoaderBlock_0
0x140c80058  mov     rcx, [rax+0F0h]
0x140c8005f  mov     edx, [rcx+84h]
0x140c80065  test    r8b, dl
0x140c80068  jnz     short loc_140C80090
0x140c8006a  mov     rax, 0FFFFF78000000264h
0x140c80074  cmp     dword ptr [rax], 1
0x140c80077  jnz     short loc_140C80090
0x140c80079  mov     rax, 0FFFFF78000000310h
0x140c80083  cmp     qword ptr [rax], 83400h
0x140c8008a  ja      short loc_140C80090
0x140c8008c  mov     al, 1
0x140c8008e  jmp     short loc_140C80092
0x140c80090  xor     al, al
0x140c80092  shr     edx, 7
0x140c80095  mov     ecx, 1; SubAuthorityCount
0x140c8009a  and     dl, 1
0x140c8009d  mov     cs:SepTokenSidSharingEnabled, al
0x140c800a3  mov     cs:SepOsLoaderTpmDriverLoaded, dl
0x140c800a9  mov     cs:SepTokenCapabilitySidSharingEnabled, al
0x140c800af  call    RtlLengthRequiredSid
0x140c800b4  mov     ecx, 2; SubAuthorityCount
0x140c800b9  mov     dword ptr [rbp+1D0h+BugCheckParameter2], eax
0x140c800bf  mov     ebx, eax
0x140c800c1  call    RtlLengthRequiredSid
0x140c800c6  mov     ecx, 6; SubAuthorityCount
0x140c800cb  mov     dword ptr [rbp+1D0h+arg_10], eax
0x140c800d1  call    RtlLengthRequiredSid
0x140c800d6  mov     ecx, 9; SubAuthorityCount
0x140c800db  mov     dword ptr [rbp+1D0h+Size], eax
0x140c800e1  call    RtlLengthRequiredSid
0x140c800e6  mov     ecx, 0Ah; SubAuthorityCount
0x140c800eb  mov     dword ptr [rsp+2D0h+var_268], eax
0x140c800ef  call    RtlLengthRequiredSid
0x140c800f4  mov     ecx, ebx; BugCheckParameter2
0x140c800f6  mov     dword ptr [rbp+1D0h+arg_18], eax
0x140c800fc  call    ExKdproPoolAllocate
0x140c80101  mov     ecx, ebx; BugCheckParameter2
0x140c80103  mov     cs:SeNullSid, rax
0x140c8010a  call    ExKdproPoolAllocate
0x140c8010f  mov     ecx, ebx; BugCheckParameter2
0x140c80111  mov     cs:SeCreatorOwnerSid, rax
0x140c80118  call    ExKdproPoolAllocate
0x140c8011d  mov     ecx, ebx; BugCheckParameter2
0x140c8011f  mov     cs:SeCreatorGroupSid, rax
0x140c80126  call    ExKdproPoolAllocate
0x140c8012b  mov     ecx, ebx; BugCheckParameter2
0x140c8012d  mov     cs:SeCreatorOwnerServerSid, rax
0x140c80134  call    ExKdproPoolAllocate
0x140c80139  mov     ecx, ebx; BugCheckParameter2
0x140c8013b  mov     cs:SeCreatorGroupServerSid, rax
0x140c80142  call    ExKdproPoolAllocate
0x140c80147  mov     ecx, ebx; BugCheckParameter2
0x140c80149  mov     cs:SeWorldSid, rax
0x140c80150  call    ExKdproPoolAllocate
0x140c80155  mov     ecx, ebx; BugCheckParameter2
0x140c80157  mov     cs:SeLocalSid, rax
0x140c8015e  call    ExKdproPoolAllocate
0x140c80163  mov     r12, cs:SeNullSid
0x140c8016a  lea     rdx, [rsp+2D0h+IdentifierAuthority]; IdentifierAuthority
0x140c8016f  mov     rcx, r12; Sid
0x140c80172  mov     cs:SeOwnerRightsSid, rax
0x140c80179  mov     r8b, 1; SubAuthorityCount
0x140c8017c  call    RtlInitializeSid
0x140c80181  mov     r13, cs:SeWorldSid
0x140c80188  lea     rdx, [rsp+2D0h+var_278]; IdentifierAuthority
0x140c8018d  mov     rcx, r13; Sid
0x140c80190  mov     r8b, 1; SubAuthorityCount
0x140c80193  call    RtlInitializeSid
0x140c80198  mov     r15, cs:SeLocalSid
0x140c8019f  lea     rdx, [rsp+2D0h+var_270]; IdentifierAuthority
0x140c801a4  mov     rcx, r15; Sid
0x140c801a7  mov     r8b, 1; SubAuthorityCount
0x140c801aa  call    RtlInitializeSid
0x140c801af  mov     r14, cs:SeCreatorOwnerSid
0x140c801b6  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801bb  mov     rcx, r14; Sid
0x140c801be  mov     r8b, 1; SubAuthorityCount
0x140c801c1  call    RtlInitializeSid
0x140c801c6  mov     rsi, cs:SeCreatorGroupSid
0x140c801cd  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801d2  mov     rcx, rsi; Sid
0x140c801d5  mov     r8b, 1; SubAuthorityCount
0x140c801d8  call    RtlInitializeSid
0x140c801dd  mov     rdi, cs:SeCreatorOwnerServerSid
0x140c801e4  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801e9  mov     rcx, rdi; Sid
0x140c801ec  mov     r8b, 1; SubAuthorityCount
0x140c801ef  call    RtlInitializeSid
0x140c801f4  mov     rbx, cs:SeCreatorGroupServerSid
0x140c801fb  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c80200  mov     rcx, rbx; Sid
0x140c80203  mov     r8b, 1; SubAuthorityCount
0x140c80206  call    RtlInitializeSid
0x140c8020b  mov     r8b, 1; SubAuthorityCount
0x140c8020e  mov     rcx, cs:SeOwnerRightsSid; Sid
0x140c80215  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c8021a  call    RtlInitializeSid
0x140c8021f  xor     eax, eax
0x140c80221  xor     ecx, ecx; SubAuthorityCount
0x140c80223  mov     [r12+8], eax
0x140c80228  mov     [r13+8], eax
0x140c8022c  mov     [r15+8], eax
0x140c80230  mov     [r14+8], eax
0x140c80234  mov     rax, cs:SeOwnerRightsSid
0x140c8023b  mov     dword ptr [rsi+8], 1
0x140c80242  mov     dword ptr [rdi+8], 2
0x140c80249  mov     dword ptr [rbx+8], 3
0x140c80250  mov     dword ptr [rax+8], 4
0x140c80257  call    RtlLengthRequiredSid
0x140c8025c  mov     ecx, eax; BugCheckParameter2
0x140c8025e  call    ExKdproPoolAllocate
0x140c80263  mov     ebx, dword ptr [rbp+1D0h+BugCheckParameter2]
0x140c80269  mov     ecx, ebx; BugCheckParameter2
0x140c8026b  mov     cs:SeNtAuthoritySid, rax
0x140c80272  call    ExKdproPoolAllocate
0x140c80277  mov     ecx, ebx; BugCheckParameter2
0x140c80279  mov     cs:SeDialupSid, rax
0x140c80280  call    ExKdproPoolAllocate
0x140c80285  mov     ecx, ebx; BugCheckParameter2
0x140c80287  mov     cs:SeNetworkSid, rax
0x140c8028e  call    ExKdproPoolAllocate
0x140c80293  mov     ecx, ebx; BugCheckParameter2
0x140c80295  mov     cs:SeBatchSid, rax
0x140c8029c  call    ExKdproPoolAllocate
0x140c802a1  mov     ecx, ebx; BugCheckParameter2
0x140c802a3  mov     cs:SeInteractiveSid, rax
0x140c802aa  call    ExKdproPoolAllocate
0x140c802af  mov     ecx, ebx; BugCheckParameter2
0x140c802b1  mov     cs:SePrincipalSelfSid, rax
0x140c802b8  call    ExKdproPoolAllocate
0x140c802bd  mov     ecx, ebx; BugCheckParameter2
0x140c802bf  mov     cs:SeServiceSid, rax
0x140c802c6  call    ExKdproPoolAllocate
0x140c802cb  mov     ecx, ebx; BugCheckParameter2
0x140c802cd  mov     cs:SeLocalSystemSid, rax
0x140c802d4  call    ExKdproPoolAllocate
0x140c802d9  mov     ecx, ebx; BugCheckParameter2
0x140c802db  mov     cs:SeAuthenticatedUsersSid, rax
0x140c802e2  call    ExKdproPoolAllocate
0x140c802e7  mov     ecx, ebx; BugCheckParameter2
0x140c802e9  mov     cs:SeRestrictedSid, rax
0x140c802f0  call    ExKdproPoolAllocate
0x140c802f5  mov     ecx, ebx; BugCheckParameter2
0x140c802f7  mov     cs:SeAnonymousLogonSid, rax
0x140c802fe  call    ExKdproPoolAllocate
0x140c80303  mov     ecx, ebx; BugCheckParameter2
0x140c80305  mov     cs:SeLocalServiceSid, rax
0x140c8030c  call    ExKdproPoolAllocate
0x140c80311  mov     ecx, ebx; BugCheckParameter2
0x140c80313  mov     cs:SeNetworkServiceSid, rax
0x140c8031a  call    ExKdproPoolAllocate
0x140c8031f  mov     edi, dword ptr [rbp+1D0h+arg_10]
0x140c80325  mov     ecx, edi; BugCheckParameter2
0x140c80327  mov     cs:SeIUserSid, rax
0x140c8032e  call    ExKdproPoolAllocate
0x140c80333  mov     ecx, edi; BugCheckParameter2
0x140c80335  mov     cs:SeAliasAdminsSid, rax
0x140c8033c  call    ExKdproPoolAllocate
0x140c80341  mov     ecx, edi; BugCheckParameter2
0x140c80343  mov     cs:SeAliasUsersSid, rax
0x140c8034a  call    ExKdproPoolAllocate
0x140c8034f  mov     ecx, edi; BugCheckParameter2
0x140c80351  mov     cs:SeAliasGuestsSid, rax
0x140c80358  call    ExKdproPoolAllocate
0x140c8035d  mov     ecx, edi; BugCheckParameter2
0x140c8035f  mov     cs:SeAliasPowerUsersSid, rax
0x140c80366  call    ExKdproPoolAllocate
0x140c8036b  mov     ecx, edi; BugCheckParameter2
0x140c8036d  mov     cs:SeAliasAccountOpsSid, rax
0x140c80374  call    ExKdproPoolAllocate
0x140c80379  mov     ecx, edi; BugCheckParameter2
0x140c8037b  mov     cs:SeAliasSystemOpsSid, rax
0x140c80382  call    ExKdproPoolAllocate
0x140c80387  mov     cs:SeAliasPrintOpsSid, rax
0x140c8038e  mov     ecx, edi; BugCheckParameter2
0x140c80390  call    ExKdproPoolAllocate
0x140c80395  mov     ecx, ebx; BugCheckParameter2
0x140c80397  mov     cs:SeAliasBackupOpsSid, rax
  ... truncated ...
```
