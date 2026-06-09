# CCscWmiCacheObject::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x180020750`
- end: `0x1800208a1`
- name: `?_SetObjectProperties@CCscWmiCacheObject@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `337`
- prototype: `int(CCscWmiCacheObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180020548`
- `0x180020750`
- `0x180022dc4`
- `0x1800230ac`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800207d4`

## pseudocode

```c
__int64 __fastcall CCscWmiCacheObject::_SetObjectProperties(
        CCscWmiCacheObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  CCscWmiCacheObject *v6; // rcx
  int v7; // eax
  int v8; // ebx
  int v9; // r8d
  __int64 v10; // rcx
  int v12[6]; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+28h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 67, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
  }
  v6 = (CCscWmiCacheObject *)*((_QWORD *)this + 2);
  if ( !v6 )
    goto LABEL_7;
  pv = 0;
  v7 = (*(__int64 (__fastcall **)(CCscWmiCacheObject *, LPVOID *, struct IWbemContext *))(*(_QWORD *)v6 + 104LL))(
         v6,
         &pv,
         a3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = WmiProp_SetStringProperty(a4, L"Location", (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    if ( v8 >= 0 )
    {
LABEL_7:
      v12[0] = 0;
      LODWORD(pv) = 0;
      if ( CCscWmiCacheObject::_QueryCscCacheStatus(v6, v12, (int *)&pv) >= 0 )
      {
        v9 = (int)pv;
      }
      else
      {
        v9 = 0;
        LODWORD(pv) = 0;
        v12[0] = 0;
      }
      v8 = WmiProp_SetBooleanProperty(a4, L"Enabled", v9);
      if ( v8 >= 0 )
        v8 = WmiProp_SetBooleanProperty(a4, L"Active", v12[0]);
    }
LABEL_15:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v8;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      68,
      WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      (unsigned int)v7);
    goto LABEL_15;
  }
LABEL_16:
  if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_DWORD *)(v10 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v10 + 16), 69, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020750  push    rbp
0x180020752  push    rbx
0x180020753  push    rdi
0x180020754  push    r14
0x180020756  mov     rbp, rsp
0x180020759  sub     rsp, 38h
0x18002075d  mov     rdi, r9
0x180020760  mov     rbx, rcx
0x180020763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002076a  lea     r14, WPP_GLOBAL_Control
0x180020771  cmp     rcx, r14
0x180020774  jz      short loc_180020794
0x180020776  test    dword ptr [rcx+1Ch], 4000000h
0x18002077d  jz      short loc_180020794
0x18002077f  mov     rcx, [rcx+10h]
0x180020783  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18002078a  mov     edx, 43h ; 'C'
0x18002078f  call    WPP_SF_
0x180020794  mov     rcx, [rbx+10h]
0x180020798  test    rcx, rcx
0x18002079b  jz      short loc_1800207E2
0x18002079d  mov     [rbp+pv], 0
0x1800207a5  lea     rdx, [rbp+pv]
0x1800207a9  mov     rax, [rcx]
0x1800207ac  mov     rax, [rax+68h]
0x1800207b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b5  mov     ebx, eax
0x1800207b7  test    eax, eax
0x1800207b9  js      short loc_18002080E
0x1800207bb  mov     r8, [rbp+pv]; unsigned __int16 *
0x1800207bf  lea     rdx, CSCWMI_STR_PROP_LOCATION; "Location"
0x1800207c6  mov     rcx, rdi; struct IWbemClassObject *
0x1800207c9  call    ?WmiProp_SetStringProperty@@YAJPEAUIWbemClassObject@@PEBG1@Z; WmiProp_SetStringProperty(IWbemClassObject *,ushort const *,ushort const *)
0x1800207ce  mov     rcx, [rbp+pv]; pv
0x1800207d2  mov     ebx, eax
0x1800207d4  call    cs:__imp_CoTaskMemFree
0x1800207da  test    ebx, ebx
0x1800207dc  js      loc_180020868
0x1800207e2  lea     r8, [rbp+pv]; int *
0x1800207e6  mov     [rbp+var_18], 0
0x1800207ed  lea     rdx, [rbp+var_18]; int *
0x1800207f1  mov     dword ptr [rbp+pv], 0
0x1800207f8  call    ?_QueryCscCacheStatus@CCscWmiCacheObject@@AEAAJPEAH0@Z; CCscWmiCacheObject::_QueryCscCacheStatus(int *,int *)
0x1800207fd  test    eax, eax
0x1800207ff  jns     short loc_18002083A
0x180020801  xor     r8d, r8d
0x180020804  mov     dword ptr [rbp+pv], r8d
0x180020808  mov     [rbp+var_18], r8d
0x18002080c  jmp     short loc_18002083E
0x18002080e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020815  cmp     rcx, r14
0x180020818  jz      short loc_180020895
0x18002081a  test    byte ptr [rcx+1Ch], 2
0x18002081e  jz      short loc_18002086F
0x180020820  mov     rcx, [rcx+10h]
0x180020824  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18002082b  mov     edx, 44h ; 'D'
0x180020830  mov     r9d, eax
0x180020833  call    WPP_SF_d
0x180020838  jmp     short loc_180020868
0x18002083a  mov     r8d, dword ptr [rbp+pv]; int
0x18002083e  lea     rdx, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x180020845  mov     rcx, rdi; struct IWbemClassObject *
0x180020848  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x18002084d  mov     ebx, eax
0x18002084f  test    eax, eax
0x180020851  js      short loc_180020868
0x180020853  mov     r8d, [rbp+var_18]; int
0x180020857  lea     rdx, CSCWMI_STR_PROP_ACTIVE; "Active"
0x18002085e  mov     rcx, rdi; struct IWbemClassObject *
0x180020861  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180020866  mov     ebx, eax
0x180020868  mov     rcx, cs:WPP_GLOBAL_Control
0x18002086f  cmp     rcx, r14
0x180020872  jz      short loc_180020895
0x180020874  test    dword ptr [rcx+1Ch], 4000000h
0x18002087b  jz      short loc_180020895
0x18002087d  mov     rcx, [rcx+10h]
0x180020881  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180020888  mov     edx, 45h ; 'E'
0x18002088d  mov     r9d, ebx
0x180020890  call    WPP_SF_d
0x180020895  mov     eax, ebx
0x180020897  add     rsp, 38h
0x18002089b  pop     r14
0x18002089d  pop     rdi
0x18002089e  pop     rbx
0x18002089f  pop     rbp
0x1800208a0  retn
```
