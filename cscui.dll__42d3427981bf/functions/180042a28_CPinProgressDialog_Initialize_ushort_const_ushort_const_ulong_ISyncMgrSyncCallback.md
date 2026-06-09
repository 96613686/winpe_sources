# CPinProgressDialog::_Initialize(ushort const *,ushort const * *,ulong,ISyncMgrSyncCallback *)

- ea: `0x180042a28`
- end: `0x180042c4a`
- name: `?_Initialize@CPinProgressDialog@@AEAAJPEBGPEAPEBGKPEAUISyncMgrSyncCallback@@@Z`
- size: `546`
- prototype: `int(CPinProgressDialog *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int, struct ISyncMgrSyncCallback *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800419e0`

## callees

- `0x180006430`
- `0x180006500`
- `0x180008a7c`
- `0x18000c1e8`
- `0x18001101c`
- `0x1800321b8`
- `0x180042a28`
- `0x180047eb0`
- `0x18004c636`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042ae9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042ae9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b43`

## pseudocode

```c
__int64 __fastcall CPinProgressDialog::_Initialize(
        CPinProgressDialog *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        struct IUnknown *a5)
{
  bool v9; // cf
  HANDLE EventW; // rax
  int StringCopy; // ebx
  HANDLE v12; // rax
  HANDLE v13; // rax
  volatile signed __int32 *v14; // rax
  volatile signed __int32 *v15; // rdi

  memset_0((char *)this + 80, 0, 0xA0u);
  *(_QWORD *)((char *)this + 84) = *((_QWORD *)this + 3);
  *(_QWORD *)((char *)this + 92) = g_hInstance;
  v9 = *((_DWORD *)this + 8) != 0;
  *((_DWORD *)this + 20) = 160;
  *((_DWORD *)this + 25) = 7177;
  *(_QWORD *)((char *)this + 212) = L"    ";
  *((_DWORD *)this + 59) = 250;
  *(_QWORD *)((char *)this + 124) = 4452LL - v9;
  *((_DWORD *)this + 26) = 40;
  *((_DWORD *)this + 38) = 2;
  *(_QWORD *)((char *)this + 108) = 4450;
  *(_QWORD *)((char *)this + 116) = 1210;
  *(_QWORD *)((char *)this + 132) = 4453;
  *(_QWORD *)((char *)this + 220) = CPinProgressDialog::_ProgressCallbackProc;
  *(_QWORD *)((char *)this + 228) = this;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 30) = EventW;
  if ( EventW || (StringCopy = ResultFromKnownLastError(), StringCopy >= 0) )
  {
    v12 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 31) = v12;
    if ( v12 || (StringCopy = ResultFromKnownLastError(), StringCopy >= 0) )
    {
      v13 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 32) = v13;
      if ( v13 || (StringCopy = ResultFromKnownLastError(), StringCopy >= 0) )
      {
        StringCopy = CscUtil_CreateStringCopy(a2, (unsigned __int16 **)this + 8);
        if ( StringCopy >= 0 )
        {
          *((_QWORD *)this + 34) = 0;
          v14 = (volatile signed __int32 *)operator new(0x20u);
          v15 = v14;
          if ( v14 )
          {
            *((_DWORD *)v14 + 2) = 1;
            *((_QWORD *)v14 + 2) = 0;
            *(_QWORD *)v14 = &CStringSet::`vftable';
            *((_QWORD *)v14 + 3) = 0;
            StringCopy = CStringSet::_Initialize((CStringSet *)v14, a3, a4);
            if ( StringCopy >= 0 )
            {
              *((_QWORD *)this + 34) = v15;
              _InterlockedIncrement(v15 + 2);
            }
            CRefCounted::ReleaseReference((CRefCounted *)v15);
            if ( StringCopy >= 0 )
            {
              StringCopy = MarshalToGIT(a5, &GUID_884ccd87_b139_4937_a4ba_4f8e19513fbe, (unsigned int *)this + 70);
              if ( StringCopy < 0
                && WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
                  (unsigned int)StringCopy);
              }
            }
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
    }
  }
  return (unsigned int)StringCopy;
}

```

## disassembly

```asm
0x180042a28  push    rbx
0x180042a2a  push    rbp
0x180042a2b  push    rsi
0x180042a2c  push    rdi
0x180042a2d  push    r14
0x180042a2f  sub     rsp, 20h
0x180042a33  mov     r14, r8
0x180042a36  mov     rdi, rdx
0x180042a39  mov     rsi, rcx
0x180042a3c  xor     edx, edx; Val
0x180042a3e  mov     r8d, 0A0h; Size
0x180042a44  add     rcx, 50h ; 'P'; void *
0x180042a48  mov     ebp, r9d
0x180042a4b  call    memset_0
0x180042a50  mov     rax, [rsi+18h]
0x180042a54  mov     [rsi+54h], rax
0x180042a58  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180042a5f  mov     [rsi+5Ch], rax
0x180042a63  mov     eax, [rsi+20h]
0x180042a66  neg     eax
0x180042a68  mov     dword ptr [rsi+50h], 0A0h
0x180042a6f  lea     rax, asc_180055438; "    "
0x180042a76  mov     dword ptr [rsi+64h], 1C09h
0x180042a7d  sbb     rcx, rcx
0x180042a80  mov     [rsi+0D4h], rax
0x180042a87  add     rcx, 1164h
0x180042a8e  mov     dword ptr [rsi+0ECh], 0FAh
0x180042a98  xor     r9d, r9d; lpName
0x180042a9b  mov     [rsi+7Ch], rcx
0x180042a9f  lea     rax, ?_ProgressCallbackProc@CPinProgressDialog@@CAJPEAUHWND__@@I_K_J2@Z; CPinProgressDialog::_ProgressCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180042aa6  mov     dword ptr [rsi+68h], 28h ; '('
0x180042aad  xor     r8d, r8d; bInitialState
0x180042ab0  mov     dword ptr [rsi+98h], 2
0x180042aba  xor     ecx, ecx; lpEventAttributes
0x180042abc  mov     qword ptr [rsi+6Ch], 1162h
0x180042ac4  lea     edx, [r9+1]; bManualReset
0x180042ac8  mov     qword ptr [rsi+74h], 4BAh
0x180042ad0  mov     qword ptr [rsi+84h], 1165h
0x180042adb  mov     [rsi+0DCh], rax
0x180042ae2  mov     [rsi+0E4h], rsi
0x180042ae9  call    cs:__imp_CreateEventW
0x180042aef  mov     [rsi+0F0h], rax
0x180042af6  test    rax, rax
0x180042af9  jnz     short loc_180042B0A
0x180042afb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180042b00  mov     ebx, eax
0x180042b02  test    eax, eax
0x180042b04  js      loc_180042C3D
0x180042b0a  xor     r9d, r9d; lpName
0x180042b0d  xor     r8d, r8d; bInitialState
0x180042b10  xor     ecx, ecx; lpEventAttributes
0x180042b12  lea     edx, [r9+1]; bManualReset
0x180042b16  call    cs:__imp_CreateEventW
0x180042b1c  mov     [rsi+0F8h], rax
0x180042b23  test    rax, rax
0x180042b26  jnz     short loc_180042B37
0x180042b28  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180042b2d  mov     ebx, eax
0x180042b2f  test    eax, eax
0x180042b31  js      loc_180042C3D
0x180042b37  xor     r9d, r9d; lpName
0x180042b3a  xor     r8d, r8d; bInitialState
0x180042b3d  xor     ecx, ecx; lpEventAttributes
0x180042b3f  lea     edx, [r9+1]; bManualReset
0x180042b43  call    cs:__imp_CreateEventW
0x180042b49  mov     [rsi+100h], rax
0x180042b50  test    rax, rax
0x180042b53  jnz     short loc_180042B64
0x180042b55  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180042b5a  mov     ebx, eax
0x180042b5c  test    eax, eax
0x180042b5e  js      loc_180042C3D
0x180042b64  lea     rdx, [rsi+40h]; unsigned __int16 **
0x180042b68  mov     rcx, rdi; unsigned __int16 *
0x180042b6b  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x180042b70  mov     ebx, eax
0x180042b72  test    eax, eax
0x180042b74  js      loc_180042C3D
0x180042b7a  mov     ecx, 20h ; ' '; Size
0x180042b7f  mov     qword ptr [rsi+110h], 0
0x180042b8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042b8f  mov     rdi, rax
0x180042b92  test    rax, rax
0x180042b95  jz      loc_180042C38
0x180042b9b  mov     dword ptr [rax+8], 1
0x180042ba2  mov     r8d, ebp; unsigned int
0x180042ba5  lea     rax, ??_7CStringSet@@6B@; const CStringSet::`vftable'
0x180042bac  mov     qword ptr [rdi+10h], 0
0x180042bb4  mov     rdx, r14; unsigned __int16 **
0x180042bb7  mov     [rdi], rax
0x180042bba  mov     rcx, rdi; this
0x180042bbd  mov     qword ptr [rdi+18h], 0
0x180042bc5  call    ?_Initialize@CStringSet@@AEAAJPEAPEBGK@Z; CStringSet::_Initialize(ushort const * *,ulong)
0x180042bca  mov     ebx, eax
0x180042bcc  test    eax, eax
0x180042bce  js      short loc_180042BDB
0x180042bd0  mov     [rsi+110h], rdi
0x180042bd7  lock inc dword ptr [rdi+8]
0x180042bdb  mov     rcx, rdi; this
0x180042bde  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180042be3  test    ebx, ebx
0x180042be5  js      short loc_180042C3D
0x180042be7  mov     rcx, [rsp+48h+arg_20]; struct IUnknown *
0x180042bec  lea     r8, [rsi+118h]; unsigned int *
0x180042bf3  lea     rdx, _GUID_884ccd87_b139_4937_a4ba_4f8e19513fbe; struct _GUID *
0x180042bfa  call    ?MarshalToGIT@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; MarshalToGIT(IUnknown *,_GUID const &,ulong *)
0x180042bff  mov     ebx, eax
0x180042c01  test    eax, eax
0x180042c03  jns     short loc_180042C3D
0x180042c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c0c  lea     rax, WPP_GLOBAL_Control
0x180042c13  cmp     rcx, rax
0x180042c16  jz      short loc_180042C3D
0x180042c18  test    byte ptr [rcx+1Ch], 2
0x180042c1c  jz      short loc_180042C3D
0x180042c1e  mov     rcx, [rcx+10h]
0x180042c22  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042c29  mov     edx, 11h
0x180042c2e  mov     r9d, ebx
0x180042c31  call    WPP_SF_d
0x180042c36  jmp     short loc_180042C3D
0x180042c38  mov     ebx, 8007000Eh
0x180042c3d  mov     eax, ebx
0x180042c3f  add     rsp, 20h
0x180042c43  pop     r14
0x180042c45  pop     rdi
0x180042c46  pop     rsi
0x180042c47  pop     rbp
0x180042c48  pop     rbx
0x180042c49  retn
```
