# OmaDmInitiateSessionAsDevice

- ea: `0x180018cf0`
- end: `0x180018e93`
- name: `OmaDmInitiateSessionAsDevice`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800147d0`
- `0x18001a7d0`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180014514`
- `0x180014698`
- `0x180018cf0`
- `0x18001d7f0`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x180018e3c`
- `DMCmnUtils!CopyString` at `0x180018e3c`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSessionAsDevice(
        unsigned __int16 *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned int a7)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // ebx
  unsigned __int16 *v13; // r14
  size_t v15; // [rsp+38h] [rbp-2C0h]
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+68h] [rbp-290h] BYREF
  const wchar_t *v18; // [rsp+78h] [rbp-280h]
  __int64 v19; // [rsp+80h] [rbp-278h]
  unsigned __int16 v20[264]; // [rsp+90h] [rbp-268h] BYREF

  memset_0(v20, 0, 0x208u);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v18 = L"OmaDmInitiateSessionAsDevice";
    v19 = 58;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      v11,
      2u,
      &v17);
  }
  if ( a1 && (!a5 || a4) )
  {
    v13 = v20;
    if ( !a6 )
      v13 = 0;
    if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, OmaDmInitiateSessionEvent, a1, a7);
    LODWORD(v15) = a6 != 0 ? 0x208 : 0;
    v12 = OmaDmInitiateSessionWorker(0, a1, a2, a3, a4, a5, v13, v15, a7, 0, 0);
    if ( v12 >= 0 && a6 )
      v12 = CopyString(v20, 0x104u, a6);
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v10, FunctionReturnValueEvent, L"OmaDmInitiateSessionAsDevice", (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180018cf0  push    rbx
0x180018cf2  push    rbp
0x180018cf3  push    rsi
0x180018cf4  push    rdi
0x180018cf5  push    r12
0x180018cf7  push    r13
0x180018cf9  push    r14
0x180018cfb  push    r15
0x180018cfd  sub     rsp, 2B8h
0x180018d04  mov     rax, cs:__security_cookie
0x180018d0b  xor     rax, rsp
0x180018d0e  mov     [rsp+2F8h+var_58], rax
0x180018d16  mov     rdi, [rsp+2F8h+arg_28]
0x180018d1e  mov     r13d, edx
0x180018d21  mov     [rsp+2F8h+var_298], r8d
0x180018d26  mov     rsi, rcx
0x180018d29  mov     r14d, 208h
0x180018d2f  lea     rcx, [rsp+2F8h+var_268]; void *
0x180018d37  mov     r8d, r14d; Size
0x180018d3a  xor     edx, edx; Val
0x180018d3c  mov     r12, r9
0x180018d3f  call    memset_0
0x180018d44  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180018d4b  lea     rbp, aOmadminitiates_10; "OmaDmInitiateSessionAsDevice"
0x180018d52  jz      short loc_180018D88
0x180018d54  lea     rax, [rsp+2F8h+var_290]
0x180018d59  mov     [rsp+2F8h+var_280], rbp
0x180018d5e  mov     r9d, 2
0x180018d64  mov     [rsp+2F8h+var_2D8], rax
0x180018d69  lea     rdx, FunctionEntryPointEvent
0x180018d70  mov     [rsp+2F8h+var_278], 3Ah ; ':'
0x180018d7c  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180018d83  call    McGenEventWrite_EventWriteTransfer
0x180018d88  test    rsi, rsi
0x180018d8b  jnz     short loc_180018D97
0x180018d8d  mov     ebx, 80070057h
0x180018d92  jmp     loc_180018E51
0x180018d97  mov     ebx, [rsp+2F8h+arg_20]
0x180018d9e  test    ebx, ebx
0x180018da0  jz      short loc_180018DA7
0x180018da2  test    r12, r12
0x180018da5  jz      short loc_180018D8D
0x180018da7  mov     r15d, [rsp+2F8h+arg_30]
0x180018daf  xor     eax, eax
0x180018db1  sub     rax, rdi
0x180018db4  neg     rax
0x180018db7  sbb     ebp, ebp
0x180018db9  xor     eax, eax
0x180018dbb  and     ebp, r14d
0x180018dbe  lea     r14, [rsp+2F8h+var_268]
0x180018dc6  test    rdi, rdi
0x180018dc9  cmovz   r14, rax
0x180018dcd  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180018dd4  jz      short loc_180018DE8
0x180018dd6  mov     r9d, r15d
0x180018dd9  lea     rdx, OmaDmInitiateSessionEvent
0x180018de0  mov     r8, rsi
0x180018de3  call    McTemplateU0zq_EventWriteTransfer
0x180018de8  mov     r9d, [rsp+2F8h+var_298]
0x180018ded  mov     r8d, r13d
0x180018df0  mov     [rsp+2F8h+var_2A8], 0
0x180018df8  mov     rdx, rsi
0x180018dfb  mov     [rsp+2F8h+var_2B0], 0
0x180018e03  xor     ecx, ecx
0x180018e05  mov     [rsp+2F8h+var_2B8], r15d
0x180018e0a  mov     dword ptr [rsp+2F8h+var_2C0], ebp
0x180018e0e  mov     [rsp+2F8h+var_2C8], r14
0x180018e13  mov     [rsp+2F8h+var_2D0], ebx
0x180018e17  mov     [rsp+2F8h+var_2D8], r12
0x180018e1c  call    ?OmaDmInitiateSessionWorker@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@W4OMADM_UIMODE@@PEAUOMADMALERTINFO@@KPEAEKW4PushRouterSubmitOrigin@@HH@Z; OmaDmInitiateSessionWorker(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,OMADM_UIMODE,OMADMALERTINFO *,ulong,uchar *,ulong,PushRouterSubmitOrigin,int,int)
0x180018e21  mov     ebx, eax
0x180018e23  test    eax, eax
0x180018e25  js      short loc_180018E4A
0x180018e27  test    rdi, rdi
0x180018e2a  jz      short loc_180018E4A
0x180018e2c  mov     r8, rdi
0x180018e2f  lea     rcx, [rsp+2F8h+var_268]
0x180018e37  mov     edx, 104h
0x180018e3c  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180018e43  nop     dword ptr [rax+rax+00h]
0x180018e48  mov     ebx, eax
0x180018e4a  lea     rbp, aOmadminitiates_10; "OmaDmInitiateSessionAsDevice"
0x180018e51  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180018e58  jz      short loc_180018E6C
0x180018e5a  mov     r9d, ebx
0x180018e5d  lea     rdx, FunctionReturnValueEvent
0x180018e64  mov     r8, rbp
0x180018e67  call    McTemplateU0zq_EventWriteTransfer
0x180018e6c  mov     eax, ebx
0x180018e6e  mov     rcx, [rsp+2F8h+var_58]
0x180018e76  xor     rcx, rsp; StackCookie
0x180018e79  call    __security_check_cookie
0x180018e7e  add     rsp, 2B8h
0x180018e85  pop     r15
0x180018e87  pop     r14
0x180018e89  pop     r13
0x180018e8b  pop     r12
0x180018e8d  pop     rdi
0x180018e8e  pop     rsi
0x180018e8f  pop     rbp
0x180018e90  pop     rbx
0x180018e91  retn
```
