# NcaEvCollHttpProbeCollectAsyncComplete(NCA_EVCOLL_PROBE_ *,ulong)

- ea: `0x180010ec4`
- end: `0x180010ff9`
- name: `?NcaEvCollHttpProbeCollectAsyncComplete@@YAXPEAUNCA_EVCOLL_PROBE_@@K@Z`
- size: `309`
- prototype: `void __fastcall(struct NCA_EVCOLL_PROBE_ *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001400`
- `0x180002fd0`

## callees

- `0x1800025c0`
- `0x180003720`
- `0x180004f34`
- `0x180010ec4`
- `0x180012740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010eed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010eed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f03`

## pseudocode

```c
void __fastcall NcaEvCollHttpProbeCollectAsyncComplete(struct NCA_EVCOLL_PROBE_ *a1, int a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // edx
  int v7; // ecx
  unsigned int TestType; // esi
  int v9; // ebp
  unsigned int v10; // edi
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 1;
  WaitForSingleObject(*((HANDLE *)a1 + 48), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
  if ( a2 == 12017 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 58;
LABEL_5:
      WPP_SF_d(v4[2], v5, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, 0);
    }
  }
  else
  {
    TestType = NcaEvCollProbeGetTestType(*(unsigned int *)(*((_QWORD *)a1 + 4) + 32LL), &v11);
    if ( TestType == 1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && ((unsigned __int8)TestType & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0 )
      {
        v5 = TestType + 58;
        goto LABEL_5;
      }
    }
    else
    {
      if ( TestType == 3 || a2 )
      {
        v10 = *((_DWORD *)a1 + 56);
        v9 = 1;
      }
      else
      {
        v9 = 0;
        v10 = 2;
      }
      if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
        McTemplateU0qzq_EventWriteTransfer(v7, v6, 3, *((_QWORD *)a1 + 1), v10);
      NcaEvCollHttpProbeCollectUpdateEvidence(a1, v11, TestType, v10, v9);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
}

```

## disassembly

```asm
0x180010ec4  mov     [rsp+arg_0], rbx
0x180010ec9  mov     [rsp+arg_10], rbp
0x180010ece  push    rsi
0x180010ecf  push    rdi
0x180010ed0  push    r14
0x180010ed2  sub     rsp, 30h
0x180010ed6  mov     edi, edx
0x180010ed8  mov     [rsp+48h+arg_8], 1
0x180010ee0  mov     rbx, rcx
0x180010ee3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010ee6  mov     rcx, [rcx+180h]; hHandle
0x180010eed  call    cs:__imp_WaitForSingleObject
0x180010ef4  nop     dword ptr [rax+rax+00h]
0x180010ef9  lea     r14, [rbx+0E8h]
0x180010f00  mov     rcx, r14; lpCriticalSection
0x180010f03  call    cs:__imp_EnterCriticalSection
0x180010f0a  nop     dword ptr [rax+rax+00h]
0x180010f0f  cmp     edi, 2EF1h
0x180010f15  jnz     short loc_180010F55
0x180010f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f1e  lea     rax, WPP_GLOBAL_Control
0x180010f25  cmp     rcx, rax
0x180010f28  jz      loc_180010FD8
0x180010f2e  test    byte ptr [rcx+1Ch], 1
0x180010f32  jz      loc_180010FD8
0x180010f38  mov     edx, 3Ah ; ':'
0x180010f3d  mov     rcx, [rcx+10h]
0x180010f41  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180010f48  xor     r9d, r9d
0x180010f4b  call    WPP_SF_d
0x180010f50  jmp     loc_180010FD8
0x180010f55  mov     rcx, [rbx+20h]
0x180010f59  lea     rdx, [rsp+48h+arg_8]
0x180010f5e  mov     ecx, [rcx+20h]
0x180010f61  call    ?NcaEvCollProbeGetTestType@@YA?AW4NCA_PROBE_TEST_TYPE_@@KPEAH@Z; NcaEvCollProbeGetTestType(ulong,int *)
0x180010f66  mov     esi, eax
0x180010f68  cmp     eax, 1
0x180010f6b  jnz     short loc_180010F8B
0x180010f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f74  lea     rax, WPP_GLOBAL_Control
0x180010f7b  cmp     rcx, rax
0x180010f7e  jz      short loc_180010FD8
0x180010f80  test    [rcx+1Ch], sil
0x180010f84  jz      short loc_180010FD8
0x180010f86  lea     edx, [rsi+3Ah]
0x180010f89  jmp     short loc_180010F3D
0x180010f8b  mov     r8d, 3
0x180010f91  cmp     esi, r8d
0x180010f94  jz      short loc_180010FA1
0x180010f96  test    edi, edi
0x180010f98  jnz     short loc_180010FA1
0x180010f9a  xor     ebp, ebp
0x180010f9c  lea     edi, [rbp+2]
0x180010f9f  jmp     short loc_180010FAC
0x180010fa1  mov     edi, [rbx+0E0h]
0x180010fa7  mov     ebp, 1
0x180010fac  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180010fb3  jz      short loc_180010FC2
0x180010fb5  mov     r9, [rbx+8]
0x180010fb9  mov     [rsp+48h+var_28], edi
0x180010fbd  call    McTemplateU0qzq_EventWriteTransfer
0x180010fc2  mov     edx, [rsp+48h+arg_8]
0x180010fc6  mov     r9d, edi
0x180010fc9  mov     r8d, esi
0x180010fcc  mov     [rsp+48h+var_28], ebp
0x180010fd0  mov     rcx, rbx
0x180010fd3  call    ?NcaEvCollHttpProbeCollectUpdateEvidence@@YAXPEAUNCA_EVCOLL_PROBE_@@HW4NCA_PROBE_TEST_TYPE_@@W4NCA_EVCOLL_PROBE_PRV_RESULT_@@H@Z; NcaEvCollHttpProbeCollectUpdateEvidence(NCA_EVCOLL_PROBE_ *,int,NCA_PROBE_TEST_TYPE_,NCA_EVCOLL_PROBE_PRV_RESULT_,int)
0x180010fd8  mov     rcx, r14
0x180010fdb  mov     rbx, [rsp+48h+arg_0]
0x180010fe0  mov     rbp, [rsp+48h+arg_10]
0x180010fe5  add     rsp, 30h
0x180010fe9  pop     r14
0x180010feb  pop     rdi
0x180010fec  pop     rsi
0x180010fed  jmp     cs:__imp_LeaveCriticalSection
```
