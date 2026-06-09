# DmGetEnrollmentForceAadToken(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong *)

- ea: `0x140055248`
- end: `0x1400552f1`
- name: `?DmGetEnrollmentForceAadToken@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140032760`
- `0x140052e60`

## callees

- `0x140003450`
- `0x140054a6c`
- `0x140055248`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400552c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400552c7`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14005527a`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14005527a`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x1400552b4`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x1400552b4`

## pseudocode

```c
__int64 __fastcall DmGetEnrollmentForceAadToken(__int64 a1, __int64 a2, __int64 a3)
{
  int InternalAcctID; // ebx
  HLOCAL hMem[2]; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v7; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v8; // [rsp+40h] [rbp-28h] BYREF

  hMem[0] = 0;
  v8 = 0;
  InternalAcctID = OmaDmGetInternalAcctID(a1, a2, hMem);
  if ( InternalAcctID >= 0 )
  {
    InternalAcctID = DmConvertInternalAccountIdToEnrollmentId((unsigned __int16 *)hMem[0], &v8);
    if ( InternalAcctID >= 0 )
    {
      v7 = v8;
      InternalAcctID = GetEnrollmentForceAadToken(&v7, a3);
    }
  }
  LocalFree(hMem[0]);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x140055248  mov     [rsp+arg_18], rbx
0x14005524d  push    rdi
0x14005524e  sub     rsp, 60h
0x140055252  mov     rax, cs:__security_cookie
0x140055259  xor     rax, rsp
0x14005525c  mov     [rsp+68h+var_18], rax
0x140055261  mov     rdi, r8
0x140055264  mov     [rsp+68h+hMem], 0
0x14005526d  xorps   xmm0, xmm0
0x140055270  lea     r8, [rsp+68h+hMem]
0x140055275  movups  xmmword ptr [rsp+68h+var_28.Data1], xmm0
0x14005527a  call    cs:__imp_OmaDmGetInternalAcctID
0x140055281  nop     dword ptr [rax+rax+00h]
0x140055286  mov     ebx, eax
0x140055288  test    eax, eax
0x14005528a  js      short loc_1400552C2
0x14005528c  mov     rcx, [rsp+68h+hMem]; unsigned __int16 *
0x140055291  lea     rdx, [rsp+68h+var_28]; struct _GUID *
0x140055296  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x14005529b  mov     ebx, eax
0x14005529d  test    eax, eax
0x14005529f  js      short loc_1400552C2
0x1400552a1  movaps  xmm0, xmmword ptr [rsp+68h+var_28.Data1]
0x1400552a6  lea     rcx, [rsp+68h+var_38]
0x1400552ab  mov     rdx, rdi
0x1400552ae  movdqa  [rsp+68h+var_38], xmm0
0x1400552b4  call    cs:__imp_GetEnrollmentForceAadToken
0x1400552bb  nop     dword ptr [rax+rax+00h]
0x1400552c0  mov     ebx, eax
0x1400552c2  mov     rcx, [rsp+68h+hMem]; hMem
0x1400552c7  call    cs:__imp_LocalFree
0x1400552ce  nop     dword ptr [rax+rax+00h]
0x1400552d3  mov     eax, ebx
0x1400552d5  mov     rcx, [rsp+68h+var_18]
0x1400552da  xor     rcx, rsp; StackCookie
0x1400552dd  call    __security_check_cookie
0x1400552e2  mov     rbx, [rsp+68h+arg_18]
0x1400552ea  add     rsp, 60h
0x1400552ee  pop     rdi
0x1400552ef  retn
```
