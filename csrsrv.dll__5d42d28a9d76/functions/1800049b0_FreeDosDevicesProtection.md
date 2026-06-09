# FreeDosDevicesProtection

- ea: `0x1800049b0`
- end: `0x180004a0b`
- name: `FreeDosDevicesProtection`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f20`

## callees

- `0x1800049b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800049f9`
- `ntdll!RtlFreeHeap` at `0x1800049f9`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800049d6`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800049d6`

## pseudocode

```c
char __fastcall FreeDosDevicesProtection(void *a1)
{
  NTSTATUS DaclSecurityDescriptor; // eax
  unsigned __int8 DaclDefaulted; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int8 DaclPresent; // [rsp+40h] [rbp+18h] BYREF
  PACL Dacl; // [rsp+48h] [rbp+20h] BYREF

  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a1, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor >= 0 && Dacl )
    LOBYTE(DaclSecurityDescriptor) = RtlFreeHeap(CsrHeap, 0, Dacl);
  return DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x1800049b0  sub     rsp, 28h
0x1800049b4  lea     r9, [rsp+28h+DaclDefaulted]; DaclDefaulted
0x1800049b9  mov     [rsp+28h+Dacl], 0
0x1800049c2  lea     r8, [rsp+28h+Dacl]; Dacl
0x1800049c7  mov     [rsp+28h+DaclPresent], 0
0x1800049cc  lea     rdx, [rsp+28h+DaclPresent]; DaclPresent
0x1800049d1  mov     [rsp+28h+DaclDefaulted], 0
0x1800049d6  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800049dd  nop     dword ptr [rax+rax+00h]
0x1800049e2  test    eax, eax
0x1800049e4  js      short loc_180004A05
0x1800049e6  mov     r8, [rsp+28h+Dacl]; BaseAddress
0x1800049eb  test    r8, r8
0x1800049ee  jz      short loc_180004A05
0x1800049f0  mov     rcx, cs:CsrHeap; HeapHandle
0x1800049f7  xor     edx, edx; Flags
0x1800049f9  call    cs:__imp_RtlFreeHeap
0x180004a00  nop     dword ptr [rax+rax+00h]
0x180004a05  add     rsp, 28h
0x180004a09  retn
```
