# CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)

- ea: `0x1800640e0`
- end: `0x180064201`
- name: `?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName, PDEVICE_OBJECT Pdo, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18004d718`
- `0x18004fa1c`

## callees

- `0x18000d1ac`
- `0x18000e0f0`
- `0x180019fc0`
- `0x1800640e0`
- `0x180064208`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064129`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064129`
- `ntoskrnl!ExFreePool` at `0x1800641d9`
- `ntoskrnl!ExFreePool` at `0x1800641d9`

## pseudocode

```c
__int64 __fastcall CreateFingerprintStringPrefix(
        PUNICODE_STRING SymbolicLinkName,
        PDEVICE_OBJECT Pdo,
        unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  struct CAMERA_DEVICE_FINGERPRINT *PoolWithTag; // rax
  struct CAMERA_DEVICE_FINGERPRINT *v9; // rdi
  int DeviceFingerprint; // ebx

  if ( !SymbolicLinkName || !Pdo || !a3 )
    return 3221225485LL;
  *a4 = 0;
  PoolWithTag = (struct CAMERA_DEVICE_FINGERPRINT *)ExAllocatePoolWithTag(PagedPool, 0x108u, 0x434D4143u);
  v9 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0x108u);
  DeviceFingerprint = CameraGetDeviceFingerprint(SymbolicLinkName, v9, Pdo);
  if ( DeviceFingerprint >= 0 )
  {
    DeviceFingerprint = RtlStringCchPrintfW(
                          a3,
                          0x69u,
                          L"%ws;%016I64X;%01X;%01X;%01X;%016I64X;%016I64X;",
                          v9,
                          *((_QWORD *)v9 + 8),
                          *((unsigned __int8 *)v9 + 72),
                          (unsigned __int8)*((_DWORD *)v9 + 19),
                          (unsigned __int8)*((_DWORD *)v9 + 20),
                          *((_QWORD *)v9 + 21),
                          *((_QWORD *)v9 + 32));
    RtlStringCchLengthW(a3, 0x69u, a4);
  }
  ExFreePool(v9);
  return (unsigned int)DeviceFingerprint;
}

```

## disassembly

```asm
0x1800640e0  push    rbx
0x1800640e2  push    rbp
0x1800640e3  push    rsi
0x1800640e4  push    rdi
0x1800640e5  push    r14
0x1800640e7  sub     rsp, 50h
0x1800640eb  mov     r14, r9
0x1800640ee  mov     rbp, r8
0x1800640f1  mov     rbx, rdx
0x1800640f4  mov     rsi, rcx
0x1800640f7  test    rcx, rcx
0x1800640fa  jz      loc_1800641F3
0x180064100  test    rdx, rdx
0x180064103  jz      loc_1800641F3
0x180064109  test    r8, r8
0x18006410c  jz      loc_1800641F3
0x180064112  mov     edx, 108h; NumberOfBytes
0x180064117  mov     qword ptr [r9], 0
0x18006411e  mov     ecx, 1; PoolType
0x180064123  mov     r8d, 434D4143h; Tag
0x180064129  call    cs:__imp_ExAllocatePoolWithTag
0x180064130  nop     dword ptr [rax+rax+00h]
0x180064135  mov     rdi, rax
0x180064138  test    rax, rax
0x18006413b  jz      loc_1800641FA
0x180064141  xor     edx, edx; Val
0x180064143  mov     r8d, 108h; Size
0x180064149  mov     rcx, rax; void *
0x18006414c  call    memset
0x180064151  mov     r8, rbx; Pdo
0x180064154  mov     rdx, rdi; struct CAMERA_DEVICE_FINGERPRINT *
0x180064157  mov     rcx, rsi; SymbolicLinkName
0x18006415a  call    ?CameraGetDeviceFingerprint@@YAJPEAU_UNICODE_STRING@@PEAUCAMERA_DEVICE_FINGERPRINT@@PEAU_DEVICE_OBJECT@@@Z; CameraGetDeviceFingerprint(_UNICODE_STRING *,CAMERA_DEVICE_FINGERPRINT *,_DEVICE_OBJECT *)
0x18006415f  mov     ebx, eax
0x180064161  test    eax, eax
0x180064163  js      short loc_1800641D6
0x180064165  mov     eax, [rdi+50h]
0x180064168  mov     esi, 69h ; 'i'
0x18006416d  movzx   edx, byte ptr [rdi+48h]
0x180064171  mov     r8d, [rdi+44h]
0x180064175  movzx   r9d, al
0x180064179  mov     eax, [rdi+4Ch]
0x18006417c  movzx   ecx, al
0x18006417f  mov     eax, [rdi+40h]
0x180064182  shl     r8, 20h
0x180064186  or      r8, rax
0x180064189  mov     rax, [rdi+100h]
0x180064190  mov     [rsp+78h+var_30], rax
0x180064195  mov     rax, [rdi+0A8h]
0x18006419c  mov     [rsp+78h+var_38], rax
0x1800641a1  mov     [rsp+78h+var_40], r9d
0x1800641a6  mov     r9, rdi
0x1800641a9  mov     [rsp+78h+var_48], ecx
0x1800641ad  mov     rcx, rbp; unsigned __int16 *
0x1800641b0  mov     [rsp+78h+var_50], edx
0x1800641b4  mov     edx, esi; unsigned __int64
0x1800641b6  mov     [rsp+78h+var_58], r8
0x1800641bb  lea     r8, aWs016i64x01x01; "%ws;%016I64X;%01X;%01X;%01X;%016I64X;%0"...
0x1800641c2  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800641c7  mov     r8, r14; unsigned __int64 *
0x1800641ca  mov     edx, esi; unsigned __int64
0x1800641cc  mov     rcx, rbp; unsigned __int16 *
0x1800641cf  mov     ebx, eax
0x1800641d1  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800641d6  mov     rcx, rdi; P
0x1800641d9  call    cs:__imp_ExFreePool
0x1800641e0  nop     dword ptr [rax+rax+00h]
0x1800641e5  mov     eax, ebx
0x1800641e7  add     rsp, 50h
0x1800641eb  pop     r14
0x1800641ed  pop     rdi
0x1800641ee  pop     rsi
0x1800641ef  pop     rbp
0x1800641f0  pop     rbx
0x1800641f1  retn
0x1800641f3  mov     eax, 0C000000Dh
0x1800641f8  jmp     short loc_1800641E7
0x1800641fa  mov     eax, 0C000009Ah
0x1800641ff  jmp     short loc_1800641E7
```
