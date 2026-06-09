# Np::ReadSync(SNI_Packet * *,int)

- ea: `0x100423420`
- end: `0x100423990`
- name: `?ReadSync@Np@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `1392`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x10041806c`
- `0x10041847c`
- `0x100423420`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b2b4`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1004235f6`
- `KERNEL32!GetOverlappedResult` at `0x100423733`
- `KERNEL32!GetOverlappedResult` at `0x1004235f6`
- `KERNEL32!GetOverlappedResult` at `0x100423733`
- `KERNEL32!WaitForSingleObject` at `0x1004235c0`
- `KERNEL32!WaitForSingleObject` at `0x1004235c0`
- `KERNEL32!GetLastError` at `0x100423515`
- `KERNEL32!GetLastError` at `0x100423604`
- `KERNEL32!GetLastError` at `0x100423741`
- `KERNEL32!GetLastError` at `0x100423515`
- `KERNEL32!GetLastError` at `0x100423604`
- `KERNEL32!GetLastError` at `0x100423741`
- `KERNEL32!GetTickCount` at `0x1004235b1`
- `KERNEL32!GetTickCount` at `0x100423636`
- `KERNEL32!GetTickCount` at `0x1004235b1`
- `KERNEL32!GetTickCount` at `0x100423636`
- `KERNEL32!ReadFile` at `0x100423501`
- `KERNEL32!ReadFile` at `0x100423501`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::ReadSync(Np *this, struct SNI_Packet **a2, signed int a3)
{
  DWORD v6; // ebx
  __int64 lpOverlapped; // rsi
  HANDLE *v8; // r13
  void *v9; // rdx
  DWORD v10; // r8d
  DWORD LastError; // ebp
  char v12; // al
  unsigned int v13; // edi
  wchar_t *v14; // r8
  __int64 v15; // rdx
  DWORD TickCount; // r15d
  DWORD v17; // eax
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+8h] BYREF
  HANDLE *v20; // [rsp+88h] [rbp+10h]
  __int64 v21; // [rsp+98h] [rbp+20h] BYREF

  v21 = -1;
  v6 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7A00[0] )
    bidScopeEnterW(&v21, off_1005E7A00[0], *((unsigned int *)this + 11));
  lpOverlapped = (__int64)*a2;
  NumberOfBytesTransferred = 0;
  *a2 = 0;
  v8 = (HANDLE *)((char *)this + 64);
  v20 = (HANDLE *)((char *)this + 64);
  while ( 1 )
  {
    if ( *((_QWORD *)this + 10) )
    {
      if ( lpOverlapped )
        SNIPacketRelease((SNI_Packet *)lpOverlapped);
      lpOverlapped = *((_QWORD *)this + 10);
      *((_QWORD *)this + 10) = 0;
    }
    else
    {
      if ( !lpOverlapped )
      {
        lpOverlapped = SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0, 0);
        v20 = (HANDLE *)((char *)this + 64);
        if ( !lpOverlapped )
        {
          LastError = 14;
          v13 = 50100;
          if ( (bidGblFlags & 2) != 0 && off_1005E4D68[0] )
          {
            SniErrorIdFromStringId(0xC3B4u);
            v14 = off_1005E4D68[0];
            v15 = 496640;
            goto LABEL_60;
          }
          goto LABEL_61;
        }
      }
      SNI::detail::Transport::PrepareForSyncCall(this, (struct SNI_Packet *)lpOverlapped);
      v9 = (void *)(*(_QWORD *)(lpOverlapped + 80) + *(unsigned int *)(lpOverlapped + 96));
      v10 = *(_DWORD *)(lpOverlapped + 92);
      NumberOfBytesTransferred = 0;
      *(_QWORD *)(lpOverlapped + 16) = 0;
      if ( ReadFile(*v8, v9, v10, 0, (LPOVERLAPPED)lpOverlapped) )
        goto LABEL_37;
      LastError = GetLastError();
      if ( LastError != 997 )
      {
        v12 = bidGblFlags;
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1005E4D70[0] )
            bidTraceW(0, 528384, off_1005E4D70[0], LastError);
          v12 = bidGblFlags;
        }
        if ( LastError != 234 )
        {
          v13 = 50100;
          if ( (v12 & 2) != 0 && off_1005E4D78[0] )
          {
            SniErrorIdFromStringId(0xC3B4u);
            v14 = off_1005E4D78[0];
            v15 = 535552;
            goto LABEL_60;
          }
          goto LABEL_61;
        }
        if ( (v12 & 2) != 0 && off_1005E4D80[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
            bidID,
            0,
            548864,
            off_1005E4D80[0],
            0);
LABEL_37:
        if ( !GetOverlappedResult(*v20, (LPOVERLAPPED)lpOverlapped, &NumberOfBytesTransferred, 1) )
        {
          LastError = GetLastError();
          if ( LastError != 234 )
          {
            v13 = 50100;
            if ( (bidGblFlags & 2) != 0 && off_1005E4D88[0] )
            {
              SniErrorIdFromStringId(0xC3B4u);
              v14 = off_1005E4D88[0];
              v15 = 558080;
              goto LABEL_60;
            }
            goto LABEL_61;
          }
        }
        goto LABEL_46;
      }
    }
    TickCount = GetTickCount();
    v17 = WaitForSingleObject(*(HANDLE *)(lpOverlapped + 24), a3);
    LastError = v17;
    if ( v17 == -1 )
    {
      v13 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_1005E4D90[0] )
        goto LABEL_61;
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_1005E4D90[0];
      v15 = 588800;
LABEL_60:
      bidTraceW(0, v15, v14, *((unsigned int *)this + 18));
      goto LABEL_61;
    }
    if ( v17 == 258 )
    {
      *((_QWORD *)this + 10) = lpOverlapped;
      v13 = 50111;
      if ( (bidGblFlags & 2) == 0 || !off_1005E4D98[0] )
        goto LABEL_61;
      SniErrorIdFromStringId(0xC3BFu);
      v14 = off_1005E4D98[0];
      v15 = 595968;
      goto LABEL_60;
    }
    v20 = (HANDLE *)((char *)this + 64);
    if ( GetOverlappedResult(*v8, (LPOVERLAPPED)lpOverlapped, &NumberOfBytesTransferred, 0) )
      goto LABEL_46;
    LastError = GetLastError();
    if ( LastError != 995 )
      break;
    SNIPacketRelease((SNI_Packet *)lpOverlapped);
    *((_QWORD *)this + 10) = 0;
    lpOverlapped = 0;
    NumberOfBytesTransferred = 0;
    if ( a3 != -1 )
    {
      a3 += TickCount - GetTickCount();
      if ( a3 <= 0 )
      {
        LastError = 258;
        v13 = 50111;
        if ( (bidGblFlags & 2) != 0 && off_1005E4DA0[0] )
        {
          SniErrorIdFromStringId(0xC3BFu);
          v14 = off_1005E4DA0[0];
          v15 = 622592;
          goto LABEL_60;
        }
        goto LABEL_61;
      }
    }
  }
  if ( LastError != 234 )
  {
    v13 = 50100;
    if ( (bidGblFlags & 2) != 0 && off_1005E4DA8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_1005E4DA8[0];
      v15 = 632832;
      goto LABEL_60;
    }
LABEL_61:
    SNISetLastError(*((unsigned int *)this + 18), LastError, v13);
    if ( LastError != 258 && lpOverlapped )
    {
      SNIPacketRelease((SNI_Packet *)lpOverlapped);
      *((_QWORD *)this + 10) = 0;
    }
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4DC0[0] )
      bidTraceW(0, 667648, off_1005E4DC0[0], LastError);
    v6 = LastError;
    goto LABEL_68;
  }
LABEL_46:
  *(_DWORD *)(lpOverlapped + 88) = NumberOfBytesTransferred;
  *a2 = (struct SNI_Packet *)lpOverlapped;
  if ( (bidGblFlags & 0x24002) == 0x24002 && off_1005E4DB0[0] )
    bidTraceW(0, 649216, off_1005E4DB0[0], NumberOfBytesTransferred);
  if ( (bidGblFlags & 0x24002) == 0x24002 )
    bidWriteBin(
      bidID,
      16,
      *(_QWORD *)(lpOverlapped + 80) + *(unsigned int *)(lpOverlapped + 96),
      NumberOfBytesTransferred,
      0);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4DB8[0] )
    bidTraceW(0, 652288, off_1005E4DB8[0], 0);
LABEL_68:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v21);
  return v6;
}

```

## disassembly

```asm
0x100423420  mov     r11, rsp
0x100423423  push    rbp
0x100423424  push    rsi
0x100423425  push    rdi
0x100423426  push    r12
0x100423428  push    r13
0x10042342a  push    r14
0x10042342c  push    r15
0x10042342e  sub     rsp, 40h
0x100423432  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x10042343a  mov     [r11+18h], rbx
0x10042343e  mov     edi, r8d
0x100423441  mov     r12, rdx
0x100423444  mov     r14, rcx
0x100423447  or      qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x10042344c  mov     eax, cs:_bidGblFlags
0x100423452  mov     ecx, 20004h
0x100423457  and     eax, ecx
0x100423459  xor     ebx, ebx
0x10042345b  cmp     eax, ecx
0x10042345d  jnz     short loc_100423486
0x10042345f  mov     rax, cs:off_1005E7A00; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x100423466  test    rax, rax
0x100423469  jz      short loc_100423486
0x10042346b  mov     [r11-58h], r8d
0x10042346f  mov     r9, rdx
0x100423472  mov     r8d, [r14+2Ch]
0x100423476  mov     rdx, cs:off_1005E7A00; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x10042347d  lea     rcx, [r11+20h]
0x100423481  call    _bidScopeEnterW
0x100423486  mov     rsi, [r12]
0x10042348a  mov     [rsp+78h+NumberOfBytesTransferred], ebx
0x100423491  mov     [r12], rbx
0x100423495  lea     r13, [r14+40h]
0x100423499  mov     [rsp+78h+arg_8], r13
0x1004234a1  mov     r15, r13
0x1004234a4  cmp     [r14+50h], rbx
0x1004234a8  jnz     loc_10042359C
0x1004234ae  test    rsi, rsi
0x1004234b1  jnz     short loc_1004234D5
0x1004234b3  xor     r8d, r8d
0x1004234b6  xor     edx, edx
0x1004234b8  mov     rcx, [r14+20h]
0x1004234bc  call    SNIPacketAllocateEx2
0x1004234c1  mov     rsi, rax
0x1004234c4  mov     [rsp+78h+arg_8], r13
0x1004234cc  test    rax, rax
0x1004234cf  jz      loc_100423692
0x1004234d5  mov     rdx, rsi; struct SNI_Packet *
0x1004234d8  mov     rcx, r14; this
0x1004234db  call    ?PrepareForSyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForSyncCall(SNI_Packet *)
0x1004234e0  mov     edx, [rsi+60h]
0x1004234e3  add     rdx, [rsi+50h]; lpBuffer
0x1004234e7  mov     r8d, [rsi+5Ch]; nNumberOfBytesToRead
0x1004234eb  mov     [rsp+78h+NumberOfBytesTransferred], ebx
0x1004234f2  mov     [rsi+10h], rbx
0x1004234f6  mov     [rsp+78h+lpOverlapped], rsi; lpOverlapped
0x1004234fb  xor     r9d, r9d; lpNumberOfBytesRead
0x1004234fe  mov     rcx, [r15]; hFile
0x100423501  call    cs:__imp_ReadFile
0x100423507  mov     r15d, 0EAh
0x10042350d  test    eax, eax
0x10042350f  jnz     loc_100423717
0x100423515  call    cs:__imp_GetLastError
0x10042351b  mov     ebp, eax
0x10042351d  cmp     eax, 3E5h
0x100423522  jz      loc_1004235B1
0x100423528  mov     eax, cs:_bidGblFlags
0x10042352e  test    al, 2
0x100423530  jz      short loc_10042355A
0x100423532  mov     rax, cs:off_1005E4D70; "<Np::ReadSync|ERR|SNI> ReadFile: %d{WIN"...
0x100423539  test    rax, rax
0x10042353c  jz      short loc_100423554
0x10042353e  mov     r9d, ebp
0x100423541  mov     r8, cs:off_1005E4D70; "<Np::ReadSync|ERR|SNI> ReadFile: %d{WIN"...
0x100423548  mov     edx, 81000h
0x10042354d  xor     ecx, ecx
0x10042354f  call    _bidTraceW
0x100423554  mov     eax, cs:_bidGblFlags
0x10042355a  cmp     ebp, r15d
0x10042355d  jz      loc_1004236D5
0x100423563  mov     edi, 0C3B4h
0x100423568  test    al, 2
0x10042356a  jz      loc_10042390D
0x100423570  mov     rax, cs:off_1005E4D78; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x100423577  test    rax, rax
0x10042357a  jz      loc_10042390D
0x100423580  mov     ecx, edi; unsigned int
0x100423582  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100423587  mov     [rsp+78h+var_50], ebp
0x10042358b  mov     r8, cs:off_1005E4D78; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x100423592  mov     edx, 82C00h
0x100423597  jmp     loc_1004238FE
0x10042359c  test    rsi, rsi
0x10042359f  jz      short loc_1004235A9
0x1004235a1  mov     rcx, rsi; this
0x1004235a4  call    SNIPacketRelease
0x1004235a9  mov     rsi, [r14+50h]
0x1004235ad  mov     [r14+50h], rbx
0x1004235b1  call    cs:__imp_GetTickCount
0x1004235b7  mov     r15d, eax
0x1004235ba  mov     edx, edi; dwMilliseconds
0x1004235bc  mov     rcx, [rsi+18h]; hHandle
0x1004235c0  call    cs:__imp_WaitForSingleObject
0x1004235c6  mov     ebp, eax
0x1004235c8  cmp     eax, 0FFFFFFFFh
0x1004235cb  jz      loc_1004238CC
0x1004235d1  cmp     eax, 102h
0x1004235d6  jz      loc_100423891
0x1004235dc  mov     [rsp+78h+arg_8], r13
0x1004235e4  xor     r9d, r9d; bWait
0x1004235e7  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1004235ef  mov     rdx, rsi; lpOverlapped
0x1004235f2  mov     rcx, [r13+0]; hFile
0x1004235f6  call    cs:__imp_GetOverlappedResult
0x1004235fc  test    eax, eax
0x1004235fe  jnz     loc_1004237D9
0x100423604  call    cs:__imp_GetLastError
0x10042360a  mov     ebp, eax
0x10042360c  cmp     eax, 3E3h
0x100423611  jnz     loc_100423790
0x100423617  mov     rcx, rsi; this
0x10042361a  call    SNIPacketRelease
0x10042361f  mov     [r14+50h], rbx
0x100423623  mov     rsi, rbx
0x100423626  mov     [rsp+78h+NumberOfBytesTransferred], ebx
0x10042362d  cmp     edi, 0FFFFFFFFh
0x100423630  jz      loc_1004234A1
0x100423636  call    cs:__imp_GetTickCount
0x10042363c  sub     r15d, eax
0x10042363f  add     edi, r15d
0x100423642  test    edi, edi
0x100423644  jg      loc_1004234A1
0x10042364a  mov     r15d, 102h
0x100423650  mov     ebp, r15d
0x100423653  mov     edi, 0C3BFh
0x100423658  test    byte ptr cs:_bidGblFlags, 2
0x10042365f  jz      loc_10042390D
0x100423665  mov     rax, cs:off_1005E4DA0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x10042366c  test    rax, rax
0x10042366f  jz      loc_10042390D
0x100423675  mov     ecx, edi; unsigned int
0x100423677  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042367c  mov     [rsp+78h+var_50], r15d
0x100423681  mov     r8, cs:off_1005E4DA0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x100423688  mov     edx, 98000h
0x10042368d  jmp     loc_1004238FE
0x100423692  mov     ebp, 0Eh
0x100423697  mov     edi, 0C3B4h
0x10042369c  test    byte ptr cs:_bidGblFlags, 2
0x1004236a3  jz      loc_10042390D
0x1004236a9  mov     rax, cs:off_1005E4D68; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004236b0  test    rax, rax
0x1004236b3  jz      loc_10042390D
0x1004236b9  mov     ecx, edi; unsigned int
0x1004236bb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004236c0  mov     [rsp+78h+var_50], ebp
0x1004236c4  mov     r8, cs:off_1005E4D68; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004236cb  mov     edx, 79400h
0x1004236d0  jmp     loc_1004238FE
0x1004236d5  test    al, 2
0x1004236d7  jz      short loc_100423717
0x1004236d9  mov     rax, cs:off_1005E4D80; "<Np::ReadSync|ERR|SNI> ReadFile returne"...
0x1004236e0  test    rax, rax
0x1004236e3  jz      short loc_100423717
0x1004236e5  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004236ed  jz      short loc_100423717
0x1004236ef  mov     rax, cs:off_1005D39E0
0x1004236f6  mov     [rsp+78h+lpOverlapped], rbx
0x1004236fb  mov     r9, cs:off_1005E4D80; "<Np::ReadSync|ERR|SNI> ReadFile returne"...
0x100423702  xor     edx, edx
0x100423704  mov     r8d, 86000h
0x10042370a  mov     rcx, cs:_bidID
0x100423711  call    cs:__guard_dispatch_icall_fptr
0x100423717  mov     r9d, 1; bWait
0x10042371d  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x100423725  mov     rdx, rsi; lpOverlapped
0x100423728  mov     rcx, [rsp+78h+arg_8]
0x100423730  mov     rcx, [rcx]; hFile
0x100423733  call    cs:__imp_GetOverlappedResult
0x100423739  test    eax, eax
0x10042373b  jnz     loc_1004237D9
0x100423741  call    cs:__imp_GetLastError
0x100423747  mov     ebp, eax
0x100423749  cmp     eax, r15d
0x10042374c  jz      loc_1004237D9
0x100423752  mov     edi, 0C3B4h
0x100423757  test    byte ptr cs:_bidGblFlags, 2
0x10042375e  jz      loc_10042390D
0x100423764  mov     rax, cs:off_1005E4D88; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x10042376b  test    rax, rax
0x10042376e  jz      loc_10042390D
0x100423774  mov     ecx, edi; unsigned int
0x100423776  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042377b  mov     [rsp+78h+var_50], ebp
0x10042377f  mov     r8, cs:off_1005E4D88; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x100423786  mov     edx, 88400h
0x10042378b  jmp     loc_1004238FE
0x100423790  mov     r15d, 0EAh
0x100423796  cmp     ebp, r15d
0x100423799  jz      short loc_1004237D9
0x10042379b  mov     edi, 0C3B4h
0x1004237a0  test    byte ptr cs:_bidGblFlags, 2
0x1004237a7  jz      loc_10042390D
0x1004237ad  mov     rax, cs:off_1005E4DA8; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004237b4  test    rax, rax
0x1004237b7  jz      loc_10042390D
0x1004237bd  mov     ecx, edi; unsigned int
0x1004237bf  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004237c4  mov     [rsp+78h+var_50], ebp
0x1004237c8  mov     r8, cs:off_1005E4DA8; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004237cf  mov     edx, 9A800h
0x1004237d4  jmp     loc_1004238FE
0x1004237d9  mov     eax, [rsp+78h+NumberOfBytesTransferred]
0x1004237e0  mov     [rsi+58h], eax
0x1004237e3  mov     [r12], rsi
0x1004237e7  mov     eax, cs:_bidGblFlags
0x1004237ed  mov     edi, 24002h
0x1004237f2  and     eax, edi
0x1004237f4  cmp     eax, edi
0x1004237f6  jnz     short loc_10042381F
0x1004237f8  mov     rax, cs:off_1005E4DB0; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x1004237ff  test    rax, rax
0x100423802  jz      short loc_10042381F
0x100423804  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x10042380c  mov     r8, cs:off_1005E4DB0; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x100423813  mov     edx, 9E800h
0x100423818  xor     ecx, ecx
0x10042381a  call    _bidTraceW
0x10042381f  mov     eax, cs:_bidGblFlags
0x100423825  and     eax, edi
0x100423827  cmp     eax, edi
0x100423829  jnz     short loc_100423851
0x10042382b  mov     r8d, [rsi+60h]
0x10042382f  add     r8, [rsi+50h]
0x100423833  mov     [rsp+78h+lpOverlapped], rbx
0x100423838  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x100423840  mov     edx, 10h
0x100423845  mov     rcx, cs:_bidID
0x10042384c  call    _bidWriteBin
0x100423851  mov     eax, cs:_bidGblFlags
0x100423857  mov     ecx, 20002h
0x10042385c  and     eax, ecx
0x10042385e  cmp     eax, ecx
0x100423860  jnz     loc_100423969
0x100423866  mov     rax, cs:off_1005E4DB8; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x10042386d  test    rax, rax
0x100423870  jz      loc_100423969
0x100423876  xor     r9d, r9d
0x100423879  mov     r8, cs:off_1005E4DB8; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x100423880  mov     edx, 9F400h
0x100423885  xor     ecx, ecx
0x100423887  call    _bidTraceW
0x10042388c  jmp     loc_100423969
0x100423891  mov     [r14+50h], rsi
0x100423895  mov     edi, 0C3BFh
0x10042389a  test    byte ptr cs:_bidGblFlags, 2
0x1004238a1  jz      short loc_10042390D
0x1004238a3  mov     rax, cs:off_1005E4D98; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004238aa  test    rax, rax
0x1004238ad  jz      short loc_10042390D
0x1004238af  mov     ecx, edi; unsigned int
0x1004238b1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004238b6  mov     [rsp+78h+var_50], 102h
0x1004238be  mov     r8, cs:off_1005E4D98; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004238c5  mov     edx, 91800h
0x1004238ca  jmp     short loc_1004238FE
0x1004238cc  mov     edi, 0C3B4h
0x1004238d1  test    byte ptr cs:_bidGblFlags, 2
0x1004238d8  jz      short loc_10042390D
0x1004238da  mov     rax, cs:off_1005E4D90; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004238e1  test    rax, rax
0x1004238e4  jz      short loc_10042390D
0x1004238e6  mov     ecx, edi; unsigned int
0x1004238e8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004238ed  or      [rsp+78h+var_50], 0FFFFFFFFh
0x1004238f2  mov     r8, cs:off_1005E4D90; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1004238f9  mov     edx, 8FC00h
0x1004238fe  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x100423902  mov     r9d, [r14+48h]
0x100423906  xor     ecx, ecx
0x100423908  call    _bidTraceW
0x10042390d  mov     r8d, edi
0x100423910  mov     edx, ebp
0x100423912  mov     ecx, [r14+48h]
0x100423916  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042391b  cmp     ebp, 102h
0x100423921  jz      short loc_100423934
0x100423923  test    rsi, rsi
0x100423926  jz      short loc_100423934
0x100423928  mov     rcx, rsi; this
0x10042392b  call    SNIPacketRelease
0x100423930  mov     [r14+50h], rbx
0x100423934  mov     eax, cs:_bidGblFlags
0x10042393a  mov     ecx, 20002h
0x10042393f  and     eax, ecx
0x100423941  cmp     eax, ecx
0x100423943  jnz     short loc_100423967
0x100423945  mov     rax, cs:off_1005E4DC0; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x10042394c  test    rax, rax
  ... truncated ...
```
