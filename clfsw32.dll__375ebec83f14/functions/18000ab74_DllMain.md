# DllMain

- ea: `0x18000ab74`
- end: `0x18000aeae`
- name: `DllMain`
- size: `826`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001584`

## callees

- `0x18000ab74`
- `0x180014e00`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x18000ae6c`
- `ntdll!EtwUnregisterTraceGuids` at `0x18000ae6c`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000ac4c`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000ac4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000addf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000addf`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000ad9c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000adc3`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000ad9c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000adc3`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000adf9`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000ae13`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000adf9`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000ae13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000abc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000abc1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ad84`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ad84`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000ae42`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000ae42`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000aca4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000aca4`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000acc9`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000acc9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // edi
  __int64 *v5; // rbx
  __int64 *v6; // rsi
  __int64 v7; // r8
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  int v10; // edx
  int i; // r8d
  int v12; // edx
  char v13; // r8
  int v14; // r10d
  int j; // r8d
  __int64 v16; // rax
  bool v18; // zf
  REGHANDLE v19; // rcx
  _QWORD *v20; // rbx
  GUID ProviderId; // [rsp+40h] [rbp-268h] BYREF
  CHAR Filename[528]; // [rsp+50h] [rbp-258h] BYREF

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      if ( !GetModuleFileNameA(hinstDLL, Filename, 0x104u) )
        goto LABEL_27;
      qword_18001DED0 = 0;
      v5 = &WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ClfsLog;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v6 = &WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18001DED8 = 1;
      do
      {
        v7 = *v6;
        *(_QWORD *)&ProviderId.Data1 = v7;
        ++v6;
        *(_QWORD *)ProviderId.Data4 = 0;
        v5[4] = v7;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, GUID *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v5,
          v7,
          1,
          &ProviderId,
          0,
          0,
          v5 + 1);
        v5 = (__int64 *)*v5;
      }
      while ( v5 );
      ProviderId = *(GUID *)&(*off_18001D020)[-16];
      if ( RegHandle )
        __fastfail(5u);
      xmmword_18001D040 = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18001D018, &RegHandle) )
        EventSetInformation(RegHandle, 2, (char *)off_18001D020, *(unsigned __int16 *)off_18001D020);
      if ( !CCrc32::m_fInitialized )
      {
        v8 = 0;
        CCrc32::m_ulPolynomial = 79764919;
        do
        {
          v9 = v8;
          v10 = 0;
          for ( i = 1; i != 9; ++i )
          {
            if ( (v9 & 1) != 0 )
              v10 |= 1 << (8 - i);
            v9 >>= 1;
          }
          v12 = v10 << 24;
          v13 = 8;
          do
          {
            v12 = (2 * v12) ^ (v12 >> 31) & 0x4C11DB7;
            --v13;
          }
          while ( v13 );
          v14 = 0;
          for ( j = 1; j != 33; ++j )
          {
            if ( (v12 & 1) != 0 )
              v14 |= 1 << (32 - j);
            v12 = (unsigned int)v12 >> 1;
          }
          v16 = v8++;
          *((_DWORD *)&CCrc32::m_rgCrcTable + v16) = v14;
        }
        while ( v8 < 0x100 );
        CCrc32::m_fInitialized = 1;
      }
      DisableThreadLibraryCalls(hinstDLL);
      g_hHeap = HeapCreate(0, 0x4000u, 0);
      if ( !g_hHeap )
        return 0;
      g_hMarshalHeap = HeapCreate(0, 0x4000u, 0);
      if ( !g_hMarshalHeap )
      {
LABEL_27:
        GetLastError();
        return 0;
      }
    }
  }
  else
  {
    if ( g_hHeap )
      v4 = HeapDestroy(g_hHeap);
    if ( g_hMarshalHeap )
    {
      if ( !HeapDestroy(g_hMarshalHeap) || (v18 = !v4, v4 = 1, v18) )
        v4 = 0;
    }
    v19 = RegHandle;
    dword_18001D018 = 0;
    RegHandle = 0;
    EventUnregister(v19);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v20 )
      {
        if ( v20[1] )
        {
          EtwUnregisterTraceGuids();
          v20[1] = 0;
        }
        v20 = (_QWORD *)*v20;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000ab74  push    rbx
0x18000ab76  push    rbp
0x18000ab77  push    rsi
0x18000ab78  push    rdi
0x18000ab79  push    r14
0x18000ab7b  push    r15
0x18000ab7d  sub     rsp, 278h
0x18000ab84  mov     rax, cs:__security_cookie
0x18000ab8b  xor     rax, rsp
0x18000ab8e  mov     [rsp+2A8h+var_48], rax
0x18000ab96  xor     r14d, r14d
0x18000ab99  mov     r15d, 1
0x18000ab9f  mov     rbp, rcx
0x18000aba2  mov     edi, r15d
0x18000aba5  test    edx, edx
0x18000aba7  jz      loc_18000ADED
0x18000abad  cmp     edx, r15d
0x18000abb0  jnz     loc_18000AE8B
0x18000abb6  mov     r8d, 104h; nSize
0x18000abbc  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x18000abc1  call    cs:__imp_GetModuleFileNameA
0x18000abc8  nop     dword ptr [rax+rax+00h]
0x18000abcd  test    eax, eax
0x18000abcf  jz      loc_18000ADDF
0x18000abd5  lea     rax, WPP_ThisDir_CTLGUID_ClfsLog
0x18000abdc  mov     cs:qword_18001DED0, r14
0x18000abe3  lea     rbx, WPP_MAIN_CB
0x18000abea  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000abf1  mov     cs:WPP_GLOBAL_Control, rbx
0x18000abf8  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000abff  mov     cs:WPP_MAIN_CB, r14
0x18000ac06  mov     cs:qword_18001DED8, rdi
0x18000ac0d  mov     r8, [rsi]
0x18000ac10  lea     rax, [rbx+8]
0x18000ac14  mov     [rsp+2A8h+var_270], rax
0x18000ac19  lea     rcx, WppControlCallback
0x18000ac20  mov     [rsp+2A8h+var_278], r14
0x18000ac25  lea     rax, [rsp+2A8h+ProviderId]
0x18000ac2a  mov     qword ptr [rsp+2A8h+ProviderId.Data1], r8
0x18000ac2f  lea     rsi, [rsi+8]
0x18000ac33  mov     qword ptr [rsp+2A8h+ProviderId.Data4], r14
0x18000ac38  mov     r9d, r15d
0x18000ac3b  mov     [rsp+2A8h+var_280], r14
0x18000ac40  mov     rdx, rbx
0x18000ac43  mov     [rsp+2A8h+var_288], rax
0x18000ac48  mov     [rbx+20h], r8
0x18000ac4c  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000ac53  nop     dword ptr [rax+rax+00h]
0x18000ac58  mov     rbx, [rbx]
0x18000ac5b  test    rbx, rbx
0x18000ac5e  jnz     short loc_18000AC0D
0x18000ac60  cmp     cs:RegHandle, r14
0x18000ac67  mov     rax, cs:off_18001D020
0x18000ac6e  movups  xmm0, xmmword ptr [rax-10h]
0x18000ac72  movdqu  xmmword ptr [rsp+2A8h+ProviderId.Data1], xmm0
0x18000ac78  jz      short loc_18000AC7F
0x18000ac7a  lea     ecx, [rbx+5]
0x18000ac7d  int     29h; Win8: RtlFailFast(ecx)
0x18000ac7f  xorps   xmm0, xmm0
0x18000ac82  lea     r9, RegHandle; RegHandle
0x18000ac89  lea     r8, dword_18001D018; CallbackContext
0x18000ac90  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ac97  lea     rcx, [rsp+2A8h+ProviderId]; ProviderId
0x18000ac9c  movdqu  cs:xmmword_18001D040, xmm0
0x18000aca4  call    cs:__imp_EventRegister
0x18000acab  nop     dword ptr [rax+rax+00h]
0x18000acb0  test    eax, eax
0x18000acb2  jnz     short loc_18000ACD5
0x18000acb4  mov     r8, cs:off_18001D020
0x18000acbb  lea     edx, [rax+2]
0x18000acbe  mov     rcx, cs:RegHandle
0x18000acc5  movzx   r9d, word ptr [r8]
0x18000acc9  call    cs:__imp_EventSetInformation
0x18000acd0  nop     dword ptr [rax+rax+00h]
0x18000acd5  cmp     cs:?m_fInitialized@CCrc32@@0_NA, r14b; bool CCrc32::m_fInitialized
0x18000acdc  jnz     loc_18000AD81
0x18000ace2  mov     r11d, 4C11DB7h
0x18000ace8  mov     r9d, r14d
0x18000aceb  mov     cs:?m_ulPolynomial@CCrc32@@0KA, r11d; ulong CCrc32::m_ulPolynomial
0x18000acf2  mov     r10d, r9d
0x18000acf5  mov     edx, r14d
0x18000acf8  mov     r8d, r15d
0x18000acfb  test    r15b, r10b
0x18000acfe  jz      short loc_18000AD0F
0x18000ad00  mov     ecx, 8
0x18000ad05  mov     eax, r15d
0x18000ad08  sub     ecx, r8d
0x18000ad0b  shl     eax, cl
0x18000ad0d  or      edx, eax
0x18000ad0f  shr     r10d, 1
0x18000ad12  add     r8d, r15d
0x18000ad15  cmp     r8d, 9
0x18000ad19  jnz     short loc_18000ACFB
0x18000ad1b  shl     edx, 18h
0x18000ad1e  mov     r8b, 8
0x18000ad21  mov     ecx, edx
0x18000ad23  lea     eax, [rdx+rdx]
0x18000ad26  sar     ecx, 1Fh
0x18000ad29  and     ecx, r11d
0x18000ad2c  mov     edx, ecx
0x18000ad2e  xor     edx, eax
0x18000ad30  add     r8b, 0FFh
0x18000ad34  jnz     short loc_18000AD21
0x18000ad36  mov     r10d, r14d
0x18000ad39  mov     r8d, r15d
0x18000ad3c  test    r15b, dl
0x18000ad3f  jz      short loc_18000AD51
0x18000ad41  mov     ecx, 20h ; ' '
0x18000ad46  mov     eax, r15d
0x18000ad49  sub     ecx, r8d
0x18000ad4c  shl     eax, cl
0x18000ad4e  or      r10d, eax
0x18000ad51  shr     edx, 1
0x18000ad53  add     r8d, r15d
0x18000ad56  cmp     r8d, 21h ; '!'
0x18000ad5a  jnz     short loc_18000AD3C
0x18000ad5c  mov     eax, r9d
0x18000ad5f  lea     rcx, ?m_rgCrcTable@CCrc32@@0PAKA; ulong near * CCrc32::m_rgCrcTable
0x18000ad66  add     r9d, r15d
0x18000ad69  mov     [rcx+rax*4], r10d
0x18000ad6d  cmp     r9d, 100h
0x18000ad74  jb      loc_18000ACF2
0x18000ad7a  mov     cs:?m_fInitialized@CCrc32@@0_NA, r15b; bool CCrc32::m_fInitialized
0x18000ad81  mov     rcx, rbp; hLibModule
0x18000ad84  call    cs:__imp_DisableThreadLibraryCalls
0x18000ad8b  nop     dword ptr [rax+rax+00h]
0x18000ad90  mov     ebx, 4000h
0x18000ad95  xor     r8d, r8d; dwMaximumSize
0x18000ad98  mov     edx, ebx; dwInitialSize
0x18000ad9a  xor     ecx, ecx; flOptions
0x18000ad9c  call    cs:__imp_HeapCreate
0x18000ada3  nop     dword ptr [rax+rax+00h]
0x18000ada8  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x18000adaf  test    rax, rax
0x18000adb2  jnz     short loc_18000ADBB
0x18000adb4  xor     eax, eax
0x18000adb6  jmp     loc_18000AE8D
0x18000adbb  xor     r8d, r8d; dwMaximumSize
0x18000adbe  mov     rdx, rbx; dwInitialSize
0x18000adc1  xor     ecx, ecx; flOptions
0x18000adc3  call    cs:__imp_HeapCreate
0x18000adca  nop     dword ptr [rax+rax+00h]
0x18000adcf  mov     cs:?g_hMarshalHeap@@3PEAXEA, rax; void * g_hMarshalHeap
0x18000add6  test    rax, rax
0x18000add9  jnz     loc_18000AE8B
0x18000addf  call    cs:__imp_GetLastError
0x18000ade6  nop     dword ptr [rax+rax+00h]
0x18000adeb  jmp     short loc_18000ADB4
0x18000aded  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18000adf4  test    rcx, rcx
0x18000adf7  jz      short loc_18000AE07
0x18000adf9  call    cs:__imp_HeapDestroy
0x18000ae00  nop     dword ptr [rax+rax+00h]
0x18000ae05  mov     edi, eax
0x18000ae07  mov     rcx, cs:?g_hMarshalHeap@@3PEAXEA; hHeap
0x18000ae0e  test    rcx, rcx
0x18000ae11  jz      short loc_18000AE2D
0x18000ae13  call    cs:__imp_HeapDestroy
0x18000ae1a  nop     dword ptr [rax+rax+00h]
0x18000ae1f  test    eax, eax
0x18000ae21  jz      short loc_18000AE2A
0x18000ae23  test    edi, edi
0x18000ae25  mov     edi, r15d
0x18000ae28  jnz     short loc_18000AE2D
0x18000ae2a  mov     edi, r14d
0x18000ae2d  mov     rcx, cs:RegHandle; RegHandle
0x18000ae34  mov     cs:dword_18001D018, r14d
0x18000ae3b  mov     cs:RegHandle, r14
0x18000ae42  call    cs:__imp_EventUnregister
0x18000ae49  nop     dword ptr [rax+rax+00h]
0x18000ae4e  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ae55  lea     rsi, WPP_GLOBAL_Control
0x18000ae5c  cmp     rbx, rsi
0x18000ae5f  jz      short loc_18000AE8B
0x18000ae61  jmp     short loc_18000AE7F
0x18000ae63  mov     rcx, [rbx+8]
0x18000ae67  test    rcx, rcx
0x18000ae6a  jz      short loc_18000AE7C
0x18000ae6c  call    cs:__imp_EtwUnregisterTraceGuids
0x18000ae73  nop     dword ptr [rax+rax+00h]
0x18000ae78  mov     [rbx+8], r14
0x18000ae7c  mov     rbx, [rbx]
0x18000ae7f  test    rbx, rbx
0x18000ae82  jnz     short loc_18000AE63
0x18000ae84  mov     cs:WPP_GLOBAL_Control, rsi
0x18000ae8b  mov     eax, edi
0x18000ae8d  mov     rcx, [rsp+2A8h+var_48]
0x18000ae95  xor     rcx, rsp; StackCookie
0x18000ae98  call    __security_check_cookie
0x18000ae9d  add     rsp, 278h
0x18000aea4  pop     r15
0x18000aea6  pop     r14
0x18000aea8  pop     rdi
0x18000aea9  pop     rsi
0x18000aeaa  pop     rbp
0x18000aeab  pop     rbx
0x18000aeac  retn
```
