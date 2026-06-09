# CTempGlassTerminal::CTempGlassTerminal(__CreateSessionParm *,long *)

- ea: `0x18002e4c0`
- end: `0x18002e654`
- name: `??0CTempGlassTerminal@@QEAA@PEAU__CreateSessionParm@@PEAJ@Z`
- size: `404`
- prototype: `CTempGlassTerminal *__fastcall(CTempGlassTerminal *__hidden this, struct __CreateSessionParm *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002e3e8`

## callees

- `0x1800077a0`
- `0x180016740`
- `0x1800212cc`
- `0x1800248ac`
- `0x18002c57c`
- `0x18002e4c0`
- `0x180031650`
- `0x1800488e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e591`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5ae`

## string_xrefs

- `0x18002e5d0`: `CreateEvent failed: 0x%x in %s`
- `0x18002e552`: `CTempGlassTerminal::CTempGlassTerminal`
- `0x18002e57a`: `CopyTSRpcStringToString failed: 0x%x in %s`
- `0x18002e607`: `TempGlass`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CTempGlassTerminal *__fastcall CTempGlassTerminal::CTempGlassTerminal(
        CTempGlassTerminal *this,
        struct __CreateSessionParm *a2,
        int *a3)
{
  int v6; // eax
  signed int v7; // ebx
  const char *v8; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const char *v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v15 = (const char *)this;
  CTSPrivateObject<ITempGlassTerminal>::CTSPrivateObject<ITempGlassTerminal>();
  *((_QWORD *)this + 199) = this;
  *(_QWORD *)this = &CTempGlassTerminal::`vftable';
  *((_DWORD *)this + 400) = 0;
  *((_DWORD *)this + 401) = -1;
  *((_DWORD *)this + 426) = 0;
  *((_QWORD *)this + 214) = 0;
  *((_QWORD *)this + 215) = 0;
  *((_QWORD *)this + 216) = 0;
  v6 = CResource::Initialize((CTempGlassTerminal *)((char *)this + 1608));
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "Lock.Initialize failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v8, (unsigned int)v6, "CTempGlassTerminal::CTempGlassTerminal");
    goto LABEL_15;
  }
  v6 = CUtils::CopyTSRpcStringToString((struct __CreateSessionParm *)((char *)a2 + 8), (unsigned __int16 **)this + 215);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "CopyTSRpcStringToString failed: 0x%x in %s";
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  SmartHANDLE::operator=((char *)this + 1728, EventW);
  if ( *((_QWORD *)this + 216) )
    goto LABEL_12;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_12:
    *((_DWORD *)this + 400) = 1;
    if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
    {
      v15 = "TempGlass";
      v16 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1800CB30B,
        v12,
        v13,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", (unsigned int)v7, "CTempGlassTerminal::CTempGlassTerminal");
  }
LABEL_15:
  *a3 = v7;
  return this;
}

```

## disassembly

```asm
0x18002e4c0  mov     [rsp+arg_8], rbx
0x18002e4c5  mov     [rsp+arg_0], rcx
0x18002e4ca  push    rbp
0x18002e4cb  push    rsi
0x18002e4cc  push    rdi
0x18002e4cd  push    r14
0x18002e4cf  push    r15
0x18002e4d1  sub     rsp, 30h
0x18002e4d5  mov     r15, r8
0x18002e4d8  mov     rbp, rdx
0x18002e4db  mov     rdi, rcx
0x18002e4de  call    ??0?$CTSPrivateObject@VITempGlassTerminal@@@@QEAA@PEBD@Z; CTSPrivateObject<ITempGlassTerminal>::CTSPrivateObject<ITempGlassTerminal>(char const *)
0x18002e4e3  mov     [rdi+638h], rdi
0x18002e4ea  lea     rax, ??_7CTempGlassTerminal@@6B@; const CTempGlassTerminal::`vftable'
0x18002e4f1  mov     [rdi], rax
0x18002e4f4  mov     dword ptr [rdi+640h], 0
0x18002e4fe  mov     dword ptr [rdi+644h], 0FFFFFFFFh
0x18002e508  lea     rcx, [rdi+648h]; this
0x18002e50f  mov     dword ptr [rcx+60h], 0
0x18002e516  mov     qword ptr [rdi+6B0h], 0
0x18002e521  lea     r14, [rdi+6B8h]
0x18002e528  mov     qword ptr [r14], 0
0x18002e52f  lea     rsi, [rdi+6C0h]
0x18002e536  mov     qword ptr [rsi], 0
0x18002e53d  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002e542  mov     ebx, eax
0x18002e544  test    eax, eax
0x18002e546  jns     short loc_18002E568
0x18002e548  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x18002e54f  mov     r8d, eax
0x18002e552  lea     r9, aCtempglassterm_3; "CTempGlassTerminal::CTempGlassTerminal"
0x18002e559  mov     ecx, 8; int
0x18002e55e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e563  jmp     loc_18002E63C
0x18002e568  lea     rcx, [rbp+8]; struct _TS_RPC_STRING *
0x18002e56c  mov     rdx, r14; unsigned __int16 **
0x18002e56f  call    ?CopyTSRpcStringToString@CUtils@@SAJPEAU_TS_RPC_STRING@@PEAPEAG@Z; CUtils::CopyTSRpcStringToString(_TS_RPC_STRING *,ushort * *)
0x18002e574  mov     ebx, eax
0x18002e576  test    eax, eax
0x18002e578  jns     short loc_18002E583
0x18002e57a  lea     rdx, aCopytsrpcstrin; "CopyTSRpcStringToString failed: 0x%x in"...
0x18002e581  jmp     short loc_18002E54F
0x18002e583  xor     r9d, r9d; lpName
0x18002e586  xor     r8d, r8d; bInitialState
0x18002e589  lea     ebp, [r9+1]
0x18002e58d  mov     edx, ebp; bManualReset
0x18002e58f  xor     ecx, ecx; lpEventAttributes
0x18002e591  call    cs:__imp_CreateEventW
0x18002e598  nop     dword ptr [rax+rax+00h]
0x18002e59d  mov     rdx, rax
0x18002e5a0  mov     rcx, rsi
0x18002e5a3  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18002e5a8  cmp     qword ptr [rsi], 0
0x18002e5ac  jnz     short loc_18002E5DC
0x18002e5ae  call    cs:__imp_GetLastError
0x18002e5b5  nop     dword ptr [rax+rax+00h]
0x18002e5ba  mov     ebx, eax
0x18002e5bc  test    eax, eax
0x18002e5be  jle     short loc_18002E5C9
0x18002e5c0  movzx   ebx, ax
0x18002e5c3  or      ebx, 80070000h
0x18002e5c9  test    ebx, ebx
0x18002e5cb  jns     short loc_18002E5DC
0x18002e5cd  mov     r8d, ebx
0x18002e5d0  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18002e5d7  jmp     loc_18002E552
0x18002e5dc  mov     [rdi+640h], ebp
0x18002e5e2  mov     eax, cs:dword_1800DF020
0x18002e5e8  cmp     eax, 5
0x18002e5eb  jbe     short loc_18002E63C
0x18002e5ed  mov     rdx, 400000000000h
0x18002e5f7  lea     rcx, dword_1800DF020
0x18002e5fe  call    _tlgKeywordOn
0x18002e603  test    al, al
0x18002e605  jz      short loc_18002E63C
0x18002e607  lea     rax, aTempglass; "TempGlass"
0x18002e60e  mov     [rsp+58h+arg_0], rax
0x18002e613  mov     [rsp+58h+arg_10], 2000000h
0x18002e61c  lea     rax, [rsp+58h+arg_0]
0x18002e621  mov     [rsp+58h+var_30], rax
0x18002e626  lea     rax, [rsp+58h+arg_10]
0x18002e62b  mov     [rsp+58h+var_38], rax
0x18002e630  lea     rdx, byte_1800CB30B
0x18002e637  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18002e63c  mov     [r15], ebx
0x18002e63f  mov     rax, rdi
0x18002e642  mov     rbx, [rsp+58h+arg_8]
0x18002e647  add     rsp, 30h
0x18002e64b  pop     r15
0x18002e64d  pop     r14
0x18002e64f  pop     rdi
0x18002e650  pop     rsi
0x18002e651  pop     rbp
0x18002e652  retn
```
