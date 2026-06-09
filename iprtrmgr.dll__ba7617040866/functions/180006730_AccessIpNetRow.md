# AccessIpNetRow

- ea: `0x180006730`
- end: `0x180006ac9`
- name: `AccessIpNetRow`
- size: `921`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026794`
- `0x180026c1c`
- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x180006730`
- `0x18000ac60`
- `0x18000baa8`
- `0x18002e814`
- `0x18002f000`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800068ab`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800068ab`
- `ntdll!RtlReleaseResource` at `0x1800069a9`
- `ntdll!RtlReleaseResource` at `0x180006a4a`
- `ntdll!RtlReleaseResource` at `0x180006a70`
- `ntdll!RtlReleaseResource` at `0x180006a7d`
- `ntdll!RtlReleaseResource` at `0x1800069a9`
- `ntdll!RtlReleaseResource` at `0x180006a4a`
- `ntdll!RtlReleaseResource` at `0x180006a70`
- `ntdll!RtlReleaseResource` at `0x180006a7d`
- `ntdll!RtlAcquireResourceShared` at `0x1800068b3`
- `ntdll!RtlAcquireResourceShared` at `0x18000697d`
- `ntdll!RtlAcquireResourceShared` at `0x180006a26`
- `ntdll!RtlAcquireResourceShared` at `0x1800068b3`
- `ntdll!RtlAcquireResourceShared` at `0x18000697d`
- `ntdll!RtlAcquireResourceShared` at `0x180006a26`
- `IPHLPAPI!SetIpNetEntry` at `0x1800069b3`
- `IPHLPAPI!SetIpNetEntry` at `0x180006a54`
- `IPHLPAPI!SetIpNetEntry` at `0x1800069b3`
- `IPHLPAPI!SetIpNetEntry` at `0x180006a54`

## string_xrefs

- `0x180006799`: `AccessIpNetRow`
- `0x180006806`: `Leaving: AccessIpNetRow`
- `0x180006a8c`: `Leaving: AccessIpNetRow`
- `0x180006851`: `AccessIpNetRow: Couldnt update Ip Addr Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessIpNetRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  unsigned int v12; // eax
  DWORD updated; // eax
  DWORD v14; // edi
  char v15; // cl
  bool v16; // zf
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  __int64 v22; // rcx
  __int64 v23; // xmm1_8
  MIB_IPNETROW_LH *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  char *v27; // rax
  __int64 v28; // rcx
  char *v29; // rax
  __int64 v30; // rax
  unsigned int v31; // [rsp+20h] [rbp-868h] BYREF
  __int128 v32; // [rsp+28h] [rbp-860h] BYREF
  __int64 v33; // [rsp+38h] [rbp-850h]
  int v34; // [rsp+40h] [rbp-848h] BYREF
  char v35[2044]; // [rsp+44h] [rbp-844h] BYREF

  v31 = 0;
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v34, L"Entered: %ws", L"AccessIpNetRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v34);
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 != 9 )
  {
    v12 = *a4;
    *a4 = 32;
    if ( v12 < 0x20 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIpNetRow");
      return 122;
    }
    *(_DWORD *)a5 = 10;
  }
  updated = UpdateCache(3, a6);
  v14 = updated;
  if ( updated )
  {
    v15 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v34, L"AccessIpNetRow: Couldnt update Ip Addr Cache. Error %d", updated);
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v34);
        v15 = Microsoft_Windows_RRASEnableBits;
      }
    }
    v16 = v15 >= 0;
    goto LABEL_44;
  }
  if ( a1 <= 4 )
    RtlAcquireResourceShared(&stru_18008C320, 1u);
  else
    RtlAcquireResourceExclusive(&stru_18008C320, 1u);
  v14 = LocateIpNetRow(a1, (a2 >> 2) - 1, a3 + 4, &v31);
  if ( v14 )
  {
    if ( ((a1 - 5) & 0xFFFFFFFD) != 0 )
      goto LABEL_43;
    RtlAcquireResourceShared(&Resource, 1u);
    v30 = InterfaceLookupByIfIndex(*(unsigned int *)(a5 + 8), 1);
    if ( v30 && *(_DWORD *)(v30 + 512) )
    {
      RtlReleaseResource(&Resource);
      v24 = (MIB_IPNETROW_LH *)(a5 + 8);
LABEL_40:
      v14 = SetIpNetEntry(v24);
      if ( !v14 )
        dword_18008C82C = 0;
      goto LABEL_43;
    }
    goto LABEL_42;
  }
  v17 = a1 - 1;
  if ( !v17 || (v18 = v17 - 1) == 0 || (v19 = v18 - 2) == 0 )
  {
    v28 = 3LL * v31;
    v29 = (char *)qword_18008C7F0;
    *(_OWORD *)(a5 + 8) = *(_OWORD *)((char *)qword_18008C7F0 + 24 * v31 + 4);
    *(_QWORD *)(a5 + 24) = *(_QWORD *)&v29[8 * v28 + 20];
    goto LABEL_43;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    if ( (unsigned int)(*(_DWORD *)(a5 + 28) - 3) > 1 )
    {
      v14 = 13;
      goto LABEL_43;
    }
    RtlAcquireResourceShared(&Resource, 1u);
    v25 = InterfaceLookupByIfIndex(*(unsigned int *)(a5 + 8), 1);
    if ( v25 && *(_DWORD *)(v25 + 512) )
    {
      RtlReleaseResource(&Resource);
      v14 = SetIpNetEntry((PMIB_IPNETROW)(a5 + 8));
      if ( !v14 )
      {
        v26 = 3LL * v31;
        v27 = (char *)qword_18008C7F0;
        *(_OWORD *)((char *)qword_18008C7F0 + 8 * v26 + 4) = *(_OWORD *)(a5 + 8);
        *(_QWORD *)&v27[8 * v26 + 20] = *(_QWORD *)(a5 + 24);
      }
      goto LABEL_43;
    }
LABEL_42:
    v14 = 1413;
    RtlReleaseResource(&Resource);
    goto LABEL_43;
  }
  v21 = v20 - 2;
  if ( v21 )
  {
    if ( v21 == 2 )
    {
      v33 = 0;
      v32 = 0;
      v22 = 3LL * v31;
      *((_DWORD *)qword_18008C7F0 + 2 * v22 + 6) = 2;
      v32 = *(_OWORD *)((char *)qword_18008C7F0 + 8 * v22 + 4);
      v23 = *(_QWORD *)((char *)qword_18008C7F0 + 8 * v22 + 20);
      v24 = (MIB_IPNETROW_LH *)&v32;
      v33 = v23;
      goto LABEL_40;
    }
  }
  else
  {
    v14 = 183;
  }
LABEL_43:
  RtlReleaseResource(&stru_18008C320);
  v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_44:
  if ( !v16 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIpNetRow");
  return v14;
}

```

## disassembly

```asm
0x180006730  push    rbx
0x180006732  push    rsi
0x180006733  push    rdi
0x180006734  push    r13
0x180006736  push    r14
0x180006738  push    r15
0x18000673a  sub     rsp, 858h
0x180006741  mov     rax, cs:__security_cookie
0x180006748  xor     rax, rsp
0x18000674b  mov     [rsp+888h+var_48], rax
0x180006753  mov     rsi, [rsp+888h+arg_20]
0x18000675b  mov     r13, r8
0x18000675e  mov     r15, [rsp+888h+arg_28]
0x180006766  mov     r14d, edx
0x180006769  mov     ebx, ecx
0x18000676b  mov     [rsp+888h+var_868], 0
0x180006773  xor     eax, eax
0x180006775  lea     rcx, [rsp+888h+var_844]; void *
0x18000677a  xor     edx, edx; Val
0x18000677c  mov     [rsp+888h+var_848], eax
0x180006780  mov     r8d, 7FCh; Size
0x180006786  mov     rdi, r9
0x180006789  call    memset_0
0x18000678e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180006795  jge     short loc_1800067D7
0x180006797  xor     eax, eax
0x180006799  lea     r8, aAccessipnetrow_0; "AccessIpNetRow"
0x1800067a0  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800067a7  mov     word ptr [rsp+888h+var_848], ax
0x1800067ac  lea     rcx, [rsp+888h+var_848]
0x1800067b1  call    FormatRRASErrorString
0x1800067b6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800067bd  jge     short loc_1800067D7
0x1800067bf  lea     r8, [rsp+888h+var_848]
0x1800067c4  lea     rdx, RasRtrmgrTraceInfo
0x1800067cb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800067d2  call    McTemplateU0z_EventWriteTransfer
0x1800067d7  cmp     [rsp+888h+arg_30], 57h ; 'W'
0x1800067df  jnz     short loc_1800067EB
0x1800067e1  mov     eax, 32h ; '2'
0x1800067e6  jmp     loc_180006AA8
0x1800067eb  cmp     ebx, 9
0x1800067ee  jz      short loc_180006830
0x1800067f0  mov     eax, [rdi]
0x1800067f2  mov     dword ptr [rdi], 20h ; ' '
0x1800067f8  cmp     eax, 20h ; ' '
0x1800067fb  jnb     short loc_18000682A
0x1800067fd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006804  jz      short loc_180006820
0x180006806  lea     r8, aLeavingAccessi_8; "Leaving: AccessIpNetRow"
0x18000680d  lea     rdx, RasRtrmgrTraceInfo
0x180006814  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000681b  call    McTemplateU0z_EventWriteTransfer
0x180006820  mov     eax, 7Ah ; 'z'
0x180006825  jmp     loc_180006AA8
0x18000682a  mov     dword ptr [rsi], 0Ah
0x180006830  mov     rdx, r15
0x180006833  mov     ecx, 3
0x180006838  call    UpdateCache
0x18000683d  mov     edi, eax
0x18000683f  test    eax, eax
0x180006841  jz      short loc_18000689D
0x180006843  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000684a  test    cl, 40h
0x18000684d  jz      short loc_180006895
0x18000684f  xor     ecx, ecx
0x180006851  lea     rdx, aAccessipnetrow; "AccessIpNetRow: Couldnt update Ip Addr "...
0x180006858  mov     word ptr [rsp+888h+var_848], cx
0x18000685d  mov     r8d, eax
0x180006860  lea     rcx, [rsp+888h+var_848]
0x180006865  call    FormatRRASErrorString
0x18000686a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006871  test    cl, 40h
0x180006874  jz      short loc_180006895
0x180006876  lea     r8, [rsp+888h+var_848]
0x18000687b  lea     rdx, RasRtrMgrTraceError
0x180006882  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006889  call    McTemplateU0z_EventWriteTransfer
0x18000688e  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006895  test    cl, 80h
0x180006898  jmp     loc_180006A8A
0x18000689d  lea     rcx, stru_18008C320; Resource
0x1800068a4  mov     dl, 1; Wait
0x1800068a6  cmp     ebx, 4
0x1800068a9  jbe     short loc_1800068B3
0x1800068ab  call    cs:__imp_RtlAcquireResourceExclusive
0x1800068b1  jmp     short loc_1800068B9
0x1800068b3  call    cs:__imp_RtlAcquireResourceShared
0x1800068b9  shr     r14d, 2
0x1800068bd  lea     r8, [r13+4]
0x1800068c1  lea     r9, [rsp+888h+var_868]
0x1800068c6  mov     ecx, ebx
0x1800068c8  lea     edx, [r14-1]
0x1800068cc  call    LocateIpNetRow
0x1800068d1  mov     edi, eax
0x1800068d3  test    eax, eax
0x1800068d5  jnz     loc_180006A10
0x1800068db  sub     ebx, 1
0x1800068de  jz      loc_1800069EB
0x1800068e4  sub     ebx, 1
0x1800068e7  jz      loc_1800069EB
0x1800068ed  lea     edx, [rax+2]
0x1800068f0  sub     ebx, edx
0x1800068f2  jz      loc_1800069EB
0x1800068f8  sub     ebx, 1
0x1800068fb  jz      short loc_18000695C
0x1800068fd  sub     ebx, edx
0x1800068ff  jz      short loc_180006952
0x180006901  cmp     ebx, edx
0x180006903  jnz     loc_180006A76
0x180006909  xor     eax, eax
0x18000690b  xorps   xmm0, xmm0
0x18000690e  mov     [rsp+888h+var_850], rax
0x180006913  mov     eax, [rsp+888h+var_868]
0x180006917  movups  [rsp+888h+var_860], xmm0
0x18000691c  lea     rcx, [rax+rax*2]
0x180006920  mov     rax, cs:qword_18008C7F0
0x180006927  mov     [rax+rcx*8+18h], edx
0x18000692b  mov     rax, cs:qword_18008C7F0
0x180006932  movups  xmm0, xmmword ptr [rax+rcx*8+4]
0x180006937  movups  [rsp+888h+var_860], xmm0
0x18000693c  movsd   xmm1, qword ptr [rax+rcx*8+14h]
0x180006942  lea     rcx, [rsp+888h+var_860]
0x180006947  movsd   [rsp+888h+var_850], xmm1
0x18000694d  jmp     loc_180006A54
0x180006952  mov     edi, 0B7h
0x180006957  jmp     loc_180006A76
0x18000695c  mov     eax, [rsi+1Ch]
0x18000695f  sub     eax, 3
0x180006962  cmp     eax, 1
0x180006965  jbe     short loc_180006971
0x180006967  mov     edi, 0Dh
0x18000696c  jmp     loc_180006A76
0x180006971  lea     rbx, Resource
0x180006978  mov     dl, 1; Wait
0x18000697a  mov     rcx, rbx; Resource
0x18000697d  call    cs:__imp_RtlAcquireResourceShared
0x180006983  mov     ecx, [rsi+8]
0x180006986  mov     edx, 1
0x18000698b  call    InterfaceLookupByIfIndex
0x180006990  test    rax, rax
0x180006993  jz      loc_180006A68
0x180006999  cmp     dword ptr [rax+200h], 0
0x1800069a0  jz      loc_180006A68
0x1800069a6  mov     rcx, rbx; Resource
0x1800069a9  call    cs:__imp_RtlReleaseResource
0x1800069af  lea     rcx, [rsi+8]; pArpEntry
0x1800069b3  call    cs:__imp_SetIpNetEntry
0x1800069b9  mov     edi, eax
0x1800069bb  test    eax, eax
0x1800069bd  jnz     loc_180006A76
0x1800069c3  mov     eax, [rsp+888h+var_868]
0x1800069c7  movups  xmm0, xmmword ptr [rsi+8]
0x1800069cb  lea     rcx, [rax+rax*2]
0x1800069cf  mov     rax, cs:qword_18008C7F0
0x1800069d6  movups  xmmword ptr [rax+rcx*8+4], xmm0
0x1800069db  movsd   xmm1, qword ptr [rsi+18h]
0x1800069e0  movsd   qword ptr [rax+rcx*8+14h], xmm1
0x1800069e6  jmp     loc_180006A76
0x1800069eb  mov     eax, [rsp+888h+var_868]
0x1800069ef  lea     rcx, [rax+rax*2]
0x1800069f3  mov     rax, cs:qword_18008C7F0
0x1800069fa  movups  xmm0, xmmword ptr [rax+rcx*8+4]
0x1800069ff  movups  xmmword ptr [rsi+8], xmm0
0x180006a03  movsd   xmm1, qword ptr [rax+rcx*8+14h]
0x180006a09  movsd   qword ptr [rsi+18h], xmm1
0x180006a0e  jmp     short loc_180006A76
0x180006a10  lea     eax, [rbx-5]
0x180006a13  test    eax, 0FFFFFFFDh
0x180006a18  jnz     short loc_180006A76
0x180006a1a  lea     rbx, Resource
0x180006a21  mov     dl, 1; Wait
0x180006a23  mov     rcx, rbx; Resource
0x180006a26  call    cs:__imp_RtlAcquireResourceShared
0x180006a2c  mov     ecx, [rsi+8]
0x180006a2f  mov     edx, 1
0x180006a34  call    InterfaceLookupByIfIndex
0x180006a39  test    rax, rax
0x180006a3c  jz      short loc_180006A68
0x180006a3e  cmp     dword ptr [rax+200h], 0
0x180006a45  jz      short loc_180006A68
0x180006a47  mov     rcx, rbx; Resource
0x180006a4a  call    cs:__imp_RtlReleaseResource
0x180006a50  lea     rcx, [rsi+8]; pArpEntry
0x180006a54  call    cs:__imp_SetIpNetEntry
0x180006a5a  mov     edi, eax
0x180006a5c  test    eax, eax
0x180006a5e  jnz     short loc_180006A76
0x180006a60  mov     cs:dword_18008C82C, eax
0x180006a66  jmp     short loc_180006A76
0x180006a68  mov     rcx, rbx; Resource
0x180006a6b  mov     edi, 585h
0x180006a70  call    cs:__imp_RtlReleaseResource
0x180006a76  lea     rcx, stru_18008C320; Resource
0x180006a7d  call    cs:__imp_RtlReleaseResource
0x180006a83  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006a8a  jz      short loc_180006AA6
0x180006a8c  lea     r8, aLeavingAccessi_8; "Leaving: AccessIpNetRow"
0x180006a93  lea     rdx, RasRtrmgrTraceInfo
0x180006a9a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006aa1  call    McTemplateU0z_EventWriteTransfer
0x180006aa6  mov     eax, edi
0x180006aa8  mov     rcx, [rsp+888h+var_48]
0x180006ab0  xor     rcx, rsp; StackCookie
0x180006ab3  call    __security_check_cookie
0x180006ab8  add     rsp, 858h
0x180006abf  pop     r15
0x180006ac1  pop     r14
0x180006ac3  pop     r13
0x180006ac5  pop     rdi
0x180006ac6  pop     rsi
0x180006ac7  pop     rbx
0x180006ac8  retn
```
