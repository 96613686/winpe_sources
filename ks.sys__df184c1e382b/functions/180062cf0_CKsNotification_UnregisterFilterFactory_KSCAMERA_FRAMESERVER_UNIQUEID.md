# CKsNotification::UnregisterFilterFactory(_KSCAMERA_FRAMESERVER_UNIQUEID *)

- ea: `0x180062cf0`
- end: `0x180062f3e`
- name: `?UnregisterFilterFactory@CKsNotification@@UEAAJPEAU_KSCAMERA_FRAMESERVER_UNIQUEID@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(CKsNotification *__hidden this, struct _KSCAMERA_FRAMESERVER_UNIQUEID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18000c630`
- `0x18000dddc`
- `0x180016e8c`
- `0x180062cf0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180062e3e`
- `ntoskrnl!KeReleaseMutex` at `0x180062e3e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180062e24`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180062e24`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062d41`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062d41`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062df0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062df0`
- `HAL!KeQueryPerformanceCounter` at `0x180062db9`
- `HAL!KeQueryPerformanceCounter` at `0x180062db9`

## pseudocode

```c
__int64 __fastcall CKsNotification::UnregisterFilterFactory(
        CKsNotification *this,
        struct _KSCAMERA_FRAMESERVER_UNIQUEID *a2)
{
  struct _KSCAMERA_FRAMESERVER_UNIQUEID *v2; // rdi
  unsigned int updated; // esi
  _QWORD *i; // rbx
  __int64 v6; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  int v11; // edx
  __int64 v13; // [rsp+28h] [rbp-40h]
  char v14; // [rsp+28h] [rbp-40h]
  LARGE_INTEGER v15; // [rsp+70h] [rbp+8h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v14 = (char)a2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      27,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      v14);
  }
  KeWaitForSingleObject((char *)this + 176, Executive, 0, 0, 0);
  if ( v2 )
  {
    updated = 0;
    for ( i = (_QWORD *)*((_QWORD *)this + 29);
          i && i != (_QWORD *)((char *)this + 232) && *((_DWORD *)this + 62);
          i = (_QWORD *)*i )
    {
      if ( i[2] == v2->FilterFactory && i[3] == v2->QPCOnCreation )
      {
        v6 = i[4] - *(_QWORD *)&v2->KSCategory.Data1;
        if ( !v6 )
          v6 = i[5] - *(_QWORD *)v2->KSCategory.Data4;
        if ( !v6 )
        {
          if ( (*((_DWORD *)i + 12))-- == 1 )
          {
            PerformanceCounter = KeQueryPerformanceCounter(0);
            v9 = (_QWORD *)*i;
            v15 = PerformanceCounter;
            if ( (_QWORD *)v9[1] != i || (v10 = (_QWORD *)i[1], (_QWORD *)*v10 != i) )
              __fastfail(3u);
            *v10 = v9;
            v9[1] = v10;
            ExFreePoolWithTag(i, 0);
            --*((_DWORD *)this + 62);
            updated = ZwUpdateWnfStateData(&WNF_KSV_DEVICESTATE, &v15, 8);
          }
          goto LABEL_17;
        }
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_iiD(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        1u,
        0x1Cu,
        (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
        v2->FilterFactory,
        v2->QPCOnCreation,
        v2->KSCategory.Data1);
  }
  else
  {
    updated = -1073741811;
  }
LABEL_17:
  KeReleaseMutex((PRKMUTEX)((char *)this + 176), 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v13) = updated;
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      29,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      v13);
  }
  return updated;
}

```

## disassembly

```asm
0x180062cf0  mov     [rsp+arg_8], rbx
0x180062cf5  mov     [rsp+arg_10], rbp
0x180062cfa  push    rsi
0x180062cfb  push    rdi
0x180062cfc  push    r12
0x180062cfe  push    r14
0x180062d00  push    r15
0x180062d02  sub     rsp, 40h
0x180062d06  mov     rdi, rdx
0x180062d09  mov     rbp, rcx
0x180062d0c  lea     r12, WPP_RECORDER_INITIALIZED
0x180062d13  xor     r15d, r15d
0x180062d16  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062d1d  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062d24  jnz     loc_180062E81
0x180062d2a  lea     r14, [rbp+0B0h]
0x180062d31  mov     [rsp+68h+Timeout], r15; Timeout
0x180062d36  mov     rcx, r14; Object
0x180062d39  xor     r9d, r9d; Alertable
0x180062d3c  xor     r8d, r8d; WaitMode
0x180062d3f  xor     edx, edx; WaitReason
0x180062d41  call    cs:__imp_KeWaitForSingleObject
0x180062d48  nop     dword ptr [rax+rax+00h]
0x180062d4d  test    rdi, rdi
0x180062d50  jz      loc_180062E73
0x180062d56  lea     rdx, [rbp+0E8h]
0x180062d5d  mov     esi, r15d
0x180062d60  mov     rbx, [rdx]
0x180062d63  test    rbx, rbx
0x180062d66  jz      loc_180062EB7
0x180062d6c  cmp     rbx, rdx
0x180062d6f  jz      loc_180062EB7
0x180062d75  cmp     [rbp+0F8h], r15d
0x180062d7c  jbe     loc_180062EB7
0x180062d82  mov     rax, [rdi]
0x180062d85  cmp     [rbx+10h], rax
0x180062d89  jz      short loc_180062D90
0x180062d8b  mov     rbx, [rbx]
0x180062d8e  jmp     short loc_180062D63
0x180062d90  mov     rax, [rdi+8]
0x180062d94  cmp     [rbx+18h], rax
0x180062d98  jnz     short loc_180062D8B
0x180062d9a  mov     rcx, [rbx+20h]
0x180062d9e  sub     rcx, [rdi+10h]
0x180062da2  jnz     short loc_180062DAC
0x180062da4  mov     rcx, [rbx+28h]
0x180062da8  sub     rcx, [rdi+18h]; PerformanceFrequency
0x180062dac  test    rcx, rcx
0x180062daf  jnz     short loc_180062D8B
0x180062db1  or      edi, 0FFFFFFFFh
0x180062db4  add     [rbx+30h], edi
0x180062db7  jnz     short loc_180062E32
0x180062db9  call    cs:__imp_KeQueryPerformanceCounter
0x180062dc0  nop     dword ptr [rax+rax+00h]
0x180062dc5  mov     rcx, [rbx]
0x180062dc8  mov     [rsp+68h+arg_0], rax
0x180062dcd  cmp     [rcx+8], rbx
0x180062dd1  jnz     loc_180062E7A
0x180062dd7  mov     rax, [rbx+8]
0x180062ddb  cmp     [rax], rbx
0x180062dde  jnz     loc_180062E7A
0x180062de4  mov     [rax], rcx
0x180062de7  xor     edx, edx; Tag
0x180062de9  mov     [rcx+8], rax
0x180062ded  mov     rcx, rbx; P
0x180062df0  call    cs:__imp_ExFreePoolWithTag
0x180062df7  nop     dword ptr [rax+rax+00h]
0x180062dfc  add     [rbp+0F8h], edi
0x180062e02  lea     rdx, [rsp+68h+arg_0]
0x180062e07  xor     r9d, r9d
0x180062e0a  mov     dword ptr [rsp+68h+var_38], r15d
0x180062e0f  mov     dword ptr [rsp+68h+var_40], r15d
0x180062e14  lea     rcx, WNF_KSV_DEVICESTATE
0x180062e1b  mov     [rsp+68h+Timeout], r15
0x180062e20  lea     r8d, [r9+8]
0x180062e24  call    cs:__imp_ZwUpdateWnfStateData
0x180062e2b  nop     dword ptr [rax+rax+00h]
0x180062e30  mov     esi, eax
0x180062e32  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062e39  xor     edx, edx; Wait
0x180062e3b  mov     rcx, r14; Mutex
0x180062e3e  call    cs:__imp_KeReleaseMutex
0x180062e45  nop     dword ptr [rax+rax+00h]
0x180062e4a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062e51  jnz     loc_180062F09
0x180062e57  lea     r11, [rsp+68h+var_28]
0x180062e5c  mov     eax, esi
0x180062e5e  mov     rbx, [r11+38h]
0x180062e62  mov     rbp, [r11+40h]
0x180062e66  mov     rsp, r11
0x180062e69  pop     r15
0x180062e6b  pop     r14
0x180062e6d  pop     r12
0x180062e6f  pop     rdi
0x180062e70  pop     rsi
0x180062e71  retn
0x180062e73  mov     esi, 0C000000Dh
0x180062e78  jmp     short loc_180062E39
0x180062e7a  mov     ecx, 3
0x180062e7f  int     29h; Win8: RtlFailFast(ecx)
0x180062e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e88  cmp     [rcx+48h], r15w
0x180062e8d  jz      loc_180062D2A
0x180062e93  mov     rcx, [rcx+40h]
0x180062e97  mov     r9d, 1Bh
0x180062e9d  mov     [rsp+68h+var_40], rdi
0x180062ea2  mov     dl, 5
0x180062ea4  mov     [rsp+68h+Timeout], rbx
0x180062ea9  lea     r8d, [r9-1Ah]
0x180062ead  call    WPP_RECORDER_SF_q
0x180062eb2  jmp     loc_180062D2A
0x180062eb7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062ebe  jz      loc_180062E32
0x180062ec4  mov     eax, [rdi+10h]
0x180062ec7  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ed5  mov     r9d, 1Ch
0x180062edb  mov     [rsp+68h+var_30], eax
0x180062edf  mov     dl, 2
0x180062ee1  mov     rax, [rdi+8]
0x180062ee5  mov     [rsp+68h+var_38], rax
0x180062eea  mov     rax, [rdi]
0x180062eed  lea     r8d, [r9-1Bh]
0x180062ef1  mov     rcx, [rcx+40h]
0x180062ef5  mov     [rsp+68h+var_40], rax
0x180062efa  mov     [rsp+68h+Timeout], rbx
0x180062eff  call    WPP_RECORDER_SF_iiD
0x180062f04  jmp     loc_180062E39
0x180062f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f10  cmp     [rcx+48h], r15w
0x180062f15  jz      loc_180062E57
0x180062f1b  mov     rcx, [rcx+40h]
0x180062f1f  mov     r9d, 1Dh
0x180062f25  mov     dword ptr [rsp+68h+var_40], esi
0x180062f29  mov     dl, 5
0x180062f2b  mov     [rsp+68h+Timeout], rbx
0x180062f30  lea     r8d, [r9-1Ch]
0x180062f34  call    WPP_RECORDER_SF_D
0x180062f39  jmp     loc_180062E57
```
