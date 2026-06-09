# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800409ac`
- end: `0x180040acc`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180040760`

## callees

- `0x18003cfdc`
- `0x18003d8e0`
- `0x180040848`
- `0x1800409ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x389D6EB, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v15);
      v12 = v15;
    }
    WORD2(v14) = 3;
    LODWORD(v14) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18009CEC8,
      0x2AF34F8u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v14,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800409ac  mov     [rsp+arg_10], rbx
0x1800409b1  mov     [rsp+arg_18], rsi
0x1800409b6  mov     [rsp+arg_0], rcx
0x1800409bb  push    rdi
0x1800409bc  sub     rsp, 40h
0x1800409c0  mov     ecx, 389D6EBh; this
0x1800409c5  mov     rdi, rdx
0x1800409c8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800409cd  mov     edx, eax
0x1800409cf  mov     qword ptr [rdi], 0
0x1800409d6  and     edx, 0FFFFFF3Fh
0x1800409dc  mov     ecx, eax
0x1800409de  and     eax, 80h
0x1800409e3  mov     r8d, edx
0x1800409e6  and     r8d, 3
0x1800409ea  mov     esi, 40h ; '@'
0x1800409ef  shl     r8d, 2
0x1800409f3  and     ecx, esi
0x1800409f5  or      r8d, ecx
0x1800409f8  shl     r8d, 2
0x1800409fc  or      r8d, eax
0x1800409ff  shl     r8d, 3
0x180040a03  test    edx, edx
0x180040a05  jnz     short loc_180040A0D
0x180040a07  mov     ecx, esi
0x180040a09  mov     edx, esi
0x180040a0b  jmp     short loc_180040A17
0x180040a0d  xor     ecx, ecx
0x180040a0f  cmp     edx, 2
0x180040a12  cmovz   ecx, esi
0x180040a15  mov     edx, ecx
0x180040a17  mov     eax, r8d
0x180040a1a  mov     ebx, 1
0x180040a1f  or      eax, edx
0x180040a21  or      r8d, ecx
0x180040a24  mov     [rdi], eax
0x180040a26  bt      r8d, 0Ah
0x180040a2b  jnb     short loc_180040A36
0x180040a2d  cmp     r8d, 800h
0x180040a34  jnb     short loc_180040A3D
0x180040a36  xor     cl, cl
0x180040a38  test    sil, r8b
0x180040a3b  jz      short loc_180040AA5
0x180040a3d  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180040a44  mov     r8d, [rax]
0x180040a47  test    r8b, 4
0x180040a4b  jnz     short loc_180040A62
0x180040a4d  lea     rdx, [rsp+48h+arg_8]
0x180040a52  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180040a57  mov     rcx, [rax]
0x180040a5a  mov     [rsp+48h+arg_8], rcx
0x180040a5f  mov     r8d, ecx
0x180040a62  xor     eax, eax
0x180040a64  mov     word ptr [rsp+48h+arg_0+4], 3
0x180040a6b  mov     r9d, r8d
0x180040a6e  mov     [rsp+48h+var_18], eax
0x180040a72  mov     dword ptr [rsp+48h+arg_0], eax
0x180040a76  lea     rcx, qword_18009CEC8
0x180040a7d  shr     r9d, 0Bh
0x180040a81  lea     rax, [rsp+48h+arg_0]
0x180040a86  shr     r8d, 0Ah
0x180040a8a  and     r9d, ebx
0x180040a8d  and     r8d, ebx
0x180040a90  mov     [rsp+48h+var_20], ebx
0x180040a94  mov     edx, 2AF34F8h
0x180040a99  mov     [rsp+48h+var_28], rax
0x180040a9e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180040aa3  mov     cl, bl
0x180040aa5  mov     eax, [rdi]
0x180040aa7  test    sil, al
0x180040aaa  jz      short loc_180040AB0
0x180040aac  test    cl, cl
0x180040aae  jnz     short loc_180040AB2
0x180040ab0  xor     ebx, ebx
0x180040ab2  mov     rsi, [rsp+48h+arg_18]
0x180040ab7  and     eax, 0FFFFFFFEh
0x180040aba  or      eax, ebx
0x180040abc  mov     rbx, [rsp+48h+arg_10]
0x180040ac1  mov     [rdi], eax
0x180040ac3  mov     rax, rdi
0x180040ac6  add     rsp, 40h
0x180040aca  pop     rdi
0x180040acb  retn
```
