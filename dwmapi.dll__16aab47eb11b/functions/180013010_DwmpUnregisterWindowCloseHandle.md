# DwmpUnregisterWindowCloseHandle

- ea: `0x180013010`
- end: `0x1800130af`
- name: `DwmpUnregisterWindowCloseHandle`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x18001244c`
- `0x180013010`

## string_xrefs

- `0x180013080`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUnregisterWindowCloseHandle(__int64 a1, __int64 a2)
{
  CApiPortClient *v4; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // [rsp+20h] [rbp-38h]
  int v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+34h] [rbp-24h]
  __int64 v11; // [rsp+3Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v13; // [rsp+70h] [rbp+18h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
    return 2147500033LL;
  v9 = 1073741973;
  v10 = a1;
  v11 = a2;
  v13 = 0;
  v6 = CApiPortClient::SendRequest(v4, &v9, 20, &v13, 0, 0);
  if ( v6 < 0 )
  {
    v7 = 604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v6,
      v8);
    return (unsigned int)v6;
  }
  v6 = v13;
  if ( v13 < 0 )
  {
    v7 = 605;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180013010  mov     [rsp+arg_0], rbx
0x180013015  push    rdi
0x180013016  sub     rsp, 50h
0x18001301a  mov     rbx, rdx
0x18001301d  mov     rdi, rcx
0x180013020  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180013027  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x18001302c  test    al, al
0x18001302e  jnz     short loc_180013037
0x180013030  mov     eax, 80004001h
0x180013035  jmp     short loc_1800130A4
0x180013037  xor     eax, eax
0x180013039  mov     [rsp+58h+var_28], 40000095h
0x180013041  mov     [rsp+58h+var_30], ax; __int16
0x180013046  lea     r9, [rsp+58h+arg_10]; int *
0x18001304b  lea     rdx, [rsp+58h+var_28]; void *
0x180013050  mov     [rsp+58h+var_24], rdi
0x180013055  mov     [rsp+58h+var_1C], rbx
0x18001305a  lea     r8d, [rax+14h]; __int16
0x18001305e  mov     [rsp+58h+arg_10], 0
0x180013066  mov     [rsp+58h+var_38], rax; int
0x18001306b  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180013070  mov     ebx, eax
0x180013072  test    eax, eax
0x180013074  jns     short loc_180013093
0x180013076  mov     edx, 25Ch; void *
0x18001307b  mov     rcx, [rsp+58h]; this
0x180013080  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180013087  mov     r9d, ebx; char *
0x18001308a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001308f  mov     eax, ebx
0x180013091  jmp     short loc_1800130A4
0x180013093  mov     ebx, [rsp+58h+arg_10]
0x180013097  test    ebx, ebx
0x180013099  jns     short loc_1800130A2
0x18001309b  mov     edx, 25Dh
0x1800130a0  jmp     short loc_18001307B
0x1800130a2  xor     eax, eax
0x1800130a4  mov     rbx, [rsp+58h+arg_0]
0x1800130a9  add     rsp, 50h
0x1800130ad  pop     rdi
0x1800130ae  retn
```
