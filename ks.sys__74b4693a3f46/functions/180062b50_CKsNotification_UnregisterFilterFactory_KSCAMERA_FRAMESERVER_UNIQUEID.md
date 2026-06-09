# CKsNotification::UnregisterFilterFactory(_KSCAMERA_FRAMESERVER_UNIQUEID *)

- ea: `0x180062b50`
- end: `0x180062d9e`
- name: `?UnregisterFilterFactory@CKsNotification@@UEAAJPEAU_KSCAMERA_FRAMESERVER_UNIQUEID@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(CKsNotification *__hidden this, struct _KSCAMERA_FRAMESERVER_UNIQUEID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18000c630`
- `0x18000dddc`
- `0x180016e3c`
- `0x180062b50`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180062c9e`
- `ntoskrnl!KeReleaseMutex` at `0x180062c9e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180062c84`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180062c84`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062ba1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062ba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062c50`
- `HAL!KeQueryPerformanceCounter` at `0x180062c19`
- `HAL!KeQueryPerformanceCounter` at `0x180062c19`

## pseudocode

```c
__int64 __fastcall CKsNotification::UnregisterFilterFactory(
        CKsNotification *this,
        struct _KSCAMERA_FRAMESERVER_UNIQUEID *a2)
{
  struct _KSCAMERA_FRAMESERVER_UNIQUEID *v2; // rdi
  char *v4; // rdx
  unsigned int updated; // esi
  char *i; // rbx
  __int64 v7; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  char *v10; // rcx
  char **v11; // rax
  int v12; // edx
  __int64 v14; // [rsp+28h] [rbp-40h]
  char v15; // [rsp+28h] [rbp-40h]
  LARGE_INTEGER v16; // [rsp+70h] [rbp+8h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v15 = (char)a2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      27,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      v15);
  }
  KeWaitForSingleObject((char *)this + 176, Executive, 0, 0, 0);
  if ( v2 )
  {
    v4 = (char *)this + 232;
    updated = 0;
    for ( i = (char *)*((_QWORD *)this + 29); i && i != v4 && *((_DWORD *)this + 62); i = *(char **)i )
    {
      if ( *((_QWORD *)i + 2) == v2->FilterFactory && *((_QWORD *)i + 3) == v2->QPCOnCreation )
      {
        v7 = *((_QWORD *)i + 4) - *(_QWORD *)&v2->KSCategory.Data1;
        if ( !v7 )
          v7 = *((_QWORD *)i + 5) - *(_QWORD *)v2->KSCategory.Data4;
        if ( !v7 )
        {
          if ( (*((_DWORD *)i + 12))-- == 1 )
          {
            PerformanceCounter = KeQueryPerformanceCounter(0);
            v10 = *(char **)i;
            v16 = PerformanceCounter;
            if ( *((char **)v10 + 1) != i || (v11 = (char **)*((_QWORD *)i + 1), *v11 != i) )
              __fastfail(3u);
            *v11 = v10;
            *((_QWORD *)v10 + 1) = v11;
            ExFreePoolWithTag(i, 0);
            --*((_DWORD *)this + 62);
            updated = ZwUpdateWnfStateData(&WNF_KSV_DEVICESTATE, &v16, 8, 0, 0, 0, 0);
          }
          goto LABEL_17;
        }
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_iiD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v4,
        1,
        28,
        (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
        v2->FilterFactory,
        v2->QPCOnCreation,
        v2->KSCategory.Data1);
    }
  }
  else
  {
    updated = -1073741811;
  }
LABEL_17:
  KeReleaseMutex((PRKMUTEX)((char *)this + 176), 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v14) = updated;
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      29,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      v14);
  }
  return updated;
}

```

## disassembly

```asm
0x180062b50  mov     [rsp+arg_8], rbx
0x180062b55  mov     [rsp+arg_10], rbp
0x180062b5a  push    rsi
0x180062b5b  push    rdi
0x180062b5c  push    r12
0x180062b5e  push    r14
0x180062b60  push    r15
0x180062b62  sub     rsp, 40h
0x180062b66  mov     rdi, rdx
0x180062b69  mov     rbp, rcx
0x180062b6c  lea     r12, WPP_RECORDER_INITIALIZED
0x180062b73  xor     r15d, r15d
0x180062b76  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062b7d  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062b84  jnz     loc_180062CE1
0x180062b8a  lea     r14, [rbp+0B0h]
0x180062b91  mov     [rsp+68h+Timeout], r15; Timeout
0x180062b96  mov     rcx, r14; Object
0x180062b99  xor     r9d, r9d; Alertable
0x180062b9c  xor     r8d, r8d; WaitMode
0x180062b9f  xor     edx, edx; WaitReason
0x180062ba1  call    cs:__imp_KeWaitForSingleObject
0x180062ba8  nop     dword ptr [rax+rax+00h]
0x180062bad  test    rdi, rdi
0x180062bb0  jz      loc_180062CD3
0x180062bb6  lea     rdx, [rbp+0E8h]
0x180062bbd  mov     esi, r15d
0x180062bc0  mov     rbx, [rdx]
0x180062bc3  test    rbx, rbx
0x180062bc6  jz      loc_180062D17
0x180062bcc  cmp     rbx, rdx
0x180062bcf  jz      loc_180062D17
0x180062bd5  cmp     [rbp+0F8h], r15d
0x180062bdc  jbe     loc_180062D17
0x180062be2  mov     rax, [rdi]
0x180062be5  cmp     [rbx+10h], rax
0x180062be9  jz      short loc_180062BF0
0x180062beb  mov     rbx, [rbx]
0x180062bee  jmp     short loc_180062BC3
0x180062bf0  mov     rax, [rdi+8]
0x180062bf4  cmp     [rbx+18h], rax
0x180062bf8  jnz     short loc_180062BEB
0x180062bfa  mov     rcx, [rbx+20h]
0x180062bfe  sub     rcx, [rdi+10h]
0x180062c02  jnz     short loc_180062C0C
0x180062c04  mov     rcx, [rbx+28h]
0x180062c08  sub     rcx, [rdi+18h]; PerformanceFrequency
0x180062c0c  test    rcx, rcx
0x180062c0f  jnz     short loc_180062BEB
0x180062c11  or      edi, 0FFFFFFFFh
0x180062c14  add     [rbx+30h], edi
0x180062c17  jnz     short loc_180062C92
0x180062c19  call    cs:__imp_KeQueryPerformanceCounter
0x180062c20  nop     dword ptr [rax+rax+00h]
0x180062c25  mov     rcx, [rbx]
0x180062c28  mov     [rsp+68h+arg_0], rax
0x180062c2d  cmp     [rcx+8], rbx
0x180062c31  jnz     loc_180062CDA
0x180062c37  mov     rax, [rbx+8]
0x180062c3b  cmp     [rax], rbx
0x180062c3e  jnz     loc_180062CDA
0x180062c44  mov     [rax], rcx
0x180062c47  xor     edx, edx; Tag
0x180062c49  mov     [rcx+8], rax
0x180062c4d  mov     rcx, rbx; P
0x180062c50  call    cs:__imp_ExFreePoolWithTag
0x180062c57  nop     dword ptr [rax+rax+00h]
0x180062c5c  add     [rbp+0F8h], edi
0x180062c62  lea     rdx, [rsp+68h+arg_0]
0x180062c67  xor     r9d, r9d
0x180062c6a  mov     dword ptr [rsp+68h+var_38], r15d
0x180062c6f  mov     dword ptr [rsp+68h+var_40], r15d
0x180062c74  lea     rcx, WNF_KSV_DEVICESTATE
0x180062c7b  mov     [rsp+68h+Timeout], r15
0x180062c80  lea     r8d, [r9+8]
0x180062c84  call    cs:__imp_ZwUpdateWnfStateData
0x180062c8b  nop     dword ptr [rax+rax+00h]
0x180062c90  mov     esi, eax
0x180062c92  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062c99  xor     edx, edx; Wait
0x180062c9b  mov     rcx, r14; Mutex
0x180062c9e  call    cs:__imp_KeReleaseMutex
0x180062ca5  nop     dword ptr [rax+rax+00h]
0x180062caa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062cb1  jnz     loc_180062D69
0x180062cb7  lea     r11, [rsp+68h+var_28]
0x180062cbc  mov     eax, esi
0x180062cbe  mov     rbx, [r11+38h]
0x180062cc2  mov     rbp, [r11+40h]
0x180062cc6  mov     rsp, r11
0x180062cc9  pop     r15
0x180062ccb  pop     r14
0x180062ccd  pop     r12
0x180062ccf  pop     rdi
0x180062cd0  pop     rsi
0x180062cd1  retn
0x180062cd3  mov     esi, 0C000000Dh
0x180062cd8  jmp     short loc_180062C99
0x180062cda  mov     ecx, 3
0x180062cdf  int     29h; Win8: RtlFailFast(ecx)
0x180062ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ce8  cmp     [rcx+48h], r15w
0x180062ced  jz      loc_180062B8A
0x180062cf3  mov     rcx, [rcx+40h]
0x180062cf7  mov     r9d, 1Bh
0x180062cfd  mov     [rsp+68h+var_40], rdi
0x180062d02  mov     dl, 5
0x180062d04  mov     [rsp+68h+Timeout], rbx
0x180062d09  lea     r8d, [r9-1Ah]
0x180062d0d  call    WPP_RECORDER_SF_q
0x180062d12  jmp     loc_180062B8A
0x180062d17  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180062d1e  jz      loc_180062C92
0x180062d24  mov     eax, [rdi+10h]
0x180062d27  lea     rbx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180062d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d35  mov     r9d, 1Ch
0x180062d3b  mov     [rsp+68h+var_30], eax
0x180062d3f  mov     dl, 2
0x180062d41  mov     rax, [rdi+8]
0x180062d45  mov     [rsp+68h+var_38], rax
0x180062d4a  mov     rax, [rdi]
0x180062d4d  lea     r8d, [r9-1Bh]
0x180062d51  mov     rcx, [rcx+40h]
0x180062d55  mov     [rsp+68h+var_40], rax
0x180062d5a  mov     [rsp+68h+Timeout], rbx
0x180062d5f  call    WPP_RECORDER_SF_iiD
0x180062d64  jmp     loc_180062C99
0x180062d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d70  cmp     [rcx+48h], r15w
0x180062d75  jz      loc_180062CB7
0x180062d7b  mov     rcx, [rcx+40h]
0x180062d7f  mov     r9d, 1Dh
0x180062d85  mov     dword ptr [rsp+68h+var_40], esi
0x180062d89  mov     dl, 5
0x180062d8b  mov     [rsp+68h+Timeout], rbx
0x180062d90  lea     r8d, [r9-1Ch]
0x180062d94  call    WPP_RECORDER_SF_D
0x180062d99  jmp     loc_180062CB7
```
