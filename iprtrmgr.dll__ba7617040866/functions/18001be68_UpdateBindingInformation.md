# UpdateBindingInformation

- ea: `0x18001be68`
- end: `0x18001c50b`
- name: `UpdateBindingInformation`
- size: `1699`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800125dc`
- `0x180018be4`
- `0x18001a110`

## callees

- `0x180011790`
- `0x1800180b4`
- `0x180018530`
- `0x18001be68`
- `0x18002ebd4`
- `0x18002f06c`
- `0x18003e450`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180058600`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18001c30b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001c30b`
- `ntdll!RtlReleaseResource` at `0x18001c4d6`
- `ntdll!RtlReleaseResource` at `0x18001c4d6`
- `KERNEL32!HeapFree` at `0x18001c2f1`
- `KERNEL32!HeapFree` at `0x18001c4c9`
- `KERNEL32!HeapFree` at `0x18001c2f1`
- `KERNEL32!HeapFree` at `0x18001c4c9`

## string_xrefs

- `0x18001bf2b`: `UpdateBindingInformation`
- `0x18001bf82`: `UpdateBindingInformation: %ws is type %d so not updating binding information`
- `0x18001c073`: `UpdateBindingInformation: Error %d getting IP info for interface %ws`
- `0x18001c1bb`: `UpdateBindingInformation: Address %d.%d.%d.%d existed on %ws earlier, but is now absent`
- `0x18001c437`: `UpdateBindingInformation: Address %d.%d.%d.%d/%d.%d.%d.%d new for %ws`

## pseudocode

```c
__int64 __fastcall UpdateBindingInformation(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v2; // rsi
  char v3; // al
  __int128 *v4; // r9
  __int64 v5; // r8
  __int128 *v6; // r9
  char *v7; // r15
  unsigned int v8; // r13d
  NET_IF_COMPARTMENT_ID v9; // edx
  unsigned int v10; // ecx
  unsigned int IpInfoForInterface; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int128 *v14; // r9
  unsigned int v16; // r14d
  int v17; // r12d
  char *v18; // rbx
  unsigned int v19; // ecx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int128 *v22; // r9
  unsigned int v23; // ecx
  unsigned int v24; // r8d
  __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  bool v28; // zf
  __int64 v29; // rax
  unsigned int i; // r12d
  __int64 v31; // r14
  int v32; // edx
  unsigned int j; // ecx
  __int64 v34; // rax
  __int128 *v35; // r9
  __int64 v36; // [rsp+20h] [rbp-1108h]
  __int64 v37; // [rsp+28h] [rbp-1100h]
  __int64 v38; // [rsp+30h] [rbp-10F8h]
  __int64 v39; // [rsp+38h] [rbp-10F0h]
  __int64 v40; // [rsp+40h] [rbp-10E8h]
  __int64 v41; // [rsp+48h] [rbp-10E0h]
  unsigned int v42; // [rsp+60h] [rbp-10C8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-10C0h] BYREF
  int v44; // [rsp+70h] [rbp-10B8h] BYREF
  _DWORD v45[3]; // [rsp+74h] [rbp-10B4h] BYREF
  __int64 v46; // [rsp+80h] [rbp-10A8h]
  int v47; // [rsp+88h] [rbp-10A0h]
  __int128 v48; // [rsp+8Ch] [rbp-109Ch]
  __int128 v49; // [rsp+9Ch] [rbp-108Ch]
  int v50; // [rsp+ACh] [rbp-107Ch]
  int v51; // [rsp+B0h] [rbp-1078h]
  _BYTE v52[2044]; // [rsp+B4h] [rbp-1074h] BYREF
  __int128 v53; // [rsp+8B0h] [rbp-878h] BYREF
  int v54; // [rsp+8C0h] [rbp-868h] BYREF
  __int128 v55; // [rsp+8C4h] [rbp-864h]
  __int128 v56; // [rsp+8D4h] [rbp-854h]
  int v57; // [rsp+8E4h] [rbp-844h]
  int v58; // [rsp+8F0h] [rbp-838h] BYREF
  _BYTE v59[2044]; // [rsp+8F4h] [rbp-834h] BYREF

  v1 = 0;
  v46 = a1;
  v2 = a1;
  v42 = 0;
  lpMem = 0;
  v44 = 0;
  v45[0] = 0;
  v58 = 0;
  memset_0(v59, 0, sizeof(v59));
  v54 = 0;
  v57 = 0;
  v3 = Microsoft_Windows_RRASEnableBits;
  v55 = 0;
  v56 = 0;
  v53 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v54) = 0;
    v4 = &v53;
    if ( v2 != -688 )
      LODWORD(v4) = v2 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"UpdateBindingInformation",
      (_DWORD)v4,
      *(_QWORD *)(v2 + 72),
      (__int64)&v54);
    v3 = Microsoft_Windows_RRASEnableBits;
  }
  if ( (unsigned int)(*(_DWORD *)(v2 + 144) - 3) > 1 )
  {
    if ( v3 < 0 )
    {
      v5 = *(_QWORD *)(v2 + 72);
      LOWORD(v58) = 0;
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v58, L"UpdateBindingInformation: %ws is type %d so not updating binding information", v5);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = &v53;
        if ( v2 != -688 )
          LODWORD(v6) = v2 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v58,
          (_DWORD)v6,
          *(_QWORD *)(v2 + 72),
          (__int64)&v54);
      }
    }
    return 1227;
  }
  v7 = *(char **)(v2 + 712);
  v8 = *(_DWORD *)(v2 + 668);
  v9 = *(_DWORD *)(v2 + 704);
  v10 = *(_DWORD *)(v2 + 16);
  v42 = 0;
  lpMem = 0;
  if ( *(_DWORD *)(v2 + 516) )
    IpInfoForInterface = GetIpInfoForInterface(
                           v10,
                           v9,
                           (unsigned int)&v42,
                           (unsigned int)&lpMem,
                           (__int64)&v44,
                           (__int64)v45);
  else
    IpInfoForInterface = GetIpv6InfoForInterface(v10, v9, &v42, &lpMem);
  v12 = IpInfoForInterface;
  if ( IpInfoForInterface )
  {
    if ( IpInfoForInterface == 232 )
    {
      if ( !*(_DWORD *)(v2 + 668) )
        return 1227;
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v13 = *(_QWORD *)(v2 + 72);
      LOWORD(v58) = 0;
      LOWORD(v54) = 0;
      FormatRRASErrorString(
        &v58,
        L"UpdateBindingInformation: Error %d getting IP info for interface %ws",
        IpInfoForInterface,
        v13);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v14 = &v53;
        if ( v2 != -688 )
          LODWORD(v14) = v2 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v58,
          (_DWORD)v14,
          *(_QWORD *)(v2 + 72),
          (__int64)&v54);
      }
    }
    return v12;
  }
  *(_DWORD *)(v2 + 512) = 1;
  if ( !*(_DWORD *)(v2 + 516) )
    goto LABEL_59;
  v16 = v42;
  v17 = 0;
  v18 = (char *)lpMem;
  while ( v1 < v8 )
  {
    v19 = 0;
    v20 = 28LL * v1;
    while ( v19 < v16 )
    {
      v21 = 28LL * v19;
      if ( *(_DWORD *)&v7[v20] == *(_DWORD *)&v18[v21] && *(_DWORD *)&v7[v20 + 4] == *(_DWORD *)&v18[v21 + 4] )
        goto LABEL_40;
      ++v19;
    }
    v17 = 1;
    if ( *(_DWORD *)(v2 + 516) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v58) = 0;
        LOWORD(v54) = 0;
        LODWORD(v37) = (unsigned __int8)v7[v20 + 3];
        LODWORD(v36) = (unsigned __int8)v7[v20 + 2];
        FormatRRASErrorString(
          &v58,
          L"UpdateBindingInformation: Address %d.%d.%d.%d existed on %ws earlier, but is now absent",
          (unsigned __int8)v7[v20],
          (unsigned __int8)v7[v20 + 1],
          v36,
          v37,
          *(_QWORD *)(v2 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v22 = &v53;
          if ( v2 != -688 )
            LODWORD(v22) = v2 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v58,
            (_DWORD)v22,
            *(_QWORD *)(v2 + 72),
            (__int64)&v54);
        }
        v18 = (char *)lpMem;
        v16 = v42;
      }
      v51 = 0;
      memset_0(v52, 0, sizeof(v52));
      v47 = 0;
      v48 = 0;
      v50 = 0;
      v49 = 0;
    }
LABEL_40:
    ++v1;
  }
  v23 = 0;
  if ( !v16 )
    goto LABEL_55;
  do
  {
    v24 = 0;
    v25 = 28LL * v23;
    while ( v24 < v8 )
    {
      v26 = 28LL * v24;
      v27 = *(_DWORD *)&v7[v26];
      if ( *(_DWORD *)(v2 + 516) )
      {
        if ( *(_DWORD *)&v18[v25] != v27 )
          goto LABEL_52;
        v28 = *(_DWORD *)&v18[v25 + 4] == *(_DWORD *)&v7[v26 + 4];
      }
      else
      {
        if ( *(_DWORD *)&v18[v25] != v27 )
          goto LABEL_52;
        v29 = *(_QWORD *)&v18[v25 + 4] - *(_QWORD *)&v7[v26 + 4];
        if ( !v29 )
          v29 = *(_QWORD *)&v18[v25 + 12] - *(_QWORD *)&v7[v26 + 12];
        v28 = v29 == 0;
      }
      if ( v28 )
        goto LABEL_54;
LABEL_52:
      ++v24;
    }
    v17 = 1;
LABEL_54:
    ++v23;
  }
  while ( v23 < v16 );
LABEL_55:
  if ( v17 )
  {
LABEL_59:
    RtlAcquireResourceExclusive(&stru_18008C500, 1u);
    if ( v7 )
      RemoveBinding(v2);
    *(_QWORD *)(v2 + 712) = lpMem;
    *(_DWORD *)(v2 + 668) = v42;
    if ( *(_DWORD *)(v2 + 516) )
    {
      *(_DWORD *)(v2 + 524) = v44;
      *(_DWORD *)(v2 + 528) = v45[0];
    }
    AddBinding(v2);
    if ( *(_DWORD *)(v2 + 516) )
    {
      for ( i = 0; i < v42; ++i )
      {
        v31 = 28LL * i;
        if ( !v8 )
          goto LABEL_84;
        v32 = 0;
        for ( j = 0; j < v8; ++j )
        {
          v34 = 28LL * j;
          if ( *(_DWORD *)((char *)lpMem + v31) == *(_DWORD *)&v7[v34]
            && *(_DWORD *)((char *)lpMem + v31 + 4) == *(_DWORD *)&v7[v34 + 4] )
          {
            v32 = 1;
          }
        }
        v2 = v46;
        if ( !v32 )
        {
LABEL_84:
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v58) = 0;
            LOWORD(v54) = 0;
            LODWORD(v41) = *((unsigned __int8 *)lpMem + v31 + 7);
            LODWORD(v40) = *((unsigned __int8 *)lpMem + v31 + 6);
            LODWORD(v39) = *((unsigned __int8 *)lpMem + v31 + 5);
            LODWORD(v38) = *((unsigned __int8 *)lpMem + v31 + 4);
            LODWORD(v37) = *((unsigned __int8 *)lpMem + v31 + 3);
            LODWORD(v36) = *((unsigned __int8 *)lpMem + v31 + 2);
            FormatRRASErrorString(
              &v58,
              L"UpdateBindingInformation: Address %d.%d.%d.%d/%d.%d.%d.%d new for %ws",
              *((unsigned __int8 *)lpMem + v31),
              *((unsigned __int8 *)lpMem + v31 + 1),
              v36,
              v37,
              v38,
              v39,
              v40,
              v41,
              *(_QWORD *)(v2 + 72));
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v35 = &v53;
              if ( v2 != -688 )
                LODWORD(v35) = v2 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v58,
                (_DWORD)v35,
                *(_QWORD *)(v2 + 72),
                (__int64)&v54);
            }
          }
        }
      }
    }
    if ( v7 )
      HeapFree(IPRouterHeap, 0, v7);
    RtlReleaseResource(&stru_18008C500);
    return 0;
  }
  if ( v18 )
    HeapFree(IPRouterHeap, 0, v18);
  return 1227;
}

```

## disassembly

```asm
0x18001be68  mov     [rsp+arg_8], rbx
0x18001be6d  mov     [rsp+arg_10], rsi
0x18001be72  push    rdi
0x18001be73  push    r12
0x18001be75  push    r13
0x18001be77  push    r14
0x18001be79  push    r15
0x18001be7b  mov     eax, 1100h
0x18001be80  call    _alloca_probe
0x18001be85  sub     rsp, rax
0x18001be88  mov     rax, cs:__security_cookie
0x18001be8f  xor     rax, rsp
0x18001be92  mov     [rsp+1128h+var_38], rax
0x18001be9a  xor     edi, edi
0x18001be9c  mov     [rsp+1128h+var_10A8], rcx
0x18001bea4  mov     rsi, rcx
0x18001bea7  mov     [rsp+1128h+var_10C8], edi
0x18001beab  lea     rcx, [rsp+1128h+var_834]; void *
0x18001beb3  mov     [rsp+1128h+lpMem], rdi
0x18001beb8  xor     edx, edx; Val
0x18001beba  mov     [rsp+1128h+var_10B8], edi
0x18001bebe  mov     r8d, 7FCh; Size
0x18001bec4  mov     [rsp+1128h+var_10B4], edi
0x18001bec8  mov     [rsp+1128h+var_838], edi
0x18001becf  call    memset_0
0x18001bed4  xor     eax, eax
0x18001bed6  mov     [rsp+1128h+var_868], edi
0x18001bedd  xorps   xmm0, xmm0
0x18001bee0  mov     [rsp+1128h+var_844], eax
0x18001bee7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001beee  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001bef5  movups  [rsp+1128h+var_864], xmm0
0x18001befd  movups  [rsp+1128h+var_854], xmm0
0x18001bf05  movups  [rsp+1128h+var_878], xmm0
0x18001bf0d  test    al, 80h
0x18001bf0f  jz      short loc_18001BF62
0x18001bf11  lea     rax, [rsi+2B0h]
0x18001bf18  mov     word ptr [rsp+1128h+var_868], di
0x18001bf20  test    rax, rax
0x18001bf23  lea     r9, [rsp+1128h+var_878]
0x18001bf2b  lea     r8, aUpdatebindingi_1; "UpdateBindingInformation"
0x18001bf32  mov     rcx, r14
0x18001bf35  cmovnz  r9, rax
0x18001bf39  lea     rdx, RasRtrmgrParamTraceInfo
0x18001bf40  lea     rax, [rsp+1128h+var_868]
0x18001bf48  mov     [rsp+1128h+var_1100], rax
0x18001bf4d  mov     rax, [rsi+48h]
0x18001bf51  mov     [rsp+1128h+var_1108], rax
0x18001bf56  call    McTemplateU0zjzz_EventWriteTransfer
0x18001bf5b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001bf62  mov     r9d, [rsi+90h]
0x18001bf69  lea     ecx, [r9-3]
0x18001bf6d  cmp     ecx, 1
0x18001bf70  jbe     loc_18001BFFB
0x18001bf76  test    al, al
0x18001bf78  jns     loc_18001C2F7
0x18001bf7e  mov     r8, [rsi+48h]
0x18001bf82  lea     rdx, aUpdatebindingi_3; "UpdateBindingInformation: %ws is type %"...
0x18001bf89  lea     rcx, [rsp+1128h+var_838]
0x18001bf91  mov     word ptr [rsp+1128h+var_838], di
0x18001bf99  mov     word ptr [rsp+1128h+var_868], di
0x18001bfa1  call    FormatRRASErrorString
0x18001bfa6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001bfad  jge     loc_18001C2F7
0x18001bfb3  lea     rax, [rsi+2B0h]
0x18001bfba  mov     rcx, r14
0x18001bfbd  test    rax, rax
0x18001bfc0  lea     r9, [rsp+1128h+var_878]
0x18001bfc8  lea     r8, [rsp+1128h+var_838]
0x18001bfd0  cmovnz  r9, rax
0x18001bfd4  lea     rdx, RasRtrmgrParamTraceInfo
0x18001bfdb  lea     rax, [rsp+1128h+var_868]
0x18001bfe3  mov     [rsp+1128h+var_1100], rax
0x18001bfe8  mov     rax, [rsi+48h]
0x18001bfec  mov     [rsp+1128h+var_1108], rax
0x18001bff1  call    McTemplateU0zjzz_EventWriteTransfer
0x18001bff6  jmp     loc_18001C2F7
0x18001bffb  lea     r9, [rsp+1128h+lpMem]
0x18001c000  mov     r15, [rsi+2C8h]
0x18001c007  lea     r8, [rsp+1128h+var_10C8]
0x18001c00c  mov     r13d, [rsi+29Ch]
0x18001c013  mov     edx, [rsi+2C0h]
0x18001c019  mov     ecx, [rsi+10h]
0x18001c01c  mov     [rsp+1128h+var_10C8], edi
0x18001c020  mov     [rsp+1128h+lpMem], rdi
0x18001c025  cmp     [rsi+204h], edi
0x18001c02b  jz      short loc_18001C048
0x18001c02d  lea     rax, [rsp+1128h+var_10B4]
0x18001c032  mov     [rsp+1128h+var_1100], rax
0x18001c037  lea     rax, [rsp+1128h+var_10B8]
0x18001c03c  mov     [rsp+1128h+var_1108], rax
0x18001c041  call    GetIpInfoForInterface
0x18001c046  jmp     short loc_18001C04D
0x18001c048  call    GetIpv6InfoForInterface
0x18001c04d  mov     ebx, eax
0x18001c04f  test    eax, eax
0x18001c051  jz      loc_18001C0FD
0x18001c057  cmp     eax, 0E8h
0x18001c05c  jz      loc_18001C0E8
0x18001c062  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001c069  jz      loc_18001C0F6
0x18001c06f  mov     r9, [rsi+48h]
0x18001c073  lea     rdx, aUpdatebindingi; "UpdateBindingInformation: Error %d gett"...
0x18001c07a  mov     r8d, eax
0x18001c07d  mov     word ptr [rsp+1128h+var_838], di
0x18001c085  lea     rcx, [rsp+1128h+var_838]
0x18001c08d  mov     word ptr [rsp+1128h+var_868], di
0x18001c095  call    FormatRRASErrorString
0x18001c09a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001c0a1  jz      short loc_18001C0F6
0x18001c0a3  lea     rax, [rsi+2B0h]
0x18001c0aa  mov     rcx, r14
0x18001c0ad  test    rax, rax
0x18001c0b0  lea     r9, [rsp+1128h+var_878]
0x18001c0b8  lea     r8, [rsp+1128h+var_838]
0x18001c0c0  cmovnz  r9, rax
0x18001c0c4  lea     rdx, RasRtrMgrParamTraceError
0x18001c0cb  lea     rax, [rsp+1128h+var_868]
0x18001c0d3  mov     [rsp+1128h+var_1100], rax
0x18001c0d8  mov     rax, [rsi+48h]
0x18001c0dc  mov     [rsp+1128h+var_1108], rax
0x18001c0e1  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c0e6  jmp     short loc_18001C0F6
0x18001c0e8  cmp     [rsi+29Ch], edi
0x18001c0ee  mov     eax, 4CBh
0x18001c0f3  cmovz   ebx, eax
0x18001c0f6  mov     eax, ebx
0x18001c0f8  jmp     loc_18001C4DE
0x18001c0fd  mov     r10d, 1
0x18001c103  mov     [rsi+200h], r10d
0x18001c10a  cmp     [rsi+204h], edi
0x18001c110  jz      loc_18001C301
0x18001c116  mov     r14d, [rsp+1128h+var_10C8]
0x18001c11b  mov     r12d, edi
0x18001c11e  mov     rbx, [rsp+1128h+lpMem]
0x18001c123  cmp     edi, r13d
0x18001c126  jnb     loc_18001C26E
0x18001c12c  xor     ecx, ecx
0x18001c12e  mov     eax, edi
0x18001c130  imul    r8, rax, 1Ch
0x18001c134  cmp     ecx, r14d
0x18001c137  jnb     short loc_18001C15C
0x18001c139  mov     eax, ecx
0x18001c13b  imul    rdx, rax, 1Ch
0x18001c13f  mov     eax, [rdx+rbx]
0x18001c142  cmp     [r8+r15], eax
0x18001c146  jnz     short loc_18001C157
0x18001c148  mov     eax, [rdx+rbx+4]
0x18001c14c  cmp     [r8+r15+4], eax
0x18001c151  jz      loc_18001C266
0x18001c157  add     ecx, r10d
0x18001c15a  jmp     short loc_18001C134
0x18001c15c  cmp     dword ptr [rsi+204h], 0
0x18001c163  mov     r12d, r10d
0x18001c166  jz      loc_18001C266
0x18001c16c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001c173  jge     loc_18001C221
0x18001c179  xor     eax, eax
0x18001c17b  mov     word ptr [rsp+1128h+var_838], ax
0x18001c183  mov     word ptr [rsp+1128h+var_868], ax
0x18001c18b  movzx   ecx, byte ptr [r8+r15+3]
0x18001c191  movzx   edx, byte ptr [r8+r15+2]
0x18001c197  mov     rax, [rsi+48h]
0x18001c19b  movzx   r9d, byte ptr [r8+r15+1]
0x18001c1a1  movzx   r8d, byte ptr [r8+r15]
0x18001c1a6  mov     [rsp+1128h+var_10F8], rax
0x18001c1ab  mov     dword ptr [rsp+1128h+var_1100], ecx
0x18001c1af  lea     rcx, [rsp+1128h+var_838]
0x18001c1b7  mov     dword ptr [rsp+1128h+var_1108], edx
0x18001c1bb  lea     rdx, aUpdatebindingi_0; "UpdateBindingInformation: Address %d.%d"...
0x18001c1c2  call    FormatRRASErrorString
0x18001c1c7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001c1ce  jge     short loc_18001C217
0x18001c1d0  lea     rax, [rsi+2B0h]
0x18001c1d7  test    rax, rax
0x18001c1da  lea     r9, [rsp+1128h+var_878]
0x18001c1e2  lea     r8, [rsp+1128h+var_838]
0x18001c1ea  cmovnz  r9, rax
0x18001c1ee  lea     rdx, RasRtrmgrParamTraceInfo
0x18001c1f5  lea     rax, [rsp+1128h+var_868]
0x18001c1fd  mov     [rsp+1128h+var_1100], rax
0x18001c202  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c209  mov     rax, [rsi+48h]
0x18001c20d  mov     [rsp+1128h+var_1108], rax
0x18001c212  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c217  mov     rbx, [rsp+1128h+lpMem]
0x18001c21c  mov     r14d, [rsp+1128h+var_10C8]
0x18001c221  xor     eax, eax
0x18001c223  lea     rcx, [rsp+1128h+var_1074]; void *
0x18001c22b  xor     edx, edx; Val
0x18001c22d  mov     [rsp+1128h+var_1078], eax
0x18001c234  mov     r8d, 7FCh; Size
0x18001c23a  call    memset_0
0x18001c23f  xor     eax, eax
0x18001c241  xorps   xmm0, xmm0
0x18001c244  mov     [rsp+1128h+var_10A0], eax
0x18001c24b  movups  [rsp+1128h+var_109C], xmm0
0x18001c253  mov     [rsp+1128h+var_107C], eax
0x18001c25a  lea     r10d, [rax+1]
0x18001c25e  movups  [rsp+1128h+var_108C], xmm0
0x18001c266  add     edi, r10d
0x18001c269  jmp     loc_18001C123
0x18001c26e  xor     edi, edi
0x18001c270  mov     ecx, edi
0x18001c272  test    r14d, r14d
0x18001c275  jz      short loc_18001C2DB
0x18001c277  mov     eax, ecx
0x18001c279  mov     r8d, edi
0x18001c27c  imul    r9, rax, 1Ch
0x18001c280  cmp     r8d, r13d
0x18001c283  jnb     short loc_18001C2D0
0x18001c285  mov     eax, r8d
0x18001c288  imul    rdx, rax, 1Ch
0x18001c28c  mov     eax, [rdx+r15]
0x18001c290  cmp     [rsi+204h], edi
0x18001c296  jz      short loc_18001C2AA
0x18001c298  cmp     [r9+rbx], eax
0x18001c29c  jnz     short loc_18001C2CB
0x18001c29e  mov     eax, [rdx+r15+4]
0x18001c2a3  cmp     [r9+rbx+4], eax
0x18001c2a8  jmp     short loc_18001C2C9
0x18001c2aa  cmp     [r9+rbx], eax
0x18001c2ae  jnz     short loc_18001C2CB
0x18001c2b0  mov     rax, [r9+rbx+4]
0x18001c2b5  sub     rax, [rdx+r15+4]
0x18001c2ba  jnz     short loc_18001C2C6
0x18001c2bc  mov     rax, [r9+rbx+0Ch]
0x18001c2c1  sub     rax, [rdx+r15+0Ch]
0x18001c2c6  test    rax, rax
0x18001c2c9  jz      short loc_18001C2D3
0x18001c2cb  add     r8d, r10d
0x18001c2ce  jmp     short loc_18001C280
0x18001c2d0  mov     r12d, r10d
0x18001c2d3  add     ecx, r10d
0x18001c2d6  cmp     ecx, r14d
0x18001c2d9  jb      short loc_18001C277
0x18001c2db  test    r12d, r12d
0x18001c2de  jnz     short loc_18001C301
0x18001c2e0  test    rbx, rbx
0x18001c2e3  jz      short loc_18001C2F7
0x18001c2e5  mov     rcx, cs:IPRouterHeap; hHeap
0x18001c2ec  mov     r8, rbx; lpMem
0x18001c2ef  xor     edx, edx; dwFlags
0x18001c2f1  call    cs:__imp_HeapFree
0x18001c2f7  mov     eax, 4CBh
0x18001c2fc  jmp     loc_18001C4DE
0x18001c301  mov     dl, r10b; Wait
0x18001c304  lea     rcx, stru_18008C500; Resource
0x18001c30b  call    cs:__imp_RtlAcquireResourceExclusive
0x18001c311  test    r15, r15
0x18001c314  jz      short loc_18001C31E
0x18001c316  mov     rcx, rsi
0x18001c319  call    RemoveBinding
0x18001c31e  mov     rax, [rsp+1128h+lpMem]
0x18001c323  mov     [rsi+2C8h], rax
0x18001c32a  mov     eax, [rsp+1128h+var_10C8]
0x18001c32e  mov     [rsi+29Ch], eax
0x18001c334  cmp     [rsi+204h], edi
0x18001c33a  jz      short loc_18001C350
0x18001c33c  mov     eax, [rsp+1128h+var_10B8]
0x18001c340  mov     [rsi+20Ch], eax
0x18001c346  mov     eax, [rsp+1128h+var_10B4]
0x18001c34a  mov     [rsi+210h], eax
0x18001c350  mov     rcx, rsi
0x18001c353  call    AddBinding
0x18001c358  cmp     [rsi+204h], edi
0x18001c35e  jz      loc_18001C4B8
0x18001c364  mov     r12d, edi
0x18001c367  cmp     r12d, [rsp+1128h+var_10C8]
0x18001c36c  jnb     loc_18001C4B8
0x18001c372  mov     eax, r12d
0x18001c375  imul    r14, rax, 1Ch
0x18001c379  test    r13d, r13d
0x18001c37c  jz      short loc_18001C3C0
0x18001c37e  mov     r8, [rsp+1128h+lpMem]
0x18001c383  mov     edx, edi
0x18001c385  mov     ecx, edi
0x18001c387  mov     esi, 1
0x18001c38c  mov     r9d, [r14+r8]
0x18001c390  mov     eax, ecx
0x18001c392  imul    rax, 1Ch
0x18001c396  cmp     r9d, [rax+r15]
0x18001c39a  jnz     short loc_18001C3A9
0x18001c39c  mov     eax, [rax+r15+4]
0x18001c3a1  cmp     [r14+r8+4], eax
0x18001c3a6  cmovz   edx, esi
0x18001c3a9  add     ecx, esi
0x18001c3ab  cmp     ecx, r13d
0x18001c3ae  jb      short loc_18001C390
0x18001c3b0  mov     rsi, [rsp+1128h+var_10A8]
0x18001c3b8  test    edx, edx
0x18001c3ba  jnz     loc_18001C4B0
0x18001c3c0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001c3c7  jge     loc_18001C49A
0x18001c3cd  mov     rax, [rsp+1128h+lpMem]
0x18001c3d2  mov     word ptr [rsp+1128h+var_838], di
0x18001c3da  mov     word ptr [rsp+1128h+var_868], di
0x18001c3e2  movzx   ecx, byte ptr [r14+rax+4]
0x18001c3e8  movzx   edx, byte ptr [r14+rax+3]
0x18001c3ee  movzx   r11d, byte ptr [r14+rax+7]
  ... truncated ...
```
