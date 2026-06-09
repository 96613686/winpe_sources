# NcaEvCollInsideOutsideCollect(void *,void *,void *,void *)

- ea: `0x180010350`
- end: `0x18001041d`
- name: `?NcaEvCollInsideOutsideCollect@@YAXPEAX000@Z`
- size: `205`
- prototype: `void __fastcall(void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002310`
- `0x180004f04`
- `0x18000c978`
- `0x180010350`
- `0x180016678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010392`

## pseudocode

```c
void __fastcall NcaEvCollInsideOutsideCollect(void *a1, void *a2, void *a3, void *a4)
{
  int v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  unsigned int v6; // eax

  v4 = (int)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_771a672108da301c4352a042022c0f91_Traceguids);
  EnterCriticalSection(&stru_180028FB0);
  v5 = gNcaEvCollInOut;
  if ( v4 )
    v5 = qword_180028FA8;
  NcaSrcLnkdTriggerRearm(v5);
  v6 = NcaNlmTriggerGetCurrentProfiles() & 1;
  if ( v6 != dword_180028FE0 )
  {
    dword_180028FE0 = v6;
    NcaDAPEvidenceSnapshotSetGlobalState(4, v6);
  }
  LeaveCriticalSection(&stru_180028FB0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_771a672108da301c4352a042022c0f91_Traceguids);
}

```

## disassembly

```asm
0x180010350  mov     [rsp+arg_0], rbx
0x180010355  push    rdi
0x180010356  sub     rsp, 20h
0x18001035a  mov     rbx, rdx
0x18001035d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010364  lea     rdi, WPP_GLOBAL_Control
0x18001036b  cmp     rcx, rdi
0x18001036e  jz      short loc_18001038B
0x180010370  test    byte ptr [rcx+1Ch], 8
0x180010374  jz      short loc_18001038B
0x180010376  mov     rcx, [rcx+10h]
0x18001037a  lea     r8, WPP_771a672108da301c4352a042022c0f91_Traceguids
0x180010381  mov     edx, 12h
0x180010386  call    WPP_SF_
0x18001038b  lea     rcx, stru_180028FB0; lpCriticalSection
0x180010392  call    cs:__imp_EnterCriticalSection
0x180010399  nop     dword ptr [rax+rax+00h]
0x18001039e  mov     rcx, cs:?gNcaEvCollInOut@@3UNCA_EVCOLL_INOUT_COMPONENT_@@A; NCA_EVCOLL_INOUT_COMPONENT_ gNcaEvCollInOut
0x1800103a5  test    ebx, ebx
0x1800103a7  jz      short loc_1800103B0
0x1800103a9  mov     rcx, cs:qword_180028FA8
0x1800103b0  call    NcaSrcLnkdTriggerRearm
0x1800103b5  call    NcaNlmTriggerGetCurrentProfiles
0x1800103ba  and     eax, 1
0x1800103bd  cmp     eax, cs:dword_180028FE0
0x1800103c3  jz      short loc_1800103D7
0x1800103c5  mov     edx, eax
0x1800103c7  mov     cs:dword_180028FE0, eax
0x1800103cd  mov     ecx, 4
0x1800103d2  call    NcaDAPEvidenceSnapshotSetGlobalState
0x1800103d7  lea     rcx, stru_180028FB0; lpCriticalSection
0x1800103de  call    cs:__imp_LeaveCriticalSection
0x1800103e5  nop     dword ptr [rax+rax+00h]
0x1800103ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103f1  cmp     rcx, rdi
0x1800103f4  jz      short loc_180010411
0x1800103f6  test    byte ptr [rcx+1Ch], 8
0x1800103fa  jz      short loc_180010411
0x1800103fc  mov     rcx, [rcx+10h]
0x180010400  lea     r8, WPP_771a672108da301c4352a042022c0f91_Traceguids
0x180010407  mov     edx, 13h
0x18001040c  call    WPP_SF_
0x180010411  mov     rbx, [rsp+28h+arg_0]
0x180010416  add     rsp, 20h
0x18001041a  pop     rdi
0x18001041b  retn
```
