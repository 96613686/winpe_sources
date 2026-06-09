# HrOnCommandDeleteBridgeConnections(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x180045340`
- end: `0x180045512`
- name: `?HrOnCommandDeleteBridgeConnections@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018d74`
- `0x18001bc10`
- `0x18001d580`
- `0x18002bf6c`
- `0x18002c0a8`
- `0x180034cc8`
- `0x180034fbc`
- `0x180040a5c`
- `0x18004449c`
- `0x180045340`
- `0x180065010`

## import_xrefs

- `USER32!SendMessageW` at `0x180045455`
- `USER32!SendMessageW` at `0x1800454ed`
- `USER32!SendMessageW` at `0x180045455`
- `USER32!SendMessageW` at `0x1800454ed`
- `ole32!CoCreateInstance` at `0x1800453a2`
- `ole32!CoCreateInstance` at `0x1800453a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrOnCommandDeleteBridgeConnections(__int64 *a1, HWND a2)
{
  HICON v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  HRESULT Instance; // esi
  __int64 i; // rbx
  unsigned int v9; // r9d
  struct IUnknown *v11[5]; // [rsp+30h] [rbp-28h] BYREF
  struct IUnknown *ppv; // [rsp+78h] [rbp+20h] BYREF

  v4 = BeginWaitCursor();
  v11[1] = (struct IUnknown *)v4;
  ppv = 0;
  if ( (unsigned int)FCheckGroupMembershipInternal(v6, v5, 0x220u, 0) )
  {
    Instance = CoCreateInstance(&CLSID_HNetCfgMgr, 0, 3u, &IID_IHNetCfgMgr, (LPVOID *)&ppv);
LABEL_3:
    if ( Instance >= 0 )
    {
      for ( i = *a1; i != a1[1] && Instance >= 0; i += 8 )
      {
        v11[0] = 0;
        Instance = HrNetConFromPidl(i, v11, 1);
        if ( Instance >= 0 )
        {
          SetLUAParent(v11[0], a2);
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, __int64))ppv->lpVtbl[2].AddRef)(
                       ppv,
                       v11[0],
                       1);
        }
      }
      ReleaseObj(ppv);
      if ( Instance >= 0 )
        goto LABEL_24;
    }
    if ( (unsigned int)HR_CANCELLED(Instance) )
      goto LABEL_24;
    if ( Instance != -2147220764 )
    {
      if ( Instance == -2147180508 )
      {
        v9 = 10603;
        goto LABEL_23;
      }
      if ( Instance != -2147024891 )
      {
        if ( Instance == -2147024882 )
        {
          v9 = 1101;
          goto LABEL_23;
        }
        if ( Instance != -2147024156 )
        {
          v9 = 10605;
LABEL_23:
          NcMsgBox(hInst, a2, 0x424u, v9, 0x30u);
LABEL_24:
          SendMessageW(a2, 0x111u, 2u, Instance);
          Instance = 0;
          goto LABEL_25;
        }
      }
    }
    v9 = 1096;
    goto LABEL_23;
  }
  Instance = CoCreateInstanceAsAdmin(a2, &CLSID_HNetCfgMgr, &IID_IHNetCfgMgr, (void **)&ppv);
  if ( !(unsigned int)HR_CANCELLED(Instance) )
    goto LABEL_3;
  SendMessageW(a2, 0x111u, 2u, 0);
LABEL_25:
  EndWaitCursor(v4);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180045340  mov     [rsp+arg_0], rbx
0x180045345  mov     [rsp+arg_8], rbp
0x18004534a  push    rsi
0x18004534b  push    rdi
0x18004534c  push    r14
0x18004534e  sub     rsp, 40h
0x180045352  mov     rbp, rdx
0x180045355  mov     r14, rcx
0x180045358  call    ?BeginWaitCursor@@YAPEAUHICON__@@XZ; BeginWaitCursor(void)
0x18004535d  mov     rdi, rax
0x180045360  mov     [rsp+58h+var_20], rax
0x180045365  mov     [rsp+58h+arg_18], 0
0x18004536e  xor     r9d, r9d; int
0x180045371  mov     r8d, 220h; unsigned int
0x180045377  call    ?FCheckGroupMembershipInternal@@YAHEKKH@Z; FCheckGroupMembershipInternal(uchar,ulong,ulong,int)
0x18004537c  test    eax, eax
0x18004537e  jz      loc_18004541A
0x180045384  lea     rax, [rsp+58h+arg_18]
0x180045389  mov     [rsp+58h+ppv], rax; ppv
0x18004538e  lea     r9, IID_IHNetCfgMgr; riid
0x180045395  xor     edx, edx; pUnkOuter
0x180045397  lea     r8d, [rdx+3]; dwClsContext
0x18004539b  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x1800453a2  call    cs:__imp_CoCreateInstance
0x1800453a8  mov     esi, eax
0x1800453aa  test    esi, esi
0x1800453ac  js      loc_18004546E
0x1800453b2  mov     rbx, [r14]
0x1800453b5  cmp     rbx, [r14+8]
0x1800453b9  jz      loc_180045460
0x1800453bf  test    esi, esi
0x1800453c1  js      loc_180045460
0x1800453c7  mov     [rsp+58h+var_28], 0
0x1800453d0  mov     r8d, 1
0x1800453d6  lea     rdx, [rsp+58h+var_28]
0x1800453db  mov     rcx, rbx
0x1800453de  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x1800453e3  mov     esi, eax
0x1800453e5  test    eax, eax
0x1800453e7  js      short loc_180045414
0x1800453e9  mov     rdx, rbp; HWND
0x1800453ec  mov     rcx, [rsp+58h+var_28]; struct IUnknown *
0x1800453f1  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x1800453f6  mov     rcx, [rsp+58h+arg_18]
0x1800453fb  mov     rax, [rcx]
0x1800453fe  mov     r8d, 1
0x180045404  mov     rdx, [rsp+58h+var_28]
0x180045409  mov     rax, [rax+38h]
0x18004540d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045412  mov     esi, eax
0x180045414  add     rbx, 8
0x180045418  jmp     short loc_1800453B5
0x18004541a  lea     r9, [rsp+58h+arg_18]; void **
0x18004541f  lea     r8, IID_IHNetCfgMgr; struct _GUID *
0x180045426  lea     rdx, CLSID_HNetCfgMgr; struct _GUID *
0x18004542d  mov     rcx, rbp; HWND
0x180045430  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180045435  mov     esi, eax
0x180045437  mov     ecx, eax; int
0x180045439  call    ?HR_CANCELLED@@YAHJ@Z; HR_CANCELLED(long)
0x18004543e  test    eax, eax
0x180045440  jz      loc_1800453AA
0x180045446  xor     r9d, r9d; lParam
0x180045449  mov     edx, 111h; Msg
0x18004544e  lea     r8d, [r9+2]; wParam
0x180045452  mov     rcx, rbp; hWnd
0x180045455  call    cs:__imp_SendMessageW
0x18004545b  jmp     loc_1800454F5
0x180045460  mov     rcx, [rsp+58h+arg_18]; struct IUnknown *
0x180045465  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004546a  test    esi, esi
0x18004546c  jns     short loc_1800454DC
0x18004546e  mov     ecx, esi; int
0x180045470  call    ?HR_CANCELLED@@YAHJ@Z; HR_CANCELLED(long)
0x180045475  test    eax, eax
0x180045477  jnz     short loc_1800454DC
0x180045479  cmp     esi, 800402E4h
0x18004547f  jz      short loc_1800454B9
0x180045481  cmp     esi, 8004A024h
0x180045487  jz      short loc_1800454B1
0x180045489  cmp     esi, 80070005h
0x18004548f  jz      short loc_1800454B9
0x180045491  cmp     esi, 8007000Eh
0x180045497  jz      short loc_1800454A9
0x180045499  cmp     esi, 800702E4h
0x18004549f  jz      short loc_1800454B9
0x1800454a1  mov     r9d, 296Dh
0x1800454a7  jmp     short loc_1800454BF
0x1800454a9  mov     r9d, 44Dh
0x1800454af  jmp     short loc_1800454BF
0x1800454b1  mov     r9d, 296Bh
0x1800454b7  jmp     short loc_1800454BF
0x1800454b9  mov     r9d, 448h; unsigned int
0x1800454bf  mov     dword ptr [rsp+58h+ppv], 30h ; '0'; uType
0x1800454c7  mov     r8d, 424h; unsigned int
0x1800454cd  mov     rdx, rbp; hWnd
0x1800454d0  mov     rcx, cs:hInst; hModule
0x1800454d7  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x1800454dc  movsxd  r9, esi; lParam
0x1800454df  mov     edx, 111h; Msg
0x1800454e4  mov     r8d, 2; wParam
0x1800454ea  mov     rcx, rbp; hWnd
0x1800454ed  call    cs:__imp_SendMessageW
0x1800454f3  xor     esi, esi
0x1800454f5  mov     rcx, rdi; HICON
0x1800454f8  call    ?EndWaitCursor@@YAXPEAUHICON__@@@Z; EndWaitCursor(HICON__ *)
0x1800454fd  mov     eax, esi
0x1800454ff  mov     rbx, [rsp+58h+arg_0]
0x180045504  mov     rbp, [rsp+58h+arg_8]
0x180045509  add     rsp, 40h
0x18004550d  pop     r14
0x18004550f  pop     rdi
0x180045510  pop     rsi
0x180045511  retn
```
