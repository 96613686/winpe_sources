# OmaDmInitiateSessionAsUser

- ea: `0x180018ea0`
- end: `0x180019054`
- name: `OmaDmInitiateSessionAsUser`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a7d0`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180014514`
- `0x180014698`
- `0x180018ea0`
- `0x18001d7f0`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x180018ffd`
- `DMCmnUtils!CopyString` at `0x180018ffd`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSessionAsUser(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned __int16 **a7,
        unsigned int a8)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // ebx
  unsigned __int16 *v13; // r14
  size_t v15; // [rsp+38h] [rbp-2C0h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+68h] [rbp-290h] BYREF
  const wchar_t *v19; // [rsp+78h] [rbp-280h]
  __int64 v20; // [rsp+80h] [rbp-278h]
  unsigned __int16 v21[264]; // [rsp+90h] [rbp-268h] BYREF

  memset_0(v21, 0, 0x208u);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v19 = L"OmaDmInitiateSessionAsUser";
    v20 = 54;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      v11,
      2u,
      &v18);
  }
  if ( a2 && (!a6 || a5) )
  {
    v13 = v21;
    if ( !a7 )
      v13 = 0;
    if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, OmaDmInitiateSessionEvent, a2, a8);
    LODWORD(v15) = a7 != 0 ? 0x208 : 0;
    v12 = OmaDmInitiateSessionWorker(a1, a2, a3, a4, a5, a6, v13, v15, a8, 1, a1 == 0);
    if ( v12 >= 0 && a7 )
      v12 = CopyString(v21, 0x104u, a7);
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v10, FunctionReturnValueEvent, L"OmaDmInitiateSessionAsUser", (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180018ea0  push    rbx
0x180018ea2  push    rbp
0x180018ea3  push    rsi
0x180018ea4  push    rdi
0x180018ea5  push    r12
0x180018ea7  push    r13
0x180018ea9  push    r14
0x180018eab  push    r15
0x180018ead  sub     rsp, 2B8h
0x180018eb4  mov     rax, cs:__security_cookie
0x180018ebb  xor     rax, rsp
0x180018ebe  mov     [rsp+2F8h+var_58], rax
0x180018ec6  mov     r12, [rsp+2F8h+arg_20]
0x180018ece  mov     rsi, rdx
0x180018ed1  mov     rdi, [rsp+2F8h+arg_30]
0x180018ed9  mov     r13, rcx
0x180018edc  mov     [rsp+2F8h+var_294], r8d
0x180018ee1  lea     rcx, [rsp+2F8h+var_268]; void *
0x180018ee9  mov     r14d, 208h
0x180018eef  mov     [rsp+2F8h+var_298], r9d
0x180018ef4  mov     r8d, r14d; Size
0x180018ef7  xor     edx, edx; Val
0x180018ef9  call    memset_0
0x180018efe  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180018f05  lea     rbp, aOmadminitiates_9; "OmaDmInitiateSessionAsUser"
0x180018f0c  jz      short loc_180018F42
0x180018f0e  lea     rax, [rsp+2F8h+var_290]
0x180018f13  mov     [rsp+2F8h+var_280], rbp
0x180018f18  mov     r9d, 2
0x180018f1e  mov     [rsp+2F8h+var_2D8], rax
0x180018f23  lea     rdx, FunctionEntryPointEvent
0x180018f2a  mov     [rsp+2F8h+var_278], 36h ; '6'
0x180018f36  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x180018f3d  call    McGenEventWrite_EventWriteTransfer
0x180018f42  test    rsi, rsi
0x180018f45  jnz     short loc_180018F51
0x180018f47  mov     ebx, 80070057h
0x180018f4c  jmp     loc_180019012
0x180018f51  mov     ebx, [rsp+2F8h+arg_28]
0x180018f58  test    ebx, ebx
0x180018f5a  jz      short loc_180018F61
0x180018f5c  test    r12, r12
0x180018f5f  jz      short loc_180018F47
0x180018f61  mov     r15d, [rsp+2F8h+arg_38]
0x180018f69  xor     eax, eax
0x180018f6b  sub     rax, rdi
0x180018f6e  neg     rax
0x180018f71  sbb     ebp, ebp
0x180018f73  xor     eax, eax
0x180018f75  and     ebp, r14d
0x180018f78  lea     r14, [rsp+2F8h+var_268]
0x180018f80  test    rdi, rdi
0x180018f83  cmovz   r14, rax
0x180018f87  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180018f8e  jz      short loc_180018FA2
0x180018f90  mov     r9d, r15d
0x180018f93  lea     rdx, OmaDmInitiateSessionEvent
0x180018f9a  mov     r8, rsi
0x180018f9d  call    McTemplateU0zq_EventWriteTransfer
0x180018fa2  mov     r9d, [rsp+2F8h+var_298]
0x180018fa7  xor     eax, eax
0x180018fa9  mov     r8d, [rsp+2F8h+var_294]
0x180018fae  test    r13, r13
0x180018fb1  mov     rdx, rsi
0x180018fb4  mov     rcx, r13
0x180018fb7  setz    al
0x180018fba  mov     [rsp+2F8h+var_2A8], eax
0x180018fbe  mov     [rsp+2F8h+var_2B0], 1
0x180018fc6  mov     [rsp+2F8h+var_2B8], r15d
0x180018fcb  mov     dword ptr [rsp+2F8h+var_2C0], ebp
0x180018fcf  mov     [rsp+2F8h+var_2C8], r14
0x180018fd4  mov     [rsp+2F8h+var_2D0], ebx
0x180018fd8  mov     [rsp+2F8h+var_2D8], r12
0x180018fdd  call    ?OmaDmInitiateSessionWorker@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@W4OMADM_UIMODE@@PEAUOMADMALERTINFO@@KPEAEKW4PushRouterSubmitOrigin@@HH@Z; OmaDmInitiateSessionWorker(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,OMADM_UIMODE,OMADMALERTINFO *,ulong,uchar *,ulong,PushRouterSubmitOrigin,int,int)
0x180018fe2  mov     ebx, eax
0x180018fe4  test    eax, eax
0x180018fe6  js      short loc_18001900B
0x180018fe8  test    rdi, rdi
0x180018feb  jz      short loc_18001900B
0x180018fed  mov     r8, rdi
0x180018ff0  lea     rcx, [rsp+2F8h+var_268]
0x180018ff8  mov     edx, 104h
0x180018ffd  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180019004  nop     dword ptr [rax+rax+00h]
0x180019009  mov     ebx, eax
0x18001900b  lea     rbp, aOmadminitiates_9; "OmaDmInitiateSessionAsUser"
0x180019012  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180019019  jz      short loc_18001902D
0x18001901b  mov     r9d, ebx
0x18001901e  lea     rdx, FunctionReturnValueEvent
0x180019025  mov     r8, rbp
0x180019028  call    McTemplateU0zq_EventWriteTransfer
0x18001902d  mov     eax, ebx
0x18001902f  mov     rcx, [rsp+2F8h+var_58]
0x180019037  xor     rcx, rsp; StackCookie
0x18001903a  call    __security_check_cookie
0x18001903f  add     rsp, 2B8h
0x180019046  pop     r15
0x180019048  pop     r14
0x18001904a  pop     r13
0x18001904c  pop     r12
0x18001904e  pop     rdi
0x18001904f  pop     rsi
0x180019050  pop     rbp
0x180019051  pop     rbx
0x180019052  retn
```
