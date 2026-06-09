# mySetControlFlagsOnSDDL(ushort const *,ushort,ushort * *)

- ea: `0x1800280a0`
- end: `0x180028149`
- name: `?mySetControlFlagsOnSDDL@@YAJPEBGGPEAPEAG@Z`
- size: `169`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033144`

## callees

- `0x180008400`
- `0x180012450`
- `0x1800270d8`
- `0x1800280a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002813b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002813b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800280e9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800280e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180028119`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180028119`

## pseudocode

```c
__int64 __fastcall mySetControlFlagsOnSDDL(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int v5; // eax
  unsigned int v6; // ecx
  unsigned int v7; // ebx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  pSecurityDescriptor = 0;
  if ( !myConvertStringSecurityDescriptorToSecurityDescriptor(a1, a2, &pSecurityDescriptor, a4) )
  {
    v5 = myHLastError();
    v6 = 34996628;
LABEL_3:
    v7 = v5;
    CSPrintErrorLineFile(v6, v5);
    goto LABEL_9;
  }
  if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u) )
  {
    v5 = myHLastError();
    v6 = 35455380;
    goto LABEL_3;
  }
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(pSecurityDescriptor, 1u, 0x1Fu, a3, 0) )
  {
    v5 = myHLastError();
    v6 = 36569492;
    goto LABEL_3;
  }
  v7 = 0;
LABEL_9:
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x1800280a0  push    rbx
0x1800280a2  sub     rsp, 30h
0x1800280a6  mov     rbx, r8
0x1800280a9  mov     qword ptr [r8], 0
0x1800280b0  lea     r8, [rsp+38h+pSecurityDescriptor]; void **
0x1800280b5  mov     [rsp+38h+pSecurityDescriptor], 0
0x1800280be  call    ?myConvertStringSecurityDescriptorToSecurityDescriptor@@YAHPEBGKPEAPEAXPEAK@Z; myConvertStringSecurityDescriptorToSecurityDescriptor(ushort const *,ulong,void * *,ulong *)
0x1800280c3  test    eax, eax
0x1800280c5  jnz     short loc_1800280DC
0x1800280c7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800280cc  mov     ecx, 2160194h; unsigned int
0x1800280d1  mov     edx, eax; int
0x1800280d3  mov     ebx, eax
0x1800280d5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800280da  jmp     short loc_180028131
0x1800280dc  mov     rcx, [rsp+38h+pSecurityDescriptor]; pSecurityDescriptor
0x1800280e1  mov     edx, 1000h; ControlBitsOfInterest
0x1800280e6  mov     r8d, edx; ControlBitsToSet
0x1800280e9  call    cs:__imp_SetSecurityDescriptorControl
0x1800280ef  test    eax, eax
0x1800280f1  jnz     short loc_1800280FF
0x1800280f3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800280f8  mov     ecx, 21D0194h
0x1800280fd  jmp     short loc_1800280D1
0x1800280ff  mov     rcx, [rsp+38h+pSecurityDescriptor]; SecurityDescriptor
0x180028104  mov     edx, 1; RequestedStringSDRevision
0x180028109  mov     r9, rbx; StringSecurityDescriptor
0x18002810c  mov     [rsp+38h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180028115  lea     r8d, [rdx+1Eh]; SecurityInformation
0x180028119  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18002811f  test    eax, eax
0x180028121  jnz     short loc_18002812F
0x180028123  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180028128  mov     ecx, 22E0194h
0x18002812d  jmp     short loc_1800280D1
0x18002812f  xor     ebx, ebx
0x180028131  mov     rcx, [rsp+38h+pSecurityDescriptor]; hMem
0x180028136  test    rcx, rcx
0x180028139  jz      short loc_180028141
0x18002813b  call    cs:__imp_LocalFree
0x180028141  mov     eax, ebx
0x180028143  add     rsp, 30h
0x180028147  pop     rbx
0x180028148  retn
```
