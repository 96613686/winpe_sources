# EtwpSetWmiGuidSecurity(ushort *,_ACL *,ulong)

- ea: `0x1800140cc`
- end: `0x1800143d5`
- name: `?EtwpSetWmiGuidSecurity@@YAKPEAGPEAU_ACL@@K@Z`
- size: `777`
- prototype: `unsigned int(unsigned __int16 *, struct _ACL *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013e28`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x1800140cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800142a9`
- `ntdll!RtlInitUnicodeString` at `0x1800142a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001431b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001431b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014378`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001428e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001428e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014271`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143a6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180014313`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180014313`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001433a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001433a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180014197`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180014197`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800141aa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800141aa`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001436e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001436e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001417b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001417b`

## pseudocode

```c
__int64 __fastcall EtwpSetWmiGuidSecurity(unsigned __int16 *a1, struct _ACL *a2, SECURITY_INFORMATION a3)
{
  HANDLE v6; // rsi
  __int64 FileW; // rdi
  DWORD v8; // ebx
  BOOL v9; // eax
  __int16 v10; // cx
  int v11; // r15d
  WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  BOOL OverlappedResult; // ebx
  DWORD LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h]
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  struct _OVERLAPPED Overlapped; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-48h] BYREF
  __int128 p_DestinationString; // [rsp+C8h] [rbp-38h]
  __int128 v31; // [rsp+D8h] [rbp-28h]
  WCHAR SourceString[10]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[76]; // [rsp+104h] [rbp+4h] BYREF

  DestinationString = 0;
  v26 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  wcscpy(SourceString, L"\\WmiGuid\\");
  v29 = 0;
  BytesReturned = 0;
  v6 = 0;
  p_DestinationString = 0;
  FileW = -1;
  v31 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(v33, 0, 0x4Au);
  Handle = 0;
  OutBuffer = 0;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  v8 = 8;
  if ( a3 == 8 )
  {
    v9 = SetSecurityDescriptorSacl(pSecurityDescriptor, 1, a2, 0);
    v10 = 512;
    v11 = 0x1000000;
  }
  else
  {
    v9 = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, a2, 0);
    v10 = 256;
    v11 = 0x40000;
  }
  WORD1(pSecurityDescriptor[0]) |= v10;
  if ( !v9 )
    goto LABEL_27;
  v12 = SourceString;
  v13 = 47;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v13;
  }
  while ( v13 );
  v14 = (47 - v13) & -(__int64)(v13 != 0);
  if ( v13 )
  {
    v15 = 2147483646;
    v16 = &SourceString[v14];
    v17 = 47 - v14;
    if ( 47 != v14 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*a1 )
          break;
        *v16++ = *a1++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
    if ( v17 )
    {
      FileW = (__int64)CreateFileW(L"\\\\.\\WMIDataDevice", 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
      if ( FileW == -1 )
        goto LABEL_27;
      Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
      if ( !Overlapped.hEvent )
        goto LABEL_27;
      RtlInitUnicodeString(&DestinationString, SourceString);
      DWORD2(OutBuffer) = v11;
      p_DestinationString = (unsigned __int64)&DestinationString;
      v29 = 0;
      *(_QWORD *)&OutBuffer = &v29;
      v31 = 0;
      LODWORD(v29) = 48;
      do
      {
        OverlappedResult = DeviceIoControl(
                             (HANDLE)FileW,
                             0x224108u,
                             &OutBuffer,
                             0x18u,
                             &OutBuffer,
                             0x18u,
                             &BytesReturned,
                             &Overlapped);
        if ( GetLastError() == 997 )
          OverlappedResult = GetOverlappedResult((HANDLE)FileW, &Overlapped, &BytesReturned, 1);
        if ( OverlappedResult )
        {
          v8 = 0;
          goto LABEL_26;
        }
        LastError = GetLastError();
        v8 = LastError;
      }
      while ( LastError == 4203 );
      if ( LastError )
        goto LABEL_28;
LABEL_26:
      v6 = Handle;
      if ( !SetKernelObjectSecurity(Handle, a3, pSecurityDescriptor) )
LABEL_27:
        v8 = GetLastError();
    }
  }
LABEL_28:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  if ( v6 )
    CloseHandle(v6);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v8;
}

```

## disassembly

```asm
0x1800140cc  mov     [rsp-8+arg_0], rbx
0x1800140d1  push    rbp
0x1800140d2  push    rsi
0x1800140d3  push    rdi
0x1800140d4  push    r12
0x1800140d6  push    r13
0x1800140d8  push    r14
0x1800140da  push    r15
0x1800140dc  lea     rbp, [rsp-60h]
0x1800140e1  sub     rsp, 160h
0x1800140e8  mov     rax, cs:__security_cookie
0x1800140ef  xor     rax, rsp
0x1800140f2  mov     [rbp+90h+var_40], rax
0x1800140f6  xorps   xmm1, xmm1
0x1800140f9  xorps   xmm0, xmm0
0x1800140fc  xor     r13d, r13d
0x1800140ff  xor     eax, eax
0x180014101  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180014105  mov     r12d, r8d
0x180014108  mov     r15, rdx
0x18001410b  movdqu  xmmword ptr [rbp+90h+Overlapped.InternalHigh], xmm0
0x180014110  mov     r14, rcx
0x180014113  mov     [rbp+90h+var_110], rax
0x180014117  movups  xmm0, xmmword ptr cs:aWmiguid; "\\WmiGuid\\"
0x18001411e  mov     eax, dword ptr cs:aWmiguid+10h; "\\"
0x180014124  lea     r8d, [r13+4Ah]; Size
0x180014128  xor     edx, edx; Val
0x18001412a  mov     [rbp+90h+Overlapped.Internal], r13
0x18001412e  lea     rcx, [rbp+90h+var_8C]; void *
0x180014132  movaps  xmmword ptr [rbp+90h+SourceString], xmm0
0x180014136  movups  [rbp+90h+var_D8], xmm1
0x18001413a  mov     [rsp+190h+BytesReturned], r13d
0x18001413f  mov     esi, r13d
0x180014142  movups  [rbp+90h+var_C8], xmm1
0x180014146  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001414a  mov     [rbp+90h+var_90], eax
0x18001414d  movups  [rbp+90h+var_B8], xmm1
0x180014151  movups  [rsp+190h+pSecurityDescriptor], xmm1
0x180014156  movups  [rsp+190h+var_120], xmm1
0x18001415b  call    memset_0
0x180014160  xorps   xmm0, xmm0
0x180014163  mov     [rbp+90h+Overlapped.hEvent], r13
0x180014167  xor     eax, eax
0x180014169  lea     edx, [rdi+2]; dwRevision
0x18001416c  lea     rcx, [rsp+190h+pSecurityDescriptor]; pSecurityDescriptor
0x180014171  mov     [rsp+190h+Handle], rax
0x180014176  movups  [rsp+190h+OutBuffer], xmm0
0x18001417b  call    cs:__imp_InitializeSecurityDescriptor
0x180014181  xor     r9d, r9d; bDaclDefaulted
0x180014184  lea     ebx, [rdi+9]
0x180014187  lea     edx, [rdi+2]; bDaclPresent
0x18001418a  mov     r8, r15; pDacl
0x18001418d  lea     rcx, [rsp+190h+pSecurityDescriptor]; pSecurityDescriptor
0x180014192  cmp     r12d, ebx
0x180014195  jnz     short loc_1800141AA
0x180014197  call    cs:__imp_SetSecurityDescriptorSacl
0x18001419d  mov     ecx, 200h
0x1800141a2  mov     r15d, 1000000h
0x1800141a8  jmp     short loc_1800141BB
0x1800141aa  call    cs:__imp_SetSecurityDescriptorDacl
0x1800141b0  mov     ecx, 100h
0x1800141b5  mov     r15d, 40000h
0x1800141bb  or      word ptr [rsp+190h+pSecurityDescriptor+2], cx
0x1800141c0  test    eax, eax
0x1800141c2  jz      loc_180014378
0x1800141c8  mov     edx, 2Fh ; '/'
0x1800141cd  lea     rax, [rbp+90h+SourceString]
0x1800141d1  mov     r8d, edx
0x1800141d4  cmp     [rax], r13w
0x1800141d8  jz      short loc_1800141E4
0x1800141da  add     rax, 2
0x1800141de  sub     r8, 1
0x1800141e2  jnz     short loc_1800141D4
0x1800141e4  mov     rcx, rdx
0x1800141e7  mov     rax, r8
0x1800141ea  sub     rcx, r8
0x1800141ed  neg     rax
0x1800141f0  sbb     r9, r9
0x1800141f3  and     r9, rcx
0x1800141f6  test    r8, r8
0x1800141f9  jz      loc_180014380
0x1800141ff  lea     rax, [rbp+90h+SourceString]
0x180014203  mov     ecx, 7FFFFFFEh
0x180014208  lea     rax, [rax+r9*2]
0x18001420c  sub     rdx, r9
0x18001420f  jz      short loc_180014235
0x180014211  test    rcx, rcx
0x180014214  jz      short loc_180014235
0x180014216  movzx   r8d, word ptr [r14]
0x18001421a  test    r8w, r8w
0x18001421e  jz      short loc_180014235
0x180014220  mov     [rax], r8w
0x180014224  add     r14, 2
0x180014228  add     rax, 2
0x18001422c  dec     rcx
0x18001422f  sub     rdx, 1
0x180014233  jnz     short loc_180014211
0x180014235  test    rdx, rdx
0x180014238  lea     rcx, [rax-2]
0x18001423c  cmovnz  rcx, rax
0x180014240  mov     [rcx], r13w
0x180014244  jz      loc_180014380
0x18001424a  mov     [rsp+190h+hTemplateFile], r13; hTemplateFile
0x18001424f  lea     rcx, FileName; "\\\\.\\WMIDataDevice"
0x180014256  mov     [rsp+190h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18001425e  xor     r9d, r9d; lpSecurityAttributes
0x180014261  xor     r8d, r8d; dwShareMode
0x180014264  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x18001426c  mov     edx, 0C0000000h; dwDesiredAccess
0x180014271  call    cs:__imp_CreateFileW
0x180014277  mov     rdi, rax
0x18001427a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001427e  jz      loc_180014378
0x180014284  xor     r9d, r9d; lpName
0x180014287  xor     r8d, r8d; bInitialState
0x18001428a  xor     edx, edx; bManualReset
0x18001428c  xor     ecx, ecx; lpEventAttributes
0x18001428e  call    cs:__imp_CreateEventW
0x180014294  mov     [rbp+90h+Overlapped.hEvent], rax
0x180014298  test    rax, rax
0x18001429b  jz      loc_180014378
0x1800142a1  lea     rdx, [rbp+90h+SourceString]; SourceString
0x1800142a5  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800142a9  call    cs:__imp_RtlInitUnicodeString
0x1800142af  xorps   xmm0, xmm0
0x1800142b2  mov     dword ptr [rsp+190h+OutBuffer+8], r15d
0x1800142b7  lea     rax, [rbp+90h+DestinationString]
0x1800142bb  mov     r14d, 18h
0x1800142c1  movups  [rbp+90h+var_C8], xmm0
0x1800142c5  mov     qword ptr [rbp+90h+var_C8], rax
0x1800142c9  lea     rax, [rbp+90h+var_D8]
0x1800142cd  movups  [rbp+90h+var_D8], xmm0
0x1800142d1  mov     qword ptr [rsp+190h+OutBuffer], rax
0x1800142d6  movups  [rbp+90h+var_B8], xmm0
0x1800142da  mov     dword ptr [rbp+90h+var_D8], 30h ; '0'
0x1800142e1  lea     rax, [rbp+90h+Overlapped]
0x1800142e5  mov     r9d, r14d; nInBufferSize
0x1800142e8  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x1800142ed  lea     r8, [rsp+190h+OutBuffer]; lpInBuffer
0x1800142f2  lea     rax, [rsp+190h+BytesReturned]
0x1800142f7  mov     edx, 224108h; dwIoControlCode
0x1800142fc  mov     [rsp+190h+hTemplateFile], rax; lpBytesReturned
0x180014301  mov     rcx, rdi; hDevice
0x180014304  lea     rax, [rsp+190h+OutBuffer]
0x180014309  mov     [rsp+190h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18001430e  mov     qword ptr [rsp+190h+dwCreationDisposition], rax; lpOutBuffer
0x180014313  call    cs:__imp_DeviceIoControl
0x180014319  mov     ebx, eax
0x18001431b  call    cs:__imp_GetLastError
0x180014321  cmp     eax, 3E5h
0x180014326  jnz     short loc_180014342
0x180014328  mov     r9d, 1; bWait
0x18001432e  lea     r8, [rsp+190h+BytesReturned]; lpNumberOfBytesTransferred
0x180014333  lea     rdx, [rbp+90h+Overlapped]; lpOverlapped
0x180014337  mov     rcx, rdi; hFile
0x18001433a  call    cs:__imp_GetOverlappedResult
0x180014340  mov     ebx, eax
0x180014342  test    ebx, ebx
0x180014344  jnz     short loc_18001435B
0x180014346  call    cs:__imp_GetLastError
0x18001434c  mov     ebx, eax
0x18001434e  cmp     eax, 106Bh
0x180014353  jz      short loc_1800142E1
0x180014355  test    eax, eax
0x180014357  jnz     short loc_180014380
0x180014359  jmp     short loc_18001435E
0x18001435b  mov     ebx, r13d
0x18001435e  mov     rsi, [rsp+190h+Handle]
0x180014363  lea     r8, [rsp+190h+pSecurityDescriptor]; SecurityDescriptor
0x180014368  mov     rcx, rsi; Handle
0x18001436b  mov     edx, r12d; SecurityInformation
0x18001436e  call    cs:__imp_SetKernelObjectSecurity
0x180014374  test    eax, eax
0x180014376  jnz     short loc_180014380
0x180014378  call    cs:__imp_GetLastError
0x18001437e  mov     ebx, eax
0x180014380  mov     rcx, [rbp+90h+Overlapped.hEvent]; hObject
0x180014384  test    rcx, rcx
0x180014387  jz      short loc_18001438F
0x180014389  call    cs:__imp_CloseHandle
0x18001438f  test    rsi, rsi
0x180014392  jz      short loc_18001439D
0x180014394  mov     rcx, rsi; hObject
0x180014397  call    cs:__imp_CloseHandle
0x18001439d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800143a1  jz      short loc_1800143AC
0x1800143a3  mov     rcx, rdi; hObject
0x1800143a6  call    cs:__imp_CloseHandle
0x1800143ac  mov     eax, ebx
0x1800143ae  mov     rcx, [rbp+90h+var_40]
0x1800143b2  xor     rcx, rsp; StackCookie
0x1800143b5  call    __security_check_cookie
0x1800143ba  mov     rbx, [rsp+190h+arg_0]
0x1800143c2  add     rsp, 160h
0x1800143c9  pop     r15
0x1800143cb  pop     r14
0x1800143cd  pop     r13
0x1800143cf  pop     r12
0x1800143d1  pop     rdi
0x1800143d2  pop     rsi
0x1800143d3  pop     rbp
0x1800143d4  retn
```
