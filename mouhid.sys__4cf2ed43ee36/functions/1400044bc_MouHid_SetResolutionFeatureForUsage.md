# MouHid_SetResolutionFeatureForUsage

- ea: `0x1400044bc`
- end: `0x140004799`
- name: `MouHid_SetResolutionFeatureForUsage`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400047a0`

## callees

- `0x140002a08`
- `0x1400044bc`
- `0x140004dd0`
- `0x1400051c0`
- `0x14000b5a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000471c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000471c`
- `ntoskrnl!ExAllocatePool2` at `0x1400045e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400045e0`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x140004553`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x1400045a8`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x140004553`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x1400045a8`
- `HIDPARSE!HidP_SetUsageValue` at `0x14000465f`
- `HIDPARSE!HidP_SetUsageValue` at `0x14000465f`

## pseudocode

```c
__int64 __fastcall MouHid_SetResolutionFeatureForUsage(_QWORD *a1, USAGE a2, USAGE a3, _DWORD *a4)
{
  int v8; // r8d
  __int64 v9; // r15
  __int64 *v10; // rdx
  struct _HIDP_PREPARSED_DATA *PreparsedData; // r12
  USHORT LinkCollection; // r14
  UCHAR *Pool2; // rax
  CHAR *v14; // rdi
  NTSTATUS v15; // ebx
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  ULONG i; // ecx
  USHORT ValueCapsLength[8]; // [rsp+40h] [rbp-59h] BYREF
  struct _HIDP_VALUE_CAPS ValueCaps; // [rsp+50h] [rbp-49h] BYREF

  ValueCapsLength[0] = 0;
  memset(&ValueCaps, 0, sizeof(ValueCaps));
  v9 = a1[27];
  v10 = WPP_bce545a1de1235e2be96703916423b99_Traceguids;
  PreparsedData = *(struct _HIDP_PREPARSED_DATA **)(v9 + 32);
  *a4 = 1;
  ValueCapsLength[0] = 1;
  if ( *(_WORD *)(v9 + 48) )
  {
    if ( HidP_GetSpecificValueCaps(HidP_Input, a2, 0, a3, &ValueCaps, ValueCapsLength, PreparsedData) >= 0
      && ValueCapsLength[0] == 1 )
    {
      LinkCollection = ValueCaps.LinkCollection;
      if ( ValueCaps.LinkCollection )
      {
        if ( HidP_GetSpecificValueCaps(
               HidP_Feature,
               1u,
               ValueCaps.LinkCollection,
               0x48u,
               &ValueCaps,
               ValueCapsLength,
               PreparsedData) >= 0
          && ValueCapsLength[0] == 1
          && ValueCaps.LogicalMax > ValueCaps.LogicalMin )
        {
          Pool2 = (UCHAR *)ExAllocatePool2(64, *(unsigned __int16 *)(v9 + 48), 1215655757);
          v14 = (CHAR *)Pool2;
          if ( !Pool2 )
          {
            v15 = -1073741670;
LABEL_10:
            v10 = WPP_bce545a1de1235e2be96703916423b99_Traceguids;
            goto LABEL_26;
          }
          *Pool2 = ValueCaps.ReportID;
          v15 = MouHid_CallHidClass(a1, 721298, 0, 0, Pool2, *(unsigned __int16 *)(v9 + 48));
          if ( v15 >= 0 )
          {
            v15 = HidP_SetUsageValue(
                    HidP_Feature,
                    1u,
                    LinkCollection,
                    0x48u,
                    ValueCaps.LogicalMax,
                    PreparsedData,
                    v14,
                    *(unsigned __int16 *)(v9 + 48));
            if ( v15 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_22;
              v18 = 10;
              goto LABEL_15;
            }
            v15 = MouHid_CallHidClass(a1, 721297, v14, *(unsigned __int16 *)(v9 + 48), 0, 0);
            if ( v15 >= 0 )
            {
              v19 = 1;
              for ( i = 0; i < ValueCaps.UnitsExp; v19 *= 10 )
                ++i;
              *a4 = ValueCaps.PhysicalMax * v19;
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v18 = 11;
LABEL_15:
              LOBYTE(v16) = 2;
              WPP_RECORDER_SF_qd(
                WPP_GLOBAL_Control->DeviceExtension,
                v16,
                v17,
                v18,
                (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids,
                *a1,
                v15);
            }
          }
LABEL_22:
          ExFreePoolWithTag(v14, 0);
          if ( v15 >= 0 )
            return (unsigned int)v15;
          goto LABEL_10;
        }
      }
    }
    v10 = WPP_bce545a1de1235e2be96703916423b99_Traceguids;
  }
  v15 = -1073741637;
LABEL_26:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      v8,
      12,
      (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids,
      *a1,
      v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400044bc  push    rbp
0x1400044be  push    rbx
0x1400044bf  push    rsi
0x1400044c0  push    rdi
0x1400044c1  push    r12
0x1400044c3  push    r13
0x1400044c5  push    r14
0x1400044c7  push    r15
0x1400044c9  lea     rbp, [rsp-1Fh]
0x1400044ce  sub     rsp, 0B8h
0x1400044d5  mov     rax, cs:__security_cookie
0x1400044dc  xor     rax, rsp
0x1400044df  mov     [rbp+57h+var_50], rax
0x1400044e3  xor     r14d, r14d
0x1400044e6  movzx   edi, r8w
0x1400044ea  movzx   ebx, dx
0x1400044ed  mov     [rbp+57h+var_B0], r14w
0x1400044f2  mov     rsi, rcx
0x1400044f5  xor     edx, edx; Val
0x1400044f7  lea     rcx, [rbp+57h+var_A0]; void *
0x1400044fb  mov     r13, r9
0x1400044fe  lea     r8d, [r14+48h]; Size
0x140004502  call    memset
0x140004507  mov     r15, [rsi+0D8h]
0x14000450e  lea     eax, [r14+1]
0x140004512  lea     rdx, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004519  mov     r12, [r15+20h]
0x14000451d  mov     [r13+0], eax
0x140004521  mov     [rbp+57h+var_B0], ax
0x140004525  cmp     r14w, [r15+30h]
0x14000452a  jz      loc_140004738
0x140004530  lea     rax, [rbp+57h+var_B0]
0x140004534  mov     [rsp+0F0h+PreparsedData], r12; PreparsedData
0x140004539  mov     [rsp+0F0h+ValueCapsLength], rax; ValueCapsLength
0x14000453e  xor     r8d, r8d; LinkCollection
0x140004541  lea     rax, [rbp+57h+var_A0]
0x140004545  movzx   r9d, di; Usage
0x140004549  movzx   edx, bx; UsagePage
0x14000454c  mov     [rsp+0F0h+ValueCaps], rax; ValueCaps
0x140004551  xor     ecx, ecx; ReportType
0x140004553  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000455a  nop     dword ptr [rax+rax+00h]
0x14000455f  test    eax, eax
0x140004561  js      loc_140004731
0x140004567  lea     edi, [r14+1]
0x14000456b  cmp     [rbp+57h+var_B0], di
0x14000456f  jnz     loc_140004731
0x140004575  movzx   r14d, [rbp+57h+var_A0.LinkCollection]
0x14000457a  test    r14w, r14w
0x14000457e  jz      loc_140004731
0x140004584  lea     rax, [rbp+57h+var_B0]
0x140004588  mov     [rsp+0F0h+PreparsedData], r12; PreparsedData
0x14000458d  mov     [rsp+0F0h+ValueCapsLength], rax; ValueCapsLength
0x140004592  lea     r9d, [rdi+47h]; Usage
0x140004596  lea     rax, [rbp+57h+var_A0]
0x14000459a  mov     edx, edi; UsagePage
0x14000459c  movzx   r8d, r14w; LinkCollection
0x1400045a0  mov     [rsp+0F0h+ValueCaps], rax; ValueCaps
0x1400045a5  lea     ecx, [rdi+1]; ReportType
0x1400045a8  call    cs:__imp_HidP_GetSpecificValueCaps
0x1400045af  nop     dword ptr [rax+rax+00h]
0x1400045b4  test    eax, eax
0x1400045b6  js      loc_140004731
0x1400045bc  cmp     [rbp+57h+var_B0], di
0x1400045c0  jnz     loc_140004731
0x1400045c6  mov     eax, [rbp+57h+var_A0.LogicalMin]
0x1400045c9  cmp     [rbp+57h+var_A0.LogicalMax], eax
0x1400045cc  jle     loc_140004731
0x1400045d2  movzx   edx, word ptr [r15+30h]
0x1400045d7  lea     ecx, [rdi+3Fh]
0x1400045da  mov     r8d, 48756F4Dh
0x1400045e0  call    cs:__imp_ExAllocatePool2
0x1400045e7  nop     dword ptr [rax+rax+00h]
0x1400045ec  mov     rdi, rax
0x1400045ef  test    rax, rax
0x1400045f2  jnz     short loc_140004605
0x1400045f4  mov     ebx, 0C000009Ah
0x1400045f9  lea     rdx, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004600  jmp     loc_14000473D
0x140004605  mov     al, [rbp+57h+var_A0.ReportID]
0x140004608  xor     r9d, r9d
0x14000460b  mov     [rdi], al
0x14000460d  xor     r8d, r8d
0x140004610  movzx   eax, word ptr [r15+30h]
0x140004615  mov     edx, 0B0192h
0x14000461a  mov     dword ptr [rsp+0F0h+ValueCapsLength], eax
0x14000461e  mov     rcx, rsi
0x140004621  mov     [rsp+0F0h+ValueCaps], rdi
0x140004626  call    MouHid_CallHidClass
0x14000462b  mov     ebx, eax
0x14000462d  test    eax, eax
0x14000462f  js      loc_140004717
0x140004635  movzx   eax, word ptr [r15+30h]
0x14000463a  mov     edx, 1; UsagePage
0x14000463f  mov     [rsp+0F0h+ReportLength], eax; ReportLength
0x140004643  movzx   r8d, r14w; LinkCollection
0x140004647  mov     eax, [rbp+57h+var_A0.LogicalMax]
0x14000464a  mov     [rsp+0F0h+PreparsedData], rdi; Report
0x14000464f  lea     r9d, [rdx+47h]; Usage
0x140004653  mov     [rsp+0F0h+ValueCapsLength], r12; PreparsedData
0x140004658  lea     ecx, [rdx+1]; ReportType
0x14000465b  mov     dword ptr [rsp+0F0h+ValueCaps], eax; UsageValue
0x14000465f  call    cs:__imp_HidP_SetUsageValue
0x140004666  nop     dword ptr [rax+rax+00h]
0x14000466b  xor     r14d, r14d
0x14000466e  mov     ebx, eax
0x140004670  test    eax, eax
0x140004672  jns     short loc_1400046B8
0x140004674  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000467b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004682  jz      loc_140004717
0x140004688  lea     r9d, [r14+0Ah]
0x14000468c  mov     rax, [rsi]
0x14000468f  mov     dl, 2
0x140004691  mov     rcx, cs:WPP_GLOBAL_Control
0x140004698  mov     dword ptr [rsp+0F0h+PreparsedData], ebx
0x14000469c  mov     [rsp+0F0h+ValueCapsLength], rax
0x1400046a1  lea     rax, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x1400046a8  mov     [rsp+0F0h+ValueCaps], rax
0x1400046ad  mov     rcx, [rcx+40h]
0x1400046b1  call    WPP_RECORDER_SF_qd
0x1400046b6  jmp     short loc_140004717
0x1400046b8  movzx   r9d, word ptr [r15+30h]
0x1400046bd  mov     r8, rdi
0x1400046c0  mov     dword ptr [rsp+0F0h+ValueCapsLength], r14d
0x1400046c5  mov     edx, 0B0191h
0x1400046ca  mov     rcx, rsi
0x1400046cd  mov     [rsp+0F0h+ValueCaps], r14
0x1400046d2  call    MouHid_CallHidClass
0x1400046d7  mov     ebx, eax
0x1400046d9  test    eax, eax
0x1400046db  jns     short loc_1400046F5
0x1400046dd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400046e4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400046eb  jz      short loc_140004717
0x1400046ed  mov     r9d, 0Bh
0x1400046f3  jmp     short loc_14000468C
0x1400046f5  mov     edx, [rbp+57h+var_A0.UnitsExp]
0x1400046f8  mov     eax, 1
0x1400046fd  mov     ecx, r14d
0x140004700  test    edx, edx
0x140004702  jz      short loc_14000470F
0x140004704  lea     eax, [rax+rax*4]
0x140004707  inc     ecx
0x140004709  add     eax, eax
0x14000470b  cmp     ecx, edx
0x14000470d  jb      short loc_140004704
0x14000470f  imul    eax, [rbp+57h+var_A0.PhysicalMax]
0x140004713  mov     [r13+0], eax
0x140004717  xor     edx, edx; Tag
0x140004719  mov     rcx, rdi; P
0x14000471c  call    cs:__imp_ExFreePoolWithTag
0x140004723  nop     dword ptr [rax+rax+00h]
0x140004728  test    ebx, ebx
0x14000472a  jns     short loc_140004776
0x14000472c  jmp     loc_1400045F9
0x140004731  lea     rdx, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004738  mov     ebx, 0C00000BBh
0x14000473d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004744  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000474b  jz      short loc_140004776
0x14000474d  mov     rcx, [rsi]
0x140004750  mov     r9d, 0Ch
0x140004756  mov     dword ptr [rsp+0F0h+PreparsedData], ebx
0x14000475a  mov     [rsp+0F0h+ValueCapsLength], rcx
0x14000475f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004766  mov     [rsp+0F0h+ValueCaps], rdx
0x14000476b  mov     dl, 2
0x14000476d  mov     rcx, [rcx+40h]
0x140004771  call    WPP_RECORDER_SF_qd
0x140004776  mov     eax, ebx
0x140004778  mov     rcx, [rbp+57h+var_50]
0x14000477c  xor     rcx, rsp; StackCookie
0x14000477f  call    __security_check_cookie
0x140004784  add     rsp, 0B8h
0x14000478b  pop     r15
0x14000478d  pop     r14
0x14000478f  pop     r13
0x140004791  pop     r12
0x140004793  pop     rdi
0x140004794  pop     rsi
0x140004795  pop     rbx
0x140004796  pop     rbp
0x140004797  retn
```
