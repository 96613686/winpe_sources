# OmaDmInitiateSessionEx

- ea: `0x180019060`
- end: `0x180019245`
- name: `OmaDmInitiateSessionEx`
- size: `485`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018cb0`
- `0x18001a6a0`
- `0x18001a940`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x18000cbd8`
- `0x180014514`
- `0x180014698`
- `0x180019060`
- `0x18001d7f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019213`
- `DMCmnUtils!CopyString` at `0x1800191d4`
- `DMCmnUtils!CopyString` at `0x1800191d4`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSessionEx(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        unsigned __int16 **a6,
        unsigned int a7)
{
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int16 *v11; // rbx
  int CallerAuthenticatedUserSid; // edi
  unsigned __int16 *v13; // r12
  unsigned __int16 *v17; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+70h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  unsigned __int16 v22[264]; // [rsp+A0h] [rbp-60h] BYREF

  v18 = a4;
  memset_0(v22, 0, 0x208u);
  v11 = 0;
  v17 = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v20 = L"OmaDmInitiateSessionEx";
    v21 = 46;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      v10,
      2u,
      &v19);
  }
  if ( a1 )
  {
    if ( !a5 || a4 )
    {
      v13 = v22;
      if ( !a6 )
        v13 = 0;
      if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v9, OmaDmInitiateSessionEvent, a1, a7);
      CallerAuthenticatedUserSid = GetCallerAuthenticatedUserSid((HLOCAL *)&v17);
      if ( CallerAuthenticatedUserSid < 0 )
      {
        v11 = v17;
      }
      else
      {
        v11 = v17;
        CallerAuthenticatedUserSid = OmaDmInitiateSessionWorker(
                                       v17,
                                       a1,
                                       a2,
                                       a3,
                                       v18,
                                       a5,
                                       v13,
                                       a6 != 0 ? 0x208 : 0,
                                       a7,
                                       0,
                                       0);
        if ( CallerAuthenticatedUserSid >= 0 && a6 )
          CallerAuthenticatedUserSid = CopyString(v22, 0x104u, a6);
      }
    }
    else
    {
      CallerAuthenticatedUserSid = -2147024809;
    }
  }
  else
  {
    CallerAuthenticatedUserSid = -2147024809;
  }
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v9,
      FunctionReturnValueEvent,
      L"OmaDmInitiateSessionEx",
      (unsigned int)CallerAuthenticatedUserSid);
  if ( v11 )
    LocalFree(v11);
  return (unsigned int)CallerAuthenticatedUserSid;
}

```

## disassembly

```asm
0x180019060  push    rbp
0x180019062  push    rbx
0x180019063  push    rsi
0x180019064  push    rdi
0x180019065  push    r12
0x180019067  push    r13
0x180019069  push    r14
0x18001906b  push    r15
0x18001906d  lea     rbp, [rsp-1C8h]
0x180019075  sub     rsp, 2C8h
0x18001907c  mov     rax, cs:__security_cookie
0x180019083  xor     rax, rsp
0x180019086  mov     [rbp+200h+var_50], rax
0x18001908d  mov     rsi, [rbp+200h+arg_28]
0x180019094  mov     r14, rcx
0x180019097  mov     [rsp+300h+var_2A0], r8d
0x18001909c  lea     rcx, [rbp+200h+var_260]; void *
0x1800190a0  mov     [rsp+300h+var_29C], edx
0x1800190a4  mov     r12d, 208h
0x1800190aa  mov     r8d, r12d; Size
0x1800190ad  mov     [rsp+300h+var_290], r9
0x1800190b2  xor     edx, edx; Val
0x1800190b4  mov     rdi, r9
0x1800190b7  call    memset_0
0x1800190bc  xor     ebx, ebx
0x1800190be  lea     r15, aOmadminitiates_8; "OmaDmInitiateSessionEx"
0x1800190c5  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800190cc  mov     [rsp+300h+var_298], rbx
0x1800190d1  jz      short loc_180019100
0x1800190d3  lea     rax, [rsp+300h+var_288]
0x1800190d8  mov     [rbp+200h+var_278], r15
0x1800190dc  lea     r9d, [rbx+2]
0x1800190e0  mov     [rsp+300h+var_2E0], rax
0x1800190e5  lea     rdx, FunctionEntryPointEvent
0x1800190ec  mov     [rbp+200h+var_270], 2Eh ; '.'
0x1800190f4  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x1800190fb  call    McGenEventWrite_EventWriteTransfer
0x180019100  test    r14, r14
0x180019103  jnz     short loc_18001910F
0x180019105  mov     edi, 80070057h
0x18001910a  jmp     loc_1800191F0
0x18001910f  mov     r15d, [rbp+200h+arg_20]
0x180019116  test    r15d, r15d
0x180019119  jz      short loc_18001912A
0x18001911b  test    rdi, rdi
0x18001911e  jnz     short loc_18001912A
0x180019120  mov     edi, 80070057h
0x180019125  jmp     loc_1800191E9
0x18001912a  mov     r13d, [rbp+200h+arg_30]
0x180019131  xor     eax, eax
0x180019133  sub     rax, rsi
0x180019136  neg     rax
0x180019139  sbb     ebx, ebx
0x18001913b  xor     eax, eax
0x18001913d  and     ebx, r12d
0x180019140  lea     r12, [rbp+200h+var_260]
0x180019144  test    rsi, rsi
0x180019147  cmovz   r12, rax
0x18001914b  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180019152  jz      short loc_180019166
0x180019154  mov     r9d, r13d
0x180019157  lea     rdx, OmaDmInitiateSessionEvent
0x18001915e  mov     r8, r14
0x180019161  call    McTemplateU0zq_EventWriteTransfer
0x180019166  lea     rcx, [rsp+300h+var_298]; unsigned __int16 **
0x18001916b  call    ?GetCallerAuthenticatedUserSid@@YAJPEAPEAG@Z; GetCallerAuthenticatedUserSid(ushort * *)
0x180019170  mov     edi, eax
0x180019172  test    eax, eax
0x180019174  js      short loc_1800191E4
0x180019176  mov     rax, [rsp+300h+var_290]
0x18001917b  mov     rdx, r14
0x18001917e  mov     r9d, [rsp+300h+var_2A0]
0x180019183  mov     r8d, [rsp+300h+var_29C]
0x180019188  mov     [rsp+300h+var_2B0], 0
0x180019190  mov     [rsp+300h+var_2B8], 0
0x180019198  mov     [rsp+300h+var_2C0], r13d
0x18001919d  mov     [rsp+300h+var_2C8], ebx
0x1800191a1  mov     rbx, [rsp+300h+var_298]
0x1800191a6  mov     [rsp+300h+var_2D0], r12
0x1800191ab  mov     rcx, rbx
0x1800191ae  mov     [rsp+300h+var_2D8], r15d
0x1800191b3  mov     [rsp+300h+var_2E0], rax
0x1800191b8  call    ?OmaDmInitiateSessionWorker@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@W4OMADM_UIMODE@@PEAUOMADMALERTINFO@@KPEAEKW4PushRouterSubmitOrigin@@HH@Z; OmaDmInitiateSessionWorker(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,OMADM_UIMODE,OMADMALERTINFO *,ulong,uchar *,ulong,PushRouterSubmitOrigin,int,int)
0x1800191bd  mov     edi, eax
0x1800191bf  test    eax, eax
0x1800191c1  js      short loc_1800191E9
0x1800191c3  test    rsi, rsi
0x1800191c6  jz      short loc_1800191E9
0x1800191c8  mov     r8, rsi
0x1800191cb  lea     rcx, [rbp+200h+var_260]
0x1800191cf  mov     edx, 104h
0x1800191d4  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800191db  nop     dword ptr [rax+rax+00h]
0x1800191e0  mov     edi, eax
0x1800191e2  jmp     short loc_1800191E9
0x1800191e4  mov     rbx, [rsp+300h+var_298]
0x1800191e9  lea     r15, aOmadminitiates_8; "OmaDmInitiateSessionEx"
0x1800191f0  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800191f7  jz      short loc_18001920B
0x1800191f9  mov     r9d, edi
0x1800191fc  lea     rdx, FunctionReturnValueEvent
0x180019203  mov     r8, r15
0x180019206  call    McTemplateU0zq_EventWriteTransfer
0x18001920b  test    rbx, rbx
0x18001920e  jz      short loc_18001921F
0x180019210  mov     rcx, rbx; hMem
0x180019213  call    cs:__imp_LocalFree
0x18001921a  nop     dword ptr [rax+rax+00h]
0x18001921f  mov     eax, edi
0x180019221  mov     rcx, [rbp+200h+var_50]
0x180019228  xor     rcx, rsp; StackCookie
0x18001922b  call    __security_check_cookie
0x180019230  add     rsp, 2C8h
0x180019237  pop     r15
0x180019239  pop     r14
0x18001923b  pop     r13
0x18001923d  pop     r12
0x18001923f  pop     rdi
0x180019240  pop     rsi
0x180019241  pop     rbx
0x180019242  pop     rbp
0x180019243  retn
```
