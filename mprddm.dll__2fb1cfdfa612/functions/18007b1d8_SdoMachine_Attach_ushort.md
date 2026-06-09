# SdoMachine::Attach(ushort *)

- ea: `0x18007b1d8`
- end: `0x18007b405`
- name: `?Attach@SdoMachine@@QEAAJPEAG@Z`
- size: `557`
- prototype: `__int64 __fastcall(SdoMachine *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007aa4c`

## callees

- `0x180071cec`
- `0x18007b1d8`
- `0x18007b40c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007b2af`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b2af`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b34a`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b34a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b23d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b23d`

## string_xrefs

- `0x18007b259`: `CoCreateInstance SdoMachine failed %x\n`
- `0x18007b362`: `SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n`
- `0x18007b29f`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall SdoMachine::Attach(LPVOID *this, unsigned __int16 *a2)
{
  HRESULT Instance; // eax
  int v5; // ebx
  const wchar_t *v6; // rdx
  OLECHAR *v7; // r14
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, OLECHAR *, __int64 *); // rbx
  enum _IASDATASTORE DataStore; // eax
  LPVOID v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  Instance = CoCreateInstance(&CLSID_SdoMachine, 0, 1u, &IID_ISdoMachine, this);
  v5 = Instance;
  if ( Instance < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800C9F60 + 1) )
      goto LABEL_23;
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"CoCreateInstance SdoMachine failed %x\n", (unsigned int)Instance);
    goto LABEL_22;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)*this + 56LL))(*this, a2);
  if ( v5 < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800C9F60 + 1) )
      goto LABEL_23;
    v6 = L"SdoMachine::Attach failed %x\n";
LABEL_21:
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, v6, (unsigned int)v5);
LABEL_22:
    ((void (__fastcall *)(__int64, _QWORD, int *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      *((_QWORD *)&xmmword_1800C9F60 + 1),
      &v14);
LABEL_23:
    v11 = this[3];
    if ( v11 && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11) )
      this[3] = 0;
    if ( *this && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)*this + 16LL))(*this) )
      *this = 0;
    return (unsigned int)v5;
  }
  v13 = 0;
  v7 = SysAllocString(L"RemoteAccess");
  if ( v7 )
  {
    v8 = *this;
    v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64 *))(*(_QWORD *)*this + 72LL);
    DataStore = SdoMachine::GetDataStore((SdoMachine *)this);
    v5 = v9(v8, (unsigned int)DataStore, v7, &v13);
    if ( v5 >= 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v13)(v13, &IID_ISdo, (char *)this + 24);
      if ( v5 >= 0 && !this[3] )
        v5 = -2147467259;
    }
  }
  else
  {
    v5 = -2147024882;
  }
  if ( v13 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13) )
    v13 = 0;
  if ( v7 )
    SysFreeString(v7);
  if ( v5 < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800C9F60 + 1) )
      goto LABEL_23;
    v6 = L"SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n";
    goto LABEL_21;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007b1d8  mov     [rsp-8+arg_10], rbx
0x18007b1dd  mov     [rsp-8+arg_18], rsi
0x18007b1e2  push    rbp
0x18007b1e3  push    rdi
0x18007b1e4  push    r14
0x18007b1e6  lea     rbp, [rsp-750h]
0x18007b1ee  sub     rsp, 850h
0x18007b1f5  mov     rax, cs:__security_cookie
0x18007b1fc  xor     rax, rsp
0x18007b1ff  mov     [rbp+760h+var_20], rax
0x18007b206  mov     rdi, rdx
0x18007b209  mov     rsi, rcx
0x18007b20c  xor     eax, eax
0x18007b20e  lea     rcx, [rsp+860h+var_81C]; void *
0x18007b213  xor     edx, edx; Val
0x18007b215  mov     [rsp+860h+var_820], eax
0x18007b219  mov     r8d, 7FCh; Size
0x18007b21f  call    memset_0
0x18007b224  xor     edx, edx; pUnkOuter
0x18007b226  mov     [rsp+860h+ppv], rsi; ppv
0x18007b22b  lea     r9, IID_ISdoMachine; riid
0x18007b232  lea     rcx, CLSID_SdoMachine; rclsid
0x18007b239  lea     r8d, [rdx+1]; dwClsContext
0x18007b23d  call    cs:__imp_CoCreateInstance
0x18007b243  mov     ebx, eax
0x18007b245  test    eax, eax
0x18007b247  jns     short loc_18007B26D
0x18007b249  cmp     qword ptr cs:xmmword_1800C9F60+8, 0
0x18007b251  jz      loc_18007B39C
0x18007b257  xor     ecx, ecx
0x18007b259  lea     rdx, aCocreateinstan; "CoCreateInstance SdoMachine failed %x\n"
0x18007b260  mov     word ptr [rsp+860h+var_820], cx
0x18007b265  mov     r8d, eax
0x18007b268  jmp     loc_18007B373
0x18007b26d  mov     rcx, [rsi]
0x18007b270  mov     rdx, rdi
0x18007b273  mov     rax, [rcx]
0x18007b276  mov     rax, [rax+38h]
0x18007b27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b27f  mov     ebx, eax
0x18007b281  test    eax, eax
0x18007b283  jns     short loc_18007B29F
0x18007b285  cmp     qword ptr cs:xmmword_1800C9F60+8, 0
0x18007b28d  jz      loc_18007B39C
0x18007b293  lea     rdx, aSdomachineAtta; "SdoMachine::Attach failed %x\n"
0x18007b29a  jmp     loc_18007B369
0x18007b29f  lea     rcx, aRemoteaccess_0; "RemoteAccess"
0x18007b2a6  mov     [rsp+860h+var_830], 0
0x18007b2af  call    cs:__imp_SysAllocString
0x18007b2b5  mov     r14, rax
0x18007b2b8  test    rax, rax
0x18007b2bb  jnz     short loc_18007B2C4
0x18007b2bd  mov     ebx, 8007000Eh
0x18007b2c2  jmp     short loc_18007B31F
0x18007b2c4  mov     rdi, [rsi]
0x18007b2c7  mov     rcx, rsi; this
0x18007b2ca  mov     rax, [rdi]
0x18007b2cd  mov     rbx, [rax+48h]
0x18007b2d1  call    ?GetDataStore@SdoMachine@@IEAA?AW4_IASDATASTORE@@XZ; SdoMachine::GetDataStore(void)
0x18007b2d6  mov     edx, eax
0x18007b2d8  lea     r9, [rsp+860h+var_830]
0x18007b2dd  mov     rax, rbx
0x18007b2e0  mov     r8, r14
0x18007b2e3  mov     rcx, rdi
0x18007b2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2eb  mov     ebx, eax
0x18007b2ed  test    eax, eax
0x18007b2ef  js      short loc_18007B31F
0x18007b2f1  mov     rcx, [rsp+860h+var_830]
0x18007b2f6  lea     r8, [rsi+18h]
0x18007b2fa  lea     rdx, IID_ISdo
0x18007b301  mov     rax, [rcx]
0x18007b304  mov     rax, [rax]
0x18007b307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b30c  mov     ebx, eax
0x18007b30e  test    eax, eax
0x18007b310  js      short loc_18007B31F
0x18007b312  cmp     qword ptr [rsi+18h], 0
0x18007b317  mov     eax, 80004005h
0x18007b31c  cmovz   ebx, eax
0x18007b31f  mov     rcx, [rsp+860h+var_830]
0x18007b324  test    rcx, rcx
0x18007b327  jz      short loc_18007B342
0x18007b329  mov     rax, [rcx]
0x18007b32c  mov     rax, [rax+10h]
0x18007b330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b335  test    eax, eax
0x18007b337  jnz     short loc_18007B342
0x18007b339  mov     [rsp+860h+var_830], 0
0x18007b342  test    r14, r14
0x18007b345  jz      short loc_18007B350
0x18007b347  mov     rcx, r14; bstrString
0x18007b34a  call    cs:__imp_SysFreeString
0x18007b350  test    ebx, ebx
0x18007b352  jns     loc_18007B3DC
0x18007b358  cmp     qword ptr cs:xmmword_1800C9F60+8, 0
0x18007b360  jz      short loc_18007B39C
0x18007b362  lea     rdx, aSdomachineAtta_0; "SdoMachine::Attach failed UpdateRemoteA"...
0x18007b369  xor     eax, eax
0x18007b36b  mov     r8d, ebx
0x18007b36e  mov     word ptr [rsp+860h+var_820], ax
0x18007b373  lea     rcx, [rsp+860h+var_820]
0x18007b378  call    FormatRRASErrorString
0x18007b37d  mov     rdx, qword ptr cs:xmmword_1800C9F60+8
0x18007b384  lea     r8, [rsp+860h+var_820]
0x18007b389  mov     rcx, cs:gSdoWrapperEtwContext
0x18007b390  mov     rax, cs:gSdoWrapperTemplateFunc
0x18007b397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b39c  mov     rcx, [rsi+18h]
0x18007b3a0  test    rcx, rcx
0x18007b3a3  jz      short loc_18007B3BD
0x18007b3a5  mov     rax, [rcx]
0x18007b3a8  mov     rax, [rax+10h]
0x18007b3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3b1  test    eax, eax
0x18007b3b3  jnz     short loc_18007B3BD
0x18007b3b5  mov     qword ptr [rsi+18h], 0
0x18007b3bd  mov     rcx, [rsi]
0x18007b3c0  test    rcx, rcx
0x18007b3c3  jz      short loc_18007B3DC
0x18007b3c5  mov     rax, [rcx]
0x18007b3c8  mov     rax, [rax+10h]
0x18007b3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3d1  test    eax, eax
0x18007b3d3  jnz     short loc_18007B3DC
0x18007b3d5  mov     qword ptr [rsi], 0
0x18007b3dc  mov     eax, ebx
0x18007b3de  mov     rcx, [rbp+760h+var_20]
0x18007b3e5  xor     rcx, rsp; StackCookie
0x18007b3e8  call    __security_check_cookie
0x18007b3ed  lea     r11, [rsp+860h+var_10]
0x18007b3f5  mov     rbx, [r11+30h]
0x18007b3f9  mov     rsi, [r11+38h]
0x18007b3fd  mov     rsp, r11
0x18007b400  pop     r14
0x18007b402  pop     rdi
0x18007b403  pop     rbp
0x18007b404  retn
```
