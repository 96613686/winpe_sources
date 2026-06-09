# DimEnumerateInterfacesFromStack(uint,ulong *,_DIM_COMPARTMENT_INTERFACE * *)

- ea: `0x180013c9c`
- end: `0x180013f6d`
- name: `?DimEnumerateInterfacesFromStack@@YAKIPEAKPEAPEAU_DIM_COMPARTMENT_INTERFACE@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(NET_IF_COMPARTMENT_ID CompartmentId, unsigned int *, struct _DIM_COMPARTMENT_INTERFACE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014244`
- `0x180015490`

## callees

- `0x18000def0`
- `0x180013c9c`
- `0x180033e90`
- `0x180045d40`
- `0x180046e70`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180013d10`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180013f3b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180013d10`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180013f3b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180013d01`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180013d01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013da7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013da7`
- `NSI!NsiFreeTable` at `0x180013f2f`
- `NSI!NsiFreeTable` at `0x180013f2f`
- `NSI!NsiAllocateAndGetTable` at `0x180013d7a`
- `NSI!NsiAllocateAndGetTable` at `0x180013d7a`
- `RPCRT4!UuidCreate` at `0x180013e3d`
- `RPCRT4!UuidCreate` at `0x180013e3d`

## string_xrefs

- `0x180013eec`: `DimEnumerateInterfacesFromStack: Failed to set compartment Id (%d) on the thread %d.`
- `0x180013e5d`: `DimEnumerateInterfacesFromStack: UuidCreate failed for interface (VSID=%d) (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DimEnumerateInterfacesFromStack(
        NET_IF_COMPARTMENT_ID CompartmentId,
        unsigned int *a2,
        struct _DIM_COMPARTMENT_INTERFACE **a3)
{
  unsigned int v3; // r12d
  NET_IF_COMPARTMENT_ID v4; // r13d
  NET_IF_COMPARTMENT_ID v5; // esi
  unsigned int v6; // eax
  unsigned int Table; // ebx
  int v8; // edi
  struct _DIM_COMPARTMENT_INTERFACE *v9; // r15
  unsigned int i; // esi
  __int64 v11; // r14
  __int64 v12; // r13
  unsigned int v13; // eax
  unsigned int v15; // [rsp+70h] [rbp-90h] BYREF
  NET_IF_COMPARTMENT_ID v16; // [rsp+74h] [rbp-8Ch]
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+78h] [rbp-88h]
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v21; // [rsp+98h] [rbp-68h]
  struct _DIM_COMPARTMENT_INTERFACE **v22; // [rsp+A0h] [rbp-60h]
  UUID Uuid; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v24[1024]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v22 = a3;
  *a2 = 0;
  v4 = CompartmentId;
  Uuid = GUID_NULL;
  v21 = a2;
  v16 = CompartmentId;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v15 = 0;
  *a3 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v5 = CurrentThreadCompartmentId;
  v6 = SetCurrentThreadCompartmentId(v4);
  Table = v6;
  if ( v6 )
  {
    v8 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v24[0] = 0;
      FormatRRASErrorString(
        v24,
        L"DimEnumerateInterfacesFromStack: Failed to set compartment Id (%d) on the thread %d.",
        v4,
        v6);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, v24);
    }
  }
  else
  {
    v8 = 1;
    Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v20, 8, 0, 0, &v19, 88, &v18, 32, &v15, 0);
    if ( !Table && v15 )
    {
      v9 = (struct _DIM_COMPARTMENT_INTERFACE *)HeapAlloc(hHeap, 8u, 536LL * v15);
      if ( v9 )
      {
        for ( i = 0; i < v15; ++i )
        {
          v11 = 32LL * i;
          if ( *(_DWORD *)(v11 + v18 + 4) != 24 && *(_DWORD *)(88LL * i + v19 + 4) == v4 )
          {
            v12 = 536LL * v3;
            *(_DWORD *)((char *)v9 + v12) = *(_DWORD *)(v11 + v18 + 24);
            *(_QWORD *)((char *)v9 + v12 + 8) = *(_QWORD *)(v11 + v18 + 16);
            v13 = UuidCreate(&Uuid);
            Table = v13;
            if ( !v13 || v13 == 1824 )
            {
              MprConvertGuidToString(&Uuid, 258, (char *)v9 + v12 + 16);
              ++v3;
            }
            else if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v24[0] = 0;
              FormatRRASErrorString(
                v24,
                L"DimEnumerateInterfacesFromStack: UuidCreate failed for interface (VSID=%d) (%d)",
                *(unsigned int *)(v11 + v18 + 24),
                v13);
              if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, v24);
            }
            v4 = v16;
          }
        }
        v5 = CurrentThreadCompartmentId;
        *v21 = v3;
        *v22 = v9;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasDimTraceError,
            L"DimEnumerateInterfacesFromStack: Malloc failed.");
        Table = 8;
      }
    }
  }
  if ( v20 )
    NsiFreeTable(v20, 0, v19, v18);
  if ( v8 )
    SetCurrentThreadCompartmentId(v5);
  return Table;
}

```

## disassembly

```asm
0x180013c9c  mov     [rsp-8+arg_18], rbx
0x180013ca1  push    rbp
0x180013ca2  push    rsi
0x180013ca3  push    rdi
0x180013ca4  push    r12
0x180013ca6  push    r13
0x180013ca8  push    r14
0x180013caa  push    r15
0x180013cac  lea     rbp, [rsp-7D0h]
0x180013cb4  sub     rsp, 8D0h
0x180013cbb  mov     rax, cs:__security_cookie
0x180013cc2  xor     rax, rsp
0x180013cc5  mov     [rbp+800h+var_40], rax
0x180013ccc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013cd3  xor     r12d, r12d
0x180013cd6  mov     [rbp+800h+var_860], r8
0x180013cda  mov     [rdx], r12d
0x180013cdd  mov     r13d, ecx
0x180013ce0  movdqu  xmmword ptr [rbp+800h+Uuid.Data1], xmm0
0x180013ce5  mov     [rbp+800h+var_868], rdx
0x180013ce9  mov     [rsp+900h+var_88C], ecx
0x180013ced  mov     [rbp+800h+var_870], r12
0x180013cf1  mov     [rbp+800h+var_878], r12
0x180013cf5  mov     [rbp+800h+var_880], r12
0x180013cf9  mov     [rsp+900h+var_890], r12d
0x180013cfe  mov     [r8], r12
0x180013d01  call    cs:__imp_GetCurrentThreadCompartmentId
0x180013d07  mov     ecx, r13d; CompartmentId
0x180013d0a  mov     [rsp+900h+var_888], eax
0x180013d0e  mov     esi, eax
0x180013d10  call    cs:__imp_SetCurrentThreadCompartmentId
0x180013d16  mov     ebx, eax
0x180013d18  test    eax, eax
0x180013d1a  jnz     loc_180013ED5
0x180013d20  mov     [rsp+900h+var_8A0], r12b
0x180013d25  lea     edi, [rax+1]
0x180013d28  lea     rax, [rsp+900h+var_890]
0x180013d2d  mov     ecx, edi
0x180013d2f  mov     [rsp+900h+var_8A8], rax
0x180013d34  lea     r14d, [r12+8]
0x180013d39  mov     [rsp+900h+var_8B0], 20h ; ' '
0x180013d41  lea     rax, [rbp+800h+var_880]
0x180013d45  mov     [rsp+900h+var_8B8], rax
0x180013d4a  lea     r9, [rbp+800h+var_870]
0x180013d4e  mov     [rsp+900h+var_8C0], 58h ; 'X'
0x180013d56  lea     rax, [rbp+800h+var_878]
0x180013d5a  mov     [rsp+900h+var_8C8], rax
0x180013d5f  lea     r8d, [r12+7]
0x180013d64  mov     [rsp+900h+var_8D0], r12d
0x180013d69  lea     rdx, NPI_MS_IPV4_MODULEID
0x180013d70  mov     [rsp+900h+var_8D8], r12
0x180013d75  mov     [rsp+900h+var_8E0], r14d
0x180013d7a  call    cs:__imp_NsiAllocateAndGetTable
0x180013d80  mov     ebx, eax
0x180013d82  test    eax, eax
0x180013d84  jnz     loc_180013F1C
0x180013d8a  mov     eax, [rsp+900h+var_890]
0x180013d8e  test    eax, eax
0x180013d90  jz      loc_180013F1C
0x180013d96  mov     rcx, cs:hHeap; hHeap
0x180013d9d  mov     edx, r14d; dwFlags
0x180013da0  imul    r8, rax, 218h; dwBytes
0x180013da7  call    cs:__imp_HeapAlloc
0x180013dad  mov     r15, rax
0x180013db0  test    rax, rax
0x180013db3  jnz     short loc_180013DE0
0x180013db5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013dbc  jz      short loc_180013DD8
0x180013dbe  lea     r8, aDimenumeratein; "DimEnumerateInterfacesFromStack: Malloc"...
0x180013dc5  lea     rdx, RasDimTraceError
0x180013dcc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013dd3  call    McTemplateU0z_EventWriteTransfer
0x180013dd8  mov     ebx, r14d
0x180013ddb  jmp     loc_180013F1C
0x180013de0  xor     esi, esi
0x180013de2  cmp     esi, [rsp+900h+var_890]
0x180013de6  jnb     loc_180013EC1
0x180013dec  mov     rdx, [rbp+800h+var_880]
0x180013df0  mov     r14d, esi
0x180013df3  shl     r14, 5
0x180013df7  mov     eax, esi
0x180013df9  cmp     dword ptr [r14+rdx+4], 18h
0x180013dff  jz      loc_180013EBA
0x180013e05  imul    rcx, rax, 58h ; 'X'
0x180013e09  mov     rax, [rbp+800h+var_878]
0x180013e0d  cmp     [rcx+rax+4], r13d
0x180013e12  jnz     loc_180013EBA
0x180013e18  mov     eax, r12d
0x180013e1b  imul    r13, rax, 218h
0x180013e22  mov     eax, [r14+rdx+18h]
0x180013e27  mov     [r15+r13], eax
0x180013e2b  mov     rax, [rbp+800h+var_880]
0x180013e2f  mov     rcx, [r14+rax+10h]
0x180013e34  mov     [r15+r13+8], rcx
0x180013e39  lea     rcx, [rbp+800h+Uuid]; Uuid
0x180013e3d  call    cs:__imp_UuidCreate
0x180013e43  mov     ebx, eax
0x180013e45  test    eax, eax
0x180013e47  jz      short loc_180013E9D
0x180013e49  cmp     eax, 720h
0x180013e4e  jz      short loc_180013E9D
0x180013e50  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013e57  jz      short loc_180013EB5
0x180013e59  mov     r8, [rbp+800h+var_880]
0x180013e5d  lea     rdx, aDimenumeratein_0; "DimEnumerateInterfacesFromStack: UuidCr"...
0x180013e64  xor     eax, eax
0x180013e66  lea     rcx, [rbp+800h+var_840]
0x180013e6a  mov     [rbp+800h+var_840], ax
0x180013e6e  mov     r9d, ebx
0x180013e71  mov     r8d, [r14+r8+18h]
0x180013e76  call    FormatRRASErrorString
0x180013e7b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013e82  jz      short loc_180013EB5
0x180013e84  lea     r8, [rbp+800h+var_840]
0x180013e88  lea     rdx, RasDimTraceError
0x180013e8f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013e96  call    McTemplateU0z_EventWriteTransfer
0x180013e9b  jmp     short loc_180013EB5
0x180013e9d  lea     r8, [r15+10h]
0x180013ea1  mov     edx, 102h
0x180013ea6  add     r8, r13
0x180013ea9  lea     rcx, [rbp+800h+Uuid]
0x180013ead  call    MprConvertGuidToString
0x180013eb2  add     r12d, edi
0x180013eb5  mov     r13d, [rsp+900h+var_88C]
0x180013eba  add     esi, edi
0x180013ebc  jmp     loc_180013DE2
0x180013ec1  mov     rax, [rbp+800h+var_868]
0x180013ec5  mov     esi, [rsp+900h+var_888]
0x180013ec9  mov     [rax], r12d
0x180013ecc  mov     rax, [rbp+800h+var_860]
0x180013ed0  mov     [rax], r15
0x180013ed3  jmp     short loc_180013F1C
0x180013ed5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013edc  mov     edi, r12d
0x180013edf  jz      short loc_180013F1C
0x180013ee1  mov     r9d, eax
0x180013ee4  mov     [rbp+800h+var_840], r12w
0x180013ee9  mov     r8d, r13d
0x180013eec  lea     rdx, aDimenumeratein_1; "DimEnumerateInterfacesFromStack: Failed"...
0x180013ef3  lea     rcx, [rbp+800h+var_840]
0x180013ef7  call    FormatRRASErrorString
0x180013efc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013f03  jz      short loc_180013F1C
0x180013f05  lea     r8, [rbp+800h+var_840]
0x180013f09  lea     rdx, RasDimTraceError
0x180013f10  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013f17  call    McTemplateU0z_EventWriteTransfer
0x180013f1c  mov     rcx, [rbp+800h+var_870]
0x180013f20  test    rcx, rcx
0x180013f23  jz      short loc_180013F35
0x180013f25  mov     r9, [rbp+800h+var_880]
0x180013f29  xor     edx, edx
0x180013f2b  mov     r8, [rbp+800h+var_878]
0x180013f2f  call    cs:__imp_NsiFreeTable
0x180013f35  test    edi, edi
0x180013f37  jz      short loc_180013F41
0x180013f39  mov     ecx, esi; CompartmentId
0x180013f3b  call    cs:__imp_SetCurrentThreadCompartmentId
0x180013f41  mov     eax, ebx
0x180013f43  mov     rcx, [rbp+800h+var_40]
0x180013f4a  xor     rcx, rsp; StackCookie
0x180013f4d  call    __security_check_cookie
0x180013f52  mov     rbx, [rsp+900h+arg_18]
0x180013f5a  add     rsp, 8D0h
0x180013f61  pop     r15
0x180013f63  pop     r14
0x180013f65  pop     r13
0x180013f67  pop     r12
0x180013f69  pop     rdi
0x180013f6a  pop     rsi
0x180013f6b  pop     rbp
0x180013f6c  retn
```
