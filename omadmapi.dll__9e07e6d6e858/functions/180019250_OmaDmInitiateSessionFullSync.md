# OmaDmInitiateSessionFullSync

- ea: `0x180019250`
- end: `0x180019400`
- name: `OmaDmInitiateSessionFullSync`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180014514`
- `0x180014698`
- `0x180019250`
- `0x18001d7f0`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x1800193a9`
- `DMCmnUtils!CopyString` at `0x1800193a9`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSessionFullSync(
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
    v19 = L"OmaDmInitiateSessionFullSync";
    v20 = 58;
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
    v12 = OmaDmInitiateSessionWorker(a1, a2, a3, a4, a5, a6, v13, v15, a8, 0, 1);
    if ( v12 >= 0 && a7 )
      v12 = CopyString(v21, 0x104u, a7);
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v10, FunctionReturnValueEvent, L"OmaDmInitiateSessionFullSync", (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180019250  push    rbx
0x180019252  push    rbp
0x180019253  push    rsi
0x180019254  push    rdi
0x180019255  push    r12
0x180019257  push    r13
0x180019259  push    r14
0x18001925b  push    r15
0x18001925d  sub     rsp, 2B8h
0x180019264  mov     rax, cs:__security_cookie
0x18001926b  xor     rax, rsp
0x18001926e  mov     [rsp+2F8h+var_58], rax
0x180019276  mov     r12, [rsp+2F8h+arg_20]
0x18001927e  mov     rsi, rdx
0x180019281  mov     rdi, [rsp+2F8h+arg_30]
0x180019289  mov     r13, rcx
0x18001928c  mov     [rsp+2F8h+var_294], r8d
0x180019291  lea     rcx, [rsp+2F8h+var_268]; void *
0x180019299  mov     r14d, 208h
0x18001929f  mov     [rsp+2F8h+var_298], r9d
0x1800192a4  mov     r8d, r14d; Size
0x1800192a7  xor     edx, edx; Val
0x1800192a9  call    memset_0
0x1800192ae  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800192b5  lea     rbp, aOmadminitiates_6; "OmaDmInitiateSessionFullSync"
0x1800192bc  jz      short loc_1800192F2
0x1800192be  lea     rax, [rsp+2F8h+var_290]
0x1800192c3  mov     [rsp+2F8h+var_280], rbp
0x1800192c8  mov     r9d, 2
0x1800192ce  mov     [rsp+2F8h+var_2D8], rax
0x1800192d3  lea     rdx, FunctionEntryPointEvent
0x1800192da  mov     [rsp+2F8h+var_278], 3Ah ; ':'
0x1800192e6  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x1800192ed  call    McGenEventWrite_EventWriteTransfer
0x1800192f2  test    rsi, rsi
0x1800192f5  jnz     short loc_180019301
0x1800192f7  mov     ebx, 80070057h
0x1800192fc  jmp     loc_1800193BE
0x180019301  mov     ebx, [rsp+2F8h+arg_28]
0x180019308  test    ebx, ebx
0x18001930a  jz      short loc_180019311
0x18001930c  test    r12, r12
0x18001930f  jz      short loc_1800192F7
0x180019311  mov     r15d, [rsp+2F8h+arg_38]
0x180019319  xor     eax, eax
0x18001931b  sub     rax, rdi
0x18001931e  neg     rax
0x180019321  sbb     ebp, ebp
0x180019323  xor     eax, eax
0x180019325  and     ebp, r14d
0x180019328  lea     r14, [rsp+2F8h+var_268]
0x180019330  test    rdi, rdi
0x180019333  cmovz   r14, rax
0x180019337  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x18001933e  jz      short loc_180019352
0x180019340  mov     r9d, r15d
0x180019343  lea     rdx, OmaDmInitiateSessionEvent
0x18001934a  mov     r8, rsi
0x18001934d  call    McTemplateU0zq_EventWriteTransfer
0x180019352  mov     r9d, [rsp+2F8h+var_298]
0x180019357  mov     rdx, rsi
0x18001935a  mov     r8d, [rsp+2F8h+var_294]
0x18001935f  mov     rcx, r13
0x180019362  mov     [rsp+2F8h+var_2A8], 1
0x18001936a  mov     [rsp+2F8h+var_2B0], 0
0x180019372  mov     [rsp+2F8h+var_2B8], r15d
0x180019377  mov     dword ptr [rsp+2F8h+var_2C0], ebp
0x18001937b  mov     [rsp+2F8h+var_2C8], r14
0x180019380  mov     [rsp+2F8h+var_2D0], ebx
0x180019384  mov     [rsp+2F8h+var_2D8], r12
0x180019389  call    ?OmaDmInitiateSessionWorker@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@W4OMADM_UIMODE@@PEAUOMADMALERTINFO@@KPEAEKW4PushRouterSubmitOrigin@@HH@Z; OmaDmInitiateSessionWorker(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,OMADM_UIMODE,OMADMALERTINFO *,ulong,uchar *,ulong,PushRouterSubmitOrigin,int,int)
0x18001938e  mov     ebx, eax
0x180019390  test    eax, eax
0x180019392  js      short loc_1800193B7
0x180019394  test    rdi, rdi
0x180019397  jz      short loc_1800193B7
0x180019399  mov     r8, rdi
0x18001939c  lea     rcx, [rsp+2F8h+var_268]
0x1800193a4  mov     edx, 104h
0x1800193a9  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800193b0  nop     dword ptr [rax+rax+00h]
0x1800193b5  mov     ebx, eax
0x1800193b7  lea     rbp, aOmadminitiates_6; "OmaDmInitiateSessionFullSync"
0x1800193be  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800193c5  jz      short loc_1800193D9
0x1800193c7  mov     r9d, ebx
0x1800193ca  lea     rdx, FunctionReturnValueEvent
0x1800193d1  mov     r8, rbp
0x1800193d4  call    McTemplateU0zq_EventWriteTransfer
0x1800193d9  mov     eax, ebx
0x1800193db  mov     rcx, [rsp+2F8h+var_58]
0x1800193e3  xor     rcx, rsp; StackCookie
0x1800193e6  call    __security_check_cookie
0x1800193eb  add     rsp, 2B8h
0x1800193f2  pop     r15
0x1800193f4  pop     r14
0x1800193f6  pop     r13
0x1800193f8  pop     r12
0x1800193fa  pop     rdi
0x1800193fb  pop     rsi
0x1800193fc  pop     rbp
0x1800193fd  pop     rbx
0x1800193fe  retn
```
