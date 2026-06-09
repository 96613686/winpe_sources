# System::System(void)

- ea: `0x1004e3a0`
- end: `0x1004e6e8`
- name: `??0System@@QAE@XZ`
- size: `840`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x10008130`

## callees

- `0x1000f750`
- `0x1000faa0`
- `0x1000fc30`
- `0x10012db0`
- `0x100186f0`
- `0x10025e60`
- `0x1004e3a0`
- `0x1004eda0`
- `0x1005cbf0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004e681`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004e681`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1004e595`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1004e595`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1004e3fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1004e3fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e3ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e441`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e488`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e3ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e441`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1004e488`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1004e508`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1004e508`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1004e69b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1004e69b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1004e4fe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1004e4fe`

## pseudocode

```c
void *System::System()
{
  struct Err *v0; // ecx
  int v1; // ecx
  SIZE_T v2; // ecx
  void *v3; // eax
  _SYSTEM_INFO SystemInfo; // [esp+4h] [ebp-6Ch] BYREF
  _DWORD v6[3]; // [esp+28h] [ebp-48h] BYREF
  void *Block; // [esp+34h] [ebp-3Ch]
  void *v8; // [esp+38h] [ebp-38h]
  Err *v9; // [esp+3Ch] [ebp-34h]
  _MEMORYSTATUS Buffer; // [esp+40h] [ebp-30h] BYREF
  int v11; // [esp+6Ch] [ebp-4h]

  v9 = (Err *)&Sys;
  Sys = 1;
  v11 = 0;
  InitializeCriticalSection(&stru_100668BC);
  hEvent = CreateEventA(0, 0, 0, 0);
  if ( !hEvent )
    System::ErrGetLastError(v0);
  dword_100668DC = 0;
  dword_100668E0 = 0;
  dword_100668D8 = 0;
  dword_100668E4 = 1;
  InitializeCriticalSection(&stru_100668F8);
  dword_1006691C = 0;
  dword_10066920 = 0;
  dword_10066924 = 0;
  dword_10066948 = 0;
  dword_1006694C = 0;
  dword_10066944 = 0;
  InitializeCriticalSection(&stru_10066950);
  dword_10066974 = 0;
  v6[0] = 1;
  LOBYTE(v11) = 5;
  dword_10066928 = 0;
  lpAddress = 0;
  dword_10066968 = 0;
  dword_1006696C = 0;
  dword_10066970 = 0;
  dword_10066940 = 0;
  dword_100668B4 = 3;
  dword_100668B8 = 0;
  Buffer.dwLength = 32;
  GlobalMemoryStatus(&Buffer);
  GetSystemInfo(&SystemInfo);
  v1 = 0;
  dword_10066914 = 0;
  if ( SystemInfo.dwPageSize != 1 )
  {
    do
      dword_10066914 = ++v1;
    while ( 1 << v1 != SystemInfo.dwPageSize );
  }
  if ( Buffer.dwTotalPhys > 0x4000000 )
  {
    dword_1006692C = 0x8000;
    v2 = 0x8000;
LABEL_9:
    dword_10066930 = 6912;
    goto LABEL_10;
  }
  dword_10066930 = 256;
  v2 = Buffer.dwTotalPhys >> 11;
  dword_1006692C = Buffer.dwTotalPhys >> 11;
  if ( Buffer.dwTotalPhys > 0xC00000 )
  {
    dword_10066930 = ((Buffer.dwTotalPhys - 12582912) >> 13) + 256;
    if ( (unsigned int)dword_10066930 > 0x1B00 )
      goto LABEL_9;
  }
LABEL_10:
  v3 = _malloc((v2 + 7) >> 3);
  dword_10066928 = v3;
  if ( v3 )
  {
    dword_1006691C = v3;
    dword_10066920 = (dword_1006692C + 7) >> 3;
    Bitmap::Clear((Bitmap *)&dword_1006691C, dword_10066924, 8 * dword_10066920, (struct Err *)v6);
    Bitmap::Set((Bitmap *)&dword_1006691C, 0, dword_1006692C, (struct Err *)v6);
    dword_10066934 = 0;
    dword_1006693C = 0;
    dword_10066938 = 0;
    if ( (dword_100668E4 & 8) == 0 )
      goto LABEL_24;
    Err::operator=(&dword_100668E4);
  }
  else if ( Sys < 8 )
  {
    if ( (Sys & 0xFFFFFFFE) != 0 )
    {
      if ( *(&Sys + 3) )
        operator delete[](*(&Sys + 3));
      if ( ::Block )
        operator delete[](::Block);
    }
    Sys = _xmm;
    ::Block = 0;
  }
  if ( dword_10066928 )
    _free(dword_10066928);
  if ( lpAddress )
    VirtualFree(lpAddress, 0, 0x8000u);
LABEL_24:
  if ( (v6[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v8 )
      operator delete[](v8);
  }
  return &Sys;
}

```

## disassembly

```asm
0x1004e3a0  mov     edi, edi
0x1004e3a2  push    ebp
0x1004e3a3  mov     ebp, esp
0x1004e3a5  push    0FFFFFFFFh
0x1004e3a7  push    offset ??0System@@QAE@XZ_SEH
0x1004e3ac  mov     eax, large fs:0
0x1004e3b2  push    eax
0x1004e3b3  sub     esp, 60h
0x1004e3b6  mov     eax, ___security_cookie
0x1004e3bb  xor     eax, ebp
0x1004e3bd  mov     [ebp+var_10], eax
0x1004e3c0  push    eax
0x1004e3c1  lea     eax, [ebp+var_C]
0x1004e3c4  mov     large fs:0, eax
0x1004e3ca  mov     eax, [ebp+var_34]
0x1004e3cd  mov     [ebp+var_34], eax
0x1004e3d0  mov     [ebp+var_34], offset ?Sys@@3VSystem@@A; System Sys
0x1004e3d7  mov     dword ptr ?Sys@@3VSystem@@A, 1; System Sys
0x1004e3e1  push    offset stru_100668BC; lpCriticalSection
0x1004e3e6  mov     [ebp+var_4], 0
0x1004e3ed  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1004e3f3  push    0; lpName
0x1004e3f5  push    0; bInitialState
0x1004e3f7  push    0; bManualReset
0x1004e3f9  push    0; lpEventAttributes
0x1004e3fb  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x1004e401  mov     hEvent, eax
0x1004e406  test    eax, eax
0x1004e408  jnz     short loc_1004E414
0x1004e40a  push    offset dword_100668E4
0x1004e40f  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004e414  mov     dword_100668DC, 0
0x1004e41e  mov     dword_100668E0, 0
0x1004e428  mov     dword_100668D8, 0
0x1004e432  mov     dword_100668E4, 1
0x1004e43c  push    offset stru_100668F8; lpCriticalSection
0x1004e441  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1004e447  mov     dword_1006691C, 0
0x1004e451  mov     dword_10066920, 0
0x1004e45b  mov     dword_10066924, 0
0x1004e465  mov     dword_10066948, 0
0x1004e46f  mov     dword_1006694C, 0
0x1004e479  mov     dword_10066944, 0
0x1004e483  push    offset stru_10066950; lpCriticalSection
0x1004e488  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1004e48e  mov     dword_10066974, 0
0x1004e498  mov     [ebp+var_48], 1
0x1004e49f  mov     byte ptr [ebp+var_4], 5
0x1004e4a3  lea     eax, [ebp+Buffer]
0x1004e4a6  push    eax; lpBuffer
0x1004e4a7  mov     dword_10066928, 0
0x1004e4b1  mov     lpAddress, 0
0x1004e4bb  mov     dword_10066968, 0
0x1004e4c5  mov     dword_1006696C, 0
0x1004e4cf  mov     dword_10066970, 0
0x1004e4d9  mov     dword_10066940, 0
0x1004e4e3  mov     dword_100668B4, 3
0x1004e4ed  mov     dword_100668B8, 0
0x1004e4f7  mov     [ebp+Buffer.dwLength], 20h ; ' '
0x1004e4fe  call    ds:__imp__GlobalMemoryStatus@4; GlobalMemoryStatus(x)
0x1004e504  lea     eax, [ebp+SystemInfo]
0x1004e507  push    eax; lpSystemInfo
0x1004e508  call    ds:__imp__GetSystemInfo@4; GetSystemInfo(x)
0x1004e50e  mov     edx, [ebp+SystemInfo.dwPageSize]
0x1004e511  xor     ecx, ecx
0x1004e513  mov     dword_10066914, ecx
0x1004e519  cmp     edx, 1
0x1004e51c  jz      short loc_1004E532
0x1004e51e  mov     edi, edi
0x1004e520  inc     ecx
0x1004e521  mov     eax, 1
0x1004e526  shl     eax, cl
0x1004e528  mov     dword_10066914, ecx
0x1004e52e  cmp     eax, edx
0x1004e530  jnz     short loc_1004E520
0x1004e532  mov     eax, [ebp+Buffer.dwTotalPhys]
0x1004e535  cmp     eax, 4000000h
0x1004e53a  jbe     short loc_1004E54D
0x1004e53c  mov     dword_1006692C, 8000h
0x1004e546  mov     ecx, 8000h
0x1004e54b  jmp     short loc_1004E584
0x1004e54d  mov     ecx, eax
0x1004e54f  mov     dword_10066930, 100h
0x1004e559  shr     ecx, 0Bh
0x1004e55c  mov     dword_1006692C, ecx
0x1004e562  mov     edx, ecx
0x1004e564  cmp     eax, 0C00000h
0x1004e569  jbe     short loc_1004E58E
0x1004e56b  add     eax, 0FF400000h
0x1004e570  shr     eax, 0Dh
0x1004e573  add     eax, 100h
0x1004e578  mov     dword_10066930, eax
0x1004e57d  cmp     eax, 1B00h
0x1004e582  jbe     short loc_1004E58E
0x1004e584  mov     dword_10066930, 1B00h
0x1004e58e  lea     eax, [ecx+7]
0x1004e591  shr     eax, 3
0x1004e594  push    eax; Size
0x1004e595  call    ds:__imp__malloc
0x1004e59b  mov     ecx, eax
0x1004e59d  add     esp, 4
0x1004e5a0  mov     dword_10066928, ecx
0x1004e5a6  test    ecx, ecx
0x1004e5a8  jnz     short loc_1004E5FD
0x1004e5aa  mov     eax, dword ptr ?Sys@@3VSystem@@A; System Sys
0x1004e5af  cmp     eax, 8
0x1004e5b2  jge     loc_1004E677
0x1004e5b8  test    eax, 0FFFFFFFEh
0x1004e5bd  jz      short loc_1004E5E3
0x1004e5bf  mov     eax, dword ptr ?Sys@@3VSystem@@A+0Ch; System Sys
0x1004e5c4  test    eax, eax
0x1004e5c6  jz      short loc_1004E5D1
0x1004e5c8  push    eax; Block
0x1004e5c9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e5ce  add     esp, 4
0x1004e5d1  mov     eax, Block
0x1004e5d6  test    eax, eax
0x1004e5d8  jz      short loc_1004E5E3
0x1004e5da  push    eax; Block
0x1004e5db  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e5e0  add     esp, 4
0x1004e5e3  movaps  xmm0, ds:__xmm@0000000000000000fffffc0d00000008
0x1004e5ea  movaps  ?Sys@@3VSystem@@A, xmm0; System Sys
0x1004e5f1  mov     Block, 0
0x1004e5fb  jmp     short loc_1004E677
0x1004e5fd  mov     eax, dword_1006692C
0x1004e602  mov     edx, dword_10066924; unsigned int
0x1004e608  add     eax, 7
0x1004e60b  shr     eax, 3
0x1004e60e  mov     dword_1006691C, ecx
0x1004e614  lea     ecx, [ebp+var_48]
0x1004e617  mov     dword_10066920, eax
0x1004e61c  push    ecx; struct Err *
0x1004e61d  shl     eax, 3
0x1004e620  mov     ecx, offset dword_1006691C; this
0x1004e625  push    eax; unsigned int
0x1004e626  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x1004e62b  lea     eax, [ebp+var_48]
0x1004e62e  xor     edx, edx; unsigned int
0x1004e630  push    eax; struct Err *
0x1004e631  push    dword_1006692C; unsigned int
0x1004e637  mov     ecx, offset dword_1006691C; this
0x1004e63c  call    ?Set@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Set(ulong,ulong,Err &)
0x1004e641  test    byte ptr dword_100668E4, 8
0x1004e648  mov     dword_10066934, 0
0x1004e652  mov     dword_1006693C, 0
0x1004e65c  mov     dword_10066938, 0
0x1004e666  jz      short loc_1004E6A1
0x1004e668  push    offset dword_100668E4
0x1004e66d  mov     ecx, offset ?Sys@@3VSystem@@A; System Sys
0x1004e672  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1004e677  mov     eax, dword_10066928
0x1004e67c  test    eax, eax
0x1004e67e  jz      short loc_1004E68A
0x1004e680  push    eax; Block
0x1004e681  call    ds:__imp__free
0x1004e687  add     esp, 4
0x1004e68a  mov     eax, lpAddress
0x1004e68f  test    eax, eax
0x1004e691  jz      short loc_1004E6A1
0x1004e693  push    8000h; dwFreeType
0x1004e698  push    0; dwSize
0x1004e69a  push    eax; lpAddress
0x1004e69b  call    ds:__imp__VirtualFree@12; VirtualFree(x,x,x)
0x1004e6a1  test    [ebp+var_48], 0FFFFFFFEh
0x1004e6a8  jz      short loc_1004E6CA
0x1004e6aa  mov     eax, [ebp+Block]
0x1004e6ad  test    eax, eax
0x1004e6af  jz      short loc_1004E6BA
0x1004e6b1  push    eax; Block
0x1004e6b2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e6b7  add     esp, 4
0x1004e6ba  mov     ecx, [ebp+var_38]
0x1004e6bd  test    ecx, ecx
0x1004e6bf  jz      short loc_1004E6CA
0x1004e6c1  push    ecx; Block
0x1004e6c2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e6c7  add     esp, 4
0x1004e6ca  mov     eax, offset ?Sys@@3VSystem@@A; System Sys
0x1004e6cf  mov     ecx, [ebp+var_C]
0x1004e6d2  mov     large fs:0, ecx
0x1004e6d9  pop     ecx
0x1004e6da  mov     ecx, [ebp+var_10]
0x1004e6dd  xor     ecx, ebp; StackCookie
0x1004e6df  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e6e4  mov     esp, ebp
0x1004e6e6  pop     ebp
0x1004e6e7  retn
0x10061790  mov     ecx, [ebp+var_34]; this
0x10061793  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061798  mov     ecx, [ebp+var_34]
0x1006179b  add     ecx, 1Ch; lpCriticalSection
0x1006179e  jmp     ??1Queue@@QAE@XZ; Queue::~Queue(void)
0x100617a3  mov     ecx, [ebp+var_34]
0x100617a6  add     ecx, 58h ; 'X'; lpCriticalSection
0x100617a9  jmp     ??1CriticalSection@@QAE@XZ; CriticalSection::~CriticalSection(void)
0x100617ae  mov     ecx, [ebp+var_34]
0x100617b1  add     ecx, 0A4h; this
0x100617b7  jmp     ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100617bc  mov     ecx, [ebp+var_34]
0x100617bf  add     ecx, 0B0h; lpCriticalSection
0x100617c5  jmp     ??1CriticalSection@@QAE@XZ; CriticalSection::~CriticalSection(void)
0x100617ca  lea     ecx, [ebp+var_48]; this
0x100617cd  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100617d7  nop
0x100617d8  nop
0x100617d9  mov     edx, [esp-4+arg_4]
0x100617dd  lea     eax, [edx+0Ch]
0x100617e0  mov     ecx, [edx-64h]
0x100617e3  xor     ecx, eax; StackCookie
0x100617e5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100617ea  mov     ecx, [edx-4]
0x100617ed  xor     ecx, eax; StackCookie
0x100617ef  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100617f4  mov     eax, offset stru_100640FC
0x100617f9  jmp     ___CxxFrameHandler3
```
