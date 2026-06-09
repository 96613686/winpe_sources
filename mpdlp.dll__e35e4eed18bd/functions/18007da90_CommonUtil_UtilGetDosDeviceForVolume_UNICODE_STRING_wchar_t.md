# CommonUtil::UtilGetDosDeviceForVolume(_UNICODE_STRING *,wchar_t * *)

- ea: `0x18007da90`
- end: `0x18007e378`
- name: `?UtilGetDosDeviceForVolume@CommonUtil@@YAJPEAU_UNICODE_STRING@@PEAPEA_W@Z`
- size: `2280`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, struct _UNICODE_STRING *, wchar_t **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007e57c`

## callees

- `0x18007da90`
- `0x18007e378`
- `0x18007e3a8`
- `0x18007e41c`
- `0x18007e4e0`
- `0x18007f51c`
- `0x180080030`
- `0x1800809d0`
- `0x180101af8`
- `0x180105f50`
- `0x18010cb40`
- `0x18023a290`
- `0x18023a310`
- `0x18023a6d0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18007ddd6`
- `MpClient!MpFreeMemory` at `0x18007de5a`
- `MpClient!MpFreeMemory` at `0x18007e23c`
- `MpClient!MpFreeMemory` at `0x18007e302`
- `MpClient!MpFreeMemory` at `0x18007e311`
- `MpClient!MpFreeMemory` at `0x18007e31f`
- `MpClient!MpFreeMemory` at `0x18007e332`
- `MpClient!MpFreeMemory` at `0x18007ddd6`
- `MpClient!MpFreeMemory` at `0x18007de5a`
- `MpClient!MpFreeMemory` at `0x18007e23c`
- `MpClient!MpFreeMemory` at `0x18007e302`
- `MpClient!MpFreeMemory` at `0x18007e311`
- `MpClient!MpFreeMemory` at `0x18007e31f`
- `MpClient!MpFreeMemory` at `0x18007e332`
- `MpClient!MpAllocMemory` at `0x18007dc1c`
- `MpClient!MpAllocMemory` at `0x18007dd8c`
- `MpClient!MpAllocMemory` at `0x18007de3f`
- `MpClient!MpAllocMemory` at `0x18007dc1c`
- `MpClient!MpAllocMemory` at `0x18007dd8c`
- `MpClient!MpAllocMemory` at `0x18007de3f`
- `ntdll!NtCreateFile` at `0x18007dd03`
- `ntdll!NtCreateFile` at `0x18007dd03`
- `ntdll!RtlPrefixUnicodeString` at `0x18007df98`
- `ntdll!RtlPrefixUnicodeString` at `0x18007df98`
- `ntdll!NtWaitForSingleObject` at `0x18007dec2`
- `ntdll!NtWaitForSingleObject` at `0x18007dec2`
- `ntdll!RtlInitUnicodeString` at `0x18007dc9e`
- `ntdll!RtlInitUnicodeString` at `0x18007e04f`
- `ntdll!RtlInitUnicodeString` at `0x18007dc9e`
- `ntdll!RtlInitUnicodeString` at `0x18007e04f`
- `ntdll!NtDeviceIoControlFile` at `0x18007deab`
- `ntdll!NtDeviceIoControlFile` at `0x18007deab`
- `ntdll!NtClose` at `0x18007e2dc`
- `ntdll!NtClose` at `0x18007e2dc`
- `KERNEL32!ResetEvent` at `0x18007de25`
- `KERNEL32!ResetEvent` at `0x18007de25`
- `KERNEL32!CreateEventW` at `0x18007dd56`
- `KERNEL32!CreateEventW` at `0x18007dd56`
- `KERNEL32!CloseHandle` at `0x18007e341`
- `KERNEL32!CloseHandle` at `0x18007e341`

## string_xrefs

- `0x18007dc90`: `\Device\MountPointManager`
- `0x18007db58`: `GetVolumePathNamesForVolumeNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CommonUtil::UtilGetDosDeviceForVolume(
        const void **this,
        struct _UNICODE_STRING *a2,
        wchar_t **a3,
        bool a4)
{
  void *v4; // rbx
  _DWORD *v5; // rsi
  ULONG v6; // r15d
  int LoadedKernel32ProcAddress; // eax
  int inited; // edi
  __int64 v9; // r14
  char *p_InputBuffer; // r13
  __int64 v11; // r9
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  NTSTATUS v14; // edi
  HANDLE EventW; // rax
  void *v16; // r12
  unsigned int v17; // eax
  size_t v18; // rdi
  __int64 v19; // rdi
  _DWORD *v20; // r12
  NTSTATUS Status; // edi
  int v22; // r15d
  unsigned int v23; // edi
  int LastFailure; // eax
  unsigned __int64 v25; // rdx
  unsigned __int16 v26; // r8
  USHORT Length; // r10
  __int16 v28; // dx
  PWSTR Buffer; // rcx
  _WORD *v30; // r9
  WCHAR *v31; // r11
  unsigned int v32; // r8d
  _BYTE *j; // r12
  __int64 v34; // rax
  unsigned int v36; // [rsp+68h] [rbp-A0h]
  unsigned int v37; // [rsp+6Ch] [rbp-9Ch]
  __int64 i; // [rsp+70h] [rbp-98h]
  ULONG InputBufferLength; // [rsp+78h] [rbp-90h]
  _OWORD v41[3]; // [rsp+88h] [rbp-80h] BYREF
  struct _UNICODE_STRING *v42; // [rsp+B8h] [rbp-50h]
  __int128 v43; // [rsp+E0h] [rbp-28h]
  HANDLE v44; // [rsp+F0h] [rbp-18h]
  __int128 v45; // [rsp+118h] [rbp+10h]
  UNICODE_STRING String2; // [rsp+128h] [rbp+20h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+30h] BYREF
  __int64 v48; // [rsp+140h] [rbp+38h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v50[37]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v51; // [rsp+3C8h] [rbp+2C0h] BYREF
  int v52; // [rsp+3D0h] [rbp+2C8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+3D8h] [rbp+2D0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+3E8h] [rbp+2E0h] BYREF
  _BYTE v55[528]; // [rsp+3F8h] [rbp+2F0h] BYREF
  char InputBuffer; // [rsp+608h] [rbp+500h] BYREF

  v42 = a2;
  *(_QWORD *)&a2->Length = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v37 = 0;
  String2 = 0;
  memset(v50, 0, 584);
  v43 = 0;
  v45 = 0;
  memset(v41, 0, sizeof(v41));
  v52 = 0;
  v51 = 0;
  v48 = 0;
  if ( !qword_180313918 )
  {
    LOBYTE(a3) = 1;
    LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                  (CommonUtil *)&v48,
                                  (__int64 (**)(void))"GetVolumePathNamesForVolumeNameW",
                                  (const char *)a3,
                                  a4);
    inited = LoadedKernel32ProcAddress;
    if ( LoadedKernel32ProcAddress < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_167bf0eddf4c33edfd51d100c28ec711_Traceguids,
          (unsigned int)LoadedKernel32ProcAddress);
      goto LABEL_6;
    }
    if ( !qword_180313918 )
      qword_180313918 = v48;
  }
  memset(v50, 0, 0x248u);
  inited = UtilInitMpBuffer(&v50[1], &v50[4], 520);
  if ( inited < 0 )
  {
LABEL_6:
    v9 = v45;
    goto LABEL_99;
  }
  *((_QWORD *)&v50[0] + 1) = *(_QWORD *)&v50[1];
  WORD1(v50[0]) = WORD4(v50[1]);
  LOWORD(v50[0]) = 0;
  v43 = 0;
  p_InputBuffer = &InputBuffer;
  v9 = MpAllocMemory(4096);
  if ( !v9 )
  {
    v11 = 2147942414LL;
    inited = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_99;
    v13 = 26;
    goto LABEL_98;
  }
  v36 = 4096;
  *((_QWORD *)&v41[0] + 1) = 520;
  memset((char *)&v41[1] + 12, 0, 20);
  *(_QWORD *)&v41[1] = v55;
  DWORD2(v41[1]) = 520;
  *(_QWORD *)&v41[0] = v55;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\MountPointManager");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = NtCreateFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x40u, 0, 0);
  if ( v14 < 0 )
  {
    inited = v14 | 0x10000000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_99;
    v13 = 28;
LABEL_18:
    _mm_lfence();
    v11 = (unsigned int)inited;
    v12 = WPP_GLOBAL_Control;
    goto LABEL_98;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v16 = EventW;
  if ( !EventW )
  {
    LastFailure = HrGetLastFailure();
    inited = LastFailure;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_99;
    v13 = 29;
LABEL_97:
    v11 = (unsigned int)LastFailure;
LABEL_98:
    WPP_SF_d(v12[2], v13, WPP_167bf0eddf4c33edfd51d100c28ec711_Traceguids, v11);
    goto LABEL_99;
  }
  v4 = EventW;
  v44 = EventW;
  v17 = *(unsigned __int16 *)this + 26;
  InputBufferLength = v17;
  v18 = v17;
  if ( v17 > 0x100 )
  {
    _mm_lfence();
    p_InputBuffer = (char *)MpAllocMemory(v17);
    if ( !p_InputBuffer )
    {
      v11 = 2147942414LL;
      inited = -2147024882;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_99;
      v13 = 30;
      goto LABEL_98;
    }
    *(_QWORD *)&v43 = p_InputBuffer;
  }
  memset(p_InputBuffer, 0, v18);
  *((_WORD *)p_InputBuffer + 10) = *(_WORD *)this;
  *((_DWORD *)p_InputBuffer + 4) = 24;
  memmove(p_InputBuffer + 24, this[1], *(unsigned __int16 *)this);
  v19 = v9;
  for ( i = v9; ; v19 = i )
  {
    ResetEvent(v16);
    v6 += 4096;
    if ( v6 > v36 )
    {
      _mm_lfence();
      v19 = MpAllocMemory(v6);
      if ( !v19 )
      {
        v20 = v5;
        goto LABEL_33;
      }
      MpFreeMemory(v9);
      v9 = v19;
      i = v19;
      v36 = v6;
    }
    v5 = (_DWORD *)v19;
    v20 = (_DWORD *)v19;
LABEL_33:
    Status = NtDeviceIoControlFile(
               FileHandle,
               v4,
               0,
               0,
               &IoStatusBlock,
               0x6D0008u,
               p_InputBuffer,
               InputBufferLength,
               v5,
               v6);
    if ( Status != 259 )
      goto LABEL_36;
    Status = NtWaitForSingleObject(v4, 1u, 0);
    if ( Status >= 0 )
      break;
LABEL_37:
    if ( Status == -2147483643 )
    {
      ++v37;
      v16 = v4;
      if ( v37 < 0x40 )
        continue;
    }
    inited = Status | 0x10000000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 32;
      goto LABEL_18;
    }
    goto LABEL_99;
  }
  Status = IoStatusBlock.Status;
LABEL_36:
  if ( Status < 0 )
    goto LABEL_37;
  if ( !v5[1] )
  {
    v11 = 2147549183LL;
    inited = -2147418113;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 33;
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  v22 = 0;
  v23 = 0;
  do
  {
    String2.Buffer = (PWSTR)((char *)v5 + (unsigned int)v20[6 * v23 + 2]);
    String2.Length = v20[6 * v23 + 3];
    String2.MaximumLength = String2.Length;
    if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
      break;
    ++v23;
  }
  while ( v23 < v5[1] );
  if ( v23 >= v5[1] )
  {
    v11 = 2147549183LL;
    inited = -2147418113;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 34;
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  String2.Buffer = (PWSTR)((char *)v5 + (unsigned int)v5[6 * v23 + 2]);
  String2.Length = v5[6 * v23 + 3];
  String2.MaximumLength = String2.Length;
  LOWORD(v50[0]) = 0;
  LastFailure = UtilAppendMpStringBufferUnicodeStr(v50, &String2);
  inited = LastFailure;
  if ( LastFailure < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 35;
      goto LABEL_97;
    }
    goto LABEL_99;
  }
  RtlInitUnicodeString(&String2, L"\\");
  v25 = LOWORD(v50[0]) + (unsigned int)String2.Length + 2LL;
  if ( v25 > 0xFFFE )
  {
    inited = -2147024809;
    goto LABEL_63;
  }
  LastFailure = UtilPrepareMpBuffer(&v50[1], v25, 0, 0);
  inited = LastFailure;
  if ( LastFailure >= 0 )
  {
    *((_QWORD *)&v50[0] + 1) = *(_QWORD *)&v50[1];
    v26 = WORD4(v50[1]);
    WORD1(v50[0]) = WORD4(v50[1]);
    Length = String2.Length;
    if ( String2.Length )
    {
      v28 = v50[0];
      if ( LOWORD(v50[0]) + (unsigned int)String2.Length > WORD4(v50[1]) )
      {
        inited = -2147024774;
LABEL_63:
        LastFailure = inited;
        goto LABEL_64;
      }
      Buffer = String2.Buffer;
      v30 = (_WORD *)(*(_QWORD *)&v50[1] + 2 * ((unsigned __int64)LOWORD(v50[0]) >> 1));
      v31 = (PWSTR)((char *)String2.Buffer + String2.Length);
      if ( String2.Buffer < v31 )
      {
        do
          *v30++ = *Buffer++;
        while ( Buffer < v31 );
        v26 = WORD1(v50[0]);
        v28 = v50[0];
      }
      LOWORD(v50[0]) = Length + v28;
      if ( (unsigned __int16)(Length + v28) < v26 )
        *v30 = 0;
    }
    *(_WORD *)(*((_QWORD *)&v50[0] + 1) + 2LL) = 92;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_167bf0eddf4c33edfd51d100c28ec711_Traceguids,
        *((_QWORD *)&v50[0] + 1));
    v32 = 520;
    for ( j = v55;
          !(unsigned int)((__int64 (__fastcall *)(_QWORD, _BYTE *, _QWORD, int *))qword_180313918)(
                           *((_QWORD *)&v50[0] + 1),
                           j,
                           v32 >> 1,
                           &v52);
          j = *(_BYTE **)&v41[0] )
    {
      LastFailure = HrGetLastFailure();
      inited = LastFailure;
      if ( LastFailure != -2147024662 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 38;
          goto LABEL_97;
        }
        goto LABEL_99;
      }
      LastFailure = UtilPrepareMpBuffer(v41, (unsigned int)(2 * v52), 1, 0);
      inited = LastFailure;
      if ( LastFailure < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 39;
          goto LABEL_97;
        }
        goto LABEL_99;
      }
      if ( (unsigned int)++v22 >= 0x40 )
        break;
      v32 = DWORD2(v41[0]);
    }
    if ( v51 )
    {
      MpFreeMemory(v51);
      v51 = 0;
    }
    LastFailure = MpAllocSprintfW(&v51, L"%s", j);
    inited = LastFailure;
    if ( LastFailure >= 0 )
    {
      v34 = v51;
      v51 = 0;
      *(_QWORD *)&v42->Length = v34;
      inited = 0;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 40;
        goto LABEL_97;
      }
    }
    goto LABEL_99;
  }
LABEL_64:
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 36;
    goto LABEL_97;
  }
LABEL_99:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( (int)UtilFreeMpBuffer(&v50[1]) >= 0 )
    v50[0] = 0;
  if ( *(_QWORD *)&v41[2] )
    MpFreeMemory(*(_QWORD *)&v41[2]);
  if ( (_QWORD)v43 )
    MpFreeMemory(v43);
  if ( v9 )
    MpFreeMemory(v9);
  if ( v51 )
    MpFreeMemory(v51);
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18007da90  mov     rax, rsp
0x18007da93  mov     [rax+18h], rbx
0x18007da97  push    rbp
0x18007da98  push    rsi
0x18007da99  push    rdi
0x18007da9a  push    r12
0x18007da9c  push    r13
0x18007da9e  push    r14
0x18007daa0  push    r15
0x18007daa2  lea     rbp, [rax-658h]
0x18007daa9  sub     rsp, 720h
0x18007dab0  movaps  xmmword ptr [rax-48h], xmm6
0x18007dab4  mov     rax, cs:__security_cookie
0x18007dabb  xor     rax, rsp
0x18007dabe  mov     [rbp+650h+var_50], rax
0x18007dac5  mov     [rbp+650h+var_6A0], rdx
0x18007dac9  mov     [rsp+750h+var_6E8], rcx
0x18007dace  xor     r14d, r14d
0x18007dad1  mov     [rdx], r14
0x18007dad4  xorps   xmm0, xmm0
0x18007dad7  movups  xmmword ptr [rbp+650h+ObjectAttributes.Length], xmm0
0x18007dadb  movups  xmmword ptr [rbp+650h+ObjectAttributes.ObjectName], xmm0
0x18007dadf  movups  xmmword ptr [rbp+650h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007dae3  movups  xmmword ptr [rbp+650h+DestinationString.Length], xmm0
0x18007daea  xorps   xmm1, xmm1
0x18007daed  movups  xmmword ptr [rbp+650h+IoStatusBlock], xmm1
0x18007daf4  mov     [rbp+650h+FileHandle], r14
0x18007daf8  mov     ebx, r14d
0x18007dafb  mov     esi, r14d
0x18007dafe  mov     r15d, r14d
0x18007db01  mov     dword ptr [rsp+750h+var_6F0+4], r14d
0x18007db06  movups  xmmword ptr [rbp+650h+String2.Length], xmm0
0x18007db0a  mov     word ptr [rbp+650h+var_5E0], r14w
0x18007db0f  xor     edx, edx; Val
0x18007db11  mov     r8d, 246h; Size
0x18007db17  lea     rcx, [rbp+650h+var_5E0+2]; void *
0x18007db1b  call    memset
0x18007db20  xorps   xmm0, xmm0
0x18007db23  movups  [rbp+650h+var_678], xmm0
0x18007db27  xorps   xmm1, xmm1
0x18007db2a  movups  [rbp+650h+var_640], xmm1
0x18007db2e  movups  [rbp+650h+var_6D0], xmm0
0x18007db32  movups  [rbp+650h+var_6C0], xmm0
0x18007db36  movups  [rbp+650h+var_6B0], xmm0
0x18007db3a  mov     [rbp+650h+var_388], r14d
0x18007db41  mov     [rbp+650h+var_390], r14
0x18007db48  mov     [rbp+650h+var_618], r14
0x18007db4c  cmp     cs:qword_180313918, r14
0x18007db53  jnz     short loc_18007DBBB
0x18007db55  mov     r8b, 1; char *
0x18007db58  lea     rdx, aGetvolumepathn; "GetVolumePathNamesForVolumeNameW"
0x18007db5f  lea     rcx, [rbp+650h+var_618]; this
0x18007db63  call    ?UtilRawGetLoadedKernel32ProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBD_N@Z; CommonUtil::UtilRawGetLoadedKernel32ProcAddress(__int64 (**)(void),char const *,bool)
0x18007db68  mov     edi, eax
0x18007db6a  test    eax, eax
0x18007db6c  jns     short loc_18007DBA7
0x18007db6e  lea     rsi, WPP_GLOBAL_Control
0x18007db75  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db7c  cmp     rcx, rsi
0x18007db7f  jz      short loc_18007DB9E
0x18007db81  test    byte ptr [rcx+1Ch], 1
0x18007db85  jz      short loc_18007DB9E
0x18007db87  lea     edx, [r14+18h]
0x18007db8b  mov     r9d, eax
0x18007db8e  lea     r8, WPP_167bf0eddf4c33edfd51d100c28ec711_Traceguids
0x18007db95  mov     rcx, [rcx+10h]
0x18007db99  call    WPP_SF_d
0x18007db9e  mov     r14, qword ptr [rbp+650h+var_640]
0x18007dba2  jmp     loc_18007E2D3
0x18007dba7  cmp     cs:qword_180313918, r14
0x18007dbae  jnz     short loc_18007DBBB
0x18007dbb0  mov     rax, [rbp+650h+var_618]
0x18007dbb4  mov     cs:qword_180313918, rax
0x18007dbbb  xor     edx, edx; Val
0x18007dbbd  mov     r8d, 248h; Size
0x18007dbc3  lea     rcx, [rbp+650h+var_5E0]; void *
0x18007dbc7  call    memset
0x18007dbcc  mov     r12d, 208h
0x18007dbd2  mov     r8d, r12d
0x18007dbd5  lea     rdx, [rbp+650h+var_5A0]
0x18007dbdc  lea     rcx, [rbp+650h+var_5D0]
0x18007dbe3  call    UtilInitMpBuffer
0x18007dbe8  mov     edi, eax
0x18007dbea  test    eax, eax
0x18007dbec  js      short loc_18007DB9E
0x18007dbee  mov     rax, [rbp+650h+var_5D0]
0x18007dbf5  mov     qword ptr [rbp+650h+var_5E0+8], rax
0x18007dbf9  movzx   eax, [rbp+650h+var_5C8]
0x18007dc00  mov     word ptr [rbp+650h+var_5E0+2], ax
0x18007dc04  mov     word ptr [rbp+650h+var_5E0], r14w
0x18007dc09  xorps   xmm6, xmm6
0x18007dc0c  movups  [rbp+650h+var_678], xmm6
0x18007dc10  lea     r13, [rbp+650h+InputBuffer]
0x18007dc17  mov     ecx, 1000h
0x18007dc1c  call    cs:__imp_MpAllocMemory
0x18007dc22  mov     r14, rax
0x18007dc25  xor     edi, edi
0x18007dc27  test    rax, rax
0x18007dc2a  jnz     short loc_18007DC5E
0x18007dc2c  mov     r9d, 8007000Eh
0x18007dc32  mov     edi, r9d
0x18007dc35  lea     rsi, WPP_GLOBAL_Control
0x18007dc3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc43  cmp     rcx, rsi
0x18007dc46  jz      loc_18007E2D3
0x18007dc4c  test    byte ptr [rcx+1Ch], 1
0x18007dc50  jz      loc_18007E2D3
0x18007dc56  lea     edx, [rax+1Ah]
0x18007dc59  jmp     loc_18007E2C3
0x18007dc5e  mov     eax, 1000h
0x18007dc63  mov     dword ptr [rsp+750h+var_6F0], eax
0x18007dc67  mov     qword ptr [rbp+650h+var_6D0+8], r12
0x18007dc6b  xorps   xmm0, xmm0
0x18007dc6e  movdqu  [rbp+650h+var_6C0+0Ch], xmm0
0x18007dc73  mov     dword ptr [rbp+650h+var_6B0+0Ch], edi
0x18007dc76  lea     rax, [rbp+650h+var_360]
0x18007dc7d  mov     qword ptr [rbp+650h+var_6C0], rax
0x18007dc81  mov     dword ptr [rbp+650h+var_6C0+8], r12d
0x18007dc85  lea     rax, [rbp+650h+var_360]
0x18007dc8c  mov     qword ptr [rbp+650h+var_6D0], rax
0x18007dc90  lea     rdx, SourceString; "\\Device\\MountPointManager"
0x18007dc97  lea     rcx, [rbp+650h+DestinationString]; DestinationString
0x18007dc9e  call    cs:__imp_RtlInitUnicodeString
0x18007dca4  mov     [rbp+650h+ObjectAttributes.Length], 30h ; '0'
0x18007dcab  mov     [rbp+650h+ObjectAttributes.RootDirectory], rdi
0x18007dcaf  mov     ecx, 40h ; '@'
0x18007dcb4  mov     [rbp+650h+ObjectAttributes.Attributes], ecx
0x18007dcb7  lea     rax, [rbp+650h+DestinationString]
0x18007dcbe  mov     [rbp+650h+ObjectAttributes.ObjectName], rax
0x18007dcc2  xorps   xmm0, xmm0
0x18007dcc5  movdqu  xmmword ptr [rbp+650h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007dcca  mov     [rsp+750h+EaLength], edi; EaLength
0x18007dcce  mov     [rsp+750h+EaBuffer], rdi; EaBuffer
0x18007dcd3  mov     [rsp+750h+CreateOptions], ecx; CreateOptions
0x18007dcd7  lea     r12d, [rcx-3Fh]
0x18007dcdb  mov     [rsp+750h+CreateDisposition], r12d; CreateDisposition
0x18007dce0  mov     [rsp+750h+ShareAccess], 7; ShareAccess
0x18007dce8  mov     [rsp+750h+FileAttributes], edi; FileAttributes
0x18007dcec  mov     [rsp+750h+AllocationSize], rdi; AllocationSize
0x18007dcf1  lea     r9, [rbp+650h+IoStatusBlock]; IoStatusBlock
0x18007dcf8  lea     r8, [rbp+650h+ObjectAttributes]; ObjectAttributes
0x18007dcfc  lea     edx, [rcx-3Dh]; DesiredAccess
0x18007dcff  lea     rcx, [rbp+650h+FileHandle]; FileHandle
0x18007dd03  call    cs:__imp_NtCreateFile
0x18007dd09  mov     edi, eax
0x18007dd0b  test    eax, eax
0x18007dd0d  jns     short loc_18007DD4B
0x18007dd0f  bts     edi, 1Ch
0x18007dd13  lea     rsi, WPP_GLOBAL_Control
0x18007dd1a  mov     rax, cs:WPP_GLOBAL_Control
0x18007dd21  cmp     rax, rsi
0x18007dd24  jz      loc_18007E2D3
0x18007dd2a  test    [rax+1Ch], r12b
0x18007dd2e  jz      loc_18007E2D3
0x18007dd34  lea     edx, [r12+1Bh]
0x18007dd39  lfence
0x18007dd3c  mov     r9d, edi
0x18007dd3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd46  jmp     loc_18007E2C3
0x18007dd4b  xor     r9d, r9d; lpName
0x18007dd4e  xor     r8d, r8d; bInitialState
0x18007dd51  mov     edx, r12d; bManualReset
0x18007dd54  xor     ecx, ecx; lpEventAttributes
0x18007dd56  call    cs:__imp_CreateEventW
0x18007dd5c  mov     r12, rax
0x18007dd5f  test    rax, rax
0x18007dd62  jz      loc_18007E29B
0x18007dd68  mov     rbx, rax
0x18007dd6b  mov     [rbp+650h+var_668], rax
0x18007dd6f  mov     rax, [rsp+750h+var_6E8]
0x18007dd74  movzx   eax, word ptr [rax]
0x18007dd77  add     eax, 1Ah
0x18007dd7a  mov     [rsp+750h+InputBufferLength], eax
0x18007dd7e  mov     edi, eax
0x18007dd80  cmp     eax, 100h
0x18007dd85  jbe     short loc_18007DDE0
0x18007dd87  lfence
0x18007dd8a  mov     ecx, edi
0x18007dd8c  call    cs:__imp_MpAllocMemory
0x18007dd92  mov     r13, rax
0x18007dd95  test    rax, rax
0x18007dd98  jnz     short loc_18007DDCC
0x18007dd9a  mov     r9d, 8007000Eh
0x18007dda0  mov     edi, r9d
0x18007dda3  lea     rsi, WPP_GLOBAL_Control
0x18007ddaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ddb1  cmp     rcx, rsi
0x18007ddb4  jz      loc_18007E2D3
0x18007ddba  test    byte ptr [rcx+1Ch], 1
0x18007ddbe  jz      loc_18007E2D3
0x18007ddc4  lea     edx, [rax+1Eh]
0x18007ddc7  jmp     loc_18007E2C3
0x18007ddcc  movq    rcx, xmm6
0x18007ddd1  test    rcx, rcx
0x18007ddd4  jz      short loc_18007DDDC
0x18007ddd6  call    cs:__imp_MpFreeMemory
0x18007dddc  mov     qword ptr [rbp+650h+var_678], r13
0x18007dde0  mov     r8, rdi; Size
0x18007dde3  xor     edx, edx; Val
0x18007dde5  mov     rcx, r13; void *
0x18007dde8  call    memset
0x18007dded  mov     rdx, [rsp+750h+var_6E8]
0x18007ddf2  movzx   eax, word ptr [rdx]
0x18007ddf5  mov     [r13+14h], ax
0x18007ddfa  mov     dword ptr [r13+10h], 18h
0x18007de02  movzx   r8d, word ptr [rdx]; Size
0x18007de06  lea     rcx, [r13+18h]; void *
0x18007de0a  mov     rdx, [rdx+8]; Src
0x18007de0e  call    memmove
0x18007de13  mov     rdi, r14
0x18007de16  mov     [rsp+750h+var_6E8], r14
0x18007de1b  jmp     short loc_18007DE22
0x18007de1d  mov     rdi, [rsp+750h+var_6E8]
0x18007de22  mov     rcx, r12; hEvent
0x18007de25  call    cs:__imp_ResetEvent
0x18007de2b  add     r15d, 1000h
0x18007de32  cmp     r15d, dword ptr [rsp+750h+var_6F0]
0x18007de37  jbe     short loc_18007DE6D
0x18007de39  lfence
0x18007de3c  mov     ecx, r15d
0x18007de3f  call    cs:__imp_MpAllocMemory
0x18007de45  mov     rdi, rax
0x18007de48  test    rax, rax
0x18007de4b  jnz     short loc_18007DE52
0x18007de4d  mov     r12, rsi
0x18007de50  jmp     short loc_18007DE73
0x18007de52  test    r14, r14
0x18007de55  jz      short loc_18007DE60
0x18007de57  mov     rcx, r14
0x18007de5a  call    cs:__imp_MpFreeMemory
0x18007de60  mov     r14, rdi
0x18007de63  mov     [rsp+750h+var_6E8], rdi
0x18007de68  mov     dword ptr [rsp+750h+var_6F0], r15d
0x18007de6d  mov     rsi, rdi
0x18007de70  mov     r12, rdi
0x18007de73  mov     dword ptr [rsp+750h+EaBuffer], r15d; OutputBufferLength
0x18007de78  mov     qword ptr [rsp+750h+CreateOptions], rsi; OutputBuffer
0x18007de7d  mov     eax, [rsp+750h+InputBufferLength]
0x18007de81  mov     [rsp+750h+CreateDisposition], eax; InputBufferLength
0x18007de85  mov     qword ptr [rsp+750h+ShareAccess], r13; InputBuffer
0x18007de8a  mov     [rsp+750h+FileAttributes], 6D0008h; IoControlCode
0x18007de92  lea     rax, [rbp+650h+IoStatusBlock]
0x18007de99  mov     [rsp+750h+AllocationSize], rax; IoStatusBlock
0x18007de9e  xor     r9d, r9d; ApcContext
0x18007dea1  xor     r8d, r8d; ApcRoutine
0x18007dea4  mov     rdx, rbx; Event
0x18007dea7  mov     rcx, [rbp+650h+FileHandle]; FileHandle
0x18007deab  call    cs:__imp_NtDeviceIoControlFile
0x18007deb1  mov     edi, eax
0x18007deb3  cmp     eax, 103h
0x18007deb8  jnz     short loc_18007DED4
0x18007deba  xor     r8d, r8d; Timeout
0x18007debd  mov     dl, 1; Alertable
0x18007debf  mov     rcx, rbx; Handle
0x18007dec2  call    cs:__imp_NtWaitForSingleObject
0x18007dec8  mov     edi, eax
0x18007deca  test    eax, eax
0x18007decc  js      short loc_18007DED8
0x18007dece  mov     edi, dword ptr [rbp+650h+IoStatusBlock]
0x18007ded4  test    edi, edi
0x18007ded6  jns     short loc_18007DF25
0x18007ded8  cmp     edi, 80000005h
0x18007dede  jnz     short loc_18007DEF6
0x18007dee0  mov     eax, dword ptr [rsp+750h+var_6F0+4]
0x18007dee4  inc     eax
0x18007dee6  mov     dword ptr [rsp+750h+var_6F0+4], eax
0x18007deea  cmp     eax, 40h ; '@'
0x18007deed  mov     r12, rbx
0x18007def0  jb      loc_18007DE1D
0x18007def6  bts     edi, 1Ch
0x18007defa  lea     rsi, WPP_GLOBAL_Control
0x18007df01  mov     rax, cs:WPP_GLOBAL_Control
0x18007df08  cmp     rax, rsi
0x18007df0b  jz      loc_18007E2D3
0x18007df11  test    byte ptr [rax+1Ch], 1
0x18007df15  jz      loc_18007E2D3
0x18007df1b  mov     edx, 20h ; ' '
0x18007df20  jmp     loc_18007DD39
0x18007df25  mov     r13d, 1
0x18007df2b  cmp     [rsi+4], r13d
0x18007df2f  jnb     short loc_18007DF64
0x18007df31  mov     r9d, 8000FFFFh
0x18007df37  mov     edi, r9d
0x18007df3a  lea     rsi, WPP_GLOBAL_Control
0x18007df41  mov     rcx, cs:WPP_GLOBAL_Control
0x18007df48  cmp     rcx, rsi
0x18007df4b  jz      loc_18007E2D3
0x18007df51  test    [rcx+1Ch], r13b
0x18007df55  jz      loc_18007E2D3
0x18007df5b  lea     edx, [r13+20h]
0x18007df5f  jmp     loc_18007E2C3
0x18007df64  xor     r15d, r15d
0x18007df67  mov     edi, r15d
0x18007df6a  mov     eax, edi
0x18007df6c  lea     rcx, [rax+rax*2]
0x18007df70  mov     eax, [r12+rcx*8+8]
0x18007df75  add     rax, rsi
0x18007df78  mov     [rbp+650h+String2.Buffer], rax
0x18007df7c  movzx   eax, word ptr [r12+rcx*8+0Ch]
0x18007df82  mov     [rbp+650h+String2.Length], ax
  ... truncated ...
```
