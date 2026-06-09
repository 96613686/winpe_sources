# CRemoteAssistanceApp::CRemoteAssistanceApp(void)

- ea: `0x14000b99c`
- end: `0x14000bdd0`
- name: `??0CRemoteAssistanceApp@@QEAA@XZ`
- size: `1076`
- prototype: `CRemoteAssistanceApp *__fastcall(CRemoteAssistanceApp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400194c8`

## callees

- `0x140001cc4`
- `0x14000b99c`
- `0x1400114bc`
- `0x1400192b8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000bc72`
- `KERNEL32!InitializeCriticalSection` at `0x14000bc72`
- `KERNEL32!CreateEventW` at `0x14000bbb7`
- `KERNEL32!CreateEventW` at `0x14000bc5f`
- `KERNEL32!CreateEventW` at `0x14000bd44`
- `KERNEL32!CreateEventW` at `0x14000bbb7`
- `KERNEL32!CreateEventW` at `0x14000bc5f`
- `KERNEL32!CreateEventW` at `0x14000bd44`
- `USERENV!GetProfileType` at `0x14000bda3`
- `USERENV!GetProfileType` at `0x14000bda3`

## pseudocode

```c
CRemoteAssistanceApp *__fastcall CRemoteAssistanceApp::CRemoteAssistanceApp(CRemoteAssistanceApp *this)
{
  char *v2; // rcx
  _QWORD *v3; // rax
  DWORD dwFlags; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 24;
  ATL::_pAtlModule = this;
  *(_OWORD *)v2 = 0;
  *((_OWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 8) = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v2) >= 0 )
    *((_DWORD *)this + 2) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  *(_QWORD *)this = &CRemoteAssistanceApp::`vftable';
  *((_QWORD *)this + 9) = &CExpInterDlg::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 22) = 0;
  AtlAxWinInit();
  *((_WORD *)this + 68) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 25) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 1;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 59) = 1;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 34) = &CNovInterDlg::`vftable';
  *((_QWORD *)this + 40) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 102) = 0;
  *((_QWORD *)this + 50) = 0;
  *(_QWORD *)((char *)this + 436) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 103) = 1;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_DWORD *)this + 108) = 0;
  *((_DWORD *)this + 111) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 116) = 35;
  *((_DWORD *)this + 117) = 1;
  *((_QWORD *)this + 64) = (char *)this + 504;
  *((_QWORD *)this + 63) = (char *)this + 504;
  *((_DWORD *)this + 124) = 0;
  *(_QWORD *)((char *)this + 524) = 17;
  *((_DWORD *)this + 134) = 5;
  *((_DWORD *)this + 133) = 0;
  *(_QWORD *)((char *)this + 540) = 0;
  *((_DWORD *)this + 130) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_DWORD *)this + 137) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 72) = (char *)this + 568;
  *((_QWORD *)this + 71) = (char *)this + 568;
  *((_QWORD *)this + 73) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_OWORD *)this + 44) = 0;
  *((_DWORD *)this + 180) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_DWORD *)this + 186) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 1;
  *((_DWORD *)this + 196) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_DWORD *)this + 262) = 0;
  *((_QWORD *)this + 132) = CreateEventW(0, 1, 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1008));
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 110) = 0;
  *((_DWORD *)this + 222) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_DWORD *)this + 250) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_DWORD *)this + 228) = 14;
  *((_QWORD *)this + 115) = 0;
  *((_QWORD *)this + 116) = 0;
  *((_DWORD *)this + 200) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_DWORD *)this + 238) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 106) = CreateEventW(0, 1, 1, 0);
  v3 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
  {
    *(_DWORD *)v3 = 0;
    v3[1] = 0;
    v3[2] = 0;
    v3[3] = 0;
    *((_DWORD *)v3 + 8) = 0;
    *((_DWORD *)v3 + 9) = 1;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 61) = v3;
  *((_DWORD *)this + 251) = 0;
  *((_QWORD *)this + 105) = 0;
  dwFlags = 0;
  if ( GetProfileType(&dwFlags) && (dwFlags & 5) == 4 )
    *((_DWORD *)this + 211) = 1;
  return this;
}

```

## disassembly

```asm
0x14000b99c  push    rbx
0x14000b99e  push    rbp
0x14000b99f  push    rsi
0x14000b9a0  push    rdi
0x14000b9a1  sub     rsp, 28h
0x14000b9a5  mov     rdi, rcx
0x14000b9a8  xorps   xmm0, xmm0
0x14000b9ab  add     rcx, 18h; this
0x14000b9af  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x14000b9b6  xor     esi, esi
0x14000b9b8  xor     eax, eax
0x14000b9ba  movups  xmmword ptr [rcx], xmm0
0x14000b9bd  movups  xmmword ptr [rcx+10h], xmm0
0x14000b9c1  mov     [rcx+20h], rax
0x14000b9c5  mov     [rdi+8], rsi
0x14000b9c9  mov     [rdi+10h], rsi
0x14000b9cd  mov     [rdi+40h], rsi
0x14000b9d1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000b9d6  lea     ebp, [rsi+1]
0x14000b9d9  test    eax, eax
0x14000b9db  jns     short loc_14000B9E6
0x14000b9dd  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, bpl; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000b9e4  jmp     short loc_14000B9ED
0x14000b9e6  mov     dword ptr [rdi+8], 38h ; '8'
0x14000b9ed  lea     rax, ??_7CRemoteAssistanceApp@@6B@; const CRemoteAssistanceApp::`vftable'
0x14000b9f4  mov     [rdi], rax
0x14000b9f7  lea     rax, ??_7CExpInterDlg@@6B@; const CExpInterDlg::`vftable'
0x14000b9fe  mov     [rdi+48h], rax
0x14000ba02  mov     [rdi+50h], rsi
0x14000ba06  mov     [rdi+70h], rsi
0x14000ba0a  mov     [rdi+78h], rsi
0x14000ba0e  mov     [rdi+80h], esi
0x14000ba14  mov     [rdi+0B0h], rsi
0x14000ba1b  call    AtlAxWinInit
0x14000ba20  mov     [rdi+88h], si
0x14000ba27  lea     rax, ??_7CNovInterDlg@@6B@; const CNovInterDlg::`vftable'
0x14000ba2e  mov     [rdi+90h], rsi
0x14000ba35  lea     rbx, [rdi+238h]
0x14000ba3c  mov     [rdi+98h], rsi
0x14000ba43  xorps   xmm0, xmm0
0x14000ba46  mov     [rdi+0A8h], rsi
0x14000ba4d  xor     r9d, r9d; lpName
0x14000ba50  mov     [rdi+0C0h], rsi
0x14000ba57  xor     r8d, r8d; bInitialState
0x14000ba5a  mov     [rdi+0D8h], esi
0x14000ba60  mov     edx, ebp; bManualReset
0x14000ba62  mov     [rdi+0F0h], rsi
0x14000ba69  xor     ecx, ecx; lpEventAttributes
0x14000ba6b  mov     [rdi+0C8h], rsi
0x14000ba72  movups  xmmword ptr [rdi+0F8h], xmm0
0x14000ba79  mov     [rdi+0A0h], rsi
0x14000ba80  mov     [rdi+0B8h], rsi
0x14000ba87  mov     [rdi+0E0h], rsi
0x14000ba8e  mov     [rdi+0E8h], ebp
0x14000ba94  mov     [rdi+108h], rsi
0x14000ba9b  mov     [rdi+0B0h], rsi
0x14000baa2  mov     [rdi+0ECh], ebp
0x14000baa8  mov     [rdi+118h], rsi
0x14000baaf  mov     [rdi+138h], rsi
0x14000bab6  mov     [rdi+110h], rax
0x14000babd  xor     eax, eax
0x14000babf  mov     [rdi+140h], rsi
0x14000bac6  mov     [rdi+148h], esi
0x14000bacc  mov     [rdi+168h], rsi
0x14000bad3  mov     [rdi+198h], esi
0x14000bad9  mov     [rdi+190h], rsi
0x14000bae0  mov     [rdi+1B4h], rsi
0x14000bae7  mov     [rdi+1D8h], rsi
0x14000baee  mov     [rdi+188h], rsi
0x14000baf5  mov     [rdi+160h], rsi
0x14000bafc  mov     [rdi+170h], rsi
0x14000bb03  mov     [rdi+150h], rsi
0x14000bb0a  mov     [rdi+178h], rsi
0x14000bb11  mov     [rdi+180h], rsi
0x14000bb18  mov     [rdi+19Ch], ebp
0x14000bb1e  mov     [rdi+1A0h], rsi
0x14000bb25  mov     [rdi+1A8h], rsi
0x14000bb2c  mov     [rdi+1B0h], eax
0x14000bb32  lea     rax, [rdi+1F8h]
0x14000bb39  mov     [rdi+1BCh], esi
0x14000bb3f  mov     [rdi+1C0h], rsi
0x14000bb46  mov     [rdi+1C8h], rsi
0x14000bb4d  mov     [rdi+1E0h], rsi
0x14000bb54  mov     dword ptr [rdi+1D0h], 23h ; '#'
0x14000bb5e  mov     [rdi+1D4h], ebp
0x14000bb64  mov     [rdi+200h], rax
0x14000bb6b  mov     [rax], rax
0x14000bb6e  mov     [rdi+1F0h], esi
0x14000bb74  mov     qword ptr [rdi+20Ch], 11h
0x14000bb7f  mov     dword ptr [rdi+218h], 5
0x14000bb89  mov     [rdi+214h], esi
0x14000bb8f  mov     [rdi+21Ch], rsi
0x14000bb96  mov     [rdi+208h], esi
0x14000bb9c  mov     [rdi+228h], rsi
0x14000bba3  mov     [rdi+224h], esi
0x14000bba9  mov     [rdi+230h], rsi
0x14000bbb0  mov     [rbx+8], rbx
0x14000bbb4  mov     [rbx], rbx
0x14000bbb7  call    cs:__imp_CreateEventW
0x14000bbbe  nop     dword ptr [rax+rax+00h]
0x14000bbc3  mov     [rbx+10h], rax
0x14000bbc7  mov     [rbx+18h], rsi
0x14000bbcb  mov     [rdi+288h], rsi
0x14000bbd2  mov     [rdi+290h], rsi
0x14000bbd9  mov     [rdi+298h], rsi
0x14000bbe0  mov     [rdi+2A0h], rsi
0x14000bbe7  mov     [rdi+2A8h], rsi
0x14000bbee  lea     rbx, [rdi+3F0h]
0x14000bbf5  mov     [rdi+2B0h], rsi
0x14000bbfc  xorps   xmm0, xmm0
0x14000bbff  mov     [rdi+2B8h], rsi
0x14000bc06  xor     eax, eax
0x14000bc08  movups  xmmword ptr [rdi+2C0h], xmm0
0x14000bc0f  mov     [rdi+2D0h], eax
0x14000bc15  xor     r9d, r9d; lpName
0x14000bc18  mov     [rdi+2D8h], rsi
0x14000bc1f  xor     r8d, r8d; bInitialState
0x14000bc22  mov     [rdi+2E0h], rsi
0x14000bc29  mov     edx, ebp; bManualReset
0x14000bc2b  mov     [rdi+2E8h], esi
0x14000bc31  xor     ecx, ecx; lpEventAttributes
0x14000bc33  mov     [rdi+2F0h], rsi
0x14000bc3a  mov     [rdi+2F8h], rbp
0x14000bc41  mov     [rdi+310h], esi
0x14000bc47  mov     [rdi+308h], rsi
0x14000bc4e  mov     [rdi+300h], rsi
0x14000bc55  mov     [rdi+318h], rsi
0x14000bc5c  mov     [rbx+28h], esi
0x14000bc5f  call    cs:__imp_CreateEventW
0x14000bc66  nop     dword ptr [rax+rax+00h]
0x14000bc6b  mov     rcx, rbx; lpCriticalSection
0x14000bc6e  mov     [rbx+30h], rax
0x14000bc72  call    cs:__imp_InitializeCriticalSection
0x14000bc79  nop     dword ptr [rax+rax+00h]
0x14000bc7e  xor     r9d, r9d; lpName
0x14000bc81  mov     [rdi+3D0h], rsi
0x14000bc88  mov     r8d, ebp; bInitialState
0x14000bc8b  mov     [rdi+340h], rsi
0x14000bc92  mov     edx, ebp; bManualReset
0x14000bc94  mov     [rdi+368h], rsi
0x14000bc9b  xor     ecx, ecx; lpEventAttributes
0x14000bc9d  mov     [rdi+370h], rsi
0x14000bca4  mov     [rdi+378h], esi
0x14000bcaa  mov     [rdi+3D8h], rsi
0x14000bcb1  mov     [rdi+3E0h], rsi
0x14000bcb8  mov     [rdi+3E8h], esi
0x14000bcbe  mov     [rdi+330h], rsi
0x14000bcc5  mov     [rdi+358h], rsi
0x14000bccc  mov     [rdi+360h], rsi
0x14000bcd3  mov     [rdi+268h], rsi
0x14000bcda  mov     [rdi+270h], rsi
0x14000bce1  mov     dword ptr [rdi+390h], 0Eh
0x14000bceb  mov     [rdi+398h], rsi
0x14000bcf2  mov     [rdi+3A0h], rsi
0x14000bcf9  mov     [rdi+320h], esi
0x14000bcff  mov     [rdi+3A8h], rsi
0x14000bd06  mov     [rdi+3B0h], rsi
0x14000bd0d  mov     [rdi+3B8h], esi
0x14000bd13  mov     [rdi+380h], rsi
0x14000bd1a  mov     [rdi+388h], rsi
0x14000bd21  mov     [rdi+328h], rsi
0x14000bd28  mov     [rdi+278h], rsi
0x14000bd2f  mov     [rdi+3C0h], rsi
0x14000bd36  mov     [rdi+3C8h], rsi
0x14000bd3d  mov     [rdi+280h], rsi
0x14000bd44  call    cs:__imp_CreateEventW
0x14000bd4b  nop     dword ptr [rax+rax+00h]
0x14000bd50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bd57  mov     ecx, 30h ; '0'; unsigned __int64
0x14000bd5c  mov     [rdi+350h], rax
0x14000bd63  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000bd68  test    rax, rax
0x14000bd6b  jz      short loc_14000BD83
0x14000bd6d  mov     [rax], esi
0x14000bd6f  mov     [rax+8], rsi
0x14000bd73  mov     [rax+10h], rsi
0x14000bd77  mov     [rax+18h], rsi
0x14000bd7b  mov     [rax+20h], esi
0x14000bd7e  mov     [rax+24h], ebp
0x14000bd81  jmp     short loc_14000BD86
0x14000bd83  mov     rax, rsi
0x14000bd86  lea     rcx, [rsp+48h+dwFlags]; dwFlags
0x14000bd8b  mov     [rdi+1E8h], rax
0x14000bd92  mov     [rdi+3ECh], esi
0x14000bd98  mov     [rdi+348h], rsi
0x14000bd9f  mov     [rsp+48h+dwFlags], esi
0x14000bda3  call    cs:__imp_GetProfileType
0x14000bdaa  nop     dword ptr [rax+rax+00h]
0x14000bdaf  test    eax, eax
0x14000bdb1  jz      short loc_14000BDC3
0x14000bdb3  mov     eax, [rsp+48h+dwFlags]
0x14000bdb7  and     al, 5
0x14000bdb9  cmp     al, 4
0x14000bdbb  jnz     short loc_14000BDC3
0x14000bdbd  mov     [rdi+34Ch], ebp
0x14000bdc3  mov     rax, rdi
0x14000bdc6  add     rsp, 28h
0x14000bdca  pop     rdi
0x14000bdcb  pop     rsi
0x14000bdcc  pop     rbp
0x14000bdcd  pop     rbx
0x14000bdce  retn
```
