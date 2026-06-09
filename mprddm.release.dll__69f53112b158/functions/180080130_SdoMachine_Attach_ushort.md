# SdoMachine::Attach(ushort *)

- ea: `0x180080130`
- end: `0x180080352`
- name: `?Attach@SdoMachine@@QEAAJPEAG@Z`
- size: `546`
- prototype: `__int64 __fastcall(SdoMachine *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f904`

## callees

- `0x1800755b8`
- `0x180080130`
- `0x180080358`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180080203`
- `OLEAUT32!__imp_SysAllocString` at `0x180080203`
- `OLEAUT32!__imp_SysFreeString` at `0x18008029f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008029f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080195`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080195`

## string_xrefs

- `0x1800801b7`: `CoCreateInstance SdoMachine failed %x\n`
- `0x1800802bb`: `SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n`
- `0x1800801f7`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall SdoMachine::Attach(LPVOID *this, unsigned __int16 *a2)
{
  HRESULT Instance; // eax
  int v5; // ebx
  __int64 v6; // r8
  const wchar_t *v7; // rdx
  int v8; // eax
  OLECHAR *v9; // r14
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, _QWORD, OLECHAR *, __int64 *); // rbx
  enum _IASDATASTORE DataStore; // eax
  LPVOID v13; // rcx
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  Instance = CoCreateInstance(&CLSID_SdoMachine, 0, 1u, &IID_ISdoMachine, this);
  v5 = Instance;
  if ( Instance < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800D0F60 + 1) )
      goto LABEL_22;
    v6 = (unsigned int)Instance;
    v7 = L"CoCreateInstance SdoMachine failed %x\n";
    goto LABEL_21;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)*this + 56LL))(*this, a2);
  v5 = v8;
  if ( v8 < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800D0F60 + 1) )
      goto LABEL_22;
    v6 = (unsigned int)v8;
    v7 = L"SdoMachine::Attach failed %x\n";
    goto LABEL_21;
  }
  v15 = 0;
  v9 = SysAllocString(L"RemoteAccess");
  if ( v9 )
  {
    v10 = *this;
    v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, OLECHAR *, __int64 *))(*(_QWORD *)*this + 72LL);
    DataStore = SdoMachine::GetDataStore((SdoMachine *)this);
    v5 = v11(v10, (unsigned int)DataStore, v9, &v15);
    if ( v5 >= 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v15)(v15, &IID_ISdo, (char *)this + 24);
      if ( v5 >= 0 && !this[3] )
        v5 = -2147467259;
    }
  }
  else
  {
    v5 = -2147024882;
  }
  if ( v15 && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15) )
    v15 = 0;
  if ( v9 )
    SysFreeString(v9);
  if ( v5 < 0 )
  {
    if ( !*((_QWORD *)&xmmword_1800D0F60 + 1) )
      goto LABEL_22;
    v6 = (unsigned int)v5;
    v7 = L"SdoMachine::Attach failed UpdateRemoteAccessServiceSdo failed no service sdo %x\n";
LABEL_21:
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, v7, v6);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      *((_QWORD *)&xmmword_1800D0F60 + 1),
      &v16);
LABEL_22:
    v13 = this[3];
    if ( v13 && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13) )
      this[3] = 0;
    if ( *this && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)*this + 16LL))(*this) )
      *this = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180080130  mov     [rsp-8+arg_10], rbx
0x180080135  push    rbp
0x180080136  push    rsi
0x180080137  push    rdi
0x180080138  push    r14
0x18008013a  push    r15
0x18008013c  lea     rbp, [rsp-750h]
0x180080144  sub     rsp, 850h
0x18008014b  mov     rax, cs:__security_cookie
0x180080152  xor     rax, rsp
0x180080155  mov     [rbp+770h+var_30], rax
0x18008015c  mov     rdi, rdx
0x18008015f  mov     rsi, rcx
0x180080162  xor     r15d, r15d
0x180080165  lea     rcx, [rsp+870h+var_82C]; void *
0x18008016a  xor     edx, edx; Val
0x18008016c  mov     [rsp+870h+var_830], r15d
0x180080171  mov     r8d, 7FCh; Size
0x180080177  call    memset_0
0x18008017c  lea     r9, IID_ISdoMachine; riid
0x180080183  mov     [rsp+870h+ppv], rsi; ppv
0x180080188  xor     edx, edx; pUnkOuter
0x18008018a  lea     r8d, [r15+1]; dwClsContext
0x18008018e  lea     rcx, CLSID_SdoMachine; rclsid
0x180080195  call    cs:__imp_CoCreateInstance
0x18008019c  nop     dword ptr [rax+rax+00h]
0x1800801a1  mov     ebx, eax
0x1800801a3  test    eax, eax
0x1800801a5  jns     short loc_1800801C3
0x1800801a7  cmp     qword ptr cs:xmmword_1800D0F60+8, r15
0x1800801ae  jz      loc_1800802F1
0x1800801b4  mov     r8d, eax
0x1800801b7  lea     rdx, aCocreateinstan; "CoCreateInstance SdoMachine failed %x\n"
0x1800801be  jmp     loc_1800802C2
0x1800801c3  mov     rcx, [rsi]
0x1800801c6  mov     rdx, rdi
0x1800801c9  mov     rax, [rcx]
0x1800801cc  mov     rax, [rax+38h]
0x1800801d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801d5  mov     ebx, eax
0x1800801d7  test    eax, eax
0x1800801d9  jns     short loc_1800801F7
0x1800801db  cmp     qword ptr cs:xmmword_1800D0F60+8, r15
0x1800801e2  jz      loc_1800802F1
0x1800801e8  mov     r8d, eax
0x1800801eb  lea     rdx, aSdomachineAtta; "SdoMachine::Attach failed %x\n"
0x1800801f2  jmp     loc_1800802C2
0x1800801f7  lea     rcx, aRemoteaccess_0; "RemoteAccess"
0x1800801fe  mov     [rsp+870h+var_840], r15
0x180080203  call    cs:__imp_SysAllocString
0x18008020a  nop     dword ptr [rax+rax+00h]
0x18008020f  mov     r14, rax
0x180080212  test    rax, rax
0x180080215  jnz     short loc_18008021E
0x180080217  mov     ebx, 8007000Eh
0x18008021c  jmp     short loc_180080278
0x18008021e  mov     rdi, [rsi]
0x180080221  mov     rcx, rsi; this
0x180080224  mov     rax, [rdi]
0x180080227  mov     rbx, [rax+48h]
0x18008022b  call    ?GetDataStore@SdoMachine@@IEAA?AW4_IASDATASTORE@@XZ; SdoMachine::GetDataStore(void)
0x180080230  mov     edx, eax
0x180080232  lea     r9, [rsp+870h+var_840]
0x180080237  mov     rax, rbx
0x18008023a  mov     r8, r14
0x18008023d  mov     rcx, rdi
0x180080240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080245  mov     ebx, eax
0x180080247  test    eax, eax
0x180080249  js      short loc_180080278
0x18008024b  mov     rcx, [rsp+870h+var_840]
0x180080250  lea     r8, [rsi+18h]
0x180080254  lea     rdx, IID_ISdo
0x18008025b  mov     rax, [rcx]
0x18008025e  mov     rax, [rax]
0x180080261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080266  mov     ebx, eax
0x180080268  test    eax, eax
0x18008026a  js      short loc_180080278
0x18008026c  cmp     [rsi+18h], r15
0x180080270  mov     eax, 80004005h
0x180080275  cmovz   ebx, eax
0x180080278  mov     rcx, [rsp+870h+var_840]
0x18008027d  test    rcx, rcx
0x180080280  jz      short loc_180080297
0x180080282  mov     rax, [rcx]
0x180080285  mov     rax, [rax+10h]
0x180080289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008028e  test    eax, eax
0x180080290  jnz     short loc_180080297
0x180080292  mov     [rsp+870h+var_840], r15
0x180080297  test    r14, r14
0x18008029a  jz      short loc_1800802AB
0x18008029c  mov     rcx, r14; bstrString
0x18008029f  call    cs:__imp_SysFreeString
0x1800802a6  nop     dword ptr [rax+rax+00h]
0x1800802ab  test    ebx, ebx
0x1800802ad  jns     short loc_180080329
0x1800802af  cmp     qword ptr cs:xmmword_1800D0F60+8, r15
0x1800802b6  jz      short loc_1800802F1
0x1800802b8  mov     r8d, ebx
0x1800802bb  lea     rdx, aSdomachineAtta_0; "SdoMachine::Attach failed UpdateRemoteA"...
0x1800802c2  lea     rcx, [rsp+870h+var_830]
0x1800802c7  mov     word ptr [rsp+870h+var_830], r15w
0x1800802cd  call    FormatRRASErrorString
0x1800802d2  mov     rdx, qword ptr cs:xmmword_1800D0F60+8
0x1800802d9  lea     r8, [rsp+870h+var_830]
0x1800802de  mov     rcx, cs:gSdoWrapperEtwContext
0x1800802e5  mov     rax, cs:gSdoWrapperTemplateFunc
0x1800802ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802f1  mov     rcx, [rsi+18h]
0x1800802f5  test    rcx, rcx
0x1800802f8  jz      short loc_18008030E
0x1800802fa  mov     rax, [rcx]
0x1800802fd  mov     rax, [rax+10h]
0x180080301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080306  test    eax, eax
0x180080308  jnz     short loc_18008030E
0x18008030a  mov     [rsi+18h], r15
0x18008030e  mov     rcx, [rsi]
0x180080311  test    rcx, rcx
0x180080314  jz      short loc_180080329
0x180080316  mov     rax, [rcx]
0x180080319  mov     rax, [rax+10h]
0x18008031d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080322  test    eax, eax
0x180080324  jnz     short loc_180080329
0x180080326  mov     [rsi], r15
0x180080329  mov     eax, ebx
0x18008032b  mov     rcx, [rbp+770h+var_30]
0x180080332  xor     rcx, rsp; StackCookie
0x180080335  call    __security_check_cookie
0x18008033a  mov     rbx, [rsp+870h+arg_10]
0x180080342  add     rsp, 850h
0x180080349  pop     r15
0x18008034b  pop     r14
0x18008034d  pop     rdi
0x18008034e  pop     rsi
0x18008034f  pop     rbp
0x180080350  retn
```
