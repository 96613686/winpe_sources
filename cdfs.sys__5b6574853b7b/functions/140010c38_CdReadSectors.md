# CdReadSectors

- ea: `0x140010c38`
- end: `0x140010d6a`
- name: `CdReadSectors`
- size: `306`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Buffer, PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013c0c`
- `0x140013e2c`

## callees

- `0x140001114`
- `0x140010c38`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140010c65`
- `ntoskrnl!KeInitializeEvent` at `0x140010c65`
- `ntoskrnl!IofCallDriver` at `0x140010cd4`
- `ntoskrnl!IofCallDriver` at `0x140010cd4`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140010cad`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140010cad`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010cfd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010cfd`

## pseudocode

```c
char __fastcall CdReadSectors(
        __int64 a1,
        union _LARGE_INTEGER a2,
        __int64 a3,
        char a4,
        PVOID Buffer,
        PDEVICE_OBJECT DeviceObject)
{
  PIRP v8; // rax
  struct _DEVICE_OBJECT *v9; // rcx
  NTSTATUS v10; // eax
  __int64 v11; // r8
  struct _KEVENT Object; // [rsp+40h] [rbp-28h] BYREF
  union _LARGE_INTEGER StartingOffset; // [rsp+78h] [rbp+10h] BYREF

  StartingOffset = a2;
  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, NotificationEvent, 0);
  v8 = IoBuildSynchronousFsdRequest(
         3u,
         DeviceObject,
         Buffer,
         0x800u,
         &StartingOffset,
         &Object,
         (PIO_STATUS_BLOCK)(*(_QWORD *)(a1 + 8) + 48LL));
  if ( !v8 )
    CdRaiseStatusEx(a1, 3221225626LL, 0, 655360, 1163);
  v9 = DeviceObject;
  v8->Tail.Overlay.CurrentStackLocation[-1].Flags |= 2u;
  v10 = IofCallDriver(v9, v8);
  if ( v10 == 259 )
  {
    v10 = KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    if ( v10 < 0 )
      goto LABEL_6;
    v10 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
  }
  if ( v10 >= 0 )
    return 1;
LABEL_6:
  if ( !a4 )
  {
    LOBYTE(v11) = 1;
    CdRaiseStatusEx(a1, (unsigned int)v10, v11, 655360, 1209);
  }
  return 0;
}

```

## disassembly

```asm
0x140010c38  mov     r11, rsp
0x140010c3b  mov     [r11+8], rbx
0x140010c3f  mov     [r11+10h], rdx
0x140010c43  push    rdi
0x140010c44  sub     rsp, 60h
0x140010c48  xorps   xmm0, xmm0
0x140010c4b  mov     rbx, rcx
0x140010c4e  xor     eax, eax
0x140010c50  lea     rcx, [r11-28h]; Event
0x140010c54  movups  xmmword ptr [rsp+68h+Object.Header], xmm0
0x140010c59  xor     r8d, r8d; State
0x140010c5c  mov     [r11-18h], rax
0x140010c60  xor     edx, edx; Type
0x140010c62  mov     dil, r9b
0x140010c65  call    cs:__imp_KeInitializeEvent
0x140010c6c  nop     dword ptr [rax+rax+00h]
0x140010c71  mov     rax, [rbx+8]
0x140010c75  mov     r9d, 800h; Length
0x140010c7b  mov     r8, [rsp+68h+Buffer]; Buffer
0x140010c83  add     rax, 30h ; '0'
0x140010c87  mov     rdx, [rsp+68h+DeviceObject]; DeviceObject
0x140010c8f  mov     ecx, 3; MajorFunction
0x140010c94  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140010c99  lea     rax, [rsp+68h+Object]
0x140010c9e  mov     [rsp+68h+Event], rax; Event
0x140010ca3  lea     rax, [rsp+68h+arg_8]
0x140010ca8  mov     [rsp+68h+StartingOffset], rax; StartingOffset
0x140010cad  call    cs:__imp_IoBuildSynchronousFsdRequest
0x140010cb4  nop     dword ptr [rax+rax+00h]
0x140010cb9  mov     rdx, rax; Irp
0x140010cbc  test    rax, rax
0x140010cbf  jz      short loc_140010D2F
0x140010cc1  mov     rax, [rax+0B8h]
0x140010cc8  mov     rcx, [rsp+68h+DeviceObject]; DeviceObject
0x140010cd0  or      byte ptr [rax-46h], 2
0x140010cd4  call    cs:__imp_IofCallDriver
0x140010cdb  nop     dword ptr [rax+rax+00h]
0x140010ce0  cmp     eax, 103h
0x140010ce5  jnz     short loc_140010D14
0x140010ce7  xor     r9d, r9d; Alertable
0x140010cea  mov     [rsp+68h+StartingOffset], 0; Timeout
0x140010cf3  xor     r8d, r8d; WaitMode
0x140010cf6  lea     rcx, [rsp+68h+Object]; Object
0x140010cfb  xor     edx, edx; WaitReason
0x140010cfd  call    cs:__imp_KeWaitForSingleObject
0x140010d04  nop     dword ptr [rax+rax+00h]
0x140010d09  test    eax, eax
0x140010d0b  js      short loc_140010D18
0x140010d0d  mov     rax, [rbx+8]
0x140010d11  mov     eax, [rax+30h]
0x140010d14  test    eax, eax
0x140010d16  jns     short loc_140010D21
0x140010d18  test    dil, dil
0x140010d1b  jz      short loc_140010D4E
0x140010d1d  xor     al, al
0x140010d1f  jmp     short loc_140010D23
0x140010d21  mov     al, 1
0x140010d23  mov     rbx, [rsp+68h+arg_0]
0x140010d28  add     rsp, 60h
0x140010d2c  pop     rdi
0x140010d2d  retn
0x140010d2f  mov     r9d, 0A0000h
0x140010d35  mov     dword ptr [rsp+68h+StartingOffset], 48Bh
0x140010d3d  xor     r8d, r8d
0x140010d40  mov     edx, 0C000009Ah
0x140010d45  mov     rcx, rbx
0x140010d48  call    CdRaiseStatusEx
0x140010d4e  mov     r9d, 0A0000h
0x140010d54  mov     dword ptr [rsp+68h+StartingOffset], 4B9h
0x140010d5c  mov     r8b, 1
0x140010d5f  mov     edx, eax
0x140010d61  mov     rcx, rbx
0x140010d64  call    CdRaiseStatusEx
```
