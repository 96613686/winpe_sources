# DeleteFilterFromIndex

- ea: `0x18003be30`
- end: `0x18003c0d6`
- name: `DeleteFilterFromIndex`
- size: `678`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180011330`
- `0x18001e244`
- `0x180042b08`
- `0x180043910`

## callees

- `0x180007e38`
- `0x180011500`
- `0x180011bfc`
- `0x18003ba8c`
- `0x18003be30`
- `0x18003c48c`
- `0x18003c64c`
- `0x18003c9bc`
- `0x18003ca68`
- `0x18003cb2c`
- `0x18003cc08`
- `0x18004180c`
- `0x1800418bc`
- `0x180041a88`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c076`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c051`

## string_xrefs

- `0x18003beb2`: `DeleteFilterFromIndex`
- `0x18003bfb2`: `DeleteFilterFromIndex`
- `0x18003c0b4`: `DeleteFilterFromIndex`

## pseudocode

```c
__int64 __fastcall DeleteFilterFromIndex(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v6; // rbp
  unsigned __int16 v8; // r14
  int LayerStringFromLayerId; // eax
  __int64 v10; // r10
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rbx
  __int64 IntFilter; // rax
  __int64 v15; // rdi
  int v16; // edx
  int v17; // ebx
  int v18; // r8d
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rsi
  const char *v22; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  _QWORD v25[9]; // [rsp+50h] [rbp-48h] BYREF

  v6 = a2;
  v8 = a1;
  v25[0] = 0;
  a5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LayerStringFromLayerId = WfpGetLayerStringFromLayerId((unsigned __int16)a1);
    WPP_SF_sddI(*(_QWORD *)(v10 + 16), v11, v12, LayerStringFromLayerId, v8, v6, v12);
  }
  if ( a4 && (_DWORD)v6 )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "DeleteFilterFromIndex", 3221225485LL);
    goto LABEL_37;
  }
  IntFilter = FindIntFilter(v8, a3, &a5);
  v15 = a5;
  v13 = IntFilter;
  if ( IntFilter )
    goto LABEL_35;
  v17 = WfpGetLayerStringFromLayerId(v8);
  if ( *(__int64 *)(v15 + 16) <= 2 )
    goto LABEL_14;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_19;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_sddIqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v18, v17, v8, v6, a3, v15, *(_DWORD *)(v15 + 16));
LABEL_14:
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && *((_BYTE *)v19 + 25) >= 5u && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_sddIq(v19[2], v16, v18, v17, v8, v6, a3, v15);
LABEL_19:
  v13 = GetLayerFromIdRead(v8, v25);
  if ( !v13 )
  {
    v21 = v25[0];
    if ( a4 || !*(_QWORD *)(v25[0] + 96LL) || (_DWORD)v6 )
    {
      if ( (unsigned int)IsValidIndex(v25[0], (unsigned int)v6) )
      {
        v13 = (*((__int64 (__fastcall **)(_QWORD, __int64))gWfpGlobal
               + 7 * *(int *)(*(_QWORD *)(v21 + 144) + 16 * v6 + 8)
               + 20))(
                *(_QWORD *)(*(_QWORD *)(v21 + 144) + 16 * v6),
                v15);
        if ( !v13 )
        {
          if ( (Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState & 0x10) != 0 )
            IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState
                                         & 1;
          else
            IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline();
          if ( IsEnabledDeviceUsageNoInline )
            *((_BYTE *)gWfpGlobal + 1076) = AreAllIpv4InLayersEmpty();
          EnterCriticalSection(&gLayerStatsLock);
          *(_QWORD *)(v21 + 136) -= *(_QWORD *)(v15 + 80);
          _InterlockedDecrement((volatile signed __int32 *)(v21 + 152));
          LeaveCriticalSection(&gLayerStatsLock);
          v13 = RemoveFilterFromFilterHashtable(v8, a3);
          if ( !v13 )
            HandleFilterDeref(v15, 0);
        }
        goto LABEL_35;
      }
      v22 = "IsValidIndex";
    }
    else
    {
      v22 = "DeleteFilterFromIndex";
    }
    v13 = WfpReportSysErrorAsNtStatus(v20, v22, 3221225485LL);
  }
LABEL_35:
  if ( v15 )
    HandleFilterDeref(v15, 0);
LABEL_37:
  if ( v13 )
    WfpReportError(v13, "DeleteFilterFromIndex");
  return v13;
}

```

## disassembly

```asm
0x18003be30  mov     rax, rsp
0x18003be33  push    rbx
0x18003be34  push    rbp
0x18003be35  push    rsi
0x18003be36  push    rdi
0x18003be37  push    r12
0x18003be39  push    r14
0x18003be3b  push    r15
0x18003be3d  sub     rsp, 60h
0x18003be41  mov     r12d, r9d
0x18003be44  mov     ebp, edx
0x18003be46  mov     r15, r8
0x18003be49  movzx   r14d, cx
0x18003be4d  mov     qword ptr [rax-48h], 0
0x18003be55  mov     qword ptr [rax+28h], 0
0x18003be5d  mov     r10, cs:WPP_GLOBAL_Control
0x18003be64  lea     rax, WPP_GLOBAL_Control
0x18003be6b  mov     sil, 8
0x18003be6e  cmp     r10, rax
0x18003be71  jz      short loc_18003BEA3
0x18003be73  cmp     byte ptr [r10+19h], 5
0x18003be78  jb      short loc_18003BEA3
0x18003be7a  test    [r10+1Ch], sil
0x18003be7e  jz      short loc_18003BEA3
0x18003be80  movzx   ecx, r14w
0x18003be84  call    WfpGetLayerStringFromLayerId
0x18003be89  mov     rcx, [r10+10h]
0x18003be8d  mov     r9, rax
0x18003be90  mov     [rsp+98h+var_68], r8
0x18003be95  mov     [rsp+98h+var_70], ebp
0x18003be99  mov     [rsp+98h+var_78], r14d
0x18003be9e  call    WPP_SF_sddI
0x18003bea3  test    r12d, r12d
0x18003bea6  jz      short loc_18003BEC6
0x18003bea8  test    ebp, ebp
0x18003beaa  jz      short loc_18003BEC6
0x18003beac  mov     r8d, 0C000000Dh
0x18003beb2  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x18003beb9  call    WfpReportSysErrorAsNtStatus
0x18003bebe  mov     rbx, rax
0x18003bec1  jmp     loc_18003C0AF
0x18003bec6  lea     r8, [rsp+98h+arg_20]
0x18003bece  mov     rdx, r15
0x18003bed1  movzx   ecx, r14w
0x18003bed5  call    FindIntFilter
0x18003beda  mov     rdi, [rsp+98h+arg_20]
0x18003bee2  mov     rbx, rax
0x18003bee5  test    rax, rax
0x18003bee8  jnz     loc_18003C0A0
0x18003beee  movzx   ecx, r14w
0x18003bef2  call    WfpGetLayerStringFromLayerId
0x18003bef7  cmp     qword ptr [rdi+10h], 2
0x18003befc  mov     rbx, rax
0x18003beff  jle     short loc_18003BF46
0x18003bf01  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf08  lea     rax, WPP_GLOBAL_Control
0x18003bf0f  cmp     rcx, rax
0x18003bf12  jz      short loc_18003BF84
0x18003bf14  cmp     byte ptr [rcx+19h], 3
0x18003bf18  jb      short loc_18003BF54
0x18003bf1a  test    [rcx+1Ch], sil
0x18003bf1e  jz      short loc_18003BF54
0x18003bf20  mov     eax, [rdi+10h]
0x18003bf23  mov     r9, rbx
0x18003bf26  mov     rcx, [rcx+10h]
0x18003bf2a  mov     [rsp+98h+var_58], eax
0x18003bf2e  mov     [rsp+98h+var_60], rdi
0x18003bf33  mov     [rsp+98h+var_68], r15
0x18003bf38  mov     [rsp+98h+var_70], ebp
0x18003bf3c  mov     [rsp+98h+var_78], r14d
0x18003bf41  call    WPP_SF_sddIqd
0x18003bf46  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf4d  lea     rax, WPP_GLOBAL_Control
0x18003bf54  cmp     rcx, rax
0x18003bf57  jz      short loc_18003BF84
0x18003bf59  cmp     byte ptr [rcx+19h], 5
0x18003bf5d  jb      short loc_18003BF84
0x18003bf5f  test    [rcx+1Ch], sil
0x18003bf63  jz      short loc_18003BF84
0x18003bf65  mov     rcx, [rcx+10h]
0x18003bf69  mov     r9, rbx
0x18003bf6c  mov     [rsp+98h+var_60], rdi
0x18003bf71  mov     [rsp+98h+var_68], r15
0x18003bf76  mov     [rsp+98h+var_70], ebp
0x18003bf7a  mov     [rsp+98h+var_78], r14d
0x18003bf7f  call    WPP_SF_sddIq
0x18003bf84  lea     rdx, [rsp+98h+var_48]
0x18003bf89  movzx   ecx, r14w
0x18003bf8d  call    GetLayerFromIdRead
0x18003bf92  mov     rbx, rax
0x18003bf95  test    rax, rax
0x18003bf98  jnz     loc_18003C0A0
0x18003bf9e  mov     rsi, [rsp+98h+var_48]
0x18003bfa3  test    r12d, r12d
0x18003bfa6  jnz     short loc_18003BFCC
0x18003bfa8  cmp     [rsi+60h], rax
0x18003bfac  jz      short loc_18003BFCC
0x18003bfae  test    ebp, ebp
0x18003bfb0  jnz     short loc_18003BFCC
0x18003bfb2  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x18003bfb9  mov     r8d, 0C000000Dh
0x18003bfbf  call    WfpReportSysErrorAsNtStatus
0x18003bfc4  mov     rbx, rax
0x18003bfc7  jmp     loc_18003C0A0
0x18003bfcc  mov     edx, ebp
0x18003bfce  mov     rcx, rsi
0x18003bfd1  call    IsValidIndex
0x18003bfd6  test    eax, eax
0x18003bfd8  jnz     short loc_18003BFE3
0x18003bfda  lea     rdx, aIsvalidindex; "IsValidIndex"
0x18003bfe1  jmp     short loc_18003BFB9
0x18003bfe3  mov     r8, [rsi+90h]
0x18003bfea  mov     r9, rbp
0x18003bfed  add     r9, r9
0x18003bff0  mov     rdx, rdi
0x18003bff3  movsxd  rax, dword ptr [r8+r9*8+8]
0x18003bff8  imul    rcx, rax, 38h ; '8'
0x18003bffc  mov     rax, cs:gWfpGlobal
0x18003c003  mov     rax, [rcx+rax+0A0h]
0x18003c00b  mov     rcx, [r8+r9*8]
0x18003c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c014  mov     rbx, rax
0x18003c017  test    rax, rax
0x18003c01a  jnz     loc_18003C0A0
0x18003c020  mov     eax, cs:Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState
0x18003c026  test    al, 10h
0x18003c028  jz      short loc_18003C02F
0x18003c02a  and     eax, 1
0x18003c02d  jmp     short loc_18003C034
0x18003c02f  call    Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline
0x18003c034  test    eax, eax
0x18003c036  jz      short loc_18003C04A
0x18003c038  call    AreAllIpv4InLayersEmpty
0x18003c03d  mov     rcx, cs:gWfpGlobal
0x18003c044  mov     [rcx+434h], al
0x18003c04a  lea     rcx, gLayerStatsLock; lpCriticalSection
0x18003c051  call    cs:__imp_EnterCriticalSection
0x18003c058  nop     dword ptr [rax+rax+00h]
0x18003c05d  mov     rax, [rdi+50h]
0x18003c061  lea     rcx, gLayerStatsLock; lpCriticalSection
0x18003c068  sub     [rsi+88h], rax
0x18003c06f  lock dec dword ptr [rsi+98h]
0x18003c076  call    cs:__imp_LeaveCriticalSection
0x18003c07d  nop     dword ptr [rax+rax+00h]
0x18003c082  mov     rdx, r15
0x18003c085  movzx   ecx, r14w
0x18003c089  call    RemoveFilterFromFilterHashtable
0x18003c08e  mov     rbx, rax
0x18003c091  test    rax, rax
0x18003c094  jnz     short loc_18003C0A0
0x18003c096  xor     edx, edx
0x18003c098  mov     rcx, rdi
0x18003c09b  call    HandleFilterDeref
0x18003c0a0  test    rdi, rdi
0x18003c0a3  jz      short loc_18003C0AF
0x18003c0a5  xor     edx, edx
0x18003c0a7  mov     rcx, rdi
0x18003c0aa  call    HandleFilterDeref
0x18003c0af  test    rbx, rbx
0x18003c0b2  jz      short loc_18003C0C3
0x18003c0b4  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x18003c0bb  mov     rcx, rbx
0x18003c0be  call    WfpReportError
0x18003c0c3  mov     rax, rbx
0x18003c0c6  add     rsp, 60h
0x18003c0ca  pop     r15
0x18003c0cc  pop     r14
0x18003c0ce  pop     r12
0x18003c0d0  pop     rdi
0x18003c0d1  pop     rsi
0x18003c0d2  pop     rbp
0x18003c0d3  pop     rbx
0x18003c0d4  retn
```
