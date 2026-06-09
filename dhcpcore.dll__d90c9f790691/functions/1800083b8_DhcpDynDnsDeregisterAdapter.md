# DhcpDynDnsDeregisterAdapter

- ea: `0x1800083b8`
- end: `0x180008738`
- name: `DhcpDynDnsDeregisterAdapter`
- size: `896`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180003ea0`
- `0x1800095d8`

## callees

- `0x180007190`
- `0x1800083b8`
- `0x180009038`
- `0x180009310`
- `0x18000a580`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d310`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008705`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800086c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800086c6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008474`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008474`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008676`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008676`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x1800084fe`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x1800084fe`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800084bf`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800084bf`

## pseudocode

```c
__int64 __fastcall DhcpDynDnsDeregisterAdapter(__int64 a1, int *a2, unsigned int a3, int a4)
{
  __int64 v6; // r15
  char v8; // r14
  __int64 v9; // rcx
  DWORD v10; // ebx
  const wchar_t *v11; // r9
  int *v12; // rcx
  __int64 v13; // rdx
  __int16 *v14; // rax
  __int16 *v15; // rcx
  char v16; // al
  DWORD v18; // eax
  DWORD LastError; // eax
  _DWORD v20[2]; // [rsp+30h] [rbp-1C8h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-1C0h]
  __int64 v22; // [rsp+40h] [rbp-1B8h]
  __int64 v23; // [rsp+48h] [rbp-1B0h]
  __int64 v24; // [rsp+50h] [rbp-1A8h]
  __int64 v25; // [rsp+58h] [rbp-1A0h]
  __int64 v26; // [rsp+60h] [rbp-198h]
  int v27; // [rsp+68h] [rbp-190h]
  int v28; // [rsp+6Ch] [rbp-18Ch]
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+78h] [rbp-180h]
  _DWORD v30[40]; // [rsp+80h] [rbp-178h] BYREF
  __int16 v31; // [rsp+120h] [rbp-D8h] BYREF

  v6 = 80;
  memset_0(v20, 0, 0x50u);
  memset_0(v30, 0, 0x140u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 12, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, a2);
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_Dd(1028, 13, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, a3, a4);
  }
  v8 = 0;
  if ( a4 && DhcpGlobalHostStatus )
  {
    ResetEvent(DhcpGlobalHostStatus);
    v8 = 1;
  }
  v28 = 288;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  v22 = (unsigned __int64)a2 & -(__int64)(a4 != 0);
  v21 = (unsigned __int64)&DhcpGlobalHostStatus & -(__int64)(v8 != 0);
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v27 = 0;
  v20[1] = 1;
  v20[0] = 80;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 14, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, a2);
  v10 = DnsDhcpRegisterAddrs(v20);
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    LODWORD(v11) = (_DWORD)a2;
    if ( !a4 )
      v11 = L"[Dyndns-disabled]";
    WPP_SF_SD(1025, 15, (unsigned int)WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, (_DWORD)v11, v10);
  }
  if ( a4 )
  {
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0zq_EtwEventWriteTransfer(v9, DNSDeregisteringAdapter, a2, v10);
    memset_0(v30, 0, sizeof(v30));
    v31 = 0;
    v12 = &dword_180053FEC;
    v30[0] = v10;
    if ( a2 )
      v12 = a2;
    v30[3] = 16;
    v13 = 2147483646;
    v14 = &v31;
    do
    {
      if ( !v13 )
        break;
      if ( !*(_WORD *)v12 )
        break;
      *v14 = *(_WORD *)v12;
      v12 = (int *)((char *)v12 + 2);
      ++v14;
      --v13;
      --v6;
    }
    while ( v6 );
    v15 = v14 - 1;
    if ( v6 )
      v15 = v14;
    *v15 = 0;
  }
  else
  {
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v9, DNSDeregisteringDynDnsDisabled, v10);
    InitializeTraceElementFromContext(v30, 0, v10, 17);
  }
  TraceLogEx(v30);
  v16 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 16, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, v10);
    v16 = xmmword_1800616A0;
  }
  if ( !v10 )
  {
    if ( !v8 )
    {
LABEL_34:
      if ( a4 && !a3 )
        Sleep(0x3E8u);
      return v10;
    }
    if ( !DhcpGlobalHostStatus || a3 )
      return v10;
    v18 = WaitForSingleObject(DhcpGlobalHostStatus, 0xFA0u);
    if ( v18 != 128 )
    {
      if ( v18 == 258 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_(1025, 19, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids);
        return 0;
      }
      if ( v18 != -1 )
        return 0;
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 18, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, LastError);
    return v10;
  }
  if ( (v16 & 2) != 0 )
    WPP_SF_D(1025, 17, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, v10);
  if ( !v8 )
    goto LABEL_34;
  return v10;
}

```

## disassembly

```asm
0x1800083b8  mov     [rsp+arg_0], rbx
0x1800083bd  mov     [rsp+arg_18], rsi
0x1800083c2  push    rdi
0x1800083c3  push    r12
0x1800083c5  push    r13
0x1800083c7  push    r14
0x1800083c9  push    r15
0x1800083cb  sub     rsp, 1D0h
0x1800083d2  mov     rax, cs:__security_cookie
0x1800083d9  xor     rax, rsp
0x1800083dc  mov     [rsp+1F8h+var_38], rax
0x1800083e4  mov     r12d, r8d
0x1800083e7  lea     rcx, [rsp+1F8h+var_1C8]; void *
0x1800083ec  mov     rdi, rdx
0x1800083ef  mov     r15d, 50h ; 'P'
0x1800083f5  mov     r8d, r15d; Size
0x1800083f8  xor     edx, edx; Val
0x1800083fa  mov     esi, r9d
0x1800083fd  call    memset_0
0x180008402  xor     edx, edx; Val
0x180008404  lea     rcx, [rsp+1F8h+var_178]; void *
0x18000840c  mov     r8d, 140h; Size
0x180008412  call    memset_0
0x180008417  mov     al, byte ptr cs:xmmword_1800616A0
0x18000841d  lea     rbx, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180008424  test    al, 10h
0x180008426  jz      short loc_18000845E
0x180008428  lea     edx, [r15-44h]
0x18000842c  mov     ecx, 404h
0x180008431  mov     r9, rdi
0x180008434  mov     r8, rbx
0x180008437  call    WPP_SF_S
0x18000843c  mov     al, byte ptr cs:xmmword_1800616A0
0x180008442  test    al, 10h
0x180008444  jz      short loc_18000845E
0x180008446  lea     edx, [r15-43h]
0x18000844a  mov     [rsp+1F8h+var_1D8], esi
0x18000844e  mov     ecx, 404h
0x180008453  mov     r9d, r12d
0x180008456  mov     r8, rbx
0x180008459  call    WPP_SF_Dd
0x18000845e  xor     r13d, r13d
0x180008461  mov     r14b, r13b
0x180008464  test    esi, esi
0x180008466  jz      short loc_18000847D
0x180008468  mov     rcx, cs:DhcpGlobalHostStatus; hEvent
0x18000846f  test    rcx, rcx
0x180008472  jz      short loc_18000847D
0x180008474  call    cs:__imp_ResetEvent
0x18000847a  mov     r14b, 1
0x18000847d  mov     eax, esi
0x18000847f  mov     [rsp+1F8h+var_18C], 120h
0x180008487  neg     eax
0x180008489  mov     [rsp+1F8h+var_1A8], r13
0x18000848e  mov     al, r14b
0x180008491  mov     [rsp+1F8h+var_198], r13
0x180008496  sbb     rcx, rcx
0x180008499  mov     [rsp+1F8h+var_1A0], r13
0x18000849e  and     rcx, rdi
0x1800084a1  mov     [rsp+1F8h+var_1B0], r13
0x1800084a6  neg     al
0x1800084a8  mov     [rsp+1F8h+var_1B8], rcx
0x1800084ad  lea     rax, DhcpGlobalHostStatus
0x1800084b4  sbb     rcx, rcx
0x1800084b7  and     rcx, rax
0x1800084ba  mov     [rsp+1F8h+var_1C0], rcx
0x1800084bf  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800084c5  mov     [rsp+1F8h+var_180], eax
0x1800084c9  mov     [rsp+1F8h+var_190], r13d
0x1800084ce  mov     [rsp+1F8h+var_1C4], 1
0x1800084d6  mov     [rsp+1F8h+var_1C8], r15d
0x1800084db  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800084e2  jz      short loc_1800084F9
0x1800084e4  mov     edx, 0Eh
0x1800084e9  mov     ecx, 404h
0x1800084ee  mov     r9, rdi
0x1800084f1  mov     r8, rbx
0x1800084f4  call    WPP_SF_S
0x1800084f9  lea     rcx, [rsp+1F8h+var_1C8]
0x1800084fe  call    cs:__imp_DnsDhcpRegisterAddrs
0x180008504  mov     ebx, eax
0x180008506  test    byte ptr cs:xmmword_1800616A0, 2
0x18000850d  jz      short loc_180008539
0x18000850f  test    esi, esi
0x180008511  mov     [rsp+1F8h+var_1D8], ebx
0x180008515  lea     rax, aDyndnsDisabled; "[Dyndns-disabled]"
0x18000851c  mov     r9, rdi
0x18000851f  cmovz   r9, rax
0x180008523  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x18000852a  mov     edx, 0Fh
0x18000852f  mov     ecx, 401h
0x180008534  call    WPP_SF_SD
0x180008539  test    esi, esi
0x18000853b  jz      loc_1800085DC
0x180008541  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180008548  jz      short loc_18000855C
0x18000854a  mov     r9d, ebx
0x18000854d  lea     rdx, DNSDeregisteringAdapter
0x180008554  mov     r8, rdi
0x180008557  call    McTemplateU0zq_EtwEventWriteTransfer
0x18000855c  xor     edx, edx; Val
0x18000855e  lea     rcx, [rsp+1F8h+var_178]; void *
0x180008566  mov     r8d, 0A0h; Size
0x18000856c  call    memset_0
0x180008571  test    rdi, rdi
0x180008574  mov     [rsp+1F8h+var_D8], r13w
0x18000857d  lea     rcx, dword_180053FEC
0x180008584  mov     [rsp+1F8h+var_178], ebx
0x18000858b  cmovnz  rcx, rdi
0x18000858f  mov     [rsp+1F8h+var_16C], 10h
0x18000859a  mov     edx, 7FFFFFFEh
0x18000859f  lea     rax, [rsp+1F8h+var_D8]
0x1800085a7  test    rdx, rdx
0x1800085aa  jz      short loc_1800085CB
0x1800085ac  movzx   r8d, word ptr [rcx]
0x1800085b0  test    r8w, r8w
0x1800085b4  jz      short loc_1800085CB
0x1800085b6  mov     [rax], r8w
0x1800085ba  add     rcx, 2
0x1800085be  add     rax, 2
0x1800085c2  dec     rdx
0x1800085c5  sub     r15, 1
0x1800085c9  jnz     short loc_1800085A7
0x1800085cb  test    r15, r15
0x1800085ce  lea     rcx, [rax-2]
0x1800085d2  cmovnz  rcx, rax
0x1800085d6  mov     [rcx], r13w
0x1800085da  jmp     short loc_18000860C
0x1800085dc  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800085e3  jz      short loc_1800085F4
0x1800085e5  mov     r8d, ebx
0x1800085e8  lea     rdx, DNSDeregisteringDynDnsDisabled
0x1800085ef  call    McTemplateU0q_EtwEventWriteTransfer
0x1800085f4  mov     r9d, 11h
0x1800085fa  lea     rcx, [rsp+1F8h+var_178]
0x180008602  mov     r8d, ebx
0x180008605  xor     edx, edx
0x180008607  call    InitializeTraceElementFromContext
0x18000860c  lea     rcx, [rsp+1F8h+var_178]
0x180008614  call    TraceLogEx
0x180008619  mov     al, byte ptr cs:xmmword_1800616A0
0x18000861f  test    al, 10h
0x180008621  jz      short loc_180008642
0x180008623  mov     edx, 10h
0x180008628  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x18000862f  mov     ecx, 404h
0x180008634  mov     r9d, ebx
0x180008637  call    WPP_SF_D
0x18000863c  mov     al, byte ptr cs:xmmword_1800616A0
0x180008642  test    ebx, ebx
0x180008644  jz      short loc_1800086AB
0x180008646  test    al, 2
0x180008648  jz      short loc_180008663
0x18000864a  mov     edx, 11h
0x18000864f  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180008656  mov     ecx, 401h
0x18000865b  mov     r9d, ebx
0x18000865e  call    WPP_SF_D
0x180008663  test    r14b, r14b
0x180008666  jnz     short loc_18000867C
0x180008668  test    esi, esi
0x18000866a  jz      short loc_18000867C
0x18000866c  test    r12d, r12d
0x18000866f  jnz     short loc_18000867C
0x180008671  mov     ecx, 3E8h; dwMilliseconds
0x180008676  call    cs:__imp_Sleep
0x18000867c  mov     eax, ebx
0x18000867e  mov     rcx, [rsp+1F8h+var_38]
0x180008686  xor     rcx, rsp; StackCookie
0x180008689  call    __security_check_cookie
0x18000868e  lea     r11, [rsp+1F8h+var_28]
0x180008696  mov     rbx, [r11+30h]
0x18000869a  mov     rsi, [r11+48h]
0x18000869e  mov     rsp, r11
0x1800086a1  pop     r15
0x1800086a3  pop     r14
0x1800086a5  pop     r13
0x1800086a7  pop     r12
0x1800086a9  pop     rdi
0x1800086aa  retn
0x1800086ab  test    r14b, r14b
0x1800086ae  jz      short loc_180008668
0x1800086b0  mov     rcx, cs:DhcpGlobalHostStatus; hHandle
0x1800086b7  test    rcx, rcx
0x1800086ba  jz      short loc_18000867C
0x1800086bc  test    r12d, r12d
0x1800086bf  jnz     short loc_18000867C
0x1800086c1  mov     edx, 0FA0h; dwMilliseconds
0x1800086c6  call    cs:__imp_WaitForSingleObject
0x1800086cc  cmp     eax, 80h
0x1800086d1  jz      short loc_180008705
0x1800086d3  cmp     eax, 102h
0x1800086d8  jz      short loc_1800086E4
0x1800086da  cmp     eax, 0FFFFFFFFh
0x1800086dd  jz      short loc_180008705
0x1800086df  mov     ebx, r13d
0x1800086e2  jmp     short loc_18000867C
0x1800086e4  test    byte ptr cs:xmmword_1800616A0, 2
0x1800086eb  jz      short loc_1800086DF
0x1800086ed  mov     edx, 13h
0x1800086f2  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x1800086f9  mov     ecx, 401h
0x1800086fe  call    WPP_SF_
0x180008703  jmp     short loc_1800086DF
0x180008705  call    cs:__imp_GetLastError
0x18000870b  mov     ebx, eax
0x18000870d  test    byte ptr cs:xmmword_1800616A0, 2
0x180008714  jz      loc_18000867C
0x18000871a  mov     edx, 12h
0x18000871f  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180008726  mov     ecx, 401h
0x18000872b  mov     r9d, eax
0x18000872e  call    WPP_SF_D
0x180008733  jmp     loc_18000867C
```
