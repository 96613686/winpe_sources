# NfsRdrpGetUidGidFromLdap

- ea: `0x140028f00`
- end: `0x1400290fd`
- name: `NfsRdrpGetUidGidFromLdap`
- size: `509`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025be0`
- `0x140029b24`

## callees

- `0x140028f00`
- `0x14003972c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400290de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400290de`
- `ntoskrnl!ExAllocatePool2` at `0x140028ffb`
- `ntoskrnl!ExAllocatePool2` at `0x140028ffb`
- `ksecdd!SecLookupAccountSid` at `0x140029056`
- `ksecdd!SecLookupAccountSid` at `0x140029056`

## pseudocode

```c
__int64 __fastcall NfsRdrpGetUidGidFromLdap(
        __int64 a1,
        _QWORD *a2,
        void **a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _WORD *v10; // rax
  _WORD *v11; // rcx
  NTSTATUS v12; // edi
  unsigned int v13; // eax
  WCHAR *Pool2; // rax
  WCHAR *v15; // rsi
  void *v16; // rcx
  ULONG DomainSize; // [rsp+40h] [rbp-31h] BYREF
  ULONG NameSize; // [rsp+44h] [rbp-2Dh] BYREF
  struct _UNICODE_STRING NameBuffer; // [rsp+48h] [rbp-29h] BYREF
  struct _UNICODE_STRING DomainBuffer; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v22[9]; // [rsp+68h] [rbp-9h] BYREF
  enum _SID_NAME_USE NameUse; // [rsp+C8h] [rbp+57h] BYREF

  if ( a2 && (v10 = (_WORD *)a2[4]) != 0 && (v11 = (_WORD *)a2[2]) != 0 && *v10 && *v11 )
  {
    if ( (*(_DWORD *)(a1 + 2316) & 8) == 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 2352));
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 2316), 0, 0) & 8) == 0 )
      {
        v13 = NfsUpCallGetUidGidWithLdapClient(*(_QWORD *)(a1 + 2016), a2[4], a2[2], a2[3], a4, a5, a6, a7);
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 2352));
        return v13;
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 2352));
    }
    return (unsigned int)-1073741058;
  }
  else
  {
    v22[0] = 0;
    NameSize = 0;
    DomainSize = 0;
    NameUse = 0;
    v22[1] = 0;
    NameBuffer = 0;
    DomainBuffer = 0;
    Pool2 = (WCHAR *)ExAllocatePool2(258, 1058, 844260942);
    v15 = Pool2;
    if ( Pool2 )
    {
      v16 = *a3;
      DomainBuffer.Buffer = Pool2;
      NameBuffer.Buffer = Pool2 + 273;
      *(_DWORD *)&DomainBuffer.Length = 35782656;
      *(_DWORD *)&NameBuffer.Length = 0x2000000;
      v12 = SecLookupAccountSid(v16, &NameSize, &NameBuffer, &DomainSize, &DomainBuffer, &NameUse);
      if ( v12 >= 0 )
      {
        if ( (*(_DWORD *)(a1 + 2316) & 8) != 0 )
        {
          v12 = -1073741058;
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 2352));
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 2316), 0, 0) & 8) != 0 )
            v12 = -1073741058;
          else
            v12 = NfsUpCallGetUidGidWithLdapClient(
                    *(_QWORD *)(a1 + 2016),
                    (unsigned int)&DomainBuffer,
                    (unsigned int)&NameBuffer,
                    (unsigned int)v22,
                    a4,
                    a5,
                    a6,
                    a7);
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 2352));
        }
      }
      ExFreePoolWithTag(v15, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028f00  push    rbp
0x140028f02  push    rbx
0x140028f03  push    rsi
0x140028f04  push    rdi
0x140028f05  push    r14
0x140028f07  push    r15
0x140028f09  lea     rbp, [rsp-17h]
0x140028f0e  sub     rsp, 88h
0x140028f15  xor     r15d, r15d
0x140028f18  mov     r14, r9
0x140028f1b  mov     rdi, r8
0x140028f1e  mov     rbx, rcx
0x140028f21  test    rdx, rdx
0x140028f24  jz      loc_140028FC9
0x140028f2a  mov     rax, [rdx+20h]
0x140028f2e  test    rax, rax
0x140028f31  jz      loc_140028FC9
0x140028f37  mov     rcx, [rdx+10h]
0x140028f3b  test    rcx, rcx
0x140028f3e  jz      loc_140028FC9
0x140028f44  cmp     [rax], r15w
0x140028f48  jz      short loc_140028FC9
0x140028f4a  cmp     [rcx], r15w
0x140028f4e  jz      short loc_140028FC9
0x140028f50  mov     eax, [rbx+90Ch]
0x140028f56  test    al, 8
0x140028f58  jnz     short loc_140028F79
0x140028f5a  lock inc dword ptr [rbx+930h]
0x140028f61  mov     ecx, r15d
0x140028f64  xor     eax, eax
0x140028f66  lock cmpxchg [rbx+90Ch], ecx
0x140028f6e  test    al, 8
0x140028f70  jz      short loc_140028F83
0x140028f72  lock dec dword ptr [rbx+930h]
0x140028f79  mov     edi, 0C00002FEh
0x140028f7e  jmp     loc_1400290EA
0x140028f83  mov     rax, [rbp+3Fh+arg_30]
0x140028f87  mov     r9, [rdx+18h]
0x140028f8b  mov     r8, [rdx+10h]
0x140028f8f  mov     rdx, [rdx+20h]
0x140028f93  mov     rcx, [rbx+7E0h]
0x140028f9a  mov     [rsp+0B0h+var_78], rax
0x140028f9f  mov     rax, [rbp+3Fh+arg_28]
0x140028fa3  mov     [rsp+0B0h+var_80], rax
0x140028fa8  mov     rax, [rbp+3Fh+arg_20]
0x140028fac  mov     [rsp+0B0h+NameUse], rax
0x140028fb1  mov     [rsp+0B0h+DomainBuffer], r14
0x140028fb6  call    NfsUpCallGetUidGidWithLdapClient
0x140028fbb  lock dec dword ptr [rbx+930h]
0x140028fc2  mov     edi, eax
0x140028fc4  jmp     loc_1400290EA
0x140028fc9  xorps   xmm0, xmm0
0x140028fcc  mov     [rbp+3Fh+var_48], r15
0x140028fd0  xorps   xmm1, xmm1
0x140028fd3  mov     [rbp+3Fh+NameSize], r15d
0x140028fd7  mov     edx, 422h
0x140028fdc  mov     [rbp+3Fh+DomainSize], r15d
0x140028fe0  mov     ecx, 102h
0x140028fe5  mov     [rbp+3Fh+arg_8], r15d
0x140028fe9  mov     r8d, 3252664Eh
0x140028fef  mov     [rbp+3Fh+var_40], r15
0x140028ff3  movups  xmmword ptr [rbp+3Fh+NameBuffer.Length], xmm0
0x140028ff7  movups  xmmword ptr [rbp+3Fh+var_58.Length], xmm1
0x140028ffb  call    cs:__imp_ExAllocatePool2
0x140029002  nop     dword ptr [rax+rax+00h]
0x140029007  mov     rsi, rax
0x14002900a  test    rax, rax
0x14002900d  jnz     short loc_140029019
0x14002900f  mov     edi, 0C000009Ah
0x140029014  jmp     loc_1400290EA
0x140029019  mov     rcx, [rdi]; Sid
0x14002901c  lea     r9, [rbp+3Fh+DomainSize]; DomainSize
0x140029020  add     rax, 222h
0x140029026  mov     [rbp+3Fh+var_58.Buffer], rsi
0x14002902a  mov     [rbp+3Fh+NameBuffer.Buffer], rax
0x14002902e  lea     r8, [rbp+3Fh+NameBuffer]; NameBuffer
0x140029032  lea     rax, [rbp+3Fh+arg_8]
0x140029036  mov     dword ptr [rbp+3Fh+var_58.Length], 2220000h
0x14002903d  mov     [rsp+0B0h+NameUse], rax; NameUse
0x140029042  lea     rdx, [rbp+3Fh+NameSize]; NameSize
0x140029046  lea     rax, [rbp+3Fh+var_58]
0x14002904a  mov     dword ptr [rbp+3Fh+NameBuffer.Length], 2000000h
0x140029051  mov     [rsp+0B0h+DomainBuffer], rax; DomainBuffer
0x140029056  call    cs:__imp_SecLookupAccountSid
0x14002905d  nop     dword ptr [rax+rax+00h]
0x140029062  mov     edi, eax
0x140029064  test    eax, eax
0x140029066  js      short loc_1400290D9
0x140029068  mov     eax, [rbx+90Ch]
0x14002906e  test    al, 8
0x140029070  jz      short loc_140029079
0x140029072  mov     edi, 0C00002FEh
0x140029077  jmp     short loc_1400290D9
0x140029079  lock inc dword ptr [rbx+930h]
0x140029080  mov     ecx, r15d
0x140029083  xor     eax, eax
0x140029085  lock cmpxchg [rbx+90Ch], ecx
0x14002908d  test    al, 8
0x14002908f  jz      short loc_140029098
0x140029091  mov     edi, 0C00002FEh
0x140029096  jmp     short loc_1400290D2
0x140029098  mov     rax, [rbp+3Fh+arg_30]
0x14002909c  lea     r9, [rbp+3Fh+var_48]
0x1400290a0  mov     rcx, [rbx+7E0h]
0x1400290a7  lea     r8, [rbp+3Fh+NameBuffer]
0x1400290ab  mov     [rsp+0B0h+var_78], rax
0x1400290b0  lea     rdx, [rbp+3Fh+var_58]
0x1400290b4  mov     rax, [rbp+3Fh+arg_28]
0x1400290b8  mov     [rsp+0B0h+var_80], rax
0x1400290bd  mov     rax, [rbp+3Fh+arg_20]
0x1400290c1  mov     [rsp+0B0h+NameUse], rax
0x1400290c6  mov     [rsp+0B0h+DomainBuffer], r14
0x1400290cb  call    NfsUpCallGetUidGidWithLdapClient
0x1400290d0  mov     edi, eax
0x1400290d2  lock dec dword ptr [rbx+930h]
0x1400290d9  xor     edx, edx; Tag
0x1400290db  mov     rcx, rsi; P
0x1400290de  call    cs:__imp_ExFreePoolWithTag
0x1400290e5  nop     dword ptr [rax+rax+00h]
0x1400290ea  mov     eax, edi
0x1400290ec  add     rsp, 88h
0x1400290f3  pop     r15
0x1400290f5  pop     r14
0x1400290f7  pop     rdi
0x1400290f8  pop     rsi
0x1400290f9  pop     rbx
0x1400290fa  pop     rbp
0x1400290fb  retn
```
