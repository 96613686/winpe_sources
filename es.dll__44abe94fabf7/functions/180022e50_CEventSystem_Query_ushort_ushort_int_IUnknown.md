# CEventSystem::Query(ushort *,ushort *,int *,IUnknown * *)

- ea: `0x180022e50`
- end: `0x180023199`
- name: `?Query@CEventSystem@@UEAAJPEAG0PEAHPEAPEAUIUnknown@@@Z`
- size: `841`
- prototype: `int(CEventSystem *__hidden this, unsigned __int16 *, unsigned __int16 *, int *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180005cf0`
- `0x18001f46c`
- `0x180022e50`
- `0x1800231a0`
- `0x1800304a0`
- `0x18003ecb0`
- `0x1800434de`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180022fed`
- `msvcrt!_itow_s` at `0x180022fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230de`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022f0c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022f0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022f4f`

## string_xrefs

- `0x180023061`: `com\complus\src\events\tier1\enum.cpp`

## pseudocode

```c
__int64 __fastcall CEventSystem::Query(
        CEventSystem *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int *a4,
        struct IUnknown **a5)
{
  int v9; // ebx
  char v10; // si
  __int64 result; // rax
  int v12; // r14d
  LPVOID v13; // rax
  struct IEventSystemTier2 *v14; // rbx
  int v15; // [rsp+28h] [rbp-A0h]
  unsigned __int8 v17; // [rsp+54h] [rbp-74h]
  WINBOOL IsMember; // [rsp+58h] [rbp-70h] BYREF
  int v19; // [rsp+5Ch] [rbp-6Ch] BYREF
  struct IEventSystemTier2 *v20; // [rsp+60h] [rbp-68h]
  CEventSystem *v21; // [rsp+68h] [rbp-60h]
  wchar_t Buffer[12]; // [rsp+70h] [rbp-58h] BYREF

  v21 = this;
  v9 = 0;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a3 || !a2 || !*a3 )
    return 2147942487LL;
  if ( !wcscmp_0(a2, L"EventSystem.EventSubscriptionCollection") )
  {
    v9 = 1;
LABEL_8:
    v10 = v9;
    goto LABEL_9;
  }
  if ( !wcscmp_0(a2, L"EventSystem.EventClass") )
    goto LABEL_8;
  if ( !wcscmp_0(a2, L"EventSystem.EventSubscription") )
  {
    v10 = 0;
    v9 = 1;
  }
  else
  {
    if ( wcscmp_0(a2, L"EventSystem.EventClassCollection") )
    {
      if ( !wcscmp_0(a2, L"EventSystem.EventPublisher") || !wcscmp_0(a2, L"EventSystem.EventPublisherCollection") )
        return 2147942659LL;
      else
        return 2147942487LL;
    }
    v10 = 1;
    v9 = 0;
  }
LABEL_9:
  v20 = 0;
  IsMember = 0;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    LODWORD(result) = 0;
  }
  else
  {
    LODWORD(result) = GetLastError();
    if ( (int)result > 0 )
      LODWORD(result) = (unsigned __int16)result | 0x80070000;
  }
  if ( (int)result < 0 )
    return (unsigned int)result;
  v17 = IsMember != 0;
  v20 = (struct IEventSystemTier2 *)*((_QWORD *)this + 3);
  v12 = -2147024882;
  v19 = -2147024882;
  v13 = CoTaskMemAlloc(0xA0u);
  if ( v13 )
  {
    LOBYTE(v15) = 0;
    v14 = (struct IEventSystemTier2 *)EventObjectCollection::EventObjectCollection(
                                        (__int64)v13,
                                        v9,
                                        a3,
                                        (__int64)a4,
                                        v20,
                                        v15,
                                        v17,
                                        0,
                                        0,
                                        &v19);
    v12 = v19;
  }
  else
  {
    v14 = 0;
  }
  v20 = v14;
  if ( !v14 )
    InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x27Fu, 0xC0001204, 0x10u);
  if ( v12 < 0 )
  {
    if ( v14 )
      EventObjectCollection::`scalar deleting destructor'(v14);
    v14 = 0;
    v20 = 0;
  }
  else
  {
    (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v14 + 8LL))(v14);
  }
  if ( v12 >= 0 )
  {
    if ( v10 )
    {
      *a5 = (struct IUnknown *)v14;
      return 0;
    }
    else
    {
      *a5 = EventObjectCollection::firstItem(v14);
      (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v14 + 16LL))(v14);
      return *a5 == 0;
    }
  }
  else
  {
    _itow_s(*a4, Buffer, 0xCu, 10);
    CEventSystem::SetQueryErrorInfo(v21, 0xC000120C, 4u, a2, a3, Buffer, &a3[*a4]);
    return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x180022e50  push    rbx
0x180022e52  push    rsi
0x180022e53  push    rdi
0x180022e54  push    r12
0x180022e56  push    r13
0x180022e58  push    r14
0x180022e5a  push    r15
0x180022e5c  sub     rsp, 90h
0x180022e63  mov     rax, cs:__security_cookie
0x180022e6a  xor     rax, rsp
0x180022e6d  mov     [rsp+0C8h+var_40], rax
0x180022e75  mov     r13, r9
0x180022e78  mov     r12, r8
0x180022e7b  mov     rdi, rdx
0x180022e7e  mov     r14, rcx
0x180022e81  mov     [rsp+0C8h+var_60], rcx
0x180022e86  mov     r15, [rsp+0C8h+arg_20]
0x180022e8e  xor     ebx, ebx
0x180022e90  test    r15, r15
0x180022e93  jz      loc_180023192
0x180022e99  mov     [r15], rbx
0x180022e9c  test    r9, r9
0x180022e9f  jz      loc_180023192
0x180022ea5  mov     [r9], ebx
0x180022ea8  test    r8, r8
0x180022eab  jz      loc_18002318B
0x180022eb1  test    rdx, rdx
0x180022eb4  jz      loc_18002318B
0x180022eba  cmp     [r8], bx
0x180022ebe  jz      loc_18002318B
0x180022ec4  mov     [rsp+0C8h+var_78], ebx
0x180022ec8  lea     rdx, aEventsystemEve_1; "EventSystem.EventSubscriptionCollection"
0x180022ecf  mov     rcx, rdi; String1
0x180022ed2  call    wcscmp_0
0x180022ed7  test    eax, eax
0x180022ed9  jnz     loc_180023072
0x180022edf  lea     ebx, [rax+1]
0x180022ee2  mov     sil, bl
0x180022ee5  mov     [rsp+0C8h+var_68], 0
0x180022eee  mov     [rsp+0C8h+IsMember], 0
0x180022ef6  mov     [rsp+0C8h+IsMember], 0
0x180022efe  lea     r8, [rsp+0C8h+IsMember]; IsMember
0x180022f03  mov     rdx, cs:SidToCheck; SidToCheck
0x180022f0a  xor     ecx, ecx; TokenHandle
0x180022f0c  call    cs:__imp_CheckTokenMembership
0x180022f12  test    eax, eax
0x180022f14  jz      loc_1800230DE
0x180022f1a  xor     eax, eax
0x180022f1c  mov     [rsp+0C8h+var_78], eax
0x180022f20  mov     eax, [rsp+0C8h+var_78]
0x180022f24  test    eax, eax
0x180022f26  js      loc_1800230F9
0x180022f2c  cmp     [rsp+0C8h+IsMember], 0
0x180022f31  setnz   [rsp+0C8h+var_74]
0x180022f36  mov     rax, [r14+18h]
0x180022f3a  mov     [rsp+0C8h+var_68], rax
0x180022f3f  mov     r14d, 8007000Eh
0x180022f45  mov     [rsp+0C8h+var_6C], r14d
0x180022f4a  mov     ecx, 0A0h; cb
0x180022f4f  call    cs:__imp_CoTaskMemAlloc
0x180022f55  test    rax, rax
0x180022f58  jz      loc_180023049
0x180022f5e  lea     rcx, [rsp+0C8h+var_6C]
0x180022f63  mov     [rsp+0C8h+var_80], rcx
0x180022f68  mov     [rsp+0C8h+var_88], 0
0x180022f70  mov     [rsp+0C8h+var_90], 0
0x180022f78  mov     cl, [rsp+0C8h+var_74]
0x180022f7c  mov     byte ptr [rsp+0C8h+var_98], cl
0x180022f80  mov     byte ptr [rsp+0C8h+var_A0], 0
0x180022f85  mov     rcx, [rsp+0C8h+var_68]
0x180022f8a  mov     [rsp+0C8h+var_A8], rcx
0x180022f8f  mov     r9, r13
0x180022f92  mov     r8, r12
0x180022f95  mov     edx, ebx
0x180022f97  mov     rcx, rax
0x180022f9a  call    ??0EventObjectCollection@@AEAA@W4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@PEBGPEAHPEAUIEventSystemTier2@@_N4HHAEAJ@Z; EventObjectCollection::EventObjectCollection(__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *,int *,IEventSystemTier2 *,bool,bool,int,int,long &)
0x180022f9f  mov     rbx, rax
0x180022fa2  mov     r14d, [rsp+0C8h+var_6C]
0x180022fa7  mov     [rsp+0C8h+var_68], rbx
0x180022fac  test    rbx, rbx
0x180022faf  jz      loc_180023050
0x180022fb5  test    r14d, r14d
0x180022fb8  js      loc_1800230FF
0x180022fbe  mov     rax, [rbx]
0x180022fc1  mov     rcx, rbx
0x180022fc4  mov     rax, [rax+8]
0x180022fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fcd  mov     [rsp+0C8h+var_78], r14d
0x180022fd2  mov     eax, [rsp+0C8h+var_78]
0x180022fd6  test    eax, eax
0x180022fd8  jns     short loc_180023030
0x180022fda  mov     r9d, 0Ah; Radix
0x180022fe0  lea     r8d, [r9+2]; BufferCount
0x180022fe4  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x180022fe9  mov     ecx, [r13+0]; Value
0x180022fed  call    cs:__imp__itow_s
0x180022ff3  movsxd  rax, dword ptr [r13+0]
0x180022ff7  lea     rdx, [r12+rax*2]
0x180022ffb  mov     [rsp+0C8h+var_98], rdx
0x180023000  lea     rax, [rsp+0C8h+Buffer]
0x180023005  mov     [rsp+0C8h+var_A0], rax
0x18002300a  mov     [rsp+0C8h+var_A8], r12
0x18002300f  mov     r9, rdi
0x180023012  mov     edx, 0C000120Ch; unsigned int
0x180023017  mov     r8d, 4; unsigned int
0x18002301d  mov     rcx, [rsp+0C8h+var_60]; this
0x180023022  call    ?SetQueryErrorInfo@CEventSystem@@AEAAXKKZZ; CEventSystem::SetQueryErrorInfo(ulong,ulong,...)
0x180023027  mov     eax, [rsp+0C8h+var_78]
0x18002302b  jmp     loc_180023168
0x180023030  test    sil, sil
0x180023033  jz      loc_180023118
0x180023039  mov     [r15], rbx
0x18002303c  mov     [rsp+0C8h+var_78], 0
0x180023044  jmp     loc_180023164
0x180023049  xor     ebx, ebx
0x18002304b  jmp     loc_180022FA7
0x180023050  mov     edx, 27Fh; unsigned int
0x180023055  mov     r9d, 10h; unsigned __int16
0x18002305b  mov     r8d, 0C0001204h; unsigned int
0x180023061  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x180023068  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18002306d  jmp     loc_180022FB5
0x180023072  lea     rdx, aEventsystemEve_2; "EventSystem.EventClass"
0x180023079  mov     rcx, rdi; String1
0x18002307c  call    wcscmp_0
0x180023081  test    eax, eax
0x180023083  jz      loc_180022EE2
0x180023089  lea     rdx, aEventsystemEve_5; "EventSystem.EventSubscription"
0x180023090  mov     rcx, rdi; String1
0x180023093  call    wcscmp_0
0x180023098  test    eax, eax
0x18002309a  jz      short loc_1800230D1
0x18002309c  lea     rdx, aEventsystemEve_3; "EventSystem.EventClassCollection"
0x1800230a3  mov     rcx, rdi; String1
0x1800230a6  call    wcscmp_0
0x1800230ab  test    eax, eax
0x1800230ad  jnz     short loc_1800230B9
0x1800230af  lea     esi, [rax+1]
0x1800230b2  xor     ebx, ebx
0x1800230b4  jmp     loc_180022EE5
0x1800230b9  lea     rdx, aEventsystemEve_0; "EventSystem.EventPublisher"
0x1800230c0  mov     rcx, rdi; String1
0x1800230c3  call    wcscmp_0
0x1800230c8  test    eax, eax
0x1800230ca  jnz     short loc_180023143
0x1800230cc  jmp     loc_18002315D
0x1800230d1  mov     sil, bl
0x1800230d4  mov     ebx, 1
0x1800230d9  jmp     loc_180022EE5
0x1800230de  call    cs:__imp_GetLastError
0x1800230e4  test    eax, eax
0x1800230e6  jle     loc_180022F1C
0x1800230ec  movzx   eax, ax
0x1800230ef  or      eax, 80070000h
0x1800230f4  jmp     loc_180022F1C
0x1800230f9  mov     eax, [rsp+0C8h+var_78]
0x1800230fd  jmp     short loc_180023168
0x1800230ff  test    rbx, rbx
0x180023102  jz      short loc_18002310C
0x180023104  mov     rcx, rbx; this
0x180023107  call    ??_GEventObjectCollection@@AEAAPEAXI@Z; EventObjectCollection::`scalar deleting destructor'(uint)
0x18002310c  xor     ebx, ebx
0x18002310e  mov     [rsp+0C8h+var_68], rbx
0x180023113  jmp     loc_180022FCD
0x180023118  mov     rcx, rbx; this
0x18002311b  call    ?firstItem@EventObjectCollection@@QEAAPEAUIUnknown@@XZ; EventObjectCollection::firstItem(void)
0x180023120  mov     [r15], rax
0x180023123  mov     rax, [rbx]
0x180023126  mov     rcx, rbx
0x180023129  mov     rax, [rax+10h]
0x18002312d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023132  xor     eax, eax
0x180023134  cmp     [r15], rax
0x180023137  setz    al
0x18002313a  mov     [rsp+0C8h+var_78], eax
0x18002313e  jmp     loc_180023044
0x180023143  lea     rdx, aEventsystemEve_4; "EventSystem.EventPublisherCollection"
0x18002314a  mov     rcx, rdi; String1
0x18002314d  call    wcscmp_0
0x180023152  test    eax, eax
0x180023154  jz      short loc_18002315D
0x180023156  mov     eax, 80070057h
0x18002315b  jmp     short loc_180023168
0x18002315d  mov     eax, 80070103h
0x180023162  jmp     short loc_180023168
0x180023164  mov     eax, [rsp+0C8h+var_78]
0x180023168  mov     rcx, [rsp+0C8h+var_40]
0x180023170  xor     rcx, rsp; StackCookie
0x180023173  call    __security_check_cookie
0x180023178  add     rsp, 90h
0x18002317f  pop     r15
0x180023181  pop     r14
0x180023183  pop     r13
0x180023185  pop     r12
0x180023187  pop     rdi
0x180023188  pop     rsi
0x180023189  pop     rbx
0x18002318a  retn
0x18002318b  mov     eax, 80070057h
0x180023190  jmp     short loc_180023168
0x180023192  mov     eax, 80004003h
0x180023197  jmp     short loc_180023168
0x180044dfe  push    rbp
0x180044e00  sub     rsp, 50h
0x180044e04  mov     rbp, rdx
0x180044e07  lea     rdx, [rbp+50h]; int *
0x180044e0b  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180044e10  nop
0x180044e11  add     rsp, 50h
0x180044e15  pop     rbp
0x180044e16  retn
```
