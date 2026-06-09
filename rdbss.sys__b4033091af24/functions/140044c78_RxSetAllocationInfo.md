# RxSetAllocationInfo

- ea: `0x140044c78`
- end: `0x140045021`
- name: `RxSetAllocationInfo`
- size: `937`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14006f9e0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140011680`
- `0x140016e20`
- `0x1400194cc`
- `0x140019530`
- `0x140044c78`
- `0x14006d6e0`
- `0x140071c90`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x140044fdd`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14007ba59`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140044fdd`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14007ba59`
- `ntoskrnl!CcSetFileSizes` at `0x140044f28`
- `ntoskrnl!CcSetFileSizes` at `0x140044f28`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140044de9`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140044de9`
- `ntoskrnl!CcInitializeCacheMap` at `0x140044d98`
- `ntoskrnl!CcInitializeCacheMap` at `0x140044d98`

## pseudocode

```c
__int64 __fastcall RxSetAllocationInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 LazyWriteContext; // rdi
  struct _FILE_OBJECT *v5; // r13
  LONGLONG QuadPart; // r15
  _QWORD *p_DataSectionObject; // rax
  struct _CC_FILE_SIZES *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  LONGLONG *v12; // r12
  LONGLONG v13; // rbx
  PLARGE_INTEGER Timer_high; // rdx
  unsigned int v15; // esi
  LARGE_INTEGER *v16; // r12
  int v17; // eax
  char v18; // r12
  char v19; // [rsp+30h] [rbp-68h]
  PLARGE_INTEGER NewFileSize[11]; // [rsp+40h] [rbp-58h] BYREF
  char v22; // [rsp+B8h] [rbp+20h]

  LazyWriteContext = a3;
  v5 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 184) + 48LL);
  NewFileSize[2] = (PLARGE_INTEGER)v5;
  v22 = 0;
  NewFileSize[0] = *(PLARGE_INTEGER *)(a2 + 24);
  QuadPart = NewFileSize[0]->QuadPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      45,
      WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
      (unsigned int)QuadPart);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_LLL(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      *(unsigned int *)(LazyWriteContext + 32),
      QuadPart,
      *(_DWORD *)(LazyWriteContext + 24));
  }
  p_DataSectionObject = &v5->SectionObjectPointer->DataSectionObject;
  if ( *p_DataSectionObject && !p_DataSectionObject[1] && *(_BYTE *)(a2 + 64) )
  {
    if ( (v5->Flags & 0x4000) != 0 )
      return 3221225768LL;
    v9 = (struct _CC_FILE_SIZES *)(LazyWriteContext + 24);
    v10 = *(_QWORD *)(LazyWriteContext + 32);
    if ( v10 > *(_QWORD *)(LazyWriteContext + 24) )
    {
      v11 = *(unsigned int *)(*(_QWORD *)(LazyWriteContext + 120) + 104LL);
      v9->AllocationSize.QuadPart = -v11 & (v11 + v10);
    }
    CcInitializeCacheMap(v5, v9, 0, &Callbacks, (PVOID)LazyWriteContext);
    v22 = 1;
  }
  NewFileSize[3] = (PLARGE_INTEGER)v5;
  v5->Flags |= 0x1000u;
  v12 = (LONGLONG *)(LazyWriteContext + 32);
  v13 = *(_QWORD *)(LazyWriteContext + 32);
  Timer_high = NewFileSize[0];
  if ( v13 <= *(_QWORD *)NewFileSize[0] )
    goto LABEL_25;
  if ( !*(_DWORD *)(LazyWriteContext + 484) )
  {
    if ( !MmCanFileBeTruncated(v5->SectionObjectPointer, NewFileSize[0]) )
    {
      v15 = -1073741245;
      goto LABEL_46;
    }
    LOBYTE(a3) = 1;
    RxAcquirePagingIoResource(a1, LazyWriteContext, a3);
    *v12 = QuadPart;
    if ( *(_QWORD *)(LazyWriteContext + 40) > QuadPart )
      *(_QWORD *)(LazyWriteContext + 40) = QuadPart;
    RxReleasePagingIoResource(a1, LazyWriteContext);
LABEL_25:
    v16 = *(LARGE_INTEGER **)(LazyWriteContext + 24);
    NewFileSize[1] = v16;
    *(_QWORD *)(LazyWriteContext + 24) = QuadPart;
    v17 = RxpSetInfoMiniRdr(a1, a2, a3, 19);
    v15 = v17;
    if ( v17 >= 0 )
    {
      if ( v16 == (LARGE_INTEGER *)QuadPart )
      {
        v12 = (LONGLONG *)(LazyWriteContext + 32);
      }
      else
      {
        v18 = 0;
        v19 = 0;
        NewFileSize[0] = (PLARGE_INTEGER)QuadPart;
        if ( *(_QWORD *)(LazyWriteContext + 488)
          && (*(_DWORD *)(LazyWriteContext + 496) & 2) != 0
          && ((*(_DWORD *)(LazyWriteContext + 164) & 2) == 0
           || (*(_DWORD *)(LazyWriteContext + 160) & 0x8000000) == 0
           || (*(_DWORD *)(LazyWriteContext + 500) & 0x100) != 0)
          && QuadPart < v13
          && (QuadPart & 0xFFF) != 0 )
        {
          LOBYTE(Timer_high) = 1;
          RxFlushFcbInSystemCacheEx(LazyWriteContext, Timer_high, NewFileSize);
          v18 = 1;
          v19 = 1;
        }
        CcSetFileSizes(v5, (PCC_FILE_SIZES)(LazyWriteContext + 24));
        if ( !*(_QWORD *)(LazyWriteContext + 488) || (*(_DWORD *)(LazyWriteContext + 496) & 2) == 0 || v18 )
        {
          NewFileSize[0] = (PLARGE_INTEGER)QuadPart;
          RxPurgeFcbInSystemCache((PFCB)LazyWriteContext, (PLARGE_INTEGER)NewFileSize, 0, 0, 0);
        }
        v12 = (LONGLONG *)(LazyWriteContext + 32);
      }
    }
    else
    {
      *(_QWORD *)(LazyWriteContext + 24) = v16;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = (PLARGE_INTEGER)HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( ((unsigned __int8)Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            47,
            WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
            (unsigned int)v17);
      }
      v12 = (LONGLONG *)(LazyWriteContext + 32);
    }
    goto LABEL_46;
  }
  v15 = -1073740747;
LABEL_46:
  if ( v22 )
    CcUninitializeCacheMap(v5, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_LLD(
      WPP_GLOBAL_Control->AttachedDevice,
      Timer_high,
      a3,
      *(unsigned int *)v12,
      *(_DWORD *)(LazyWriteContext + 24),
      v15,
      v19);
  }
  return v15;
}

```

## disassembly

```asm
0x140044c78  mov     rax, rsp
0x140044c7b  mov     [rax+20h], r9
0x140044c7f  mov     [rax+18h], r8
0x140044c83  mov     [rax+10h], rdx
0x140044c87  mov     [rax+8], rcx
0x140044c8b  push    rbx
0x140044c8c  push    rsi
0x140044c8d  push    rdi
0x140044c8e  push    r12
0x140044c90  push    r13
0x140044c92  push    r14
0x140044c94  push    r15
0x140044c96  sub     rsp, 60h
0x140044c9a  mov     rdi, r8
0x140044c9d  mov     rsi, rdx
0x140044ca0  mov     rax, [rdx+0B8h]
0x140044ca7  mov     r13, [rax+30h]
0x140044cab  mov     [rsp+98h+var_48], r13
0x140044cb0  xor     r14d, r14d
0x140044cb3  mov     [rsp+98h+arg_18], r14b
0x140044cbb  mov     rax, [rdx+18h]
0x140044cbf  mov     [rsp+98h+NewFileSize], rax
0x140044cc4  mov     r15, [rax]
0x140044cc7  lea     rbx, WPP_GLOBAL_Control
0x140044cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140044cd5  cmp     rcx, rbx
0x140044cd8  jz      short loc_140044CFE
0x140044cda  mov     eax, [rcx+2Ch]
0x140044cdd  test    al, 20h
0x140044cdf  jz      short loc_140044CFE
0x140044ce1  cmp     byte ptr [rcx+29h], 4
0x140044ce5  jb      short loc_140044CFE
0x140044ce7  mov     r9d, r15d
0x140044cea  lea     edx, [r14+2Dh]
0x140044cee  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x140044cf5  mov     rcx, [rcx+18h]
0x140044cf9  call    WPP_SF_d
0x140044cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d05  cmp     rcx, rbx
0x140044d08  jz      short loc_140044D30
0x140044d0a  mov     eax, [rcx+2Ch]
0x140044d0d  test    al, 20h
0x140044d0f  jz      short loc_140044D30
0x140044d11  cmp     byte ptr [rcx+29h], 2
0x140044d15  jb      short loc_140044D30
0x140044d17  mov     eax, [rdi+18h]
0x140044d1a  mov     [rsp+98h+var_70], eax
0x140044d1e  mov     dword ptr [rsp+98h+LazyWriteContext], r15d
0x140044d23  mov     r9d, [rdi+20h]
0x140044d27  mov     rcx, [rcx+18h]
0x140044d2b  call    WPP_SF_LLL
0x140044d30  mov     rax, [r13+28h]
0x140044d34  cmp     [rax], r14
0x140044d37  jz      short loc_140044DAC
0x140044d39  cmp     [rax+8], r14
0x140044d3d  jnz     short loc_140044DAC
0x140044d3f  cmp     [rsi+40h], r14b
0x140044d43  jz      short loc_140044DAC
0x140044d45  mov     eax, [r13+50h]
0x140044d49  bt      eax, 0Eh
0x140044d4d  jnb     short loc_140044D65
0x140044d4f  mov     eax, 0C0000128h
0x140044d54  add     rsp, 60h
0x140044d58  pop     r15
0x140044d5a  pop     r14
0x140044d5c  pop     r13
0x140044d5e  pop     r12
0x140044d60  pop     rdi
0x140044d61  pop     rsi
0x140044d62  pop     rbx
0x140044d63  retn
0x140044d65  lea     rdx, [rdi+18h]; FileSizes
0x140044d69  mov     r8, [rdi+20h]
0x140044d6d  cmp     r8, [rdx]
0x140044d70  jle     short loc_140044D86
0x140044d72  mov     rax, [rdi+78h]
0x140044d76  mov     ecx, [rax+68h]
0x140044d79  lea     rax, [rcx+r8]
0x140044d7d  neg     rcx
0x140044d80  and     rax, rcx
0x140044d83  mov     [rdx], rax
0x140044d86  mov     [rsp+98h+LazyWriteContext], rdi; LazyWriteContext
0x140044d8b  lea     r9, Callbacks; Callbacks
0x140044d92  xor     r8d, r8d; PinAccess
0x140044d95  mov     rcx, r13; FileObject
0x140044d98  call    cs:__imp_CcInitializeCacheMap
0x140044d9f  nop     dword ptr [rax+rax+00h]
0x140044da4  mov     [rsp+98h+arg_18], 1
0x140044dac  mov     [rsp+98h+var_40], r13
0x140044db1  bts     dword ptr [r13+50h], 0Ch
0x140044db7  lea     r12, [rdi+20h]
0x140044dbb  mov     [rsp+98h+var_60], r12
0x140044dc0  mov     rbx, [r12]
0x140044dc4  mov     rdx, [rsp+98h+NewFileSize]; NewFileSize
0x140044dc9  cmp     rbx, [rdx]
0x140044dcc  jle     short loc_140044E31
0x140044dce  cmp     [rdi+1E4h], r14d
0x140044dd5  jbe     short loc_140044DE5
0x140044dd7  mov     esi, 0C0000435h
0x140044ddc  mov     [rsp+98h+var_64], esi
0x140044de0  jmp     loc_140044FC4
0x140044de5  mov     rcx, [r13+28h]; SectionPointer
0x140044de9  call    cs:__imp_MmCanFileBeTruncated
0x140044df0  nop     dword ptr [rax+rax+00h]
0x140044df5  test    al, al
0x140044df7  jnz     short loc_140044E00
0x140044df9  mov     esi, 0C0000243h
0x140044dfe  jmp     short loc_140044DDC
0x140044e00  mov     r8b, 1
0x140044e03  mov     rdx, rdi
0x140044e06  mov     rcx, [rsp+98h+arg_0]
0x140044e0e  call    RxAcquirePagingIoResource
0x140044e13  mov     [r12], r15
0x140044e17  cmp     [rdi+28h], r15
0x140044e1b  jle     short loc_140044E21
0x140044e1d  mov     [rdi+28h], r15
0x140044e21  mov     rdx, rdi
0x140044e24  mov     rcx, [rsp+98h+arg_0]
0x140044e2c  call    RxReleasePagingIoResource
0x140044e31  mov     r12, [rdi+18h]
0x140044e35  mov     [rsp+98h+var_50], r12
0x140044e3a  mov     [rdi+18h], r15
0x140044e3e  mov     r9d, 13h
0x140044e44  mov     rdx, rsi
0x140044e47  mov     rcx, [rsp+98h+arg_0]
0x140044e4f  call    RxpSetInfoMiniRdr
0x140044e54  mov     esi, eax
0x140044e56  mov     [rsp+98h+var_64], eax
0x140044e5a  test    eax, eax
0x140044e5c  jns     short loc_140044EA5
0x140044e5e  mov     [rdi+18h], r12
0x140044e62  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e69  lea     rbx, WPP_GLOBAL_Control
0x140044e70  cmp     rcx, rbx
0x140044e73  jz      short loc_140044E9B
0x140044e75  mov     edx, [rcx+2Ch]
0x140044e78  test    dl, 20h
0x140044e7b  jz      short loc_140044E9B
0x140044e7d  cmp     byte ptr [rcx+29h], 4
0x140044e81  jb      short loc_140044E9B
0x140044e83  mov     edx, 2Fh ; '/'
0x140044e88  mov     r9d, eax
0x140044e8b  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x140044e92  mov     rcx, [rcx+18h]
0x140044e96  call    WPP_SF_d
0x140044e9b  mov     r12, [rsp+98h+var_60]
0x140044ea0  jmp     loc_140044FCB
0x140044ea5  cmp     r12, r15
0x140044ea8  jz      loc_140044FBF
0x140044eae  mov     [rsp+98h+NewFileSize], r14
0x140044eb3  mov     r12b, r14b
0x140044eb6  mov     [rsp+98h+var_68], r14b
0x140044ebb  mov     [rsp+98h+NewFileSize], r15
0x140044ec0  cmp     [rdi+1E8h], r14
0x140044ec7  jz      short loc_140044F21
0x140044ec9  mov     eax, [rdi+1F0h]
0x140044ecf  test    al, 2
0x140044ed1  jz      short loc_140044F21
0x140044ed3  mov     eax, [rdi+0A4h]
0x140044ed9  test    al, 2
0x140044edb  jz      short loc_140044EF5
0x140044edd  mov     eax, [rdi+0A0h]
0x140044ee3  bt      eax, 1Bh
0x140044ee7  jnb     short loc_140044EF5
0x140044ee9  mov     eax, [rdi+1F4h]
0x140044eef  bt      eax, 8
0x140044ef3  jnb     short loc_140044F21
0x140044ef5  cmp     r15, rbx
0x140044ef8  jge     short loc_140044F21
0x140044efa  test    r15, 0FFFh
0x140044f01  jz      short loc_140044F21
0x140044f03  mov     r9d, 1
0x140044f09  lea     r8, [rsp+98h+NewFileSize]
0x140044f0e  mov     dl, r9b
0x140044f11  mov     rcx, rdi
0x140044f14  call    RxFlushFcbInSystemCacheEx
0x140044f19  mov     r12b, 1
0x140044f1c  mov     [rsp+98h+var_68], r12b
0x140044f21  lea     rdx, [rdi+18h]; FileSizes
0x140044f25  mov     rcx, r13; FileObject
0x140044f28  call    cs:__imp_CcSetFileSizes
0x140044f2f  nop     dword ptr [rax+rax+00h]
0x140044f34  cmp     [rdi+1E8h], r14
0x140044f3b  jz      short loc_140044F4C
0x140044f3d  mov     eax, [rdi+1F0h]
0x140044f43  test    al, 2
0x140044f45  jz      short loc_140044F4C
0x140044f47  test    r12b, r12b
0x140044f4a  jz      short loc_140044F69
0x140044f4c  mov     [rsp+98h+NewFileSize], r15
0x140044f51  mov     byte ptr [rsp+98h+LazyWriteContext], r14b; FlushFile
0x140044f56  xor     r9d, r9d; UninitializeCacheMaps
0x140044f59  xor     r8d, r8d; Length
0x140044f5c  lea     rdx, [rsp+98h+NewFileSize]; FileOffset
0x140044f61  mov     rcx, rdi; Fcb
0x140044f64  call    RxPurgeFcbInSystemCache
0x140044f69  mov     r12, [rsp+98h+var_60]
0x140044f6e  lea     rbx, WPP_GLOBAL_Control
0x140044f75  jmp     short loc_140044FCB
0x140044f77  mov     esi, eax
0x140044f79  mov     [rsp+98h+var_64], eax
0x140044f7d  mov     rax, [rsp+98h+var_50]
0x140044f82  mov     rdi, [rsp+98h+arg_10]
0x140044f8a  mov     [rdi+18h], rax
0x140044f8e  mov     r9d, 13h
0x140044f94  mov     rdx, [rsp+98h+arg_8]
0x140044f9c  mov     rcx, [rsp+98h+arg_0]
0x140044fa4  call    RxpSetInfoMiniRdr
0x140044fa9  xor     r14d, r14d
0x140044fac  lea     rbx, WPP_GLOBAL_Control
0x140044fb3  mov     r13, [rsp+98h+var_48]
0x140044fb8  mov     r12, [rsp+98h+var_60]
0x140044fbd  jmp     short loc_140044FCB
0x140044fbf  mov     r12, [rsp+98h+var_60]
0x140044fc4  lea     rbx, WPP_GLOBAL_Control
0x140044fcb  cmp     [rsp+98h+arg_18], r14b
0x140044fd3  jz      short loc_140044FE9
0x140044fd5  xor     r8d, r8d; UninitializeEvent
0x140044fd8  xor     edx, edx; TruncateSize
0x140044fda  mov     rcx, r13; FileObject
0x140044fdd  call    cs:__imp_CcUninitializeCacheMap
0x140044fe4  nop     dword ptr [rax+rax+00h]
0x140044fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x140044ff0  cmp     rcx, rbx
0x140044ff3  jz      short loc_14004501A
0x140044ff5  mov     eax, [rcx+2Ch]
0x140044ff8  test    al, 20h
0x140044ffa  jz      short loc_14004501A
0x140044ffc  cmp     byte ptr [rcx+29h], 2
0x140045000  jb      short loc_14004501A
0x140045002  mov     [rsp+98h+var_70], esi
0x140045006  mov     eax, [rdi+18h]
0x140045009  mov     dword ptr [rsp+98h+LazyWriteContext], eax
0x14004500d  mov     r9d, [r12]
0x140045011  mov     rcx, [rcx+18h]
0x140045015  call    WPP_SF_LLD
0x14004501a  mov     eax, esi
0x14004501c  jmp     loc_140044D54
0x14007ba3e  push    rbp
0x14007ba40  sub     rsp, 30h
0x14007ba44  mov     rbp, rdx
0x14007ba47  cmp     byte ptr [rbp+0B8h], 0
0x14007ba4e  jz      short loc_14007BA66
0x14007ba50  xor     r8d, r8d; UninitializeEvent
0x14007ba53  xor     edx, edx; TruncateSize
0x14007ba55  mov     rcx, [rbp+58h]; FileObject
0x14007ba59  call    cs:__imp_CcUninitializeCacheMap
0x14007ba60  nop     dword ptr [rax+rax+00h]
0x14007ba65  nop
0x14007ba66  add     rsp, 30h
0x14007ba6a  pop     rbp
0x14007ba6b  retn
```
