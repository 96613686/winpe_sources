# InboundConnection::InitializeAsConfigConnection(int)

- ea: `0x18002a6d0`
- end: `0x18002a80e`
- name: `?InitializeAsConfigConnection@InboundConnection@@UEAAJH@Z`
- size: `318`
- prototype: `__int64 __fastcall(InboundConnection *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000538c`
- `0x18002a6d0`
- `0x18002ab94`
- `0x18002ac24`
- `0x18002ad2c`
- `0x180031154`
- `0x18003286c`
- `0x180032c3c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002a7f3`
- `KERNEL32!LeaveCriticalSection` at `0x18002a7f3`
- `KERNEL32!EnterCriticalSection` at `0x18002a717`
- `KERNEL32!EnterCriticalSection` at `0x18002a717`
- `RASDLG!RasSrvInitializeService` at `0x18002a782`
- `RASDLG!RasSrvInitializeService` at `0x18002a782`

## pseudocode

```c
__int64 __fastcall InboundConnection::InitializeAsConfigConnection(InboundConnection *this, int a2)
{
  _BYTE *v2; // rsi
  __int64 v5; // rcx
  __int64 v6; // rbp
  unsigned int v7; // edx
  const unsigned __int16 *StringPcch; // rax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  int v11; // eax
  PVOID *v12; // rcx
  int v14[10]; // [rsp+20h] [rbp-28h] BYREF

  v2 = (char *)this + 172;
  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 172) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  v6 = (__int64)this + 24;
  if ( this == (InboundConnection *)8 )
    v6 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  v14[0] = 0;
  *((_BYTE *)this + 72) = 1;
  *((_QWORD *)this + 10) = 0;
  StringPcch = SzLoadStringPcch(qword_180044F40, v7, v14);
  InboundConnection::SetName((InboundConnection *)((char *)this - 8), StringPcch);
  InboundConnection::SetDeviceName((InboundConnection *)((char *)this - 8), 0);
  *((_DWORD *)this + 38) = 0;
  v9 = 0;
  *(GUID *)((char *)this + 156) = GUID_InboundConfigConnectionId;
  *v2 = 1;
  if ( a2 )
  {
    v10 = RasSrvInitializeService();
    v11 = HrFromRasError(v10);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids,
            (unsigned int)v11);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
          WPP_SF_d(v12[2], 22, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids, v9);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return v9;
}

```

## disassembly

```asm
0x18002a6d0  mov     [rsp+arg_8], rbx
0x18002a6d5  mov     [rsp+arg_10], rbp
0x18002a6da  push    rsi
0x18002a6db  push    rdi
0x18002a6dc  push    r14
0x18002a6de  sub     rsp, 30h
0x18002a6e2  lea     rsi, [rcx+0ACh]
0x18002a6e9  mov     rdi, rcx
0x18002a6ec  mov     rcx, rsi
0x18002a6ef  mov     r14d, edx
0x18002a6f2  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18002a6f7  test    al, al
0x18002a6f9  jz      short loc_18002A700
0x18002a6fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a700  mov     eax, 8
0x18002a705  lea     rbx, [rdi-8]
0x18002a709  test    rbx, rbx
0x18002a70c  lea     rbp, [rdi+18h]
0x18002a710  cmovz   rbp, rax
0x18002a714  mov     rcx, rbp; lpCriticalSection
0x18002a717  call    cs:__imp_EnterCriticalSection
0x18002a71d  mov     eax, 1
0x18002a722  mov     [rsp+48h+var_28], 0
0x18002a72a  xchg    al, [rdi+48h]
0x18002a72d  mov     qword ptr [rbx+58h], 0
0x18002a735  lea     r8, [rsp+48h+var_28]; int *
0x18002a73a  mov     rcx, cs:qword_180044F40; hModule
0x18002a741  call    ?SzLoadStringPcch@@YAPEBGPEAUHINSTANCE__@@IPEAH@Z; SzLoadStringPcch(HINSTANCE__ *,uint,int *)
0x18002a746  mov     rdx, rax; unsigned __int16 *
0x18002a749  mov     rcx, rbx; this
0x18002a74c  call    ?SetName@InboundConnection@@AEAAXPEBG@Z; InboundConnection::SetName(ushort const *)
0x18002a751  xor     edx, edx; unsigned __int16 *
0x18002a753  mov     rcx, rbx; this
0x18002a756  call    ?SetDeviceName@InboundConnection@@AEAAXPEBG@Z; InboundConnection::SetDeviceName(ushort const *)
0x18002a75b  mov     dword ptr [rdi+98h], 0
0x18002a765  xor     ebx, ebx
0x18002a767  mov     eax, 1
0x18002a76c  movups  xmm0, xmmword ptr cs:?GUID_InboundConfigConnectionId@@3U_GUID@@B.Data1; _GUID const GUID_InboundConfigConnectionId ...
0x18002a773  movdqu  xmmword ptr [rdi+9Ch], xmm0
0x18002a77b  xchg    al, [rsi]
0x18002a77d  test    r14d, r14d
0x18002a780  jz      short loc_18002A7F0
0x18002a782  call    cs:__imp_RasSrvInitializeService
0x18002a788  mov     ecx, eax; unsigned int
0x18002a78a  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002a78f  mov     ebx, eax
0x18002a791  test    eax, eax
0x18002a793  jns     short loc_18002A7F0
0x18002a795  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a79c  lea     rdi, WPP_GLOBAL_Control
0x18002a7a3  cmp     rcx, rdi
0x18002a7a6  jz      short loc_18002A7F0
0x18002a7a8  test    byte ptr [rcx+1Ch], 1
0x18002a7ac  jz      short loc_18002A7CD
0x18002a7ae  mov     rcx, [rcx+10h]
0x18002a7b2  lea     r8, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids
0x18002a7b9  mov     edx, 15h
0x18002a7be  mov     r9d, eax
0x18002a7c1  call    WPP_SF_d
0x18002a7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7cd  cmp     rcx, rdi
0x18002a7d0  jz      short loc_18002A7F0
0x18002a7d2  test    byte ptr [rcx+1Ch], 1
0x18002a7d6  jz      short loc_18002A7F0
0x18002a7d8  mov     rcx, [rcx+10h]
0x18002a7dc  lea     r8, WPP_f5b0e8f8468b399d61f8354bdcc79c55_Traceguids
0x18002a7e3  mov     edx, 16h
0x18002a7e8  mov     r9d, ebx
0x18002a7eb  call    WPP_SF_d
0x18002a7f0  mov     rcx, rbp; lpCriticalSection
0x18002a7f3  call    cs:__imp_LeaveCriticalSection
0x18002a7f9  mov     rbp, [rsp+48h+arg_10]
0x18002a7fe  mov     eax, ebx
0x18002a800  mov     rbx, [rsp+48h+arg_8]
0x18002a805  add     rsp, 30h
0x18002a809  pop     r14
0x18002a80b  pop     rdi
0x18002a80c  pop     rsi
0x18002a80d  retn
```
