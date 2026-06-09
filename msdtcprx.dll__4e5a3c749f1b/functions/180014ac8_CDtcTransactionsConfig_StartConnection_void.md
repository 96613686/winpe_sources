# CDtcTransactionsConfig::StartConnection(void)

- ea: `0x180014ac8`
- end: `0x180014db3`
- name: `?StartConnection@CDtcTransactionsConfig@@AEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(CDtcTransactionsConfig *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017c94`

## callees

- `0x180003cf0`
- `0x180006880`
- `0x180014ac8`
- `0x18004c3fc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d16`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180014b54`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180014b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b73`

## string_xrefs

- `0x180014b88`: `CreateEvent failed`
- `0x180014af8`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x180014b0d`: `CDtcTransactionsConfig::StartConnection`
- `0x180014bef`: `CDtcTransactionsConfig::StartConnection`
- `0x180014c2a`: `CDtcTransactionsConfig::StartConnection`
- `0x180014c54`: `CDtcTransactionsConfig::StartConnection`
- `0x180014c8b`: `CDtcTransactionsConfig::StartConnection`
- `0x180014cb9`: `CDtcTransactionsConfig::StartConnection`
- `0x180014cde`: `CDtcTransactionsConfig::StartConnection`
- `0x180014b9e`: `ClientNetworkProtocol`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::StartConnection(CDtcTransactionsConfig *this)
{
  struct INameObject *v1; // rdi
  signed int LastError; // eax
  signed int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  unsigned int v7; // ebp
  struct INameObject *v8; // rax
  __int64 v10; // [rsp+28h] [rbp-40h]
  struct IProperties *v11; // [rsp+70h] [rbp+8h] BYREF
  __int64 v12; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  v11 = 0;
  v12 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    46,
    L"CDtcTransactionsConfig::StartConnection",
    0,
    L"In");
  if ( *((_QWORD *)this + 7) )
    goto LABEL_8;
  (**((void (__fastcall ***)(char *))this + 10))((char *)this + 80);
  if ( !*((_QWORD *)this + 7) )
    *((_QWORD *)this + 7) = CreateEventA(0, 1, 0, 0);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
  if ( *((_QWORD *)this + 7) )
  {
LABEL_8:
    v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL) + 344LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
           L"ClientNetworkProtocol",
           33);
    v4 = (*(__int64 (__fastcall **)(_QWORD, struct IProperties **))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL) + 152LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
           &v11);
    if ( v4 >= 0 )
    {
      v4 = (**(__int64 (__fastcall ***)(struct IProperties *, GUID *, __int64 *))v11)(v11, &IID_ICustomProperties, &v12);
      if ( v4 >= 0 )
      {
        v8 = ContactToNameObject(v11);
        v1 = v8;
        if ( v8 )
        {
          v4 = (*(__int64 (__fastcall **)(struct INameObject *, _QWORD))(*(_QWORD *)v8 + 104LL))(v8, 0);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(struct INameObject *, __int64))(*(_QWORD *)v1 + 136LL))(v1, 1);
            if ( v4 >= 0 )
            {
              (*(void (__fastcall **)(struct INameObject *, _QWORD))(*(_QWORD *)v1 + 48LL))(v1, v7);
              v4 = CDtcTransactionsConfig::DoConnection(this, v1);
              if ( v4 >= 0 )
                goto LABEL_21;
              v5 = L"Failed to start connection";
              v6 = 111;
            }
            else
            {
              v5 = L"SetIsMSDTC call failed for MSDTCUIS.";
              v6 = 102;
            }
          }
          else
          {
            v5 = L"SetSPN call failed for MSDTCUIS.";
            v6 = 95;
          }
        }
        else
        {
          v4 = -2147024882;
          v5 = L"Out of memory converting UI contact";
          v6 = 88;
        }
      }
      else
      {
        v5 = L"UI contact does not support ICP";
        v6 = 80;
      }
    }
    else
    {
      v5 = L"Failed to get the UI contact";
      v6 = 72;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"CreateEvent failed";
    v6 = 60;
  }
  LODWORD(v10) = v4;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    v6,
    L"CDtcTransactionsConfig::StartConnection",
    v10,
    v5);
LABEL_21:
  CoTaskMemFree(0);
  if ( v1 )
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(struct IProperties *))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  LODWORD(v10) = v4;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    121,
    L"CDtcTransactionsConfig::StartConnection",
    v10,
    L"Out");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014ac8  mov     r11, rsp
0x180014acb  mov     [r11+18h], rbx
0x180014acf  mov     [r11+20h], rbp
0x180014ad3  push    rsi
0x180014ad4  push    rdi
0x180014ad5  push    r12
0x180014ad7  push    r13
0x180014ad9  push    r15
0x180014adb  sub     rsp, 40h
0x180014adf  xor     edi, edi
0x180014ae1  mov     qword ptr [r11+8], 0
0x180014ae9  lea     rax, aIn_0; "In"
0x180014af0  mov     [r11+10h], rdi
0x180014af4  mov     [r11-38h], rax
0x180014af8  lea     r12, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180014aff  mov     rsi, rcx
0x180014b02  mov     [r11-40h], rdi
0x180014b06  lea     r13d, [rdi+0Fh]
0x180014b0a  mov     r8, r12
0x180014b0d  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014b14  mov     ecx, r13d
0x180014b17  lea     r9d, [rdi+2Eh]
0x180014b1b  mov     [r11-48h], rbp
0x180014b1f  lea     edx, [rdi+6]
0x180014b22  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014b27  lea     r15d, [rdi+1]
0x180014b2b  cmp     [rsi+38h], rdi
0x180014b2f  jnz     short loc_180014B9A
0x180014b31  lea     rbx, [rsi+50h]
0x180014b35  mov     rax, [rbx]
0x180014b38  mov     rcx, rbx
0x180014b3b  mov     rax, [rax]
0x180014b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b43  cmp     [rsi+38h], rdi
0x180014b47  jnz     short loc_180014B5E
0x180014b49  xor     r9d, r9d; lpName
0x180014b4c  xor     r8d, r8d; bInitialState
0x180014b4f  mov     edx, r15d; bManualReset
0x180014b52  xor     ecx, ecx; lpEventAttributes
0x180014b54  call    cs:__imp_CreateEventA
0x180014b5a  mov     [rsi+38h], rax
0x180014b5e  mov     rax, [rbx]
0x180014b61  mov     rcx, rbx
0x180014b64  mov     rax, [rax+10h]
0x180014b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b6d  cmp     [rsi+38h], rdi
0x180014b71  jnz     short loc_180014B9A
0x180014b73  call    cs:__imp_GetLastError
0x180014b79  mov     ebx, eax
0x180014b7b  test    eax, eax
0x180014b7d  jle     short loc_180014B88
0x180014b7f  movzx   ebx, ax
0x180014b82  or      ebx, 80070000h
0x180014b88  lea     rax, aCreateeventFai; "CreateEvent failed"
0x180014b8f  mov     r9d, 3Ch ; '<'
0x180014b95  jmp     loc_180014CF8
0x180014b9a  mov     rax, [rsi+18h]
0x180014b9e  lea     rdx, aClientnetworkp; "ClientNetworkProtocol"
0x180014ba5  mov     r8d, 21h ; '!'
0x180014bab  mov     rcx, [rax+8]
0x180014baf  mov     rax, [rcx]
0x180014bb2  mov     rax, [rax+158h]
0x180014bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bbe  mov     ebp, eax
0x180014bc0  lea     rdx, [rsp+68h+arg_0]
0x180014bc5  mov     rax, [rsi+18h]
0x180014bc9  mov     rcx, [rax+8]
0x180014bcd  mov     rax, [rcx]
0x180014bd0  mov     rax, [rax+98h]
0x180014bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bdc  mov     ebx, eax
0x180014bde  test    eax, eax
0x180014be0  jns     short loc_180014BFB
0x180014be2  lea     rax, aFailedToGetThe_6; "Failed to get the UI contact"
0x180014be9  mov     r9d, 48h ; 'H'
0x180014bef  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014bf6  jmp     loc_180014CF8
0x180014bfb  mov     rcx, [rsp+68h+arg_0]
0x180014c00  lea     r8, [rsp+68h+arg_8]
0x180014c05  lea     rdx, IID_ICustomProperties
0x180014c0c  mov     rax, [rcx]
0x180014c0f  mov     rax, [rax]
0x180014c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c17  mov     ebx, eax
0x180014c19  test    eax, eax
0x180014c1b  jns     short loc_180014C36
0x180014c1d  lea     rax, aUiContactDoesN; "UI contact does not support ICP"
0x180014c24  mov     r9d, 50h ; 'P'
0x180014c2a  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014c31  jmp     loc_180014CF8
0x180014c36  mov     rcx, [rsp+68h+arg_0]; struct IProperties *
0x180014c3b  call    ?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z; ContactToNameObject(IProperties *)
0x180014c40  mov     rdi, rax
0x180014c43  test    rax, rax
0x180014c46  jnz     short loc_180014C64
0x180014c48  mov     ebx, 8007000Eh
0x180014c4d  lea     rax, aOutOfMemoryCon; "Out of memory converting UI contact"
0x180014c54  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014c5b  lea     r9d, [rdi+58h]
0x180014c5f  jmp     loc_180014CF8
0x180014c64  mov     rax, [rax]
0x180014c67  xor     edx, edx
0x180014c69  mov     rcx, rdi
0x180014c6c  mov     rax, [rax+68h]
0x180014c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c75  mov     ebx, eax
0x180014c77  mov     edx, r15d
0x180014c7a  test    eax, eax
0x180014c7c  jns     short loc_180014C94
0x180014c7e  lea     rax, aSetspnCallFail; "SetSPN call failed for MSDTCUIS."
0x180014c85  mov     r9d, 5Fh ; '_'
0x180014c8b  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014c92  jmp     short loc_180014CFB
0x180014c94  mov     rax, [rdi]
0x180014c97  mov     rcx, rdi
0x180014c9a  mov     rax, [rax+88h]
0x180014ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca6  mov     ebx, eax
0x180014ca8  test    eax, eax
0x180014caa  jns     short loc_180014CC2
0x180014cac  lea     rax, aSetismsdtcCall; "SetIsMSDTC call failed for MSDTCUIS."
0x180014cb3  mov     r9d, 66h ; 'f'
0x180014cb9  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014cc0  jmp     short loc_180014CF8
0x180014cc2  mov     rax, [rdi]
0x180014cc5  mov     edx, ebp
0x180014cc7  mov     rcx, rdi
0x180014cca  mov     rax, [rax+30h]
0x180014cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd3  mov     rdx, rdi; struct INameObject *
0x180014cd6  mov     rcx, rsi; this
0x180014cd9  call    ?DoConnection@CDtcTransactionsConfig@@AEAAJPEAUINameObject@@@Z; CDtcTransactionsConfig::DoConnection(INameObject *)
0x180014cde  lea     rbp, aCdtctransactio_2; "CDtcTransactionsConfig::StartConnection"
0x180014ce5  mov     ebx, eax
0x180014ce7  test    eax, eax
0x180014ce9  jns     short loc_180014D14
0x180014ceb  lea     rax, aFailedToStartC; "Failed to start connection"
0x180014cf2  mov     r9d, 6Fh ; 'o'
0x180014cf8  mov     edx, r15d
0x180014cfb  mov     [rsp+68h+var_38], rax
0x180014d00  mov     r8, r12
0x180014d03  mov     dword ptr [rsp+68h+var_40], ebx
0x180014d07  mov     ecx, r13d
0x180014d0a  mov     [rsp+68h+var_48], rbp
0x180014d0f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014d14  xor     ecx, ecx; pv
0x180014d16  call    cs:__imp_CoTaskMemFree
0x180014d1c  test    rdi, rdi
0x180014d1f  jz      short loc_180014D30
0x180014d21  mov     rax, [rdi]
0x180014d24  mov     rcx, rdi
0x180014d27  mov     rax, [rax+10h]
0x180014d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d30  mov     rcx, [rsp+68h+arg_8]
0x180014d35  test    rcx, rcx
0x180014d38  jz      short loc_180014D4F
0x180014d3a  mov     rax, [rcx]
0x180014d3d  mov     rax, [rax+10h]
0x180014d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d46  mov     [rsp+68h+arg_8], 0
0x180014d4f  mov     rcx, [rsp+68h+arg_0]
0x180014d54  test    rcx, rcx
0x180014d57  jz      short loc_180014D6E
0x180014d59  mov     rax, [rcx]
0x180014d5c  mov     rax, [rax+10h]
0x180014d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d65  mov     [rsp+68h+arg_0], 0
0x180014d6e  mov     r9d, 79h ; 'y'
0x180014d74  lea     rax, aOut; "Out"
0x180014d7b  mov     [rsp+68h+var_38], rax
0x180014d80  mov     r8, r12
0x180014d83  mov     dword ptr [rsp+68h+var_40], ebx
0x180014d87  mov     ecx, r13d
0x180014d8a  mov     [rsp+68h+var_48], rbp
0x180014d8f  lea     edx, [r9-73h]
0x180014d93  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014d98  lea     r11, [rsp+68h+var_28]
0x180014d9d  mov     eax, ebx
0x180014d9f  mov     rbx, [r11+40h]
0x180014da3  mov     rbp, [r11+48h]
0x180014da7  mov     rsp, r11
0x180014daa  pop     r15
0x180014dac  pop     r13
0x180014dae  pop     r12
0x180014db0  pop     rdi
0x180014db1  pop     rsi
0x180014db2  retn
```
