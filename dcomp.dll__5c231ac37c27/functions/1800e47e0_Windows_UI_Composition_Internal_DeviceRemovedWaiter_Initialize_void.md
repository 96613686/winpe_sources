# Windows::UI::Composition::Internal::DeviceRemovedWaiter::Initialize(void)

- ea: `0x1800e47e0`
- end: `0x1800e4902`
- name: `?Initialize@DeviceRemovedWaiter@Internal@Composition@UI@Windows@@QEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f9f8`

## callees

- `0x18001358c`
- `0x18004057c`
- `0x1800bafcc`
- `0x1800bb00c`
- `0x1800d4e8c`
- `0x1800e47e0`
- `0x1800e4908`
- `0x1800e55cc`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800e47f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800e47f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4807`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800e489b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800e489b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800e48f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800e48f1`

## string_xrefs

- `0x1800e482e`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtsharedd3ddevicepool.cpp`
- `0x1800e4872`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtsharedd3ddevicepool.cpp`
- `0x1800e48d7`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtsharedd3ddevicepool.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Internal::DeviceRemovedWaiter::Initialize(char *pv)
{
  wil::details *v2; // rcx
  HANDLE Event; // rsi
  HANDLE *v4; // rdi
  int LastErrorFailHr; // eax
  unsigned int v6; // edi
  int v8; // eax
  unsigned int v9; // esi
  PTP_WAIT ThreadpoolWait; // rax
  const char *v11; // r9
  struct _TP_WAIT *v12; // rbp
  struct _TP_WAIT *v13; // rsi
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v16; // [rsp+50h] [rbp+8h] BYREF

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v4 = (HANDLE *)(pv + 24);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      pv + 24,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v6 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtsharedd3ddevicepool.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v14);
      return v6;
    }
    v4 = (HANDLE *)(pv + 24);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, HANDLE, char *))(**((_QWORD **)pv + 2) + 520LL))(
         *((_QWORD *)pv + 2),
         *v4,
         pv + 40);
  v9 = v8;
  if ( v8 >= 0 )
  {
    pv[44] = 1;
    ThreadpoolWait = CreateThreadpoolWait(
                       Windows::UI::Composition::Internal::DeviceRemovedWaiter::Initialize_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                       pv,
                       0);
    v12 = (struct _TP_WAIT *)*((_QWORD *)pv + 4);
    v13 = ThreadpoolWait;
    if ( v12 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      wil::details::DestroyThreadPoolWait<0>::Destroy(v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    *((_QWORD *)pv + 4) = v13;
    if ( v13 )
    {
      SetThreadpoolWait(v13, *v4, 0);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x46,
               (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtsharedd3ddevicepool.cpp",
               v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtsharedd3ddevicepool.cpp",
      (const char *)(unsigned int)v8,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x1800e47e0  push    rbx
0x1800e47e2  push    rbp
0x1800e47e3  push    rsi
0x1800e47e4  push    rdi
0x1800e47e5  sub     rsp, 28h
0x1800e47e9  mov     rbx, rcx
0x1800e47ec  mov     r9d, 1F0003h; dwDesiredAccess
0x1800e47f2  xor     ecx, ecx; lpEventAttributes
0x1800e47f4  xor     r8d, r8d; dwFlags
0x1800e47f7  xor     edx, edx; lpName
0x1800e47f9  call    cs:__imp_CreateEventExW
0x1800e47ff  mov     rsi, rax
0x1800e4802  test    rax, rax
0x1800e4805  jz      short loc_1800E481E
0x1800e4807  call    cs:__imp_GetLastError
0x1800e480d  lea     rdi, [rbx+18h]
0x1800e4811  mov     rdx, rsi
0x1800e4814  mov     rcx, rdi
0x1800e4817  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800e481c  jmp     short loc_1800E484D
0x1800e481e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e4823  mov     edi, eax
0x1800e4825  test    eax, eax
0x1800e4827  jns     short loc_1800E4849
0x1800e4829  mov     rcx, [rsp+48h]; this
0x1800e482e  lea     r8, aOnecoreuapWind_276; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800e4835  mov     r9d, eax; char *
0x1800e4838  mov     edx, 33h ; '3'; void *
0x1800e483d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4842  mov     eax, edi
0x1800e4844  jmp     loc_1800E48F9
0x1800e4849  lea     rdi, [rbx+18h]
0x1800e484d  mov     rcx, [rbx+10h]
0x1800e4851  lea     r8, [rbx+28h]
0x1800e4855  mov     rdx, [rdi]
0x1800e4858  mov     rax, [rcx]
0x1800e485b  mov     rax, [rax+208h]
0x1800e4862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4867  mov     esi, eax
0x1800e4869  test    eax, eax
0x1800e486b  jns     short loc_1800E488A
0x1800e486d  mov     rcx, [rsp+48h]; this
0x1800e4872  lea     r8, aOnecoreuapWind_276; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800e4879  mov     r9d, eax; char *
0x1800e487c  mov     edx, 37h ; '7'; void *
0x1800e4881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4886  mov     eax, esi
0x1800e4888  jmp     short loc_1800E48F9
0x1800e488a  xor     r8d, r8d; pcbe
0x1800e488d  mov     byte ptr [rbx+2Ch], 1
0x1800e4891  mov     rdx, rbx; pv
0x1800e4894  lea     rcx, _Windows__UI__Composition__Internal__DeviceRemovedWaiter__Initialize____2____lambda_1____lambda_invoker_cdecl_; pfnwa
0x1800e489b  call    cs:__imp_CreateThreadpoolWait
0x1800e48a1  mov     rbp, [rbx+20h]
0x1800e48a5  mov     rsi, rax
0x1800e48a8  test    rbp, rbp
0x1800e48ab  jz      short loc_1800E48C9
0x1800e48ad  lea     rcx, [rsp+48h+arg_0]; this
0x1800e48b2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800e48b7  mov     rcx, rbp; pwa
0x1800e48ba  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800e48bf  lea     rcx, [rsp+48h+arg_0]; this
0x1800e48c4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800e48c9  mov     [rbx+20h], rsi
0x1800e48cd  test    rsi, rsi
0x1800e48d0  jnz     short loc_1800E48E8
0x1800e48d2  mov     rcx, [rsp+48h]; this
0x1800e48d7  lea     r8, aOnecoreuapWind_276; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800e48de  lea     edx, [rsi+46h]; void *
0x1800e48e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e48e6  jmp     short loc_1800E48F9
0x1800e48e8  mov     rdx, [rdi]; h
0x1800e48eb  xor     r8d, r8d; pftTimeout
0x1800e48ee  mov     rcx, rsi; pwa
0x1800e48f1  call    cs:__imp_SetThreadpoolWait
0x1800e48f7  xor     eax, eax
0x1800e48f9  add     rsp, 28h
0x1800e48fd  pop     rdi
0x1800e48fe  pop     rsi
0x1800e48ff  pop     rbp
0x1800e4900  pop     rbx
0x1800e4901  retn
```
