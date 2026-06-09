# Microsoft::Windows::MDM::OmadmClient::Utilities::GetEnrollmentSendDeviceToken(ushort const *,tagDMACCOUNTLOOKUPTYPE,int *)

- ea: `0x140053000`
- end: `0x1400530af`
- name: `?GetEnrollmentSendDeviceToken@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAH@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003450`
- `0x140053000`
- `0x140054a6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053088`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14005303b`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14005303b`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x140053075`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x140053075`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::GetEnrollmentSendDeviceToken(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  int InternalAcctID; // ebx
  HLOCAL hMem[2]; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v8; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v9; // [rsp+40h] [rbp-28h] BYREF

  hMem[0] = 0;
  v9 = 0;
  InternalAcctID = OmaDmGetInternalAcctID(a2, a3, hMem);
  if ( InternalAcctID >= 0 )
  {
    InternalAcctID = DmConvertInternalAccountIdToEnrollmentId((unsigned __int16 *)hMem[0], &v9);
    if ( InternalAcctID >= 0 )
    {
      v8 = v9;
      InternalAcctID = GetEnrollmentAadSendDeviceToken(&v8, a4);
    }
  }
  LocalFree(hMem[0]);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x140053000  mov     [rsp+arg_0], rbx
0x140053005  push    rdi
0x140053006  sub     rsp, 60h
0x14005300a  mov     rax, cs:__security_cookie
0x140053011  xor     rax, rsp
0x140053014  mov     [rsp+68h+var_18], rax
0x140053019  mov     rdi, r9
0x14005301c  mov     [rsp+68h+hMem], 0
0x140053025  mov     r9d, r8d
0x140053028  mov     rcx, rdx
0x14005302b  xorps   xmm0, xmm0
0x14005302e  lea     r8, [rsp+68h+hMem]
0x140053033  mov     edx, r9d
0x140053036  movups  xmmword ptr [rsp+68h+var_28.Data1], xmm0
0x14005303b  call    cs:__imp_OmaDmGetInternalAcctID
0x140053042  nop     dword ptr [rax+rax+00h]
0x140053047  mov     ebx, eax
0x140053049  test    eax, eax
0x14005304b  js      short loc_140053083
0x14005304d  mov     rcx, [rsp+68h+hMem]; unsigned __int16 *
0x140053052  lea     rdx, [rsp+68h+var_28]; struct _GUID *
0x140053057  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x14005305c  mov     ebx, eax
0x14005305e  test    eax, eax
0x140053060  js      short loc_140053083
0x140053062  movaps  xmm0, xmmword ptr [rsp+68h+var_28.Data1]
0x140053067  lea     rcx, [rsp+68h+var_38]
0x14005306c  mov     rdx, rdi
0x14005306f  movdqa  [rsp+68h+var_38], xmm0
0x140053075  call    cs:__imp_GetEnrollmentAadSendDeviceToken
0x14005307c  nop     dword ptr [rax+rax+00h]
0x140053081  mov     ebx, eax
0x140053083  mov     rcx, [rsp+68h+hMem]; hMem
0x140053088  call    cs:__imp_LocalFree
0x14005308f  nop     dword ptr [rax+rax+00h]
0x140053094  mov     eax, ebx
0x140053096  mov     rcx, [rsp+68h+var_18]
0x14005309b  xor     rcx, rsp; StackCookie
0x14005309e  call    __security_check_cookie
0x1400530a3  mov     rbx, [rsp+68h+arg_0]
0x1400530a8  add     rsp, 60h
0x1400530ac  pop     rdi
0x1400530ad  retn
```
