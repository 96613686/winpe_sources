# HandleZAM

- ea: `0x1800327ec`
- end: `0x180032e7a`
- name: `HandleZAM`
- size: `1678`
- prototype: `void __fastcall(char *buf, size_t Size, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003238c`

## callees

- `0x180002238`
- `0x18000ac60`
- `0x18001f170`
- `0x180021674`
- `0x1800301e4`
- `0x180030574`
- `0x180030b94`
- `0x180031078`
- `0x1800313c8`
- `0x180031bac`
- `0x180031bd8`
- `0x180031c14`
- `0x1800327ec`
- `0x180033628`
- `0x180034038`
- `0x180035328`
- `0x1800354d4`
- `0x180036548`
- `0x1800583cc`
- `0x180058506`
- `0x180058512`
- `0x18005852a`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!rand` at `0x180032c7c`
- `msvcrt!rand` at `0x180032c7c`
- `ntdll!NtQuerySystemTime` at `0x180032ce7`
- `ntdll!NtQuerySystemTime` at `0x180032ce7`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032c53`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032c65`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032c53`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032c65`
- `ntdll!RtlReleaseResource` at `0x180032d28`
- `ntdll!RtlReleaseResource` at `0x180032d38`
- `ntdll!RtlReleaseResource` at `0x180032e1e`
- `ntdll!RtlReleaseResource` at `0x180032d28`
- `ntdll!RtlReleaseResource` at `0x180032d38`
- `ntdll!RtlReleaseResource` at `0x180032e1e`
- `ntdll!RtlAcquireResourceShared` at `0x180032d99`
- `ntdll!RtlAcquireResourceShared` at `0x180032d99`
- `KERNEL32!HeapAlloc` at `0x180032cc6`
- `KERNEL32!HeapAlloc` at `0x180032cc6`
- `rtutils!RouterLogEventExW` at `0x180032ae4`
- `rtutils!RouterLogEventExW` at `0x180032ae4`

## string_xrefs

- `0x180032ba1`: `ZAM Cache check for %d.%d.%d.%d, %d.%d.%d.%d is %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HandleZAM(char *buf, size_t Size, union _LARGE_INTEGER a3)
{
  size_t v4; // r12
  char *v6; // rdi
  ULONG v7; // edx
  __int64 v8; // rbx
  char *v9; // rbx
  int v10; // edx
  int v11; // r10d
  unsigned int v12; // r11d
  ULONG v13; // r14d
  __int64 Scope; // rax
  __int64 v15; // r15
  __int64 v16; // rdx
  int v17; // ebx
  int v18; // ecx
  int v19; // ebx
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  int v22; // r13d
  bool v23; // zf
  char v24; // r10
  int v25; // ecx
  int v26; // edx
  __int64 v27; // r9
  __int64 v28; // r8
  int v29; // r11d
  __int64 v30; // rax
  double v31; // xmm0_8
  double v32; // xmm7_8
  double v33; // xmm0_8
  void *v34; // rax
  void *v35; // rbx
  double v36; // xmm0_8
  struct _RTL_RESOURCE *v37; // rcx
  __int64 i; // r14
  __int64 *v39; // r13
  __int64 v40; // rbx
  union _LARGE_INTEGER v41; // rax
  __int64 v42; // rdx
  LPCWSTR ptszFormat; // [rsp+20h] [rbp-8B8h]
  LPCWSTR ptszFormata; // [rsp+20h] [rbp-8B8h]
  __int64 v45; // [rsp+28h] [rbp-8B0h]
  __int64 v46; // [rsp+28h] [rbp-8B0h]
  __int64 v47; // [rsp+30h] [rbp-8A8h]
  __int64 v48; // [rsp+30h] [rbp-8A8h]
  int v49; // [rsp+38h] [rbp-8A0h]
  int v50; // [rsp+40h] [rbp-898h]
  int v51; // [rsp+48h] [rbp-890h]
  int v52; // [rsp+60h] [rbp-878h] BYREF
  ULONG pulResult; // [rsp+64h] [rbp-874h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+68h] [rbp-870h] BYREF
  int v55; // [rsp+70h] [rbp-868h] BYREF
  _BYTE v56[2044]; // [rsp+74h] [rbp-864h] BYREF

  SystemTime = a3;
  v4 = (unsigned int)Size;
  v52 = 0;
  v55 = 0;
  memset_0(v56, 0, sizeof(v56));
  pulResult = v4;
  if ( ULongSub(v4, 0x14u, &pulResult) < 0 )
    goto LABEL_34;
  v6 = buf + 20;
  if ( buf[3] )
  {
    while ( ULongSub(pulResult, 1u, &pulResult) >= 0 )
    {
      if ( pulResult < v7 )
        break;
      v8 = (unsigned __int8)v6[1];
      if ( ULongSub(pulResult, v8 + 1, &pulResult) < 0 )
        break;
      if ( !pulResult )
        break;
      v9 = &v6[v8 + 2];
      if ( ULongSub(pulResult, (unsigned __int8)*v9 + 1, &pulResult) < 0 )
        break;
      v6 = &v9[v10];
      if ( v11 + 1 >= v12 )
        goto LABEL_9;
    }
    goto LABEL_34;
  }
LABEL_9:
  v13 = pulResult;
  while ( ((unsigned __int8)v6 & 3) != 0 )
  {
    if ( !v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"HandleZAM: Insufficient buffer to do the padding to 4 byte boundary");
      break;
    }
    *v6++ = 0;
    --v13;
  }
  Scope = FindScope(*((unsigned int *)buf + 3), (unsigned int)~(*((_DWORD *)buf + 4) - *((_DWORD *)buf + 3)));
  v15 = Scope;
  if ( !Scope )
  {
    v22 = 0;
    CheckForScopeRangeMismatch(buf);
    goto LABEL_36;
  }
  v16 = a3.QuadPart
      ? ((__int64 (__fastcall *)(_QWORD, _QWORD))FindBoundaryEntry)((union _LARGE_INTEGER)a3.QuadPart, Scope)
      : 0LL;
  if ( !v13 || v13 < 8 * (unsigned __int64)(unsigned __int8)*v6 + 8 )
  {
LABEL_34:
    v23 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    goto LABEL_46;
  }
  if ( v16 )
  {
    v17 = *((_DWORD *)buf + 2);
    if ( v17 == (unsigned int)MyScopeZoneID(v15) )
      ReportLeakyScope(v15, buf, v6);
    v18 = *(_DWORD *)&v6[8 * (unsigned __int8)*v6 + 4];
    if ( v18 )
      *(_DWORD *)(a3.QuadPart + 64) = v18;
    return;
  }
  AssertZBR(v15, *((unsigned int *)buf + 1), *((unsigned __int16 *)v6 + 1));
  v19 = *((_DWORD *)buf + 2);
  if ( v19 != (unsigned int)MyScopeZoneID(v15) )
  {
    v20 = *((_DWORD *)buf + 1);
    StringCbPrintfW(&g_AddrBuf1, 0x28u, L"%d.%d.%d.%d", (unsigned __int8)v20, BYTE1(v20), BYTE2(v20), HIBYTE(v20));
    v21 = *((_DWORD *)buf + 3);
    LODWORD(v48) = HIBYTE(v21);
    LODWORD(v46) = BYTE2(v21);
    LODWORD(ptszFormata) = BYTE1(v21);
    StringCbPrintfW(&g_AddrBuf2, 0x28u, L"%d.%d.%d.%d", (unsigned __int8)v21, ptszFormata, v46, v48);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(
        &v55,
        L"WARNING: Possible leaky Local Scope detected between this machine and %ls, boundary exists for %ls.",
        &g_AddrBuf1,
        &g_AddrBuf2);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v55);
    }
    RouterLogEventExW(g_hLogHandle, 2u, 0, 0x4ECEu, L"%S%S", &g_AddrBuf1, &g_AddrBuf2);
  }
  v22 = 1;
  CheckForScopeNameMismatch(v15, buf);
  if ( !*(_DWORD *)&v6[8 * (unsigned __int8)*v6 + 4] )
    *(_DWORD *)&v6[8 * (unsigned __int8)*v6 + 4] = MyScopeZoneID(v15);
LABEL_36:
  AssertInZamCache(*((unsigned int *)buf + 2), *((unsigned int *)buf + 3), &v52);
  v24 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v25 = (unsigned __int8)buf[11];
    v26 = (unsigned __int8)buf[10];
    v27 = (unsigned __int8)buf[9];
    v28 = (unsigned __int8)buf[8];
    v51 = (unsigned __int8)buf[15];
    v50 = (unsigned __int8)buf[14];
    v49 = (unsigned __int8)buf[13];
    LOWORD(v55) = 0;
    LODWORD(v47) = (unsigned __int8)buf[12];
    LODWORD(v45) = v25;
    LODWORD(ptszFormat) = v26;
    FormatRRASErrorString(
      &v55,
      L"ZAM Cache check for %d.%d.%d.%d, %d.%d.%d.%d is %d",
      v28,
      v27,
      ptszFormat,
      v45,
      v47,
      v49,
      v50,
      v51,
      v52);
    v24 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v55);
      v24 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( !v52 )
  {
    v29 = g_ipMyLocalZoneID;
    if ( !v22 )
    {
      if ( !v13 || v13 < 8 * (unsigned __int64)(unsigned __int8)*v6 + 8 )
      {
LABEL_45:
        v23 = v24 >= 0;
LABEL_46:
        if ( v23 )
          return;
LABEL_71:
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"HandleZAM: Insufficient buffer");
        return;
      }
      if ( (unsigned int)ZamIncludesZoneID(v6, (unsigned int)g_ipMyLocalZoneID) )
        return;
    }
    if ( v13 >= 2 )
    {
      v30 = (unsigned __int8)++*v6;
      if ( (unsigned __int8)v30 < (unsigned __int8)v6[1] )
      {
        if ( v13 < (unsigned __int64)(8 * v30 + 8) )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
            return;
          goto LABEL_71;
        }
        *(_DWORD *)&v6[8 * (unsigned __int8)*v6] = g_ipMyAddress;
        if ( !v22 )
        {
          *(_DWORD *)&v6[8 * (unsigned __int8)*v6 + 4] = v29;
          SendMZAPMessage(buf, v4 + 8);
        }
        RtlAcquireResourceShared(&stru_18008C560, 1u);
        for ( i = 0; i != 57; ++i )
        {
          v39 = &g_bbScopeTable[2 * i];
          v40 = *v39;
          if ( (__int64 *)*v39 != v39 )
          {
            v41 = SystemTime;
            do
            {
              if ( v40 != v41.QuadPart )
              {
                if ( !FindBoundaryEntry(v40, v15) )
                {
                  v42 = *(unsigned int *)(v40 + 64);
                  if ( !(_DWORD)v42 || !(unsigned int)ZamIncludesZoneID(v6, v42) )
                  {
                    *(_DWORD *)&v6[8 * (unsigned __int8)*v6 + 4] = v42;
                    SendMZAPMessageByIndex(buf, v4 + 8);
                  }
                }
                v41 = SystemTime;
              }
              v40 = *(_QWORD *)v40;
            }
            while ( (__int64 *)v40 != v39 );
          }
        }
        v37 = &stru_18008C560;
      }
      else
      {
        SystemTime.QuadPart = 0;
        RtlAcquireResourceExclusive(&stru_18008C5C0, 1u);
        RtlAcquireResourceExclusive(&stru_18008C680, 1u);
        if ( FindPendingZLE(buf)
          || (v31 = (double)rand(),
              v32 = log_0(v31 / 32767.0 * 256.0 + 1.0),
              v33 = log_0(256.0),
              v34 = HeapAlloc(IPRouterHeap, 0, v4),
              (v35 = v34) == 0) )
        {
          RtlReleaseResource(&stru_18008C680);
        }
        else
        {
          memcpy_0(v34, buf, v4);
          NtQuerySystemTime(&SystemTime);
          v36 = floor_0(v32 * 300.0 / v33 + 0.5);
          AddPendingZLE(v35, (unsigned int)v4, SystemTime.QuadPart + (unsigned int)(10000000 * (int)v36));
          RtlReleaseResource(&stru_18008C680);
          UpdateMzapTimer();
        }
        v37 = &stru_18008C5C0;
      }
      RtlReleaseResource(v37);
      return;
    }
    goto LABEL_45;
  }
}

```

## disassembly

```asm
0x1800327ec  mov     rax, rsp
0x1800327ef  push    rbx
0x1800327f0  push    rsi
0x1800327f1  push    rdi
0x1800327f2  push    r12
0x1800327f4  push    r13
0x1800327f6  push    r14
0x1800327f8  push    r15
0x1800327fa  sub     rsp, 8A0h
0x180032801  movaps  xmmword ptr [rax-48h], xmm6
0x180032805  movaps  xmmword ptr [rax-58h], xmm7
0x180032809  mov     rax, cs:__security_cookie
0x180032810  xor     rax, rsp
0x180032813  mov     [rsp+8D8h+var_68], rax
0x18003281b  mov     r13, r8
0x18003281e  mov     qword ptr [rsp+8D8h+SystemTime], r8
0x180032823  mov     r12d, edx
0x180032826  mov     rsi, rcx
0x180032829  xor     eax, eax
0x18003282b  mov     [rsp+8D8h+var_878], 0
0x180032833  xor     edx, edx; Val
0x180032835  mov     [rsp+8D8h+var_868], eax
0x180032839  mov     r8d, 7FCh; Size
0x18003283f  lea     rcx, [rsp+8D8h+var_864]; void *
0x180032844  call    memset_0
0x180032849  lea     r8, [rsp+8D8h+pulResult]; pulResult
0x18003284e  mov     [rsp+8D8h+pulResult], r12d
0x180032853  mov     edx, 14h; ulSubtrahend
0x180032858  mov     ecx, r12d; ulMinuend
0x18003285b  call    ULongSub
0x180032860  test    eax, eax
0x180032862  js      loc_180032B16
0x180032868  movzx   r11d, byte ptr [rsi+3]
0x18003286d  lea     rdi, [rsi+14h]
0x180032871  xor     r10d, r10d
0x180032874  test    r11d, r11d
0x180032877  jz      short loc_1800328F1
0x180032879  mov     ecx, [rsp+8D8h+pulResult]; ulMinuend
0x18003287d  lea     r8, [rsp+8D8h+pulResult]; pulResult
0x180032882  mov     edx, 1; ulSubtrahend
0x180032887  call    ULongSub
0x18003288c  test    eax, eax
0x18003288e  js      loc_180032B16
0x180032894  mov     ecx, [rsp+8D8h+pulResult]; ulMinuend
0x180032898  cmp     ecx, edx
0x18003289a  jb      loc_180032B16
0x1800328a0  movzx   ebx, byte ptr [rdi+1]
0x1800328a4  lea     r8, [rsp+8D8h+pulResult]; pulResult
0x1800328a9  lea     edx, [rbx+1]; ulSubtrahend
0x1800328ac  call    ULongSub
0x1800328b1  test    eax, eax
0x1800328b3  js      loc_180032B16
0x1800328b9  mov     ecx, [rsp+8D8h+pulResult]; ulMinuend
0x1800328bd  cmp     ecx, 1
0x1800328c0  jb      loc_180032B16
0x1800328c6  add     rbx, 2
0x1800328ca  lea     r8, [rsp+8D8h+pulResult]; pulResult
0x1800328cf  add     rbx, rdi
0x1800328d2  movzx   edx, byte ptr [rbx]
0x1800328d5  inc     edx; ulSubtrahend
0x1800328d7  call    ULongSub
0x1800328dc  test    eax, eax
0x1800328de  js      loc_180032B16
0x1800328e4  mov     edi, edx
0x1800328e6  inc     r10d
0x1800328e9  add     rdi, rbx
0x1800328ec  cmp     r10d, r11d
0x1800328ef  jb      short loc_180032879
0x1800328f1  mov     r14d, [rsp+8D8h+pulResult]
0x1800328f6  jmp     short loc_180032907
0x1800328f8  cmp     r14d, 1
0x1800328fc  jb      short loc_18003290F
0x1800328fe  mov     byte ptr [rdi], 0
0x180032901  inc     rdi
0x180032904  dec     r14d
0x180032907  test    dil, 3
0x18003290b  jnz     short loc_1800328F8
0x18003290d  jmp     short loc_180032932
0x18003290f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180032916  jz      short loc_180032932
0x180032918  lea     r8, aHandlezamInsuf; "HandleZAM: Insufficient buffer to do th"...
0x18003291f  lea     rdx, RasRtrmgrTraceInfo
0x180032926  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003292d  call    McTemplateU0z_EventWriteTransfer
0x180032932  mov     ecx, [rsi+0Ch]
0x180032935  mov     edx, [rsi+10h]
0x180032938  sub     edx, ecx
0x18003293a  not     edx
0x18003293c  call    FindScope
0x180032941  mov     r15, rax
0x180032944  test    rax, rax
0x180032947  jz      loc_180032B22
0x18003294d  test    r13, r13
0x180032950  jz      short loc_180032962
0x180032952  mov     rdx, rax
0x180032955  mov     rcx, r13
0x180032958  call    FindBoundaryEntry
0x18003295d  mov     rdx, rax
0x180032960  jmp     short loc_180032964
0x180032962  xor     edx, edx
0x180032964  cmp     r14d, 1
0x180032968  jb      loc_180032B16
0x18003296e  movzx   eax, byte ptr [rdi]
0x180032971  lea     rcx, ds:8[rax*8]
0x180032979  mov     eax, r14d
0x18003297c  cmp     rax, rcx
0x18003297f  jb      loc_180032B16
0x180032985  mov     rcx, r15
0x180032988  test    rdx, rdx
0x18003298b  jz      short loc_1800329BF
0x18003298d  mov     ebx, [rsi+8]
0x180032990  call    MyScopeZoneID
0x180032995  cmp     ebx, eax
0x180032997  jnz     short loc_1800329A7
0x180032999  mov     r8, rdi
0x18003299c  mov     rdx, rsi
0x18003299f  mov     rcx, r15
0x1800329a2  call    ReportLeakyScope
0x1800329a7  movzx   eax, byte ptr [rdi]
0x1800329aa  mov     ecx, [rdi+rax*8+4]
0x1800329ae  test    ecx, ecx
0x1800329b0  jz      loc_180032E49
0x1800329b6  mov     [r13+40h], ecx
0x1800329ba  jmp     loc_180032E49
0x1800329bf  movzx   r8d, word ptr [rdi+2]
0x1800329c4  mov     edx, [rsi+4]
0x1800329c7  call    AssertZBR
0x1800329cc  mov     ebx, [rsi+8]
0x1800329cf  mov     rcx, r15
0x1800329d2  call    MyScopeZoneID
0x1800329d7  cmp     ebx, eax
0x1800329d9  jz      loc_180032AEA
0x1800329df  mov     r9d, [rsi+4]
0x1800329e3  lea     r13, g_AddrBuf1
0x1800329ea  mov     r8d, r9d
0x1800329ed  mov     eax, r9d
0x1800329f0  shr     eax, 10h
0x1800329f3  mov     ebx, 28h ; '('
0x1800329f8  movzx   edx, al
0x1800329fb  mov     eax, r9d
0x1800329fe  shr     r8d, 18h
0x180032a02  mov     dword ptr [rsp+8D8h+var_8A8], r8d
0x180032a07  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180032a0e  mov     dword ptr [rsp+8D8h+var_8B0], edx
0x180032a12  mov     edx, ebx; cbDest
0x180032a14  shr     eax, 8
0x180032a17  movzx   ecx, al
0x180032a1a  mov     dword ptr [rsp+8D8h+ptszFormat], ecx
0x180032a1e  mov     rcx, r13; pszDest
0x180032a21  movzx   r9d, r9b
0x180032a25  call    StringCbPrintfW
0x180032a2a  mov     r9d, [rsi+0Ch]
0x180032a2e  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180032a35  mov     eax, r9d
0x180032a38  mov     r11d, r9d
0x180032a3b  shr     eax, 10h
0x180032a3e  mov     edx, ebx; cbDest
0x180032a40  movzx   r10d, al
0x180032a44  lea     rbx, g_AddrBuf2
0x180032a4b  mov     eax, r9d
0x180032a4e  shr     r11d, 18h
0x180032a52  mov     dword ptr [rsp+8D8h+var_8A8], r11d
0x180032a57  shr     eax, 8
0x180032a5a  movzx   ecx, al
0x180032a5d  mov     dword ptr [rsp+8D8h+var_8B0], r10d
0x180032a62  mov     dword ptr [rsp+8D8h+ptszFormat], ecx
0x180032a66  mov     rcx, rbx; pszDest
0x180032a69  movzx   r9d, r9b
0x180032a6d  call    StringCbPrintfW
0x180032a72  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180032a79  jge     short loc_180032ABA
0x180032a7b  xor     eax, eax
0x180032a7d  lea     rdx, aWarningPossibl; "WARNING: Possible leaky Local Scope det"...
0x180032a84  mov     r9, rbx
0x180032a87  mov     word ptr [rsp+8D8h+var_868], ax
0x180032a8c  mov     r8, r13
0x180032a8f  lea     rcx, [rsp+8D8h+var_868]
0x180032a94  call    FormatRRASErrorString
0x180032a99  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180032aa0  jge     short loc_180032ABA
0x180032aa2  lea     r8, [rsp+8D8h+var_868]
0x180032aa7  lea     rdx, RasRtrmgrTraceInfo
0x180032aae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032ab5  call    McTemplateU0z_EventWriteTransfer
0x180032aba  mov     rcx, cs:g_hLogHandle; hLogHandle
0x180032ac1  lea     rax, aSS_0; "%S%S"
0x180032ac8  xor     r8d, r8d; dwErrorCode
0x180032acb  mov     [rsp+8D8h+var_8A8], rbx
0x180032ad0  mov     [rsp+8D8h+var_8B0], r13
0x180032ad5  mov     r9d, 4ECEh; dwMessageId
0x180032adb  mov     [rsp+8D8h+ptszFormat], rax; ptszFormat
0x180032ae0  lea     edx, [r8+2]; dwEventType
0x180032ae4  call    cs:__imp_RouterLogEventExW
0x180032aea  mov     rdx, rsi
0x180032aed  mov     rcx, r15
0x180032af0  mov     r13d, 1
0x180032af6  call    CheckForScopeNameMismatch
0x180032afb  movzx   eax, byte ptr [rdi]
0x180032afe  cmp     dword ptr [rdi+rax*8+4], 0
0x180032b03  jnz     short loc_180032B2D
0x180032b05  mov     rcx, r15
0x180032b08  call    MyScopeZoneID
0x180032b0d  movzx   ecx, byte ptr [rdi]
0x180032b10  mov     [rdi+rcx*8+4], eax
0x180032b14  jmp     short loc_180032B2D
0x180032b16  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180032b1d  jmp     loc_180032C25
0x180032b22  xor     r13d, r13d
0x180032b25  mov     rcx, rsi
0x180032b28  call    CheckForScopeRangeMismatch
0x180032b2d  mov     edx, [rsi+0Ch]
0x180032b30  lea     r8, [rsp+8D8h+var_878]
0x180032b35  mov     ecx, [rsi+8]
0x180032b38  call    AssertInZamCache
0x180032b3d  mov     r10, cs:Microsoft_Windows_RRASEnableBits
0x180032b44  test    r10b, r10b
0x180032b47  jns     loc_180032BD8
0x180032b4d  mov     r10d, [rsp+8D8h+var_878]
0x180032b52  xor     eax, eax
0x180032b54  movzx   ecx, byte ptr [rsi+0Bh]
0x180032b58  movzx   edx, byte ptr [rsi+0Ah]
0x180032b5c  movzx   r11d, byte ptr [rsi+0Eh]
0x180032b61  movzx   ebx, byte ptr [rsi+0Dh]
0x180032b65  movzx   r9d, byte ptr [rsi+9]
0x180032b6a  movzx   r8d, byte ptr [rsi+8]
0x180032b6f  mov     [rsp+8D8h+var_888], r10d
0x180032b74  movzx   r10d, byte ptr [rsi+0Fh]
0x180032b79  mov     [rsp+8D8h+var_890], r10d
0x180032b7e  mov     [rsp+8D8h+var_898], r11d
0x180032b83  mov     [rsp+8D8h+var_8A0], ebx
0x180032b87  mov     word ptr [rsp+8D8h+var_868], ax
0x180032b8c  movzx   eax, byte ptr [rsi+0Ch]
0x180032b90  mov     dword ptr [rsp+8D8h+var_8A8], eax
0x180032b94  mov     dword ptr [rsp+8D8h+var_8B0], ecx
0x180032b98  lea     rcx, [rsp+8D8h+var_868]
0x180032b9d  mov     dword ptr [rsp+8D8h+ptszFormat], edx
0x180032ba1  lea     rdx, aZamCacheCheckF; "ZAM Cache check for %d.%d.%d.%d, %d.%d."...
0x180032ba8  call    FormatRRASErrorString
0x180032bad  mov     r10, cs:Microsoft_Windows_RRASEnableBits
0x180032bb4  test    r10b, r10b
0x180032bb7  jns     short loc_180032BD8
0x180032bb9  lea     r8, [rsp+8D8h+var_868]
0x180032bbe  lea     rdx, RasRtrmgrTraceInfo
0x180032bc5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032bcc  call    McTemplateU0z_EventWriteTransfer
0x180032bd1  mov     r10, cs:Microsoft_Windows_RRASEnableBits
0x180032bd8  cmp     [rsp+8D8h+var_878], 0
0x180032bdd  jnz     loc_180032E49
0x180032be3  mov     r11d, cs:g_ipMyLocalZoneID
0x180032bea  test    r13d, r13d
0x180032bed  jnz     short loc_180032C1B
0x180032bef  cmp     r14d, 1
0x180032bf3  jb      short loc_180032C21
0x180032bf5  movzx   eax, byte ptr [rdi]
0x180032bf8  lea     rcx, ds:8[rax*8]
0x180032c00  mov     eax, r14d
0x180032c03  cmp     rax, rcx
0x180032c06  jb      short loc_180032C21
0x180032c08  mov     edx, r11d
0x180032c0b  mov     rcx, rdi
0x180032c0e  call    ZamIncludesZoneID
0x180032c13  test    eax, eax
0x180032c15  jnz     loc_180032E49
0x180032c1b  cmp     r14d, 2
0x180032c1f  jnb     short loc_180032C30
0x180032c21  test    r10b, 80h
0x180032c25  jnz     loc_180032E2F
0x180032c2b  jmp     loc_180032E49
0x180032c30  inc     byte ptr [rdi]
0x180032c32  movzx   eax, byte ptr [rdi]
0x180032c35  cmp     al, [rdi+1]
0x180032c38  jb      loc_180032D46
0x180032c3e  lea     r14, stru_18008C5C0
0x180032c45  mov     qword ptr [rsp+8D8h+SystemTime], 0
0x180032c4e  mov     rcx, r14; Resource
0x180032c51  mov     dl, 1; Wait
0x180032c53  call    cs:__imp_RtlAcquireResourceExclusive
0x180032c59  lea     r15, stru_18008C680
0x180032c60  mov     dl, 1; Wait
0x180032c62  mov     rcx, r15; Resource
0x180032c65  call    cs:__imp_RtlAcquireResourceExclusive
0x180032c6b  mov     rcx, rsi
0x180032c6e  call    FindPendingZLE
0x180032c73  test    rax, rax
0x180032c76  jnz     loc_180032D35
0x180032c7c  call    cs:__imp_rand
0x180032c82  movd    xmm0, eax
0x180032c86  cvtdq2pd xmm0, xmm0
0x180032c8a  divsd   xmm0, cs:__real@40dfffc000000000
0x180032c92  mulsd   xmm0, cs:__real@4070000000000000
0x180032c9a  addsd   xmm0, cs:__real@3ff0000000000000; X
0x180032ca2  call    log_0
0x180032ca7  movaps  xmm7, xmm0
0x180032caa  movsd   xmm0, cs:__real@4070000000000000; X
0x180032cb2  call    log_0
0x180032cb7  mov     rcx, cs:IPRouterHeap; hHeap
0x180032cbe  mov     r8, r12; dwBytes
0x180032cc1  xor     edx, edx; dwFlags
0x180032cc3  movaps  xmm6, xmm0
0x180032cc6  call    cs:__imp_HeapAlloc
  ... truncated ...
```
