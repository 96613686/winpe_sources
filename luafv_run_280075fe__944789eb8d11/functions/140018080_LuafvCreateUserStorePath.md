# LuafvCreateUserStorePath

- ea: `0x140018080`
- end: `0x1400181eb`
- name: `LuafvCreateUserStorePath`
- size: `363`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140017648`
- `0x140019b10`

## callees

- `0x1400175dc`
- `0x140018080`
- `0x14001dd90`

## import_xrefs

- `FLTMGR!FltClose` at `0x140018189`
- `FLTMGR!FltClose` at `0x140018189`
- `FLTMGR!FltCreateFileEx2` at `0x140018173`
- `FLTMGR!FltCreateFileEx2` at `0x140018173`

## pseudocode

```c
__int64 __fastcall LuafvCreateUserStorePath(PFLT_INSTANCE Instance, void *a2, __int64 a3)
{
  void *v3; // rbx
  ULONG Flags; // ecx
  struct _UNICODE_STRING *v8; // rax
  NTSTATUS v9; // edi
  __int64 result; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  void *v13; // [rsp+F0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v3 = 0;
  v13 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( *(_BYTE *)(a3 + 80) )
  {
    Flags = 257;
  }
  else
  {
    result = LuafvCreateUserStoreSecurityDescriptor(*(_QWORD *)(a3 + 16), &v13);
    if ( (int)result < 0 )
      return result;
    v3 = v13;
    Flags = 256;
  }
  if ( a2 )
    v8 = (struct _UNICODE_STRING *)(*(_QWORD *)(a3 + 16) + 88LL);
  else
    v8 = (struct _UNICODE_STRING *)(a3 + 40);
  ObjectAttributes.ObjectName = v8;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v3;
  ObjectAttributes.SecurityQualityOfService = 0;
  v9 = FltCreateFileEx2(
         LuafvDriverData,
         Instance,
         &FileHandle,
         0,
         0x1C0000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x10u,
         3u,
         3u,
         0x21u,
         0,
         0,
         Flags,
         0);
  if ( v9 >= 0 )
    FltClose(FileHandle);
  if ( v3 )
    LuafvFreePool(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140018080  mov     [rsp-8+arg_0], rbx
0x140018085  mov     [rsp-8+arg_8], rsi
0x14001808a  push    rbp
0x14001808b  push    rdi
0x14001808c  push    r14
0x14001808e  lea     rbp, [rsp-47h]
0x140018093  sub     rsp, 0C0h
0x14001809a  xorps   xmm0, xmm0
0x14001809d  mov     [rbp+57h+FileHandle], 0
0x1400180a5  xor     ebx, ebx
0x1400180a7  xor     eax, eax
0x1400180a9  mov     rdi, r8
0x1400180ac  mov     rsi, rdx
0x1400180af  mov     r14, rcx
0x1400180b2  mov     [rbp+57h+arg_10], rbx
0x1400180b6  movups  xmmword ptr [rbp+57h+var_40.ObjectName], xmm0
0x1400180ba  movups  xmmword ptr [rbp+57h+var_40+1Ch], xmm0
0x1400180be  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x1400180c2  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1400180c6  cmp     [r8+50h], al
0x1400180ca  jz      loc_1400181C2
0x1400180d0  mov     ecx, 101h
0x1400180d5  test    rsi, rsi
0x1400180d8  jnz     loc_1400181B5
0x1400180de  lea     rax, [rdi+28h]
0x1400180e2  mov     [rsp+0D0h+DriverContext], 0; DriverContext
0x1400180eb  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x1400180ef  mov     [rsp+0D0h+Flags], ecx; Flags
0x1400180f3  xor     r9d, r9d; FileObject
0x1400180f6  mov     rcx, cs:LuafvDriverData; Filter
0x1400180fd  mov     rdx, r14; Instance
0x140018100  mov     [rsp+0D0h+EaLength], 0; EaLength
0x140018108  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x140018111  mov     [rsp+0D0h+CreateOptions], 21h ; '!'; CreateOptions
0x140018119  mov     [rbp+57h+var_40.ObjectName], rax
0x14001811d  mov     eax, 3
0x140018122  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x140018126  mov     [rsp+0D0h+ShareAccess], eax; ShareAccess
0x14001812a  lea     rax, [rbp+57h+var_50]
0x14001812e  mov     [rsp+0D0h+FileAttributes], 10h; FileAttributes
0x140018136  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x14001813f  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x140018144  lea     rax, [rbp+57h+var_40]
0x140018148  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x14001814d  mov     [rsp+0D0h+DesiredAccess], 1C0000h; DesiredAccess
0x140018155  mov     [rbp+57h+var_40.Length], 30h ; '0'
0x14001815c  mov     [rbp+57h+var_40.RootDirectory], rsi
0x140018160  mov     [rbp+57h+var_40.Attributes], 240h
0x140018167  mov     [rbp+57h+var_40.SecurityDescriptor], rbx
0x14001816b  mov     [rbp+57h+var_40.SecurityQualityOfService], 0
0x140018173  call    cs:__imp_FltCreateFileEx2
0x14001817a  nop     dword ptr [rax+rax+00h]
0x14001817f  mov     edi, eax
0x140018181  test    eax, eax
0x140018183  js      short loc_140018195
0x140018185  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140018189  call    cs:__imp_FltClose
0x140018190  nop     dword ptr [rax+rax+00h]
0x140018195  test    rbx, rbx
0x140018198  jnz     short loc_1400181E1
0x14001819a  mov     eax, edi
0x14001819c  lea     r11, [rsp+0D0h+var_10]
0x1400181a4  mov     rbx, [r11+20h]
0x1400181a8  mov     rsi, [r11+28h]
0x1400181ac  mov     rsp, r11
0x1400181af  pop     r14
0x1400181b1  pop     rdi
0x1400181b2  pop     rbp
0x1400181b3  retn
0x1400181b5  mov     rax, [rdi+10h]
0x1400181b9  add     rax, 58h ; 'X'
0x1400181bd  jmp     loc_1400180E2
0x1400181c2  mov     rcx, [r8+10h]
0x1400181c6  lea     rdx, [rbp+57h+arg_10]
0x1400181ca  call    LuafvCreateUserStoreSecurityDescriptor
0x1400181cf  test    eax, eax
0x1400181d1  js      short loc_14001819C
0x1400181d3  mov     rbx, [rbp+57h+arg_10]
0x1400181d7  mov     ecx, 100h
0x1400181dc  jmp     loc_1400180D5
0x1400181e1  mov     rcx, rbx
0x1400181e4  call    LuafvFreePool
0x1400181e9  jmp     short loc_14001819A
```
