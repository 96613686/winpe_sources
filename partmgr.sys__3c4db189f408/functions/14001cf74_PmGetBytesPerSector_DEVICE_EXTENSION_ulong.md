# PmGetBytesPerSector(_DEVICE_EXTENSION *,ulong *)

- ea: `0x14001cf74`
- end: `0x14001cfed`
- name: `?PmGetBytesPerSector@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z`
- size: `121`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001c764`
- `0x14001cde0`

## callees

- `0x140010f20`
- `0x14001cf74`
- `0x14001ff00`

## pseudocode

```c
__int64 __fastcall PmGetBytesPerSector(struct _DEVICE_EXTENSION *a1, unsigned int *a2)
{
  struct _DEVICE_OBJECT *v3; // r8
  __int64 v4; // rax
  int DriveGeometry; // edx
  struct _DISK_GEOMETRY v7; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
  memset(&v7, 0, sizeof(v7));
  if ( (v3->Characteristics & 1) != 0 || (v4 = *((_QWORD *)a1 + 33)) == 0 )
  {
    DriveGeometry = PmGetDriveGeometry(v3, &v7);
    if ( DriveGeometry >= 0 )
      *a2 = v7.BytesPerSector;
  }
  else
  {
    DriveGeometry = 0;
    *a2 = *(_DWORD *)(v4 + 16);
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x14001cf74  push    rbx
0x14001cf76  sub     rsp, 40h
0x14001cf7a  mov     rax, cs:__security_cookie
0x14001cf81  xor     rax, rsp
0x14001cf84  mov     [rsp+48h+var_10], rax
0x14001cf89  xor     eax, eax
0x14001cf8b  xorps   xmm0, xmm0
0x14001cf8e  mov     [rdx], eax
0x14001cf90  mov     rbx, rdx
0x14001cf93  mov     r8, [rcx+8]
0x14001cf97  movups  xmmword ptr [rsp+48h+var_28.Cylinders], xmm0
0x14001cf9c  mov     qword ptr [rsp+48h+var_28.SectorsPerTrack], rax
0x14001cfa1  mov     eax, [r8+34h]
0x14001cfa5  test    al, 1
0x14001cfa7  jnz     short loc_14001CFBE
0x14001cfa9  mov     rax, [rcx+108h]
0x14001cfb0  test    rax, rax
0x14001cfb3  jz      short loc_14001CFBE
0x14001cfb5  mov     eax, [rax+10h]
0x14001cfb8  xor     edx, edx
0x14001cfba  mov     [rbx], eax
0x14001cfbc  jmp     short loc_14001CFD7
0x14001cfbe  lea     rdx, [rsp+48h+var_28]; struct _DISK_GEOMETRY *
0x14001cfc3  mov     rcx, r8; struct _DEVICE_OBJECT *
0x14001cfc6  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x14001cfcb  mov     edx, eax
0x14001cfcd  test    eax, eax
0x14001cfcf  js      short loc_14001CFD7
0x14001cfd1  mov     ecx, [rsp+48h+var_28.BytesPerSector]
0x14001cfd5  mov     [rbx], ecx
0x14001cfd7  mov     eax, edx
0x14001cfd9  mov     rcx, [rsp+48h+var_10]
0x14001cfde  xor     rcx, rsp; StackCookie
0x14001cfe1  call    __security_check_cookie
0x14001cfe6  add     rsp, 40h
0x14001cfea  pop     rbx
0x14001cfeb  retn
```
