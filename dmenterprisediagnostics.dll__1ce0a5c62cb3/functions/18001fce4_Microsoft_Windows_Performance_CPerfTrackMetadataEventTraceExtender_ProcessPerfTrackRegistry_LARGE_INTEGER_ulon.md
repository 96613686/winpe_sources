# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001fce4`
- end: `0x18001fe9b`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `439`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f160`

## callees

- `0x1800017e0`
- `0x1800099b8`
- `0x18000efbc`
- `0x18000f570`
- `0x18001f3a4`
- `0x18001f664`
- `0x18001fce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe63`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001fd9f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001fd9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4)
{
  DWORD LowPart; // ebx
  int v7; // r14d
  int v8; // eax
  unsigned int v9; // ebx
  DWORD v10; // edi
  LSTATUS v11; // esi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  void *v14[3]; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+68h] [rbp-98h]
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[128]; // [rsp+90h] [rbp-70h] BYREF

  LowPart = a2.LowPart;
  v7 = (int)this;
  memset(hKey, 0, sizeof(hKey));
  v8 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\PerfTrack\\InteractionClasses",
         0x20019u);
  if ( v8 )
  {
    v9 = ATL::AtlHresultFromWin32(v8);
  }
  else
  {
    Block = 0;
    v16 = 0;
    v10 = 0;
    do
    {
      cchName = 128;
      ftLastWriteTime = 0;
      v11 = RegEnumKeyExW(hKey[0], v10, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( !v11 && cchName < 0x80 )
      {
        memset(v14, 0, sizeof(v14));
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v14, hKey[0], Name, 0x20019u) )
        {
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(
            v7,
            LowPart,
            a3,
            a4,
            (ATL::CRegKey *)v14,
            (__int64)Name,
            (__int64)&Block);
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(
            v7,
            LowPart,
            a3,
            a4,
            (ATL::CRegKey *)v14,
            (__int64)Name,
            (__int64)&Block);
        }
        ATL::CRegKey::Close((ATL::CRegKey *)v14);
      }
      ++v10;
    }
    while ( v11 != 259 );
    free(Block);
    v9 = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v9;
}

```

## disassembly

```asm
0x18001fce4  push    rbp
0x18001fce6  push    rbx
0x18001fce7  push    rsi
0x18001fce8  push    rdi
0x18001fce9  push    r12
0x18001fceb  push    r13
0x18001fced  push    r14
0x18001fcef  push    r15
0x18001fcf1  lea     rbp, [rsp-0A8h]
0x18001fcf9  sub     rsp, 1A8h
0x18001fd00  mov     rax, cs:__security_cookie
0x18001fd07  xor     rax, rsp
0x18001fd0a  mov     [rbp+0E0h+var_50], rax
0x18001fd11  mov     r12d, r9d
0x18001fd14  mov     r15d, r8d
0x18001fd17  mov     rbx, rdx
0x18001fd1a  mov     r14, rcx
0x18001fd1d  xor     r13d, r13d
0x18001fd20  mov     [rsp+1E0h+hKey], r13
0x18001fd25  mov     [rsp+1E0h+var_168], r13
0x18001fd2a  mov     [rbp+0E0h+var_160], r13
0x18001fd2e  mov     r9d, 20019h; unsigned int
0x18001fd34  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001fd3b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001fd42  lea     rcx, [rsp+1E0h+hKey]; this
0x18001fd47  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001fd4c  test    eax, eax
0x18001fd4e  jz      short loc_18001FD5E
0x18001fd50  mov     ecx, eax; unsigned int
0x18001fd52  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001fd57  mov     ebx, eax
0x18001fd59  jmp     loc_18001FE6C
0x18001fd5e  mov     [rsp+1E0h+Block], r13
0x18001fd63  mov     [rsp+1E0h+var_178], r13d
0x18001fd68  mov     edi, r13d
0x18001fd6b  mov     [rsp+1E0h+cchName], 80h
0x18001fd73  mov     qword ptr [rbp+0E0h+ftLastWriteTime.dwLowDateTime], r13
0x18001fd77  lea     rax, [rbp+0E0h+ftLastWriteTime]
0x18001fd7b  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001fd80  mov     [rsp+1E0h+lpcchClass], r13; lpcchClass
0x18001fd85  mov     [rsp+1E0h+lpClass], r13; lpClass
0x18001fd8a  mov     [rsp+1E0h+lpReserved], r13; lpReserved
0x18001fd8f  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x18001fd94  lea     r8, [rbp+0E0h+Name]; lpName
0x18001fd98  mov     edx, edi; dwIndex
0x18001fd9a  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001fd9f  call    cs:__imp_RegEnumKeyExW
0x18001fda5  mov     esi, eax
0x18001fda7  test    eax, eax
0x18001fda9  jnz     loc_18001FE50
0x18001fdaf  cmp     [rsp+1E0h+cchName], 80h
0x18001fdb7  jnb     loc_18001FE50
0x18001fdbd  mov     [rsp+1E0h+var_198], r13
0x18001fdc2  mov     [rsp+1E0h+var_190], r13
0x18001fdc7  mov     [rsp+1E0h+var_188], r13
0x18001fdcc  mov     r9d, 20019h; unsigned int
0x18001fdd2  lea     r8, [rbp+0E0h+Name]; lpSubKey
0x18001fdd6  mov     rdx, [rsp+1E0h+hKey]; hKey
0x18001fddb  lea     rcx, [rsp+1E0h+var_198]; this
0x18001fde0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001fde5  test    eax, eax
0x18001fde7  jnz     short loc_18001FE46
0x18001fde9  lea     rax, [rsp+1E0h+Block]
0x18001fdee  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x18001fdf3  lea     rax, [rbp+0E0h+Name]
0x18001fdf7  mov     [rsp+1E0h+lpClass], rax; __int64
0x18001fdfc  lea     rax, [rsp+1E0h+var_198]
0x18001fe01  mov     [rsp+1E0h+lpReserved], rax; ATL::CRegKey *
0x18001fe06  mov     r9d, r12d; int
0x18001fe09  mov     r8d, r15d; int
0x18001fe0c  mov     rdx, rbx; int
0x18001fe0f  mov     rcx, r14; int
0x18001fe12  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18001fe17  lea     rax, [rsp+1E0h+Block]
0x18001fe1c  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x18001fe21  lea     rax, [rbp+0E0h+Name]
0x18001fe25  mov     [rsp+1E0h+lpClass], rax; __int64
0x18001fe2a  lea     rax, [rsp+1E0h+var_198]
0x18001fe2f  mov     [rsp+1E0h+lpReserved], rax; ATL::CRegKey *
0x18001fe34  mov     r9d, r12d; int
0x18001fe37  mov     r8d, r15d; int
0x18001fe3a  mov     rdx, rbx; int
0x18001fe3d  mov     rcx, r14; int
0x18001fe40  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18001fe45  nop
0x18001fe46  lea     rcx, [rsp+1E0h+var_198]; this
0x18001fe4b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fe50  inc     edi
0x18001fe52  cmp     esi, 103h
0x18001fe58  jnz     loc_18001FD6B
0x18001fe5e  mov     rcx, [rsp+1E0h+Block]; Block
0x18001fe63  call    cs:__imp_free
0x18001fe69  mov     ebx, r13d
0x18001fe6c  lea     rcx, [rsp+1E0h+hKey]; this
0x18001fe71  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fe76  mov     eax, ebx
0x18001fe78  mov     rcx, [rbp+0E0h+var_50]
0x18001fe7f  xor     rcx, rsp; StackCookie
0x18001fe82  call    __security_check_cookie
0x18001fe87  add     rsp, 1A8h
0x18001fe8e  pop     r15
0x18001fe90  pop     r14
0x18001fe92  pop     r13
0x18001fe94  pop     r12
0x18001fe96  pop     rdi
0x18001fe97  pop     rsi
0x18001fe98  pop     rbx
0x18001fe99  pop     rbp
0x18001fe9a  retn
```
