# CIconOverlayExt::IsMemberOf(ushort const *,ulong)

- ea: `0x180001e50`
- end: `0x180002454`
- name: `?IsMemberOf@CIconOverlayExt@@UEAAJPEBGK@Z`
- size: `1540`
- prototype: `__int64 __fastcall(CIconOverlayExt *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e50`
- `0x180003c20`
- `0x1800065a0`
- `0x180008b40`
- `0x180032b8c`
- `0x18004c62a`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180001f71`
- `SHLWAPI!PathIsUNCW` at `0x180001f71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000214d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000214d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000216c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000216c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002071`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002071`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180001efa`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180001efa`
- `ntdll!RtlAppendPathElement` at `0x180002294`
- `ntdll!RtlAppendPathElement` at `0x180002294`
- `ntdll!RtlpEnsureBufferSize` at `0x180001fc8`
- `ntdll!RtlpEnsureBufferSize` at `0x1800021f9`
- `ntdll!RtlpEnsureBufferSize` at `0x180001fc8`
- `ntdll!RtlpEnsureBufferSize` at `0x1800021f9`
- `ntdll!RtlInitUnicodeString` at `0x180001f8f`
- `ntdll!RtlInitUnicodeString` at `0x1800021c0`
- `ntdll!RtlInitUnicodeString` at `0x18000227a`
- `ntdll!RtlInitUnicodeString` at `0x180001f8f`
- `ntdll!RtlInitUnicodeString` at `0x1800021c0`
- `ntdll!RtlInitUnicodeString` at `0x18000227a`
- `ntdll!RtlFreeUnicodeString` at `0x180002442`
- `ntdll!RtlFreeUnicodeString` at `0x180002442`
- `MPR!WNetGetConnectionW` at `0x1800020f6`
- `MPR!WNetGetConnectionW` at `0x180002191`
- `MPR!WNetGetConnectionW` at `0x1800020f6`
- `MPR!WNetGetConnectionW` at `0x180002191`

## pseudocode

```c
__int64 __fastcall CIconOverlayExt::IsMemberOf(CIconOverlayExt *this, const unsigned __int16 *a2)
{
  bool v2; // zf
  int Instance; // ebx
  PUCHAR StaticBuffer; // rcx
  __int64 result; // rax
  USHORT Length; // r9
  unsigned __int16 v8; // dx
  unsigned __int64 v9; // r8
  signed int v10; // edi
  unsigned __int64 v11; // rdx
  PUCHAR v12; // rdx
  signed int ConnectionW; // eax
  WCHAR *v14; // rsi
  SIZE_T v15; // r14
  HANDLE ProcessHeap; // rax
  signed int v17; // eax
  void *v18; // rdx
  USHORT v19; // r9
  unsigned __int16 v20; // dx
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // rdx
  int appended; // eax
  HANDLE v24; // rax
  int v25; // ecx
  int v26; // ecx
  DWORD DestinationString; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString_8; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR RemoteName[4]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-A0h] BYREF
  _WORD v33[260]; // [rsp+78h] [rbp-90h] BYREF
  int v34; // [rsp+280h] [rbp+178h] BYREF
  PUCHAR v35; // [rsp+288h] [rbp+180h]
  _RTL_BUFFER Buffer; // [rsp+290h] [rbp+188h] BYREF

  v2 = a2[1] == 58;
  Buffer.Buffer = (PUCHAR)v33;
  Buffer.StaticBuffer = (PUCHAR)v33;
  v35 = (PUCHAR)v33;
  LODWORD(v29) = 0;
  Buffer.Size = 520;
  Buffer.StaticSize = 520;
  v33[0] = 0;
  v34 = 34078720;
  if ( !v2 )
  {
    if ( !PathIsUNCW(a2) )
      goto LABEL_18;
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, a2);
    Length = DestinationString_8.Length;
    v8 = 0;
    LOWORD(v34) = 0;
    v9 = DestinationString_8.Length + 2LL;
    if ( v9 > 0xFFFE )
    {
      v26 = -1073741562;
    }
    else
    {
      if ( v9 <= Buffer.Size )
      {
LABEL_15:
        v10 = 0;
        v35 = Buffer.Buffer;
        memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v8 >> 1)], DestinationString_8.Buffer, Length);
        v11 = (unsigned __int16)(DestinationString_8.Length + v34);
        LOWORD(v34) = v11;
        HIWORD(v34) = v11 + 2;
        *(_WORD *)&v35[2 * (v11 >> 1)] = 0;
        goto LABEL_16;
      }
      if ( RtlpEnsureBufferSize(0, &Buffer, v9) >= 0 )
      {
        v8 = v34;
        Length = DestinationString_8.Length;
        goto LABEL_15;
      }
      v26 = -1073741801;
    }
    v10 = ResultFromNtStatus(v26);
    goto LABEL_16;
  }
  LOWORD(Buffer.ReservedForIMalloc) = *a2;
  *(_DWORD *)((char *)&Buffer.ReservedForIMalloc + 2) = 58;
  if ( GetDriveTypeW((LPCWSTR)&Buffer.ReservedForIMalloc) != 4 )
  {
LABEL_3:
    Instance = v29 == 0;
    goto LABEL_4;
  }
  DestinationString = 0;
  ConnectionW = WNetGetConnectionW((LPCWSTR)&Buffer.ReservedForIMalloc, RemoteName, &DestinationString);
  v10 = ConnectionW;
  if ( ConnectionW == 234 )
  {
    *(_QWORD *)&DestinationString_8.Length = 0;
    v15 = 2LL * DestinationString;
    if ( !is_mul_ok(DestinationString, 2u) )
      goto LABEL_18;
    v14 = 0;
    ProcessHeap = GetProcessHeap();
    v10 = -2147418113;
    if ( ProcessHeap )
    {
      v10 = 0;
      v14 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v15);
      if ( !v14 )
        v10 = -2147024882;
    }
    if ( v10 < 0 )
      goto LABEL_28;
    v17 = WNetGetConnectionW((LPCWSTR)&Buffer.ReservedForIMalloc, v14, &DestinationString);
    v10 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v10 = (unsigned __int16)v17 | 0x80070000;
      if ( v10 < 0 )
      {
        CscUtil_HeapFree(v14, v18);
        goto LABEL_28;
      }
    }
LABEL_39:
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, v14);
    v19 = DestinationString_8.Length;
    v20 = 0;
    LOWORD(v34) = 0;
    v21 = DestinationString_8.Length + 2LL;
    if ( v21 > 0xFFFE )
    {
      v25 = -1073741562;
    }
    else
    {
      if ( v21 <= Buffer.Size )
      {
LABEL_43:
        v35 = Buffer.Buffer;
        memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v20 >> 1)], DestinationString_8.Buffer, v19);
        v22 = (unsigned __int16)(DestinationString_8.Length + v34);
        LOWORD(v34) = v22;
        HIWORD(v34) = v22 + 2;
        *(_WORD *)&v35[2 * (v22 >> 1)] = 0;
        goto LABEL_44;
      }
      if ( RtlpEnsureBufferSize(0, &Buffer, v21) >= 0 )
      {
        v20 = v34;
        v19 = DestinationString_8.Length;
        goto LABEL_43;
      }
      v25 = -1073741801;
    }
    v10 = ResultFromNtStatus(v25);
    if ( v10 < 0 )
    {
LABEL_47:
      if ( v14 )
      {
        v24 = GetProcessHeap();
        if ( v24 )
        {
          if ( !HeapFree(v24, 0, v14) )
            ResultFromLastError();
        }
      }
      goto LABEL_16;
    }
LABEL_44:
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, a2 + 2);
    v10 = 0;
    appended = RtlAppendPathElement(1, &v34, &DestinationString_8);
    if ( appended < 0 )
      v10 = ResultFromNtStatus(appended);
    goto LABEL_47;
  }
  if ( ConnectionW > 0 )
    v10 = (unsigned __int16)ConnectionW | 0x80070000;
  v14 = 0;
  if ( v10 >= 0 )
    goto LABEL_39;
LABEL_28:
  if ( (_WORD)v10 == 2250 )
    goto LABEL_3;
LABEL_16:
  if ( v10 )
  {
    if ( v10 == 1 )
      goto LABEL_3;
  }
  else
  {
    CPath::RemoveBackslash((CPath *)v33);
  }
LABEL_18:
  *(_QWORD *)&DestinationString_8.Length = 0;
  Instance = CoCreateInstance(
               &CLSID_OfflineFilesCache,
               0,
               1u,
               &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
               (LPVOID *)&DestinationString_8);
  if ( Instance >= 0 )
  {
    v12 = v35;
    v30 = 0;
    if ( Buffer.Buffer != Buffer.StaticBuffer )
      v12 = Buffer.Buffer;
    Instance = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, __int64 *))(**(_QWORD **)&DestinationString_8.Length
                                                                            + 80LL))(
                 *(_QWORD *)&DestinationString_8.Length,
                 v12,
                 0,
                 &v30);
    if ( Instance >= 0 )
    {
      DestinationString = 0;
      v32 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v32) >= 0 )
      {
        Buffer.ReservedForIMalloc = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, PVOID *))v32)(
               v32,
               &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b,
               &Buffer.ReservedForIMalloc) >= 0 )
        {
          (*(void (__fastcall **)(PVOID, DWORD *))(*(_QWORD *)Buffer.ReservedForIMalloc + 24LL))(
            Buffer.ReservedForIMalloc,
            &DestinationString);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Buffer.ReservedForIMalloc + 16LL))(Buffer.ReservedForIMalloc);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        if ( !DestinationString )
        {
          Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, PVOID *))v30)(
                       v30,
                       &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b,
                       &Buffer.ReservedForIMalloc);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)Buffer.ReservedForIMalloc + 24LL))(
                         Buffer.ReservedForIMalloc,
                         &v29);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Buffer.ReservedForIMalloc + 16LL))(Buffer.ReservedForIMalloc);
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&DestinationString_8.Length + 16LL))(*(_QWORD *)&DestinationString_8.Length);
    if ( Instance >= 0 )
      goto LABEL_3;
  }
LABEL_4:
  StaticBuffer = Buffer.StaticBuffer;
  if ( Buffer.Buffer && Buffer.Buffer != Buffer.StaticBuffer )
  {
    *(_QWORD *)&DestinationString_8.Length = 0;
    DestinationString_8.Buffer = (PWSTR)Buffer.Buffer;
    RtlFreeUnicodeString(&DestinationString_8);
    StaticBuffer = Buffer.StaticBuffer;
  }
  result = (unsigned int)Instance;
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return result;
}

```

## disassembly

```asm
0x180001e50  mov     r11, rsp
0x180001e53  push    rbp
0x180001e54  push    rbx
0x180001e55  push    r15
0x180001e57  lea     rbp, [r11-1D8h]
0x180001e5e  sub     rsp, 2C0h
0x180001e65  mov     rax, cs:__security_cookie
0x180001e6c  xor     rax, rsp
0x180001e6f  mov     [rbp+1D0h+var_18], rax
0x180001e76  xor     r15d, r15d
0x180001e79  mov     [r11+8], rsi
0x180001e7d  cmp     word ptr [rdx+2], 3Ah ; ':'
0x180001e82  lea     rax, [rsp+2D0h+var_260]
0x180001e87  mov     [rbp+1D0h+Buffer.Buffer], rax
0x180001e8e  mov     ecx, 208h
0x180001e93  lea     rax, [rsp+2D0h+var_260]
0x180001e98  mov     [r11+18h], rdi
0x180001e9c  mov     [rbp+1D0h+Buffer.StaticBuffer], rax
0x180001ea3  mov     rbx, rdx
0x180001ea6  lea     rax, [rsp+2D0h+var_260]
0x180001eab  mov     [r11+20h], r14
0x180001eaf  mov     [rbp+1D0h+var_50], rax
0x180001eb6  mov     dword ptr [rsp+2D0h+var_288], r15d
0x180001ebb  mov     [rbp+1D0h+Buffer.Size], rcx
0x180001ec2  mov     [rbp+1D0h+Buffer.StaticSize], rcx
0x180001ec9  mov     [rsp+2D0h+var_260], r15w
0x180001ecf  mov     [rbp+1D0h+var_58], 2080000h
0x180001ed9  jnz     loc_180001F6E
0x180001edf  movzx   eax, word ptr [rdx]
0x180001ee2  lea     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]; lpRootPathName
0x180001ee9  mov     word ptr [rbp+1D0h+Buffer.ReservedForIMalloc], ax
0x180001ef0  mov     dword ptr [rbp+1D0h+Buffer.ReservedForIMalloc+2], 3Ah ; ':'
0x180001efa  call    cs:__imp_GetDriveTypeW
0x180001f00  cmp     eax, 4
0x180001f03  jz      loc_1800020E0
0x180001f09  cmp     dword ptr [rsp+2D0h+var_288], r15d
0x180001f0e  mov     ebx, r15d
0x180001f11  setz    bl
0x180001f14  mov     rax, [rbp+1D0h+Buffer.Buffer]
0x180001f1b  mov     r14, [rsp+2D0h+arg_18]
0x180001f23  mov     rdi, [rsp+2D0h+arg_10]
0x180001f2b  mov     rsi, [rsp+2D0h+arg_0]
0x180001f33  mov     rcx, [rbp+1D0h+Buffer.StaticBuffer]
0x180001f3a  test    rax, rax
0x180001f3d  jz      short loc_180001F48
0x180001f3f  cmp     rax, rcx
0x180001f42  jnz     loc_180002433
0x180001f48  mov     eax, ebx
0x180001f4a  test    rcx, rcx
0x180001f4d  jz      short loc_180001F53
0x180001f4f  mov     [rcx], r15w
0x180001f53  mov     rcx, [rbp+1D0h+var_18]
0x180001f5a  xor     rcx, rsp; StackCookie
0x180001f5d  call    __security_check_cookie
0x180001f62  add     rsp, 2C0h
0x180001f69  pop     r15
0x180001f6b  pop     rbx
0x180001f6c  pop     rbp
0x180001f6d  retn
0x180001f6e  mov     rcx, rbx; pszPath
0x180001f71  call    cs:__imp_PathIsUNCW
0x180001f77  test    eax, eax
0x180001f79  jz      loc_18000204C
0x180001f7f  xorps   xmm0, xmm0
0x180001f82  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; DestinationString
0x180001f87  mov     rdx, rbx; SourceString
0x180001f8a  movups  xmmword ptr [rsp+2D0h+DestinationString.Buffer], xmm0
0x180001f8f  call    cs:__imp_RtlInitUnicodeString
0x180001f95  movzx   r9d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x180001f9b  mov     edx, r15d
0x180001f9e  mov     word ptr [rbp+1D0h+var_58], dx
0x180001fa5  lea     r8, [r9+2]; RequiredSize
0x180001fa9  cmp     r8, 0FFFEh
0x180001fb0  ja      loc_180002311
0x180001fb6  cmp     r8, [rbp+1D0h+Buffer.Size]
0x180001fbd  jbe     short loc_180001FE3
0x180001fbf  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x180001fc6  xor     ecx, ecx; Flags
0x180001fc8  call    cs:__imp_RtlpEnsureBufferSize
0x180001fce  test    eax, eax
0x180001fd0  js      loc_180002318
0x180001fd6  movzx   edx, word ptr [rbp+1D0h+var_58]
0x180001fdd  movzx   r9d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x180001fe3  mov     rcx, [rbp+1D0h+Buffer.Buffer]
0x180001fea  mov     edi, r15d
0x180001fed  movzx   eax, dx
0x180001ff0  mov     rdx, [rsp+2D0h+Src]; Src
0x180001ff5  shr     rax, 1
0x180001ff8  mov     [rbp+1D0h+var_50], rcx
0x180001fff  movzx   r8d, r9w; Size
0x180002003  lea     rcx, [rcx+rax*2]; void *
0x180002007  call    memmove_0
0x18000200c  movzx   eax, word ptr [rbp+1D0h+var_58]
0x180002013  add     ax, word ptr [rsp+2D0h+DestinationString.Buffer]
0x180002018  movzx   edx, ax
0x18000201b  mov     word ptr [rbp+1D0h+var_58], dx
0x180002022  lea     eax, [rdx+2]
0x180002025  shr     rdx, 1
0x180002028  mov     word ptr [rbp+1D0h+var_58+2], ax
0x18000202f  mov     rax, [rbp+1D0h+var_50]
0x180002036  mov     [rax+rdx*2], r15w
0x18000203b  test    edi, edi
0x18000203d  jz      loc_180002329
0x180002043  cmp     edi, 1
0x180002046  jz      loc_180001F09
0x18000204c  lea     rax, [rsp+2D0h+DestinationString.Buffer]
0x180002051  mov     [rsp+2D0h+DestinationString.Buffer], r15
0x180002056  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x18000205d  mov     [rsp+20h], rax; ppv
0x180002062  xor     edx, edx; pUnkOuter
0x180002064  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18000206b  mov     r8d, 1; dwClsContext
0x180002071  call    cs:__imp_CoCreateInstance
0x180002077  mov     ebx, eax
0x180002079  test    eax, eax
0x18000207b  js      loc_180001F14
0x180002081  mov     r8, [rbp+1D0h+Buffer.Buffer]
0x180002088  lea     r9, [rsp+2D0h+var_280]
0x18000208d  cmp     r8, [rbp+1D0h+Buffer.StaticBuffer]
0x180002094  mov     rcx, [rsp+2D0h+DestinationString.Buffer]
0x180002099  mov     rdx, [rbp+1D0h+var_50]
0x1800020a0  mov     [rsp+2D0h+var_280], r15
0x1800020a5  cmovnz  rdx, r8
0x1800020a9  xor     r8d, r8d
0x1800020ac  mov     rax, [rcx]
0x1800020af  mov     rax, [rax+50h]
0x1800020b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b8  mov     ebx, eax
0x1800020ba  test    eax, eax
0x1800020bc  jns     loc_180002338
0x1800020c2  mov     rcx, [rsp+2D0h+DestinationString.Buffer]
0x1800020c7  mov     rax, [rcx]
0x1800020ca  mov     rax, [rax+10h]
0x1800020ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020d3  test    ebx, ebx
0x1800020d5  js      loc_180001F14
0x1800020db  jmp     loc_180001F09
0x1800020e0  lea     r8, [rsp+2D0h+DestinationString]; lpnLength
0x1800020e5  mov     dword ptr [rsp+2D0h+DestinationString.Length], r15d
0x1800020ea  lea     rdx, [rsp+2D0h+RemoteName]; lpRemoteName
0x1800020ef  lea     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]; lpLocalName
0x1800020f6  call    cs:__imp_WNetGetConnectionW
0x1800020fc  mov     edi, eax
0x1800020fe  cmp     eax, 0EAh
0x180002103  jz      short loc_18000212D
0x180002105  test    eax, eax
0x180002107  jle     short loc_180002112
0x180002109  movzx   edi, ax
0x18000210c  or      edi, 80070000h
0x180002112  mov     rsi, r15
0x180002115  test    edi, edi
0x180002117  jns     loc_1800021B0
0x18000211d  cmp     di, 8CAh
0x180002122  jz      loc_180001F09
0x180002128  jmp     loc_18000203B
0x18000212d  mov     ecx, dword ptr [rsp+2D0h+DestinationString.Length]
0x180002131  mov     eax, 2
0x180002136  mul     rcx
0x180002139  mov     [rsp+2D0h+DestinationString.Buffer], r15
0x18000213e  mov     r14, rax
0x180002141  test    rdx, rdx
0x180002144  jnz     loc_18000204C
0x18000214a  mov     rsi, r15
0x18000214d  call    cs:__imp_GetProcessHeap
0x180002153  test    rax, rax
0x180002156  mov     edi, 8000FFFFh
0x18000215b  cmovnz  edi, r15d
0x18000215f  jz      short loc_18000217E
0x180002161  mov     r8, r14; dwBytes
0x180002164  mov     edx, 8; dwFlags
0x180002169  mov     rcx, rax; hHeap
0x18000216c  call    cs:__imp_HeapAlloc
0x180002172  mov     rsi, rax
0x180002175  test    rax, rax
0x180002178  jz      loc_1800022EC
0x18000217e  test    edi, edi
0x180002180  js      short loc_18000211D
0x180002182  lea     r8, [rsp+2D0h+DestinationString]; lpnLength
0x180002187  mov     rdx, rsi; lpRemoteName
0x18000218a  lea     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]; lpLocalName
0x180002191  call    cs:__imp_WNetGetConnectionW
0x180002197  mov     edi, eax
0x180002199  test    eax, eax
0x18000219b  jz      short loc_1800021B0
0x18000219d  jle     short loc_1800021A8
0x18000219f  movzx   edi, ax
0x1800021a2  or      edi, 80070000h
0x1800021a8  test    edi, edi
0x1800021aa  js      loc_1800022F6
0x1800021b0  xorps   xmm0, xmm0
0x1800021b3  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; DestinationString
0x1800021b8  mov     rdx, rsi; SourceString
0x1800021bb  movups  xmmword ptr [rsp+2D0h+DestinationString.Buffer], xmm0
0x1800021c0  call    cs:__imp_RtlInitUnicodeString
0x1800021c6  movzx   r9d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x1800021cc  mov     edx, r15d
0x1800021cf  mov     word ptr [rbp+1D0h+var_58], dx
0x1800021d6  lea     r8, [r9+2]; RequiredSize
0x1800021da  cmp     r8, 0FFFEh
0x1800021e1  ja      loc_180002303
0x1800021e7  cmp     r8, [rbp+1D0h+Buffer.Size]
0x1800021ee  jbe     short loc_180002214
0x1800021f0  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x1800021f7  xor     ecx, ecx; Flags
0x1800021f9  call    cs:__imp_RtlpEnsureBufferSize
0x1800021ff  test    eax, eax
0x180002201  js      loc_18000230A
0x180002207  movzx   edx, word ptr [rbp+1D0h+var_58]
0x18000220e  movzx   r9d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x180002214  mov     rcx, [rbp+1D0h+Buffer.Buffer]
0x18000221b  movzx   eax, dx
0x18000221e  mov     rdx, [rsp+2D0h+Src]; Src
0x180002223  shr     rax, 1
0x180002226  mov     [rbp+1D0h+var_50], rcx
0x18000222d  movzx   r8d, r9w; Size
0x180002231  lea     rcx, [rcx+rax*2]; void *
0x180002235  call    memmove_0
0x18000223a  movzx   eax, word ptr [rbp+1D0h+var_58]
0x180002241  add     ax, word ptr [rsp+2D0h+DestinationString.Buffer]
0x180002246  movzx   edx, ax
0x180002249  mov     word ptr [rbp+1D0h+var_58], dx
0x180002250  lea     eax, [rdx+2]
0x180002253  shr     rdx, 1
0x180002256  mov     word ptr [rbp+1D0h+var_58+2], ax
0x18000225d  mov     rax, [rbp+1D0h+var_50]
0x180002264  mov     [rax+rdx*2], r15w
0x180002269  xorps   xmm0, xmm0
0x18000226c  lea     rdx, [rbx+4]; SourceString
0x180002270  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; DestinationString
0x180002275  movups  xmmword ptr [rsp+2D0h+DestinationString.Buffer], xmm0
0x18000227a  call    cs:__imp_RtlInitUnicodeString
0x180002280  lea     r8, [rsp+2D0h+DestinationString.Buffer]
0x180002285  mov     ecx, 1
0x18000228a  lea     rdx, [rbp+1D0h+var_58]
0x180002291  mov     edi, r15d
0x180002294  call    cs:__imp_RtlAppendPathElement
0x18000229a  test    eax, eax
0x18000229c  jns     short loc_1800022B4
0x18000229e  mov     ecx, eax; int
0x1800022a0  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800022a5  mov     edi, eax
0x1800022a7  jmp     short loc_1800022B4
0x1800022a9  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800022ae  mov     edi, eax
0x1800022b0  test    eax, eax
0x1800022b2  jns     short loc_180002269
0x1800022b4  test    rsi, rsi
0x1800022b7  jz      loc_18000203B
0x1800022bd  call    cs:__imp_GetProcessHeap
0x1800022c3  test    rax, rax
0x1800022c6  jz      loc_18000203B
0x1800022cc  mov     r8, rsi; lpMem
0x1800022cf  xor     edx, edx; dwFlags
0x1800022d1  mov     rcx, rax; hHeap
0x1800022d4  call    cs:__imp_HeapFree
0x1800022da  test    eax, eax
0x1800022dc  jnz     loc_18000203B
0x1800022e2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800022e7  jmp     loc_18000203B
0x1800022ec  mov     edi, 8007000Eh
0x1800022f1  jmp     loc_18000217E
0x1800022f6  mov     rcx, rsi; lpMem
0x1800022f9  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800022fe  jmp     loc_18000211D
0x180002303  mov     ecx, 0C0000106h; int
0x180002308  jmp     short loc_1800022A9
0x18000230a  mov     ecx, 0C0000017h
0x18000230f  jmp     short loc_1800022A9
0x180002311  mov     ecx, 0C0000106h
0x180002316  jmp     short loc_18000231D
0x180002318  mov     ecx, 0C0000017h; int
0x18000231d  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180002322  mov     edi, eax
0x180002324  jmp     loc_18000203B
0x180002329  lea     rcx, [rsp+2D0h+var_260]; this
0x18000232e  call    ?RemoveBackslash@CPath@@QEAAJXZ; CPath::RemoveBackslash(void)
0x180002333  jmp     loc_18000204C
0x180002338  mov     rcx, [rsp+2D0h+var_280]
0x18000233d  lea     rdx, [rsp+2D0h+var_270]
0x180002342  mov     dword ptr [rsp+2D0h+DestinationString.Length], r15d
0x180002347  mov     [rsp+2D0h+var_270], r15
0x18000234c  mov     rax, [rcx]
0x18000234f  mov     rax, [rax+28h]
0x180002353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002358  test    eax, eax
0x18000235a  js      loc_18000241D
0x180002360  mov     rcx, [rsp+2D0h+var_270]
0x180002365  lea     r8, [rbp+1D0h+Buffer.ReservedForIMalloc]
0x18000236c  mov     [rbp+1D0h+Buffer.ReservedForIMalloc], r15
0x180002373  lea     rdx, _GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b
0x18000237a  mov     rax, [rcx]
0x18000237d  mov     rax, [rax]
0x180002380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002385  test    eax, eax
0x180002387  js      short loc_1800023B4
0x180002389  mov     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]
0x180002390  lea     rdx, [rsp+2D0h+DestinationString]
0x180002395  mov     rax, [rcx]
0x180002398  mov     rax, [rax+18h]
0x18000239c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
