# DmGetEnrollmentType(ushort const *,tagDMACCOUNTLOOKUPTYPE,EnrollmentEnrollType *)

- ea: `0x18002066c`
- end: `0x180020721`
- name: `?DmGetEnrollmentType@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAW4EnrollmentEnrollType@@@Z`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a6a0`
- `0x18001a7d0`
- `0x18001a940`

## callees

- `0x1800031b0`
- `0x1800205c8`
- `0x18002066c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800206fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800206fa`
- `DMCmnUtils!CopyString` at `0x1800206ad`
- `DMCmnUtils!CopyString` at `0x1800206ad`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800206e7`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800206e7`

## pseudocode

```c
__int64 __fastcall DmGetEnrollmentType(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  int EnrollmentType; // ebx
  HLOCAL hMem; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v7; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v8; // [rsp+40h] [rbp-28h] BYREF

  hMem = 0;
  v8 = 0;
  if ( a1 )
  {
    EnrollmentType = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    if ( EnrollmentType >= 0 )
    {
      EnrollmentType = DmConvertInternalAccountIdToEnrollmentId((unsigned __int16 *)hMem, &v8);
      if ( EnrollmentType >= 0 )
      {
        v7 = v8;
        EnrollmentType = GetEnrollmentType(&v7, a3);
      }
    }
  }
  else
  {
    EnrollmentType = -2147024809;
  }
  LocalFree(hMem);
  return (unsigned int)EnrollmentType;
}

```

## disassembly

```asm
0x18002066c  mov     [rsp+arg_8], rbx
0x180020671  push    rdi
0x180020672  sub     rsp, 60h
0x180020676  mov     rax, cs:__security_cookie
0x18002067d  xor     rax, rsp
0x180020680  mov     [rsp+68h+var_18], rax
0x180020685  mov     [rsp+68h+hMem], 0
0x18002068e  xorps   xmm0, xmm0
0x180020691  mov     rdi, r8
0x180020694  movups  xmmword ptr [rsp+68h+var_28.Data1], xmm0
0x180020699  test    rcx, rcx
0x18002069c  jnz     short loc_1800206A5
0x18002069e  mov     ebx, 80070057h
0x1800206a3  jmp     short loc_1800206F5
0x1800206a5  lea     r8, [rsp+68h+hMem]
0x1800206aa  or      edx, 0FFFFFFFFh
0x1800206ad  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800206b4  nop     dword ptr [rax+rax+00h]
0x1800206b9  mov     ebx, eax
0x1800206bb  test    eax, eax
0x1800206bd  js      short loc_1800206F5
0x1800206bf  mov     rcx, [rsp+68h+hMem]; unsigned __int16 *
0x1800206c4  lea     rdx, [rsp+68h+var_28]; struct _GUID *
0x1800206c9  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x1800206ce  mov     ebx, eax
0x1800206d0  test    eax, eax
0x1800206d2  js      short loc_1800206F5
0x1800206d4  movaps  xmm0, xmmword ptr [rsp+68h+var_28.Data1]
0x1800206d9  lea     rcx, [rsp+68h+var_38]
0x1800206de  mov     rdx, rdi
0x1800206e1  movdqa  [rsp+68h+var_38], xmm0
0x1800206e7  call    cs:__imp_GetEnrollmentType
0x1800206ee  nop     dword ptr [rax+rax+00h]
0x1800206f3  mov     ebx, eax
0x1800206f5  mov     rcx, [rsp+68h+hMem]; hMem
0x1800206fa  call    cs:__imp_LocalFree
0x180020701  nop     dword ptr [rax+rax+00h]
0x180020706  mov     eax, ebx
0x180020708  mov     rcx, [rsp+68h+var_18]
0x18002070d  xor     rcx, rsp; StackCookie
0x180020710  call    __security_check_cookie
0x180020715  mov     rbx, [rsp+68h+arg_8]
0x18002071a  add     rsp, 60h
0x18002071e  pop     rdi
0x18002071f  retn
```
