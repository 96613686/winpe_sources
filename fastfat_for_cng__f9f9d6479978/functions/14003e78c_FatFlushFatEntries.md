# FatFlushFatEntries

- ea: `0x14003e78c`
- end: `0x14003e86a`
- name: `FatFlushFatEntries`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400412a8`

## callees

- `0x14003e78c`
- `0x14003ea88`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003e80d`
- `ntoskrnl!CcFlushCache` at `0x14003e80d`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003e843`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003e843`
- `ntoskrnl!ExRaiseStatus` at `0x14003e851`
- `ntoskrnl!ExRaiseStatus` at `0x14003e851`

## pseudocode

```c
__int64 __fastcall FatFlushFatEntries(__int64 a1, __int64 a2, int a3, int a4)
{
  int v5; // r10d
  char v7; // al
  DWORD v8; // eax
  ULONG v9; // r8d
  __int64 v10; // rcx
  __int64 result; // rax
  NTSTATUS v12; // eax
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp+10h] BYREF

  v5 = *(unsigned __int16 *)(a2 + 288) * *(unsigned __int16 *)(a2 + 292);
  v7 = *(_BYTE *)(a2 + 376);
  FileOffset.HighPart = 0;
  IoStatus = 0;
  if ( v7 == 12 )
  {
    v8 = v5 + ((unsigned int)(3 * a3) >> 1);
    v9 = ((unsigned int)(3 * a4) >> 1) + 1;
  }
  else if ( v7 == 32 )
  {
    v8 = v5 + 4 * a3;
    v9 = 4 * a4;
  }
  else
  {
    v8 = v5 + 2 * a3;
    v9 = 2 * a4;
  }
  FileOffset.LowPart = v8;
  CcFlushCache((PSECTION_OBJECT_POINTERS)(a2 + 736), &FileOffset, v9, &IoStatus);
  LODWORD(result) = IoStatus.Status;
  if ( IoStatus.Status < 0
    || (result = FatHijackIrpAndFlushDevice(v10, *(_QWORD *)(a1 + 40), *(_QWORD *)(a2 + 136)),
        IoStatus.Status = result,
        (int)result < 0) )
  {
    *(_DWORD *)(a1 + 72) = result;
    v12 = FsRtlNormalizeNtstatus(result, -1073741591);
    ExRaiseStatus(v12);
  }
  return result;
}

```

## disassembly

```asm
0x14003e78c  mov     [rsp+arg_0], rbx
0x14003e791  push    rdi
0x14003e792  sub     rsp, 30h
0x14003e796  movzx   eax, word ptr [rdx+120h]
0x14003e79d  xorps   xmm0, xmm0
0x14003e7a0  movzx   r10d, word ptr [rdx+124h]
0x14003e7a8  mov     rbx, rdx
0x14003e7ab  imul    r10d, eax
0x14003e7af  mov     rdi, rcx
0x14003e7b2  mov     al, [rdx+178h]
0x14003e7b8  mov     dword ptr [rsp+38h+FileOffset+4], 0
0x14003e7c0  movups  xmmword ptr [rsp+38h+IoStatus], xmm0
0x14003e7c5  cmp     al, 0Ch
0x14003e7c7  jnz     short loc_14003E7DE
0x14003e7c9  lea     eax, [r8+r8*2]
0x14003e7cd  shr     eax, 1
0x14003e7cf  lea     r8d, [r9+r9*2]
0x14003e7d3  add     eax, r10d
0x14003e7d6  shr     r8d, 1
0x14003e7d9  inc     r8d
0x14003e7dc  jmp     short loc_14003E7F8
0x14003e7de  cmp     al, 20h ; ' '
0x14003e7e0  jnz     short loc_14003E7F0
0x14003e7e2  lea     eax, [r10+r8*4]
0x14003e7e6  lea     r8d, ds:0[r9*4]
0x14003e7ee  jmp     short loc_14003E7F8
0x14003e7f0  lea     eax, [r10+r8*2]
0x14003e7f4  lea     r8d, [r9+r9]; Length
0x14003e7f8  lea     rcx, [rdx+2E0h]; SectionObjectPointer
0x14003e7ff  mov     dword ptr [rsp+38h+FileOffset], eax
0x14003e803  lea     rdx, [rsp+38h+FileOffset]; FileOffset
0x14003e808  lea     r9, [rsp+38h+IoStatus]; IoStatus
0x14003e80d  call    cs:__imp_CcFlushCache
0x14003e814  nop     dword ptr [rax+rax+00h]
0x14003e819  mov     eax, dword ptr [rsp+38h+IoStatus]
0x14003e81d  test    eax, eax
0x14003e81f  js      short loc_14003E839
0x14003e821  mov     r8, [rbx+88h]
0x14003e828  mov     rdx, [rdi+28h]
0x14003e82c  call    FatHijackIrpAndFlushDevice
0x14003e831  mov     dword ptr [rsp+38h+IoStatus], eax
0x14003e835  test    eax, eax
0x14003e837  jns     short loc_14003E85E
0x14003e839  mov     edx, 0C00000E9h; GenericException
0x14003e83e  mov     [rdi+48h], eax
0x14003e841  mov     ecx, eax; Exception
0x14003e843  call    cs:__imp_FsRtlNormalizeNtstatus
0x14003e84a  nop     dword ptr [rax+rax+00h]
0x14003e84f  mov     ecx, eax; Status
0x14003e851  call    cs:__imp_ExRaiseStatus
0x14003e85e  mov     rbx, [rsp+38h+arg_0]
0x14003e863  add     rsp, 30h
0x14003e867  pop     rdi
0x14003e868  retn
```
