# PmIsSystemCriticalFlagNeeded(_DEVICE_EXTENSION *,ulong *,ulong *)

- ea: `0x14000cd18`
- end: `0x14000cda4`
- name: `?PmIsSystemCriticalFlagNeeded@@YAEPEAU_DEVICE_EXTENSION@@PEAK1@Z`
- size: `140`
- prototype: `unsigned __int8 __fastcall(struct _DEVICE_EXTENSION *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d048`
- `0x140020c40`

## callees

- `0x14000cd18`
- `0x14000e6f0`

## pseudocode

```c
unsigned __int8 __fastcall PmIsSystemCriticalFlagNeeded(
        struct _DEVICE_EXTENSION *a1,
        unsigned int *a2,
        unsigned int *a3)
{
  __int64 MSFTIdentifier; // rax

  MSFTIdentifier = StRtlFindMSFTIdentifier(*((_QWORD *)a1 + 31));
  if ( MSFTIdentifier )
  {
    if ( *(_QWORD *)(MSFTIdentifier + 8) == *(_QWORD *)&GUID_BOOT_DISK.Data1
      && *(_QWORD *)(MSFTIdentifier + 16) == *(_QWORD *)GUID_BOOT_DISK.Data4 )
    {
      if ( !a2 || *a2 == 1 )
      {
        *a3 = 536871168;
        return 1;
      }
    }
    else if ( *(_QWORD *)(MSFTIdentifier + 8) == *(_QWORD *)&GUID_SYSTEM_DISK.Data1
           && *(_QWORD *)(MSFTIdentifier + 16) == *(_QWORD *)GUID_SYSTEM_DISK.Data4
           && (!a2 || *a2 == 2) )
    {
      *a3 = 538968064;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000cd18  mov     [rsp+arg_0], rbx
0x14000cd1d  push    rdi
0x14000cd1e  sub     rsp, 20h
0x14000cd22  mov     rcx, [rcx+0F8h]
0x14000cd29  mov     rdi, r8
0x14000cd2c  mov     rbx, rdx
0x14000cd2f  call    StRtlFindMSFTIdentifier
0x14000cd34  mov     rdx, rax
0x14000cd37  test    rax, rax
0x14000cd3a  jz      short loc_14000CD96
0x14000cd3c  mov     rcx, [rax+8]
0x14000cd40  cmp     rcx, qword ptr cs:?GUID_BOOT_DISK@@3U_GUID@@B.Data1; _GUID const GUID_BOOT_DISK ...
0x14000cd47  jnz     short loc_14000CD6A
0x14000cd49  mov     rcx, [rax+10h]
0x14000cd4d  cmp     rcx, qword ptr cs:?GUID_BOOT_DISK@@3U_GUID@@B.Data4; _GUID const GUID_BOOT_DISK ...
0x14000cd54  jnz     short loc_14000CD6A
0x14000cd56  test    rbx, rbx
0x14000cd59  jz      short loc_14000CD60
0x14000cd5b  cmp     dword ptr [rbx], 1
0x14000cd5e  jnz     short loc_14000CD96
0x14000cd60  mov     dword ptr [rdi], 20000100h
0x14000cd66  mov     al, 1
0x14000cd68  jmp     short loc_14000CD98
0x14000cd6a  mov     rax, [rax+8]
0x14000cd6e  cmp     rax, qword ptr cs:?GUID_SYSTEM_DISK@@3U_GUID@@B.Data1; _GUID const GUID_SYSTEM_DISK ...
0x14000cd75  jnz     short loc_14000CD96
0x14000cd77  mov     rax, [rdx+10h]
0x14000cd7b  cmp     rax, qword ptr cs:?GUID_SYSTEM_DISK@@3U_GUID@@B.Data4; _GUID const GUID_SYSTEM_DISK ...
0x14000cd82  jnz     short loc_14000CD96
0x14000cd84  test    rbx, rbx
0x14000cd87  jz      short loc_14000CD8E
0x14000cd89  cmp     dword ptr [rbx], 2
0x14000cd8c  jnz     short loc_14000CD96
0x14000cd8e  mov     dword ptr [rdi], 20200000h
0x14000cd94  jmp     short loc_14000CD66
0x14000cd96  xor     al, al
0x14000cd98  mov     rbx, [rsp+28h+arg_0]
0x14000cd9d  add     rsp, 20h
0x14000cda1  pop     rdi
0x14000cda2  retn
```
