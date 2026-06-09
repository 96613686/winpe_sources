# DwmpIsWindowCapturable

- ea: `0x180012870`
- end: `0x180012929`
- name: `DwmpIsWindowCapturable`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x18001244c`
- `0x180012870`

## string_xrefs

- `0x1800128ed`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpIsWindowCapturable(__int64 a1, _DWORD *a2)
{
  CApiPortClient *v4; // rcx
  int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-28h]
  int v9; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+34h] [rbp-14h]
  int v11; // [rsp+3Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v13; // [rsp+60h] [rbp+18h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
    return 2147500033LL;
  v11 = 0;
  *a2 = 0;
  v9 = 1073741974;
  v10 = a1;
  v13 = 0;
  v5 = CApiPortClient::SendRequest(v4, &v9, 16, &v13, &v9, 16);
  if ( v5 < 0 )
  {
    v6 = 630;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v5,
      v8);
    return (unsigned int)v5;
  }
  v5 = v13;
  if ( v13 < 0 )
  {
    v6 = 631;
    goto LABEL_4;
  }
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x180012870  mov     [rsp+arg_0], rbx
0x180012875  push    rdi
0x180012876  sub     rsp, 40h
0x18001287a  mov     rdi, rdx
0x18001287d  mov     rbx, rcx
0x180012880  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180012887  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x18001288c  test    al, al
0x18001288e  jz      loc_180012919
0x180012894  mov     eax, 10h
0x180012899  mov     [rsp+48h+var_C], 0
0x1800128a1  mov     [rsp+48h+var_20], ax; __int16
0x1800128a6  lea     r9, [rsp+48h+arg_10]; int *
0x1800128ab  mov     r8d, eax; __int16
0x1800128ae  mov     dword ptr [rdi], 0
0x1800128b4  lea     rax, [rsp+48h+var_18]
0x1800128b9  mov     [rsp+48h+var_18], 40000096h
0x1800128c1  lea     rdx, [rsp+48h+var_18]; void *
0x1800128c6  mov     [rsp+48h+var_28], rax; int
0x1800128cb  mov     [rsp+48h+var_14], rbx
0x1800128d0  mov     [rsp+48h+arg_10], 0
0x1800128d8  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x1800128dd  mov     ebx, eax
0x1800128df  test    eax, eax
0x1800128e1  jns     short loc_180012900
0x1800128e3  mov     edx, 276h; void *
0x1800128e8  mov     rcx, [rsp+48h]; this
0x1800128ed  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x1800128f4  mov     r9d, ebx; char *
0x1800128f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128fc  mov     eax, ebx
0x1800128fe  jmp     short loc_18001291E
0x180012900  mov     ebx, [rsp+48h+arg_10]
0x180012904  test    ebx, ebx
0x180012906  jns     short loc_18001290F
0x180012908  mov     edx, 277h
0x18001290d  jmp     short loc_1800128E8
0x18001290f  mov     eax, [rsp+48h+var_C]
0x180012913  mov     [rdi], eax
0x180012915  xor     eax, eax
0x180012917  jmp     short loc_18001291E
0x180012919  mov     eax, 80004001h
0x18001291e  mov     rbx, [rsp+48h+arg_0]
0x180012923  add     rsp, 40h
0x180012927  pop     rdi
0x180012928  retn
```
