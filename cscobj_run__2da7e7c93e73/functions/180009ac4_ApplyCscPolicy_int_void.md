# ApplyCscPolicy(int,void *)

- ea: `0x180009ac4`
- end: `0x180009d47`
- name: `?ApplyCscPolicy@@YAJHPEAX@Z`
- size: `643`
- prototype: `int(int, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f820`
- `0x18001fdb0`

## callees

- `0x180002040`
- `0x1800057e0`
- `0x180009ac4`
- `0x180009d50`
- `0x18000f5cc`
- `0x180013a44`
- `0x18002254c`
- `0x18002a808`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009cd1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009ba4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009ba4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009b3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009b3d`

## pseudocode

```c
__int64 __fastcall ApplyCscPolicy(int a1, void *a2, __int64 a3)
{
  const char *v5; // r9
  signed int LastError; // ebx
  HANDLE EventW; // rax
  void *v8; // rsi
  unsigned int v9; // eax
  const struct _GUID *v10; // rdx
  bool v11; // sf
  void *v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // edi
  _QWORD v19[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-20h]
  __int64 v21; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+48h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    v5 = "User";
    if ( !a1 )
      v5 = "Machine";
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), a2, a3, v5);
  }
  LastError = -2147023553;
  if ( (unsigned int)CscPolAuth_ReadPolicyAuthority() == 1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v8 = EventW;
    if ( EventW )
    {
      v9 = ProcessPolicy_Internal(a1 == 0, a2, 0, EventW, 0);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 109, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v9);
      }
      LastError = WaitForSingleObject(v8, 0xFFFFFFFF);
      if ( LastError == -1 )
        LastError = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          110,
          WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)LastError);
      }
      v11 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError < 0;
      }
      if ( !v11 )
      {
        CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)v19, v10);
        v21 = 0;
        v13 = CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT((__int64)v19, v12, &v21);
        v15 = v13;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 111, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v13);
        }
        if ( v15 < 0 )
        {
          LastError = -2147023838;
        }
        else
        {
          LOBYTE(v14) = a1 != 0;
          v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 520LL))(v21, v14);
          LastError = v16;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 112, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v16);
          }
        }
        ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(&v21);
        v17 = v20;
        v19[0] = &CInterfaceInGITBase::`vftable';
        if ( v20 )
        {
          ppv = 0;
          if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
          {
            (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v17);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
      }
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 113, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, 2147943743LL);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009ac4  mov     [rsp-28h+arg_0], rbx
0x180009ac9  mov     [rsp-28h+arg_8], rsi
0x180009ace  push    rbp
0x180009acf  push    rdi
0x180009ad0  push    r13
0x180009ad2  push    r14
0x180009ad4  push    r15
0x180009ad6  mov     rbp, rsp
0x180009ad9  sub     rsp, 60h
0x180009add  mov     rdi, rdx
0x180009ae0  mov     r14d, ecx
0x180009ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aea  lea     r15, WPP_GLOBAL_Control
0x180009af1  mov     r13d, 4000000h
0x180009af7  cmp     rcx, r15
0x180009afa  jz      short loc_180009B20
0x180009afc  test    [rcx+1Ch], r13d
0x180009b00  jz      short loc_180009B20
0x180009b02  mov     rcx, [rcx+10h]
0x180009b06  lea     rax, aMachine; "Machine"
0x180009b0d  test    r14d, r14d
0x180009b10  lea     r9, aUser; "User"
0x180009b17  cmovz   r9, rax
0x180009b1b  call    WPP_SF_s
0x180009b20  mov     ebx, 8007053Fh
0x180009b25  call    ?CscPolAuth_ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ; CscPolAuth_ReadPolicyAuthority(void)
0x180009b2a  cmp     eax, 1
0x180009b2d  jnz     loc_180009CFF
0x180009b33  xor     r9d, r9d; lpName
0x180009b36  xor     r8d, r8d; bInitialState
0x180009b39  xor     edx, edx; bManualReset
0x180009b3b  xor     ecx, ecx; lpEventAttributes
0x180009b3d  call    cs:__imp_CreateEventW
0x180009b43  mov     rsi, rax
0x180009b46  test    rax, rax
0x180009b49  jz      loc_180009D2C
0x180009b4f  xor     ecx, ecx
0x180009b51  mov     dword ptr [rsp+60h+ppv], 0; int
0x180009b59  test    r14d, r14d
0x180009b5c  mov     r9, rax; void *
0x180009b5f  mov     rdx, rdi; void *
0x180009b62  setz    cl; unsigned int
0x180009b65  xor     r8d, r8d; unsigned __int64
0x180009b68  call    ?ProcessPolicy_Internal@@YAKKPEAX_K0H@Z; ProcessPolicy_Internal(ulong,void *,unsigned __int64,void *,int)
0x180009b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b74  lea     rdi, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180009b7b  cmp     rcx, r15
0x180009b7e  jz      short loc_180009B9A
0x180009b80  test    [rcx+1Ch], r13d
0x180009b84  jz      short loc_180009B9A
0x180009b86  mov     rcx, [rcx+10h]
0x180009b8a  mov     edx, 6Dh ; 'm'
0x180009b8f  mov     r9d, eax
0x180009b92  mov     r8, rdi
0x180009b95  call    WPP_SF_d
0x180009b9a  or      r15d, 0FFFFFFFFh
0x180009b9e  mov     rcx, rsi; hHandle
0x180009ba1  mov     edx, r15d; dwMilliseconds
0x180009ba4  call    cs:__imp_WaitForSingleObject
0x180009baa  mov     ebx, eax
0x180009bac  cmp     eax, r15d
0x180009baf  jnz     short loc_180009BB9
0x180009bb1  call    cs:__imp_GetLastError
0x180009bb7  mov     ebx, eax
0x180009bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bc0  lea     rsi, WPP_GLOBAL_Control
0x180009bc7  cmp     rcx, rsi
0x180009bca  jz      short loc_180009BE6
0x180009bcc  test    [rcx+1Ch], r13d
0x180009bd0  jz      short loc_180009BE6
0x180009bd2  mov     rcx, [rcx+10h]
0x180009bd6  mov     edx, 6Eh ; 'n'
0x180009bdb  mov     r9d, ebx
0x180009bde  mov     r8, rdi
0x180009be1  call    WPP_SF_d
0x180009be6  test    ebx, ebx
0x180009be8  jle     short loc_180009BF5
0x180009bea  movzx   ebx, bx
0x180009bed  or      ebx, 80070000h
0x180009bf3  test    ebx, ebx
0x180009bf5  js      loc_180009D2C
0x180009bfb  lea     rcx, [rbp+var_30]; this
0x180009bff  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x180009c04  lea     r8, [rbp+arg_10]
0x180009c08  mov     [rbp+arg_10], 0
0x180009c10  lea     rcx, [rbp+var_30]
0x180009c14  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x180009c19  mov     ebx, eax
0x180009c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c22  cmp     rcx, rsi
0x180009c25  jz      short loc_180009C41
0x180009c27  test    [rcx+1Ch], r13d
0x180009c2b  jz      short loc_180009C41
0x180009c2d  mov     rcx, [rcx+10h]
0x180009c31  mov     edx, 6Fh ; 'o'
0x180009c36  mov     r9d, eax
0x180009c39  mov     r8, rdi
0x180009c3c  call    WPP_SF_d
0x180009c41  test    ebx, ebx
0x180009c43  js      short loc_180009C88
0x180009c45  mov     rcx, [rbp+arg_10]
0x180009c49  test    r14d, r14d
0x180009c4c  setnz   dl
0x180009c4f  mov     rax, [rcx]
0x180009c52  mov     rax, [rax+208h]
0x180009c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c5e  mov     ebx, eax
0x180009c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c67  cmp     rcx, rsi
0x180009c6a  jz      short loc_180009C8D
0x180009c6c  test    [rcx+1Ch], r13d
0x180009c70  jz      short loc_180009C8D
0x180009c72  mov     rcx, [rcx+10h]
0x180009c76  mov     edx, 70h ; 'p'
0x180009c7b  mov     r9d, eax
0x180009c7e  mov     r8, rdi
0x180009c81  call    WPP_SF_d
0x180009c86  jmp     short loc_180009C8D
0x180009c88  mov     ebx, 80070422h
0x180009c8d  lea     rcx, [rbp+arg_10]
0x180009c91  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x180009c96  mov     edi, [rbp+var_20]
0x180009c99  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x180009ca0  mov     [rbp+var_30], rax
0x180009ca4  test    edi, edi
0x180009ca6  jz      loc_180009D2C
0x180009cac  xor     edx, edx; pUnkOuter
0x180009cae  mov     [rbp+arg_18], 0
0x180009cb6  lea     rax, [rbp+arg_18]
0x180009cba  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009cc1  mov     [rsp+60h+ppv], rax; ppv
0x180009cc6  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009ccd  lea     r8d, [rdx+1]; dwClsContext
0x180009cd1  call    cs:__imp_CoCreateInstance
0x180009cd7  test    eax, eax
0x180009cd9  js      short loc_180009D2C
0x180009cdb  mov     rcx, [rbp+arg_18]
0x180009cdf  mov     edx, edi
0x180009ce1  mov     rax, [rcx]
0x180009ce4  mov     rax, [rax+20h]
0x180009ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ced  mov     rcx, [rbp+arg_18]
0x180009cf1  mov     rax, [rcx]
0x180009cf4  mov     rax, [rax+10h]
0x180009cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cfd  jmp     short loc_180009D2C
0x180009cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d06  cmp     rcx, r15
0x180009d09  jz      short loc_180009D2C
0x180009d0b  test    [rcx+1Ch], r13d
0x180009d0f  jz      short loc_180009D2C
0x180009d11  mov     rcx, [rcx+10h]
0x180009d15  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180009d1c  mov     edx, 71h ; 'q'
0x180009d21  mov     r9d, 8007053Fh
0x180009d27  call    WPP_SF_d
0x180009d2c  lea     r11, [rsp+60h+var_s0]
0x180009d31  mov     eax, ebx
0x180009d33  mov     rbx, [r11+30h]
0x180009d37  mov     rsi, [r11+38h]
0x180009d3b  mov     rsp, r11
0x180009d3e  pop     r15
0x180009d40  pop     r14
0x180009d42  pop     r13
0x180009d44  pop     rdi
0x180009d45  pop     rbp
0x180009d46  retn
```
