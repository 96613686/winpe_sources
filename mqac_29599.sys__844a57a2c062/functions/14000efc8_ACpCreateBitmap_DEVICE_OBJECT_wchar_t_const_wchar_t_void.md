# ACpCreateBitmap(_DEVICE_OBJECT *,wchar_t const *,wchar_t * *,void * *)

- ea: `0x14000efc8`
- end: `0x14000f1fd`
- name: `?ACpCreateBitmap@@YAPEAVCPingPong@@PEAU_DEVICE_OBJECT@@PEB_WPEAPEA_WPEAPEAX@Z`
- size: `565`
- prototype: `struct CPingPong *(struct _DEVICE_OBJECT *, const wchar_t *, wchar_t **, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000f950`
- `0x140010984`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001c34`
- `0x14000ef28`
- `0x14000efc8`
- `0x14000f390`
- `0x14001105c`
- `0x1400110d0`
- `0x140024fc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000f093`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f093`
- `ntoskrnl!ZwCreateFile` at `0x14000f126`
- `ntoskrnl!ZwCreateFile` at `0x14000f126`

## pseudocode

```c
struct CPingPong *__fastcall ACpCreateBitmap(struct _DEVICE_OBJECT *a1, wchar_t *a2, wchar_t **a3, void **a4)
{
  char *v7; // rax
  CPingPong *v8; // rbx
  const WCHAR *FileName; // rax
  unsigned int v11; // edx
  WCHAR *v12; // rdi
  NTSTATUS v13; // eax
  unsigned int v14; // edx
  void *v15; // rax
  union _LARGE_INTEGER AllocationSize; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+67h] BYREF

  v7 = (char *)operator new(0x1000u, 0x100u, 0x4841514Du, LowPoolPriority);
  v8 = (CPingPong *)v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, &WPP_664e97eed756311217f592c2f10907d7_Traceguids, 4096);
    }
    return 0;
  }
  *(_QWORD *)(v7 + 4) = 0;
  *((_DWORD *)v7 + 3) = 32640;
  memset(v7 + 16, 0, 0xFF0u);
  FileName = (const WCHAR *)ACpGenerateFileName(a2);
  v12 = (WCHAR *)FileName;
  if ( !FileName )
  {
    CPingPong::`scalar deleting destructor'(v8, v11);
    return 0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  AllocationSize.QuadPart = 0x2000;
  v13 = ZwCreateFile(
          &FileHandle,
          0xC0100000,
          &ObjectAttributes,
          &IoStatusBlock,
          &AllocationSize,
          0x80u,
          1u,
          3u,
          0x2Au,
          0,
          0);
  *(_DWORD *)v8 = 2053468741;
  if ( v13 < 0 )
  {
    if ( v13 == -1073741790 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, v13, (_DWORD)v12, 34);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, v13, (_DWORD)v12, v13);
    }
    CPingPong::`scalar deleting destructor'(v8, v14);
    operator delete(v12);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_S(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 17, (unsigned int)v13, v12);
  }
  v15 = FileHandle;
  *a3 = v12;
  *a4 = v15;
  return v8;
}

```

## disassembly

```asm
0x14000efc8  push    rbp
0x14000efca  push    rbx
0x14000efcb  push    rsi
0x14000efcc  push    rdi
0x14000efcd  push    r14
0x14000efcf  push    r15
0x14000efd1  lea     rbp, [rsp-2Fh]
0x14000efd6  sub     rsp, 0C8h
0x14000efdd  mov     r15, [rcx+40h]
0x14000efe1  mov     rsi, r9
0x14000efe4  mov     r14, r8
0x14000efe7  mov     rdi, rdx
0x14000efea  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000efed  mov     edx, 100h; unsigned __int64
0x14000eff2  mov     ecx, 1000h; unsigned __int64
0x14000eff7  mov     r8d, 4841514Dh; unsigned int
0x14000effd  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000f002  mov     rbx, rax
0x14000f005  test    rax, rax
0x14000f008  jnz     short loc_14000F044
0x14000f00a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f011  lea     rax, WPP_GLOBAL_Control
0x14000f018  cmp     rcx, rax
0x14000f01b  jz      short loc_14000F03D
0x14000f01d  mov     eax, [rcx+6Ch]
0x14000f020  test    al, 1
0x14000f022  jz      short loc_14000F03D
0x14000f024  mov     rcx, [rcx+58h]
0x14000f028  lea     edx, [rbx+0Eh]
0x14000f02b  mov     r9d, 1000h
0x14000f031  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000f038  call    WPP_SF_d
0x14000f03d  xor     eax, eax
0x14000f03f  jmp     loc_14000F1EC
0x14000f044  lea     rcx, [rax+10h]; void *
0x14000f048  mov     qword ptr [rax+4], 0
0x14000f050  xor     edx, edx; Val
0x14000f052  mov     dword ptr [rax+0Ch], 7F80h
0x14000f059  mov     r8d, 0FF0h; Size
0x14000f05f  call    memset
0x14000f064  mov     edx, [r15+148h]
0x14000f06b  mov     rcx, rdi; wchar_t *
0x14000f06e  call    ACpGenerateFileName
0x14000f073  mov     rdi, rax
0x14000f076  test    rax, rax
0x14000f079  jnz     short loc_14000F085
0x14000f07b  mov     rcx, rbx; this
0x14000f07e  call    ??_GCPingPong@@QEAAPEAXI@Z; CPingPong::`scalar deleting destructor'(uint)
0x14000f083  jmp     short loc_14000F03D
0x14000f085  xorps   xmm0, xmm0
0x14000f088  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f08c  mov     rdx, rdi; SourceString
0x14000f08f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f093  call    cs:__imp_RtlInitUnicodeString
0x14000f09a  nop     dword ptr [rax+rax+00h]
0x14000f09f  mov     [rsp+0F0h+EaLength], 0; EaLength
0x14000f0a7  lea     rax, [rbp+57h+DestinationString]
0x14000f0ab  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x14000f0b4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000f0b8  mov     [rsp+0F0h+CreateOptions], 2Ah ; '*'; CreateOptions
0x14000f0c0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f0c4  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x14000f0cc  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000f0d0  xorps   xmm0, xmm0
0x14000f0d3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000f0d7  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x14000f0df  lea     rax, [rbp+57h+var_90]
0x14000f0e3  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x14000f0eb  mov     edx, 0C0100000h; DesiredAccess
0x14000f0f0  mov     [rsp+0F0h+AllocationSize], rax; AllocationSize
0x14000f0f5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f0fd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000f105  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000f10d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f112  mov     [rbp+57h+FileHandle], 0
0x14000f11a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000f11e  mov     qword ptr [rbp+57h+var_90], 2000h
0x14000f126  call    cs:__imp_ZwCreateFile
0x14000f12d  nop     dword ptr [rax+rax+00h]
0x14000f132  mov     dword ptr [rbx], 7A657245h
0x14000f138  mov     r8d, eax
0x14000f13b  test    eax, eax
0x14000f13d  jns     short loc_14000F1B4
0x14000f13f  cmp     eax, 0C0000022h
0x14000f144  jnz     short loc_14000F16F
0x14000f146  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f14d  lea     rax, WPP_GLOBAL_Control
0x14000f154  cmp     rcx, rax
0x14000f157  jz      short loc_14000F19F
0x14000f159  mov     eax, [rcx+6Ch]
0x14000f15c  test    al, 1
0x14000f15e  jz      short loc_14000F19F
0x14000f160  mov     edx, 0Fh
0x14000f165  mov     dword ptr [rsp+0F0h+AllocationSize], 0C0000022h
0x14000f16d  jmp     short loc_14000F193
0x14000f16f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f176  lea     rax, WPP_GLOBAL_Control
0x14000f17d  cmp     rcx, rax
0x14000f180  jz      short loc_14000F19F
0x14000f182  mov     eax, [rcx+6Ch]
0x14000f185  test    al, 1
0x14000f187  jz      short loc_14000F19F
0x14000f189  mov     edx, 10h
0x14000f18e  mov     dword ptr [rsp+0F0h+AllocationSize], r8d
0x14000f193  mov     rcx, [rcx+58h]
0x14000f197  mov     r9, rdi
0x14000f19a  call    WPP_SF_Sd
0x14000f19f  mov     rcx, rbx; this
0x14000f1a2  call    ??_GCPingPong@@QEAAPEAXI@Z; CPingPong::`scalar deleting destructor'(uint)
0x14000f1a7  mov     rcx, rdi; void *
0x14000f1aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000f1af  jmp     loc_14000F03D
0x14000f1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1bb  lea     rax, WPP_GLOBAL_Control
0x14000f1c2  cmp     rcx, rax
0x14000f1c5  jz      short loc_14000F1DF
0x14000f1c7  mov     eax, [rcx+6Ch]
0x14000f1ca  test    al, 4
0x14000f1cc  jz      short loc_14000F1DF
0x14000f1ce  mov     rcx, [rcx+58h]
0x14000f1d2  mov     edx, 11h
0x14000f1d7  mov     r9, rdi
0x14000f1da  call    WPP_SF_S
0x14000f1df  mov     rax, [rbp+57h+FileHandle]
0x14000f1e3  mov     [r14], rdi
0x14000f1e6  mov     [rsi], rax
0x14000f1e9  mov     rax, rbx
0x14000f1ec  add     rsp, 0C8h
0x14000f1f3  pop     r15
0x14000f1f5  pop     r14
0x14000f1f7  pop     rdi
0x14000f1f8  pop     rsi
0x14000f1f9  pop     rbx
0x14000f1fa  pop     rbp
0x14000f1fb  retn
```
