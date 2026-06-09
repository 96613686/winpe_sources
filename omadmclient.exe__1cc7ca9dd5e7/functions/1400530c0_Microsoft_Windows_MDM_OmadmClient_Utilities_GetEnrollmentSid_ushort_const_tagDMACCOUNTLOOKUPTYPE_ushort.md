# Microsoft::Windows::MDM::OmadmClient::Utilities::GetEnrollmentSid(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)

- ea: `0x1400530c0`
- end: `0x14005316f`
- name: `?GetEnrollmentSid@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003450`
- `0x1400530c0`
- `0x140054a6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053148`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400530fb`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400530fb`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140053135`
- `dmEnrollEngine!GetEnrollmentSID` at `0x140053135`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::GetEnrollmentSid(
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
      InternalAcctID = GetEnrollmentSID(&v8, a4);
    }
  }
  LocalFree(hMem[0]);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x1400530c0  mov     [rsp+arg_0], rbx
0x1400530c5  push    rdi
0x1400530c6  sub     rsp, 60h
0x1400530ca  mov     rax, cs:__security_cookie
0x1400530d1  xor     rax, rsp
0x1400530d4  mov     [rsp+68h+var_18], rax
0x1400530d9  mov     rdi, r9
0x1400530dc  mov     [rsp+68h+hMem], 0
0x1400530e5  mov     r9d, r8d
0x1400530e8  mov     rcx, rdx
0x1400530eb  xorps   xmm0, xmm0
0x1400530ee  lea     r8, [rsp+68h+hMem]
0x1400530f3  mov     edx, r9d
0x1400530f6  movups  xmmword ptr [rsp+68h+var_28.Data1], xmm0
0x1400530fb  call    cs:__imp_OmaDmGetInternalAcctID
0x140053102  nop     dword ptr [rax+rax+00h]
0x140053107  mov     ebx, eax
0x140053109  test    eax, eax
0x14005310b  js      short loc_140053143
0x14005310d  mov     rcx, [rsp+68h+hMem]; unsigned __int16 *
0x140053112  lea     rdx, [rsp+68h+var_28]; struct _GUID *
0x140053117  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x14005311c  mov     ebx, eax
0x14005311e  test    eax, eax
0x140053120  js      short loc_140053143
0x140053122  movaps  xmm0, xmmword ptr [rsp+68h+var_28.Data1]
0x140053127  lea     rcx, [rsp+68h+var_38]
0x14005312c  mov     rdx, rdi
0x14005312f  movdqa  [rsp+68h+var_38], xmm0
0x140053135  call    cs:__imp_GetEnrollmentSID
0x14005313c  nop     dword ptr [rax+rax+00h]
0x140053141  mov     ebx, eax
0x140053143  mov     rcx, [rsp+68h+hMem]; hMem
0x140053148  call    cs:__imp_LocalFree
0x14005314f  nop     dword ptr [rax+rax+00h]
0x140053154  mov     eax, ebx
0x140053156  mov     rcx, [rsp+68h+var_18]
0x14005315b  xor     rcx, rsp; StackCookie
0x14005315e  call    __security_check_cookie
0x140053163  mov     rbx, [rsp+68h+arg_0]
0x140053168  add     rsp, 60h
0x14005316c  pop     rdi
0x14005316d  retn
```
