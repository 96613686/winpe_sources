# BiGetNtPartitionPathCallback

- ea: `0x180030cd0`
- end: `0x180031028`
- name: `BiGetNtPartitionPathCallback`
- size: `856`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003210`
- `0x1800033d4`
- `0x18003095c`
- `0x180030cd0`
- `0x1800311e4`

## import_xrefs

- `ntdll!ZwClose` at `0x180030e76`
- `ntdll!ZwClose` at `0x180030e76`
- `ntdll!ZwOpenFile` at `0x180030e62`
- `ntdll!ZwOpenFile` at `0x180030e62`
- `ntdll!RtlFreeHeap` at `0x180030dc2`
- `ntdll!RtlFreeHeap` at `0x180030e97`
- `ntdll!RtlFreeHeap` at `0x180030ef1`
- `ntdll!RtlFreeHeap` at `0x180030fd1`
- `ntdll!RtlFreeHeap` at `0x180030dc2`
- `ntdll!RtlFreeHeap` at `0x180030e97`
- `ntdll!RtlFreeHeap` at `0x180030ef1`
- `ntdll!RtlFreeHeap` at `0x180030fd1`
- `ntdll!RtlInitUnicodeString` at `0x180030e17`
- `ntdll!RtlInitUnicodeString` at `0x180030e17`

## pseudocode

```c
char __fastcall BiGetNtPartitionPathCallback(__int64 a1, unsigned int a2, __int64 a3)
{
  wchar_t *v3; // r14
  wchar_t *v4; // rsi
  _QWORD *v5; // r13
  __int64 v6; // rbx
  char v7; // di
  _DWORD *v8; // r12
  _DWORD *v9; // r15
  wchar_t *v10; // rbx
  int v11; // r14d
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  _QWORD *v15; // rsi
  __int64 v16; // r13
  const wchar_t *PartitionVhdFilePath; // rax
  bool v18; // zf
  __int64 ShareAccess; // [rsp+28h] [rbp-89h]
  PVOID P; // [rsp+38h] [rbp-79h] BYREF
  wchar_t *Buffer; // [rsp+40h] [rbp-71h]
  void *FileHandle; // [rsp+48h] [rbp-69h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-61h]
  _OWORD v24[2]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v25; // [rsp+78h] [rbp-39h]
  _QWORD *v26; // [rsp+80h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+17h] BYREF
  char v32; // [rsp+130h] [rbp+7Fh]

  v3 = *(wchar_t **)(a3 + 8);
  v4 = *(wchar_t **)(a3 + 16);
  v5 = *(_QWORD **)(a3 + 32);
  v6 = *(_QWORD *)(a3 + 24);
  v7 = 0;
  v8 = *(_DWORD **)(a3 + 40);
  v25 = 0;
  FileHandle = 0;
  P = 0;
  v32 = *(_BYTE *)(a3 + 1);
  String1 = v3;
  memset(v24, 0, sizeof(v24));
  Buffer = v4;
  v26 = v5;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  if ( (int)BiGetDriveLayoutBlock(a1, &P, v24) < 0 )
    return v7;
  if ( LODWORD(v24[0]) == 7 )
  {
    if ( *(_DWORD *)v6 != 7 )
      goto LABEL_6;
  }
  else if ( v3 )
  {
    goto LABEL_6;
  }
  if ( *(_OWORD *)(v6 + 4) != *(_OWORD *)((char *)v24 + 4) || *(_DWORD *)(v6 + 20) != DWORD1(v24[1]) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return v7;
  }
LABEL_6:
  v9 = P;
  v10 = 0;
  if ( *(_DWORD *)P )
  {
    if ( *(_DWORD *)P == 1 )
      v11 = 0;
    else
      v11 = 2;
  }
  else
  {
    v11 = 1;
  }
  if ( !v8 )
  {
    if ( v11 == 1 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( v11 != 1 )
  {
LABEL_32:
    if ( v11 )
      goto LABEL_20;
LABEL_33:
    v15 = 0;
    if ( !v11 )
    {
      if ( v8 )
      {
        v15 = v8;
      }
      else if ( v5 )
      {
        v15 = v5;
      }
    }
    v16 = 0;
    if ( !*((_DWORD *)P + 1) )
      goto LABEL_20;
    while ( 1 )
    {
      if ( v9[36 * v16 + 18] )
      {
        LODWORD(ShareAccess) = v9[36 * v16 + 18];
        swprintf_s(Buffer, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, ShareAccess);
        if ( v32 )
        {
          PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
          v10 = (wchar_t *)PartitionVhdFilePath;
          if ( PartitionVhdFilePath )
          {
            if ( !wcsicmp(String1, PartitionVhdFilePath) )
              goto LABEL_19;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            v10 = 0;
          }
        }
        if ( v11 == 1 )
        {
          if ( v26 )
          {
            v18 = *v26 == *(_QWORD *)&v9[36 * v16 + 14];
            goto LABEL_50;
          }
        }
        else if ( v15 && *v15 == *(_QWORD *)&v9[36 * v16 + 24] )
        {
          v18 = v15[1] == *(_QWORD *)&v9[36 * v16 + 26];
LABEL_50:
          if ( v18 )
            goto LABEL_19;
        }
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= v9[1] )
        goto LABEL_20;
    }
  }
  swprintf_s(v4, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", a2, *v8);
  RtlInitUnicodeString(&DestinationString, v4);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
  {
    ZwClose(FileHandle);
LABEL_19:
    v7 = 1;
  }
LABEL_20:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  v12 = String1;
  if ( !String1 || v32 || !v7 )
  {
LABEL_26:
    if ( !v10 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v13 = (const wchar_t *)BiGetPartitionVhdFilePath(Buffer);
  v10 = (wchar_t *)v13;
  if ( !v13 || wcsicmp(v12, v13) )
  {
    v7 = 0;
    goto LABEL_26;
  }
LABEL_27:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
LABEL_28:
  if ( v7 )
    *(_BYTE *)a3 = 1;
  return v7;
}

```

## disassembly

```asm
0x180030cd0  mov     rax, rsp
0x180030cd3  mov     [rax+8], rbx
0x180030cd7  mov     [rax+18h], r8
0x180030cdb  mov     [rax+10h], edx
0x180030cde  push    rbp
0x180030cdf  push    rsi
0x180030ce0  push    rdi
0x180030ce1  push    r12
0x180030ce3  push    r13
0x180030ce5  push    r14
0x180030ce7  push    r15
0x180030ce9  lea     rbp, [rax-5Fh]
0x180030ced  sub     rsp, 0D0h
0x180030cf4  mov     r14, [r8+8]
0x180030cf8  xorps   xmm0, xmm0
0x180030cfb  mov     rsi, [r8+10h]
0x180030cff  xor     edx, edx
0x180030d01  mov     r13, [r8+20h]
0x180030d05  xorps   xmm1, xmm1
0x180030d08  mov     rbx, [r8+18h]
0x180030d0c  xor     dil, dil
0x180030d0f  mov     r12, [r8+28h]
0x180030d13  mov     [rbp+57h+var_90], rdx
0x180030d17  mov     [rbp+57h+FileHandle], rdx
0x180030d1b  mov     [rbp+57h+P], rdx
0x180030d1f  mov     dl, [r8+1]
0x180030d23  lea     r8, [rbp+57h+var_B0]
0x180030d27  mov     [rbp+57h+arg_18], dl
0x180030d2a  lea     rdx, [rbp+57h+P]
0x180030d2e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180030d32  mov     [rbp+57h+String1], r14
0x180030d36  movups  [rbp+57h+var_B0], xmm0
0x180030d3a  mov     [rbp+57h+Buffer], rsi
0x180030d3e  movups  [rbp+57h+var_A0], xmm0
0x180030d42  mov     [rbp+57h+var_88], r13
0x180030d46  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180030d4a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180030d4e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180030d52  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180030d56  call    BiGetDriveLayoutBlock
0x180030d5b  test    eax, eax
0x180030d5d  js      loc_180030F09
0x180030d63  cmp     dword ptr [rbp+57h+var_B0], 7
0x180030d67  jnz     short loc_180030DA8
0x180030d69  cmp     dword ptr [rbx], 7
0x180030d6c  jnz     short loc_180030DA2
0x180030d6e  mov     rax, [rbx+4]
0x180030d72  cmp     rax, qword ptr [rbp+57h+var_B0+4]
0x180030d76  jnz     short loc_180030DAF
0x180030d78  mov     rax, [rbx+0Ch]
0x180030d7c  cmp     rax, qword ptr [rbp+57h+var_B0+0Ch]
0x180030d80  jnz     short loc_180030DAF
0x180030d82  mov     eax, [rbx+14h]
0x180030d85  cmp     eax, dword ptr [rbp+57h+var_A0+4]
0x180030d88  jnz     short loc_180030DAF
0x180030d8a  mov     r15, [rbp+57h+P]
0x180030d8e  xor     ebx, ebx
0x180030d90  mov     ecx, [r15]
0x180030d93  test    ecx, ecx
0x180030d95  jz      short loc_180030DD8
0x180030d97  cmp     ecx, 1
0x180030d9a  jz      short loc_180030DD3
0x180030d9c  lea     r14d, [rbx+2]
0x180030da0  jmp     short loc_180030DDE
0x180030da2  cmp     dword ptr [rbp+57h+var_B0], 7
0x180030da6  jz      short loc_180030D8A
0x180030da8  test    r14, r14
0x180030dab  jnz     short loc_180030D8A
0x180030dad  jmp     short loc_180030D6E
0x180030daf  mov     rcx, gs:60h
0x180030db8  xor     edx, edx; Flags
0x180030dba  mov     r8, [rbp+57h+P]; P
0x180030dbe  mov     rcx, [rcx+30h]; HeapHandle
0x180030dc2  call    cs:__imp_RtlFreeHeap
0x180030dc9  nop     dword ptr [rax+rax+00h]
0x180030dce  jmp     loc_180030F09
0x180030dd3  xor     r14d, r14d
0x180030dd6  jmp     short loc_180030DDE
0x180030dd8  mov     r14d, 1
0x180030dde  test    r12, r12
0x180030de1  jz      loc_180030F28
0x180030de7  cmp     r14d, 1
0x180030deb  jnz     loc_180030F2E
0x180030df1  mov     eax, [r12]
0x180030df5  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x180030dfc  mov     r9d, [rbp+57h+arg_8]
0x180030e00  lea     edx, [r14+34h]; BufferCount
0x180030e04  mov     rcx, rsi; Buffer
0x180030e07  mov     [rsp+100h+ShareAccess], eax
0x180030e0b  call    swprintf_s
0x180030e10  mov     rdx, rsi; SourceString
0x180030e13  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030e17  call    cs:__imp_RtlInitUnicodeString
0x180030e1e  nop     dword ptr [rax+rax+00h]
0x180030e23  lea     rax, [rbp+57h+DestinationString]
0x180030e27  mov     [rsp+28h], ebx; OpenOptions
0x180030e2b  xorps   xmm0, xmm0
0x180030e2e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180030e32  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180030e36  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030e3d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180030e41  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180030e45  mov     edx, 80000000h; DesiredAccess
0x180030e4a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180030e51  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180030e55  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x180030e5d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030e62  call    cs:__imp_ZwOpenFile
0x180030e69  nop     dword ptr [rax+rax+00h]
0x180030e6e  test    eax, eax
0x180030e70  js      short loc_180030E85
0x180030e72  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180030e76  call    cs:__imp_ZwClose
0x180030e7d  nop     dword ptr [rax+rax+00h]
0x180030e82  mov     dil, 1
0x180030e85  mov     rcx, gs:60h
0x180030e8e  mov     r8, r15; P
0x180030e91  xor     edx, edx; Flags
0x180030e93  mov     rcx, [rcx+30h]; HeapHandle
0x180030e97  call    cs:__imp_RtlFreeHeap
0x180030e9e  nop     dword ptr [rax+rax+00h]
0x180030ea3  mov     rsi, [rbp+57h+String1]
0x180030ea7  test    rsi, rsi
0x180030eaa  jz      short loc_180030EDA
0x180030eac  cmp     [rbp+57h+arg_18], 0
0x180030eb0  jnz     short loc_180030EDA
0x180030eb2  test    dil, dil
0x180030eb5  jz      short loc_180030EDA
0x180030eb7  mov     rcx, [rbp+57h+Buffer]; SourceString
0x180030ebb  call    BiGetPartitionVhdFilePath
0x180030ec0  mov     rbx, rax
0x180030ec3  test    rax, rax
0x180030ec6  jz      short loc_180030ED7
0x180030ec8  mov     rdx, rax; String2
0x180030ecb  mov     rcx, rsi; String1
0x180030ece  call    _wcsicmp
0x180030ed3  test    eax, eax
0x180030ed5  jz      short loc_180030EDF
0x180030ed7  xor     dil, dil
0x180030eda  test    rbx, rbx
0x180030edd  jz      short loc_180030EFD
0x180030edf  mov     rcx, gs:60h
0x180030ee8  mov     r8, rbx; P
0x180030eeb  xor     edx, edx; Flags
0x180030eed  mov     rcx, [rcx+30h]; HeapHandle
0x180030ef1  call    cs:__imp_RtlFreeHeap
0x180030ef8  nop     dword ptr [rax+rax+00h]
0x180030efd  test    dil, dil
0x180030f00  jz      short loc_180030F09
0x180030f02  mov     rax, [rbp+57h+arg_10]
0x180030f06  mov     byte ptr [rax], 1
0x180030f09  mov     rbx, [rsp+100h+arg_0]
0x180030f11  mov     al, dil
0x180030f14  add     rsp, 0D0h
0x180030f1b  pop     r15
0x180030f1d  pop     r14
0x180030f1f  pop     r13
0x180030f21  pop     r12
0x180030f23  pop     rdi
0x180030f24  pop     rsi
0x180030f25  pop     rbp
0x180030f26  retn
0x180030f28  cmp     r14d, 1
0x180030f2c  jz      short loc_180030F37
0x180030f2e  test    r14d, r14d
0x180030f31  jnz     loc_180030E85
0x180030f37  xor     esi, esi
0x180030f39  test    r14d, r14d
0x180030f3c  jnz     short loc_180030F4F
0x180030f3e  test    r12, r12
0x180030f41  jz      short loc_180030F48
0x180030f43  mov     rsi, r12
0x180030f46  jmp     short loc_180030F4F
0x180030f48  test    r13, r13
0x180030f4b  cmovnz  rsi, r13
0x180030f4f  xor     r13d, r13d
0x180030f52  cmp     [r15+4], ebx
0x180030f56  jbe     loc_180030E85
0x180030f5c  lea     r12, ds:0[r13*8]
0x180030f64  add     r12, r13
0x180030f67  add     r12, r12
0x180030f6a  mov     eax, [r15+r12*8+48h]
0x180030f6f  test    eax, eax
0x180030f71  jz      loc_180031016
0x180030f77  mov     r9d, [rbp+57h+arg_8]
0x180030f7b  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x180030f82  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180030f86  mov     edx, 35h ; '5'; BufferCount
0x180030f8b  mov     [rsp+100h+ShareAccess], eax
0x180030f8f  call    swprintf_s
0x180030f94  cmp     [rbp+57h+arg_18], dil
0x180030f98  jz      short loc_180030FDF
0x180030f9a  mov     rcx, [rbp+57h+Buffer]; SourceString
0x180030f9e  call    BiGetPartitionVhdFilePath
0x180030fa3  mov     rbx, rax
0x180030fa6  test    rax, rax
0x180030fa9  jz      short loc_180030FDF
0x180030fab  mov     rcx, [rbp+57h+String1]; String1
0x180030faf  mov     rdx, rax; String2
0x180030fb2  call    _wcsicmp
0x180030fb7  test    eax, eax
0x180030fb9  jz      loc_180030E82
0x180030fbf  mov     rcx, gs:60h
0x180030fc8  mov     r8, rbx; P
0x180030fcb  xor     edx, edx; Flags
0x180030fcd  mov     rcx, [rcx+30h]; HeapHandle
0x180030fd1  call    cs:__imp_RtlFreeHeap
0x180030fd8  nop     dword ptr [rax+rax+00h]
0x180030fdd  xor     ebx, ebx
0x180030fdf  cmp     r14d, 1
0x180030fe3  jnz     short loc_180030FF8
0x180030fe5  mov     rcx, [rbp+57h+var_88]
0x180030fe9  test    rcx, rcx
0x180030fec  jz      short loc_180031016
0x180030fee  mov     rax, [r15+r12*8+38h]
0x180030ff3  cmp     [rcx], rax
0x180030ff6  jmp     short loc_180031010
0x180030ff8  test    rsi, rsi
0x180030ffb  jz      short loc_180031016
0x180030ffd  mov     rax, [rsi]
0x180031000  cmp     rax, [r15+r12*8+60h]
0x180031005  jnz     short loc_180031016
0x180031007  mov     rax, [rsi+8]
0x18003100b  cmp     rax, [r15+r12*8+68h]
0x180031010  jz      loc_180030E82
0x180031016  inc     r13d
0x180031019  cmp     r13d, [r15+4]
0x18003101d  jb      loc_180030F5C
0x180031023  jmp     loc_180030E85
```
