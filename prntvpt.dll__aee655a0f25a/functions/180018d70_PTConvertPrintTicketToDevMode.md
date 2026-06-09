# PTConvertPrintTicketToDevMode

- ea: `0x180018d70`
- end: `0x180018efe`
- name: `PTConvertPrintTicketToDevMode`
- size: `398`
- prototype: `HRESULT __stdcall(HPTPROVIDER hProvider, IStream *pPrintTicket, EDefaultDevmodeType baseDevmodeType, EPrintTicketScope scope, ULONG *pcbDevmode, PDEVMODE *ppDevmode, BSTR *pbstrErrorMessage)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056e0`
- `0x18000af4c`
- `0x18000f970`
- `0x180018d08`
- `0x180018d70`
- `0x1800225b8`
- `0x180023010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180018e5b`
- `KERNEL32!LocalAlloc` at `0x180018e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e90`

## pseudocode

```c
HRESULT __stdcall PTConvertPrintTicketToDevMode(
        HPTPROVIDER hProvider,
        IStream *pPrintTicket,
        EDefaultDevmodeType baseDevmodeType,
        EPrintTicketScope scope,
        ULONG *pcbDevmode,
        PDEVMODE *ppDevmode,
        BSTR *pbstrErrorMessage)
{
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  struct CPrintTicketHandle *v13; // r15
  OLECHAR *v15; // rcx
  HRESULT v16; // ebx
  int v17; // r8d
  int v18; // r9d
  ULONG v19; // ecx
  char *v20; // rax
  void *v21; // rdx
  void *Src; // [rsp+40h] [rbp-38h] BYREF
  int v23[2]; // [rsp+48h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+50h] [rbp-28h] BYREF

  v13 = CPrintTicketHandle::ConvertHandle(hProvider, 0);
  if ( !v13 )
    return -2147024890;
  if ( !pPrintTicket || !pcbDevmode || !ppDevmode )
    return -2147024809;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, (int)&DocPerf_PrintTicket_ConvertPrintTicketToDevMode_Start, v11, v12, &v24);
  Src = 0;
  *(_QWORD *)v23 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, IStream *, _QWORD, _QWORD, ULONG *, void **, int *))(**((_QWORD **)v13 + 3)
                                                                                              + 64LL))(
          *((_QWORD *)v13 + 3),
          pPrintTicket,
          (unsigned int)baseDevmodeType,
          (unsigned int)scope,
          pcbDevmode,
          &Src,
          v23);
  *ppDevmode = 0;
  if ( Src )
  {
    v19 = *pcbDevmode + 8;
    if ( v19 >= *pcbDevmode )
    {
      v20 = (char *)LocalAlloc(0, v19);
      if ( v20 )
      {
        *(_DWORD *)v20 = 1347702851;
        v21 = Src;
        v16 = 0;
        *ppDevmode = (PDEVMODE)(v20 + 8);
        memcpy_0(v20 + 8, v21, *pcbDevmode);
      }
      else
      {
        v16 = -2147024882;
        *pcbDevmode = 0;
      }
    }
    else
    {
      v16 = -2147024362;
    }
    CoTaskMemFree(Src);
  }
  if ( pbstrErrorMessage )
  {
    v15 = 0;
    if ( *(_QWORD *)v23 )
    {
      v15 = *(OLECHAR **)v23;
      *(_QWORD *)v23 = 0;
    }
    *pbstrErrorMessage = v15;
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (int)v15,
      (int)&DocPerf_PrintTicket_ConvertPrintTicketToDevMode_Stop,
      v17,
      v18,
      &v24);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v23);
  return v16;
}

```

## disassembly

```asm
0x180018d70  push    rbp
0x180018d72  push    rbx
0x180018d73  push    rsi
0x180018d74  push    rdi
0x180018d75  push    r12
0x180018d77  push    r13
0x180018d79  push    r14
0x180018d7b  push    r15
0x180018d7d  mov     rbp, rsp
0x180018d80  sub     rsp, 78h
0x180018d84  mov     rax, cs:__security_cookie
0x180018d8b  xor     rax, rsp
0x180018d8e  mov     [rbp+var_18], rax
0x180018d92  mov     rdi, [rbp+pcbDevmode]
0x180018d96  mov     rbx, rdx
0x180018d99  mov     rsi, [rbp+ppDevmode]
0x180018d9d  xor     edx, edx; int
0x180018d9f  mov     r14, [rbp+pbstrErrorMessage]
0x180018da3  mov     r13d, r9d
0x180018da6  mov     r12d, r8d
0x180018da9  call    ?ConvertHandle@CPrintTicketHandle@@SAPEAV1@PEAUHPTPROVIDER__@@H@Z; CPrintTicketHandle::ConvertHandle(HPTPROVIDER__ *,int)
0x180018dae  mov     r15, rax
0x180018db1  test    rax, rax
0x180018db4  jnz     short loc_180018DC0
0x180018db6  mov     eax, 80070006h
0x180018dbb  jmp     loc_180018EE1
0x180018dc0  test    rbx, rbx
0x180018dc3  jz      loc_180018EDC
0x180018dc9  test    rdi, rdi
0x180018dcc  jz      loc_180018EDC
0x180018dd2  test    rsi, rsi
0x180018dd5  jz      loc_180018EDC
0x180018ddb  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180018de2  jz      short loc_180018DF9
0x180018de4  lea     rax, [rbp+var_28]
0x180018de8  lea     rdx, DocPerf_PrintTicket_ConvertPrintTicketToDevMode_Start; int
0x180018def  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x180018df4  call    McGenEventWrite_EventWriteTransfer
0x180018df9  mov     [rbp+Src], 0
0x180018e01  lea     rdx, [rbp+var_30]
0x180018e05  mov     [rsp+78h+var_48], rdx
0x180018e0a  mov     r9d, r13d
0x180018e0d  mov     qword ptr [rbp+var_30], 0
0x180018e15  lea     rdx, [rbp+Src]
0x180018e19  mov     rcx, [r15+18h]
0x180018e1d  mov     r8d, r12d
0x180018e20  mov     [rsp+78h+var_50], rdx
0x180018e25  mov     rdx, rbx
0x180018e28  mov     [rsp+78h+var_58], rdi
0x180018e2d  mov     rax, [rcx]
0x180018e30  mov     rax, [rax+40h]
0x180018e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e39  xor     r15d, r15d
0x180018e3c  mov     ebx, eax
0x180018e3e  mov     [rsi], r15
0x180018e41  cmp     [rbp+Src], r15
0x180018e45  jz      short loc_180018E96
0x180018e47  mov     eax, [rdi]
0x180018e49  lea     ecx, [rax+8]
0x180018e4c  cmp     ecx, eax
0x180018e4e  jnb     short loc_180018E57
0x180018e50  mov     ebx, 80070216h
0x180018e55  jmp     short loc_180018E8C
0x180018e57  mov     edx, ecx; uBytes
0x180018e59  xor     ecx, ecx; uFlags
0x180018e5b  call    cs:__imp_LocalAlloc
0x180018e61  test    rax, rax
0x180018e64  jnz     short loc_180018E70
0x180018e66  mov     ebx, 8007000Eh
0x180018e6b  mov     [rdi], r15d
0x180018e6e  jmp     short loc_180018E8C
0x180018e70  mov     dword ptr [rax], 50545043h
0x180018e76  lea     rcx, [rax+8]; void *
0x180018e7a  mov     rdx, [rbp+Src]; Src
0x180018e7e  mov     ebx, r15d
0x180018e81  mov     [rsi], rcx
0x180018e84  mov     r8d, [rdi]; Size
0x180018e87  call    memcpy_0
0x180018e8c  mov     rcx, [rbp+Src]; pv
0x180018e90  call    cs:__imp_CoTaskMemFree
0x180018e96  test    r14, r14
0x180018e99  jz      short loc_180018EB1
0x180018e9b  mov     rax, qword ptr [rbp+var_30]
0x180018e9f  mov     rcx, r15
0x180018ea2  test    rax, rax
0x180018ea5  jz      short loc_180018EAE
0x180018ea7  mov     rcx, rax; int
0x180018eaa  mov     qword ptr [rbp+var_30], r15
0x180018eae  mov     [r14], rcx
0x180018eb1  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180018eb8  jz      short loc_180018ECF
0x180018eba  lea     rax, [rbp+var_28]
0x180018ebe  lea     rdx, DocPerf_PrintTicket_ConvertPrintTicketToDevMode_Stop; int
0x180018ec5  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x180018eca  call    McGenEventWrite_EventWriteTransfer
0x180018ecf  lea     rcx, [rbp+var_30]
0x180018ed3  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180018ed8  mov     eax, ebx
0x180018eda  jmp     short loc_180018EE1
0x180018edc  mov     eax, 80070057h
0x180018ee1  mov     rcx, [rbp+var_18]
0x180018ee5  xor     rcx, rsp; StackCookie
0x180018ee8  call    __security_check_cookie
0x180018eed  add     rsp, 78h
0x180018ef1  pop     r15
0x180018ef3  pop     r14
0x180018ef5  pop     r13
0x180018ef7  pop     r12
0x180018ef9  pop     rdi
0x180018efa  pop     rsi
0x180018efb  pop     rbx
0x180018efc  pop     rbp
0x180018efd  retn
```
