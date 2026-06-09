# FatFlushDirentForFile

- ea: `0x14003e40c`
- end: `0x14003e4ad`
- name: `FatFlushDirentForFile`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400412a8`

## callees

- `0x14003e40c`
- `0x14003ea88`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003e449`
- `ntoskrnl!CcFlushCache` at `0x14003e449`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003e486`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003e486`
- `ntoskrnl!ExRaiseStatus` at `0x14003e494`
- `ntoskrnl!ExRaiseStatus` at `0x14003e494`

## pseudocode

```c
__int64 __fastcall FatFlushDirentForFile(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v5; // rcx
  __int64 result; // rax
  NTSTATUS v7; // eax
  NTSTATUS Exception[4]; // [rsp+20h] [rbp-18h] BYREF
  union _LARGE_INTEGER v9; // [rsp+48h] [rbp+10h] BYREF

  v9.QuadPart = *(unsigned int *)(a2 + 244);
  v3 = *(_QWORD *)(a2 + 176);
  *(_OWORD *)Exception = 0;
  CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v3 + 120), &v9, 0x20u, (PIO_STATUS_BLOCK)Exception);
  LODWORD(result) = Exception[0];
  if ( Exception[0] < 0
    || (result = FatHijackIrpAndFlushDevice(v5, *(_QWORD *)(a1 + 40), *(_QWORD *)(*(_QWORD *)(a2 + 184) + 136LL)),
        Exception[0] = result,
        (int)result < 0) )
  {
    *(_DWORD *)(a1 + 72) = result;
    v7 = FsRtlNormalizeNtstatus(result, -1073741591);
    ExRaiseStatus(v7);
  }
  return result;
}

```

## disassembly

```asm
0x14003e40c  mov     r11, rsp
0x14003e40f  mov     [r11+8], rbx
0x14003e413  push    rdi
0x14003e414  sub     rsp, 30h
0x14003e418  mov     eax, [rdx+0F4h]
0x14003e41e  lea     r9, [r11-18h]; IoStatus
0x14003e422  mov     rbx, rcx
0x14003e425  mov     [r11+10h], rax
0x14003e429  mov     rcx, [rdx+0B0h]
0x14003e430  xorps   xmm0, xmm0
0x14003e433  mov     rdi, rdx
0x14003e436  mov     r8d, 20h ; ' '; Length
0x14003e43c  movups  xmmword ptr [rsp+38h+Exception], xmm0
0x14003e441  lea     rdx, [r11+10h]; FileOffset
0x14003e445  mov     rcx, [rcx+78h]; SectionObjectPointer
0x14003e449  call    cs:__imp_CcFlushCache
0x14003e450  nop     dword ptr [rax+rax+00h]
0x14003e455  mov     eax, [rsp+38h+Exception]
0x14003e459  test    eax, eax
0x14003e45b  js      short loc_14003E47C
0x14003e45d  mov     r8, [rdi+0B8h]
0x14003e464  mov     rdx, [rbx+28h]
0x14003e468  mov     r8, [r8+88h]
0x14003e46f  call    FatHijackIrpAndFlushDevice
0x14003e474  mov     [rsp+38h+Exception], eax
0x14003e478  test    eax, eax
0x14003e47a  jns     short loc_14003E4A1
0x14003e47c  mov     edx, 0C00000E9h; GenericException
0x14003e481  mov     [rbx+48h], eax
0x14003e484  mov     ecx, eax; Exception
0x14003e486  call    cs:__imp_FsRtlNormalizeNtstatus
0x14003e48d  nop     dword ptr [rax+rax+00h]
0x14003e492  mov     ecx, eax; Status
0x14003e494  call    cs:__imp_ExRaiseStatus
0x14003e4a1  mov     rbx, [rsp+38h+arg_0]
0x14003e4a6  add     rsp, 30h
0x14003e4aa  pop     rdi
0x14003e4ab  retn
```
