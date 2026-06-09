# ExecuteRulesInTransaction

- ea: `0x140008c44`
- end: `0x140008ead`
- name: `ExecuteRulesInTransaction`
- size: `617`
- prototype: `void __fastcall(wchar_t ***, wchar_t *, struct IUnknown **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009550`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x140008034`
- `0x140008c44`
- `0x14000cd44`
- `0x14000d110`
- `0x140020010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140008c8d`
- `ole32!CoCreateInstance` at `0x140008c8d`
- `comsvcs!CoEnterServiceDomain` at `0x140008d9f`
- `comsvcs!CoEnterServiceDomain` at `0x140008d9f`
- `comsvcs!CoLeaveServiceDomain` at `0x140008e1b`
- `comsvcs!CoLeaveServiceDomain` at `0x140008e1b`

## pseudocode

```c
void __fastcall ExecuteRulesInTransaction(wchar_t ***a1, wchar_t *a2, struct IUnknown **a3, unsigned int a4)
{
  HRESULT Instance; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  wchar_t *v11; // rdx
  IUnknown *pConfigObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-20h]

  pConfigObject = 0;
  v13 = 0;
  Instance = CoCreateInstance(
               &GUID_ecabb0c8_7f19_11d2_978e_0000f8757e2a,
               0,
               1u,
               &IID_IUnknown,
               (LPVOID *)&pConfigObject);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pConfigObject->lpVtbl->QueryInterface)(
                 pConfigObject,
                 &GUID_59f4c2a3_d3d7_4a31_b6e4_6ab3177c50b9,
                 &v13);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 24LL))(v13, 3);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, 4);
        if ( Instance >= 0 )
        {
          Instance = CoEnterServiceDomain(pConfigObject);
          if ( Instance >= 0 )
          {
            CMqGenObj::CMqGenObj((CMqGenObj *)pExceptionObject);
            if ( *a1 )
              v11 = **a1;
            else
              v11 = 0;
            Instance = CMqGenObj::InvokeTransactionalRuleHandlers((CMqGenObj *)pExceptionObject, v11, a2, *a3, a4);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            CoLeaveServiceDomain(pConfigObject);
            if ( Instance < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 31;
                goto LABEL_30;
              }
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 30;
              goto LABEL_30;
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 29;
            goto LABEL_30;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 28;
          goto LABEL_30;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 27;
        goto LABEL_30;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 26;
LABEL_30:
      WPP_SF_d(v9[2], v10, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
    }
  }
  if ( pConfigObject )
    ((void (__fastcall *)(IUnknown *))pConfigObject->lpVtbl->Release)(pConfigObject);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( Instance < 0 )
  {
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, Instance);
    throw (bad_hresult *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140008c44  push    rbp
0x140008c46  push    rbx
0x140008c47  push    rsi
0x140008c48  push    rdi
0x140008c49  push    r14
0x140008c4b  push    r15
0x140008c4d  mov     rbp, rsp
0x140008c50  sub     rsp, 68h
0x140008c54  mov     r14d, r9d
0x140008c57  mov     rdi, r8
0x140008c5a  mov     r15, rdx
0x140008c5d  mov     rsi, rcx
0x140008c60  mov     [rbp+pConfigObject], 0
0x140008c68  mov     [rbp+var_30], 0
0x140008c70  lea     rax, [rbp+pConfigObject]
0x140008c74  mov     [rsp+68h+ppv], rax; ppv
0x140008c79  lea     r9, IID_IUnknown; riid
0x140008c80  xor     edx, edx; pUnkOuter
0x140008c82  lea     r8d, [rdx+1]; dwClsContext
0x140008c86  lea     rcx, _GUID_ecabb0c8_7f19_11d2_978e_0000f8757e2a; rclsid
0x140008c8d  call    cs:__imp_CoCreateInstance
0x140008c93  mov     ebx, eax
0x140008c95  test    eax, eax
0x140008c97  jns     short loc_140008CC4
0x140008c99  lea     rax, WPP_GLOBAL_Control
0x140008ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ca7  cmp     rcx, rax
0x140008caa  jz      loc_140008E56
0x140008cb0  test    byte ptr [rcx+1Ch], 1
0x140008cb4  jz      loc_140008E56
0x140008cba  mov     edx, 1Ah
0x140008cbf  jmp     loc_140008E43
0x140008cc4  mov     rcx, [rbp+pConfigObject]
0x140008cc8  mov     rax, [rcx]
0x140008ccb  lea     r8, [rbp+var_30]
0x140008ccf  lea     rdx, _GUID_59f4c2a3_d3d7_4a31_b6e4_6ab3177c50b9
0x140008cd6  mov     rax, [rax]
0x140008cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cde  mov     ebx, eax
0x140008ce0  test    eax, eax
0x140008ce2  jns     short loc_140008D0F
0x140008ce4  lea     rax, WPP_GLOBAL_Control
0x140008ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008cf2  cmp     rcx, rax
0x140008cf5  jz      loc_140008E56
0x140008cfb  test    byte ptr [rcx+1Ch], 1
0x140008cff  jz      loc_140008E56
0x140008d05  mov     edx, 1Bh
0x140008d0a  jmp     loc_140008E43
0x140008d0f  mov     rcx, [rbp+var_30]
0x140008d13  mov     rax, [rcx]
0x140008d16  mov     edx, 3
0x140008d1b  mov     rax, [rax+18h]
0x140008d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d24  mov     ebx, eax
0x140008d26  test    eax, eax
0x140008d28  jns     short loc_140008D55
0x140008d2a  lea     rax, WPP_GLOBAL_Control
0x140008d31  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d38  cmp     rcx, rax
0x140008d3b  jz      loc_140008E56
0x140008d41  test    byte ptr [rcx+1Ch], 1
0x140008d45  jz      loc_140008E56
0x140008d4b  mov     edx, 1Ch
0x140008d50  jmp     loc_140008E43
0x140008d55  mov     rcx, [rbp+var_30]
0x140008d59  mov     rax, [rcx]
0x140008d5c  mov     edx, 4
0x140008d61  mov     rax, [rax+20h]
0x140008d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d6a  mov     ebx, eax
0x140008d6c  test    eax, eax
0x140008d6e  jns     short loc_140008D9B
0x140008d70  lea     rax, WPP_GLOBAL_Control
0x140008d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d7e  cmp     rcx, rax
0x140008d81  jz      loc_140008E56
0x140008d87  test    byte ptr [rcx+1Ch], 1
0x140008d8b  jz      loc_140008E56
0x140008d91  mov     edx, 1Dh
0x140008d96  jmp     loc_140008E43
0x140008d9b  mov     rcx, [rbp+pConfigObject]; pConfigObject
0x140008d9f  call    cs:__imp_CoEnterServiceDomain
0x140008da5  mov     ebx, eax
0x140008da7  test    eax, eax
0x140008da9  jns     short loc_140008DD3
0x140008dab  lea     rax, WPP_GLOBAL_Control
0x140008db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140008db9  cmp     rcx, rax
0x140008dbc  jz      loc_140008E56
0x140008dc2  test    byte ptr [rcx+1Ch], 1
0x140008dc6  jz      loc_140008E56
0x140008dcc  mov     edx, 1Eh
0x140008dd1  jmp     short loc_140008E43
0x140008dd3  lea     rcx, [rbp+pExceptionObject]; this
0x140008dd7  call    ??0CMqGenObj@@QEAA@XZ; CMqGenObj::CMqGenObj(void)
0x140008ddc  mov     rax, [rsi]
0x140008ddf  test    rax, rax
0x140008de2  jz      short loc_140008DE9
0x140008de4  mov     rdx, [rax]
0x140008de7  jmp     short loc_140008DEB
0x140008de9  xor     edx, edx; wchar_t *
0x140008deb  mov     dword ptr [rsp+68h+ppv], r14d; unsigned int
0x140008df0  mov     r9, [rdi]; struct IUnknown *
0x140008df3  mov     r8, r15; wchar_t *
0x140008df6  lea     rcx, [rbp+pExceptionObject]; this
0x140008dfa  call    ?InvokeTransactionalRuleHandlers@CMqGenObj@@UEAAJPEA_W0PEAUIUnknown@@K@Z; CMqGenObj::InvokeTransactionalRuleHandlers(wchar_t *,wchar_t *,IUnknown *,ulong)
0x140008dff  mov     ebx, eax
0x140008e01  mov     rcx, [rbp+var_20]
0x140008e05  test    rcx, rcx
0x140008e08  jz      short loc_140008E17
0x140008e0a  mov     rax, [rcx]
0x140008e0d  mov     rax, [rax+10h]
0x140008e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e16  nop
0x140008e17  mov     rcx, [rbp+pConfigObject]; pUnkStatus
0x140008e1b  call    cs:__imp_CoLeaveServiceDomain
0x140008e21  test    ebx, ebx
0x140008e23  jns     short loc_140008E56
0x140008e25  lea     rax, WPP_GLOBAL_Control
0x140008e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e33  cmp     rcx, rax
0x140008e36  jz      short loc_140008E56
0x140008e38  test    byte ptr [rcx+1Ch], 1
0x140008e3c  jz      short loc_140008E56
0x140008e3e  mov     edx, 1Fh
0x140008e43  mov     r9d, ebx
0x140008e46  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x140008e4d  mov     rcx, [rcx+10h]
0x140008e51  call    WPP_SF_d
0x140008e56  mov     rcx, [rbp+pConfigObject]
0x140008e5a  test    rcx, rcx
0x140008e5d  jz      short loc_140008E6B
0x140008e5f  mov     rax, [rcx]
0x140008e62  mov     rax, [rax+10h]
0x140008e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e6b  mov     rcx, [rbp+var_30]
0x140008e6f  test    rcx, rcx
0x140008e72  jz      short loc_140008E80
0x140008e74  mov     rax, [rcx]
0x140008e77  mov     rax, [rax+10h]
0x140008e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e80  test    ebx, ebx
0x140008e82  jns     short loc_140008EA0
0x140008e84  mov     edx, ebx; unsigned int
0x140008e86  lea     rcx, [rbp+pExceptionObject]; this
0x140008e8a  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x140008e8f  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x140008e96  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140008e9a  call    _CxxThrowException_0
0x140008ea0  add     rsp, 68h
0x140008ea4  pop     r15
0x140008ea6  pop     r14
0x140008ea8  pop     rdi
0x140008ea9  pop     rsi
0x140008eaa  pop     rbx
0x140008eab  pop     rbp
0x140008eac  retn
```
