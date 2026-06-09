# CreateDevice(ushort const *,ushort const *,ulong,int,CreateStorageDeviceFlags,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x180096f1c`
- end: `0x180097396`
- name: `?CreateDevice@@YAPEAXPEBG0KHW4CreateStorageDeviceFlags@@PEBU_GUID@@PEBDK2@Z`
- size: `1146`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009739c`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180007fd5`
- `0x180096d5c`
- `0x180096e1c`
- `0x180096f1c`
- `0x18009754c`
- `0x180097cf4`
- `0x180098204`
- `0x180098600`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097322`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097322`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009710e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009710e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009732a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009732a`
- `ntdll!NtCreateFile` at `0x18009728e`
- `ntdll!NtCreateFile` at `0x18009728e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180097058`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180097058`
- `ntdll!RtlNtStatusToDosError` at `0x180097064`
- `ntdll!RtlNtStatusToDosError` at `0x180097188`
- `ntdll!RtlNtStatusToDosError` at `0x1800972e8`
- `ntdll!RtlNtStatusToDosError` at `0x180097064`
- `ntdll!RtlNtStatusToDosError` at `0x180097188`
- `ntdll!RtlNtStatusToDosError` at `0x1800972e8`
- `ntdll!RtlFreeUnicodeString` at `0x180097310`
- `ntdll!RtlFreeUnicodeString` at `0x180097310`
- `ntdll!RtlInitUnicodeStringEx` at `0x18009717c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18009717c`

## string_xrefs

- `0x180096fc2`: `VstorCreateDevice`
- `0x180097212`: `VstorCreateDevice_CreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CreateDevice(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        struct _GUID *a6,
        char *a7,
        unsigned int a8,
        struct _GUID *a9)
{
  char *v13; // r15
  __int64 v14; // rdi
  signed int v15; // ebx
  unsigned int v16; // r12d
  const wchar_t *v17; // r13
  int inited; // eax
  PWSTR Buffer; // r14
  __int16 v20; // cx
  int v21; // eax
  __int64 v22; // rbx
  size_t v23; // rbx
  char *v24; // rsi
  __int64 v25; // rbx
  int v26; // edi
  void *v27; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  int EaBuffer; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v35; // [rsp+C4h] [rbp-3Ch]
  struct _GUID v36; // [rsp+D4h] [rbp-2Ch]
  __int64 v37; // [rsp+E4h] [rbp-1Ch]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v40[42]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v41[42]; // [rsp+260h] [rbp+160h] BYREF

  FileHandle = (void *)-1LL;
  UnicodeString = 0;
  v13 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  EaBuffer = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  memset_0(v40, 0, sizeof(v40));
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v40,
    "VstorCreateDevice");
  v40[0] = &VstorlibTraceProvider::VstorCreateDevice::`vftable';
  VstorlibTraceProvider::VstorCreateDevice::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice *)v40,
    a1,
    (const unsigned __int16 *)a2,
    a3,
    a4,
    0x40u,
    a6,
    a7,
    a8,
    a9);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  if ( !v14 )
  {
    v15 = 87;
    goto LABEL_37;
  }
  v16 = 0;
  v17 = 0;
  if ( a4 )
  {
    inited = RtlDosPathNameToNtPathName_U_WithStatus(a2, &UnicodeString, 0, 0);
    if ( inited < 0 )
    {
LABEL_27:
      v15 = RtlNtStatusToDosError(inited);
      goto LABEL_37;
    }
    LODWORD(v14) = UnicodeString.Length >> 1;
    Buffer = UnicodeString.Buffer;
  }
  else if ( (unsigned int)v14 > 2 && *(_WORD *)a2 == 92 && (Buffer = (PWSTR)(a2 + 2), *(_WORD *)(a2 + 2) == 92) )
  {
    v20 = *(_WORD *)(a2 + 4);
    v21 = v14 - 1;
    if ( v20 == 63 )
      v21 = v14;
    LODWORD(v14) = v21;
    if ( v20 == 63 )
      Buffer = (PWSTR)a2;
    v16 = v20 != 63 ? 7 : 0;
    v17 = L"\\\\?\\UNC";
    if ( v20 == 63 )
      v17 = 0;
  }
  else
  {
    Buffer = (PWSTR)a2;
    if ( (unsigned int)v14 > 0x104 )
    {
      v16 = 4;
      v17 = L"\\\\?\\";
    }
  }
  v22 = -1;
  do
    ++v22;
  while ( a1[v22] );
  v13 = (char *)malloc(saturated_mul((unsigned int)v22 + v16 + (_DWORD)v14 + 1, 2u));
  if ( !v13 )
  {
    v15 = 14;
    goto LABEL_37;
  }
  v23 = 2LL * (unsigned int)v22;
  memcpy_0(v13, a1, v23);
  v24 = &v13[v23];
  if ( v16 )
  {
    memcpy_0(v24, v17, 2LL * v16);
    v24 += 2 * v16;
  }
  memcpy_0(v24, Buffer, 2LL * (unsigned int)v14);
  *(_WORD *)&v24[2 * (unsigned int)v14] = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)v13);
  if ( inited < 0 )
    goto LABEL_27;
  BYTE1(v35) = 10;
  WORD1(v35) = 25;
  *(_QWORD *)((char *)&v35 + 4) = *(_QWORD *)"StorVsp-v2";
  *(_DWORD *)((char *)&v35 + 11) = *(_DWORD *)"-v2";
  HIDWORD(v37) = 64;
  if ( a6 )
  {
    v36 = *a6;
    LOBYTE(v37) = 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  memset_0(v41, 0, sizeof(v41));
  v25 = v40[34];
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v41,
    "VstorCreateDevice_CreateFile");
  v41[0] = &VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable';
  VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice_CreateFile *)v41,
    &DestinationString,
    a6,
    (const struct _GUID *)(v25 + 8));
  v26 = NtCreateFile(&FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 2u, 0x40u, &EaBuffer, 0x2Cu);
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v41,
    (v26 | 0x10000000) & (unsigned int)-(v26 != 0));
  v41[0] = &VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable';
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v41);
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v41);
  if ( v26 >= 0 )
  {
    v15 = 0;
  }
  else if ( v26 == -1073741808 || v26 == -1073741766 )
  {
    v15 = -1069940716;
  }
  else
  {
    v15 = RtlNtStatusToDosError(v26);
    if ( v15 == 317 )
      v15 = v26;
  }
LABEL_37:
  if ( UnicodeString.Buffer )
  {
    RtlFreeUnicodeString(&UnicodeString);
    UnicodeString.Buffer = 0;
  }
  if ( v13 )
    free(v13);
  SetLastError(v15);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40, (unsigned int)v15);
  v27 = FileHandle;
  v40[0] = &VstorlibTraceProvider::VstorCreateDevice::`vftable';
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v40);
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v40);
  return v27;
}

```

## disassembly

```asm
0x180096f1c  mov     [rsp-8+arg_18], rbx
0x180096f21  push    rbp
0x180096f22  push    rsi
0x180096f23  push    rdi
0x180096f24  push    r12
0x180096f26  push    r13
0x180096f28  push    r14
0x180096f2a  push    r15
0x180096f2c  lea     rbp, [rsp-2C0h]
0x180096f34  sub     rsp, 3C0h
0x180096f3b  mov     rax, cs:__security_cookie
0x180096f42  xor     rax, rsp
0x180096f45  mov     [rbp+2F0h+var_40], rax
0x180096f4c  mov     r14d, r9d
0x180096f4f  mov     r13d, r8d
0x180096f52  mov     [rsp+3F0h+DesiredAccess], r8d
0x180096f57  mov     rsi, rdx
0x180096f5a  mov     r12, rcx
0x180096f5d  mov     [rsp+3F0h+Src], rcx
0x180096f62  mov     rdi, [rbp+2F0h+arg_28]
0x180096f69  mov     [rsp+3F0h+var_380], rdi
0x180096f6e  mov     rbx, [rbp+2F0h+arg_30]
0x180096f75  mov     [rbp+2F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180096f7d  xorps   xmm0, xmm0
0x180096f80  movups  xmmword ptr [rsp+3F0h+UnicodeString.Length], xmm0
0x180096f85  xor     eax, eax
0x180096f87  mov     r15d, eax
0x180096f8a  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x180096f8e  xorps   xmm1, xmm1
0x180096f91  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.Length], xmm1
0x180096f95  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.ObjectName], xmm1
0x180096f99  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180096f9d  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm0
0x180096fa1  mov     [rbp+2F0h+var_330], eax
0x180096fa4  movups  [rbp+2F0h+var_32C], xmm1
0x180096fa8  movups  [rbp+2F0h+var_31C], xmm1
0x180096fac  mov     [rbp+2F0h+var_30C], rax
0x180096fb0  xor     edx, edx; Val
0x180096fb2  mov     r8d, 150h; Size
0x180096fb8  lea     rcx, [rbp+2F0h+var_2E0]; void *
0x180096fbc  call    memset_0
0x180096fc1  nop
0x180096fc2  lea     rdx, aVstorcreatedev_1; "VstorCreateDevice"
0x180096fc9  lea     rcx, [rbp+2F0h+var_2E0]
0x180096fcd  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180096fd2  lea     rax, ??_7VstorCreateDevice@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice::`vftable'
0x180096fd9  mov     [rbp+2F0h+var_2E0], rax
0x180096fdd  mov     rax, [rbp+2F0h+arg_40]
0x180096fe4  mov     [rsp+3F0h+EaBuffer], rax; struct _GUID *
0x180096fe9  mov     eax, [rbp+2F0h+arg_38]
0x180096fef  mov     [rsp+3F0h+CreateOptions], eax; unsigned int
0x180096ff3  mov     qword ptr [rsp+3F0h+CreateDisposition], rbx; char *
0x180096ff8  mov     qword ptr [rsp+3F0h+ShareAccess], rdi; struct _GUID *
0x180096ffd  mov     [rsp+3F0h+FileAttributes], 40h ; '@'; unsigned int
0x180097005  mov     dword ptr [rsp+3F0h+AllocationSize], r14d; int
0x18009700a  mov     r9d, r13d; unsigned int
0x18009700d  mov     r8, rsi; unsigned __int16 *
0x180097010  mov     rdx, r12; unsigned __int16 *
0x180097013  lea     rcx, [rbp+2F0h+var_2E0]; this
0x180097017  call    ?StartActivity@VstorCreateDevice@VstorlibTraceProvider@@QEAAXPEBG0KHIPEBU_GUID@@PEBDK1@Z; VstorlibTraceProvider::VstorCreateDevice::StartActivity(ushort const *,ushort const *,ulong,int,uint,_GUID const *,char const *,ulong,_GUID const *)
0x18009701c  nop
0x18009701d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180097021  mov     rdi, r8
0x180097024  xor     ebx, ebx
0x180097026  inc     rdi
0x180097029  cmp     [rsi+rdi*2], bx
0x18009702d  jnz     short loc_180097026
0x18009702f  test    rdi, rdi
0x180097032  jnz     short loc_18009703F
0x180097034  lea     ebx, [rdi+57h]
0x180097037  xor     r14d, r14d
0x18009703a  jmp     loc_180097305
0x18009703f  mov     r12d, ebx
0x180097042  mov     r13, rbx
0x180097045  test    r14d, r14d
0x180097048  jz      short loc_18009707F
0x18009704a  xor     r9d, r9d
0x18009704d  xor     r8d, r8d
0x180097050  lea     rdx, [rsp+3F0h+UnicodeString]
0x180097055  mov     rcx, rsi
0x180097058  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18009705e  test    eax, eax
0x180097060  jns     short loc_18009706E
0x180097062  mov     ecx, eax; Status
0x180097064  call    cs:__imp_RtlNtStatusToDosError
0x18009706a  mov     ebx, eax
0x18009706c  jmp     short loc_180097037
0x18009706e  movzx   edi, [rsp+3F0h+UnicodeString.Length]
0x180097073  shr     edi, 1
0x180097075  mov     r14, [rbp+2F0h+UnicodeString.Buffer]
0x180097079  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009707d  jmp     short loc_1800970E4
0x18009707f  cmp     edi, 2
0x180097082  jbe     short loc_1800970CC
0x180097084  cmp     word ptr [rsi], 5Ch ; '\'
0x180097088  jnz     short loc_1800970CC
0x18009708a  lea     r14, [rsi+2]
0x18009708e  cmp     word ptr [r14], 5Ch ; '\'
0x180097093  jnz     short loc_1800970CC
0x180097095  movzx   ecx, word ptr [rsi+4]
0x180097099  lea     eax, [rdi-1]
0x18009709c  mov     dx, 3Fh ; '?'
0x1800970a0  cmp     cx, dx
0x1800970a3  cmovz   eax, edi
0x1800970a6  mov     edi, eax
0x1800970a8  cmovz   r14, rsi
0x1800970ac  movzx   eax, cx
0x1800970af  sub     ax, dx
0x1800970b2  neg     ax
0x1800970b5  sbb     r12d, r12d
0x1800970b8  and     r12d, 7
0x1800970bc  lea     r13, aUnc; "\\\\?\\UNC"
0x1800970c3  cmp     cx, dx
0x1800970c6  cmovz   r13, rbx
0x1800970ca  jmp     short loc_1800970E4
0x1800970cc  mov     r14, rsi
0x1800970cf  cmp     edi, 104h
0x1800970d5  jbe     short loc_1800970E4
0x1800970d7  mov     r12d, 4
0x1800970dd  lea     r13, asc_1800C2D10; "\\\\?\\"
0x1800970e4  mov     rbx, r8
0x1800970e7  mov     rsi, [rsp+3F0h+Src]
0x1800970ec  xor     eax, eax
0x1800970ee  inc     rbx
0x1800970f1  cmp     [rsi+rbx*2], ax
0x1800970f5  jnz     short loc_1800970EE
0x1800970f7  lea     edx, [rdi+1]
0x1800970fa  add     edx, r12d
0x1800970fd  add     edx, ebx
0x1800970ff  mov     eax, 2
0x180097104  mul     rdx
0x180097107  cmovb   rax, r8
0x18009710b  mov     rcx, rax; Size
0x18009710e  call    cs:__imp_malloc
0x180097114  mov     r15, rax
0x180097117  test    rax, rax
0x18009711a  jnz     short loc_180097124
0x18009711c  lea     ebx, [rax+0Eh]
0x18009711f  jmp     loc_180097037
0x180097124  mov     eax, ebx
0x180097126  lea     rbx, [rax+rax]
0x18009712a  mov     r8, rbx; Size
0x18009712d  mov     rdx, rsi; Src
0x180097130  mov     rcx, r15; void *
0x180097133  call    memcpy_0
0x180097138  lea     rsi, [rbx+r15]
0x18009713c  test    r12d, r12d
0x18009713f  jz      short loc_180097159
0x180097141  mov     eax, r12d
0x180097144  lea     rbx, [rax+rax]
0x180097148  mov     r8, rbx; Size
0x18009714b  mov     rdx, r13; Src
0x18009714e  mov     rcx, rsi; void *
0x180097151  call    memcpy_0
0x180097156  add     rsi, rbx
0x180097159  mov     eax, edi
0x18009715b  lea     rbx, [rax+rax]
0x18009715f  mov     r8, rbx; Size
0x180097162  mov     rdx, r14; Src
0x180097165  mov     rcx, rsi; void *
0x180097168  call    memcpy_0
0x18009716d  xor     r14d, r14d
0x180097170  mov     [rbx+rsi], r14w
0x180097175  mov     rdx, r15; SourceString
0x180097178  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x18009717c  call    cs:__imp_RtlInitUnicodeStringEx
0x180097182  test    eax, eax
0x180097184  jns     short loc_180097195
0x180097186  mov     ecx, eax; Status
0x180097188  call    cs:__imp_RtlNtStatusToDosError
0x18009718e  mov     ebx, eax
0x180097190  jmp     loc_180097305
0x180097195  mov     byte ptr [rbp+2F0h+var_32C+1], 0Ah
0x180097199  mov     eax, 19h
0x18009719e  mov     word ptr [rbp+2F0h+var_32C+2], ax
0x1800971a2  movsd   xmm0, qword ptr cs:aStorvspV2; "StorVsp-v2"
0x1800971aa  movsd   qword ptr [rbp+2F0h+var_32C+4], xmm0
0x1800971af  mov     eax, dword ptr cs:aStorvspV2+7; "-v2"
0x1800971b5  mov     dword ptr [rbp+2F0h+var_32C+0Bh], eax
0x1800971b8  mov     r12d, 40h ; '@'
0x1800971be  mov     dword ptr [rbp+2F0h+var_30C+4], r12d
0x1800971c2  mov     rdi, [rsp+3F0h+var_380]
0x1800971c7  test    rdi, rdi
0x1800971ca  jz      short loc_1800971D8
0x1800971cc  movups  xmm0, xmmword ptr [rdi]
0x1800971cf  movdqu  [rbp+2F0h+var_31C], xmm0
0x1800971d4  mov     byte ptr [rbp+2F0h+var_30C], 1
0x1800971d8  mov     [rbp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1800971df  mov     [rbp+2F0h+ObjectAttributes.RootDirectory], r14
0x1800971e3  mov     [rbp+2F0h+ObjectAttributes.Attributes], r12d
0x1800971e7  lea     rax, [rbp+2F0h+DestinationString]
0x1800971eb  mov     [rbp+2F0h+ObjectAttributes.ObjectName], rax
0x1800971ef  xorps   xmm0, xmm0
0x1800971f2  movdqu  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800971f7  xor     edx, edx; Val
0x1800971f9  mov     r8d, 150h; Size
0x1800971ff  lea     rcx, [rbp+2F0h+var_190]; void *
0x180097206  call    memset_0
0x18009720b  mov     rbx, [rbp+2F0h+var_1D0]
0x180097212  lea     rdx, aVstorcreatedev_0; "VstorCreateDevice_CreateFile"
0x180097219  lea     rcx, [rbp+2F0h+var_190]
0x180097220  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180097225  lea     rsi, ??_7VstorCreateDevice_CreateFile@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable'
0x18009722c  mov     [rbp+2F0h+var_190], rsi
0x180097233  lea     r9, [rbx+8]; struct _GUID *
0x180097237  mov     r8, rdi; struct _GUID *
0x18009723a  lea     rdx, [rbp+2F0h+DestinationString]; struct _UNICODE_STRING *
0x18009723e  lea     rcx, [rbp+2F0h+var_190]; this
0x180097245  call    ?StartActivity@VstorCreateDevice_CreateFile@VstorlibTraceProvider@@QEAAXAEAU_UNICODE_STRING@@PEBU_GUID@@1@Z; VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(_UNICODE_STRING &,_GUID const *,_GUID const *)
0x18009724a  nop
0x18009724b  mov     [rsp+3F0h+EaLength], 2Ch ; ','; EaLength
0x180097253  lea     rax, [rbp+2F0h+var_330]
0x180097257  mov     [rsp+3F0h+EaBuffer], rax; EaBuffer
0x18009725c  mov     [rsp+3F0h+CreateOptions], r12d; CreateOptions
0x180097261  mov     [rsp+3F0h+CreateDisposition], 2; CreateDisposition
0x180097269  mov     [rsp+3F0h+ShareAccess], 7; ShareAccess
0x180097271  mov     [rsp+3F0h+FileAttributes], 80h; FileAttributes
0x180097279  mov     [rsp+3F0h+AllocationSize], r14; AllocationSize
0x18009727e  lea     r9, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x180097282  lea     r8, [rbp+2F0h+ObjectAttributes]; ObjectAttributes
0x180097286  mov     edx, [rsp+3F0h+DesiredAccess]; DesiredAccess
0x18009728a  lea     rcx, [rbp+2F0h+FileHandle]; FileHandle
0x18009728e  call    cs:__imp_NtCreateFile
0x180097294  mov     edi, eax
0x180097296  mov     ecx, eax
0x180097298  mov     r8d, eax
0x18009729b  bts     r8d, 1Ch
0x1800972a0  neg     ecx
0x1800972a2  sbb     edx, edx
0x1800972a4  and     edx, r8d
0x1800972a7  lea     rcx, [rbp+2F0h+var_190]
0x1800972ae  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800972b3  mov     [rbp+2F0h+var_190], rsi
0x1800972ba  lea     rcx, [rbp+2F0h+var_190]
0x1800972c1  call    ?Destroy@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800972c6  lea     rcx, [rbp+2F0h+var_190]
0x1800972cd  call    ??1?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800972d2  test    edi, edi
0x1800972d4  jns     short loc_180097302
0x1800972d6  cmp     edi, 0C0000010h
0x1800972dc  jz      short loc_1800972FB
0x1800972de  cmp     edi, 0C000003Ah
0x1800972e4  jz      short loc_1800972FB
0x1800972e6  mov     ecx, edi; Status
0x1800972e8  call    cs:__imp_RtlNtStatusToDosError
0x1800972ee  mov     ebx, eax
0x1800972f0  cmp     eax, 13Dh
0x1800972f5  jnz     short loc_180097305
0x1800972f7  mov     ebx, edi
0x1800972f9  jmp     short loc_180097305
0x1800972fb  mov     ebx, 0C03A0014h
0x180097300  jmp     short loc_180097305
0x180097302  mov     ebx, r14d
0x180097305  cmp     [rbp+2F0h+UnicodeString.Buffer], r14
0x180097309  jz      short loc_18009731A
0x18009730b  lea     rcx, [rsp+3F0h+UnicodeString]; UnicodeString
0x180097310  call    cs:__imp_RtlFreeUnicodeString
0x180097316  mov     [rbp+2F0h+UnicodeString.Buffer], r14
0x18009731a  test    r15, r15
0x18009731d  jz      short loc_180097328
0x18009731f  mov     rcx, r15; Block
0x180097322  call    cs:__imp_free
0x180097328  mov     ecx, ebx; dwErrCode
0x18009732a  call    cs:__imp_SetLastError
0x180097330  test    ebx, ebx
0x180097332  jle     short loc_18009733D
0x180097334  movzx   ebx, bx
0x180097337  or      ebx, 80070000h
0x18009733d  mov     edx, ebx
0x18009733f  lea     rcx, [rbp+2F0h+var_2E0]
0x180097343  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180097348  mov     rbx, [rbp+2F0h+FileHandle]
0x18009734c  lea     rax, ??_7VstorCreateDevice@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice::`vftable'
0x180097353  mov     [rbp+2F0h+var_2E0], rax
0x180097357  lea     rcx, [rbp+2F0h+var_2E0]
0x18009735b  call    ?Destroy@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180097360  lea     rcx, [rbp+2F0h+var_2E0]
0x180097364  call    ??1?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180097369  mov     rax, rbx
0x18009736c  mov     rcx, [rbp+2F0h+var_40]
0x180097373  xor     rcx, rsp; StackCookie
0x180097376  call    __security_check_cookie
0x18009737b  mov     rbx, [rsp+3F0h+arg_18]
0x180097383  add     rsp, 3C0h
0x18009738a  pop     r15
0x18009738c  pop     r14
0x18009738e  pop     r13
0x180097390  pop     r12
0x180097392  pop     rdi
0x180097393  pop     rsi
0x180097394  pop     rbp
0x180097395  retn
```
