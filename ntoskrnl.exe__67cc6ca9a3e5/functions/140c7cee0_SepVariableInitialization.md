# SepVariableInitialization

- ea: `0x140c7cee0`
- end: `0x140c7e912`
- name: `SepVariableInitialization`
- size: `6706`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140c7eae8`

## callees

- `0x14045b2b0`
- `0x14062eb7c`
- `0x140681d88`
- `0x1406f4880`
- `0x1407c8fc8`
- `0x1408f9f00`
- `0x1409fb170`
- `0x140c7c420`
- `0x140c7cee0`

## string_xrefs

- `0x140c7cf15`: `lpacCom`
- `0x140c7cf28`: `lpacCryptoServices`
- `0x140c7cfeb`: `lpacDeviceAccess`
- `0x140c7cf6d`: `registryRead`
- `0x140c7cf7b`: `lpacServicesManagement`
- `0x140c7cf33`: `lpacIdentityServices`
- `0x140c7d041`: `isolatedWin32-promptForAccess`
- `0x140c7d04f`: `isolatedWin32-accessToPublisherDirectory`
- `0x140c7d00f`: `sessionImpersonation`
- `0x140c7d01a`: `constrainedImpersonation`

## pseudocode

```c

```

## disassembly

```asm
0x140c7cee0  push    rbp
0x140c7cee2  push    rbx
0x140c7cee3  push    rsi
0x140c7cee4  push    rdi
0x140c7cee5  push    r12
0x140c7cee7  push    r13
0x140c7cee9  push    r14
0x140c7ceeb  push    r15
0x140c7ceed  lea     rbp, [rsp-198h]
0x140c7cef5  sub     rsp, 298h
0x140c7cefc  lea     rax, aLpacappexperie; "lpacAppExperience"
0x140c7cf03  mov     qword ptr [rbp+1D0h+String2.Length], 240022h
0x140c7cf0b  mov     [rbp+1D0h+String2.Buffer], rax
0x140c7cf0f  mov     r8d, 40h ; '@'
0x140c7cf15  lea     rax, aLpaccom; "lpacCom"
0x140c7cf1c  mov     qword ptr [rbp+1D0h+var_1A8.Length], 10000Eh
0x140c7cf24  mov     [rbp+1D0h+var_1A8.Buffer], rax
0x140c7cf28  lea     rax, aLpaccryptoserv; "lpacCryptoServices"
0x140c7cf2f  mov     [rbp+1D0h+var_198.Buffer], rax
0x140c7cf33  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x140c7cf3a  mov     [rbp+1D0h+var_188.Buffer], rax
0x140c7cf3e  lea     rax, aLpacinstrument_0; "lpacInstrumentation"
0x140c7cf45  mov     [rbp+1D0h+var_178.Buffer], rax
0x140c7cf49  lea     rax, aLpacenterprise; "lpacEnterprisePolicyChangeNotifications"
0x140c7cf50  mov     [rbp+1D0h+var_168.Buffer], rax
0x140c7cf54  lea     rax, aLpacmedia; "lpacMedia"
0x140c7cf5b  mov     [rbp+1D0h+var_1B8.Buffer], rax
0x140c7cf5f  lea     rax, aLpacpnpnotific; "lpacPnpNotifications"
0x140c7cf66  mov     [rbp+1D0h+var_158.Buffer], rax
0x140c7cf6d  lea     rax, aRegistryread_0; "registryRead"
0x140c7cf74  mov     [rbp+1D0h+var_148.Buffer], rax
0x140c7cf7b  lea     rax, aLpacservicesma; "lpacServicesManagement"
0x140c7cf82  mov     [rbp+1D0h+var_138.Buffer], rax
0x140c7cf89  lea     rax, aLpacsessionman; "lpacSessionManagement"
0x140c7cf90  mov     [rbp+1D0h+var_128.Buffer], rax
0x140c7cf97  lea     rax, aLpacprinting; "lpacPrinting"
0x140c7cf9e  mov     [rbp+1D0h+var_118.Buffer], rax
0x140c7cfa5  lea     rax, aLpacwebplatfor; "lpacWebPlatform"
0x140c7cfac  mov     [rbp+1D0h+var_108.Buffer], rax
0x140c7cfb3  lea     rax, aLpacpayments; "lpacPayments"
0x140c7cfba  mov     [rbp+1D0h+var_F8.Buffer], rax
0x140c7cfc1  lea     rax, aLpacclipboard; "lpacClipboard"
0x140c7cfc8  mov     [rbp+1D0h+var_E8.Buffer], rax
0x140c7cfcf  lea     rax, aLpacime; "lpacIME"
0x140c7cfd6  mov     [rbp+1D0h+var_D8.Buffer], rax
0x140c7cfdd  lea     rax, aLpacpackageman; "lpacPackageManagerOperation"
0x140c7cfe4  mov     [rbp+1D0h+var_C8.Buffer], rax
0x140c7cfeb  lea     rax, aLpacdeviceacce; "lpacDeviceAccess"
0x140c7cff2  mov     [rbp+1D0h+var_B8.Buffer], rax
0x140c7cff9  lea     rax, aLearningmodelo; "learningModeLogging"
0x140c7d000  mov     [rbp+1D0h+var_1F8.Buffer], rax
0x140c7d004  lea     rax, aPermissivelear; "permissiveLearningMode"
0x140c7d00b  mov     [rbp+1D0h+var_1E8.Buffer], rax
0x140c7d00f  lea     rax, aSessionimperso; "sessionImpersonation"
0x140c7d016  mov     [rbp+1D0h+var_1C8.Buffer], rax
0x140c7d01a  lea     rax, aConstrainedimp; "constrainedImpersonation"
0x140c7d021  mov     [rbp+1D0h+var_1D8.Buffer], rax
0x140c7d025  lea     rax, aIsolatedwin32V; "isolatedWin32-volumeRootMinimal"
0x140c7d02c  mov     [rbp+1D0h+var_A8.Buffer], rax
0x140c7d033  lea     rax, aIsolatedwin32P_0; "isolatedWin32-profilesRootMinimal"
0x140c7d03a  mov     [rbp+1D0h+var_98.Buffer], rax
0x140c7d041  lea     rax, aIsolatedwin32P; "isolatedWin32-promptForAccess"
0x140c7d048  mov     [rbp+1D0h+var_88.Buffer], rax
0x140c7d04f  lea     rax, aIsolatedwin32A; "isolatedWin32-accessToPublisherDirector"...
0x140c7d056  mov     [rbp+1D0h+var_208.Buffer], rax
0x140c7d05a  mov     eax, cs:dword_141203188
0x140c7d060  mov     dword ptr [rsp+2D0h+IdentifierAuthority.Value], eax
0x140c7d064  mov     qword ptr [rbp+1D0h+var_198.Length], 260024h
0x140c7d06c  mov     qword ptr [rbp+1D0h+var_188.Length], 2A0028h
0x140c7d074  mov     qword ptr [rbp+1D0h+var_178.Length], 280026h
0x140c7d07c  mov     qword ptr [rbp+1D0h+var_168.Length], 50004Eh
0x140c7d084  mov     qword ptr [rbp+1D0h+var_1B8.Length], 140012h
0x140c7d08c  mov     qword ptr [rbp+1D0h+var_158.Length], 2A0028h
0x140c7d094  mov     qword ptr [rbp+1D0h+var_148.Length], 1A0018h
0x140c7d09f  mov     qword ptr [rbp+1D0h+var_138.Length], 2E002Ch
0x140c7d0aa  mov     qword ptr [rbp+1D0h+var_128.Length], 2C002Ah
0x140c7d0b5  mov     qword ptr [rbp+1D0h+var_118.Length], 1A0018h
0x140c7d0c0  mov     qword ptr [rbp+1D0h+var_108.Length], 20001Eh
0x140c7d0cb  mov     qword ptr [rbp+1D0h+var_F8.Length], 1A0018h
0x140c7d0d6  mov     qword ptr [rbp+1D0h+var_E8.Length], 1C001Ah
0x140c7d0e1  mov     qword ptr [rbp+1D0h+var_D8.Length], 10000Eh
0x140c7d0ec  mov     qword ptr [rbp+1D0h+var_C8.Length], 380036h
0x140c7d0f7  mov     qword ptr [rbp+1D0h+var_B8.Length], 220020h
0x140c7d102  mov     qword ptr [rbp+1D0h+var_1F8.Length], 280026h
0x140c7d10a  mov     qword ptr [rbp+1D0h+var_1E8.Length], 2E002Ch
0x140c7d112  mov     qword ptr [rbp+1D0h+var_1C8.Length], 2A0028h
0x140c7d11a  mov     qword ptr [rbp+1D0h+var_1D8.Length], 320030h
0x140c7d122  mov     qword ptr [rbp+1D0h+var_A8.Length], 40003Eh
0x140c7d12d  mov     qword ptr [rbp+1D0h+var_98.Length], 440042h
0x140c7d138  mov     qword ptr [rbp+1D0h+var_88.Length], 3C003Ah
0x140c7d143  mov     qword ptr [rbp+1D0h+var_208.Length], 520050h
0x140c7d14b  movzx   eax, cs:word_14120318C
0x140c7d152  mov     word ptr [rsp+2D0h+IdentifierAuthority.Value+4], ax
0x140c7d157  mov     eax, cs:dword_1412031A0
0x140c7d15d  mov     dword ptr [rsp+2D0h+var_278.Value], eax
0x140c7d161  movzx   eax, cs:word_1412031A4
0x140c7d168  mov     word ptr [rsp+2D0h+var_278.Value+4], ax
0x140c7d16d  mov     eax, cs:dword_1412031A8
0x140c7d173  mov     dword ptr [rsp+2D0h+var_270.Value], eax
0x140c7d177  movzx   eax, cs:word_1412031AC
0x140c7d17e  mov     word ptr [rsp+2D0h+var_270.Value+4], ax
0x140c7d183  mov     eax, cs:dword_141203190
0x140c7d189  mov     dword ptr [rsp+2D0h+var_298.Value], eax
0x140c7d18d  movzx   eax, cs:word_141203194
0x140c7d194  mov     word ptr [rsp+2D0h+var_298.Value+4], ax
0x140c7d199  mov     eax, cs:dword_141203198
0x140c7d19f  mov     dword ptr [rsp+2D0h+var_2A8.Value], eax
0x140c7d1a3  movzx   eax, cs:word_14120319C
0x140c7d1aa  mov     word ptr [rsp+2D0h+var_2A8.Value+4], ax
0x140c7d1af  mov     eax, cs:dword_1412031B8
0x140c7d1b5  mov     dword ptr [rsp+2D0h+var_290.Value], eax
0x140c7d1b9  movzx   eax, cs:word_1412031BC
0x140c7d1c0  mov     word ptr [rsp+2D0h+var_290.Value+4], ax
0x140c7d1c5  mov     eax, cs:dword_1412031C0
0x140c7d1cb  mov     dword ptr [rsp+2D0h+var_288.Value], eax
0x140c7d1cf  movzx   eax, cs:word_1412031C4
0x140c7d1d6  mov     word ptr [rsp+2D0h+var_288.Value+4], ax
0x140c7d1db  mov     eax, cs:dword_1412031B0
0x140c7d1e1  mov     dword ptr [rsp+2D0h+var_2A0.Value], eax
0x140c7d1e5  movzx   eax, cs:word_1412031B4
0x140c7d1ec  mov     word ptr [rsp+2D0h+var_2A0.Value+4], ax
0x140c7d1f1  mov     rax, cs:KeLoaderBlock_0
0x140c7d1f8  mov     rcx, [rax+0F0h]
0x140c7d1ff  mov     edx, [rcx+84h]
0x140c7d205  test    r8b, dl
0x140c7d208  jnz     short loc_140C7D230
0x140c7d20a  mov     rax, 0FFFFF78000000264h
0x140c7d214  cmp     dword ptr [rax], 1
0x140c7d217  jnz     short loc_140C7D230
0x140c7d219  mov     rax, 0FFFFF78000000310h
0x140c7d223  cmp     qword ptr [rax], 83400h
0x140c7d22a  ja      short loc_140C7D230
0x140c7d22c  mov     al, 1
0x140c7d22e  jmp     short loc_140C7D232
0x140c7d230  xor     al, al
0x140c7d232  shr     edx, 7
0x140c7d235  mov     ecx, 1; SubAuthorityCount
0x140c7d23a  and     dl, 1
0x140c7d23d  mov     cs:SepTokenSidSharingEnabled, al
0x140c7d243  mov     cs:SepOsLoaderTpmDriverLoaded, dl
0x140c7d249  mov     cs:SepTokenCapabilitySidSharingEnabled, al
0x140c7d24f  call    RtlLengthRequiredSid
0x140c7d254  mov     ecx, 2; SubAuthorityCount
0x140c7d259  mov     dword ptr [rbp+1D0h+BugCheckParameter2], eax
0x140c7d25f  mov     ebx, eax
0x140c7d261  call    RtlLengthRequiredSid
0x140c7d266  mov     ecx, 6; SubAuthorityCount
0x140c7d26b  mov     dword ptr [rbp+1D0h+arg_10], eax
0x140c7d271  call    RtlLengthRequiredSid
0x140c7d276  mov     ecx, 9; SubAuthorityCount
0x140c7d27b  mov     dword ptr [rbp+1D0h+Size], eax
0x140c7d281  call    RtlLengthRequiredSid
0x140c7d286  mov     ecx, 0Ah; SubAuthorityCount
0x140c7d28b  mov     dword ptr [rsp+2D0h+var_268], eax
0x140c7d28f  call    RtlLengthRequiredSid
0x140c7d294  mov     ecx, ebx; BugCheckParameter2
0x140c7d296  mov     dword ptr [rbp+1D0h+arg_18], eax
0x140c7d29c  call    ExKdproPoolAllocate
0x140c7d2a1  mov     ecx, ebx; BugCheckParameter2
0x140c7d2a3  mov     cs:SeNullSid, rax
0x140c7d2aa  call    ExKdproPoolAllocate
0x140c7d2af  mov     ecx, ebx; BugCheckParameter2
0x140c7d2b1  mov     cs:SeCreatorOwnerSid, rax
0x140c7d2b8  call    ExKdproPoolAllocate
0x140c7d2bd  mov     ecx, ebx; BugCheckParameter2
0x140c7d2bf  mov     cs:SeCreatorGroupSid, rax
0x140c7d2c6  call    ExKdproPoolAllocate
0x140c7d2cb  mov     ecx, ebx; BugCheckParameter2
0x140c7d2cd  mov     cs:SeCreatorOwnerServerSid, rax
0x140c7d2d4  call    ExKdproPoolAllocate
0x140c7d2d9  mov     ecx, ebx; BugCheckParameter2
0x140c7d2db  mov     cs:SeCreatorGroupServerSid, rax
0x140c7d2e2  call    ExKdproPoolAllocate
0x140c7d2e7  mov     ecx, ebx; BugCheckParameter2
0x140c7d2e9  mov     cs:SeWorldSid, rax
0x140c7d2f0  call    ExKdproPoolAllocate
0x140c7d2f5  mov     ecx, ebx; BugCheckParameter2
0x140c7d2f7  mov     cs:SeLocalSid, rax
0x140c7d2fe  call    ExKdproPoolAllocate
0x140c7d303  mov     r12, cs:SeNullSid
0x140c7d30a  lea     rdx, [rsp+2D0h+IdentifierAuthority]; IdentifierAuthority
0x140c7d30f  mov     rcx, r12; Sid
0x140c7d312  mov     cs:SeOwnerRightsSid, rax
0x140c7d319  mov     r8b, 1; SubAuthorityCount
0x140c7d31c  call    RtlInitializeSid
0x140c7d321  mov     r13, cs:SeWorldSid
0x140c7d328  lea     rdx, [rsp+2D0h+var_278]; IdentifierAuthority
0x140c7d32d  mov     rcx, r13; Sid
0x140c7d330  mov     r8b, 1; SubAuthorityCount
0x140c7d333  call    RtlInitializeSid
0x140c7d338  mov     r15, cs:SeLocalSid
0x140c7d33f  lea     rdx, [rsp+2D0h+var_270]; IdentifierAuthority
0x140c7d344  mov     rcx, r15; Sid
0x140c7d347  mov     r8b, 1; SubAuthorityCount
0x140c7d34a  call    RtlInitializeSid
0x140c7d34f  mov     r14, cs:SeCreatorOwnerSid
0x140c7d356  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c7d35b  mov     rcx, r14; Sid
0x140c7d35e  mov     r8b, 1; SubAuthorityCount
0x140c7d361  call    RtlInitializeSid
0x140c7d366  mov     rsi, cs:SeCreatorGroupSid
0x140c7d36d  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c7d372  mov     rcx, rsi; Sid
0x140c7d375  mov     r8b, 1; SubAuthorityCount
0x140c7d378  call    RtlInitializeSid
0x140c7d37d  mov     rdi, cs:SeCreatorOwnerServerSid
0x140c7d384  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c7d389  mov     rcx, rdi; Sid
0x140c7d38c  mov     r8b, 1; SubAuthorityCount
0x140c7d38f  call    RtlInitializeSid
0x140c7d394  mov     rbx, cs:SeCreatorGroupServerSid
0x140c7d39b  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c7d3a0  mov     rcx, rbx; Sid
0x140c7d3a3  mov     r8b, 1; SubAuthorityCount
0x140c7d3a6  call    RtlInitializeSid
0x140c7d3ab  mov     r8b, 1; SubAuthorityCount
0x140c7d3ae  mov     rcx, cs:SeOwnerRightsSid; Sid
0x140c7d3b5  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c7d3ba  call    RtlInitializeSid
0x140c7d3bf  xor     eax, eax
0x140c7d3c1  xor     ecx, ecx; SubAuthorityCount
0x140c7d3c3  mov     [r12+8], eax
0x140c7d3c8  mov     [r13+8], eax
0x140c7d3cc  mov     [r15+8], eax
0x140c7d3d0  mov     [r14+8], eax
0x140c7d3d4  mov     rax, cs:SeOwnerRightsSid
0x140c7d3db  mov     dword ptr [rsi+8], 1
0x140c7d3e2  mov     dword ptr [rdi+8], 2
0x140c7d3e9  mov     dword ptr [rbx+8], 3
0x140c7d3f0  mov     dword ptr [rax+8], 4
0x140c7d3f7  call    RtlLengthRequiredSid
0x140c7d3fc  mov     ecx, eax; BugCheckParameter2
0x140c7d3fe  call    ExKdproPoolAllocate
0x140c7d403  mov     ebx, dword ptr [rbp+1D0h+BugCheckParameter2]
0x140c7d409  mov     ecx, ebx; BugCheckParameter2
0x140c7d40b  mov     cs:SeNtAuthoritySid, rax
0x140c7d412  call    ExKdproPoolAllocate
0x140c7d417  mov     ecx, ebx; BugCheckParameter2
0x140c7d419  mov     cs:SeDialupSid, rax
0x140c7d420  call    ExKdproPoolAllocate
0x140c7d425  mov     ecx, ebx; BugCheckParameter2
0x140c7d427  mov     cs:SeNetworkSid, rax
0x140c7d42e  call    ExKdproPoolAllocate
0x140c7d433  mov     ecx, ebx; BugCheckParameter2
0x140c7d435  mov     cs:SeBatchSid, rax
0x140c7d43c  call    ExKdproPoolAllocate
0x140c7d441  mov     ecx, ebx; BugCheckParameter2
0x140c7d443  mov     cs:SeInteractiveSid, rax
0x140c7d44a  call    ExKdproPoolAllocate
0x140c7d44f  mov     ecx, ebx; BugCheckParameter2
0x140c7d451  mov     cs:SePrincipalSelfSid, rax
0x140c7d458  call    ExKdproPoolAllocate
0x140c7d45d  mov     ecx, ebx; BugCheckParameter2
0x140c7d45f  mov     cs:SeServiceSid, rax
0x140c7d466  call    ExKdproPoolAllocate
0x140c7d46b  mov     ecx, ebx; BugCheckParameter2
0x140c7d46d  mov     cs:SeLocalSystemSid, rax
0x140c7d474  call    ExKdproPoolAllocate
0x140c7d479  mov     ecx, ebx; BugCheckParameter2
0x140c7d47b  mov     cs:SeAuthenticatedUsersSid, rax
0x140c7d482  call    ExKdproPoolAllocate
0x140c7d487  mov     ecx, ebx; BugCheckParameter2
0x140c7d489  mov     cs:SeRestrictedSid, rax
0x140c7d490  call    ExKdproPoolAllocate
0x140c7d495  mov     ecx, ebx; BugCheckParameter2
0x140c7d497  mov     cs:SeAnonymousLogonSid, rax
0x140c7d49e  call    ExKdproPoolAllocate
0x140c7d4a3  mov     ecx, ebx; BugCheckParameter2
0x140c7d4a5  mov     cs:SeLocalServiceSid, rax
0x140c7d4ac  call    ExKdproPoolAllocate
0x140c7d4b1  mov     ecx, ebx; BugCheckParameter2
0x140c7d4b3  mov     cs:SeNetworkServiceSid, rax
0x140c7d4ba  call    ExKdproPoolAllocate
0x140c7d4bf  mov     edi, dword ptr [rbp+1D0h+arg_10]
0x140c7d4c5  mov     ecx, edi; BugCheckParameter2
0x140c7d4c7  mov     cs:SeIUserSid, rax
0x140c7d4ce  call    ExKdproPoolAllocate
0x140c7d4d3  mov     ecx, edi; BugCheckParameter2
0x140c7d4d5  mov     cs:SeAliasAdminsSid, rax
0x140c7d4dc  call    ExKdproPoolAllocate
0x140c7d4e1  mov     ecx, edi; BugCheckParameter2
0x140c7d4e3  mov     cs:SeAliasUsersSid, rax
0x140c7d4ea  call    ExKdproPoolAllocate
0x140c7d4ef  mov     ecx, edi; BugCheckParameter2
0x140c7d4f1  mov     cs:SeAliasGuestsSid, rax
0x140c7d4f8  call    ExKdproPoolAllocate
0x140c7d4fd  mov     ecx, edi; BugCheckParameter2
0x140c7d4ff  mov     cs:SeAliasPowerUsersSid, rax
0x140c7d506  call    ExKdproPoolAllocate
0x140c7d50b  mov     ecx, edi; BugCheckParameter2
0x140c7d50d  mov     cs:SeAliasAccountOpsSid, rax
0x140c7d514  call    ExKdproPoolAllocate
0x140c7d519  mov     ecx, edi; BugCheckParameter2
0x140c7d51b  mov     cs:SeAliasSystemOpsSid, rax
0x140c7d522  call    ExKdproPoolAllocate
0x140c7d527  mov     cs:SeAliasPrintOpsSid, rax
0x140c7d52e  mov     ecx, edi; BugCheckParameter2
0x140c7d530  call    ExKdproPoolAllocate
0x140c7d535  mov     ecx, ebx; BugCheckParameter2
0x140c7d537  mov     cs:SeAliasBackupOpsSid, rax
  ... truncated ...
```
