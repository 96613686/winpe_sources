# AlpcSection::Create(AlpcPort const *,unsigned __int64,SipcSectionId const &,void *,AlpcSection * *)

- ea: `0x1800a3da8`
- end: `0x1800a4117`
- name: `?Create@AlpcSection@@SAJPEBVAlpcPort@@_KAEBVSipcSectionId@@PEAXPEAPEAV1@@Z`
- size: `879`
- prototype: `static int(const struct AlpcPort *, unsigned __int64, const struct SipcSectionId *, void *, struct AlpcSection **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1801421e0`

## callees

- `0x1800835d4`
- `0x1800a3da8`
- `0x1800a4198`
- `0x1800a43b0`
- `0x1800a9e00`
- `0x1800f08d8`
- `0x1800f2448`
- `0x180143ae8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3ddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a3ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3ec2`
- `ntdll!NtAlpcCreateSectionView` at `0x1800a3fb6`
- `ntdll!NtAlpcCreateSectionView` at `0x1800a3fb6`
- `ntdll!NtQueryLicenseValue` at `0x1800a3e73`
- `ntdll!NtQueryLicenseValue` at `0x1800a3e73`
- `ntdll!NtAlpcCreatePortSection` at `0x1800a3f90`
- `ntdll!NtAlpcCreatePortSection` at `0x1800a3f90`
- `ntdll!RtlInitUnicodeString` at `0x1800a3e54`
- `ntdll!RtlInitUnicodeString` at `0x1800a3e54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800a3e02`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800a3e02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a3f3a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a3f3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a3eb2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a3eb2`

## pseudocode

```c
__int64 __fastcall AlpcSection::Create(
        const struct AlpcPort *a1,
        unsigned __int64 a2,
        const struct SipcSectionId *a3,
        void *a4,
        struct AlpcSection **a5)
{
  PWSTR Buffer; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  signed int LastError; // eax
  int v13; // ebx
  __int64 v14; // rbx
  unsigned __int64 v15; // rdi
  HANDLE FileW; // rax
  signed int v17; // eax
  int PortSection; // eax
  int v19; // eax
  int v20; // edi
  unsigned __int64 i; // rcx
  unsigned __int64 v22; // rbx
  char *v23; // rax
  HANDLE v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r9
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int64 v30; // [rsp+40h] [rbp-51h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-49h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-41h] BYREF
  HANDLE v33; // [rsp+58h] [rbp-39h] BYREF
  __int128 v34; // [rsp+60h] [rbp-31h] BYREF
  __int128 v35; // [rsp+70h] [rbp-21h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-11h] BYREF
  unsigned __int64 InBuffer[10]; // [rsp+90h] [rbp-1h] BYREF

  Buffer = 0;
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v11 = GetCurrentProcess();
  if ( !DuplicateHandle(v11, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = -2147418113;
    if ( LastError < 0 )
      v13 = LastError;
    goto LABEL_29;
  }
  v14 = 0;
  v30 = 0;
  LODWORD(v33) = 0;
  BytesReturned = 0;
  v15 = (a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Kernel-ProductInfo");
  if ( (int)NtQueryLicenseValue(&DestinationString, 0, &v33, 4, &BytesReturned) >= 0 && (_DWORD)v33 == 192 )
  {
    FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
    v33 = FileW;
    if ( FileW == (HANDLE)-1LL
      || (BytesReturned = 0,
          InBuffer[0] = (v15 + 65575) & 0xFFFFFFFFFFFF0000uLL,
          DestinationString = 0,
          !DeviceIoControl(FileW, 0x15026Cu, InBuffer, 8u, &DestinationString, 0x10u, &BytesReturned, 0)) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v13 = -2147418113;
      if ( v17 < 0 )
        v13 = v17;
      SipcFileHandle::Reset((SipcFileHandle *)&v33);
      goto LABEL_28;
    }
    SipcWin32Handle::Attach((SipcWin32Handle *)&v30, *(void **)&DestinationString.Length);
    Buffer = DestinationString.Buffer;
    SipcFileHandle::Reset((SipcFileHandle *)&v33);
    v14 = v30;
  }
  v34 = 0;
  v35 = 0;
  PortSection = NtAlpcCreatePortSection(TargetHandle, 0, v14, v15 + 40, (char *)&v34 + 8, (char *)&v35 + 8);
  if ( PortSection < 0 )
  {
    v19 = PortSection | 0x10000000;
    v13 = -2147418113;
    if ( v19 < 0 )
      v13 = v19;
    goto LABEL_28;
  }
  v20 = NtAlpcCreateSectionView(TargetHandle, 0, &v34);
  if ( v20 >= 0 )
  {
    for ( i = 0; i < a2; i += 4096LL )
      *(_BYTE *)(v35 + i) = 0;
    memset_0((void *)(a2 + v35), 204, *((_QWORD *)&v35 + 1) - a2);
    v22 = v35 + ((*((_QWORD *)&v35 + 1) - 40LL) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)v22 = a2;
    *(_OWORD *)(v22 + 8) = *(_OWORD *)a3;
    *(_OWORD *)(v22 + 24) = *((_OWORD *)a3 + 1);
    v23 = (char *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 )
    {
      v24 = TargetHandle;
      v25 = *((_QWORD *)&v35 + 1);
      v26 = *((_QWORD *)&v34 + 1);
      *((_QWORD *)v23 + 4) = v35;
      *(_QWORD *)v23 = &SipcSection::`vftable';
      *((_QWORD *)v23 + 5) = v25;
      *((_QWORD *)v23 + 3) = a1;
      *((_QWORD *)v23 + 6) = *(_QWORD *)v22;
      v27 = *(_OWORD *)(v22 + 8);
      *a5 = (struct AlpcSection *)v23;
      *(_OWORD *)(v23 + 56) = v27;
      v28 = *(_OWORD *)(v22 + 24);
      *(_QWORD *)v23 = &AlpcSection::`vftable';
      *((_DWORD *)v23 + 22) = 0;
      *(_OWORD *)(v23 + 72) = v28;
      *((_QWORD *)v23 + 12) = v24;
      *((_QWORD *)v23 + 13) = v26;
      *((_QWORD *)v23 + 14) = Buffer;
      TargetHandle = 0;
      SipcSection::ProtectExtraMemory((SipcSection *)v23);
      SipcWin32Handle::Reset((SipcWin32Handle *)&v30);
      v13 = 0;
LABEL_29:
      SipcWin32Handle::Reset((SipcWin32Handle *)&TargetHandle);
      return (unsigned int)v13;
    }
    *a5 = 0;
    v20 = -1073741801;
  }
  v13 = AlpcSection::Unmap((void *)v35, a4, *((void **)&v34 + 1));
  if ( v13 < 0 )
  {
LABEL_28:
    SipcWin32Handle::Reset((SipcWin32Handle *)&v30);
    goto LABEL_29;
  }
  SipcWin32Handle::Reset((SipcWin32Handle *)&v30);
  SipcWin32Handle::Reset((SipcWin32Handle *)&TargetHandle);
  return v20 | 0x10000000u;
}

```

## disassembly

```asm
0x1800a3da8  push    rbp
0x1800a3daa  push    rbx
0x1800a3dab  push    rsi
0x1800a3dac  push    rdi
0x1800a3dad  push    r12
0x1800a3daf  push    r13
0x1800a3db1  push    r14
0x1800a3db3  push    r15
0x1800a3db5  lea     rbp, [rsp-17h]
0x1800a3dba  sub     rsp, 0A8h
0x1800a3dc1  xor     r14d, r14d
0x1800a3dc4  mov     r15, r9
0x1800a3dc7  mov     [rbp+4Fh+TargetHandle], r14
0x1800a3dcb  mov     r12, r8
0x1800a3dce  mov     rsi, rdx
0x1800a3dd1  mov     r13, rcx
0x1800a3dd4  call    cs:__imp_GetCurrentProcess
0x1800a3dda  mov     rbx, rax
0x1800a3ddd  call    cs:__imp_GetCurrentProcess
0x1800a3de3  mov     [rsp+0E0h+dwOptions], 2; dwOptions
0x1800a3deb  lea     r9, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x1800a3def  mov     rcx, rax; hSourceProcessHandle
0x1800a3df2  mov     [rsp+0E0h+bInheritHandle], r14d; bInheritHandle
0x1800a3df7  mov     r8, rbx; hTargetProcessHandle
0x1800a3dfa  mov     [rsp+0E0h+dwDesiredAccess], r14d; dwDesiredAccess
0x1800a3dff  mov     rdx, r15; hSourceHandle
0x1800a3e02  call    cs:__imp_DuplicateHandle
0x1800a3e08  test    eax, eax
0x1800a3e0a  jnz     short loc_1800A3E2D
0x1800a3e0c  call    cs:__imp_GetLastError
0x1800a3e12  test    eax, eax
0x1800a3e14  jle     short loc_1800A3E1E
0x1800a3e16  movzx   eax, ax
0x1800a3e19  or      eax, 80070000h
0x1800a3e1e  test    eax, eax
0x1800a3e20  mov     ebx, 8000FFFFh
0x1800a3e25  cmovs   ebx, eax
0x1800a3e28  jmp     loc_1800A40DE
0x1800a3e2d  mov     rbx, r14
0x1800a3e30  lea     rdi, [rsi+7]
0x1800a3e34  xorps   xmm0, xmm0
0x1800a3e37  mov     [rbp+4Fh+var_A0], rbx
0x1800a3e3b  lea     rdx, SourceString; "Kernel-ProductInfo"
0x1800a3e42  mov     dword ptr [rbp+4Fh+var_88], ebx
0x1800a3e45  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800a3e49  mov     [rbp+4Fh+BytesReturned], ebx
0x1800a3e4c  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1800a3e50  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800a3e54  call    cs:__imp_RtlInitUnicodeString
0x1800a3e5a  lea     rax, [rbp+4Fh+BytesReturned]
0x1800a3e5e  mov     r9d, 4
0x1800a3e64  lea     r8, [rbp+4Fh+var_88]
0x1800a3e68  mov     qword ptr [rsp+0E0h+dwDesiredAccess], rax
0x1800a3e6d  xor     edx, edx
0x1800a3e6f  lea     rcx, [rbp+4Fh+DestinationString]
0x1800a3e73  call    cs:__imp_NtQueryLicenseValue
0x1800a3e79  test    eax, eax
0x1800a3e7b  js      loc_1800A3F66
0x1800a3e81  cmp     dword ptr [rbp+4Fh+var_88], 0C0h
0x1800a3e88  jnz     loc_1800A3F66
0x1800a3e8e  mov     qword ptr [rsp+0E0h+dwOptions], r14; hTemplateFile
0x1800a3e93  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x1800a3e9a  mov     r8d, 3; dwShareMode
0x1800a3ea0  mov     [rsp+0E0h+bInheritHandle], r14d; dwFlagsAndAttributes
0x1800a3ea5  xor     r9d, r9d; lpSecurityAttributes
0x1800a3ea8  mov     [rsp+0E0h+dwDesiredAccess], r8d; dwCreationDisposition
0x1800a3ead  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a3eb2  call    cs:__imp_CreateFileW
0x1800a3eb8  mov     [rbp+4Fh+var_88], rax
0x1800a3ebc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a3ec0  jnz     short loc_1800A3EEC
0x1800a3ec2  call    cs:__imp_GetLastError
0x1800a3ec8  test    eax, eax
0x1800a3eca  jle     short loc_1800A3ED4
0x1800a3ecc  movzx   eax, ax
0x1800a3ecf  or      eax, 80070000h
0x1800a3ed4  test    eax, eax
0x1800a3ed6  lea     rcx, [rbp+4Fh+var_88]; this
0x1800a3eda  mov     ebx, 8000FFFFh
0x1800a3edf  cmovs   ebx, eax
0x1800a3ee2  call    ?Reset@SipcFileHandle@@QEAAXXZ; SipcFileHandle::Reset(void)
0x1800a3ee7  jmp     loc_1800A40D5
0x1800a3eec  mov     [rsp+0E0h+lpOverlapped], r14; lpOverlapped
0x1800a3ef1  lea     rcx, [rdi+10027h]
0x1800a3ef8  and     rcx, 0FFFFFFFFFFFF0000h
0x1800a3eff  mov     [rbp+4Fh+BytesReturned], r14d
0x1800a3f03  mov     [rbp+4Fh+InBuffer], rcx
0x1800a3f07  lea     r8, [rbp+4Fh+InBuffer]; lpInBuffer
0x1800a3f0b  lea     rcx, [rbp+4Fh+BytesReturned]
0x1800a3f0f  xorps   xmm0, xmm0
0x1800a3f12  mov     qword ptr [rsp+0E0h+dwOptions], rcx; lpBytesReturned
0x1800a3f17  mov     r9d, 8; nInBufferSize
0x1800a3f1d  lea     rcx, [rbp+4Fh+DestinationString]
0x1800a3f21  mov     [rsp+0E0h+bInheritHandle], 10h; nOutBufferSize
0x1800a3f29  mov     qword ptr [rsp+0E0h+dwDesiredAccess], rcx; lpOutBuffer
0x1800a3f2e  mov     edx, 15026Ch; dwIoControlCode
0x1800a3f33  mov     rcx, rax; hDevice
0x1800a3f36  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800a3f3a  call    cs:__imp_DeviceIoControl
0x1800a3f40  test    eax, eax
0x1800a3f42  jz      loc_1800A3EC2
0x1800a3f48  mov     rdx, qword ptr [rbp+4Fh+DestinationString.Length]; void *
0x1800a3f4c  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800a3f50  call    ?Attach@SipcWin32Handle@@QEAAXPEAX@Z; SipcWin32Handle::Attach(void *)
0x1800a3f55  mov     r14, [rbp+4Fh+DestinationString.Buffer]
0x1800a3f59  lea     rcx, [rbp+4Fh+var_88]; this
0x1800a3f5d  call    ?Reset@SipcFileHandle@@QEAAXXZ; SipcFileHandle::Reset(void)
0x1800a3f62  mov     rbx, [rbp+4Fh+var_A0]
0x1800a3f66  mov     rcx, [rbp+4Fh+TargetHandle]
0x1800a3f6a  lea     rax, [rbp+4Fh+var_68]
0x1800a3f6e  mov     qword ptr [rsp+0E0h+bInheritHandle], rax
0x1800a3f73  lea     r9, [rdi+28h]
0x1800a3f77  xorps   xmm0, xmm0
0x1800a3f7a  lea     rax, [rbp+4Fh+var_78]
0x1800a3f7e  mov     r8, rbx
0x1800a3f81  mov     qword ptr [rsp+0E0h+dwDesiredAccess], rax
0x1800a3f86  xor     edx, edx
0x1800a3f88  movups  xmmword ptr [rbp-31h], xmm0
0x1800a3f8c  movups  xmmword ptr [rbp-21h], xmm0
0x1800a3f90  call    cs:__imp_NtAlpcCreatePortSection
0x1800a3f96  test    eax, eax
0x1800a3f98  jns     short loc_1800A3FAC
0x1800a3f9a  or      eax, 10000000h
0x1800a3f9f  mov     ebx, 8000FFFFh
0x1800a3fa4  cmovl   ebx, eax
0x1800a3fa7  jmp     loc_1800A40D5
0x1800a3fac  mov     rcx, [rbp+4Fh+TargetHandle]
0x1800a3fb0  lea     r8, [rbp+4Fh+var_80]
0x1800a3fb4  xor     edx, edx
0x1800a3fb6  call    cs:__imp_NtAlpcCreateSectionView
0x1800a3fbc  mov     edi, eax
0x1800a3fbe  test    eax, eax
0x1800a3fc0  js      loc_1800A40BF
0x1800a3fc6  mov     rdi, [rbp+4Fh+arg_20]
0x1800a3fca  xor     ecx, ecx
0x1800a3fcc  test    rsi, rsi
0x1800a3fcf  jz      short loc_1800A3FE5
0x1800a3fd1  mov     rax, [rbp+4Fh+var_70]
0x1800a3fd5  mov     byte ptr [rax+rcx], 0
0x1800a3fd9  add     rcx, 1000h
0x1800a3fe0  cmp     rcx, rsi
0x1800a3fe3  jb      short loc_1800A3FD1
0x1800a3fe5  mov     r8, [rbp+4Fh+var_68]
0x1800a3fe9  mov     edx, 0CCh; Val
0x1800a3fee  mov     rcx, [rbp+4Fh+var_70]
0x1800a3ff2  sub     r8, rsi; Size
0x1800a3ff5  add     rcx, rsi; void *
0x1800a3ff8  call    memset_0
0x1800a3ffd  mov     rbx, [rbp+4Fh+var_68]
0x1800a4001  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4008  add     rbx, 0FFFFFFFFFFFFFFD8h
0x1800a400c  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800a4011  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1800a4015  add     rbx, [rbp+4Fh+var_70]
0x1800a4019  mov     [rbx], rsi
0x1800a401c  movups  xmm0, xmmword ptr [r12]
0x1800a4021  movups  xmmword ptr [rbx+8], xmm0
0x1800a4025  movups  xmm1, xmmword ptr [r12+10h]
0x1800a402b  movups  xmmword ptr [rbx+18h], xmm1
0x1800a402f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a4034  test    rax, rax
0x1800a4037  jz      short loc_1800A40B3
0x1800a4039  mov     rcx, [rbp+4Fh+var_70]
0x1800a403d  lea     r10, ??_7SipcSection@@6B@; const SipcSection::`vftable'
0x1800a4044  mov     r8, [rbp+4Fh+TargetHandle]
0x1800a4048  mov     rdx, [rbp+4Fh+var_68]
0x1800a404c  mov     r9, [rbp+4Fh+var_78]
0x1800a4050  mov     [rax+20h], rcx
0x1800a4054  mov     [rax], r10
0x1800a4057  mov     [rax+28h], rdx
0x1800a405b  mov     [rax+18h], r13
0x1800a405f  mov     rcx, [rbx]
0x1800a4062  mov     [rax+30h], rcx
0x1800a4066  lea     rcx, ??_7AlpcSection@@6B@; const AlpcSection::`vftable'
0x1800a406d  movups  xmm0, xmmword ptr [rbx+8]
0x1800a4071  mov     [rdi], rax
0x1800a4074  movups  xmmword ptr [rax+38h], xmm0
0x1800a4078  movups  xmm1, xmmword ptr [rbx+18h]
0x1800a407c  mov     [rax], rcx
0x1800a407f  mov     rcx, rax; this
0x1800a4082  mov     dword ptr [rax+58h], 0
0x1800a4089  movups  xmmword ptr [rax+48h], xmm1
0x1800a408d  mov     [rax+60h], r8
0x1800a4091  mov     [rax+68h], r9
0x1800a4095  mov     [rax+70h], r14
0x1800a4099  mov     [rbp+4Fh+TargetHandle], 0
0x1800a40a1  call    ?ProtectExtraMemory@SipcSection@@IEBAXXZ; SipcSection::ProtectExtraMemory(void)
0x1800a40a6  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800a40aa  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a40af  xor     ebx, ebx
0x1800a40b1  jmp     short loc_1800A40DE
0x1800a40b3  mov     qword ptr [rdi], 0
0x1800a40ba  mov     edi, 0C0000017h
0x1800a40bf  mov     r8, [rbp+4Fh+var_78]; void *
0x1800a40c3  mov     rdx, r15; void *
0x1800a40c6  mov     rcx, [rbp+4Fh+var_70]; void *
0x1800a40ca  call    ?Unmap@AlpcSection@@CAJPEAX00@Z; AlpcSection::Unmap(void *,void *,void *)
0x1800a40cf  mov     ebx, eax
0x1800a40d1  test    eax, eax
0x1800a40d3  jns     short loc_1800A40EB
0x1800a40d5  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800a40d9  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a40de  lea     rcx, [rbp+4Fh+TargetHandle]; this
0x1800a40e2  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a40e7  mov     eax, ebx
0x1800a40e9  jmp     short loc_1800A4103
0x1800a40eb  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800a40ef  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a40f4  lea     rcx, [rbp+4Fh+TargetHandle]; this
0x1800a40f8  call    ?Reset@SipcWin32Handle@@QEAAXXZ; SipcWin32Handle::Reset(void)
0x1800a40fd  bts     edi, 1Ch
0x1800a4101  mov     eax, edi
0x1800a4103  add     rsp, 0A8h
0x1800a410a  pop     r15
0x1800a410c  pop     r14
0x1800a410e  pop     r13
0x1800a4110  pop     r12
0x1800a4112  pop     rdi
0x1800a4113  pop     rsi
0x1800a4114  pop     rbx
0x1800a4115  pop     rbp
0x1800a4116  retn
```
