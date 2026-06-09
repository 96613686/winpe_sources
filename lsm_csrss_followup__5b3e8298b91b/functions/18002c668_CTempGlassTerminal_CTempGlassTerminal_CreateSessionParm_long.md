# CTempGlassTerminal::CTempGlassTerminal(__CreateSessionParm *,long *)

- ea: `0x18002c668`
- end: `0x18002c7ec`
- name: `??0CTempGlassTerminal@@QEAA@PEAU__CreateSessionParm@@PEAJ@Z`
- size: `388`
- prototype: `CTempGlassTerminal *__fastcall(CTempGlassTerminal *__hidden this, struct __CreateSessionParm *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002c590`

## callees

- `0x1800074c0`
- `0x18001288c`
- `0x18001eecc`
- `0x180022bb8`
- `0x18002a71c`
- `0x18002c668`
- `0x18002f624`
- `0x1800458dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c739`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c750`

## string_xrefs

- `0x18002c76c`: `CreateEvent failed: 0x%x in %s`
- `0x18002c6fa`: `CTempGlassTerminal::CTempGlassTerminal`
- `0x18002c722`: `CopyTSRpcStringToString failed: 0x%x in %s`
- `0x18002c7a0`: `TempGlass`

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
    if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
    {
      v15 = "TempGlass";
      v16 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1800C6183,
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
0x18002c668  mov     [rsp+arg_8], rbx
0x18002c66d  mov     [rsp+arg_0], rcx
0x18002c672  push    rbp
0x18002c673  push    rsi
0x18002c674  push    rdi
0x18002c675  push    r14
0x18002c677  push    r15
0x18002c679  sub     rsp, 30h
0x18002c67d  mov     r15, r8
0x18002c680  mov     rbp, rdx
0x18002c683  mov     rdi, rcx
0x18002c686  call    ??0?$CTSPrivateObject@VITempGlassTerminal@@@@QEAA@PEBD@Z; CTSPrivateObject<ITempGlassTerminal>::CTSPrivateObject<ITempGlassTerminal>(char const *)
0x18002c68b  mov     [rdi+638h], rdi
0x18002c692  lea     rax, ??_7CTempGlassTerminal@@6B@; const CTempGlassTerminal::`vftable'
0x18002c699  mov     [rdi], rax
0x18002c69c  mov     dword ptr [rdi+640h], 0
0x18002c6a6  mov     dword ptr [rdi+644h], 0FFFFFFFFh
0x18002c6b0  lea     rcx, [rdi+648h]; this
0x18002c6b7  mov     dword ptr [rcx+60h], 0
0x18002c6be  mov     qword ptr [rdi+6B0h], 0
0x18002c6c9  lea     r14, [rdi+6B8h]
0x18002c6d0  mov     qword ptr [r14], 0
0x18002c6d7  lea     rsi, [rdi+6C0h]
0x18002c6de  mov     qword ptr [rsi], 0
0x18002c6e5  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002c6ea  mov     ebx, eax
0x18002c6ec  test    eax, eax
0x18002c6ee  jns     short loc_18002C710
0x18002c6f0  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x18002c6f7  mov     r8d, eax
0x18002c6fa  lea     r9, aCtempglassterm_3; "CTempGlassTerminal::CTempGlassTerminal"
0x18002c701  mov     ecx, 8; int
0x18002c706  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c70b  jmp     loc_18002C7D5
0x18002c710  lea     rcx, [rbp+8]; struct _TS_RPC_STRING *
0x18002c714  mov     rdx, r14; unsigned __int16 **
0x18002c717  call    ?CopyTSRpcStringToString@CUtils@@SAJPEAU_TS_RPC_STRING@@PEAPEAG@Z; CUtils::CopyTSRpcStringToString(_TS_RPC_STRING *,ushort * *)
0x18002c71c  mov     ebx, eax
0x18002c71e  test    eax, eax
0x18002c720  jns     short loc_18002C72B
0x18002c722  lea     rdx, aCopytsrpcstrin; "CopyTSRpcStringToString failed: 0x%x in"...
0x18002c729  jmp     short loc_18002C6F7
0x18002c72b  xor     r9d, r9d; lpName
0x18002c72e  xor     r8d, r8d; bInitialState
0x18002c731  lea     ebp, [r9+1]
0x18002c735  mov     edx, ebp; bManualReset
0x18002c737  xor     ecx, ecx; lpEventAttributes
0x18002c739  call    cs:__imp_CreateEventW
0x18002c73f  mov     rdx, rax
0x18002c742  mov     rcx, rsi
0x18002c745  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18002c74a  cmp     qword ptr [rsi], 0
0x18002c74e  jnz     short loc_18002C775
0x18002c750  call    cs:__imp_GetLastError
0x18002c756  mov     ebx, eax
0x18002c758  test    eax, eax
0x18002c75a  jle     short loc_18002C765
0x18002c75c  movzx   ebx, ax
0x18002c75f  or      ebx, 80070000h
0x18002c765  test    ebx, ebx
0x18002c767  jns     short loc_18002C775
0x18002c769  mov     r8d, ebx
0x18002c76c  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18002c773  jmp     short loc_18002C6FA
0x18002c775  mov     [rdi+640h], ebp
0x18002c77b  mov     eax, cs:dword_1800DA020
0x18002c781  cmp     eax, 5
0x18002c784  jbe     short loc_18002C7D5
0x18002c786  mov     rdx, 400000000000h
0x18002c790  lea     rcx, dword_1800DA020
0x18002c797  call    _tlgKeywordOn
0x18002c79c  test    al, al
0x18002c79e  jz      short loc_18002C7D5
0x18002c7a0  lea     rax, aTempglass; "TempGlass"
0x18002c7a7  mov     [rsp+58h+arg_0], rax
0x18002c7ac  mov     [rsp+58h+arg_10], 2000000h
0x18002c7b5  lea     rax, [rsp+58h+arg_0]
0x18002c7ba  mov     [rsp+58h+var_30], rax
0x18002c7bf  lea     rax, [rsp+58h+arg_10]
0x18002c7c4  mov     [rsp+58h+var_38], rax
0x18002c7c9  lea     rdx, byte_1800C6183
0x18002c7d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18002c7d5  mov     [r15], ebx
0x18002c7d8  mov     rax, rdi
0x18002c7db  mov     rbx, [rsp+58h+arg_8]
0x18002c7e0  add     rsp, 30h
0x18002c7e4  pop     r15
0x18002c7e6  pop     r14
0x18002c7e8  pop     rdi
0x18002c7e9  pop     rsi
0x18002c7ea  pop     rbp
0x18002c7eb  retn
```
