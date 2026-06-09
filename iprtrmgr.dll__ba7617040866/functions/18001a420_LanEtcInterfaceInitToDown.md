# LanEtcInterfaceInitToDown

- ea: `0x18001a420`
- end: `0x18001a825`
- name: `LanEtcInterfaceInitToDown`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022f60`

## callees

- `0x180011790`
- `0x1800177cc`
- `0x18001a420`
- `0x18001afb0`
- `0x1800401a0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a69f`
- `KERNEL32!HeapFree` at `0x18001a7fd`
- `KERNEL32!HeapFree` at `0x18001a69f`
- `KERNEL32!HeapFree` at `0x18001a7fd`
- `IPHLPAPI!SetIfEntry` at `0x18001a6bc`
- `IPHLPAPI!SetIfEntry` at `0x18001a6bc`

## string_xrefs

- `0x18001a5e4`: `LanInterfaceInitToDown: Error %d reading IP Address information for interface %ws`

## pseudocode

```c
__int64 __fastcall LanEtcInterfaceInitToDown(__int64 a1)
{
  char v2; // al
  __int128 *v3; // r9
  bool v4; // zf
  unsigned int v5; // esi
  __int64 *v6; // rdx
  __int128 *v7; // r9
  unsigned int v9; // eax
  __int64 v10; // r9
  unsigned __int8 *v11; // rdi
  unsigned int v12; // esi
  IF_INDEX v13; // esi
  DWORD v14; // edi
  __int64 v15; // r8
  __int128 *v16; // r9
  __int64 v17; // r8
  __int128 *v18; // r9
  __int64 v19; // [rsp+20h] [rbp-C18h]
  __int64 v20; // [rsp+20h] [rbp-C18h]
  __int64 v21; // [rsp+28h] [rbp-C10h]
  unsigned int v22; // [rsp+40h] [rbp-BF8h] BYREF
  int v23; // [rsp+44h] [rbp-BF4h] BYREF
  int v24; // [rsp+48h] [rbp-BF0h] BYREF
  int v25; // [rsp+4Ch] [rbp-BECh] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-BE8h] BYREF
  __int128 v27; // [rsp+58h] [rbp-BE0h] BYREF
  struct _MIB_IFROW pIfRow; // [rsp+70h] [rbp-BC8h] BYREF
  int v29; // [rsp+3D0h] [rbp-868h] BYREF
  __int128 v30; // [rsp+3D4h] [rbp-864h]
  __int128 v31; // [rsp+3E4h] [rbp-854h]
  int v32; // [rsp+3F4h] [rbp-844h]
  int v33; // [rsp+400h] [rbp-838h] BYREF
  _BYTE v34[2044]; // [rsp+404h] [rbp-834h] BYREF

  v23 = -1;
  v25 = 0;
  v24 = 0;
  memset_0(&pIfRow, 0, sizeof(pIfRow));
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v29 = 0;
  v32 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  LOBYTE(v22) = Microsoft_Windows_RRASEnableBits & 0x80;
  v30 = 0;
  v31 = 0;
  v27 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = &v27;
    LOWORD(v29) = 0;
    if ( a1 != -688 )
      LODWORD(v3) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"LanInterfaceInitToDown",
      (_DWORD)v3,
      *(_QWORD *)(a1 + 72),
      (__int64)&v29);
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  v4 = *(_DWORD *)(a1 + 516) == 0;
  v22 = 0;
  lpMem = 0;
  if ( v4 )
  {
    v5 = 87;
    if ( v2 < 0 )
    {
      LOWORD(v33) = 0;
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v33, L"LanInterfaceInitToDown: Function called for Ipv6. Returning %d", 87);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = RasRtrmgrParamTraceInfo;
        v20 = *(_QWORD *)(a1 + 72);
LABEL_9:
        v7 = &v27;
        if ( a1 != -688 )
          LODWORD(v7) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v6,
          (unsigned int)&v33,
          (_DWORD)v7,
          v20,
          (__int64)&v29);
        return v5;
      }
    }
    return v5;
  }
  v9 = ReadAddressFromRegistry(*(wchar_t **)(a1 + 72), (BYTE *)&v22, &lpMem);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 != 232 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v10 = *(_QWORD *)(a1 + 72);
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        FormatRRASErrorString(
          &v33,
          L"LanInterfaceInitToDown: Error %d reading IP Address information for interface %ws",
          v9,
          v10);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v6 = RasRtrMgrParamTraceError;
          v20 = *(_QWORD *)(a1 + 72);
          goto LABEL_9;
        }
      }
      return v5;
    }
    return 0;
  }
  else
  {
    v11 = (unsigned __int8 *)lpMem;
    v12 = 0;
    if ( !v22 )
      goto LABEL_39;
    do
    {
      if ( !(unsigned int)GetAdapterInfoV4(
                            *(_DWORD *)&v11[28 * v12],
                            *(_DWORD *)(a1 + 704),
                            (unsigned int)&v23,
                            (unsigned int)&v25,
                            (__int64)&v24) )
        break;
      ++v12;
    }
    while ( v12 < v22 );
    v13 = v23;
    if ( v23 != -1 && v23 == *(_DWORD *)(a1 + 16) )
    {
      HeapFree(IPRouterHeap, 0, v11);
      pIfRow.dwIndex = v13;
      pIfRow.dwAdminStatus = 2;
      v14 = SetIfEntry(&pIfRow);
      if ( v14 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v15 = *(_QWORD *)(a1 + 72);
          LOWORD(v33) = 0;
          LOWORD(v29) = 0;
          FormatRRASErrorString(&v33, L"LanInterfaceInitToDown: Couldnt set IFEntry for %ws", v15);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v16 = &v27;
            if ( a1 != -688 )
              LODWORD(v16) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v33,
              (_DWORD)v16,
              *(_QWORD *)(a1 + 72),
              (__int64)&v29);
          }
        }
      }
      DeleteAllRoutes(a1, 0);
      return v14;
    }
    else
    {
LABEL_39:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v17 = *(_QWORD *)(a1 + 72);
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        LODWORD(v21) = v11[2];
        LODWORD(v19) = v11[1];
        FormatRRASErrorString(
          &v33,
          L"LanInterfaceInitToDown: Couldnt find adapter index for interface %ws using %d.%d.%d.%d",
          v17,
          *v11,
          v19,
          v21,
          v11[3]);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v18 = &v27;
          if ( a1 != -688 )
            LODWORD(v18) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v33,
            (_DWORD)v18,
            *(_QWORD *)(a1 + 72),
            (__int64)&v29);
        }
      }
      HeapFree(IPRouterHeap, 0, v11);
      return 1003;
    }
  }
}

```

## disassembly

```asm
0x18001a420  push    rbx
0x18001a422  push    rsi
0x18001a423  push    rdi
0x18001a424  push    r12
0x18001a426  sub     rsp, 0C18h
0x18001a42d  mov     rax, cs:__security_cookie
0x18001a434  xor     rax, rsp
0x18001a437  mov     [rsp+0C38h+var_38], rax
0x18001a43f  mov     rbx, rcx
0x18001a442  mov     dword ptr [rsp+0C38h+var_BF8+4], 0FFFFFFFFh
0x18001a44a  lea     rcx, [rsp+0C38h+pIfRow]; void *
0x18001a44f  mov     [rsp+0C38h+var_BEC], 0
0x18001a457  xor     edx, edx; Val
0x18001a459  mov     [rsp+0C38h+var_BF0], 0
0x18001a461  mov     r8d, 35Ch; Size
0x18001a467  call    memset_0
0x18001a46c  xor     eax, eax
0x18001a46e  lea     rcx, [rsp+0C38h+var_834]; void *
0x18001a476  xor     edx, edx; Val
0x18001a478  mov     [rsp+0C38h+var_838], eax
0x18001a47f  mov     r8d, 7FCh; Size
0x18001a485  call    memset_0
0x18001a48a  xor     eax, eax
0x18001a48c  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001a493  xorps   xmm0, xmm0
0x18001a496  mov     [rsp+0C38h+var_868], eax
0x18001a49d  mov     [rsp+0C38h+var_844], eax
0x18001a4a4  lea     rdi, [rbx+2B0h]
0x18001a4ab  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001a4b2  mov     cl, al
0x18001a4b4  and     cl, 80h
0x18001a4b7  mov     byte ptr [rsp+0C38h+var_BF8], cl
0x18001a4bb  movups  [rsp+0C38h+var_864], xmm0
0x18001a4c3  movups  [rsp+0C38h+var_854], xmm0
0x18001a4cb  movups  [rsp+0C38h+var_BE0], xmm0
0x18001a4d0  jz      short loc_18001A51B
0x18001a4d2  xor     eax, eax
0x18001a4d4  lea     r9, [rsp+0C38h+var_BE0]
0x18001a4d9  mov     word ptr [rsp+0C38h+var_868], ax
0x18001a4e1  lea     r8, aLaninterfacein_1; "LanInterfaceInitToDown"
0x18001a4e8  lea     rax, [rsp+0C38h+var_868]
0x18001a4f0  test    rdi, rdi
0x18001a4f3  mov     [rsp+0C38h+var_C10], rax
0x18001a4f8  lea     rdx, RasRtrmgrParamTraceInfo
0x18001a4ff  mov     rax, [rbx+48h]
0x18001a503  cmovnz  r9, rdi
0x18001a507  mov     rcx, r12
0x18001a50a  mov     [rsp+0C38h+var_C18], rax
0x18001a50f  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a514  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001a51b  cmp     dword ptr [rbx+204h], 0
0x18001a522  mov     dword ptr [rsp+0C38h+var_BF8], 0
0x18001a52a  mov     [rsp+0C38h+lpMem], 0
0x18001a533  jnz     short loc_18001A5B0
0x18001a535  mov     esi, 57h ; 'W'
0x18001a53a  test    al, al
0x18001a53c  jns     short loc_18001A5A9
0x18001a53e  xor     eax, eax
0x18001a540  lea     rdx, aLaninterfacein_3; "LanInterfaceInitToDown: Function called"...
0x18001a547  mov     r8d, esi
0x18001a54a  mov     word ptr [rsp+0C38h+var_838], ax
0x18001a552  lea     rcx, [rsp+0C38h+var_838]
0x18001a55a  mov     word ptr [rsp+0C38h+var_868], ax
0x18001a562  call    FormatRRASErrorString
0x18001a567  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001a56e  jge     short loc_18001A5A9
0x18001a570  lea     rcx, [rsp+0C38h+var_868]
0x18001a578  mov     [rsp+0C38h+var_C10], rcx
0x18001a57d  lea     rdx, RasRtrmgrParamTraceInfo
0x18001a584  mov     rcx, [rbx+48h]
0x18001a588  mov     [rsp+0C38h+var_C18], rcx
0x18001a58d  test    rdi, rdi
0x18001a590  lea     r9, [rsp+0C38h+var_BE0]
0x18001a595  lea     r8, [rsp+0C38h+var_838]
0x18001a59d  mov     rcx, r12
0x18001a5a0  cmovnz  r9, rdi
0x18001a5a4  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a5a9  mov     eax, esi
0x18001a5ab  jmp     loc_18001A808
0x18001a5b0  mov     rcx, [rbx+48h]; Source
0x18001a5b4  lea     r8, [rsp+0C38h+lpMem]; __int64
0x18001a5b9  lea     rdx, [rsp+0C38h+var_BF8]; __int64
0x18001a5be  call    ReadAddressFromRegistry
0x18001a5c3  mov     esi, eax
0x18001a5c5  test    eax, eax
0x18001a5c7  jz      short loc_18001A638
0x18001a5c9  cmp     eax, 0E8h
0x18001a5ce  jnz     short loc_18001A5D7
0x18001a5d0  xor     eax, eax
0x18001a5d2  jmp     loc_18001A808
0x18001a5d7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001a5de  jz      short loc_18001A5A9
0x18001a5e0  mov     r9, [rbx+48h]
0x18001a5e4  lea     rdx, aLaninterfacein; "LanInterfaceInitToDown: Error %d readin"...
0x18001a5eb  xor     eax, eax
0x18001a5ed  lea     rcx, [rsp+0C38h+var_838]
0x18001a5f5  mov     r8d, esi
0x18001a5f8  mov     word ptr [rsp+0C38h+var_838], ax
0x18001a600  mov     word ptr [rsp+0C38h+var_868], ax
0x18001a608  call    FormatRRASErrorString
0x18001a60d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001a614  jz      short loc_18001A5A9
0x18001a616  lea     rax, [rsp+0C38h+var_868]
0x18001a61e  mov     [rsp+0C38h+var_C10], rax
0x18001a623  lea     rdx, RasRtrMgrParamTraceError
0x18001a62a  mov     rax, [rbx+48h]
0x18001a62e  mov     [rsp+0C38h+var_C18], rax
0x18001a633  jmp     loc_18001A58D
0x18001a638  mov     rdi, [rsp+0C38h+lpMem]
0x18001a63d  xor     esi, esi
0x18001a63f  cmp     dword ptr [rsp+0C38h+var_BF8], esi
0x18001a643  jbe     loc_18001A755
0x18001a649  mov     edx, [rbx+2C0h]
0x18001a64f  lea     r9, [rsp+0C38h+var_BEC]
0x18001a654  mov     eax, esi
0x18001a656  lea     r8, [rsp+0C38h+var_BF8+4]
0x18001a65b  imul    rcx, rax, 1Ch
0x18001a65f  lea     rax, [rsp+0C38h+var_BF0]
0x18001a664  mov     [rsp+0C38h+var_C18], rax
0x18001a669  mov     ecx, [rcx+rdi]
0x18001a66c  call    GetAdapterInfoV4
0x18001a671  test    eax, eax
0x18001a673  jz      short loc_18001A67D
0x18001a675  inc     esi
0x18001a677  cmp     esi, dword ptr [rsp+0C38h+var_BF8]
0x18001a67b  jb      short loc_18001A649
0x18001a67d  mov     esi, dword ptr [rsp+0C38h+var_BF8+4]
0x18001a681  cmp     esi, 0FFFFFFFFh
0x18001a684  jz      loc_18001A755
0x18001a68a  cmp     esi, [rbx+10h]
0x18001a68d  jnz     loc_18001A755
0x18001a693  mov     rcx, cs:IPRouterHeap; hHeap
0x18001a69a  mov     r8, rdi; lpMem
0x18001a69d  xor     edx, edx; dwFlags
0x18001a69f  call    cs:__imp_HeapFree
0x18001a6a5  lea     rcx, [rsp+0C38h+pIfRow]; pIfRow
0x18001a6aa  mov     [rsp+0C38h+pIfRow.dwIndex], esi
0x18001a6b1  mov     [rsp+0C38h+pIfRow.dwAdminStatus], 2
0x18001a6bc  call    cs:__imp_SetIfEntry
0x18001a6c2  mov     edi, eax
0x18001a6c4  test    eax, eax
0x18001a6c6  jz      short loc_18001A744
0x18001a6c8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001a6cf  jge     short loc_18001A744
0x18001a6d1  mov     r8, [rbx+48h]
0x18001a6d5  lea     rdx, aLaninterfacein_2; "LanInterfaceInitToDown: Couldnt set IFE"...
0x18001a6dc  xor     ecx, ecx
0x18001a6de  mov     word ptr [rsp+0C38h+var_838], cx
0x18001a6e6  mov     word ptr [rsp+0C38h+var_868], cx
0x18001a6ee  lea     rcx, [rsp+0C38h+var_838]
0x18001a6f6  call    FormatRRASErrorString
0x18001a6fb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001a702  jge     short loc_18001A744
0x18001a704  lea     rax, [rbx+2B0h]
0x18001a70b  mov     rcx, r12
0x18001a70e  test    rax, rax
0x18001a711  lea     r9, [rsp+0C38h+var_BE0]
0x18001a716  lea     r8, [rsp+0C38h+var_838]
0x18001a71e  cmovnz  r9, rax
0x18001a722  lea     rdx, RasRtrmgrParamTraceInfo
0x18001a729  lea     rax, [rsp+0C38h+var_868]
0x18001a731  mov     [rsp+0C38h+var_C10], rax
0x18001a736  mov     rax, [rbx+48h]
0x18001a73a  mov     [rsp+0C38h+var_C18], rax
0x18001a73f  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a744  xor     edx, edx
0x18001a746  mov     rcx, rbx
0x18001a749  call    DeleteAllRoutes
0x18001a74e  mov     eax, edi
0x18001a750  jmp     loc_18001A808
0x18001a755  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001a75c  jge     loc_18001A7F1
0x18001a762  mov     r8, [rbx+48h]
0x18001a766  xor     eax, eax
0x18001a768  mov     word ptr [rsp+0C38h+var_838], ax
0x18001a770  mov     word ptr [rsp+0C38h+var_868], ax
0x18001a778  movzx   ecx, byte ptr [rdi+2]
0x18001a77c  movzx   edx, byte ptr [rdi+1]
0x18001a780  movzx   eax, byte ptr [rdi+3]
0x18001a784  movzx   r9d, byte ptr [rdi]
0x18001a788  mov     [rsp+0C38h+var_C08], eax
0x18001a78c  mov     dword ptr [rsp+0C38h+var_C10], ecx
0x18001a790  lea     rcx, [rsp+0C38h+var_838]
0x18001a798  mov     dword ptr [rsp+0C38h+var_C18], edx
0x18001a79c  lea     rdx, aLaninterfacein_0; "LanInterfaceInitToDown: Couldnt find ad"...
0x18001a7a3  call    FormatRRASErrorString
0x18001a7a8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001a7af  jge     short loc_18001A7F1
0x18001a7b1  lea     rax, [rbx+2B0h]
0x18001a7b8  mov     rcx, r12
0x18001a7bb  test    rax, rax
0x18001a7be  lea     r9, [rsp+0C38h+var_BE0]
0x18001a7c3  lea     r8, [rsp+0C38h+var_838]
0x18001a7cb  cmovnz  r9, rax
0x18001a7cf  lea     rdx, RasRtrmgrParamTraceInfo
0x18001a7d6  lea     rax, [rsp+0C38h+var_868]
0x18001a7de  mov     [rsp+0C38h+var_C10], rax
0x18001a7e3  mov     rax, [rbx+48h]
0x18001a7e7  mov     [rsp+0C38h+var_C18], rax
0x18001a7ec  call    McTemplateU0zjzz_EventWriteTransfer
0x18001a7f1  mov     rcx, cs:IPRouterHeap; hHeap
0x18001a7f8  mov     r8, rdi; lpMem
0x18001a7fb  xor     edx, edx; dwFlags
0x18001a7fd  call    cs:__imp_HeapFree
0x18001a803  mov     eax, 3EBh
0x18001a808  mov     rcx, [rsp+0C38h+var_38]
0x18001a810  xor     rcx, rsp; StackCookie
0x18001a813  call    __security_check_cookie
0x18001a818  add     rsp, 0C18h
0x18001a81f  pop     r12
0x18001a821  pop     rdi
0x18001a822  pop     rsi
0x18001a823  pop     rbx
0x18001a824  retn
```
