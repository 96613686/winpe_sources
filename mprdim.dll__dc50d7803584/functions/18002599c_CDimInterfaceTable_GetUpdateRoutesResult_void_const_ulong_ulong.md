# CDimInterfaceTable::GetUpdateRoutesResult(void * const,ulong,ulong *)

- ea: `0x18002599c`
- end: `0x180025c1d`
- name: `?GetUpdateRoutesResult@CDimInterfaceTable@@QEAAKQEAXKPEAK@Z`
- size: `641`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, void *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ff70`

## callees

- `0x180005550`
- `0x1800055f0`
- `0x180005670`
- `0x1800056c4`
- `0x180006ce0`
- `0x18000def0`
- `0x18000df70`
- `0x18001d69c`
- `0x18002599c`
- `0x18002eaec`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180025a43`: `CDimInterfaceTable::GetUpdateRoutesResult: pUpdateResult is nullptr`
- `0x180025a70`: `CDimInterfaceTable::GetUpdateRoutesResult: Transport Not available`
- `0x180025abe`: `CDimInterfaceTable::GetUpdateRoutesResult: Interface not found`
- `0x180025b27`: `CDimInterfaceTable::GetUpdateRoutesResult:  pDimInterface->GetTransportInfo returned %d`
- `0x180025bb6`: `CDimInterfaceTable::GetUpdateRoutesResult: returned %d`

## pseudocode

```c
__int64 __fastcall CDimInterfaceTable::GetUpdateRoutesResult(
        CDimInterfaceTable *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int *a4)
{
  CDimInterfaceTable *v7; // rdi
  int v8; // esi
  unsigned int v9; // ebx
  const wchar_t *v10; // r8
  CDimInterface *v11; // rcx
  unsigned int UpdateRoutesResult; // eax
  __int64 v13; // rax
  __int128 *v14; // r9
  CDimInterface *v16; // [rsp+38h] [rbp-C8h] BYREF
  std::tr1::_Ref_count_base *v17; // [rsp+40h] [rbp-C0h]
  GUID ActivityId; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+68h] [rbp-98h] BYREF
  __int128 v21; // [rsp+6Ch] [rbp-94h]
  __int128 v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v7 = g_pCDimInterfaceTable;
  ActivityId = 0;
  v19 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v8 = SetRasServerActivityId(&ActivityId);
  if ( a4 )
  {
    if ( CDimRouterManager::IsTransportAvailable(g_pCDimRouterManager, a3) )
    {
      CDimInterfaceTable::AcquireShared(v7);
      CDimInterfaceTable::GetCDimInterface((__int64)v7, &v16, a2);
      v11 = v16;
      if ( v16 )
      {
        if ( v8 )
        {
          ReSetActivityId(&ActivityId);
          v11 = v16;
        }
        v8 = SetActivityId((LPGUID)v11 + 194);
        UpdateRoutesResult = CDimInterface::GetUpdateRoutesResult(v16, a3, a4);
        v9 = UpdateRoutesResult;
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v24) = 0;
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v24,
            L"CDimInterfaceTable::GetUpdateRoutesResult:  pDimInterface->GetTransportInfo returned %d",
            UpdateRoutesResult);
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            v13 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v16 + 280LL))(v16);
            v14 = &v19;
            if ( v16 != (CDimInterface *)-3104LL )
              LODWORD(v14) = (_DWORD)v16 + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceInfo,
              (unsigned int)&v24,
              (_DWORD)v14,
              v13,
              (__int64)&v20);
          }
        }
      }
      else
      {
        v9 = 6;
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasDimTraceError,
            L"CDimInterfaceTable::GetUpdateRoutesResult: Interface not found");
      }
      CDimInterfaceTable::ReleaseShared(v7);
      if ( v17 )
        std::tr1::_Ref_count_base::_Decref(v17);
    }
    else
    {
      v9 = 902;
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v10 = L"CDimInterfaceTable::GetUpdateRoutesResult: Transport Not available";
        goto LABEL_7;
      }
    }
  }
  else
  {
    v9 = 87;
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v10 = L"CDimInterfaceTable::GetUpdateRoutesResult: pUpdateResult is nullptr";
LABEL_7:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, v10);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"CDimInterfaceTable::GetUpdateRoutesResult: returned %d", v9);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v24);
  }
  if ( v8 )
    ReSetActivityId(&ActivityId);
  return v9;
}

```

## disassembly

```asm
0x18002599c  mov     [rsp-8+arg_0], rbx
0x1800259a1  mov     [rsp-8+arg_8], rsi
0x1800259a6  push    rbp
0x1800259a7  push    rdi
0x1800259a8  push    r12
0x1800259aa  push    r14
0x1800259ac  push    r15
0x1800259ae  lea     rbp, [rsp-7A0h]
0x1800259b6  sub     rsp, 8A0h
0x1800259bd  mov     rax, cs:__security_cookie
0x1800259c4  xor     rax, rsp
0x1800259c7  mov     [rbp+7C0h+var_30], rax
0x1800259ce  mov     r15, r9
0x1800259d1  mov     ebx, r8d
0x1800259d4  mov     r14, rdx
0x1800259d7  mov     rdi, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x1800259de  xorps   xmm0, xmm0
0x1800259e1  movups  xmmword ptr [rsp+8C0h+ActivityId.Data1], xmm0
0x1800259e6  xorps   xmm1, xmm1
0x1800259e9  movups  [rsp+8C0h+var_868], xmm1
0x1800259ee  xor     eax, eax
0x1800259f0  mov     [rbp+7C0h+var_830], eax
0x1800259f3  xor     edx, edx; Val
0x1800259f5  mov     r8d, 7FCh; Size
0x1800259fb  lea     rcx, [rbp+7C0h+var_82C]; void *
0x1800259ff  call    memset_0
0x180025a04  xor     eax, eax
0x180025a06  mov     [rsp+8C0h+var_858], eax
0x180025a0a  xorps   xmm0, xmm0
0x180025a0d  movups  [rsp+8C0h+var_854], xmm0
0x180025a12  movups  [rsp+8C0h+var_844], xmm0
0x180025a17  mov     [rbp+7C0h+var_834], eax
0x180025a1a  lea     rcx, [rsp+8C0h+ActivityId]; ActivityId
0x180025a1f  call    SetRasServerActivityId
0x180025a24  mov     esi, eax
0x180025a26  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180025a2d  test    r15, r15
0x180025a30  jnz     short loc_180025A4C
0x180025a32  lea     ebx, [r15+57h]
0x180025a36  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180025a3d  jz      loc_180025BA4
0x180025a43  lea     r8, aCdiminterfacet_2; "CDimInterfaceTable::GetUpdateRoutesResu"...
0x180025a4a  jmp     short loc_180025A77
0x180025a4c  mov     edx, ebx; unsigned int
0x180025a4e  mov     rcx, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; this
0x180025a55  call    ?IsTransportAvailable@CDimRouterManager@@QEAA_NK@Z; CDimRouterManager::IsTransportAvailable(ulong)
0x180025a5a  test    al, al
0x180025a5c  jnz     short loc_180025A8B
0x180025a5e  mov     ebx, 386h
0x180025a63  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180025a6a  jz      loc_180025BA4
0x180025a70  lea     r8, aCdiminterfacet_49; "CDimInterfaceTable::GetUpdateRoutesResu"...
0x180025a77  lea     rdx, RasDimTraceError
0x180025a7e  mov     rcx, r12
0x180025a81  call    McTemplateU0z_EventWriteTransfer
0x180025a86  jmp     loc_180025BA4
0x180025a8b  mov     rcx, rdi; this
0x180025a8e  call    ?AcquireShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireShared(void)
0x180025a93  mov     r8, r14
0x180025a96  lea     rdx, [rsp+8C0h+var_888]
0x180025a9b  mov     rcx, rdi
0x180025a9e  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x180025aa3  nop
0x180025aa4  mov     rcx, [rsp+8C0h+var_888]
0x180025aa9  test    rcx, rcx
0x180025aac  jnz     short loc_180025AD9
0x180025aae  lea     ebx, [rcx+6]
0x180025ab1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180025ab8  jz      loc_180025B8B
0x180025abe  lea     r8, aCdiminterfacet_56; "CDimInterfaceTable::GetUpdateRoutesResu"...
0x180025ac5  lea     rdx, RasDimTraceError
0x180025acc  mov     rcx, r12
0x180025acf  call    McTemplateU0z_EventWriteTransfer
0x180025ad4  jmp     loc_180025B8B
0x180025ad9  test    esi, esi
0x180025adb  jz      short loc_180025AEC
0x180025add  lea     rcx, [rsp+8C0h+ActivityId]; ActivityId
0x180025ae2  call    ReSetActivityId
0x180025ae7  mov     rcx, [rsp+8C0h+var_888]
0x180025aec  add     rcx, 0C20h; ActivityId
0x180025af3  lea     rdx, [rsp+8C0h+ActivityId]
0x180025af8  call    SetActivityId
0x180025afd  mov     esi, eax
0x180025aff  mov     r8, r15; unsigned int *
0x180025b02  mov     edx, ebx; unsigned int
0x180025b04  mov     rcx, [rsp+8C0h+var_888]; this
0x180025b09  call    ?GetUpdateRoutesResult@CDimInterface@@QEAAKKPEAK@Z; CDimInterface::GetUpdateRoutesResult(ulong,ulong *)
0x180025b0e  mov     ebx, eax
0x180025b10  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180025b17  jz      short loc_180025B8B
0x180025b19  xor     ecx, ecx
0x180025b1b  mov     word ptr [rbp+7C0h+var_830], cx
0x180025b1f  mov     word ptr [rsp+8C0h+var_858], cx
0x180025b24  mov     r8d, eax
0x180025b27  lea     rdx, aCdiminterfacet_0; "CDimInterfaceTable::GetUpdateRoutesResu"...
0x180025b2e  lea     rcx, [rbp+7C0h+var_830]
0x180025b32  call    FormatRRASErrorString
0x180025b37  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180025b3e  jz      short loc_180025B8B
0x180025b40  mov     rcx, [rsp+8C0h+var_888]
0x180025b45  mov     rax, [rcx]
0x180025b48  mov     rax, [rax+118h]
0x180025b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b54  mov     rcx, [rsp+8C0h+var_888]
0x180025b59  add     rcx, 0C20h
0x180025b60  lea     r9, [rsp+8C0h+var_868]
0x180025b65  cmovnz  r9, rcx
0x180025b69  lea     rcx, [rsp+8C0h+var_858]
0x180025b6e  mov     [rsp+8C0h+var_898], rcx
0x180025b73  mov     [rsp+8C0h+var_8A0], rax
0x180025b78  lea     r8, [rbp+7C0h+var_830]
0x180025b7c  lea     rdx, RasDimParamTraceInfo
0x180025b83  mov     rcx, r12
0x180025b86  call    McTemplateU0zjzz_EventWriteTransfer
0x180025b8b  mov     rcx, rdi; this
0x180025b8e  call    ?ReleaseShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseShared(void)
0x180025b93  nop
0x180025b94  mov     rcx, [rsp+8C0h+var_880]; this
0x180025b99  test    rcx, rcx
0x180025b9c  jz      short loc_180025BA4
0x180025b9e  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180025ba3  nop
0x180025ba4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180025bab  jz      short loc_180025BE2
0x180025bad  xor     eax, eax
0x180025baf  mov     word ptr [rbp+7C0h+var_830], ax
0x180025bb3  mov     r8d, ebx
0x180025bb6  lea     rdx, aCdiminterfacet_38; "CDimInterfaceTable::GetUpdateRoutesResu"...
0x180025bbd  lea     rcx, [rbp+7C0h+var_830]
0x180025bc1  call    FormatRRASErrorString
0x180025bc6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180025bcd  jz      short loc_180025BE2
0x180025bcf  lea     r8, [rbp+7C0h+var_830]
0x180025bd3  lea     rdx, RasDimTraceInfo
0x180025bda  mov     rcx, r12
0x180025bdd  call    McTemplateU0z_EventWriteTransfer
0x180025be2  test    esi, esi
0x180025be4  jz      short loc_180025BF0
0x180025be6  lea     rcx, [rsp+8C0h+ActivityId]; ActivityId
0x180025beb  call    ReSetActivityId
0x180025bf0  mov     eax, ebx
0x180025bf2  mov     rcx, [rbp+7C0h+var_30]
0x180025bf9  xor     rcx, rsp; StackCookie
0x180025bfc  call    __security_check_cookie
0x180025c01  lea     r11, [rsp+8C0h+var_20]
0x180025c09  mov     rbx, [r11+30h]
0x180025c0d  mov     rsi, [r11+38h]
0x180025c11  mov     rsp, r11
0x180025c14  pop     r15
0x180025c16  pop     r14
0x180025c18  pop     r12
0x180025c1a  pop     rdi
0x180025c1b  pop     rbp
0x180025c1c  retn
```
