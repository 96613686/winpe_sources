# CNtfsStorage::OpenNtFileHandle(_UNICODE_STRING const &,void *,void *,ulong,ulong,int,void * *)

- ea: `0x180034068`
- end: `0x1800341ec`
- name: `?OpenNtFileHandle@CNtfsStorage@@CAJAEBU_UNICODE_STRING@@PEAX1KKHPEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void *, void *, unsigned int, unsigned int, int, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003340c`
- `0x180033810`
- `0x18003e304`
- `0x180053b80`

## callees

- `0x180034068`
- `0x1800341f4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18003412b`
- `ntdll!NtCreateFile` at `0x18003412b`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::OpenNtFileHandle(
        struct _UNICODE_STRING *a1,
        void *a2,
        void *a3,
        int a4,
        unsigned int a5,
        int a6,
        void **a7)
{
  ULONG ShareAccess; // r8d
  ACCESS_MASK v8; // edx
  int v9; // eax
  int v10; // r9d
  ULONG CreateDisposition; // ecx
  NTSTATUS v12; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-1h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+Fh] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+4Fh] BYREF

  ObjectAttributes.SecurityDescriptor = a3;
  ShareAccess = 7;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.SecurityQualityOfService = 0;
  IoStatusBlock = 0;
  if ( (a4 & 7) != 0 )
  {
    switch ( a4 & 7 )
    {
      case 1:
        v8 = ~(a5 << 14) & 0x10000 | 0x120116;
        break;
      case 2:
        v8 = ~(a5 << 14) & 0x10000 | 0x12019F;
        break;
      case 4:
        v8 = 1048704;
        break;
      default:
        return 2147680511LL;
    }
  }
  else
  {
    v8 = 1179785;
  }
  v9 = a4 & 0x70;
  if ( (a4 & 0x70) != 0 )
  {
    switch ( v9 )
    {
      case 16:
        ShareAccess = 0;
        break;
      case 32:
        ShareAccess = 1;
        break;
      case 48:
        ShareAccess = 6;
        break;
      case 64:
        break;
      default:
        return 2147680511LL;
    }
  }
  v10 = a4 & 0x21000;
  if ( !v10 )
  {
    CreateDisposition = (a6 != 0) + 1;
    goto LABEL_8;
  }
  if ( v10 != 4096 )
    return 2147680511LL;
  CreateDisposition = a6 != 0 ? 5 : 3;
LABEL_8:
  v12 = NtCreateFile(
          &FileHandle,
          v8,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          ShareAccess,
          CreateDisposition,
          0x20u,
          0,
          0);
  if ( v12 < 0 )
    return NtStatusToScode(v12);
  *a7 = FileHandle;
  return 0;
}

```

## disassembly

```asm
0x180034068  push    rbp
0x18003406a  lea     rbp, [rsp-3Fh]
0x18003406f  sub     rsp, 0A0h
0x180034076  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], r8
0x18003407a  mov     eax, r9d
0x18003407d  mov     r8d, 7
0x180034083  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18003408b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180034093  xorps   xmm0, xmm0
0x180034096  mov     [rbp+3Fh+FileHandle], 0
0x18003409e  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdx
0x1800340a2  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rcx
0x1800340a6  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x1800340ae  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1800340b2  and     eax, r8d
0x1800340b5  jnz     loc_180034154
0x1800340bb  mov     edx, 120089h; DesiredAccess
0x1800340c0  mov     eax, r9d
0x1800340c3  and     eax, 70h
0x1800340c6  jz      short loc_1800340D4
0x1800340c8  cmp     eax, 10h
0x1800340cb  jnz     loc_1800341A6
0x1800340d1  xor     r8d, r8d
0x1800340d4  and     r9d, 21000h
0x1800340db  jnz     loc_1800341D1
0x1800340e1  mov     eax, [rbp+3Fh+arg_28]
0x1800340e4  neg     eax
0x1800340e6  sbb     ecx, ecx
0x1800340e8  neg     ecx
0x1800340ea  inc     ecx
0x1800340ec  mov     [rsp+0A0h+EaLength], 0; EaLength
0x1800340f4  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1800340f8  mov     [rsp+0A0h+EaBuffer], 0; EaBuffer
0x180034101  mov     [rsp+0A0h+CreateOptions], 20h ; ' '; CreateOptions
0x180034109  mov     [rsp+0A0h+CreateDisposition], ecx; CreateDisposition
0x18003410d  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180034111  mov     [rsp+0A0h+ShareAccess], r8d; ShareAccess
0x180034116  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18003411a  mov     [rsp+0A0h+FileAttributes], 80h; FileAttributes
0x180034122  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x18003412b  call    cs:__imp_NtCreateFile
0x180034131  test    eax, eax
0x180034133  js      short loc_18003414B
0x180034135  mov     rax, [rbp+3Fh+arg_30]
0x180034139  mov     rcx, [rbp+3Fh+FileHandle]
0x18003413d  mov     [rax], rcx
0x180034140  xor     eax, eax
0x180034142  add     rsp, 0A0h
0x180034149  pop     rbp
0x18003414a  retn
0x18003414b  mov     ecx, eax; int
0x18003414d  call    ?NtStatusToScode@@YAJJ@Z; NtStatusToScode(long)
0x180034152  jmp     short loc_180034142
0x180034154  sub     eax, 1
0x180034157  jz      short loc_18003418D
0x180034159  sub     eax, 1
0x18003415c  jz      short loc_180034174
0x18003415e  cmp     eax, 2
0x180034161  jz      short loc_18003416A
0x180034163  mov     eax, 800300FFh
0x180034168  jmp     short loc_180034142
0x18003416a  mov     edx, 100080h
0x18003416f  jmp     loc_1800340C0
0x180034174  mov     edx, [rbp+3Fh+arg_20]
0x180034177  shl     edx, 0Eh
0x18003417a  not     edx
0x18003417c  and     edx, 10000h
0x180034182  or      edx, 12019Fh
0x180034188  jmp     loc_1800340C0
0x18003418d  mov     edx, [rbp+3Fh+arg_20]
0x180034190  shl     edx, 0Eh
0x180034193  not     edx
0x180034195  and     edx, 10000h
0x18003419b  or      edx, 120116h
0x1800341a1  jmp     loc_1800340C0
0x1800341a6  cmp     eax, 20h ; ' '
0x1800341a9  jz      short loc_1800341C6
0x1800341ab  cmp     eax, 30h ; '0'
0x1800341ae  jz      short loc_1800341BB
0x1800341b0  cmp     eax, 40h ; '@'
0x1800341b3  jz      loc_1800340D4
0x1800341b9  jmp     short loc_180034163
0x1800341bb  mov     r8d, 6
0x1800341c1  jmp     loc_1800340D4
0x1800341c6  mov     r8d, 1
0x1800341cc  jmp     loc_1800340D4
0x1800341d1  cmp     r9d, 1000h
0x1800341d8  jnz     short loc_180034163
0x1800341da  mov     eax, [rbp+3Fh+arg_28]
0x1800341dd  neg     eax
0x1800341df  sbb     ecx, ecx
0x1800341e1  and     ecx, 2
0x1800341e4  add     ecx, 3
0x1800341e7  jmp     loc_1800340EC
```
