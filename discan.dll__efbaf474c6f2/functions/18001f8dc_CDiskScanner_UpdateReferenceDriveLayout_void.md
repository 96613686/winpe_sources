# CDiskScanner::UpdateReferenceDriveLayout(void *)

- ea: `0x18001f8dc`
- end: `0x18001fabe`
- name: `?UpdateReferenceDriveLayout@CDiskScanner@@QEAAJPEAX@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct _STORAGE_DEVICE_NUMBER_EX *this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001ce8c`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x1800064d8`
- `0x180006688`
- `0x180009604`
- `0x18001f8dc`
- `0x180020688`

## string_xrefs

- `0x18001f90e`: `CDiskScanner::UpdateReferenceDriveLayout`

## pseudocode

```c
__int64 __fastcall CDiskScanner::UpdateReferenceDriveLayout(struct _STORAGE_DEVICE_NUMBER_EX *this, void *a2)
{
  __int64 v4; // r9
  int DriveLayout; // eax
  unsigned int v6; // edi
  const char *v8; // [rsp+40h] [rbp-38h] BYREF
  int v9; // [rsp+48h] [rbp-30h]

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v8 = "CDiskScanner::UpdateReferenceDriveLayout";
  ++*(_WORD *)(v4 + 8);
  *(_QWORD *)(v4 + 16) = "CDiskScanner::UpdateReferenceDriveLayout";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskScanner::UpdateReferenceDriveLayout");
  }
  DriveLayout = DiskGetDriveLayoutEx(this, a2, &this[5].Flags, &this[5], &this[5].Size);
  v9 = DriveLayout;
  v6 = DriveLayout;
  if ( DriveLayout >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          this->DeviceNumber);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
            this->DeviceNumber);
        }
      }
      WppDumpDriveLayout(this, *(const struct _DRIVE_LAYOUT_INFORMATION_EX **)&this[5].Flags);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          this->DeviceNumber);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      this->DeviceNumber,
      DriveLayout);
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v8);
  return v6;
}

```

## disassembly

```asm
0x18001f8dc  mov     r11, rsp
0x18001f8df  push    rbx
0x18001f8e0  push    rsi
0x18001f8e1  push    rdi
0x18001f8e2  push    r15
0x18001f8e4  sub     rsp, 58h
0x18001f8e8  mov     r8d, cs:_tls_index
0x18001f8ef  mov     rdi, rdx
0x18001f8f2  mov     rax, gs:58h
0x18001f8fb  mov     rbx, rcx
0x18001f8fe  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001f905  mov     edx, 8
0x18001f90a  mov     r9, [rax+r8*8]
0x18001f90e  lea     r8, aCdiskscannerUp; "CDiskScanner::UpdateReferenceDriveLayou"...
0x18001f915  mov     eax, 10h
0x18001f91a  mov     [r11-38h], r8
0x18001f91e  inc     word ptr [rdx+r9]
0x18001f923  movzx   edx, word ptr [rdx+r9]
0x18001f928  mov     [rax+r9], r8
0x18001f92c  cmp     dx, cx
0x18001f92f  movzx   eax, cx
0x18001f932  cmovb   ax, dx
0x18001f936  cmovb   cx, dx
0x18001f93a  mov     [rsp+78h+var_48], ax
0x18001f93f  xor     eax, eax
0x18001f941  mov     [rsp+78h+var_44], eax
0x18001f945  mov     rax, cs:off_180047060; "                                       "...
0x18001f94c  mov     [rsp+78h+var_46], cx
0x18001f951  mov     [r11-40h], rax
0x18001f955  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f95c  lea     r15, WPP_GLOBAL_Control
0x18001f963  cmp     rcx, r15
0x18001f966  jz      short loc_18001F98A
0x18001f968  test    byte ptr [rcx+1Ch], 1
0x18001f96c  jz      short loc_18001F98A
0x18001f96e  cmp     byte ptr [rcx+19h], 5
0x18001f972  jb      short loc_18001F98A
0x18001f974  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f978  lea     r9, [r11-48h]
0x18001f97c  mov     edx, 0Dh
0x18001f981  mov     [r11-58h], r8
0x18001f985  call    WPP_SF_aZs
0x18001f98a  lea     rax, [rbx+0CCh]
0x18001f991  mov     rdx, rdi
0x18001f994  lea     rsi, [rbx+0D0h]
0x18001f99b  mov     [rsp+78h+var_58], rax
0x18001f9a0  mov     r8, rsi
0x18001f9a3  lea     r9, [rbx+0C8h]
0x18001f9aa  mov     rcx, rbx
0x18001f9ad  call    ?DiskGetDriveLayoutEx@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXAEAV?$CHeapPtr@U_DRIVE_LAYOUT_INFORMATION_EX@@VCCRTAllocator@ATL@@@ATL@@AEAKPEAK@Z; DiskGetDriveLayoutEx(_STORAGE_DEVICE_NUMBER_EX const *,void *,ATL::CHeapPtr<_DRIVE_LAYOUT_INFORMATION_EX,ATL::CCRTAllocator> &,ulong &,ulong *)
0x18001f9b2  mov     [rsp+78h+var_30], eax
0x18001f9b6  mov     edi, eax
0x18001f9b8  test    eax, eax
0x18001f9ba  jns     short loc_18001FA02
0x18001f9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9c3  cmp     rcx, r15
0x18001f9c6  jz      loc_18001FAA8
0x18001f9cc  test    byte ptr [rcx+1Ch], 1
0x18001f9d0  jz      loc_18001FAA8
0x18001f9d6  cmp     byte ptr [rcx+19h], 2
0x18001f9da  jb      loc_18001FAA8
0x18001f9e0  mov     r9d, [rbx+10h]
0x18001f9e4  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001f9eb  mov     rcx, [rcx+10h]
0x18001f9ef  mov     edx, 4Ch ; 'L'
0x18001f9f4  mov     dword ptr [rsp+78h+var_58], eax
0x18001f9f8  call    WPP_SF_Dd
0x18001f9fd  jmp     loc_18001FAA8
0x18001fa02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa09  test    byte ptr [rcx+1Ch], 1
0x18001fa0d  jz      loc_18001FAA8
0x18001fa13  cmp     byte ptr [rcx+19h], 4
0x18001fa17  jb      loc_18001FAA8
0x18001fa1d  cmp     rcx, r15
0x18001fa20  jz      short loc_18001FA6C
0x18001fa22  mov     r9d, [rbx+10h]
0x18001fa26  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001fa2d  mov     rcx, [rcx+10h]
0x18001fa31  mov     edx, 4Dh ; 'M'
0x18001fa36  call    WPP_SF_d
0x18001fa3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa42  cmp     rcx, r15
0x18001fa45  jz      short loc_18001FA6C
0x18001fa47  test    byte ptr [rcx+1Ch], 1
0x18001fa4b  jz      short loc_18001FA6C
0x18001fa4d  cmp     byte ptr [rcx+19h], 4
0x18001fa51  jb      short loc_18001FA6C
0x18001fa53  mov     r9d, [rbx+10h]
0x18001fa57  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001fa5e  mov     rcx, [rcx+10h]
0x18001fa62  mov     edx, 4Eh ; 'N'
0x18001fa67  call    WPP_SF_d
0x18001fa6c  mov     rdx, [rsi]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x18001fa6f  mov     rcx, rbx; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001fa72  call    ?WppDumpDriveLayout@@YAXPEBU_STORAGE_DEVICE_NUMBER_EX@@PEBU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; WppDumpDriveLayout(_STORAGE_DEVICE_NUMBER_EX const *,_DRIVE_LAYOUT_INFORMATION_EX const *)
0x18001fa77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa7e  cmp     rcx, r15
0x18001fa81  jz      short loc_18001FAA8
0x18001fa83  test    byte ptr [rcx+1Ch], 1
0x18001fa87  jz      short loc_18001FAA8
0x18001fa89  cmp     byte ptr [rcx+19h], 4
0x18001fa8d  jb      short loc_18001FAA8
0x18001fa8f  mov     r9d, [rbx+10h]
0x18001fa93  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001fa9a  mov     rcx, [rcx+10h]
0x18001fa9e  mov     edx, 4Fh ; 'O'
0x18001faa3  call    WPP_SF_d
0x18001faa8  lea     rcx, [rsp+78h+var_38]; this
0x18001faad  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001fab2  mov     eax, edi
0x18001fab4  add     rsp, 58h
0x18001fab8  pop     r15
0x18001faba  pop     rdi
0x18001fabb  pop     rsi
0x18001fabc  pop     rbx
0x18001fabd  retn
```
