# SdoMachine::Attach(ushort *)

- ea: `0x180034034`
- end: `0x180034261`
- name: `?Attach@SdoMachine@@QEAAJPEAG@Z`
- size: `557`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180032f24`

## callees

- `0x180034034`
- `0x180034268`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034099`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034099`
- `OLEAUT32!__imp_SysAllocString` at `0x18003410b`
- `OLEAUT32!__imp_SysAllocString` at `0x18003410b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800341a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800341a6`

## string_xrefs

- `0x1800340b5`: `CoCreateInstance SdoMachine failed %x\n`
- `0x1800341be`: `SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n`
- `0x1800340fb`: `RemoteAccess`

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
    if ( !*((_QWORD *)&xmmword_180078D60 + 1) )
      goto LABEL_23;
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"CoCreateInstance SdoMachine failed %x\n", (unsigned int)Instance);
    goto LABEL_22;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)*this + 56LL))(*this, a2);
  if ( v5 < 0 )
  {
    if ( !*((_QWORD *)&xmmword_180078D60 + 1) )
      goto LABEL_23;
    v6 = L"SdoMachine::Attach failed %x\n";
LABEL_21:
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, v6, (unsigned int)v5);
LABEL_22:
    ((void (__fastcall *)(__int64, _QWORD, int *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      *((_QWORD *)&xmmword_180078D60 + 1),
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
    if ( !*((_QWORD *)&xmmword_180078D60 + 1) )
      goto LABEL_23;
    v6 = L"SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n";
    goto LABEL_21;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180034034  mov     [rsp-8+arg_10], rbx
0x180034039  mov     [rsp-8+arg_18], rsi
0x18003403e  push    rbp
0x18003403f  push    rdi
0x180034040  push    r14
0x180034042  lea     rbp, [rsp-750h]
0x18003404a  sub     rsp, 850h
0x180034051  mov     rax, cs:__security_cookie
0x180034058  xor     rax, rsp
0x18003405b  mov     [rbp+760h+var_20], rax
0x180034062  mov     rdi, rdx
0x180034065  mov     rsi, rcx
0x180034068  xor     eax, eax
0x18003406a  lea     rcx, [rsp+860h+var_81C]; void *
0x18003406f  xor     edx, edx; Val
0x180034071  mov     [rsp+860h+var_820], eax
0x180034075  mov     r8d, 7FCh; Size
0x18003407b  call    memset_0
0x180034080  xor     edx, edx; pUnkOuter
0x180034082  mov     [rsp+860h+ppv], rsi; ppv
0x180034087  lea     r9, IID_ISdoMachine; riid
0x18003408e  lea     rcx, CLSID_SdoMachine; rclsid
0x180034095  lea     r8d, [rdx+1]; dwClsContext
0x180034099  call    cs:__imp_CoCreateInstance
0x18003409f  mov     ebx, eax
0x1800340a1  test    eax, eax
0x1800340a3  jns     short loc_1800340C9
0x1800340a5  cmp     qword ptr cs:xmmword_180078D60+8, 0
0x1800340ad  jz      loc_1800341F8
0x1800340b3  xor     ecx, ecx
0x1800340b5  lea     rdx, aCocreateinstan_0; "CoCreateInstance SdoMachine failed %x\n"
0x1800340bc  mov     word ptr [rsp+860h+var_820], cx
0x1800340c1  mov     r8d, eax
0x1800340c4  jmp     loc_1800341CF
0x1800340c9  mov     rcx, [rsi]
0x1800340cc  mov     rdx, rdi
0x1800340cf  mov     rax, [rcx]
0x1800340d2  mov     rax, [rax+38h]
0x1800340d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340db  mov     ebx, eax
0x1800340dd  test    eax, eax
0x1800340df  jns     short loc_1800340FB
0x1800340e1  cmp     qword ptr cs:xmmword_180078D60+8, 0
0x1800340e9  jz      loc_1800341F8
0x1800340ef  lea     rdx, aSdomachineAtta; "SdoMachine::Attach failed %x\n"
0x1800340f6  jmp     loc_1800341C5
0x1800340fb  lea     rcx, aRemoteaccess_0; "RemoteAccess"
0x180034102  mov     [rsp+860h+var_830], 0
0x18003410b  call    cs:__imp_SysAllocString
0x180034111  mov     r14, rax
0x180034114  test    rax, rax
0x180034117  jnz     short loc_180034120
0x180034119  mov     ebx, 8007000Eh
0x18003411e  jmp     short loc_18003417B
0x180034120  mov     rdi, [rsi]
0x180034123  mov     rcx, rsi; this
0x180034126  mov     rax, [rdi]
0x180034129  mov     rbx, [rax+48h]
0x18003412d  call    ?GetDataStore@SdoMachine@@IEAA?AW4_IASDATASTORE@@XZ; SdoMachine::GetDataStore(void)
0x180034132  mov     edx, eax
0x180034134  lea     r9, [rsp+860h+var_830]
0x180034139  mov     rax, rbx
0x18003413c  mov     r8, r14
0x18003413f  mov     rcx, rdi
0x180034142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034147  mov     ebx, eax
0x180034149  test    eax, eax
0x18003414b  js      short loc_18003417B
0x18003414d  mov     rcx, [rsp+860h+var_830]
0x180034152  lea     r8, [rsi+18h]
0x180034156  lea     rdx, IID_ISdo
0x18003415d  mov     rax, [rcx]
0x180034160  mov     rax, [rax]
0x180034163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034168  mov     ebx, eax
0x18003416a  test    eax, eax
0x18003416c  js      short loc_18003417B
0x18003416e  cmp     qword ptr [rsi+18h], 0
0x180034173  mov     eax, 80004005h
0x180034178  cmovz   ebx, eax
0x18003417b  mov     rcx, [rsp+860h+var_830]
0x180034180  test    rcx, rcx
0x180034183  jz      short loc_18003419E
0x180034185  mov     rax, [rcx]
0x180034188  mov     rax, [rax+10h]
0x18003418c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034191  test    eax, eax
0x180034193  jnz     short loc_18003419E
0x180034195  mov     [rsp+860h+var_830], 0
0x18003419e  test    r14, r14
0x1800341a1  jz      short loc_1800341AC
0x1800341a3  mov     rcx, r14; bstrString
0x1800341a6  call    cs:__imp_SysFreeString
0x1800341ac  test    ebx, ebx
0x1800341ae  jns     loc_180034238
0x1800341b4  cmp     qword ptr cs:xmmword_180078D60+8, 0
0x1800341bc  jz      short loc_1800341F8
0x1800341be  lea     rdx, aSdomachineAtta_0; "SdoMachine::Attach failed UpdateRemoteA"...
0x1800341c5  xor     eax, eax
0x1800341c7  mov     r8d, ebx
0x1800341ca  mov     word ptr [rsp+860h+var_820], ax
0x1800341cf  lea     rcx, [rsp+860h+var_820]
0x1800341d4  call    FormatRRASErrorString
0x1800341d9  mov     rdx, qword ptr cs:xmmword_180078D60+8
0x1800341e0  lea     r8, [rsp+860h+var_820]
0x1800341e5  mov     rcx, cs:gSdoWrapperEtwContext
0x1800341ec  mov     rax, cs:gSdoWrapperTemplateFunc
0x1800341f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341f8  mov     rcx, [rsi+18h]
0x1800341fc  test    rcx, rcx
0x1800341ff  jz      short loc_180034219
0x180034201  mov     rax, [rcx]
0x180034204  mov     rax, [rax+10h]
0x180034208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003420d  test    eax, eax
0x18003420f  jnz     short loc_180034219
0x180034211  mov     qword ptr [rsi+18h], 0
0x180034219  mov     rcx, [rsi]
0x18003421c  test    rcx, rcx
0x18003421f  jz      short loc_180034238
0x180034221  mov     rax, [rcx]
0x180034224  mov     rax, [rax+10h]
0x180034228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003422d  test    eax, eax
0x18003422f  jnz     short loc_180034238
0x180034231  mov     qword ptr [rsi], 0
0x180034238  mov     eax, ebx
0x18003423a  mov     rcx, [rbp+760h+var_20]
0x180034241  xor     rcx, rsp; StackCookie
0x180034244  call    __security_check_cookie
0x180034249  lea     r11, [rsp+860h+var_10]
0x180034251  mov     rbx, [r11+30h]
0x180034255  mov     rsi, [r11+38h]
0x180034259  mov     rsp, r11
0x18003425c  pop     r14
0x18003425e  pop     rdi
0x18003425f  pop     rbp
0x180034260  retn
```
