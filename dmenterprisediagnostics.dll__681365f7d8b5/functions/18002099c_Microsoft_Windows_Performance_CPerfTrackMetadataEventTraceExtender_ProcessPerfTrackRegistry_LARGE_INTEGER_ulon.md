# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002099c`
- end: `0x180020b60`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `452`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fd80`

## callees

- `0x180001800`
- `0x180009e98`
- `0x18000f63c`
- `0x18000fc40`
- `0x18001ffe0`
- `0x1800202cc`
- `0x18002099c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020b21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020b21`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020a57`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020a57`

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
  unsigned int v8; // eax
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
0x18002099c  push    rbp
0x18002099e  push    rbx
0x18002099f  push    rsi
0x1800209a0  push    rdi
0x1800209a1  push    r12
0x1800209a3  push    r13
0x1800209a5  push    r14
0x1800209a7  push    r15
0x1800209a9  lea     rbp, [rsp-0A8h]
0x1800209b1  sub     rsp, 1A8h
0x1800209b8  mov     rax, cs:__security_cookie
0x1800209bf  xor     rax, rsp
0x1800209c2  mov     [rbp+0E0h+var_50], rax
0x1800209c9  mov     r12d, r9d
0x1800209cc  mov     r15d, r8d
0x1800209cf  mov     rbx, rdx
0x1800209d2  mov     r14, rcx
0x1800209d5  xor     r13d, r13d
0x1800209d8  mov     [rsp+1E0h+hKey], r13
0x1800209dd  mov     [rsp+1E0h+var_168], r13
0x1800209e2  mov     [rbp+0E0h+var_160], r13
0x1800209e6  mov     r9d, 20019h; unsigned int
0x1800209ec  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800209f3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800209fa  lea     rcx, [rsp+1E0h+hKey]; this
0x1800209ff  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180020a04  test    eax, eax
0x180020a06  jz      short loc_180020A16
0x180020a08  mov     ecx, eax; unsigned int
0x180020a0a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180020a0f  mov     ebx, eax
0x180020a11  jmp     loc_180020B30
0x180020a16  mov     [rsp+1E0h+Block], r13
0x180020a1b  mov     [rsp+1E0h+var_178], r13d
0x180020a20  mov     edi, r13d
0x180020a23  mov     [rsp+1E0h+cchName], 80h
0x180020a2b  mov     qword ptr [rbp+0E0h+ftLastWriteTime.dwLowDateTime], r13
0x180020a2f  lea     rax, [rbp+0E0h+ftLastWriteTime]
0x180020a33  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180020a38  mov     [rsp+1E0h+lpcchClass], r13; lpcchClass
0x180020a3d  mov     [rsp+1E0h+lpClass], r13; lpClass
0x180020a42  mov     [rsp+1E0h+lpReserved], r13; lpReserved
0x180020a47  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x180020a4c  lea     r8, [rbp+0E0h+Name]; lpName
0x180020a50  mov     edx, edi; dwIndex
0x180020a52  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180020a57  call    cs:__imp_RegEnumKeyExW
0x180020a5e  nop     dword ptr [rax+rax+00h]
0x180020a63  mov     esi, eax
0x180020a65  test    eax, eax
0x180020a67  jnz     loc_180020B0E
0x180020a6d  cmp     [rsp+1E0h+cchName], 80h
0x180020a75  jnb     loc_180020B0E
0x180020a7b  mov     [rsp+1E0h+var_198], r13
0x180020a80  mov     [rsp+1E0h+var_190], r13
0x180020a85  mov     [rsp+1E0h+var_188], r13
0x180020a8a  mov     r9d, 20019h; unsigned int
0x180020a90  lea     r8, [rbp+0E0h+Name]; lpSubKey
0x180020a94  mov     rdx, [rsp+1E0h+hKey]; hKey
0x180020a99  lea     rcx, [rsp+1E0h+var_198]; this
0x180020a9e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180020aa3  test    eax, eax
0x180020aa5  jnz     short loc_180020B04
0x180020aa7  lea     rax, [rsp+1E0h+Block]
0x180020aac  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x180020ab1  lea     rax, [rbp+0E0h+Name]
0x180020ab5  mov     [rsp+1E0h+lpClass], rax; __int64
0x180020aba  lea     rax, [rsp+1E0h+var_198]
0x180020abf  mov     [rsp+1E0h+lpReserved], rax; ATL::CRegKey *
0x180020ac4  mov     r9d, r12d; int
0x180020ac7  mov     r8d, r15d; int
0x180020aca  mov     rdx, rbx; int
0x180020acd  mov     rcx, r14; int
0x180020ad0  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x180020ad5  lea     rax, [rsp+1E0h+Block]
0x180020ada  mov     [rsp+1E0h+lpcchClass], rax; __int64
0x180020adf  lea     rax, [rbp+0E0h+Name]
0x180020ae3  mov     [rsp+1E0h+lpClass], rax; __int64
0x180020ae8  lea     rax, [rsp+1E0h+var_198]
0x180020aed  mov     [rsp+1E0h+lpReserved], rax; ATL::CRegKey *
0x180020af2  mov     r9d, r12d; int
0x180020af5  mov     r8d, r15d; int
0x180020af8  mov     rdx, rbx; int
0x180020afb  mov     rcx, r14; int
0x180020afe  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x180020b03  nop
0x180020b04  lea     rcx, [rsp+1E0h+var_198]; this
0x180020b09  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020b0e  inc     edi
0x180020b10  cmp     esi, 103h
0x180020b16  jnz     loc_180020A23
0x180020b1c  mov     rcx, [rsp+1E0h+Block]; Block
0x180020b21  call    cs:__imp_free
0x180020b28  nop     dword ptr [rax+rax+00h]
0x180020b2d  mov     ebx, r13d
0x180020b30  lea     rcx, [rsp+1E0h+hKey]; this
0x180020b35  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020b3a  mov     eax, ebx
0x180020b3c  mov     rcx, [rbp+0E0h+var_50]
0x180020b43  xor     rcx, rsp; StackCookie
0x180020b46  call    __security_check_cookie
0x180020b4b  add     rsp, 1A8h
0x180020b52  pop     r15
0x180020b54  pop     r14
0x180020b56  pop     r13
0x180020b58  pop     r12
0x180020b5a  pop     rdi
0x180020b5b  pop     rsi
0x180020b5c  pop     rbx
0x180020b5d  pop     rbp
0x180020b5e  retn
```
