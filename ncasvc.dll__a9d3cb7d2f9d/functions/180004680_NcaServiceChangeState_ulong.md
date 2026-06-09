# NcaServiceChangeState(ulong)

- ea: `0x180004680`
- end: `0x18000476b`
- name: `?NcaServiceChangeState@@YAJK@Z`
- size: `235`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800026d0`
- `0x180004400`
- `0x180004780`
- `0x180004984`

## callees

- `0x1800024b0`
- `0x1800033bc`
- `0x180004680`
- `0x180004f04`
- `0x180004f34`

## string_xrefs

- `0x1800046fc`: `NcaServiceChangeState`
- `0x180004738`: `NcaServiceChangeState`

## pseudocode

```c
__int64 __fastcall NcaServiceChangeState(DWORD a1)
{
  unsigned int v2; // edi
  PVOID *v3; // rcx
  DWORD v4; // ebx
  DWORD v5; // ebx
  DWORD v6; // ebx
  int v7; // eax

  v2 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ServiceStatus.dwCurrentState != a1 )
  {
    ServiceStatus.dwCurrentState = a1;
    v4 = a1 - 1;
    if ( !v4 )
      goto LABEL_9;
    v5 = v4 - 1;
    if ( !v5 || (v6 = v5 - 1) == 0 )
    {
      ServiceStatus.dwWaitHint = 30000;
      ServiceStatus.dwCheckPoint = 0;
      goto LABEL_10;
    }
    if ( v6 == 1 )
LABEL_9:
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
LABEL_10:
    v7 = NcaServiceSetStatus();
    v2 = v7;
    if ( v7 < 0 )
      NcaReportReturnError("NcaServiceChangeState", (unsigned int)v7);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 28, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids, v2);
  if ( (v2 & 0x80000000) != 0 )
    return (unsigned int)NcaReportReturnError("NcaServiceChangeState", v2);
  return v2;
}

```

## disassembly

```asm
0x180004680  mov     [rsp+arg_0], rbx
0x180004685  mov     [rsp+arg_8], rbp
0x18000468a  push    rdi
0x18000468b  sub     rsp, 20h
0x18000468f  mov     ebx, ecx
0x180004691  xor     edi, edi
0x180004693  mov     rcx, cs:WPP_GLOBAL_Control
0x18000469a  lea     rbp, WPP_GLOBAL_Control
0x1800046a1  cmp     rcx, rbp
0x1800046a4  jz      short loc_1800046C6
0x1800046a6  test    byte ptr [rcx+1Ch], 8
0x1800046aa  jz      short loc_1800046C6
0x1800046ac  mov     rcx, [rcx+10h]
0x1800046b0  lea     edx, [rdi+1Bh]
0x1800046b3  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800046ba  call    WPP_SF_
0x1800046bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046c6  cmp     cs:ServiceStatus.dwCurrentState, ebx
0x1800046cc  jz      short loc_18000470F
0x1800046ce  mov     cs:ServiceStatus.dwCurrentState, ebx
0x1800046d4  sub     ebx, 1
0x1800046d7  jz      short loc_1800046E8
0x1800046d9  sub     ebx, 1
0x1800046dc  jz      short loc_180004759
0x1800046de  sub     ebx, 1
0x1800046e1  jz      short loc_180004759
0x1800046e3  cmp     ebx, 1
0x1800046e6  jnz     short loc_1800046EF
0x1800046e8  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rdi
0x1800046ef  call    ?NcaServiceSetStatus@@YAJXZ; NcaServiceSetStatus(void)
0x1800046f4  mov     edi, eax
0x1800046f6  test    eax, eax
0x1800046f8  jns     short loc_180004708
0x1800046fa  mov     edx, eax
0x1800046fc  lea     rcx, aNcaservicechan; "NcaServiceChangeState"
0x180004703  call    NcaReportReturnError
0x180004708  mov     rcx, cs:WPP_GLOBAL_Control
0x18000470f  cmp     rcx, rbp
0x180004712  jz      short loc_180004732
0x180004714  test    byte ptr [rcx+1Ch], 8
0x180004718  jz      short loc_180004732
0x18000471a  mov     rcx, [rcx+10h]
0x18000471e  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004725  mov     edx, 1Ch
0x18000472a  mov     r9d, edi
0x18000472d  call    WPP_SF_d
0x180004732  test    edi, edi
0x180004734  jns     short loc_180004746
0x180004736  mov     edx, edi
0x180004738  lea     rcx, aNcaservicechan; "NcaServiceChangeState"
0x18000473f  call    NcaReportReturnError
0x180004744  mov     edi, eax
0x180004746  mov     rbx, [rsp+28h+arg_0]
0x18000474b  mov     eax, edi
0x18000474d  mov     rbp, [rsp+28h+arg_8]
0x180004752  add     rsp, 20h
0x180004756  pop     rdi
0x180004757  retn
0x180004759  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x180004763  mov     cs:ServiceStatus.dwCheckPoint, edi
0x180004769  jmp     short loc_1800046EF
```
