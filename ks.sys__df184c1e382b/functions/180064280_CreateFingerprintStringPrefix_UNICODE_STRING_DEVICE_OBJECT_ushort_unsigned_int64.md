# CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)

- ea: `0x180064280`
- end: `0x1800643a1`
- name: `?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName, PDEVICE_OBJECT Pdo, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18004d8b8`
- `0x18004fbbc`

## callees

- `0x18000d1ac`
- `0x18000e0f0`
- `0x18001a000`
- `0x180064280`
- `0x1800643a8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800642c9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800642c9`
- `ntoskrnl!ExFreePool` at `0x180064379`
- `ntoskrnl!ExFreePool` at `0x180064379`

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
0x180064280  push    rbx
0x180064282  push    rbp
0x180064283  push    rsi
0x180064284  push    rdi
0x180064285  push    r14
0x180064287  sub     rsp, 50h
0x18006428b  mov     r14, r9
0x18006428e  mov     rbp, r8
0x180064291  mov     rbx, rdx
0x180064294  mov     rsi, rcx
0x180064297  test    rcx, rcx
0x18006429a  jz      loc_180064393
0x1800642a0  test    rdx, rdx
0x1800642a3  jz      loc_180064393
0x1800642a9  test    r8, r8
0x1800642ac  jz      loc_180064393
0x1800642b2  mov     edx, 108h; NumberOfBytes
0x1800642b7  mov     qword ptr [r9], 0
0x1800642be  mov     ecx, 1; PoolType
0x1800642c3  mov     r8d, 434D4143h; Tag
0x1800642c9  call    cs:__imp_ExAllocatePoolWithTag
0x1800642d0  nop     dword ptr [rax+rax+00h]
0x1800642d5  mov     rdi, rax
0x1800642d8  test    rax, rax
0x1800642db  jz      loc_18006439A
0x1800642e1  xor     edx, edx; Val
0x1800642e3  mov     r8d, 108h; Size
0x1800642e9  mov     rcx, rax; void *
0x1800642ec  call    memset
0x1800642f1  mov     r8, rbx; Pdo
0x1800642f4  mov     rdx, rdi; struct CAMERA_DEVICE_FINGERPRINT *
0x1800642f7  mov     rcx, rsi; SymbolicLinkName
0x1800642fa  call    ?CameraGetDeviceFingerprint@@YAJPEAU_UNICODE_STRING@@PEAUCAMERA_DEVICE_FINGERPRINT@@PEAU_DEVICE_OBJECT@@@Z; CameraGetDeviceFingerprint(_UNICODE_STRING *,CAMERA_DEVICE_FINGERPRINT *,_DEVICE_OBJECT *)
0x1800642ff  mov     ebx, eax
0x180064301  test    eax, eax
0x180064303  js      short loc_180064376
0x180064305  mov     eax, [rdi+50h]
0x180064308  mov     esi, 69h ; 'i'
0x18006430d  movzx   edx, byte ptr [rdi+48h]
0x180064311  mov     r8d, [rdi+44h]
0x180064315  movzx   r9d, al
0x180064319  mov     eax, [rdi+4Ch]
0x18006431c  movzx   ecx, al
0x18006431f  mov     eax, [rdi+40h]
0x180064322  shl     r8, 20h
0x180064326  or      r8, rax
0x180064329  mov     rax, [rdi+100h]
0x180064330  mov     [rsp+78h+var_30], rax
0x180064335  mov     rax, [rdi+0A8h]
0x18006433c  mov     [rsp+78h+var_38], rax
0x180064341  mov     [rsp+78h+var_40], r9d
0x180064346  mov     r9, rdi
0x180064349  mov     [rsp+78h+var_48], ecx
0x18006434d  mov     rcx, rbp; unsigned __int16 *
0x180064350  mov     [rsp+78h+var_50], edx
0x180064354  mov     edx, esi; unsigned __int64
0x180064356  mov     [rsp+78h+var_58], r8
0x18006435b  lea     r8, aWs016i64x01x01; "%ws;%016I64X;%01X;%01X;%01X;%016I64X;%0"...
0x180064362  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064367  mov     r8, r14; unsigned __int64 *
0x18006436a  mov     edx, esi; unsigned __int64
0x18006436c  mov     rcx, rbp; unsigned __int16 *
0x18006436f  mov     ebx, eax
0x180064371  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180064376  mov     rcx, rdi; P
0x180064379  call    cs:__imp_ExFreePool
0x180064380  nop     dword ptr [rax+rax+00h]
0x180064385  mov     eax, ebx
0x180064387  add     rsp, 50h
0x18006438b  pop     r14
0x18006438d  pop     rdi
0x18006438e  pop     rsi
0x18006438f  pop     rbp
0x180064390  pop     rbx
0x180064391  retn
0x180064393  mov     eax, 0C000000Dh
0x180064398  jmp     short loc_180064387
0x18006439a  mov     eax, 0C000009Ah
0x18006439f  jmp     short loc_180064387
```
