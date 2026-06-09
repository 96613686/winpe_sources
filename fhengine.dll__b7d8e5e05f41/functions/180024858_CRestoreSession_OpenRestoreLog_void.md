# CRestoreSession::OpenRestoreLog(void)

- ea: `0x180024858`
- end: `0x180024a14`
- name: `?OpenRestoreLog@CRestoreSession@@AEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(CRestoreSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800236d0`

## callees

- `0x180007818`
- `0x180012278`
- `0x180024858`
- `0x180024d48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800248b4`
- `KERNEL32!GetLastError` at `0x1800248b4`
- `ntdll!NtCreateFile` at `0x180024967`
- `ntdll!NtCreateFile` at `0x180024967`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800248aa`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800248aa`
- `ntdll!RtlNtStatusToDosError` at `0x180024975`
- `ntdll!RtlNtStatusToDosError` at `0x180024975`
- `ntdll!RtlFreeUnicodeString` at `0x180024a00`
- `ntdll!RtlFreeUnicodeString` at `0x180024a00`

## pseudocode

```c
__int64 __fastcall CRestoreSession::OpenRestoreLog(CRestoreSession *this)
{
  void **v1; // rsi
  unsigned int v2; // ebx
  bool v3; // zf
  signed int LastError; // eax
  NTSTATUS v6; // eax
  char v7; // si
  signed int v8; // eax
  int v9; // edx
  int v10; // r8d
  _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF

  v1 = (void **)((char *)this + 240);
  v2 = 0;
  v3 = *((_QWORD *)this + 30) == -1;
  NtPathName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( v3 )
  {
    if ( RtlDosPathNameToNtPathName_U(*((PCWSTR *)this + 21), &NtPathName, 0, 0) )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = NtCreateFile(v1, 0x100004u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 3u, 0x200020u, 0, 0);
      v7 = v6;
      if ( v6 )
      {
        v8 = RtlNtStatusToDosError(v6);
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 == -2147024864 )
          v2 = -2147220475;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)this + 21), v7);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids,
          *((_QWORD *)this + 21));
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v2);
    }
  }
  RtlFreeUnicodeString(&NtPathName);
  return v2;
}

```

## disassembly

```asm
0x180024858  push    rbp
0x18002485a  push    rbx
0x18002485b  push    rsi
0x18002485c  push    rdi
0x18002485d  lea     rbp, [rsp-3Fh]
0x180024862  sub     rsp, 0B8h
0x180024869  xorps   xmm1, xmm1
0x18002486c  lea     rsi, [rcx+0F0h]
0x180024873  xorps   xmm0, xmm0
0x180024876  xor     ebx, ebx
0x180024878  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18002487c  mov     rdi, rcx
0x18002487f  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180024883  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180024887  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002488b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002488f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180024893  jnz     loc_1800249FC
0x180024899  mov     rcx, [rcx+0A8h]; DosPathName
0x1800248a0  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800248a4  xor     r9d, r9d; DirectoryInfo
0x1800248a7  xor     r8d, r8d; NtFileNamePart
0x1800248aa  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800248b0  test    al, al
0x1800248b2  jnz     short loc_180024907
0x1800248b4  call    cs:__imp_GetLastError
0x1800248ba  mov     ebx, eax
0x1800248bc  test    eax, eax
0x1800248be  jle     short loc_1800248C9
0x1800248c0  movzx   ebx, ax
0x1800248c3  or      ebx, 80070000h
0x1800248c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248d0  lea     rax, WPP_GLOBAL_Control
0x1800248d7  cmp     rcx, rax
0x1800248da  jz      loc_1800249FC
0x1800248e0  test    byte ptr [rcx+1Ch], 1
0x1800248e4  jz      loc_1800249FC
0x1800248ea  mov     rcx, [rcx+10h]
0x1800248ee  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x1800248f5  mov     edx, 24h ; '$'
0x1800248fa  mov     r9d, ebx
0x1800248fd  call    WPP_SF_d
0x180024902  jmp     loc_1800249FC
0x180024907  mov     [rsp+0D0h+EaLength], ebx; EaLength
0x18002490b  lea     rax, [rbp+57h+NtPathName]
0x18002490f  mov     [rsp+0D0h+EaBuffer], rbx; EaBuffer
0x180024914  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180024918  mov     [rsp+0D0h+CreateOptions], 200020h; CreateOptions
0x180024920  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180024924  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x18002492c  xorps   xmm0, xmm0
0x18002492f  mov     [rsp+0D0h+ShareAccess], 2; ShareAccess
0x180024937  mov     edx, 100004h; DesiredAccess
0x18002493c  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180024944  mov     rcx, rsi; FileHandle
0x180024947  mov     [rsp+0D0h+AllocationSize], rbx; AllocationSize
0x18002494c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180024953  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180024957  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002495e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180024962  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024967  call    cs:__imp_NtCreateFile
0x18002496d  mov     esi, eax
0x18002496f  test    eax, eax
0x180024971  jz      short loc_1800249C7
0x180024973  mov     ecx, eax; Status
0x180024975  call    cs:__imp_RtlNtStatusToDosError
0x18002497b  mov     ebx, eax
0x18002497d  test    eax, eax
0x18002497f  jle     short loc_18002498A
0x180024981  movzx   ebx, ax
0x180024984  or      ebx, 80070000h
0x18002498a  cmp     ebx, 80070020h
0x180024990  mov     eax, 80040405h
0x180024995  cmovz   ebx, eax
0x180024998  mov     rcx, cs:WPP_GLOBAL_Control
0x18002499f  lea     rax, WPP_GLOBAL_Control
0x1800249a6  cmp     rcx, rax
0x1800249a9  jz      short loc_1800249FC
0x1800249ab  test    byte ptr [rcx+1Ch], 1
0x1800249af  jz      short loc_1800249FC
0x1800249b1  mov     r9, [rdi+0A8h]
0x1800249b8  mov     rcx, [rcx+10h]
0x1800249bc  mov     dword ptr [rsp+0D0h+AllocationSize], esi
0x1800249c0  call    WPP_SF_SD
0x1800249c5  jmp     short loc_1800249FC
0x1800249c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ce  lea     rax, WPP_GLOBAL_Control
0x1800249d5  cmp     rcx, rax
0x1800249d8  jz      short loc_1800249FC
0x1800249da  test    byte ptr [rcx+1Ch], 8
0x1800249de  jz      short loc_1800249FC
0x1800249e0  mov     r9, [rdi+0A8h]
0x1800249e7  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x1800249ee  mov     rcx, [rcx+10h]
0x1800249f2  mov     edx, 26h ; '&'
0x1800249f7  call    WPP_SF_S
0x1800249fc  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x180024a00  call    cs:__imp_RtlFreeUnicodeString
0x180024a06  mov     eax, ebx
0x180024a08  add     rsp, 0B8h
0x180024a0f  pop     rdi
0x180024a10  pop     rsi
0x180024a11  pop     rbx
0x180024a12  pop     rbp
0x180024a13  retn
```
