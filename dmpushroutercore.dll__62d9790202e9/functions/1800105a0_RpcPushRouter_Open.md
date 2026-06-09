# RpcPushRouter_Open

- ea: `0x1800105a0`
- end: `0x1800107a4`
- name: `RpcPushRouter_Open`
- size: `516`
- prototype: `__int64 __fastcall(void *, void **, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001370`
- `0x1800039f0`
- `0x18000dc6c`
- `0x18000f694`
- `0x180010320`
- `0x1800103f8`
- `0x1800105a0`
- `0x1800129e8`
- `0x18001478c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001066e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001066e`

## pseudocode

```c
__int64 __fastcall RpcPushRouter_Open(
        PushRouter *a1,
        void **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int v9; // r13d
  int RegisteredInfo; // ebx
  __int16 *v11; // rdx
  PushRouter **v12; // rax
  __int64 v14; // r8
  int ClientHandle; // eax
  DWORD v16; // [rsp+20h] [rbp-51h]
  const OLECHAR **v17; // [rsp+38h] [rbp-39h]
  int v18; // [rsp+40h] [rbp-31h] BYREF
  PushRouter *v19; // [rsp+48h] [rbp-29h] BYREF
  const OLECHAR *v20; // [rsp+50h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-19h] BYREF
  HLOCAL v22; // [rsp+60h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+68h] [rbp-9h] BYREF

  hMem = 0;
  v22 = 0;
  v9 = 0;
  if ( (a3 || a4) && a5 )
  {
    *a2 = 0;
    EnterCriticalSection(&g_csPushRouter);
    v9 = 1;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)MDM_PUSHROUTER_Context,
        (const EVENT_DESCRIPTOR *)PushRouterPushRouterOpenCallReceived,
        v14,
        1u,
        &v23);
    RegisteredInfo = FindRegisteredInfo(a3, a4, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v22);
    if ( RegisteredInfo >= 0 )
    {
      RegisteredInfo = EnsurePushRouterCreated();
      if ( RegisteredInfo >= 0 )
      {
        ClientHandle = PushRouter::GetClientHandle(a1, a1, a3, a4, v16, a5, a2);
        RegisteredInfo = ClientHandle;
        if ( ClientHandle >= 0 )
        {
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
            McTemplateU0zzzd_EventWriteTransfer(
              (_DWORD)a1,
              (unsigned int)PushRouterPushRouterOpenCallSucceeded,
              *((_QWORD *)*a2 + 6),
              (_DWORD)a3,
              (__int64)a4,
              ClientHandle);
          if ( (unsigned int)dword_180050060 > 2 )
          {
            v19 = (PushRouter *)a4;
            v17 = (const OLECHAR **)&v19;
            v11 = (__int16 *)byte_18004648B;
            v23.Ptr = (ULONGLONG)a1;
            v12 = (PushRouter **)&v23;
            goto LABEL_8;
          }
          goto LABEL_9;
        }
      }
    }
  }
  else
  {
    RegisteredInfo = -2147467261;
  }
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    McTemplateU0zzd_EventWriteTransfer((_DWORD)a1, (_DWORD)a2, (_DWORD)a3, (_DWORD)a4, RegisteredInfo);
  if ( (unsigned int)dword_180050060 > 2 )
  {
    v23.Ptr = (ULONGLONG)a4;
    v17 = (const OLECHAR **)&v23;
    v11 = word_1800464DA;
    v19 = a1;
    v12 = &v19;
LABEL_8:
    v20 = a3;
    v18 = RegisteredInfo;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)a1,
      (__int64)v11,
      (__int64)a3,
      (__int64)a4,
      (__int64)v12,
      (__int64)&v18,
      &v20,
      v17);
  }
LABEL_9:
  LocalFree(hMem);
  LocalFree(v22);
  if ( v9 )
    LeaveCriticalSection(&g_csPushRouter);
  return (unsigned int)RegisteredInfo;
}

```

## disassembly

```asm
0x1800105a0  push    rbp
0x1800105a2  push    rbx
0x1800105a3  push    rsi
0x1800105a4  push    rdi
0x1800105a5  push    r12
0x1800105a7  push    r13
0x1800105a9  push    r14
0x1800105ab  push    r15
0x1800105ad  lea     rbp, [rsp-17h]
0x1800105b2  sub     rsp, 88h
0x1800105b9  mov     rax, cs:__security_cookie
0x1800105c0  xor     rax, rsp
0x1800105c3  mov     [rbp+4Fh+var_48], rax
0x1800105c7  mov     r15, [rbp+4Fh+arg_20]
0x1800105cb  xor     eax, eax
0x1800105cd  mov     [rbp+4Fh+hMem], rax
0x1800105d1  mov     rdi, r9
0x1800105d4  mov     [rbp+4Fh+var_60], rax
0x1800105d8  mov     rsi, r8
0x1800105db  mov     r14, rdx
0x1800105de  mov     r12, rcx
0x1800105e1  lea     ebx, [rax+1]
0x1800105e4  mov     r13d, eax
0x1800105e7  test    r8, r8
0x1800105ea  jnz     loc_1800106A8
0x1800105f0  test    r9, r9
0x1800105f3  jnz     loc_1800106A8
0x1800105f9  mov     ebx, 80004003h
0x1800105fe  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x180010605  jz      short loc_180010616
0x180010607  mov     r9, rdi
0x18001060a  mov     [rsp+0C0h+var_A0], ebx
0x18001060e  mov     r8, rsi
0x180010611  call    McTemplateU0zzd_EventWriteTransfer
0x180010616  mov     eax, cs:dword_180050060
0x18001061c  cmp     eax, 2
0x18001061f  jbe     short loc_180010660
0x180010621  lea     rax, [rbp+4Fh+var_58]
0x180010625  mov     qword ptr [rbp+4Fh+var_58], rdi
0x180010629  mov     [rsp+0C0h+var_88], rax
0x18001062e  lea     rdx, word_1800464DA
0x180010635  lea     rax, [rbp+4Fh+var_70]
0x180010639  mov     [rbp+4Fh+var_78], r12
0x18001063d  mov     [rsp+0C0h+var_90], rax
0x180010642  lea     rax, [rbp+4Fh+var_80]
0x180010646  mov     [rsp+0C0h+var_98], rax
0x18001064b  lea     rax, [rbp+4Fh+var_78]
0x18001064f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180010654  mov     [rbp+4Fh+var_70], rsi
0x180010658  mov     [rbp+4Fh+var_80], ebx
0x18001065b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180010660  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180010664  call    cs:__imp_LocalFree
0x18001066a  mov     rcx, [rbp+4Fh+var_60]; hMem
0x18001066e  call    cs:__imp_LocalFree
0x180010674  test    r13d, r13d
0x180010677  jz      short loc_180010686
0x180010679  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010680  call    cs:__imp_LeaveCriticalSection
0x180010686  mov     eax, ebx
0x180010688  mov     rcx, [rbp+4Fh+var_48]
0x18001068c  xor     rcx, rsp; StackCookie
0x18001068f  call    __security_check_cookie
0x180010694  add     rsp, 88h
0x18001069b  pop     r15
0x18001069d  pop     r14
0x18001069f  pop     r13
0x1800106a1  pop     r12
0x1800106a3  pop     rdi
0x1800106a4  pop     rsi
0x1800106a5  pop     rbx
0x1800106a6  pop     rbp
0x1800106a7  retn
0x1800106a8  test    r15, r15
0x1800106ab  jz      loc_1800105F9
0x1800106b1  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800106b8  mov     [rdx], rax
0x1800106bb  call    cs:__imp_EnterCriticalSection
0x1800106c1  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x1800106c8  mov     r13d, ebx
0x1800106cb  jz      short loc_1800106EC
0x1800106cd  lea     rax, [rbp+4Fh+var_58]
0x1800106d1  mov     r9d, ebx
0x1800106d4  lea     rdx, PushRouterPushRouterOpenCallReceived
0x1800106db  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800106e0  lea     rcx, MDM_PUSHROUTER_Context
0x1800106e7  call    McGenEventWrite_EventWriteTransfer
0x1800106ec  lea     r9, [rbp+4Fh+var_60]; unsigned __int16 **
0x1800106f0  mov     rdx, rdi; unsigned __int16 *
0x1800106f3  lea     r8, [rbp+4Fh+hMem]; unsigned __int16 **
0x1800106f7  mov     rcx, rsi; unsigned __int16 *
0x1800106fa  call    ?FindRegisteredInfo@@YAJPEBG0PEAPEAG1@Z; FindRegisteredInfo(ushort const *,ushort const *,ushort * *,ushort * *)
0x1800106ff  mov     ebx, eax
0x180010701  test    eax, eax
0x180010703  js      loc_1800105FE
0x180010709  call    ?EnsurePushRouterCreated@@YAJXZ; EnsurePushRouterCreated(void)
0x18001070e  mov     ebx, eax
0x180010710  test    eax, eax
0x180010712  js      loc_1800105FE
0x180010718  mov     [rsp+0C0h+var_90], r14; void **
0x18001071d  mov     r9, rdi; unsigned __int16 *
0x180010720  mov     r8, rsi; unsigned __int16 *
0x180010723  mov     [rsp+0C0h+var_98], r15; unsigned __int16 **
0x180010728  mov     rdx, r12; void *
0x18001072b  call    ?GetClientHandle@PushRouter@@QEAAJPEAXPEBG1HPEAPEAGPEAPEAX@Z; PushRouter::GetClientHandle(void *,ushort const *,ushort const *,int,ushort * *,void * *)
0x180010730  mov     ebx, eax
0x180010732  test    eax, eax
0x180010734  js      loc_1800105FE
0x18001073a  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180010741  jz      short loc_180010762
0x180010743  mov     r8, [r14]
0x180010746  lea     rdx, PushRouterPushRouterOpenCallSucceeded
0x18001074d  mov     dword ptr [rsp+0C0h+var_98], eax
0x180010751  mov     r9, rsi
0x180010754  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180010759  mov     r8, [r8+30h]
0x18001075d  call    McTemplateU0zzzd_EventWriteTransfer
0x180010762  mov     eax, cs:dword_180050060
0x180010768  cmp     eax, 2
0x18001076b  jbe     loc_180010660
0x180010771  lea     rax, [rbp+4Fh+var_78]
0x180010775  mov     [rbp+4Fh+var_78], rdi
0x180010779  mov     [rsp+0C0h+var_88], rax
0x18001077e  lea     rdx, byte_18004648B
0x180010785  lea     rax, [rbp+4Fh+var_70]
0x180010789  mov     qword ptr [rbp+4Fh+var_58], r12
0x18001078d  mov     [rsp+0C0h+var_90], rax
0x180010792  lea     rax, [rbp+4Fh+var_80]
0x180010796  mov     [rsp+0C0h+var_98], rax
0x18001079b  lea     rax, [rbp+4Fh+var_58]
0x18001079f  jmp     loc_18001064F
```
