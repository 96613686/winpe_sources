# AccessIfStatus

- ea: `0x180005250`
- end: `0x180005474`
- name: `AccessIfStatus`
- size: `548`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005250`
- `0x18000ac60`
- `0x18002e558`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180005420`
- `ntdll!RtlReleaseResource` at `0x180005420`
- `ntdll!RtlAcquireResourceShared` at `0x180005396`
- `ntdll!RtlAcquireResourceShared` at `0x180005396`
- `KERNEL32!SystemTimeToFileTime` at `0x1800053f8`
- `KERNEL32!SystemTimeToFileTime` at `0x1800053f8`
- `KERNEL32!GetSystemTime` at `0x1800053e8`
- `KERNEL32!GetSystemTime` at `0x1800053e8`

## string_xrefs

- `0x1800052ca`: `AccessIfStatus`
- `0x18000532f`: `Leaving: AccessIfStatus`
- `0x180005369`: `Leaving: AccessIfStatus`
- `0x18000542f`: `Leaving: AccessIfStatus`

## pseudocode

```c
__int64 __fastcall AccessIfStatus(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5,
        int a6,
        int a7)
{
  char v11; // al
  unsigned int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // rbx
  int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-848h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-840h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-838h] BYREF
  int v20; // [rsp+50h] [rbp-828h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-824h] BYREF

  v17 = 0;
  FileTime = 0;
  v20 = 0;
  SystemTime = 0;
  memset_0(v21, 0, sizeof(v21));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"Entered: %ws", L"AccessIfStatus");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 <= 4 )
  {
    v13 = *a4;
    *a4 = 28;
    if ( v13 >= 0x1C )
    {
      RtlAcquireResourceShared(&Resource, 1u);
      v14 = LocateIfRow(a1, (a2 >> 2) - 1, a3 + 4, &v17);
      if ( !v14 )
      {
        v15 = v17;
        a5[2] = *(_DWORD *)(v17 + 16);
        a5[3] = *(_DWORD *)(v15 + 172);
        a5[4] = *(_DWORD *)(v15 + 168);
        v16 = *(_DWORD *)(v15 + 336);
        a5[5] = v16;
        if ( v16 )
        {
          GetSystemTime(&SystemTime);
          SystemTimeToFileTime(&SystemTime, &FileTime);
          a5[6] = *(_QWORD *)&FileTime - *(_QWORD *)(v15 + 496) < *(_QWORD *)(v15 + 488);
        }
      }
      RtlReleaseResource(&Resource);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIfStatus");
      return v14;
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIfStatus");
      return 122;
    }
  }
  else
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIfStatus");
    return 87;
  }
}

```

## disassembly

```asm
0x180005250  mov     [rsp+arg_0], rbx
0x180005255  mov     [rsp+arg_8], rsi
0x18000525a  push    rdi
0x18000525b  push    r14
0x18000525d  push    r15
0x18000525f  sub     rsp, 860h
0x180005266  mov     rax, cs:__security_cookie
0x18000526d  xor     rax, rsp
0x180005270  mov     [rsp+878h+var_28], rax
0x180005278  mov     rdi, [rsp+878h+arg_20]
0x180005280  mov     r15, r8
0x180005283  mov     esi, edx
0x180005285  mov     [rsp+878h+var_848], 0
0x18000528e  mov     r14d, ecx
0x180005291  mov     qword ptr [rsp+878h+FileTime.dwLowDateTime], 0
0x18000529a  xorps   xmm0, xmm0
0x18000529d  lea     rcx, [rsp+878h+var_824]; void *
0x1800052a2  xor     eax, eax
0x1800052a4  xor     edx, edx; Val
0x1800052a6  mov     r8d, 7FCh; Size
0x1800052ac  mov     [rsp+878h+var_828], eax
0x1800052b0  movups  xmmword ptr [rsp+878h+SystemTime.wYear], xmm0
0x1800052b5  mov     rbx, r9
0x1800052b8  call    memset_0
0x1800052bd  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800052c4  test    al, al
0x1800052c6  jns     short loc_180005311
0x1800052c8  xor     eax, eax
0x1800052ca  lea     r8, aAccessifstatus; "AccessIfStatus"
0x1800052d1  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800052d8  mov     word ptr [rsp+878h+var_828], ax
0x1800052dd  lea     rcx, [rsp+878h+var_828]
0x1800052e2  call    FormatRRASErrorString
0x1800052e7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800052ee  test    al, al
0x1800052f0  jns     short loc_180005311
0x1800052f2  lea     r8, [rsp+878h+var_828]
0x1800052f7  lea     rdx, RasRtrmgrTraceInfo
0x1800052fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005305  call    McTemplateU0z_EventWriteTransfer
0x18000530a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005311  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x180005319  jnz     short loc_180005325
0x18000531b  mov     eax, 32h ; '2'
0x180005320  jmp     loc_18000544B
0x180005325  cmp     r14d, 4
0x180005329  jbe     short loc_180005353
0x18000532b  test    al, 80h
0x18000532d  jz      short loc_180005349
0x18000532f  lea     r8, aLeavingAccessi_10; "Leaving: AccessIfStatus"
0x180005336  lea     rdx, RasRtrmgrTraceInfo
0x18000533d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005344  call    McTemplateU0z_EventWriteTransfer
0x180005349  mov     eax, 57h ; 'W'
0x18000534e  jmp     loc_18000544B
0x180005353  mov     eax, [rbx]
0x180005355  mov     dword ptr [rbx], 1Ch
0x18000535b  cmp     eax, 1Ch
0x18000535e  jnb     short loc_18000538D
0x180005360  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005367  jz      short loc_180005383
0x180005369  lea     r8, aLeavingAccessi_10; "Leaving: AccessIfStatus"
0x180005370  lea     rdx, RasRtrmgrTraceInfo
0x180005377  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000537e  call    McTemplateU0z_EventWriteTransfer
0x180005383  mov     eax, 7Ah ; 'z'
0x180005388  jmp     loc_18000544B
0x18000538d  mov     dl, 1; Wait
0x18000538f  lea     rcx, Resource; Resource
0x180005396  call    cs:__imp_RtlAcquireResourceShared
0x18000539c  shr     esi, 2
0x18000539f  lea     r8, [r15+4]
0x1800053a3  lea     r9, [rsp+878h+var_848]
0x1800053a8  mov     ecx, r14d
0x1800053ab  lea     edx, [rsi-1]
0x1800053ae  call    LocateIfRow
0x1800053b3  mov     esi, eax
0x1800053b5  test    eax, eax
0x1800053b7  jnz     short loc_180005419
0x1800053b9  mov     rbx, [rsp+878h+var_848]
0x1800053be  mov     ecx, [rbx+10h]
0x1800053c1  mov     [rdi+8], ecx
0x1800053c4  mov     ecx, [rbx+0ACh]
0x1800053ca  mov     [rdi+0Ch], ecx
0x1800053cd  mov     ecx, [rbx+0A8h]
0x1800053d3  mov     [rdi+10h], ecx
0x1800053d6  mov     ecx, [rbx+150h]
0x1800053dc  mov     [rdi+14h], ecx
0x1800053df  test    ecx, ecx
0x1800053e1  jz      short loc_180005419
0x1800053e3  lea     rcx, [rsp+878h+SystemTime]; lpSystemTime
0x1800053e8  call    cs:__imp_GetSystemTime
0x1800053ee  lea     rdx, [rsp+878h+FileTime]; lpFileTime
0x1800053f3  lea     rcx, [rsp+878h+SystemTime]; lpSystemTime
0x1800053f8  call    cs:__imp_SystemTimeToFileTime
0x1800053fe  mov     rax, qword ptr [rsp+878h+FileTime.dwLowDateTime]
0x180005403  xor     edx, edx
0x180005405  sub     rax, [rbx+1F0h]
0x18000540c  cmp     rax, [rbx+1E8h]
0x180005413  setb    dl
0x180005416  mov     [rdi+18h], edx
0x180005419  lea     rcx, Resource; Resource
0x180005420  call    cs:__imp_RtlReleaseResource
0x180005426  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000542d  jz      short loc_180005449
0x18000542f  lea     r8, aLeavingAccessi_10; "Leaving: AccessIfStatus"
0x180005436  lea     rdx, RasRtrmgrTraceInfo
0x18000543d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005444  call    McTemplateU0z_EventWriteTransfer
0x180005449  mov     eax, esi
0x18000544b  mov     rcx, [rsp+878h+var_28]
0x180005453  xor     rcx, rsp; StackCookie
0x180005456  call    __security_check_cookie
0x18000545b  lea     r11, [rsp+878h+var_18]
0x180005463  mov     rbx, [r11+20h]
0x180005467  mov     rsi, [r11+28h]
0x18000546b  mov     rsp, r11
0x18000546e  pop     r15
0x180005470  pop     r14
0x180005472  pop     rdi
0x180005473  retn
```
