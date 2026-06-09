# CConnectivityWatcher::RegisterForConnectivityNotification(int *)

- ea: `0x18001038c`
- end: `0x180010445`
- name: `?RegisterForConnectivityNotification@CConnectivityWatcher@@QEAAJPEAH@Z`
- size: `185`
- prototype: `int __fastcall(CConnectivityWatcher *this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000637c`

## callees

- `0x180006a9c`
- `0x18001026c`
- `0x18001038c`
- `0x180010470`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001040e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001040e`

## string_xrefs

- `0x1800103b1`: `clientcore\ds\security\gina\profile\roaming\network.cpp`

## pseudocode

```c
int __fastcall CConnectivityWatcher::RegisterForConnectivityNotification(CConnectivityWatcher *this, int *a2)
{
  int HaveConnectivity; // eax
  int v5; // edi
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  HaveConnectivity = CConnectivityWatcher::HaveConnectivity(this, a2);
  v5 = HaveConnectivity;
  if ( HaveConnectivity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)(unsigned int)HaveConnectivity,
      v9);
    return v5;
  }
  if ( !*((_DWORD *)this + 14) && !*a2 && !*((_DWORD *)this + 15) )
  {
    v7 = RtlSubscribeWnfStateChangeNotification(
           (char *)this + 72,
           WNF_WCM_INTERFACE_LIST,
           *((unsigned int *)this + 16),
           CConnectivityWatcher::_WnfInterfaceListSubscription);
    if ( v7 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x309,
               v8,
               (const char *)(unsigned int)v7,
               (int)this);
    *((_DWORD *)this + 15) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001038c  mov     [rsp+arg_0], rbx
0x180010391  mov     [rsp+arg_8], rsi
0x180010396  push    rdi
0x180010397  sub     rsp, 40h
0x18001039b  mov     rsi, rdx
0x18001039e  mov     rbx, rcx
0x1800103a1  call    ?HaveConnectivity@CConnectivityWatcher@@QEAAJPEAH@Z; CConnectivityWatcher::HaveConnectivity(int *)
0x1800103a6  mov     edi, eax
0x1800103a8  test    eax, eax
0x1800103aa  jns     short loc_1800103C9
0x1800103ac  mov     rcx, [rsp+48h]; this
0x1800103b1  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x1800103b8  mov     r9d, eax; char *
0x1800103bb  mov     edx, 2FDh; void *
0x1800103c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103c5  mov     eax, edi
0x1800103c7  jmp     short loc_180010435
0x1800103c9  cmp     dword ptr [rbx+38h], 0
0x1800103cd  jnz     short loc_180010433
0x1800103cf  cmp     dword ptr [rsi], 0
0x1800103d2  jnz     short loc_180010433
0x1800103d4  cmp     dword ptr [rbx+3Ch], 0
0x1800103d8  jnz     short loc_180010433
0x1800103da  mov     r8d, [rbx+40h]
0x1800103de  lea     rcx, [rbx+48h]
0x1800103e2  mov     rdx, cs:WNF_WCM_INTERFACE_LIST
0x1800103e9  lea     r9, ?_WnfInterfaceListSubscription@CConnectivityWatcher@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CConnectivityWatcher::_WnfInterfaceListSubscription(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800103f0  mov     [rsp+48h+var_10], 0
0x1800103f8  mov     [rsp+48h+var_18], 0
0x180010400  mov     [rsp+48h+var_20], 0
0x180010409  mov     qword ptr [rsp+48h+var_28], rbx; int
0x18001040e  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010414  test    eax, eax
0x180010416  jns     short loc_18001042C
0x180010418  mov     rcx, [rsp+48h]; this
0x18001041d  mov     r9d, eax; char *
0x180010420  mov     edx, 309h; void *
0x180010425  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001042a  jmp     short loc_180010435
0x18001042c  mov     dword ptr [rbx+3Ch], 1
0x180010433  xor     eax, eax
0x180010435  mov     rbx, [rsp+48h+arg_0]
0x18001043a  mov     rsi, [rsp+48h+arg_8]
0x18001043f  add     rsp, 40h
0x180010443  pop     rdi
0x180010444  retn
```
