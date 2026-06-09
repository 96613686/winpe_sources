# RxSetEndOfFileInfo

- ea: `0x1400708e0`
- end: `0x140070f6b`
- name: `RxSetEndOfFileInfo`
- size: `1675`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14006f9e0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140011680`
- `0x140016d40`
- `0x140016e20`
- `0x140017280`
- `0x140017370`
- `0x140019444`
- `0x1400198a0`
- `0x1400242c0`
- `0x14006d6e0`
- `0x1400708e0`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x140070f55`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14007b635`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140070f55`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14007b635`
- `ntoskrnl!CcSetFileSizes` at `0x140070b11`
- `ntoskrnl!CcSetFileSizes` at `0x140070b11`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140070db8`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140070db8`
- `ntoskrnl!CcInitializeCacheMap` at `0x140070d67`
- `ntoskrnl!CcInitializeCacheMap` at `0x140070d67`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140070b94`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140070b94`

## pseudocode

```c
__int64 __fastcall RxSetEndOfFileInfo(__int64 a1, __int64 a2, struct _CC_FILE_SIZES *a3, __int64 a4)
{
  unsigned int v6; // ebx
  struct _FILE_OBJECT *v7; // r9
  struct _FILE_OBJECT *v8; // r15
  char v9; // r14
  LARGE_INTEGER *v10; // rdx
  LARGE_INTEGER v11; // rsi
  LARGE_INTEGER FileSize; // r8
  LARGE_INTEGER AllocationSize; // r11
  PSECTION_OBJECT_POINTERS *p_SectionObjectPointer; // rcx
  _QWORD *p_DataSectionObject; // rax
  __int64 v16; // r8
  LARGE_INTEGER *v17; // rdx
  LONG HighPart; // ecx
  LARGE_INTEGER v19; // r13
  char v20; // r13
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  LONGLONG *v24; // rsi
  LARGE_INTEGER *p_AllocationSize; // rdx
  LONGLONG *v26; // r15
  __int64 v27; // r13
  LARGE_INTEGER *SharedCacheMap; // rcx
  char v30; // [rsp+89h] [rbp-D7h]
  PCC_FILE_SIZES FileSizes; // [rsp+90h] [rbp-D0h]
  LARGE_INTEGER *QuadPart; // [rsp+98h] [rbp-C8h] BYREF
  LARGE_INTEGER ValidDataLength; // [rsp+A0h] [rbp-C0h]
  LARGE_INTEGER v34; // [rsp+A8h] [rbp-B8h]
  PSECTION_OBJECT_POINTERS *v35; // [rsp+B0h] [rbp-B0h]
  LARGE_INTEGER *p_FileSize; // [rsp+B8h] [rbp-A8h]
  LARGE_INTEGER *p_ValidDataLength; // [rsp+C0h] [rbp-A0h]
  LARGE_INTEGER v38; // [rsp+C8h] [rbp-98h]
  LARGE_INTEGER v39; // [rsp+D0h] [rbp-90h]
  LARGE_INTEGER v40; // [rsp+D8h] [rbp-88h]
  struct _FILE_OBJECT *v41; // [rsp+E0h] [rbp-80h]
  __int64 v42; // [rsp+E8h] [rbp-78h]
  _QWORD Parameter[2]; // [rsp+F8h] [rbp-68h] BYREF
  __int128 v44; // [rsp+108h] [rbp-58h]
  __int64 v45; // [rsp+118h] [rbp-48h]
  PFILE_OBJECT FileObject; // [rsp+170h] [rbp+10h]
  LARGE_INTEGER v48; // [rsp+180h] [rbp+20h]

  v6 = -1073741823;
  v42 = *(_QWORD *)(a4 + 32);
  v7 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 184) + 48LL);
  FileObject = v7;
  v8 = v7;
  v41 = v7;
  v38.QuadPart = 0;
  v39.QuadPart = 0;
  v40.QuadPart = 0;
  v9 = 0;
  v30 = 0;
  v10 = *(LARGE_INTEGER **)(a2 + 24);
  QuadPart = v10;
  v11 = *v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _WORD))WPP_SF_qiiii)(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      a3,
      a3,
      (LARGE_INTEGER)a3[1].FileSize.QuadPart,
      (LARGE_INTEGER)v11.QuadPart,
      (LARGE_INTEGER)a3[1].AllocationSize.QuadPart,
      (LARGE_INTEGER)a3[1].ValidDataLength.QuadPart,
      0);
    v10 = QuadPart;
    v7 = v8;
  }
  if ( LOWORD(a3->AllocationSize.LowPart) == 0xEC22 )
  {
    p_FileSize = &a3[1].FileSize;
    FileSize = a3[1].FileSize;
    v48 = FileSize;
    v38 = FileSize;
    FileSizes = a3 + 1;
    AllocationSize = a3[1].AllocationSize;
    v34 = AllocationSize;
    v39 = AllocationSize;
    p_ValidDataLength = &a3[1].ValidDataLength;
    ValidDataLength = a3[1].ValidDataLength;
    v40 = ValidDataLength;
    p_SectionObjectPointer = &v8->SectionObjectPointer;
    v35 = &v8->SectionObjectPointer;
    p_DataSectionObject = &v8->SectionObjectPointer->DataSectionObject;
    if ( *p_DataSectionObject && !p_DataSectionObject[1] && *(_BYTE *)(a2 + 64) )
    {
      if ( (v8->Flags & 0x4000) != 0 )
        goto LABEL_48;
      if ( FileSize.QuadPart > AllocationSize.QuadPart )
      {
        v23 = *(unsigned int *)(a3[5].AllocationSize.QuadPart + 104);
        a3[1].AllocationSize.QuadPart = (v23 + FileSize.QuadPart) & ~(v23 - 1);
      }
      CcInitializeCacheMap(v8, a3 + 1, 0, &Callbacks, a3);
      v30 = 1;
      v10 = QuadPart;
      v7 = FileObject;
      p_SectionObjectPointer = v35;
      FileSize = v48;
      AllocationSize = v34;
    }
    if ( p_FileSize->QuadPart == v11.QuadPart )
    {
      v6 = 0;
      v19 = ValidDataLength;
      v8->Flags |= 0x1000u;
      goto LABEL_51;
    }
    if ( p_FileSize->QuadPart <= v11.QuadPart )
      goto LABEL_6;
    if ( a3[20].AllocationSize.HighPart )
    {
      v6 = -1073740747;
    }
    else
    {
      if ( MmCanFileBeTruncated(*p_SectionObjectPointer, v10) )
      {
LABEL_6:
        LOBYTE(FileSize.LowPart) = 1;
        v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RxAcquirePagingIoResource)(
               a1,
               a3,
               (LARGE_INTEGER)FileSize.QuadPart);
        *p_FileSize = v11;
        v17 = p_ValidDataLength;
        if ( p_ValidDataLength->QuadPart > v11.QuadPart )
          *p_ValidDataLength = v11;
        HighPart = a3[6].ValidDataLength.HighPart;
        if ( ((HighPart & 2) == 0 || (a3[6].ValidDataLength.LowPart & 0x8000000) == 0)
          && ((HighPart & 1) == 0 || (a3[6].ValidDataLength.LowPart & 0x2000000) == 0)
          || (!*v35 || !(*v35)->SharedCacheMap) && (*(_DWORD *)(v42 + 128) & 8) != 0 )
        {
          *v17 = v11;
        }
        FileSizes->AllocationSize = v11;
        v6 = RxpSetInfoMiniRdr(a1, a2, v16, 20);
        if ( v6 )
        {
          v7 = FileObject;
          FileSize = v48;
          AllocationSize = v34;
          v19 = ValidDataLength;
        }
        else
        {
          if ( v9 )
          {
            RxReleasePagingIoResource(a1, a3);
            v9 = 0;
          }
          v20 = 0;
          QuadPart = (LARGE_INTEGER *)v11.QuadPart;
          if ( a3[20].FileSize.QuadPart
            && (a3[20].ValidDataLength.LowPart & 2) != 0
            && ((a3[6].ValidDataLength.HighPart & 2) == 0
             || (a3[6].ValidDataLength.LowPart & 0x8000000) == 0
             || (a3[20].ValidDataLength.HighPart & 0x100) != 0)
            && v11.QuadPart < v48.QuadPart
            && (v11.LowPart & 0xFFF) != 0 )
          {
            RxFlushFcbInSystemCacheEx(a3, 1, &QuadPart);
            v20 = 1;
          }
          CcSetFileSizes(v8, FileSizes);
          if ( !a3[20].FileSize.QuadPart || (a3[20].ValidDataLength.LowPart & 2) == 0 || v20 )
          {
            v44 = 0;
            v45 = 0;
            Parameter[0] = a3;
            Parameter[1] = &QuadPart;
            LODWORD(v44) = 0;
            BYTE4(v44) = 0;
            KeExpandKernelStackAndCalloutEx(
              RxpPurgeFcbInSystemCacheCallout,
              Parameter,
              0x6000u,
              0,
              (PVOID)RxContextLookasideList.L.ListHead.Region);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qDiD(WPP_GLOBAL_Control->AttachedDevice, v21, v22, a3, 0, QuadPart, DWORD2(v44));
            }
          }
          v7 = FileObject;
          FileSize = v48;
          AllocationSize = v34;
          v19 = ValidDataLength;
        }
        v8->Flags |= 0x1000u;
LABEL_51:
        if ( (v6 & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, v6);
            v7 = FileObject;
            FileSize = v48;
            AllocationSize = v34;
          }
          v24 = (LONGLONG *)p_FileSize;
          *p_FileSize = FileSize;
          p_AllocationSize = &a3[1].AllocationSize;
          FileSizes->AllocationSize = AllocationSize;
          v26 = (LONGLONG *)p_ValidDataLength;
          *p_ValidDataLength = v19;
          SharedCacheMap = (LARGE_INTEGER *)(*v35)->SharedCacheMap;
          if ( SharedCacheMap )
            SharedCacheMap[1] = FileSize;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v27 = a1;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 52, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, a1);
              v7 = FileObject;
              p_AllocationSize = &a3[1].AllocationSize;
            }
            goto LABEL_54;
          }
        }
        else
        {
          v24 = (LONGLONG *)p_FileSize;
          p_AllocationSize = &a3[1].AllocationSize;
          v26 = (LONGLONG *)p_ValidDataLength;
        }
        v27 = a1;
LABEL_54:
        if ( v9 )
        {
          RxReleasePagingIoResource(v27, a3);
          v7 = FileObject;
          p_AllocationSize = &a3[1].AllocationSize;
        }
        if ( v30 )
        {
          CcUninitializeCacheMap(v7, 0, 0);
          p_AllocationSize = &a3[1].AllocationSize;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_Dqiii)(
            WPP_GLOBAL_Control->AttachedDevice,
            p_AllocationSize,
            (LARGE_INTEGER)FileSize.QuadPart,
            v6,
            a3,
            *v24,
            p_AllocationSize->QuadPart,
            *v26);
        }
        return v6;
      }
      v6 = -1073741245;
      v7 = FileObject;
      FileSize = v48;
      AllocationSize = v34;
    }
LABEL_48:
    v19 = ValidDataLength;
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids);
  }
  return 3221225488LL;
}

```

## disassembly

```asm
0x1400708e0  mov     [rsp+arg_10], r8
0x1400708e5  mov     [rsp+arg_0], rcx
0x1400708ea  push    rbx
0x1400708eb  push    rsi
0x1400708ec  push    rdi
0x1400708ed  push    r12
0x1400708ef  push    r13
0x1400708f1  push    r14
0x1400708f3  push    r15
0x1400708f5  sub     rsp, 0E0h
0x1400708fc  mov     rdi, r8
0x1400708ff  mov     r13, rdx
0x140070902  mov     ebx, 0C0000001h
0x140070907  mov     [rsp+118h+var_D4], ebx
0x14007090b  mov     rax, [r9+20h]
0x14007090f  mov     [rsp+118h+var_78], rax
0x140070917  mov     rax, [rdx+0B8h]
0x14007091e  mov     r9, [rax+30h]
0x140070922  mov     [rsp+118h+FileObject], r9
0x14007092a  mov     r15, r9
0x14007092d  mov     [rsp+118h+var_80], r9
0x140070935  xor     eax, eax
0x140070937  mov     [rsp+118h+var_98], rax
0x14007093f  mov     [rsp+118h+var_90], rax
0x140070947  mov     [rsp+118h+var_88], rax
0x14007094f  mov     [rsp+118h+var_D7], al
0x140070953  xor     r14b, r14b
0x140070956  mov     [rsp+118h+var_D8], r14b
0x14007095b  mov     rdx, [rdx+18h]; NewFileSize
0x14007095f  mov     [rsp+118h+var_C8], rdx
0x140070964  mov     rsi, [rdx]
0x140070967  lea     r12, WPP_GLOBAL_Control
0x14007096e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070975  cmp     rcx, r12
0x140070978  jnz     loc_14007F526
0x14007097e  mov     eax, 0EC22h
0x140070983  cmp     [rdi], ax
0x140070986  jnz     loc_140070E99
0x14007098c  lea     rax, [rdi+20h]
0x140070990  mov     [rsp+118h+var_A8], rax
0x140070995  mov     r8, [rax]
0x140070998  mov     [rsp+118h+arg_18], r8
0x1400709a0  mov     [rsp+118h+var_98], r8
0x1400709a8  lea     r10, [rdi+18h]
0x1400709ac  mov     [rsp+118h+FileSizes], r10
0x1400709b1  mov     r11, [r10]
0x1400709b4  mov     [rsp+118h+var_B8], r11
0x1400709b9  mov     [rsp+118h+var_90], r11
0x1400709c1  lea     rax, [rdi+28h]
0x1400709c5  mov     [rsp+118h+var_A0], rax
0x1400709ca  mov     rax, [rax]
0x1400709cd  mov     [rsp+118h+var_C0], rax
0x1400709d2  mov     [rsp+118h+var_88], rax
0x1400709da  lea     rcx, [r15+28h]
0x1400709de  mov     [rsp+118h+var_B0], rcx
0x1400709e3  mov     rax, [rcx]
0x1400709e6  cmp     qword ptr [rax], 0
0x1400709ea  jnz     loc_140070D15
0x1400709f0  mov     rbx, [rsp+118h+var_A8]
0x1400709f5  cmp     [rbx], rsi
0x1400709f8  jz      loc_140070CFD
0x1400709fe  jg      loc_140070D9C
0x140070a04  mov     r8b, 1
0x140070a07  mov     rdx, rdi
0x140070a0a  mov     rcx, [rsp+118h+arg_0]
0x140070a12  call    RxAcquirePagingIoResource
0x140070a17  movzx   r14d, al
0x140070a1b  mov     [rsp+118h+var_D8], al
0x140070a1f  mov     [rbx], rsi
0x140070a22  mov     rdx, [rsp+118h+var_A0]
0x140070a27  cmp     [rdx], rsi
0x140070a2a  jg      loc_140070DEC
0x140070a30  mov     ecx, [rdi+0A4h]
0x140070a36  test    cl, 2
0x140070a39  jnz     short loc_140070AA1
0x140070a3b  test    cl, 1
0x140070a3e  jz      short loc_140070A4C
0x140070a40  test    dword ptr [rdi+0A0h], 2000000h
0x140070a4a  jnz     short loc_140070AAD
0x140070a4c  mov     [rdx], rsi
0x140070a4f  mov     rax, [rsp+118h+FileSizes]
0x140070a54  mov     [rax], rsi
0x140070a57  mov     r9d, 14h
0x140070a5d  mov     rdx, r13
0x140070a60  mov     r13, [rsp+118h+arg_0]
0x140070a68  mov     rcx, r13
0x140070a6b  call    RxpSetInfoMiniRdr
0x140070a70  mov     ebx, eax
0x140070a72  mov     [rsp+118h+var_D4], eax
0x140070a76  test    eax, eax
0x140070a78  jz      short loc_140070ADC
0x140070a7a  mov     r9, [rsp+118h+FileObject]
0x140070a82  mov     r8, [rsp+118h+arg_18]
0x140070a8a  mov     r11, [rsp+118h+var_B8]
0x140070a8f  mov     r13, [rsp+118h+var_C0]
0x140070a94  or      dword ptr [r15+50h], 1000h
0x140070a9c  jmp     loc_140070E0C
0x140070aa1  test    dword ptr [rdi+0A0h], 8000000h
0x140070aab  jz      short loc_140070A3B
0x140070aad  mov     rax, [rsp+118h+var_B0]
0x140070ab2  mov     rax, [rax]
0x140070ab5  test    rax, rax
0x140070ab8  jz      short loc_140070AC1
0x140070aba  cmp     qword ptr [rax+8], 0
0x140070abf  jnz     short loc_140070A4F
0x140070ac1  mov     rax, [rsp+118h+var_78]
0x140070ac9  mov     eax, [rax+80h]
0x140070acf  test    al, 8
0x140070ad1  jz      loc_140070A4F
0x140070ad7  jmp     loc_140070A4C
0x140070adc  test    r14b, r14b
0x140070adf  jnz     loc_140070DF4
0x140070ae5  mov     [rsp+118h+var_C8], 0
0x140070aee  xor     r13b, r13b
0x140070af1  mov     [rsp+118h+var_D6], r13b
0x140070af6  mov     [rsp+118h+var_C8], rsi
0x140070afb  cmp     qword ptr [rdi+1E8h], 0
0x140070b03  jnz     loc_140070C5A
0x140070b09  mov     rdx, [rsp+118h+FileSizes]; FileSizes
0x140070b0e  mov     rcx, r15; FileObject
0x140070b11  call    cs:__imp_CcSetFileSizes
0x140070b18  nop     dword ptr [rax+rax+00h]
0x140070b1d  cmp     qword ptr [rdi+1E8h], 0
0x140070b25  jnz     loc_140070C6A
0x140070b2b  xorps   xmm0, xmm0
0x140070b2e  xor     eax, eax
0x140070b30  movups  [rsp+118h+Parameter], xmm0
0x140070b38  movups  [rsp+118h+var_58], xmm0
0x140070b40  mov     [rsp+118h+var_48], rax
0x140070b48  mov     qword ptr [rsp+118h+Parameter], rdi
0x140070b50  lea     rax, [rsp+118h+var_C8]
0x140070b55  mov     qword ptr [rsp+118h+Parameter+8], rax
0x140070b5d  mov     dword ptr [rsp+118h+var_58], 0
0x140070b68  mov     byte ptr [rsp+118h+var_58+4], 0
0x140070b70  mov     rax, qword ptr cs:RxContextLookasideList.L+8
0x140070b77  mov     [rsp+118h+Context], rax; Context
0x140070b7c  xor     r9d, r9d; Wait
0x140070b7f  mov     r8d, 6000h; Size
0x140070b85  lea     rdx, [rsp+118h+Parameter]; Parameter
0x140070b8d  lea     rcx, RxpPurgeFcbInSystemCacheCallout; Callout
0x140070b94  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140070b9b  nop     dword ptr [rax+rax+00h]
0x140070ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x140070ba7  cmp     rcx, r12
0x140070baa  jz      loc_140070C81
0x140070bb0  test    dword ptr [rcx+2Ch], 200h
0x140070bb7  jz      loc_140070C81
0x140070bbd  cmp     byte ptr [rcx+29h], 2
0x140070bc1  jb      loc_140070C81
0x140070bc7  mov     eax, dword ptr [rsp+118h+var_58+8]
0x140070bce  mov     dword ptr [rsp+118h+var_E8], eax
0x140070bd2  mov     rax, [rsp+118h+var_C8]
0x140070bd7  mov     [rsp+118h+var_F0], rax
0x140070bdc  mov     dword ptr [rsp+118h+Context], 0
0x140070be4  mov     r9, rdi
0x140070be7  mov     rcx, [rcx+18h]
0x140070beb  call    WPP_SF_qDiD
0x140070bf0  jmp     loc_140070C81
0x140070bf5  mov     eax, [rdi+0A4h]
0x140070bfb  test    al, 2
0x140070bfd  jz      short loc_140070C1B
0x140070bff  test    dword ptr [rdi+0A0h], 8000000h
0x140070c09  jz      short loc_140070C1B
0x140070c0b  test    dword ptr [rdi+1F4h], 100h
0x140070c15  jz      loc_140070B09
0x140070c1b  cmp     rsi, [rsp+118h+arg_18]
0x140070c23  jge     loc_140070B09
0x140070c29  test    rsi, 0FFFh
0x140070c30  jz      loc_140070B09
0x140070c36  mov     r9d, 1
0x140070c3c  lea     r8, [rsp+118h+var_C8]
0x140070c41  movzx   edx, r9b
0x140070c45  mov     rcx, rdi
0x140070c48  call    RxFlushFcbInSystemCacheEx
0x140070c4d  mov     r13b, 1
0x140070c50  mov     [rsp+118h+var_D6], r13b
0x140070c55  jmp     loc_140070B09
0x140070c5a  mov     eax, [rdi+1F0h]
0x140070c60  test    al, 2
0x140070c62  jz      loc_140070B09
0x140070c68  jmp     short loc_140070BF5
0x140070c6a  mov     eax, [rdi+1F0h]
0x140070c70  test    al, 2
0x140070c72  jz      loc_140070B2B
0x140070c78  test    r13b, r13b
0x140070c7b  jnz     loc_140070B2B
0x140070c81  mov     r9, [rsp+118h+FileObject]
0x140070c89  mov     r8, [rsp+118h+arg_18]
0x140070c91  mov     r11, [rsp+118h+var_B8]
0x140070c96  mov     r13, [rsp+118h+var_C0]
0x140070c9b  jmp     short loc_140070CF0
0x140070c9d  mov     ebx, eax
0x140070c9f  mov     [rsp+118h+var_D4], eax
0x140070ca3  lea     r12, WPP_GLOBAL_Control
0x140070caa  mov     rdi, [rsp+118h+arg_10]
0x140070cb2  mov     r15, [rsp+118h+var_80]
0x140070cba  mov     r8, [rsp+118h+var_98]
0x140070cc2  mov     [rsp+118h+arg_18], r8
0x140070cca  mov     r11, [rsp+118h+var_90]
0x140070cd2  mov     [rsp+118h+var_B8], r11
0x140070cd7  mov     r13, [rsp+118h+var_88]
0x140070cdf  movzx   r14d, [rsp+118h+var_D8]
0x140070ce5  mov     r9, r15
0x140070ce8  mov     [rsp+118h+FileObject], r15
0x140070cf0  test    ebx, ebx
0x140070cf2  jnz     loc_140070E0C
0x140070cf8  jmp     loc_140070A94
0x140070cfd  xor     ebx, ebx
0x140070cff  mov     [rsp+118h+var_D4], ebx
0x140070d03  mov     r13, [rsp+118h+var_C0]
0x140070d08  or      dword ptr [r15+50h], 1000h
0x140070d10  jmp     loc_140070E0C
0x140070d15  cmp     qword ptr [rax+8], 0
0x140070d1a  jnz     loc_1400709F0
0x140070d20  cmp     byte ptr [r13+40h], 0
0x140070d25  jz      loc_1400709F0
0x140070d2b  test    dword ptr [r15+50h], 4000h
0x140070d33  jnz     short loc_140070DAE
0x140070d35  cmp     r8, r11
0x140070d38  jle     short loc_140070D52
0x140070d3a  mov     rax, [rdi+78h]
0x140070d3e  mov     ecx, [rax+68h]
0x140070d41  lea     rdx, [rcx-1]
0x140070d45  not     rdx
0x140070d48  lea     rax, [rcx+r8]
0x140070d4c  and     rdx, rax
0x140070d4f  mov     [r10], rdx
0x140070d52  mov     [rsp+118h+Context], rdi; LazyWriteContext
0x140070d57  lea     r9, Callbacks; Callbacks
0x140070d5e  xor     r8d, r8d; PinAccess
0x140070d61  mov     rdx, r10; FileSizes
0x140070d64  mov     rcx, r15; FileObject
0x140070d67  call    cs:__imp_CcInitializeCacheMap
0x140070d6e  nop     dword ptr [rax+rax+00h]
0x140070d73  mov     [rsp+118h+var_D7], 1
0x140070d78  mov     rdx, [rsp+118h+var_C8]
0x140070d7d  mov     r9, [rsp+118h+FileObject]
0x140070d85  mov     rcx, [rsp+118h+var_B0]
0x140070d8a  mov     r8, [rsp+118h+arg_18]
0x140070d92  mov     r11, [rsp+118h+var_B8]
0x140070d97  jmp     loc_1400709F0
0x140070d9c  cmp     dword ptr [rdi+1E4h], 0
0x140070da3  jbe     short loc_140070DB5
0x140070da5  mov     ebx, 0C0000435h
0x140070daa  mov     [rsp+118h+var_D4], ebx
0x140070dae  mov     r13, [rsp+118h+var_C0]
0x140070db3  jmp     short loc_140070E0C
0x140070db5  mov     rcx, [rcx]; SectionPointer
0x140070db8  call    cs:__imp_MmCanFileBeTruncated
0x140070dbf  nop     dword ptr [rax+rax+00h]
0x140070dc4  test    al, al
0x140070dc6  jnz     loc_140070A04
0x140070dcc  mov     ebx, 0C0000243h
0x140070dd1  mov     [rsp+118h+var_D4], ebx
0x140070dd5  mov     r9, [rsp+118h+FileObject]
0x140070ddd  mov     r8, [rsp+118h+arg_18]
0x140070de5  mov     r11, [rsp+118h+var_B8]
0x140070dea  jmp     short loc_140070DAE
0x140070dec  mov     [rdx], rsi
0x140070def  jmp     loc_140070A30
0x140070df4  mov     rdx, rdi
0x140070df7  mov     rcx, r13
0x140070dfa  call    RxReleasePagingIoResource
0x140070dff  xor     r14b, r14b
0x140070e02  mov     [rsp+118h+var_D8], r14b
0x140070e07  jmp     loc_140070AE5
0x140070e0c  test    ebx, ebx
0x140070e0e  js      loc_140070ED9
0x140070e14  mov     rsi, [rsp+118h+var_A8]
0x140070e19  mov     rdx, [rsp+118h+FileSizes]
0x140070e1e  mov     r15, [rsp+118h+var_A0]
0x140070e23  mov     r13, [rsp+118h+arg_0]
0x140070e2b  test    r14b, r14b
0x140070e2e  jnz     loc_140070F30
0x140070e34  cmp     [rsp+118h+var_D7], 0
0x140070e39  jnz     loc_140070F4D
0x140070e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140070e46  cmp     rcx, r12
0x140070e49  jnz     short loc_140070E61
0x140070e4b  mov     eax, ebx
0x140070e4d  add     rsp, 0E0h
0x140070e54  pop     r15
0x140070e56  pop     r14
0x140070e58  pop     r13
0x140070e5a  pop     r12
0x140070e5c  pop     rdi
0x140070e5d  pop     rsi
0x140070e5e  pop     rbx
0x140070e5f  retn
0x140070e61  mov     eax, [rcx+2Ch]
0x140070e64  test    al, 20h
0x140070e66  jz      short loc_140070E4B
0x140070e68  cmp     byte ptr [rcx+29h], 2
0x140070e6c  jb      short loc_140070E4B
0x140070e6e  mov     rax, [r15]
0x140070e71  mov     [rsp+118h+var_E0], rax
0x140070e76  mov     rax, [rdx]
0x140070e79  mov     [rsp+118h+var_E8], rax
0x140070e7e  mov     rax, [rsi]
0x140070e81  mov     [rsp+118h+var_F0], rax
  ... truncated ...
```
