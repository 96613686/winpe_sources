# sub_1805F4ECC

- ea: `0x1805f4ecc`
- end: `0x1805f54be`
- name: `sub_1805F4ECC`
- size: `1522`
- prototype: `signed int __fastcall(__int64 *, __int64, int)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180451680`
- `0x1807d20b0`
- `0x1807d4af0`
- `0x1807d5b20`
- `0x1807d7140`
- `0x180913d20`
- `0x1809148c0`

## callees

- `0x18013f000`
- `0x180177270`
- `0x180177520`
- `0x1801a08a8`
- `0x1801a569c`
- `0x1801a5f5c`
- `0x18022f134`
- `0x1805f4dcc`
- `0x1805f4ecc`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1805f4fa5`
- `ntdll!NtOpenFile` at `0x1805f4fa5`
- `ntdll!RtlInitUnicodeString` at `0x1805f4f59`
- `ntdll!RtlInitUnicodeString` at `0x1805f4f59`
- `ntdll!RtlNtStatusToDosError` at `0x1805f4fe9`
- `ntdll!RtlNtStatusToDosError` at `0x1805f4fe9`
- `KERNEL32!CreateFileW` at `0x1805f5191`
- `KERNEL32!CreateFileW` at `0x1805f53e2`
- `KERNEL32!CreateFileW` at `0x1805f5191`
- `KERNEL32!CreateFileW` at `0x1805f53e2`
- `KERNEL32!GetLastError` at `0x1805f51a0`
- `KERNEL32!GetLastError` at `0x1805f5405`
- `KERNEL32!GetLastError` at `0x1805f51a0`
- `KERNEL32!GetLastError` at `0x1805f5405`

## pseudocode

```c
signed int __fastcall sub_1805F4ECC(__int64 *a1, __int64 a2, int a3)
{
  __int64 v6; // rbx
  NTSTATUS v7; // eax
  NTSTATUS v8; // edi
  signed int result; // eax
  __int64 v10; // rax
  unsigned __int16 v11; // cx
  __int64 v12; // rcx
  unsigned __int16 v13; // di
  unsigned __int16 v14; // ax
  int v15; // eax
  int v16; // r8d
  unsigned int v17; // ecx
  _QWORD *v18; // rcx
  int v19; // edx
  DWORD v20; // edx
  HANDLE FileW; // rax
  signed int LastError; // ebx
  _QWORD *v23; // rcx
  __int64 v24; // rdi
  unsigned int v25; // ecx
  __int16 *i; // rax
  __int16 v27; // cx
  __int64 v28; // rax
  __int64 v29; // r8
  struct _OBJECT_ATTRIBUTES *p_ObjectAttributes; // rcx
  __int64 v31; // rdi
  __int16 v32; // ax
  struct _OBJECT_ATTRIBUTES *v33; // rax
  DWORD v34; // edx
  void *FileHandle; // [rsp+40h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+1Fh] BYREF

  if ( !a1 )
    sub_1801A08A8(0);
  v6 = -1;
  *a1 = -1;
  if ( !a2 )
    sub_1801A08A8(a1);
  if ( !(unsigned int)sub_180177520(a2, L"\\Device\\", 8) )
  {
    *(&ObjectAttributes.Length + 1) = 0;
    IoStatusBlock = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)a2);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.ObjectName = &DestinationString;
    FileHandle = 0;
    v7 = NtOpenFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 3u, 0x10u);
    v8 = v7;
    if ( v7 < 0 )
    {
      _mm_lfence();
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        sub_1801A569C(*((_QWORD *)hDevice + 2), 16, (unsigned int)qword_180CE69F8, a2, v7);
      result = RtlNtStatusToDosError(v8);
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( FileHandle != (void *)-1LL )
      v6 = (__int64)FileHandle;
LABEL_83:
    *a1 = v6;
    return 0;
  }
  if ( !(unsigned int)sub_180177520(a2, L"Disk", 4) )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a2 + 2 * v10) );
    if ( (unsigned int)v10 < 6
      || ((v11 = *(_WORD *)(a2 + 8), v11 < 0x30u) || v11 > 0x39u)
      && (unsigned __int16)(v11 - 97) > 5u
      && (unsigned __int16)(v11 - 65) > 5u
      || ((v12 = *(unsigned __int16 *)(a2 + 10), (unsigned __int16)v12 < 0x30u) || (unsigned __int16)v12 > 0x39u)
      && (unsigned __int16)(v12 - 97) > 5u
      && (unsigned __int16)(v12 - 65) > 5u )
    {
      v18 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return -2147024809;
      v19 = 17;
      goto LABEL_94;
    }
    v13 = sub_180177270(v12);
    v14 = sub_180177270(*(unsigned __int16 *)(a2 + 8));
    sub_1805F4DCC(v14);
    v15 = sub_1805F4DCC(v13);
    v17 = v15 + 8 * v16;
    if ( v17 < 0x80 )
    {
      if ( (int)sub_1801A5F5C(&ObjectAttributes, 21, L"\\\\.\\%c:", (unsigned __int16)(v17 + 65)) < 0 )
      {
        v18 = hDevice;
        if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
          return -2147024809;
        v19 = 19;
        goto LABEL_94;
      }
    }
    else if ( (int)sub_1801A5F5C(&ObjectAttributes, 21, L"\\\\.\\PHYSICALDRIVE%u", v17 - 128) < 0 )
    {
      v18 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return -2147024809;
      v19 = 18;
LABEL_94:
      sub_1801A569C(v18[2], v19, (unsigned int)qword_180CE69F8, a2, 87);
      return -2147024809;
    }
    v20 = -1073741824;
    if ( a3 != 2 )
      v20 = 0x80000000;
    FileW = CreateFileW((LPCWSTR)&ObjectAttributes, v20, 7u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v23 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_41;
      goto LABEL_40;
    }
LABEL_82:
    v6 = (__int64)FileW;
    goto LABEL_83;
  }
  if ( (unsigned int)sub_180177520(a2, L"\\\\.\\", 4) && (unsigned int)sub_180177520(a2, L"\\\\?\\", 4) )
  {
    v18 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      return -2147024809;
    v19 = 25;
    goto LABEL_94;
  }
  v24 = -1;
  do
    ++v24;
  while ( *(_WORD *)(a2 + 2 * v24) );
  memset(&ObjectAttributes, 0, 42);
  if ( (unsigned int)v24 >= 6
    && ((v25 = *(unsigned __int16 *)(a2 + 8), v25 >= 0x61) && v25 <= 0x7A || (unsigned __int16)(v25 - 65) <= 0x19u)
    && *(_WORD *)(a2 + 10) == 58 )
  {
    if ( (int)sub_1801A5F5C(&ObjectAttributes, 21, L"\\\\.\\%c:", *(unsigned __int16 *)(a2 + 8)) < 0 )
    {
      v18 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return -2147024809;
      v19 = 21;
      goto LABEL_94;
    }
  }
  else
  {
    if ( (unsigned int)v24 <= 0x11 || (unsigned int)sub_180177520(a2, L"\\\\.\\PHYSICALDRIVE", 17) )
    {
      v18 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return -2147024809;
      v19 = 23;
      goto LABEL_94;
    }
    for ( i = (__int16 *)(a2 + 34); ; ++i )
    {
      v27 = *i;
      if ( !*i )
      {
        LODWORD(v28) = v24;
        goto LABEL_71;
      }
      if ( v27 == 47 || v27 == 92 )
        break;
    }
    v28 = ((__int64)i - a2) >> 1;
LABEL_71:
    if ( (unsigned int)v28 > 0x7FFFFFFE )
      goto LABEL_88;
    v29 = (unsigned int)v28;
    p_ObjectAttributes = &ObjectAttributes;
    v31 = 21;
    do
    {
      if ( !(v29 + v31 - 21) )
        break;
      v32 = *(_WORD *)((char *)&p_ObjectAttributes->Length + a2 - (_QWORD)&ObjectAttributes);
      if ( !v32 )
        break;
      LOWORD(p_ObjectAttributes->Length) = v32;
      p_ObjectAttributes = (struct _OBJECT_ATTRIBUTES *)((char *)p_ObjectAttributes + 2);
      --v31;
    }
    while ( v31 );
    v33 = (struct _OBJECT_ATTRIBUTES *)((char *)p_ObjectAttributes - 2);
    if ( v31 )
      v33 = p_ObjectAttributes;
    LOWORD(v33->Length) = 0;
    if ( !v31 )
    {
LABEL_88:
      v18 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return -2147024809;
      v19 = 22;
      goto LABEL_94;
    }
  }
  v34 = -1073741824;
  if ( a3 != 2 )
    v34 = 0x80000000;
  FileW = CreateFileW((LPCWSTR)&ObjectAttributes, v34, 7u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_82;
  LastError = GetLastError();
  v23 = hDevice;
  if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
    goto LABEL_41;
LABEL_40:
  sub_18022F134(v23[2], (__int64)&ObjectAttributes, LastError);
LABEL_41:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x1805f4ecc  mov     [rsp-8+arg_10], rbx
0x1805f4ed1  mov     [rsp-8+arg_18], rsi
0x1805f4ed6  push    rbp
0x1805f4ed7  push    rdi
0x1805f4ed8  push    r12
0x1805f4eda  push    r14
0x1805f4edc  push    r15
0x1805f4ede  lea     rbp, [rsp-37h]
0x1805f4ee3  sub     rsp, 0A0h
0x1805f4eea  mov     rax, cs:__security_cookie
0x1805f4ef1  xor     rax, rsp
0x1805f4ef4  mov     [rbp+57h+var_28], rax
0x1805f4ef8  xor     r12d, r12d
0x1805f4efb  mov     r15d, r8d
0x1805f4efe  mov     rsi, rdx
0x1805f4f01  mov     r14, rcx
0x1805f4f04  test    rcx, rcx
0x1805f4f07  jnz     short loc_1805F4F0E
0x1805f4f09  call    sub_1801A08A8
0x1805f4f0e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1805f4f12  mov     [r14], rbx
0x1805f4f15  test    rsi, rsi
0x1805f4f18  jnz     short loc_1805F4F1F
0x1805f4f1a  call    sub_1801A08A8
0x1805f4f1f  mov     r8d, 8
0x1805f4f25  lea     rdx, aDevice_3; "\\Device\\"
0x1805f4f2c  mov     rcx, rsi
0x1805f4f2f  call    sub_180177520
0x1805f4f34  test    eax, eax
0x1805f4f36  jnz     loc_1805F5017
0x1805f4f3c  xorps   xmm0, xmm0
0x1805f4f3f  mov     dword ptr [rbp+57h+ObjectAttributes+4], r12d
0x1805f4f43  xorps   xmm1, xmm1
0x1805f4f46  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r12d
0x1805f4f4a  mov     rdx, rsi; SourceString
0x1805f4f4d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1805f4f51  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1805f4f55  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1805f4f59  call    cs:RtlInitUnicodeString
0x1805f4f5f  mov     edx, 30h ; '0'
0x1805f4f64  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1805f4f68  mov     [rbp+57h+ObjectAttributes.Length], edx
0x1805f4f6b  lea     rax, [rbp+57h+DestinationString]
0x1805f4f6f  xorps   xmm0, xmm0
0x1805f4f72  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x1805f4f76  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1805f4f7a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1805f4f7e  lea     r15d, [rdx-20h]
0x1805f4f82  mov     [rbp+57h+FileHandle], r12
0x1805f4f86  mov     [rsp+0C0h+OpenOptions], r15d; OpenOptions
0x1805f4f8b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1805f4f8f  mov     edx, 100003h; DesiredAccess
0x1805f4f94  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x1805f4f9c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1805f4fa0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1805f4fa5  call    cs:NtOpenFile
0x1805f4fab  mov     edi, eax
0x1805f4fad  test    eax, eax
0x1805f4faf  jns     short loc_1805F5004
0x1805f4fb1  lfence
0x1805f4fb4  mov     rcx, cs:hDevice
0x1805f4fbb  lea     r8, hDevice
0x1805f4fc2  cmp     rcx, r8
0x1805f4fc5  jz      short loc_1805F4FE7
0x1805f4fc7  test    byte ptr [rcx+1Ch], 1
0x1805f4fcb  jz      short loc_1805F4FE7
0x1805f4fcd  mov     rcx, [rcx+10h]
0x1805f4fd1  lea     r8, qword_180CE69F8
0x1805f4fd8  mov     edx, r15d
0x1805f4fdb  mov     [rsp+0C0h+ShareAccess], eax
0x1805f4fdf  mov     r9, rsi
0x1805f4fe2  call    sub_1801A569C
0x1805f4fe7  mov     ecx, edi; Status
0x1805f4fe9  call    cs:__imp_RtlNtStatusToDosError
0x1805f4fef  test    eax, eax
0x1805f4ff1  jle     loc_1805F5496
0x1805f4ff7  movzx   eax, ax
0x1805f4ffa  or      eax, 80070000h
0x1805f4fff  jmp     loc_1805F5496
0x1805f5004  cmp     [rbp+57h+FileHandle], rbx
0x1805f5008  jz      loc_1805F53F0
0x1805f500e  mov     rbx, [rbp+57h+FileHandle]
0x1805f5012  jmp     loc_1805F53F0
0x1805f5017  mov     edi, 4
0x1805f501c  lea     rdx, aDisk_0; "Disk"
0x1805f5023  mov     r8d, edi
0x1805f5026  mov     rcx, rsi
0x1805f5029  call    sub_180177520
0x1805f502e  test    eax, eax
0x1805f5030  jnz     loc_1805F5225
0x1805f5036  mov     rax, rbx
0x1805f5039  inc     rax
0x1805f503c  cmp     [rsi+rax*2], r12w
0x1805f5041  jnz     short loc_1805F5039
0x1805f5043  cmp     eax, 6
0x1805f5046  jb      loc_1805F51FA
0x1805f504c  movzx   ecx, word ptr [rsi+8]
0x1805f5050  mov     edx, 30h ; '0'
0x1805f5055  mov     r8w, 5
0x1805f505a  cmp     cx, dx
0x1805f505d  jb      short loc_1805F5065
0x1805f505f  cmp     cx, 39h ; '9'
0x1805f5063  jbe     short loc_1805F507C
0x1805f5065  lea     eax, [rcx-61h]
0x1805f5068  cmp     ax, r8w
0x1805f506c  jbe     short loc_1805F507C
0x1805f506e  sub     cx, 41h ; 'A'
0x1805f5072  cmp     cx, r8w
0x1805f5076  ja      loc_1805F51FA
0x1805f507c  movzx   ecx, word ptr [rsi+0Ah]
0x1805f5080  cmp     cx, dx
0x1805f5083  jb      short loc_1805F508B
0x1805f5085  cmp     cx, 39h ; '9'
0x1805f5089  jbe     short loc_1805F50A1
0x1805f508b  lea     eax, [rcx-61h]
0x1805f508e  cmp     ax, r8w
0x1805f5092  jbe     short loc_1805F50A1
0x1805f5094  lea     eax, [rcx-41h]
0x1805f5097  cmp     ax, r8w
0x1805f509b  ja      loc_1805F51FA
0x1805f50a1  call    sub_180177270
0x1805f50a6  movzx   ecx, word ptr [rsi+8]
0x1805f50aa  movzx   edi, ax
0x1805f50ad  call    sub_180177270
0x1805f50b2  movzx   ecx, ax
0x1805f50b5  call    sub_1805F4DCC
0x1805f50ba  mov     r8d, eax
0x1805f50bd  movzx   ecx, di
0x1805f50c0  add     r8d, r8d
0x1805f50c3  call    sub_1805F4DCC
0x1805f50c8  mov     edx, 15h
0x1805f50cd  lea     ecx, [rax+r8*8]
0x1805f50d1  cmp     ecx, 80h
0x1805f50d7  jb      short loc_1805F511C
0x1805f50d9  lea     r9d, [rcx-80h]
0x1805f50dd  lea     rcx, [rbp+57h+ObjectAttributes]
0x1805f50e1  lea     r8, aPhysicaldriveU; "\\\\.\\PHYSICALDRIVE%u"
0x1805f50e8  call    sub_1801A5F5C
0x1805f50ed  test    eax, eax
0x1805f50ef  jns     short loc_1805F5163
0x1805f50f1  mov     rcx, cs:hDevice
0x1805f50f8  lea     r8, hDevice
0x1805f50ff  cmp     rcx, r8
0x1805f5102  jz      loc_1805F5491
0x1805f5108  test    byte ptr [rcx+1Ch], 1
0x1805f510c  jz      loc_1805F5491
0x1805f5112  mov     edx, 12h
0x1805f5117  jmp     loc_1805F5476
0x1805f511c  add     cx, 41h ; 'A'
0x1805f5120  lea     r8, aC_4; "\\\\.\\%c:"
0x1805f5127  movzx   r9d, cx
0x1805f512b  lea     rcx, [rbp+57h+ObjectAttributes]
0x1805f512f  call    sub_1801A5F5C
0x1805f5134  test    eax, eax
0x1805f5136  jns     short loc_1805F5163
0x1805f5138  mov     rcx, cs:hDevice
0x1805f513f  lea     r8, hDevice
0x1805f5146  cmp     rcx, r8
0x1805f5149  jz      loc_1805F5491
0x1805f514f  test    byte ptr [rcx+1Ch], 1
0x1805f5153  jz      loc_1805F5491
0x1805f5159  mov     edx, 13h
0x1805f515e  jmp     loc_1805F5476
0x1805f5163  mov     edx, 0C0000000h
0x1805f5168  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x1805f516d  mov     eax, 80000000h
0x1805f5172  mov     [rsp+0C0h+OpenOptions], r12d; dwFlagsAndAttributes
0x1805f5177  cmp     r15d, 2
0x1805f517b  mov     [rsp+0C0h+ShareAccess], 3; dwCreationDisposition
0x1805f5183  lea     rcx, [rbp+57h+ObjectAttributes]; lpFileName
0x1805f5187  cmovnz  edx, eax; dwDesiredAccess
0x1805f518a  xor     r9d, r9d; lpSecurityAttributes
0x1805f518d  lea     r8d, [r9+7]; dwShareMode
0x1805f5191  call    cs:__imp_CreateFileW
0x1805f5197  cmp     rax, rbx
0x1805f519a  jnz     loc_1805F53ED
0x1805f51a0  call    cs:__imp_GetLastError
0x1805f51a6  mov     ebx, eax
0x1805f51a8  mov     rcx, cs:hDevice
0x1805f51af  lea     r8, hDevice
0x1805f51b6  cmp     rcx, r8
0x1805f51b9  jz      short loc_1805F51E6
0x1805f51bb  test    byte ptr [rcx+1Ch], 1
0x1805f51bf  jz      short loc_1805F51E6
0x1805f51c1  mov     edx, 14h
0x1805f51c6  mov     rcx, [rcx+10h]; LoggerHandle
0x1805f51ca  lea     rax, [rbp+57h+ObjectAttributes]
0x1805f51ce  mov     [rsp+0C0h+OpenOptions], ebx; char
0x1805f51d2  lea     r8, qword_180CE69F8
0x1805f51d9  mov     r9, rsi
0x1805f51dc  mov     qword ptr [rsp+0C0h+ShareAccess], rax; __int64
0x1805f51e1  call    sub_18022F134
0x1805f51e6  test    ebx, ebx
0x1805f51e8  jle     short loc_1805F51F3
0x1805f51ea  movzx   ebx, bx
0x1805f51ed  or      ebx, 80070000h
0x1805f51f3  mov     eax, ebx
0x1805f51f5  jmp     loc_1805F5496
0x1805f51fa  mov     rcx, cs:hDevice
0x1805f5201  lea     r8, hDevice
0x1805f5208  cmp     rcx, r8
0x1805f520b  jz      loc_1805F5491
0x1805f5211  test    byte ptr [rcx+1Ch], 1
0x1805f5215  jz      loc_1805F5491
0x1805f521b  mov     edx, 11h
0x1805f5220  jmp     loc_1805F5476
0x1805f5225  mov     r8, rdi
0x1805f5228  lea     rdx, asc_180C1E088; "\\\\.\\"
0x1805f522f  mov     rcx, rsi
0x1805f5232  call    sub_180177520
0x1805f5237  test    eax, eax
0x1805f5239  jz      short loc_1805F527C
0x1805f523b  mov     r8, rdi
0x1805f523e  lea     rdx, Str1; "\\\\?\\"
0x1805f5245  mov     rcx, rsi
0x1805f5248  call    sub_180177520
0x1805f524d  test    eax, eax
0x1805f524f  jz      short loc_1805F527C
0x1805f5251  mov     rcx, cs:hDevice
0x1805f5258  lea     r8, hDevice
0x1805f525f  cmp     rcx, r8
0x1805f5262  jz      loc_1805F5491
0x1805f5268  test    byte ptr [rcx+1Ch], 1
0x1805f526c  jz      loc_1805F5491
0x1805f5272  mov     edx, 19h
0x1805f5277  jmp     loc_1805F5476
0x1805f527c  mov     rdi, rbx
0x1805f527f  inc     rdi
0x1805f5282  cmp     [rsi+rdi*2], r12w
0x1805f5287  jnz     short loc_1805F527F
0x1805f5289  xor     eax, eax
0x1805f528b  xorps   xmm0, xmm0
0x1805f528e  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x1805f5292  mov     word ptr [rbp+57h+ObjectAttributes.SecurityQualityOfService], ax
0x1805f5296  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1805f529a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1805f529e  cmp     edi, 6
0x1805f52a1  jb      short loc_1805F5311
0x1805f52a3  movzx   ecx, word ptr [rsi+8]
0x1805f52a7  cmp     ecx, 61h ; 'a'
0x1805f52aa  jb      short loc_1805F52B1
0x1805f52ac  cmp     ecx, 7Ah ; 'z'
0x1805f52af  jbe     short loc_1805F52BE
0x1805f52b1  lea     eax, [rcx-41h]
0x1805f52b4  mov     edx, 19h
0x1805f52b9  cmp     ax, dx
0x1805f52bc  ja      short loc_1805F5311
0x1805f52be  mov     eax, 3Ah ; ':'
0x1805f52c3  cmp     ax, [rsi+0Ah]
0x1805f52c7  jnz     short loc_1805F5311
0x1805f52c9  lea     edi, [rax-25h]
0x1805f52cc  mov     r9d, ecx
0x1805f52cf  mov     edx, edi
0x1805f52d1  lea     r8, aC_4; "\\\\.\\%c:"
0x1805f52d8  lea     rcx, [rbp+57h+ObjectAttributes]
0x1805f52dc  call    sub_1801A5F5C
0x1805f52e1  test    eax, eax
0x1805f52e3  jns     loc_1805F53B4
0x1805f52e9  mov     rcx, cs:hDevice
0x1805f52f0  lea     r8, hDevice
0x1805f52f7  cmp     rcx, r8
0x1805f52fa  jz      loc_1805F5491
0x1805f5300  test    byte ptr [rcx+1Ch], 1
0x1805f5304  jz      loc_1805F5491
0x1805f530a  mov     edx, edi
0x1805f530c  jmp     loc_1805F5476
0x1805f5311  cmp     edi, 11h
0x1805f5314  jbe     loc_1805F5458
0x1805f531a  mov     r8d, 11h
0x1805f5320  lea     rdx, aPhysicaldrive; "\\\\.\\PHYSICALDRIVE"
0x1805f5327  mov     rcx, rsi
0x1805f532a  call    sub_180177520
0x1805f532f  test    eax, eax
0x1805f5331  jnz     loc_1805F5458
0x1805f5337  lea     rax, [rsi+22h]
0x1805f533b  jmp     short loc_1805F5355
0x1805f533d  cmp     cx, 2Fh ; '/'
0x1805f5341  jz      loc_1805F53FA
0x1805f5347  cmp     cx, 5Ch ; '\'
0x1805f534b  jz      loc_1805F53FA
0x1805f5351  add     rax, 2
0x1805f5355  movzx   ecx, word ptr [rax]
0x1805f5358  test    cx, cx
0x1805f535b  jnz     short loc_1805F533D
0x1805f535d  mov     eax, edi
0x1805f535f  cmp     eax, 7FFFFFFEh
0x1805f5364  ja      loc_1805F5438
0x1805f536a  mov     r8d, eax
0x1805f536d  lea     rcx, [rbp+57h+ObjectAttributes]
0x1805f5371  lea     rax, [rbp+57h+ObjectAttributes]
0x1805f5375  mov     rdx, rsi
0x1805f5378  sub     rdx, rax
0x1805f537b  mov     edi, 15h
0x1805f5380  lea     rax, [rdi-15h]
0x1805f5384  add     rax, r8
0x1805f5387  jz      short loc_1805F539F
0x1805f5389  movzx   eax, word ptr [rdx+rcx]
0x1805f538d  test    ax, ax
0x1805f5390  jz      short loc_1805F539F
0x1805f5392  mov     [rcx], ax
  ... truncated ...
```
