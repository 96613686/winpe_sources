# LPA::Lui::ValidateAppContainerCapability(void *,ushort const *)

- ea: `0x1800ce378`
- end: `0x1800ce409`
- name: `?ValidateAppContainerCapability@Lui@LPA@@CAJPEAXPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ce810`

## callees

- `0x18006ba8c`
- `0x1800ce378`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce3b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce3b1`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800ce3e1`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800ce3e1`

## pseudocode

```c
__int64 __fastcall LPA::Lui::ValidateAppContainerCapability(void *a1, const unsigned __int16 *a2)
{
  CommonUtil *v3; // rcx
  __int64 result; // rax
  CommonUtil *v5; // rcx
  const unsigned __int16 *v6; // [rsp+48h] [rbp+10h] BYREF
  int TokenInformation; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  v6 = a2;
  LOBYTE(v6) = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(a1, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( !TokenInformation )
      return 2147942405LL;
  }
  else
  {
    result = CommonUtil::GetLastErrorToHResultAndForceFailure(v3);
    if ( (int)result < 0 )
      return result;
  }
  if ( (int)CapabilityCheck(a1, L"Microsoft.eSIMManagement_8wekyb3d8bbwe", &v6) < 0 )
    return CommonUtil::GetLastErrorToHResultAndForceFailure(v5);
  else
    return (_BYTE)v6 == 0 ? 0x80070005 : 0;
}

```

## disassembly

```asm
0x1800ce378  mov     rax, rsp
0x1800ce37b  mov     [rax+10h], rdx
0x1800ce37f  push    rbx
0x1800ce380  sub     rsp, 30h
0x1800ce384  mov     r9d, 4; TokenInformationLength
0x1800ce38a  mov     byte ptr [rax+10h], 0
0x1800ce38e  mov     dword ptr [rax+18h], 0
0x1800ce395  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800ce39a  mov     dword ptr [rax+20h], 0
0x1800ce3a1  lea     rax, [rax+20h]
0x1800ce3a5  mov     rbx, rcx
0x1800ce3a8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800ce3ad  lea     edx, [r9+19h]; TokenInformationClass
0x1800ce3b1  call    cs:__imp_GetTokenInformation
0x1800ce3b7  test    eax, eax
0x1800ce3b9  jz      short loc_1800CE3C9
0x1800ce3bb  cmp     [rsp+38h+TokenInformation], 0
0x1800ce3c0  jnz     short loc_1800CE3D2
0x1800ce3c2  mov     eax, 80070005h
0x1800ce3c7  jmp     short loc_1800CE403
0x1800ce3c9  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce3ce  test    eax, eax
0x1800ce3d0  js      short loc_1800CE403
0x1800ce3d2  lea     r8, [rsp+38h+arg_8]
0x1800ce3d7  mov     rcx, rbx
0x1800ce3da  lea     rdx, aMicrosoftEsimm; "Microsoft.eSIMManagement_8wekyb3d8bbwe"
0x1800ce3e1  call    cs:__imp_CapabilityCheck
0x1800ce3e7  test    eax, eax
0x1800ce3e9  js      short loc_1800CE3FE
0x1800ce3eb  mov     al, byte ptr [rsp+38h+arg_8]
0x1800ce3ef  neg     al
0x1800ce3f1  mov     eax, 80070005h
0x1800ce3f6  sbb     ecx, ecx
0x1800ce3f8  not     ecx
0x1800ce3fa  and     eax, ecx
0x1800ce3fc  jmp     short loc_1800CE403
0x1800ce3fe  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce403  add     rsp, 30h
0x1800ce407  pop     rbx
0x1800ce408  retn
```
