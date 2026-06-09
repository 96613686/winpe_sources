# SecNotifyObtainFileHash

- ea: `0x140031c88`
- end: `0x140031eba`
- name: `SecNotifyObtainFileHash`
- size: `562`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140021b8c`
- `0x140022468`
- `0x140031b38`

## callees

- `0x1400100ec`
- `0x1400104af`
- `0x140011650`
- `0x1400119c0`
- `0x140030020`
- `0x14003044c`
- `0x140030758`
- `0x140031c88`
- `0x140031ebc`
- `0x140032adc`
- `0x14003a800`
- `0x14003a80c`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x140031d15`
- `ntoskrnl!ZwCreateEvent` at `0x140031d15`
- `ntoskrnl!ZwFsControlFile` at `0x140031da9`
- `ntoskrnl!ZwFsControlFile` at `0x140031da9`
- `ntoskrnl!ZwClose` at `0x140031e88`
- `ntoskrnl!ZwClose` at `0x140031e88`
- `ntoskrnl!ObfDereferenceObject` at `0x140031e73`
- `ntoskrnl!ObfDereferenceObject` at `0x140031e73`

## pseudocode

```c
__int64 __fastcall SecNotifyObtainFileHash(__int64 a1, _BYTE *a2)
{
  int FileSize_0; // ebx
  int v5; // eax
  struct _FILE_OBJECT *v6; // rdi
  NTSTATUS v7; // eax
  char IsFileEaCacheable; // r15
  _BYTE v10[8]; // [rsp+50h] [rbp-69h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-61h] BYREF
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-59h] BYREF
  void *EventHandle; // [rsp+68h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-49h] BYREF
  __int64 InputBuffer; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A8h] [rbp-11h]
  union _LARGE_INTEGER FileSize; // [rsp+B0h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-1h] BYREF
  __int128 OutputBuffer; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D8h] [rbp+1Fh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  FileObject = 0;
  FileHandle = 0;
  EventHandle = 0;
  InputBuffer = 0;
  v16 = 0;
  v20 = 0;
  v10[0] = 0;
  FileSize.QuadPart = 0;
  OutputBuffer = 0;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  FileSize_0 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( FileSize_0 >= 0 )
  {
    v5 = SecOpenFileForHashing(a1, &FileHandle, &FileObject, v10);
    v6 = FileObject;
    FileSize_0 = v5;
    if ( v5 >= 0 )
    {
      if ( !v10[0]
        || (v16 = 1,
            InputBuffer = 0x3000C0001LL,
            v7 = ZwFsControlFile(
                   FileHandle,
                   EventHandle,
                   0,
                   0,
                   &IoStatusBlock,
                   0x90240u,
                   &InputBuffer,
                   0xCu,
                   &OutputBuffer,
                   0x18u),
            FileSize_0 = v7,
            v7 == 259) )
      {
        memset(a2, 0, 0x94u);
        IsFileEaCacheable = SecCacheIsFileEaCacheable(v6);
        if ( IsFileEaCacheable && (FileSize_0 = SecCacheQueryFileHashEa(v6, a2), FileSize_0 >= 0) && *a2 == 3 )
        {
          SecIncrementEaCacheHitCounter();
        }
        else
        {
          SecIncrementEaCacheMissCounter();
          FileSize_0 = FsRtlGetFileSize_0(v6, &FileSize);
          if ( FileSize_0 >= 0 )
          {
            if ( FileSize.QuadPart )
            {
              FileSize_0 = SecCryptComputeFileHash(FileHandle, (ULONG *)&FileSize, a2);
              if ( FileSize_0 >= 0 )
              {
                if ( IsFileEaCacheable )
                {
                  _mm_lfence();
                  SecCacheSetFileHashEa(v6, a2);
                }
                FileSize_0 = 0;
              }
            }
            else
            {
              FileSize_0 = -1073741811;
            }
          }
        }
      }
      else if ( v7 >= 0 )
      {
        FileSize_0 = -1073741808;
      }
    }
    if ( FileHandle )
      FltClose_0(FileHandle);
    if ( v6 )
      ObfDereferenceObject(v6);
  }
  if ( EventHandle )
    ZwClose(EventHandle);
  return (unsigned int)FileSize_0;
}

```

## disassembly

```asm
0x140031c88  mov     [rsp-8+arg_10], rbx
0x140031c8d  push    rbp
0x140031c8e  push    rsi
0x140031c8f  push    rdi
0x140031c90  push    r12
0x140031c92  push    r15
0x140031c94  lea     rbp, [rsp-37h]
0x140031c99  sub     rsp, 0F0h
0x140031ca0  mov     rax, cs:__security_cookie
0x140031ca7  xor     rax, rsp
0x140031caa  mov     [rbp+57h+var_30], rax
0x140031cae  xor     r12d, r12d
0x140031cb1  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140031cb9  xor     eax, eax
0x140031cbb  mov     [rbp+57h+FileObject], r12
0x140031cbf  xorps   xmm0, xmm0
0x140031cc2  mov     [rbp+57h+FileHandle], r12
0x140031cc6  mov     rsi, rdx
0x140031cc9  mov     [rbp+57h+EventHandle], r12
0x140031ccd  mov     rdi, rcx
0x140031cd0  mov     [rbp+57h+var_70], rax
0x140031cd4  mov     edx, 1F0003h; DesiredAccess
0x140031cd9  mov     [rbp+57h+var_68], eax
0x140031cdc  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x140031ce0  mov     [rbp+57h+var_38], rax
0x140031ce4  xor     r9d, r9d; EventType
0x140031ce7  mov     [rbp+57h+var_C0], r12b
0x140031ceb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140031cef  mov     qword ptr [rbp+57h+FileSize], r12
0x140031cf3  movups  [rbp+57h+var_48], xmm0
0x140031cf7  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140031cfb  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140031cff  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x140031d03  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140031d08  mov     [rsp+110h+InitialState], r12b; InitialState
0x140031d0d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140031d15  call    cs:__imp_ZwCreateEvent
0x140031d1c  nop     dword ptr [rax+rax+00h]
0x140031d21  mov     ebx, eax
0x140031d23  test    eax, eax
0x140031d25  js      loc_140031E7F
0x140031d2b  lea     r9, [rbp+57h+var_C0]
0x140031d2f  mov     rcx, rdi
0x140031d32  lea     r8, [rbp+57h+FileObject]
0x140031d36  lea     rdx, [rbp+57h+FileHandle]
0x140031d3a  call    SecOpenFileForHashing
0x140031d3f  mov     rdi, [rbp+57h+FileObject]
0x140031d43  mov     ebx, eax
0x140031d45  test    eax, eax
0x140031d47  js      loc_140031E5C
0x140031d4d  cmp     [rbp+57h+var_C0], r12b
0x140031d51  jz      short loc_140031DD0
0x140031d53  mov     rdx, [rbp+57h+EventHandle]; Event
0x140031d57  lea     eax, [r12+1]
0x140031d5c  lea     ecx, [rax+0Bh]
0x140031d5f  mov     [rsp+110h+OutputBufferLength], 18h; OutputBufferLength
0x140031d67  mov     [rbp+57h+var_68], eax
0x140031d6a  xor     r9d, r9d; ApcContext
0x140031d6d  lea     rax, [rbp+57h+var_48]
0x140031d71  mov     dword ptr [rbp+57h+var_70], 0C0001h
0x140031d78  mov     [rsp+110h+OutputBuffer], rax; OutputBuffer
0x140031d7d  xor     r8d, r8d; ApcRoutine
0x140031d80  mov     [rsp+110h+InputBufferLength], ecx; InputBufferLength
0x140031d84  lea     rax, [rbp+57h+var_70]
0x140031d88  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031d8c  mov     [rsp+110h+InputBuffer], rax; InputBuffer
0x140031d91  lea     rax, [rbp+57h+IoStatusBlock]
0x140031d95  mov     [rsp+110h+FsControlCode], 90240h; FsControlCode
0x140031d9d  mov     qword ptr [rsp+110h+InitialState], rax; IoStatusBlock
0x140031da2  mov     dword ptr [rbp+57h+var_70+4], 3
0x140031da9  call    cs:__imp_ZwFsControlFile
0x140031db0  nop     dword ptr [rax+rax+00h]
0x140031db5  mov     ebx, eax
0x140031db7  cmp     eax, 103h
0x140031dbc  jz      short loc_140031DD0
0x140031dbe  test    eax, eax
0x140031dc0  js      loc_140031E5C
0x140031dc6  mov     ebx, 0C0000010h
0x140031dcb  jmp     loc_140031E5C
0x140031dd0  xor     edx, edx; Val
0x140031dd2  mov     r8d, 94h; Size
0x140031dd8  mov     rcx, rsi; void *
0x140031ddb  call    memset
0x140031de0  mov     rcx, rdi; FileObject
0x140031de3  call    SecCacheIsFileEaCacheable
0x140031de8  mov     r15b, al
0x140031deb  test    al, al
0x140031ded  jz      short loc_140031E0C
0x140031def  mov     rdx, rsi
0x140031df2  mov     rcx, rdi
0x140031df5  call    SecCacheQueryFileHashEa
0x140031dfa  mov     ebx, eax
0x140031dfc  test    eax, eax
0x140031dfe  js      short loc_140031E0C
0x140031e00  cmp     byte ptr [rsi], 3
0x140031e03  jnz     short loc_140031E0C
0x140031e05  call    SecIncrementEaCacheHitCounter
0x140031e0a  jmp     short loc_140031E5C
0x140031e0c  call    SecIncrementEaCacheMissCounter
0x140031e11  lea     rdx, [rbp+57h+FileSize]; FileSize
0x140031e15  mov     rcx, rdi; FileObject
0x140031e18  call    FsRtlGetFileSize_0
0x140031e1d  mov     ebx, eax
0x140031e1f  test    eax, eax
0x140031e21  js      short loc_140031E5C
0x140031e23  cmp     qword ptr [rbp+57h+FileSize], r12
0x140031e27  jnz     short loc_140031E30
0x140031e29  mov     ebx, 0C000000Dh
0x140031e2e  jmp     short loc_140031E5C
0x140031e30  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031e34  lea     rdx, [rbp+57h+FileSize]
0x140031e38  mov     r8, rsi
0x140031e3b  call    SecCryptComputeFileHash
0x140031e40  mov     ebx, eax
0x140031e42  test    eax, eax
0x140031e44  js      short loc_140031E5C
0x140031e46  test    r15b, r15b
0x140031e49  jz      short loc_140031E59
0x140031e4b  lfence
0x140031e4e  mov     rdx, rsi
0x140031e51  mov     rcx, rdi
0x140031e54  call    SecCacheSetFileHashEa
0x140031e59  mov     ebx, r12d
0x140031e5c  cmp     [rbp+57h+FileHandle], r12
0x140031e60  jz      short loc_140031E6B
0x140031e62  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031e66  call    FltClose_0
0x140031e6b  test    rdi, rdi
0x140031e6e  jz      short loc_140031E7F
0x140031e70  mov     rcx, rdi; Object
0x140031e73  call    cs:__imp_ObfDereferenceObject
0x140031e7a  nop     dword ptr [rax+rax+00h]
0x140031e7f  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140031e83  test    rcx, rcx
0x140031e86  jz      short loc_140031E94
0x140031e88  call    cs:__imp_ZwClose
0x140031e8f  nop     dword ptr [rax+rax+00h]
0x140031e94  mov     eax, ebx
0x140031e96  mov     rcx, [rbp+57h+var_30]
0x140031e9a  xor     rcx, rsp; StackCookie
0x140031e9d  call    __security_check_cookie
0x140031ea2  mov     rbx, [rsp+110h+arg_10]
0x140031eaa  add     rsp, 0F0h
0x140031eb1  pop     r15
0x140031eb3  pop     r12
0x140031eb5  pop     rdi
0x140031eb6  pop     rsi
0x140031eb7  pop     rbp
0x140031eb8  retn
```
