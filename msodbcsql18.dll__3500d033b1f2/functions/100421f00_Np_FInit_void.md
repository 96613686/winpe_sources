# Np::FInit(void)

- ea: `0x100421f00`
- end: `0x100422068`
- name: `?FInit@Np@@EEAAKXZ`
- size: `360`
- prototype: `unsigned int __fastcall(Np *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100421f00`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b1d0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x100421fab`
- `KERNEL32!CreateEventW` at `0x100421fab`
- `KERNEL32!GetLastError` at `0x100421fba`
- `KERNEL32!GetLastError` at `0x100421fba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::FInit(Np *this)
{
  DWORD LastError; // ebx
  unsigned __int64 EventW; // rax
  __int64 v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E79D0[0] )
    bidScopeEnterW(&v5, off_1005E79D0[0], *((unsigned int *)this + 11));
  LastError = SNI::detail::Transport::Initialize(this);
  if ( !LastError )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4C98[0] )
      bidTraceW(0, 72704, off_1005E4C98[0], 0);
    if ( g_osviSNI.dwMajorVersion < 6 )
    {
      EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 14) = EventW;
      if ( EventW )
      {
        *((_QWORD *)this + 14) = EventW | 1;
      }
      else
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 && off_1005E4CA0[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(0, 84992, off_1005E4CA0[0], 1);
        }
        SNISetLastError(1, LastError, 50100);
      }
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4CA8[0] )
    bidTraceW(0, 124928, off_1005E4CA8[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v5);
  return LastError;
}

```

## disassembly

```asm
0x100421f00  mov     r11, rsp
0x100421f03  push    rdi
0x100421f04  sub     rsp, 40h
0x100421f08  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100421f10  mov     [r11+8], rbx
0x100421f14  mov     [r11+18h], rsi
0x100421f18  mov     rdi, rcx
0x100421f1b  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x100421f20  mov     eax, cs:_bidGblFlags
0x100421f26  mov     ecx, 20004h
0x100421f2b  and     eax, ecx
0x100421f2d  cmp     eax, ecx
0x100421f2f  jnz     short loc_100421F51
0x100421f31  mov     rax, cs:off_1005E79D0; "<Np::FInit|API|SNI> %u#\n"
0x100421f38  test    rax, rax
0x100421f3b  jz      short loc_100421F51
0x100421f3d  mov     r8d, [rdi+2Ch]
0x100421f41  mov     rdx, cs:off_1005E79D0; "<Np::FInit|API|SNI> %u#\n"
0x100421f48  lea     rcx, [r11+10h]
0x100421f4c  call    _bidScopeEnterW
0x100421f51  mov     rcx, rdi; this
0x100421f54  call    ?Initialize@Transport@detail@SNI@@QEAAKXZ; SNI::detail::Transport::Initialize(void)
0x100421f59  mov     ebx, eax
0x100421f5b  mov     esi, 20002h
0x100421f60  test    eax, eax
0x100421f62  jnz     loc_10042201D
0x100421f68  mov     ecx, cs:_bidGblFlags
0x100421f6e  and     ecx, esi
0x100421f70  cmp     ecx, esi
0x100421f72  jnz     short loc_100421F96
0x100421f74  mov     rcx, cs:off_1005E4C98; "<Np::FInit|RET|SNI> %d{WINERR}\n"
0x100421f7b  test    rcx, rcx
0x100421f7e  jz      short loc_100421F96
0x100421f80  xor     r9d, r9d
0x100421f83  mov     r8, cs:off_1005E4C98; "<Np::FInit|RET|SNI> %d{WINERR}\n"
0x100421f8a  mov     edx, 11C00h
0x100421f8f  xor     ecx, ecx
0x100421f91  call    _bidTraceW
0x100421f96  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x100421f9d  jnb     short loc_10042201D
0x100421f9f  xor     r9d, r9d; lpName
0x100421fa2  xor     r8d, r8d; bInitialState
0x100421fa5  lea     edx, [r9+1]; bManualReset
0x100421fa9  xor     ecx, ecx; lpEventAttributes
0x100421fab  call    cs:__imp_CreateEventW
0x100421fb1  mov     [rdi+70h], rax
0x100421fb5  test    rax, rax
0x100421fb8  jnz     short loc_100422015
0x100421fba  call    cs:__imp_GetLastError
0x100421fc0  mov     ebx, eax
0x100421fc2  mov     edi, 0C3B4h
0x100421fc7  test    byte ptr cs:_bidGblFlags, 2
0x100421fce  jz      short loc_100422004
0x100421fd0  mov     rax, cs:off_1005E4CA0; "<Np::FInit|ERR|SNI> ProviderNum: %d{Pro"...
0x100421fd7  test    rax, rax
0x100421fda  jz      short loc_100422004
0x100421fdc  mov     ecx, edi; unsigned int
0x100421fde  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100421fe3  mov     [rsp+48h+var_20], ebx
0x100421fe7  mov     [rsp+48h+var_28], eax
0x100421feb  mov     r9d, 1
0x100421ff1  mov     r8, cs:off_1005E4CA0; "<Np::FInit|ERR|SNI> ProviderNum: %d{Pro"...
0x100421ff8  mov     edx, 14C00h
0x100421ffd  xor     ecx, ecx
0x100421fff  call    _bidTraceW
0x100422004  mov     r8d, edi
0x100422007  mov     edx, ebx
0x100422009  mov     ecx, 1
0x10042200e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422013  jmp     short loc_10042201D
0x100422015  or      rax, 1
0x100422019  mov     [rdi+70h], rax
0x10042201d  mov     eax, cs:_bidGblFlags
0x100422023  and     eax, esi
0x100422025  cmp     eax, esi
0x100422027  jnz     short loc_10042204C
0x100422029  mov     rax, cs:off_1005E4CA8; "<Np::FInit|RET|SNI> %d{WINERR}\n"
0x100422030  test    rax, rax
0x100422033  jz      short loc_10042204C
0x100422035  mov     r9d, ebx
0x100422038  mov     r8, cs:off_1005E4CA8; "<Np::FInit|RET|SNI> %d{WINERR}\n"
0x10042203f  mov     edx, 1E800h
0x100422044  xor     ecx, ecx
0x100422046  call    _bidTraceW
0x10042204b  nop
0x10042204c  lea     rcx, [rsp+48h+arg_8]; this
0x100422051  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100422056  mov     eax, ebx
0x100422058  mov     rbx, [rsp+48h+arg_0]
0x10042205d  mov     rsi, [rsp+48h+arg_10]
0x100422062  add     rsp, 40h
0x100422066  pop     rdi
0x100422067  retn
```
