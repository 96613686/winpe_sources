# OpenDhcpSocket

- ea: `0x180023754`
- end: `0x180023921`
- name: `OpenDhcpSocket`
- size: `461`
- prototype: ``
- caller_count: `8`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c240`
- `0x18001ff40`
- `0x1800232e8`
- `0x180031d48`
- `0x180031e90`
- `0x180033228`
- `0x180033480`
- `0x180034fe4`

## callees

- `0x180009108`
- `0x18000a100`
- `0x18000b650`
- `0x180015604`
- `0x18001bc5c`
- `0x1800231f4`
- `0x180023754`
- `0x180041484`
- `0x180049a80`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d310`
- `0x18004d4c0`
- `0x18004d9e8`

## pseudocode

```c
__int64 __fastcall OpenDhcpSocket(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // edi
  _QWORD *v6; // rsi
  BOOL v7; // edi
  bool v8; // zf

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 31, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 32, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    v5 = 50;
    v6 = (_QWORD *)(a1 + 72);
LABEL_27:
    *v6 = -1;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_SD(1025, 36, (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 56), v5);
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v3, (int)ErrorOpeningSocket, *(_DWORD *)(a1 + 48), v5);
    TraceLogErrorv4(a1, v5, 40);
    goto LABEL_32;
  }
  v6 = (_QWORD *)(a1 + 72);
  if ( *(_QWORD *)(a1 + 72) == -1 )
  {
    if ( DhcpGlobalPdcCount <= 0 && (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 34, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, (unsigned int)DhcpGlobalPdcCount);
    if ( !*(_DWORD *)(a1 + 792) )
      goto LABEL_25;
    v7 = !*(_DWORD *)(a1 + 776)
      || (unsigned int)DhcpIsInitState((_DWORD *)a1)
      || (unsigned int)DhcpIsInitRebootState(a1)
      || *(_DWORD *)(a1 + 416)
      || !*(_DWORD *)(a1 + 120);
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_DDll(v3, v2, v4, *(unsigned int *)(a1 + 120), *(_DWORD *)(a1 + 416), *(_DWORD *)(a1 + 776), v7);
    if ( v7 )
    {
      v5 = InitializeGlobalZeroSocket(a1);
      v8 = v5 == 0;
    }
    else
    {
LABEL_25:
      v5 = InitializeDhcpSocket(a1 + 72, *(unsigned int *)(a1 + 120));
      v8 = v5 == 0;
    }
    if ( v8 )
      goto LABEL_32;
    goto LABEL_27;
  }
  v5 = 0;
  if ( (xmmword_1800616A0 & 0x10) == 0 )
    return v5;
  WPP_SF_(1028, 33, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
LABEL_32:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 37, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180023754  push    rbx
0x180023756  push    rbp
0x180023757  push    rsi
0x180023758  push    rdi
0x180023759  sub     rsp, 48h
0x18002375d  mov     rbx, rcx
0x180023760  test    byte ptr cs:xmmword_1800616A0, 10h
0x180023767  lea     rbp, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002376e  jz      short loc_180023786
0x180023770  mov     r9, [rbx+18h]
0x180023774  mov     edx, 1Fh
0x180023779  mov     ecx, 404h
0x18002377e  mov     r8, rbp
0x180023781  call    WPP_SF_q
0x180023786  call    DhcpIsFSEGuestSystem
0x18002378b  test    eax, eax
0x18002378d  jz      short loc_1800237B8
0x18002378f  test    byte ptr cs:xmmword_1800616A0, 2
0x180023796  jz      short loc_1800237AA
0x180023798  mov     edx, 20h ; ' '
0x18002379d  mov     ecx, 401h
0x1800237a2  mov     r8, rbp
0x1800237a5  call    WPP_SF_
0x1800237aa  mov     edi, 32h ; '2'
0x1800237af  lea     rsi, [rbx+48h]
0x1800237b3  jmp     loc_1800238A2
0x1800237b8  lea     rsi, [rbx+48h]
0x1800237bc  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800237c0  jz      short loc_1800237E6
0x1800237c2  xor     edi, edi
0x1800237c4  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800237cb  jz      loc_180023916
0x1800237d1  lea     edx, [rdi+21h]
0x1800237d4  mov     ecx, 404h
0x1800237d9  mov     r8, rbp
0x1800237dc  call    WPP_SF_
0x1800237e1  jmp     loc_1800238F8
0x1800237e6  mov     r9d, cs:DhcpGlobalPdcCount
0x1800237ed  test    r9d, r9d
0x1800237f0  jg      short loc_18002380D
0x1800237f2  test    byte ptr cs:xmmword_1800616A0, 2
0x1800237f9  jz      short loc_18002380D
0x1800237fb  mov     edx, 22h ; '"'
0x180023800  mov     ecx, 401h
0x180023805  mov     r8, rbp
0x180023808  call    WPP_SF_d
0x18002380d  mov     eax, [rbx+318h]
0x180023813  test    eax, eax
0x180023815  jz      short loc_18002388B
0x180023817  mov     eax, [rbx+308h]
0x18002381d  test    eax, eax
0x18002381f  jz      short loc_18002384A
0x180023821  mov     rcx, rbx
0x180023824  call    DhcpIsInitState
0x180023829  test    eax, eax
0x18002382b  jnz     short loc_18002384A
0x18002382d  mov     rcx, rbx
0x180023830  call    DhcpIsInitRebootState
0x180023835  test    eax, eax
0x180023837  jnz     short loc_18002384A
0x180023839  cmp     [rbx+1A0h], eax
0x18002383f  jnz     short loc_18002384A
0x180023841  cmp     [rbx+78h], eax
0x180023844  jz      short loc_18002384A
0x180023846  xor     edi, edi
0x180023848  jmp     short loc_18002384F
0x18002384a  mov     edi, 1
0x18002384f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180023856  jz      short loc_180023879
0x180023858  mov     eax, [rbx+308h]
0x18002385e  mov     r9d, [rbx+78h]
0x180023862  mov     [rsp+68h+var_38], edi
0x180023866  mov     [rsp+68h+var_40], eax
0x18002386a  mov     eax, [rbx+1A0h]
0x180023870  mov     [rsp+68h+var_48], eax
0x180023874  call    WPP_SF_DDll
0x180023879  test    edi, edi
0x18002387b  jz      short loc_18002388B
0x18002387d  mov     rcx, rbx
0x180023880  call    InitializeGlobalZeroSocket
0x180023885  mov     edi, eax
0x180023887  test    eax, eax
0x180023889  jmp     short loc_1800238A0
0x18002388b  mov     eax, [rbx+330h]
0x180023891  mov     rcx, rsi
0x180023894  mov     edx, [rbx+78h]
0x180023897  call    InitializeDhcpSocket
0x18002389c  mov     edi, eax
0x18002389e  test    eax, eax
0x1800238a0  jz      short loc_1800238F8
0x1800238a2  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800238a9  test    byte ptr cs:xmmword_1800616A0, 2
0x1800238b0  jz      short loc_1800238CC
0x1800238b2  mov     r9, [rbx+38h]
0x1800238b6  mov     edx, 24h ; '$'
0x1800238bb  mov     ecx, 401h
0x1800238c0  mov     [rsp+68h+var_48], edi
0x1800238c4  mov     r8, rbp
0x1800238c7  call    WPP_SF_SD
0x1800238cc  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 4
0x1800238d3  jz      short loc_1800238E8
0x1800238d5  mov     r8d, [rbx+30h]
0x1800238d9  lea     rdx, ErrorOpeningSocket
0x1800238e0  mov     r9d, edi
0x1800238e3  call    McTemplateU0qq_EtwEventWriteTransfer
0x1800238e8  mov     r8d, 28h ; '('
0x1800238ee  mov     edx, edi
0x1800238f0  mov     rcx, rbx
0x1800238f3  call    TraceLogErrorv4
0x1800238f8  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800238ff  jz      short loc_180023916
0x180023901  mov     edx, 25h ; '%'
0x180023906  mov     ecx, 404h
0x18002390b  mov     r9d, edi
0x18002390e  mov     r8, rbp
0x180023911  call    WPP_SF_D
0x180023916  mov     eax, edi
0x180023918  add     rsp, 48h
0x18002391c  pop     rdi
0x18002391d  pop     rsi
0x18002391e  pop     rbp
0x18002391f  pop     rbx
0x180023920  retn
```
