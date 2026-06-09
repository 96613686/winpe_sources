# CFveApiBase::FveQueryVolumes(_FVE_QUERY_TYPE,uchar *,ulong *)

- ea: `0x18007ccb8`
- end: `0x18007d1e5`
- name: `?FveQueryVolumes@CFveApiBase@@SAJW4_FVE_QUERY_TYPE@@PEAEPEAK@Z`
- size: `1325`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800c21c4`

## callees

- `0x180005410`
- `0x18000b3b0`
- `0x18000ba30`
- `0x18000bb54`
- `0x18000be40`
- `0x18000ca50`
- `0x180023880`
- `0x18002fea0`
- `0x180030150`
- `0x18003caa4`
- `0x18007ccb8`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18007cfc9`
- `msvcrt!wcstoul` at `0x18007cfc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123ca8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007cda7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007cda7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007ce43`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007cec2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007ce43`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007cec2`

## pseudocode

```c
__int64 __fastcall CFveApiBase::FveQueryVolumes(int a1, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 FileW; // r12
  unsigned int *v5; // rdi
  unsigned int v6; // esi
  int v7; // ecx
  int v8; // ecx
  int v9; // eax
  int LastHresultError; // ebx
  unsigned int v11; // r13d
  unsigned int v12; // esi
  bool v13; // cf
  unsigned int v14; // ecx
  unsigned int *v15; // r15
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // r14
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r10d
  __int64 v22; // rax
  int v24; // [rsp+44h] [rbp-C4h]
  unsigned __int16 *v25; // [rsp+48h] [rbp-C0h] BYREF
  void *lpMem; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-B0h] BYREF
  int v28; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v29; // [rsp+68h] [rbp-A0h]
  unsigned int *v30; // [rsp+70h] [rbp-98h]
  int v31; // [rsp+78h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-88h]
  unsigned __int64 v33; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v34; // [rsp+90h] [rbp-78h]
  unsigned __int16 *v35; // [rsp+98h] [rbp-70h]
  _DWORD *v36; // [rsp+A0h] [rbp-68h]
  DWORD OutBuffer; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t *EndPtr; // [rsp+B0h] [rbp-58h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t String[12]; // [rsp+C0h] [rbp-48h] BYREF

  v29 = a2;
  FileW = -1;
  v32 = -1;
  v5 = 0;
  v30 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  v6 = 0;
  memset(String, 0, 22);
  EndPtr = 0;
  v33 = 0;
  v25 = 0;
  v27 = 0;
  lpMem = 0;
  if ( (unsigned int)(a1 - 1) > 0xD )
    goto LABEL_52;
  v7 = a1 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
LABEL_52:
        LastHresultError = -2147024809;
        goto LABEL_53;
      }
      v9 = 2;
    }
    else
    {
      v9 = 1;
    }
  }
  else
  {
    v9 = 0;
  }
  v24 = v9;
  if ( !a3 || *a3 && !a2 )
    goto LABEL_52;
  FileW = (__int64)CreateFileW(off_18012A180[v9], 0x80u, 3u, 0, 3u, 0, 0);
  v32 = FileW;
  if ( FileW == -1 )
  {
    LastHresultError = GetLastHresultError();
  }
  else
  {
    while ( 1 )
    {
      if ( v5 )
      {
        CFveApiBase::FastFree(v5);
        v5 = 0;
        v30 = 0;
      }
      v34 = ++v6;
      if ( v6 > 5 )
      {
LABEL_16:
        LastHresultError = -2147418113;
        goto LABEL_53;
      }
      if ( DeviceIoControl((HANDLE)FileW, 0x4C4210CCu, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
        goto LABEL_52;
      LastHresultError = GetLastHresultError();
      if ( LastHresultError != -2147024662 )
        goto LABEL_53;
      LastHresultError = 0;
      v5 = (unsigned int *)CFveApiBase::FastAlloc(OutBuffer);
      v30 = v5;
      if ( !v5 )
      {
        LastHresultError = -2147024882;
        goto LABEL_53;
      }
      if ( DeviceIoControl((HANDLE)FileW, 0x4C4210CCu, 0, 0, v5, OutBuffer, &BytesReturned, 0) )
        break;
      LastHresultError = GetLastHresultError();
      if ( LastHresultError != -2147024662 )
        goto LABEL_53;
    }
    v11 = 8;
    v31 = 8;
    v12 = 520 * v5[1] + 2;
    OutBuffer = v12;
    v13 = *a3 < v12;
    *a3 = v12;
    if ( v13 )
    {
      if ( v29 )
        LastHresultError = -2147024774;
    }
    else
    {
      memset_0(v29, 0, v12);
      v14 = 0;
      v28 = 0;
      v15 = v5 + 2;
      v36 = v5 + 2;
      v16 = v29;
      v17 = v29;
      v35 = v29;
      while ( v14 < v5[1] && v11 < *v5 && v17 + 260 <= (unsigned __int16 *)((char *)v16 + v12 - 2) )
      {
        LastHresultError = StringCbCopyNW(String, 0x16u, (const unsigned __int16 *)((char *)v15 + v15[2]), v15[3]);
        if ( LastHresultError < 0 )
          goto LABEL_53;
        v18 = wcstoul(String, &EndPtr, 10);
        if ( v18 == -1 || EndPtr != (wchar_t *)((char *)String + (v15[3] & 0xFFFFFFFE)) )
          goto LABEL_16;
        if ( lpMem )
        {
          CFveApiBase::FastFree(lpMem);
          lpMem = 0;
        }
        LastHresultError = CFveApiBase::BuildVolumeCdoPath(v24, v18, (unsigned __int16 **)&lpMem);
        if ( LastHresultError < 0 )
          goto LABEL_53;
        if ( v27 )
        {
          CFveApiBase::FastFree(v27);
          v27 = 0;
        }
        v19 = CFveApiBase::VolumeNameToDevicePath((LPCWSTR)lpMem, &v27);
        LastHresultError = v19;
        if ( v19 == -2147024894 )
          goto LABEL_40;
        if ( v19 < 0 )
          goto LABEL_53;
        if ( v25 )
        {
          CFveApiBase::FastFree(v25);
          v25 = 0;
        }
        v20 = CFveApiBase::DevicePathToVolumeGuidName(v27, &v25);
        LastHresultError = v20;
        if ( v20 == -2147024894 )
        {
LABEL_40:
          LastHresultError = 0;
        }
        else
        {
          if ( v20 < 0 )
            goto LABEL_53;
          LastHresultError = StringCbCopyW(v17, 0x208u, v25);
          if ( LastHresultError < 0 )
            goto LABEL_53;
          LastHresultError = StringCbCatW(v17, v21, L"\\");
          if ( LastHresultError < 0 )
            goto LABEL_53;
          LastHresultError = StringCbLengthW(v17, 0x208u, &v33);
          if ( LastHresultError < 0 )
            goto LABEL_53;
          v17 = (unsigned __int16 *)((char *)v17 + v33 + 2);
          v35 = v17;
        }
        v22 = *v15;
        v11 += v22;
        v31 = v11;
        v14 = ++v28;
        v15 = (unsigned int *)((char *)v15 + v22);
        v36 = v15;
        v12 = OutBuffer;
        v16 = v29;
      }
      *v17 = 0;
    }
  }
LABEL_53:
  if ( v25 )
    CFveApiBase::FastFree(v25);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v27 )
    CFveApiBase::FastFree(v27);
  if ( v5 )
    CFveApiBase::FastFree(v5);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18007ccb8  mov     r11, rsp
0x18007ccbb  mov     [r11+8], rbx
0x18007ccbf  mov     [r11+20h], rsi
0x18007ccc3  push    rdi
0x18007ccc4  push    r12
0x18007ccc6  push    r13
0x18007ccc8  push    r14
0x18007ccca  push    r15
0x18007cccc  sub     rsp, 0E0h
0x18007ccd3  mov     rax, cs:__security_cookie
0x18007ccda  xor     rax, rsp
0x18007ccdd  mov     [rsp+108h+var_30], rax
0x18007cce5  mov     r14, r8
0x18007cce8  mov     [rsp+108h+var_A0], rdx
0x18007cced  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007ccf1  mov     [r11-88h], r12
0x18007ccf8  xor     edi, edi
0x18007ccfa  mov     [rsp+108h+var_98], rdi
0x18007ccff  mov     [r11-60h], edi
0x18007cd03  mov     [r11-50h], edi
0x18007cd07  xor     esi, esi
0x18007cd09  xorps   xmm0, xmm0
0x18007cd0c  xor     eax, eax
0x18007cd0e  movups  xmmword ptr [r11-48h], xmm0
0x18007cd13  mov     [r11-3Ah], rax
0x18007cd17  mov     [r11-58h], rax
0x18007cd1b  mov     [r11-80h], rax
0x18007cd1f  mov     [rsp+108h+var_C0], rax
0x18007cd24  mov     [rsp+108h+var_B0], rax
0x18007cd29  mov     [rsp+108h+lpMem], rax
0x18007cd2e  lea     eax, [rcx-1]
0x18007cd31  cmp     eax, 0Dh
0x18007cd34  ja      loc_18007D15D
0x18007cd3a  sub     ecx, 1
0x18007cd3d  jz      short loc_18007CD59
0x18007cd3f  sub     ecx, 1
0x18007cd42  jz      short loc_18007CD52
0x18007cd44  cmp     ecx, 1
0x18007cd47  jnz     loc_18007D15D
0x18007cd4d  lea     eax, [rdi+2]
0x18007cd50  jmp     short loc_18007CD5B
0x18007cd52  mov     eax, 1
0x18007cd57  jmp     short loc_18007CD5B
0x18007cd59  xor     eax, eax
0x18007cd5b  mov     [rsp+108h+var_C4], eax
0x18007cd5f  test    r14, r14
0x18007cd62  jz      loc_18007D15D
0x18007cd68  cmp     dword ptr [r8], 0
0x18007cd6c  jbe     short loc_18007CD77
0x18007cd6e  test    rdx, rdx
0x18007cd71  jz      loc_18007D15D
0x18007cd77  mov     ecx, eax
0x18007cd79  lea     rax, off_18012A180; "\\\\.\\BitLocker\\Unsupported"
0x18007cd80  mov     [rsp+108h+hTemplateFile], 0; hTemplateFile
0x18007cd89  mov     [rsp+108h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18007cd91  mov     r8d, 3; dwShareMode
0x18007cd97  mov     [rsp+108h+dwCreationDisposition], r8d; dwCreationDisposition
0x18007cd9c  xor     r9d, r9d; lpSecurityAttributes
0x18007cd9f  lea     edx, [r8+7Dh]; dwDesiredAccess
0x18007cda3  mov     rcx, [rax+rcx*8]; lpFileName
0x18007cda7  call    cs:__imp_CreateFileW
0x18007cdae  nop     dword ptr [rax+rax+00h]
0x18007cdb3  mov     r12, rax
0x18007cdb6  mov     [rsp+108h+var_88], rax
0x18007cdbe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007cdc2  jnz     short loc_18007CDD4
0x18007cdc4  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007cdc9  mov     ebx, eax
0x18007cdcb  mov     [rsp+108h+var_C8], eax
0x18007cdcf  jmp     loc_18007D166
0x18007cdd4  mov     r13d, 4C4210CCh
0x18007cdda  mov     r15d, 800700EAh
0x18007cde0  test    rdi, rdi
0x18007cde3  jz      short loc_18007CDF4
0x18007cde5  mov     rcx, rdi; lpMem
0x18007cde8  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007cded  xor     edi, edi
0x18007cdef  mov     [rsp+108h+var_98], rdi
0x18007cdf4  inc     esi
0x18007cdf6  mov     [rsp+108h+var_78], esi
0x18007cdfd  cmp     esi, 5
0x18007ce00  jbe     short loc_18007CE0C
0x18007ce02  mov     ebx, 8000FFFFh
0x18007ce07  jmp     loc_18007D162
0x18007ce0c  mov     [rsp+108h+lpOverlapped], 0; lpOverlapped
0x18007ce15  lea     rax, [rsp+108h+BytesReturned]
0x18007ce1d  mov     [rsp+108h+hTemplateFile], rax; lpBytesReturned
0x18007ce22  mov     [rsp+108h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18007ce2a  lea     rax, [rsp+108h+OutBuffer]
0x18007ce32  mov     qword ptr [rsp+108h+dwCreationDisposition], rax; lpOutBuffer
0x18007ce37  xor     r9d, r9d; nInBufferSize
0x18007ce3a  xor     r8d, r8d; lpInBuffer
0x18007ce3d  mov     edx, r13d; dwIoControlCode
0x18007ce40  mov     rcx, r12; hDevice
0x18007ce43  call    cs:__imp_DeviceIoControl
0x18007ce4a  nop     dword ptr [rax+rax+00h]
0x18007ce4f  test    eax, eax
0x18007ce51  jnz     loc_18007D15D
0x18007ce57  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007ce5c  mov     ebx, eax
0x18007ce5e  mov     [rsp+108h+var_C8], eax
0x18007ce62  cmp     eax, r15d
0x18007ce65  jnz     loc_18007D166
0x18007ce6b  xor     ebx, ebx
0x18007ce6d  mov     [rsp+108h+var_C8], ebx
0x18007ce71  mov     ecx, [rsp+108h+OutBuffer]; unsigned __int64
0x18007ce78  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18007ce7d  mov     rdi, rax
0x18007ce80  mov     [rsp+108h+var_98], rax
0x18007ce85  test    rax, rax
0x18007ce88  jnz     short loc_18007CE94
0x18007ce8a  mov     ebx, 8007000Eh
0x18007ce8f  jmp     loc_18007D162
0x18007ce94  mov     [rsp+108h+lpOverlapped], rbx; lpOverlapped
0x18007ce99  lea     rax, [rsp+108h+BytesReturned]
0x18007cea1  mov     [rsp+108h+hTemplateFile], rax; lpBytesReturned
0x18007cea6  mov     eax, [rsp+108h+OutBuffer]
0x18007cead  mov     [rsp+108h+dwFlagsAndAttributes], eax; nOutBufferSize
0x18007ceb1  mov     qword ptr [rsp+108h+dwCreationDisposition], rdi; lpOutBuffer
0x18007ceb6  xor     r9d, r9d; nInBufferSize
0x18007ceb9  xor     r8d, r8d; lpInBuffer
0x18007cebc  mov     edx, r13d; dwIoControlCode
0x18007cebf  mov     rcx, r12; hDevice
0x18007cec2  call    cs:__imp_DeviceIoControl
0x18007cec9  nop     dword ptr [rax+rax+00h]
0x18007cece  test    eax, eax
0x18007ced0  jnz     short loc_18007CEF3
0x18007ced2  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007ced7  mov     ebx, eax
0x18007ced9  mov     [rsp+108h+var_C8], eax
0x18007cedd  cmp     eax, r15d
0x18007cee0  jnz     loc_18007D166
0x18007cee6  mov     [rsp+108h+var_C8], 0
0x18007ceee  jmp     loc_18007CDE0
0x18007cef3  mov     r13d, 8
0x18007cef9  mov     [rsp+108h+var_90], r13d
0x18007cefe  imul    eax, [rdi+4], 208h
0x18007cf05  lea     esi, [rax+2]
0x18007cf08  mov     [rsp+108h+OutBuffer], esi
0x18007cf0f  cmp     [r14], esi
0x18007cf12  mov     [r14], esi
0x18007cf15  jnb     short loc_18007CF2C
0x18007cf17  cmp     [rsp+108h+var_A0], rbx
0x18007cf1c  jz      loc_18007D166
0x18007cf22  mov     ebx, 8007007Ah
0x18007cf27  jmp     loc_18007D162
0x18007cf2c  mov     r8d, esi; Size
0x18007cf2f  xor     edx, edx; Val
0x18007cf31  mov     rcx, [rsp+108h+var_A0]; void *
0x18007cf36  call    memset_0
0x18007cf3b  xor     ecx, ecx
0x18007cf3d  mov     [rsp+108h+var_A8], ecx
0x18007cf41  lea     r15, [rdi+8]
0x18007cf45  mov     [rsp+108h+var_68], r15
0x18007cf4d  mov     rdx, [rsp+108h+var_A0]
0x18007cf52  mov     r14, rdx
0x18007cf55  mov     [rsp+108h+var_70], rdx
0x18007cf5d  cmp     ecx, [rdi+4]
0x18007cf60  jnb     loc_18007D155
0x18007cf66  cmp     r13d, [rdi]
0x18007cf69  jnb     loc_18007D155
0x18007cf6f  mov     ecx, esi
0x18007cf71  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18007cf75  add     rcx, rdx
0x18007cf78  lea     rax, [r14+208h]
0x18007cf7f  cmp     rax, rcx
0x18007cf82  ja      loc_18007D155
0x18007cf88  mov     r9d, [r15+0Ch]; unsigned __int64
0x18007cf8c  mov     r8d, [r15+8]
0x18007cf90  add     r8, r15; unsigned __int16 *
0x18007cf93  mov     edx, 16h; unsigned __int64
0x18007cf98  lea     rcx, [rsp+108h+String]; unsigned __int16 *
0x18007cfa0  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007cfa5  mov     ebx, eax
0x18007cfa7  mov     [rsp+108h+var_C8], eax
0x18007cfab  xor     esi, esi
0x18007cfad  test    eax, eax
0x18007cfaf  js      loc_18007D166
0x18007cfb5  lea     r8d, [rsi+0Ah]; Radix
0x18007cfb9  lea     rdx, [rsp+108h+EndPtr]; EndPtr
0x18007cfc1  lea     rcx, [rsp+108h+String]; String
0x18007cfc9  call    cs:__imp_wcstoul
0x18007cfd0  nop     dword ptr [rax+rax+00h]
0x18007cfd5  mov     ebx, eax
0x18007cfd7  cmp     eax, 0FFFFFFFFh
0x18007cfda  jz      loc_18007CE02
0x18007cfe0  mov     ecx, [r15+0Ch]
0x18007cfe4  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18007cfe8  lea     rdx, [rsp+108h+String]
0x18007cff0  add     rdx, rcx
0x18007cff3  cmp     [rsp+108h+EndPtr], rdx
0x18007cffb  jnz     loc_18007CE02
0x18007d001  mov     rcx, [rsp+108h+lpMem]; lpMem
0x18007d006  test    rcx, rcx
0x18007d009  jz      short loc_18007D015
0x18007d00b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d010  mov     [rsp+108h+lpMem], rsi
0x18007d015  lea     r8, [rsp+108h+lpMem]
0x18007d01a  mov     edx, ebx
0x18007d01c  mov     ecx, [rsp+108h+var_C4]
0x18007d020  call    ?BuildVolumeCdoPath@CFveApiBase@@SAJW4_FVE_DEVICE_TYPE@@KPEAPEAG@Z; CFveApiBase::BuildVolumeCdoPath(_FVE_DEVICE_TYPE,ulong,ushort * *)
0x18007d025  mov     ebx, eax
0x18007d027  mov     [rsp+108h+var_C8], eax
0x18007d02b  test    eax, eax
0x18007d02d  js      loc_18007D166
0x18007d033  mov     rcx, [rsp+108h+var_B0]; lpMem
0x18007d038  test    rcx, rcx
0x18007d03b  jz      short loc_18007D047
0x18007d03d  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d042  mov     [rsp+108h+var_B0], rsi
0x18007d047  lea     rdx, [rsp+108h+var_B0]; unsigned __int16 **
0x18007d04c  mov     rcx, [rsp+108h+lpMem]; lpFileName
0x18007d051  call    ?VolumeNameToDevicePath@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::VolumeNameToDevicePath(ushort const *,ushort * *)
0x18007d056  mov     ebx, eax
0x18007d058  mov     [rsp+108h+var_C8], eax
0x18007d05c  cmp     eax, 80070002h
0x18007d061  jnz     short loc_18007D06E
0x18007d063  mov     ebx, esi
0x18007d065  mov     [rsp+108h+var_C8], ebx
0x18007d069  jmp     loc_18007D124
0x18007d06e  test    eax, eax
0x18007d070  js      loc_18007D166
0x18007d076  mov     rcx, [rsp+108h+var_C0]; lpMem
0x18007d07b  test    rcx, rcx
0x18007d07e  jz      short loc_18007D08A
0x18007d080  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d085  mov     [rsp+108h+var_C0], rsi
0x18007d08a  lea     rdx, [rsp+108h+var_C0]; unsigned __int16 **
0x18007d08f  mov     rcx, [rsp+108h+var_B0]; unsigned __int16 *
0x18007d094  call    ?DevicePathToVolumeGuidName@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::DevicePathToVolumeGuidName(ushort const *,ushort * *)
0x18007d099  mov     ebx, eax
0x18007d09b  mov     [rsp+108h+var_C8], eax
0x18007d09f  cmp     eax, 80070002h
0x18007d0a4  jz      short loc_18007D063
0x18007d0a6  test    eax, eax
0x18007d0a8  js      loc_18007D166
0x18007d0ae  mov     r8, [rsp+108h+var_C0]; unsigned __int16 *
0x18007d0b3  mov     r10d, 208h
0x18007d0b9  mov     edx, r10d; unsigned __int64
0x18007d0bc  mov     rcx, r14; unsigned __int16 *
0x18007d0bf  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18007d0c4  mov     ebx, eax
0x18007d0c6  mov     [rsp+108h+var_C8], eax
0x18007d0ca  test    eax, eax
0x18007d0cc  js      loc_18007D166
0x18007d0d2  lea     r8, asc_180134CC8; "\\"
0x18007d0d9  mov     edx, r10d; unsigned __int64
0x18007d0dc  mov     rcx, r14; unsigned __int16 *
0x18007d0df  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18007d0e4  mov     ebx, eax
0x18007d0e6  mov     [rsp+108h+var_C8], eax
0x18007d0ea  test    eax, eax
0x18007d0ec  js      short loc_18007D166
0x18007d0ee  lea     r8, [rsp+108h+var_80]; unsigned __int64 *
0x18007d0f6  mov     edx, 208h; unsigned __int64
0x18007d0fb  mov     rcx, r14; unsigned __int16 *
0x18007d0fe  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007d103  mov     ebx, eax
0x18007d105  mov     [rsp+108h+var_C8], eax
0x18007d109  test    eax, eax
0x18007d10b  js      short loc_18007D166
0x18007d10d  mov     rax, [rsp+108h+var_80]
0x18007d115  add     r14, 2
0x18007d119  add     r14, rax
0x18007d11c  mov     [rsp+108h+var_70], r14
0x18007d124  mov     eax, [r15]
0x18007d127  add     r13d, eax
0x18007d12a  mov     [rsp+108h+var_90], r13d
0x18007d12f  mov     ecx, [rsp+108h+var_A8]
0x18007d133  inc     ecx
0x18007d135  mov     [rsp+108h+var_A8], ecx
0x18007d139  add     r15, rax
0x18007d13c  mov     [rsp+108h+var_68], r15
0x18007d144  mov     esi, [rsp+108h+OutBuffer]
0x18007d14b  mov     rdx, [rsp+108h+var_A0]
0x18007d150  jmp     loc_18007CF5D
0x18007d155  xor     eax, eax
0x18007d157  mov     [r14], ax
0x18007d15b  jmp     short loc_18007D166
0x18007d15d  mov     ebx, 80070057h
0x18007d162  mov     [rsp+108h+var_C8], ebx
0x18007d166  mov     rcx, [rsp+108h+var_C0]; lpMem
0x18007d16b  test    rcx, rcx
0x18007d16e  jz      short loc_18007D175
0x18007d170  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d175  mov     rcx, [rsp+108h+lpMem]; lpMem
0x18007d17a  test    rcx, rcx
0x18007d17d  jz      short loc_18007D184
0x18007d17f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d184  mov     rcx, [rsp+108h+var_B0]; lpMem
0x18007d189  test    rcx, rcx
0x18007d18c  jz      short loc_18007D193
0x18007d18e  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d193  test    rdi, rdi
0x18007d196  jz      short loc_18007D1A0
0x18007d198  mov     rcx, rdi; lpMem
0x18007d19b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007d1a0  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18007d1a4  jz      short loc_18007D1B5
0x18007d1a6  mov     rcx, r12; hObject
  ... truncated ...
```
